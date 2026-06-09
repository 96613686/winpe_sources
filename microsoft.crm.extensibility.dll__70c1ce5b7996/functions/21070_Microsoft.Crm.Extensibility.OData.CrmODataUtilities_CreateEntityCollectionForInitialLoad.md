# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateEntityCollectionForInitialLoad

- ea: `0x21070`
- end: `0x210fd`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::CreateEntityCollectionForInitialLoad`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1d660`

## callees

- `0x21070`

## string_xrefs

- `0x210b6`: `Deleted Entity change is not supported in initial load`

## pseudocode

```c

```

## disassembly

```asm
0x21070  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0x21075  stloc.0
0x21076  ldnull
0x21077  stloc.1
0x21078  ldarg.0
0x21079  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChangesCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_Changes()
0x2107e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IChangedItem>::get_Count()
0x21083  ldc.i4.0
0x21084  ble.s    loc_210FB
0x21086  ldarg.0
0x21087  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChangesCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.BusinessEntityChanges::get_Changes()
0x2108c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IChangedItem>::GetEnumerator()
0x21091  stloc.2
0x21092  br.s     loc_210E7
0x21094  ldloc.2
0x21095  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IChangedItem>::get_Current()
0x2109a  stloc.3
0x2109b  ldloc.3
0x2109c  callvirt instance valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ChangeType [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IChangedItem::get_Type()
0x210a1  brtrue.s loc_210B1
0x210a3  ldloc.3
0x210a4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.NewOrUpdatedItem
0x210a9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.NewOrUpdatedItem::get_NewOrUpdatedEntity()
0x210ae  stloc.1
0x210af  br.s     loc_210C7
0x210b1  ldc.i4   0x1F5
0x210b6  ldstr    aDeletedEntityC// "Deleted Entity change is not supported "...
0x210bb  ldc.i4.0
0x210bc  newarr   [mscorlib]System.Object
0x210c1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x210c6  throw
0x210c7  ldloc.0
0x210c8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_EntityName()
0x210cd  brtrue.s loc_210DB
0x210cf  ldloc.0
0x210d0  ldloc.1
0x210d1  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x210d6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::set_EntityName(string)
0x210db  ldloc.0
0x210dc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x210e1  ldloc.1
0x210e2  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x210e7  ldloc.2
0x210e8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x210ed  brtrue.s loc_21094
0x210ef  leave.s  loc_210FB
0x210f1  ldloc.2
0x210f2  brfalse.s loc_210FA
0x210f4  ldloc.2
0x210f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x210fa  endfinally
0x210fb  ldloc.0
0x210fc  ret
```
