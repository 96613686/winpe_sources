# winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::IsConstrainedBySize(bool)

- ea: `0x180024738`
- end: `0x1800247e3`
- name: `?IsConstrainedBySize@?$consume_Windows_UI_Composition_Internal_IWriteCaptureController@UCaptureController@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@_N@Z`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024298`

## callees

- `0x180003580`
- `0x1800125ec`
- `0x180024738`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::IsConstrainedBySize(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        char a2)
{
  __int64 (__fastcall ***v2)(_QWORD, __int64 *, __int64 *); // rcx
  unsigned int v3; // eax
  __int64 v4; // rbx
  unsigned int v5; // eax
  int v7; // [rsp+20h] [rbp-20h] BYREF
  __int128 v8; // [rsp+28h] [rbp-18h]
  __int64 v9; // [rsp+50h] [rbp+10h] BYREF
  char v10; // [rsp+58h] [rbp+18h] BYREF

  v10 = a2;
  v2 = *a1;
  if ( v2 )
  {
    v9 = 0;
    v3 = (**v2)(v2, winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::IWriteCaptureController>, &v9);
    v4 = v9;
  }
  else
  {
    v3 = 0;
    v9 = 0;
    v4 = 0;
  }
  v7 = 0;
  v8 = 0;
  winrt::check_hresult(&v10, v3, &v7);
  v7 = 0;
  v8 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 120LL))(v4, 0);
  winrt::check_hresult(&v10, v5, &v7);
  return winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v9);
}

```

## disassembly

```asm
0x180024738  mov     [rsp-8+arg_10], rbx
0x18002473d  mov     [rsp-8+arg_8], dl
0x180024741  push    rbp
0x180024742  mov     rbp, rsp
0x180024745  sub     rsp, 40h
0x180024749  mov     rcx, [rcx]
0x18002474c  test    rcx, rcx
0x18002474f  jnz     short loc_18002475B
0x180024751  xor     eax, eax
0x180024753  mov     [rbp+arg_0], rax
0x180024757  xor     ebx, ebx
0x180024759  jmp     short loc_180024781
0x18002475b  mov     [rbp+arg_0], 0
0x180024763  mov     rax, [rcx]
0x180024766  lea     r8, [rbp+arg_0]
0x18002476a  lea     rdx, ??$guid_v@UIWriteCaptureController@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::IWriteCaptureController>
0x180024771  mov     rax, [rax]
0x180024774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024779  mov     rbx, [rbp+arg_0]
0x18002477d  mov     [rbp+arg_0], rbx
0x180024781  mov     [rbp+var_20], 0
0x180024788  xorps   xmm0, xmm0
0x18002478b  movdqu  [rbp+var_18], xmm0
0x180024790  lea     r8, [rbp+var_20]
0x180024794  mov     edx, eax
0x180024796  lea     rcx, [rbp+arg_8]
0x18002479a  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002479f  mov     [rbp+var_20], 0
0x1800247a6  xorps   xmm0, xmm0
0x1800247a9  movdqu  [rbp+var_18], xmm0
0x1800247ae  mov     rax, [rbx]
0x1800247b1  xor     edx, edx
0x1800247b3  mov     rcx, rbx
0x1800247b6  mov     rax, [rax+78h]
0x1800247ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800247bf  lea     r8, [rbp+var_20]
0x1800247c3  mov     edx, eax
0x1800247c5  lea     rcx, [rbp+arg_8]
0x1800247c9  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800247ce  nop
0x1800247cf  lea     rcx, [rbp+arg_0]
0x1800247d3  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800247d8  mov     rbx, [rsp+40h+arg_10]
0x1800247dd  add     rsp, 40h
0x1800247e1  pop     rbp
0x1800247e2  retn
```
