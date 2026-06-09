# Concurrency::streams::details::streambuf_state_manager<char>::sbumpc(void)

- ea: `0x1800c3520`
- end: `0x1800c35a8`
- name: `?sbumpc@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAAHXZ`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800c0d5c`
- `0x1800c3520`
- `0x180101010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c354d`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c354d`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800c3531`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800c3531`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800c3562`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800c3562`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::sbumpc(__int64 a1)
{
  unsigned int v3; // eax
  __int128 v4; // [rsp+20h] [rbp-18h] BYREF

  if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
  {
    v4 = 0;
    __ExceptionPtrCopy(&v4, (const void *)(a1 + 24));
    __ExceptionPtrRethrow(&v4);
  }
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) )
    return 0xFFFFFFFFLL;
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 296LL))(a1);
  return Concurrency::streams::details::streambuf_state_manager<char>::check_sync_read_eof(a1, v3);
}

```

## disassembly

```asm
0x1800c3520  mov     [rsp+arg_8], rbx
0x1800c3525  push    rdi
0x1800c3526  sub     rsp, 30h
0x1800c352a  mov     rbx, rcx
0x1800c352d  add     rcx, 18h
0x1800c3531  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800c3537  test    al, al
0x1800c3539  jz      short loc_1800C3569
0x1800c353b  xorps   xmm0, xmm0
0x1800c353e  movdqu  [rsp+38h+var_18], xmm0
0x1800c3544  lea     rdx, [rbx+18h]
0x1800c3548  lea     rcx, [rsp+38h+var_18]
0x1800c354d  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800c3553  lea     rax, [rsp+38h+var_18]
0x1800c3558  mov     [rsp+38h+arg_0], rax
0x1800c355d  lea     rcx, [rsp+38h+var_18]
0x1800c3562  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800c3568  nop
0x1800c3569  mov     rax, [rbx]
0x1800c356c  mov     rcx, rbx
0x1800c356f  mov     rax, [rax+8]
0x1800c3573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3578  test    al, al
0x1800c357a  jnz     short loc_1800C3581
0x1800c357c  or      eax, 0FFFFFFFFh
0x1800c357f  jmp     short loc_1800C359D
0x1800c3581  mov     rax, [rbx]
0x1800c3584  mov     rcx, rbx
0x1800c3587  mov     rax, [rax+128h]
0x1800c358e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c3593  mov     edx, eax
0x1800c3595  mov     rcx, rbx
0x1800c3598  call    ?check_sync_read_eof@?$streambuf_state_manager@D@details@streams@Concurrency@@AEAAHH@Z; Concurrency::streams::details::streambuf_state_manager<char>::check_sync_read_eof(int)
0x1800c359d  mov     rbx, [rsp+38h+arg_8]
0x1800c35a2  add     rsp, 30h
0x1800c35a6  pop     rdi
0x1800c35a7  retn
```
