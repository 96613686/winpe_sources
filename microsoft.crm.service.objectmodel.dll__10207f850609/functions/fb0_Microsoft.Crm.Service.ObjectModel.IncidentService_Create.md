# Microsoft.Crm.Service.ObjectModel.IncidentService::Create

- ea: `0xfb0`
- end: `0x1180`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::Create`
- size: `464`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0xfb0`
- `0x1f30`
- `0x1fd0`
- `0x25f0`
- `0x2930`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  ldarg.2
0xfb1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SoapPacket()
0xfb6  ldarg.1
0xfb7  ldstr    aTicketnumber// "ticketnumber"
0xfbc  ldarg.0
0xfbd  ldftn    instance string Microsoft.Crm.Service.ObjectModel.IncidentService::GetNextIncidentNumber(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0xfc3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext/GenerateStringValue::.ctor(object, native int)
0xfc8  ldarg.2
0xfc9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::InitializeStringAttributeFromOfflineData(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext/GenerateStringValue, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xfce  ldarg.2
0xfcf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0xfd4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0xfd9  ldnull
0xfda  stloc.0
0xfdb  ldarg.1
0xfdc  ldstr    aParentcaseid// "parentcaseid"
0xfe1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xfe6  brfalse.s loc_1041
0xfe8  ldarg.1
0xfe9  ldstr    aParentcaseid// "parentcaseid"
0xfee  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xff3  callvirt instance string [mscorlib]System.Object::ToString()
0xff8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xffd  brtrue.s loc_1041
0xfff  ldarg.1
0x1000  ldstr    aParentcaseid// "parentcaseid"
0x1005  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x100a  unbox.any [mscorlib]System.Guid
0x100f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1014  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1019  brfalse.s loc_1041
0x101b  ldarg.0
0x101c  ldarg.1
0x101d  ldarg.2
0x101e  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateParentCaseAttributeIsNull(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity incident, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1023  ldarg.0
0x1024  ldarg.1
0x1025  ldarg.2
0x1026  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::CheckMaxChildAssosciationLimit(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity incident, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x102b  ldarg.0
0x102c  ldarg.1
0x102d  ldarg.2
0x102e  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.IncidentService::InitializeIncidentWithInheritance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity incident, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1033  starg.s  1
0x1035  ldarg.1
0x1036  ldstr    aMasterid// "masterid"
0x103b  ldnull
0x103c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1041  ldarg.1
0x1042  ldstr    aIsescalated// "isescalated"
0x1047  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x104c  brfalse.s loc_1070
0x104e  ldarg.1
0x104f  ldstr    aIsescalated// "isescalated"
0x1054  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1059  unbox.any [mscorlib]System.Boolean
0x105e  brfalse.s loc_1070
0x1060  ldarg.1
0x1061  ldstr    aEscalatedon// "escalatedon"
0x1066  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x106b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1070  ldarg.0
0x1071  ldarg.1
0x1072  ldarg.2
0x1073  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1078  stloc.0
0x1079  leave    loc_1162
0x107e  pop
0x107f  ldstr    aIncident// "Incident"
0x1084  ldarg.2
0x1085  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x108a  stloc.1
0x108b  ldloc.1
0x108c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x1091  ldstr    aTicketnumber// "ticketnumber"
0x1096  ldc.i4.0
0x1097  ldarg.1
0x1098  ldstr    aTicketnumber// "ticketnumber"
0x109d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x10a2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x10a7  pop
0x10a8  ldarg.0
0x10a9  ldloc.1
0x10aa  ldarg.2
0x10ab  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x10b0  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x10b5  brtrue.s loc_10B9
0x10b7  rethrow
0x10b9  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x10be  brfalse.s loc_10EB
0x10c0  ldarg.1
0x10c1  ldstr    aTicketnumber// "ticketnumber"
0x10c6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::ClearAttribute(string)
0x10cb  ldarg.2
0x10cc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SoapPacket()
0x10d1  ldarg.1
0x10d2  ldstr    aTicketnumber// "ticketnumber"
0x10d7  ldarg.0
0x10d8  ldftn    instance string Microsoft.Crm.Service.ObjectModel.IncidentService::GetNextIncidentNumber(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10de  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext/GenerateStringValue::.ctor(object, native int)
0x10e3  ldarg.2
0x10e4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext::InitializeStringAttributeFromOfflineData(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SoapContext/GenerateStringValue, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x10e9  br.s     loc_10FD
0x10eb  ldarg.1
0x10ec  ldstr    aTicketnumber// "ticketnumber"
0x10f1  ldarg.0
0x10f2  ldarg.2
0x10f3  call     instance string Microsoft.Crm.Service.ObjectModel.IncidentService::GetNextIncidentNumber(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x10f8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x10fd  ldarg.1
0x10fe  ldstr    aParentcaseid// "parentcaseid"
0x1103  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1108  brfalse.s loc_1157
0x110a  ldarg.1
0x110b  ldstr    aParentcaseid// "parentcaseid"
0x1110  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1115  callvirt instance string [mscorlib]System.Object::ToString()
0x111a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x111f  brtrue.s loc_1157
0x1121  ldarg.1
0x1122  ldstr    aParentcaseid// "parentcaseid"
0x1127  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x112c  unbox.any [mscorlib]System.Guid
0x1131  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1136  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x113b  brfalse.s loc_1157
0x113d  ldarg.0
0x113e  ldarg.1
0x113f  ldarg.2
0x1140  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::ValidateParentCaseAttributeIsNull(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity incident, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1145  ldarg.0
0x1146  ldarg.1
0x1147  ldarg.2
0x1148  call     instance void Microsoft.Crm.Service.ObjectModel.IncidentService::CheckMaxChildAssosciationLimit(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity incident, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x114d  ldarg.0
0x114e  ldarg.1
0x114f  ldarg.2
0x1150  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.IncidentService::InitializeIncidentWithInheritance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity incident, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1155  starg.s  1
0x1157  ldarg.0
0x1158  ldarg.1
0x1159  ldarg.2
0x115a  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x115f  stloc.0
0x1160  leave.s  loc_1162
0x1162  ldarg.2
0x1163  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x1168  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x116d  leave.s  loc_117E
0x116f  pop
0x1170  ldarg.2
0x1171  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x1176  ldc.i4.0
0x1177  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x117c  rethrow
0x117e  ldloc.0
0x117f  ret
```
