# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>,>(void)

- ea: `0x180006d20`
- end: `0x180006ebe`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `414`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180019a18`

## callees

- `0x180006d20`
- `0x1800162d8`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006e32`
- `KERNEL32!InitializeCriticalSection` at `0x180006e32`
- `ole32!CoTaskMemAlloc` at `0x180006d3f`
- `ole32!CoTaskMemAlloc` at `0x180006d3f`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>,>(
        _QWORD *a1)
{
  char *v2; // rax
  wil::details::in1diag3 *v3; // rcx
  char *v4; // rbx
  _QWORD *result; // rax
  __int128 v6; // [rsp+20h] [rbp-30h]

  v2 = (char *)CoTaskMemAlloc(0x158u);
  v4 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  *(_QWORD *)&v6 = 0x2C14003843123LL;
  *(_QWORD *)v2 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>::`vftable';
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 1) = v2;
  *(_OWORD *)(v2 + 24) = 0;
  *((_QWORD *)&v6 + 1) = "AOMDUsageTipTest";
  *(_OWORD *)(v2 + 40) = 0;
  *(_OWORD *)(v2 + 56) = 0;
  *((_QWORD *)v2 + 10) = 0;
  *((_QWORD *)v2 + 11) = 0;
  *((_QWORD *)v2 + 12) = 0;
  *((_QWORD *)v2 + 13) = 0;
  *((_QWORD *)v2 + 14) = 0;
  *((_QWORD *)v2 + 15) = 0;
  *((_QWORD *)v2 + 16) = 0;
  *((_QWORD *)v2 + 17) = 0;
  *((_QWORD *)v2 + 18) = 0;
  *((_DWORD *)v2 + 18) = 0;
  *(_OWORD *)(v2 + 152) = 0;
  *((_WORD *)v2 + 85) = -1;
  v2[168] = 0;
  *((_QWORD *)v2 + 22) = 0;
  *((_QWORD *)v2 + 23) = 0;
  *((_QWORD *)v2 + 31) = 0;
  *(_OWORD *)(v2 + 24) = v6;
  *((_DWORD *)v2 + 48) = 0;
  *(_OWORD *)(v2 + 40) = 1u;
  *((_DWORD *)v2 + 60) = 0;
  *(_OWORD *)(v2 + 56) = 0u;
  InitializeCriticalSection((LPCRITICAL_SECTION)v2 + 5);
  *((_QWORD *)v4 + 33) = 0;
  *(_QWORD *)v4 = &tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::`vftable';
  *((_QWORD *)v4 + 32) = v4 + 16;
  result = a1;
  *((_QWORD *)v4 + 34) = 0;
  *((_QWORD *)v4 + 35) = 0;
  *((_QWORD *)v4 + 36) = 0;
  *((_QWORD *)v4 + 37) = 0;
  *((_QWORD *)v4 + 38) = 0;
  *((_QWORD *)v4 + 39) = 0;
  *((_QWORD *)v4 + 40) = 0;
  *((_QWORD *)v4 + 41) = 0;
  *((_DWORD *)v4 + 84) = 1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x180006d20  mov     [rsp-8+arg_0], rbx
0x180006d25  mov     [rsp-8+arg_8], rsi
0x180006d2a  mov     [rsp-8+arg_10], rdi
0x180006d2f  push    rbp
0x180006d30  mov     rbp, rsp
0x180006d33  sub     rsp, 50h
0x180006d37  mov     rdi, rcx
0x180006d3a  mov     ecx, 158h; cb
0x180006d3f  call    cs:__imp_CoTaskMemAlloc
0x180006d46  nop     dword ptr [rax+rax+00h]
0x180006d4b  xor     esi, esi
0x180006d4d  mov     rbx, rax
0x180006d50  test    rax, rax
0x180006d53  jz      loc_180006EB8
0x180006d59  xorps   xmm0, xmm0
0x180006d5c  mov     dword ptr [rbp+var_30], 3843123h
0x180006d63  movdqu  [rbp+var_20+8], xmm0
0x180006d68  lea     rax, ??_7?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>::`vftable'
0x180006d6f  mov     dword ptr [rbp+var_30+4], 2C140h
0x180006d76  mov     [rbx], rax
0x180006d79  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180006d80  mov     [rbx+10h], rsi
0x180006d84  lea     rax, aAomdusagetipte_1; "AOMDUsageTipTest"
0x180006d8b  mov     [rbx+8], rbx
0x180006d8f  movups  xmmword ptr [rbx+18h], xmm0
0x180006d93  mov     qword ptr [rbp+var_30+8], rax
0x180006d97  xor     eax, eax
0x180006d99  movups  xmmword ptr [rbx+28h], xmm0
0x180006d9d  mov     dword ptr [rbp+var_20+2], eax
0x180006da0  movups  xmmword ptr [rbx+38h], xmm0
0x180006da4  mov     [rbx+50h], rsi
0x180006da8  mov     [rbx+58h], rsi
0x180006dac  mov     [rbx+60h], rsi
0x180006db0  mov     [rbx+68h], rsi
0x180006db4  mov     [rbx+70h], rsi
0x180006db8  mov     [rbx+78h], rsi
0x180006dbc  mov     [rbx+80h], rsi
0x180006dc3  mov     [rbx+88h], rsi
0x180006dca  mov     [rbx+90h], rsi
0x180006dd1  mov     [rbx+48h], esi
0x180006dd4  movups  xmmword ptr [rbx+98h], xmm0
0x180006ddb  or      word ptr [rbx+0AAh], 0FFFFh
0x180006de4  movups  xmm0, [rbp+var_30]
0x180006de8  mov     [rbx+0A8h], sil
0x180006def  mov     [rbx+0B0h], rsi
0x180006df6  mov     [rbx+0B8h], rsi
0x180006dfd  mov     [rbx+0F8h], rsi
0x180006e04  movups  xmmword ptr [rbx+18h], xmm0
0x180006e08  mov     word ptr [rbp+var_20+6], ax
0x180006e0c  mov     word ptr [rbp+var_20], 1
0x180006e12  movups  xmm1, [rbp+var_20]
0x180006e16  mov     [rbp+var_8], rsi
0x180006e1a  movups  xmm0, xmmword ptr [rbp-10h]
0x180006e1e  mov     [rbx+0C0h], esi
0x180006e24  movups  xmmword ptr [rbx+28h], xmm1
0x180006e28  mov     [rbx+0F0h], esi
0x180006e2e  movups  xmmword ptr [rbx+38h], xmm0
0x180006e32  call    cs:__imp_InitializeCriticalSection
0x180006e39  nop     dword ptr [rax+rax+00h]
0x180006e3e  mov     [rbx+108h], rsi
0x180006e45  lea     rax, ??_7?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::`vftable'
0x180006e4c  mov     [rbx], rax
0x180006e4f  lea     rax, [rbx+10h]
0x180006e53  mov     [rbx+100h], rax
0x180006e5a  mov     rax, rdi
0x180006e5d  mov     [rbx+110h], rsi
0x180006e64  mov     [rbx+118h], rsi
0x180006e6b  mov     [rbx+120h], rsi
0x180006e72  mov     [rbx+128h], rsi
0x180006e79  mov     [rbx+130h], rsi
0x180006e80  mov     [rbx+138h], rsi
0x180006e87  mov     [rbx+140h], rsi
0x180006e8e  mov     [rbx+148h], rsi
0x180006e95  mov     rsi, [rsp+50h+arg_8]
0x180006e9a  mov     dword ptr [rbx+150h], 1
0x180006ea4  mov     [rdi], rbx
0x180006ea7  mov     rbx, [rsp+50h+arg_0]
0x180006eac  mov     rdi, [rsp+50h+arg_10]
0x180006eb1  add     rsp, 50h
0x180006eb5  pop     rbp
0x180006eb6  retn
0x180006eb8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
