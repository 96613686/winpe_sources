# CPacket::Done(ushort,CPacketBuffer *,CQueue *)

- ea: `0x14001569c`
- end: `0x140015abe`
- name: `?Done@CPacket@@QEAAXGPEAVCPacketBuffer@@PEAVCQueue@@@Z`
- size: `1058`
- prototype: `void __fastcall(CPacket *__hidden this, unsigned __int16, struct CPacketBuffer *, struct CQueue *)`
- caller_count: `10`
- callee_count: `25`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400060c0`
- `0x1400061fc`
- `0x140006334`
- `0x14000648c`
- `0x140017884`
- `0x140018644`
- `0x140018b9c`
- `0x14001dd80`
- `0x14001e0c0`
- `0x14001f8d4`

## callees

- `0x140003994`
- `0x140003d84`
- `0x140003f24`
- `0x140009a04`
- `0x140009b90`
- `0x140009bac`
- `0x14000a120`
- `0x14000a1d4`
- `0x14000a224`
- `0x14000baa0`
- `0x1400126fc`
- `0x140012754`
- `0x14001428c`
- `0x140014850`
- `0x140014c48`
- `0x1400155c8`
- `0x140015654`
- `0x14001569c`
- `0x140017d9c`
- `0x140017ec4`
- `0x140018dc8`
- `0x140018ff4`
- `0x14001b114`
- `0x14001edfc`
- `0x140024bf0`

## pseudocode

```c
void __fastcall CPacket::Done(CPacket *this, unsigned __int16 a2, struct CPacketBuffer *a3, struct CQueue *a4)
{
  unsigned int v5; // ebp
  int v6; // ecx
  _DWORD *v9; // r15
  struct CBaseHeader *v10; // r14
  struct CSubQueueHeader *v11; // rax
  struct CSubQueueHeader *v12; // rbx
  int v13; // edx
  int v14; // r11d
  __int64 v15; // rax
  struct COnDiskExtensionHeader *v16; // rax
  char *v17; // rbx
  char *NextSectionDataPtrSafe; // rcx
  unsigned int *v19; // rax
  struct COnDiskExtensionHeader *v20; // rax
  struct _DEVICE_OBJECT *v21; // rcx
  char *DeviceExtension; // rbx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // r8
  struct QueueCounters *v26; // rdx
  struct CDeviceExt *v27; // rcx
  __int64 v28; // rax
  char v29[16]; // [rsp+40h] [rbp-138h] BYREF
  int v30; // [rsp+50h] [rbp-128h]
  __int64 v31; // [rsp+58h] [rbp-120h]
  unsigned __int64 CPacketHandle; // [rsp+60h] [rbp-118h]
  int v33; // [rsp+68h] [rbp-110h]
  int v34; // [rsp+180h] [rbp+8h]

  v5 = a2;
  v6 = *((_DWORD *)this + 13);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_qqq(
        WPP_GLOBAL_Control->Queue.ListEntry.Blink,
        38,
        WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
        this,
        a3,
        a4);
    }
    return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      39,
      WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
      this,
      a3,
      a4);
    v6 = *((_DWORD *)this + 13);
  }
  if ( (v6 & 0x8000000) == 0 )
    CPacket::CacheCurrentState(this, a3);
  v9 = (_DWORD *)*((_QWORD *)this + 4);
  v10 = (struct CBaseHeader *)(((unsigned __int64)a3 + 36) & -(__int64)(a3 != 0));
  v11 = CPacketBuffer::SubQueueHeaderSafe(v10);
  v12 = v11;
  if ( v9 )
  {
    if ( (v9[42] & 0x20) == 0 )
    {
      if ( v11 )
      {
        v13 = *((_DWORD *)v11 + 1) >> 1;
        if ( (_WORD)v13 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
          {
            WPP_SF_DD(
              WPP_GLOBAL_Control->Queue.ListEntry.Blink,
              40,
              WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
              v5,
              (unsigned __int16)v13);
          }
          v5 = *((_DWORD *)v12 + 1) >> 1;
        }
      }
    }
  }
  if ( (v5 & 0x8000u) != 0 && CPacket::DeadLetterQueue(this, a3) && (*((_DWORD *)this + 13) & 0x20000000) != 0 )
  {
    v15 = (__int64)a3 + 16;
    if ( !a3 )
      v15 = 12;
    if ( (*(_BYTE *)v15 & 0x10) == 0 )
    {
      if ( v12 )
        *((_DWORD *)v12 + 2) = v14;
      if ( !a4 && (*(_WORD *)((((unsigned __int64)a3 + 36) & -(__int64)(a3 != 0)) + 2) & 0x1000) != 0 )
      {
        v16 = CPacketBuffer::OnDiskExtensionHeaderSafe((struct CBaseHeader *)(((unsigned __int64)a3 + 36)
                                                                            & -(__int64)(a3 != 0)));
        if ( v16 )
        {
          v34 = *((_DWORD *)v16 + 2);
          if ( (v34 & 1) != 0 )
          {
            v17 = (char *)v10 + *(unsigned int *)((((unsigned __int64)a3 + 36) & -(__int64)(a3 != 0)) + 8);
            NextSectionDataPtrSafe = GetNextSectionDataPtrSafe((unsigned __int64)v16, *(unsigned int *)v16, v17);
            if ( (v34 & 2) == 0 )
            {
LABEL_33:
              if ( NextSectionDataPtrSafe + 4 <= v17 && NextSectionDataPtrSafe + 4 >= NextSectionDataPtrSafe )
              {
                if ( NextSectionDataPtrSafe )
                {
                  if ( NextSectionDataPtrSafe != (char *)-4LL )
                  {
                    v20 = CPacketBuffer::OnDiskExtensionHeaderSafe((struct CBaseHeader *)(((unsigned __int64)a3 + 36)
                                                                                        & -(__int64)(a3 != 0)));
                    if ( v20 )
                    {
                      if ( (*((_BYTE *)v20 + 8) & 8) == 0 )
                      {
                        CQEntry::AddRefBuffer(this);
                        v21 = (struct _DEVICE_OBJECT *)*((_QWORD *)this + 13);
                        DeviceExtension = (char *)v21->DeviceExtension;
                        v31 = 0;
                        v30 = 13;
                        CPacketHandle = GenerateCPacketHandle(v21, this);
                        v33 = (unsigned __int16)v5;
                        CBaseObject::AddRef(this);
                        if ( (int)CQMInterface::ProcessRequest(
                                    (CQMInterface *)(DeviceExtension + 72),
                                    (const struct CACRequest *)v29) >= 0 )
                          return;
                        CBaseObject::Release(this);
                        CQEntry::ReleaseBuffer(this);
                      }
                    }
                  }
                }
              }
              goto LABEL_41;
            }
            v19 = (unsigned int *)drv_section_cast_safe<CSubQueueHeader *>(NextSectionDataPtrSafe, v17);
            if ( v19 )
            {
              NextSectionDataPtrSafe = GetNextSectionDataPtrSafe((unsigned __int64)v19, *v19, v17);
              goto LABEL_33;
            }
          }
        }
      }
    }
  }
