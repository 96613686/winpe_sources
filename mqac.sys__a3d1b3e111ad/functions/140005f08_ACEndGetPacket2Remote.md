# ACEndGetPacket2Remote

- ea: `0x140005f08`
- end: `0x1400060b7`
- name: `ACEndGetPacket2Remote`
- size: `431`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000a3b0`

## callees

- `0x140001010`
- `0x140001cb0`
- `0x140003d84`
- `0x140005f08`
- `0x140009adc`
- `0x14000a1d4`
- `0x14000cb4c`
- `0x140018b9c`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140005f33`
- `ntoskrnl!ProbeForRead` at `0x140005f33`

## pseudocode

```c
__int64 __fastcall ACEndGetPacket2Remote(struct _DEVICE_OBJECT *a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // edi
  struct CPacket *v6; // r15
  CQEntry *v7; // rsi
  struct CPacketBuffer *v9; // r15
  struct CCursor *v10; // rax
  unsigned int v11; // edx
  int v12; // ecx
  _OWORD v13[4]; // [rsp+40h] [rbp-48h] BYREF

  v5 = 1;
  ProbeForRead((volatile void *)a3, 0x48u, 1u);
  v6 = *(struct CPacket **)(a3 + 24);
  v7 = CPacketHandleToCPacket(a1, v6);
  if ( v7 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 87, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v7);
    }
    v9 = CQEntry::Buffer(v7);
    if ( v9 )
    {
      CQEntry::ReleaseBuffer(v7);
      v10 = 0;
      v11 = *(_DWORD *)(a3 + 8);
      if ( v11 )
        v10 = CCursor::Validate(a1, v11);
      v12 = *(_DWORD *)(a3 + 4);
      if ( v12 < 0 || (v12 & 0x40000010) == 0x40000010 )
        v5 = 0;
      v13[0] = *(_OWORD *)(a3 + 56);
      return (unsigned int)CPacket::RemoteRequestTail(v7, v10, v5, v13, v9);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 88, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v7);
      }
      return 3221225626LL;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 86, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids, v6);
    }
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x140005f08  push    rbx
0x140005f0a  push    rsi
0x140005f0b  push    rdi
0x140005f0c  push    r12
0x140005f0e  push    r14
0x140005f10  push    r15
0x140005f12  sub     rsp, 58h
0x140005f16  mov     r14, r8
0x140005f19  mov     r12, rcx
0x140005f1c  mov     [rsp+88h+var_50], 0
0x140005f25  mov     edi, 1
0x140005f2a  mov     r8d, edi; Alignment
0x140005f2d  lea     edx, [rdi+47h]; Length
0x140005f30  mov     rcx, r14; Address
0x140005f33  call    cs:__imp_ProbeForRead
0x140005f3a  nop     dword ptr [rax+rax+00h]
0x140005f3f  mov     r15, [r14+18h]
0x140005f43  mov     [rsp+88h+var_50], r15
0x140005f48  mov     rdx, r15; struct CPacket *
0x140005f4b  mov     rcx, r12; struct _DEVICE_OBJECT *
0x140005f4e  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAU_DEVICE_OBJECT@@PEAV1@@Z; CPacketHandleToCPacket(_DEVICE_OBJECT *,CPacket *)
0x140005f53  mov     rsi, rax
0x140005f56  test    rax, rax
0x140005f59  jnz     short loc_140005F96
0x140005f5b  lea     rbx, WPP_GLOBAL_Control
0x140005f62  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f69  cmp     rcx, rbx
0x140005f6c  jz      short loc_140005F8C
0x140005f6e  mov     eax, [rcx+6Ch]
0x140005f71  test    dil, al
0x140005f74  jz      short loc_140005F8C
0x140005f76  lea     edx, [rdi+55h]
0x140005f79  mov     r9, r15
0x140005f7c  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005f83  mov     rcx, [rcx+58h]
0x140005f87  call    WPP_SF_q
0x140005f8c  mov     eax, 0C000000Dh
0x140005f91  jmp     loc_1400060A8
0x140005f96  lea     rbx, WPP_GLOBAL_Control
0x140005f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fa4  cmp     rcx, rbx
0x140005fa7  jz      short loc_140005FC8
0x140005fa9  mov     eax, [rcx+6Ch]
0x140005fac  test    al, 4
0x140005fae  jz      short loc_140005FC8
0x140005fb0  mov     edx, 57h ; 'W'
0x140005fb5  mov     r9, rsi
0x140005fb8  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005fbf  mov     rcx, [rcx+58h]
0x140005fc3  call    WPP_SF_q
0x140005fc8  mov     rcx, rsi; this
0x140005fcb  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x140005fd0  mov     r15, rax
0x140005fd3  test    rax, rax
0x140005fd6  jnz     short loc_14000600D
0x140005fd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fdf  cmp     rcx, rbx
0x140005fe2  jz      short loc_140006003
0x140005fe4  mov     eax, [rcx+6Ch]
0x140005fe7  test    dil, al
0x140005fea  jz      short loc_140006003
0x140005fec  lea     edx, [r15+58h]
0x140005ff0  mov     r9, rsi
0x140005ff3  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x140005ffa  mov     rcx, [rcx+58h]
0x140005ffe  call    WPP_SF_q
0x140006003  mov     eax, 0C000009Ah
0x140006008  jmp     loc_1400060A8
0x14000600d  mov     rcx, rsi; this
0x140006010  call    ?ReleaseBuffer@CQEntry@@QEBAXXZ; CQEntry::ReleaseBuffer(void)
0x140006015  xor     eax, eax
0x140006017  mov     edx, [r14+8]; unsigned int
0x14000601b  test    edx, edx
0x14000601d  jz      short loc_140006027
0x14000601f  mov     rcx, r12; struct _DEVICE_OBJECT *
0x140006022  call    ?Validate@CCursor@@SAPEAV1@PEAU_DEVICE_OBJECT@@K@Z; CCursor::Validate(_DEVICE_OBJECT *,ulong)
0x140006027  mov     ecx, [r14+4]
0x14000602b  test    ecx, ecx
0x14000602d  js      short loc_14000603A
0x14000602f  mov     edx, 40000010h
0x140006034  and     ecx, edx
0x140006036  cmp     ecx, edx
0x140006038  jnz     short loc_14000603C
0x14000603a  xor     edi, edi
0x14000603c  movups  xmm0, xmmword ptr [r14+38h]
0x140006041  movdqu  [rsp+88h+var_48], xmm0
0x140006047  mov     [rsp+88h+var_68], r15
0x14000604c  lea     r9, [rsp+88h+var_48]
0x140006051  mov     r8d, edi
0x140006054  mov     rdx, rax
0x140006057  mov     rcx, rsi
0x14000605a  call    ?RemoteRequestTail@CPacket@@QEAAJPEAVCCursor@@HUBOID@@PEAVCPacketBuffer@@@Z; CPacket::RemoteRequestTail(CCursor *,int,BOID,CPacketBuffer *)
0x14000605f  mov     ebx, eax
0x140006061  mov     [rsp+88h+var_58], eax
0x140006065  jmp     short loc_1400060A6
0x140006067  mov     ebx, eax
0x140006069  mov     [rsp+88h+var_58], eax
0x14000606d  lea     rax, WPP_GLOBAL_Control
0x140006074  mov     rcx, cs:WPP_GLOBAL_Control
0x14000607b  cmp     rcx, rax
0x14000607e  jz      short loc_1400060A6
0x140006080  mov     eax, [rcx+6Ch]
0x140006083  test    al, 1
0x140006085  jz      short loc_1400060A6
0x140006087  mov     edx, 59h ; 'Y'
0x14000608c  mov     dword ptr [rsp+88h+var_68], ebx
0x140006090  mov     r9, [rsp+88h+var_50]
0x140006095  lea     r8, WPP_f86a1d0b65b9332f45d2e4d56fd5f4d7_Traceguids
0x14000609c  mov     rcx, [rcx+58h]
0x1400060a0  call    WPP_SF_qD
0x1400060a5  nop
0x1400060a6  mov     eax, ebx
0x1400060a8  add     rsp, 58h
0x1400060ac  pop     r15
0x1400060ae  pop     r14
0x1400060b0  pop     r12
0x1400060b2  pop     rdi
0x1400060b3  pop     rsi
0x1400060b4  pop     rbx
0x1400060b5  retn
```
