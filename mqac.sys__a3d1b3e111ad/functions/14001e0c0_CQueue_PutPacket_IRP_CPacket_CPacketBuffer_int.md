# CQueue::PutPacket(_IRP *,CPacket *,CPacketBuffer *,int)

- ea: `0x14001e0c0`
- end: `0x14001e4c0`
- name: `?PutPacket@CQueue@@QEAAJPEAU_IRP@@PEAVCPacket@@PEAVCPacketBuffer@@H@Z`
- size: `1024`
- prototype: `__int64 __fastcall(CQueue *__hidden this, struct _IRP *, struct CPacket *, struct CPacketBuffer *, int)`
- caller_count: `11`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400078f4`
- `0x140007a88`
- `0x14000df60`
- `0x140015ac4`
- `0x140017d9c`
- `0x140017ec4`
- `0x14001821c`
- `0x140018b9c`
- `0x14001d390`
- `0x14001f3dc`
- `0x14001f8d4`

## callees

- `0x140001cb0`
- `0x140002b74`
- `0x140002d24`
- `0x14000b9b4`
- `0x14000baa0`
- `0x1400140f4`
- `0x14001428c`
- `0x140014c00`
- `0x14001569c`
- `0x1400183c4`
- `0x140018ff4`
- `0x140019348`
- `0x140019454`
- `0x140019dd0`
- `0x14001b114`
- `0x14001c9c0`
- `0x14001d5bc`
- `0x14001e0c0`
- `0x14001e6e8`
- `0x14001e888`
- `0x14001ec98`
- `0x140024bf0`

## pseudocode

```c
__int64 __fastcall CQueue::PutPacket(
        struct _DEVICE_OBJECT **this,
        struct _IRP *a2,
        struct CPacket *a3,
        struct CPacketBuffer *a4,
        int a5)
{
  int v9; // eax
  CPacket *v10; // rcx
  unsigned __int16 v11; // dx
  unsigned __int64 v12; // r14
  int v13; // r12d
  __int64 v14; // r9
  unsigned __int64 v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rax
  unsigned __int64 v19; // rbp
  struct CSecurityHeader *v20; // rax
  struct CPropertyHeader *v21; // rax
  int v22; // edx
  int v23; // ecx
  struct _DEVICE_OBJECT *v24; // rax
  char *DeviceExtension; // rbx
  struct _DEVICE_OBJECT *v26; // rax
  struct _IRP *Request; // rbp
  int v28; // ebx
  int v29; // eax
  struct CPacketBuffer *v30; // rax
  struct CPacketBuffer *v31; // rbx
  int v33; // eax
  _QWORD v34[2]; // [rsp+30h] [rbp-128h]
  char v35[16]; // [rsp+40h] [rbp-118h] BYREF
  int v36; // [rsp+50h] [rbp-108h]
  wchar_t v37[106]; // [rsp+5Ch] [rbp-FCh] BYREF
  unsigned int v38; // [rsp+170h] [rbp+18h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      12,
      WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids,
      a2,
      a3,
      a4);
  }
  v9 = *((_DWORD *)a3 + 13);
  if ( (v9 & 0x20000) != 0 )
  {
    v10 = a3;
    if ( (v9 & 0x10000) != 0 )
    {
      CPacket::PacketRundown(a3, -1072824278);
      return 0;
    }
    v11 = *((_WORD *)a3 + 26) & 0xE1FF;
LABEL_8:
    CPacket::Done(v10, v11, a4, 0);
    return 0;
  }
  if ( *((_QWORD *)a3 + 4) )
  {
    v13 = 0;
  }
  else
  {
    v12 = (unsigned __int64)a4 + 4;
    v13 = 1;
    if ( !*(_QWORD *)((char *)a4 + 4) )
      *(_QWORD *)v12 = ACpGetSequentialID(this[8]);
    if ( ((unsigned int (__fastcall *)(struct _DEVICE_OBJECT **))(*this)->CurrentIrp)(this)
      && (*((_WORD *)a4 + 19) & 0x1000) == 0 )
    {
      v14 = *((unsigned int *)a4 + 11);
      v34[1] = 12;
      v15 = ((unsigned __int64)a4 + 36) & -(__int64)(a4 != 0);
      v16 = 0;
      *(_WORD *)(v15 + 2) |= 0x1000u;
      v17 = v14 + v15;
      *(_QWORD *)(v14 + v15) = 12;
      v18 = 0;
      v34[0] = v14 + v15;
      do
        v16 += v34[v18++];
      while ( v18 != 2 );
      *(_DWORD *)(v17 + 8) = 2;
      *(_DWORD *)(v17 + 4) += 148;
      *(_QWORD *)(v16 + 4) = 0;
      *(_QWORD *)(v16 + 12) = 0;
      *(_DWORD *)v16 = 148;
      *(_WORD *)(v16 + 20) = 0;
      *(_WORD *)(v16 + 84) = 0;
      *(_DWORD *)((((unsigned __int64)a4 + 36) & -(__int64)(a4 != 0)) + 8) = v14 + 160;
    }
    if ( !a5 )
      CQueue::ChargeQuota((CQueue *)this, *((_DWORD *)a4 + 11));
    CPacket::CacheCurrentState(a3, a4);
    CQueue::InsertPacket((CQueue *)this, a3);
    if ( (*((_DWORD *)a3 + 13) & 0x800000) == 0 )
      CQueue::SetPacketInformation(
        (CQueue *)this,
        (struct CPacketInfo *)(v12 & ((unsigned __int128)-(__int128)(unsigned __int64)a4 >> 64)));
    if ( !a5 )
    {
      v19 = (unsigned __int64)a4 + 36;
      if ( ((_DWORD)this[21] & 0x100) != 0 )
      {
        v20 = CPacketBuffer::SecurityHeaderSafe((struct CBaseHeader *)(v19 & -(__int64)(a4 != 0)));
        if ( !v20 || (*(_BYTE *)v20 & 0x10) == 0 )
        {
          v11 = -32762;
LABEL_26:
          v10 = a3;
          goto LABEL_8;
        }
      }
      if ( *((_DWORD *)this + 60) != 1 )
      {
        v21 = CPacketBuffer::PropertyHeaderSafe((struct CBaseHeader *)(v19 & -(__int64)(a4 != 0)));
        if ( !v21 )
          goto LABEL_35;
        v22 = *((_DWORD *)this + 60);
        if ( v22 )
        {
          v23 = 1;
          if ( v22 != 2 )
            v23 = -1;
        }
        else
        {
          v23 = 0;
        }
        if ( v23 != (*((_DWORD *)v21 + 10) & 1) )
        {
LABEL_35:
          v11 = -32761;
          goto LABEL_26;
        }
      }
      if ( ((_DWORD)this[21] & 2) != 0 )
      {
        v11 = 0x8000;
        goto LABEL_26;
      }
      if ( this[23] > this[22] )
      {
        CPacket::Done(a3, 0x8003u, a4, 0);
        v24 = this[8];
        v36 = 12;
        DeviceExtension = (char *)v24->DeviceExtension;
        MQpQueueFormatToFormatName((const struct QUEUE_FORMAT *)(this + 11), v37, 0x64u, &v38, 0);
        CQMInterface::ProcessRequest((CQMInterface *)(DeviceExtension + 72), (const struct CACRequest *)v35);
        return 0;
      }
    }
  }
  if ( !_bittest((const signed __int32 *)a3 + 13, 0x12u) )
  {
    v26 = (struct _DEVICE_OBJECT *)*((_QWORD *)a3 + 7);
    if ( v26 < this[43] )
      this[43] = v26;
  }
  CQueue::UpdateFirstUnloggedLookupId((CQueue *)this, *((_QWORD *)a3 + 7), (*((unsigned __int16 *)a3 + 26) >> 11) & 1);
  if ( *((_QWORD *)a3 + 7) < (unsigned __int64)this[44] )
  {
    while ( !_bittest((const signed __int32 *)a3 + 13, 0x12u) )
    {
      Request = CQueueBase::GetRequest((CQueueBase *)this, a3);
      if ( !Request )
        break;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->Queue.ListEntry.Blink,
          13,
          WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids,
          Request,
          a3);
      }
      v28 = *((_DWORD *)&Request->Tail.CompletionKey + 6);
      v29 = CPacket::CompleteRequest(a3, Request);
      if ( (v28 & 0x20) != 0 && v29 >= 0 )
        return 0;
    }
  }
  if ( v13 )
  {
    v30 = CQEntry::Buffer(a3);
    v31 = v30;
    if ( !v30 )
      return 3221225626LL;
    if ( (*((_BYTE *)v30 + 16) & 0x10) == 0 )
    {
      v33 = ((__int64 (__fastcall *)(struct _DEVICE_OBJECT **))(*this)->CurrentIrp)(this);
      CPacket::StartTimer(a3, v31, v33, 0);
    }
    if ( (((_DWORD)this[21] & 4) != 0 || ((*((_DWORD *)v31 + 24) >> 5) & 3) == 1)
      && (*((_DWORD *)a3 + 13) & 0x800000) == 0 )
    {
      return CPacket::Store(a3, a2);
    }
    if ( (*((_BYTE *)v31 + 16) & 0x10) == 0 && !a5 )
      CPacket::SendArrivalAcknowledgment(a3);
  }
  return 0;
}

