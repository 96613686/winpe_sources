# Concurrency::streams::details::streambuf_state_manager<char>::scopy(char *,unsigned __int64)

- ea: `0x1800c35f0`
- end: `0x1800c3676`
- name: `?scopy@?$streambuf_state_manager@D@details@streams@Concurrency@@UEAA_KPEAD_K@Z`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800c35f0`
- `0x180101010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c3622`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1800c3622`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800c3606`
- `msvcp_win!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1800c3606`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800c3637`
- `msvcp_win!?__ExceptionPtrRethrow@@YAXPEBX@Z` at `0x1800c3637`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::streams::details::streambuf_state_manager<char>::scopy(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _OWORD v7[3]; // [rsp+20h] [rbp-38h] BYREF

  if ( __ExceptionPtrToBool((const void *)(a1 + 24)) )
  {
    v7[0] = 0;
    __ExceptionPtrCopy(v7, (const void *)(a1 + 24));
    __ExceptionPtrRethrow(v7);
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1) )
    return (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)a1 + 344LL))(a1, a2, a3);
  else
    return 0;
}

```

## disassembly

```asm
0x1800c35f0  push    rbx
0x1800c35f2  push    rbp
0x1800c35f3  push    rsi
0x1800c35f4  push    rdi
0x1800c35f5  sub     rsp, 38h
0x1800c35f9  mov     rsi, r8
0x1800c35fc  mov     rbp, rdx
0x1800c35ff  mov     rbx, rcx
0x1800c3602  add     rcx, 18h
0x1800c3606  call    cs:__imp_?__ExceptionPtrToBool@@YA_NPEBX@Z; __ExceptionPtrToBool(void const *)
0x1800c360c  test    al, al
0x1800c360e  jz      short loc_1800C363E
0x1800c3610  xorps   xmm0, xmm0
0x1800c3613  movdqu  [rsp+58h+var_38], xmm0
0x1800c3619  lea     rdx, [rbx+18h]
0x1800c361d  lea     rcx, [rsp+58h+var_38]
0x1800c3622  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x1800c3628  lea     rax, [rsp+58h+var_38]
0x1800c362d  mov     [rsp+58h+arg_0], rax
0x1800c3632  lea     rcx, [rsp+58h+var_38]
0x1800c3637  call    cs:__imp_?__ExceptionPtrRethrow@@YAXPEBX@Z; __ExceptionPtrRethrow(void const *)
0x1800c363d  nop
0x1800c363e  mov     rax, [rbx]
0x1800c3641  mov     rcx, rbx
0x1800c3644  mov     rax, [rax+8]
0x1800c3648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c364d  test    al, al
0x1800c364f  jnz     short loc_1800C3655
0x1800c3651  xor     eax, eax
0x1800c3653  jmp     short loc_1800C366D
0x1800c3655  mov     rax, [rbx]
0x1800c3658  mov     r8, rsi
0x1800c365b  mov     rdx, rbp
0x1800c365e  mov     rcx, rbx
0x1800c3661  mov     rax, [rax+158h]
0x1800c3668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c366d  add     rsp, 38h
0x1800c3671  pop     rdi
0x1800c3672  pop     rsi
0x1800c3673  pop     rbp
0x1800c3674  pop     rbx
0x1800c3675  retn
```
