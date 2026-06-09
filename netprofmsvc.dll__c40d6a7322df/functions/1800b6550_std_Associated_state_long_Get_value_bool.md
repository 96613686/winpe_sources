# std::_Associated_state<long>::_Get_value(bool)

- ea: `0x1800b6550`
- end: `0x1800b6657`
- name: `?_Get_value@?$_Associated_state@J@std@@UEAAAEAJ_N@Z`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800b6660`

## callees

- `0x1800a88a0`
- `0x1800b1950`
- `0x1800b1f94`
- `0x1800b6550`
- `0x1800b66dc`
- `0x1800b6d90`

## import_xrefs

- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800b65a6`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800b6603`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800b65a6`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800b6603`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800b65d1`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800b662e`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800b65d1`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800b662e`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800b65bf`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800b661c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800b65bf`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800b661c`
- `msvcp_win!_Cnd_wait` at `0x1800b65f1`
- `msvcp_win!_Cnd_wait` at `0x1800b65f1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Associated_state<long>::_Get_value(__int64 a1, char a2)
{
  _BYTE *v4; // rsi
  __int128 v6; // [rsp+20h] [rbp-38h] BYREF
  __int128 *v7; // [rsp+30h] [rbp-28h]
  _Mtx_t v8[2]; // [rsp+38h] [rbp-20h] BYREF

  *(_OWORD *)v8 = 0;
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v8, a1 + 32);
  v4 = (_BYTE *)(a1 + 184);
  if ( a2 && *v4 )
    std::_Throw_future_error2(2);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    v7 = &v6;
    __ExceptionPtrRethrow(&v6);
  }
  *v4 = 1;
  std::_Associated_state<long>::_Maybe_run_deferred_function(a1, v8);
  while ( !*(_DWORD *)(a1 + 188) )
    _Cnd_wait((_Cnd_t)(a1 + 112), v8[0]);
  if ( __ExceptionPtrToBool((const void *)(a1 + 16)) )
  {
    v6 = 0;
    __ExceptionPtrCopy(&v6, (const void *)(a1 + 16));
    v7 = &v6;
    __ExceptionPtrRethrow(&v6);
  }
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v8);
  return a1 + 12;
}

```

## disassembly

```asm
0x1800b6550  push    rbp
0x1800b6552  push    rbx
0x1800b6553  push    rsi
0x1800b6554  push    rdi
0x1800b6555  mov     rbp, rsp
0x1800b6558  sub     rsp, 58h
0x1800b655c  mov     rax, cs:__security_cookie
0x1800b6563  xor     rax, rsp
0x1800b6566  mov     [rbp+var_10], rax
0x1800b656a  mov     bl, dl
0x1800b656c  mov     rdi, rcx
0x1800b656f  xorps   xmm0, xmm0
0x1800b6572  movups  xmmword ptr [rbp+var_20], xmm0
0x1800b6576  lea     rdx, [rcx+20h]
0x1800b657a  lea     rcx, [rbp+var_20]
0x1800b657e  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x1800b6583  nop
0x1800b6584  lea     rsi, [rdi+0B8h]
0x1800b658b  test    bl, bl
0x1800b658d  jz      short loc_1800B659F
0x1800b658f  cmp     byte ptr [rsi], 0
0x1800b6592  jz      short loc_1800B659F
0x1800b6594  mov     ecx, 2
0x1800b6599  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800b659f  lea     rbx, [rdi+10h]
0x1800b65a3  mov     rcx, rbx
0x1800b65a6  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800b65ac  test    al, al
0x1800b65ae  jz      short loc_1800B65D8
0x1800b65b0  xorps   xmm0, xmm0
0x1800b65b3  movdqu  [rbp+var_38], xmm0
0x1800b65b8  mov     rdx, rbx
0x1800b65bb  lea     rcx, [rbp+var_38]
0x1800b65bf  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800b65c5  lea     rax, [rbp+var_38]
0x1800b65c9  mov     [rbp+var_28], rax
0x1800b65cd  lea     rcx, [rbp+var_38]
0x1800b65d1  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800b65d7  nop
0x1800b65d8  mov     byte ptr [rsi], 1
0x1800b65db  lea     rdx, [rbp+var_20]
0x1800b65df  mov     rcx, rdi
0x1800b65e2  call    ?_Maybe_run_deferred_function@?$_Associated_state@J@std@@IEAAXAEAV?$unique_lock@Vmutex@std@@@2@@Z; std::_Associated_state<long>::_Maybe_run_deferred_function(std::unique_lock<std::mutex> &)
0x1800b65e7  jmp     short loc_1800B65F7
0x1800b65e9  mov     rdx, [rbp+var_20]; _Mtx_t
0x1800b65ed  lea     rcx, [rdi+70h]; _Cnd_t
0x1800b65f1  call    cs:__imp__Cnd_wait
0x1800b65f7  cmp     dword ptr [rdi+0BCh], 0
0x1800b65fe  jz      short loc_1800B65E9
0x1800b6600  mov     rcx, rbx
0x1800b6603  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800b6609  test    al, al
0x1800b660b  jz      short loc_1800B6635
0x1800b660d  xorps   xmm0, xmm0
0x1800b6610  movdqu  [rbp+var_38], xmm0
0x1800b6615  mov     rdx, rbx
0x1800b6618  lea     rcx, [rbp+var_38]
0x1800b661c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800b6622  lea     rax, [rbp+var_38]
0x1800b6626  mov     [rbp+var_28], rax
0x1800b662a  lea     rcx, [rbp+var_38]
0x1800b662e  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800b6634  nop
0x1800b6635  lea     rcx, [rbp+var_20]
0x1800b6639  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1800b663e  lea     rax, [rdi+0Ch]
0x1800b6642  mov     rcx, [rbp+var_10]
0x1800b6646  xor     rcx, rsp; StackCookie
0x1800b6649  call    __security_check_cookie
0x1800b664e  add     rsp, 58h
0x1800b6652  pop     rdi
0x1800b6653  pop     rsi
0x1800b6654  pop     rbx
0x1800b6655  pop     rbp
0x1800b6656  retn
```
