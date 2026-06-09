# WPP_RECORDER_SF_d

- ea: `0x140005c9c`
- end: `0x140005d7f`
- name: `WPP_RECORDER_SF_d`
- size: `227`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003470`
- `0x140011660`

## callees

- `0x140005c9c`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140005d67`
- `WppRecorder!WppAutoLogTrace` at `0x140005d67`

## pseudocode

```c
__int64 WPP_RECORDER_SF_d(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, int a5, ...)
{
  unsigned __int64 v7; // rbx
  unsigned int v9; // edi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-48h]
  va_list va; // [rsp+98h] [rbp+30h] BYREF

  va_start(va, a5);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, a3 - 1) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64 *, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids,
      a4,
      va,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v9, a3, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids, v12, va);
}

```

## disassembly

```asm
0x140005c9c  push    rbx
0x140005c9e  push    rbp
0x140005c9f  push    rsi
0x140005ca0  push    rdi
0x140005ca1  push    r14
0x140005ca3  sub     rsp, 40h
0x140005ca7  mov     ebp, r8d
0x140005caa  mov     r14, rcx
0x140005cad  mov     ebx, r8d
0x140005cb0  shr     rbx, 10h
0x140005cb4  movzx   esi, r9w
0x140005cb8  lea     r11d, [rbp-1]
0x140005cbc  movzx   edi, dl
0x140005cbf  mov     r10d, r11d
0x140005cc2  shr     r10, 5
0x140005cc6  lea     rax, [rbx+rbx*4]
0x140005cca  and     r10d, 7FFh
0x140005cd1  lea     rax, [r10+rax*4]
0x140005cd5  mov     r10, cs:WPP_GLOBAL_Control
0x140005cdc  mov     eax, [r10+rax*4+2Ch]
0x140005ce1  bt      eax, r11d
0x140005ce5  jnb     short loc_140005D34
0x140005ce7  lea     rcx, [rbx+rbx*4]
0x140005ceb  add     rcx, rcx
0x140005cee  cmp     [r10+rcx*8+29h], dil
0x140005cf3  jb      short loc_140005D34
0x140005cf5  mov     rax, cs:pfnWppTraceMessage
0x140005cfc  lea     rdx, [rsp+68h+arg_28]
0x140005d04  mov     rcx, [r10+rcx*8+18h]
0x140005d09  lea     r8, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x140005d10  mov     [rsp+68h+var_38], 0
0x140005d19  mov     r9d, esi
0x140005d1c  mov     [rsp+68h+var_40], 4
0x140005d25  mov     [rsp+68h+var_48], rdx
0x140005d2a  mov     edx, 2Bh ; '+'
0x140005d2f  call    _guard_dispatch_icall
0x140005d34  mov     [rsp+68h+var_30], 0
0x140005d3d  lea     rax, [rsp+68h+arg_28]
0x140005d45  mov     [rsp+68h+var_38], 4
0x140005d4e  lea     r9, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x140005d55  mov     [rsp+68h+var_40], rax
0x140005d5a  mov     r8d, ebp
0x140005d5d  mov     edx, edi
0x140005d5f  mov     word ptr [rsp+68h+var_48], si
0x140005d64  mov     rcx, r14
0x140005d67  call    cs:__imp_WppAutoLogTrace
0x140005d6e  nop     dword ptr [rax+rax+00h]
0x140005d73  add     rsp, 40h
0x140005d77  pop     r14
0x140005d79  pop     rdi
0x140005d7a  pop     rsi
0x140005d7b  pop     rbp
0x140005d7c  pop     rbx
0x140005d7d  retn
```
