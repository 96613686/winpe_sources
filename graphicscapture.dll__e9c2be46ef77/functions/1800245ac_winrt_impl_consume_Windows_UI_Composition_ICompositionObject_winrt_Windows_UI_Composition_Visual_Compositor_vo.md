# winrt::impl::consume_Windows_UI_Composition_ICompositionObject<winrt::Windows::UI::Composition::Visual>::Compositor(void)

- ea: `0x1800245ac`
- end: `0x180024669`
- name: `?Compositor@?$consume_Windows_UI_Composition_ICompositionObject@UVisual@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024298`

## callees

- `0x180003580`
- `0x1800125ec`
- `0x1800245ac`
- `0x180028010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositionObject<winrt::Windows::UI::Composition::Visual>::Compositor(
        __int64 (__fastcall ****a1)(_QWORD, __int64 *, _QWORD **),
        _QWORD *a2)
{
  __int64 (__fastcall ***v3)(_QWORD, __int64 *, _QWORD **); // rcx
  unsigned int v4; // eax
  _QWORD *v5; // rbx
  unsigned int v6; // eax
  int v8; // [rsp+28h] [rbp-18h] BYREF
  __int128 v9; // [rsp+30h] [rbp-10h]
  _QWORD *v10; // [rsp+60h] [rbp+20h] BYREF
  _QWORD *v11; // [rsp+68h] [rbp+28h] BYREF
  __int64 v12; // [rsp+70h] [rbp+30h] BYREF

  v11 = a2;
  v12 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v11 = 0;
    v4 = (**v3)(v3, winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject>, &v11);
    v5 = v11;
    v10 = v11;
  }
  else
  {
    v4 = 0;
    v10 = 0;
    v5 = 0;
  }
  v8 = 0;
  v9 = 0;
  winrt::check_hresult(&v11, v4, &v8);
  v8 = 0;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v5 + 48LL))(v5, &v12);
  winrt::check_hresult(&v11, v6, &v8);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v10);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x1800245ac  mov     [rsp-18h+arg_8], rdx
0x1800245b1  push    rbp
0x1800245b2  push    rbx
0x1800245b3  push    rdi
0x1800245b4  mov     rbp, rsp
0x1800245b7  sub     rsp, 40h
0x1800245bb  mov     rdi, rdx
0x1800245be  mov     [rbp+arg_10], 0
0x1800245c6  mov     rcx, [rcx]
0x1800245c9  test    rcx, rcx
0x1800245cc  jnz     short loc_1800245D8
0x1800245ce  xor     eax, eax
0x1800245d0  mov     [rbp+arg_0], rax
0x1800245d4  xor     ebx, ebx
0x1800245d6  jmp     short loc_1800245FE
0x1800245d8  mov     [rbp+arg_8], 0
0x1800245e0  mov     rax, [rcx]
0x1800245e3  lea     r8, [rbp+arg_8]
0x1800245e7  lea     rdx, ??$guid_v@UICompositionObject@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject>
0x1800245ee  mov     rax, [rax]
0x1800245f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800245f6  mov     rbx, [rbp+arg_8]
0x1800245fa  mov     [rbp+arg_0], rbx
0x1800245fe  mov     [rbp+var_18], 0
0x180024605  xorps   xmm0, xmm0
0x180024608  movdqu  [rbp+var_10], xmm0
0x18002460d  lea     r8, [rbp+var_18]
0x180024611  mov     edx, eax
0x180024613  lea     rcx, [rbp+arg_8]
0x180024617  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002461c  mov     [rbp+var_18], 0
0x180024623  xorps   xmm0, xmm0
0x180024626  movdqu  [rbp+var_10], xmm0
0x18002462b  mov     rax, [rbx]
0x18002462e  lea     rdx, [rbp+arg_10]
0x180024632  mov     rcx, rbx
0x180024635  mov     rax, [rax+30h]
0x180024639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002463e  lea     r8, [rbp+var_18]
0x180024642  mov     edx, eax
0x180024644  lea     rcx, [rbp+arg_8]
0x180024648  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18002464d  nop
0x18002464e  lea     rcx, [rbp+arg_0]
0x180024652  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180024657  mov     rax, [rbp+arg_10]
0x18002465b  mov     [rdi], rax
0x18002465e  mov     rax, rdi
0x180024661  add     rsp, 40h
0x180024665  pop     rdi
0x180024666  pop     rbx
0x180024667  pop     rbp
0x180024668  retn
```
