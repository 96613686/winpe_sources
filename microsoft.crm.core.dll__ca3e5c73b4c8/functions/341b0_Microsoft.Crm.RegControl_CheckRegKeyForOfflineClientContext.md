# Microsoft.Crm.RegControl::CheckRegKeyForOfflineClientContext

- ea: `0x341b0`
- end: `0x34241`
- name: `Microsoft.Crm.RegControl::CheckRegKeyForOfflineClientContext`
- size: `145`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x34190`
- `0x341a0`

## callees

- `0x33770`
- `0x33800`
- `0x33930`
- `0x341b0`

## string_xrefs

- `0x341d1`: `Error while trying to open the client registry key. Value for RegControl.CrmClientKeyPath: {0}`
- `0x34201`: `Error while getting the value '{0}' from registry key '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x341b0  call     bool Microsoft.Crm.RegControl::IsInClientContext()
0x341b5  brtrue.s loc_341B9
0x341b7  ldc.i4.0
0x341b8  ret
0x341b9  call     class [mscorlib]Microsoft.Win32.RegistryKey Microsoft.Crm.RegControl::get_CrmClientKeyHive()
0x341be  call     string Microsoft.Crm.RegControl::get_CrmClientKeyPath()
0x341c3  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x341c8  stloc.0
0x341c9  ldloc.0
0x341ca  brtrue.s loc_341EF
0x341cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x341d1  ldstr    aErrorWhileTryi// "Error while trying to open the client r"...
0x341d6  ldc.i4.1
0x341d7  newarr   [mscorlib]System.Object
0x341dc  dup
0x341dd  ldc.i4.0
0x341de  call     string Microsoft.Crm.RegControl::get_CrmClientKeyPath()
0x341e3  stelem.ref
0x341e4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x341e9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x341ee  throw
0x341ef  ldloc.0
0x341f0  stloc.2
0x341f1  ldloc.0
0x341f2  ldarg.0
0x341f3  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x341f8  stloc.3
0x341f9  ldloc.3
0x341fa  brtrue.s loc_34224
0x341fc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34201  ldstr    aErrorWhileGett// "Error while getting the value '{0}' fro"...
0x34206  ldc.i4.2
0x34207  newarr   [mscorlib]System.Object
0x3420c  dup
0x3420d  ldc.i4.0
0x3420e  ldarg.0
0x3420f  stelem.ref
0x34210  dup
0x34211  ldc.i4.1
0x34212  ldloc.0
0x34213  callvirt instance string [mscorlib]Microsoft.Win32.RegistryKey::get_Name()
0x34218  stelem.ref
0x34219  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3421e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x34223  throw
0x34224  ldloc.3
0x34225  callvirt instance string [mscorlib]System.Object::ToString()
0x3422a  call     int32 [mscorlib]System.Int32::Parse(string)
0x3422f  stloc.1
0x34230  leave.s  loc_3423C
0x34232  ldloc.2
0x34233  brfalse.s loc_3423B
0x34235  ldloc.2
0x34236  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3423b  endfinally
0x3423c  ldloc.1
0x3423d  ldc.i4.0
0x3423e  cgt.un
0x34240  ret
```
