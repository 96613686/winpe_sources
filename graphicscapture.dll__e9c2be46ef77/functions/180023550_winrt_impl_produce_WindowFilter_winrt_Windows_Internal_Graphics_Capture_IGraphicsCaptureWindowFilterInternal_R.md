# winrt::impl::produce<WindowFilter,winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureWindowFilterInternal>::RemoveWindow(unsigned __int64)

- ea: `0x180023550`
- end: `0x1800235eb`
- name: `?RemoveWindow@?$produce@UWindowFilter@@UIGraphicsCaptureWindowFilterInternal@Capture@Graphics@Internal@Windows@winrt@@@impl@winrt@@UEAAH_K@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003580`
- `0x180007c28`
- `0x1800125ec`
- `0x180022cc4`
- `0x180023550`
- `0x1800241d4`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002356f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002356f`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<WindowFilter,winrt::Windows::Internal::Graphics::Capture::IGraphicsCaptureWindowFilterInternal>::RemoveWindow(
        __int64 a1,
        unsigned int a2)
{
  RTL_SRWLOCK *v3; // rdi
  __int64 v4; // rcx
  unsigned int v5; // eax
  int v7; // [rsp+20h] [rbp-38h] BYREF
  __int128 v8; // [rsp+28h] [rbp-30h]
  int v9; // [rsp+60h] [rbp+8h] BYREF
  __int64 v10; // [rsp+70h] [rbp+18h] BYREF
  RTL_SRWLOCK *v11; // [rsp+78h] [rbp+20h] BYREF

  v3 = (RTL_SRWLOCK *)((a1 - 16) & -(__int64)(a1 != 0));
  AcquireSRWLockExclusive(v3 + 5);
  v11 = v3 + 5;
  WindowFilter::CheckClosed((WindowFilter *)v3);
  v4 = *(_QWORD *)winrt::agile_ref<winrt::Windows::Graphics::Capture::Server::CaptureWindowFilter>::get(&v3[3], &v10);
  v7 = 0;
  v8 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 56LL))(v4, a2);
  winrt::check_hresult(&v9, v5, &v7);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v10);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  return 0;
}

```

## disassembly

```asm
0x180023550  push    rbx
0x180023552  push    rsi
0x180023553  push    rdi
0x180023554  sub     rsp, 40h
0x180023558  mov     rsi, rdx
0x18002355b  lea     rax, [rcx-10h]
0x18002355f  neg     rcx
0x180023562  sbb     rdi, rdi
0x180023565  and     rdi, rax
0x180023568  lea     rbx, [rdi+28h]
0x18002356c  mov     rcx, rbx; SRWLock
0x18002356f  call    cs:__imp_AcquireSRWLockExclusive
0x180023575  mov     [rsp+58h+arg_18], rbx
0x18002357a  mov     rcx, rdi; this
0x18002357d  call    ?CheckClosed@WindowFilter@@AEAAXXZ; WindowFilter::CheckClosed(void)
0x180023582  lea     rcx, [rdi+18h]
0x180023586  lea     rdx, [rsp+58h+arg_10]
0x18002358b  call    ?get@?$agile_ref@UCaptureWindowFilter@Server@Capture@Graphics@Windows@winrt@@@winrt@@QEBA?AUCaptureWindowFilter@Server@Capture@Graphics@Windows@2@XZ; winrt::agile_ref<winrt::Windows::Graphics::Capture::Server::CaptureWindowFilter>::get(void)
0x180023590  nop
0x180023591  mov     rcx, [rax]
0x180023594  mov     [rsp+58h+var_38], 0
0x18002359c  xorps   xmm0, xmm0
0x18002359f  movdqu  [rsp+58h+var_30], xmm0
0x1800235a5  mov     rax, [rcx]
0x1800235a8  mov     edx, esi
0x1800235aa  mov     rax, [rax+38h]
0x1800235ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235b3  lea     r8, [rsp+58h+var_38]
0x1800235b8  mov     edx, eax
0x1800235ba  lea     rcx, [rsp+58h+arg_0]
0x1800235bf  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800235c4  nop
0x1800235c5  lea     rcx, [rsp+58h+arg_10]
0x1800235ca  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1800235cf  nop
0x1800235d0  lea     rcx, [rsp+58h+arg_18]
0x1800235d5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800235da  xor     eax, eax
0x1800235dc  jmp     short loc_1800235E2
0x1800235de  mov     eax, [rsp+58h+arg_0]
0x1800235e2  add     rsp, 40h
0x1800235e6  pop     rdi
0x1800235e7  pop     rsi
0x1800235e8  pop     rbx
0x1800235e9  retn
```
