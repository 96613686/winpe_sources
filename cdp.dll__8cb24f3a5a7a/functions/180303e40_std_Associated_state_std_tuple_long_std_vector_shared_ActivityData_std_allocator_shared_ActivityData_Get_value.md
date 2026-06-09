# std::_Associated_state<std::tuple<long,std::vector<shared::ActivityData,std::allocator<shared::ActivityData>>>>::_Get_value(bool)

- ea: `0x180303e40`
- end: `0x180303f29`
- name: `?_Get_value@?$_Associated_state@V?$tuple@JV?$vector@UActivityData@shared@@V?$allocator@UActivityData@shared@@@std@@@std@@@std@@@std@@UEAAAEAV?$tuple@JV?$vector@UActivityData@shared@@V?$allocator@UActivityData@shared@@@std@@@std@@@2@_N@Z`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180089254`
- `0x180089910`
- `0x1802bead0`
- `0x180303e40`
- `0x180303f30`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180303eac`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180303f0c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180303eac`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x180303f0c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180303e9a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180303efa`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180303e9a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180303efa`
- `msvcp_win!_Cnd_wait` at `0x180303ecf`
- `msvcp_win!_Cnd_wait` at `0x180303ecf`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180303e81`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180303ee1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180303e81`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x180303ee1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<std::tuple<long,std::vector<shared::ActivityData>>>::_Get_value(
        __int64 a1,
        char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v7, a1 + 64);
  v4 = (_BYTE *)(a1 + 216);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 48)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 48));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<std::tuple<long,std::vector<shared::ActivityData>>>::_Maybe_run_deferred_function(a1, v7);
  while ( !*(_DWORD *)(a1 + 220) )
    _Cnd_wait((_Cnd_t)(a1 + 144), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 48)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 48));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 16;
}

```

## disassembly

```asm
0x180303e40  push    rbp
0x180303e42  push    rbx
0x180303e43  push    rsi
0x180303e44  push    rdi
0x180303e45  mov     rbp, rsp
0x180303e48  sub     rsp, 48h
0x180303e4c  mov     bl, dl
0x180303e4e  mov     rdi, rcx
0x180303e51  lea     rdx, [rcx+40h]
0x180303e55  lea     rcx, [rbp+var_18]
0x180303e59  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x180303e5e  nop
0x180303e5f  lea     rsi, [rdi+0D8h]
0x180303e66  test    bl, bl
0x180303e68  jz      short loc_180303E7A
0x180303e6a  cmp     byte ptr [rsi], 0
0x180303e6d  jz      short loc_180303E7A
0x180303e6f  mov     ecx, 2
0x180303e74  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x180303e7a  lea     rbx, [rdi+30h]
0x180303e7e  mov     rcx, rbx
0x180303e81  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180303e87  test    al, al
0x180303e89  jz      short loc_180303EB3
0x180303e8b  xorps   xmm0, xmm0
0x180303e8e  movdqu  [rbp+var_28], xmm0
0x180303e93  mov     rdx, rbx
0x180303e96  lea     rcx, [rbp+var_28]
0x180303e9a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180303ea0  lea     rax, [rbp+var_28]
0x180303ea4  mov     [rbp+arg_0], rax
0x180303ea8  lea     rcx, [rbp+var_28]
0x180303eac  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180303eb2  nop
0x180303eb3  mov     byte ptr [rsi], 1
0x180303eb6  lea     rdx, [rbp+var_18]
0x180303eba  mov     rcx, rdi
0x180303ebd  call    ?_Maybe_run_deferred_function@?$_Associated_state@V?$tuple@JV?$vector@UActivityData@shared@@V?$allocator@UActivityData@shared@@@std@@@std@@@std@@@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<std::tuple<long,std::vector<shared::ActivityData>>>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x180303ec2  jmp     short loc_180303ED5
0x180303ec4  mov     rdx, [rbp+var_18]; _Mtx_t
0x180303ec8  lea     rcx, [rdi+90h]; _Cnd_t
0x180303ecf  call    cs:__imp__Cnd_wait
0x180303ed5  cmp     dword ptr [rdi+0DCh], 0
0x180303edc  jz      short loc_180303EC4
0x180303ede  mov     rcx, rbx
0x180303ee1  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x180303ee7  test    al, al
0x180303ee9  jz      short loc_180303F13
0x180303eeb  xorps   xmm0, xmm0
0x180303eee  movdqu  [rbp+var_28], xmm0
0x180303ef3  mov     rdx, rbx
0x180303ef6  lea     rcx, [rbp+var_28]
0x180303efa  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180303f00  lea     rax, [rbp+var_28]
0x180303f04  mov     [rbp+arg_0], rax
0x180303f08  lea     rcx, [rbp+var_28]
0x180303f0c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x180303f12  nop
0x180303f13  lea     rcx, [rbp+var_18]
0x180303f17  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x180303f1c  lea     rax, [rdi+10h]
0x180303f20  add     rsp, 48h
0x180303f24  pop     rdi
0x180303f25  pop     rsi
0x180303f26  pop     rbx
0x180303f27  pop     rbp
0x180303f28  retn
```
