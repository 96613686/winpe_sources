# WPP_RECORDER_SF_d

- ea: `0x140003cb4`
- end: `0x140003d91`
- name: `WPP_RECORDER_SF_d`
- size: `221`
- prototype: ``
- caller_count: `73`
- callee_count: `2`
- tags: ``

## callers

- `0x1400011ac`
- `0x140001800`
- `0x140001eec`
- `0x140002ac8`
- `0x140003074`
- `0x1400031d0`
- `0x140003330`
- `0x1400035cc`
- `0x140003970`
- `0x140005964`
- `0x140006470`
- `0x140006750`
- `0x140006bc0`
- `0x140007200`
- `0x1400074d0`
- `0x1400077cc`
- `0x140007b60`
- `0x140007d40`
- `0x14000916c`
- `0x140009658`
- `0x140009cc8`
- `0x14000a060`
- `0x14000a380`
- `0x14000a9d0`
- `0x14000aca0`
- `0x14000b4d0`
- `0x14000b5b0`
- `0x14000d4b0`
- `0x14000d740`
- `0x14000d83c`
- `0x14000da70`
- `0x14000df68`
- `0x14000e29c`
- `0x140010810`
- `0x1400114c0`
- `0x1400121d4`
- `0x140012590`
- `0x1400135cc`
- `0x1400147a0`
- `0x1400149b4`
- `0x140014b10`
- `0x140014c64`
- `0x140014eb4`
- `0x14001513c`
- `0x1400152ec`
- `0x14001552c`
- `0x140015688`
- `0x1400162d0`
- `0x140016738`
- `0x14001699c`

## callees

- `0x140003cb4`
- `0x14001fc70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003d74`
- `WppRecorder!WppAutoLogTrace` at `0x140003d74`

## pseudocode

```c
__int64 WPP_RECORDER_SF_d(__int64 a1, _DWORD a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // r11
  int v9; // eax
  int v11; // [rsp+20h] [rbp-28h]
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      va,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, va);
}

```

## disassembly

```asm
0x140003cb4  mov     [rsp+arg_0], rbx
0x140003cb9  mov     [rsp+arg_8], rsi
0x140003cbe  push    rdi
0x140003cbf  sub     rsp, 40h
0x140003cc3  mov     edi, r8d
0x140003cc6  mov     rsi, rcx
0x140003cc9  mov     r11d, r8d
0x140003ccc  shr     r11, 10h
0x140003cd0  movzx   ebx, r9w
0x140003cd4  lea     r10d, [rdi-1]
0x140003cd8  mov     edx, r10d
0x140003cdb  and     r10d, 1Fh
0x140003cdf  shr     rdx, 5
0x140003ce3  lea     rax, [r11+r11*4]
0x140003ce7  and     edx, 7FFh
0x140003ced  lea     rax, [rdx+rax*4]
0x140003cf1  mov     edx, r10d
0x140003cf4  mov     r10, cs:WPP_GLOBAL_Control
0x140003cfb  mov     eax, [r10+rax*4+2Ch]
0x140003d00  bt      eax, edx
0x140003d03  jnb     short loc_140003D46
0x140003d05  mov     rax, cs:pfnWppTraceMessage
0x140003d0c  lea     rdx, [rsp+48h+arg_28]
0x140003d11  mov     r8, [rsp+48h+arg_20]
0x140003d16  lea     rcx, [r11+r11*4]
0x140003d1a  add     rcx, rcx
0x140003d1d  mov     [rsp+48h+var_18], 0
0x140003d26  mov     [rsp+48h+var_20], 4
0x140003d2f  mov     r9d, ebx
0x140003d32  mov     [rsp+48h+var_28], rdx
0x140003d37  mov     edx, 2Bh ; '+'
0x140003d3c  mov     rcx, [r10+rcx*8+18h]
0x140003d41  call    _guard_dispatch_icall
0x140003d46  mov     r9, [rsp+48h+arg_20]
0x140003d4b  lea     rax, [rsp+48h+arg_28]
0x140003d50  mov     [rsp+48h+var_10], 0
0x140003d59  mov     r8d, edi
0x140003d5c  mov     [rsp+48h+var_18], 4
0x140003d65  xor     edx, edx
0x140003d67  mov     [rsp+48h+var_20], rax
0x140003d6c  mov     rcx, rsi
0x140003d6f  mov     word ptr [rsp+48h+var_28], bx
0x140003d74  call    cs:__imp_WppAutoLogTrace
0x140003d7b  nop     dword ptr [rax+rax+00h]
0x140003d80  mov     rbx, [rsp+48h+arg_0]
0x140003d85  mov     rsi, [rsp+48h+arg_8]
0x140003d8a  add     rsp, 40h
0x140003d8e  pop     rdi
0x140003d8f  retn
```
