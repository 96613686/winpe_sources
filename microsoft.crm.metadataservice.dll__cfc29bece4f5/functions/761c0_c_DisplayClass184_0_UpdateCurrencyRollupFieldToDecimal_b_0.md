# <>c__DisplayClass184_0::<UpdateCurrencyRollupFieldToDecimal>b__0

- ea: `0x761c0`
- end: `0x7655f`
- name: `<>c__DisplayClass184_0::<UpdateCurrencyRollupFieldToDecimal>b__0`
- size: `927`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x25220`
- `0x761c0`

## string_xrefs

- `0x76242`: `extensiontablename`
- `0x7627f`: `extensiontablename`
- `0x76480`: `Update store procedures for the rollup field {0}`

## pseudocode

```c

```

## disassembly

```asm
0x761c0  ldarg.0
0x761c1  ldarg.0
0x761c2  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass184_0::attributeMetadata
0x761c7  ldstr    aTablecolumnnam// "tablecolumnname"
0x761cc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x761d1  castclass [mscorlib]System.String
0x761d6  stfld    string <>c__DisplayClass184_0::tableColumnName
0x761db  ldarg.0
0x761dc  ldarg.0
0x761dd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass184_0::attributeMetadata
0x761e2  ldstr    aDefaultvalue_0// "defaultvalue"
0x761e7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x761ec  castclass [mscorlib]System.String
0x761f1  stfld    string <>c__DisplayClass184_0::attributeDefaultValue
0x761f6  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x761fb  ldstr    aRetrieveParent// "Retrieve parent entity"
0x76200  ldc.i4.0
0x76201  newarr   [mscorlib]System.Object
0x76206  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x7620b  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x76210  ldarg.0
0x76211  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass184_0::attributeMetadata
0x76216  ldstr    aEntityid// "entityid"
0x7621b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x76220  unbox.any [mscorlib]System.Guid
0x76225  ldstr    aEntity_0// "Entity"
0x7622a  ldc.i4.3
0x7622b  newarr   [mscorlib]System.String
0x76230  dup
0x76231  ldc.i4.0
0x76232  ldstr    aIslogicalentit// "islogicalentity"
0x76237  stelem.ref
0x76238  dup
0x76239  ldc.i4.1
0x7623a  ldstr    aBasetablename// "basetablename"
0x7623f  stelem.ref
0x76240  dup
0x76241  ldc.i4.2
0x76242  ldstr    aExtensiontable// "extensiontablename"
0x76247  stelem.ref
0x76248  ldarg.0
0x76249  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x7624e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x76253  stloc.0
0x76254  ldarg.0
0x76255  ldarg.0
0x76256  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass184_0::attributeMetadata
0x7625b  ldstr    aIsstoredonprim// "isstoredonprimarytable"
0x76260  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x76265  unbox.any [mscorlib]System.Boolean
0x7626a  brfalse.s loc_7627E
0x7626c  ldloc.0
0x7626d  ldstr    aBasetablename// "basetablename"
0x76272  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x76277  castclass [mscorlib]System.String
0x7627c  br.s     loc_7628E
0x7627e  ldloc.0
0x7627f  ldstr    aExtensiontable// "extensiontablename"
0x76284  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x76289  castclass [mscorlib]System.String
0x7628e  stfld    string <>c__DisplayClass184_0::tableName
0x76293  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x76298  dup
0x76299  ldstr    aTablecolumnnam_0// "tableColumnName"
0x7629e  ldarg.0
0x7629f  ldfld    string <>c__DisplayClass184_0::tableColumnName
0x762a4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x762a9  dup
0x762aa  ldstr    aTablename// "tableName"
0x762af  ldarg.0
0x762b0  ldfld    string <>c__DisplayClass184_0::tableName
0x762b5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x762ba  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryCustomProperty::AddCustomProperties(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>)
0x762bf  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x762c4  ldstr    aGetDataTypeFor// "Get data type for sql column {0}"
0x762c9  ldc.i4.1
0x762ca  newarr   [mscorlib]System.Object
0x762cf  dup
0x762d0  ldc.i4.0
0x762d1  ldarg.0
0x762d2  ldfld    string <>c__DisplayClass184_0::tableColumnName
0x762d7  stelem.ref
0x762d8  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x762dd  ldarg.0
0x762de  ldfld    string <>c__DisplayClass184_0::tableName
0x762e3  ldarg.0
0x762e4  ldfld    string <>c__DisplayClass184_0::tableColumnName
0x762e9  ldarg.0
0x762ea  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x762ef  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x762f4  call     string [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::GetSQLColumnDataType(string, string, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x762f9  ldstr    aMoney// "money"
0x762fe  call     bool [mscorlib]System.String::Equals(string, string)
0x76303  brtrue.s loc_76306
0x76305  ret
0x76306  ldarg.0
0x76307  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity <>c__DisplayClass184_0::attributeMetadata
0x7630c  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity)
0x76311  stloc.1
0x76312  ldloc.1
0x76313  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_IsBaseCurrency()
0x76318  brtrue   loc_76518
0x7631d  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x76322  ldstr    aRetrieveDepend// "Retrieve dependent calculated fields"
0x76327  ldc.i4.0
0x76328  newarr   [mscorlib]System.Object
0x7632d  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x76332  ldloc.1
0x76333  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x76338  ldarg.0
0x76339  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x7633e  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag> Microsoft.Crm.Metadata.AttributeService::RetrieveDependentCalculatedAttributes(valuetype [mscorlib]System.Guid attributeId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x76343  stloc.2
0x76344  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x76349  ldstr    aDropUdfReferen// "Drop UDF reference of dependent calcula"...
0x7634e  ldc.i4.0
0x7634f  newarr   [mscorlib]System.Object
0x76354  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x76359  ldloc.2
0x7635a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>::GetEnumerator()
0x7635f  stloc.3
0x76360  br.s     loc_763A1
0x76362  ldloca.s 3
0x76364  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>::get_Current()
0x76369  stloc.s  4
0x7636b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x76370  ldstr    aDropUdfReferen_0// "Drop UDF reference of {0}"
0x76375  ldc.i4.1
0x76376  newarr   [mscorlib]System.Object
0x7637b  dup
0x7637c  ldc.i4.0
0x7637d  ldloc.s  4
0x7637f  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_LogicalName()
0x76384  stelem.ref
0x76385  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x7638a  ldloc.s  4
0x7638c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x76391  ldarg.0
0x76392  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x76397  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x7639c  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::DropUdfReferenceForCalculatedField(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x763a1  ldloca.s 3
0x763a3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>::MoveNext()
0x763a8  brtrue.s loc_76362
0x763aa  leave.s  loc_763BA
0x763ac  ldloca.s 3
0x763ae  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>
0x763b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x763b9  endfinally
0x763ba  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x763bf  ldstr    aAlterSqlColumn// "Alter sql column {0}.{1} to decimal typ"...
0x763c4  ldc.i4.2
0x763c5  newarr   [mscorlib]System.Object
0x763ca  dup
0x763cb  ldc.i4.0
0x763cc  ldarg.0
0x763cd  ldfld    string <>c__DisplayClass184_0::tableName
0x763d2  stelem.ref
0x763d3  dup
0x763d4  ldc.i4.1
0x763d5  ldarg.0
0x763d6  ldfld    string <>c__DisplayClass184_0::tableColumnName
0x763db  stelem.ref
0x763dc  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x763e1  ldloc.1
0x763e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x763e7  ldarg.0
0x763e8  ldfld    string <>c__DisplayClass184_0::tableName
0x763ed  ldarg.0
0x763ee  ldfld    string <>c__DisplayClass184_0::tableColumnName
0x763f3  ldc.i4.1
0x763f4  ldarg.0
0x763f5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x763fa  ldc.i4.1
0x763fb  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ChangeSqlColumnTypeToDecimal(valuetype [mscorlib]System.Guid, string, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x76400  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x76405  ldstr    aRestoreUdfRefe// "Restore UDF reference of dependent calc"...
0x7640a  ldc.i4.0
0x7640b  newarr   [mscorlib]System.Object
0x76410  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x76415  ldloc.2
0x76416  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>::GetEnumerator()
0x7641b  stloc.3
0x7641c  br.s     loc_76462
0x7641e  ldloca.s 3
0x76420  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>::get_Current()
0x76425  stloc.s  5
0x76427  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x7642c  ldstr    aRestoreUdfRefe_0// "Restore UDF reference of {0}"
0x76431  ldc.i4.1
0x76432  newarr   [mscorlib]System.Object
0x76437  dup
0x76438  ldc.i4.0
0x76439  ldloc.s  5
0x7643b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_LogicalName()
0x76440  stelem.ref
0x76441  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x76446  ldloc.s  5
0x76448  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x7644d  ldarg.0
0x7644e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x76453  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x76458  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SystemFormService::.ctor()
0x7645d  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::RestoreUdfReferenceForCalculatedField(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.IBusinessProcessObject)
0x76462  ldloca.s 3
0x76464  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>::MoveNext()
0x76469  brtrue.s loc_7641E
0x7646b  leave.s  loc_7647B
0x7646d  ldloca.s 3
0x7646f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag>
0x76475  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7647a  endfinally
0x7647b  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x76480  ldstr    aUpdateStorePro// "Update store procedures for the rollup "...
0x76485  ldc.i4.1
0x76486  newarr   [mscorlib]System.Object
0x7648b  dup
0x7648c  ldc.i4.0
0x7648d  ldloc.1
0x7648e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_LogicalName()
0x76493  stelem.ref
0x76494  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x76499  ldarg.0
0x7649a  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RollupPropertiesService <>c__DisplayClass184_0::rollupPropertiesService
0x7649f  ldloc.1
0x764a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x764a5  ldarg.0
0x764a6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x764ab  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RollupPropertiesService::UpdateStoredProcedure(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x764b0  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x764b5  ldstr    aRestoreDefault// "Restore default constraint"
0x764ba  ldc.i4.0
0x764bb  newarr   [mscorlib]System.Object
0x764c0  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x764c5  ldarg.0
0x764c6  ldfld    string <>c__DisplayClass184_0::tableName
0x764cb  ldarg.0
0x764cc  ldfld    string <>c__DisplayClass184_0::tableColumnName
0x764d1  ldarg.0
0x764d2  ldfld    string <>c__DisplayClass184_0::attributeDefaultValue
0x764d7  ldarg.0
0x764d8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x764dd  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::AddDefaultConstraint(string, string, string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x764e2  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x764e7  ldstr    aScheduleBootst// "Schedule bootstrap job for {0}"
0x764ec  ldc.i4.1
0x764ed  newarr   [mscorlib]System.Object
0x764f2  dup
0x764f3  ldc.i4.0
0x764f4  ldloc.1
0x764f5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_LogicalName()
0x764fa  stelem.ref
0x764fb  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x76500  ldarg.0
0x76501  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RollupPropertiesService <>c__DisplayClass184_0::rollupPropertiesService
0x76506  ldloc.1
0x76507  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x7650c  ldarg.0
0x7650d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x76512  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RollupPropertiesService::RecalculateRollup(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x76517  ret
0x76518  ldsfld   class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Metadata.AttributeService::Logger
0x7651d  ldstr    aThisIsBaseCurr// "This is base currency rollup field. Alt"...
0x76522  ldc.i4.2
0x76523  newarr   [mscorlib]System.Object
0x76528  dup
0x76529  ldc.i4.0
0x7652a  ldarg.0
0x7652b  ldfld    string <>c__DisplayClass184_0::tableName
0x76530  stelem.ref
0x76531  dup
0x76532  ldc.i4.1
0x76533  ldarg.0
0x76534  ldfld    string <>c__DisplayClass184_0::tableColumnName
0x76539  stelem.ref
0x7653a  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x7653f  ldloc.1
0x76540  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_AttributeId()
0x76545  ldarg.0
0x76546  ldfld    string <>c__DisplayClass184_0::tableName
0x7654b  ldarg.0
0x7654c  ldfld    string <>c__DisplayClass184_0::tableColumnName
0x76551  ldc.i4.1
0x76552  ldarg.0
0x76553  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass184_0::context
0x76558  ldc.i4.1
0x76559  call     void [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::ChangeSqlColumnTypeToDecimal(valuetype [mscorlib]System.Guid, string, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x7655e  ret
```