LABEL_41:
  if ( (*((_DWORD *)this + 13) & 0x20000) == 0 )
    *((_WORD *)this + 26) = v5 | *((_WORD *)this + 26) & 0x1000;
  *((_DWORD *)this + 13) |= 0x20000u;
  if ( (int)CPacket::DeleteStorage(this) >= 0 )
  {
    CPacket::CancelTimeout(this);
    CPacket::CompleteWriter(this, 0);
    v23 = *((_DWORD *)this + 13);
    if ( (v23 & 0x40000) == 0 )
    {
      *((_DWORD *)this + 13) = v23 | 0x40000;
      if ( v9 && (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 104LL))(v9) )
      {
        v24 = (*(__int64 (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 104LL))(v9);
        v25 = *((unsigned int *)a3 + 11);
        v26 = *(struct QueueCounters **)(v24 + 232);
        v27 = *(struct CDeviceExt **)(*(_QWORD *)(v24 + 64) + 64LL);
        *(_QWORD *)(v24 + 184) -= v25;
        --*(_DWORD *)(v24 + 192);
        update_performance_counters(v27, v26, -(int)v25, -1);
      }
      if ( (v5 & 0x8000) != 0 )
      {
        v28 = (__int64)a3 + 16;
        if ( !a3 )
          v28 = 12;
        if ( (*(_BYTE *)v28 & 0x10) == 0 && !a4 )
          CPacket::SendAcknowledgment(this, v5);
        CPacket::Kill(this, v5, a4);
      }
      else if ( v9 )
      {
        CPacket::SendArrivalAcknowledgment(this);
        CPacket::SendAcknowledgment(this, 0x4000u);
        CPacket::Journalize(this);
      }
      *((_DWORD *)this + 13) |= 0x80000000;
      CBaseObject::Release(this);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 41, WPP_521cf5ef77973c292796e113f00b944d_Traceguids, this);
  }
}

