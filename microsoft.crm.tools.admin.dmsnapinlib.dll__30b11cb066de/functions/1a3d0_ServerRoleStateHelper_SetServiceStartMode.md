# ServerRoleStateHelper::SetServiceStartMode

- ea: `0x1a3d0`
- end: `0x1a409`
- name: `ServerRoleStateHelper::SetServiceStartMode`
- size: `57`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1a080`
- `0x1a0b0`
- `0x1a0e0`
- `0x1a130`

## callees

- `0x1a3d0`

## string_xrefs

- `0x1a3e5`: `Cannot set the start mode of service ({0}) on the remote machine ({1}). Exception: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x1a3d0  ldarg.1
0x1a3d1  ldarg.0
0x1a3d2  ldarg.2
0x1a3d3  call     void [Microsoft.Crm.Setup.Shared.Interop]Microsoft.Crm.Setup.Common.Utility.ServiceUtility::SetServiceStartType(string, string, modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32)
0x1a3d8  leave.s  loc_1A405
0x1a3da  stloc.0
0x1a3db  ldloc.0
0x1a3dc  isinst   [System]System.ComponentModel.Win32Exception
0x1a3e1  brtrue.s loc_1A3E5
0x1a3e3  rethrow
0x1a3e5  ldstr    aCannotSetTheSt// "Cannot set the start mode of service ({"...
0x1a3ea  ldc.i4.3
0x1a3eb  newarr   [mscorlib]System.Object
0x1a3f0  dup
0x1a3f1  ldc.i4.0
0x1a3f2  ldarg.1
0x1a3f3  stelem.ref
0x1a3f4  dup
0x1a3f5  ldc.i4.1
0x1a3f6  ldarg.0
0x1a3f7  stelem.ref
0x1a3f8  dup
0x1a3f9  ldc.i4.2
0x1a3fa  ldloc.0
0x1a3fb  stelem.ref
0x1a3fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x1a401  ldc.i4.0
0x1a402  stloc.1
0x1a403  leave.s  loc_1A407
0x1a405  ldc.i4.1
0x1a406  ret
0x1a407  ldloc.1
0x1a408  ret
```
