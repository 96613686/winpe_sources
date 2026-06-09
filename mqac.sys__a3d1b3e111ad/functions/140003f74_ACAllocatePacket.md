# ACAllocatePacket

- ea: `0x140003f74`
- end: `0x1400041a3`
- name: `ACAllocatePacket`
- size: `559`
- prototype: `__int64 __usercall@<rax>(struct _DEVICE_OBJECT *@<rcx>, volatile void *Address, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001c34`
- `0x140003d84`
- `0x140003f74`
- `0x140009a04`
- `0x140009b90`
- `0x14000b5d8`
- `0x14000ef4c`
- `0x140012754`
- `0x1400152d0`

## import_xrefs

- `ntoskrnl!ProbeForWrite` at `0x140003fe0`
- `ntoskrnl!ProbeForWrite` at `0x140003fe0`

## pseudocode

```c
__int64 __fastcall ACAllocatePacket(
        struct _DEVICE_OBJECT *a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        struct CBaseHeader **Address,
        __int64 a6)
{
  unsigned int v6; // edi
  int v11; // eax
  unsigned int v12; // edi
  struct CPacket *v13; // rdi
  struct CBaseHeader *v14; // rsi
  CQEntry *v15; // [rsp+30h] [rbp-48h] BYREF

  v6 = a4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 20, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, a4);
  }
  if ( !Address )
    return 3221225485LL;
  ProbeForWrite(Address, 0x10u, 1u);
  *Address = 0;
  Address[1] = 0;
  v15 = 0;
  v11 = CPacket::Create(&v15, a1, v6, a3, a2);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = v15;
    v14 = AC2QM(v15);
    if ( v14 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 24, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v13);
      }
      *Address = v14;
      Address[1] = (struct CBaseHeader *)GenerateCPacketHandle(a1, v13);
      CQEntry::AddRefBuffer(v13);
      *(_QWORD *)(a6 + 8) = 8;
      return 0;
    }
    else
    {
      CBaseObject::Release(v13);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_q(
          WPP_GLOBAL_Control->Queue.ListEntry.Blink,
          23,
          WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
          Address);
      }
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Dq(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        22,
        WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids,
        (unsigned int)v11,
        Address);
    }
    return v12;
  }
}

```

## disassembly

