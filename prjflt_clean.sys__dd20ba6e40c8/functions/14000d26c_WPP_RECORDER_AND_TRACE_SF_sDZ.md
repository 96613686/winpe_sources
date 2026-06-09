# WPP_RECORDER_AND_TRACE_SF_sDZ

- ea: `0x14000d26c`
- end: `0x14000d440`
- name: `WPP_RECORDER_AND_TRACE_SF_sDZ`
- size: `468`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400025f4`
- `0x140005960`
- `0x140028d9c`
- `0x140029d90`
- `0x14002d988`
- `0x14003dd88`
- `0x14003e624`

## callees

- `0x140005cf4`
- `0x14000d26c`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000d41f`
- `WppRecorder!WppAutoLogTrace` at `0x14000d41f`

## pseudocode

```c
__int64 WPP_RECORDER_AND_TRACE_SF_sDZ(
        __int16 a1,
        char a2,
        char a3,
        __int64 a4,
        unsigned __int8 a5,
        unsigned int a6,
        USHORT a7,
        ULONGLONG a8,
        const char *a9,
        ...)
{
  const wchar_t *v9; // rbx
  const wchar_t *v10; // r15
  const char *v11; // rdi
  __int64 v12; // rbp
  __int64 v13; // rsi
  __int64 result; // rax
  __int64 v16; // r14
  __int64 v18; // rcx
  const wchar_t *v19; // r8
  const wchar_t *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  const char *v23; // r9
  bool v24; // zf
  bool v25; // zf
  int v26; // [rsp+20h] [rbp-A8h]
  __int64 v27; // [rsp+78h] [rbp-50h]
  __int64 v28; // [rsp+80h] [rbp-48h]
  __int64 v29; // [rsp+88h] [rbp-40h]
  __int64 v30; // [rsp+90h] [rbp-38h]
  __int64 v31; // [rsp+98h] [rbp-30h]
  __int64 v32; // [rsp+A0h] [rbp-28h]
  __int64 v33; // [rsp+A8h] [rbp-20h]
  __int64 v35; // [rsp+118h] [rbp+50h] BYREF
  va_list va; // [rsp+118h] [rbp+50h]
  unsigned __int16 *v37; // [rsp+120h] [rbp+58h]
  va_list va1; // [rsp+128h] [rbp+60h] BYREF

  va_start(va1, a9);
  va_start(va, a9);
  v35 = va_arg(va1, _QWORD);
  v37 = va_arg(va1, unsigned __int16 *);
  v9 = v37;
  v10 = L"NULL";
  v11 = a9;
  v12 = 8;
  v13 = -1;
  result = a4;
  v16 = 5;
  if ( !a2 )
    goto LABEL_17;
  if ( !v37 )
  {
    v18 = 8;
    goto LABEL_6;
  }
  v18 = *v37;
  if ( !*v37 )
  {
LABEL_6:
    v19 = L"NULL";
    goto LABEL_7;
  }
  v19 = (const wchar_t *)*((_QWORD *)v37 + 1);
LABEL_7:
  v20 = v37;
  if ( !v37 )
    v20 = L"\b";
  if ( a9 )
  {
    v21 = -1;
    do
      ++v21;
    while ( a9[v21] );
    v22 = v21 + 1;
  }
  else
  {
    v22 = 5;
  }
  v23 = a9;
  if ( !a9 )
    v23 = "NULL";
  FastWppTraceMessage(a1, a7, a8, v23, v22, va, 4, v20, 2, v19, v18, 0);
  result = a4;
LABEL_17:
  if ( a3 )
  {
    v24 = v9 == 0;
    if ( v9 )
    {
      v12 = *v9;
      if ( *v9 )
        v10 = (const wchar_t *)*((_QWORD *)v9 + 1);
      v24 = v9 == 0;
    }
    if ( v24 )
      v9 = L"\b";
    v25 = a9 == 0;
    if ( a9 )
    {
      do
        ++v13;
      while ( a9[v13] );
      v16 = v13 + 1;
      v25 = a9 == 0;
    }
    if ( v25 )
      v11 = "NULL";
    LOWORD(v26) = a7;
    return WppAutoLogTrace(
             result,
             a5,
             a6,
             a8,
             v26,
             v11,
             v16,
             (__int64 *)va,
             4,
             v9,
             2,
             v10,
             v12,
             0,
             "NULL",
             v27,
             v28,
             v29,
             v30,
             v31,
             v32,
             v33);
  }
  return result;
}

```

## disassembly

