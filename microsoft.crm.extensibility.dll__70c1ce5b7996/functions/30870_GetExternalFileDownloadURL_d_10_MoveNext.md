# <GetExternalFileDownloadURL>d__10::MoveNext

- ea: `0x30870`
- end: `0x30927`
- name: `<GetExternalFileDownloadURL>d__10::MoveNext`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0xd0d0`
- `0xd0f0`
- `0xd110`
- `0x24ed0`
- `0x24f30`
- `0x30870`

## string_xrefs

- `0x308a3`: `prvCreateEntity`

## pseudocode

```c

```

## disassembly

```asm
0x30870  ldarg.0
0x30871  ldfld    int32 <GetExternalFileDownloadURL>d__10::<>1__state
0x30876  stloc.0
0x30877  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationContext()
0x3087c  stloc.2
0x3087d  ldloc.2
0x3087e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x30883  ldc.i4.0
0x30884  ldc.i4.0
0x30885  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x3088a  stloc.3
0x3088b  ldloc.3
0x3088c  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetCurrentUserId()
0x30891  ldc.i4.0
0x30892  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x30897  ldloc.3
0x30898  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x3089d  ldloc.2
0x3089e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x308a3  ldstr    aPrvcreateentit// "prvCreateEntity"
0x308a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetPrivilege(string)
0x308ad  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x308b2  ldloc.3
0x308b3  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x308b8  ldarg.0
0x308b9  ldfld    class Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata <GetExternalFileDownloadURL>d__10::metadata
0x308be  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata::get_AttachmentId()
0x308c3  ldarg.0
0x308c4  ldfld    class Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata <GetExternalFileDownloadURL>d__10::metadata
0x308c9  callvirt instance int32 Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata::get_AttachmentType()
0x308ce  ldarg.0
0x308cf  ldfld    class Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata <GetExternalFileDownloadURL>d__10::metadata
0x308d4  callvirt instance string Microsoft.Crm.Extensibility.StorageService.DownloadRequestMetadata::get_FileName()
0x308d9  ldloc.3
0x308da  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExternalStorage.DownloadService::DownloadSASURI(valuetype [mscorlib]System.Guid, int32, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x308df  stloc.1
0x308e0  leave.s  loc_30912
0x308e2  pop
0x308e3  ldloc.3
0x308e4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x308e9  rethrow
0x308eb  ldloc.0
0x308ec  ldc.i4.0
0x308ed  bge.s    loc_308F8
0x308ef  ldloc.3
0x308f0  brfalse.s loc_308F8
0x308f2  ldloc.3
0x308f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x308f8  endfinally
0x308f9  stloc.s  4
0x308fb  ldarg.0
0x308fc  ldc.i4.s 0xFE
0x308fe  stfld    int32 <GetExternalFileDownloadURL>d__10::<>1__state
0x30903  ldarg.0
0x30904  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetExternalFileDownloadURL>d__10::<>t__builder
0x30909  ldloc.s  4
0x3090b  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetException(class [mscorlib]System.Exception)
0x30910  leave.s  loc_30926
0x30912  ldarg.0
0x30913  ldc.i4.s 0xFE
0x30915  stfld    int32 <GetExternalFileDownloadURL>d__10::<>1__state
0x3091a  ldarg.0
0x3091b  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string> <GetExternalFileDownloadURL>d__10::<>t__builder
0x30920  ldloc.1
0x30921  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<string>::SetResult(var<u1>)
0x30926  ret
```
