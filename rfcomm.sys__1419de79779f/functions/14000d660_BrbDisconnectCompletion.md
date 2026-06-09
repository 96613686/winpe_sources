# BrbDisconnectCompletion

- ea: `0x14000d660`
- end: `0x14000d739`
- name: `BrbDisconnectCompletion`
- size: `217`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x14000d660`
- `0x14000fa84`
- `0x14001bfa8`
- `0x14001ea34`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000d68b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d68b`

## string_xrefs

- `0x14000d6e7`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
__int64 __fastcall BrbDisconnectCompletion(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  void *DeviceExtension; // rdi
  int v9; // edx
  int v10; // r8d
  __int64 result; // rax
  int v12; // edx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    KeGetCurrentIrql();
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    NtStatusTxt(a4);
    WPP_RECORDER_SF_sqqd((_DWORD)DeviceExtension, v9, v10, 31);
  }
  (*(void (__fastcall **)(__int64))(a1 + 320))(a2);
  result = RefObj_ReleaseEx(
             a3 + 24,
             BrbpDisconnect,
             694,
             "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c");
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_(
             WPP_GLOBAL_Control->DeviceExtension,
             v12,
             3,
             32,
             (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
  return result;
}

```

## disassembly

```asm
0x14000d660  push    rbx
0x14000d662  push    rbp
0x14000d663  push    rsi
0x14000d664  push    rdi
0x14000d665  push    r12
0x14000d667  push    r14
0x14000d669  push    r15
0x14000d66b  sub     rsp, 50h
0x14000d66f  mov     r14d, r9d
0x14000d672  mov     rsi, r8
0x14000d675  mov     rbp, rdx
0x14000d678  mov     r15, rcx
0x14000d67b  lea     r12, WPP_RECORDER_INITIALIZED
0x14000d682  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000d689  jz      short loc_14000D6CE
0x14000d68b  call    cs:__imp_KeGetCurrentIrql
0x14000d692  nop     dword ptr [rax+rax+00h]
0x14000d697  movzx   ebx, al
0x14000d69a  mov     ecx, r14d
0x14000d69d  mov     rax, cs:WPP_GLOBAL_Control
0x14000d6a4  mov     rdi, [rax+40h]
0x14000d6a8  call    NtStatusTxt
0x14000d6ad  mov     [rsp+88h+var_48], ebx
0x14000d6b1  mov     r9d, 1Fh
0x14000d6b7  mov     [rsp+88h+var_50], rbp
0x14000d6bc  mov     rcx, rdi
0x14000d6bf  mov     [rsp+88h+var_58], rsi
0x14000d6c4  mov     [rsp+88h+var_60], rax
0x14000d6c9  call    WPP_RECORDER_SF_sqqd
0x14000d6ce  mov     rax, [r15+140h]
0x14000d6d5  mov     rcx, rbp
0x14000d6d8  call    _guard_dispatch_icall
0x14000d6dd  lea     rcx, [rsi+18h]
0x14000d6e1  mov     r8d, 2B6h
0x14000d6e7  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000d6ee  lea     rdx, BrbpDisconnect
0x14000d6f5  call    RefObj_ReleaseEx
0x14000d6fa  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000d701  jz      short loc_14000D729
0x14000d703  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d70a  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000d711  mov     r9d, 20h ; ' '
0x14000d717  mov     [rsp+88h+var_68], rax
0x14000d71c  mov     rcx, [rcx+40h]
0x14000d720  lea     r8d, [r9-1Dh]
0x14000d724  call    WPP_RECORDER_SF_
0x14000d729  add     rsp, 50h
0x14000d72d  pop     r15
0x14000d72f  pop     r14
0x14000d731  pop     r12
0x14000d733  pop     rdi
0x14000d734  pop     rsi
0x14000d735  pop     rbp
0x14000d736  pop     rbx
0x14000d737  retn
```
