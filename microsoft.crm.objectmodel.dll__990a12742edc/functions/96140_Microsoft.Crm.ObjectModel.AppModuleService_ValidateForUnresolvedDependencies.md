# Microsoft.Crm.ObjectModel.AppModuleService::ValidateForUnresolvedDependencies

- ea: `0x96140`
- end: `0x96324`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::ValidateForUnresolvedDependencies`
- size: `484`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x91df0`
- `0x92240`
- `0x95ec0`

## callees

- `0x958c0`
- `0x96140`
- `0x96330`
- `0x19a260`

## string_xrefs

- `0x96156`: `requiredcomponentobjectid`
- `0x961be`: `requiredcomponentobjectid`
- `0x9615e`: `requiredcomponenttype`
- `0x961d1`: `requiredcomponenttype`
- `0x9614e`: `dependentcomponentobjectid`
- `0x9616b`: `dependentcomponentobjectid`
- `0x96206`: `dependentcomponentobjectid`

## pseudocode

```c

```

## disassembly

```asm
0x96140  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::.ctor()
0x96145  stloc.0
0x96146  ldc.i4.3
0x96147  newarr   [mscorlib]System.String
0x9614c  dup
0x9614d  ldc.i4.0
0x9614e  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x96153  stelem.ref
0x96154  dup
0x96155  ldc.i4.1
0x96156  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x9615b  stelem.ref
0x9615c  dup
0x9615d  ldc.i4.2
0x9615e  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x96163  stelem.ref
0x96164  stloc.1
0x96165  ldarg.0
0x96166  ldstr    aDependency_0// "Dependency"
0x9616b  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x96170  ldarg.2
0x96171  call     T0x2B00005B
0x96176  ldloc.1
0x96177  ldarg.s  5
0x96179  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9617e  stloc.2
0x9617f  newobj   instance void Microsoft.Crm.ObjectModel.DependencyService::.ctor()
0x96184  ldloc.2
0x96185  ldarg.s  5
0x96187  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9618c  ldtoken  [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType
0x96191  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x96196  ldarg.1
0x96197  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x9619c  unbox.any [mscorlib]System.Int32
0x961a1  stloc.3
0x961a2  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x961a7  stloc.s  4
0x961a9  br       loc_9624F
0x961ae  ldloc.s  4
0x961b0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x961b5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x961ba  stloc.s  5
0x961bc  ldloc.s  5
0x961be  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x961c3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x961c8  unbox.any [mscorlib]System.Guid
0x961cd  stloc.s  6
0x961cf  ldloc.s  5
0x961d1  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x961d6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x961db  unbox.any [mscorlib]System.Int32
0x961e0  stloc.s  7
0x961e2  ldtoken  [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType
0x961e7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x961ec  ldloc.s  7
0x961ee  box      [mscorlib]System.Int32
0x961f3  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x961f8  brfalse.s loc_9624F
0x961fa  ldarg.3
0x961fb  ldloc.s  6
0x961fd  call     T0x2B000131
0x96202  brtrue.s loc_9624F
0x96204  ldloc.s  5
0x96206  ldstr    aDependentcompo// "dependentcomponentobjectid"
0x9620b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x96210  unbox.any [mscorlib]System.Guid
0x96215  stloc.s  8
0x96217  ldloc.0
0x96218  ldloc.s  8
0x9621a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::ContainsKey(var<u1>)
0x9621f  brtrue.s loc_9622E
0x96221  ldloc.0
0x96222  ldloc.s  8
0x96224  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>::.ctor()
0x96229  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::Add(var<u1>, !!T0)
0x9622e  ldarg.0
0x9622f  ldloc.s  7
0x96231  ldloc.s  6
0x96233  ldarg.s  5
0x96235  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component Microsoft.Crm.ObjectModel.AppModuleService::GetUnresolvedDependencyInfo(int32 componentType, valuetype [mscorlib]System.Guid componentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9623a  stloc.s  9
0x9623c  ldloc.s  9
0x9623e  brfalse.s loc_9624F
0x96240  ldloc.0
0x96241  ldloc.s  8
0x96243  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::get_Item(void)
0x96248  ldloc.s  9
0x9624a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>::Add(var<u1>)
0x9624f  ldloc.s  4
0x96251  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x96256  brtrue   loc_961AE
0x9625b  leave.s  loc_96272
0x9625d  ldloc.s  4
0x9625f  isinst   [mscorlib]System.IDisposable
0x96264  stloc.s  0xA
0x96266  ldloc.s  0xA
0x96268  brfalse.s loc_96271
0x9626a  ldloc.s  0xA
0x9626c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x96271  endfinally
0x96272  ldloc.0
0x96273  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::GetEnumerator()
0x96278  stloc.s  0xB
0x9627a  br       loc_96307
0x9627f  ldloca.s 0xB
0x96281  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::get_Current()
0x96286  stloc.s  0xC
0x96288  ldarg.0
0x96289  ldloc.3
0x9628a  ldloca.s 0xC
0x9628c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::get_Key()
0x96291  ldarg.s  5
0x96293  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component Microsoft.Crm.ObjectModel.AppModuleService::GetUnresolvedDependencyInfo(int32 componentType, valuetype [mscorlib]System.Guid componentId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x96298  stloc.s  0xD
0x9629a  ldarg.s  4
0x9629c  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::.ctor()
0x962a1  dup
0x962a2  ldc.i4.2
0x962a3  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ErrorType(valuetype [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ErrorType)
0x962a8  dup
0x962a9  ldloca.s 0xC
0x962ab  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::get_Key()
0x962b0  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ComponentId(valuetype [mscorlib]System.Guid)
0x962b5  dup
0x962b6  ldloc.3
0x962b7  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ComponentType(int32)
0x962bc  dup
0x962bd  ldloc.s  0xD
0x962bf  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component::get_DisplayName()
0x962c4  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_DisplayName(string)
0x962c9  dup
0x962ca  ldloc.s  0xD
0x962cc  callvirt instance int32 [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component::get_ComponentSubType()
0x962d1  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ComponentSubType(int32)
0x962d6  dup
0x962d7  ldloc.s  0xD
0x962d9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component::get_ParentEntityId()
0x962de  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ParentEntityId(valuetype [mscorlib]System.Guid)
0x962e3  dup
0x962e4  ldloc.s  0xD
0x962e6  callvirt instance string [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component::get_ParentEntityName()
0x962eb  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_ParentEntityName(string)
0x962f0  dup
0x962f1  ldloca.s 0xC
0x962f3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::get_Value()
0x962f8  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>::ToArray()
0x962fd  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue::set_RequiredComponents(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component[])
0x96302  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidationIssue>::Add(var<u1>)
0x96307  ldloca.s 0xB
0x96309  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>::MoveNext()
0x9630e  brtrue   loc_9627F
0x96313  leave.s  loc_96323
0x96315  ldloca.s 0xB
0x96317  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.Component>>
0x9631d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x96322  endfinally
0x96323  ret
```
