# GlobalLockSentry::InitTerm(bool)

- ea: `0x18002f0f0`
- end: `0x18002f14f`
- name: `?InitTerm@GlobalLockSentry@@SAJ_N@Z`
- size: `95`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18002f0f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f10e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f10e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002f104`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18002f104`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f13b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f13b`

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
0x18002f0f0  sub     rsp, 28h
0x18002f0f4  test    cl, cl
0x18002f0f6  jz      short loc_18002F12B
0x18002f0f8  mov     edx, 64h ; 'd'; dwSpinCount
0x18002f0fd  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f104  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18002f10a  test    eax, eax
0x18002f10c  jnz     short loc_18002F122
0x18002f10e  call    cs:__imp_GetLastError
0x18002f114  test    eax, eax
0x18002f116  jle     short loc_18002F14A
0x18002f118  movzx   eax, ax
0x18002f11b  or      eax, 80070000h
0x18002f120  jmp     short loc_18002F14A
0x18002f122  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 1; bool GlobalLockSentry::isInitializedCriticalSection
0x18002f129  jmp     short loc_18002F148
0x18002f12b  cmp     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x18002f132  jz      short loc_18002F148
0x18002f134  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002f13b  call    cs:__imp_DeleteCriticalSection
0x18002f141  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x18002f148  xor     eax, eax
0x18002f14a  add     rsp, 28h
0x18002f14e  retn
```
