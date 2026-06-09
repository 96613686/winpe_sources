# CAutoImpersonate::ResetImpersonation(void)

- ea: `0x18000927c`
- end: `0x1800092cd`
- name: `?ResetImpersonation@CAutoImpersonate@@QEAAXXZ`
- size: `81`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180007468`
- `0x180008258`
- `0x180009c68`
- `0x1800115b8`
- `0x180011880`
- `0x180012314`
- `0x180013aac`
- `0x180016158`

## callees

- `0x18000547c`
- `0x18000927c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009290`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009290`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800092b6`

## string_xrefs

- `0x18000929f`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

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
0x18000927c  push    rbx
0x18000927e  sub     rsp, 20h
0x180009282  cmp     byte ptr [rcx+8], 0
0x180009286  mov     rbx, rcx
0x180009289  jz      short loc_1800092C7
0x18000928b  mov     rdx, [rcx]; Token
0x18000928e  xor     ecx, ecx; Thread
0x180009290  call    cs:__imp_SetThreadToken
0x180009296  test    eax, eax
0x180009298  jnz     short loc_1800092AE
0x18000929a  mov     rcx, [rsp+28h]; this
0x18000929f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800092a6  lea     edx, [rax+4Fh]; void *
0x1800092a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800092ae  mov     rcx, [rbx]; hObject
0x1800092b1  test    rcx, rcx
0x1800092b4  jz      short loc_1800092BC
0x1800092b6  call    cs:__imp_CloseHandle
0x1800092bc  mov     qword ptr [rbx], 0
0x1800092c3  mov     byte ptr [rbx+8], 0
0x1800092c7  add     rsp, 20h
0x1800092cb  pop     rbx
0x1800092cc  retn
```
