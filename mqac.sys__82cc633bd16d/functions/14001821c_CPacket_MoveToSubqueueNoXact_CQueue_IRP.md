# CPacket::MoveToSubqueueNoXact(CQueue *,_IRP *)

- ea: `0x14001821c`
- end: `0x140018376`
- name: `?MoveToSubqueueNoXact@CPacket@@AEAAJPEAVCQueue@@PEAU_IRP@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(CPacket *__hidden this, struct CQueue *, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x14001d7c0`

## callees

- `0x140001c04`
- `0x140001cb0`
- `0x14000a224`
- `0x140012754`
- `0x140014850`
- `0x140014ba8`
- `0x140014c48`
- `0x14001821c`
- `0x1400183c4`
- `0x140019254`
- `0x14001e0c0`

## pseudocode

```c
__int64 __fastcall CPacket::MoveToSubqueueNoXact(CPacket *this, struct CQueue *a2, struct _IRP *a3)
{
  struct CPacketBuffer *v6; // rbp
  struct CSubQueueHeader *v7; // r14
  PDEVICE_OBJECT v8; // rcx
  __int64 v9; // rdx
  struct CPacket *v10; // rdi
  const wchar_t *v12; // rdx
  int v13; // eax
  unsigned int v14; // esi

  v6 = CQEntry::Buffer(this);
  v7 = CPacketBuffer::SubQueueHeaderSafe((struct CBaseHeader *)(((unsigned __int64)v6 + 36) & -(__int64)(v6 != 0)));
  if ( !v7 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return 3221225473LL;
    }
    v9 = 52;
LABEL_9:
    WPP_SF_(v8->Queue.ListEntry.Blink, v9, WPP_521cf5ef77973c292796e113f00b944d_Traceguids);
    return 3221225473LL;
  }
  v10 = CPacket::CloneSameForMove(this);
  if ( !v10 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) == 0 )
    {
      return 3221225473LL;
    }
    v9 = 53;
    goto LABEL_9;
  }
  if ( *((_BYTE *)a2 + 88) == 8 )
    v12 = (const wchar_t *)*((_QWORD *)a2 + 12);
  else
    v12 = 0;
  CSubQueueHeader::SetSubqueueName(v7, v12);
  ++*((_DWORD *)v7 + 3);
  *((_DWORD *)v7 + 2) = 0;
  *((_DWORD *)v7 + 4) = MEMORY[0xFFFFF78000000014] / 10000000 + 1240428288;
  CPacket::CancelTimeout(this);
  CPacket::CompleteWriter(this, 0);
  *((_DWORD *)this + 13) |= 0x60000u;
  v13 = CQueue::PutPacket((struct _DEVICE_OBJECT **)a2, a3, v10, v6, 1);
  v14 = v13;
  if ( v13 >= 0 )
  {
    *((_DWORD *)this + 13) |= 0x80000000;
    CBaseObject::Release(this);
  }
  else
  {
    CPacket::PacketRundown(v10, v13);
  }
  return v14;
}

```

## disassembly

