# Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::SetTimeout

- ea: `0x37d0`
- end: `0x38ad`
- name: `Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::SetTimeout`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3640`

## callees

- `0x37d0`

## string_xrefs

- `0x388f`: `Error during the access of the Registry. Cannot set {0} value. Exception = ({1})`

## pseudocode

```c

```

## disassembly

```asm
0x37d0  ldc.i4.1
0x37d1  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x37d6  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x37db  beq.s    loc_37DE
0x37dd  ret
0x37de  nop
0x37df  ldc.i4   0x80000002
0x37e4  ldc.i4   0x100
0x37e9  call     class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenBaseKey(valuetype [mscorlib]Microsoft.Win32.RegistryHive, valuetype [mscorlib]Microsoft.Win32.RegistryView)
0x37ee  stloc.0
0x37ef  ldloc.0
0x37f0  ldstr    aSoftwareMicros_0// "SOFTWARE\\Microsoft\\MSCRM"
0x37f5  ldc.i4.1
0x37f6  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x37fb  stloc.1
0x37fc  ldloc.1
0x37fd  ldarg.1
0x37fe  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x3803  stloc.2
0x3804  ldloc.2
0x3805  brfalse.s loc_3834
0x3807  ldloc.2
0x3808  unbox.any [mscorlib]System.Int32
0x380d  stloc.3
0x380e  ldloc.3
0x380f  ldarg.2
0x3810  bge.s    loc_3858
0x3812  ldloc.1
0x3813  ldarg.1
0x3814  ldarg.2
0x3815  box      [mscorlib]System.Int32
0x381a  ldc.i4.4
0x381b  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0x3820  ldarg.0
0x3821  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>> Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::oldValues
0x3826  ldarg.1
0x3827  ldloc.3
0x3828  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x382d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>>::Add(var<u1>, !!T0)
0x3832  br.s     loc_3858
0x3834  ldloc.1
0x3835  ldarg.1
0x3836  ldarg.2
0x3837  box      [mscorlib]System.Int32
0x383c  ldc.i4.4
0x383d  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::SetValue(string, object, valuetype [mscorlib]Microsoft.Win32.RegistryValueKind)
0x3842  ldarg.0
0x3843  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>> Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::oldValues
0x3848  ldarg.1
0x3849  ldloca.s 4
0x384b  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x3851  ldloc.s  4
0x3853  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>>::Add(var<u1>, !!T0)
0x3858  leave.s  loc_3864
0x385a  ldloc.1
0x385b  brfalse.s loc_3863
0x385d  ldloc.1
0x385e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3863  endfinally
0x3864  leave.s  loc_3870
0x3866  ldloc.0
0x3867  brfalse.s loc_386F
0x3869  ldloc.0
0x386a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x386f  endfinally
0x3870  leave.s  loc_38AC
0x3872  stloc.s  5
0x3874  ldloc.s  5
0x3876  isinst   [mscorlib]System.UnauthorizedAccessException
0x387b  brtrue.s loc_388F
0x387d  ldloc.s  5
0x387f  isinst   [mscorlib]System.Security.SecurityException
0x3884  brtrue.s loc_388F
0x3886  ldloc.s  5
0x3888  isinst   [mscorlib]System.IO.IOException
0x388d  brfalse.s loc_38AA
0x388f  ldstr    aErrorDuringThe// "Error during the access of the Registry"...
0x3894  ldc.i4.2
0x3895  newarr   [mscorlib]System.Object
0x389a  dup
0x389b  ldc.i4.0
0x389c  ldarg.1
0x389d  stelem.ref
0x389e  dup
0x389f  ldc.i4.1
0x38a0  ldloc.s  5
0x38a2  stelem.ref
0x38a3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x38a8  leave.s  loc_38AC
0x38aa  rethrow
0x38ac  ret
```
