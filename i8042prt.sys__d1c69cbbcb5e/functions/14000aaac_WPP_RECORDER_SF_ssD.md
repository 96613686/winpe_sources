# WPP_RECORDER_SF_ssD

- ea: `0x14000aaac`
- end: `0x14000ac35`
- name: `WPP_RECORDER_SF_ssD`
- size: `393`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140017f98`
- `0x14001a7ac`

## callees

- `0x14000aaac`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000ac19`
- `WppRecorder!WppAutoLogTrace` at `0x14000ac19`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_ssD(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int16 a4,
        __int64 a5,
        const char *a6,
        const char *a7)
{
  __int64 v7; // rdi
  const char *v8; // rsi
  __int64 v11; // rax
  const char *v12; // rdx
  __int64 v13; // rax
  __int64 v14; // r8
  const char *v15; // rcx
  __int64 v16; // rax
  bool v17; // zf
  int v19; // [rsp+20h] [rbp-78h]

  v7 = -1;
  v8 = a6;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
  {
    if ( a7 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a7[v11] );
    }
    v12 = a7;
    if ( !a7 )
      v12 = "NULL";
    if ( a6 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a6[v13] );
      v14 = v13 + 1;
    }
    else
    {
      v14 = 5;
    }
    v15 = a6;
    if ( !a6 )
      v15 = "NULL";
    pfnWppTraceMessage(WPP_GLOBAL_Control->AttachedDevice, 43, a5, a4, v15, v14, v12);
  }
  if ( a7 )
  {
    v16 = -1;
    do
      ++v16;
    while ( a7[v16] );
  }
  v17 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v17 = a6 == 0;
  }
  if ( v17 )
    v8 = "NULL";
  LOWORD(v19) = a4;
  return WppAutoLogTrace(a1, 0, 16, a5, v19, v8);
}

```

## disassembly

```asm
0x14000aaac  push    rbx
0x14000aaae  push    rbp
0x14000aaaf  push    rsi
0x14000aab0  push    rdi
0x14000aab1  push    r13
0x14000aab3  push    r14
0x14000aab5  push    r15
0x14000aab7  sub     rsp, 60h
0x14000aabb  mov     rax, cs:WPP_GLOBAL_Control
0x14000aac2  lea     r13, aNull; "NULL"
0x14000aac9  mov     rbx, [rsp+98h+arg_30]
0x14000aad1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000aad5  mov     rsi, [rsp+98h+arg_28]
0x14000aadd  mov     r15, rcx
0x14000aae0  movzx   r14d, r9w
0x14000aae4  test    dword ptr [rax+2Ch], 8000h
0x14000aaeb  lea     ebp, [rdi+6]
0x14000aaee  jz      loc_14000AB96
0x14000aaf4  test    rbx, rbx
0x14000aaf7  jz      short loc_14000AB0B
0x14000aaf9  mov     rax, rdi
0x14000aafc  inc     rax
0x14000aaff  cmp     byte ptr [rbx+rax], 0
0x14000ab03  jnz     short loc_14000AAFC
0x14000ab05  lea     r9, [rax+1]
0x14000ab09  jmp     short loc_14000AB0E
0x14000ab0b  mov     r9, rbp
0x14000ab0e  test    rbx, rbx
0x14000ab11  mov     rdx, rbx
0x14000ab14  cmovz   rdx, r13
0x14000ab18  test    rsi, rsi
0x14000ab1b  jz      short loc_14000AB2F
0x14000ab1d  mov     rax, rdi
0x14000ab20  inc     rax
0x14000ab23  cmp     byte ptr [rsi+rax], 0
0x14000ab27  jnz     short loc_14000AB20
0x14000ab29  lea     r8, [rax+1]
0x14000ab2d  jmp     short loc_14000AB32
0x14000ab2f  mov     r8, rbp
0x14000ab32  mov     rax, cs:pfnWppTraceMessage
0x14000ab39  lea     r10, [rsp+98h+arg_38]
0x14000ab41  mov     [rsp+98h+var_48], 0
0x14000ab4a  test    rsi, rsi
0x14000ab4d  mov     [rsp+98h+var_50], 4
0x14000ab56  mov     rcx, rsi
0x14000ab59  mov     [rsp+98h+var_58], r10
0x14000ab5e  cmovz   rcx, r13
0x14000ab62  mov     [rsp+98h+var_60], r9
0x14000ab67  mov     r9d, r14d
0x14000ab6a  mov     [rsp+98h+var_68], rdx
0x14000ab6f  mov     edx, 2Bh ; '+'
0x14000ab74  mov     [rsp+98h+var_70], r8
0x14000ab79  mov     r8, [rsp+98h+arg_20]
0x14000ab81  mov     [rsp+98h+var_78], rcx
0x14000ab86  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ab8d  mov     rcx, [rcx+18h]
0x14000ab91  call    _guard_dispatch_icall
0x14000ab96  test    rbx, rbx
0x14000ab99  jz      short loc_14000ABAC
0x14000ab9b  mov     rax, rdi
0x14000ab9e  inc     rax
0x14000aba1  cmp     byte ptr [rbx+rax], 0
0x14000aba5  jnz     short loc_14000AB9E
0x14000aba7  inc     rax
0x14000abaa  jmp     short loc_14000ABAF
0x14000abac  mov     rax, rbp
0x14000abaf  test    rbx, rbx
0x14000abb2  cmovz   rbx, r13
0x14000abb6  test    rsi, rsi
0x14000abb9  jz      short loc_14000ABCB
0x14000abbb  inc     rdi
0x14000abbe  cmp     byte ptr [rsi+rdi], 0
0x14000abc2  jnz     short loc_14000ABBB
0x14000abc4  lea     rbp, [rdi+1]
0x14000abc8  test    rsi, rsi
0x14000abcb  mov     r9, [rsp+98h+arg_20]
0x14000abd3  lea     rcx, [rsp+98h+arg_38]
0x14000abdb  mov     [rsp+98h+var_40], 0
0x14000abe4  cmovz   rsi, r13
0x14000abe8  mov     [rsp+98h+var_48], 4
0x14000abf1  xor     edx, edx
0x14000abf3  mov     [rsp+98h+var_50], rcx
0x14000abf8  mov     rcx, r15
0x14000abfb  mov     [rsp+98h+var_58], rax
0x14000ac00  mov     [rsp+98h+var_60], rbx
0x14000ac05  mov     [rsp+98h+var_68], rbp
0x14000ac0a  lea     r8d, [rdx+10h]
0x14000ac0e  mov     [rsp+98h+var_70], rsi
0x14000ac13  mov     word ptr [rsp+98h+var_78], r14w
0x14000ac19  call    cs:__imp_WppAutoLogTrace
0x14000ac20  nop     dword ptr [rax+rax+00h]
0x14000ac25  add     rsp, 60h
0x14000ac29  pop     r15
0x14000ac2b  pop     r14
0x14000ac2d  pop     r13
0x14000ac2f  pop     rdi
0x14000ac30  pop     rsi
0x14000ac31  pop     rbp
0x14000ac32  pop     rbx
0x14000ac33  retn
```
