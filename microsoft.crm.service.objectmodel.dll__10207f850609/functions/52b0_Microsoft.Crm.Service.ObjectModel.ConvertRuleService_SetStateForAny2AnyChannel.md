# Microsoft.Crm.Service.ObjectModel.ConvertRuleService::SetStateForAny2AnyChannel

- ea: `0x52b0`
- end: `0x5434`
- name: `Microsoft.Crm.Service.ObjectModel.ConvertRuleService::SetStateForAny2AnyChannel`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x5210`

## callees

- `0x52b0`
- `0x5440`
- `0x5470`
- `0x5680`
- `0x57a0`
- `0x58a0`

## pseudocode

```c

```

## disassembly

```asm
0x52b0  ldarg.s  5
0x52b2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x52b7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x52bc  ldnull
0x52bd  stloc.0
0x52be  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x52c3  stloc.1
0x52c4  ldarg.2
0x52c5  ldc.i4.1
0x52c6  bne.un.s loc_52F9
0x52c8  ldarg.0
0x52c9  ldarg.1
0x52ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x52cf  ldarg.s  4
0x52d1  ldstr    aQueueid// "queueid"
0x52d6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x52db  callvirt instance string [mscorlib]System.Object::ToString()
0x52e0  ldarg.s  4
0x52e2  ldstr    aSourcechannelt// "sourcechanneltypecode"
0x52e7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x52ec  unbox.any [mscorlib]System.Int32
0x52f1  ldarg.s  5
0x52f3  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.ConvertRuleService::GetExistingActivatedRule(valuetype [mscorlib]System.Guid convertRuleId, string queueId, int32 sourceTypeCode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x52f8  stloc.0
0x52f9  ldarg.0
0x52fa  ldarg.1
0x52fb  ldarg.2
0x52fc  ldarg.3
0x52fd  ldarg.s  4
0x52ff  ldarg.s  5
0x5301  call     instance bool Microsoft.Crm.Service.ObjectModel.ConvertRuleService::SetStateRuleAndWorkflow(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, int32 newState, int32 newStatusCode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity originalEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5306  ldarg.s  4
0x5308  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x530d  ldstr    aSourcechannelt// "sourcechanneltypecode"
0x5312  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x5317  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x531c  unbox.any [mscorlib]System.Int32
0x5321  stloc.2
0x5322  ldarg.s  4
0x5324  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x5329  ldstr    aSourcechannelt// "sourcechanneltypecode"
0x532e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x5333  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x5338  unbox.any [mscorlib]System.Int32
0x533d  stloc.3
0x533e  ldarg.s  4
0x5340  ldstr    aQueueid// "queueid"
0x5345  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x534a  stloc.s  4
0x534c  ldarg.0
0x534d  ldloc.2
0x534e  ldarg.2
0x534f  ldloc.s  4
0x5351  ldloc.3
0x5352  ldarg.1
0x5353  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x5358  ldarg.s  5
0x535a  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleService::RegisterPlugIns(int32 objectTypeCode, int32 newState, bool hasQueueId, int32 sourceChannelTypeCode, valuetype [mscorlib]System.Guid convertRuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x535f  ldloc.0
0x5360  brfalse.s loc_5388
0x5362  ldloc.0
0x5363  ldstr    aConvertruleid_0// "convertruleid"
0x5368  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x536d  unbox.any [mscorlib]System.Guid
0x5372  stloc.1
0x5373  ldc.i4.0
0x5374  stsfld   bool Microsoft.Crm.Service.ObjectModel.ConvertRuleService::deleteOriginalEntityWorkFlow
0x5379  ldarg.0
0x537a  ldloc.0
0x537b  ldarg.s  5
0x537d  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleService::DeActivateConvertRule(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity activatedConvertRule, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5382  ldc.i4.1
0x5383  stsfld   bool Microsoft.Crm.Service.ObjectModel.ConvertRuleService::deleteOriginalEntityWorkFlow
0x5388  ldloc.1
0x5389  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x538e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5393  brfalse.s loc_53A0
0x5395  ldarg.0
0x5396  ldloc.1
0x5397  ldarg.s  5
0x5399  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleService::DeleteConvertRuleWorkflow(valuetype [mscorlib]System.Guid convertRuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x539e  br.s     loc_53CF
0x53a0  ldarg.2
0x53a1  brtrue.s loc_53CF
0x53a3  ldsfld   bool Microsoft.Crm.Service.ObjectModel.ConvertRuleService::deleteOriginalEntityWorkFlow
0x53a8  brfalse.s loc_53CF
0x53aa  ldarg.s  4
0x53ac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x53b1  ldstr    aConvertruleid_0// "convertruleid"
0x53b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x53bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x53c0  unbox.any [mscorlib]System.Guid
0x53c5  stloc.1
0x53c6  ldarg.0
0x53c7  ldloc.1
0x53c8  ldarg.s  5
0x53ca  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleService::DeleteConvertRuleWorkflow(valuetype [mscorlib]System.Guid convertRuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x53cf  ldarg.s  5
0x53d1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x53d6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x53db  stloc.s  5
0x53dd  leave.s  loc_5431
0x53df  stloc.s  6
0x53e1  ldarg.s  5
0x53e3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x53e8  ldc.i4.0
0x53e9  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x53ee  ldarg.0
0x53ef  ldarg.1
0x53f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x53f5  ldarg.s  5
0x53f7  call     instance void Microsoft.Crm.Service.ObjectModel.ConvertRuleService::DeleteConvertRuleWorkflow(valuetype [mscorlib]System.Guid convertRuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x53fc  ldloc.s  6
0x53fe  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x5403  ldc.i4   0x80045016
0x5408  bne.un.s loc_541C
0x540a  ldloc.s  6
0x540c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5411  ldc.i4   0x8004F886
0x5416  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x541b  throw
0x541c  ldc.i4   0x800608F4
0x5421  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x5426  ldc.i4   0x800608F4
0x542b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x5430  throw
0x5431  ldloc.s  5
0x5433  ret
```
