# WPP_RECORDER_SF_Ld

- ea: `0x14000163c`
- end: `0x140001715`
- name: `WPP_RECORDER_SF_Ld`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140001100`

## callees

- `0x14000163c`
- `0x140004e10`

## import_xrefs

- `WppRecorder!WppAutoLogTrace` at `0x1400016f8`
- `WppRecorder!WppAutoLogTrace` at `0x1400016f8`

## pseudocode

```c
__int64 __fastcall WPP_RECORDER_SF_Ld(__int64 a1)
{
  int v3; // [rsp+20h] [rbp-48h]
  int v4; // [rsp+50h] [rbp-18h] BYREF
  _DWORD v5[4]; // [rsp+58h] [rbp-10h] BYREF

  v4 = -1073741789;
  v5[0] = 983040;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    ((void (__fastcall *)(struct _DEVICE_OBJECT *, __int64, __int64 *, __int64, _DWORD *, __int64, int *, __int64, _QWORD))pfnWppTraceMessage)(
      WPP_GLOBAL_Control->AttachedDevice,
      43,
      WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids,
      13,
      v5,
      4,
      &v4,
      4,
      0);
  LOWORD(v3) = 13;
  return WppAutoLogTrace(a1, 2, 3, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids, v3, v5);
}

```

## disassembly

```asm
0x14000163c  mov     r11, rsp
0x14000163f  mov     [r11+8], rbx
0x140001643  mov     [r11+10h], rsi
0x140001647  push    rdi
0x140001648  sub     rsp, 60h
0x14000164c  mov     rbx, rcx
0x14000164f  mov     [rsp+68h+var_18], 0C0000023h
0x140001657  mov     rcx, cs:WPP_GLOBAL_Control
0x14000165e  mov     esi, 0Dh
0x140001663  mov     [rsp+68h+var_10], 0F0000h
0x14000166b  mov     eax, [rcx+2Ch]
0x14000166e  lea     edi, [rsi-9]
0x140001671  test    dil, al
0x140001674  jz      short loc_1400016B9
0x140001676  cmp     byte ptr [rcx+29h], 2
0x14000167a  jb      short loc_1400016B9
0x14000167c  mov     rax, cs:pfnWppTraceMessage
0x140001683  lea     rdx, [r11-18h]
0x140001687  mov     rcx, [rcx+18h]
0x14000168b  lea     r8, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids
0x140001692  mov     qword ptr [r11-28h], 0
0x14000169a  mov     r9d, esi
0x14000169d  mov     [r11-30h], rdi
0x1400016a1  mov     [r11-38h], rdx
0x1400016a5  lea     rdx, [r11-10h]
0x1400016a9  mov     [r11-40h], rdi
0x1400016ad  mov     [r11-48h], rdx
0x1400016b1  lea     edx, [rsi+1Eh]
0x1400016b4  call    _guard_dispatch_icall
0x1400016b9  mov     [rsp+68h+var_20], 0
0x1400016c2  lea     rax, [rsp+68h+var_18]
0x1400016c7  mov     [rsp+68h+var_28], rdi
0x1400016cc  lea     r9, WPP_5fb2b8b2da473567e94ec36236fb6212_Traceguids
0x1400016d3  mov     [rsp+68h+var_30], rax
0x1400016d8  mov     edx, 2
0x1400016dd  lea     rax, [rsp+68h+var_10]
0x1400016e2  mov     [rsp+68h+var_38], rdi
0x1400016e7  mov     [rsp+68h+var_40], rax
0x1400016ec  mov     rcx, rbx
0x1400016ef  mov     [rsp+68h+var_48], si
0x1400016f4  lea     r8d, [rdx+1]
0x1400016f8  call    cs:__imp_WppAutoLogTrace
0x1400016ff  nop     dword ptr [rax+rax+00h]
0x140001704  mov     rbx, [rsp+68h+arg_0]
0x140001709  mov     rsi, [rsp+68h+arg_8]
0x14000170e  add     rsp, 60h
0x140001712  pop     rdi
0x140001713  retn
```
