# GlobalLockSentry::InitTerm(bool)

- ea: `0x18000d980`
- end: `0x18000d9f2`
- name: `?InitTerm@GlobalLockSentry@@SAJ_N@Z`
- size: `114`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000607c`

## callees

- `0x18000d980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d9a4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d994`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18000d994`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d9d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d9d7`

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
0x18000d980  sub     rsp, 28h
0x18000d984  test    cl, cl
0x18000d986  jz      short loc_18000D9C7
0x18000d988  mov     edx, 64h ; 'd'; dwSpinCount
0x18000d98d  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d994  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18000d99b  nop     dword ptr [rax+rax+00h]
0x18000d9a0  test    eax, eax
0x18000d9a2  jnz     short loc_18000D9BE
0x18000d9a4  call    cs:__imp_GetLastError
0x18000d9ab  nop     dword ptr [rax+rax+00h]
0x18000d9b0  test    eax, eax
0x18000d9b2  jle     short loc_18000D9EC
0x18000d9b4  movzx   eax, ax
0x18000d9b7  or      eax, 80070000h
0x18000d9bc  jmp     short loc_18000D9EC
0x18000d9be  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 1; bool GlobalLockSentry::isInitializedCriticalSection
0x18000d9c5  jmp     short loc_18000D9EA
0x18000d9c7  cmp     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x18000d9ce  jz      short loc_18000D9EA
0x18000d9d0  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d9d7  call    cs:__imp_DeleteCriticalSection
0x18000d9de  nop     dword ptr [rax+rax+00h]
0x18000d9e3  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x18000d9ea  xor     eax, eax
0x18000d9ec  add     rsp, 28h
0x18000d9f0  retn
```
