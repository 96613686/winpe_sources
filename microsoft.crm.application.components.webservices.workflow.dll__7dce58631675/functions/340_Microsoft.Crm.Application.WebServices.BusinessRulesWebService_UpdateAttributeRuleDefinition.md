# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::UpdateAttributeRuleDefinition

- ea: `0x340`
- end: `0x407`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::UpdateAttributeRuleDefinition`
- size: `199`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x260`
- `0x2d0`

## callees

- `0x340`

## string_xrefs

- `0x357`: `ruleAsJson`

## pseudocode

```c

```

## disassembly

```asm
0x340  ldarg.2
0x341  ldstr    aEntityid// "entityId"
0x346  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x34b  ldarg.3
0x34c  ldstr    aAttributeid// "attributeId"
0x351  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x356  ldarg.1
0x357  ldstr    aRuleasjson// "ruleAsJson"
0x35c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x361  ldarg.2
0x362  ldloca.s 0
0x364  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x369  brtrue.s loc_371
0x36b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x370  stloc.0
0x371  ldarg.3
0x372  ldloca.s 1
0x374  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x379  brtrue.s loc_381
0x37b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x380  stloc.1
0x381  ldloc.0
0x382  ldstr    aEntityid// "entityId"
0x387  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x38c  ldloc.1
0x38d  ldstr    aAttributeid// "attributeId"
0x392  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x397  ldarg.1
0x398  call     T0x2B000004
0x39d  stloc.2
0x39e  ldarg.s  5
0x3a0  ldloc.2
0x3a1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter::GetWorkflowStep(class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.BusinessRule)
0x3a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3ab  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.RuleWorkflowStepHelper::SerializeToXaml(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3b0  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0x3b5  stloc.3
0x3b6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3bb  ldstr    aAttributeEntit// "<attribute><entityid>{0}</entityid><att"...
0x3c0  ldc.i4.4
0x3c1  newarr   [mscorlib]System.Object
0x3c6  dup
0x3c7  ldc.i4.0
0x3c8  ldarg.2
0x3c9  stelem.ref
0x3ca  dup
0x3cb  ldc.i4.1
0x3cc  ldarg.3
0x3cd  stelem.ref
0x3ce  dup
0x3cf  ldc.i4.2
0x3d0  ldloc.3
0x3d1  stelem.ref
0x3d2  dup
0x3d3  ldc.i4.3
0x3d4  ldarg.s  4
0x3d6  stelem.ref
0x3d7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3dc  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x3e1  stloc.s  4
0x3e3  newobj   instance void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::.ctor()
0x3e8  stloc.s  5
0x3ea  ldloc.s  5
0x3ec  ldloc.s  4
0x3ee  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x3f3  callvirt instance void [Microsoft.Crm.Application.Components.WebServices.SystemCustomization]Microsoft.Crm.Application.WebServices.SystemCustomization.SystemCustomization::UpdateAttribute(class [System.Xml]System.Xml.XmlNode)
0x3f8  leave.s  loc_406
0x3fa  ldloc.s  5
0x3fc  brfalse.s loc_405
0x3fe  ldloc.s  5
0x400  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x405  endfinally
0x406  ret
```
