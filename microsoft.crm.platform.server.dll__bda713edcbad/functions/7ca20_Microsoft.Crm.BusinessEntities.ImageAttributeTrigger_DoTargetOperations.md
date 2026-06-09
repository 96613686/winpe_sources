# Microsoft.Crm.BusinessEntities.ImageAttributeTrigger::DoTargetOperations

- ea: `0x7ca20`
- end: `0x7cb78`
- name: `Microsoft.Crm.BusinessEntities.ImageAttributeTrigger::DoTargetOperations`
- size: `344`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x7c740`
- `0x7c750`
- `0x7c760`

## callees

- `0x13c30`
- `0x150a0`
- `0x15a40`
- `0x1ab10`
- `0x1ae30`
- `0x1ef80`
- `0x222b0`
- `0x5d5d0`
- `0x7c620`
- `0x7c970`
- `0x7ca20`
- `0x90910`
- `0x90920`
- `0x90930`
- `0x90960`

## string_xrefs

- `0x7ca98`: `ImageDescriptor`
- `0x7cac2`: `ImageDescriptor`
- `0x7cb05`: `ImageDescriptor`
- `0x7cb21`: `ImageDescriptor`
- `0x7ca67`: `imagedescriptorid`
- `0x7cad4`: `imagedescriptorid`

## pseudocode

```c

```

## disassembly

```asm
0x7ca20  ldarg.0
0x7ca21  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ImageTriggerData> Microsoft.Crm.BusinessEntities.ImageAttributeTrigger::_imageTriggerOperations
0x7ca26  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class ImageTriggerData>::get_Values()
0x7ca2b  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class ImageTriggerData>::GetEnumerator()
0x7ca30  stloc.0
0x7ca31  br       loc_7CB5B
0x7ca36  ldloca.s 0
0x7ca38  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class ImageTriggerData>::get_Current()
0x7ca3d  stloc.1
0x7ca3e  ldloc.1
0x7ca3f  callvirt instance valuetype Microsoft.Crm.BusinessEntities.OperationType ImageTriggerData::get_Operation()
0x7ca44  stloc.2
0x7ca45  ldnull
0x7ca46  stloc.3
0x7ca47  ldnull
0x7ca48  stloc.s  4
0x7ca4a  ldloc.2
0x7ca4b  ldc.i4.1
0x7ca4c  bne.un.s loc_7CABA
0x7ca4e  ldloc.1
0x7ca4f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x7ca54  callvirt instance void ImageTriggerData::set_ImageId(valuetype [mscorlib]System.Guid value)
0x7ca59  ldarg.0
0x7ca5a  ldloc.1
0x7ca5b  ldarg.1
0x7ca5c  call     instance void Microsoft.Crm.BusinessEntities.ImageAttributeTrigger::SetColumnSet(class ImageTriggerData triggerData, valuetype [mscorlib]System.Guid id)
0x7ca61  ldarg.0
0x7ca62  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7ca67  ldstr    aImagedescripto_0// "imagedescriptorid"
0x7ca6c  ldloc.1
0x7ca6d  callvirt instance valuetype [mscorlib]System.Guid ImageTriggerData::get_ImageId()
0x7ca72  box      [mscorlib]System.Guid
0x7ca77  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName, object value)
0x7ca7c  ldarg.0
0x7ca7d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.EntityChangingTrigger::get_Entity()
0x7ca82  ldloc.1
0x7ca83  callvirt instance string ImageTriggerData::get_AttributeOfName()
0x7ca88  ldloc.1
0x7ca89  callvirt instance valuetype [mscorlib]System.Guid ImageTriggerData::get_ImageId()
0x7ca8e  box      [mscorlib]System.Guid
0x7ca93  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7ca98  ldstr    aImagedescripto// "ImageDescriptor"
0x7ca9d  ldarg.0
0x7ca9e  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7caa3  ldarg.0
0x7caa4  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7caa9  newobj   instance void Microsoft.Crm.Query.CreatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x7caae  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x7cab3  stloc.s  4
0x7cab5  br       loc_7CB3F
0x7caba  ldloc.2
0x7cabb  ldc.i4.4
0x7cabc  beq.s    loc_7CAC2
0x7cabe  ldloc.2
0x7cabf  ldc.i4.2
0x7cac0  bne.un.s loc_7CB3F
0x7cac2  ldstr    aImagedescripto// "ImageDescriptor"
0x7cac7  ldarg.0
0x7cac8  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7cacd  newobj   instance void Microsoft.Crm.Query.FilterExpression::.ctor(string entityPlatformName, class Microsoft.Crm.BusinessEntities.ExecutionContext orgContext)
0x7cad2  stloc.3
0x7cad3  ldloc.3
0x7cad4  ldstr    aImagedescripto_0// "imagedescriptorid"
0x7cad9  ldc.i4.0
0x7cada  ldloc.1
0x7cadb  callvirt instance valuetype [mscorlib]System.Guid ImageTriggerData::get_ImageId()
0x7cae0  box      [mscorlib]System.Guid
0x7cae5  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x7caea  pop
0x7caeb  ldloc.2
0x7caec  ldc.i4.4
0x7caed  bne.un.s loc_7CB19
0x7caef  ldarg.0
0x7caf0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.BusinessEntities.EntityChangingTrigger::get_Entity()
0x7caf5  ldloc.1
0x7caf6  callvirt instance string ImageTriggerData::get_AttributeOfName()
0x7cafb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x7cb00  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7cb05  ldstr    aImagedescripto// "ImageDescriptor"
0x7cb0a  ldloc.3
0x7cb0b  newobj   instance void Microsoft.Crm.Query.DeletePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.FilterExpression criteria)
0x7cb10  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x7cb15  stloc.s  4
0x7cb17  br.s     loc_7CB3F
0x7cb19  ldarg.0
0x7cb1a  ldloc.1
0x7cb1b  ldarg.1
0x7cb1c  call     instance void Microsoft.Crm.BusinessEntities.ImageAttributeTrigger::SetColumnSet(class ImageTriggerData triggerData, valuetype [mscorlib]System.Guid id)
0x7cb21  ldstr    aImagedescripto// "ImageDescriptor"
0x7cb26  ldarg.0
0x7cb27  ldfld    class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.BusinessEntities.TriggerBase::columnSet
0x7cb2c  ldloc.3
0x7cb2d  ldarg.0
0x7cb2e  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7cb33  newobj   instance void Microsoft.Crm.Query.UpdatePlan::.ctor(string entityPlatformName, class Microsoft.Crm.Query.ColumnSetExpression 'cs', class Microsoft.Crm.Query.FilterExpression criteria, class Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0x7cb38  call     instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Query.QueryPlan::get_Command()
0x7cb3d  stloc.s  4
0x7cb3f  ldloc.s  4
0x7cb41  brfalse.s loc_7CB5B
0x7cb43  ldloc.s  4
0x7cb45  ldarg.0
0x7cb46  ldfld    class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.BusinessEntities.TriggerBase::context
0x7cb4b  call     int32 Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteNonQuery(class [System.Data]System.Data.IDbCommand command, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x7cb50  pop
0x7cb51  leave.s  loc_7CB5B
0x7cb53  ldloc.s  4
0x7cb55  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7cb5a  endfinally
0x7cb5b  ldloca.s 0
0x7cb5d  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class ImageTriggerData>::MoveNext()
0x7cb62  brtrue   loc_7CA36
0x7cb67  leave.s  loc_7CB77
0x7cb69  ldloca.s 0
0x7cb6b  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class ImageTriggerData>
0x7cb71  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7cb76  endfinally
0x7cb77  ret
```
