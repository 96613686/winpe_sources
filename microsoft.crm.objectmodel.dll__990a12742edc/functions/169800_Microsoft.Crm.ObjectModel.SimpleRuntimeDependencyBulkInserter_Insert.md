# Microsoft.Crm.ObjectModel.SimpleRuntimeDependencyBulkInserter::Insert

- ea: `0x169800`
- end: `0x1698f0`
- name: `Microsoft.Crm.ObjectModel.SimpleRuntimeDependencyBulkInserter::Insert`
- size: `240`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x16a030`
- `0x16a160`
- `0x16a2c0`

## callees

- `0x169800`

## string_xrefs

- `0x16980c`: `dependentComponentNodeId`
- `0x16986b`: `RequiredComponentNodeId`
- `0x169877`: `RequiredComponentType`
- `0x169888`: `DependentComponentNodeId`
- `0x169899`: `DependentComponentType`
- `0x1698ab`: `RequiredComponentModifiedTime`
- `0x1698c5`: `CreatedTime`
- `0x169801`: `requiredComponentNodeId`
- `0x169818`: `dependentComponentNodeType`
- `0x169823`: `requiredComponentType`

## pseudocode

```c

```

## disassembly

```asm
0x169800  ldarg.1
0x169801  ldstr    aRequiredcompon_9// "requiredComponentNodeId"
0x169806  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x16980b  ldarg.3
0x16980c  ldstr    aDependentcompo_5// "dependentComponentNodeId"
0x169811  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x169816  ldarg.s  4
0x169818  ldstr    aDependentcompo_9// "dependentComponentNodeType"
0x16981d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x169822  ldarg.2
0x169823  ldstr    aRequiredcompon_10// "requiredComponentType"
0x169828  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x16982d  ldarga.s 3
0x16982f  ldarg.1
0x169830  constrained. [mscorlib]System.Guid
0x169836  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x16983b  brfalse.s loc_169849
0x16983d  ldarg.0
0x16983e  ldfld    string Microsoft.Crm.ObjectModel.SimpleRuntimeDependencyBulkInserter::CircularDependency
0x169843  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x169848  throw
0x169849  ldarg.0
0x16984a  call     instance class [System.Data]System.Data.DataTable [Microsoft.Crm]Microsoft.Crm.BusinessEntities.SimpleBulkInserterWithType::get_InsertTable()
0x16984f  callvirt instance class [System.Data]System.Data.DataRow [System.Data]System.Data.DataTable::NewRow()
0x169854  stloc.0
0x169855  ldloc.0
0x169856  ldstr    aDependencyid_0// "DependencyId"
0x16985b  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x169860  box      [mscorlib]System.Guid
0x169865  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x16986a  ldloc.0
0x16986b  ldstr    aRequiredcompon_6// "RequiredComponentNodeId"
0x169870  ldarg.1
0x169871  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x169876  ldloc.0
0x169877  ldstr    aRequiredcompon_7// "RequiredComponentType"
0x16987c  ldarg.2
0x16987d  box      [mscorlib]System.Int32
0x169882  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x169887  ldloc.0
0x169888  ldstr    aDependentcompo_7// "DependentComponentNodeId"
0x16988d  ldarg.3
0x16988e  box      [mscorlib]System.Guid
0x169893  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x169898  ldloc.0
0x169899  ldstr    aDependentcompo_8// "DependentComponentType"
0x16989e  ldarg.s  4
0x1698a0  box      [mscorlib]System.Int32
0x1698a5  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x1698aa  ldloc.0
0x1698ab  ldstr    aRequiredcompon_8// "RequiredComponentModifiedTime"
0x1698b0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x1698b5  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::ToSqlDateTime()
0x1698ba  box      [mscorlib]System.DateTime
0x1698bf  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x1698c4  ldloc.0
0x1698c5  ldstr    aCreatedtime// "CreatedTime"
0x1698ca  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x1698cf  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::ToSqlDateTime()
0x1698d4  box      [mscorlib]System.DateTime
0x1698d9  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x1698de  ldarg.0
0x1698df  call     instance class [System.Data]System.Data.DataTable [Microsoft.Crm]Microsoft.Crm.BusinessEntities.SimpleBulkInserterWithType::get_InsertTable()
0x1698e4  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x1698e9  ldloc.0
0x1698ea  callvirt instance void [System.Data]System.Data.DataRowCollection::Add(class [System.Data]System.Data.DataRow)
0x1698ef  ret
```
