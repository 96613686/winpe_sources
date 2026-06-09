# Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetreiveTranslationsWithOneApprovedVersion

- ea: `0xeba0`
- end: `0xed5c`
- name: `Microsoft.Crm.Service.ObjectModel.KnowledgeArticleService::RetreiveTranslationsWithOneApprovedVersion`
- size: `444`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xdca0`

## callees

- `0xeba0`

## pseudocode

```c

```

## disassembly

```asm
0xeba0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xeba5  stloc.0
0xeba6  ldstr    aKnowledgeartic// "KnowledgeArticle"
0xebab  ldarg.2
0xebac  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0xebb1  stloc.1
0xebb2  ldloc.1
0xebb3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0xebb8  ldc.i4.3
0xebb9  newarr   [mscorlib]System.String
0xebbe  dup
0xebbf  ldc.i4.0
0xebc0  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xebc5  stelem.ref
0xebc6  dup
0xebc7  ldc.i4.1
0xebc8  ldstr    aStatecode// "statecode"
0xebcd  stelem.ref
0xebce  dup
0xebcf  ldc.i4.2
0xebd0  ldstr    aLanguagelocale// "languagelocaleid"
0xebd5  stelem.ref
0xebd6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0xebdb  ldloc.1
0xebdc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xebe1  ldstr    aStatecode// "statecode"
0xebe6  ldc.i4.0
0xebe7  ldc.i4.1
0xebe8  box      [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KnowledgeArticleState
0xebed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xebf2  pop
0xebf3  ldloc.1
0xebf4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xebf9  ldstr    aParentarticlec// "parentarticlecontentid"
0xebfe  ldc.i4.0
0xebff  ldarg.1
0xec00  box      [mscorlib]System.Guid
0xec05  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xec0a  pop
0xec0b  ldloc.1
0xec0c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xec11  ldstr    aIsprimary// "isprimary"
0xec16  ldc.i4.0
0xec17  ldc.i4.0
0xec18  box      [mscorlib]System.Boolean
0xec1d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xec22  pop
0xec23  ldloc.1
0xec24  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0xec29  ldstr    aIsrootarticle// "isrootarticle"
0xec2e  ldc.i4.0
0xec2f  ldc.i4.0
0xec30  box      [mscorlib]System.Boolean
0xec35  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0xec3a  pop
0xec3b  ldarg.0
0xec3c  ldloc.1
0xec3d  ldarg.2
0xec3e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xec43  stloc.2
0xec44  ldloc.2
0xec45  brfalse  loc_ED5A
0xec4a  ldloc.2
0xec4b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0xec50  ldc.i4.0
0xec51  ble      loc_ED5A
0xec56  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::.ctor()
0xec5b  stloc.3
0xec5c  ldloc.2
0xec5d  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0xec62  stloc.s  4
0xec64  br.s     loc_ECD5
0xec66  ldloc.s  4
0xec68  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xec6d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0xec72  stloc.s  5
0xec74  ldloc.s  5
0xec76  ldstr    aLanguagelocale// "languagelocaleid"
0xec7b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xec80  unbox.any [mscorlib]System.Guid
0xec85  stloc.s  6
0xec87  ldloc.3
0xec88  ldloc.s  6
0xec8a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0xec8f  brfalse.s loc_ECB1
0xec91  ldloc.3
0xec92  ldloc.s  6
0xec94  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0xec99  ldloc.s  5
0xec9b  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xeca0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xeca5  unbox.any [mscorlib]System.Guid
0xecaa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xecaf  br.s     loc_ECD5
0xecb1  ldloc.3
0xecb2  ldloc.s  6
0xecb4  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0xecb9  dup
0xecba  ldloc.s  5
0xecbc  ldstr    aKnowledgeartic_0// "knowledgearticleid"
0xecc1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0xecc6  unbox.any [mscorlib]System.Guid
0xeccb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xecd0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::set_Item(var<u1>, !!T0)
0xecd5  ldloc.s  4
0xecd7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xecdc  brtrue.s loc_EC66
0xecde  leave.s  loc_ECF5
0xece0  ldloc.s  4
0xece2  isinst   [mscorlib]System.IDisposable
0xece7  stloc.s  7
0xece9  ldloc.s  7
0xeceb  brfalse.s loc_ECF4
0xeced  ldloc.s  7
0xecef  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xecf4  endfinally
0xecf5  ldloc.3
0xecf6  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::GetEnumerator()
0xecfb  stloc.s  8
0xecfd  br.s     loc_ED41
0xecff  ldloca.s 8
0xed01  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Current()
0xed06  stloc.s  9
0xed08  ldloca.s 9
0xed0a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Value()
0xed0f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0xed14  ldc.i4.1
0xed15  bne.un.s loc_ED2C
0xed17  ldloc.0
0xed18  ldloca.s 9
0xed1a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::get_Value()
0xed1f  ldc.i4.0
0xed20  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Item(!!T0)
0xed25  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0xed2a  br.s     loc_ED41
0xed2c  ldc.i4   0x80061401
0xed31  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0xed36  ldc.i4   0x80061401
0xed3b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xed40  throw
0xed41  ldloca.s 8
0xed43  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>::MoveNext()
0xed48  brtrue.s loc_ECFF
0xed4a  leave.s  loc_ED5A
0xed4c  ldloca.s 8
0xed4e  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>>
0xed54  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xed59  endfinally
0xed5a  ldloc.0
0xed5b  ret
```
