# Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::Do

- ea: `0x17c0`
- end: `0x17f0`
- name: `Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::Do`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0xff0`
- `0x17c0`
- `0x17f0`

## string_xrefs

- `0x17d7`: `InstallHelpIndexesAction.CatastrophicFailure`

## pseudocode

```c

```

## disassembly

```asm
0x17c0  ldarg.0
0x17c1  ldarg.1
0x17c2  call     instance void Microsoft.Crm.Setup.Common.InstallHelpIndexesAction::InstallHelpIndexes(class [mscorlib]System.Collections.IDictionary parameters)
0x17c7  leave.s  loc_17EF
0x17c9  stloc.0
0x17ca  ldc.i4   0x8000FFFF
0x17cf  ldloc.0
0x17d0  callvirt instance int32 [mscorlib]System.Runtime.InteropServices.ExternalException::get_ErrorCode()
0x17d5  bne.un.s loc_17ED
0x17d7  ldstr    aInstallhelpind// "InstallHelpIndexesAction.CatastrophicFa"...
0x17dc  ldc.i4.0
0x17dd  newarr   [mscorlib]System.Object
0x17e2  call     string Microsoft.Crm.Setup.Common.CommonResource::GetString(string name, object[] args)
0x17e7  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x17ec  throw
0x17ed  rethrow
0x17ef  ret
```
