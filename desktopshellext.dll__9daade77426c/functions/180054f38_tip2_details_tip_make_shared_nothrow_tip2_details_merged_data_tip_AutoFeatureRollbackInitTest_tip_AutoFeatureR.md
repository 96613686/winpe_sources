# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AutoFeatureRollbackInitTest,_tip_AutoFeatureRollbackInitTest>,>(void)

- ea: `0x180054f38`
- end: `0x180054fe5`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AutoFeatureRollbackInitTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AutoFeatureRollbackInitTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180059194`

## callees

- `0x18002008c`
- `0x18002ed14`
- `0x180054f38`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054f4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054f4a`

## string_xrefs

- `0x180054f68`: `AutoFeatureRollbackInitTest`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AutoFeatureRollbackInitTest,_tip_AutoFeatureRollbackInitTest>,>(
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
  v5[0] = 56221996;
  v8 = 0;
  v6 = "AutoFeatureRollbackInitTest";
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
0x180054f38  mov     [rsp+arg_0], rbx
0x180054f3d  push    rdi
0x180054f3e  sub     rsp, 50h
0x180054f42  mov     rdi, rcx
0x180054f45  mov     ecx, 118h; cb
0x180054f4a  call    cs:__imp_CoTaskMemAlloc
0x180054f50  mov     rbx, rax
0x180054f53  test    rax, rax
0x180054f56  jnz     short loc_180054F5E
0x180054f58  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180054f5e  xor     edx, edx
0x180054f60  mov     [rsp+58h+var_38], 359E12Ch
0x180054f68  lea     rcx, aAutofeaturerol_1; "AutoFeatureRollbackInitTest"
0x180054f6f  mov     [rsp+58h+var_26], edx
0x180054f73  mov     [rsp+58h+var_30], rcx
0x180054f78  lea     rax, ??_7?$producer_convert@UPackageManagerBroker@@UIPackageManagerBroker@@X@impl@winrt@@6B@; const winrt::impl::producer_convert<PackageManagerBroker,IPackageManagerBroker,void>::`vftable'
0x180054f7f  mov     [rsp+58h+var_22], dx
0x180054f84  lea     rcx, [rbx+8]
0x180054f88  mov     [rsp+58h+var_10], rdx
0x180054f8d  lea     r8, [rsp+58h+var_38]
0x180054f92  xorps   xmm0, xmm0
0x180054f95  mov     [rbx], rax
0x180054f98  mov     rdx, rbx
0x180054f9b  mov     [rsp+58h+var_34], 0C100h
0x180054fa3  mov     [rsp+58h+var_28], 1
0x180054faa  movdqu  [rsp+58h+var_20], xmm0
0x180054fb0  call    ??0?$shared_data@$00$0A@$00@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<1,0,1>::shared_data<1,0,1>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180054fb5  lea     rax, ??_7?$merged_data@U_tip_AutoFeatureRollbackRetrievePolicyTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AutoFeatureRollbackRetrievePolicyTest,_tip_AutoFeatureRollbackRetrievePolicyTest>::`vftable'
0x180054fbc  mov     dword ptr [rbx+110h], 1
0x180054fc6  mov     [rbx], rax
0x180054fc9  lea     rax, [rbx+10h]
0x180054fcd  mov     [rbx+108h], rax
0x180054fd4  mov     rax, rdi
0x180054fd7  mov     [rdi], rbx
0x180054fda  mov     rbx, [rsp+58h+arg_0]
0x180054fdf  add     rsp, 50h
0x180054fe3  pop     rdi
0x180054fe4  retn
```