```asm
0x140003f74  push    rbx
0x140003f76  push    rsi
0x140003f77  push    rdi
0x140003f78  push    r13
0x140003f7a  push    r14
0x140003f7c  push    r15
0x140003f7e  sub     rsp, 48h
0x140003f82  mov     edi, r9d
0x140003f85  mov     esi, r8d
0x140003f88  mov     r15d, edx
0x140003f8b  mov     r14, rcx
0x140003f8e  lea     r13, WPP_GLOBAL_Control
0x140003f95  mov     rcx, cs:WPP_GLOBAL_Control
0x140003f9c  cmp     rcx, r13
0x140003f9f  jz      short loc_140003FBD
0x140003fa1  mov     eax, [rcx+6Ch]
0x140003fa4  test    al, 4
0x140003fa6  jz      short loc_140003FBD
0x140003fa8  mov     edx, 14h
0x140003fad  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140003fb4  mov     rcx, [rcx+58h]
0x140003fb8  call    WPP_SF_d
0x140003fbd  mov     rbx, [rsp+78h+Address]
0x140003fc5  test    rbx, rbx
0x140003fc8  jnz     short loc_140003FD4
0x140003fca  mov     eax, 0C000000Dh
0x140003fcf  jmp     loc_140004194
0x140003fd4  mov     edx, 10h; Length
0x140003fd9  lea     r8d, [rdx-0Fh]; Alignment
0x140003fdd  mov     rcx, rbx; Address
0x140003fe0  call    cs:__imp_ProbeForWrite
0x140003fe7  nop     dword ptr [rax+rax+00h]
0x140003fec  mov     qword ptr [rbx], 0
0x140003ff3  mov     qword ptr [rbx+8], 0
0x140003ffb  mov     [rsp+78h+var_48], 0
0x140004004  mov     dword ptr [rsp+78h+var_58], r15d
0x140004009  mov     r9d, esi
0x14000400c  mov     r8d, edi
0x14000400f  mov     rdx, r14
0x140004012  lea     rcx, [rsp+78h+var_48]
0x140004017  call    ?Create@CPacket@@SAJPEAPEAV1@PEAU_DEVICE_OBJECT@@KW4ACPoolType@@H@Z; CPacket::Create(CPacket * *,_DEVICE_OBJECT *,ulong,ACPoolType,int)
0x14000401c  mov     edi, eax
0x14000401e  test    eax, eax
0x140004020  jns     short loc_14000405A
0x140004022  mov     rcx, cs:WPP_GLOBAL_Control
0x140004029  cmp     rcx, r13
0x14000402c  jz      short loc_140004053
0x14000402e  mov     edx, [rcx+6Ch]
0x140004031  test    dl, 1
0x140004034  jz      short loc_140004053
0x140004036  mov     edx, 16h
0x14000403b  mov     [rsp+78h+var_58], rbx
0x140004040  mov     r9d, eax
0x140004043  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000404a  mov     rcx, [rcx+58h]
0x14000404e  call    WPP_SF_Dq
0x140004053  mov     eax, edi
0x140004055  jmp     loc_140004194
0x14000405a  mov     rdi, [rsp+78h+var_48]
0x14000405f  mov     rcx, rdi; struct CPacket *
0x140004062  call    ?AC2QM@@YAPEAUCBaseHeader@@PEAVCPacket@@@Z; AC2QM(CPacket *)
0x140004067  mov     rsi, rax
0x14000406a  test    rax, rax
0x14000406d  jnz     short loc_1400040AA
0x14000406f  mov     rcx, rdi; this
0x140004072  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140004077  mov     rcx, cs:WPP_GLOBAL_Control
0x14000407e  cmp     rcx, r13
0x140004081  jz      short loc_1400040A0
0x140004083  mov     eax, [rcx+6Ch]
0x140004086  test    al, 1
0x140004088  jz      short loc_1400040A0
0x14000408a  lea     edx, [rsi+17h]
0x14000408d  mov     r9, rbx
0x140004090  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004097  mov     rcx, [rcx+58h]
0x14000409b  call    WPP_SF_q
0x1400040a0  mov     eax, 0C000009Ah
0x1400040a5  jmp     loc_140004194
0x1400040aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040b1  cmp     rcx, r13
0x1400040b4  jz      short loc_1400040D6
0x1400040b6  mov     eax, [rcx+6Ch]
0x1400040b9  test    al, 4
0x1400040bb  jz      short loc_1400040D6
0x1400040bd  mov     edx, 18h
0x1400040c2  mov     r9, rdi
0x1400040c5  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x1400040cc  mov     rcx, [rcx+58h]
0x1400040d0  call    WPP_SF_q
0x1400040d5  nop
0x1400040d6  mov     [rbx], rsi
0x1400040d9  mov     rdx, rdi; struct CPacket *
0x1400040dc  mov     rcx, r14; struct _DEVICE_OBJECT *
0x1400040df  call    ?GenerateCPacketHandle@@YA_KPEAU_DEVICE_OBJECT@@PEAVCPacket@@@Z; GenerateCPacketHandle(_DEVICE_OBJECT *,CPacket *)
0x1400040e4  mov     [rbx+8], rax
0x1400040e8  mov     rcx, rdi; this
0x1400040eb  call    ?AddRefBuffer@CQEntry@@QEBAXXZ; CQEntry::AddRefBuffer(void)
0x1400040f0  nop
0x1400040f1  mov     rax, [rsp+78h+arg_28]
0x1400040f9  mov     qword ptr [rax+8], 8
0x140004101  xor     eax, eax
0x140004103  jmp     loc_140004194
0x140004108  lea     rdx, WPP_GLOBAL_Control
0x14000410f  mov     rcx, cs:WPP_GLOBAL_Control
0x140004116  cmp     rcx, rdx
0x140004119  jz      short loc_140004148
0x14000411b  mov     edx, [rcx+6Ch]
0x14000411e  test    dl, 1
0x140004121  jz      short loc_140004148
0x140004123  mov     r9d, eax
0x140004126  mov     edx, 19h
0x14000412b  mov     rax, [rsp+78h+Address]
0x140004133  mov     [rsp+78h+var_58], rax
0x140004138  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000413f  mov     rcx, [rcx+58h]
0x140004143  call    WPP_SF_Dq
0x140004148  mov     eax, 0C000000Dh
0x14000414d  jmp     short loc_140004194
0x14000414f  lea     rdx, WPP_GLOBAL_Control
0x140004156  mov     rcx, cs:WPP_GLOBAL_Control
0x14000415d  cmp     rcx, rdx
0x140004160  jz      short loc_14000418F
0x140004162  mov     edx, [rcx+6Ch]
0x140004165  test    dl, 1
0x140004168  jz      short loc_14000418F
0x14000416a  mov     r9d, eax
0x14000416d  mov     edx, 15h
0x140004172  mov     rax, [rsp+78h+Address]
0x14000417a  mov     [rsp+78h+var_58], rax
0x14000417f  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140004186  mov     rcx, [rcx+58h]
0x14000418a  call    WPP_SF_Dq
0x14000418f  mov     eax, 0C000000Dh
0x140004194  add     rsp, 48h
0x140004198  pop     r15
0x14000419a  pop     r14
0x14000419c  pop     r13
0x14000419e  pop     rdi
0x14000419f  pop     rsi
0x1400041a0  pop     rbx
0x1400041a1  retn
```
