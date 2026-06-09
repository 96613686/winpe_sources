# Microsoft.Crm.WebServices.OfflineSync::ProcessRequest

- ea: `0xf490`
- end: `0xf556`
- name: `Microsoft.Crm.WebServices.OfflineSync::ProcessRequest`
- size: `198`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xf490`
- `0xf5f0`
- `0xf770`
- `0xf870`

## string_xrefs

- `0xf4ef`: `Exception during BCP file writing in response. Details: {0}`
- `0xf521`: `ProcessRequest() completed with stepWasCompleted={0} for bcpFile={1}.`

## pseudocode

```c

```

## disassembly

```asm
0xf490  ldarg.1
0xf491  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0xf496  stloc.0
0xf497  ldarg.0
0xf498  ldarg.1
0xf499  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth Microsoft.Crm.WebServices.OfflineSync::CreateUserAuth(class [System.Web]System.Web.HttpContext context)
0xf49e  stloc.1
0xf49f  ldarg.0
0xf4a0  ldarg.1
0xf4a1  ldloc.1
0xf4a2  call     instance void Microsoft.Crm.WebServices.OfflineSync::GenerateSyncData(class [System.Web]System.Web.HttpContext context, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth currentUserAuth)
0xf4a7  ldarg.0
0xf4a8  ldloc.1
0xf4a9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xf4ae  call     instance unsigned int8[] Microsoft.Crm.WebServices.OfflineSync::CreateBcpFileAndAddHeader(valuetype [mscorlib]System.Guid organizationId)
0xf4b3  stloc.2
0xf4b4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0xf4b9  stloc.3
0xf4ba  ldc.i4.0
0xf4bb  stloc.s  4
0xf4bd  ldloc.0
0xf4be  ldloc.2
0xf4bf  callvirt instance void [System.Web]System.Web.HttpResponse::BinaryWrite(unsigned int8[])
0xf4c4  ldarg.0
0xf4c5  ldfld    int32 Microsoft.Crm.WebServices.OfflineSync::hResult
0xf4ca  brtrue.s loc_F4D8
0xf4cc  ldloc.0
0xf4cd  ldarg.0
0xf4ce  ldfld    string Microsoft.Crm.WebServices.OfflineSync::bcpFilePath
0xf4d3  callvirt instance void [System.Web]System.Web.HttpResponse::WriteFile(string)
0xf4d8  ldloc.0
0xf4d9  callvirt instance void [System.Web]System.Web.HttpResponse::Flush()
0xf4de  ldc.i4.1
0xf4df  stloc.s  4
0xf4e1  leave.s  loc_F555
0xf4e3  stloc.s  5
0xf4e5  ldloc.s  5
0xf4e7  ldloc.1
0xf4e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xf4ed  ldc.i4.s 0x14
0xf4ef  ldstr    aExceptionDurin// "Exception during BCP file writing in re"...
0xf4f4  ldc.i4.1
0xf4f5  newarr   [mscorlib]System.Object
0xf4fa  dup
0xf4fb  ldc.i4.0
0xf4fc  ldloc.s  5
0xf4fe  stelem.ref
0xf4ff  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf504  rethrow
0xf506  ldarg.0
0xf507  ldfld    class [mscorlib]System.IO.FileInfo Microsoft.Crm.WebServices.OfflineSync::bcpFile
0xf50c  brfalse.s loc_F519
0xf50e  ldarg.0
0xf50f  ldfld    class [mscorlib]System.IO.FileInfo Microsoft.Crm.WebServices.OfflineSync::bcpFile
0xf514  callvirt instance void [mscorlib]System.IO.FileSystemInfo::Delete()
0xf519  ldloc.1
0xf51a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xf51f  ldc.i4.s 0x14
0xf521  ldstr    aProcessrequest// "ProcessRequest() completed with stepWas"...
0xf526  ldc.i4.2
0xf527  newarr   [mscorlib]System.Object
0xf52c  dup
0xf52d  ldc.i4.0
0xf52e  ldloc.s  4
0xf530  box      [mscorlib]System.Boolean
0xf535  stelem.ref
0xf536  dup
0xf537  ldc.i4.1
0xf538  ldarg.0
0xf539  ldfld    string Microsoft.Crm.WebServices.OfflineSync::bcpFilePath
0xf53e  stelem.ref
0xf53f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf544  ldloc.0
0xf545  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0xf54a  endfinally
0xf54b  ldloc.3
0xf54c  brfalse.s loc_F554
0xf54e  ldloc.3
0xf54f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf554  endfinally
0xf555  ret
```
