# Windows::UI::Composition::Internal::SharedD3DDevicePool::ValidateClient(IUnknown *)

- ea: `0x1800cfbec`
- end: `0x1800cfd0d`
- name: `?ValidateClient@SharedD3DDevicePool@Internal@Composition@UI@Windows@@QEAAJPEAUIUnknown@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(Windows::UI::Composition::Internal::SharedD3DDevicePool *__hidden this, struct IUnknown *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cfbb0`

## callees

- `0x18003f1d8`
- `0x18003f9d4`
- `0x1800cfbec`
- `0x1800e79a8`
- `0x180148028`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cfc14`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cfc14`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cfc43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cfc84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cfc43`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800cfc84`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800cfceb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800cfceb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800cfd05`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800cfd05`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::Internal::SharedD3DDevicePool::ValidateClient(
        RTL_SRWLOCK *this,
        struct IUnknown *a2)
{
  RTL_SRWLOCK *v2; // rbx
  struct ID3D11Device *lpVtbl; // rdi
  int v6; // esi
  __int64 v8; // rcx
  struct IUnknownVtbl *v9; // rdx
  struct _TP_WORK *ThreadpoolWork; // rax
  PVOID *p_pv; // [rsp+20h] [rbp-20h] BYREF
  struct Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice *v12; // [rsp+28h] [rbp-18h] BYREF
  char v13; // [rsp+30h] [rbp-10h]
  PVOID pv; // [rsp+70h] [rbp+30h] BYREF
  struct _TP_WORK *v15; // [rsp+78h] [rbp+38h] BYREF

  v2 = this + 8;
  pv = 0;
  AcquireSRWLockExclusive(this + 8);
  lpVtbl = (struct ID3D11Device *)a2[2].lpVtbl;
  if ( lpVtbl )
  {
    v6 = ((__int64 (__fastcall *)(struct IUnknownVtbl *))lpVtbl->lpVtbl->GetDeviceRemovedReason)(a2[2].lpVtbl);
    if ( v6 < 0 )
    {
      v9 = a2[3].lpVtbl;
      p_pv = &pv;
      v12 = 0;
      v13 = 1;
      Windows::UI::Composition::Internal::SharedD3DDevicePool::EraseSharedDevice(
        (Windows::UI::Composition::Internal::SharedD3DDevicePool *)this,
        (struct _LUID)v9,
        lpVtbl,
        &v12);
      wil::details::out_param_t<std::unique_ptr<Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice>>::~out_param_t<std::unique_ptr<Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice>>(&p_pv);
    }
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    if ( pv )
    {
      ThreadpoolWork = CreateThreadpoolWork(
                         Windows::UI::Composition::Internal::SharedD3DDevicePool::ValidateClient_::_12_::_lambda_1_::_lambda_invoker_cdecl_,
                         pv,
                         0);
      v15 = ThreadpoolWork;
      if ( ThreadpoolWork )
      {
        pv = 0;
        SubmitThreadpoolWork(ThreadpoolWork);
      }
      wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&v15);
      if ( pv )
        std::default_delete<Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice>::operator()(v8);
    }
    return (unsigned int)v6;
  }
  else
  {
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    if ( pv )
      ((void (*)(void))std::default_delete<Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice>::operator())();
    return 2289696773LL;
  }
}

