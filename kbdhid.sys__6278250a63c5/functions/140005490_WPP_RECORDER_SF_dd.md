# WPP_RECORDER_SF_dd

- ea: `0x140005490`
- end: `0x14000556d`
- name: `WPP_RECORDER_SF_dd`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140003470`
- `0x140005928`

## callees

- `0x140005490`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140005550`
- `WppRecorder!WppAutoLogTrace` at `0x140005550`

## pseudocode

```c
__int64 WPP_RECORDER_SF_dd(__int64 a1, unsigned __int8 a2, _DWORD a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-38h]
  __int64 v10; // [rsp+88h] [rbp+30h] BYREF
  va_list va; // [rsp+88h] [rbp+30h]
  va_list va1; // [rsp+90h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v10 = va_arg(va1, _QWORD);
  v7 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids,
      a4,
      (__int64 *)va,
      4,
      va1,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, v7, 3, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids, v9, (__int64 *)va);
}

```

## disassembly

```asm
0x140005490  mov     r11, rsp
0x140005493  mov     [r11+8], rbx
0x140005497  mov     [r11+10h], rsi
0x14000549b  push    rdi
0x14000549c  sub     rsp, 50h
0x1400054a0  mov     rsi, rcx
0x1400054a3  movzx   edi, r9w
0x1400054a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400054ae  movzx   ebx, dl
0x1400054b1  mov     eax, [rcx+2Ch]
0x1400054b4  test    al, 4
0x1400054b6  jz      short loc_140005504
0x1400054b8  cmp     [rcx+29h], bl
0x1400054bb  jb      short loc_140005504
0x1400054bd  mov     rax, cs:pfnWppTraceMessage
0x1400054c4  lea     rdx, [r11+38h]
0x1400054c8  mov     rcx, [rcx+18h]
0x1400054cc  lea     r8, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x1400054d3  mov     qword ptr [r11-18h], 0
0x1400054db  mov     r9d, edi
0x1400054de  mov     qword ptr [r11-20h], 4
0x1400054e6  mov     [r11-28h], rdx
0x1400054ea  lea     rdx, [r11+30h]
0x1400054ee  mov     qword ptr [r11-30h], 4
0x1400054f6  mov     [r11-38h], rdx
0x1400054fa  mov     edx, 2Bh ; '+'
0x1400054ff  call    _guard_dispatch_icall
0x140005504  mov     [rsp+58h+var_10], 0
0x14000550d  lea     rax, [rsp+58h+arg_30]
0x140005515  mov     [rsp+58h+var_18], 4
0x14000551e  lea     r9, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x140005525  mov     [rsp+58h+var_20], rax
0x14000552a  mov     r8d, 3
0x140005530  lea     rax, [rsp+58h+arg_28]
0x140005538  mov     [rsp+58h+var_28], 4
0x140005541  mov     [rsp+58h+var_30], rax
0x140005546  mov     edx, ebx
0x140005548  mov     rcx, rsi
0x14000554b  mov     [rsp+58h+var_38], di
0x140005550  call    cs:__imp_WppAutoLogTrace
0x140005557  nop     dword ptr [rax+rax+00h]
0x14000555c  mov     rbx, [rsp+58h+arg_0]
0x140005561  mov     rsi, [rsp+58h+arg_8]
0x140005566  add     rsp, 50h
0x14000556a  pop     rdi
0x14000556b  retn
```
