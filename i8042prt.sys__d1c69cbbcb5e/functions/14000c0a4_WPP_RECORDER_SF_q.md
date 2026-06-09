# WPP_RECORDER_SF_q

- ea: `0x14000c0a4`
- end: `0x14000c181`
- name: `WPP_RECORDER_SF_q`
- size: `221`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400080e0`
- `0x14000b5f4`
- `0x14000b8a8`
- `0x14000d610`

## callees

- `0x14000c0a4`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x14000c164`
- `WppRecorder!WppAutoLogTrace` at `0x14000c164`

## pseudocode

```c
__int64 WPP_RECORDER_SF_q(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // r11
  int v9; // eax
  int v11; // [rsp+20h] [rbp-28h]
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) )
    pfnWppTraceMessage(*((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7), 43, a5, a4, va, 8, 0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, va);
}

```

## disassembly

```asm
0x14000c0a4  mov     [rsp+arg_0], rbx
0x14000c0a9  mov     [rsp+arg_8], rsi
0x14000c0ae  push    rdi
0x14000c0af  sub     rsp, 40h
0x14000c0b3  mov     edi, r8d
0x14000c0b6  mov     rsi, rcx
0x14000c0b9  mov     r11d, r8d
0x14000c0bc  shr     r11, 10h
0x14000c0c0  movzx   ebx, r9w
0x14000c0c4  lea     r10d, [rdi-1]
0x14000c0c8  mov     edx, r10d
0x14000c0cb  and     r10d, 1Fh
0x14000c0cf  shr     rdx, 5
0x14000c0d3  lea     rax, [r11+r11*4]
0x14000c0d7  and     edx, 7FFh
0x14000c0dd  lea     rax, [rdx+rax*4]
0x14000c0e1  mov     edx, r10d
0x14000c0e4  mov     r10, cs:WPP_GLOBAL_Control
0x14000c0eb  mov     eax, [r10+rax*4+2Ch]
0x14000c0f0  bt      eax, edx
0x14000c0f3  jnb     short loc_14000C136
0x14000c0f5  mov     rax, cs:pfnWppTraceMessage
0x14000c0fc  lea     rdx, [rsp+48h+arg_28]
0x14000c101  mov     r8, [rsp+48h+arg_20]
0x14000c106  lea     rcx, [r11+r11*4]
0x14000c10a  add     rcx, rcx
0x14000c10d  mov     [rsp+48h+var_18], 0
0x14000c116  mov     [rsp+48h+var_20], 8
0x14000c11f  mov     r9d, ebx
0x14000c122  mov     [rsp+48h+var_28], rdx
0x14000c127  mov     edx, 2Bh ; '+'
0x14000c12c  mov     rcx, [r10+rcx*8+18h]
0x14000c131  call    _guard_dispatch_icall
0x14000c136  mov     r9, [rsp+48h+arg_20]
0x14000c13b  lea     rax, [rsp+48h+arg_28]
0x14000c140  mov     [rsp+48h+var_10], 0
0x14000c149  mov     r8d, edi
0x14000c14c  mov     [rsp+48h+var_18], 8
0x14000c155  xor     edx, edx
0x14000c157  mov     [rsp+48h+var_20], rax
0x14000c15c  mov     rcx, rsi
0x14000c15f  mov     word ptr [rsp+48h+var_28], bx
0x14000c164  call    cs:__imp_WppAutoLogTrace
0x14000c16b  nop     dword ptr [rax+rax+00h]
0x14000c170  mov     rbx, [rsp+48h+arg_0]
0x14000c175  mov     rsi, [rsp+48h+arg_8]
0x14000c17a  add     rsp, 40h
0x14000c17e  pop     rdi
0x14000c17f  retn
```
