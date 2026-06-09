# wil::details::ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8___::operator()

- ea: `0x1800285b8`
- end: `0x180028608`
- name: `wil::details::ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8___::operator()`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180028450`
- `0x18002a7cc`

## callees

- `0x18002220c`
- `0x1800285b8`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x1800285e2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x1800285e2`

## string_xrefs

- `0x1800285f1`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFnGuard__lambda_c2af53d0ad810067f2b6d1052d429af8___::operator()(__int64 a1)
{
  void *v1; // rdx
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)(a1 + 17) )
  {
    *(_BYTE *)(a1 + 17) = 0;
    v1 = **(void ***)a1;
    if ( v1 )
    {
      if ( !WTSFreeMemoryExW(WTSTypeSessionInfoLevel1, v1, **(_DWORD **)(a1 + 8)) )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x268,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
          v2);
    }
  }
}

```

## disassembly

```asm
0x1800285b8  mov     [rsp+arg_0], rcx
0x1800285bd  sub     rsp, 28h
0x1800285c1  cmp     byte ptr [rcx+11h], 0
0x1800285c5  jz      short loc_180028603
0x1800285c7  mov     byte ptr [rcx+11h], 0
0x1800285cb  mov     rax, [rcx]
0x1800285ce  mov     rdx, [rax]; pMemory
0x1800285d1  test    rdx, rdx
0x1800285d4  jz      short loc_180028603
0x1800285d6  mov     r8, [rcx+8]
0x1800285da  mov     r8d, [r8]; NumberOfEntries
0x1800285dd  mov     ecx, 2; WTSTypeClass
0x1800285e2  call    cs:__imp_WTSFreeMemoryExW
0x1800285e8  mov     rcx, [rsp+28h]; this
0x1800285ed  test    eax, eax
0x1800285ef  jnz     short loc_180028603
0x1800285f1  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800285f8  mov     edx, 268h; void *
0x1800285fd  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180028602  nop
0x180028603  add     rsp, 28h
0x180028607  retn
```
