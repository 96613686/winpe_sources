# std::_Func_impl_no_alloc__LPA::CoreLpa::CreateAndStartHelpers_::_25_::_lambda_1__void_::_Do_call

- ea: `0x180073cb0`
- end: `0x180073cfd`
- name: `std::_Func_impl_no_alloc__LPA::CoreLpa::CreateAndStartHelpers_::_25_::_lambda_1__void_::_Do_call`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180073cb0`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073cec`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180073cec`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180073ccb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180073ccb`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__LPA::CoreLpa::CreateAndStartHelpers_::_25_::_lambda_1__void_::_Do_call(
        __int64 a1)
{
  struct _TP_WORK *ThreadpoolWork; // rdi

  ThreadpoolWork = CreateThreadpoolWork(LPA::CoreLpa::PerformReset, *(PVOID *)(a1 + 8), 0);
  if ( ThreadpoolWork )
  {
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 8) + 8LL))(*(_QWORD *)(a1 + 8));
    SubmitThreadpoolWork(ThreadpoolWork);
  }
}

```

## disassembly

```asm
0x180073cb0  mov     [rsp+arg_0], rbx
0x180073cb5  push    rdi
0x180073cb6  sub     rsp, 20h
0x180073cba  mov     rdx, [rcx+8]; pv
0x180073cbe  mov     rbx, rcx
0x180073cc1  lea     rcx, ?PerformReset@CoreLpa@LPA@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180073cc8  xor     r8d, r8d; pcbe
0x180073ccb  call    cs:__imp_CreateThreadpoolWork
0x180073cd1  mov     rdi, rax
0x180073cd4  test    rax, rax
0x180073cd7  jz      short loc_180073CF2
0x180073cd9  mov     rcx, [rbx+8]
0x180073cdd  mov     rdx, [rcx]
0x180073ce0  mov     rax, [rdx+8]
0x180073ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ce9  mov     rcx, rdi; pwk
0x180073cec  call    cs:__imp_SubmitThreadpoolWork
0x180073cf2  mov     rbx, [rsp+28h+arg_0]
0x180073cf7  add     rsp, 20h
0x180073cfb  pop     rdi
0x180073cfc  retn
```
