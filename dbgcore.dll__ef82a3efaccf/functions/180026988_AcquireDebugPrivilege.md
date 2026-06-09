# AcquireDebugPrivilege

- ea: `0x180026988`
- end: `0x1800269b3`
- name: `AcquireDebugPrivilege`
- size: `43`
- prototype: `__int64 __fastcall(PVOID *ReturnedState)`
- caller_count: `2`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180013510`
- `0x1800269bc`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x1800269a3`
- `ntdll!RtlAcquirePrivilege` at `0x1800269a3`

## pseudocode

```c
bool __fastcall AcquireDebugPrivilege(PVOID *ReturnedState)
{
  ULONG Privilege; // [rsp+38h] [rbp+10h] BYREF

  Privilege = 20;
  return RtlAcquirePrivilege(&Privilege, 1u, 0, ReturnedState) >= 0;
}

```

## disassembly

```asm
0x180026988  sub     rsp, 28h
0x18002698c  xor     r8d, r8d; Flags
0x18002698f  mov     [rsp+28h+Privilege], 14h
0x180026997  mov     r9, rcx; ReturnedState
0x18002699a  lea     rcx, [rsp+28h+Privilege]; Privilege
0x18002699f  lea     edx, [r8+1]; NumPriv
0x1800269a3  call    cs:__imp_RtlAcquirePrivilege
0x1800269a9  shr     eax, 1Fh
0x1800269ac  xor     al, 1
0x1800269ae  add     rsp, 28h
0x1800269b2  retn
```
