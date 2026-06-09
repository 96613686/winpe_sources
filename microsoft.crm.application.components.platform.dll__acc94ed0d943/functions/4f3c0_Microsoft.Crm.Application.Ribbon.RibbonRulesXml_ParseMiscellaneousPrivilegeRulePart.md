# Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseMiscellaneousPrivilegeRulePart

- ea: `0x4f3c0`
- end: `0x4f423`
- name: `Microsoft.Crm.Application.Ribbon.RibbonRulesXml::ParseMiscellaneousPrivilegeRulePart`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x4f3c0`

## string_xrefs

- `0x4f3e5`: `PrivilegeDepth`
- `0x4f3d0`: `PrivilegeName`

## pseudocode

```c

```

## disassembly

```asm
0x4f3c0  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.MiscellaneousPrivilegeRulePart::.ctor()
0x4f3c5  stloc.0
0x4f3c6  ldloc.0
0x4f3c7  ldc.i4.s 0xD
0x4f3c9  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RuleType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RulePart::RuleType
0x4f3ce  ldloc.0
0x4f3cf  ldarg.0
0x4f3d0  ldstr    aPrivilegename// "PrivilegeName"
0x4f3d5  ldsfld   string [mscorlib]System.String::Empty
0x4f3da  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4f3df  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.MiscellaneousPrivilegeRulePart::PrivilegeName
0x4f3e4  ldarg.0
0x4f3e5  ldstr    aPrivilegedepth// "PrivilegeDepth"
0x4f3ea  ldsfld   string [mscorlib]System.String::Empty
0x4f3ef  callvirt instance string [System.Xml]System.Xml.XPath.XPathNavigator::GetAttribute(string, string)
0x4f3f4  stloc.1
0x4f3f5  ldloc.1
0x4f3f6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f3fb  brtrue.s loc_4F41A
0x4f3fd  ldloc.0
0x4f3fe  ldtoken  [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeDepth
0x4f403  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4f408  ldloc.1
0x4f409  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x4f40e  unbox.any [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeDepth
0x4f413  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeDepth [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.MiscellaneousPrivilegeRulePart::PrivilegeDepth
0x4f418  br.s     loc_4F421
0x4f41a  ldloc.0
0x4f41b  ldc.i4.m1
0x4f41c  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.PrivilegeDepth [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.MiscellaneousPrivilegeRulePart::PrivilegeDepth
0x4f421  ldloc.0
0x4f422  ret
```
