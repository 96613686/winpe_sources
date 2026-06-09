# CAutoLock<_CWriter>::~CAutoLock<_CWriter>(void)

- ea: `0x180002e50`
- end: `0x180002e64`
- name: `??1?$CAutoLock@U_CWriter@@@@QEAA@XZ`
- size: `20`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000af30`
- `0x18000b090`
- `0x18000b116`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180002e5d`

## pseudocode

```c
__int64 __fastcall CAutoLock<_CWriter>::~CAutoLock<_CWriter>(__int64 a1)
{
  return RtlReleaseSRWLockExclusive(*(_QWORD *)a1 + *(int *)(**(_QWORD **)a1 + 4LL));
}

```

## disassembly

```asm
0x180002e50  mov     rdx, [rcx]
0x180002e53  mov     rax, [rdx]
0x180002e56  movsxd  rcx, dword ptr [rax+4]
0x180002e5a  add     rcx, rdx
0x180002e5d  jmp     cs:__imp_RtlReleaseSRWLockExclusive
```
