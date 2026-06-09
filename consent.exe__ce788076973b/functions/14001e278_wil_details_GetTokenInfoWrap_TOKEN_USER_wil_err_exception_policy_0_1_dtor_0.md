# _wil::details::GetTokenInfoWrap__TOKEN_USER_wil::err_exception_policy_0__::_1_::dtor$0

- ea: `0x14001e278`
- end: `0x14001e29e`
- name: `_wil::details::GetTokenInfoWrap__TOKEN_USER_wil::err_exception_policy_0__::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x14000fb20`
- `0x14001e278`

## pseudocode

```c
void __fastcall wil::details::GetTokenInfoWrap__TOKEN_USER_wil::err_exception_policy_0__::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 32) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(*(void ***)(a2 + 64));
  }
}

```

## disassembly

```asm
0x14001e278  push    rbp
0x14001e27a  sub     rsp, 20h
0x14001e27e  mov     rbp, rdx
0x14001e281  mov     eax, [rbp+20h]
0x14001e284  and     eax, 1
0x14001e287  test    eax, eax
0x14001e289  jz      short loc_14001E298
0x14001e28b  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14001e28f  mov     rcx, [rbp+40h]
0x14001e293  call    ??1?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@QEAA@XZ; wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>::~unique_ptr<_TOKEN_USER,wil::details::token_info_deleter>(void)
0x14001e298  add     rsp, 20h
0x14001e29c  pop     rbp
0x14001e29d  retn
```
