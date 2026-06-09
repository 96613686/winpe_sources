# WPP_RECORDER_SF_qqd

- ea: `0x140002d28`
- end: `0x140002e60`
- name: `WPP_RECORDER_SF_qqd`
- size: `312`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140002370`
- `0x14000383c`
- `0x140003fd0`

## callees

- `0x140002d28`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140002e46`
- `WppRecorder!WppAutoLogTrace` at `0x140002e46`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqd(__int64 a1, unsigned __int8 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // rdi
  unsigned int v8; // esi
  int v10; // eax
  int v12; // [rsp+20h] [rbp-78h]
  __int64 v13; // [rsp+C8h] [rbp+30h] BYREF
  va_list va; // [rsp+C8h] [rbp+30h]
  __int64 v15; // [rsp+D0h] [rbp+38h] BYREF
  va_list va1; // [rsp+D0h] [rbp+38h]
  va_list va2; // [rsp+D8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v13 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v15 = va_arg(va2, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v8 = a2;
  v10 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v10, ((_BYTE)a3 - 1) & 0x1F) && *((_BYTE *)&WPP_GLOBAL_Control->Timer + 80 * v7 + 1) >= a2 )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      4,
      0);
  LOWORD(v12) = a4;
  return WppAutoLogTrace(a1, v8, a3, a5, v12, (__int64 *)va);
}

```

## disassembly

```asm
0x140002d28  push    rbx
0x140002d2a  push    rbp
0x140002d2b  push    rsi
0x140002d2c  push    rdi
0x140002d2d  push    r14
0x140002d2f  push    r15
0x140002d31  sub     rsp, 68h
0x140002d35  mov     r14d, r8d
0x140002d38  mov     r15, rcx
0x140002d3b  mov     edi, r8d
0x140002d3e  shr     rdi, 10h
0x140002d42  movzx   esi, dl
0x140002d45  lea     ebx, [r14-1]
0x140002d49  movzx   ebp, r9w
0x140002d4d  mov     r10d, ebx
0x140002d50  and     ebx, 1Fh
0x140002d53  shr     r10, 5
0x140002d57  lea     rax, [rdi+rdi*4]
0x140002d5b  and     r10d, 7FFh
0x140002d62  mov     edx, ebx
0x140002d64  mov     ebx, 8
0x140002d69  lea     r11, [r10+rax*4]
0x140002d6d  mov     r10, cs:WPP_GLOBAL_Control
0x140002d74  mov     eax, [r10+r11*4+2Ch]
0x140002d79  bt      eax, edx
0x140002d7c  jnb     short loc_140002DEE
0x140002d7e  lea     rcx, [rdi+rdi*4]
0x140002d82  add     rcx, rcx
0x140002d85  cmp     [r10+rcx*8+29h], sil
0x140002d8a  jb      short loc_140002DEE
0x140002d8c  mov     rax, cs:pfnWppTraceMessage
0x140002d93  lea     rdx, [rsp+98h+arg_38]
0x140002d9b  mov     r8, [rsp+98h+arg_20]
0x140002da3  mov     r9d, ebp
0x140002da6  mov     rcx, [r10+rcx*8+18h]
0x140002dab  mov     [rsp+98h+var_48], 0
0x140002db4  mov     [rsp+98h+var_50], 4
0x140002dbd  mov     [rsp+98h+var_58], rdx
0x140002dc2  lea     rdx, [rsp+98h+arg_30]
0x140002dca  mov     [rsp+98h+var_60], rbx
0x140002dcf  mov     [rsp+98h+var_68], rdx
0x140002dd4  lea     rdx, [rsp+98h+arg_28]
0x140002ddc  mov     [rsp+98h+var_70], rbx
0x140002de1  mov     [rsp+98h+var_78], rdx
0x140002de6  lea     edx, [rbx+23h]
0x140002de9  call    _guard_dispatch_icall
0x140002dee  mov     r9, [rsp+98h+arg_20]
0x140002df6  lea     rax, [rsp+98h+arg_38]
0x140002dfe  mov     [rsp+98h+var_40], 0
0x140002e07  mov     r8d, r14d
0x140002e0a  mov     [rsp+98h+var_48], 4
0x140002e13  mov     edx, esi
0x140002e15  mov     [rsp+98h+var_50], rax
0x140002e1a  mov     rcx, r15
0x140002e1d  mov     [rsp+98h+var_58], rbx
0x140002e22  lea     rax, [rsp+98h+arg_30]
0x140002e2a  mov     [rsp+98h+var_60], rax
0x140002e2f  lea     rax, [rsp+98h+arg_28]
0x140002e37  mov     [rsp+98h+var_68], rbx
0x140002e3c  mov     [rsp+98h+var_70], rax
0x140002e41  mov     word ptr [rsp+98h+var_78], bp
0x140002e46  call    cs:__imp_WppAutoLogTrace
0x140002e4d  nop     dword ptr [rax+rax+00h]
0x140002e52  add     rsp, 68h
0x140002e56  pop     r15
0x140002e58  pop     r14
0x140002e5a  pop     rdi
0x140002e5b  pop     rsi
0x140002e5c  pop     rbp
0x140002e5d  pop     rbx
0x140002e5e  retn
```
