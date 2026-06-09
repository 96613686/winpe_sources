# CTransaction::Commit2(_IRP *)

- ea: `0x14001f714`
- end: `0x14001f8cd`
- name: `?Commit2@CTransaction@@QEAAJPEAU_IRP@@@Z`
- size: `441`
- prototype: `__int64 __fastcall(CTransaction *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140009258`

## callees

- `0x140001c04`
- `0x140001cb0`
- `0x14000a224`
- `0x140015654`
- `0x14001916c`
- `0x140019254`
- `0x140019454`
- `0x140019f04`
- `0x14001f714`
- `0x14001faa4`

## pseudocode

```c
int __fastcall CTransaction::Commit2(CTransaction *this, struct _IRP *a2)
{
  CTransaction *i; // r14
  CQEntry *v6; // rdi
  struct CPacketBuffer *v7; // rax
  struct CSubQueueHeader *v8; // rax
  CSubQueueHeader *v9; // r11
  _DWORD *v10; // r11
  int v11; // eax

  if ( !*((_DWORD *)this + 32) )
  {
    *((_DWORD *)this + 14) |= 2u;
    *((_DWORD *)this + 33) = 0;
    CTransaction::CompletePendingReaders(this);
    for ( i = (CTransaction *)*((_QWORD *)this + 9); ; i = *(CTransaction **)i )
    {
      v6 = 0;
      if ( (CTransaction *)((char *)this + 72) != i )
        v6 = (CTransaction *)((char *)i - 72);
      if ( !v6 )
      {
LABEL_22:
        if ( !*((_DWORD *)this + 32) )
          return *((_DWORD *)this + 33);
        a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry = 0;
        *((_OWORD *)&a2->Tail.CompletionKey + 1) = 0;
        *((_DWORD *)&a2->Tail.CompletionKey + 6) = *(_DWORD *)(&a2->Tail.CompletionKey + 3) & 0xFFFFFFF8 | 4;
        return CQueueBase::HoldRequest(
                 this,
                 a2,
                 0xFFFFFFFF,
                 (void (*)(struct _DEVICE_OBJECT *, struct _IRP *))ACCancelXactControl,
                 0);
      }
      if ( (*((_DWORD *)v6 + 13) & 0x4000000) != 0 )
      {
        v7 = CQEntry::Buffer(v6);
        if ( !v7 )
        {
          *((_DWORD *)this + 33) = -1073741670;
          goto LABEL_22;
        }
        v8 = CPacketBuffer::SubQueueHeaderSafe((struct CPacketBuffer *)((char *)v7 + 36));
        if ( v8 && (*((_BYTE *)v8 + 4) & 1) != 0 )
        {
          CSubQueueHeader::SetSubqueueName(v8, (const wchar_t *)v8 + 42);
          CSubQueueHeader::SetMovingToSubqueueName(v9, &qword_140027730);
          ++v10[3];
          v10[2] = 0;
          v10[4] = MEMORY[0xFFFFF78000000014] / 10000000 + 1240428288;
          *((_DWORD *)v6 + 13) &= 0xFE7FFFFF;
          v11 = CPacket::Store(v6, 0);
        }
        else
        {
          if ( (*((_DWORD *)v6 + 13) & 0x2000000) != 0 )
            continue;
          v11 = CPacket::DeleteStorage(v6);
        }
        if ( v11 < 0 )
        {
          *((_DWORD *)this + 33) = v11;
          goto LABEL_22;
        }
        ++*((_DWORD *)this + 32);
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 17, WPP_2411d249fb60352b0c479e189fc20775_Traceguids);
  }
  return -1073741811;
}

```

## disassembly

