# Microsoft.Crm.Metadata.PrivilegeDescription::FillPropertiesFromXml_0

- ea: `0x3c1f0`
- end: `0x3c315`
- name: `Microsoft.Crm.Metadata.PrivilegeDescription::FillPropertiesFromXml_0`
- size: `293`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18a80`
- `0x3c1f0`
- `0x3c680`
- `0x3c6a0`
- `0x3c6c0`
- `0x3c6e0`
- `0x3c700`
- `0x3c720`
- `0x3c740`
- `0x3c760`
- `0x3c780`
- `0x3c7e0`

## string_xrefs

- `0x3c1f1`: `PrivilegeId`
- `0x3c210`: `PrivilegeId`
- `0x3c2d3`: `AccessRight`
- `0x3c203`: `Privilege XML requires the privilege id`

## pseudocode

```c

```

## disassembly

```asm
0x3c1f0  ldarg.0
0x3c1f1  ldstr    aPrivilegeid_0// "PrivilegeId"
0x3c1f6  ldarg.1
0x3c1f7  ldnull
0x3c1f8  call     T0x2B000065
0x3c1fd  pop
0x3c1fe  ldc.i4.0
0x3c1ff  ldarg.2
0x3c200  and
0x3c201  brfalse.s loc_3C20E
0x3c203  ldstr    aPrivilegeXmlRe// "Privilege XML requires the privilege id"
0x3c208  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x3c20d  throw
0x3c20e  ldarg.0
0x3c20f  ldarg.0
0x3c210  ldstr    aPrivilegeid_0// "PrivilegeId"
0x3c215  ldarg.1
0x3c216  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x3c21b  box      [mscorlib]System.Guid
0x3c220  call     T0x2B000065
0x3c225  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_PrivilegeId(valuetype [mscorlib]System.Guid value)
0x3c22a  ldarg.0
0x3c22b  ldarg.0
0x3c22c  ldstr    aName// "Name"
0x3c231  ldarg.1
0x3c232  ldsfld   string [mscorlib]System.String::Empty
0x3c237  call     T0x2B000066
0x3c23c  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_Name(string value)
0x3c241  ldarg.0
0x3c242  ldarg.0
0x3c243  ldstr    aCanbebasic// "CanBeBasic"
0x3c248  ldarg.1
0x3c249  ldc.i4.1
0x3c24a  box      [mscorlib]System.Boolean
0x3c24f  call     T0x2B000067
0x3c254  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeBasic(bool value)
0x3c259  ldarg.0
0x3c25a  ldarg.0
0x3c25b  ldstr    aCanbelocal// "CanBeLocal"
0x3c260  ldarg.1
0x3c261  ldc.i4.1
0x3c262  box      [mscorlib]System.Boolean
0x3c267  call     T0x2B000067
0x3c26c  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeLocal(bool value)
0x3c271  ldarg.0
0x3c272  ldarg.0
0x3c273  ldstr    aCanbedeep// "CanBeDeep"
0x3c278  ldarg.1
0x3c279  ldc.i4.1
0x3c27a  box      [mscorlib]System.Boolean
0x3c27f  call     T0x2B000067
0x3c284  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeDeep(bool value)
0x3c289  ldarg.0
0x3c28a  ldarg.0
0x3c28b  ldstr    aCanbeglobal// "CanBeGlobal"
0x3c290  ldarg.1
0x3c291  ldc.i4.1
0x3c292  box      [mscorlib]System.Boolean
0x3c297  call     T0x2B000067
0x3c29c  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeGlobal(bool value)
0x3c2a1  ldarg.0
0x3c2a2  ldarg.0
0x3c2a3  ldstr    aCanbeentityref// "CanBeEntityReference"
0x3c2a8  ldarg.1
0x3c2a9  ldc.i4.0
0x3c2aa  box      [mscorlib]System.Boolean
0x3c2af  call     T0x2B000067
0x3c2b4  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeEntityReference(bool value)
0x3c2b9  ldarg.0
0x3c2ba  ldarg.0
0x3c2bb  ldstr    aCanbeparentent// "CanBeParentEntityReference"
0x3c2c0  ldarg.1
0x3c2c1  ldc.i4.0
0x3c2c2  box      [mscorlib]System.Boolean
0x3c2c7  call     T0x2B000067
0x3c2cc  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_CanBeParentEntityReference(bool value)
0x3c2d1  ldarg.0
0x3c2d2  ldarg.0
0x3c2d3  ldstr    aAccessright// "AccessRight"
0x3c2d8  ldarg.1
0x3c2d9  ldc.i4.0
0x3c2da  box      [mscorlib]System.Int32
0x3c2df  call     T0x2B000068
0x3c2e4  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_AccessRight(int32 value)
0x3c2e9  ldarg.0
0x3c2ea  ldarg.0
0x3c2eb  ldstr    aIsmanaged// "IsManaged"
0x3c2f0  ldarg.1
0x3c2f1  ldc.i4.0
0x3c2f2  box      [mscorlib]System.Boolean
0x3c2f7  call     T0x2B000067
0x3c2fc  callvirt instance void Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::set_IsManaged(bool value)
0x3c301  ldarg.0
0x3c302  ldarg.0
0x3c303  ldstr    aIntroducedvers// "IntroducedVersion"
0x3c308  ldarg.1
0x3c309  ldnull
0x3c30a  call     T0x2B000069
0x3c30f  callvirt instance void Microsoft.Crm.Metadata.PrivilegeDescription::set_IntroducedVersion(class [mscorlib]System.Version value)
0x3c314  ret
```
