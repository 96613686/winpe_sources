# winrt::Windows::Graphics::Capture::implementation::GetClosedEvent(winrt::Windows::UI::Composition::Visual const &)

- ea: `0x1800190c8`
- end: `0x180019183`
- name: `?GetClosedEvent@implementation@Capture@Graphics@Windows@winrt@@YAPEAXAEBUVisual@Composition@UI@45@@Z`
- size: `187`
- prototype: `void *__fastcall(winrt::Windows::Graphics::Capture::implementation *__hidden this, const struct winrt::Windows::UI::Composition::Visual *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017300`

## callees

- `0x180003580`
- `0x1800125ec`
- `0x1800168e4`
- `0x1800190c8`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall winrt::Windows::Graphics::Capture::implementation::GetClosedEvent(
        winrt::Windows::Graphics::Capture::implementation *this,
        const struct winrt::Windows::UI::Composition::Visual *a2)
{
  __int64 (__fastcall ***v2)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v3; // rcx
  unsigned int v4; // eax
  unsigned int v5; // eax
  __int64 v6; // rbx
  int v8; // [rsp+20h] [rbp-30h] BYREF
  __int128 v9; // [rsp+28h] [rbp-28h]
  int v10; // [rsp+38h] [rbp-18h] BYREF
  __int128 v11; // [rsp+40h] [rbp-10h]
  char v12; // [rsp+60h] [rbp+10h] BYREF
  __int64 v13; // [rsp+68h] [rbp+18h] BYREF
  __int64 v14; // [rsp+70h] [rbp+20h] BYREF

  v2 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))this;
  if ( v2 )
  {
    v13 = 0;
    v8 = 0;
    v9 = 0;
    v4 = (**v2)(v2, winrt::impl::guid_v<winrt::Windows::UI::Composition::Private::IVisualPrivate>, &v13);
    winrt::check_hresult(&v12, v4, &v8);
    v3 = v13;
    v14 = v13;
  }
  else
  {
    v14 = 0;
    v3 = 0;
  }
  v10 = 0;
  v11 = 0;
  v13 = 0;
  v8 = 0;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 144LL))(v3, &v13);
  winrt::check_hresult(&v12, v5, &v8);
  v6 = winrt::check_pointer<void>(v13, &v10);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v14);
  return v6;
}

```

## disassembly

```asm
0x1800190c8  mov     [rsp-8+arg_18], rbx
0x1800190cd  push    rbp
0x1800190ce  mov     rbp, rsp
0x1800190d1  sub     rsp, 50h
0x1800190d5  xor     ebx, ebx
0x1800190d7  mov     rcx, [rcx]
0x1800190da  test    rcx, rcx
0x1800190dd  jnz     short loc_1800190E7
0x1800190df  mov     [rbp+arg_10], rbx
0x1800190e3  mov     ecx, ebx
0x1800190e5  jmp     short loc_180019123
0x1800190e7  mov     [rbp+arg_8], rbx
0x1800190eb  mov     [rbp+var_30], ebx
0x1800190ee  xorps   xmm0, xmm0
0x1800190f1  movdqu  [rbp+var_28], xmm0
0x1800190f6  mov     rax, [rcx]
0x1800190f9  lea     r8, [rbp+arg_8]
0x1800190fd  lea     rdx, ??$guid_v@UIVisualPrivate@Private@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::Private::IVisualPrivate>
0x180019104  mov     rax, [rax]
0x180019107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001910c  lea     r8, [rbp+var_30]
0x180019110  mov     edx, eax
0x180019112  lea     rcx, [rbp+arg_0]
0x180019116  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001911b  mov     rcx, [rbp+arg_8]
0x18001911f  mov     [rbp+arg_10], rcx
0x180019123  mov     [rbp+var_18], ebx
0x180019126  xorps   xmm0, xmm0
0x180019129  movdqu  [rbp+var_10], xmm0
0x18001912e  mov     [rbp+arg_8], rbx
0x180019132  mov     [rbp+var_30], ebx
0x180019135  movdqu  [rbp+var_28], xmm0
0x18001913a  mov     rax, [rcx]
0x18001913d  lea     rdx, [rbp+arg_8]
0x180019141  mov     rax, [rax+90h]
0x180019148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001914d  lea     r8, [rbp+var_30]
0x180019151  mov     edx, eax
0x180019153  lea     rcx, [rbp+arg_0]
0x180019157  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001915c  lea     rdx, [rbp+var_18]
0x180019160  mov     rcx, [rbp+arg_8]
0x180019164  call    ??$check_pointer@X@winrt@@YAPEAXPEAXAEBUslim_source_location@impl@0@@Z; winrt::check_pointer<void>(void *,winrt::impl::slim_source_location const &)
0x180019169  mov     rbx, rax
0x18001916c  lea     rcx, [rbp+arg_10]
0x180019170  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x180019175  mov     rax, rbx
0x180019178  mov     rbx, [rsp+50h+arg_18]
0x18001917d  add     rsp, 50h
0x180019181  pop     rbp
0x180019182  retn
```
