# WPP_RECORDER_SF_Lqd

- ea: `0x140005ba8`
- end: `0x140005c93`
- name: `WPP_RECORDER_SF_Lqd`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003470`

## callees

- `0x140005ba8`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140005c7d`
- `WppRecorder!WppAutoLogTrace` at `0x140005c7d`

## pseudocode

```c
__int64 WPP_RECORDER_SF_Lqd(__int64 a1, unsigned __int8 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  unsigned int v7; // ebx
  int v9; // [rsp+20h] [rbp-68h]
  __int64 v10; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v12; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v10 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v12 = va_arg(va2, _QWORD);
  v7 = a2;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= a2 )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids,
      a4,
      (__int64 *)va,
      4,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v9) = a4;
  return WppAutoLogTrace(a1, v7, 3, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids, v9, (__int64 *)va);
}

```

## disassembly

```asm
0x140005ba8  mov     r11, rsp
0x140005bab  push    rbx
0x140005bac  push    rbp
0x140005bad  push    rsi
0x140005bae  push    rdi
0x140005baf  sub     rsp, 68h
0x140005bb3  mov     rsi, rcx
0x140005bb6  movzx   edi, r9w
0x140005bba  mov     rcx, cs:WPP_GLOBAL_Control
0x140005bc1  mov     ebp, 4
0x140005bc6  movzx   ebx, dl
0x140005bc9  mov     eax, [rcx+2Ch]
0x140005bcc  test    bpl, al
0x140005bcf  jz      short loc_140005C23
0x140005bd1  cmp     [rcx+29h], bl
0x140005bd4  jb      short loc_140005C23
0x140005bd6  mov     rax, cs:pfnWppTraceMessage
0x140005bdd  lea     rdx, [r11+40h]
0x140005be1  mov     rcx, [rcx+18h]
0x140005be5  lea     r8, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x140005bec  mov     qword ptr [r11-38h], 0
0x140005bf4  mov     r9d, edi
0x140005bf7  mov     [r11-40h], rbp
0x140005bfb  mov     [r11-48h], rdx
0x140005bff  lea     rdx, [r11+38h]
0x140005c03  mov     qword ptr [r11-50h], 8
0x140005c0b  mov     [r11-58h], rdx
0x140005c0f  lea     rdx, [r11+30h]
0x140005c13  mov     [r11-60h], rbp
0x140005c17  mov     [r11-68h], rdx
0x140005c1b  lea     edx, [rbp+27h]
0x140005c1e  call    _guard_dispatch_icall
0x140005c23  mov     [rsp+88h+var_30], 0
0x140005c2c  lea     rax, [rsp+88h+arg_38]
0x140005c34  mov     [rsp+88h+var_38], rbp
0x140005c39  lea     r9, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x140005c40  mov     [rsp+88h+var_40], rax
0x140005c45  mov     r8d, 3
0x140005c4b  mov     [rsp+88h+var_48], 8
0x140005c54  lea     rax, [rsp+88h+arg_30]
0x140005c5c  mov     [rsp+88h+var_50], rax
0x140005c61  mov     edx, ebx
0x140005c63  lea     rax, [rsp+88h+arg_28]
0x140005c6b  mov     [rsp+88h+var_58], rbp
0x140005c70  mov     [rsp+88h+var_60], rax
0x140005c75  mov     rcx, rsi
0x140005c78  mov     [rsp+88h+var_68], di
0x140005c7d  call    cs:__imp_WppAutoLogTrace
0x140005c84  nop     dword ptr [rax+rax+00h]
0x140005c89  add     rsp, 68h
0x140005c8d  pop     rdi
0x140005c8e  pop     rsi
0x140005c8f  pop     rbp
0x140005c90  pop     rbx
0x140005c91  retn
```
