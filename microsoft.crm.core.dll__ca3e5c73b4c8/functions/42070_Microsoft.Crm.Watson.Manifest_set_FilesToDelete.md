# Microsoft.Crm.Watson.Manifest::set_FilesToDelete

- ea: `0x42070`
- end: `0x42090`
- name: `Microsoft.Crm.Watson.Manifest::set_FilesToDelete`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x41490`

## callees

- `0x42070`

## string_xrefs

- `0x42078`: `FilesToDelete`
- `0x4207d`: `FilesToDelete - The paths of the files to delete cannot be null.`

## pseudocode

```c

```

## disassembly

```asm
0x42070  ldarg.0
0x42071  ldfld    string[] Microsoft.Crm.Watson.Manifest::filesToDelete
0x42076  brtrue.s loc_42088
0x42078  ldstr    aFilestodelete// "FilesToDelete"
0x4207d  ldstr    aFilestodeleteT// "FilesToDelete - The paths of the files "...
0x42082  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x42087  throw
0x42088  ldarg.0
0x42089  ldarg.1
0x4208a  stfld    string[] Microsoft.Crm.Watson.Manifest::filesToDelete
0x4208f  ret
```
