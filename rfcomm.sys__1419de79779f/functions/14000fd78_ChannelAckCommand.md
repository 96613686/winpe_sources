# ChannelAckCommand

- ea: `0x14000fd78`
- end: `0x14000fe42`
- name: `ChannelAckCommand`
- size: `202`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001138c`
- `0x14001291c`
- `0x140012c60`
- `0x140014210`

## callees

- `0x140003bf4`
- `0x14000fd78`
- `0x14001354c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fd99`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000fd99`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fdc8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000fdc8`

## string_xrefs

- `0x14000fde1`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
char __fastcall ChannelAckCommand(__int64 a1, char a2, int a3)
{
  __int64 v3; // rbp
  char v7; // r14
  KIRQL v8; // al
  __int64 v9; // rcx
  __int64 v10; // rbx
  int v11; // edx

  v3 = *(_QWORD *)(a1 + 56);
  v7 = 0;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 56));
  LOBYTE(v9) = a2;
  *(_BYTE *)(v3 + 64) = v8;
  v10 = RfcommAckCmdLocked(v9, a1 + 136, a1 + 144);
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 56), *(_BYTE *)(v3 + 64));
  if ( v10 )
  {
    *(_DWORD *)(v10 + 104) = a3;
    RefObj_ReleaseEx(v10 + 24, 541803329, 2013, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    v7 = 1;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v11,
      3,
      42,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x14000fd78  push    rbx
0x14000fd7a  push    rbp
0x14000fd7b  push    rsi
0x14000fd7c  push    rdi
0x14000fd7d  push    r14
0x14000fd7f  push    r15
0x14000fd81  sub     rsp, 38h
0x14000fd85  mov     rbp, [rcx+38h]
0x14000fd89  mov     rbx, rcx
0x14000fd8c  mov     r15d, r8d
0x14000fd8f  mov     sil, dl
0x14000fd92  xor     r14b, r14b
0x14000fd95  lea     rcx, [rbp+38h]; SpinLock
0x14000fd99  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000fda0  nop     dword ptr [rax+rax+00h]
0x14000fda5  lea     r8, [rbx+90h]
0x14000fdac  mov     cl, sil
0x14000fdaf  lea     rdx, [rbx+88h]
0x14000fdb6  mov     [rbp+40h], al
0x14000fdb9  call    RfcommAckCmdLocked
0x14000fdbe  mov     dl, [rbp+40h]; NewIrql
0x14000fdc1  lea     rcx, [rbp+38h]; SpinLock
0x14000fdc5  mov     rbx, rax
0x14000fdc8  call    cs:__imp_KeReleaseSpinLock
0x14000fdcf  nop     dword ptr [rax+rax+00h]
0x14000fdd4  test    rbx, rbx
0x14000fdd7  jz      short loc_14000FDFB
0x14000fdd9  lea     rcx, [rbx+18h]
0x14000fddd  mov     [rbx+68h], r15d
0x14000fde1  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000fde8  mov     edx, 204B4341h
0x14000fded  mov     r8d, 7DDh
0x14000fdf3  call    RefObj_ReleaseEx
0x14000fdf8  mov     r14b, 1
0x14000fdfb  lea     rax, WPP_RECORDER_INITIALIZED
0x14000fe02  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000fe09  jz      short loc_14000FE31
0x14000fe0b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe12  lea     rax, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14000fe19  mov     r9d, 2Ah ; '*'
0x14000fe1f  mov     [rsp+68h+var_48], rax
0x14000fe24  mov     rcx, [rcx+40h]
0x14000fe28  lea     r8d, [r9-27h]
0x14000fe2c  call    WPP_RECORDER_SF_
0x14000fe31  mov     al, r14b
0x14000fe34  add     rsp, 38h
0x14000fe38  pop     r15
0x14000fe3a  pop     r14
0x14000fe3c  pop     rdi
0x14000fe3d  pop     rsi
0x14000fe3e  pop     rbp
0x14000fe3f  pop     rbx
0x14000fe40  retn
```