```asm
0x14001821c  push    rbx
0x14001821e  push    rbp
0x14001821f  push    rsi
0x140018220  push    rdi
0x140018221  push    r14
0x140018223  push    r15
0x140018225  sub     rsp, 38h
0x140018229  mov     r15, r8
0x14001822c  mov     rsi, rdx
0x14001822f  mov     rbx, rcx
0x140018232  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x140018237  mov     r9, rax
0x14001823a  mov     rbp, rax
0x14001823d  neg     r9
0x140018240  sbb     rcx, rcx
0x140018243  lea     r10, [rax+24h]
0x140018247  and     rcx, r10; struct CBaseHeader *
0x14001824a  call    ?SubQueueHeaderSafe@CPacketBuffer@@SAPEAVCSubQueueHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::SubQueueHeaderSafe(CBaseHeader *)
0x14001824f  mov     r14, rax
0x140018252  test    rax, rax
0x140018255  jnz     short loc_140018277
0x140018257  mov     rcx, cs:WPP_GLOBAL_Control
0x14001825e  lea     rax, WPP_GLOBAL_Control
0x140018265  cmp     rcx, rax
0x140018268  jz      short loc_1400182B4
0x14001826a  mov     eax, [rcx+6Ch]
0x14001826d  test    al, 1
0x14001826f  jz      short loc_1400182B4
0x140018271  lea     edx, [r14+34h]
0x140018275  jmp     short loc_1400182A4
0x140018277  mov     rcx, rbx; this
0x14001827a  call    ?CloneSameForMove@CPacket@@AEAAPEAV1@XZ; CPacket::CloneSameForMove(void)
0x14001827f  mov     rdi, rax
0x140018282  test    rax, rax
0x140018285  jnz     short loc_1400182BE
0x140018287  mov     rcx, cs:WPP_GLOBAL_Control
0x14001828e  lea     rax, WPP_GLOBAL_Control
0x140018295  cmp     rcx, rax
0x140018298  jz      short loc_1400182B4
0x14001829a  mov     eax, [rcx+6Ch]
0x14001829d  test    al, 1
0x14001829f  jz      short loc_1400182B4
0x1400182a1  lea     edx, [rdi+35h]
0x1400182a4  mov     rcx, [rcx+58h]
0x1400182a8  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x1400182af  call    WPP_SF_
0x1400182b4  mov     eax, 0C0000001h
0x1400182b9  jmp     loc_140018368
0x1400182be  cmp     byte ptr [rsi+58h], 8
0x1400182c2  jnz     short loc_1400182CA
0x1400182c4  mov     rdx, [rsi+60h]
0x1400182c8  jmp     short loc_1400182CC
0x1400182ca  xor     edx, edx; wchar_t *
0x1400182cc  mov     rcx, r14; this
0x1400182cf  call    ?SetSubqueueName@CSubQueueHeader@@QEAAXPEB_W@Z; CSubQueueHeader::SetSubqueueName(wchar_t const *)
0x1400182d4  inc     dword ptr [r14+0Ch]
0x1400182d8  mov     rcx, 0FFFFF78000000014h
0x1400182e2  mov     dword ptr [r14+8], 0
0x1400182ea  mov     rax, 0D6BF94D5E57A42BDh
0x1400182f4  mov     rcx, [rcx]
0x1400182f7  imul    rcx
0x1400182fa  add     rdx, rcx
0x1400182fd  mov     rcx, rbx; this
0x140018300  sar     rdx, 17h
0x140018304  mov     rax, rdx
0x140018307  shr     rax, 3Fh
0x14001830b  add     rdx, rax
0x14001830e  add     edx, 49EF6F00h
0x140018314  mov     [r14+10h], edx
0x140018318  call    ?CancelTimeout@CPacket@@AEAAXXZ; CPacket::CancelTimeout(void)
0x14001831d  xor     edx, edx; int
0x14001831f  mov     rcx, rbx; this
0x140018322  call    ?CompleteWriter@CPacket@@QEAAXJ@Z; CPacket::CompleteWriter(long)
0x140018327  or      dword ptr [rbx+34h], 60000h
0x14001832e  mov     r9, rbp; struct CPacketBuffer *
0x140018331  mov     r8, rdi; struct CPacket *
0x140018334  mov     [rsp+68h+var_48], 1; int
0x14001833c  mov     rdx, r15; struct _IRP *
0x14001833f  mov     rcx, rsi; this
0x140018342  call    ?PutPacket@CQueue@@QEAAJPEAU_IRP@@PEAVCPacket@@PEAVCPacketBuffer@@H@Z; CQueue::PutPacket(_IRP *,CPacket *,CPacketBuffer *,int)
0x140018347  mov     esi, eax
0x140018349  test    eax, eax
0x14001834b  jns     short loc_140018359
0x14001834d  mov     edx, eax; int
0x14001834f  mov     rcx, rdi; this
0x140018352  call    ?PacketRundown@CPacket@@QEAAXJ@Z; CPacket::PacketRundown(long)
0x140018357  jmp     short loc_140018366
0x140018359  bts     dword ptr [rbx+34h], 1Fh
0x14001835e  mov     rcx, rbx; this
0x140018361  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140018366  mov     eax, esi
0x140018368  add     rsp, 38h
0x14001836c  pop     r15
0x14001836e  pop     r14
0x140018370  pop     rdi
0x140018371  pop     rsi
0x140018372  pop     rbp
0x140018373  pop     rbx
0x140018374  retn
```
