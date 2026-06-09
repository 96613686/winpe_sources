# Microsoft.Crm.LanguageUtility::PreferredLanguageToLcid

- ea: `0x20a10`
- end: `0x20af7`
- name: `Microsoft.Crm.LanguageUtility::PreferredLanguageToLcid`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x20930`

## callees

- `0x207b0`
- `0x20a10`
- `0x20c50`
- `0x4f940`

## string_xrefs

- `0x20abd`: `LCID '{0}' for preferred language '{1}' is not installed. Defaulting to 1033`

## pseudocode

```c

```

## disassembly

```asm
0x20a10  newobj   instance void <>c__DisplayClass5_0::.ctor()
0x20a15  stloc.0
0x20a16  ldarg.0
0x20a17  ldstr    aPreferredlangu// "preferredLanguage"
0x20a1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x20a21  ldarg.1
0x20a22  ldstr    aOrganizationid_0// "organizationId"
0x20a27  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x20a2c  ldloc.0
0x20a2d  ldc.i4   0x409
0x20a32  stfld    int32 <>c__DisplayClass5_0::lcid
0x20a37  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> Microsoft.Crm.LanguageUtility::get_PreferredLanguageMapping()
0x20a3c  stloc.1
0x20a3d  ldloc.1
0x20a3e  ldarg.0
0x20a3f  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::ContainsKey(var<u1>)
0x20a44  brfalse.s loc_20A55
0x20a46  ldloc.0
0x20a47  ldloc.1
0x20a48  ldarg.0
0x20a49  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::get_Item(void)
0x20a4e  stfld    int32 <>c__DisplayClass5_0::lcid
0x20a53  br.s     loc_20A8F
0x20a55  ldnull
0x20a56  ldarg.1
0x20a57  ldc.i4.s 0xA
0x20a59  ldstr    a0_0// "{0}"
0x20a5e  ldc.i4.1
0x20a5f  newarr   [mscorlib]System.Object
0x20a64  dup
0x20a65  ldc.i4.0
0x20a66  ldstr    aUnexpectedPref// "Unexpected preferred language: "
0x20a6b  ldarg.0
0x20a6c  call     string [mscorlib]System.String::Concat(string, string)
0x20a71  stelem.ref
0x20a72  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20a77  ldarg.0
0x20a78  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(string)
0x20a7d  stloc.2
0x20a7e  ldloc.0
0x20a7f  ldloc.2
0x20a80  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x20a85  stfld    int32 <>c__DisplayClass5_0::lcid
0x20a8a  leave.s  loc_20A8F
0x20a8c  pop
0x20a8d  leave.s  loc_20A8F
0x20a8f  call     int32[] Microsoft.Crm.LanguageUtility::RetrieveInstalledLanguagePacks()
0x20a94  ldloc.0
0x20a95  ldftn    instance bool <>c__DisplayClass5_0::<PreferredLanguageToLcid>b__0(int32 value)
0x20a9b  newobj   instance void class [mscorlib]System.Func`2<int32, bool>::.ctor(object, native int)
0x20aa0  call     T0x2B00000B
0x20aa5  brtrue.s loc_20AF0
0x20aa7  ldnull
0x20aa8  ldarg.1
0x20aa9  ldc.i4.s 0xA
0x20aab  ldstr    a0_0// "{0}"
0x20ab0  ldc.i4.1
0x20ab1  newarr   [mscorlib]System.Object
0x20ab6  dup
0x20ab7  ldc.i4.0
0x20ab8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20abd  ldstr    aLcid0ForPrefer// "LCID '{0}' for preferred language '{1}'"...
0x20ac2  ldc.i4.2
0x20ac3  newarr   [mscorlib]System.Object
0x20ac8  dup
0x20ac9  ldc.i4.0
0x20aca  ldloc.0
0x20acb  ldfld    int32 <>c__DisplayClass5_0::lcid
0x20ad0  box      [mscorlib]System.Int32
0x20ad5  stelem.ref
0x20ad6  dup
0x20ad7  ldc.i4.1
0x20ad8  ldarg.0
0x20ad9  stelem.ref
0x20ada  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x20adf  stelem.ref
0x20ae0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20ae5  ldloc.0
0x20ae6  ldc.i4   0x409
0x20aeb  stfld    int32 <>c__DisplayClass5_0::lcid
0x20af0  ldloc.0
0x20af1  ldfld    int32 <>c__DisplayClass5_0::lcid
0x20af6  ret
```
