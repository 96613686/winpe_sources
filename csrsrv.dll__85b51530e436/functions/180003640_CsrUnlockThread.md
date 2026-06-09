# CsrUnlockThread

- ea: `0x180003640`
- end: `0x180003664`
- name: `CsrUnlockThread`
- size: `36`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180003a20`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180003650`
- `ntdll!RtlLeaveCriticalSection` at `0x180003650`

## pseudocode

```c
__int64 __fastcall CsrUnlockThread(void *a1)
{
  CsrLockedDereferenceThread(a1);
  RtlLeaveCriticalSection(&CsrProcessStructureLock);
  return 0;
}

```

## disassembly

```asm
0x180003640  sub     rsp, 28h
0x180003644  call    CsrLockedDereferenceThread
0x180003649  lea     rcx, CsrProcessStructureLock; CriticalSection
0x180003650  call    cs:__imp_RtlLeaveCriticalSection
0x180003657  nop     dword ptr [rax+rax+00h]
0x18000365c  xor     eax, eax
0x18000365e  add     rsp, 28h
0x180003662  retn
```