```asm
0x14000d26c  mov     [rsp+arg_18], r9
0x14000d271  push    rbx
0x14000d272  push    rbp
0x14000d273  push    rsi
0x14000d274  push    rdi
0x14000d275  push    r12
0x14000d277  push    r13
0x14000d279  push    r14
0x14000d27b  push    r15
0x14000d27d  sub     rsp, 88h
0x14000d284  mov     rbx, [rsp+0C8h+arg_50]
0x14000d28c  lea     r15, aNull_0; "NULL"
0x14000d293  mov     rdi, [rsp+0C8h+arg_40]
0x14000d29b  mov     ebp, 8
0x14000d2a0  movzx   r13d, [rsp+0C8h+arg_30]
0x14000d2a9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000d2ad  movzx   r10d, cx
0x14000d2b1  xor     r11d, r11d
0x14000d2b4  lea     rcx, aNull; "NULL"
0x14000d2bb  mov     rax, r9
0x14000d2be  mov     [rsp+0C8h+var_58], rcx
0x14000d2c3  lea     r14d, [rbp-3]
0x14000d2c7  lea     r9, asc_1400156D4; "\b"
0x14000d2ce  mov     r12b, r8b
0x14000d2d1  test    dl, dl
0x14000d2d3  jz      loc_14000D386
0x14000d2d9  test    rbx, rbx
0x14000d2dc  jz      short loc_14000D2ED
0x14000d2de  movzx   ecx, word ptr [rbx]
0x14000d2e1  cmp     [rbx], r11w
0x14000d2e5  jz      short loc_14000D2F0
0x14000d2e7  mov     r8, [rbx+8]
0x14000d2eb  jmp     short loc_14000D2F3
0x14000d2ed  mov     rcx, rbp
0x14000d2f0  mov     r8, r15
0x14000d2f3  test    rbx, rbx
0x14000d2f6  mov     rdx, rbx
0x14000d2f9  cmovz   rdx, r9
0x14000d2fd  test    rdi, rdi
0x14000d300  jz      short loc_14000D313
0x14000d302  mov     rax, rsi
0x14000d305  inc     rax
0x14000d308  cmp     [rdi+rax], r11b
0x14000d30c  jnz     short loc_14000D305
0x14000d30e  inc     rax
0x14000d311  jmp     short loc_14000D316
0x14000d313  mov     rax, r14
0x14000d316  mov     [rsp+0C8h+var_70], r11
0x14000d31b  test    rdi, rdi
0x14000d31e  mov     [rsp+0C8h+var_78], rcx
0x14000d323  mov     r9, rdi
0x14000d326  cmovz   r9, [rsp+0C8h+var_58]
0x14000d32c  lea     rcx, [rsp+0C8h+arg_48]
0x14000d334  mov     [rsp+0C8h+var_80], r8
0x14000d339  mov     r8, [rsp+0C8h+arg_38]
0x14000d341  mov     [rsp+0C8h+var_88], 2
0x14000d34a  mov     [rsp+0C8h+var_90], rdx
0x14000d34f  mov     edx, r13d
0x14000d352  mov     [rsp+0C8h+var_98], 4
0x14000d35b  mov     [rsp+0C8h+var_A0], rcx
0x14000d360  mov     ecx, r10d
0x14000d363  mov     [rsp+0C8h+var_A8], rax
0x14000d368  call    FastWppTraceMessage
0x14000d36d  mov     rax, [rsp+0C8h+arg_18]
0x14000d375  lea     r9, asc_1400156D4; "\b"
0x14000d37c  xor     r11d, r11d
0x14000d37f  lea     rcx, aNull; "NULL"
0x14000d386  test    r12b, r12b
0x14000d389  jz      loc_14000D42B
0x14000d38f  test    rbx, rbx
0x14000d392  jz      short loc_14000D3A4
0x14000d394  movzx   ebp, word ptr [rbx]
0x14000d397  cmp     [rbx], r11w
0x14000d39b  jz      short loc_14000D3A1
0x14000d39d  mov     r15, [rbx+8]
0x14000d3a1  test    rbx, rbx
0x14000d3a4  cmovz   rbx, r9
0x14000d3a8  test    rdi, rdi
0x14000d3ab  jz      short loc_14000D3BD
0x14000d3ad  inc     rsi
0x14000d3b0  cmp     [rdi+rsi], r11b
0x14000d3b4  jnz     short loc_14000D3AD
0x14000d3b6  lea     r14, [rsi+1]
0x14000d3ba  test    rdi, rdi
0x14000d3bd  mov     r9, [rsp+0C8h+arg_38]
0x14000d3c5  cmovz   rdi, rcx
0x14000d3c9  mov     r8d, [rsp+0C8h+arg_28]
0x14000d3d1  lea     rcx, [rsp+0C8h+arg_48]
0x14000d3d9  movzx   edx, [rsp+0C8h+arg_20]
0x14000d3e1  mov     [rsp+0C8h+var_60], r11
0x14000d3e6  mov     [rsp+0C8h+var_68], rbp
0x14000d3eb  mov     [rsp+0C8h+var_70], r15
0x14000d3f0  mov     [rsp+0C8h+var_78], 2
0x14000d3f9  mov     [rsp+0C8h+var_80], rbx
0x14000d3fe  mov     [rsp+0C8h+var_88], 4
0x14000d407  mov     [rsp+0C8h+var_90], rcx
0x14000d40c  mov     rcx, rax
0x14000d40f  mov     [rsp+0C8h+var_98], r14
0x14000d414  mov     [rsp+0C8h+var_A0], rdi
0x14000d419  mov     word ptr [rsp+0C8h+var_A8], r13w
0x14000d41f  call    cs:__imp_WppAutoLogTrace
0x14000d426  nop     dword ptr [rax+rax+00h]
0x14000d42b  add     rsp, 88h
0x14000d432  pop     r15
0x14000d434  pop     r14
0x14000d436  pop     r13
0x14000d438  pop     r12
0x14000d43a  pop     rdi
0x14000d43b  pop     rsi
0x14000d43c  pop     rbp
0x14000d43d  pop     rbx
0x14000d43e  retn
```
