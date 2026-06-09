# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>,>(void)

- ea: `0x180030f84`
- end: `0x18003104f`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_EnrollmentAttestationTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_EnrollmentAttestationTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `203`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180031524`
- `0x180034b80`

## callees

- `0x18000cbf0`
- `0x180030f84`
- `0x180031058`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030f96`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180030f96`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>,>(
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

  v2 = CoTaskMemAlloc(0x120u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  v6[0] = 55920397;
  v9 = 0;
  *v2 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable';
  v10 = 0;
  v12 = 0;
  v7 = "EnrollmentAttestationTipTest";
  v6[1] = 49664;
  v8 = 513;
  v11 = 0;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(v2 + 1, v2, v6);
  *((_DWORD *)v4 + 68) = 0;
  *v4 = &tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::`vftable';
  v4[33] = v4 + 2;
  result = a1;
  *((_WORD *)v4 + 138) = 0;
  *((_DWORD *)v4 + 70) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180030f84  mov     [rsp+arg_0], rbx
0x180030f89  push    rdi
0x180030f8a  sub     rsp, 50h
0x180030f8e  mov     rdi, rcx
0x180030f91  mov     ecx, 120h; cb
0x180030f96  call    cs:__imp_CoTaskMemAlloc
0x180030f9d  nop     dword ptr [rax+rax+00h]
0x180030fa2  mov     rbx, rax
0x180030fa5  test    rax, rax
0x180030fa8  jz      loc_180031049
0x180030fae  xor     ecx, ecx
0x180030fb0  mov     [rsp+58h+var_38], 355470Dh
0x180030fb8  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVDeviceInformationCollection@Enumeration@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Enumeration::DeviceInformationCollection *>::`vftable'
0x180030fbf  mov     [rsp+58h+var_26], ecx
0x180030fc3  mov     [rbx], rax
0x180030fc6  lea     r8, [rsp+58h+var_38]
0x180030fcb  lea     rax, aEnrollmentatte; "EnrollmentAttestationTipTest"
0x180030fd2  mov     [rsp+58h+var_22], cx
0x180030fd7  xorps   xmm0, xmm0
0x180030fda  mov     [rsp+58h+var_10], rcx
0x180030fdf  lea     rcx, [rbx+8]
0x180030fe3  mov     [rsp+58h+var_30], rax
0x180030fe8  mov     rdx, rbx
0x180030feb  mov     [rsp+58h+var_34], 0C200h
0x180030ff3  mov     [rsp+58h+var_28], 201h
0x180030ffa  movdqu  [rsp+58h+var_20], xmm0
0x180031000  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x180031005  lea     rax, ??_7?$merged_data@U_tip_EnrollmentAttestationTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_EnrollmentAttestationTipTest,_tip_EnrollmentAttestationTipTest>::`vftable'
0x18003100c  mov     dword ptr [rbx+110h], 0
0x180031016  mov     [rbx], rax
0x180031019  lea     rax, [rbx+10h]
0x18003101d  mov     [rbx+108h], rax
0x180031024  mov     rax, rdi
0x180031027  mov     word ptr [rbx+114h], 0
0x180031030  mov     dword ptr [rbx+118h], 1
0x18003103a  mov     [rdi], rbx
0x18003103d  mov     rbx, [rsp+58h+arg_0]
0x180031042  add     rsp, 50h
0x180031046  pop     rdi
0x180031047  retn
0x180031049  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
