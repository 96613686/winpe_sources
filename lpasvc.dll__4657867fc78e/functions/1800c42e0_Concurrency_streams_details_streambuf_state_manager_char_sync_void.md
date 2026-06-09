# Concurrency::streams::details::streambuf_state_manager<char>::sync(void)

- ea: `0x1800c42e0`
- end: `0x1800c43e8`
- name: `?sync@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@XZ`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callees

- `0x180061c50`
- `0x1800a1ef0`
- `0x1800a31c4`
- `0x1800a3454`
- `0x1800a3d34`
- `0x1800a68e0`
- `0x1800a8c18`
- `0x1800c42e0`
- `0x180101010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c4336`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c4336`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800c4311`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800c4311`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::sync(__int64 a1, __int64 a2)
{
  const void *v4; // rsi
  __int64 v5; // rbx
  __int64 v6; // rax
  int v7; // eax
  __int64 exception_checked; // rax
  __int128 v10; // [rsp+30h] [rbp-39h] BYREF
  _BYTE v11[16]; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v12[13]; // [rsp+58h] [rbp-11h] BYREF
  _QWORD *v13; // [rsp+D0h] [rbp+67h] BYREF

  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) )
  {
    v13 = v12;
    v12[0] = ___7___Func_impl_no_alloc_V_lambda_1___1__sync___streambuf_state_manager_D_details_streams_Concurrency__UEAA_AV__task_X_pplx__XZ__N_N_std__6B_;
    v12[7] = v12;
    v7 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 352LL))(a1, &v10);
    exception_checked = Concurrency::streams::details::streambuf_state_manager<char>::create_exception_checked_task<bool>(
                          a1,
                          (unsigned int)v11,
                          v7,
                          (unsigned int)v12,
                          3);
    ___then_V_lambda_2___1__sync___streambuf_state_manager_D_details_streams_Concurrency__UEAA_AV__task_X_pplx__XZ____task__N_pplx__QEBA_AV__task_X_1___QEAV_lambda_2___1__sync___streambuf_state_manager_D_details_streams_Concurrency__UEAA_AV21_XZ__Z(
      exception_checked,
      a2,
      &v13);
    std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(v11);
  }
  else
  {
    v4 = (const void *)(a1 + 24);
    if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
    {
      v5 = pplx::task_options::task_options((pplx::task_options *)v12);
      v10 = 0;
      __ExceptionPtrCopy(&v10, v4);
      pplx::task_from_exception<void,std::exception_ptr>(a2, &v10, v5);
    }
    else
    {
      v6 = pplx::task_options::task_options((pplx::task_options *)v12);
      pplx::task_from_result<void>(a2, v6);
    }
    pplx::task_options::~task_options((pplx::task_options *)v12);
  }
  return a2;
}

```

## disassembly

