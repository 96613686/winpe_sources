# GlobalLockSentry::InitTerm(bool)

- ea: `0x180030210`
- end: `0x180030282`
- name: `?InitTerm@GlobalLockSentry@@SAJ_N@Z`
- size: `114`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180030210`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030234`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180030224`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180030224`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030267`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180030267`

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
0x180030210  sub     rsp, 28h
0x180030214  test    cl, cl
0x180030216  jz      short loc_180030257
0x180030218  mov     edx, 64h ; 'd'; dwSpinCount
0x18003021d  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030224  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003022b  nop     dword ptr [rax+rax+00h]
0x180030230  test    eax, eax
0x180030232  jnz     short loc_18003024E
0x180030234  call    cs:__imp_GetLastError
0x18003023b  nop     dword ptr [rax+rax+00h]
0x180030240  test    eax, eax
0x180030242  jle     short loc_18003027C
0x180030244  movzx   eax, ax
0x180030247  or      eax, 80070000h
0x18003024c  jmp     short loc_18003027C
0x18003024e  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 1; bool GlobalLockSentry::isInitializedCriticalSection
0x180030255  jmp     short loc_18003027A
0x180030257  cmp     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x18003025e  jz      short loc_18003027A
0x180030260  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180030267  call    cs:__imp_DeleteCriticalSection
0x18003026e  nop     dword ptr [rax+rax+00h]
0x180030273  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x18003027a  xor     eax, eax
0x18003027c  add     rsp, 28h
0x180030280  retn
```
