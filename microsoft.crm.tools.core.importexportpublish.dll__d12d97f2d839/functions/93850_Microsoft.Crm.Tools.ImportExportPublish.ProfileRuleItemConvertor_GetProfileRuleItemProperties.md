# Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemConvertor::GetProfileRuleItemProperties

- ea: `0x93850`
- end: `0x938fd`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemConvertor::GetProfileRuleItemProperties`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x936a0`

## callees

- `0x93850`
- `0x939f0`

## string_xrefs

- `0x938b4`: `ConditionXml`
- `0x938b9`: `conditionxml`
- `0x93890`: `ChannelAccessProfileRuleId`
- `0x93895`: `channelaccessprofileruleid`
- `0x938d8`: `AssociatedChannelAccessProfile`
- `0x938dd`: `associatedchannelaccessprofile`

## pseudocode

```c

```

## disassembly

```asm
0x93850  ldarg.0
0x93851  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemConvertor::_profileRuleItemProperties
0x93856  brtrue   loc_938F6
0x9385b  ldarg.0
0x9385c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap>::.ctor()
0x93861  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemConvertor::_profileRuleItemProperties
0x93866  ldarg.0
0x93867  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemConvertor::_profileRuleItemProperties
0x9386c  ldstr    aName_1// "Name"
0x93871  ldstr    aName// "name"
0x93876  ldtoken  [mscorlib]System.String
0x9387b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x93880  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x93885  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap>::Add(var<u1>)
0x9388a  ldarg.0
0x9388b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemConvertor::_profileRuleItemProperties
0x93890  ldstr    aChannelaccessp_2// "ChannelAccessProfileRuleId"
0x93895  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x9389a  ldtoken  [mscorlib]System.Guid
0x9389f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x938a4  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x938a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap>::Add(var<u1>)
0x938ae  ldarg.0
0x938af  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemConvertor::_profileRuleItemProperties
0x938b4  ldstr    aConditionxml// "ConditionXml"
0x938b9  ldstr    aConditionxml_0// "conditionxml"
0x938be  ldtoken  [mscorlib]System.String
0x938c3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x938c8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x938cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap>::Add(var<u1>)
0x938d2  ldarg.0
0x938d3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemConvertor::_profileRuleItemProperties
0x938d8  ldstr    aAssociatedchan// "AssociatedChannelAccessProfile"
0x938dd  ldstr    aAssociatedchan_0// "associatedchannelaccessprofile"
0x938e2  ldtoken  [mscorlib]System.Guid
0x938e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x938ec  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap::.ctor(string nodeName, string name, class [mscorlib]System.Type type)
0x938f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap>::Add(var<u1>)
0x938f6  ldarg.0
0x938f7  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemPropertyMap> Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleItemConvertor::_profileRuleItemProperties
0x938fc  ret
```
