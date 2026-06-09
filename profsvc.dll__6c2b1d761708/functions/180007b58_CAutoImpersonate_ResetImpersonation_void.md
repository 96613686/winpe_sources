# CAutoImpersonate::ResetImpersonation(void)

- ea: `0x180007b58`
- end: `0x180007bba`
- name: `?ResetImpersonation@CAutoImpersonate@@QEAAXXZ`
- size: `98`
- prototype: `void __fastcall(CAutoImpersonate *__hidden this)`
- caller_count: `19`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005c80`
- `0x180006dbc`
- `0x180008fa0`
- `0x180010734`
- `0x180012508`
- `0x1800156ec`
- `0x180016150`
- `0x18001bdd8`
- `0x18001ce78`
- `0x180038118`
- `0x1800393f8`
- `0x18003a24c`
- `0x18003b26c`
- `0x180045160`
- `0x18004ff88`
- `0x180050f9c`
- `0x1800547b5`
- `0x180054bc3`
- `0x180054c41`

## callees

- `0x180007b58`
- `0x18002df48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007b6c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007b6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007b84`

## string_xrefs

- `0x180007ba7`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

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
0x180007b58  push    rbx
0x180007b5a  sub     rsp, 20h
0x180007b5e  cmp     byte ptr [rcx+8], 0
0x180007b62  mov     rbx, rcx
0x180007b65  jz      short loc_180007B9B
0x180007b67  mov     rdx, [rcx]; Token
0x180007b6a  xor     ecx, ecx; Thread
0x180007b6c  call    cs:__imp_SetThreadToken
0x180007b73  nop     dword ptr [rax+rax+00h]
0x180007b78  test    eax, eax
0x180007b7a  jz      short loc_180007BA2
0x180007b7c  mov     rcx, [rbx]; hObject
0x180007b7f  test    rcx, rcx
0x180007b82  jz      short loc_180007B90
0x180007b84  call    cs:__imp_CloseHandle
0x180007b8b  nop     dword ptr [rax+rax+00h]
0x180007b90  mov     qword ptr [rbx], 0
0x180007b97  mov     byte ptr [rbx+8], 0
0x180007b9b  add     rsp, 20h
0x180007b9f  pop     rbx
0x180007ba0  retn
0x180007ba2  mov     rcx, [rsp+28h]; this
0x180007ba7  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x180007bae  mov     edx, 4Fh ; 'O'; void *
0x180007bb3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007bb8  jmp     short loc_180007B7C
```
