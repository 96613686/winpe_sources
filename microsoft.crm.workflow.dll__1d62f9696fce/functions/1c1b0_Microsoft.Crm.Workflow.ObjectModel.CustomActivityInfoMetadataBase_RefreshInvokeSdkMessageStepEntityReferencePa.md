# Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::RefreshInvokeSdkMessageStepEntityReferenceParameter

- ea: `0x1c1b0`
- end: `0x1c3d0`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::RefreshInvokeSdkMessageStepEntityReferenceParameter`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1caf0`

## callees

- `0xcf0`
- `0xf9a0`
- `0x1b9d0`
- `0x1c1b0`
- `0x1c3d0`
- `0x1c440`
- `0x1c5d0`
- `0x1c600`
- `0x1ca80`
- `0x1e6b0`

## string_xrefs

- `0x1c348`: `REMOVEUSERFROMRECORDTEAM_Record`

## pseudocode

```c

```

## disassembly

```asm
0x1c1b0  ldarg.0
0x1c1b1  ldarg.3
0x1c1b2  ldarg.s  4
0x1c1b4  call     instance bool Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::CheckIfReferenceParameterExist(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[] inputs, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo[] outputs)
0x1c1b9  brtrue.s loc_1C1BC
0x1c1bb  ret
0x1c1bc  ldarg.0
0x1c1bd  ldarg.1
0x1c1be  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetCustomOperationEntity(valuetype [mscorlib]System.Guid sdkMessageId)
0x1c1c3  stloc.0
0x1c1c4  ldloc.0
0x1c1c5  brfalse  loc_1C2AB
0x1c1ca  ldarg.0
0x1c1cb  ldfld    class Microsoft.Crm.Workflow.IUIDataGenerator Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::_uiDataGenerator
0x1c1d0  ldloc.0
0x1c1d1  ldarg.0
0x1c1d2  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_Context()
0x1c1d7  ldarg.0
0x1c1d8  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_Context()
0x1c1dd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1c1e2  callvirt instance class Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator Microsoft.Crm.Workflow.IUIDataGenerator::GetUIDataGenerator(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity workflow, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache)
0x1c1e7  castclass Microsoft.Crm.Workflow.ObjectModel.CustomOperationUIDataGenerator
0x1c1ec  ldarg.0
0x1c1ed  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_Context()
0x1c1f2  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GenerateUIData(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1c1f7  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetEntityTypeWorkflowArguments()
0x1c1fc  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>::GetEnumerator()
0x1c201  stloc.1
0x1c202  br       loc_1C28C
0x1c207  ldloca.s 1
0x1c209  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>::get_Current()
0x1c20e  stloc.2
0x1c20f  ldloc.2
0x1c210  callvirt instance valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::get_Direction()
0x1c215  brtrue.s loc_1C252
0x1c217  ldarg.3
0x1c218  stloc.3
0x1c219  ldc.i4.0
0x1c21a  stloc.s  4
0x1c21c  br.s     loc_1C249
0x1c21e  ldloc.3
0x1c21f  ldloc.s  4
0x1c221  ldelem.ref
0x1c222  stloc.s  5
0x1c224  ldloc.s  5
0x1c226  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x1c22b  ldloc.2
0x1c22c  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::get_Name()
0x1c231  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c236  brfalse.s loc_1C243
0x1c238  ldarg.0
0x1c239  ldloc.s  5
0x1c23b  ldloc.2
0x1c23c  call     instance void Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::UpdateEntityTypeForEntityReferenceParameter(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase parameter, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument argument)
0x1c241  br.s     loc_1C28C
0x1c243  ldloc.s  4
0x1c245  ldc.i4.1
0x1c246  add
0x1c247  stloc.s  4
0x1c249  ldloc.s  4
0x1c24b  ldloc.3
0x1c24c  ldlen
0x1c24d  conv.i4
0x1c24e  blt.s    loc_1C21E
0x1c250  br.s     loc_1C28C
0x1c252  ldarg.s  4
0x1c254  stloc.3
0x1c255  ldc.i4.0
0x1c256  stloc.s  4
0x1c258  br.s     loc_1C285
0x1c25a  ldloc.3
0x1c25b  ldloc.s  4
0x1c25d  ldelem.ref
0x1c25e  stloc.s  6
0x1c260  ldloc.s  6
0x1c262  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x1c267  ldloc.2
0x1c268  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::get_Name()
0x1c26d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c272  brfalse.s loc_1C27F
0x1c274  ldarg.0
0x1c275  ldloc.s  6
0x1c277  ldloc.2
0x1c278  call     instance void Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::UpdateEntityTypeForEntityReferenceParameter(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase parameter, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument argument)
0x1c27d  br.s     loc_1C28C
0x1c27f  ldloc.s  4
0x1c281  ldc.i4.1
0x1c282  add
0x1c283  stloc.s  4
0x1c285  ldloc.s  4
0x1c287  ldloc.3
0x1c288  ldlen
0x1c289  conv.i4
0x1c28a  blt.s    loc_1C25A
0x1c28c  ldloca.s 1
0x1c28e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>::MoveNext()
0x1c293  brtrue   loc_1C207
0x1c298  leave    loc_1C3CF
0x1c29d  ldloca.s 1
0x1c29f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>
0x1c2a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c2aa  endfinally
0x1c2ab  ldarg.0
0x1c2ac  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetAccessTeamEnabledEntities()
0x1c2b1  stloc.s  7
0x1c2b3  ldarg.3
0x1c2b4  stloc.3
0x1c2b5  ldc.i4.0
0x1c2b6  stloc.s  4
0x1c2b8  br       loc_1C3C5
0x1c2bd  ldloc.3
0x1c2be  ldloc.s  4
0x1c2c0  ldelem.ref
0x1c2c1  stloc.s  8
0x1c2c3  ldloc.s  8
0x1c2c5  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x1c2ca  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1c2cf  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c2d4  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c2d9  brtrue.s loc_1C30E
0x1c2db  ldloc.s  8
0x1c2dd  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x1c2e2  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup
0x1c2e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c2ec  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c2f1  brtrue.s loc_1C30E
0x1c2f3  ldloc.s  8
0x1c2f5  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x1c2fa  ldtoken  [mscorlib]System.Guid
0x1c2ff  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1c304  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1c309  brfalse  loc_1C3BF
0x1c30e  ldstr    a01// "{0}_{1}"
0x1c313  ldarg.2
0x1c314  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1c319  ldloc.s  8
0x1c31b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x1c320  call     string [mscorlib]System.String::Format(string, object, object)
0x1c325  stloc.s  9
0x1c327  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0x1c32c  ldloc.s  9
0x1c32e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::ContainsKey(var<u1>)
0x1c333  brfalse  loc_1C3BF
0x1c338  ldloc.s  9
0x1c33a  ldstr    aAddusertorecor_1// "ADDUSERTORECORDTEAM_Record"
0x1c33f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c344  brtrue.s loc_1C366
0x1c346  ldloc.s  9
0x1c348  ldstr    aRemoveuserfrom_1// "REMOVEUSERFROMRECORDTEAM_Record"
0x1c34d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c352  brtrue.s loc_1C366
0x1c354  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>> Microsoft.Crm.Workflow.Utility.SdkMessageTypeConversion::get_TypeConversionDictionary()
0x1c359  ldloc.s  9
0x1c35b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<string>>::get_Item(void)
0x1c360  stloc.s  0xB
0x1c362  ldloc.s  0xB
0x1c364  br.s     loc_1C368
0x1c366  ldloc.s  7
0x1c368  stloc.s  0xA
0x1c36a  ldloc.s  8
0x1c36c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x1c371  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Clear()
0x1c376  ldloc.s  0xA
0x1c378  brtrue.s loc_1C386
0x1c37a  ldarg.0
0x1c37b  ldloc.s  9
0x1c37d  ldloc.s  0xA
0x1c37f  call     instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::ProcessConvertedEntityNames(string key, class [mscorlib]System.Collections.Generic.IList`1<string> entityNames)
0x1c384  stloc.s  0xA
0x1c386  ldloc.s  0xA
0x1c388  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x1c38d  stloc.s  0xC
0x1c38f  br.s     loc_1C3A8
0x1c391  ldloc.s  0xC
0x1c393  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1c398  stloc.s  0xD
0x1c39a  ldloc.s  8
0x1c39c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x1c3a1  ldloc.s  0xD
0x1c3a3  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x1c3a8  ldloc.s  0xC
0x1c3aa  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c3af  brtrue.s loc_1C391
0x1c3b1  leave.s  loc_1C3BF
0x1c3b3  ldloc.s  0xC
0x1c3b5  brfalse.s loc_1C3BE
0x1c3b7  ldloc.s  0xC
0x1c3b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c3be  endfinally
0x1c3bf  ldloc.s  4
0x1c3c1  ldc.i4.1
0x1c3c2  add
0x1c3c3  stloc.s  4
0x1c3c5  ldloc.s  4
0x1c3c7  ldloc.3
0x1c3c8  ldlen
0x1c3c9  conv.i4
0x1c3ca  blt      loc_1C2BD
0x1c3cf  ret
```
