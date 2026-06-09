# Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::Remove

- ea: `0x1110`
- end: `0x1131`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2::Remove`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1110`

## pseudocode

```c

```

## disassembly

```asm
0x1110  ldarg.0
0x1111  callvirt instance class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0> class Microsoft.Xrm.Tools.OwinJobManager.Server.JobController`2<var<u1>, !!T0>::get_JobManager()
0x1116  ldarg.1
0x1117  callvirt instance bool class Microsoft.Xrm.Tools.OwinJobManager.Server.JobManager`2<var<u1>, !!T0>::TryRemove(valuetype [mscorlib]System.Guid)
0x111c  brtrue.s loc_1125
0x111e  ldarg.0
0x111f  callvirt instance class [System.Web.Http]System.Web.Http.Results.NotFoundResult [System.Web.Http]System.Web.Http.ApiController::NotFound()
0x1124  ret
0x1125  ldarg.0
0x1126  ldc.i4   0xCC
0x112b  callvirt instance class [System.Web.Http]System.Web.Http.Results.StatusCodeResult [System.Web.Http]System.Web.Http.ApiController::StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x1130  ret
```
