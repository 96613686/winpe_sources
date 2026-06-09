# BrbpReadComplete

- ea: `0x14000ebe0`
- end: `0x14000ecca`
- name: `BrbpReadComplete`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003bf4`
- `0x14000ebe0`
- `0x14000f758`
- `0x1400147a0`
- `0x14001bfa8`
- `0x14001ea34`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000ec0b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000ec0b`

## string_xrefs

- `0x14000ec6a`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\brb.c`

## pseudocode

```c
__int64 __fastcall BrbpReadComplete(__int64 a1, __int64 a2, __int64 a3, int a4)
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
    WPP_RECORDER_SF_qsd((_DWORD)DeviceExtension, v9, v10, 50);
  }
  RfcommParseData(a3, *(_QWORD *)(a2 + 136), *(_DWORD *)(a2 + 132), a4);
  RefObj_ReleaseEx(a3 + 24, 1145128274, 1140, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\brb.c");
  result = (*(__int64 (__fastcall **)(__int64))(a1 + 320))(a2);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return WPP_RECORDER_SF_(
             WPP_GLOBAL_Control->DeviceExtension,
             v12,
             3,
             51,
             (__int64)WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids);
  return result;
}

```

## disassembly

```asm
0x14000ebe0  push    rbx
0x14000ebe2  push    rbp
0x14000ebe3  push    rsi
0x14000ebe4  push    rdi
0x14000ebe5  push    r12
0x14000ebe7  push    r14
0x14000ebe9  push    r15
0x14000ebeb  sub     rsp, 40h
0x14000ebef  mov     ebp, r9d
0x14000ebf2  mov     r14, r8
0x14000ebf5  mov     rsi, rdx
0x14000ebf8  mov     r15, rcx
0x14000ebfb  lea     r12, WPP_RECORDER_INITIALIZED
0x14000ec02  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000ec09  jz      short loc_14000EC48
0x14000ec0b  call    cs:__imp_KeGetCurrentIrql
0x14000ec12  nop     dword ptr [rax+rax+00h]
0x14000ec17  movzx   ebx, al
0x14000ec1a  mov     ecx, ebp
0x14000ec1c  mov     rax, cs:WPP_GLOBAL_Control
0x14000ec23  mov     rdi, [rax+40h]
0x14000ec27  call    NtStatusTxt
0x14000ec2c  mov     [rsp+78h+var_40], ebx
0x14000ec30  mov     r9d, 32h ; '2'
0x14000ec36  mov     [rsp+78h+var_48], rax
0x14000ec3b  mov     rcx, rdi
0x14000ec3e  mov     [rsp+78h+var_50], rsi
0x14000ec43  call    WPP_RECORDER_SF_qsd
0x14000ec48  mov     r8d, [rsi+84h]
0x14000ec4f  mov     r9d, ebp
0x14000ec52  mov     rdx, [rsi+88h]
0x14000ec59  mov     rcx, r14
0x14000ec5c  call    RfcommParseData
0x14000ec61  lea     rcx, [r14+18h]
0x14000ec65  mov     edx, 44414552h
0x14000ec6a  lea     r9, aOnecoreDrivers_0; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000ec71  mov     r8d, 474h
0x14000ec77  call    RefObj_ReleaseEx
0x14000ec7c  mov     rax, [r15+140h]
0x14000ec83  mov     rcx, rsi
0x14000ec86  call    _guard_dispatch_icall
0x14000ec8b  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14000ec92  jz      short loc_14000ECBA
0x14000ec94  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ec9b  lea     rax, WPP_71fcf61518bb3ac45e7476452d4a8435_Traceguids
0x14000eca2  mov     r9d, 33h ; '3'
0x14000eca8  mov     [rsp+78h+var_58], rax
0x14000ecad  mov     rcx, [rcx+40h]
0x14000ecb1  lea     r8d, [r9-30h]
0x14000ecb5  call    WPP_RECORDER_SF_
0x14000ecba  add     rsp, 40h
0x14000ecbe  pop     r15
0x14000ecc0  pop     r14
0x14000ecc2  pop     r12
0x14000ecc4  pop     rdi
0x14000ecc5  pop     rsi
0x14000ecc6  pop     rbp
0x14000ecc7  pop     rbx
0x14000ecc8  retn
```