```

## disassembly

```asm
0x14001569c  push    rbx
0x14001569e  push    rbp
0x14001569f  push    rsi
0x1400156a0  push    rdi
0x1400156a1  push    r12
0x1400156a3  push    r13
0x1400156a5  push    r14
0x1400156a7  push    r15
0x1400156a9  sub     rsp, 138h
0x1400156b0  mov     rdi, rcx
0x1400156b3  movzx   ebp, dx
0x1400156b6  mov     ecx, [rcx+34h]
0x1400156b9  mov     r13, r9
0x1400156bc  mov     rsi, r8
0x1400156bf  test    ecx, ecx
0x1400156c1  jns     short loc_14001570C
0x1400156c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400156ca  lea     r12, WPP_GLOBAL_Control
0x1400156d1  cmp     rcx, r12
0x1400156d4  jz      loc_140015AA9
0x1400156da  mov     eax, [rcx+6Ch]
0x1400156dd  test    al, 4
0x1400156df  jz      loc_140015AA9
0x1400156e5  mov     rcx, [rcx+58h]
0x1400156e9  mov     edx, 26h ; '&'
0x1400156ee  mov     [rsp+178h+var_150], r9
0x1400156f3  mov     r9, rdi
0x1400156f6  mov     [rsp+178h+var_158], r8
0x1400156fb  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x140015702  call    WPP_SF_qqq
0x140015707  jmp     loc_140015AA9
0x14001570c  mov     r10, cs:WPP_GLOBAL_Control
0x140015713  lea     r12, WPP_GLOBAL_Control
0x14001571a  cmp     r10, r12
0x14001571d  jz      short loc_14001574C
0x14001571f  mov     eax, [r10+6Ch]
0x140015723  test    al, 4
0x140015725  jz      short loc_14001574C
0x140015727  mov     rcx, [r10+58h]
0x14001572b  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x140015732  mov     edx, 27h ; '''
0x140015737  mov     [rsp+178h+var_150], r13
0x14001573c  mov     r9, rdi
0x14001573f  mov     [rsp+178h+var_158], rsi
0x140015744  call    WPP_SF_qqq
0x140015749  mov     ecx, [rdi+34h]
0x14001574c  bt      ecx, 1Bh
0x140015750  jb      short loc_14001575D
0x140015752  mov     rdx, rsi; struct CPacketBuffer *
0x140015755  mov     rcx, rdi; this
0x140015758  call    ?CacheCurrentState@CPacket@@QEAAXPEAVCPacketBuffer@@@Z; CPacket::CacheCurrentState(CPacketBuffer *)
0x14001575d  mov     r15, [rdi+20h]
0x140015761  lea     rcx, [rsi+24h]
0x140015765  mov     rax, rsi
0x140015768  neg     rax
0x14001576b  sbb     r14, r14
0x14001576e  and     r14, rcx
0x140015771  mov     rcx, r14; struct CBaseHeader *
0x140015774  call    ?SubQueueHeaderSafe@CPacketBuffer@@SAPEAVCSubQueueHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::SubQueueHeaderSafe(CBaseHeader *)
0x140015779  xor     r11d, r11d
0x14001577c  mov     rbx, rax
0x14001577f  test    r15, r15
0x140015782  jz      short loc_1400157D8
0x140015784  mov     ecx, [r15+0A8h]
0x14001578b  test    cl, 20h
0x14001578e  jnz     short loc_1400157D8
0x140015790  test    rax, rax
0x140015793  jz      short loc_1400157D8
0x140015795  mov     edx, [rax+4]
0x140015798  shr     edx, 1
0x14001579a  test    dx, dx
0x14001579d  jz      short loc_1400157D8
0x14001579f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400157a6  cmp     rcx, r12
0x1400157a9  jz      short loc_1400157D3
0x1400157ab  mov     eax, [rcx+6Ch]
0x1400157ae  test    al, 4
0x1400157b0  jz      short loc_1400157D3
0x1400157b2  mov     rcx, [rcx+58h]
0x1400157b6  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x1400157bd  movzx   eax, dx
0x1400157c0  mov     r9d, ebp
0x1400157c3  lea     edx, [r11+28h]
0x1400157c7  mov     dword ptr [rsp+178h+var_158], eax
0x1400157cb  call    WPP_SF_DD
0x1400157d0  xor     r11d, r11d
0x1400157d3  mov     ebp, [rbx+4]
0x1400157d6  shr     ebp, 1
0x1400157d8  mov     ecx, 8000h
0x1400157dd  movzx   eax, bp
0x1400157e0  and     ax, cx
0x1400157e3  mov     edx, 1000h
0x1400157e8  mov     [rsp+178h+var_148], ax
0x1400157ed  jz      loc_140015959
0x1400157f3  mov     rdx, rsi; struct CPacketBuffer *
0x1400157f6  mov     rcx, rdi; this
0x1400157f9  call    ?DeadLetterQueue@CPacket@@QEBAPEAVCQueue@@PEAVCPacketBuffer@@@Z; CPacket::DeadLetterQueue(CPacketBuffer *)
0x1400157fe  test    rax, rax
0x140015801  jz      loc_14001595D
0x140015807  test    dword ptr [rdi+34h], 20000000h
0x14001580e  jz      loc_14001595D
0x140015814  test    rsi, rsi
0x140015817  lea     rax, [rsi+10h]
0x14001581b  mov     ecx, 0Ch
0x140015820  cmovz   rax, rcx
0x140015824  test    byte ptr [rax], 10h
0x140015827  jnz     loc_14001595D
0x14001582d  test    rbx, rbx
0x140015830  jz      short loc_140015836
0x140015832  mov     [rbx+8], r11d
0x140015836  xor     ebx, ebx
0x140015838  mov     edx, 1000h
0x14001583d  test    r13, r13
0x140015840  jnz     loc_140015964
0x140015846  test    [r14+2], dx
0x14001584b  jz      loc_140015964
0x140015851  mov     rcx, r14; struct CBaseHeader *
0x140015854  call    ?OnDiskExtensionHeaderSafe@CPacketBuffer@@SAPEAVCOnDiskExtensionHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::OnDiskExtensionHeaderSafe(CBaseHeader *)
0x140015859  test    rax, rax
0x14001585c  jz      loc_14001595F
0x140015862  mov     ecx, [rax+8]
0x140015865  mov     [rsp+178h+arg_0], ecx
0x14001586c  test    cl, 1
0x14001586f  jz      loc_14001595F
0x140015875  mov     ebx, [r14+8]
0x140015879  mov     rcx, rax; unsigned __int64
0x14001587c  mov     edx, [rax]; unsigned __int64
0x14001587e  add     rbx, r14
0x140015881  mov     r8, rbx; char *
0x140015884  call    ?GetNextSectionDataPtrSafe@@YAPEAD_K0PEAD@Z; GetNextSectionDataPtrSafe(unsigned __int64,unsigned __int64,char *)
0x140015889  test    byte ptr [rsp+178h+arg_0], 2
0x140015891  mov     rcx, rax
0x140015894  jz      short loc_1400158B7
0x140015896  mov     rdx, rbx
0x140015899  call    ??$drv_section_cast_safe@PEAVCSubQueueHeader@@@@YAPEAVCSubQueueHeader@@PEAXPEAD@Z; drv_section_cast_safe<CSubQueueHeader *>(void *,char *)
0x14001589e  test    rax, rax
0x1400158a1  jz      loc_14001595D
0x1400158a7  mov     edx, [rax]; unsigned __int64
0x1400158a9  mov     r8, rbx; char *
0x1400158ac  mov     rcx, rax; unsigned __int64
0x1400158af  call    ?GetNextSectionDataPtrSafe@@YAPEAD_K0PEAD@Z; GetNextSectionDataPtrSafe(unsigned __int64,unsigned __int64,char *)
0x1400158b4  mov     rcx, rax
0x1400158b7  lea     rax, [rcx+4]
0x1400158bb  cmp     rax, rbx
0x1400158be  ja      loc_14001595D
0x1400158c4  xor     ebx, ebx
0x1400158c6  cmp     rax, rcx
0x1400158c9  jb      loc_14001595F
0x1400158cf  test    rcx, rcx
0x1400158d2  jz      loc_14001595F
0x1400158d8  lea     rax, [rcx+4]
0x1400158dc  test    rax, rax
0x1400158df  jz      short loc_14001595F
0x1400158e1  mov     rcx, r14; struct CBaseHeader *
0x1400158e4  call    ?OnDiskExtensionHeaderSafe@CPacketBuffer@@SAPEAVCOnDiskExtensionHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::OnDiskExtensionHeaderSafe(CBaseHeader *)
0x1400158e9  test    rax, rax
0x1400158ec  jz      short loc_14001595F
0x1400158ee  test    byte ptr [rax+8], 8
0x1400158f2  jnz     short loc_14001595F
0x1400158f4  mov     rcx, rdi; this
0x1400158f7  call    ?AddRefBuffer@CQEntry@@QEBAXXZ; CQEntry::AddRefBuffer(void)
0x1400158fc  mov     rcx, [rdi+68h]; struct _DEVICE_OBJECT *
0x140015900  xor     edx, edx
0x140015902  mov     rbx, [rcx+40h]
0x140015906  mov     [rsp+178h+var_120], rdx
0x14001590b  mov     rdx, rdi; struct CPacket *
0x14001590e  mov     [rsp+178h+var_128], 0Dh
0x140015916  call    ?GenerateCPacketHandle@@YA_KPEAU_DEVICE_OBJECT@@PEAVCPacket@@@Z; GenerateCPacketHandle(_DEVICE_OBJECT *,CPacket *)
0x14001591b  mov     [rsp+178h+var_118], rax
0x140015920  mov     rcx, rdi; this
0x140015923  movzx   eax, bp
0x140015926  mov     [rsp+178h+var_110], eax
0x14001592a  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x14001592f  lea     rcx, [rbx+48h]; this
0x140015933  lea     rdx, [rsp+178h+var_138]; struct CACRequest *
0x140015938  call    ?ProcessRequest@CQMInterface@@QEAAJAEBVCACRequest@@@Z; CQMInterface::ProcessRequest(CACRequest const &)
0x14001593d  xor     ebx, ebx
0x14001593f  test    eax, eax
0x140015941  jns     loc_140015AA9
0x140015947  mov     rcx, rdi; this
0x14001594a  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001594f  mov     rcx, rdi; this
0x140015952  call    ?ReleaseBuffer@CQEntry@@QEBAXXZ; CQEntry::ReleaseBuffer(void)
0x140015957  jmp     short loc_14001595F
0x140015959  xor     ebx, ebx
0x14001595b  jmp     short loc_140015964
0x14001595d  xor     ebx, ebx
0x14001595f  mov     edx, 1000h
0x140015964  mov     ecx, 20000h
0x140015969  test    [rdi+34h], ecx
0x14001596c  jnz     short loc_14001597C
0x14001596e  movzx   eax, word ptr [rdi+34h]
0x140015972  and     ax, dx
0x140015975  or      ax, bp
0x140015978  mov     [rdi+34h], ax
0x14001597c  or      [rdi+34h], ecx
0x14001597f  mov     rcx, rdi; this
0x140015982  call    ?DeleteStorage@CPacket@@QEAAJXZ; CPacket::DeleteStorage(void)
0x140015987  test    eax, eax
0x140015989  jns     short loc_1400159C3
0x14001598b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015992  cmp     rcx, r12
0x140015995  jz      loc_140015AA9
0x14001599b  mov     eax, [rcx+6Ch]
0x14001599e  test    al, 1
0x1400159a0  jz      loc_140015AA9
0x1400159a6  mov     rcx, [rcx+58h]
0x1400159aa  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x1400159b1  mov     edx, 29h ; ')'
0x1400159b6  mov     r9, rdi
0x1400159b9  call    WPP_SF_q
0x1400159be  jmp     loc_140015AA9
0x1400159c3  mov     rcx, rdi; this
0x1400159c6  call    ?CancelTimeout@CPacket@@AEAAXXZ; CPacket::CancelTimeout(void)
0x1400159cb  xor     edx, edx; int
0x1400159cd  mov     rcx, rdi; this
0x1400159d0  call    ?CompleteWriter@CPacket@@QEAAXJ@Z; CPacket::CompleteWriter(long)
0x1400159d5  mov     eax, [rdi+34h]
0x1400159d8  mov     ecx, 40000h
0x1400159dd  test    ecx, eax
0x1400159df  jnz     loc_140015AA9
0x1400159e5  or      eax, ecx
0x1400159e7  mov     [rdi+34h], eax
0x1400159ea  test    r15, r15
0x1400159ed  jz      short loc_140015A3E
0x1400159ef  mov     rax, [r15]
0x1400159f2  mov     rcx, r15
0x1400159f5  mov     rax, [rax+68h]
0x1400159f9  call    _guard_dispatch_icall
0x1400159fe  test    rax, rax
0x140015a01  jz      short loc_140015A3E
0x140015a03  mov     rax, [r15]
0x140015a06  mov     rcx, r15
0x140015a09  mov     rax, [rax+68h]
0x140015a0d  call    _guard_dispatch_icall
0x140015a12  mov     r8d, [rsi+2Ch]
0x140015a16  or      r9d, 0FFFFFFFFh; int
0x140015a1a  mov     rcx, [rax+40h]
0x140015a1e  mov     rdx, [rax+0E8h]; struct QueueCounters *
0x140015a25  mov     rcx, [rcx+40h]; struct CDeviceExt *
0x140015a29  sub     [rax+0B8h], r8
0x140015a30  neg     r8d; int
0x140015a33  dec     dword ptr [rax+0C0h]
0x140015a39  call    ?update_performance_counters@@YAXPEAUCDeviceExt@@PEAUQueueCounters@@JJ@Z; update_performance_counters(CDeviceExt *,QueueCounters *,long,long)
0x140015a3e  cmp     [rsp+178h+var_148], bx
0x140015a43  jz      short loc_140015A7A
0x140015a45  test    rsi, rsi
0x140015a48  lea     rax, [rsi+10h]
0x140015a4c  mov     ecx, 0Ch
0x140015a51  cmovz   rax, rcx
0x140015a55  test    byte ptr [rax], 10h
0x140015a58  jnz     short loc_140015A6A
0x140015a5a  test    r13, r13
0x140015a5d  jnz     short loc_140015A6A
0x140015a5f  movzx   edx, bp; unsigned __int16
0x140015a62  mov     rcx, rdi; this
0x140015a65  call    ?SendAcknowledgment@CPacket@@AEAAXG@Z; CPacket::SendAcknowledgment(ushort)
0x140015a6a  mov     r8, r13; struct CQueue *
0x140015a6d  movzx   edx, bp; unsigned __int16
0x140015a70  mov     rcx, rdi; this
0x140015a73  call    ?Kill@CPacket@@AEAAXGPEAVCQueue@@@Z; CPacket::Kill(ushort,CQueue *)
0x140015a78  jmp     short loc_140015A9C
0x140015a7a  test    r15, r15
0x140015a7d  jz      short loc_140015A9C
0x140015a7f  mov     rcx, rdi; this
0x140015a82  call    ?SendArrivalAcknowledgment@CPacket@@QEAAXXZ; CPacket::SendArrivalAcknowledgment(void)
0x140015a87  mov     edx, 4000h; unsigned __int16
0x140015a8c  mov     rcx, rdi; this
0x140015a8f  call    ?SendAcknowledgment@CPacket@@AEAAXG@Z; CPacket::SendAcknowledgment(ushort)
0x140015a94  mov     rcx, rdi; this
0x140015a97  call    ?Journalize@CPacket@@AEAAXXZ; CPacket::Journalize(void)
0x140015a9c  bts     dword ptr [rdi+34h], 1Fh
0x140015aa1  mov     rcx, rdi; this
0x140015aa4  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140015aa9  add     rsp, 138h
0x140015ab0  pop     r15
0x140015ab2  pop     r14
0x140015ab4  pop     r13
0x140015ab6  pop     r12
0x140015ab8  pop     rdi
0x140015ab9  pop     rsi
0x140015aba  pop     rbp
0x140015abb  pop     rbx
0x140015abc  retn
```
