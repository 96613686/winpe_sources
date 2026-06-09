# WPP_RECORDER_SF_

- ea: `0x140003bf4`
- end: `0x140003cab`
- name: `WPP_RECORDER_SF_`
- size: `183`
- prototype: ``
- caller_count: `118`
- callee_count: `2`
- tags: ``

## callers

- `0x140001958`
- `0x140001eec`
- `0x14000256c`
- `0x1400031d0`
- `0x140003330`
- `0x140003970`
- `0x140005800`
- `0x1400058c0`
- `0x140005964`
- `0x140005f2c`
- `0x1400060c4`
- `0x140006470`
- `0x140006814`
- `0x140006a04`
- `0x140006bc0`
- `0x1400074d0`
- `0x1400077cc`
- `0x140007d40`
- `0x140008104`
- `0x140008460`
- `0x14000877c`
- `0x140008fd4`
- `0x14000916c`
- `0x1400097f4`
- `0x140009cc8`
- `0x14000a060`
- `0x14000a5f0`
- `0x14000a9d0`
- `0x14000abf0`
- `0x14000aca0`
- `0x14000b090`
- `0x14000b318`
- `0x14000b5b0`
- `0x14000d370`
- `0x14000d4b0`
- `0x14000d660`
- `0x14000d740`
- `0x14000d83c`
- `0x14000da70`
- `0x14000de90`
- `0x14000df68`
- `0x14000e29c`
- `0x14000e4e0`
- `0x14000e840`
- `0x14000ebe0`
- `0x14000ecd0`
- `0x14000ee70`
- `0x14000fc00`
- `0x14000fd78`
- `0x14000fe48`

## callees

- `0x140003bf4`
- `0x14001fc70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003c8e`
- `WppRecorder!WppAutoLogTrace` at `0x140003c8e`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5)
{
  unsigned __int64 v7; // r11
  int v9; // eax
  int v11; // [rsp+20h] [rbp-18h]

  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, 0);
}

```

## disassembly

```asm
0x140003bf4  mov     [rsp+arg_0], rbx
0x140003bf9  mov     [rsp+arg_8], rsi
0x140003bfe  push    rdi
0x140003bff  sub     rsp, 30h
0x140003c03  mov     edi, r8d
0x140003c06  mov     rsi, rcx
0x140003c09  mov     r11d, r8d
0x140003c0c  shr     r11, 10h
0x140003c10  movzx   ebx, r9w
0x140003c14  lea     r10d, [rdi-1]
0x140003c18  mov     edx, r10d
0x140003c1b  and     r10d, 1Fh
0x140003c1f  shr     rdx, 5
0x140003c23  lea     rax, [r11+r11*4]
0x140003c27  and     edx, 7FFh
0x140003c2d  lea     rax, [rdx+rax*4]
0x140003c31  mov     edx, r10d
0x140003c34  mov     r10, cs:WPP_GLOBAL_Control
0x140003c3b  mov     eax, [r10+rax*4+2Ch]
0x140003c40  bt      eax, edx
0x140003c43  jnb     short loc_140003C73
0x140003c45  mov     rax, cs:pfnWppTraceMessage
0x140003c4c  lea     rcx, [r11+r11*4]
0x140003c50  mov     r8, [rsp+38h+arg_20]
0x140003c55  add     rcx, rcx
0x140003c58  mov     r9d, ebx
0x140003c5b  mov     [rsp+38h+var_18], 0
0x140003c64  mov     edx, 2Bh ; '+'
0x140003c69  mov     rcx, [r10+rcx*8+18h]
0x140003c6e  call    _guard_dispatch_icall
0x140003c73  mov     r9, [rsp+38h+arg_20]
0x140003c78  mov     r8d, edi
0x140003c7b  mov     [rsp+38h+var_10], 0
0x140003c84  xor     edx, edx
0x140003c86  mov     rcx, rsi
0x140003c89  mov     word ptr [rsp+38h+var_18], bx
0x140003c8e  call    cs:__imp_WppAutoLogTrace
0x140003c95  nop     dword ptr [rax+rax+00h]
0x140003c9a  mov     rbx, [rsp+38h+arg_0]
0x140003c9f  mov     rsi, [rsp+38h+arg_8]
0x140003ca4  add     rsp, 30h
0x140003ca8  pop     rdi
0x140003ca9  retn
```
