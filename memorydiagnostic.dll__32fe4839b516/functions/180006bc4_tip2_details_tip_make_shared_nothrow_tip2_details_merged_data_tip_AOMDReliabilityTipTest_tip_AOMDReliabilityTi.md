# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(void)

- ea: `0x180006bc4`
- end: `0x180006d18`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `340`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180006a0c`
- `0x180015cd0`

## callees

- `0x180006bc4`
- `0x1800162d8`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006cd0`
- `KERNEL32!InitializeCriticalSection` at `0x180006cd0`
- `ole32!CoTaskMemAlloc` at `0x180006bde`
- `ole32!CoTaskMemAlloc` at `0x180006bde`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(
        _QWORD *a1)
{
  char *v2; // rax
  char *v3; // rbx
  _QWORD *result; // rax
  __int128 v5; // [rsp+20h] [rbp-30h]

  v2 = (char *)CoTaskMemAlloc(0x118u);
  v3 = v2;
  if ( !v2 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
  *(_QWORD *)&v5 = 0xC1400384C3B9LL;
  *(_QWORD *)v2 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>::`vftable';
  *((_QWORD *)v2 + 2) = 0;
  *((_QWORD *)v2 + 1) = v2;
  *(_OWORD *)(v2 + 24) = 0;
  *((_QWORD *)&v5 + 1) = "AOMDReliabilityTipTest";
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
  *((_DWORD *)v2 + 48) = 0;
  *((_DWORD *)v2 + 60) = 0;
  *(_OWORD *)(v2 + 24) = v5;
  *(_OWORD *)(v2 + 40) = 1u;
  *(_OWORD *)(v2 + 56) = 0u;
  InitializeCriticalSection((LPCRITICAL_SECTION)v2 + 5);
  *((_DWORD *)v3 + 68) = 1;
  *(_QWORD *)v3 = &tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::`vftable';
  *((_QWORD *)v3 + 33) = v3 + 16;
  result = a1;
  *a1 = v3;
  return result;
}

```

## disassembly

```asm
0x180006bc4  mov     [rsp-8+arg_0], rbx
0x180006bc9  mov     [rsp-8+arg_8], rdi
0x180006bce  push    rbp
0x180006bcf  mov     rbp, rsp
0x180006bd2  sub     rsp, 50h
0x180006bd6  mov     rdi, rcx
0x180006bd9  mov     ecx, 118h; cb
0x180006bde  call    cs:__imp_CoTaskMemAlloc
0x180006be5  nop     dword ptr [rax+rax+00h]
0x180006bea  xor     ecx, ecx; this
0x180006bec  mov     rbx, rax
0x180006bef  test    rax, rax
0x180006bf2  jz      loc_180006D12
0x180006bf8  xorps   xmm0, xmm0
0x180006bfb  mov     [rbp+var_8], rcx
0x180006bff  movdqu  [rbp+var_20+8], xmm0
0x180006c04  lea     rax, ??_7?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>::`vftable'
0x180006c0b  mov     dword ptr [rbp+var_30], 384C3B9h
0x180006c12  mov     [rbx], rax
0x180006c15  lea     rax, aAomdreliabilit; "AOMDReliabilityTipTest"
0x180006c1c  mov     [rbx+10h], rcx
0x180006c20  mov     [rbx+8], rbx
0x180006c24  movups  xmmword ptr [rbx+18h], xmm0
0x180006c28  mov     qword ptr [rbp+var_30+8], rax
0x180006c2c  xor     eax, eax
0x180006c2e  movups  xmmword ptr [rbx+28h], xmm0
0x180006c32  mov     dword ptr [rbp+var_20+2], eax
0x180006c35  movups  xmmword ptr [rbx+38h], xmm0
0x180006c39  mov     [rbx+50h], rcx
0x180006c3d  mov     [rbx+58h], rcx
0x180006c41  mov     [rbx+60h], rcx
0x180006c45  mov     [rbx+68h], rcx
0x180006c49  mov     [rbx+70h], rcx
0x180006c4d  mov     [rbx+78h], rcx
0x180006c51  mov     [rbx+80h], rcx
0x180006c58  mov     [rbx+88h], rcx
0x180006c5f  mov     [rbx+90h], rcx
0x180006c66  mov     [rbx+48h], ecx
0x180006c69  movups  xmmword ptr [rbx+98h], xmm0
0x180006c70  or      word ptr [rbx+0AAh], 0FFFFh
0x180006c79  mov     [rbx+0A8h], cl
0x180006c7f  mov     [rbx+0B0h], rcx
0x180006c86  mov     [rbx+0B8h], rcx
0x180006c8d  mov     [rbx+0F8h], rcx
0x180006c94  mov     word ptr [rbp+var_20+6], ax
0x180006c98  mov     [rbx+0C0h], ecx
0x180006c9e  mov     [rbx+0F0h], ecx
0x180006ca4  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180006cab  mov     dword ptr [rbp+var_30+4], 0C140h
0x180006cb2  movups  xmm0, [rbp+var_30]
0x180006cb6  mov     word ptr [rbp+var_20], 1
0x180006cbc  movups  xmm1, [rbp+var_20]
0x180006cc0  movups  xmmword ptr [rbx+18h], xmm0
0x180006cc4  movups  xmm0, xmmword ptr [rbp-10h]
0x180006cc8  movups  xmmword ptr [rbx+28h], xmm1
0x180006ccc  movups  xmmword ptr [rbx+38h], xmm0
0x180006cd0  call    cs:__imp_InitializeCriticalSection
0x180006cd7  nop     dword ptr [rax+rax+00h]
0x180006cdc  lea     rax, ??_7?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::`vftable'
0x180006ce3  mov     dword ptr [rbx+110h], 1
0x180006ced  mov     [rbx], rax
0x180006cf0  lea     rax, [rbx+10h]
0x180006cf4  mov     [rbx+108h], rax
0x180006cfb  mov     rax, rdi
0x180006cfe  mov     [rdi], rbx
0x180006d01  mov     rbx, [rsp+50h+arg_0]
0x180006d06  mov     rdi, [rsp+50h+arg_8]
0x180006d0b  add     rsp, 50h
0x180006d0f  pop     rbp
0x180006d10  retn
0x180006d12  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
