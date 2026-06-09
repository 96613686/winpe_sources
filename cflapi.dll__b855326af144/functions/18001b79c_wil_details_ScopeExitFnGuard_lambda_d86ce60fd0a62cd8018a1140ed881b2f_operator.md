# wil::details::ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f___::operator()

- ea: `0x18001b79c`
- end: `0x18001b7ec`
- name: `wil::details::ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f___::operator()`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001a948`
- `0x18001e970`

## callees

- `0x18001b79c`
- `0x18002220c`

## import_xrefs

- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x18001b7c6`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemoryExW` at `0x18001b7c6`

## string_xrefs

- `0x18001b7d5`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFnGuard__lambda_d86ce60fd0a62cd8018a1140ed881b2f___::operator()(__int64 a1)
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
          (void *)0x4E4,
          (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
          v2);
    }
  }
}

```

## disassembly

```asm
0x18001b79c  mov     [rsp+arg_0], rcx
0x18001b7a1  sub     rsp, 28h
0x18001b7a5  cmp     byte ptr [rcx+11h], 0
0x18001b7a9  jz      short loc_18001B7E7
0x18001b7ab  mov     byte ptr [rcx+11h], 0
0x18001b7af  mov     rax, [rcx]
0x18001b7b2  mov     rdx, [rax]; pMemory
0x18001b7b5  test    rdx, rdx
0x18001b7b8  jz      short loc_18001B7E7
0x18001b7ba  mov     r8, [rcx+8]
0x18001b7be  mov     r8d, [r8]; NumberOfEntries
0x18001b7c1  mov     ecx, 2; WTSTypeClass
0x18001b7c6  call    cs:__imp_WTSFreeMemoryExW
0x18001b7cc  mov     rcx, [rsp+28h]; this
0x18001b7d1  test    eax, eax
0x18001b7d3  jnz     short loc_18001B7E7
0x18001b7d5  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001b7dc  mov     edx, 4E4h; void *
0x18001b7e1  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18001b7e6  nop
0x18001b7e7  add     rsp, 28h
0x18001b7eb  retn
```
