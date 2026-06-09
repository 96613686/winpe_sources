# CTransaction::Commit3(void)

- ea: `0x14001f8d4`
- end: `0x14001fa9c`
- name: `?Commit3@CTransaction@@QEAAJXZ`
- size: `456`
- prototype: `__int64 __fastcall(CTransaction *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1400092f8`

## callees

- `0x140001cb0`
- `0x140003d84`
- `0x14000a224`
- `0x14000a274`
- `0x1400126fc`
- `0x140012754`
- `0x14001569c`
- `0x140015ac4`
- `0x1400183c4`
- `0x1400195ac`
- `0x14001d15c`
- `0x14001e0c0`
- `0x14001f8d4`
- `0x14001faa4`
- `0x14001fb64`
- `0x140024bf0`

## pseudocode

```c
__int64 __fastcall CTransaction::Commit3(CTransaction *this)
{
  _QWORD *v2; // r14
  __int64 v3; // rdi
  struct CPacketBuffer *v4; // rbp
  __int64 v5; // rbx
  struct CSubQueueHeader *v6; // rax
  struct CSubQueueHeader *v7; // rsi
  CTransaction *v8; // rcx
  CQueue *v9; // rax
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  struct CQueue *SubqueueByName; // rax
  CTransaction *v13; // rcx

  CTransaction::CompletePendingReaders(this);
  v2 = (_QWORD *)((char *)this + 72);
  while ( 1 )
  {
    v3 = 0;
    if ( (_QWORD *)*v2 != v2 )
      v3 = *v2 - 72LL;
    if ( !v3 )
      return 0;
    v4 = CQEntry::Buffer((CQEntry *)v3);
    if ( !v4 )
      return 3221225626LL;
    XList<CPacket,72>::gethead(v2);
    v5 = *(_QWORD *)(v3 + 64);
    if ( (*(_DWORD *)(v3 + 52) & 0x4000000) != 0 )
    {
      v6 = CPacketBuffer::SubQueueHeaderSafe((struct CPacketBuffer *)((char *)v4 + 36));
      v7 = v6;
      if ( v6 && (*((_BYTE *)v6 + 4) & 1) != 0 )
      {
        CBaseObject::AddRef((CBaseObject *)v5);
        CTransaction::DeleteXactDummy(v8, (struct CPacket *)v3);
        v9 = (CQueue *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v5 + 32) + 104LL))(*(_QWORD *)(v5 + 32));
        if ( !v9 )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
          {
            v11 = 18;
LABEL_18:
            WPP_SF_q(v10->Queue.ListEntry.Blink, v11, WPP_2411d249fb60352b0c479e189fc20775_Traceguids, v5);
            goto LABEL_19;
          }
          goto LABEL_19;
        }
        SubqueueByName = CQueue::GetSubqueueByName(v9, (const wchar_t *)v7 + 10);
        if ( SubqueueByName )
        {
          CPacket::DoneMove((CPacket *)v5, v4, SubqueueByName);
          *((_DWORD *)v7 + 1) &= ~1u;
          goto LABEL_22;
        }
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
        {
          v11 = 19;
          goto LABEL_18;
        }
LABEL_19:
        CPacket::PacketRundown((CPacket *)v5, -1073741670);
      }
      else
      {
        CBaseObject::AddRef((CBaseObject *)v5);
        CTransaction::DeleteXactDummy(v13, (struct CPacket *)v3);
        *(_DWORD *)(v5 + 52) &= ~0x40000u;
        *(_WORD *)(v5 + 52) &= ~0x1000u;
        *(_DWORD *)(v5 + 52) |= 0x2000000u;
        CPacket::Done((CPacket *)v5, 0, v4, 0);
LABEL_22:
        CBaseObject::Release((CBaseObject *)v5);
      }
    }
    else
    {
      *(_QWORD *)(v3 + 40) = 0;
      CQEntry::TargetQueue((CQEntry *)v3, 0);
      CQueue::PutPacket((struct _DEVICE_OBJECT **)v5, 0, (struct CPacket *)v3, v4, 0);
      *(_DWORD *)(v3 + 52) &= ~0x40000u;
      CQueue::PutPacket((struct _DEVICE_OBJECT **)v5, 0, (struct CPacket *)v3, v4, 0);
    }
  }
}

```

