# Windows::Internal::ComTaskPool::QueueTask<_lambda_cc75c53f368e9cb9cafefcafe4f7344e_>(Windows::Internal::TaskApartment,_lambda_cc75c53f368e9cb9cafefcafe4f7344e_ &&)

- ea: `0x18001abcc`
- end: `0x18001ac60`
- name: `??$QueueTask@V_lambda_cc75c53f368e9cb9cafefcafe4f7344e_@@@ComTaskPool@Internal@Windows@@SAJW4TaskApartment@12@$$QEAV_lambda_cc75c53f368e9cb9cafefcafe4f7344e_@@@Z`
- size: `148`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a7c8`

## callees

- `0x18001abcc`
- `0x18001ac68`
- `0x18002ccfc`
- `0x180034094`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ac17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ac17`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001ac36`
- `api-ms-win-shcore-taskpool-l1-1-0!SHTaskPoolQueueTask` at `0x18001ac36`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::ComTaskPool::QueueTask<_lambda_cc75c53f368e9cb9cafefcafe4f7344e_>(
        __int64 a1,
        __int64 a2)
{
  void *v3; // rax
  __int64 v4; // rbx
  DWORD CurrentThreadId; // eax
  unsigned int v6; // edi
  void *v8; // [rsp+50h] [rbp+18h] BYREF

  v3 = operator new(0x178u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v3;
  v4 = 0;
  if ( v3 )
  {
    v4 = Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_cc75c53f368e9cb9cafefcafe4f7344e_>::CTaskWrapper<_lambda_cc75c53f368e9cb9cafefcafe4f7344e_>(
           v3,
           a2);
    v8 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(&v8);
  CurrentThreadId = GetCurrentThreadId();
  v6 = SHTaskPoolQueueTask(3, 0, CurrentThreadId, 0);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  return v6;
}

```

## disassembly

```asm
0x18001abcc  mov     [rsp+arg_0], rbx
0x18001abd1  push    rdi
0x18001abd2  sub     rsp, 30h
0x18001abd6  mov     rdi, rdx
0x18001abd9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001abe0  mov     ecx, 178h; unsigned __int64
0x18001abe5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001abea  mov     [rsp+38h+arg_10], rax
0x18001abef  xor     ebx, ebx
0x18001abf1  test    rax, rax
0x18001abf4  jz      short loc_18001AC0D
0x18001abf6  mov     rdx, rdi
0x18001abf9  mov     rcx, rax
0x18001abfc  call    ??$?0V_lambda_cc75c53f368e9cb9cafefcafe4f7344e_@@@?$CTaskWrapper@V_lambda_cc75c53f368e9cb9cafefcafe4f7344e_@@@ComTaskPool@Internal@Windows@@QEAA@$$QEAV_lambda_cc75c53f368e9cb9cafefcafe4f7344e_@@@Z; Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_cc75c53f368e9cb9cafefcafe4f7344e_>::CTaskWrapper<_lambda_cc75c53f368e9cb9cafefcafe4f7344e_>(_lambda_cc75c53f368e9cb9cafefcafe4f7344e_ &&)
0x18001ac01  mov     rbx, rax
0x18001ac04  mov     [rsp+38h+arg_10], 0
0x18001ac0d  lea     rcx, [rsp+38h+arg_10]
0x18001ac12  call    ??1?$MakeAllocator@VWeakReferenceImpl@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>::~MakeAllocator<Microsoft::WRL::Details::WeakReferenceImpl>(void)
0x18001ac17  call    cs:__imp_GetCurrentThreadId
0x18001ac1d  mov     [rsp+38h+var_10], 0
0x18001ac26  mov     [rsp+38h+var_18], rbx
0x18001ac2b  xor     r9d, r9d
0x18001ac2e  mov     r8d, eax
0x18001ac31  xor     edx, edx
0x18001ac33  lea     ecx, [rdx+3]
0x18001ac36  call    cs:__imp_SHTaskPoolQueueTask
0x18001ac3c  mov     edi, eax
0x18001ac3e  test    rbx, rbx
0x18001ac41  jz      short loc_18001AC53
0x18001ac43  mov     rdx, [rbx]
0x18001ac46  mov     rcx, rbx
0x18001ac49  mov     rax, [rdx+10h]
0x18001ac4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac52  nop
0x18001ac53  mov     eax, edi
0x18001ac55  mov     rbx, [rsp+38h+arg_0]
0x18001ac5a  add     rsp, 30h
0x18001ac5e  pop     rdi
0x18001ac5f  retn
```
