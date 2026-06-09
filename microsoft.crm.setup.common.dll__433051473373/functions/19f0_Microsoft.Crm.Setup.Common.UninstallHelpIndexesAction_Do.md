# Microsoft.Crm.Setup.Common.UninstallHelpIndexesAction::Do

- ea: `0x19f0`
- end: `0x1a1e`
- name: `Microsoft.Crm.Setup.Common.UninstallHelpIndexesAction::Do`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x19f0`
- `0x1a20`

## string_xrefs

- `0x1a07`: `Setup failed to uninstall Microsoft CRM help indexes`

## pseudocode

```c

```

## disassembly

```asm
0x19f0  ldarg.0
0x19f1  ldarg.1
0x19f2  call     instance void Microsoft.Crm.Setup.Common.UninstallHelpIndexesAction::UninstallHelpIndexes(class [mscorlib]System.Collections.IDictionary parameters)
0x19f7  leave.s  loc_1A1D
0x19f9  stloc.0
0x19fa  ldc.i4   0x8000FFFF
0x19ff  ldloc.0
0x1a00  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x1a05  bne.un.s loc_1A19
0x1a07  ldstr    aSetupFailedToU// "Setup failed to uninstall Microsoft CRM"...
0x1a0c  ldc.i4.0
0x1a0d  newarr   [mscorlib]System.Object
0x1a12  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x1a17  br.s     loc_1A1B
0x1a19  rethrow
0x1a1b  leave.s  loc_1A1D
0x1a1d  ret
```
