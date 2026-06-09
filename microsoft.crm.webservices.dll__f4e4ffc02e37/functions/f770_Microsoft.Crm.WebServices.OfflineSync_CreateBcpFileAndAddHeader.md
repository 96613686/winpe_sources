# Microsoft.Crm.WebServices.OfflineSync::CreateBcpFileAndAddHeader

- ea: `0xf770`
- end: `0xf869`
- name: `Microsoft.Crm.WebServices.OfflineSync::CreateBcpFileAndAddHeader`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xf490`

## callees

- `0xf770`
- `0xf8f0`

## string_xrefs

- `0xf7ba`: `Data file {0} was deleted on server before it was sent to client. Entity '{1}', count rows {2}`
- `0xf801`: `Exception during BCP file header creation. Details: {0}`
- `0xf81a`: `BCP file header creation completed with stepWasCompleted={0} for bcpFile={1}. hResult={2}, fileSize={3}, metadataTimeStamp={4}`

## pseudocode

```c

```

## disassembly

```asm
0xf770  ldc.i4.0
0xf771  stloc.0
0xf772  ldnull
0xf773  stloc.1
0xf774  ldc.i4.0
0xf775  conv.i8
0xf776  stloc.2
0xf777  ldarg.0
0xf778  ldfld    int32 Microsoft.Crm.WebServices.OfflineSync::hResult
0xf77d  brtrue.s loc_F7EA
0xf77f  ldarg.0
0xf780  ldarg.0
0xf781  ldfld    string Microsoft.Crm.WebServices.OfflineSync::bcpFilePath
0xf786  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0xf78b  stfld    class [mscorlib]System.IO.FileInfo Microsoft.Crm.WebServices.OfflineSync::bcpFile
0xf790  ldarg.0
0xf791  ldfld    class [mscorlib]System.IO.FileInfo Microsoft.Crm.WebServices.OfflineSync::bcpFile
0xf796  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0xf79b  brfalse.s loc_F7AB
0xf79d  ldarg.0
0xf79e  ldfld    class [mscorlib]System.IO.FileInfo Microsoft.Crm.WebServices.OfflineSync::bcpFile
0xf7a3  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0xf7a8  stloc.2
0xf7a9  br.s     loc_F7EA
0xf7ab  ldarg.0
0xf7ac  ldc.i4   0x80044229
0xf7b1  stfld    int32 Microsoft.Crm.WebServices.OfflineSync::hResult
0xf7b6  ldnull
0xf7b7  ldarg.1
0xf7b8  ldc.i4.s 0x14
0xf7ba  ldstr    aDataFile0WasDe// "Data file {0} was deleted on server bef"...
0xf7bf  ldc.i4.3
0xf7c0  newarr   [mscorlib]System.Object
0xf7c5  dup
0xf7c6  ldc.i4.0
0xf7c7  ldarg.0
0xf7c8  ldfld    string Microsoft.Crm.WebServices.OfflineSync::bcpFilePath
0xf7cd  stelem.ref
0xf7ce  dup
0xf7cf  ldc.i4.1
0xf7d0  ldarg.0
0xf7d1  ldfld    string Microsoft.Crm.WebServices.OfflineSync::entityName
0xf7d6  stelem.ref
0xf7d7  dup
0xf7d8  ldc.i4.2
0xf7d9  ldarg.0
0xf7da  ldfld    int64 Microsoft.Crm.WebServices.OfflineSync::rowCount
0xf7df  box      [mscorlib]System.Int64
0xf7e4  stelem.ref
0xf7e5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf7ea  ldarg.1
0xf7eb  ldarg.0
0xf7ec  ldfld    int32 Microsoft.Crm.WebServices.OfflineSync::hResult
0xf7f1  ldloc.2
0xf7f2  call     unsigned int8[] Microsoft.Crm.WebServices.OfflineSyncHelper::CreateBcpFileHeader(valuetype [mscorlib]System.Guid organizationId, int32 hResult, int64 fileSize)
0xf7f7  stloc.1
0xf7f8  ldc.i4.1
0xf7f9  stloc.0
0xf7fa  leave.s  loc_F867
0xf7fc  stloc.3
0xf7fd  ldloc.3
0xf7fe  ldarg.1
0xf7ff  ldc.i4.s 0x14
0xf801  ldstr    aExceptionDurin_2// "Exception during BCP file header creati"...
0xf806  ldc.i4.1
0xf807  newarr   [mscorlib]System.Object
0xf80c  dup
0xf80d  ldc.i4.0
0xf80e  ldloc.3
0xf80f  stelem.ref
0xf810  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf815  rethrow
0xf817  ldarg.1
0xf818  ldc.i4.s 0x14
0xf81a  ldstr    aBcpFileHeaderC// "BCP file header creation completed with"...
0xf81f  ldc.i4.5
0xf820  newarr   [mscorlib]System.Object
0xf825  dup
0xf826  ldc.i4.0
0xf827  ldloc.0
0xf828  box      [mscorlib]System.Boolean
0xf82d  stelem.ref
0xf82e  dup
0xf82f  ldc.i4.1
0xf830  ldarg.0
0xf831  ldfld    string Microsoft.Crm.WebServices.OfflineSync::bcpFilePath
0xf836  stelem.ref
0xf837  dup
0xf838  ldc.i4.2
0xf839  ldarg.0
0xf83a  ldfld    int32 Microsoft.Crm.WebServices.OfflineSync::hResult
0xf83f  box      [mscorlib]System.Int32
0xf844  stelem.ref
0xf845  dup
0xf846  ldc.i4.3
0xf847  ldloc.2
0xf848  box      [mscorlib]System.Int64
0xf84d  stelem.ref
0xf84e  dup
0xf84f  ldc.i4.4
0xf850  ldarg.1
0xf851  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xf856  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf85b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0xf860  stelem.ref
0xf861  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf866  endfinally
0xf867  ldloc.1
0xf868  ret
```
