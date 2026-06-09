# winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::Root(winrt::Windows::UI::Composition::Visual const &)

- ea: `0x180024874`
- end: `0x18002492c`
- name: `?Root@?$consume_Windows_UI_Composition_Internal_IWriteCaptureController@UCaptureController@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUVisual@Composition@UI@Windows@3@@Z`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024298`

## callees

- `0x180003580`
- `0x1800125ec`
- `0x180024874`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::Root(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        _QWORD *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, __int64 *, __int64 *); // rcx
  unsigned int v4; // eax
  __int64 v5; // rbx
  unsigned int v6; // eax
  int v8; // [rsp+20h] [rbp-20h] BYREF
  __int128 v9; // [rsp+28h] [rbp-18h]
  __int64 v10; // [rsp+50h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    v10 = 0;
    v4 = (**v3)(v3, winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::IWriteCaptureController>, &v10);
    v5 = v10;
    v11 = v10;
  }
  else
  {
    v4 = 0;
    v11 = 0;
    v5 = 0;
  }
  v8 = 0;
  v9 = 0;
  winrt::check_hresult(&v10, v4, &v8);
  v8 = 0;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v5 + 152LL))(v5, *a2);
  winrt::check_hresult(&v10, v6, &v8);
  return winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v11);
}

```

## disassembly

```asm
0x180024874  mov     [rsp-8+arg_8], rbx
0x180024879  mov     [rsp-8+arg_18], rdi
0x18002487e  push    rbp
0x18002487f  mov     rbp, rsp
0x180024882  sub     rsp, 40h
0x180024886  mov     rdi, rdx
0x180024889  mov     rcx, [rcx]
0x18002488c  test    rcx, rcx
0x18002488f  jnz     short loc_18002489B
0x180024891  xor     eax, eax
0x180024893  mov     [rbp+arg_10], rax
0x180024897  xor     ebx, ebx
0x180024899  jmp     short loc_1800248C1
0x18002489b  mov     [rbp+arg_0], 0
0x1800248a3  mov     rax, [rcx]
0x1800248a6  lea     r8, [rbp+arg_0]
0x1800248aa  lea     rdx, ??$guid_v@UIWriteCaptureController@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::IWriteCaptureController>
0x1800248b1  mov     rax, [rax]
0x1800248b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248b9  mov     rbx, [rbp+arg_0]
0x1800248bd  mov     [rbp+arg_10], rbx
0x1800248c1  mov     [rbp+var_20], 0
0x1800248c8  xorps   xmm0, xmm0
0x1800248cb  movdqu  [rbp+var_18], xmm0
0x1800248d0  lea     r8, [rbp+var_20]
0x1800248d4  mov     edx, eax
0x1800248d6  lea     rcx, [rbp+arg_0]
0x1800248da  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800248df  mov     [rbp+var_20], 0
0x1800248e6  xorps   xmm0, xmm0
0x1800248e9  movdqu  [rbp+var_18], xmm0
0x1800248ee  mov     rax, [rbx]
0x1800248f1  mov     rdx, [rdi]
0x1800248f4  mov     rcx, rbx
0x1800248f7  mov     rax, [rax+98h]
0x1800248fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024903  lea     r8, [rbp+var_20]
0x180024907  mov     edx, eax
0x180024909  lea     rcx, [rbp+arg_0]
0x18002490d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024912  nop
0x180024913  lea     rcx, [rbp+arg_10]
0x180024917  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x18002491c  mov     rbx, [rsp+40h+arg_8]
0x180024921  mov     rdi, [rsp+40h+arg_18]
0x180024926  add     rsp, 40h
0x18002492a  pop     rbp
0x18002492b  retn
```