```

## disassembly

```asm
0x14001e0c0  mov     [rsp+arg_0], rbx
0x14001e0c5  mov     [rsp+arg_8], rbp
0x14001e0ca  push    rsi
0x14001e0cb  push    rdi
0x14001e0cc  push    r12
0x14001e0ce  push    r13
0x14001e0d0  push    r14
0x14001e0d2  sub     rsp, 130h
0x14001e0d9  mov     rbx, r9
0x14001e0dc  mov     rdi, r8
0x14001e0df  mov     r13, rdx
0x14001e0e2  mov     rsi, rcx
0x14001e0e5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e0ec  lea     rax, WPP_GLOBAL_Control
0x14001e0f3  cmp     rcx, rax
0x14001e0f6  jz      short loc_14001E121
0x14001e0f8  mov     eax, [rcx+6Ch]
0x14001e0fb  test    al, 4
0x14001e0fd  jz      short loc_14001E121
0x14001e0ff  mov     rcx, [rcx+58h]
0x14001e103  mov     edx, 0Ch
0x14001e108  mov     [rsp+158h+var_130], rbx
0x14001e10d  mov     r9, r13
0x14001e110  mov     qword ptr [rsp+158h+var_138], r8
0x14001e115  lea     r8, WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids
0x14001e11c  call    WPP_SF_qqq
0x14001e121  mov     eax, [rdi+34h]
0x14001e124  bt      eax, 11h
0x14001e128  jnb     short loc_14001E15E
0x14001e12a  mov     rcx, rdi; this
0x14001e12d  bt      eax, 10h
0x14001e131  jnb     short loc_14001E142
0x14001e133  mov     edx, 0C00E002Ah; int
0x14001e138  call    ?PacketRundown@CPacket@@QEAAXJ@Z; CPacket::PacketRundown(long)
0x14001e13d  jmp     loc_14001E4A1
0x14001e142  movzx   edx, word ptr [rdi+34h]
0x14001e146  mov     eax, 0E1FFh
0x14001e14b  and     dx, ax; unsigned __int16
0x14001e14e  mov     r8, rbx; struct CPacketBuffer *
0x14001e151  xor     r9d, r9d; struct CQueue *
0x14001e154  call    ?Done@CPacket@@QEAAXGPEAVCPacketBuffer@@PEAVCQueue@@@Z; CPacket::Done(ushort,CPacketBuffer *,CQueue *)
0x14001e159  jmp     loc_14001E4A1
0x14001e15e  xor     ebp, ebp
0x14001e160  cmp     [rdi+20h], rbp
0x14001e164  jnz     loc_14001E362
0x14001e16a  lea     r14, [rbx+4]
0x14001e16e  lea     r12d, [rbp+1]
0x14001e172  cmp     [r14], rbp
0x14001e175  jnz     short loc_14001E183
0x14001e177  mov     rcx, [rsi+40h]; struct _DEVICE_OBJECT *
0x14001e17b  call    ?ACpGetSequentialID@@YA_KPEAU_DEVICE_OBJECT@@@Z; ACpGetSequentialID(_DEVICE_OBJECT *)
0x14001e180  mov     [r14], rax
0x14001e183  mov     rax, [rsi]
0x14001e186  mov     rcx, rsi
0x14001e189  mov     rax, [rax+20h]
0x14001e18d  call    _guard_dispatch_icall
0x14001e192  test    eax, eax
0x14001e194  jz      short loc_14001E20E
0x14001e196  lea     rcx, [rbx+24h]
0x14001e19a  mov     r10d, 1000h
0x14001e1a0  test    [rcx+2], r10w
0x14001e1a5  jnz     short loc_14001E20E
0x14001e1a7  mov     r9d, [rbx+2Ch]
0x14001e1ab  mov     rax, rbx
0x14001e1ae  neg     rax
0x14001e1b1  mov     eax, 0Ch
0x14001e1b6  sbb     r8, r8
0x14001e1b9  mov     [rsp+158h+var_120], rax
0x14001e1be  and     r8, rcx
0x14001e1c1  mov     rcx, rbp
0x14001e1c4  or      [r8+2], r10w
0x14001e1c9  lea     rdx, [r9+r8]
0x14001e1cd  mov     [rdx], rax
0x14001e1d0  mov     rax, rbp
0x14001e1d3  mov     [rsp+158h+var_128], rdx
0x14001e1d8  add     rcx, [rsp+rax*8+158h+var_128]
0x14001e1dd  inc     rax
0x14001e1e0  cmp     rax, 2
0x14001e1e4  jnz     short loc_14001E1D8
0x14001e1e6  mov     [rdx+8], eax
0x14001e1e9  mov     eax, 94h
0x14001e1ee  add     [rdx+4], eax
0x14001e1f1  mov     [rcx+4], rbp
0x14001e1f5  mov     [rcx+0Ch], rbp
0x14001e1f9  mov     [rcx], eax
0x14001e1fb  lea     eax, [r9+0A0h]
0x14001e202  mov     [rcx+14h], bp
0x14001e206  mov     [rcx+54h], bp
0x14001e20a  mov     [r8+8], eax
0x14001e20e  cmp     [rsp+158h+arg_20], ebp
0x14001e215  jnz     short loc_14001E222
0x14001e217  mov     edx, [rbx+2Ch]; unsigned int
0x14001e21a  mov     rcx, rsi; this
0x14001e21d  call    ?ChargeQuota@CQueue@@AEAAXK@Z; CQueue::ChargeQuota(ulong)
0x14001e222  mov     rdx, rbx; struct CPacketBuffer *
0x14001e225  mov     rcx, rdi; this
0x14001e228  call    ?CacheCurrentState@CPacket@@QEAAXPEAVCPacketBuffer@@@Z; CPacket::CacheCurrentState(CPacketBuffer *)
0x14001e22d  mov     rdx, rdi; struct CPacket *
0x14001e230  mov     rcx, rsi; this
0x14001e233  call    ?InsertPacket@CQueue@@AEAAXPEAVCPacket@@@Z; CQueue::InsertPacket(CPacket *)
0x14001e238  test    dword ptr [rdi+34h], 800000h
0x14001e23f  jnz     short loc_14001E255
0x14001e241  mov     rax, rbx
0x14001e244  mov     rcx, rsi; this
0x14001e247  neg     rax
0x14001e24a  sbb     rdx, rdx
0x14001e24d  and     rdx, r14; struct CPacketInfo *
0x14001e250  call    ?SetPacketInformation@CQueue@@QEAAXPEAVCPacketInfo@@@Z; CQueue::SetPacketInformation(CPacketInfo *)
0x14001e255  cmp     [rsp+158h+arg_20], ebp
0x14001e25c  jnz     loc_14001E365
0x14001e262  test    dword ptr [rsi+0A8h], 100h
0x14001e26c  lea     rbp, [rbx+24h]
0x14001e270  jz      short loc_14001E29A
0x14001e272  mov     rax, rbx
0x14001e275  neg     rax
0x14001e278  sbb     rcx, rcx
0x14001e27b  and     rcx, rbp; struct CBaseHeader *
0x14001e27e  call    ?SecurityHeaderSafe@CPacketBuffer@@SAPEAUCSecurityHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::SecurityHeaderSafe(CBaseHeader *)
0x14001e283  test    rax, rax
0x14001e286  jz      short loc_14001E28D
0x14001e288  test    byte ptr [rax], 10h
0x14001e28b  jnz     short loc_14001E29A
0x14001e28d  mov     edx, 8006h
0x14001e292  mov     rcx, rdi
0x14001e295  jmp     loc_14001E14E
0x14001e29a  cmp     [rsi+0F0h], r12d
0x14001e2a1  jz      short loc_14001E2E8
0x14001e2a3  mov     rax, rbx
0x14001e2a6  neg     rax
0x14001e2a9  sbb     rcx, rcx
0x14001e2ac  and     rcx, rbp; struct CBaseHeader *
0x14001e2af  call    ?PropertyHeaderSafe@CPacketBuffer@@SAPEAUCPropertyHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::PropertyHeaderSafe(CBaseHeader *)
0x14001e2b4  xor     ebp, ebp
0x14001e2b6  test    rax, rax
0x14001e2b9  jz      short loc_14001E2E1
0x14001e2bb  mov     edx, [rsi+0F0h]
0x14001e2c1  test    edx, edx
0x14001e2c3  jz      short loc_14001E2D5
0x14001e2c5  or      r8d, 0FFFFFFFFh
0x14001e2c9  mov     ecx, r12d
0x14001e2cc  cmp     edx, 2
0x14001e2cf  cmovnz  ecx, r8d
0x14001e2d3  jmp     short loc_14001E2D7
0x14001e2d5  mov     ecx, ebp
0x14001e2d7  mov     eax, [rax+28h]
0x14001e2da  and     eax, r12d
0x14001e2dd  cmp     ecx, eax
0x14001e2df  jz      short loc_14001E2EA
0x14001e2e1  mov     edx, 8007h
0x14001e2e6  jmp     short loc_14001E292
0x14001e2e8  xor     ebp, ebp
0x14001e2ea  mov     eax, [rsi+0A8h]
0x14001e2f0  test    al, 2
0x14001e2f2  jz      short loc_14001E2FB
0x14001e2f4  mov     edx, 8000h
0x14001e2f9  jmp     short loc_14001E292
0x14001e2fb  mov     rax, [rsi+0B0h]
0x14001e302  cmp     [rsi+0B8h], rax
0x14001e309  jbe     short loc_14001E365
0x14001e30b  mov     edx, 8003h; unsigned __int16
0x14001e310  xor     r9d, r9d; struct CQueue *
0x14001e313  mov     r8, rbx; struct CPacketBuffer *
0x14001e316  mov     rcx, rdi; this
0x14001e319  call    ?Done@CPacket@@QEAAXGPEAVCPacketBuffer@@PEAVCQueue@@@Z; CPacket::Done(ushort,CPacketBuffer *,CQueue *)
0x14001e31e  mov     rax, [rsi+40h]
0x14001e322  lea     rcx, [rsi+58h]; struct QUEUE_FORMAT *
0x14001e326  lea     r9, [rsp+158h+arg_10]; unsigned int *
0x14001e32e  mov     [rsp+158h+var_108], 0Ch
0x14001e336  mov     r8d, 64h ; 'd'; unsigned int
0x14001e33c  mov     [rsp+158h+var_138], bpl; bool
0x14001e341  lea     rdx, [rsp+158h+var_FC]; wchar_t *
0x14001e346  mov     rbx, [rax+40h]
0x14001e34a  call    ?MQpQueueFormatToFormatName@@YAJPEBUQUEUE_FORMAT@@PEA_WKPEAK_N@Z; MQpQueueFormatToFormatName(QUEUE_FORMAT const *,wchar_t *,ulong,ulong *,bool)
0x14001e34f  lea     rcx, [rbx+48h]; this
0x14001e353  lea     rdx, [rsp+158h+var_118]; struct CACRequest *
0x14001e358  call    ?ProcessRequest@CQMInterface@@QEAAJAEBVCACRequest@@@Z; CQMInterface::ProcessRequest(CACRequest const &)
0x14001e35d  jmp     loc_14001E4A1
0x14001e362  mov     r12d, ebp
0x14001e365  bt      dword ptr [rdi+34h], 12h
0x14001e36a  jb      short loc_14001E380
0x14001e36c  mov     rax, [rdi+38h]
0x14001e370  cmp     rax, [rsi+158h]
0x14001e377  jnb     short loc_14001E380
0x14001e379  mov     [rsi+158h], rax
0x14001e380  movzx   r8d, word ptr [rdi+34h]
0x14001e385  mov     rcx, rsi; this
0x14001e388  mov     rdx, [rdi+38h]; unsigned __int64
0x14001e38c  shr     r8d, 0Bh
0x14001e390  and     r8d, 1; int
0x14001e394  call    ?UpdateFirstUnloggedLookupId@CQueue@@AEAAX_KH@Z; CQueue::UpdateFirstUnloggedLookupId(unsigned __int64,int)
0x14001e399  mov     rax, [rsi+160h]
0x14001e3a0  cmp     [rdi+38h], rax
0x14001e3a4  jnb     short loc_14001E417
0x14001e3a6  bt      dword ptr [rdi+34h], 12h
0x14001e3ab  jb      short loc_14001E417
0x14001e3ad  mov     rdx, rdi; struct CPacket *
0x14001e3b0  mov     rcx, rsi; this
0x14001e3b3  call    ?GetRequest@CQueueBase@@IEAAPEAU_IRP@@PEAVCPacket@@@Z; CQueueBase::GetRequest(CPacket *)
0x14001e3b8  mov     rbp, rax
0x14001e3bb  test    rax, rax
0x14001e3be  jz      short loc_14001E417
0x14001e3c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e3c7  lea     rax, WPP_GLOBAL_Control
0x14001e3ce  cmp     rcx, rax
0x14001e3d1  jz      short loc_14001E3F8
0x14001e3d3  mov     edx, [rcx+6Ch]
0x14001e3d6  test    dl, 4
0x14001e3d9  jz      short loc_14001E3F8
0x14001e3db  mov     rcx, [rcx+58h]
0x14001e3df  lea     r8, WPP_fa0c76334f1634ba991c664600eb5d12_Traceguids
0x14001e3e6  mov     edx, 0Dh
0x14001e3eb  mov     qword ptr [rsp+158h+var_138], rdi
0x14001e3f0  mov     r9, rbp
0x14001e3f3  call    WPP_SF_qq
0x14001e3f8  mov     ebx, [rbp+90h]
0x14001e3fe  mov     rdx, rbp; struct _IRP *
0x14001e401  mov     rcx, rdi; this
0x14001e404  call    ?CompleteRequest@CPacket@@QEAAJPEAU_IRP@@@Z; CPacket::CompleteRequest(_IRP *)
0x14001e409  test    bl, 20h
0x14001e40c  jz      short loc_14001E3A6
0x14001e40e  test    eax, eax
0x14001e410  js      short loc_14001E3A6
0x14001e412  jmp     loc_14001E4A1
0x14001e417  test    r12d, r12d
0x14001e41a  jz      loc_14001E4A1
0x14001e420  mov     rcx, rdi; this
0x14001e423  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001e428  mov     rbx, rax
0x14001e42b  test    rax, rax
0x14001e42e  jnz     short loc_14001E437
0x14001e430  mov     eax, 0C000009Ah
0x14001e435  jmp     short loc_14001E4A3
0x14001e437  test    byte ptr [rax+10h], 10h
0x14001e43b  jnz     short loc_14001E45D
0x14001e43d  mov     rax, [rsi]
0x14001e440  mov     rcx, rsi
0x14001e443  mov     rax, [rax+20h]
0x14001e447  call    _guard_dispatch_icall
0x14001e44c  mov     r8d, eax; int
0x14001e44f  xor     r9d, r9d; unsigned int
0x14001e452  mov     rdx, rbx; struct CPacketBuffer *
0x14001e455  mov     rcx, rdi; this
0x14001e458  call    ?StartTimer@CPacket@@QEAAXPEAVCPacketBuffer@@HK@Z; CPacket::StartTimer(CPacketBuffer *,int,ulong)
0x14001e45d  mov     eax, [rsi+0A8h]
0x14001e463  test    al, 4
0x14001e465  jnz     short loc_14001E473
0x14001e467  mov     eax, [rbx+60h]
0x14001e46a  shr     eax, 5
0x14001e46d  and     al, 3
0x14001e46f  cmp     al, 1
0x14001e471  jnz     short loc_14001E489
0x14001e473  test    dword ptr [rdi+34h], 800000h
0x14001e47a  jnz     short loc_14001E489
0x14001e47c  mov     rdx, r13; struct _IRP *
0x14001e47f  mov     rcx, rdi; this
0x14001e482  call    ?Store@CPacket@@QEAAJPEAU_IRP@@@Z; CPacket::Store(_IRP *)
0x14001e487  jmp     short loc_14001E4A3
0x14001e489  test    byte ptr [rbx+10h], 10h
0x14001e48d  jnz     short loc_14001E4A1
0x14001e48f  cmp     [rsp+158h+arg_20], 0
0x14001e497  jnz     short loc_14001E4A1
0x14001e499  mov     rcx, rdi; this
0x14001e49c  call    ?SendArrivalAcknowledgment@CPacket@@QEAAXXZ; CPacket::SendArrivalAcknowledgment(void)
0x14001e4a1  xor     eax, eax
0x14001e4a3  lea     r11, [rsp+158h+var_28]
0x14001e4ab  mov     rbx, [r11+30h]
0x14001e4af  mov     rbp, [r11+38h]
0x14001e4b3  mov     rsp, r11
0x14001e4b6  pop     r14
0x14001e4b8  pop     r13
0x14001e4ba  pop     r12
0x14001e4bc  pop     rdi
0x14001e4bd  pop     rsi
0x14001e4be  retn
```
