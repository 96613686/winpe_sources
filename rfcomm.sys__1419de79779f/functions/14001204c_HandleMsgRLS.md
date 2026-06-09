# HandleMsgRLS

- ea: `0x14001204c`
- end: `0x1400121cb`
- name: `HandleMsgRLS`
- size: `383`
- prototype: `char __fastcall(__int64, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012c60`

## callees

- `0x140003bf4`
- `0x140005c38`
- `0x14001204c`
- `0x140019e5c`
- `0x14001a12c`
- `0x14001ea34`
- `0x14001ebd8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400120a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400120a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400120f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400121ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400120f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400121ba`

## string_xrefs

- `0x14001215a`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\rfcomm.c`

## pseudocode

```c
char __fastcall HandleMsgRLS(__int64 a1, __int64 a2, __int64 a3, __int64 *a4)
{
  char v7; // di
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 Locked; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rbp
  int v14; // edx
  IRP *v15; // rax
  _IRP *MasterIrp; // rdx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      3,
      98,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  *(_BYTE *)(a1 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 56));
  v7 = 1;
  LOBYTE(v8) = *(_BYTE *)(a2 + 2) >> 2;
  LOBYTE(v9) = 1;
  Locked = ChannelFindLocked(a1, v8, v9);
  v11 = Locked;
  if ( Locked )
  {
    v12 = ChannelReferenceConnLocked(Locked, 1312901187);
    *(_BYTE *)(v11 + 200) = *(_BYTE *)(a2 + 3);
    v13 = v12;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    if ( v13 && (v15 = (IRP *)IrpList_Dequeue(v13 + 736)) != 0 )
    {
      MasterIrp = v15->AssociatedIrp.MasterIrp;
      *(_QWORD *)&MasterIrp->Type = 0;
      LOWORD(MasterIrp->MdlAddress) = 0;
      BYTE2(MasterIrp->MdlAddress) = 0;
      *(_DWORD *)&MasterIrp->Type = 2;
      *((_BYTE *)&MasterIrp->Size + 2) = *(_BYTE *)(a2 + 3);
      RfcommCompleteTdiIrp(v15);
    }
    else
    {
      _InterlockedExchange((volatile __int32 *)(v11 + 196), 1);
      if ( !v13 )
        goto LABEL_9;
    }
    RefObj_ReleaseEx(v13 + 24, 1312901187, 3848, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\rfcomm.c");
  }
  else
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 56), *(_BYTE *)(a1 + 64));
    v7 = 0;
  }
LABEL_9:
  *a4 = v11;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      3,
      99,
      (__int64)WPP_b836b845fcda37d2ab199c1061241d17_Traceguids);
  return v7;
}

```

## disassembly

```asm
0x14001204c  push    rbx
0x14001204e  push    rbp
0x14001204f  push    rsi
0x140012050  push    rdi
0x140012051  push    r12
0x140012053  push    r13
0x140012055  push    r14
0x140012057  push    r15
0x140012059  sub     rsp, 38h
0x14001205d  mov     r12, r9
0x140012060  mov     r15, rdx
0x140012063  mov     rsi, rcx
0x140012066  lea     r13, WPP_RECORDER_INITIALIZED
0x14001206d  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140012074  lea     rbp, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x14001207b  jz      short loc_14001209C
0x14001207d  mov     rcx, cs:WPP_GLOBAL_Control
0x140012084  mov     r9d, 62h ; 'b'
0x14001208a  mov     [rsp+78h+var_58], rbp
0x14001208f  mov     rcx, [rcx+40h]
0x140012093  lea     r8d, [r9-5Fh]
0x140012097  call    WPP_RECORDER_SF_
0x14001209c  lea     r14, [rsi+38h]
0x1400120a0  mov     rcx, r14; SpinLock
0x1400120a3  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400120aa  nop     dword ptr [rax+rax+00h]
0x1400120af  mov     [rsi+40h], al
0x1400120b2  mov     edi, 1
0x1400120b7  mov     dl, [r15+2]
0x1400120bb  mov     rcx, rsi
0x1400120be  shr     dl, 2
0x1400120c1  mov     r8b, dil
0x1400120c4  call    ChannelFindLocked
0x1400120c9  mov     rbx, rax
0x1400120cc  test    rax, rax
0x1400120cf  jz      loc_1400121B4
0x1400120d5  mov     edx, 4E414843h
0x1400120da  mov     rcx, rax
0x1400120dd  call    ChannelReferenceConnLocked
0x1400120e2  mov     dl, [r15+3]
0x1400120e6  mov     rcx, r14; SpinLock
0x1400120e9  mov     [rbx+0C8h], dl
0x1400120ef  mov     rbp, rax
0x1400120f2  mov     dl, [rsi+40h]; NewIrql
0x1400120f5  call    cs:__imp_KeReleaseSpinLock
0x1400120fc  nop     dword ptr [rax+rax+00h]
0x140012101  test    rbp, rbp
0x140012104  jz      short loc_140012144
0x140012106  lea     rcx, [rbp+2E0h]
0x14001210d  call    IrpList_Dequeue
0x140012112  test    rax, rax
0x140012115  jz      short loc_140012144
0x140012117  mov     rdx, [rax+18h]
0x14001211b  lea     r8d, [rdi+0Ah]
0x14001211f  xor     ecx, ecx
0x140012121  mov     [rdx], rcx
0x140012124  mov     [rdx+8], cx
0x140012128  mov     [rdx+0Ah], cl
0x14001212b  mov     dword ptr [rdx], 2
0x140012131  mov     cl, [r15+3]
0x140012135  mov     [rdx+4], cl
0x140012138  xor     edx, edx
0x14001213a  mov     rcx, rax; Irp
0x14001213d  call    RfcommCompleteTdiIrp
0x140012142  jmp     short loc_140012151
0x140012144  mov     eax, edi
0x140012146  xchg    eax, [rbx+0C4h]
0x14001214c  test    rbp, rbp
0x14001214f  jz      short loc_14001216C
0x140012151  lea     rcx, [rbp+18h]
0x140012155  mov     edx, 4E414843h
0x14001215a  lea     r9, aOnecoreDrivers_3; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140012161  mov     r8d, 0F08h
0x140012167  call    RefObj_ReleaseEx
0x14001216c  lea     rbp, WPP_b836b845fcda37d2ab199c1061241d17_Traceguids
0x140012173  mov     [r12], rbx
0x140012177  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14001217e  jz      short loc_14001219F
0x140012180  mov     rcx, cs:WPP_GLOBAL_Control
0x140012187  mov     r9d, 63h ; 'c'
0x14001218d  mov     [rsp+78h+var_58], rbp
0x140012192  mov     rcx, [rcx+40h]
0x140012196  lea     r8d, [r9-60h]
0x14001219a  call    WPP_RECORDER_SF_
0x14001219f  mov     al, dil
0x1400121a2  add     rsp, 38h
0x1400121a6  pop     r15
0x1400121a8  pop     r14
0x1400121aa  pop     r13
0x1400121ac  pop     r12
0x1400121ae  pop     rdi
0x1400121af  pop     rsi
0x1400121b0  pop     rbp
0x1400121b1  pop     rbx
0x1400121b2  retn
0x1400121b4  mov     dl, [rsi+40h]; NewIrql
0x1400121b7  mov     rcx, r14; SpinLock
0x1400121ba  call    cs:__imp_KeReleaseSpinLock
0x1400121c1  nop     dword ptr [rax+rax+00h]
0x1400121c6  xor     dil, dil
0x1400121c9  jmp     short loc_140012173
```
