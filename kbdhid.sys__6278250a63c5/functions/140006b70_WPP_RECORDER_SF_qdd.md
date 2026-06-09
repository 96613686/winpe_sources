# WPP_RECORDER_SF_qdd

- ea: `0x140006b70`
- end: `0x140006c65`
- name: `WPP_RECORDER_SF_qdd`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400042d0`

## callees

- `0x140006b70`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006c48`
- `WppRecorder!WppAutoLogTrace` at `0x140006c48`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qdd(__int64 a1, _DWORD a2, _DWORD a3, unsigned __int16 a4, __int64 a5, ...)
{
  int v8; // [rsp+20h] [rbp-48h]
  __int64 v9; // [rsp+98h] [rbp+30h] BYREF
  va_list va; // [rsp+98h] [rbp+30h]
  __int64 v11; // [rsp+A0h] [rbp+38h] BYREF
  va_list va1; // [rsp+A0h] [rbp+38h]
  va_list va2; // [rsp+A8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
      a4,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v8) = a4;
  return WppAutoLogTrace(a1, 2, 1, WPP_98d22518711f34f074bb80910c9ade48_Traceguids, v8, (__int64 *)va);
}

```

## disassembly

```asm
0x140006b70  mov     r11, rsp
0x140006b73  mov     [r11+8], rbx
0x140006b77  mov     [r11+10h], rsi
0x140006b7b  push    rdi
0x140006b7c  sub     rsp, 60h
0x140006b80  mov     rdi, rcx
0x140006b83  movzx   ebx, r9w
0x140006b87  mov     rcx, cs:WPP_GLOBAL_Control
0x140006b8e  mov     esi, 4
0x140006b93  mov     eax, [rcx+2Ch]
0x140006b96  test    al, 1
0x140006b98  jz      short loc_140006BED
0x140006b9a  cmp     byte ptr [rcx+29h], 2
0x140006b9e  jb      short loc_140006BED
0x140006ba0  mov     rax, cs:pfnWppTraceMessage
0x140006ba7  lea     rdx, [r11+40h]
0x140006bab  mov     rcx, [rcx+18h]
0x140006baf  lea     r8, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140006bb6  mov     qword ptr [r11-18h], 0
0x140006bbe  mov     r9d, ebx
0x140006bc1  mov     [r11-20h], rsi
0x140006bc5  mov     [r11-28h], rdx
0x140006bc9  lea     rdx, [r11+38h]
0x140006bcd  mov     [r11-30h], rsi
0x140006bd1  mov     [r11-38h], rdx
0x140006bd5  lea     rdx, [r11+30h]
0x140006bd9  mov     qword ptr [r11-40h], 8
0x140006be1  mov     [r11-48h], rdx
0x140006be5  lea     edx, [rsi+27h]
0x140006be8  call    _guard_dispatch_icall
0x140006bed  mov     [rsp+68h+var_10], 0
0x140006bf6  lea     rax, [rsp+68h+arg_38]
0x140006bfe  mov     [rsp+68h+var_18], rsi
0x140006c03  lea     r9, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140006c0a  mov     [rsp+68h+var_20], rax
0x140006c0f  mov     edx, 2
0x140006c14  mov     [rsp+68h+var_28], rsi
0x140006c19  lea     rax, [rsp+68h+arg_30]
0x140006c21  mov     [rsp+68h+var_30], rax
0x140006c26  mov     rcx, rdi
0x140006c29  lea     rax, [rsp+68h+arg_28]
0x140006c31  mov     [rsp+68h+var_38], 8
0x140006c3a  mov     [rsp+68h+var_40], rax
0x140006c3f  lea     r8d, [rdx-1]
0x140006c43  mov     [rsp+68h+var_48], bx
0x140006c48  call    cs:__imp_WppAutoLogTrace
0x140006c4f  nop     dword ptr [rax+rax+00h]
0x140006c54  mov     rbx, [rsp+68h+arg_0]
0x140006c59  mov     rsi, [rsp+68h+arg_8]
0x140006c5e  add     rsp, 60h
0x140006c62  pop     rdi
0x140006c63  retn
```
