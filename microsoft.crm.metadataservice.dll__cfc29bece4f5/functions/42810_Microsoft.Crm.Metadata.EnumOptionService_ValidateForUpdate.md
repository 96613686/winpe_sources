# Microsoft.Crm.Metadata.EnumOptionService::ValidateForUpdate

- ea: `0x42810`
- end: `0x428f9`
- name: `Microsoft.Crm.Metadata.EnumOptionService::ValidateForUpdate`
- size: `233`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x41740`

## callees

- `0x42810`
- `0x42900`
- `0x4b8b0`

## string_xrefs

- `0x4281d`: `Only DisplayName and Description can be updated for 'Boolean' options.`
- `0x42878`: `For 'Picklist' and 'Status' options, only ParentValues can be updated.`
- `0x428a7`: `For State Options you can update only DisplayName, Description and DefaultStatusCode.`

## pseudocode

```c

```

## disassembly

```asm
0x42810  ldarg.1
0x42811  brtrue.s loc_42814
0x42813  ret
0x42814  ldc.i4.3
0x42815  ldarg.2
0x42816  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x4281b  bne.un.s loc_42828
0x4281d  ldstr    aOnlyDisplaynam// "Only DisplayName and Description can be"...
0x42822  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x42827  throw
0x42828  ldarg.1
0x42829  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::get_InnerEntityData()
0x4282e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_MetadataAttributes()
0x42833  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfoCollection::GetEnumerator()
0x42838  stloc.0
0x42839  br.s     loc_428B2
0x4283b  ldloc.0
0x4283c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x42841  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo
0x42846  stloc.1
0x42847  ldarg.2
0x42848  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetType()
0x4284d  call     bool Microsoft.Crm.Metadata.OptionSetService::IsValidCascadingOptionSetType(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.OptionSetType optionSetType)
0x42852  brfalse.s loc_42883
0x42854  ldstr    aParentvalues// "parentvalues"
0x42859  ldloc.1
0x4285a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_Name()
0x4285f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x42864  brfalse.s loc_428B2
0x42866  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x4286b  ldloc.1
0x4286c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_Name()
0x42871  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x42876  brfalse.s loc_428B2
0x42878  ldstr    aForPicklistAnd// "For 'Picklist' and 'Status' options, on"...
0x4287d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x42882  throw
0x42883  ldstr    aAttributepickl_0// "attributepicklistvalueid"
0x42888  ldloc.1
0x42889  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_Name()
0x4288e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x42893  brfalse.s loc_428B2
0x42895  ldstr    aStateStatusVal// "state_status_value"
0x4289a  ldloc.1
0x4289b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeInfo::get_Name()
0x428a0  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x428a5  brfalse.s loc_428B2
0x428a7  ldstr    aForStateOption// "For State Options you can update only D"...
0x428ac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x428b1  throw
0x428b2  ldloc.0
0x428b3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x428b8  brtrue.s loc_4283B
0x428ba  leave.s  loc_428CD
0x428bc  ldloc.0
0x428bd  isinst   [mscorlib]System.IDisposable
0x428c2  stloc.2
0x428c3  ldloc.2
0x428c4  brfalse.s loc_428CC
0x428c6  ldloc.2
0x428c7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x428cc  endfinally
0x428cd  ldarg.1
0x428ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescriptionPropertyBag::get_InnerEntityData()
0x428d3  ldstr    aStateStatusVal// "state_status_value"
0x428d8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x428dd  brtrue.s loc_428F8
0x428df  ldarg.0
0x428e0  ldarg.1
0x428e1  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_StateOrStatusValue()
0x428e6  ldarg.1
0x428e7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributePicklistValueDescription::get_AttributePicklistValueId()
0x428ec  ldarg.2
0x428ed  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.OptionSetDescription::get_OptionSetId()
0x428f2  ldarg.3
0x428f3  call     instance void Microsoft.Crm.Metadata.EnumOptionService::ValidateDefaultStatusValueForStateOption(int32 defaultStatusValueForState, valuetype [mscorlib]System.Guid stateOptionId, valuetype [mscorlib]System.Guid stateOptionSetId, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0x428f8  ret
```
