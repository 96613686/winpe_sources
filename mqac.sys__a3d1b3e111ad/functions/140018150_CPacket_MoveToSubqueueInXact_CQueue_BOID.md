# CPacket::MoveToSubqueueInXact(CQueue *,BOID *)

- ea: `0x140018150`
- end: `0x140018214`
- name: `?MoveToSubqueueInXact@CPacket@@AEAAJPEAVCQueue@@PEAUBOID@@@Z`
- size: `196`
- prototype: `__int64 __fastcall(CPacket *__hidden this, struct CQueue *, struct BOID *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14001d7c0`

## callees

- `0x140001c04`
- `0x140001cb0`
- `0x14000a224`
- `0x1400126fc`
- `0x140018150`
- `0x14001916c`
- `0x14001fb20`
- `0x14001fbb4`

## pseudocode

```c
__int64 __fastcall CPacket::MoveToSubqueueInXact(struct _DEVICE_OBJECT **this, struct CQueue *a2, struct BOID *a3)
{
  CTransaction *v5; // rbp
  const wchar_t *v7; // rbx
  struct CPacketBuffer *v8; // rax
  int XactDummy; // ebx
  CSubQueueHeader *v10; // rax
  __int64 v11; // r11

  v5 = CTransaction::Find(this[13], a3);
  if ( v5 )
  {
    if ( *((_BYTE *)a2 + 88) == 8 )
      v7 = (const wchar_t *)*((_QWORD *)a2 + 12);
    else
      v7 = &qword_140027730;
    v8 = CQEntry::Buffer((CQEntry *)this);
    if ( v8 && (v10 = CPacketBuffer::SubQueueHeaderSafe((struct CPacketBuffer *)((char *)v8 + 36))) != 0 )
    {
      CSubQueueHeader::SetMovingToSubqueueName(v10, v7);
      *(_DWORD *)(v11 + 4) |= 1u;
      XactDummy = CTransaction::CreateXactDummy(v5, (struct CPacket *)this);
      if ( XactDummy >= 0 )
        CBaseObject::AddRef(a2);
    }
    else
    {
      return (unsigned int)-1073741823;
    }
    return (unsigned int)XactDummy;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 51, WPP_521cf5ef77973c292796e113f00b944d_Traceguids);
    }
    return 3222143057LL;
  }
}

```

## disassembly

```asm
0x140018150  push    rbx
0x140018152  push    rbp
0x140018153  push    rsi
0x140018154  push    rdi
0x140018155  sub     rsp, 28h
0x140018159  mov     rdi, rdx
0x14001815c  mov     rsi, rcx
0x14001815f  mov     rcx, [rcx+68h]; struct _DEVICE_OBJECT *
0x140018163  mov     rdx, r8; struct BOID *
0x140018166  call    ?Find@CTransaction@@SAPEAV1@PEAU_DEVICE_OBJECT@@PEBUBOID@@@Z; CTransaction::Find(_DEVICE_OBJECT *,BOID const *)
0x14001816b  mov     rbp, rax
0x14001816e  test    rax, rax
0x140018171  jnz     short loc_1400181A7
0x140018173  mov     rcx, cs:WPP_GLOBAL_Control
0x14001817a  lea     rax, WPP_GLOBAL_Control
0x140018181  cmp     rcx, rax
0x140018184  jz      short loc_1400181A0
0x140018186  mov     eax, [rcx+6Ch]
0x140018189  test    al, 1
0x14001818b  jz      short loc_1400181A0
0x14001818d  mov     rcx, [rcx+58h]
0x140018191  lea     edx, [rbp+33h]
0x140018194  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x14001819b  call    WPP_SF_
0x1400181a0  mov     eax, 0C00E0051h
0x1400181a5  jmp     short loc_14001820A
0x1400181a7  cmp     byte ptr [rdi+58h], 8
0x1400181ab  jnz     short loc_1400181B3
0x1400181ad  mov     rbx, [rdi+60h]
0x1400181b1  jmp     short loc_1400181BA
0x1400181b3  lea     rbx, qword_140027730
0x1400181ba  mov     rcx, rsi; this
0x1400181bd  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x1400181c2  test    rax, rax
0x1400181c5  jnz     short loc_1400181CE
0x1400181c7  mov     ebx, 0C0000001h
0x1400181cc  jmp     short loc_140018208
0x1400181ce  lea     rcx, [rax+24h]; struct CBaseHeader *
0x1400181d2  call    ?SubQueueHeaderSafe@CPacketBuffer@@SAPEAVCSubQueueHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::SubQueueHeaderSafe(CBaseHeader *)
0x1400181d7  mov     r11, rax
0x1400181da  test    rax, rax
0x1400181dd  jz      short loc_1400181C7
0x1400181df  mov     rdx, rbx; wchar_t *
0x1400181e2  mov     rcx, rax; this
0x1400181e5  call    ?SetMovingToSubqueueName@CSubQueueHeader@@QEAAXPEB_W@Z; CSubQueueHeader::SetMovingToSubqueueName(wchar_t const *)
0x1400181ea  or      dword ptr [r11+4], 1
0x1400181ef  mov     rdx, rsi; struct CPacket *
0x1400181f2  mov     rcx, rbp; this
0x1400181f5  call    ?CreateXactDummy@CTransaction@@AEAAJPEAVCPacket@@@Z; CTransaction::CreateXactDummy(CPacket *)
0x1400181fa  mov     ebx, eax
0x1400181fc  test    eax, eax
0x1400181fe  js      short loc_140018208
0x140018200  mov     rcx, rdi; this
0x140018203  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x140018208  mov     eax, ebx
0x14001820a  add     rsp, 28h
0x14001820e  pop     rdi
0x14001820f  pop     rsi
0x140018210  pop     rbp
0x140018211  pop     rbx
0x140018212  retn
```
