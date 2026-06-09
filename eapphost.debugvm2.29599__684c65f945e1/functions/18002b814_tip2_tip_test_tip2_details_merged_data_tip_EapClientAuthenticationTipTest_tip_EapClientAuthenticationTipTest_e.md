# tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::ensure_data(void)

- ea: `0x18002b814`
- end: `0x18002b866`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002a4fc`
- `0x18002b43c`

## callees

- `0x180009728`
- `0x180022514`
- `0x180022b84`
- `0x180022f18`
- `0x18002b814`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b828`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002b828`

## pseudocode

```c
_QWORD *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::ensure_data(
        _QWORD *a1)
{
  LPVOID v2; // rax
  wil::details::in1diag3 *v3; // rcx
  __int64 v5; // [rsp+30h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v2 = CoTaskMemAlloc(0x158u);
    if ( !v2 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
    v5 = tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(v2);
    wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(
      a1,
      &v5);
    wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(&v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18002b814  push    rbx
0x18002b816  sub     rsp, 20h
0x18002b81a  cmp     qword ptr [rcx], 0
0x18002b81e  mov     rbx, rcx
0x18002b821  jnz     short loc_18002B857
0x18002b823  mov     ecx, 158h; cb
0x18002b828  call    cs:__imp_CoTaskMemAlloc
0x18002b82e  test    rax, rax
0x18002b831  jz      short loc_18002B860
0x18002b833  mov     rcx, rax
0x18002b836  call    ??0?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(void)
0x18002b83b  lea     rdx, [rsp+28h+arg_0]
0x18002b840  mov     [rsp+28h+arg_0], rax
0x18002b845  mov     rcx, rbx
0x18002b848  call    ??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)
0x18002b84d  lea     rcx, [rsp+28h+arg_0]
0x18002b852  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x18002b857  mov     rax, rbx
0x18002b85a  add     rsp, 20h
0x18002b85e  pop     rbx
0x18002b85f  retn
0x18002b860  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
