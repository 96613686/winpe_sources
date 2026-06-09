# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(void)

- ea: `0x180006b88`
- end: `0x180006ca9`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@$$V@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ`
- size: `289`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callers

- `0x180015e38`

## callees

- `0x180006b88`
- `0x1800155f4`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x180006c6d`
- `KERNEL32!InitializeCriticalSection` at `0x180006c6d`
- `ole32!CoTaskMemAlloc` at `0x180006b9a`
- `ole32!CoTaskMemAlloc` at `0x180006b9a`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>,>(
        _QWORD *a1)
{
  wil::details::in1diag3 *v2; // rcx
  char *v3; // rbx
  _QWORD *result; // rax

  v3 = (char *)CoTaskMemAlloc(0x118u);
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
  *((_DWORD *)v3 + 6) = 59032505;
  *((_DWORD *)v3 + 7) = 49472;
  *((_QWORD *)v3 + 4) = "AOMDReliabilityTipTest";
  *((_WORD *)v3 + 20) = 1;
  *((_QWORD *)v3 + 6) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)v3 + 5);
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
0x180006b88  mov     [rsp+arg_0], rbx
0x180006b8d  push    rdi
0x180006b8e  sub     rsp, 20h
0x180006b92  mov     rdi, rcx
0x180006b95  mov     ecx, 118h; cb
0x180006b9a  call    cs:__imp_CoTaskMemAlloc
0x180006ba0  xor     r9d, r9d
0x180006ba3  mov     rbx, rax
0x180006ba6  test    rax, rax
0x180006ba9  jz      loc_180006CA3
0x180006baf  xor     r8d, r8d
0x180006bb2  lea     rax, ??_7?$ITypedEventHandler@PEAVToastNotification@Notifications@UI@Windows@@PEAVToastFailedEventArgs@234@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Notifications::ToastNotification *,Windows::UI::Notifications::ToastFailedEventArgs *>::`vftable'
0x180006bb9  mov     [rbx], rax
0x180006bbc  lea     rdx, aAomdreliabilit; "AOMDReliabilityTipTest"
0x180006bc3  mov     [rbx+10h], r9
0x180006bc7  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180006bce  mov     [rbx+8], rbx
0x180006bd2  xorps   xmm0, xmm0
0x180006bd5  mov     [rbx+50h], r9
0x180006bd9  mov     [rbx+58h], r9
0x180006bdd  mov     [rbx+60h], r9
0x180006be1  mov     [rbx+68h], r9
0x180006be5  mov     [rbx+70h], r9
0x180006be9  mov     [rbx+78h], r9
0x180006bed  mov     [rbx+80h], r9
0x180006bf4  mov     [rbx+88h], r9
0x180006bfb  mov     [rbx+90h], r9
0x180006c02  mov     [rbx+48h], r9d
0x180006c06  movups  xmmword ptr [rbx+98h], xmm0
0x180006c0d  mov     [rbx+0A8h], r9b
0x180006c14  mov     word ptr [rbx+0AAh], 0FFFFh
0x180006c1d  mov     [rbx+0B0h], r9
0x180006c24  mov     [rbx+0B8h], r9
0x180006c2b  mov     [rbx+0F8h], r9
0x180006c32  mov     [rbx+2Ah], r8d
0x180006c36  mov     [rbx+2Eh], r8w
0x180006c3b  mov     [rbx+0C0h], r9d
0x180006c42  mov     [rbx+0F0h], r9d
0x180006c49  mov     dword ptr [rbx+18h], 384C3B9h
0x180006c50  mov     dword ptr [rbx+1Ch], 0C140h
0x180006c57  mov     [rbx+20h], rdx
0x180006c5b  mov     word ptr [rbx+28h], 1
0x180006c61  mov     [rbx+30h], r9
0x180006c65  mov     [rbx+38h], r9
0x180006c69  mov     [rbx+40h], r9
0x180006c6d  call    cs:__imp_InitializeCriticalSection
0x180006c73  lea     rax, ??_7?$merged_data@U_tip_AOMDReliabilityTipTest@@U1@@details@tip2@@6B@; const tip2::details::merged_data<_tip_AOMDReliabilityTipTest,_tip_AOMDReliabilityTipTest>::`vftable'
0x180006c7a  mov     dword ptr [rbx+110h], 1
0x180006c84  mov     [rbx], rax
0x180006c87  lea     rax, [rbx+10h]
0x180006c8b  mov     [rbx+108h], rax
0x180006c92  mov     rax, rdi
0x180006c95  mov     [rdi], rbx
0x180006c98  mov     rbx, [rsp+28h+arg_0]
0x180006c9d  add     rsp, 20h
0x180006ca1  pop     rdi
0x180006ca2  retn
0x180006ca3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
