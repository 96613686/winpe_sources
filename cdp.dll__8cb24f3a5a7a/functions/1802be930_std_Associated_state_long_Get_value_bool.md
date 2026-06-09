# std::_Associated_state<long>::_Get_value(bool)

- ea: `0x1802be930`
- end: `0x1802bea16`
- name: `?_Get_value@?$_Associated_state@J@std@@UEAAAEAJ_N@Z`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180089254`
- `0x180089910`
- `0x1802be930`
- `0x1802bea1c`
- `0x1802bead0`

## import_xrefs

- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1802be99c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1802be9f9`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1802be99c`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1802be9f9`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1802be98a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1802be9e7`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1802be98a`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1802be9e7`
- `msvcp_win!_Cnd_wait` at `0x1802be9bc`
- `msvcp_win!_Cnd_wait` at `0x1802be9bc`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1802be971`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1802be9ce`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1802be971`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1802be9ce`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<long>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-28h] BYREF
  _Mtx_t v7[3]; // [rsp+30h] [rbp-18h] BYREF

  std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(v7, a1 + 32);
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<int>::_Maybe_run_deferred_function(a1, v7);
  while ( !*(_DWORD *)(a1 + 188) )
    _Cnd_wait((_Cnd_t)(a1 + 112), v7[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return a1 + 12;
}

```

## disassembly

```asm
0x1802be930  push    rbp
0x1802be932  push    rbx
0x1802be933  push    rsi
0x1802be934  push    rdi
0x1802be935  mov     rbp, rsp
0x1802be938  sub     rsp, 48h
0x1802be93c  mov     bl, dl
0x1802be93e  mov     rdi, rcx
0x1802be941  lea     rdx, [rcx+20h]
0x1802be945  lea     rcx, [rbp+var_18]
0x1802be949  call    ??0?$unique_lock@Vrecursive_mutex@std@@@std@@QEAA@AEAVrecursive_mutex@1@@Z; std::unique_lock<std::recursive_mutex>::unique_lock<std::recursive_mutex>(std::recursive_mutex &)
0x1802be94e  nop
0x1802be94f  lea     rsi, [rdi+0B8h]
0x1802be956  test    bl, bl
0x1802be958  jz      short loc_1802BE96A
0x1802be95a  cmp     byte ptr [rsi], 0
0x1802be95d  jz      short loc_1802BE96A
0x1802be95f  mov     ecx, 2
0x1802be964  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1802be96a  lea     rbx, [rdi+10h]
0x1802be96e  mov     rcx, rbx
0x1802be971  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1802be977  test    al, al
0x1802be979  jz      short loc_1802BE9A3
0x1802be97b  xorps   xmm0, xmm0
0x1802be97e  movdqu  [rbp+var_28], xmm0
0x1802be983  mov     rdx, rbx
0x1802be986  lea     rcx, [rbp+var_28]
0x1802be98a  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1802be990  lea     rax, [rbp+var_28]
0x1802be994  mov     [rbp+arg_0], rax
0x1802be998  lea     rcx, [rbp+var_28]
0x1802be99c  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1802be9a2  nop
0x1802be9a3  mov     byte ptr [rsi], 1
0x1802be9a6  lea     rdx, [rbp+var_18]
0x1802be9aa  mov     rcx, rdi
0x1802be9ad  call    ?_Maybe_run_deferred_function@?$_Associated_state@H@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<int>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x1802be9b2  jmp     short loc_1802BE9C2
0x1802be9b4  mov     rdx, [rbp+var_18]; _Mtx_t
0x1802be9b8  lea     rcx, [rdi+70h]; _Cnd_t
0x1802be9bc  call    cs:__imp__Cnd_wait
0x1802be9c2  cmp     dword ptr [rdi+0BCh], 0
0x1802be9c9  jz      short loc_1802BE9B4
0x1802be9cb  mov     rcx, rbx
0x1802be9ce  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1802be9d4  test    al, al
0x1802be9d6  jz      short loc_1802BEA00
0x1802be9d8  xorps   xmm0, xmm0
0x1802be9db  movdqu  [rbp+var_28], xmm0
0x1802be9e0  mov     rdx, rbx
0x1802be9e3  lea     rcx, [rbp+var_28]
0x1802be9e7  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1802be9ed  lea     rax, [rbp+var_28]
0x1802be9f1  mov     [rbp+arg_0], rax
0x1802be9f5  lea     rcx, [rbp+var_28]
0x1802be9f9  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1802be9ff  nop
0x1802bea00  lea     rcx, [rbp+var_18]
0x1802bea04  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1802bea09  lea     rax, [rdi+0Ch]
0x1802bea0d  add     rsp, 48h
0x1802bea11  pop     rdi
0x1802bea12  pop     rsi
0x1802bea13  pop     rbx
0x1802bea14  pop     rbp
0x1802bea15  retn
```
