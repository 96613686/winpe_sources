# GlobalLockSentry::InitTerm(bool)

- ea: `0x1800121f0`
- end: `0x18001224f`
- name: `?InitTerm@GlobalLockSentry@@SAJ_N@Z`
- size: `95`
- prototype: `__int64 __fastcall(bool)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800121f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001223b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001223b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180012204`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180012204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001220e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001220e`

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
0x1800121f0  sub     rsp, 28h
0x1800121f4  test    cl, cl
0x1800121f6  jz      short loc_18001222B
0x1800121f8  mov     edx, 64h ; 'd'; dwSpinCount
0x1800121fd  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012204  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18001220a  test    eax, eax
0x18001220c  jnz     short loc_180012222
0x18001220e  call    cs:__imp_GetLastError
0x180012214  test    eax, eax
0x180012216  jle     short loc_18001224A
0x180012218  movzx   eax, ax
0x18001221b  or      eax, 80070000h
0x180012220  jmp     short loc_18001224A
0x180012222  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 1; bool GlobalLockSentry::isInitializedCriticalSection
0x180012229  jmp     short loc_180012248
0x18001222b  cmp     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x180012232  jz      short loc_180012248
0x180012234  lea     rcx, ?lock@GlobalLockSentry@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001223b  call    cs:__imp_DeleteCriticalSection
0x180012241  mov     cs:?isInitializedCriticalSection@GlobalLockSentry@@0_NA, 0; bool GlobalLockSentry::isInitializedCriticalSection
0x180012248  xor     eax, eax
0x18001224a  add     rsp, 28h
0x18001224e  retn
```
