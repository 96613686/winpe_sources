# Microsoft.Crm.Platform.Server.DataEngine.EntityCrudManager::ModifyPlan

- ea: `0x54380`
- end: `0x5465e`
- name: `Microsoft.Crm.Platform.Server.DataEngine.EntityCrudManager::ModifyPlan`
- size: `734`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x8a730`

## callees

- `0x13360`
- `0x14230`
- `0x18520`
- `0x1ef40`
- `0x54380`
- `0x66ca0`
- `0x8a830`

## string_xrefs

- `0x5454a`: `The create operation is invalid because the `
- `0x5458b`: `The create operation is invalid because the `
- `0x545e3`: `The create operation is invalid because the `
- `0x54624`: `The create operation is invalid because the `

## pseudocode

```c

```

## disassembly

```asm
0x54380  ldarg.0
0x54381  brfalse  loc_5465D
0x54386  ldarg.1
0x54387  brfalse  loc_5465D
0x5438c  ldarg.2
0x5438d  brfalse  loc_5465D
0x54392  ldarg.2
0x54393  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x54398  callvirt instance string [mscorlib]System.Type::get_FullName()
0x5439d  ldstr    aMicrosoftCrmEn// "Microsoft.Crm.Entities.AsyncOperation"
0x543a2  ldc.i4.5
0x543a3  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x543a8  brtrue   loc_5465D
0x543ad  ldnull
0x543ae  stloc.0
0x543af  ldarg.1
0x543b0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest Microsoft.Crm.BusinessEntities.ExecutionContext::get_Request()
0x543b5  dup
0x543b6  brtrue.s loc_543BC
0x543b8  pop
0x543b9  ldc.i4.0
0x543ba  br.s     loc_543F6
0x543bc  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_Parameters()
0x543c1  dup
0x543c2  brtrue.s loc_543D0
0x543c4  pop
0x543c5  ldloca.s 3
0x543c7  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x543cd  ldloc.3
0x543ce  br.s     loc_543E1
0x543d0  ldstr    aTarget_0// "Target"
0x543d5  ldloca.s 0
0x543d7  call     instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x543dc  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x543e1  stloc.1
0x543e2  ldc.i4.1
0x543e3  stloc.2
0x543e4  ldloca.s 1
0x543e6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x543eb  ldloc.2
0x543ec  ceq
0x543ee  ldloca.s 1
0x543f0  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x543f5  and
0x543f6  brfalse  loc_5465D
0x543fb  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x54400  stloc.s  4
0x54402  ldloc.s  4
0x54404  ldloc.0
0x54405  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity
0x5440a  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x5440f  ldloc.s  4
0x54411  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x54416  dup
0x54417  brtrue.s loc_5441D
0x54419  pop
0x5441a  ldc.i4.0
0x5441b  br.s     loc_54422
0x5441d  call     instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_HasLazyFileAttribute()
0x54422  brfalse  loc_5465D
0x54427  ldnull
0x54428  stloc.s  5
0x5442a  ldloc.s  4
0x5442c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x54431  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x54436  dup
0x54437  brtrue.s loc_5443D
0x54439  pop
0x5443a  ldc.i4.0
0x5443b  br.s     loc_54450
0x5443d  ldloc.s  4
0x5443f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x54444  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LazyFileAttributeKey()
0x54449  ldloca.s 5
0x5444b  call     instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::TryGetValue(var<u1>, !!T0)
0x54450  brfalse  loc_5465D
0x54455  ldloc.s  5
0x54457  isinst   [mscorlib]System.String
0x5445c  stloc.s  6
0x5445e  ldloc.s  6
0x54460  ldsfld   string [mscorlib]System.String::Empty
0x54465  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5446a  brfalse  loc_5461C
0x5446f  ldloc.s  4
0x54471  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x54476  callvirt instance class [mscorlib]System.Lazy`1<object> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LazyFileAttributeValue()
0x5447b  stloc.s  7
0x5447d  ldloc.s  7
0x5447f  brfalse  loc_545DB
0x54484  ldarg.0
0x54485  callvirt instance class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.QueryPlan::get_Entity()
0x5448a  brfalse  loc_545DB
0x5448f  ldarg.0
0x54490  callvirt instance class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.QueryPlan::get_Entity()
0x54495  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5449a  brfalse  loc_545DB
0x5449f  ldarg.0
0x544a0  callvirt instance class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.QueryPlan::get_Entity()
0x544a5  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x544aa  callvirt instance class Microsoft.Crm.Query.AttributeExpressionCollection Microsoft.Crm.Query.ColumnSetExpression::get_Attributes()
0x544af  brfalse  loc_545DB
0x544b4  ldarg.0
0x544b5  callvirt instance class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.QueryPlan::get_Entity()
0x544ba  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x544bf  callvirt instance class Microsoft.Crm.Query.AttributeExpressionCollection Microsoft.Crm.Query.ColumnSetExpression::get_Attributes()
0x544c4  ldloc.s  4
0x544c6  ldftn    instance bool <>c__DisplayClass4_0::<ModifyPlan>b__0(class Microsoft.Crm.Query.AttributeExpression ae)
0x544cc  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Query.AttributeExpression, bool>::.ctor(object, native int)
0x544d1  call     T0x2B000085
0x544d6  call     T0x2B000086
0x544db  stloc.s  8
0x544dd  ldarg.0
0x544de  callvirt instance class Microsoft.Crm.Query.EntityExpression Microsoft.Crm.Query.QueryPlan::get_Entity()
0x544e3  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x544e8  callvirt instance class Microsoft.Crm.Query.AttributeExpressionCollection Microsoft.Crm.Query.ColumnSetExpression::get_Attributes()
0x544ed  ldloc.s  4
0x544ef  ldftn    instance bool <>c__DisplayClass4_0::<ModifyPlan>b__1(class Microsoft.Crm.Query.AttributeExpression ae)
0x544f5  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Query.AttributeExpression, bool>::.ctor(object, native int)
0x544fa  call     T0x2B000085
0x544ff  call     T0x2B000086
0x54504  stloc.s  9
0x54506  ldloc.s  8
0x54508  brfalse.s loc_54583
0x5450a  ldloc.s  9
0x5450c  brfalse.s loc_54583
0x5450e  ldloc.s  7
0x54510  callvirt instance var<u1> class [mscorlib]System.Lazy`1<object>::get_Value()
0x54515  isinst   [mscorlib]System.String
0x5451a  stloc.s  6
0x5451c  ldloc.s  6
0x5451e  brfalse.s loc_54542
0x54520  ldloc.s  8
0x54522  ldloc.s  6
0x54524  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_Value(object value)
0x54529  ldloc.s  9
0x5452b  ldloc.s  4
0x5452d  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x54532  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LazyFileSizeAttributeValue()
0x54537  box      [mscorlib]System.Int32
0x5453c  callvirt instance void Microsoft.Crm.Query.AttributeExpression::set_Value(object value)
0x54541  ret
0x54542  ldc.i4.5
0x54543  newarr   [mscorlib]System.String
0x54548  dup
0x54549  ldc.i4.0
0x5454a  ldstr    aTheCreateOpera// "The create operation is invalid because"...
0x5454f  stelem.ref
0x54550  dup
0x54551  ldc.i4.1
0x54552  ldarg.2
0x54553  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x54558  stelem.ref
0x54559  dup
0x5455a  ldc.i4.2
0x5455b  ldstr    aEnittyHasALazy// " enitty has a lazy file attribute named"...
0x54560  stelem.ref
0x54561  dup
0x54562  ldc.i4.3
0x54563  ldloc.s  4
0x54565  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x5456a  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LazyFileAttributeKey()
0x5456f  stelem.ref
0x54570  dup
0x54571  ldc.i4.4
0x54572  ldstr    aWhoseLazyValue// " whose lazy value is not a string."
0x54577  stelem.ref
0x54578  call     string [mscorlib]System.String::Concat(string[])
0x5457d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x54582  throw
0x54583  ldc.i4.7
0x54584  newarr   [mscorlib]System.String
0x54589  dup
0x5458a  ldc.i4.0
0x5458b  ldstr    aTheCreateOpera// "The create operation is invalid because"...
0x54590  stelem.ref
0x54591  dup
0x54592  ldc.i4.1
0x54593  ldarg.2
0x54594  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x54599  stelem.ref
0x5459a  dup
0x5459b  ldc.i4.2
0x5459c  ldstr    aEntityDoesNotH// " entity does not have a lazy file attri"...
0x545a1  stelem.ref
0x545a2  dup
0x545a3  ldc.i4.3
0x545a4  ldloc.s  4
0x545a6  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x545ab  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LazyFileAttributeKey()
0x545b0  stelem.ref
0x545b1  dup
0x545b2  ldc.i4.4
0x545b3  ldstr    aAndALazyFileSi// " and a lazy file size attribute named "
0x545b8  stelem.ref
0x545b9  dup
0x545ba  ldc.i4.5
0x545bb  ldloc.s  4
0x545bd  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x545c2  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LazyFileSizeAttributeKey()
0x545c7  stelem.ref
0x545c8  dup
0x545c9  ldc.i4.6
0x545ca  ldstr    asc_D651A// "."
0x545cf  stelem.ref
0x545d0  call     string [mscorlib]System.String::Concat(string[])
0x545d5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x545da  throw
0x545db  ldc.i4.5
0x545dc  newarr   [mscorlib]System.String
0x545e1  dup
0x545e2  ldc.i4.0
0x545e3  ldstr    aTheCreateOpera// "The create operation is invalid because"...
0x545e8  stelem.ref
0x545e9  dup
0x545ea  ldc.i4.1
0x545eb  ldarg.2
0x545ec  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x545f1  stelem.ref
0x545f2  dup
0x545f3  ldc.i4.2
0x545f4  ldstr    aEntityHasALazy// " entity has a lazy attribute value for "...
0x545f9  stelem.ref
0x545fa  dup
0x545fb  ldc.i4.3
0x545fc  ldloc.s  4
0x545fe  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x54603  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LazyFileAttributeKey()
0x54608  stelem.ref
0x54609  dup
0x5460a  ldc.i4.4
0x5460b  ldstr    aWhoseValueIsNo// " whose value is not a lazy<object>."
0x54610  stelem.ref
0x54611  call     string [mscorlib]System.String::Concat(string[])
0x54616  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x5461b  throw
0x5461c  ldc.i4.5
0x5461d  newarr   [mscorlib]System.String
0x54622  dup
0x54623  ldc.i4.0
0x54624  ldstr    aTheCreateOpera// "The create operation is invalid because"...
0x54629  stelem.ref
0x5462a  dup
0x5462b  ldc.i4.1
0x5462c  ldarg.2
0x5462d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x54632  stelem.ref
0x54633  dup
0x54634  ldc.i4.2
0x54635  ldstr    aHasALazyAttrib// " has a lazy attribute named "
0x5463a  stelem.ref
0x5463b  dup
0x5463c  ldc.i4.3
0x5463d  ldloc.s  4
0x5463f  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::target
0x54644  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LazyFileAttributeKey()
0x54649  stelem.ref
0x5464a  dup
0x5464b  ldc.i4.4
0x5464c  ldstr    aWhoseValueIsNo_0// " whose value is not null."
0x54651  stelem.ref
0x54652  call     string [mscorlib]System.String::Concat(string[])
0x54657  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x5465c  throw
0x5465d  ret
```
