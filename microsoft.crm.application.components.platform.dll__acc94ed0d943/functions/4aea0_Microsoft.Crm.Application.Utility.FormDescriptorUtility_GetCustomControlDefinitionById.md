# Microsoft.Crm.Application.Utility.FormDescriptorUtility::GetCustomControlDefinitionById

- ea: `0x4aea0`
- end: `0x4af29`
- name: `Microsoft.Crm.Application.Utility.FormDescriptorUtility::GetCustomControlDefinitionById`
- size: `137`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x17590`
- `0x33400`
- `0x33480`
- `0x4b050`
- `0x4b150`

## callees

- `0x4aea0`
- `0x5be20`
- `0x94440`
- `0x94500`

## string_xrefs

- `0x4aeb3`: `manifest`
- `0x4af01`: `manifest`

## pseudocode

```c

```

## disassembly

```asm
0x4aea0  ldnull
0x4aea1  stloc.0
0x4aea2  ldstr    aCustomcontrol// "customcontrol"
0x4aea7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x4aeac  stloc.1
0x4aead  ldloc.1
0x4aeae  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x4aeb3  ldstr    aManifest// "manifest"
0x4aeb8  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x4aebd  ldloc.1
0x4aebe  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x4aec3  ldstr    aCustomcontroli// "customcontrolid"
0x4aec8  ldc.i4.0
0x4aec9  ldc.i4.1
0x4aeca  newarr   [mscorlib]System.Object
0x4aecf  dup
0x4aed0  ldc.i4.0
0x4aed1  ldarg.0
0x4aed2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4aed7  box      [mscorlib]System.Guid
0x4aedc  stelem.ref
0x4aedd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x4aee2  ldloc.1
0x4aee3  ldarg.1
0x4aee4  newobj   instance void Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x4aee9  callvirt instance class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.ServiceCommands.RetrieveMultipleCommand::Execute()
0x4aeee  stloc.2
0x4aeef  ldloc.2
0x4aef0  brfalse.s loc_4AF27
0x4aef2  ldloc.2
0x4aef3  call     T0x2B000021
0x4aef8  brfalse.s loc_4AF27
0x4aefa  ldloc.2
0x4aefb  ldc.i4.0
0x4aefc  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x4af01  ldstr    aManifest// "manifest"
0x4af06  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x4af0b  callvirt instance string [mscorlib]System.Object::ToString()
0x4af10  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x4af15  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlManifestHelper::ParseAndGetCustomControlDefinition(class [System.Xml]System.Xml.XmlDocument)
0x4af1a  stloc.0
0x4af1b  ldloc.0
0x4af1c  ldarg.0
0x4af1d  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4af22  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.CustomControl.CustomControlDefinition::set_CustomControlId(valuetype [mscorlib]System.Guid)
0x4af27  ldloc.0
0x4af28  ret
```
