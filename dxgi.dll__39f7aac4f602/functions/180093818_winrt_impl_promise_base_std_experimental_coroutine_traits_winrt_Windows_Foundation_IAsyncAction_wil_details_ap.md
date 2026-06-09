# winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,wil::details::apartment_variable_base<1,wil::apartment_variable_platform> *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::unhandled_exception(void)

- ea: `0x180093818`
- end: `0x1800938b2`
- name: `?unhandled_exception@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAU?$apartment_variable_base@$00Uapartment_variable_platform@wil@@@details@wil@@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEAAXXZ`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800c9fda`

## callees

- `0x18007ac48`
- `0x18007ac54`
- `0x180093818`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18009386c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18009386c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180093885`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180093885`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18009389a`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x18009389a`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180093852`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x180093852`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180093847`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x180093847`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180093861`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180093861`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,wil::details::apartment_variable_base<1,wil::apartment_variable_platform> *>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::unhandled_exception(
        __int64 a1)
{
  __int128 v2; // [rsp+20h] [rbp-18h] BYREF
  RTL_SRWLOCK *SRWLock; // [rsp+48h] [rbp+10h]

  SRWLock = (RTL_SRWLOCK *)(a1 + 72);
  WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)(a1 + 72));
  v2 = 0;
  __ExceptionPtrCreate(&v2);
  __ExceptionPtrCurrentException(&v2);
  __ExceptionPtrAssign((void *)(a1 + 56), &v2);
  __ExceptionPtrDestroy(&v2);
  v2 = 0;
  __ExceptionPtrCopy(&v2, (const void *)(a1 + 56));
  try
  {
    __ExceptionPtrRethrow(&v2);
  }
  catch ( winrt::hresult_canceled )
  {
    *(_DWORD *)(a1 + 96) = 2;
  }
  catch ( ... )
  {
    *(_DWORD *)(a1 + 96) = 3;
  }
  ReleaseSRWLockExclusive_0(SRWLock);
}

```

## disassembly

```asm
0x180093818  mov     [rsp+arg_0], rcx
0x18009381d  push    rbx
0x18009381e  sub     rsp, 30h
0x180093822  mov     rbx, rcx
0x180093825  add     rcx, 48h ; 'H'; SRWLock
0x180093829  mov     [rsp+38h+SRWLock], rcx
0x18009382e  mov     [rsp+38h+arg_10], rcx
0x180093833  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180093838  nop
0x180093839  xorps   xmm0, xmm0
0x18009383c  movdqu  [rsp+38h+var_18], xmm0
0x180093842  lea     rcx, [rsp+38h+var_18]
0x180093847  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18009384d  lea     rcx, [rsp+38h+var_18]
0x180093852  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x180093858  lea     rdx, [rsp+38h+var_18]
0x18009385d  lea     rcx, [rbx+38h]
0x180093861  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180093867  lea     rcx, [rsp+38h+var_18]
0x18009386c  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180093872  nop
0x180093873  xorps   xmm0, xmm0
0x180093876  movdqu  [rsp+38h+var_18], xmm0
0x18009387c  lea     rdx, [rbx+38h]
0x180093880  lea     rcx, [rsp+38h+var_18]
0x180093885  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x18009388b  lea     rax, [rsp+38h+var_18]
0x180093890  mov     [rsp+38h+arg_18], rax
0x180093895  lea     rcx, [rsp+38h+var_18]
0x18009389a  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800938a0  nop
0x1800938a1  jmp     short $+2
0x1800938a3  mov     rcx, [rsp+38h+SRWLock]; SRWLock
0x1800938a8  add     rsp, 30h
0x1800938ac  pop     rbx
0x1800938ad  jmp     ReleaseSRWLockExclusive_0
```
