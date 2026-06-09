# WPP_RECORDER_SF_sD

- ea: `0x140008a10`
- end: `0x140008b75`
- name: `WPP_RECORDER_SF_sD`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14001eda0`
- `0x14001fa30`

## callees

- `0x140008a10`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140008b59`
- `WppRecorder!WppAutoLogTrace` at `0x140008b59`

## pseudocode

```c
__int64 WPP_RECORDER_SF_sD(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        const char *a6,
        ...)
{
  const char *v6; // rdi
  __int64 v9; // rbx
  unsigned __int64 v10; // r14
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rcx
  const char *v15; // rdx
  bool v16; // zf
  int v18; // [rsp+20h] [rbp-68h]
  va_list va; // [rsp+C0h] [rbp+38h] BYREF

  va_start(va, a6);
  v6 = a6;
  v9 = -1;
  v10 = (unsigned __int64)a3 >> 16;
  v12 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v10 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v12, a3 - 1) )
  {
    if ( a6 )
    {
      v13 = -1;
      do
        v16 = a6[++v13] == 0;
      while ( !v16 );
      v14 = v13 + 1;
    }
    else
    {
      v14 = 5;
    }
    v15 = a6;
    if ( !a6 )
      v15 = "NULL";
    pfnWppTraceMessage(*((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v10), 43, a5, a4, v15, v14, va);
  }
  v16 = a6 == 0;
  if ( a6 )
  {
    do
      v16 = a6[++v9] == 0;
    while ( !v16 );
    v16 = a6 == 0;
  }
  if ( v16 )
    v6 = "NULL";
  LOWORD(v18) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v18, v6);
}

```

## disassembly

```asm
0x140008a10  push    rbx
0x140008a12  push    rbp
0x140008a13  push    rsi
0x140008a14  push    rdi
0x140008a15  push    r13
0x140008a17  push    r14
0x140008a19  push    r15
0x140008a1b  sub     rsp, 50h
0x140008a1f  mov     rdi, [rsp+88h+arg_28]
0x140008a27  mov     r13, rcx
0x140008a2a  mov     ebp, r8d
0x140008a2d  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140008a34  mov     r14d, r8d
0x140008a37  mov     esi, 5
0x140008a3c  shr     r14, 10h
0x140008a40  lea     r8, aNull; "NULL"
0x140008a47  movzx   r15d, r9w
0x140008a4b  lea     r11d, [rbp-1]
0x140008a4f  mov     edx, r11d
0x140008a52  shr     rdx, 5
0x140008a56  lea     rax, [r14+r14*4]
0x140008a5a  and     edx, 7FFh
0x140008a60  lea     r10, [rdx+rax*4]
0x140008a64  mov     rax, cs:WPP_GLOBAL_Control
0x140008a6b  mov     ecx, [rax+r10*4+2Ch]
0x140008a70  bt      ecx, r11d
0x140008a74  jnb     loc_140008AFF
0x140008a7a  test    rdi, rdi
0x140008a7d  jz      short loc_140008A93
0x140008a7f  mov     rax, rbx
0x140008a82  cmp     byte ptr [rdi+rax+1], 0
0x140008a87  lea     rax, [rax+1]
0x140008a8b  jnz     short loc_140008A82
0x140008a8d  lea     rcx, [rax+1]
0x140008a91  jmp     short loc_140008A96
0x140008a93  mov     rcx, rsi
0x140008a96  mov     rax, cs:pfnWppTraceMessage
0x140008a9d  lea     r10, [r14+r14*4]
0x140008aa1  mov     [rsp+88h+var_48], 0
0x140008aaa  test    rdi, rdi
0x140008aad  mov     [rsp+88h+var_50], 4
0x140008ab6  mov     rdx, rdi
0x140008ab9  cmovz   rdx, r8
0x140008abd  mov     r9d, r15d
0x140008ac0  lea     r8, [rsp+88h+arg_30]
0x140008ac8  add     r10, r10
0x140008acb  mov     [rsp+88h+var_58], r8
0x140008ad0  mov     r8, [rsp+88h+arg_20]
0x140008ad8  mov     [rsp+88h+var_60], rcx
0x140008add  mov     rcx, cs:WPP_GLOBAL_Control
0x140008ae4  mov     [rsp+88h+var_68], rdx
0x140008ae9  mov     edx, 2Bh ; '+'
0x140008aee  mov     rcx, [rcx+r10*8+18h]
0x140008af3  call    _guard_dispatch_icall
0x140008af8  lea     r8, aNull; "NULL"
0x140008aff  test    rdi, rdi
0x140008b02  jz      short loc_140008B16
0x140008b04  cmp     byte ptr [rdi+rbx+1], 0
0x140008b09  lea     rbx, [rbx+1]
0x140008b0d  jnz     short loc_140008B04
0x140008b0f  lea     rsi, [rbx+1]
0x140008b13  test    rdi, rdi
0x140008b16  mov     r9, [rsp+88h+arg_20]
0x140008b1e  lea     rax, [rsp+88h+arg_30]
0x140008b26  mov     [rsp+88h+var_40], 0
0x140008b2f  cmovz   rdi, r8
0x140008b33  mov     [rsp+88h+var_48], 4
0x140008b3c  mov     r8d, ebp
0x140008b3f  mov     [rsp+88h+var_50], rax
0x140008b44  xor     edx, edx
0x140008b46  mov     [rsp+88h+var_58], rsi
0x140008b4b  mov     rcx, r13
0x140008b4e  mov     [rsp+88h+var_60], rdi
0x140008b53  mov     word ptr [rsp+88h+var_68], r15w
0x140008b59  call    cs:__imp_WppAutoLogTrace
0x140008b60  nop     dword ptr [rax+rax+00h]
0x140008b65  add     rsp, 50h
0x140008b69  pop     r15
0x140008b6b  pop     r14
0x140008b6d  pop     r13
0x140008b6f  pop     rdi
0x140008b70  pop     rsi
0x140008b71  pop     rbp
0x140008b72  pop     rbx
0x140008b73  retn
```
