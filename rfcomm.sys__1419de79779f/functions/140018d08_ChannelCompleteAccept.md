# ChannelCompleteAccept

- ea: `0x140018d08`
- end: `0x140018e95`
- name: `ChannelCompleteAccept`
- size: `397`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140005f2c`
- `0x140006bc0`
- `0x140006f68`
- `0x14000a380`
- `0x140018330`

## callees

- `0x140003bf4`
- `0x14000ca20`
- `0x14000fc00`
- `0x140014b10`
- `0x140018d08`
- `0x140019cd0`
- `0x14001bfa8`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018de5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140018de5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018e28`
- `ntoskrnl!KeReleaseSpinLock` at `0x140018e28`
- `ntoskrnl!IofCompleteRequest` at `0x140018db5`
- `ntoskrnl!IofCompleteRequest` at `0x140018db5`

## string_xrefs

- `0x140018dcf`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`
- `0x140018e3d`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\channel.c`

## pseudocode

```c
_UNKNOWN **__fastcall ChannelCompleteAccept(__int64 a1, __int64 a2, IRP *a3, int a4)
{
  __int64 v4; // r15
  __int64 v7; // rbp
  void *DeviceExtension; // rbx
  const char *v10; // rax
  int v11; // edx
  _QWORD *v12; // rax
  __int64 v13; // r8
  _QWORD *v14; // rdx
  int v15; // edx
  _UNKNOWN **result; // rax

  v4 = *(_QWORD *)(a1 + 56);
  v7 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
    v10 = NtStatusTxt(a4);
    WPP_RECORDER_SF_qqs(
      (_DWORD)DeviceExtension,
      v11,
      3,
      22,
      (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids,
      a1,
      (char)a3,
      (__int64)v10);
  }
  if ( a4 < 0 )
  {
    LOBYTE(a2) = *(_BYTE *)(a1 + 184);
    RfcommSendDMEx(v4, a2, 0);
    ChannelDisconnectRequest(a1, 2);
  }
  else
  {
    ChannelAccept(a1, v7);
  }
  if ( a3 )
  {
    a3->IoStatus.Status = a4;
    IofCompleteRequest(a3, 2);
  }
  if ( v7 )
    RefObj_ReleaseEx(v7 + 24, 1145981254, 500, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
  *(_BYTE *)(v4 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 56));
  v12 = (_QWORD *)(a1 + 240);
  v13 = *(_QWORD *)(a1 + 240);
  if ( *(_QWORD *)(v13 + 8) != a1 + 240 || (v14 = *(_QWORD **)(a1 + 248), (_QWORD *)*v14 != v12) )
    __fastfail(3u);
  *v14 = v13;
  *(_QWORD *)(v13 + 8) = v14;
  *(_QWORD *)(a1 + 248) = a1 + 240;
  *v12 = v12;
  KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 56), *(_BYTE *)(v4 + 64));
  RefObj_ReleaseEx(a1 + 24, 1414546241, 510, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\channel.c");
  result = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return (_UNKNOWN **)WPP_RECORDER_SF_(
                          WPP_GLOBAL_Control->DeviceExtension,
                          v15,
                          3,
                          23,
                          (__int64)WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids);
  return result;
}

```

## disassembly

