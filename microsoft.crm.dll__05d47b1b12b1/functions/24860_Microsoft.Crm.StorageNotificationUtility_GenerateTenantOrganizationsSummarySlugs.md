# Microsoft.Crm.StorageNotificationUtility::GenerateTenantOrganizationsSummarySlugs

- ea: `0x24860`
- end: `0x24bbb`
- name: `Microsoft.Crm.StorageNotificationUtility::GenerateTenantOrganizationsSummarySlugs`
- size: `859`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x24760`

## callees

- `0x15c80`
- `0x15d20`
- `0x24860`
- `0x24ca0`
- `0x24df0`
- `0x25140`
- `0x251b0`
- `0x4fd50`
- `0x4fd70`
- `0x4fd90`
- `0x4fdb0`
- `0x4fdd0`
- `0x4fec0`

## string_xrefs

- `0x248ef`: `Org not found in organization table, assuming deleted.`
- `0x24b92`: `COPY_YEAR`

## pseudocode

```c

```

## disassembly

```asm
0x24860  newobj   instance void <>c__DisplayClass21_0::.ctor()
0x24865  stloc.0
0x24866  ldloc.0
0x24867  ldc.i4   0x800
0x2486c  stfld    int32 <>c__DisplayClass21_0::tablePartMaxSize
0x24871  ldc.i4.6
0x24872  stloc.1
0x24873  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x24878  stloc.2
0x24879  ldarg.0
0x2487a  call     class TenantStorageDetails Microsoft.Crm.StorageNotificationUtility::RetrieveMsOnlineStorageDetails(valuetype [mscorlib]System.Guid orgId)
0x2487f  stloc.3
0x24880  call     class Microsoft.Crm.StorageNotificationEventSource Microsoft.Crm.StorageNotificationEventSource::get_Instance()
0x24885  ldarg.0
0x24886  ldloc.3
0x24887  callvirt instance string TenantStorageDetails::GetOrganizationSizesAsString()
0x2488c  ldloc.3
0x2488d  callvirt instance int32 TenantStorageDetails::get_MaxStorage()
0x24892  ldloc.3
0x24893  callvirt instance int32 TenantStorageDetails::get_CurrentSize()
0x24898  ldloc.3
0x24899  callvirt instance int32 TenantStorageDetails::get_ThresholdPercentage()
0x2489e  callvirt instance void Microsoft.Crm.StorageNotificationEventSource::StorageInformationForEmail(valuetype [mscorlib]System.Guid organizationId, string associatesOrganizations, int32 maxStorage, int32 currentSize, int32 thresholdPercentage)
0x248a3  ldloc.3
0x248a4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32> TenantStorageDetails::get_OrgSizes()
0x248a9  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int32>::GetEnumerator()
0x248ae  stloc.s  7
0x248b0  br       loc_249AD
0x248b5  ldloca.s 7
0x248b7  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, int32>::get_Current()
0x248bc  stloc.s  8
0x248be  ldloca.s 8
0x248c0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, int32>::get_Key()
0x248c5  ldc.i4.2
0x248c6  newarr   [mscorlib]System.String
0x248cb  dup
0x248cc  ldc.i4.0
0x248cd  ldstr    aFriendlyname// "FriendlyName"
0x248d2  stelem.ref
0x248d3  dup
0x248d4  ldc.i4.1
0x248d5  ldstr    aType// "Type"
0x248da  stelem.ref
0x248db  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.StorageNotificationUtility::RetrieveOrganizationDetails(valuetype [mscorlib]System.Guid organizationId, string[] columnNames)
0x248e0  stloc.s  9
0x248e2  ldloc.s  9
0x248e4  brtrue.s loc_24904
0x248e6  ldloca.s 8
0x248e8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, int32>::get_Key()
0x248ed  ldc.i4.s 0x14
0x248ef  ldstr    aOrgNotFoundInO// "Org not found in organization table, as"...
0x248f4  ldc.i4.0
0x248f5  newarr   [mscorlib]System.Object
0x248fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x248ff  br       loc_249AD
0x24904  ldloca.s 8
0x24906  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, int32>::get_Key()
0x2490b  call     int32 Microsoft.Crm.StorageNotificationUtility::RetrieveOrganizationLanguageCode(valuetype [mscorlib]System.Guid orgId)
0x24910  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x24915  stloc.s  0xA
0x24917  ldloc.s  9
0x24919  ldstr    aFriendlyname// "FriendlyName"
0x2491e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x24923  castclass [mscorlib]System.String
0x24928  stloc.s  0xB
0x2492a  ldloc.s  9
0x2492c  ldstr    aType// "Type"
0x24931  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x24936  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType
0x2493b  stloc.s  0xC
0x2493d  ldloc.s  0xC
0x2493f  ldloc.s  0xA
0x24941  call     string Microsoft.Crm.StorageNotificationUtility::GetOrganizationTypeName(valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType type, class [mscorlib]System.Globalization.CultureInfo culture)
0x24946  stloc.s  0xD
0x24948  ldc.i4.s 0xB
0x2494a  ldloc.s  0xC
0x2494c  bne.un.s loc_2495A
0x2494e  ldc.i4.s 0xC
0x24950  ldloc.s  0xC
0x24952  bne.un.s loc_2495A
0x24954  ldc.i4.s 0xD
0x24956  ldloc.s  0xC
0x24958  beq.s    loc_249AD
0x2495a  ldloca.s 8
0x2495c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, int32>::get_Value()
0x24961  conv.r8
0x24962  ldc.r8   1024.0
0x2496b  div
0x2496c  stloc.s  0x10
0x2496e  ldloca.s 0x10
0x24970  ldstr    a0000// "#,0.000"
0x24975  ldloc.s  0xA
0x24977  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x2497c  stloc.s  0xE
0x2497e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24983  ldstr    aTrTdStyleFontS// "<tr>\r\n\t<td style=\"font-size:12px;pa"...
0x24988  ldc.i4.3
0x24989  newarr   [mscorlib]System.Object
0x2498e  dup
0x2498f  ldc.i4.0
0x24990  ldloc.s  0xB
0x24992  stelem.ref
0x24993  dup
0x24994  ldc.i4.1
0x24995  ldloc.s  0xD
0x24997  stelem.ref
0x24998  dup
0x24999  ldc.i4.2
0x2499a  ldloc.s  0xE
0x2499c  stelem.ref
0x2499d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x249a2  stloc.s  0xF
0x249a4  ldloc.2
0x249a5  ldloc.s  0xF
0x249a7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x249ac  pop
0x249ad  ldloca.s 7
0x249af  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, int32>::MoveNext()
0x249b4  brtrue   loc_248B5
0x249b9  leave.s  loc_249C9
0x249bb  ldloca.s 7
0x249bd  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, int32>
0x249c3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x249c8  endfinally
0x249c9  ldloc.0
0x249ca  ldloc.2
0x249cb  callvirt instance string [mscorlib]System.Object::ToString()
0x249d0  stfld    string <>c__DisplayClass21_0::html
0x249d5  ldloc.0
0x249d6  ldfld    string <>c__DisplayClass21_0::html
0x249db  ldsfld   class [mscorlib]System.Func`3<char, int32, int32> <>c::<>9__21_0
0x249e0  dup
0x249e1  brtrue.s loc_249FA
0x249e3  pop
0x249e4  ldsfld   class <>c <>c::<>9
0x249e9  ldftn    instance int32 <>c::<GenerateTenantOrganizationsSummarySlugs>b__21_0(char x, int32 i)
0x249ef  newobj   instance void class [mscorlib]System.Func`3<char, int32, int32>::.ctor(object, native int)
0x249f4  dup
0x249f5  stsfld   class [mscorlib]System.Func`3<char, int32, int32> <>c::<>9__21_0
0x249fa  call     T0x2B00001D
0x249ff  ldloc.0
0x24a00  ldftn    instance bool <>c__DisplayClass21_0::<GenerateTenantOrganizationsSummarySlugs>b__1(int32 i)
0x24a06  newobj   instance void class [mscorlib]System.Func`2<int32, bool>::.ctor(object, native int)
0x24a0b  call     T0x2B00001E
0x24a10  ldloc.0
0x24a11  ldftn    instance string <>c__DisplayClass21_0::<GenerateTenantOrganizationsSummarySlugs>b__2(int32 i)
0x24a17  newobj   instance void class [mscorlib]System.Func`2<int32, string>::.ctor(object, native int)
0x24a1c  call     T0x2B00001F
0x24a21  call     T0x2B000020
0x24a26  stloc.s  4
0x24a28  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x24a2d  stloc.s  5
0x24a2f  ldc.i4.0
0x24a30  stloc.s  0x11
0x24a32  br.s     loc_24A81
0x24a34  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24a39  ldstr    aInstancesTable// "INSTANCES_TABLE_{0}"
0x24a3e  ldc.i4.1
0x24a3f  newarr   [mscorlib]System.Object
0x24a44  dup
0x24a45  ldc.i4.0
0x24a46  ldloc.s  0x11
0x24a48  ldc.i4.1
0x24a49  add
0x24a4a  box      [mscorlib]System.Int32
0x24a4f  stelem.ref
0x24a50  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x24a55  stloc.s  0x12
0x24a57  ldloc.s  5
0x24a59  ldloc.s  0x12
0x24a5b  ldloc.s  0x11
0x24a5d  ldloc.s  4
0x24a5f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x24a64  blt.s    loc_24A6D
0x24a66  ldstr    asc_6B04A// " "
0x24a6b  br.s     loc_24A76
0x24a6d  ldloc.s  4
0x24a6f  ldloc.s  0x11
0x24a71  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x24a76  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x24a7b  ldloc.s  0x11
0x24a7d  ldc.i4.1
0x24a7e  add
0x24a7f  stloc.s  0x11
0x24a81  ldloc.s  0x11
0x24a83  ldloc.1
0x24a84  blt.s    loc_24A34
0x24a86  ldloc.3
0x24a87  callvirt instance int32 TenantStorageDetails::get_MaxStorage()
0x24a8c  ldc.i4.0
0x24a8d  bgt.s    loc_24A9A
0x24a8f  ldc.r8   0.0
0x24a98  br.s     loc_24AB3
0x24a9a  ldloc.3
0x24a9b  callvirt instance int32 TenantStorageDetails::get_CurrentSize()
0x24aa0  conv.r8
0x24aa1  ldc.r8   100.0
0x24aaa  mul
0x24aab  ldloc.3
0x24aac  callvirt instance int32 TenantStorageDetails::get_MaxStorage()
0x24ab1  conv.r8
0x24ab2  div
0x24ab3  stloc.s  6
0x24ab5  ldloc.s  5
0x24ab7  ldstr    aUsedStorage// "USED_STORAGE"
0x24abc  ldloc.3
0x24abd  callvirt instance int32 TenantStorageDetails::get_CurrentSize()
0x24ac2  conv.r8
0x24ac3  ldc.r8   1024.0
0x24acc  div
0x24acd  stloc.s  0x10
0x24acf  ldloca.s 0x10
0x24ad1  ldstr    a0000// "#,0.000"
0x24ad6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24adb  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x24ae0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x24ae5  ldloc.s  5
0x24ae7  ldstr    aMaxStorage// "MAX_STORAGE"
0x24aec  ldloc.3
0x24aed  callvirt instance int32 TenantStorageDetails::get_MaxStorage()
0x24af2  conv.r8
0x24af3  ldc.r8   1024.0
0x24afc  div
0x24afd  stloc.s  0x10
0x24aff  ldloca.s 0x10
0x24b01  ldstr    a0000// "#,0.000"
0x24b06  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24b0b  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x24b10  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x24b15  ldloc.s  5
0x24b17  ldstr    aUsedStoragePer// "USED_STORAGE_PERCENTAGE"
0x24b1c  ldloca.s 6
0x24b1e  ldstr    a000// "#,0.00"
0x24b23  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24b28  call     instance string [mscorlib]System.Double::ToString(string, class [mscorlib]System.IFormatProvider)
0x24b2d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x24b32  ldloc.s  5
0x24b34  ldstr    aTotalBarWidth// "TOTAL_BAR_WIDTH"
0x24b39  ldloc.s  6
0x24b3b  ldc.r8   100.0
0x24b44  bgt.s    loc_24B4A
0x24b46  ldloc.s  6
0x24b48  br.s     loc_24B53
0x24b4a  ldc.r8   100.0
0x24b53  call     float64 [mscorlib]System.Math::Round(float64)
0x24b58  stloc.s  0x10
0x24b5a  ldloca.s 0x10
0x24b5c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24b61  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x24b66  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x24b6b  ldloc.s  5
0x24b6d  ldstr    aTotalBarColor// "TOTAL_BAR_COLOR"
0x24b72  ldloc.s  6
0x24b74  ldc.r8   100.0
0x24b7d  blt.s    loc_24B86
0x24b7f  ldstr    aFf0000// "#ff0000"
0x24b84  br.s     loc_24B8B
0x24b86  ldstr    aF09b21// "#f09b21"
0x24b8b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x24b90  ldloc.s  5
0x24b92  ldstr    aCopyYear// "COPY_YEAR"
0x24b97  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x24b9c  stloc.s  0x13
0x24b9e  ldloca.s 0x13
0x24ba0  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x24ba5  stloc.s  0x14
0x24ba7  ldloca.s 0x14
0x24ba9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24bae  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x24bb3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x24bb8  ldloc.s  5
0x24bba  ret
```
