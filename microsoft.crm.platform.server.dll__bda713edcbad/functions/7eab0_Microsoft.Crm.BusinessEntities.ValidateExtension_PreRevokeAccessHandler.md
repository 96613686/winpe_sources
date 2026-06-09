# Microsoft.Crm.BusinessEntities.ValidateExtension::PreRevokeAccessHandler

- ea: `0x7eab0`
- end: `0x7eba9`
- name: `Microsoft.Crm.BusinessEntities.ValidateExtension::PreRevokeAccessHandler`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x61160`
- `0x61180`
- `0x688a0`
- `0x68910`
- `0x68960`
- `0x7eab0`

## string_xrefs

- `0x7eab7`: `Revoke Access operation is not valid when offline`
- `0x7eb0e`: `revokeTarget not passed to Revoke Access method`
- `0x7eb7f`: `Invalid Principal type passed to Revoke Access. Must be a SystemUser or a Team, revokeTargetType: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7eab0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x7eab5  brfalse.s loc_7EAC7
0x7eab7  ldstr    aRevokeAccessOp// "Revoke Access operation is not valid wh"...
0x7eabc  ldc.i4   0x8004410E
0x7eac1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7eac6  throw
0x7eac7  ldarg.2
0x7eac8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Moniker()
0x7eacd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x7ead2  stloc.0
0x7ead3  ldloc.0
0x7ead4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsUserOwned()
0x7ead9  brtrue.s loc_7EB04
0x7eadb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7eae0  ldstr    aShareMethodsAr// "Share methods are invalid for entities "...
0x7eae5  ldc.i4.1
0x7eae6  newarr   [mscorlib]System.Object
0x7eaeb  dup
0x7eaec  ldc.i4.0
0x7eaed  ldloc.0
0x7eaee  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x7eaf3  stelem.ref
0x7eaf4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7eaf9  ldc.i4   0x8004023B
0x7eafe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7eb03  throw
0x7eb04  ldarg.2
0x7eb05  callvirt instance class Microsoft.Crm.BusinessEntities.SecurityPrincipal Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Principal()
0x7eb0a  stloc.1
0x7eb0b  ldloc.1
0x7eb0c  brtrue.s loc_7EB19
0x7eb0e  ldstr    aRevoketargetNo// "revokeTarget not passed to Revoke Acces"...
0x7eb13  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x7eb18  throw
0x7eb19  ldloc.1
0x7eb1a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_PrincipalId()
0x7eb1f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7eb24  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7eb29  brfalse.s loc_7EB36
0x7eb2b  ldstr    aRevoketargetPr// "revokeTarget PrincipalId is empty guid"
0x7eb30  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x7eb35  throw
0x7eb36  ldloc.1
0x7eb37  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x7eb3c  ldarg.2
0x7eb3d  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7eb42  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7eb47  ldstr    aSystemuser_0// "SystemUser"
0x7eb4c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x7eb51  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7eb56  beq.s    loc_7EBA8
0x7eb58  ldloc.1
0x7eb59  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x7eb5e  ldarg.2
0x7eb5f  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x7eb64  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7eb69  ldstr    aTeam// "Team"
0x7eb6e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x7eb73  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7eb78  beq.s    loc_7EBA8
0x7eb7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7eb7f  ldstr    aInvalidPrincip_3// "Invalid Principal type passed to Revoke"...
0x7eb84  ldc.i4.1
0x7eb85  newarr   [mscorlib]System.Object
0x7eb8a  dup
0x7eb8b  ldc.i4.0
0x7eb8c  ldloc.1
0x7eb8d  callvirt instance int32 Microsoft.Crm.BusinessEntities.SecurityPrincipal::get_Type()
0x7eb92  box      [mscorlib]System.Int32
0x7eb97  stelem.ref
0x7eb98  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7eb9d  ldc.i4   0x80040203
0x7eba2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x7eba7  throw
0x7eba8  ret
```
