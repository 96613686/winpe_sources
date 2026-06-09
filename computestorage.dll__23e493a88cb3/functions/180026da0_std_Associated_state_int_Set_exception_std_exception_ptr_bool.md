# std::_Associated_state<int>::_Set_exception(std::exception_ptr,bool)

- ea: `0x180026da0`
- end: `0x180026e9b`
- name: `?_Set_exception@?$_Associated_state@H@std@@QEAAXVexception_ptr@2@_N@Z`
- size: `251`
- prototype: `void __fastcall(_BYTE *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800446da`

## callees

- `0x180002690`
- `0x180022994`
- `0x180026da0`
- `0x180026f4c`
- `0x180049010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180026e17`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180026e17`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180026dee`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180026dee`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180026e3e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180026e65`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180026e3e`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180026e65`
- `msvcp_win!_Mtx_unlock` at `0x180026e55`
- `msvcp_win!_Mtx_unlock` at `0x180026e55`

## pseudocode

```c
void __fastcall std::_Associated_state<int>::_Set_exception(_BYTE *a1, void *a2)
{
  __int128 v4; // [rsp+20h] [rbp-40h] BYREF
  __int128 *v5; // [rsp+30h] [rbp-30h]
  void *v6; // [rsp+38h] [rbp-28h]
  _Mtx_t v7[2]; // [rsp+40h] [rbp-20h] BYREF

  v6 = a2;
  *(_OWORD *)v7 = 0;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v7, a1 + 32);
  v4 = 0;
  __ExceptionPtrCopy(&v4, a2);
  v5 = &v4;
  if ( a1[193] )
    std::_Throw_future_error2(3);
  __ExceptionPtrAssign(a1 + 16, &v4);
  (*(void (__fastcall **)(_BYTE *, _Mtx_t *, _QWORD))(*(_QWORD *)a1 + 40LL))(a1, v7, 0);
  __ExceptionPtrDestroy(&v4);
  if ( LOBYTE(v7[1]) )
    _Mtx_unlock(v7[0]);
  __ExceptionPtrDestroy(a2);
}

```

## disassembly

```asm
0x180026da0  mov     [rsp-8+arg_10], rbx
0x180026da5  mov     [rsp-8+arg_18], rdi
0x180026daa  push    rbp
0x180026dab  mov     rbp, rsp
0x180026dae  sub     rsp, 60h
0x180026db2  mov     rax, cs:__security_cookie
0x180026db9  xor     rax, rsp
0x180026dbc  mov     [rbp+var_10], rax
0x180026dc0  mov     rdi, rdx
0x180026dc3  mov     rbx, rcx
0x180026dc6  mov     [rbp+var_28], rdx
0x180026dca  xorps   xmm0, xmm0
0x180026dcd  movups  xmmword ptr [rbp+var_20], xmm0
0x180026dd1  lea     rdx, [rcx+20h]
0x180026dd5  lea     rcx, [rbp+var_20]
0x180026dd9  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180026dde  nop
0x180026ddf  xorps   xmm0, xmm0
0x180026de2  movdqu  [rbp+var_40], xmm0
0x180026de7  mov     rdx, rdi
0x180026dea  lea     rcx, [rbp+var_40]
0x180026dee  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180026df5  nop     dword ptr [rax+rax+00h]
0x180026dfa  lea     rax, [rbp+var_40]
0x180026dfe  mov     [rbp+var_30], rax
0x180026e02  cmp     byte ptr [rbx+0C1h], 0
0x180026e09  jnz     loc_180026E90
0x180026e0f  lea     rcx, [rbx+10h]
0x180026e13  lea     rdx, [rbp+var_40]
0x180026e17  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180026e1e  nop     dword ptr [rax+rax+00h]
0x180026e23  mov     rax, [rbx]
0x180026e26  xor     r8d, r8d
0x180026e29  lea     rdx, [rbp+var_20]
0x180026e2d  mov     rcx, rbx
0x180026e30  mov     rax, [rax+28h]
0x180026e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e39  nop
0x180026e3a  lea     rcx, [rbp+var_40]
0x180026e3e  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180026e45  nop     dword ptr [rax+rax+00h]
0x180026e4a  nop
0x180026e4b  cmp     byte ptr [rbp+var_20+8], 0
0x180026e4f  jz      short loc_180026E62
0x180026e51  mov     rcx, [rbp+var_20]; _Mtx_t
0x180026e55  call    cs:__imp__Mtx_unlock
0x180026e5c  nop     dword ptr [rax+rax+00h]
0x180026e61  nop
0x180026e62  mov     rcx, rdi
0x180026e65  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180026e6c  nop     dword ptr [rax+rax+00h]
0x180026e71  mov     rcx, [rbp+var_10]
0x180026e75  xor     rcx, rsp; StackCookie
0x180026e78  call    __security_check_cookie
0x180026e7d  lea     r11, [rsp+60h+var_s0]
0x180026e82  mov     rbx, [r11+20h]
0x180026e86  mov     rdi, [r11+28h]
0x180026e8a  mov     rsp, r11
0x180026e8d  pop     rbp
0x180026e8e  retn
0x180026e90  mov     ecx, 3
0x180026e95  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
```
