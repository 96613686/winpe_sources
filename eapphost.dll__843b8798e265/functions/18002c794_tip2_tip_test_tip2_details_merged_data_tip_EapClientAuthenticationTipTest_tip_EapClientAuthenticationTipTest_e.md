# tip2::tip_test<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>>::ensure_data(void)

- ea: `0x18002c794`
- end: `0x18002c7ed`
- name: `?ensure_data@?$tip_test@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b310`
- `0x18002c3b4`

## callees

- `0x180009b10`
- `0x180023184`
- `0x1800237b4`
- `0x180023b80`
- `0x18002c794`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c7a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c7a8`

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
0x18002c794  push    rbx
0x18002c796  sub     rsp, 20h
0x18002c79a  cmp     qword ptr [rcx], 0
0x18002c79e  mov     rbx, rcx
0x18002c7a1  jnz     short loc_18002C7DD
0x18002c7a3  mov     ecx, 158h; cb
0x18002c7a8  call    cs:__imp_CoTaskMemAlloc
0x18002c7af  nop     dword ptr [rax+rax+00h]
0x18002c7b4  test    rax, rax
0x18002c7b7  jz      short loc_18002C7E7
0x18002c7b9  mov     rcx, rax
0x18002c7bc  call    ??0?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>(void)
0x18002c7c1  lea     rdx, [rsp+28h+arg_0]
0x18002c7c6  mov     [rsp+28h+arg_0], rax
0x18002c7cb  mov     rcx, rbx
0x18002c7ce  call    ??4?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::operator=(wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy> &&)
0x18002c7d3  lea     rcx, [rsp+28h+arg_0]
0x18002c7d8  call    ??1?$com_ptr_t@V?$merged_data@U_tip_EapClientAuthenticationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_EapClientAuthenticationTipTest,_tip_EapClientAuthenticationTipTest>,wil::err_returncode_policy>(void)
0x18002c7dd  mov     rax, rbx
0x18002c7e0  add     rsp, 20h
0x18002c7e4  pop     rbx
0x18002c7e5  retn
0x18002c7e7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
