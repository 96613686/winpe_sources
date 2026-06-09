# Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::ResetTimeout

- ea: `0x38b0`
- end: `0x3990`
- name: `Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::ResetTimeout`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39d0`

## callees

- `0x38b0`

## string_xrefs

- `0x3973`: `Error during the access of the Registry. Cannot reset {0} value. Exception = ({1})`

## pseudocode

```c

```

## disassembly

```asm
0x38b0  ldc.i4.1
0x38b1  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x38b6  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x38bb  beq.s    loc_38BE
0x38bd  ret
0x38be  ldarg.0
0x38bf  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>> Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::oldValues
0x38c4  ldarg.1
0x38c5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>>::ContainsKey(var<u1>)
0x38ca  brtrue.s loc_38CD
0x38cc  ret
0x38cd  nop
0x38ce  ldc.i4   0x80000002
0x38d3  ldc.i4   0x100
0x38d8  call     class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenBaseKey(valuetype [mscorlib]Microsoft.Win32.RegistryHive, valuetype [mscorlib]Microsoft.Win32.RegistryView)
0x38dd  stloc.0
0x38de  ldloc.0
0x38df  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\MSCRM"
0x38e4  ldc.i4.1
0x38e5  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x38ea  stloc.1
0x38eb  ldarg.0
0x38ec  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>> Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::oldValues
0x38f1  ldarg.1
0x38f2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>>::get_Item(void)
0x38f7  stloc.2
0x38f8  ldloca.s 2
0x38fa  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x38ff  brfalse.s loc_3924
0x3901  ldloc.1
0x3902  ldarg.1
0x3903  ldarg.0
0x3904  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>> Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::oldValues
0x3909  ldarg.1
0x390a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>>::get_Item(void)
0x390f  stloc.2
0x3910  ldloca.s 2
0x3912  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x3917  box      [mscorlib]System.Int32
0x391c  ldc.i4.4
0x391d  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0x3922  br.s     loc_392B
0x3924  ldloc.1
0x3925  ldarg.1
0x3926  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::DeleteValue(string)
0x392b  ldarg.0
0x392c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>> Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::oldValues
0x3931  ldarg.1
0x3932  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>>::Remove(var<u1>)
0x3937  pop
0x3938  leave.s  loc_3944
0x393a  ldloc.1
0x393b  brfalse.s loc_3943
0x393d  ldloc.1
0x393e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3943  endfinally
0x3944  leave.s  loc_3950
0x3946  ldloc.0
0x3947  brfalse.s loc_394F
0x3949  ldloc.0
0x394a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x394f  endfinally
0x3950  leave.s  loc_398F
0x3952  stloc.3
0x3953  ldloc.3
0x3954  isinst   [mscorlib]System.UnauthorizedAccessException
0x3959  brtrue.s loc_3973
0x395b  ldloc.3
0x395c  isinst   [mscorlib]System.ArgumentException
0x3961  brtrue.s loc_3973
0x3963  ldloc.3
0x3964  isinst   [mscorlib]System.Security.SecurityException
0x3969  brtrue.s loc_3973
0x396b  ldloc.3
0x396c  isinst   [mscorlib]System.IO.IOException
0x3971  brfalse.s loc_398D
0x3973  ldstr    aErrorDuringThe_0// "Error during the access of the Registry"...
0x3978  ldc.i4.2
0x3979  newarr   [mscorlib]System.Object
0x397e  dup
0x397f  ldc.i4.0
0x3980  ldarg.1
0x3981  stelem.ref
0x3982  dup
0x3983  ldc.i4.1
0x3984  ldloc.3
0x3985  stelem.ref
0x3986  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x398b  leave.s  loc_398F
0x398d  rethrow
0x398f  ret
```
