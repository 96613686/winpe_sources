# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>,>(void)

- ea: `0x180006cb0`
- end: `0x180006e16`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `358`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180018c48`

## callees

- `0x180006cb0`
- `0x1800155f4`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006d96`
- `KERNEL32!InitializeCriticalSection` at `0x180006d96`
- `ole32!CoTaskMemAlloc` at `0x180006cc7`
- `ole32!CoTaskMemAlloc` at `0x180006cc7`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _QWORD *result; // rax

  v3 = (char *)CoTaskMemAlloc(0x158u);
  if ( !v3 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v2);
  *(_QWORD *)v3 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>::`vftable';
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 1) = v3;
  *((_QWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 12) = 0;
  *((_QWORD *)v3 + 13) = 0;
  *((_QWORD *)v3 + 14) = 0;
  *((_QWORD *)v3 + 15) = 0;
  *((_QWORD *)v3 + 16) = 0;
  *((_QWORD *)v3 + 17) = 0;
  *((_QWORD *)v3 + 18) = 0;
  *((_DWORD *)v3 + 18) = 0;
  *(_OWORD *)(v3 + 152) = 0;
  v3[168] = 0;
  *((_WORD *)v3 + 85) = -1;
  *((_QWORD *)v3 + 22) = 0;
  *((_QWORD *)v3 + 23) = 0;
  *((_QWORD *)v3 + 31) = 0;
  *(_DWORD *)(v3 + 42) = 0;
  *((_WORD *)v3 + 23) = 0;
  *((_DWORD *)v3 + 48) = 0;
  *((_DWORD *)v3 + 60) = 0;
  *((_DWORD *)v3 + 6) = 58994979;
  *((_DWORD *)v3 + 7) = 180544;
  *((_QWORD *)v3 + 4) = "AOMDUsageTipTest";
  *((_WORD *)v3 + 20) = 1;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 5);
  *((_QWORD *)v3 + 33) = 0;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::`vftable';
  *((_QWORD *)v3 + 32) = v3 + 16;
  result = a1;
  *((_QWORD *)v3 + 34) = 0;
  *((_QWORD *)v3 + 35) = 0;
  *((_QWORD *)v3 + 36) = 0;
  *((_QWORD *)v3 + 37) = 0;
  *((_QWORD *)v3 + 38) = 0;
  *((_QWORD *)v3 + 39) = 0;
  *((_QWORD *)v3 + 40) = 0;
  *((_QWORD *)v3 + 41) = 0;
  *((_DWORD *)v3 + 84) = 1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180006cb0  mov     [rsp+arg_0], rbx
0x180006cb5  mov     [rsp+arg_8], rsi
0x180006cba  push    rdi
0x180006cbb  sub     rsp, 20h
0x180006cbf  mov     rdi, rcx
0x180006cc2  mov     ecx, 158h; cb
0x180006cc7  call    cs:__imp_CoTaskMemAlloc
0x180006ccd  xor     esi, esi
0x180006ccf  mov     rbx, rax
0x180006cd2  test    rax, rax
0x180006cd5  jz      loc_180006E10
0x180006cdb  xor     r8d, r8d
0x180006cde  lea     rax, ??_7?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>::`vftable'
0x180006ce5  mov     [rbx], rax
0x180006ce8  lea     rdx, aAomdusagetipte_1; "AOMDUsageTipTest"
0x180006cef  mov     [rbx+10h], rsi
0x180006cf3  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180006cfa  mov     [rbx+8], rbx
0x180006cfe  xorps   xmm0, xmm0
0x180006d01  mov     [rbx+50h], rsi
0x180006d05  mov     [rbx+58h], rsi
0x180006d09  mov     [rbx+60h], rsi
0x180006d0d  mov     [rbx+68h], rsi
0x180006d11  mov     [rbx+70h], rsi
0x180006d15  mov     [rbx+78h], rsi
0x180006d19  mov     [rbx+80h], rsi
0x180006d20  mov     [rbx+88h], rsi
0x180006d27  mov     [rbx+90h], rsi
0x180006d2e  mov     [rbx+48h], esi
0x180006d31  movups  xmmword ptr [rbx+98h], xmm0
0x180006d38  mov     [rbx+0A8h], sil
0x180006d3f  mov     word ptr [rbx+0AAh], 0FFFFh
0x180006d48  mov     [rbx+0B0h], rsi
0x180006d4f  mov     [rbx+0B8h], rsi
0x180006d56  mov     [rbx+0F8h], rsi
0x180006d5d  mov     [rbx+2Ah], r8d
0x180006d61  mov     [rbx+2Eh], r8w
0x180006d66  mov     [rbx+0C0h], esi
0x180006d6c  mov     [rbx+0F0h], esi
0x180006d72  mov     dword ptr [rbx+18h], 3843123h
0x180006d79  mov     dword ptr [rbx+1Ch], 2C140h
0x180006d80  mov     [rbx+20h], rdx
0x180006d84  mov     word ptr [rbx+28h], 1
0x180006d8a  mov     [rbx+30h], rsi
0x180006d8e  mov     [rbx+38h], rsi
0x180006d92  mov     [rbx+40h], rsi
0x180006d96  call    cs:__imp_InitializeCriticalSection
0x180006d9c  mov     [rbx+108h], rsi
0x180006da3  lea     rax, ??_7?$merged_data@U_tip_AOMDUsageTipTest_attributes@@Vtest_data_basic@tip2@@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AOMDUsageTipTest_attributes,tip2::test_data_basic>::`vftable'
0x180006daa  mov     [rbx], rax
0x180006dad  lea     rax, [rbx+10h]
0x180006db1  mov     [rbx+100h], rax
0x180006db8  mov     rax, rdi
0x180006dbb  mov     [rbx+110h], rsi
0x180006dc2  mov     [rbx+118h], rsi
0x180006dc9  mov     [rbx+120h], rsi
0x180006dd0  mov     [rbx+128h], rsi
0x180006dd7  mov     [rbx+130h], rsi
0x180006dde  mov     [rbx+138h], rsi
0x180006de5  mov     [rbx+140h], rsi
0x180006dec  mov     [rbx+148h], rsi
0x180006df3  mov     rsi, [rsp+28h+arg_8]
0x180006df8  mov     dword ptr [rbx+150h], 1
0x180006e02  mov     [rdi], rbx
0x180006e05  mov     rbx, [rsp+28h+arg_0]
0x180006e0a  add     rsp, 20h
0x180006e0e  pop     rdi
0x180006e0f  retn
0x180006e10  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
