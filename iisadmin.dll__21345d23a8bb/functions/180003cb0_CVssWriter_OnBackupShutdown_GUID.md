# CVssWriter::OnBackupShutdown(_GUID)

- ea: `0x180003cb0`
- end: `0x180003cb3`
- name: `?OnBackupShutdown@CVssWriter@@UEAA_NU_GUID@@@Z`
- size: `3`
- prototype: `bool __fastcall(CVssWriter *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall CVssWriter::OnBackupShutdown(CVssWriter *this, struct _GUID *a2)
{
  return 1;
}

```

## disassembly

```asm
0x180003cb0  mov     al, 1
0x180003cb2  retn
```
