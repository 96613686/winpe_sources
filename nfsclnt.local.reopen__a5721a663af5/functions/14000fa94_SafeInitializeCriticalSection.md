# SafeInitializeCriticalSection

- ea: `0x14000fa94`
- end: `0x14000fac5`
- name: `SafeInitializeCriticalSection`
- size: `49`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400030c0`
- `0x140003a48`
- `0x14000664c`
- `0x14000dcf0`
- `0x14000e9e4`

## callees

- `0x14000fa94`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x14000fa9d`
- `KERNEL32!InitializeCriticalSection` at `0x14000fa9d`
- `KERNEL32!EnterCriticalSection` at `0x14000faa6`
- `KERNEL32!EnterCriticalSection` at `0x14000faa6`
- `KERNEL32!LeaveCriticalSection` at `0x14000fab0`
- `KERNEL32!LeaveCriticalSection` at `0x14000fab0`

## pseudocode

```c
__int64 __fastcall SafeInitializeCriticalSection(LPCRITICAL_SECTION lpCriticalSection)
{
  InitializeCriticalSection(lpCriticalSection);
  EnterCriticalSection(lpCriticalSection);
  LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x14000fa94  push    rbx
0x14000fa96  sub     rsp, 20h
0x14000fa9a  mov     rbx, rcx
0x14000fa9d  call    cs:__imp_InitializeCriticalSection
0x14000faa3  mov     rcx, rbx; lpCriticalSection
0x14000faa6  call    cs:__imp_EnterCriticalSection
0x14000faac  nop
0x14000faad  mov     rcx, rbx; lpCriticalSection
0x14000fab0  call    cs:__imp_LeaveCriticalSection
0x14000fab6  xor     eax, eax
0x14000fab8  jmp     short loc_14000FABF
0x14000faba  mov     eax, 8007000Eh
0x14000fabf  add     rsp, 20h
0x14000fac3  pop     rbx
0x14000fac4  retn
```
