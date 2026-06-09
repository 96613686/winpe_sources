# WPP_RECORDER_SF_S

- ea: `0x14000a67c`
- end: `0x14000a7b1`
- name: `WPP_RECORDER_SF_S`
- size: `309`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140018bf0`
- `0x14001908c`
- `0x140019cfc`
- `0x14001b830`

## callees

- `0x14000a67c`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000a793`
- `WppRecorder!WppAutoLogTrace` at `0x14000a793`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_S(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned __int16 a4,
        __int64 a5,
        const wchar_t *a6)
{
  const wchar_t *v6; // rbx
  __int64 v7; // rdi
  unsigned __int64 v10; // r14
  int v12; // ecx
  __int64 v13; // rax
  __int64 v14; // rcx
  const wchar_t *v15; // rdx
  bool v16; // zf
  int v18; // [rsp+20h] [rbp-68h]

  v6 = a6;
  v7 = -1;
  v10 = (unsigned __int64)a3 >> 16;
  v12 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v10 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v12, a3 - 1) )
  {
    if ( a6 )
    {
      v13 = -1;
      do
        ++v13;
      while ( a6[v13] );
      v14 = 2 * v13 + 2;
    }
    else
    {
      v14 = 10;
    }
    v15 = a6;
    if ( !a6 )
      v15 = L"NULL";
    pfnWppTraceMessage(*((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v10), 43, a5, a4, v15, v14, 0);
  }
  v16 = a6 == 0;
  if ( a6 )
  {
    do
      ++v7;
    while ( a6[v7] );
    v16 = a6 == 0;
  }
  if ( v16 )
    v6 = L"NULL";
  LOWORD(v18) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v18, v6);
}

```

## disassembly

```asm
0x14000a67c  push    rbx
0x14000a67e  push    rbp
0x14000a67f  push    rsi
0x14000a680  push    rdi
0x14000a681  push    r12
0x14000a683  push    r13
0x14000a685  push    r14
0x14000a687  push    r15
0x14000a689  sub     rsp, 48h
0x14000a68d  mov     rbx, [rsp+88h+arg_28]
0x14000a695  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000a699  mov     ebp, r8d
0x14000a69c  mov     r12, rcx
0x14000a69f  mov     r14d, r8d
0x14000a6a2  xor     r13d, r13d
0x14000a6a5  shr     r14, 10h
0x14000a6a9  lea     r8, aNull_0; "NULL"
0x14000a6b0  movzx   r15d, r9w
0x14000a6b4  lea     esi, [rdi+0Bh]
0x14000a6b7  lea     r11d, [rbp-1]
0x14000a6bb  mov     edx, r11d
0x14000a6be  shr     rdx, 5
0x14000a6c2  lea     rax, [r14+r14*4]
0x14000a6c6  and     edx, 7FFh
0x14000a6cc  lea     r10, [rdx+rax*4]
0x14000a6d0  mov     rax, cs:WPP_GLOBAL_Control
0x14000a6d7  mov     ecx, [rax+r10*4+2Ch]
0x14000a6dc  bt      ecx, r11d
0x14000a6e0  jnb     short loc_14000A750
0x14000a6e2  test    rbx, rbx
0x14000a6e5  jz      short loc_14000A6FE
0x14000a6e7  mov     rax, rdi
0x14000a6ea  inc     rax
0x14000a6ed  cmp     [rbx+rax*2], r13w
0x14000a6f2  jnz     short loc_14000A6EA
0x14000a6f4  lea     rcx, ds:2[rax*2]
0x14000a6fc  jmp     short loc_14000A701
0x14000a6fe  mov     rcx, rsi
0x14000a701  mov     rax, cs:pfnWppTraceMessage
0x14000a708  lea     r10, [r14+r14*4]
0x14000a70c  test    rbx, rbx
0x14000a70f  mov     [rsp+88h+var_58], r13
0x14000a714  mov     [rsp+88h+var_60], rcx
0x14000a719  mov     rdx, rbx
0x14000a71c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a723  cmovz   rdx, r8
0x14000a727  mov     r8, [rsp+88h+arg_20]
0x14000a72f  add     r10, r10
0x14000a732  mov     [rsp+88h+var_68], rdx
0x14000a737  mov     r9d, r15d
0x14000a73a  mov     edx, 2Bh ; '+'
0x14000a73f  mov     rcx, [rcx+r10*8+18h]
0x14000a744  call    _guard_dispatch_icall
0x14000a749  lea     r8, aNull_0; "NULL"
0x14000a750  test    rbx, rbx
0x14000a753  jz      short loc_14000A76A
0x14000a755  inc     rdi
0x14000a758  cmp     [rbx+rdi*2], r13w
0x14000a75d  jnz     short loc_14000A755
0x14000a75f  lea     rsi, ds:2[rdi*2]
0x14000a767  test    rbx, rbx
0x14000a76a  mov     r9, [rsp+88h+arg_20]
0x14000a772  cmovz   rbx, r8
0x14000a776  mov     [rsp+88h+var_50], r13
0x14000a77b  mov     r8d, ebp
0x14000a77e  mov     [rsp+88h+var_58], rsi
0x14000a783  xor     edx, edx
0x14000a785  mov     [rsp+88h+var_60], rbx
0x14000a78a  mov     rcx, r12
0x14000a78d  mov     word ptr [rsp+88h+var_68], r15w
0x14000a793  call    cs:__imp_WppAutoLogTrace
0x14000a79a  nop     dword ptr [rax+rax+00h]
0x14000a79f  add     rsp, 48h
0x14000a7a3  pop     r15
0x14000a7a5  pop     r14
0x14000a7a7  pop     r13
0x14000a7a9  pop     r12
0x14000a7ab  pop     rdi
0x14000a7ac  pop     rsi
0x14000a7ad  pop     rbp
0x14000a7ae  pop     rbx
0x14000a7af  retn
```
