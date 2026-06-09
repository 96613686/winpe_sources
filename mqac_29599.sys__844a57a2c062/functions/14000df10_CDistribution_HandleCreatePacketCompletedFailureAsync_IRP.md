# CDistribution::HandleCreatePacketCompletedFailureAsync(_IRP *)

- ea: `0x14000df10`
- end: `0x14000df57`
- name: `?HandleCreatePacketCompletedFailureAsync@CDistribution@@UEAAXPEAU_IRP@@@Z`
- size: `71`
- prototype: `void(CDistribution *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000d728`
- `0x14000d848`
- `0x14000df10`
- `0x140011dc4`

## pseudocode

```c
void __fastcall CDistribution::HandleCreatePacketCompletedFailureAsync(CDistribution *this, struct _IRP *a2)
{
  struct CPacket *Packet; // rax
  struct _IRP *v3; // r8
  __int64 v4; // r9
  __int64 v5; // [rsp+40h] [rbp+18h] BYREF
  __int64 v6; // [rsp+48h] [rbp+20h] BYREF

  Packet = CIrp2Pkt::SafePeekFirstPacket(a2);
  if ( Packet )
  {
    v5 = *((_QWORD *)Packet + 5);
    v6 = v4;
    ACpCleanupAttachedPackets(v3);
    R<CTransaction>::~R<CTransaction>(&v5);
    R<CTransaction>::~R<CTransaction>(&v6);
  }
}

```

## disassembly

```asm
0x14000df10  sub     rsp, 28h
0x14000df14  mov     r9, rcx
0x14000df17  mov     r8, rdx
0x14000df1a  mov     rcx, rdx; struct _IRP *
0x14000df1d  call    ?SafePeekFirstPacket@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@@Z; CIrp2Pkt::SafePeekFirstPacket(_IRP *)
0x14000df22  test    rax, rax
0x14000df25  jz      short loc_14000DF51
0x14000df27  mov     rax, [rax+28h]
0x14000df2b  mov     rcx, r8; struct _IRP *
0x14000df2e  mov     [rsp+28h+arg_10], rax
0x14000df33  mov     [rsp+28h+arg_18], r9
0x14000df38  call    ACpCleanupAttachedPackets
0x14000df3d  lea     rcx, [rsp+28h+arg_10]
0x14000df42  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14000df47  lea     rcx, [rsp+28h+arg_18]
0x14000df4c  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14000df51  add     rsp, 28h
0x14000df55  retn
```
