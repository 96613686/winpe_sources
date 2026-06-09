# Microsoft.Crm.Sdk.Metadata2006.EntityMetadata::LoadPrivileges

- ea: `0xd360`
- end: `0xd3be`
- name: `Microsoft.Crm.Sdk.Metadata2006.EntityMetadata::LoadPrivileges`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xcf00`

## callees

- `0xd360`
- `0xd3f0`
- `0xd410`
- `0xd430`
- `0xd440`

## pseudocode

```c

```

## disassembly

```asm
0xd360  ldc.i4.0
0xd361  stloc.0
0xd362  br.s     loc_D3AF
0xd364  ldarg.1
0xd365  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPrivilegeCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrivilegesByType()
0xd36a  ldloc.0
0xd36b  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataArrayList`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege>::get_Item(!!T0)
0xd370  stloc.1
0xd371  ldloc.1
0xd372  brfalse.s loc_D3AB
0xd374  newobj   instance void Microsoft.Crm.Sdk.Metadata2006.SecurityPrivilege::.ctor()
0xd379  stloc.2
0xd37a  ldloc.2
0xd37b  ldloc.1
0xd37c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0xd381  callvirt instance void Microsoft.Crm.Sdk.Metadata2006.SecurityPrivilege::set_PrivilegeId(valuetype [mscorlib]System.Guid value)
0xd386  ldloc.2
0xd387  ldloc.1
0xd388  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_PrivilegeType()
0xd38d  callvirt instance void Microsoft.Crm.Sdk.Metadata2006.SecurityPrivilege::set_PrivilegeType(valuetype Microsoft.Crm.Sdk.Metadata2006.PrivilegeType value)
0xd392  ldloc.2
0xd393  ldloc.1
0xd394  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Name()
0xd399  callvirt instance void Microsoft.Crm.Sdk.Metadata2006.SecurityPrivilege::set_Name(string value)
0xd39e  ldarg.0
0xd39f  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Sdk.Metadata2006.EntityMetadata::privileges
0xd3a4  ldloc.2
0xd3a5  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xd3aa  pop
0xd3ab  ldloc.0
0xd3ac  ldc.i4.1
0xd3ad  add
0xd3ae  stloc.0
0xd3af  ldloc.0
0xd3b0  ldarg.1
0xd3b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IPrivilegeCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrivilegesByType()
0xd3b6  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0xd3bb  blt.s    loc_D364
0xd3bd  ret
```