```asm
0x14001f714  push    rbx
0x14001f716  push    rsi
0x14001f717  push    rdi
0x14001f718  push    r14
0x14001f71a  push    r15
0x14001f71c  sub     rsp, 30h
0x14001f720  cmp     dword ptr [rcx+80h], 0
0x14001f727  mov     rsi, rdx
0x14001f72a  mov     rbx, rcx
0x14001f72d  jz      short loc_14001F768
0x14001f72f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f736  lea     rax, WPP_GLOBAL_Control
0x14001f73d  cmp     rcx, rax
0x14001f740  jz      short loc_14001F75E
0x14001f742  mov     eax, [rcx+6Ch]
0x14001f745  test    al, 1
0x14001f747  jz      short loc_14001F75E
0x14001f749  mov     rcx, [rcx+58h]
0x14001f74d  lea     r8, WPP_2411d249fb60352b0c479e189fc20775_Traceguids
0x14001f754  mov     edx, 11h
0x14001f759  call    WPP_SF_
0x14001f75e  mov     eax, 0C000000Dh
0x14001f763  jmp     loc_14001F8C0
0x14001f768  or      dword ptr [rcx+38h], 2
0x14001f76c  mov     dword ptr [rcx+84h], 0
0x14001f776  call    ?CompletePendingReaders@CTransaction@@AEAAXXZ; CTransaction::CompletePendingReaders(void)
0x14001f77b  lea     r15, [rbx+48h]
0x14001f77f  mov     r14, [r15]
0x14001f782  xor     edi, edi
0x14001f784  lea     rax, [r14-48h]
0x14001f788  cmp     r15, r14
0x14001f78b  cmovnz  rdi, rax
0x14001f78f  test    rdi, rdi
0x14001f792  jz      loc_14001F871
0x14001f798  test    dword ptr [rdi+34h], 4000000h
0x14001f79f  jz      loc_14001F857
0x14001f7a5  mov     rcx, rdi; this
0x14001f7a8  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001f7ad  test    rax, rax
0x14001f7b0  jz      loc_14001F867
0x14001f7b6  lea     rcx, [rax+24h]; struct CBaseHeader *
0x14001f7ba  call    ?SubQueueHeaderSafe@CPacketBuffer@@SAPEAVCSubQueueHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::SubQueueHeaderSafe(CBaseHeader *)
0x14001f7bf  mov     r11, rax
0x14001f7c2  test    rax, rax
0x14001f7c5  jz      short loc_14001F83C
0x14001f7c7  test    byte ptr [rax+4], 1
0x14001f7cb  jz      short loc_14001F83C
0x14001f7cd  lea     rdx, [rax+54h]; wchar_t *
0x14001f7d1  mov     rcx, rax; this
0x14001f7d4  call    ?SetSubqueueName@CSubQueueHeader@@QEAAXPEB_W@Z; CSubQueueHeader::SetSubqueueName(wchar_t const *)
0x14001f7d9  lea     rdx, qword_140027730; wchar_t *
0x14001f7e0  mov     rcx, r11; this
0x14001f7e3  call    ?SetMovingToSubqueueName@CSubQueueHeader@@QEAAXPEB_W@Z; CSubQueueHeader::SetMovingToSubqueueName(wchar_t const *)
0x14001f7e8  inc     dword ptr [r11+0Ch]
0x14001f7ec  mov     r8, 0FFFFF78000000014h
0x14001f7f6  mov     dword ptr [r11+8], 0
0x14001f7fe  mov     rax, 0D6BF94D5E57A42BDh
0x14001f808  mov     rcx, rdi; this
0x14001f80b  mov     r8, [r8]
0x14001f80e  imul    r8
0x14001f811  add     rdx, r8
0x14001f814  sar     rdx, 17h
0x14001f818  mov     rax, rdx
0x14001f81b  shr     rax, 3Fh
0x14001f81f  add     rdx, rax
0x14001f822  add     edx, 49EF6F00h
0x14001f828  mov     [r11+10h], edx
0x14001f82c  xor     edx, edx; struct _IRP *
0x14001f82e  and     dword ptr [rdi+34h], 0FE7FFFFFh
0x14001f835  call    ?Store@CPacket@@QEAAJPEAU_IRP@@@Z; CPacket::Store(_IRP *)
0x14001f83a  jmp     short loc_14001F84D
0x14001f83c  test    dword ptr [rdi+34h], 2000000h
0x14001f843  jnz     short loc_14001F857
0x14001f845  mov     rcx, rdi; this
0x14001f848  call    ?DeleteStorage@CPacket@@QEAAJXZ; CPacket::DeleteStorage(void)
0x14001f84d  test    eax, eax
0x14001f84f  js      short loc_14001F85F
0x14001f851  inc     dword ptr [rbx+80h]
0x14001f857  mov     r14, [r14]
0x14001f85a  jmp     loc_14001F782
0x14001f85f  mov     [rbx+84h], eax
0x14001f865  jmp     short loc_14001F871
0x14001f867  mov     dword ptr [rbx+84h], 0C000009Ah
0x14001f871  cmp     dword ptr [rbx+80h], 0
0x14001f878  jnz     short loc_14001F882
0x14001f87a  mov     eax, [rbx+84h]
0x14001f880  jmp     short loc_14001F8C0
0x14001f882  xorps   xmm0, xmm0
0x14001f885  mov     [rsp+58h+var_38], 0; int
0x14001f88d  movups  xmmword ptr [rsi+78h], xmm0
0x14001f891  lea     r9, ACCancelXactControl; void (*)(struct _DEVICE_OBJECT *, struct _IRP *)
0x14001f898  or      r8d, 0FFFFFFFFh; unsigned int
0x14001f89c  movups  xmmword ptr [rsi+88h], xmm0
0x14001f8a3  mov     eax, [rsi+90h]
0x14001f8a9  mov     rdx, rsi; struct _IRP *
0x14001f8ac  and     eax, 0FFFFFFFCh
0x14001f8af  mov     rcx, rbx; this
0x14001f8b2  or      eax, 4
0x14001f8b5  mov     [rsi+90h], eax
0x14001f8bb  call    ?HoldRequest@CQueueBase@@IEAAJPEAU_IRP@@KP6AXPEAU_DEVICE_OBJECT@@0@ZH@Z; CQueueBase::HoldRequest(_IRP *,ulong,void (*)(_DEVICE_OBJECT *,_IRP *),int)
0x14001f8c0  add     rsp, 30h
0x14001f8c4  pop     r15
0x14001f8c6  pop     r14
0x14001f8c8  pop     rdi
0x14001f8c9  pop     rsi
0x14001f8ca  pop     rbx
0x14001f8cb  retn
```
