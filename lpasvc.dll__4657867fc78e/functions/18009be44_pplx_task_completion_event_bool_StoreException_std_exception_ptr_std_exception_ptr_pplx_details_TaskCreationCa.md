# pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)

- ea: `0x18009be44`
- end: `0x18009befc`
- name: `??$_StoreException@Vexception_ptr@std@@@?$task_completion_event@_N@pplx@@QEBA_NVexception_ptr@std@@AEBV_TaskCreationCallstack@details@1@@Z`
- size: `184`
- prototype: `char __fastcall(__int64, void *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009a26c`

## callees

- `0x180014300`
- `0x1800143d0`
- `0x180061c50`
- `0x18009be44`
- `0x1800a8d3c`
- `0x1800be604`
- `0x1800c0208`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18009bee7`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18009bee7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009be9a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18009be9a`

## pseudocode

```c
char __fastcall pplx::task_completion_event<bool>::_StoreException<std::exception_ptr>(
        __int64 a1,
        void *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rbx
  __int64 v7; // rax
  char v8; // bl
  __int128 v10; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v11[40]; // [rsp+30h] [rbp-28h] BYREF

  v6 = (struct _RTL_CRITICAL_SECTION *)(*(_QWORD *)a1 + 24LL);
  pplx::details::critical_section_impl::lock(v6);
  if ( (unsigned __int8)pplx::task_completion_event<unsigned __int64>::_IsTriggered(a1)
    || *(_QWORD *)(*(_QWORD *)a1 + 96LL) )
  {
    pplx::details::critical_section_impl::unlock(v6);
    v8 = 0;
  }
  else
  {
    v10 = 0;
    __ExceptionPtrCopy(&v10, a2);
    v7 = pplx::task_completion_event<unsigned __int64>::_ToExceptionHolder(v11, &v10, a3);
    std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(*(_QWORD *)a1 + 96LL, v7);
    std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(v11);
    pplx::details::critical_section_impl::unlock(v6);
    v8 = 1;
  }
  __ExceptionPtrDestroy(a2);
  return v8;
}

```

## disassembly

```asm
0x18009be44  mov     [rsp+arg_10], rbx
0x18009be49  mov     [rsp+arg_8], rdx
0x18009be4e  push    rbp
0x18009be4f  push    rsi
0x18009be50  push    rdi
0x18009be51  sub     rsp, 40h
0x18009be55  mov     rbp, r8
0x18009be58  mov     rsi, rdx
0x18009be5b  mov     rdi, rcx
0x18009be5e  mov     rbx, [rcx]
0x18009be61  add     rbx, 18h
0x18009be65  mov     [rsp+58h+arg_0], rbx
0x18009be6a  mov     rcx, rbx; lpCriticalSection
0x18009be6d  call    ?lock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::lock(void)
0x18009be72  nop
0x18009be73  mov     rcx, rdi
0x18009be76  call    ?_IsTriggered@?$task_completion_event@_K@pplx@@QEBA_NXZ; pplx::task_completion_event<unsigned __int64>::_IsTriggered(void)
0x18009be7b  test    al, al
0x18009be7d  jnz     short loc_18009BED9
0x18009be7f  mov     rax, [rdi]
0x18009be82  cmp     qword ptr [rax+60h], 0
0x18009be87  jnz     short loc_18009BED9
0x18009be89  xorps   xmm0, xmm0
0x18009be8c  movdqu  [rsp+58h+var_38], xmm0
0x18009be92  mov     rdx, rsi
0x18009be95  lea     rcx, [rsp+58h+var_38]
0x18009be9a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18009bea0  mov     r8, rbp
0x18009bea3  lea     rdx, [rsp+58h+var_38]
0x18009bea8  lea     rcx, [rsp+58h+var_28]
0x18009bead  call    ?_ToExceptionHolder@?$task_completion_event@_K@pplx@@CA?AV?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@Vexception_ptr@4@AEBV_TaskCreationCallstack@details@2@@Z; pplx::task_completion_event<unsigned __int64>::_ToExceptionHolder(std::exception_ptr,pplx::details::_TaskCreationCallstack const &)
0x18009beb2  mov     rcx, [rdi]
0x18009beb5  add     rcx, 60h ; '`'
0x18009beb9  mov     rdx, rax
0x18009bebc  call    ??4?$shared_ptr@U_ExceptionHolder@details@pplx@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<pplx::details::_ExceptionHolder>::operator=(std::shared_ptr<pplx::details::_ExceptionHolder> &&)
0x18009bec1  lea     rcx, [rsp+58h+var_28]
0x18009bec6  call    ??1?$shared_ptr@UApduHelperNotificationHandler@LPA@@@std@@QEAA@XZ; std::shared_ptr<LPA::ApduHelperNotificationHandler>::~shared_ptr<LPA::ApduHelperNotificationHandler>(void)
0x18009becb  nop
0x18009becc  mov     rcx, rbx; lpCriticalSection
0x18009becf  call    ?unlock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::unlock(void)
0x18009bed4  nop
0x18009bed5  mov     bl, 1
0x18009bed7  jmp     short loc_18009BEE4
0x18009bed9  mov     rcx, rbx; lpCriticalSection
0x18009bedc  call    ?unlock@critical_section_impl@details@pplx@@QEAAXXZ; pplx::details::critical_section_impl::unlock(void)
0x18009bee1  nop
0x18009bee2  xor     ebx, ebx
0x18009bee4  mov     rcx, rsi
0x18009bee7  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18009beed  mov     al, bl
0x18009beef  mov     rbx, [rsp+58h+arg_10]
0x18009bef4  add     rsp, 40h
0x18009bef8  pop     rdi
0x18009bef9  pop     rsi
0x18009befa  pop     rbp
0x18009befb  retn
```
