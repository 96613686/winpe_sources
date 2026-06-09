# WPP_RECORDER_SF_qq

- ea: `0x140004e58`
- end: `0x140004f53`
- name: `WPP_RECORDER_SF_qq`
- size: `251`
- prototype: ``
- caller_count: `15`
- callee_count: `2`
- tags: ``

## callers

- `0x140001460`
- `0x140006470`
- `0x140007d40`
- `0x140008334`
- `0x1400085a0`
- `0x140009658`
- `0x14000e094`
- `0x14000e29c`
- `0x140010150`
- `0x140010688`
- `0x140010810`
- `0x1400135cc`
- `0x140013bf8`
- `0x140013fb4`
- `0x140015c4c`

## callees

- `0x140004e58`
- `0x14001fc70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004f3d`
- `WppRecorder!WppAutoLogTrace` at `0x140004f3d`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qq(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
{
  unsigned __int64 v7; // r11
  int v9; // eax
  int v11; // [rsp+20h] [rbp-58h]
  __int64 v12; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a5);
  va_start(va, a5);
  v12 = va_arg(va1, _QWORD);
  v7 = (unsigned __int64)a3 >> 16;
  v9 = *((_DWORD *)&WPP_GLOBAL_Control->Timer + 20 * v7 + (((a3 - 1) >> 5) & 0x7FF) + 1);
  if ( _bittest(&v9, (a3 - 1) & 0x1F) )
    ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      *((_QWORD *)&WPP_GLOBAL_Control->AttachedDevice + 10 * v7),
      43,
      a5,
      a4,
      (__int64 *)va,
      8,
      va1,
      8,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, (__int64 *)va);
}

```

## disassembly

```asm
0x140004e58  push    rbx
0x140004e5a  push    rbp
0x140004e5b  push    rsi
0x140004e5c  push    rdi
0x140004e5d  sub     rsp, 58h
0x140004e61  mov     edi, r8d
0x140004e64  mov     rsi, rcx
0x140004e67  mov     r11d, r8d
0x140004e6a  mov     ebp, 8
0x140004e6f  shr     r11, 10h
0x140004e73  movzx   ebx, r9w
0x140004e77  lea     r10d, [rdi-1]
0x140004e7b  mov     edx, r10d
0x140004e7e  and     r10d, 1Fh
0x140004e82  shr     rdx, 5
0x140004e86  lea     rax, [r11+r11*4]
0x140004e8a  and     edx, 7FFh
0x140004e90  lea     rax, [rdx+rax*4]
0x140004e94  mov     edx, r10d
0x140004e97  mov     r10, cs:WPP_GLOBAL_Control
0x140004e9e  mov     eax, [r10+rax*4+2Ch]
0x140004ea3  bt      eax, edx
0x140004ea6  jnb     short loc_140004EFB
0x140004ea8  mov     rax, cs:pfnWppTraceMessage
0x140004eaf  lea     rcx, [r11+r11*4]
0x140004eb3  mov     r8, [rsp+78h+arg_20]
0x140004ebb  lea     rdx, [rsp+78h+arg_30]
0x140004ec3  mov     [rsp+78h+var_38], 0
0x140004ecc  add     rcx, rcx
0x140004ecf  mov     [rsp+78h+var_40], rbp
0x140004ed4  mov     r9d, ebx
0x140004ed7  mov     [rsp+78h+var_48], rdx
0x140004edc  lea     rdx, [rsp+78h+arg_28]
0x140004ee4  mov     [rsp+78h+var_50], rbp
0x140004ee9  mov     rcx, [r10+rcx*8+18h]
0x140004eee  mov     [rsp+78h+var_58], rdx
0x140004ef3  lea     edx, [rbp+23h]
0x140004ef6  call    _guard_dispatch_icall
0x140004efb  mov     r9, [rsp+78h+arg_20]
0x140004f03  lea     rax, [rsp+78h+arg_30]
0x140004f0b  mov     [rsp+78h+var_30], 0
0x140004f14  mov     r8d, edi
0x140004f17  mov     [rsp+78h+var_38], rbp
0x140004f1c  xor     edx, edx
0x140004f1e  mov     [rsp+78h+var_40], rax
0x140004f23  mov     rcx, rsi
0x140004f26  lea     rax, [rsp+78h+arg_28]
0x140004f2e  mov     [rsp+78h+var_48], rbp
0x140004f33  mov     [rsp+78h+var_50], rax
0x140004f38  mov     word ptr [rsp+78h+var_58], bx
0x140004f3d  call    cs:__imp_WppAutoLogTrace
0x140004f44  nop     dword ptr [rax+rax+00h]
0x140004f49  add     rsp, 58h
0x140004f4d  pop     rdi
0x140004f4e  pop     rsi
0x140004f4f  pop     rbp
0x140004f50  pop     rbx
0x140004f51  retn
```