```

## disassembly

```asm
0x1800cfbec  mov     [rsp-28h+arg_10], rbx
0x1800cfbf1  push    rbp
0x1800cfbf2  push    rsi
0x1800cfbf3  push    rdi
0x1800cfbf4  push    r14
0x1800cfbf6  push    r15
0x1800cfbf8  mov     rbp, rsp
0x1800cfbfb  sub     rsp, 40h
0x1800cfbff  lea     rbx, [rcx+40h]
0x1800cfc03  mov     [rbp+pv], 0
0x1800cfc0b  mov     r15, rcx
0x1800cfc0e  mov     r14, rdx
0x1800cfc11  mov     rcx, rbx; SRWLock
0x1800cfc14  call    cs:__imp_AcquireSRWLockExclusive
0x1800cfc1a  mov     rdi, [r14+10h]
0x1800cfc1e  test    rdi, rdi
0x1800cfc21  jz      short loc_1800CFC6C
0x1800cfc23  mov     rax, [rdi]
0x1800cfc26  mov     rcx, rdi
0x1800cfc29  mov     rax, [rax+138h]
0x1800cfc30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cfc35  mov     esi, eax
0x1800cfc37  test    eax, eax
0x1800cfc39  js      short loc_1800CFCAC
0x1800cfc3b  test    rbx, rbx
0x1800cfc3e  jz      short loc_1800CFC49
0x1800cfc40  mov     rcx, rbx; SRWLock
0x1800cfc43  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cfc49  mov     rdx, [rbp+pv]; pv
0x1800cfc4d  test    rdx, rdx
0x1800cfc50  jnz     loc_1800CFCE1
0x1800cfc56  mov     eax, esi
0x1800cfc58  mov     rbx, [rsp+40h+arg_10]
0x1800cfc60  add     rsp, 40h
0x1800cfc64  pop     r15
0x1800cfc66  pop     r14
0x1800cfc68  pop     rdi
0x1800cfc69  pop     rsi
0x1800cfc6a  pop     rbp
0x1800cfc6b  retn
0x1800cfc6c  test    rbx, rbx
0x1800cfc6f  jnz     short loc_1800CFC81
0x1800cfc71  mov     rdx, [rbp+pv]
0x1800cfc75  test    rdx, rdx
0x1800cfc78  jnz     short loc_1800CFC8C
0x1800cfc7a  mov     eax, 887A0005h
0x1800cfc7f  jmp     short loc_1800CFC58
0x1800cfc81  mov     rcx, rbx; SRWLock
0x1800cfc84  call    cs:__imp_ReleaseSRWLockExclusive
0x1800cfc8a  jmp     short loc_1800CFC71
0x1800cfc8c  call    ??R?$default_delete@USharedDevice@SharedD3DDevicePool@Internal@Composition@UI@Windows@@@std@@QEBAXPEAUSharedDevice@SharedD3DDevicePool@Internal@Composition@UI@Windows@@@Z; std::default_delete<Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice>::operator()(Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice *)
0x1800cfc91  jmp     short loc_1800CFC7A
0x1800cfc93  lea     rcx, [rbp+arg_8]
0x1800cfc97  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x1800cfc9c  mov     rdx, [rbp+pv]
0x1800cfca0  test    rdx, rdx
0x1800cfca3  jz      short loc_1800CFC56
0x1800cfca5  call    ??R?$default_delete@USharedDevice@SharedD3DDevicePool@Internal@Composition@UI@Windows@@@std@@QEBAXPEAUSharedDevice@SharedD3DDevicePool@Internal@Composition@UI@Windows@@@Z; std::default_delete<Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice>::operator()(Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice *)
0x1800cfcaa  jmp     short loc_1800CFC56
0x1800cfcac  mov     rdx, [r14+18h]; struct _LUID
0x1800cfcb0  lea     rax, [rbp+pv]
0x1800cfcb4  lea     r9, [rbp+var_18]; struct Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice **
0x1800cfcb8  mov     [rbp+var_20], rax
0x1800cfcbc  mov     r8, rdi; struct ID3D11Device *
0x1800cfcbf  mov     [rbp+var_18], 0
0x1800cfcc7  mov     rcx, r15; this
0x1800cfcca  mov     [rbp+var_10], 1
0x1800cfcce  call    ?EraseSharedDevice@SharedD3DDevicePool@Internal@Composition@UI@Windows@@AEAAXU_LUID@@PEAUID3D11Device@@PEAPEAUSharedDevice@12345@@Z; Windows::UI::Composition::Internal::SharedD3DDevicePool::EraseSharedDevice(_LUID,ID3D11Device *,Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice * *)
0x1800cfcd3  lea     rcx, [rbp+var_20]
0x1800cfcd7  call    ??1?$out_param_t@V?$unique_ptr@USharedDevice@SharedD3DDevicePool@Internal@Composition@UI@Windows@@U?$default_delete@USharedDevice@SharedD3DDevicePool@Internal@Composition@UI@Windows@@@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice>>::~out_param_t<std::unique_ptr<Windows::UI::Composition::Internal::SharedD3DDevicePool::SharedDevice>>(void)
0x1800cfcdc  jmp     loc_1800CFC3B
0x1800cfce1  xor     r8d, r8d; pcbe
0x1800cfce4  lea     rcx, _Windows__UI__Composition__Internal__SharedD3DDevicePool__ValidateClient____12____lambda_1____lambda_invoker_cdecl_; pfnwk
0x1800cfceb  call    cs:__imp_CreateThreadpoolWork
0x1800cfcf1  mov     [rbp+arg_8], rax
0x1800cfcf5  test    rax, rax
0x1800cfcf8  jz      short loc_1800CFC93
0x1800cfcfa  mov     rcx, rax; pwk
0x1800cfcfd  mov     [rbp+pv], 0
0x1800cfd05  call    cs:__imp_SubmitThreadpoolWork
0x1800cfd0b  jmp     short loc_1800CFC93
```
