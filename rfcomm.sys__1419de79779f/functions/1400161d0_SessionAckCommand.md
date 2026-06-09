# SessionAckCommand

- ea: `0x1400161d0`
- end: `0x1400162c7`
- name: `SessionAckCommand`
- size: `247`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001138c`
- `0x14001291c`
- `0x140012c60`
- `0x140014210`

## callees

- `0x140003bf4`
- `0x140004a68`
- `0x14001354c`
- `0x1400161d0`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001622a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001622a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016259`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016259`

## string_xrefs

- `0x140016272`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
char __fastcall SessionAckCommand(__int64 a1, char a2, int a3)
{
  char v6; // di
  KIRQL v7; // al
  __int64 v8; // rcx
  __int64 v9; // rbp
  int v10; // edx

  v6 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      43,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids,
      a1);
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  LOBYTE(v8) = a2;
  *(_BYTE *)(a1 + 64) = v7;
  v9 = RfcommAckCmdLocked(v8, a1 + 176, a1 + 184);
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
  if ( v9 )
  {
    *(_DWORD *)(v9 + 104) = a3;
    RefObj_ReleaseEx(v9 + 24, 541803329, 2043, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
    v6 = 1;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v10,
      3,
      44,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return v6;
}

```

## disassembly

```asm
0x1400161d0  push    rbx
0x1400161d2  push    rbp
0x1400161d3  push    rsi
0x1400161d4  push    rdi
0x1400161d5  push    r13
0x1400161d7  push    r14
0x1400161d9  push    r15
0x1400161db  sub     rsp, 30h
0x1400161df  mov     r14d, r8d
0x1400161e2  mov     bpl, dl
0x1400161e5  mov     rsi, rcx
0x1400161e8  xor     dil, dil
0x1400161eb  lea     r15, WPP_RECORDER_INITIALIZED
0x1400161f2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1400161f9  lea     r13, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140016200  jz      short loc_140016226
0x140016202  mov     [rsp+68h+var_40], rcx
0x140016207  mov     r9d, 2Bh ; '+'
0x14001620d  mov     rcx, cs:WPP_GLOBAL_Control
0x140016214  mov     [rsp+68h+var_48], r13
0x140016219  lea     r8d, [r9-28h]
0x14001621d  mov     rcx, [rcx+40h]
0x140016221  call    WPP_RECORDER_SF_q
0x140016226  lea     rcx, [rsi+38h]; SpinLock
0x14001622a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016231  nop     dword ptr [rax+rax+00h]
0x140016236  lea     r8, [rsi+0B8h]
0x14001623d  mov     cl, bpl
0x140016240  lea     rdx, [rsi+0B0h]
0x140016247  mov     [rsi+40h], al
0x14001624a  call    RfcommAckCmdLocked
0x14001624f  mov     dl, [rsi+40h]; NewIrql
0x140016252  lea     rcx, [rsi+38h]; SpinLock
0x140016256  mov     rbp, rax
0x140016259  call    cs:__imp_KeReleaseSpinLock
0x140016260  nop     dword ptr [rax+rax+00h]
0x140016265  test    rbp, rbp
0x140016268  jz      short loc_14001628C
0x14001626a  lea     rcx, [rbp+18h]
0x14001626e  mov     [rbp+68h], r14d
0x140016272  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140016279  mov     edx, 204B4341h
0x14001627e  mov     r8d, 7FBh
0x140016284  call    RefObj_ReleaseEx
0x140016289  mov     dil, 1
0x14001628c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140016293  jz      short loc_1400162B4
0x140016295  mov     rcx, cs:WPP_GLOBAL_Control
0x14001629c  mov     r9d, 2Ch ; ','
0x1400162a2  mov     [rsp+68h+var_48], r13
0x1400162a7  mov     rcx, [rcx+40h]
0x1400162ab  lea     r8d, [r9-29h]
0x1400162af  call    WPP_RECORDER_SF_
0x1400162b4  mov     al, dil
0x1400162b7  add     rsp, 30h
0x1400162bb  pop     r15
0x1400162bd  pop     r14
0x1400162bf  pop     r13
0x1400162c1  pop     rdi
0x1400162c2  pop     rsi
0x1400162c3  pop     rbp
0x1400162c4  pop     rbx
0x1400162c5  retn
```
