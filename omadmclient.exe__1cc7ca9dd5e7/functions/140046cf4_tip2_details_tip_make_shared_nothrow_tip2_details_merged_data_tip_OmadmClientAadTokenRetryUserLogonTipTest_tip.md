# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_OmadmClientAadTokenRetryUserLogonTipTest,_tip_OmadmClientAadTokenRetryUserLogonTipTest>,>(void)

- ea: `0x140046cf4`
- end: `0x140046dc0`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_OmadmClientAadTokenRetryUserLogonTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_OmadmClientAadTokenRetryUserLogonTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140047060`
- `0x140048db0`

## callees

- `0x14000ce6c`
- `0x14001f224`
- `0x140046cf4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140046d06`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140046d06`

## string_xrefs

- `0x140046d3b`: `OmadmClientAadTokenRetryUserLogonTipTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_OmadmClientAadTokenRetryUserLogonTipTest,_tip_OmadmClientAadTokenRetryUserLogonTipTest>,>(
        _QWORD *a1)
{
  _QWORD *v2; // rax
  wil::details::in1diag3 *v3; // rcx
  _QWORD *v4; // rbx
  _QWORD *result; // rax
  _DWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v7; // [rsp+28h] [rbp-30h]
  __int16 v8; // [rsp+30h] [rbp-28h]
  int v9; // [rsp+32h] [rbp-26h]
  __int16 v10; // [rsp+36h] [rbp-22h]
  __int128 v11; // [rsp+38h] [rbp-20h]
  __int64 v12; // [rsp+48h] [rbp-10h]

  v2 = CoTaskMemAlloc(0x128u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 54315128;
  v9 = 0;
  *v2 = &tip2::details::test_data_interface::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "OmadmClientAadTokenRetryUserLogonTipTest";
  v6[1] = 49664;
  v8 = 513;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  v4[34] = 0;
  *v4 = &tip2::details::merged_data<_tip_OmadmClientAadTokenRetryUserLogonTipTest,_tip_OmadmClientAadTokenRetryUserLogonTipTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_WORD *)v4 + 140) = 0;
  *((_DWORD *)v4 + 72) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x140046cf4  mov     [rsp+arg_0], rbx
0x140046cf9  push    rdi
0x140046cfa  sub     rsp, 50h
0x140046cfe  mov     rdi, rcx
0x140046d01  mov     ecx, 128h; cb
0x140046d06  call    cs:__imp_CoTaskMemAlloc
0x140046d0d  nop     dword ptr [rax+rax+00h]
0x140046d12  mov     rbx, rax
0x140046d15  test    rax, rax
0x140046d18  jz      loc_140046DBA
0x140046d1e  xor     ecx, ecx
0x140046d20  mov     [rsp+58h+var_38], 33CC878h
0x140046d28  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x140046d2f  mov     [rsp+58h+var_26], ecx
0x140046d33  mov     [rbx], rax
0x140046d36  lea     r8, [rsp+58h+var_38]
0x140046d3b  lea     rax, aOmadmclientaad; "OmadmClientAadTokenRetryUserLogonTipTes"...
0x140046d42  mov     [rsp+58h+var_22], cx
0x140046d47  xorps   xmm0, xmm0
0x140046d4a  mov     [rsp+58h+var_10], rcx
0x140046d4f  lea     rcx, [rbx+8]
0x140046d53  mov     [rsp+58h+var_30], rax
0x140046d58  mov     rdx, rbx
0x140046d5b  mov     [rsp+58h+var_34], 0C200h
0x140046d63  mov     [rsp+58h+var_28], 201h
0x140046d6a  movdqu  [rsp+58h+var_20], xmm0
0x140046d70  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x140046d75  lea     rax, ??_7?$merged_data@U_tip_OmadmClientAadTokenRetryUserLogonTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_OmadmClientAadTokenRetryUserLogonTipTest,_tip_OmadmClientAadTokenRetryUserLogonTipTest>::`vftable'
0x140046d7c  mov     qword ptr [rbx+110h], 0
0x140046d87  mov     [rbx], rax
0x140046d8a  lea     rax, [rbx+10h]
0x140046d8e  mov     [rbx+108h], rax
0x140046d95  mov     rax, rdi
0x140046d98  mov     word ptr [rbx+118h], 0
0x140046da1  mov     dword ptr [rbx+120h], 1
0x140046dab  mov     [rdi], rbx
0x140046dae  mov     rbx, [rsp+58h+arg_0]
0x140046db3  add     rsp, 50h
0x140046db7  pop     rdi
0x140046db8  retn
0x140046dba  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
