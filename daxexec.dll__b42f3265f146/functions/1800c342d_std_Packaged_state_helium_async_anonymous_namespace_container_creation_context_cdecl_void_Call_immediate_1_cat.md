# _std::_Packaged_state_helium_async::_anonymous_namespace_::container_creation_context___cdecl(void)_::_Call_immediate_::_1_::catch$11

- ea: `0x1800c342d`
- end: `0x1800c352b`
- name: `_std::_Packaged_state_helium_async::_anonymous_namespace_::container_creation_context___cdecl(void)_::_Call_immediate_::_1_::catch$11`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180057984`
- `0x18005ad70`
- `0x1800c342d`
- `0x1800cd010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800c34fb`
- `msvcp_win!_Mtx_unlock` at `0x1800c34fb`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c348d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c348d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c34e4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c350c`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c34e4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c350c`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800c3457`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800c3457`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800c3447`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800c3447`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800c34bd`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800c34bd`

## pseudocode

```c
__int64 __fastcall std::_Packaged_state_helium_async::_anonymous_namespace_::container_creation_context___cdecl_void__::_Call_immediate_::_1_::catch_11(
        __int64 a1,
        __int64 a2)
{
  _BYTE *v3; // rbx

  *(_OWORD *)(a2 + 56) = 0;
  __ExceptionPtrCreate((void *)(a2 + 56));
  __ExceptionPtrCurrentException((void *)(a2 + 56));
  *(_QWORD *)(a2 + 72) = a2 + 56;
  v3 = *(_BYTE **)(a2 + 48);
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(a2 + 80, v3 + 104);
  *(_OWORD *)(a2 + 32) = 0;
  __ExceptionPtrCopy((void *)(a2 + 32), (const void *)(a2 + 56));
  *(_QWORD *)(a2 + 48) = a2 + 32;
  if ( v3[265] )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign(v3 + 88, (const void *)(a2 + 32));
  (*(void (__fastcall **)(_BYTE *, __int64, _QWORD))(*(_QWORD *)v3 + 40LL))(v3, a2 + 80, 0);
  __ExceptionPtrDestroy((void *)(a2 + 32));
  if ( *(_BYTE *)(a2 + 88) )
    _Mtx_unlock(*(_Mtx_t *)(a2 + 80));
  __ExceptionPtrDestroy((void *)(a2 + 56));
  return 0;
}

```

## disassembly

```asm
0x1800c342d  mov     [rsp+arg_8], rdx
0x1800c3432  push    rbx
0x1800c3433  push    rbp
0x1800c3434  sub     rsp, 28h
0x1800c3438  mov     rbp, rdx
0x1800c343b  xorps   xmm0, xmm0
0x1800c343e  movdqu  xmmword ptr [rbp+38h], xmm0
0x1800c3443  lea     rcx, [rbp+38h]
0x1800c3447  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800c344e  nop     dword ptr [rax+rax+00h]
0x1800c3453  lea     rcx, [rbp+38h]
0x1800c3457  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800c345e  nop     dword ptr [rax+rax+00h]
0x1800c3463  lea     rax, [rbp+38h]
0x1800c3467  mov     [rbp+48h], rax
0x1800c346b  mov     rbx, [rbp+30h]
0x1800c346f  lea     rdx, [rbx+68h]
0x1800c3473  lea     rcx, [rbp+50h]
0x1800c3477  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800c347c  nop
0x1800c347d  xorps   xmm0, xmm0
0x1800c3480  movdqu  xmmword ptr [rbp+20h], xmm0
0x1800c3485  lea     rdx, [rbp+38h]
0x1800c3489  lea     rcx, [rbp+20h]
0x1800c348d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800c3494  nop     dword ptr [rax+rax+00h]
0x1800c3499  lea     rax, [rbp+20h]
0x1800c349d  mov     [rbp+30h], rax
0x1800c34a1  cmp     byte ptr [rbx+109h], 0
0x1800c34a8  jz      short loc_1800C34B5
0x1800c34aa  mov     ecx, 3
0x1800c34af  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800c34b5  lea     rcx, [rbx+58h]
0x1800c34b9  lea     rdx, [rbp+20h]
0x1800c34bd  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800c34c4  nop     dword ptr [rax+rax+00h]
0x1800c34c9  mov     rax, [rbx]
0x1800c34cc  xor     r8d, r8d
0x1800c34cf  lea     rdx, [rbp+50h]
0x1800c34d3  mov     rcx, rbx
0x1800c34d6  mov     rax, [rax+28h]
0x1800c34da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c34df  nop
0x1800c34e0  lea     rcx, [rbp+20h]
0x1800c34e4  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800c34eb  nop     dword ptr [rax+rax+00h]
0x1800c34f0  nop
0x1800c34f1  cmp     byte ptr [rbp+58h], 0
0x1800c34f5  jz      short loc_1800C3508
0x1800c34f7  mov     rcx, [rbp+50h]; _Mtx_t
0x1800c34fb  call    cs:__imp__Mtx_unlock
0x1800c3502  nop     dword ptr [rax+rax+00h]
0x1800c3507  nop
0x1800c3508  lea     rcx, [rbp+38h]
0x1800c350c  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800c3513  nop     dword ptr [rax+rax+00h]
0x1800c3518  nop
0x1800c3519  mov     rax, 0
0x1800c3523  add     rsp, 28h
0x1800c3527  pop     rbp
0x1800c3528  pop     rbx
0x1800c3529  retn
```
