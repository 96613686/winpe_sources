# WPP_RECORDER_SF_qDd

- ea: `0x140003bfc`
- end: `0x140003cef`
- name: `WPP_RECORDER_SF_qDd`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000383c`

## callees

- `0x140003bfc`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140003cd2`
- `WppRecorder!WppAutoLogTrace` at `0x140003cd2`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qDd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-48h]
  __int64 v8; // [rsp+98h] [rbp+30h] BYREF
  va_list va; // [rsp+98h] [rbp+30h]
  __int64 v10; // [rsp+A0h] [rbp+38h] BYREF
  va_list va1; // [rsp+A0h] [rbp+38h]
  va_list va2; // [rsp+A8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v8 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v10 = va_arg(va2, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids,
      15,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v7) = 15;
  return WppAutoLogTrace(a1, 4, 2, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140003bfc  mov     r11, rsp
0x140003bff  mov     [r11+8], rbx
0x140003c03  mov     [r11+10h], rbp
0x140003c07  push    rdi
0x140003c08  sub     rsp, 60h
0x140003c0c  mov     rbx, rcx
0x140003c0f  mov     edi, 4
0x140003c14  mov     rcx, cs:WPP_GLOBAL_Control
0x140003c1b  lea     ebp, [rdi+0Bh]
0x140003c1e  mov     eax, [rcx+2Ch]
0x140003c21  test    al, 2
0x140003c23  jz      short loc_140003C78
0x140003c25  cmp     [rcx+29h], dil
0x140003c29  jb      short loc_140003C78
0x140003c2b  mov     rax, cs:pfnWppTraceMessage
0x140003c32  lea     rdx, [r11+40h]
0x140003c36  mov     rcx, [rcx+18h]
0x140003c3a  lea     r8, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003c41  mov     qword ptr [r11-18h], 0
0x140003c49  mov     r9d, ebp
0x140003c4c  mov     [r11-20h], rdi
0x140003c50  mov     [r11-28h], rdx
0x140003c54  lea     rdx, [r11+38h]
0x140003c58  mov     [r11-30h], rdi
0x140003c5c  mov     [r11-38h], rdx
0x140003c60  lea     rdx, [r11+30h]
0x140003c64  mov     qword ptr [r11-40h], 8
0x140003c6c  mov     [r11-48h], rdx
0x140003c70  lea     edx, [rdi+27h]
0x140003c73  call    _guard_dispatch_icall
0x140003c78  mov     [rsp+68h+var_10], 0
0x140003c81  lea     rax, [rsp+68h+arg_38]
0x140003c89  mov     [rsp+68h+var_18], rdi
0x140003c8e  lea     r9, WPP_8ae6e206fd5f3a01a789e273b148a72f_Traceguids
0x140003c95  mov     [rsp+68h+var_20], rax
0x140003c9a  mov     r8d, 2
0x140003ca0  mov     [rsp+68h+var_28], rdi
0x140003ca5  lea     rax, [rsp+68h+arg_30]
0x140003cad  mov     [rsp+68h+var_30], rax
0x140003cb2  mov     edx, edi
0x140003cb4  lea     rax, [rsp+68h+arg_28]
0x140003cbc  mov     [rsp+68h+var_38], 8
0x140003cc5  mov     [rsp+68h+var_40], rax
0x140003cca  mov     rcx, rbx
0x140003ccd  mov     [rsp+68h+var_48], bp
0x140003cd2  call    cs:__imp_WppAutoLogTrace
0x140003cd9  nop     dword ptr [rax+rax+00h]
0x140003cde  mov     rbx, [rsp+68h+arg_0]
0x140003ce3  mov     rbp, [rsp+68h+arg_8]
0x140003ce8  add     rsp, 60h
0x140003cec  pop     rdi
0x140003ced  retn
```
