# WPP_RECORDER_SF_qqqd

- ea: `0x140004a0c`
- end: `0x140004b2b`
- name: `WPP_RECORDER_SF_qqqd`
- size: `287`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003fd0`

## callees

- `0x140004a0c`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140004b09`
- `WppRecorder!WppAutoLogTrace` at `0x140004b09`

## pseudocode

```c
__int64 WPP_RECORDER_SF_qqqd(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, ...)
{
  int v7; // [rsp+20h] [rbp-68h]
  int v8[4]; // [rsp+70h] [rbp-18h] BYREF
  __int64 v9; // [rsp+B8h] [rbp+30h] BYREF
  va_list va; // [rsp+B8h] [rbp+30h]
  __int64 v11; // [rsp+C0h] [rbp+38h] BYREF
  va_list va1; // [rsp+C0h] [rbp+38h]
  va_list va2; // [rsp+C8h] [rbp+40h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v9 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v11 = va_arg(va2, _QWORD);
  v8[0] = -1073741790;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, __int64 *, __int64, __int64 *, __int64, char *, __int64, int *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_bce545a1de1235e2be96703916423b99_Traceguids,
      15,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      8,
      va2,
      8,
      v8,
      4,
      0);
  LOWORD(v7) = 15;
  return WppAutoLogTrace(a1, 2, 1, WPP_bce545a1de1235e2be96703916423b99_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140004a0c  mov     r11, rsp
0x140004a0f  mov     [r11+8], rbx
0x140004a13  mov     [r11+10h], rbp
0x140004a17  push    rdi
0x140004a18  sub     rsp, 80h
0x140004a1f  mov     rbx, rcx
0x140004a22  mov     [rsp+88h+var_18], 0C0000022h
0x140004a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140004a31  mov     ebp, 0Fh
0x140004a36  mov     eax, [rcx+2Ch]
0x140004a39  lea     edi, [rbp-7]
0x140004a3c  test    al, 1
0x140004a3e  jz      short loc_140004A9F
0x140004a40  cmp     byte ptr [rcx+29h], 2
0x140004a44  jb      short loc_140004A9F
0x140004a46  mov     rax, cs:pfnWppTraceMessage
0x140004a4d  lea     rdx, [r11-18h]
0x140004a51  mov     rcx, [rcx+18h]
0x140004a55  lea     r8, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004a5c  mov     qword ptr [r11-28h], 0
0x140004a64  mov     r9d, ebp
0x140004a67  mov     qword ptr [r11-30h], 4
0x140004a6f  mov     [r11-38h], rdx
0x140004a73  lea     rdx, [r11+40h]
0x140004a77  mov     [r11-40h], rdi
0x140004a7b  mov     [r11-48h], rdx
0x140004a7f  lea     rdx, [r11+38h]
0x140004a83  mov     [r11-50h], rdi
0x140004a87  mov     [r11-58h], rdx
0x140004a8b  lea     rdx, [r11+30h]
0x140004a8f  mov     [r11-60h], rdi
0x140004a93  mov     [r11-68h], rdx
0x140004a97  lea     edx, [rbp+1Ch]
0x140004a9a  call    _guard_dispatch_icall
0x140004a9f  mov     [rsp+88h+var_20], 0
0x140004aa8  lea     rax, [rsp+88h+var_18]
0x140004aad  mov     [rsp+88h+var_28], 4
0x140004ab6  lea     r9, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004abd  mov     [rsp+88h+var_30], rax
0x140004ac2  mov     edx, 2
0x140004ac7  mov     [rsp+88h+var_38], rdi
0x140004acc  lea     rax, [rsp+88h+arg_38]
0x140004ad4  mov     [rsp+88h+var_40], rax
0x140004ad9  mov     rcx, rbx
0x140004adc  mov     [rsp+88h+var_48], rdi
0x140004ae1  lea     rax, [rsp+88h+arg_30]
0x140004ae9  mov     [rsp+88h+var_50], rax
0x140004aee  lea     r8d, [rdx-1]
0x140004af2  lea     rax, [rsp+88h+arg_28]
0x140004afa  mov     [rsp+88h+var_58], rdi
0x140004aff  mov     [rsp+88h+var_60], rax
0x140004b04  mov     [rsp+88h+var_68], bp
0x140004b09  call    cs:__imp_WppAutoLogTrace
0x140004b10  nop     dword ptr [rax+rax+00h]
0x140004b15  lea     r11, [rsp+88h+var_8]
0x140004b1d  mov     rbx, [r11+10h]
0x140004b21  mov     rbp, [r11+18h]
0x140004b25  mov     rsp, r11
0x140004b28  pop     rdi
0x140004b29  retn
```
