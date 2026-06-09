# Microsoft.Crm.Workflow.InteractiveWorkflowContext::InteractiveWorkflowContextXml

- ea: `0xdaa0`
- end: `0xdc63`
- name: `Microsoft.Crm.Workflow.InteractiveWorkflowContext::InteractiveWorkflowContextXml`
- size: `451`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0xd910`
- `0xd990`
- `0xd9d0`
- `0xd9f0`
- `0xda40`
- `0xda60`
- `0xda80`
- `0xdaa0`

## pseudocode

```c

```

## disassembly

```asm
0xdaa0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xdaa5  stloc.0
0xdaa6  ldstr    asc_30690// ""
0xdaab  stloc.1
0xdaac  ldarg.0
0xdaad  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowActivationId()
0xdab2  pop
0xdab3  ldarg.0
0xdab4  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowActivationId()
0xdab9  stloc.2
0xdaba  ldloca.s 2
0xdabc  constrained. [mscorlib]System.Guid
0xdac2  callvirt instance string [mscorlib]System.Object::ToString()
0xdac7  stloc.1
0xdac8  ldloc.0
0xdac9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdace  ldsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_workflowActivationIdTemplate
0xdad3  ldc.i4.1
0xdad4  newarr   [mscorlib]System.Object
0xdad9  dup
0xdada  ldc.i4.0
0xdadb  ldloc.1
0xdadc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xdae1  stelem.ref
0xdae2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdae7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xdaec  pop
0xdaed  ldarg.0
0xdaee  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_OriginatingWorkflowInstanceId()
0xdaf3  pop
0xdaf4  ldarg.0
0xdaf5  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_OriginatingWorkflowInstanceId()
0xdafa  stloc.2
0xdafb  ldloca.s 2
0xdafd  constrained. [mscorlib]System.Guid
0xdb03  callvirt instance string [mscorlib]System.Object::ToString()
0xdb08  stloc.1
0xdb09  ldloc.0
0xdb0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdb0f  ldsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_originatingWorkflowInstanceIdTemplate
0xdb14  ldc.i4.1
0xdb15  newarr   [mscorlib]System.Object
0xdb1a  dup
0xdb1b  ldc.i4.0
0xdb1c  ldloc.1
0xdb1d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xdb22  stelem.ref
0xdb23  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdb28  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xdb2d  pop
0xdb2e  ldarg.0
0xdb2f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowInstanceId()
0xdb34  pop
0xdb35  ldarg.0
0xdb36  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_WorkflowInstanceId()
0xdb3b  stloc.2
0xdb3c  ldloca.s 2
0xdb3e  constrained. [mscorlib]System.Guid
0xdb44  callvirt instance string [mscorlib]System.Object::ToString()
0xdb49  stloc.1
0xdb4a  ldloc.0
0xdb4b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdb50  ldsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_workflowInstanceIdTemplate
0xdb55  ldc.i4.1
0xdb56  newarr   [mscorlib]System.Object
0xdb5b  dup
0xdb5c  ldc.i4.0
0xdb5d  ldloc.1
0xdb5e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xdb63  stelem.ref
0xdb64  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdb69  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xdb6e  pop
0xdb6f  ldarg.0
0xdb70  call     instance string Microsoft.Crm.Workflow.InteractiveWorkflowContext::get_WorkflowStateXml()
0xdb75  brfalse.s loc_DB7F
0xdb77  ldarg.0
0xdb78  call     instance string Microsoft.Crm.Workflow.InteractiveWorkflowContext::get_WorkflowStateXml()
0xdb7d  br.s     loc_DB84
0xdb7f  ldstr    asc_30690// ""
0xdb84  stloc.1
0xdb85  ldloc.0
0xdb86  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdb8b  ldsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_workflowStateXmlTemplate
0xdb90  ldc.i4.1
0xdb91  newarr   [mscorlib]System.Object
0xdb96  dup
0xdb97  ldc.i4.0
0xdb98  ldloc.1
0xdb99  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xdb9e  stelem.ref
0xdb9f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdba4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xdba9  pop
0xdbaa  ldarg.0
0xdbab  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.InteractiveWorkflowContext::get_PrimaryEntityId()
0xdbb0  pop
0xdbb1  ldarg.0
0xdbb2  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.InteractiveWorkflowContext::get_PrimaryEntityId()
0xdbb7  stloc.2
0xdbb8  ldloca.s 2
0xdbba  constrained. [mscorlib]System.Guid
0xdbc0  callvirt instance string [mscorlib]System.Object::ToString()
0xdbc5  stloc.1
0xdbc6  ldloc.0
0xdbc7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdbcc  ldsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_primaryEntityIdTemplate
0xdbd1  ldc.i4.1
0xdbd2  newarr   [mscorlib]System.Object
0xdbd7  dup
0xdbd8  ldc.i4.0
0xdbd9  ldloc.1
0xdbda  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xdbdf  stelem.ref
0xdbe0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdbe5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xdbea  pop
0xdbeb  ldarg.0
0xdbec  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.SynchronousWorkflowCommonContext::get_OrganizationId()
0xdbf1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xdbf6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xdbfb  ldarg.0
0xdbfc  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.Workflow.InteractiveWorkflowContext::get_RegardingObject()
0xdc01  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0xdc06  ldc.i4.1
0xdc07  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xdc0c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xdc11  stloc.3
0xdc12  ldloca.s 3
0xdc14  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdc19  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xdc1e  stloc.1
0xdc1f  ldloc.0
0xdc20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdc25  ldsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_primaryEntityTypeCodeTemplate
0xdc2a  ldc.i4.1
0xdc2b  newarr   [mscorlib]System.Object
0xdc30  dup
0xdc31  ldc.i4.0
0xdc32  ldloc.1
0xdc33  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xdc38  stelem.ref
0xdc39  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdc3e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xdc43  pop
0xdc44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdc49  ldsfld   string Microsoft.Crm.Workflow.InteractiveWorkflowContext::_interactiveWorkflowContextTemplate
0xdc4e  ldc.i4.1
0xdc4f  newarr   [mscorlib]System.Object
0xdc54  dup
0xdc55  ldc.i4.0
0xdc56  ldloc.0
0xdc57  callvirt instance string [mscorlib]System.Object::ToString()
0xdc5c  stelem.ref
0xdc5d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdc62  ret
```
