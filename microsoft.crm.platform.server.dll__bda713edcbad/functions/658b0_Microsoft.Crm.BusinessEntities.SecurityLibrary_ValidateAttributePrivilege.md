# Microsoft.Crm.BusinessEntities.SecurityLibrary::ValidateAttributePrivilege

- ea: `0x658b0`
- end: `0x6598a`
- name: `Microsoft.Crm.BusinessEntities.SecurityLibrary::ValidateAttributePrivilege`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x657f0`

## callees

- `0x658b0`

## string_xrefs

- `0x65918`: `Secured attribute '{0}' with Id {1} can not be secured for read`
- `0x6595b`: `Secured attribute '{0}' with Id {1} can not be secured for update`

## pseudocode

```c

```

## disassembly

```asm
0x658b0  ldarg.2
0x658b1  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x658b6  ldarg.1
0x658b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x658bc  ldarg.0
0x658bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilege::get_AttributeId()
0x658c2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(valuetype [mscorlib]System.Guid)
0x658c7  stloc.0
0x658c8  ldloc.0
0x658c9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x658ce  brtrue.s loc_65902
0x658d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x658d5  ldstr    aNotSecuredAttr// "Not secured attribute '{0}' with Id {1}"
0x658da  ldc.i4.2
0x658db  newarr   [mscorlib]System.Object
0x658e0  dup
0x658e1  ldc.i4.0
0x658e2  ldloc.0
0x658e3  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x658e8  stelem.ref
0x658e9  dup
0x658ea  ldc.i4.1
0x658eb  ldloc.0
0x658ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x658f1  box      [mscorlib]System.Guid
0x658f6  stelem.ref
0x658f7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x658fc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x65901  throw
0x65902  ldloc.0
0x65903  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForRead()
0x65908  brtrue.s loc_65945
0x6590a  ldarg.0
0x6590b  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilege::get_CanRead()
0x65910  ldc.i4.4
0x65911  bne.un.s loc_65945
0x65913  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x65918  ldstr    aSecuredAttribu_0// "Secured attribute '{0}' with Id {1} can"...
0x6591d  ldc.i4.2
0x6591e  newarr   [mscorlib]System.Object
0x65923  dup
0x65924  ldc.i4.0
0x65925  ldloc.0
0x65926  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x6592b  stelem.ref
0x6592c  dup
0x6592d  ldc.i4.1
0x6592e  ldloc.0
0x6592f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x65934  box      [mscorlib]System.Guid
0x65939  stelem.ref
0x6593a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6593f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x65944  throw
0x65945  ldloc.0
0x65946  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_CanBeSecuredForUpdate()
0x6594b  brtrue.s loc_65988
0x6594d  ldarg.0
0x6594e  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributePrivilege::get_CanUpdate()
0x65953  ldc.i4.4
0x65954  bne.un.s loc_65988
0x65956  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6595b  ldstr    aSecuredAttribu_1// "Secured attribute '{0}' with Id {1} can"...
0x65960  ldc.i4.2
0x65961  newarr   [mscorlib]System.Object
0x65966  dup
0x65967  ldc.i4.0
0x65968  ldloc.0
0x65969  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x6596e  stelem.ref
0x6596f  dup
0x65970  ldc.i4.1
0x65971  ldloc.0
0x65972  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Id()
0x65977  box      [mscorlib]System.Guid
0x6597c  stelem.ref
0x6597d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x65982  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x65987  throw
0x65988  ldloc.0
0x65989  ret
```
