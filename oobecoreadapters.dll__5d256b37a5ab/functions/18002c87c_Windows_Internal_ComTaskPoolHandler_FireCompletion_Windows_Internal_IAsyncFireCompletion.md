# Windows::Internal::ComTaskPoolHandler::_FireCompletion(Windows::Internal::IAsyncFireCompletion *)

- ea: `0x18002c87c`
- end: `0x18002c97c`
- name: `?_FireCompletion@ComTaskPoolHandler@Internal@Windows@@SAJPEAUIAsyncFireCompletion@23@@Z`
- size: `256`
- prototype: `__int64 __fastcall(struct Windows::Internal::IAsyncFireCompletion *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180027730`

## callees

- `0x18000aa20`
- `0x18001f250`
- `0x180026c60`
- `0x1800283a0`
- `0x1800290c0`
- `0x180029224`
- `0x18002c87c`
- `0x18006e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c8e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c8e2`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002c8fd`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18002c8fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPoolHandler::_FireCompletion(
        struct Windows::Internal::IAsyncFireCompletion *a1)
{
  unsigned int v2; // ebp
  __int64 *v3; // rax
  __int64 v4; // rsi
  DWORD CurrentThreadId; // eax
  int v6; // edi
  bool v7; // di
  struct Windows::Internal::IAsyncFireCompletion *v9; // [rsp+58h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+18h] BYREF

  if ( (int)Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth() <= 4 )
    goto LABEL_11;
  v2 = 0;
  v9 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
  v9 = a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(&v9);
  v3 = (__int64 *)Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(
                    &v10,
                    &v9);
  v4 = *v3;
  *v3 = 0;
  if ( v10 )
  {
    v10 = 0;
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release();
  }
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v7 = v6 >= 0;
  if ( v9 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( a1 )
    (*(void (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 16LL))(a1);
  if ( !v7 )
  {
LABEL_11:
    Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth();
    v2 = (*(__int64 (__fastcall **)(struct Windows::Internal::IAsyncFireCompletion *))(*(_QWORD *)a1 + 24LL))(a1);
    Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth();
  }
  return v2;
}

```

## disassembly

```asm
0x18002c87c  mov     [rsp+arg_0], rbx
0x18002c881  push    rbp
0x18002c882  push    rsi
0x18002c883  push    rdi
0x18002c884  sub     rsp, 30h
0x18002c888  mov     rbx, rcx
0x18002c88b  call    ?GetCurrentThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAJXZ; Windows::Internal::ComTaskPool::GetCurrentThreadRecursionDepth(void)
0x18002c890  cmp     eax, 4
0x18002c893  jle     loc_18002C952
0x18002c899  xor     ebp, ebp
0x18002c89b  mov     [rsp+48h+arg_8], rbx
0x18002c8a0  lea     rcx, [rsp+48h+arg_8]
0x18002c8a5  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002c8aa  mov     [rsp+48h+arg_8], rbx
0x18002c8af  lea     rcx, [rsp+48h+arg_8]
0x18002c8b4  call    ?InternalAddRef@?$ComPtr@UIAsyncActionCompletedHandler@Foundation@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncActionCompletedHandler>::InternalAddRef(void)
0x18002c8b9  lea     rdx, [rsp+48h+arg_8]
0x18002c8be  lea     rcx, [rsp+48h+arg_10]
0x18002c8c3  call    ??$Make@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@12@$$QEAV_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@Z; Microsoft::WRL::Details::Make<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>,_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>(_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_ &&)
0x18002c8c8  mov     rsi, [rax]
0x18002c8cb  mov     [rax], rbp
0x18002c8ce  mov     rcx, [rsp+48h+arg_10]
0x18002c8d3  test    rcx, rcx
0x18002c8d6  jz      short loc_18002C8E2
0x18002c8d8  mov     [rsp+48h+arg_10], rbp
0x18002c8dd  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)
0x18002c8e2  call    cs:__imp_GetCurrentThreadId
0x18002c8e8  mov     [rsp+48h+var_20], rbp
0x18002c8ed  mov     [rsp+48h+var_28], rsi
0x18002c8f2  xor     r9d, r9d
0x18002c8f5  mov     r8d, eax
0x18002c8f8  xor     edx, edx
0x18002c8fa  lea     ecx, [rdx+3]
0x18002c8fd  call    cs:__imp_SHTaskPoolQueueTask
0x18002c903  mov     edi, eax
0x18002c905  test    rsi, rsi
0x18002c908  jz      short loc_18002C91A
0x18002c90a  mov     rdx, [rsi]
0x18002c90d  mov     rcx, rsi
0x18002c910  mov     rax, [rdx+10h]
0x18002c914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c919  nop
0x18002c91a  shr     edi, 1Fh
0x18002c91d  xor     dil, 1
0x18002c921  mov     rcx, [rsp+48h+arg_8]
0x18002c926  test    rcx, rcx
0x18002c929  jz      short loc_18002C938
0x18002c92b  mov     rax, [rcx]
0x18002c92e  mov     rax, [rax+10h]
0x18002c932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c937  nop
0x18002c938  test    rbx, rbx
0x18002c93b  jz      short loc_18002C94D
0x18002c93d  mov     rax, [rbx]
0x18002c940  mov     rcx, rbx
0x18002c943  mov     rax, [rax+10h]
0x18002c947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c94c  nop
0x18002c94d  test    dil, dil
0x18002c950  jnz     short loc_18002C96D
0x18002c952  call    ?IncrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::IncrementThreadRecursionDepth(void)
0x18002c957  mov     rax, [rbx]
0x18002c95a  mov     rcx, rbx
0x18002c95d  mov     rax, [rax+18h]
0x18002c961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c966  mov     ebp, eax
0x18002c968  call    ?DecrementThreadRecursionDepth@ComTaskPool@Internal@Windows@@SAXXZ; Windows::Internal::ComTaskPool::DecrementThreadRecursionDepth(void)
0x18002c96d  mov     eax, ebp
0x18002c96f  mov     rbx, [rsp+48h+arg_0]
0x18002c974  add     rsp, 30h
0x18002c978  pop     rdi
0x18002c979  pop     rsi
0x18002c97a  pop     rbp
0x18002c97b  retn
```
