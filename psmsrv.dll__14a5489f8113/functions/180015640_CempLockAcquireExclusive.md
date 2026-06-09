# CempLockAcquireExclusive

- ea: `0x180015640`
- end: `0x180015662`
- name: `CempLockAcquireExclusive`
- size: `34`
- prototype: `DWORD()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000e0f4`
- `0x180015050`
- `0x18002039c`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001564b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001564b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015651`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015651`

## pseudocode

```c
DWORD CempLockAcquireExclusive()
{
  DWORD result; // eax

  RtlAcquireSRWLockExclusive(PsmpBackgroundApplicationListLock);
  result = GetCurrentThreadId();
  dword_18003FE98 = result;
  return result;
}

```

## disassembly

```asm
0x180015640  sub     rsp, 28h
0x180015644  lea     rcx, PsmpBackgroundApplicationListLock
0x18001564b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180015651  call    cs:__imp_GetCurrentThreadId
0x180015657  mov     cs:dword_18003FE98, eax
0x18001565d  add     rsp, 28h
0x180015661  retn
```
