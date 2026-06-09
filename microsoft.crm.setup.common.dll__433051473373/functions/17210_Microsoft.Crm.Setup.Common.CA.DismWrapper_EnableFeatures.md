# Microsoft.Crm.Setup.Common.CA.DismWrapper::EnableFeatures

- ea: `0x17210`
- end: `0x172b4`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::EnableFeatures`
- size: `164`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x17210`
- `0x17580`
- `0x176c0`

## string_xrefs

- `0x1724a`: ` /featurename:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x17210  ldnull
0x17211  stloc.0
0x17212  ldnull
0x17213  stloc.1
0x17214  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x17219  stloc.2
0x1721a  ldloc.2
0x1721b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17220  ldstr    aOnlineEnglishE_0// "/online /english /enable-feature /nores"...
0x17225  ldc.i4.0
0x17226  newarr   [mscorlib]System.Object
0x1722b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x17230  pop
0x17231  ldarg.1
0x17232  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x17237  stloc.s  5
0x17239  br.s     loc_17260
0x1723b  ldloc.s  5
0x1723d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x17242  stloc.s  6
0x17244  ldloc.2
0x17245  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1724a  ldstr    aFeaturename0// " /featurename:{0}"
0x1724f  ldc.i4.1
0x17250  newarr   [mscorlib]System.Object
0x17255  dup
0x17256  ldc.i4.0
0x17257  ldloc.s  6
0x17259  stelem.ref
0x1725a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1725f  pop
0x17260  ldloc.s  5
0x17262  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17267  brtrue.s loc_1723B
0x17269  leave.s  loc_17277
0x1726b  ldloc.s  5
0x1726d  brfalse.s loc_17276
0x1726f  ldloc.s  5
0x17271  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17276  endfinally
0x17277  ldarg.0
0x17278  call     instance string Microsoft.Crm.Setup.Common.CA.DismWrapper::get_GetExePath()
0x1727d  ldarg.0
0x1727e  ldfld    string Microsoft.Crm.Setup.Common.CA.DismWrapper::_fileName
0x17283  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x17288  ldloc.2
0x17289  callvirt instance string [mscorlib]System.Object::ToString()
0x1728e  stloc.3
0x1728f  ldloc.3
0x17290  ldnull
0x17291  ldc.r8   5.0
0x1729a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x1729f  ldloca.s 0
0x172a1  ldloca.s 1
0x172a3  call     int32 [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Win32Utility::RunProcess(string, string, string[], valuetype [mscorlib]System.TimeSpan, string&, string&)
0x172a8  stloc.s  4
0x172aa  ldarg.0
0x172ab  ldloc.0
0x172ac  ldloc.s  4
0x172ae  call     instance valuetype Microsoft.Crm.Setup.Common.CA.DismCode Microsoft.Crm.Setup.Common.CA.DismWrapper::DismResults(string output, int32 exitCode)
0x172b3  ret
```
