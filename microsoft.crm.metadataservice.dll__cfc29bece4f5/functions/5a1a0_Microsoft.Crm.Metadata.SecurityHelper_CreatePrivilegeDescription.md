# Microsoft.Crm.Metadata.SecurityHelper::CreatePrivilegeDescription

- ea: `0x5a1a0`
- end: `0x5a276`
- name: `Microsoft.Crm.Metadata.SecurityHelper::CreatePrivilegeDescription`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x59df0`

## string_xrefs

- `0x5a1ad`: `privilegeid`
- `0x5a25c`: `accessright`

## pseudocode

```c

```

## disassembly

```asm
0x5a1a0  ldarg.s  0xA
0x5a1a2  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5a1a7  dup
0x5a1a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x5a1ad  ldstr    aPrivilegeid// "privilegeid"
0x5a1b2  ldarg.0
0x5a1b3  box      [mscorlib]System.Guid
0x5a1b8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x5a1bd  dup
0x5a1be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x5a1c3  ldstr    aName// "name"
0x5a1c8  ldarg.1
0x5a1c9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x5a1ce  dup
0x5a1cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x5a1d4  ldstr    aCanbebasic// "canbebasic"
0x5a1d9  ldarg.2
0x5a1da  box      [mscorlib]System.Boolean
0x5a1df  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x5a1e4  dup
0x5a1e5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x5a1ea  ldstr    aCanbelocal// "canbelocal"
0x5a1ef  ldarg.3
0x5a1f0  box      [mscorlib]System.Boolean
0x5a1f5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x5a1fa  dup
0x5a1fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x5a200  ldstr    aCanbedeep// "canbedeep"
0x5a205  ldarg.s  4
0x5a207  box      [mscorlib]System.Boolean
0x5a20c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x5a211  dup
0x5a212  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x5a217  ldstr    aCanbeglobal// "canbeglobal"
0x5a21c  ldarg.s  5
0x5a21e  box      [mscorlib]System.Boolean
0x5a223  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x5a228  dup
0x5a229  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x5a22e  ldstr    aCanbeentityref// "canbeentityreference"
0x5a233  ldarg.s  6
0x5a235  box      [mscorlib]System.Boolean
0x5a23a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x5a23f  dup
0x5a240  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x5a245  ldstr    aCanbeparentent// "canbeparententityreference"
0x5a24a  ldarg.s  7
0x5a24c  box      [mscorlib]System.Boolean
0x5a251  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x5a256  dup
0x5a257  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescriptionPropertyBag::get_InnerEntityData()
0x5a25c  ldstr    aAccessright// "accessright"
0x5a261  ldarg.s  8
0x5a263  box      [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights
0x5a268  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::set_Item(string, object)
0x5a26d  dup
0x5a26e  ldarg.s  9
0x5a270  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeDescription::set_ObjectTypeCode(int32)
0x5a275  ret
```
