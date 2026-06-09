# Microsoft.Crm.StorageNotificationUtility::RetrieveOrganizationSize

- ea: `0x25060`
- end: `0x2513d`
- name: `Microsoft.Crm.StorageNotificationUtility::RetrieveOrganizationSize`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x24df0`

## callees

- `0x25060`
- `0x251b0`

## string_xrefs

- `0x25093`: `Org not found in organization table, assuming deleted.`

## pseudocode

```c

```

## disassembly

```asm
0x25060  ldarg.0
0x25061  ldc.i4.4
0x25062  newarr   [mscorlib]System.String
0x25067  dup
0x25068  ldc.i4.0
0x25069  ldstr    aDatasizemb// "DataSizeMB"
0x2506e  stelem.ref
0x2506f  dup
0x25070  ldc.i4.1
0x25071  ldstr    aIndexsizemb// "IndexSizeMB"
0x25076  stelem.ref
0x25077  dup
0x25078  ldc.i4.2
0x25079  ldstr    aFreestoragemb// "FreeStorageMB"
0x2507e  stelem.ref
0x2507f  dup
0x25080  ldc.i4.3
0x25081  ldstr    aMaxstoragesize// "MaxStorageSizeMb"
0x25086  stelem.ref
0x25087  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.StorageNotificationUtility::RetrieveOrganizationDetails(valuetype [mscorlib]System.Guid organizationId, string[] columnNames)
0x2508c  stloc.0
0x2508d  ldloc.0
0x2508e  brtrue.s loc_250AB
0x25090  ldarg.0
0x25091  ldc.i4.s 0x14
0x25093  ldstr    aOrgNotFoundInO// "Org not found in organization table, as"...
0x25098  ldc.i4.0
0x25099  newarr   [mscorlib]System.Object
0x2509e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x250a3  ldc.i4.0
0x250a4  ldc.i4.0
0x250a5  newobj   instance void class [mscorlib]System.Tuple`2<int32, int32>::.ctor(var<u1>, !!T0)
0x250aa  ret
0x250ab  ldloc.0
0x250ac  ldstr    aDatasizemb// "DataSizeMB"
0x250b1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x250b6  brfalse.s loc_250CA
0x250b8  ldloc.0
0x250b9  ldstr    aDatasizemb// "DataSizeMB"
0x250be  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x250c3  unbox.any [mscorlib]System.Int32
0x250c8  br.s     loc_250CB
0x250ca  ldc.i4.0
0x250cb  ldloc.0
0x250cc  ldstr    aIndexsizemb// "IndexSizeMB"
0x250d1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x250d6  brfalse.s loc_250EA
0x250d8  ldloc.0
0x250d9  ldstr    aIndexsizemb// "IndexSizeMB"
0x250de  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x250e3  unbox.any [mscorlib]System.Int32
0x250e8  br.s     loc_250EB
0x250ea  ldc.i4.0
0x250eb  stloc.1
0x250ec  ldloc.0
0x250ed  ldstr    aFreestoragemb// "FreeStorageMB"
0x250f2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x250f7  brfalse.s loc_2510B
0x250f9  ldloc.0
0x250fa  ldstr    aFreestoragemb// "FreeStorageMB"
0x250ff  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x25104  unbox.any [mscorlib]System.Int32
0x25109  br.s     loc_2510C
0x2510b  ldc.i4.0
0x2510c  stloc.2
0x2510d  ldloc.0
0x2510e  ldstr    aMaxstoragesize// "MaxStorageSizeMb"
0x25113  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x25118  brfalse.s loc_2512C
0x2511a  ldloc.0
0x2511b  ldstr    aMaxstoragesize// "MaxStorageSizeMb"
0x25120  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x25125  unbox.any [mscorlib]System.Int32
0x2512a  br.s     loc_2512D
0x2512c  ldc.i4.0
0x2512d  stloc.3
0x2512e  ldloc.1
0x2512f  ldloc.2
0x25130  ldarg.1
0x25131  call     int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::CalculateEffectiveUsedStorageMB(int32, int32, int32, int32)
0x25136  ldloc.3
0x25137  newobj   instance void class [mscorlib]System.Tuple`2<int32, int32>::.ctor(var<u1>, !!T0)
0x2513c  ret
```
