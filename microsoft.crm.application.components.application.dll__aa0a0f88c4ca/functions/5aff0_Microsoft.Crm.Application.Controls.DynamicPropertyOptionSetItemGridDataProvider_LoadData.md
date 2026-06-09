# Microsoft.Crm.Application.Controls.DynamicPropertyOptionSetItemGridDataProvider::LoadData

- ea: `0x5aff0`
- end: `0x5b0c0`
- name: `Microsoft.Crm.Application.Controls.DynamicPropertyOptionSetItemGridDataProvider::LoadData`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x546d0`
- `0x5aff0`

## string_xrefs

- `0x5b068`: `canDelete`
- `0x5b07b`: `canDelete`
- `0x5b092`: `canDelete`
- `0x5b08c`: `canDelete_Hidden`
- `0x5b023`: `canDeleteDynamicProperty`
- `0x5b03f`: `canDeleteDynamicProperty`
- `0x5b056`: `canDeleteDynamicProperty`

## pseudocode

```c

```

## disassembly

```asm
0x5aff0  ldarg.0
0x5aff1  call     instance void Microsoft.Crm.Application.Controls.InlineEditGridDataProvider::LoadData()
0x5aff6  ldarg.0
0x5aff7  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Results()
0x5affc  callvirt instance class [System.Data]System.Data.DataTable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridData::get_Data()
0x5b001  callvirt instance class [System.Data]System.Data.DataRowCollection [System.Data]System.Data.DataTable::get_Rows()
0x5b006  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Data]System.Data.InternalDataCollectionBase::GetEnumerator()
0x5b00b  stloc.0
0x5b00c  br       loc_5B0A1
0x5b011  ldloc.0
0x5b012  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5b017  castclass [System.Data]System.Data.DataRow
0x5b01c  stloc.1
0x5b01d  ldarg.0
0x5b01e  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5b023  ldstr    aCandeletedynam// "canDeleteDynamicProperty"
0x5b028  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5b02d  ldstr    aUndefined// "undefined"
0x5b032  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5b037  brfalse.s loc_5B07A
0x5b039  ldarg.0
0x5b03a  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5b03f  ldstr    aCandeletedynam// "canDeleteDynamicProperty"
0x5b044  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5b049  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5b04e  brtrue.s loc_5B07A
0x5b050  ldarg.0
0x5b051  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5b056  ldstr    aCandeletedynam// "canDeleteDynamicProperty"
0x5b05b  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x5b060  call     bool [mscorlib]System.Boolean::Parse(string)
0x5b065  brtrue.s loc_5B07A
0x5b067  ldloc.1
0x5b068  ldstr    aCandelete// "canDelete"
0x5b06d  ldc.i4.0
0x5b06e  box      [mscorlib]System.Boolean
0x5b073  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x5b078  br.s     loc_5B08B
0x5b07a  ldloc.1
0x5b07b  ldstr    aCandelete// "canDelete"
0x5b080  ldc.i4.1
0x5b081  box      [mscorlib]System.Boolean
0x5b086  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x5b08b  ldloc.1
0x5b08c  ldstr    aCandeleteHidde// "canDelete_Hidden"
0x5b091  ldloc.1
0x5b092  ldstr    aCandelete// "canDelete"
0x5b097  callvirt instance object [System.Data]System.Data.DataRow::get_Item(string)
0x5b09c  callvirt instance void [System.Data]System.Data.DataRow::set_Item(string, object)
0x5b0a1  ldloc.0
0x5b0a2  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5b0a7  brtrue   loc_5B011
0x5b0ac  leave.s  loc_5B0BF
0x5b0ae  ldloc.0
0x5b0af  isinst   [mscorlib]System.IDisposable
0x5b0b4  stloc.2
0x5b0b5  ldloc.2
0x5b0b6  brfalse.s loc_5B0BE
0x5b0b8  ldloc.2
0x5b0b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b0be  endfinally
0x5b0bf  ret
```
