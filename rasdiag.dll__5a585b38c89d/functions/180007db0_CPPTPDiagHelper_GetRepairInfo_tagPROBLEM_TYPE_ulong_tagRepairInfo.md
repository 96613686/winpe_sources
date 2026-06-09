# CPPTPDiagHelper::GetRepairInfo(tagPROBLEM_TYPE,ulong *,tagRepairInfo * *)

- ea: `0x180007db0`
- end: `0x180007db6`
- name: `?GetRepairInfo@CPPTPDiagHelper@@UEAAJW4tagPROBLEM_TYPE@@PEAKPEAPEAUtagRepairInfo@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(CPPTPDiagHelper *__hidden this, enum tagPROBLEM_TYPE, unsigned int *, struct tagRepairInfo **)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall CPPTPDiagHelper::GetRepairInfo(
        CPPTPDiagHelper *this,
        enum tagPROBLEM_TYPE a2,
        unsigned int *a3,
        struct tagRepairInfo **a4)
{
  return 2147500033LL;
}

```

## disassembly

```asm
0x180007db0  mov     eax, 80004001h
0x180007db5  retn
```
