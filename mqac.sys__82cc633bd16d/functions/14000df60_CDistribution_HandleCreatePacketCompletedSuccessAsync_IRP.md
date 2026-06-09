# CDistribution::HandleCreatePacketCompletedSuccessAsync(_IRP *)

- ea: `0x14000df60`
- end: `0x14000e1b1`
- name: `?HandleCreatePacketCompletedSuccessAsync@CDistribution@@UEAAJPEAU_IRP@@@Z`
- size: `593`
- prototype: `int(CDistribution *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14000e1c0`

## callees

- `0x140001cb0`
- `0x14000d728`
- `0x14000df60`
- `0x14000e2c0`
- `0x140011cc8`
- `0x140011dc4`
- `0x140012754`
- `0x1400183c4`
- `0x14001d54c`
- `0x14001e0c0`
- `0x140020278`

## pseudocode

```c
__int64 __fastcall CDistribution::HandleCreatePacketCompletedSuccessAsync(CDistribution *this, struct _IRP *a2)
{
  struct CPacket *Packet; // rax
  __int64 v4; // r8
  _QWORD **v5; // rdi
  _QWORD *v6; // rsi
  CTransaction *v7; // rbx
  _QWORD *v8; // rbp
  struct CPacket *AttachedPacketsHead; // rax
  _QWORD *v10; // r8
  _QWORD *v11; // rcx
  __int64 v12; // rax
  _QWORD *v13; // rcx
  int v14; // ebp
  _QWORD *i; // rsi
  _QWORD *v16; // r8
  _QWORD *v17; // rcx
  struct CPacket *v18; // r8
  _QWORD *v19; // rcx
  _QWORD *v20; // rdx
  char v22; // r15
  _QWORD *v23; // rbx
  unsigned int Status; // esi
  _QWORD *v25; // rbp
  _QWORD *v26; // rcx
  struct CPacketBuffer *v27; // r12
  int v28; // edx
  _QWORD *v29; // r8
  _QWORD *v30; // rcx
  _QWORD *v31; // r8
  int v32; // ebp
  _QWORD *v33; // rcx
  CTransaction *v34; // [rsp+60h] [rbp+8h] BYREF
  CDistribution *v35; // [rsp+70h] [rbp+18h] BYREF

  v35 = this;
  Packet = CIrp2Pkt::SafePeekFirstPacket(a2);
  v5 = (_QWORD **)(v4 + 384);
  v6 = *(_QWORD **)(v4 + 384);
  v7 = (CTransaction *)*((_QWORD *)Packet + 5);
  v34 = v7;
  while ( 1 )
  {
    v8 = 0;
    if ( v5 != v6 )
      v8 = v6;
    if ( !v8 )
      break;
    AttachedPacketsHead = CIrp2Pkt::GetAttachedPacketsHead(a2);
    v10 = v6;
    if ( v5 == v6 )
      v10 = 0;
    v10[4] = AttachedPacketsHead;
    CBaseObject::Release((CBaseObject *)v8[4]);
    v11 = v6;
    if ( v5 == v6 )
      v11 = 0;
    v12 = v11[4];
    v13 = v6;
    *(_QWORD *)(v12 + 32) = 0;
    if ( v5 == v6 )
      v13 = 0;
    *(_QWORD *)(v13[4] + 40LL) = 0;
    v6 = (_QWORD *)*v6;
  }
  if ( v7 )
  {
    v14 = *((_DWORD *)v7 + 14);
    for ( i = *v5; ; i = (_QWORD *)*i )
    {
      v16 = 0;
      if ( v5 != i )
        v16 = i;
      if ( !v16 )
        break;
      v17 = i;
      if ( (v14 & 2) != 0 )
      {
        if ( v5 == i )
          v17 = 0;
        CBaseObject::Release((CBaseObject *)v17[4]);
      }
      else
      {
        v18 = (struct CPacket *)v16[4];
        if ( v5 == i )
          v17 = 0;
        CQueue::HandleValidTransactionUsage((CQueue *)v17[2], 1, v18);
        v19 = i;
        v20 = i;
        if ( v5 == i )
        {
          v19 = 0;
          v20 = 0;
        }
        CTransaction::SendPacket(v7, (struct CQueue *)v20[2], (struct CPacket *)v19[4]);
      }
    }
    R<CTransaction>::~R<CTransaction>(&v34);
    R<CTransaction>::~R<CTransaction>(&v35);
    return (v14 & 2) != 0 ? 0xC00E0051 : 0;
  }
  v22 = 0;
  a2->IoStatus.Information = 0;
  v23 = *v5;
  Status = 0;
  while ( 1 )
  {
    v25 = 0;
    if ( v5 != v23 )
      v25 = v23;
    if ( !v25 )
      break;
    v26 = v23;
    if ( v5 == v23 )
      v26 = 0;
    v27 = CQEntry::Buffer((CQEntry *)v26[4]);
    if ( !v27 )
    {
      CBaseObject::Release((CBaseObject *)v25[4]);
      v28 = -1073741670;
LABEL_46:
      Status = CDriverContext::LastStatus((CDriverContext *)&a2->Tail, v28);
      goto LABEL_47;
    }
    v29 = v23;
    if ( v5 == v23 )
      v29 = 0;
    CQueue::HandleValidTransactionUsage((CQueue *)v25[2], 0, (struct CPacket *)v29[4]);
    v30 = v23;
    v31 = v23;
    if ( v5 == v23 )
    {
      v30 = 0;
      v31 = 0;
    }
    v32 = CQueue::PutPacket((struct _DEVICE_OBJECT **)v30[2], a2, (struct CPacket *)v31[4], v27, 0);
    if ( v32 == 259 )
    {
      v22 = 1;
      goto LABEL_47;
    }
    if ( v32 < 0 )
    {
      v33 = v23;
      if ( v5 == v23 )
        v33 = 0;
      CPacket::PacketRundown((CPacket *)v33[4], v32);
      v28 = v32;
      goto LABEL_46;
    }
LABEL_47:
    v23 = (_QWORD *)*v23;
  }
  if ( v22 )
    Status = 259;
  R<CTransaction>::~R<CTransaction>(&v34);
  R<CTransaction>::~R<CTransaction>(&v35);
  return Status;
}

```