## disassembly

```asm
0x14001f8d4  push    rbx
0x14001f8d6  push    rbp
0x14001f8d7  push    rsi
0x14001f8d8  push    rdi
0x14001f8d9  push    r14
0x14001f8db  sub     rsp, 30h
0x14001f8df  mov     r14, rcx
0x14001f8e2  call    ?CompletePendingReaders@CTransaction@@AEAAXXZ; CTransaction::CompletePendingReaders(void)
0x14001f8e7  add     r14, 48h ; 'H'
0x14001f8eb  mov     rcx, [r14]
0x14001f8ee  xor     edi, edi
0x14001f8f0  cmp     rcx, r14
0x14001f8f3  lea     rax, [rcx-48h]
0x14001f8f7  cmovnz  rdi, rax
0x14001f8fb  test    rdi, rdi
0x14001f8fe  jz      loc_14001FA8E
0x14001f904  mov     rcx, rdi; this
0x14001f907  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001f90c  mov     rbp, rax
0x14001f90f  test    rax, rax
0x14001f912  jz      loc_14001FA87
0x14001f918  mov     rcx, r14
0x14001f91b  call    ?gethead@?$XList@VCPacket@@$0EI@@@QEAAPEAVCPacket@@XZ; XList<CPacket,72>::gethead(void)
0x14001f920  test    dword ptr [rdi+34h], 4000000h
0x14001f927  mov     rbx, [rdi+40h]
0x14001f92b  jnz     short loc_14001F979
0x14001f92d  xor     edx, edx; struct CQueue *
0x14001f92f  mov     qword ptr [rdi+28h], 0
0x14001f937  mov     rcx, rdi; this
0x14001f93a  call    ?TargetQueue@CQEntry@@QEAAXPEAVCQueue@@@Z; CQEntry::TargetQueue(CQueue *)
0x14001f93f  mov     r9, rbp; struct CPacketBuffer *
0x14001f942  mov     [rsp+58h+var_38], 0; int
0x14001f94a  mov     r8, rdi; struct CPacket *
0x14001f94d  xor     edx, edx; struct _IRP *
0x14001f94f  mov     rcx, rbx; this
0x14001f952  call    ?PutPacket@CQueue@@QEAAJPEAU_IRP@@PEAVCPacket@@PEAVCPacketBuffer@@H@Z; CQueue::PutPacket(_IRP *,CPacket *,CPacketBuffer *,int)
0x14001f957  btr     dword ptr [rdi+34h], 12h
0x14001f95c  mov     r9, rbp; struct CPacketBuffer *
0x14001f95f  mov     r8, rdi; struct CPacket *
0x14001f962  mov     [rsp+58h+var_38], 0; int
0x14001f96a  xor     edx, edx; struct _IRP *
0x14001f96c  mov     rcx, rbx; this
0x14001f96f  call    ?PutPacket@CQueue@@QEAAJPEAU_IRP@@PEAVCPacket@@PEAVCPacketBuffer@@H@Z; CQueue::PutPacket(_IRP *,CPacket *,CPacketBuffer *,int)
0x14001f974  jmp     loc_14001F8EB
0x14001f979  lea     rcx, [rbp+24h]; struct CBaseHeader *
0x14001f97d  call    ?SubQueueHeaderSafe@CPacketBuffer@@SAPEAVCSubQueueHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::SubQueueHeaderSafe(CBaseHeader *)
0x14001f982  mov     rsi, rax
0x14001f985  test    rax, rax
0x14001f988  jz      loc_14001FA47
0x14001f98e  test    byte ptr [rax+4], 1
0x14001f992  jz      loc_14001FA47
0x14001f998  mov     rcx, rbx; this
0x14001f99b  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x14001f9a0  mov     rdx, rdi; struct CPacket *
0x14001f9a3  call    ?DeleteXactDummy@CTransaction@@AEAAJPEAVCPacket@@@Z; CTransaction::DeleteXactDummy(CPacket *)
0x14001f9a8  mov     rcx, [rbx+20h]
0x14001f9ac  mov     rax, [rcx]
0x14001f9af  mov     rax, [rax+68h]
0x14001f9b3  call    _guard_dispatch_icall
0x14001f9b8  test    rax, rax
0x14001f9bb  jnz     short loc_14001F9DE
0x14001f9bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f9c4  lea     rax, WPP_GLOBAL_Control
0x14001f9cb  cmp     rcx, rax
0x14001f9ce  jz      short loc_14001FA21
0x14001f9d0  mov     eax, [rcx+6Ch]
0x14001f9d3  test    al, 1
0x14001f9d5  jz      short loc_14001FA21
0x14001f9d7  mov     edx, 12h
0x14001f9dc  jmp     short loc_14001FA0E
0x14001f9de  lea     rdx, [rsi+14h]; wchar_t *
0x14001f9e2  mov     rcx, rax; this
0x14001f9e5  call    ?GetSubqueueByName@CQueue@@QEAAPEAV1@PEB_W@Z; CQueue::GetSubqueueByName(wchar_t const *)
0x14001f9ea  test    rax, rax
0x14001f9ed  jnz     short loc_14001FA33
0x14001f9ef  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f9f6  lea     rax, WPP_GLOBAL_Control
0x14001f9fd  cmp     rcx, rax
0x14001fa00  jz      short loc_14001FA21
0x14001fa02  mov     eax, [rcx+6Ch]
0x14001fa05  test    al, 1
0x14001fa07  jz      short loc_14001FA21
0x14001fa09  mov     edx, 13h
0x14001fa0e  mov     rcx, [rcx+58h]
0x14001fa12  lea     r8, WPP_2411d249fb60352b0c479e189fc20775_Traceguids
0x14001fa19  mov     r9, rbx
0x14001fa1c  call    WPP_SF_q
0x14001fa21  mov     edx, 0C000009Ah; int
0x14001fa26  mov     rcx, rbx; this
0x14001fa29  call    ?PacketRundown@CPacket@@QEAAXJ@Z; CPacket::PacketRundown(long)
0x14001fa2e  jmp     loc_14001F8EB
0x14001fa33  mov     r8, rax; struct CQueue *
0x14001fa36  mov     rdx, rbp; struct CPacketBuffer *
0x14001fa39  mov     rcx, rbx; this
0x14001fa3c  call    ?DoneMove@CPacket@@QEAAXPEAVCPacketBuffer@@PEAVCQueue@@@Z; CPacket::DoneMove(CPacketBuffer *,CQueue *)
0x14001fa41  and     dword ptr [rsi+4], 0FFFFFFFEh
0x14001fa45  jmp     short loc_14001FA7A
0x14001fa47  mov     rcx, rbx; this
0x14001fa4a  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x14001fa4f  mov     rdx, rdi; struct CPacket *
0x14001fa52  call    ?DeleteXactDummy@CTransaction@@AEAAJPEAVCPacket@@@Z; CTransaction::DeleteXactDummy(CPacket *)
0x14001fa57  btr     dword ptr [rbx+34h], 12h
0x14001fa5c  mov     eax, 0EFFFh
0x14001fa61  and     [rbx+34h], ax
0x14001fa65  xor     edx, edx; unsigned __int16
0x14001fa67  bts     dword ptr [rbx+34h], 19h
0x14001fa6c  xor     r9d, r9d; struct CQueue *
0x14001fa6f  mov     r8, rbp; struct CPacketBuffer *
0x14001fa72  mov     rcx, rbx; this
0x14001fa75  call    ?Done@CPacket@@QEAAXGPEAVCPacketBuffer@@PEAVCQueue@@@Z; CPacket::Done(ushort,CPacketBuffer *,CQueue *)
0x14001fa7a  mov     rcx, rbx; this
0x14001fa7d  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001fa82  jmp     loc_14001F8EB
0x14001fa87  mov     eax, 0C000009Ah
0x14001fa8c  jmp     short loc_14001FA90
0x14001fa8e  xor     eax, eax
0x14001fa90  add     rsp, 30h
0x14001fa94  pop     r14
0x14001fa96  pop     rdi
0x14001fa97  pop     rsi
0x14001fa98  pop     rbp
0x14001fa99  pop     rbx
0x14001fa9a  retn
```
