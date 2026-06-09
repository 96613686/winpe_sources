# WPP_RECORDER_SF_qqd

- ea: `0x140005d88`
- end: `0x140005ec0`
- name: `WPP_RECORDER_SF_qqd`
- size: `312`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001a00`
- `0x1400026a0`
- `0x140003040`
- `0x1400053c0`
- `0x140006680`

## callees

- `0x140005d88`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140005ea6`
- `WppRecorder!WppAutoLogTrace` at `0x140005ea6`

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
0x140005d88  push    rbx
0x140005d8a  push    rbp
0x140005d8b  push    rsi
0x140005d8c  push    rdi
0x140005d8d  push    r14
0x140005d8f  push    r15
0x140005d91  sub     rsp, 68h
0x140005d95  mov     r14d, r8d
0x140005d98  mov     r15, rcx
0x140005d9b  mov     edi, r8d
0x140005d9e  shr     rdi, 10h
0x140005da2  movzx   esi, dl
0x140005da5  lea     ebx, [r14-1]
0x140005da9  movzx   ebp, r9w
0x140005dad  mov     r10d, ebx
0x140005db0  and     ebx, 1Fh
0x140005db3  shr     r10, 5
0x140005db7  lea     rax, [rdi+rdi*4]
0x140005dbb  and     r10d, 7FFh
0x140005dc2  mov     edx, ebx
0x140005dc4  mov     ebx, 8
0x140005dc9  lea     r11, [r10+rax*4]
0x140005dcd  mov     r10, cs:WPP_GLOBAL_Control
0x140005dd4  mov     eax, [r10+r11*4+2Ch]
0x140005dd9  bt      eax, edx
0x140005ddc  jnb     short loc_140005E4E
0x140005dde  lea     rcx, [rdi+rdi*4]
0x140005de2  add     rcx, rcx
0x140005de5  cmp     [r10+rcx*8+29h], sil
0x140005dea  jb      short loc_140005E4E
0x140005dec  mov     rax, cs:pfnWppTraceMessage
0x140005df3  lea     rdx, [rsp+98h+arg_38]
0x140005dfb  mov     r8, [rsp+98h+arg_20]
0x140005e03  mov     r9d, ebp
0x140005e06  mov     rcx, [r10+rcx*8+18h]
0x140005e0b  mov     [rsp+98h+var_48], 0
0x140005e14  mov     [rsp+98h+var_50], 4
0x140005e1d  mov     [rsp+98h+var_58], rdx
0x140005e22  lea     rdx, [rsp+98h+arg_30]
0x140005e2a  mov     [rsp+98h+var_60], rbx
0x140005e2f  mov     [rsp+98h+var_68], rdx
0x140005e34  lea     rdx, [rsp+98h+arg_28]
0x140005e3c  mov     [rsp+98h+var_70], rbx
0x140005e41  mov     [rsp+98h+var_78], rdx
0x140005e46  lea     edx, [rbx+23h]
0x140005e49  call    _guard_dispatch_icall
0x140005e4e  mov     r9, [rsp+98h+arg_20]
0x140005e56  lea     rax, [rsp+98h+arg_38]
0x140005e5e  mov     [rsp+98h+var_40], 0
0x140005e67  mov     r8d, r14d
0x140005e6a  mov     [rsp+98h+var_48], 4
0x140005e73  mov     edx, esi
0x140005e75  mov     [rsp+98h+var_50], rax
0x140005e7a  mov     rcx, r15
0x140005e7d  mov     [rsp+98h+var_58], rbx
0x140005e82  lea     rax, [rsp+98h+arg_30]
0x140005e8a  mov     [rsp+98h+var_60], rax
0x140005e8f  lea     rax, [rsp+98h+arg_28]
0x140005e97  mov     [rsp+98h+var_68], rbx
0x140005e9c  mov     [rsp+98h+var_70], rax
0x140005ea1  mov     word ptr [rsp+98h+var_78], bp
0x140005ea6  call    cs:__imp_WppAutoLogTrace
0x140005ead  nop     dword ptr [rax+rax+00h]
0x140005eb2  add     rsp, 68h
0x140005eb6  pop     r15
0x140005eb8  pop     r14
0x140005eba  pop     rdi
0x140005ebb  pop     rsi
0x140005ebc  pop     rbp
0x140005ebd  pop     rbx
0x140005ebe  retn
```
