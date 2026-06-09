# _std::_Packaged_state_helium_async::_anonymous_namespace_::container_creation_context___cdecl(void)_::_Call_immediate_::_1_::catch$12

- ea: `0x1800c191d`
- end: `0x1800c1a1b`
- name: `_std::_Packaged_state_helium_async::_anonymous_namespace_::container_creation_context___cdecl(void)_::_Call_immediate_::_1_::catch$12`
- size: `254`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180055f58`
- `0x1800591f0`
- `0x1800c191d`
- `0x1800cc010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800c19eb`
- `msvcp_win!_Mtx_unlock` at `0x1800c19eb`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c197d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c197d`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c19d4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c19fc`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c19d4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800c19fc`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800c1947`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800c1947`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800c1937`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800c1937`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800c19ad`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800c19ad`

## pseudocode

```c
__int64 __fastcall std::_Packaged_state_helium_async::_anonymous_namespace_::container_creation_context___cdecl_void__::_Call_immediate_::_1_::catch_12(
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
  if ( v3[217] )
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
0x1800c191d  mov     [rsp+arg_8], rdx
0x1800c1922  push    rbx
0x1800c1923  push    rbp
0x1800c1924  sub     rsp, 28h
0x1800c1928  mov     rbp, rdx
0x1800c192b  xorps   xmm0, xmm0
0x1800c192e  movdqu  xmmword ptr [rbp+38h], xmm0
0x1800c1933  lea     rcx, [rbp+38h]
0x1800c1937  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800c193e  nop     dword ptr [rax+rax+00h]
0x1800c1943  lea     rcx, [rbp+38h]
0x1800c1947  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800c194e  nop     dword ptr [rax+rax+00h]
0x1800c1953  lea     rax, [rbp+38h]
0x1800c1957  mov     [rbp+48h], rax
0x1800c195b  mov     rbx, [rbp+30h]
0x1800c195f  lea     rdx, [rbx+68h]
0x1800c1963  lea     rcx, [rbp+50h]
0x1800c1967  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800c196c  nop
0x1800c196d  xorps   xmm0, xmm0
0x1800c1970  movdqu  xmmword ptr [rbp+20h], xmm0
0x1800c1975  lea     rdx, [rbp+38h]
0x1800c1979  lea     rcx, [rbp+20h]
0x1800c197d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800c1984  nop     dword ptr [rax+rax+00h]
0x1800c1989  lea     rax, [rbp+20h]
0x1800c198d  mov     [rbp+30h], rax
0x1800c1991  cmp     byte ptr [rbx+0D9h], 0
0x1800c1998  jz      short loc_1800C19A5
0x1800c199a  mov     ecx, 3
0x1800c199f  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800c19a5  lea     rcx, [rbx+58h]
0x1800c19a9  lea     rdx, [rbp+20h]
0x1800c19ad  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800c19b4  nop     dword ptr [rax+rax+00h]
0x1800c19b9  mov     rax, [rbx]
0x1800c19bc  xor     r8d, r8d
0x1800c19bf  lea     rdx, [rbp+50h]
0x1800c19c3  mov     rcx, rbx
0x1800c19c6  mov     rax, [rax+28h]
0x1800c19ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c19cf  nop
0x1800c19d0  lea     rcx, [rbp+20h]
0x1800c19d4  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800c19db  nop     dword ptr [rax+rax+00h]
0x1800c19e0  nop
0x1800c19e1  cmp     byte ptr [rbp+58h], 0
0x1800c19e5  jz      short loc_1800C19F8
0x1800c19e7  mov     rcx, [rbp+50h]; _Mtx_t
0x1800c19eb  call    cs:__imp__Mtx_unlock
0x1800c19f2  nop     dword ptr [rax+rax+00h]
0x1800c19f7  nop
0x1800c19f8  lea     rcx, [rbp+38h]
0x1800c19fc  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800c1a03  nop     dword ptr [rax+rax+00h]
0x1800c1a08  nop
0x1800c1a09  mov     rax, 0
0x1800c1a13  add     rsp, 28h
0x1800c1a17  pop     rbp
0x1800c1a18  pop     rbx
0x1800c1a19  retn
```
