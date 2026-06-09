# Microsoft::WRL::Details::Make<CRemoteReleaseStub,Windows::Internal::IComPoolTask * &>(Windows::Internal::IComPoolTask * &)

- ea: `0x18000f668`
- end: `0x18000f739`
- name: `??$Make@VCRemoteReleaseStub@@AEAPEAUIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCRemoteReleaseStub@@@12@AEAPEAUIComPoolTask@Internal@Windows@@@Z`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032428`

## callees

- `0x1800092c0`
- `0x180009de0`
- `0x18000a330`
- `0x18000f1f4`
- `0x18000f668`
- `0x180011954`
- `0x180035010`

## import_xrefs

- `api-ms-win-shcore-thread-l1-1-0!SHGetThreadRef` at `0x18000f6b9`
- `api-ms-win-shcore-thread-l1-1-0!SHGetThreadRef` at `0x18000f6b9`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::Make<CRemoteReleaseStub,Windows::Internal::IComPoolTask * &>(
        _QWORD *a1,
        __int64 *a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // r14
  _QWORD *v7; // [rsp+50h] [rbp+8h] BYREF

  *a1 = 0;
  v7 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v7;
  if ( v7 )
  {
    v5 = *a2;
    *v7 = &CThreadRefTaker::`vftable';
    v4[1] = 0;
    SHGetThreadRef((IUnknown **)v4 + 1);
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>(v4 + 2);
    *v4 = &CRemoteReleaseStub::`vftable'{for `CThreadRefTaker'};
    v4[2] = &CRemoteReleaseStub::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>'};
    GetModuleForObject((HMODULE *)v4 + 4);
    v4[5] = v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    *((_BYTE *)v4 + 48) = 0;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(*a1 + 16LL);
    *a1 = v4;
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(&v7);
  return a1;
}

```

## disassembly

```asm
0x18000f668  push    rbx
0x18000f66a  push    rsi
0x18000f66b  push    rdi
0x18000f66c  push    r14
0x18000f66e  sub     rsp, 28h
0x18000f672  mov     r14, rdx
0x18000f675  mov     qword ptr [rcx], 0
0x18000f67c  mov     rsi, rcx
0x18000f67f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f686  mov     ecx, 38h ; '8'; unsigned __int64
0x18000f68b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f690  mov     [rsp+48h+arg_0], rax
0x18000f695  mov     rdi, rax
0x18000f698  test    rax, rax
0x18000f69b  jz      loc_18000F722
0x18000f6a1  mov     r14, [r14]
0x18000f6a4  lea     rax, ??_7CThreadRefTaker@@6B@; const CThreadRefTaker::`vftable'
0x18000f6ab  lea     rcx, [rdi+8]; ppunk
0x18000f6af  mov     [rdi], rax
0x18000f6b2  mov     qword ptr [rcx], 0
0x18000f6b9  call    cs:__imp_SHGetThreadRef
0x18000f6bf  lea     rcx, [rdi+10h]
0x18000f6c3  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>(void)
0x18000f6c8  lea     rax, ??_7CRemoteReleaseStub@@6BCThreadRefTaker@@@; const CRemoteReleaseStub::`vftable'{for `CThreadRefTaker'}
0x18000f6cf  mov     rdx, r14
0x18000f6d2  mov     [rdi], rax
0x18000f6d5  lea     rcx, [rdi+20h]; phModule
0x18000f6d9  lea     rax, ??_7CRemoteReleaseStub@@6B?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@@; const CRemoteReleaseStub::`vftable'{for `Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>'}
0x18000f6e0  mov     [rdi+10h], rax
0x18000f6e4  call    ?GetModuleForObject@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUIUnknown@@@Z; GetModuleForObject(IUnknown *)
0x18000f6e9  mov     [rdi+28h], r14
0x18000f6ed  test    r14, r14
0x18000f6f0  jz      short loc_18000F701
0x18000f6f2  mov     rax, [r14]
0x18000f6f5  mov     rcx, r14
0x18000f6f8  mov     rax, [rax+8]
0x18000f6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f701  mov     byte ptr [rdi+30h], 0
0x18000f705  mov     rcx, [rsi]
0x18000f708  test    rcx, rcx
0x18000f70b  jz      short loc_18000F716
0x18000f70d  add     rcx, 10h
0x18000f711  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18000f716  mov     [rsi], rdi
0x18000f719  mov     [rsp+48h+arg_0], 0
0x18000f722  lea     rcx, [rsp+48h+arg_0]
0x18000f727  call    ??1?$MakeAllocator@VCThumbnailRequest@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<CThumbnailRequest>::~MakeAllocator<CThumbnailRequest>(void)
0x18000f72c  mov     rax, rsi
0x18000f72f  add     rsp, 28h
0x18000f733  pop     r14
0x18000f735  pop     rdi
0x18000f736  pop     rsi
0x18000f737  pop     rbx
0x18000f738  retn
```
