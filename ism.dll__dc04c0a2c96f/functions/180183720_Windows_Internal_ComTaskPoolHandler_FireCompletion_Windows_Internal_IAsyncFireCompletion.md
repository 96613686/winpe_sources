# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x180183720`
- end: `0x180183872`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `338`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1801801a0`

## callees

- `0x18000dcd4`
- `0x18004f3a0`
- `0x1800f2584`
- `0x18017bc80`
- `0x180183720`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801837b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801837b8`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1801837d3`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x1801837d3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  __int64 v2; // rbx
  unsigned int v3; // ebp
  __int64 *v4; // rax
  __int64 v5; // r14
  DWORD CurrentThreadId; // eax
  int v7; // esi
  bool v8; // si
  struct Windows::Internal::IAsyncFireCompletion *v10; // [rsp+68h] [rbp+10h] BYREF
  __int64 v11; // [rsp+70h] [rbp+18h] BYREF

  v2 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( !*(_BYTE *)(v2 + 36) )
    _dyn_tls_on_demand_init();
  if ( *(int *)(v2 + 320) <= 4 )
    goto LABEL_21;
  v3 = 0;
  v10 = a1;
  wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(&v10);
  v10 = a1;
  wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(&v10);
  v4 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v11,
                    &v10);
  v5 = *v4;
  *v4 = 0;
  if ( v11 )
  {
    v11 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Spatial::SpatialGestureRecognizer *,Windows::UI::Input::Spatial::SpatialNavigationUpdatedEventArgs *>>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v7 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0, v5, 0);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v8 = v7 >= 0;
  if ( v10 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( !v8 )
  {
LABEL_21:
    if ( !*(_BYTE *)(v2 + 36) )
      _dyn_tls_on_demand_init();
    ++*(_DWORD *)(v2 + 320);
    v3 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 24LL))(a1);
    if ( !*(_BYTE *)(v2 + 36) )
      _dyn_tls_on_demand_init();
    --*(_DWORD *)(v2 + 320);
  }
  return v3;
}

```

## disassembly

```asm
0x180183720  mov     [rsp+arg_0], rbx
0x180183725  mov     [rsp+arg_18], rbp
0x18018372a  push    rsi
0x18018372b  push    rdi
0x18018372c  push    r12
0x18018372e  push    r13
0x180183730  push    r14
0x180183732  sub     rsp, 30h
0x180183736  mov     rdi, rcx
0x180183739  mov     edx, cs:_tls_index
0x18018373f  mov     rax, gs:58h
0x180183748  mov     rbx, [rax+rdx*8]
0x18018374c  mov     r13d, 24h ; '$'
0x180183752  cmp     byte ptr [rbx+r13], 0
0x180183757  jnz     short loc_18018375E
0x180183759  call    __dyn_tls_on_demand_init
0x18018375e  mov     r12d, 140h
0x180183764  cmp     dword ptr [r12+rbx], 4
0x180183769  jle     loc_180183828
0x18018376f  xor     ebp, ebp
0x180183771  mov     [rsp+58h+arg_8], rdi
0x180183776  lea     rcx, [rsp+58h+arg_8]
0x18018377b  call    ??1?$com_ptr_t@VAsyncHRESULTPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(void)
0x180183780  mov     [rsp+58h+arg_8], rdi
0x180183785  lea     rcx, [rsp+58h+arg_8]
0x18018378a  call    ??1?$com_ptr_t@VAsyncHRESULTPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>::~com_ptr_t<AsyncHRESULTPrincipal,wil::err_exception_policy>(void)
0x18018378f  lea     rdx, [rsp+58h+arg_8]
0x180183794  lea     rcx, [rsp+58h+arg_10]
0x180183799  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18018379e  mov     r14, [rax]
0x1801837a1  mov     [rax], rbp
0x1801837a4  mov     rcx, [rsp+58h+arg_10]
0x1801837a9  test    rcx, rcx
0x1801837ac  jz      short loc_1801837B8
0x1801837ae  mov     [rsp+58h+arg_10], rbp
0x1801837b3  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$ITypedEventHandler@PEAVSpatialGestureRecognizer@Spatial@Input@UI@Windows@@PEAVSpatialNavigationUpdatedEventArgs@2345@@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::ITypedEventHandler<Windows::UI::Input::Spatial::SpatialGestureRecognizer *,Windows::UI::Input::Spatial::SpatialNavigationUpdatedEventArgs *>>::Release(void)
0x1801837b8  call    cs:__imp_GetCurrentThreadId
0x1801837be  mov     [rsp+58h+var_30], rbp
0x1801837c3  mov     [rsp+58h+var_38], r14
0x1801837c8  xor     r9d, r9d
0x1801837cb  mov     r8d, eax
0x1801837ce  xor     edx, edx
0x1801837d0  lea     ecx, [rdx+3]
0x1801837d3  call    cs:__imp_SHTaskPoolQueueTask
0x1801837d9  mov     esi, eax
0x1801837db  test    r14, r14
0x1801837de  jz      short loc_1801837F0
0x1801837e0  mov     rax, [r14]
0x1801837e3  mov     rcx, r14
0x1801837e6  mov     rax, [rax+10h]
0x1801837ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801837ef  nop
0x1801837f0  shr     esi, 1Fh
0x1801837f3  xor     sil, 1
0x1801837f7  mov     rcx, [rsp+58h+arg_8]
0x1801837fc  test    rcx, rcx
0x1801837ff  jz      short loc_18018380E
0x180183801  mov     rax, [rcx]
0x180183804  mov     rax, [rax+10h]
0x180183808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18018380d  nop
0x18018380e  test    rdi, rdi
0x180183811  jz      short loc_180183823
0x180183813  mov     rax, [rdi]
0x180183816  mov     rcx, rdi
0x180183819  mov     rax, [rax+10h]
0x18018381d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183822  nop
0x180183823  test    sil, sil
0x180183826  jnz     short loc_180183859
0x180183828  cmp     byte ptr [rbx+r13], 0
0x18018382d  jnz     short loc_180183834
0x18018382f  call    __dyn_tls_on_demand_init
0x180183834  inc     dword ptr [r12+rbx]
0x180183838  mov     rax, [rdi]
0x18018383b  mov     rcx, rdi
0x18018383e  mov     rax, [rax+18h]
0x180183842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180183847  mov     ebp, eax
0x180183849  cmp     byte ptr [rbx+r13], 0
0x18018384e  jnz     short loc_180183855
0x180183850  call    __dyn_tls_on_demand_init
0x180183855  dec     dword ptr [r12+rbx]
0x180183859  mov     eax, ebp
0x18018385b  mov     rbx, [rsp+58h+arg_0]
0x180183860  mov     rbp, [rsp+58h+arg_18]
0x180183865  add     rsp, 30h
0x180183869  pop     r14
0x18018386b  pop     r13
0x18018386d  pop     r12
0x18018386f  pop     rdi
0x180183870  pop     rsi
0x180183871  retn
```
