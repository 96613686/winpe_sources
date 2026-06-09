# WPP_RECORDER_SF_q

- ea: `0x140004a68`
- end: `0x140004b45`
- name: `WPP_RECORDER_SF_q`
- size: `221`
- prototype: ``
- caller_count: `52`
- callee_count: `2`
- tags: ``

## callers

- `0x140001958`
- `0x140001b30`
- `0x140001d24`
- `0x14000280c`
- `0x140002ac8`
- `0x140002e20`
- `0x1400035cc`
- `0x140003868`
- `0x1400038fc`
- `0x140005560`
- `0x140005630`
- `0x140005700`
- `0x140005800`
- `0x1400058c0`
- `0x140006750`
- `0x140006814`
- `0x140006a04`
- `0x1400070c8`
- `0x140007200`
- `0x140007d40`
- `0x140008104`
- `0x140008460`
- `0x14000877c`
- `0x14000916c`
- `0x140009658`
- `0x14000a9d0`
- `0x14000aca0`
- `0x14000b090`
- `0x14000d970`
- `0x14000e094`
- `0x14000e700`
- `0x1400114c0`
- `0x14001190c`
- `0x140012c60`
- `0x1400135cc`
- `0x140013abc`
- `0x140013bf8`
- `0x140013d20`
- `0x140014eb4`
- `0x140015c4c`
- `0x1400161d0`
- `0x14001737c`
- `0x14001812c`
- `0x140018230`
- `0x1400185c8`
- `0x140018e9c`
- `0x1400195d0`
- `0x140019b64`
- `0x140019e5c`
- `0x140019f70`

## callees

- `0x140004a68`
- `0x14001fc70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004b28`
- `WppRecorder!WppAutoLogTrace` at `0x140004b28`

## pseudocode

```c
__int64 WPP_RECORDER_SF_q(__int64 a1, _DWORD a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
      8,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, va);
}

```

## disassembly

```asm
0x140004a68  mov     [rsp+arg_0], rbx
0x140004a6d  mov     [rsp+arg_8], rsi
0x140004a72  push    rdi
0x140004a73  sub     rsp, 40h
0x140004a77  mov     edi, r8d
0x140004a7a  mov     rsi, rcx
0x140004a7d  mov     r11d, r8d
0x140004a80  shr     r11, 10h
0x140004a84  movzx   ebx, r9w
0x140004a88  lea     r10d, [rdi-1]
0x140004a8c  mov     edx, r10d
0x140004a8f  and     r10d, 1Fh
0x140004a93  shr     rdx, 5
0x140004a97  lea     rax, [r11+r11*4]
0x140004a9b  and     edx, 7FFh
0x140004aa1  lea     rax, [rdx+rax*4]
0x140004aa5  mov     edx, r10d
0x140004aa8  mov     r10, cs:WPP_GLOBAL_Control
0x140004aaf  mov     eax, [r10+rax*4+2Ch]
0x140004ab4  bt      eax, edx
0x140004ab7  jnb     short loc_140004AFA
0x140004ab9  mov     rax, cs:pfnWppTraceMessage
0x140004ac0  lea     rdx, [rsp+48h+arg_28]
0x140004ac5  mov     r8, [rsp+48h+arg_20]
0x140004aca  lea     rcx, [r11+r11*4]
0x140004ace  add     rcx, rcx
0x140004ad1  mov     [rsp+48h+var_18], 0
0x140004ada  mov     [rsp+48h+var_20], 8
0x140004ae3  mov     r9d, ebx
0x140004ae6  mov     [rsp+48h+var_28], rdx
0x140004aeb  mov     edx, 2Bh ; '+'
0x140004af0  mov     rcx, [r10+rcx*8+18h]
0x140004af5  call    _guard_dispatch_icall
0x140004afa  mov     r9, [rsp+48h+arg_20]
0x140004aff  lea     rax, [rsp+48h+arg_28]
0x140004b04  mov     [rsp+48h+var_10], 0
0x140004b0d  mov     r8d, edi
0x140004b10  mov     [rsp+48h+var_18], 8
0x140004b19  xor     edx, edx
0x140004b1b  mov     [rsp+48h+var_20], rax
0x140004b20  mov     rcx, rsi
0x140004b23  mov     word ptr [rsp+48h+var_28], bx
0x140004b28  call    cs:__imp_WppAutoLogTrace
0x140004b2f  nop     dword ptr [rax+rax+00h]
0x140004b34  mov     rbx, [rsp+48h+arg_0]
0x140004b39  mov     rsi, [rsp+48h+arg_8]
0x140004b3e  add     rsp, 40h
0x140004b42  pop     rdi
0x140004b43  retn
```
