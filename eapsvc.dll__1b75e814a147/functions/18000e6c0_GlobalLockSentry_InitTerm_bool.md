# GlobalLockSentry::InitTerm(bool)

- ea: `0x18000e6c0`
- end: `0x18000e71f`
- name: `?InitTerm@GlobalLockSentry@@SAJ_N@Z`
- size: `95`
- prototype: `signed int __fastcall(char)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bf5c`

## callees

- `0x18000e6c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e70b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e70b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000e6d4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000e6d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6de`

## pseudocode

```c
signed int __fastcall GlobalLockSentry::InitTerm(char a1)
{
  signed int result; // eax

  if ( !a1 )
  {
    if ( GlobalLockSentry::isInitializedCriticalSection )
    {
      DeleteCriticalSection(&GlobalLockSentry::lock);
      GlobalLockSentry::isInitializedCriticalSection = 0;
    }
    return 0;
  }
  if ( InitializeCriticalSectionAndSpinCount(&GlobalLockSentry::lock, 0x64u) )
  {
    GlobalLockSentry::isInitializedCriticalSection = 1;
    return 0;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18000e6c0  sub     rsp, 28h
0x18000e6c4  test    cl, cl
0x18000e6c6  jz      short loc_18000E6FB
0x18000e6c8  mov     edx, 64h ; 'd'; dwSpinCount
0x18000e6cd  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e6d4  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000e6da  test    eax, eax
0x18000e6dc  jnz     short loc_18000E6F2
0x18000e6de  call    cs:__imp_GetLastError
0x18000e6e4  test    eax, eax
0x18000e6e6  jle     short loc_18000E71A
0x18000e6e8  movzx   eax, ax
0x18000e6eb  or      eax, 80070000h
0x18000e6f0  jmp     short loc_18000E71A
0x18000e6f2  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 1; bool GlobalLockSentry::isInitializedCriticalSection
0x18000e6f9  jmp     short loc_18000E718
0x18000e6fb  cmp     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x18000e702  jz      short loc_18000E718
0x18000e704  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000e70b  call    cs:__imp_DeleteCriticalSection
0x18000e711  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x18000e718  xor     eax, eax
0x18000e71a  add     rsp, 28h
0x18000e71e  retn
```
