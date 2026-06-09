# CDistribution::CreatePacket(_IRP *,CTransaction *,int,CACSendParameters const *,ACSendParametersPointerContents const *)

- ea: `0x14000dc20`
- end: `0x14000debb`
- name: `?CreatePacket@CDistribution@@EEAAJPEAU_IRP@@PEAVCTransaction@@HPEBVCACSendParameters@@PEBUACSendParametersPointerContents@@@Z`
- size: `667`
- prototype: `int(CDistribution *__hidden this, struct _IRP *, struct CTransaction *, int, const struct CACSendParameters *, const struct ACSendParametersPointerContents *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001cb0`
- `0x14000d848`
- `0x14000da30`
- `0x14000dc20`
- `0x140011dc4`
- `0x140012754`
- `0x140017b04`
- `0x1400194ec`
- `0x14001d9e4`

## pseudocode

```c
__int64 __fastcall CDistribution::CreatePacket(
        CDistribution *this,
        struct _IRP *a2,
        struct CTransaction *a3,
        int a4,
        const struct CACSendParameters *a5,
        const struct ACSendParametersPointerContents *a6)
{
  CDistribution *v6; // rsi
  CDistribution *v7; // rdi
  int v8; // r10d
  __int128 v12; // xmm6
  int v13; // r12d
  char v14; // r13
  CDistribution *v15; // rcx
  char v16; // cl
  CDistribution *v17; // rax
  CDistribution *v18; // r9
  CDistribution *v19; // rcx
  struct CPacketBuffer *v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  CDistribution *v23; // rax
  CDistribution *v24; // r8
  bool Packet; // al
  int PacketRequest; // r14d
  CDistribution *i; // rdi
  CDistribution *v29; // r15
  CDistribution *v30; // rcx
  struct CPacketBuffer *v31; // rax
  CDistribution *v32; // r8
  CDistribution *v33; // rax
  CDistribution *v34; // rdx
  __int128 v35; // [rsp+60h] [rbp-68h] BYREF
  int v36; // [rsp+70h] [rbp-58h]
  char v37; // [rsp+D0h] [rbp+8h]
  int v38; // [rsp+D8h] [rbp+10h]

  *((_DWORD *)&a2->Tail.CompletionKey + 6) |= 0x80u;
  v6 = (CDistribution *)((char *)this + 384);
  v7 = (CDistribution *)*((_QWORD *)this + 48);
  v8 = a4;
  if ( v7 == (CDistribution *)((char *)this + 384) )
  {
    CBaseObject::Release(this);
    if ( a3 )
      CBaseObject::Release(a3);
    return 0;
  }
  v12 = 0;
  v37 = 0;
  v13 = 0;
  v14 = 0;
  while ( 1 )
  {
    v15 = 0;
    if ( v6 != v7 )
      v15 = v7;
    if ( !v15 )
      break;
    v16 = *((_BYTE *)v15 + 24);
    v17 = v7;
    if ( v6 == v7 )
      v17 = 0;
    v18 = v7;
    if ( v6 == v7 )
      v18 = 0;
    v38 = CPacket::SyncCreate(
            *((struct _DEVICE_OBJECT **)this + 8),
            a2,
            a3,
            *((struct CQueue **)v18 + 2),
            *((_DWORD *)this + 100),
            *((const struct QUEUE_FORMAT *const *)this + 51),
            v8,
            a5,
            a6,
            this,
            v16,
            (struct CPacket **)v17 + 4);
    if ( v38 < 0 )
    {
      if ( CIrp2Pkt::SafePeekFirstPacket(a2) )
        ACpCleanupAttachedPackets(a2);
      return (unsigned int)v38;
    }
    v19 = v7;
    if ( v6 == v7 )
      v19 = 0;
    v20 = CQEntry::Buffer(*((CQEntry **)v19 + 4));
    v21 = (__int64)v20 + 92;
    if ( !v20 )
      v21 = 56;
    if ( v37 )
    {
      *(_DWORD *)v21 = v13;
    }
    else
    {
      v13 = *(_DWORD *)v21;
      v22 = (__int64)v20 + 52;
      v37 = 1;
      if ( !v20 )
        v22 = 16;
      v12 = *(_OWORD *)v22;
    }
    v23 = v7;
    v24 = v7;
    if ( v6 == v7 )
    {
      v23 = 0;
      v24 = 0;
    }
    Packet = CQueue::NeedAsyncCreatePacket(*((CQueue **)v23 + 2), v20, *((_BYTE *)v24 + 24), 0);
    v7 = *(CDistribution **)v7;
    v8 = a4;
    if ( Packet )
      v14 = 1;
  }
  v35 = v12;
  v36 = v13;
  PacketRequest = ACpSetMsgIdProperty((__int64)a5, (__int64)&v35);
  if ( PacketRequest < 0 )
  {
LABEL_31:
    ACpCleanupAttachedPackets(a2);
    return (unsigned int)PacketRequest;
  }
  if ( !v14 )
    return 0;
  for ( i = *(CDistribution **)v6; ; i = *(CDistribution **)i )
  {
    v29 = 0;
    if ( v6 != i )
      v29 = i;
    if ( !v29 )
      break;
    v30 = i;
    if ( v6 == i )
      v30 = 0;
    v31 = CQEntry::Buffer(*((CQEntry **)v30 + 4));
    if ( !v31 )
      goto LABEL_31;
    v32 = i;
    if ( v6 == i )
      v32 = 0;
    if ( CQueue::NeedAsyncCreatePacket(*((CQueue **)v29 + 2), v31, *((_BYTE *)v32 + 24), 0) )
    {
      v33 = i;
      v34 = i;
      if ( v6 == i )
      {
        v33 = 0;
        v34 = 0;
      }
      PacketRequest = CPacket::IssueCreatePacketRequest(*((CPacket **)v33 + 4), *((_BYTE *)v34 + 24));
      if ( PacketRequest < 0 )
        goto LABEL_31;
      ++*(_DWORD *)(a2->IoStatus.Information + 20);
    }
  }
  return 259;
}

```

