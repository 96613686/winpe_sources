# Microsoft.Crm.Application.WebServices.WorkflowWebService::SetVariableProperties

- ea: `0x3cb0`
- end: `0x3dac`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::SetVariableProperties`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3990`

## callees

- `0x3cb0`

## pseudocode

```c

```

## disassembly

```asm
0x3cb0  ldarg.2
0x3cb1  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3cb6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3cbb  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3cc0  stloc.0
0x3cc1  ldarg.s  4
0x3cc3  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3cc8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3ccd  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x3cd2  stloc.1
0x3cd3  ldloc.1
0x3cd4  switch   loc_3CF3, loc_3CF8, loc_3CFC, loc_3D00, loc_3D00, loc_3D04
0x3cf1  br.s     loc_3D08
0x3cf3  ldc.i4.s 0xE
0x3cf5  stloc.2
0x3cf6  br.s     loc_3D13
0x3cf8  ldc.i4.5
0x3cf9  stloc.2
0x3cfa  br.s     loc_3D13
0x3cfc  ldc.i4.4
0x3cfd  stloc.2
0x3cfe  br.s     loc_3D13
0x3d00  ldc.i4.2
0x3d01  stloc.2
0x3d02  br.s     loc_3D13
0x3d04  ldc.i4.6
0x3d05  stloc.2
0x3d06  br.s     loc_3D13
0x3d08  ldstr    aVariableDataTy// "Variable data type not supported."
0x3d0d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x3d12  throw
0x3d13  ldloc.0
0x3d14  brfalse.s loc_3D1E
0x3d16  ldloc.0
0x3d17  ldc.i4.1
0x3d18  bne.un.s loc_3D22
0x3d1a  ldc.i4.1
0x3d1b  stloc.3
0x3d1c  br.s     loc_3D2D
0x3d1e  ldc.i4.0
0x3d1f  stloc.3
0x3d20  br.s     loc_3D2D
0x3d22  ldstr    aVariableTypeNo// "Variable type not supported"
0x3d27  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x3d2c  throw
0x3d2d  ldarg.1
0x3d2e  ldarg.3
0x3d2f  callvirt instance string [System.Xml]System.Xml.XPath.XPathItem::get_Value()
0x3d34  ldloc.2
0x3d35  ldloc.3
0x3d36  call     string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ConstructIdentifierName(string, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, bool)
0x3d3b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_VariableName(string)
0x3d40  ldarg.1
0x3d41  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x3d46  ldarg.1
0x3d47  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_VariableName()
0x3d4c  ldloc.3
0x3d4d  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::ContainsVariable(string, bool)
0x3d52  brfalse.s loc_3D96
0x3d54  ldarg.1
0x3d55  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Workflow()
0x3d5a  ldarg.1
0x3d5b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_VariableName()
0x3d60  ldloc.3
0x3d61  callvirt instance object [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetVariableValue(string, bool)
0x3d66  stloc.s  4
0x3d68  ldloc.s  4
0x3d6a  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x3d6f  brfalse.s loc_3D88
0x3d71  ldarg.1
0x3d72  ldloc.s  4
0x3d74  unbox.any [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x3d79  stloc.s  5
0x3d7b  ldloca.s 5
0x3d7d  call     instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::GetClrType()
0x3d82  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_DataType(class [mscorlib]System.Type)
0x3d87  ret
0x3d88  ldarg.1
0x3d89  ldloc.s  4
0x3d8b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3d90  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::set_DataType(class [mscorlib]System.Type)
0x3d95  ret
0x3d96  ldstr    aVariableNameNo// "Variable name not found: "
0x3d9b  ldarg.1
0x3d9c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignVariableStep::get_VariableName()
0x3da1  call     string [mscorlib]System.String::Concat(string, string)
0x3da6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x3dab  throw
```
