# winrt::impl::consume_Windows_UI_Composition_ICompositionObject2<winrt::Windows::UI::Composition::Visual>::Comment(void)

- ea: `0x1800181ac`
- end: `0x180018269`
- name: `?Comment@?$consume_Windows_UI_Composition_ICompositionObject2@UVisual@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180018ec0`

## callees

- `0x180003580`
- `0x1800125ec`
- `0x1800181ac`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositionObject2<winrt::Windows::UI::Composition::Visual>::Comment(
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
    v4 = (**v3)(v3, winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject2>, &v11);
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
0x1800181ac  mov     [rsp-18h+arg_8], rdx
0x1800181b1  push    rbp
0x1800181b2  push    rbx
0x1800181b3  push    rdi
0x1800181b4  mov     rbp, rsp
0x1800181b7  sub     rsp, 40h
0x1800181bb  mov     rdi, rdx
0x1800181be  mov     [rbp+arg_10], 0
0x1800181c6  mov     rcx, [rcx]
0x1800181c9  test    rcx, rcx
0x1800181cc  jnz     short loc_1800181D8
0x1800181ce  xor     eax, eax
0x1800181d0  mov     [rbp+arg_0], rax
0x1800181d4  xor     ebx, ebx
0x1800181d6  jmp     short loc_1800181FE
0x1800181d8  mov     [rbp+arg_8], 0
0x1800181e0  mov     rax, [rcx]
0x1800181e3  lea     r8, [rbp+arg_8]
0x1800181e7  lea     rdx, ??$guid_v@UICompositionObject2@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject2>
0x1800181ee  mov     rax, [rax]
0x1800181f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181f6  mov     rbx, [rbp+arg_8]
0x1800181fa  mov     [rbp+arg_0], rbx
0x1800181fe  mov     [rbp+var_18], 0
0x180018205  xorps   xmm0, xmm0
0x180018208  movdqu  [rbp+var_10], xmm0
0x18001820d  lea     r8, [rbp+var_18]
0x180018211  mov     edx, eax
0x180018213  lea     rcx, [rbp+arg_8]
0x180018217  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001821c  mov     [rbp+var_18], 0
0x180018223  xorps   xmm0, xmm0
0x180018226  movdqu  [rbp+var_10], xmm0
0x18001822b  mov     rax, [rbx]
0x18001822e  lea     rdx, [rbp+arg_10]
0x180018232  mov     rcx, rbx
0x180018235  mov     rax, [rax+30h]
0x180018239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001823e  lea     r8, [rbp+var_18]
0x180018242  mov     edx, eax
0x180018244  lea     rcx, [rbp+arg_8]
0x180018248  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001824d  nop
0x18001824e  lea     rcx, [rbp+arg_0]
0x180018252  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180018257  mov     rax, [rbp+arg_10]
0x18001825b  mov     [rdi], rax
0x18001825e  mov     rax, rdi
0x180018261  add     rsp, 40h
0x180018265  pop     rdi
0x180018266  pop     rbx
0x180018267  pop     rbp
0x180018268  retn
```
