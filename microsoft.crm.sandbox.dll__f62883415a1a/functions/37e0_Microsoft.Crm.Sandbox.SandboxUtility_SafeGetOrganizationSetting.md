# Microsoft.Crm.Sandbox.SandboxUtility::SafeGetOrganizationSetting

- ea: `0x37e0`
- end: `0x3858`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::SafeGetOrganizationSetting`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1420`
- `0x37e0`

## string_xrefs

- `0x37f3`: `D:\a\1\s\src\SandBox\Core\SandboxCommon\SandboxUtility.cs`

## pseudocode

```c

```

## disassembly

```asm
0x37e0  ldarg.2
0x37e1  stloc.0
0x37e2  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x37e7  ldarg.0
0x37e8  ldarg.1
0x37e9  ldc.i4   0x2BE
0x37ee  ldstr    aSafegetorganiz// "SafeGetOrganizationSetting"
0x37f3  ldstr    aDA1SSrcSandbox// "D:\\a\\1\\s\\src\\SandBox\\Core\\Sandbo"...
0x37f8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x37fd  stloc.1
0x37fe  ldloc.1
0x37ff  brfalse.s loc_3810
0x3801  ldloc.1
0x3802  isinst   mvar<u1>
0x3807  brfalse.s loc_3810
0x3809  ldloc.1
0x380a  unbox.any mvar<u1>
0x380f  stloc.0
0x3810  leave.s  loc_3856
0x3812  stloc.2
0x3813  ldarg.2
0x3814  stloc.0
0x3815  ldstr    aSandboxutility_8// "SandboxUtility.SafeGetOrganizationSetti"...
0x381a  ldc.i4.4
0x381b  newarr   [mscorlib]System.Object
0x3820  dup
0x3821  ldc.i4.0
0x3822  ldarg.1
0x3823  stelem.ref
0x3824  dup
0x3825  ldc.i4.1
0x3826  ldarg.2
0x3827  box      mvar<u1>
0x382c  stelem.ref
0x382d  dup
0x382e  ldc.i4.2
0x382f  ldarg.0
0x3830  box      [mscorlib]System.Guid
0x3835  stelem.ref
0x3836  dup
0x3837  ldc.i4.3
0x3838  ldloc.2
0x3839  stelem.ref
0x383a  call     string [mscorlib]System.String::Format(string, object[])
0x383f  stloc.3
0x3840  ldloc.2
0x3841  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3846  ldc.i4.s 0x21
0x3848  ldloc.3
0x3849  ldc.i4.0
0x384a  newarr   [mscorlib]System.Object
0x384f  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x3854  leave.s  loc_3856
0x3856  ldloc.0
0x3857  ret
```
