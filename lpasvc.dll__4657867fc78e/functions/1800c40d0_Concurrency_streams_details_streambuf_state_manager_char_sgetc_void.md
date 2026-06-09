# Concurrency::streams::details::streambuf_state_manager<char>::sgetc(void)

- ea: `0x1800c40d0`
- end: `0x1800c4158`
- name: `?sgetc@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAAHXZ`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800c0d5c`
- `0x1800c40d0`
- `0x180101010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c40fd`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c40fd`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800c40e1`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800c40e1`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800c4112`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800c4112`

## pseudocode

```c
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::sgetc(__int64 a1)
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
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 312LL))(a1);
  return Concurrency::streams::details::streambuf_state_manager<char>::check_sync_read_eof(a1, v3);
}

```

## disassembly

```asm
0x1800c40d0  mov     [rsp+arg_8], rbx
0x1800c40d5  push    rdi
0x1800c40d6  sub     rsp, 30h
0x1800c40da  mov     rbx, rcx
0x1800c40dd  add     rcx, 18h
0x1800c40e1  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800c40e7  test    al, al
0x1800c40e9  jz      short loc_1800C4119
0x1800c40eb  xorps   xmm0, xmm0
0x1800c40ee  movdqu  [rsp+38h+var_18], xmm0
0x1800c40f4  lea     rdx, [rbx+18h]
0x1800c40f8  lea     rcx, [rsp+38h+var_18]
0x1800c40fd  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800c4103  lea     rax, [rsp+38h+var_18]
0x1800c4108  mov     [rsp+38h+arg_0], rax
0x1800c410d  lea     rcx, [rsp+38h+var_18]
0x1800c4112  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800c4118  nop
0x1800c4119  mov     rax, [rbx]
0x1800c411c  mov     rcx, rbx
0x1800c411f  mov     rax, [rax+8]
0x1800c4123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4128  test    al, al
0x1800c412a  jnz     short loc_1800C4131
0x1800c412c  or      eax, 0FFFFFFFFh
0x1800c412f  jmp     short loc_1800C414D
0x1800c4131  mov     rax, [rbx]
0x1800c4134  mov     rcx, rbx
0x1800c4137  mov     rax, [rax+138h]
0x1800c413e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c4143  mov     edx, eax
0x1800c4145  mov     rcx, rbx
0x1800c4148  call    ?check_sync_read_eof@?$streambuf_state_manager@D@details@streams@Concurrency@@AEAAHH@Z; Concurrency::streams::details::streambuf_state_manager<char>::check_sync_read_eof(int)
0x1800c414d  mov     rbx, [rsp+38h+arg_8]
0x1800c4152  add     rsp, 30h
0x1800c4156  pop     rdi
0x1800c4157  retn
```
