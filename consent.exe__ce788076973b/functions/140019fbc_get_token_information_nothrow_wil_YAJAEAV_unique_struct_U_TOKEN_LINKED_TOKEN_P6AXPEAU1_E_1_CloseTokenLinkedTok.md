# ?get_token_information_nothrow@wil@@YAJAEAV?$unique_struct@U_TOKEN_LINKED_TOKEN@@P6AXPEAU1@@_E$1?CloseTokenLinkedToken@details@wil@@YAX0@Z$$T$0A@@1@PEAX@Z

- ea: `0x140019fbc`
- end: `0x14001a035`
- name: `?get_token_information_nothrow@wil@@YAJAEAV?$unique_struct@U_TOKEN_LINKED_TOKEN@@P6AXPEAU1@@_E$1?CloseTokenLinkedToken@details@wil@@YAX0@Z$$T$0A@@1@PEAX@Z`
- size: `121`
- prototype: `__int64 __fastcall(void **TokenInformation, struct _TOKEN_LINKED_TOKEN *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140019b34`

## callees

- `0x14000df54`
- `0x140019a8c`
- `0x140019fbc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001a006`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14001a006`

## string_xrefs

- `0x14001a015`: `onecore\internal\sdk\inc\wil\opensource\wil\token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow(void **TokenInformation, struct _TOKEN_LINKED_TOKEN *a2)
{
  __int64 v2; // rdi
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD ReturnLength; // [rsp+40h] [rbp+8h] BYREF

  v2 = (__int64)a2;
  ReturnLength = 0;
  wil::details::CloseTokenLinkedToken(TokenInformation, a2);
  *TokenInformation = 0;
  if ( !v2 )
    v2 = -6;
  if ( GetTokenInformation((HANDLE)v2, TokenLinkedToken, TokenInformation, 8u, &ReturnLength) )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x151,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\token_helpers.h",
             v4);
}

```

## disassembly

```asm
0x140019fbc  mov     [rsp+arg_8], rbx
0x140019fc1  push    rdi
0x140019fc2  sub     rsp, 30h
0x140019fc6  mov     rdi, rdx
0x140019fc9  mov     [rsp+38h+arg_0], 0
0x140019fd1  mov     rbx, rcx
0x140019fd4  call    ?CloseTokenLinkedToken@details@wil@@YAXPEAU_TOKEN_LINKED_TOKEN@@@Z; wil::details::CloseTokenLinkedToken(_TOKEN_LINKED_TOKEN *)
0x140019fd9  xor     eax, eax
0x140019fdb  mov     r9d, 8; TokenInformationLength
0x140019fe1  mov     [rbx], rax
0x140019fe4  test    rdi, rdi
0x140019fe7  mov     rax, 0FFFFFFFFFFFFFFFAh
0x140019fee  mov     r8, rbx; TokenInformation
0x140019ff1  cmovz   rdi, rax
0x140019ff5  lea     rax, [rsp+38h+arg_0]
0x140019ffa  mov     rcx, rdi; TokenHandle
0x140019ffd  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x14001a002  lea     edx, [r9+0Bh]; TokenInformationClass
0x14001a006  call    cs:__imp_GetTokenInformation
0x14001a00c  test    eax, eax
0x14001a00e  jnz     short loc_14001A028
0x14001a010  mov     rcx, [rsp+38h]; this
0x14001a015  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001a01c  mov     edx, 151h; void *
0x14001a021  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001a026  jmp     short loc_14001A02A
0x14001a028  xor     eax, eax
0x14001a02a  mov     rbx, [rsp+38h+arg_8]
0x14001a02f  add     rsp, 30h
0x14001a033  pop     rdi
0x14001a034  retn
```
