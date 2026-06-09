# Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParsePrivilegeRulePart

- ea: `0x4f2d0`
- end: `0x4f3bf`
- name: `Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParsePrivilegeRulePart`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x4f2d0`

## string_xrefs

- `0x4f2f4`: `PrivilegeDepth`
- `0x4f305`: `PrivilegeType`
- `0x4f35b`: `Delete`
- `0x4f367`: `DeletePrivilege`

## pseudocode

```c

```

## disassembly

```asm
0x4f2d0  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeRulePart::.ctor()
0x4f2d5  stloc.0
0x4f2d6  ldloc.0
0x4f2d7  ldc.i4.6
0x4f2d8  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart::RuleType
0x4f2dd  ldloc.0
0x4f2de  ldarg.0
0x4f2df  ldstr    aEntityname// "EntityName"
0x4f2e4  ldsfld   string [mscorlib]System.String::Empty
0x4f2e9  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4f2ee  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.EntityLogicalNameRulePart::EntityLogicalName
0x4f2f3  ldarg.0
0x4f2f4  ldstr    aPrivilegedepth// "PrivilegeDepth"
0x4f2f9  ldsfld   string [mscorlib]System.String::Empty
0x4f2fe  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4f303  stloc.1
0x4f304  ldarg.0
0x4f305  ldstr    aPrivilegetype_0// "PrivilegeType"
0x4f30a  ldsfld   string [mscorlib]System.String::Empty
0x4f30f  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4f314  stloc.2
0x4f315  ldarg.0
0x4f316  ldstr    aAppliesto// "AppliesTo"
0x4f31b  ldsfld   string [mscorlib]System.String::Empty
0x4f320  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4f325  stloc.3
0x4f326  ldloc.1
0x4f327  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f32c  brtrue.s loc_4F34B
0x4f32e  ldloc.0
0x4f32f  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeDepth
0x4f334  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f339  ldloc.1
0x4f33a  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x4f33f  unbox.any [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeDepth
0x4f344  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeDepth [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeRulePart::PrivilegeDepth
0x4f349  br.s     loc_4F352
0x4f34b  ldloc.0
0x4f34c  ldc.i4.m1
0x4f34d  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeDepth [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeRulePart::PrivilegeDepth
0x4f352  ldloc.2
0x4f353  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f358  brtrue.s loc_4F38A
0x4f35a  ldloc.2
0x4f35b  ldstr    aDelete// "Delete"
0x4f360  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4f365  brfalse.s loc_4F36D
0x4f367  ldstr    aDeleteprivileg// "DeletePrivilege"
0x4f36c  stloc.2
0x4f36d  ldloc.0
0x4f36e  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeTypes
0x4f373  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f378  ldloc.2
0x4f379  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x4f37e  unbox.any [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeTypes
0x4f383  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeTypes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeRulePart::PrivilegeType
0x4f388  br.s     loc_4F391
0x4f38a  ldloc.0
0x4f38b  ldc.i4.0
0x4f38c  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeTypes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeRulePart::PrivilegeType
0x4f391  ldloc.3
0x4f392  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f397  brtrue.s loc_4F3B6
0x4f399  ldloc.0
0x4f39a  ldtoken  [Microsoft.Crm]Microsoft.Crm.RuleAppliesTo
0x4f39f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f3a4  ldloc.3
0x4f3a5  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x4f3aa  unbox.any [mscorlib]System.Int32
0x4f3af  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeRulePart::AppliesTo
0x4f3b4  br.s     loc_4F3BD
0x4f3b6  ldloc.0
0x4f3b7  ldc.i4.1
0x4f3b8  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeRulePart::AppliesTo
0x4f3bd  ldloc.0
0x4f3be  ret
```