## disassembly

```asm
0x14000dc20  mov     rax, rsp
0x14000dc23  mov     [rax+18h], rbx
0x14000dc27  mov     [rax+20h], r9d
0x14000dc2b  push    rbp
0x14000dc2c  push    rsi
0x14000dc2d  push    rdi
0x14000dc2e  push    r12
0x14000dc30  push    r13
0x14000dc32  push    r14
0x14000dc34  push    r15
0x14000dc36  sub     rsp, 90h
0x14000dc3d  bts     dword ptr [rdx+90h], 7
0x14000dc45  lea     rsi, [rcx+180h]
0x14000dc4c  mov     rdi, [rsi]
0x14000dc4f  mov     r10d, r9d
0x14000dc52  movaps  xmmword ptr [rax-48h], xmm6
0x14000dc56  mov     r15, r8
0x14000dc59  mov     rbp, rdx
0x14000dc5c  mov     r14, rcx
0x14000dc5f  cmp     rdi, rsi
0x14000dc62  jnz     short loc_14000DC7F
0x14000dc64  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14000dc69  test    r15, r15
0x14000dc6c  jz      loc_14000DE0F
0x14000dc72  mov     rcx, r15; this
0x14000dc75  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14000dc7a  jmp     loc_14000DE0F
0x14000dc7f  xor     ebx, ebx
0x14000dc81  xorps   xmm6, xmm6
0x14000dc84  mov     [rsp+0C8h+arg_0], bl
0x14000dc8b  xor     r12d, r12d
0x14000dc8e  mov     r13b, bl
0x14000dc91  cmp     rsi, rdi
0x14000dc94  mov     rcx, rbx
0x14000dc97  cmovnz  rcx, rdi
0x14000dc9b  test    rcx, rcx
0x14000dc9e  jz      loc_14000DDD7
0x14000dca4  mov     cl, [rcx+18h]
0x14000dca7  cmp     rsi, rdi
0x14000dcaa  mov     rdx, [r14+198h]
0x14000dcb1  mov     rax, rdi
0x14000dcb4  mov     r8d, [r14+190h]
0x14000dcbb  cmovz   rax, rbx
0x14000dcbf  mov     r9, rdi
0x14000dcc2  cmovz   r9, rbx
0x14000dcc6  add     rax, 20h ; ' '
0x14000dcca  mov     [rsp+0C8h+var_70], rax; struct CPacket **
0x14000dccf  mov     rax, [rsp+0C8h+arg_28]
0x14000dcd7  mov     [rsp+0C8h+var_78], cl; bool
0x14000dcdb  mov     r9, [r9+10h]; struct CQueue *
0x14000dcdf  mov     rcx, [r14+40h]; struct _DEVICE_OBJECT *
0x14000dce3  mov     [rsp+0C8h+var_80], r14; struct CQueue *
0x14000dce8  mov     [rsp+0C8h+var_88], rax; struct ACSendParametersPointerContents *
0x14000dced  mov     rax, [rsp+0C8h+arg_20]
0x14000dcf5  mov     [rsp+0C8h+var_90], rax; struct CACSendParameters *
0x14000dcfa  mov     [rsp+0C8h+var_98], r10d; int
0x14000dcff  mov     [rsp+0C8h+var_A0], rdx; struct QUEUE_FORMAT *
0x14000dd04  mov     rdx, rbp; struct _IRP *
0x14000dd07  mov     [rsp+0C8h+var_A8], r8d; unsigned int
0x14000dd0c  mov     r8, r15; struct CTransaction *
0x14000dd0f  call    ?SyncCreate@CPacket@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAVCTransaction@@PEAVCQueue@@KQEBUQUEUE_FORMAT@@HPEBVCACSendParameters@@PEBUACSendParametersPointerContents@@3_NPEAPEAV1@@Z; CPacket::SyncCreate(_DEVICE_OBJECT *,_IRP *,CTransaction *,CQueue *,ulong,QUEUE_FORMAT const * const,int,CACSendParameters const *,ACSendParametersPointerContents const *,CQueue *,bool,CPacket * *)
0x14000dd14  mov     [rsp+0C8h+arg_8], eax
0x14000dd1b  test    eax, eax
0x14000dd1d  js      loc_14000DDB6
0x14000dd23  cmp     rsi, rdi
0x14000dd26  mov     rcx, rdi
0x14000dd29  cmovz   rcx, rbx
0x14000dd2d  mov     rcx, [rcx+20h]; this
0x14000dd31  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14000dd36  mov     rdx, rax; struct CPacketBuffer *
0x14000dd39  test    rdx, rdx
0x14000dd3c  lea     rcx, [rax+5Ch]
0x14000dd40  mov     eax, 38h ; '8'
0x14000dd45  cmovz   rcx, rax
0x14000dd49  cmp     [rsp+0C8h+arg_0], bl
0x14000dd50  jz      short loc_14000DD57
0x14000dd52  mov     [rcx], r12d
0x14000dd55  jmp     short loc_14000DD76
0x14000dd57  mov     r12d, [rcx]
0x14000dd5a  lea     rax, [rdx+34h]
0x14000dd5e  test    rdx, rdx
0x14000dd61  mov     [rsp+0C8h+arg_0], 1
0x14000dd69  mov     r8d, 10h
0x14000dd6f  cmovz   rax, r8
0x14000dd73  movups  xmm6, xmmword ptr [rax]
0x14000dd76  cmp     rsi, rdi
0x14000dd79  mov     rax, rdi
0x14000dd7c  mov     r8, rdi
0x14000dd7f  cmovz   rax, rbx
0x14000dd83  cmovz   r8, rbx
0x14000dd87  xor     r9d, r9d; bool
0x14000dd8a  mov     rcx, [rax+10h]; this
0x14000dd8e  mov     r8b, [r8+18h]; bool
0x14000dd92  call    ?NeedAsyncCreatePacket@CQueue@@QEBA_NPEAVCPacketBuffer@@_N1@Z; CQueue::NeedAsyncCreatePacket(CPacketBuffer *,bool,bool)
0x14000dd97  mov     rdi, [rdi]
0x14000dd9a  test    al, al
0x14000dd9c  mov     r10d, [rsp+0C8h+arg_18]
0x14000dda4  mov     eax, 1
0x14000dda9  movzx   r13d, r13b
0x14000ddad  cmovnz  r13d, eax
0x14000ddb1  jmp     loc_14000DC91
0x14000ddb6  mov     rcx, rbp; struct _IRP *
0x14000ddb9  call    ?SafePeekFirstPacket@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@@Z; CIrp2Pkt::SafePeekFirstPacket(_IRP *)
0x14000ddbe  test    rax, rax
0x14000ddc1  jz      short loc_14000DDCB
0x14000ddc3  mov     rcx, rbp; struct _IRP *
0x14000ddc6  call    ACpCleanupAttachedPackets
0x14000ddcb  mov     eax, [rsp+0C8h+arg_8]
0x14000ddd2  jmp     loc_14000DE9A
0x14000ddd7  mov     rcx, [rsp+0C8h+arg_20]
0x14000dddf  lea     rdx, [rsp+0C8h+var_68]
0x14000dde4  movaps  [rsp+0C8h+var_68], xmm6
0x14000dde9  mov     [rsp+0C8h+var_58], r12d
0x14000ddee  call    ACpSetMsgIdProperty
0x14000ddf3  mov     r14d, eax
0x14000ddf6  test    eax, eax
0x14000ddf8  jns     short loc_14000DE0A
0x14000ddfa  mov     rcx, rbp; struct _IRP *
0x14000ddfd  call    ACpCleanupAttachedPackets
0x14000de02  mov     eax, r14d
0x14000de05  jmp     loc_14000DE9A
0x14000de0a  test    r13b, r13b
0x14000de0d  jnz     short loc_14000DE16
0x14000de0f  xor     eax, eax
0x14000de11  jmp     loc_14000DE9A
0x14000de16  mov     rdi, [rsi]
0x14000de19  cmp     rsi, rdi
0x14000de1c  mov     r15, rbx
0x14000de1f  cmovnz  r15, rdi
0x14000de23  test    r15, r15
0x14000de26  jz      short loc_14000DE95
0x14000de28  cmp     rsi, rdi
0x14000de2b  mov     rcx, rdi
0x14000de2e  cmovz   rcx, rbx
0x14000de32  mov     rcx, [rcx+20h]; this
0x14000de36  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14000de3b  test    rax, rax
0x14000de3e  jz      short loc_14000DDFA
0x14000de40  mov     rcx, [r15+10h]; this
0x14000de44  cmp     rsi, rdi
0x14000de47  mov     r8, rdi
0x14000de4a  mov     rdx, rax; struct CPacketBuffer *
0x14000de4d  cmovz   r8, rbx
0x14000de51  xor     r9d, r9d; bool
0x14000de54  mov     r8b, [r8+18h]; bool
0x14000de58  call    ?NeedAsyncCreatePacket@CQueue@@QEBA_NPEAVCPacketBuffer@@_N1@Z; CQueue::NeedAsyncCreatePacket(CPacketBuffer *,bool,bool)
0x14000de5d  test    al, al
0x14000de5f  jz      short loc_14000DE90
0x14000de61  cmp     rsi, rdi
0x14000de64  mov     rax, rdi
0x14000de67  mov     rdx, rdi
0x14000de6a  cmovz   rax, rbx
0x14000de6e  cmovz   rdx, rbx
0x14000de72  mov     rcx, [rax+20h]; this
0x14000de76  mov     dl, [rdx+18h]; bool
0x14000de79  call    ?IssueCreatePacketRequest@CPacket@@QEAAJ_N@Z; CPacket::IssueCreatePacketRequest(bool)
0x14000de7e  mov     r14d, eax
0x14000de81  test    eax, eax
0x14000de83  js      loc_14000DDFA
0x14000de89  mov     rax, [rbp+38h]
0x14000de8d  inc     dword ptr [rax+14h]
0x14000de90  mov     rdi, [rdi]
0x14000de93  jmp     short loc_14000DE19
0x14000de95  mov     eax, 103h
0x14000de9a  lea     r11, [rsp+0C8h+var_38]
0x14000dea2  mov     rbx, [r11+50h]
0x14000dea6  movaps  xmm6, xmmword ptr [r11-10h]
0x14000deab  mov     rsp, r11
0x14000deae  pop     r15
0x14000deb0  pop     r14
0x14000deb2  pop     r13
0x14000deb4  pop     r12
0x14000deb6  pop     rdi
0x14000deb7  pop     rsi
0x14000deb8  pop     rbp
0x14000deb9  retn
```
