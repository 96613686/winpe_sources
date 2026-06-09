# WPP_RECORDER_SF_Dd

- ea: `0x140004684`
- end: `0x14000477f`
- name: `WPP_RECORDER_SF_Dd`
- size: `251`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x14000916c`
- `0x14000aca0`
- `0x140010260`
- `0x14001190c`
- `0x140012c60`
- `0x140015c4c`
- `0x140032cf8`

## callees

- `0x140004684`
- `0x14001fc70`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004769`
- `WppRecorder!WppAutoLogTrace` at `0x140004769`

## pseudocode

```c
__int64 WPP_RECORDER_SF_Dd(__int64 a1, __int64 a2, unsigned int a3, unsigned __int16 a4, __int64 a5, ...)
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
      4,
      va1,
      4,
      0);
  LOWORD(v11) = a4;
  return WppAutoLogTrace(a1, 0, a3, a5, v11, (__int64 *)va);
}

```

## disassembly

```asm
0x140004684  push    rbx
0x140004686  push    rbp
0x140004687  push    rsi
0x140004688  push    rdi
0x140004689  sub     rsp, 58h
0x14000468d  mov     edi, r8d
0x140004690  mov     rsi, rcx
0x140004693  mov     r11d, r8d
0x140004696  mov     ebp, 4
0x14000469b  shr     r11, 10h
0x14000469f  movzx   ebx, r9w
0x1400046a3  lea     r10d, [rdi-1]
0x1400046a7  mov     edx, r10d
0x1400046aa  and     r10d, 1Fh
0x1400046ae  shr     rdx, 5
0x1400046b2  lea     rax, [r11+r11*4]
0x1400046b6  and     edx, 7FFh
0x1400046bc  lea     rax, [rdx+rax*4]
0x1400046c0  mov     edx, r10d
0x1400046c3  mov     r10, cs:WPP_GLOBAL_Control
0x1400046ca  mov     eax, [r10+rax*4+2Ch]
0x1400046cf  bt      eax, edx
0x1400046d2  jnb     short loc_140004727
0x1400046d4  mov     rax, cs:pfnWppTraceMessage
0x1400046db  lea     rcx, [r11+r11*4]
0x1400046df  mov     r8, [rsp+78h+arg_20]
0x1400046e7  lea     rdx, [rsp+78h+arg_30]
0x1400046ef  mov     [rsp+78h+var_38], 0
0x1400046f8  add     rcx, rcx
0x1400046fb  mov     [rsp+78h+var_40], rbp
0x140004700  mov     r9d, ebx
0x140004703  mov     [rsp+78h+var_48], rdx
0x140004708  lea     rdx, [rsp+78h+arg_28]
0x140004710  mov     [rsp+78h+var_50], rbp
0x140004715  mov     rcx, [r10+rcx*8+18h]
0x14000471a  mov     [rsp+78h+var_58], rdx
0x14000471f  lea     edx, [rbp+27h]
0x140004722  call    _guard_dispatch_icall
0x140004727  mov     r9, [rsp+78h+arg_20]
0x14000472f  lea     rax, [rsp+78h+arg_30]
0x140004737  mov     [rsp+78h+var_30], 0
0x140004740  mov     r8d, edi
0x140004743  mov     [rsp+78h+var_38], rbp
0x140004748  xor     edx, edx
0x14000474a  mov     [rsp+78h+var_40], rax
0x14000474f  mov     rcx, rsi
0x140004752  lea     rax, [rsp+78h+arg_28]
0x14000475a  mov     [rsp+78h+var_48], rbp
0x14000475f  mov     [rsp+78h+var_50], rax
0x140004764  mov     word ptr [rsp+78h+var_58], bx
0x140004769  call    cs:__imp_WppAutoLogTrace
0x140004770  nop     dword ptr [rax+rax+00h]
0x140004775  add     rsp, 58h
0x140004779  pop     rdi
0x14000477a  pop     rsi
0x14000477b  pop     rbp
0x14000477c  pop     rbx
0x14000477d  retn
```
