# WPP_RECORDER_SF_dd

- ea: `0x140005440`
- end: `0x140005554`
- name: `WPP_RECORDER_SF_dd`
- size: `276`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140002610`
- `0x1400048f0`
- `0x1400059c0`
- `0x1400066d0`
- `0x140006a60`
- `0x14001a19c`
- `0x14001fa30`

## callees

- `0x140005440`
- `0x14000daa0`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400054d5`
- `WppRecorder!WppAutoLogTrace` at `0x1400054d5`

## pseudocode

```c
__int64 WPP_RECORDER_SF_dd(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v8; // r10
  unsigned int v9; // r8d
  int v10; // eax
  int v12; // [rsp+20h] [rbp-38h]
  __int64 v13; // [rsp+88h] [rbp+30h] BYREF
  va_list va; // [rsp+88h] [rbp+30h]
  va_list va1; // [rsp+90h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  v8 = (unsigned __int64)a3 >> 16;
  v9 = a3 - 1;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v8 + ((unsigned __int16)v9 >> 5) + 1);
  if ( _bittest(&v10, v9) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v8),
      43,
      a5,
      a4,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x140005440  mov     [rsp+arg_0], rbx
0x140005445  mov     [rsp+arg_8], rbp
0x14000544a  push    rdi
0x14000544b  sub     rsp, 50h
0x14000544f  mov     r11, cs:WPP_GLOBAL_Control
0x140005456  mov     rbp, rcx
0x140005459  mov     ebx, r8d
0x14000545c  mov     r10d, ebx
0x14000545f  movzx   edi, r9w
0x140005463  shr     r10, 10h
0x140005467  lea     r8d, [rbx-1]
0x14000546b  mov     edx, r8d
0x14000546e  shr     rdx, 5
0x140005472  lea     rax, [r10+r10*4]
0x140005476  and     edx, 7FFh
0x14000547c  lea     rax, [rdx+rax*4]
0x140005480  mov     eax, [r11+rax*4+2Ch]
0x140005485  bt      eax, r8d
0x140005489  jb      short loc_1400054F2
0x14000548b  mov     r9, [rsp+58h+arg_20]
0x140005493  lea     rax, [rsp+58h+arg_30]
0x14000549b  mov     [rsp+58h+var_10], 0
0x1400054a4  mov     r8d, ebx
0x1400054a7  mov     [rsp+58h+var_18], 4
0x1400054b0  xor     edx, edx
0x1400054b2  mov     [rsp+58h+var_20], rax
0x1400054b7  mov     rcx, rbp
0x1400054ba  lea     rax, [rsp+58h+arg_28]
0x1400054c2  mov     [rsp+58h+var_28], 4
0x1400054cb  mov     [rsp+58h+var_30], rax
0x1400054d0  mov     word ptr [rsp+58h+var_38], di
0x1400054d5  call    cs:__imp_WppAutoLogTrace
0x1400054dc  nop     dword ptr [rax+rax+00h]
0x1400054e1  mov     rbx, [rsp+58h+arg_0]
0x1400054e6  mov     rbp, [rsp+58h+arg_8]
0x1400054eb  add     rsp, 50h
0x1400054ef  pop     rdi
0x1400054f0  retn
0x1400054f2  mov     rax, cs:pfnWppTraceMessage
0x1400054f9  lea     rcx, [r10+r10*4]
0x1400054fd  mov     r8, [rsp+58h+arg_20]
0x140005505  lea     rdx, [rsp+58h+arg_30]
0x14000550d  mov     [rsp+58h+var_18], 0
0x140005516  add     rcx, rcx
0x140005519  mov     [rsp+58h+var_20], 4
0x140005522  mov     r9d, edi
0x140005525  mov     [rsp+58h+var_28], rdx
0x14000552a  lea     rdx, [rsp+58h+arg_28]
0x140005532  mov     [rsp+58h+var_30], 4
0x14000553b  mov     rcx, [r11+rcx*8+18h]
0x140005540  mov     [rsp+58h+var_38], rdx
0x140005545  mov     edx, 2Bh ; '+'
0x14000554a  call    _guard_dispatch_icall
0x14000554f  jmp     loc_14000548B
```