## disassembly

```asm
0x14000df60  mov     [rsp+arg_8], rbx
0x14000df65  mov     [rsp+arg_18], rbp
0x14000df6a  push    rsi
0x14000df6b  push    rdi
0x14000df6c  push    r12
0x14000df6e  push    r14
0x14000df70  push    r15
0x14000df72  sub     rsp, 30h
0x14000df76  mov     r8, rcx
0x14000df79  mov     [rsp+58h+arg_10], rcx
0x14000df7e  mov     rcx, rdx; struct _IRP *
0x14000df81  mov     r14, rdx
0x14000df84  call    ?SafePeekFirstPacket@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@@Z; CIrp2Pkt::SafePeekFirstPacket(_IRP *)
0x14000df89  lea     rdi, [r8+180h]
0x14000df90  mov     rsi, [rdi]
0x14000df93  mov     rbx, [rax+28h]
0x14000df97  mov     [rsp+58h+arg_0], rbx
0x14000df9c  xor     ebp, ebp
0x14000df9e  cmp     rdi, rsi
0x14000dfa1  cmovnz  rbp, rsi
0x14000dfa5  test    rbp, rbp
0x14000dfa8  jz      short loc_14000E000
0x14000dfaa  mov     rcx, r14; struct _IRP *
0x14000dfad  call    ?GetAttachedPacketsHead@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@@Z; CIrp2Pkt::GetAttachedPacketsHead(_IRP *)
0x14000dfb2  xor     edx, edx
0x14000dfb4  mov     r8, rsi
0x14000dfb7  cmp     rdi, rsi
0x14000dfba  cmovz   r8, rdx
0x14000dfbe  mov     [r8+20h], rax
0x14000dfc2  mov     rcx, [rbp+20h]; this
0x14000dfc6  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14000dfcb  xor     eax, eax
0x14000dfcd  mov     rcx, rsi
0x14000dfd0  cmp     rdi, rsi
0x14000dfd3  cmovz   rcx, rax
0x14000dfd7  mov     rax, [rcx+20h]
0x14000dfdb  mov     rcx, rsi
0x14000dfde  mov     qword ptr [rax+20h], 0
0x14000dfe6  xor     eax, eax
0x14000dfe8  cmp     rdi, rsi
0x14000dfeb  cmovz   rcx, rax
0x14000dfef  mov     rax, [rcx+20h]
0x14000dff3  mov     qword ptr [rax+28h], 0
0x14000dffb  mov     rsi, [rsi]
0x14000dffe  jmp     short loc_14000DF9C
0x14000e000  test    rbx, rbx
0x14000e003  jz      loc_14000E0A6
0x14000e009  mov     ebp, [rbx+38h]
0x14000e00c  mov     rsi, [rdi]
0x14000e00f  xor     r8d, r8d
0x14000e012  cmp     rdi, rsi
0x14000e015  cmovnz  r8, rsi
0x14000e019  test    r8, r8
0x14000e01c  jz      short loc_14000E07C
0x14000e01e  xor     eax, eax
0x14000e020  mov     rcx, rsi
0x14000e023  test    bpl, 2
0x14000e027  jz      short loc_14000E03B
0x14000e029  cmp     rdi, rsi
0x14000e02c  cmovz   rcx, rax
0x14000e030  mov     rcx, [rcx+20h]; this
0x14000e034  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14000e039  jmp     short loc_14000E077
0x14000e03b  mov     r8, [r8+20h]; struct CPacket *
0x14000e03f  cmp     rdi, rsi
0x14000e042  mov     edx, 1; int
0x14000e047  cmovz   rcx, rax
0x14000e04b  mov     rcx, [rcx+10h]; this
0x14000e04f  call    ?HandleValidTransactionUsage@CQueue@@QEBAXHPEAVCPacket@@@Z; CQueue::HandleValidTransactionUsage(int,CPacket *)
0x14000e054  xor     eax, eax
0x14000e056  mov     rcx, rsi
0x14000e059  cmp     rdi, rsi
0x14000e05c  mov     rdx, rsi
0x14000e05f  cmovz   rcx, rax
0x14000e063  cmovz   rdx, rax
0x14000e067  mov     r8, [rcx+20h]; struct CPacket *
0x14000e06b  mov     rcx, rbx; this
0x14000e06e  mov     rdx, [rdx+10h]; struct CQueue *
0x14000e072  call    ?SendPacket@CTransaction@@QEAAXPEAVCQueue@@PEAVCPacket@@@Z; CTransaction::SendPacket(CQueue *,CPacket *)
0x14000e077  mov     rsi, [rsi]
0x14000e07a  jmp     short loc_14000E00F
0x14000e07c  and     bpl, 2
0x14000e080  lea     rcx, [rsp+58h+arg_0]
0x14000e085  neg     bpl
0x14000e088  sbb     ebx, ebx
0x14000e08a  and     ebx, 0C00E0051h
0x14000e090  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14000e095  lea     rcx, [rsp+58h+arg_10]
0x14000e09a  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14000e09f  mov     eax, ebx
0x14000e0a1  jmp     loc_14000E199
0x14000e0a6  xor     r15b, r15b
0x14000e0a9  mov     qword ptr [r14+38h], 0
0x14000e0b1  mov     rbx, [rdi]
0x14000e0b4  xor     esi, esi
0x14000e0b6  xor     ebp, ebp
0x14000e0b8  cmp     rdi, rbx
0x14000e0bb  cmovnz  rbp, rbx
0x14000e0bf  test    rbp, rbp
0x14000e0c2  jz      loc_14000E178
0x14000e0c8  xor     eax, eax
0x14000e0ca  mov     rcx, rbx
0x14000e0cd  cmp     rdi, rbx
0x14000e0d0  cmovz   rcx, rax
0x14000e0d4  mov     rcx, [rcx+20h]; this
0x14000e0d8  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14000e0dd  mov     r12, rax
0x14000e0e0  test    rax, rax
0x14000e0e3  jnz     short loc_14000E0F5
0x14000e0e5  mov     rcx, [rbp+20h]; this
0x14000e0e9  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14000e0ee  mov     edx, 0C000009Ah
0x14000e0f3  jmp     short loc_14000E165
0x14000e0f5  mov     rcx, [rbp+10h]; this
0x14000e0f9  xor     eax, eax
0x14000e0fb  cmp     rdi, rbx
0x14000e0fe  mov     r8, rbx
0x14000e101  cmovz   r8, rax
0x14000e105  xor     edx, edx; int
0x14000e107  mov     r8, [r8+20h]; struct CPacket *
0x14000e10b  call    ?HandleValidTransactionUsage@CQueue@@QEBAXHPEAVCPacket@@@Z; CQueue::HandleValidTransactionUsage(int,CPacket *)
0x14000e110  xor     eax, eax
0x14000e112  mov     rcx, rbx
0x14000e115  cmp     rdi, rbx
0x14000e118  mov     [rsp+58h+var_38], eax; int
0x14000e11c  mov     r8, rbx
0x14000e11f  mov     r9, r12; struct CPacketBuffer *
0x14000e122  cmovz   rcx, rax
0x14000e126  cmovz   r8, rax
0x14000e12a  mov     rdx, r14; struct _IRP *
0x14000e12d  mov     rcx, [rcx+10h]; this
0x14000e131  mov     r8, [r8+20h]; struct CPacket *
0x14000e135  call    ?PutPacket@CQueue@@QEAAJPEAU_IRP@@PEAVCPacket@@PEAVCPacketBuffer@@H@Z; CQueue::PutPacket(_IRP *,CPacket *,CPacketBuffer *,int)
0x14000e13a  mov     ebp, eax
0x14000e13c  cmp     eax, 103h
0x14000e141  jnz     short loc_14000E148
0x14000e143  mov     r15b, 1
0x14000e146  jmp     short loc_14000E170
0x14000e148  test    ebp, ebp
0x14000e14a  jns     short loc_14000E170
0x14000e14c  xor     eax, eax
0x14000e14e  mov     rcx, rbx
0x14000e151  cmp     rdi, rbx
0x14000e154  mov     edx, ebp; int
0x14000e156  cmovz   rcx, rax
0x14000e15a  mov     rcx, [rcx+20h]; this
0x14000e15e  call    ?PacketRundown@CPacket@@QEAAXJ@Z; CPacket::PacketRundown(long)
0x14000e163  mov     edx, ebp; int
0x14000e165  lea     rcx, [r14+78h]; this
0x14000e169  call    ?LastStatus@CDriverContext@@QEAAJJ@Z; CDriverContext::LastStatus(long)
0x14000e16e  mov     esi, eax
0x14000e170  mov     rbx, [rbx]
0x14000e173  jmp     loc_14000E0B6
0x14000e178  mov     eax, 103h
0x14000e17d  lea     rcx, [rsp+58h+arg_0]
0x14000e182  test    r15b, r15b
0x14000e185  cmovnz  esi, eax
0x14000e188  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14000e18d  lea     rcx, [rsp+58h+arg_10]
0x14000e192  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14000e197  mov     eax, esi
0x14000e199  mov     rbx, [rsp+58h+arg_8]
0x14000e19e  mov     rbp, [rsp+58h+arg_18]
0x14000e1a3  add     rsp, 30h
0x14000e1a7  pop     r15
0x14000e1a9  pop     r14
0x14000e1ab  pop     r12
0x14000e1ad  pop     rdi
0x14000e1ae  pop     rsi
0x14000e1af  retn
```
