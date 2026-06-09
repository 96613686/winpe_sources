# wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)

- ea: `0x14000ddc4`
- end: `0x14000de17`
- name: `??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `83`
- prototype: `void **__fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000a7b0`

## callees

- `0x14000ddc4`
- `0x14000de20`
- `0x140019514`

## string_xrefs

- `0x14000ddfb`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void **__fastcall wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void **a1)
{
  int token_information; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(a1, 0);
  if ( token_information < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)token_information,
      1);
  return a1;
}

```

## disassembly

```asm
0x14000ddc4  mov     [rsp+arg_0], rcx
0x14000ddc9  push    rbx
0x14000ddca  sub     rsp, 30h
0x14000ddce  mov     rbx, rcx
0x14000ddd1  mov     [rsp+38h+var_18], 0
0x14000ddd9  mov     qword ptr [rcx], 0
0x14000dde0  mov     [rsp+38h+var_18], 1; int
0x14000dde8  xor     edx, edx
0x14000ddea  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x14000ddef  test    eax, eax
0x14000ddf1  jns     short loc_14000DE0D
0x14000ddf3  mov     rcx, [rsp+38h]; this
0x14000ddf8  mov     r9d, eax; char *
0x14000ddfb  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000de02  mov     edx, 1CBEh; void *
0x14000de07  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000de0d  mov     rax, rbx
0x14000de10  add     rsp, 30h
0x14000de14  pop     rbx
0x14000de15  retn
```
