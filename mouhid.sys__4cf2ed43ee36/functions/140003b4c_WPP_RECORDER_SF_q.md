# WPP_RECORDER_SF_q

- ea: `0x140003b4c`
- end: `0x140003bf6`
- name: `WPP_RECORDER_SF_q`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140002ff0`
- `0x14000383c`

## callees

- `0x140003b4c`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003bde`
- `WppRecorder!WppAutoLogTrace` at `0x140003bde`

## pseudocode

```c
__int64 WPP_RECORDER_SF_q(__int64 a1, __int64 a2, __int64 a3, unsigned __int16 a4, int a5, ...)
{
  int v8; // [rsp+20h] [rbp-28h]
  va_list va; // [rsp+78h] [rbp+30h] BYREF

  va_start(va, a5);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids,
      a4,
      va,
      8,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 5, 2, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids, v8, va);
}

```

## disassembly

```asm
0x140003b4c  mov     r11, rsp
0x140003b4f  mov     [r11+8], rbx
0x140003b53  push    rdi
0x140003b54  sub     rsp, 40h
0x140003b58  mov     rdi, rcx
0x140003b5b  movzx   ebx, r9w
0x140003b5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140003b66  mov     eax, [rcx+2Ch]
0x140003b69  test    al, 2
0x140003b6b  jz      short loc_140003BAA
0x140003b6d  cmp     byte ptr [rcx+29h], 5
0x140003b71  jb      short loc_140003BAA
0x140003b73  mov     rax, cs:pfnWppTraceMessage
0x140003b7a  lea     rdx, [r11+30h]
0x140003b7e  mov     rcx, [rcx+18h]
0x140003b82  lea     r8, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003b89  mov     qword ptr [r11-18h], 0
0x140003b91  mov     r9d, ebx
0x140003b94  mov     qword ptr [r11-20h], 8
0x140003b9c  mov     [r11-28h], rdx
0x140003ba0  mov     edx, 2Bh ; '+'
0x140003ba5  call    _guard_dispatch_icall
0x140003baa  mov     [rsp+48h+var_10], 0
0x140003bb3  lea     rax, [rsp+48h+arg_28]
0x140003bb8  mov     edx, 5
0x140003bbd  mov     [rsp+48h+var_18], 8
0x140003bc6  mov     [rsp+48h+var_20], rax
0x140003bcb  lea     r9, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003bd2  mov     rcx, rdi
0x140003bd5  mov     [rsp+48h+var_28], bx
0x140003bda  lea     r8d, [rdx-3]
0x140003bde  call    cs:__imp_WppAutoLogTrace
0x140003be5  nop     dword ptr [rax+rax+00h]
0x140003bea  mov     rbx, [rsp+48h+arg_0]
0x140003bef  add     rsp, 40h
0x140003bf3  pop     rdi
0x140003bf4  retn
```
