# Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::LoadSettingsXml

- ea: `0x5370`
- end: `0x54f3`
- name: `Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::LoadSettingsXml`
- size: `387`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d80`
- `0x4d20`

## callees

- `0x5230`
- `0x5370`
- `0x5500`
- `0x5530`

## string_xrefs

- `0x5401`: `ConfigurationName`
- `0x5440`: `LoadSettingsXml`
- `0x5445`: `D:\a\1\s\src\Platform\Authentication\Legacy\Settings\WebConfigAuthenticationSettings.cs`
- `0x5469`: `Error retrieving authentication setting XML from database for authentication strategy : {0} and type : {1}.  There should only be 1 and only 1 configuration defined for each authentication strategy (i.e. Live, OnPremise, SPLA, Portal...)`

## pseudocode

```c

```

## disassembly

```asm
0x5370  ldarg.1
0x5371  ldstr    aHandler// "handler"
0x5376  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x537b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x5380  stloc.0
0x5381  ldsfld   string [mscorlib]System.String::Empty
0x5386  stloc.1
0x5387  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x538c  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x5391  ldc.i4.1
0x5392  bne.un.s loc_53C2
0x5394  ldarg.0
0x5395  call     instance bool Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::IsIfdEnabled()
0x539a  brfalse.s loc_53AF
0x539c  ldc.i4.4
0x539d  stloc.s  5
0x539f  ldloca.s 5
0x53a1  constrained. Microsoft.Crm.Authentication.AuthenticationStrategy
0x53a7  callvirt instance string [mscorlib]System.Object::ToString()
0x53ac  stloc.1
0x53ad  br.s     loc_5400
0x53af  ldc.i4.2
0x53b0  stloc.s  5
0x53b2  ldloca.s 5
0x53b4  constrained. Microsoft.Crm.Authentication.AuthenticationStrategy
0x53ba  callvirt instance string [mscorlib]System.Object::ToString()
0x53bf  stloc.1
0x53c0  br.s     loc_5400
0x53c2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x53c7  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x53cc  ldc.i4.2
0x53cd  bne.un.s loc_5400
0x53cf  ldarg.0
0x53d0  ldfld    class Microsoft.Crm.Authentication.AuthenticationSettingsXml Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::_settingsXml
0x53d5  callvirt instance bool Microsoft.Crm.Authentication.AuthenticationSettingsXml::get_IsPortal()
0x53da  brfalse.s loc_53EF
0x53dc  ldc.i4.3
0x53dd  stloc.s  5
0x53df  ldloca.s 5
0x53e1  constrained. Microsoft.Crm.Authentication.AuthenticationStrategy
0x53e7  callvirt instance string [mscorlib]System.Object::ToString()
0x53ec  stloc.1
0x53ed  br.s     loc_5400
0x53ef  ldc.i4.1
0x53f0  stloc.s  5
0x53f2  ldloca.s 5
0x53f4  constrained. Microsoft.Crm.Authentication.AuthenticationStrategy
0x53fa  callvirt instance string [mscorlib]System.Object::ToString()
0x53ff  stloc.1
0x5400  ldloc.0
0x5401  ldstr    aConfigurationn// "ConfigurationName"
0x5406  ldloc.1
0x5407  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x540c  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x5411  ldstr    aAuthentication_2// "AuthenticationSettings"
0x5416  ldc.i4.2
0x5417  newarr   [mscorlib]System.String
0x541c  dup
0x541d  ldc.i4.0
0x541e  ldstr    aId// "Id"
0x5423  stelem.ref
0x5424  dup
0x5425  ldc.i4.1
0x5426  ldarga.s 2
0x5428  constrained. Microsoft.Crm.Authentication.AuthenticationSettingType
0x542e  callvirt instance string [mscorlib]System.Object::ToString()
0x5433  stelem.ref
0x5434  ldc.i4.1
0x5435  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x543a  dup
0x543b  ldc.i4.0
0x543c  ldloc.0
0x543d  stelem.ref
0x543e  ldc.i4.s 0x52
0x5440  ldstr    aLoadsettingsxm// "LoadSettingsXml"
0x5445  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Authenticat"...
0x544a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x544f  stloc.2
0x5450  ldloc.2
0x5451  brfalse.s loc_5464
0x5453  ldloc.2
0x5454  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x5459  ldc.i4.1
0x545a  bne.un.s loc_5464
0x545c  ldloc.2
0x545d  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x5462  brtrue.s loc_548C
0x5464  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5469  ldstr    aErrorRetrievin// "Error retrieving authentication setting"...
0x546e  ldc.i4.2
0x546f  newarr   [mscorlib]System.Object
0x5474  dup
0x5475  ldc.i4.0
0x5476  ldloc.1
0x5477  stelem.ref
0x5478  dup
0x5479  ldc.i4.1
0x547a  ldarg.2
0x547b  box      Microsoft.Crm.Authentication.AuthenticationSettingType
0x5480  stelem.ref
0x5481  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5486  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x548b  throw
0x548c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x5491  stloc.3
0x5492  ldloc.2
0x5493  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x5498  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x549d  stloc.s  6
0x549f  br.s     loc_54AB
0x54a1  ldloca.s 6
0x54a3  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x54a8  stloc.3
0x54a9  leave.s  loc_54C4
0x54ab  ldloca.s 6
0x54ad  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x54b2  brtrue.s loc_54A1
0x54b4  leave.s  loc_54C4
0x54b6  ldloca.s 6
0x54b8  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x54be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x54c3  endfinally
0x54c4  ldloc.3
0x54c5  ldarga.s 2
0x54c7  constrained. Microsoft.Crm.Authentication.AuthenticationSettingType
0x54cd  callvirt instance string [mscorlib]System.Object::ToString()
0x54d2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x54d7  castclass [mscorlib]System.String
0x54dc  stloc.s  4
0x54de  ldarg.2
0x54df  brtrue.s loc_54EA
0x54e1  ldloc.s  4
0x54e3  call     string Microsoft.Crm.Authentication.WebConfigAuthenticationSettings::TransformXmlForAssembly(string rawAuthXml)
0x54e8  stloc.s  4
0x54ea  ldarg.1
0x54eb  ldloc.s  4
0x54ed  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.BaseConfigurationSectionHandler::CreateFromString(string)
0x54f2  ret
```
