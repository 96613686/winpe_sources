# WPP_RECORDER_SF_qDd

- ea: `0x140006978`
- end: `0x140006a6b`
- name: `WPP_RECORDER_SF_qDd`
- size: `243`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001a00`

## callees

- `0x140006978`
- `0x140007170`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x140006a4e`
- `WppRecorder!WppAutoLogTrace` at `0x140006a4e`

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
      WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids,
      16,
      (__int64 *)va,
      8,
      (__int64 *)va1,
      4,
      va2,
      4,
      0);
  LOWORD(v7) = 16;
  return WppAutoLogTrace(a1, 4, 2, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids, v7, (__int64 *)va);
}

```

## disassembly

```asm
0x140006978  mov     r11, rsp
0x14000697b  mov     [r11+8], rbx
0x14000697f  mov     [r11+10h], rbp
0x140006983  push    rdi
0x140006984  sub     rsp, 60h
0x140006988  mov     rbx, rcx
0x14000698b  mov     edi, 4
0x140006990  mov     rcx, cs:WPP_GLOBAL_Control
0x140006997  lea     ebp, [rdi+0Ch]
0x14000699a  mov     eax, [rcx+2Ch]
0x14000699d  test    al, 2
0x14000699f  jz      short loc_1400069F4
0x1400069a1  cmp     [rcx+29h], dil
0x1400069a5  jb      short loc_1400069F4
0x1400069a7  mov     rax, cs:pfnWppTraceMessage
0x1400069ae  lea     rdx, [r11+40h]
0x1400069b2  mov     rcx, [rcx+18h]
0x1400069b6  lea     r8, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x1400069bd  mov     qword ptr [r11-18h], 0
0x1400069c5  mov     r9d, ebp
0x1400069c8  mov     [r11-20h], rdi
0x1400069cc  mov     [r11-28h], rdx
0x1400069d0  lea     rdx, [r11+38h]
0x1400069d4  mov     [r11-30h], rdi
0x1400069d8  mov     [r11-38h], rdx
0x1400069dc  lea     rdx, [r11+30h]
0x1400069e0  mov     qword ptr [r11-40h], 8
0x1400069e8  mov     [r11-48h], rdx
0x1400069ec  lea     edx, [rdi+27h]
0x1400069ef  call    _guard_dispatch_icall
0x1400069f4  mov     [rsp+68h+var_10], 0
0x1400069fd  lea     rax, [rsp+68h+arg_38]
0x140006a05  mov     [rsp+68h+var_18], rdi
0x140006a0a  lea     r9, WPP_d0c714c636b731cb8beb6bdeccc6560c_Traceguids
0x140006a11  mov     [rsp+68h+var_20], rax
0x140006a16  mov     r8d, 2
0x140006a1c  mov     [rsp+68h+var_28], rdi
0x140006a21  lea     rax, [rsp+68h+arg_30]
0x140006a29  mov     [rsp+68h+var_30], rax
0x140006a2e  mov     edx, edi
0x140006a30  lea     rax, [rsp+68h+arg_28]
0x140006a38  mov     [rsp+68h+var_38], 8
0x140006a41  mov     [rsp+68h+var_40], rax
0x140006a46  mov     rcx, rbx
0x140006a49  mov     [rsp+68h+var_48], bp
0x140006a4e  call    cs:__imp_WppAutoLogTrace
0x140006a55  nop     dword ptr [rax+rax+00h]
0x140006a5a  mov     rbx, [rsp+68h+arg_0]
0x140006a5f  mov     rbp, [rsp+68h+arg_8]
0x140006a64  add     rsp, 60h
0x140006a68  pop     rdi
0x140006a69  retn
```
