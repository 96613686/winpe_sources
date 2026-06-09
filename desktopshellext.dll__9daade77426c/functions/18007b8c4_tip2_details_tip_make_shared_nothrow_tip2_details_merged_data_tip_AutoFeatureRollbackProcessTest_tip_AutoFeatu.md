# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AutoFeatureRollbackProcessTest,_tip_AutoFeatureRollbackProcessTest>,>(void)

- ea: `0x18007b8c4`
- end: `0x18007b971`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AutoFeatureRollbackProcessTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AutoFeatureRollbackProcessTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18007ca54`

## callees

- `0x18002008c`
- `0x18002ed14`
- `0x18007b8c4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b8d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007b8d6`

## string_xrefs

- `0x18007b8f4`: `AutoFeatureRollbackProcessTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AutoFeatureRollbackProcessTest,_tip_AutoFeatureRollbackProcessTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  _DWORD *v3; // rbx
  _QWORD *result; // rax
  _DWORD v5[2]; // [rsp+20h] [rbp-38h] BYREF
  const char *v6; // [rsp+28h] [rbp-30h]
  __int16 v7; // [rsp+30h] [rbp-28h]
  int v8; // [rsp+32h] [rbp-26h]
  __int16 v9; // [rsp+36h] [rbp-22h]
  __int128 v10; // [rsp+38h] [rbp-20h]
  __int64 v11; // [rsp+48h] [rbp-10h]

  v3 = CoTaskMemAlloc(0x118u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  v5[0] = 56003848;
  v8 = 0;
  v6 = "AutoFeatureRollbackProcessTest";
  v9 = 0;
  v11 = 0;
  *(_QWORD *)v3 = &winrt::impl::producer_convert<PackageManagerBroker,IPackageManagerBroker,void>::`vftable';
  v5[1] = 49408;
  v7 = 1;
  v10 = 0;
  tip2::details::shared_data<1,0,1>::shared_data<1,0,1>(v3 + 2, v3, v5);
  v3[68] = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_AutoFeatureRollbackRetrievePolicyTest,_tip_AutoFeatureRollbackRetrievePolicyTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 4;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x18007b8c4  mov     [rsp+arg_0], rbx
0x18007b8c9  push    rdi
0x18007b8ca  sub     rsp, 50h
0x18007b8ce  mov     rdi, rcx
0x18007b8d1  mov     ecx, 118h; cb
0x18007b8d6  call    cs:__imp_CoTaskMemAlloc
0x18007b8dc  mov     rbx, rax
0x18007b8df  test    rax, rax
0x18007b8e2  jnz     short loc_18007B8EA
0x18007b8e4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18007b8ea  xor     edx, edx
0x18007b8ec  mov     [rsp+58h+var_38], 3568D08h
0x18007b8f4  lea     rcx, aAutofeaturerol_0; "AutoFeatureRollbackProcessTest"
0x18007b8fb  mov     [rsp+58h+var_26], edx
0x18007b8ff  mov     [rsp+58h+var_30], rcx
0x18007b904  lea     rax, ??_7?$producer_convert@UPackageManagerBroker@@UIPackageManagerBroker@@X@impl@winrt@@6B@; const winrt::impl::producer_convert<PackageManagerBroker,IPackageManagerBroker,void>::`vftable'
0x18007b90b  mov     [rsp+58h+var_22], dx
0x18007b910  lea     rcx, [rbx+8]
0x18007b914  mov     [rsp+58h+var_10], rdx
0x18007b919  lea     r8, [rsp+58h+var_38]
0x18007b91e  xorps   xmm0, xmm0
0x18007b921  mov     [rbx], rax
0x18007b924  mov     rdx, rbx
0x18007b927  mov     [rsp+58h+var_34], 0C100h
0x18007b92f  mov     [rsp+58h+var_28], 1
0x18007b936  movdqu  [rsp+58h+var_20], xmm0
0x18007b93c  call    ??0?$shared_data@$00$0A@$00@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,1>::shared_data<1,0,1>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18007b941  lea     rax, ??_7?$merged_data@U_tip_AutoFeatureRollbackRetrievePolicyTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AutoFeatureRollbackRetrievePolicyTest,_tip_AutoFeatureRollbackRetrievePolicyTest>::`vftable'
0x18007b948  mov     dword ptr [rbx+110h], 1
0x18007b952  mov     [rbx], rax
0x18007b955  lea     rax, [rbx+10h]
0x18007b959  mov     [rbx+108h], rax
0x18007b960  mov     rax, rdi
0x18007b963  mov     [rdi], rbx
0x18007b966  mov     rbx, [rsp+58h+arg_0]
0x18007b96b  add     rsp, 50h
0x18007b96f  pop     rdi
0x18007b970  retn
```
