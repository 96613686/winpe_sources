# Microsoft.Xrm.Tools.OwinJobManager.Server.Startup::Configuration

- ea: `0x1250`
- end: `0x1284`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.Startup::Configuration`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0xf60`
- `0x1330`

## pseudocode

```c

```

## disassembly

```asm
0x1250  newobj   instance void [System.Web.Http]System.Web.Http.HttpConfiguration::.ctor()
0x1255  stloc.0
0x1256  ldloc.0
0x1257  newobj   instance void Microsoft.Xrm.Tools.OwinJobManager.Server.CustomDirectRouteProvider::.ctor()
0x125c  call     void [System.Web.Http]System.Web.Http.HttpConfigurationExtensions::MapHttpAttributeRoutes(class [System.Web.Http]System.Web.Http.HttpConfiguration, class [System.Web.Http]System.Web.Http.Routing.IDirectRouteProvider)
0x1261  ldloc.0
0x1262  callvirt instance class [System.Web.Http]System.Web.Http.Controllers.ServicesContainer [System.Web.Http]System.Web.Http.HttpConfiguration::get_Services()
0x1267  ldtoken  [System.Web.Http]System.Web.Http.ExceptionHandling.IExceptionLogger
0x126c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1271  newobj   instance void Microsoft.Xrm.Tools.OwinJobManager.Server.WebapiExceptionLogger::.ctor()
0x1276  callvirt instance void [System.Web.Http]System.Web.Http.Controllers.ServicesContainer::Add(class [mscorlib]System.Type, object)
0x127b  ldarg.1
0x127c  ldloc.0
0x127d  call     class [Owin]Owin.IAppBuilder [System.Web.Http.Owin]Owin.WebApiAppBuilderExtensions::UseWebApi(class [Owin]Owin.IAppBuilder, class [System.Web.Http]System.Web.Http.HttpConfiguration)
0x1282  pop
0x1283  ret
```
