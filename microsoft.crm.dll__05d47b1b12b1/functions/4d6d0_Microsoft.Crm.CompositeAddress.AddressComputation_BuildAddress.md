# Microsoft.Crm.CompositeAddress.AddressComputation::BuildAddress

- ea: `0x4d6d0`
- end: `0x4e07c`
- name: `Microsoft.Crm.CompositeAddress.AddressComputation::BuildAddress`
- size: `2476`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x4d6d0`
- `0x4e080`
- `0x4e0e0`
- `0x4e370`
- `0x4e3d0`
- `0x4e3e0`
- `0x4e4f0`
- `0x4e530`
- `0x4eeb0`
- `0x4eed0`
- `0x4f010`
- `0x4f020`
- `0x4f030`
- `0x4f040`
- `0x4f050`
- `0x4f060`
- `0x4f070`
- `0x4f080`

## pseudocode

```c

```

## disassembly

```asm
0x4d6d0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x4d6d5  stloc.s  9
0x4d6d7  ldarg.0
0x4d6d8  ldarg.0
0x4d6d9  ldfld    string Microsoft.Crm.CompositeAddress.AddressComputation::street
0x4d6de  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4d6e3  ldc.i4.0
0x4d6e4  ceq
0x4d6e6  stfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fStreet
0x4d6eb  ldarg.0
0x4d6ec  ldarg.0
0x4d6ed  ldfld    string Microsoft.Crm.CompositeAddress.AddressComputation::postalCode
0x4d6f2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4d6f7  ldc.i4.0
0x4d6f8  ceq
0x4d6fa  stfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCode
0x4d6ff  ldarg.0
0x4d700  ldarg.0
0x4d701  ldfld    string Microsoft.Crm.CompositeAddress.AddressComputation::city
0x4d706  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4d70b  ldc.i4.0
0x4d70c  ceq
0x4d70e  stfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCity
0x4d713  ldarg.0
0x4d714  ldarg.0
0x4d715  ldfld    string Microsoft.Crm.CompositeAddress.AddressComputation::state
0x4d71a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4d71f  ldc.i4.0
0x4d720  ceq
0x4d722  stfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fState
0x4d727  ldc.i4.1
0x4d728  stloc.0
0x4d729  ldarg.0
0x4d72a  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fStreet
0x4d72f  brtrue.s loc_4D763
0x4d731  ldarg.0
0x4d732  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCode
0x4d737  brtrue.s loc_4D763
0x4d739  ldarg.0
0x4d73a  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCity
0x4d73f  brtrue.s loc_4D763
0x4d741  ldarg.0
0x4d742  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fState
0x4d747  brtrue.s loc_4D763
0x4d749  ldarg.0
0x4d74a  ldfld    string Microsoft.Crm.CompositeAddress.AddressComputation::country
0x4d74f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4d754  brfalse.s loc_4D763
0x4d756  ldloc.s  9
0x4d758  callvirt instance string [mscorlib]System.Object::ToString()
0x4d75d  callvirt instance string [mscorlib]System.String::Trim()
0x4d762  ret
0x4d763  ldarg.0
0x4d764  ldarg.0
0x4d765  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d76a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d76f  ldarg.0
0x4d770  ldfld    string Microsoft.Crm.CompositeAddress.AddressComputation::country
0x4d775  call     instance int32 Microsoft.Crm.CompositeAddress.AddressComputation::GetIndexForCountry(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> countryInfo, string country_Value)
0x4d77a  stfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d77f  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d784  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d789  ldarg.0
0x4d78a  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d78f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo>::get_Item(!!T0)
0x4d794  callvirt instance int32 Microsoft.Crm.CompositeAddress.CountryInfo::get_FormatParameters()
0x4d799  call     int32 Microsoft.Crm.CompositeAddress.CountryInfo::GetCodeLocation(int32 formatters)
0x4d79e  stloc.s  6
0x4d7a0  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d7a5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d7aa  ldarg.0
0x4d7ab  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d7b0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo>::get_Item(!!T0)
0x4d7b5  callvirt instance int32 Microsoft.Crm.CompositeAddress.CountryInfo::get_FormatParameters()
0x4d7ba  call     bool Microsoft.Crm.CompositeAddress.CountryInfo::IsStateOnOwnLine(int32 formatters)
0x4d7bf  stloc.1
0x4d7c0  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d7c5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d7ca  ldarg.0
0x4d7cb  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d7d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo>::get_Item(!!T0)
0x4d7d5  callvirt instance int32 Microsoft.Crm.CompositeAddress.CountryInfo::get_FormatParameters()
0x4d7da  call     bool Microsoft.Crm.CompositeAddress.CountryInfo::IsStateBeforeCity(int32 formatters)
0x4d7df  stloc.2
0x4d7e0  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d7e5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d7ea  ldarg.0
0x4d7eb  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d7f0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo>::get_Item(!!T0)
0x4d7f5  callvirt instance int32 Microsoft.Crm.CompositeAddress.CountryInfo::get_FormatParameters()
0x4d7fa  call     bool Microsoft.Crm.CompositeAddress.CountryInfo::IsUpsideDown(int32 formatters)
0x4d7ff  stloc.3
0x4d800  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d805  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d80a  ldarg.0
0x4d80b  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d810  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo>::get_Item(!!T0)
0x4d815  callvirt instance int32 Microsoft.Crm.CompositeAddress.CountryInfo::get_FormatParameters()
0x4d81a  call     bool Microsoft.Crm.CompositeAddress.CountryInfo::IsStateInBracesOnly(int32 formatters)
0x4d81f  stloc.s  5
0x4d821  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d826  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d82b  ldarg.0
0x4d82c  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d831  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo>::get_Item(!!T0)
0x4d836  callvirt instance int32 Microsoft.Crm.CompositeAddress.CountryInfo::get_FormatParameters()
0x4d83b  call     int32 Microsoft.Crm.CompositeAddress.CountryInfo::GetCityPostalCodeSeparator(int32 formatters)
0x4d840  stloc.s  8
0x4d842  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d847  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d84c  ldarg.0
0x4d84d  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d852  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo>::get_Item(!!T0)
0x4d857  callvirt instance int32 Microsoft.Crm.CompositeAddress.CountryInfo::get_FormatParameters()
0x4d85c  call     int32 Microsoft.Crm.CompositeAddress.CountryInfo::GetCityStateSeparator(int32 formatters)
0x4d861  stloc.s  7
0x4d863  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d868  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d86d  ldarg.0
0x4d86e  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d873  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo>::get_Item(!!T0)
0x4d878  callvirt instance int32 Microsoft.Crm.CompositeAddress.CountryInfo::get_FormatParameters()
0x4d87d  call     bool Microsoft.Crm.CompositeAddress.CountryInfo::IsBlankLineAfterStreet(int32 formatters)
0x4d882  stloc.s  4
0x4d884  ldarg.0
0x4d885  call     class Microsoft.Crm.CompositeAddress.CountryTable Microsoft.Crm.CompositeAddress.CountryTable::get_Instance()
0x4d88a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo> Microsoft.Crm.CompositeAddress.CountryTable::get_CountryList()
0x4d88f  ldarg.0
0x4d890  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d895  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.CompositeAddress.CountryInfo>::get_Item(!!T0)
0x4d89a  callvirt instance int32 Microsoft.Crm.CompositeAddress.CountryInfo::get_Lcid()
0x4d89f  stfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::LCID
0x4d8a4  ldarg.0
0x4d8a5  ldarg.0
0x4d8a6  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::LCID
0x4d8ab  call     instance int32 Microsoft.Crm.CompositeAddress.AddressComputation::GetPrimaryLangId(int32 lcid)
0x4d8b0  ldc.i4.s 0x11
0x4d8b2  beq.s    loc_4D900
0x4d8b4  ldarg.0
0x4d8b5  ldarg.0
0x4d8b6  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::LCID
0x4d8bb  call     instance int32 Microsoft.Crm.CompositeAddress.AddressComputation::GetPrimaryLangId(int32 lcid)
0x4d8c0  ldc.i4.s 0x12
0x4d8c2  beq.s    loc_4D900
0x4d8c4  ldarg.0
0x4d8c5  ldarg.0
0x4d8c6  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::LCID
0x4d8cb  call     instance int32 Microsoft.Crm.CompositeAddress.AddressComputation::GetPrimaryLangId(int32 lcid)
0x4d8d0  ldc.i4.4
0x4d8d1  bne.un.s loc_4D92D
0x4d8d3  ldarg.0
0x4d8d4  ldarg.0
0x4d8d5  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::LCID
0x4d8da  call     instance int32 Microsoft.Crm.CompositeAddress.AddressComputation::GetSecondaryLangId(int32 lcid)
0x4d8df  ldc.i4.1
0x4d8e0  beq.s    loc_4D900
0x4d8e2  ldarg.0
0x4d8e3  ldarg.0
0x4d8e4  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::LCID
0x4d8e9  call     instance int32 Microsoft.Crm.CompositeAddress.AddressComputation::GetSecondaryLangId(int32 lcid)
0x4d8ee  ldc.i4.2
0x4d8ef  beq.s    loc_4D900
0x4d8f1  ldarg.0
0x4d8f2  ldarg.0
0x4d8f3  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::LCID
0x4d8f8  call     instance int32 Microsoft.Crm.CompositeAddress.AddressComputation::GetSecondaryLangId(int32 lcid)
0x4d8fd  ldc.i4.4
0x4d8fe  bne.un.s loc_4D92D
0x4d900  ldarg.0
0x4d901  ldarg.0
0x4d902  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fState
0x4d907  ldarg.0
0x4d908  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCity
0x4d90d  ldarg.0
0x4d90e  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fStreet
0x4d913  call     instance bool Microsoft.Crm.CompositeAddress.AddressComputation::DetectLocalAddress(bool stateExists, bool cityExists, bool streetExists)
0x4d918  brfalse.s loc_4D92D
0x4d91a  ldarg.0
0x4d91b  ldarg.0
0x4d91c  ldfld    int32 Microsoft.Crm.CompositeAddress.AddressComputation::countryIndex
0x4d921  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.CompositeAddress.AddressComputation::GenerateAddress(int32 index)
0x4d926  stloc.s  9
0x4d928  br       loc_4E06F
0x4d92d  ldloc.s  6
0x4d92f  ldc.i4.4
0x4d930  bne.un.s loc_4D96D
0x4d932  ldarg.0
0x4d933  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCode
0x4d938  brfalse.s loc_4D96D
0x4d93a  ldloc.s  9
0x4d93c  ldarg.0
0x4d93d  ldfld    string Microsoft.Crm.CompositeAddress.AddressComputation::postalCode
0x4d942  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d947  pop
0x4d948  ldarg.0
0x4d949  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fStreet
0x4d94e  brtrue.s loc_4D960
0x4d950  ldarg.0
0x4d951  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCity
0x4d956  brtrue.s loc_4D960
0x4d958  ldarg.0
0x4d959  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fState
0x4d95e  br.s     loc_4D961
0x4d960  ldc.i4.1
0x4d961  ldloc.0
0x4d962  or
0x4d963  brfalse.s loc_4D96D
0x4d965  ldloc.s  9
0x4d967  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x4d96c  pop
0x4d96d  ldloc.3
0x4d96e  brtrue.s loc_4D9BC
0x4d970  ldarg.0
0x4d971  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fStreet
0x4d976  brfalse.s loc_4D9BC
0x4d978  ldloc.s  9
0x4d97a  ldarg.0
0x4d97b  ldfld    string Microsoft.Crm.CompositeAddress.AddressComputation::street
0x4d980  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d985  pop
0x4d986  ldarg.0
0x4d987  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCode
0x4d98c  brfalse.s loc_4D993
0x4d98e  ldloc.s  6
0x4d990  ldc.i4.4
0x4d991  bne.un.s loc_4D9A3
0x4d993  ldarg.0
0x4d994  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCity
0x4d999  brtrue.s loc_4D9A3
0x4d99b  ldarg.0
0x4d99c  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fState
0x4d9a1  br.s     loc_4D9A4
0x4d9a3  ldc.i4.1
0x4d9a4  ldloc.0
0x4d9a5  or
0x4d9a6  brfalse.s loc_4D9BC
0x4d9a8  ldloc.s  9
0x4d9aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x4d9af  pop
0x4d9b0  ldloc.s  4
0x4d9b2  brfalse.s loc_4D9BC
0x4d9b4  ldloc.s  9
0x4d9b6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x4d9bb  pop
0x4d9bc  ldloc.3
0x4d9bd  brfalse.s loc_4D9C7
0x4d9bf  ldarg.0
0x4d9c0  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fState
0x4d9c5  br.s     loc_4D9C8
0x4d9c7  ldc.i4.0
0x4d9c8  ldloc.1
0x4d9c9  and
0x4d9ca  brfalse.s loc_4DA42
0x4d9cc  ldloc.s  5
0x4d9ce  brfalse.s loc_4D9DD
0x4d9d0  ldloc.s  9
0x4d9d2  ldstr    asc_6E4B2// "("
0x4d9d7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d9dc  pop
0x4d9dd  ldloc.s  9
0x4d9df  ldarg.0
0x4d9e0  ldfld    string Microsoft.Crm.CompositeAddress.AddressComputation::state
0x4d9e5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d9ea  pop
0x4d9eb  ldloc.s  5
0x4d9ed  brfalse.s loc_4D9FC
0x4d9ef  ldloc.s  9
0x4d9f1  ldstr    asc_6B046// ")"
0x4d9f6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d9fb  pop
0x4d9fc  ldarg.0
0x4d9fd  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCode
0x4da02  brfalse.s loc_4DA18
0x4da04  ldloc.s  6
0x4da06  ldc.i4.3
0x4da07  bne.un.s loc_4DA18
0x4da09  ldloc.s  9
0x4da0b  ldstr    asc_6B04A// " "
0x4da10  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4da15  pop
0x4da16  br.s     loc_4DA42
0x4da18  ldarg.0
0x4da19  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCode
0x4da1e  brfalse.s loc_4DA25
0x4da20  ldloc.s  6
0x4da22  ldc.i4.4
0x4da23  bne.un.s loc_4DA35
0x4da25  ldarg.0
0x4da26  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fCity
0x4da2b  brtrue.s loc_4DA35
0x4da2d  ldarg.0
0x4da2e  ldfld    bool Microsoft.Crm.CompositeAddress.AddressComputation::fStreet
0x4da33  br.s     loc_4DA36
0x4da35  ldc.i4.1
0x4da36  ldloc.0
0x4da37  or
0x4da38  brfalse.s loc_4DA42
0x4da3a  ldloc.s  9
0x4da3c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x4da41  pop
  ... truncated ...
```
