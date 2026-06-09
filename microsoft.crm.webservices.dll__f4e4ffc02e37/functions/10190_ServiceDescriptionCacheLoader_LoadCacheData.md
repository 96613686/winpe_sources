# ServiceDescriptionCacheLoader::LoadCacheData

- ea: `0x10190`
- end: `0x10218`
- name: `ServiceDescriptionCacheLoader::LoadCacheData`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x8850`
- `0x93e0`
- `0x9f90`
- `0x9fa0`
- `0x10190`

## string_xrefs

- `0x101ad`: `Service Description Factory: Loading Metadata.`
- `0x101e3`: `Service Description Factory: Loading Messages from Metadata.`

## pseudocode

```c

```

## disassembly

```asm
0x10190  ldarg.2
0x10191  ldc.i4.0
0x10192  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x10197  stloc.0
0x10198  ldarg.2
0x10199  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1019e  ldc.i4.s 0x1A
0x101a0  ldstr    a0// "{0}"
0x101a5  ldc.i4.1
0x101a6  newarr   [mscorlib]System.Object
0x101ab  dup
0x101ac  ldc.i4.0
0x101ad  ldstr    aServiceDescrip// "Service Description Factory: Loading Me"...
0x101b2  stelem.ref
0x101b3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x101b8  ldarg.2
0x101b9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x101be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_Entities()
0x101c3  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x101c8  newobj   instance void Microsoft.Crm.Sdk.EntityMetadatas::.ctor(class [mscorlib]System.Collections.ICollection entityMetadatas)
0x101cd  stloc.1
0x101ce  ldarg.2
0x101cf  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x101d4  ldc.i4.s 0x1A
0x101d6  ldstr    a0// "{0}"
0x101db  ldc.i4.1
0x101dc  newarr   [mscorlib]System.Object
0x101e1  dup
0x101e2  ldc.i4.0
0x101e3  ldstr    aServiceDescrip_0// "Service Description Factory: Loading Me"...
0x101e8  stelem.ref
0x101e9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x101ee  ldarg.1
0x101ef  newobj   instance void Microsoft.Crm.Sdk.SdkMessagesLoader::.ctor(string targetNamespace)
0x101f4  ldarg.2
0x101f5  callvirt instance class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessages Microsoft.Crm.Sdk.SdkMessagesLoader::GetSdkMessages(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x101fa  stloc.2
0x101fb  ldarg.2
0x101fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x10201  ldarg.1
0x10202  ldloc.2
0x10203  ldloc.1
0x10204  newobj   instance void Microsoft.Crm.Sdk.ServiceDescription::.ctor(valuetype [mscorlib]System.Guid organizationId, string targetNamespace, class [Microsoft.Crm.Extensibility]Microsoft.Crm.Sdk.SdkMessages sdkMessages, class Microsoft.Crm.Sdk.EntityMetadatas entityMetadatas)
0x10209  stloc.3
0x1020a  leave.s  loc_10216
0x1020c  ldloc.0
0x1020d  brfalse.s loc_10215
0x1020f  ldloc.0
0x10210  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10215  endfinally
0x10216  ldloc.3
0x10217  ret
```