```asm
0x140018d08  push    rbx
0x140018d0a  push    rbp
0x140018d0b  push    rsi
0x140018d0c  push    rdi
0x140018d0d  push    r13
0x140018d0f  push    r14
0x140018d11  push    r15
0x140018d13  sub     rsp, 40h
0x140018d17  mov     r15, [rcx+38h]
0x140018d1b  mov     r14d, r9d
0x140018d1e  mov     rsi, r8
0x140018d21  mov     rbp, rdx
0x140018d24  mov     rdi, rcx
0x140018d27  lea     rax, WPP_RECORDER_INITIALIZED
0x140018d2e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018d35  lea     r13, WPP_28934cb1a0ed3aa52c7031c9e42fd965_Traceguids
0x140018d3c  jz      short loc_140018D77
0x140018d3e  mov     rax, cs:WPP_GLOBAL_Control
0x140018d45  mov     ecx, r9d
0x140018d48  mov     rbx, [rax+40h]
0x140018d4c  call    NtStatusTxt
0x140018d51  mov     [rsp+78h+var_40], rax
0x140018d56  mov     r9d, 16h
0x140018d5c  mov     [rsp+78h+var_48], rsi
0x140018d61  mov     rcx, rbx
0x140018d64  mov     [rsp+78h+var_50], rdi
0x140018d69  mov     [rsp+78h+var_58], r13
0x140018d6e  lea     r8d, [r9-13h]
0x140018d72  call    WPP_RECORDER_SF_qqs
0x140018d77  test    r14d, r14d
0x140018d7a  js      short loc_140018D89
0x140018d7c  mov     rdx, rbp
0x140018d7f  mov     rcx, rdi
0x140018d82  call    ChannelAccept
0x140018d87  jmp     short loc_140018DA7
0x140018d89  mov     dl, [rdi+0B8h]
0x140018d8f  xor     r8d, r8d
0x140018d92  mov     rcx, r15
0x140018d95  call    RfcommSendDMEx
0x140018d9a  mov     edx, 2
0x140018d9f  mov     rcx, rdi
0x140018da2  call    ChannelDisconnectRequest
0x140018da7  test    rsi, rsi
0x140018daa  jz      short loc_140018DC1
0x140018dac  mov     dl, 2; PriorityBoost
0x140018dae  mov     [rsi+30h], r14d
0x140018db2  mov     rcx, rsi; Irp
0x140018db5  call    cs:__imp_IofCompleteRequest
0x140018dbc  nop     dword ptr [rax+rax+00h]
0x140018dc1  test    rbp, rbp
0x140018dc4  jz      short loc_140018DE1
0x140018dc6  lea     rcx, [rbp+18h]
0x140018dca  mov     edx, 444E4946h
0x140018dcf  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140018dd6  mov     r8d, 1F4h
0x140018ddc  call    RefObj_ReleaseEx
0x140018de1  lea     rcx, [r15+38h]; SpinLock
0x140018de5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140018dec  nop     dword ptr [rax+rax+00h]
0x140018df1  mov     [r15+40h], al
0x140018df5  lea     rax, [rdi+0F0h]
0x140018dfc  mov     r8, [rax]
0x140018dff  cmp     [r8+8], rax
0x140018e03  jnz     loc_140018E8E
0x140018e09  mov     rdx, [rax+8]
0x140018e0d  cmp     [rdx], rax
0x140018e10  jnz     short loc_140018E8E
0x140018e12  mov     [rdx], r8
0x140018e15  lea     rcx, [r15+38h]; SpinLock
0x140018e19  mov     [r8+8], rdx
0x140018e1d  mov     [rax+8], rax
0x140018e21  mov     [rax], rax
0x140018e24  mov     dl, [r15+40h]; NewIrql
0x140018e28  call    cs:__imp_KeReleaseSpinLock
0x140018e2f  nop     dword ptr [rax+rax+00h]
0x140018e34  lea     rcx, [rdi+18h]
0x140018e38  mov     edx, 54504341h
0x140018e3d  lea     r9, aOnecoreDrivers_1; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140018e44  mov     r8d, 1FEh
0x140018e4a  call    RefObj_ReleaseEx
0x140018e4f  lea     rax, WPP_RECORDER_INITIALIZED
0x140018e56  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140018e5d  jz      short loc_140018E7E
0x140018e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140018e66  mov     r9d, 17h
0x140018e6c  mov     [rsp+78h+var_58], r13
0x140018e71  mov     rcx, [rcx+40h]
0x140018e75  lea     r8d, [r9-14h]
0x140018e79  call    WPP_RECORDER_SF_
0x140018e7e  add     rsp, 40h
0x140018e82  pop     r15
0x140018e84  pop     r14
0x140018e86  pop     r13
0x140018e88  pop     rdi
0x140018e89  pop     rsi
0x140018e8a  pop     rbp
0x140018e8b  pop     rbx
0x140018e8c  retn
0x140018e8e  mov     ecx, 3
0x140018e93  int     29h; Win8: RtlFailFast(ecx)
```
