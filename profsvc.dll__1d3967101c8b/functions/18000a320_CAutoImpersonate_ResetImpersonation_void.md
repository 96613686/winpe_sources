# CAutoImpersonate::ResetImpersonation(void)

- ea: `0x18000a320`
- end: `0x18000a375`
- name: `?ResetImpersonation@CAutoImpersonate@@QEAAXXZ`
- size: `85`
- prototype: `void __fastcall(CAutoImpersonate *__hidden this)`
- caller_count: `19`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004768`
- `0x18000659c`
- `0x1800080c8`
- `0x18000b540`
- `0x180011200`
- `0x1800123cc`
- `0x180013048`
- `0x180017364`
- `0x1800190f4`
- `0x18002cf64`
- `0x180036eec`
- `0x1800384b8`
- `0x180039d6c`
- `0x1800436b0`
- `0x18004cc94`
- `0x18004debc`
- `0x180051645`
- `0x1800519ac`
- `0x180051c16`

## callees

- `0x18000a320`
- `0x18002db38`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a334`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a334`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a346`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a346`

## string_xrefs

- `0x18000a362`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
void __fastcall CAutoImpersonate::ResetImpersonation(HANDLE *this)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)this + 8) )
  {
    if ( !SetThreadToken(0, *this) )
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0x4F,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
        v2);
    if ( *this )
      CloseHandle(*this);
    *this = 0;
    *((_BYTE *)this + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000a320  push    rbx
0x18000a322  sub     rsp, 20h
0x18000a326  cmp     byte ptr [rcx+8], 0
0x18000a32a  mov     rbx, rcx
0x18000a32d  jz      short loc_18000A357
0x18000a32f  mov     rdx, [rcx]; Token
0x18000a332  xor     ecx, ecx; Thread
0x18000a334  call    cs:__imp_SetThreadToken
0x18000a33a  test    eax, eax
0x18000a33c  jz      short loc_18000A35D
0x18000a33e  mov     rcx, [rbx]; hObject
0x18000a341  test    rcx, rcx
0x18000a344  jz      short loc_18000A34C
0x18000a346  call    cs:__imp_CloseHandle
0x18000a34c  mov     qword ptr [rbx], 0
0x18000a353  mov     byte ptr [rbx+8], 0
0x18000a357  add     rsp, 20h
0x18000a35b  pop     rbx
0x18000a35c  retn
0x18000a35d  mov     rcx, [rsp+28h]; this
0x18000a362  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000a369  mov     edx, 4Fh ; 'O'; void *
0x18000a36e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a373  jmp     short loc_18000A33E
```
