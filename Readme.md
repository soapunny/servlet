## Servlet

```
@WebServlet(name="helloServlet", urlPatterns="/hello")
public class HelloServlet extends HttpsServlet{
    @Override
    protected void service(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        System.out.println("HelloServlet.service");
        System.out.println("request = " + request);
        System.out.println("response = " + response);
        
        String username = request.getParameter("username");
        System.out.println("username = "+username);

        response.setContentType("text/plain");
        response.setCharacterEncoding("utf-8");
        response.getWriter().write("hello " +username);
    }
}
```

* @WebServlet
    * name: name of the servlet</li>
    * urlPatterns: url pattern of the servlet</li>

When the url is called, the service method is called.  
`@Override protected void service(HttpServletRequest request, HttpServletResponse response)`

* Run WebApp
    * http://localhost:8081/hello?username=world
    * result: hello world




