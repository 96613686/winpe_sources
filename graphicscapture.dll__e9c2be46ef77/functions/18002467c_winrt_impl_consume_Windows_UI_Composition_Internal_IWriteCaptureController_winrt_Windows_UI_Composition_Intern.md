# winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::IsCapturing(bool)

- ea: `0x18002467c`
- end: `0x180024731`
- name: `?IsCapturing@?$consume_Windows_UI_Composition_Internal_IWriteCaptureController@UCaptureController@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@_N@Z`
- size: `181`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024298`
- `0x180024bd0`
- `0x180024bf0`

## callees

- `0x180003580`
- `0x1800125ec`
- `0x18002467c`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::impl::consume_Windows_UI_Composition_Internal_IWriteCaptureController<winrt::Windows::UI::Composition::Internal::CaptureController>::IsCapturing(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, __int64 *),
        char a2)
{
  __int64 (__fastcall ***v3)(_QWORD, __int64 *, __int64 *); // rcx
  unsigned int v4; // eax
  __int64 v5; // rbx
  __int64 v6; // rdx
  unsigned int v7; // eax
  int v9; // [rsp+20h] [rbp-20h] BYREF
  __int128 v10; // [rsp+28h] [rbp-18h]
  __int64 v11; // [rsp+50h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF

  v3 = *a1;
  if ( v3 )
  {
    v11 = 0;
    v4 = (**v3)(v3, winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::IWriteCaptureController>, &v11);
    v5 = v11;
    v12 = v11;
  }
  else
  {
    v4 = 0;
    v12 = 0;
    v5 = 0;
  }
  v9 = 0;
  v10 = 0;
  winrt::check_hresult(&v11, v4, &v9);
  v9 = 0;
  v10 = 0;
  LOBYTE(v6) = a2;
  v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 104LL))(v5, v6);
  winrt::check_hresult(&v11, v7, &v9);
  return winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v12);
}

```

## disassembly

```asm
0x18002467c  mov     [rsp-8+arg_8], rbx
0x180024681  mov     [rsp-8+arg_18], rdi
0x180024686  push    rbp
0x180024687  mov     rbp, rsp
0x18002468a  sub     rsp, 40h
0x18002468e  mov     dil, dl
0x180024691  mov     rcx, [rcx]
0x180024694  test    rcx, rcx
0x180024697  jnz     short loc_1800246A3
0x180024699  xor     eax, eax
0x18002469b  mov     [rbp+arg_10], rax
0x18002469f  xor     ebx, ebx
0x1800246a1  jmp     short loc_1800246C9
0x1800246a3  mov     [rbp+arg_0], 0
0x1800246ab  mov     rax, [rcx]
0x1800246ae  lea     r8, [rbp+arg_0]
0x1800246b2  lea     rdx, ??$guid_v@UIWriteCaptureController@Internal@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::Internal::IWriteCaptureController>
0x1800246b9  mov     rax, [rax]
0x1800246bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800246c1  mov     rbx, [rbp+arg_0]
0x1800246c5  mov     [rbp+arg_10], rbx
0x1800246c9  mov     [rbp+var_20], 0
0x1800246d0  xorps   xmm0, xmm0
0x1800246d3  movdqu  [rbp+var_18], xmm0
0x1800246d8  lea     r8, [rbp+var_20]
0x1800246dc  mov     edx, eax
0x1800246de  lea     rcx, [rbp+arg_0]
0x1800246e2  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800246e7  mov     [rbp+var_20], 0
0x1800246ee  xorps   xmm0, xmm0
0x1800246f1  movdqu  [rbp+var_18], xmm0
0x1800246f6  mov     rax, [rbx]
0x1800246f9  mov     dl, dil
0x1800246fc  mov     rcx, rbx
0x1800246ff  mov     rax, [rax+68h]
0x180024703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024708  lea     r8, [rbp+var_20]
0x18002470c  mov     edx, eax
0x18002470e  lea     rcx, [rbp+arg_0]
0x180024712  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180024717  nop
0x180024718  lea     rcx, [rbp+arg_10]
0x18002471c  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180024721  mov     rbx, [rsp+40h+arg_8]
0x180024726  mov     rdi, [rsp+40h+arg_18]
0x18002472b  add     rsp, 40h
0x18002472f  pop     rbp
0x180024730  retn
```
