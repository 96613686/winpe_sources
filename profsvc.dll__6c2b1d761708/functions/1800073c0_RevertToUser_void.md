# RevertToUser(void * *)

- ea: `0x1800073c0`
- end: `0x180007450`
- name: `?RevertToUser@@YAJPEAPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006080`
- `0x18000721c`
- `0x1800156ec`

## callees

- `0x1800073c0`
- `0x18002df48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800073ce`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800073ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007425`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800073e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007425`

## string_xrefs

- `0x180007405`: `onecore\ds\security\gina\profile\proflib\sid.cpp`

## pseudocode

```c
__int64 __fastcall RevertToUser(void **a1)
{
  const char *v2; // r9
  unsigned int LastError; // edi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( SetThreadToken(0, *a1) )
  {
    if ( *a1 )
    {
      CloseHandle(*a1);
      *a1 = 0;
    }
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4F,
                  (unsigned int)"onecore\\ds\\security\\gina\\profile\\proflib\\sid.cpp",
                  v2);
    if ( *a1 )
    {
      CloseHandle(*a1);
      *a1 = 0;
    }
    return LastError;
  }
}

```

## disassembly

```asm
0x1800073c0  push    rbx
0x1800073c2  sub     rsp, 20h
0x1800073c6  mov     rdx, [rcx]; Token
0x1800073c9  mov     rbx, rcx
0x1800073cc  xor     ecx, ecx; Thread
0x1800073ce  call    cs:__imp_SetThreadToken
0x1800073d5  nop     dword ptr [rax+rax+00h]
0x1800073da  test    eax, eax
0x1800073dc  jz      short loc_180007400
0x1800073de  mov     rcx, [rbx]; hObject
0x1800073e1  test    rcx, rcx
0x1800073e4  jz      short loc_1800073F7
0x1800073e6  call    cs:__imp_CloseHandle
0x1800073ed  nop     dword ptr [rax+rax+00h]
0x1800073f2  xor     ecx, ecx
0x1800073f4  mov     [rbx], rcx
0x1800073f7  xor     eax, eax
0x1800073f9  add     rsp, 20h
0x1800073fd  pop     rbx
0x1800073fe  retn
0x180007400  mov     rcx, [rsp+28h]; this
0x180007405  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\gina\\profile\\p"...
0x18000740c  mov     edx, 4Fh ; 'O'; void *
0x180007411  mov     [rsp+28h+arg_0], rdi
0x180007416  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000741b  mov     rcx, [rbx]; hObject
0x18000741e  mov     edi, eax
0x180007420  test    rcx, rcx
0x180007423  jz      short loc_180007436
0x180007425  call    cs:__imp_CloseHandle
0x18000742c  nop     dword ptr [rax+rax+00h]
0x180007431  xor     ecx, ecx
0x180007433  mov     [rbx], rcx
0x180007436  mov     eax, edi
0x180007438  mov     rdi, [rsp+28h+arg_0]
0x18000743d  add     rsp, 20h
0x180007441  pop     rbx
0x180007442  retn
```
