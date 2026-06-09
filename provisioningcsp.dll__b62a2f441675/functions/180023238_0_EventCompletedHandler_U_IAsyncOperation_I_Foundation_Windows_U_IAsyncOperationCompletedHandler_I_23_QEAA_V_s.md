# ??0?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@QEAA@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z

- ea: `0x180023238`
- end: `0x180023347`
- name: `??0?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@QEAA@V?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@Z`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023680`

## callees

- `0x180023238`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EventCompletedHandler<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>::EventCompletedHandler<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rsi
  __int64 v5; // rbp
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 *v7; // rbx

  *(_QWORD *)a1 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>::`vftable';
  *(_DWORD *)(a1 + 12) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>::`vftable';
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)a1 = &EventCompletedHandler<Windows::Foundation::IAsyncOperation<unsigned int>,Windows::Foundation::IAsyncOperationCompletedHandler<unsigned int>>::`vftable';
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = a2[1];
  v5 = *a2;
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
  v6 = *(volatile signed __int32 **)(a1 + 24);
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  *(_QWORD *)(a1 + 24) = v4;
  *(_QWORD *)(a1 + 16) = v5;
  v7 = (volatile signed __int32 *)a2[1];
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180023238  push    rbx
0x18002323a  push    rbp
0x18002323b  push    rsi
0x18002323c  push    rdi
0x18002323d  push    r14
0x18002323f  push    r15
0x180023241  sub     rsp, 28h
0x180023245  mov     r14, rdx
0x180023248  mov     rdi, rcx
0x18002324b  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVEnrollmentResult@Enrollment@Management@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Management::Enrollment::EnrollmentResult *>::`vftable'
0x180023252  mov     [rcx], rax
0x180023255  mov     dword ptr [rcx+0Ch], 1
0x18002325c  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$IAsyncOperationCompletedHandler@I@Foundation@Windows@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>>::`vftable'
0x180023263  mov     [rcx], rax
0x180023266  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18002326d  test    rcx, rcx
0x180023270  jz      short loc_18002327F
0x180023272  mov     rax, [rcx]
0x180023275  mov     rax, [rax+8]
0x180023279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002327e  nop
0x18002327f  lea     rax, ??_7?$EventCompletedHandler@U?$IAsyncOperation@I@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@I@23@@@6B@; const EventCompletedHandler<Windows::Foundation::IAsyncOperation<uint>,Windows::Foundation::IAsyncOperationCompletedHandler<uint>>::`vftable'
0x180023286  mov     [rdi], rax
0x180023289  mov     qword ptr [rdi+10h], 0
0x180023291  mov     qword ptr [rdi+18h], 0
0x180023299  mov     rsi, [r14+8]
0x18002329d  mov     rbp, [r14]
0x1800232a0  test    rsi, rsi
0x1800232a3  jz      short loc_1800232A9
0x1800232a5  lock inc dword ptr [rsi+8]
0x1800232a9  mov     rbx, [rdi+18h]
0x1800232ad  or      r15d, 0FFFFFFFFh
0x1800232b1  test    rbx, rbx
0x1800232b4  jz      short loc_1800232ED
0x1800232b6  mov     eax, r15d
0x1800232b9  lock xadd [rbx+8], eax
0x1800232be  add     eax, r15d
0x1800232c1  jnz     short loc_1800232ED
0x1800232c3  mov     rax, [rbx]
0x1800232c6  mov     rcx, rbx
0x1800232c9  mov     rax, [rax]
0x1800232cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232d1  mov     eax, r15d
0x1800232d4  lock xadd [rbx+0Ch], eax
0x1800232d9  add     eax, r15d
0x1800232dc  jnz     short loc_1800232ED
0x1800232de  mov     rax, [rbx]
0x1800232e1  mov     rcx, rbx
0x1800232e4  mov     rax, [rax+8]
0x1800232e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800232ed  mov     [rdi+18h], rsi
0x1800232f1  mov     [rdi+10h], rbp
0x1800232f5  mov     rbx, [r14+8]
0x1800232f9  test    rbx, rbx
0x1800232fc  jz      short loc_180023336
0x1800232fe  mov     eax, r15d
0x180023301  lock xadd [rbx+8], eax
0x180023306  add     eax, r15d
0x180023309  jnz     short loc_180023336
0x18002330b  mov     rax, [rbx]
0x18002330e  mov     rcx, rbx
0x180023311  mov     rax, [rax]
0x180023314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023319  mov     eax, r15d
0x18002331c  lock xadd [rbx+0Ch], eax
0x180023321  add     eax, r15d
0x180023324  jnz     short loc_180023336
0x180023326  mov     rax, [rbx]
0x180023329  mov     rcx, rbx
0x18002332c  mov     rax, [rax+8]
0x180023330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023335  nop
0x180023336  mov     rax, rdi
0x180023339  add     rsp, 28h
0x18002333d  pop     r15
0x18002333f  pop     r14
0x180023341  pop     rdi
0x180023342  pop     rsi
0x180023343  pop     rbp
0x180023344  pop     rbx
0x180023345  retn
```
