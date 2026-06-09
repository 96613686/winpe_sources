# Microsoft.Crm.OrganizationStorageSetUtility::GetPrimaryOrganization

- ea: `0x21c10`
- end: `0x21dd5`
- name: `Microsoft.Crm.OrganizationStorageSetUtility::GetPrimaryOrganization`
- size: `453`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x21bd0`
- `0x24510`

## callees

- `0x21c10`

## string_xrefs

- `0x21cf1`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0x21c10  ldarg.0
0x21c11  ldstr    aOrganizationid_0// "organizationId"
0x21c16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x21c1b  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x21c20  ldarg.0
0x21c21  call     instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DoesOrgExist(valuetype [mscorlib]System.Guid)
0x21c26  brtrue.s loc_21C4C
0x21c28  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x21c2d  ldstr    aGetprimaryorga// "GetPrimaryOrganization: Organization '{"...
0x21c32  ldc.i4.1
0x21c33  newarr   [mscorlib]System.Object
0x21c38  dup
0x21c39  ldc.i4.0
0x21c3a  ldarg.0
0x21c3b  box      [mscorlib]System.Guid
0x21c40  stelem.ref
0x21c41  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x21c46  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x21c4b  throw
0x21c4c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x21c51  ldarg.0
0x21c52  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x21c57  brtrue.s loc_21C5B
0x21c59  ldarg.0
0x21c5a  ret
0x21c5b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x21c60  stloc.0
0x21c61  ldloc.0
0x21c62  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x21c67  ldarg.0
0x21c68  box      [mscorlib]System.Guid
0x21c6d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x21c72  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x21c77  ldstr    aOrganizationli// "OrganizationLifecycle"
0x21c7c  ldc.i4.1
0x21c7d  newarr   [mscorlib]System.String
0x21c82  dup
0x21c83  ldc.i4.0
0x21c84  ldstr    aContextid// "ContextId"
0x21c89  stelem.ref
0x21c8a  ldloc.0
0x21c8b  ldc.i4.s 0x6A
0x21c8d  ldstr    aGetprimaryorga_0// "GetPrimaryOrganization"
0x21c92  ldstr    aDA1SSrcSharedS_3// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x21c97  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveSingleRow(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x21c9c  stloc.1
0x21c9d  ldloc.1
0x21c9e  brfalse.s loc_21CAD
0x21ca0  ldloc.1
0x21ca1  ldstr    aContextid// "ContextId"
0x21ca6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x21cab  brtrue.s loc_21CAF
0x21cad  ldarg.0
0x21cae  ret
0x21caf  ldloc.1
0x21cb0  ldstr    aContextid// "ContextId"
0x21cb5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x21cba  unbox.any [mscorlib]System.Guid
0x21cbf  stloc.2
0x21cc0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x21cc5  stloc.3
0x21cc6  ldloc.3
0x21cc7  ldstr    aContextid// "ContextId"
0x21ccc  ldloc.2
0x21ccd  box      [mscorlib]System.Guid
0x21cd2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x21cd7  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x21cdc  ldstr    aOrganizationli// "OrganizationLifecycle"
0x21ce1  ldc.i4.3
0x21ce2  newarr   [mscorlib]System.String
0x21ce7  dup
0x21ce8  ldc.i4.0
0x21ce9  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x21cee  stelem.ref
0x21cef  dup
0x21cf0  ldc.i4.1
0x21cf1  ldstr    aCreatedon// "CreatedOn"
0x21cf6  stelem.ref
0x21cf7  dup
0x21cf8  ldc.i4.2
0x21cf9  ldstr    aStatuscode// "StatusCode"
0x21cfe  stelem.ref
0x21cff  ldc.i4.1
0x21d00  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x21d05  dup
0x21d06  ldc.i4.0
0x21d07  ldloc.3
0x21d08  stelem.ref
0x21d09  ldc.i4.s 0x78
0x21d0b  ldstr    aGetprimaryorga_0// "GetPrimaryOrganization"
0x21d10  ldstr    aDA1SSrcSharedS_3// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x21d15  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x21d1a  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool> <>c::<>9__2_0
0x21d1f  dup
0x21d20  brtrue.s loc_21D39
0x21d22  pop
0x21d23  ldsfld   class <>c <>c::<>9
0x21d28  ldftn    instance bool <>c::<GetPrimaryOrganization>b__2_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> org)
0x21d2e  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool>::.ctor(object, native int)
0x21d33  dup
0x21d34  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool> <>c::<>9__2_0
0x21d39  call     T0x2B000013
0x21d3e  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, valuetype [mscorlib]System.DateTime> <>c::<>9__2_1
0x21d43  dup
0x21d44  brtrue.s loc_21D5D
0x21d46  pop
0x21d47  ldsfld   class <>c <>c::<>9
0x21d4c  ldftn    instance valuetype [mscorlib]System.DateTime <>c::<GetPrimaryOrganization>b__2_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> org)
0x21d52  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, valuetype [mscorlib]System.DateTime>::.ctor(object, native int)
0x21d57  dup
0x21d58  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, valuetype [mscorlib]System.DateTime> <>c::<>9__2_1
0x21d5d  call     T0x2B000014
0x21d62  stloc.s  4
0x21d64  ldloc.s  4
0x21d66  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool> <>c::<>9__2_2
0x21d6b  dup
0x21d6c  brtrue.s loc_21D85
0x21d6e  pop
0x21d6f  ldsfld   class <>c <>c::<>9
0x21d74  ldftn    instance bool <>c::<GetPrimaryOrganization>b__2_2(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> org)
0x21d7a  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool>::.ctor(object, native int)
0x21d7f  dup
0x21d80  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, bool> <>c::<>9__2_2
0x21d85  call     T0x2B000013
0x21d8a  stloc.s  5
0x21d8c  ldloc.s  5
0x21d8e  call     T0x2B000015
0x21d93  brfalse.s loc_21DB5
0x21d95  ldloc.s  5
0x21d97  call     T0x2B000016
0x21d9c  stloc.s  6
0x21d9e  ldloca.s 6
0x21da0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x21da5  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x21daa  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x21daf  unbox.any [mscorlib]System.Guid
0x21db4  ret
0x21db5  ldloc.s  4
0x21db7  call     T0x2B000016
0x21dbc  stloc.s  6
0x21dbe  ldloca.s 6
0x21dc0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x21dc5  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x21dca  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x21dcf  unbox.any [mscorlib]System.Guid
0x21dd4  ret
```