```asm
0x1800c42e0  mov     [rsp-8+arg_8], rbx
0x1800c42e5  push    rbp
0x1800c42e6  push    rsi
0x1800c42e7  push    rdi
0x1800c42e8  lea     rbp, [rsp-47h]
0x1800c42ed  sub     rsp, 0B0h
0x1800c42f4  mov     rdi, rdx
0x1800c42f7  mov     rbx, rcx
0x1800c42fa  mov     rax, [rcx]
0x1800c42fd  mov     rax, [rax+10h]
0x1800c4301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4306  test    al, al
0x1800c4308  jnz     short loc_1800C436B
0x1800c430a  lea     rsi, [rbx+18h]
0x1800c430e  mov     rcx, rsi
0x1800c4311  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800c4317  lea     rcx, [rbp+57h+var_68]; this
0x1800c431b  test    al, al
0x1800c431d  jz      short loc_1800C4357
0x1800c431f  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x1800c4324  mov     rbx, rax
0x1800c4327  xorps   xmm0, xmm0
0x1800c432a  movdqu  [rbp+57h+var_90], xmm0
0x1800c432f  mov     rdx, rsi
0x1800c4332  lea     rcx, [rbp+57h+var_90]
0x1800c4336  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800c433c  mov     r8, rbx
0x1800c433f  lea     rdx, [rbp+57h+var_90]
0x1800c4343  mov     rcx, rdi
0x1800c4346  call    ??$task_from_exception@XVexception_ptr@std@@@pplx@@YA?AV?$task@X@0@Vexception_ptr@std@@AEBVtask_options@0@@Z; pplx::task_from_exception<void,std::exception_ptr>(std::exception_ptr,pplx::task_options const &)
0x1800c434b  nop
0x1800c434c  lea     rcx, [rbp+57h+var_68]; this
0x1800c4350  call    ??1task_options@pplx@@QEAA@XZ; pplx::task_options::~task_options(void)
0x1800c4355  jmp     short loc_1800C43D2
0x1800c4357  call    ??0task_options@pplx@@QEAA@XZ; pplx::task_options::task_options(void)
0x1800c435c  nop
0x1800c435d  mov     rdx, rax
0x1800c4360  mov     rcx, rdi
0x1800c4363  call    ??$task_from_result@X@pplx@@YA?AV?$task@X@0@AEBVtask_options@0@@Z; pplx::task_from_result<void>(pplx::task_options const &)
0x1800c4368  nop
0x1800c4369  jmp     short loc_1800C434C
0x1800c436b  lea     rax, [rbp+57h+var_68]
0x1800c436f  mov     [rbp+57h+arg_0], rax
0x1800c4373  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1??sync@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@XZ@_N_N@std@@6B@; const std::_Func_impl_no_alloc<`Concurrency::streams::details::streambuf_state_manager<char>::sync(void)'::`2'::_lambda_1_,bool,bool>::`vftable'
0x1800c437a  mov     [rbp+57h+var_68], rax
0x1800c437e  lea     rax, [rbp+57h+var_68]
0x1800c4382  mov     [rbp+57h+var_30], rax
0x1800c4386  mov     rax, [rbx]
0x1800c4389  lea     rdx, [rbp+57h+var_90]
0x1800c438d  mov     rcx, rbx
0x1800c4390  mov     rax, [rax+160h]
0x1800c4397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c439c  nop
0x1800c439d  mov     [rsp+0C0h+var_A0], 3
0x1800c43a5  lea     r9, [rbp+57h+var_68]
0x1800c43a9  mov     r8, rax
0x1800c43ac  lea     rdx, [rbp+57h+var_78]
0x1800c43b0  mov     rcx, rbx
0x1800c43b3  call    ??$create_exception_checked_task@_N@?$streambuf_state_manager@D@details@streams@Concurrency@@AEAA?AV?$task@_N@pplx@@V45@V?$function@$$A6A_N_N@Z@std@@H@Z; Concurrency::streams::details::streambuf_state_manager<char>::create_exception_checked_task<bool>(pplx::task<bool>,std::function<bool (bool)>,int)
0x1800c43b8  nop
0x1800c43b9  lea     r8, [rbp+57h+arg_0]
0x1800c43bd  mov     rdx, rdi
0x1800c43c0  mov     rcx, rax
0x1800c43c3  call    ??$then@V_lambda_2_@?1??sync@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAA?AV?$task@X@pplx@@XZ@@?$task@_N@pplx@@QEBA?AV?$task@X@1@$$QEAV_lambda_2_@?1??sync@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAA?AV21@XZ@@Z; pplx::task<bool>::then<`Concurrency::streams::details::streambuf_state_manager<char>::sync(void)'::`2'::_lambda_2_>(`Concurrency::streams::details::streambuf_state_manager<char>::sync(void)'::`2'::_lambda_2_ &&)
0x1800c43c8  nop
0x1800c43c9  lea     rcx, [rbp+57h+var_78]
0x1800c43cd  call    ??1?$shared_ptr@UApduHelperNotificationHandler@LPA@@@std@@QEAA@XZ; std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(void)
0x1800c43d2  mov     rax, rdi
0x1800c43d5  mov     rbx, [rsp+0C0h+arg_8]
0x1800c43dd  add     rsp, 0B0h
0x1800c43e4  pop     rdi
0x1800c43e5  pop     rsi
0x1800c43e6  pop     rbp
0x1800c43e7  retn
```
