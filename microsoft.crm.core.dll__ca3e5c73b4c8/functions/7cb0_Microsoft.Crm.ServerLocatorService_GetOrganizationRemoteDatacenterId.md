# Microsoft.Crm.ServerLocatorService::GetOrganizationRemoteDatacenterId

- ea: `0x7cb0`
- end: `0x7e95`
- name: `Microsoft.Crm.ServerLocatorService::GetOrganizationRemoteDatacenterId`
- size: `485`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa00`
- `0xde0`
- `0xfa0`
- `0x1350`
- `0x7cb0`
- `0x92c0`
- `0x9620`
- `0xbdf0`
- `0x444f0`

## string_xrefs

- `0x7cfe`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x7d60`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x7e00`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x7cb0  ldc.i4.2
0x7cb1  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetConfigSku()
0x7cb6  bne.un   loc_7E8C
0x7cbb  call     class Microsoft.Crm.IOrganizationMetadataProvider Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x7cc0  ldarg.1
0x7cc1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid organizationId)
0x7cc6  stloc.0
0x7cc7  call     class Microsoft.Crm.IDataCenterInfoProvider Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x7ccc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x7cd1  stloc.1
0x7cd2  ldarg.0
0x7cd3  ldstr    aScalegroup// "ScaleGroup"
0x7cd8  ldloc.0
0x7cd9  box      [mscorlib]System.Guid
0x7cde  ldc.i4.2
0x7cdf  newarr   [mscorlib]System.String
0x7ce4  dup
0x7ce5  ldc.i4.0
0x7ce6  ldstr    aIsxdbscalegrou// "IsXdbScaleGroup"
0x7ceb  stelem.ref
0x7cec  dup
0x7ced  ldc.i4.1
0x7cee  ldstr    aEnabledisaster// "EnableDisasterRecoveryForOrganizations"
0x7cf3  stelem.ref
0x7cf4  ldc.i4   0x364
0x7cf9  ldstr    aGetorganizatio_8// "GetOrganizationRemoteDatacenterId"
0x7cfe  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x7d03  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x7d08  stloc.2
0x7d09  ldloc.2
0x7d0a  ldstr    aIsxdbscalegrou// "IsXdbScaleGroup"
0x7d0f  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7d14  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x7d19  stloc.s  4
0x7d1b  ldloca.s 4
0x7d1d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x7d22  dup
0x7d23  brfalse.s loc_7D40
0x7d25  ldloc.2
0x7d26  ldstr    aEnabledisaster// "EnableDisasterRecoveryForOrganizations"
0x7d2b  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7d30  unbox.any valuetype [mscorlib]System.Nullable`1<bool>
0x7d35  stloc.s  4
0x7d37  ldloca.s 4
0x7d39  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::GetValueOrDefault()
0x7d3e  br.s     loc_7D41
0x7d40  ldc.i4.0
0x7d41  stloc.3
0x7d42  brfalse  loc_7DF0
0x7d47  ldloc.3
0x7d48  brtrue.s loc_7D50
0x7d4a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7d4f  ret
0x7d50  ldarg.0
0x7d51  ldstr    aServer// "Server"
0x7d56  ldc.i4   0x370
0x7d5b  ldstr    aGetorganizatio_8// "GetOrganizationRemoteDatacenterId"
0x7d60  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x7d65  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x7d6a  stloc.s  5
0x7d6c  ldloc.s  5
0x7d6e  brfalse  loc_7E8C
0x7d73  ldloc.s  5
0x7d75  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x7d7a  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x7d7f  stloc.s  6
0x7d81  br.s     loc_7DD4
0x7d83  ldloca.s 6
0x7d85  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x7d8a  stloc.s  7
0x7d8c  ldloc.s  7
0x7d8e  ldstr    aScalegroupid_0// "ScaleGroupId"
0x7d93  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7d98  unbox.any [mscorlib]System.Guid
0x7d9d  ldloc.0
0x7d9e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7da3  brtrue.s loc_7DD4
0x7da5  ldloc.s  7
0x7da7  ldstr    aDatacenterid// "DatacenterId"
0x7dac  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7db1  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x7db6  stloc.s  9
0x7db8  ldloca.s 9
0x7dba  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x7dbf  stloc.s  8
0x7dc1  ldloc.s  8
0x7dc3  ldloc.1
0x7dc4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7dc9  brfalse.s loc_7DD4
0x7dcb  ldloc.s  8
0x7dcd  stloc.s  0xA
0x7dcf  leave    loc_7E92
0x7dd4  ldloca.s 6
0x7dd6  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x7ddb  brtrue.s loc_7D83
0x7ddd  leave    loc_7E8C
0x7de2  ldloca.s 6
0x7de4  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x7dea  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7def  endfinally
0x7df0  ldarg.0
0x7df1  ldstr    aAvailabilitygr// "AvailabilityGroups"
0x7df6  ldc.i4   0x384
0x7dfb  ldstr    aGetorganizatio_8// "GetOrganizationRemoteDatacenterId"
0x7e00  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x7e05  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x7e0a  stloc.s  0xB
0x7e0c  ldloc.s  0xB
0x7e0e  brfalse.s loc_7E8C
0x7e10  ldloc.s  0xB
0x7e12  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x7e17  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x7e1c  stloc.s  6
0x7e1e  br.s     loc_7E73
0x7e20  ldloca.s 6
0x7e22  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x7e27  stloc.s  0xC
0x7e29  ldloc.s  0xC
0x7e2b  ldstr    aScalegroupid_0// "ScaleGroupId"
0x7e30  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7e35  unbox.any [mscorlib]System.Guid
0x7e3a  ldloc.0
0x7e3b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7e40  brtrue.s loc_7E73
0x7e42  ldloc.s  0xC
0x7e44  ldstr    aDatacenterid_0// "DataCenterId"
0x7e49  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7e4e  brfalse.s loc_7E73
0x7e50  ldloc.s  0xC
0x7e52  ldstr    aDatacenterid_0// "DataCenterId"
0x7e57  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x7e5c  unbox.any [mscorlib]System.Guid
0x7e61  stloc.s  0xD
0x7e63  ldloc.s  0xD
0x7e65  ldloc.1
0x7e66  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x7e6b  brfalse.s loc_7E73
0x7e6d  ldloc.s  0xD
0x7e6f  stloc.s  0xA
0x7e71  leave.s  loc_7E92
0x7e73  ldloca.s 6
0x7e75  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x7e7a  brtrue.s loc_7E20
0x7e7c  leave.s  loc_7E8C
0x7e7e  ldloca.s 6
0x7e80  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x7e86  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7e8b  endfinally
0x7e8c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7e91  ret
0x7e92  ldloc.s  0xA
0x7e94  ret
```
