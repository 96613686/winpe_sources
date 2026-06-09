# CTransaction::Commit1(_IRP *)

- ea: `0x14001f56c`
- end: `0x14001f70c`
- name: `?Commit1@CTransaction@@QEAAJPEAU_IRP@@@Z`
- size: `416`
- prototype: `__int64 __fastcall(CTransaction *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1400091b8`

## callees

- `0x140001c04`
- `0x140001cb0`
- `0x140003d84`
- `0x1400140f4`
- `0x140019454`
- `0x140019f04`
- `0x14001c868`
- `0x14001e888`
- `0x14001f56c`
- `0x14001faa4`

## pseudocode

```c
int __fastcall CTransaction::Commit1(CTransaction *this, struct _IRP *a2)
{
  char *v5; // r12
  char *i; // r14
  char *v7; // rax
  CQEntry *v8; // rbp
  struct CPacketBuffer *v9; // rax
  struct CPacketBuffer *v10; // r13
  CQueue *v11; // rbx
  int v12; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 15, &WPP_2411d249fb60352b0c479e189fc20775_Traceguids, a2);
  }
  if ( *((_DWORD *)this + 32) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 16, &WPP_2411d249fb60352b0c479e189fc20775_Traceguids);
    }
    return -1073741811;
  }
  else
  {
    *((_DWORD *)this + 14) |= 2u;
    *((_DWORD *)this + 33) = 0;
    CTransaction::CompletePendingReaders(this);
    v5 = (char *)this + 72;
    for ( i = (char *)*((_QWORD *)this + 9); ; i = *(char **)i )
    {
      v7 = 0;
      v8 = (CQEntry *)(i - 72);
      if ( v5 != i )
        v7 = i - 72;
      if ( !v7 )
        break;
      if ( v5 == i )
        v8 = 0;
      if ( (*((_DWORD *)v8 + 13) & 0x4000000) == 0 )
      {
        v9 = CQEntry::Buffer(v8);
        v10 = v9;
        if ( !v9 )
        {
          *((_DWORD *)this + 33) = -1073741670;
          break;
        }
        *((_DWORD *)v9 + 4) &= ~0x40u;
        *(_QWORD *)((char *)v9 + 4) = ACpGetSequentialID(*((struct _DEVICE_OBJECT **)this + 8));
        v11 = (CQueue *)*((_QWORD *)v8 + 8);
        CQueue::AssignSequence(v11, v10);
        CQueue::SetPacketInformation(v11, (struct CPacketBuffer *)((char *)v10 + 4));
        *((_DWORD *)v8 + 13) &= 0xFE7FFFFF;
        v12 = CPacket::Store(v8, 0);
        if ( v12 < 0 )
        {
          *((_DWORD *)this + 33) = v12;
          break;
        }
        ++*((_DWORD *)this + 32);
      }
    }
    if ( *((_DWORD *)this + 32) )
    {
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
    else
    {
      return *((_DWORD *)this + 33);
    }
  }
}

```

## disassembly

```asm
0x14001f56c  push    rbx
0x14001f56e  push    rbp
0x14001f56f  push    rsi
0x14001f570  push    rdi
0x14001f571  push    r12
0x14001f573  push    r13
0x14001f575  push    r14
0x14001f577  push    r15
0x14001f579  sub     rsp, 38h
0x14001f57d  mov     r15, rdx
0x14001f580  mov     rsi, rcx
0x14001f583  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f58a  lea     rbx, WPP_GLOBAL_Control
0x14001f591  cmp     rcx, rbx
0x14001f594  jz      short loc_14001F5B5
0x14001f596  mov     eax, [rcx+6Ch]
0x14001f599  test    al, 4
0x14001f59b  jz      short loc_14001F5B5
0x14001f59d  mov     rcx, [rcx+58h]
0x14001f5a1  lea     r8, WPP_2411d249fb60352b0c479e189fc20775_Traceguids
0x14001f5a8  mov     edx, 0Fh
0x14001f5ad  mov     r9, r15
0x14001f5b0  call    WPP_SF_q
0x14001f5b5  cmp     dword ptr [rsi+80h], 0
0x14001f5bc  jz      short loc_14001F5F0
0x14001f5be  mov     rcx, cs:WPP_GLOBAL_Control
0x14001f5c5  cmp     rcx, rbx
0x14001f5c8  jz      short loc_14001F5E6
0x14001f5ca  mov     eax, [rcx+6Ch]
0x14001f5cd  test    al, 1
0x14001f5cf  jz      short loc_14001F5E6
0x14001f5d1  mov     rcx, [rcx+58h]
0x14001f5d5  lea     r8, WPP_2411d249fb60352b0c479e189fc20775_Traceguids
0x14001f5dc  mov     edx, 10h
0x14001f5e1  call    WPP_SF_
0x14001f5e6  mov     eax, 0C000000Dh
0x14001f5eb  jmp     loc_14001F6FA
0x14001f5f0  or      dword ptr [rsi+38h], 2
0x14001f5f4  mov     rcx, rsi; this
0x14001f5f7  mov     dword ptr [rsi+84h], 0
0x14001f601  call    ?CompletePendingReaders@CTransaction@@AEAAXXZ; CTransaction::CompletePendingReaders(void)
0x14001f606  lea     r12, [rsi+48h]
0x14001f60a  mov     r14, [r12]
0x14001f60e  xor     eax, eax
0x14001f610  lea     rbp, [r14-48h]
0x14001f614  cmp     r12, r14
0x14001f617  cmovnz  rax, rbp
0x14001f61b  test    rax, rax
0x14001f61e  jz      loc_14001F6A7
0x14001f624  xor     eax, eax
0x14001f626  cmp     r12, r14
0x14001f629  cmovz   rbp, rax
0x14001f62d  test    dword ptr [rbp+34h], 4000000h
0x14001f634  jnz     short loc_14001F68D
0x14001f636  mov     rcx, rbp; this
0x14001f639  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001f63e  mov     r13, rax
0x14001f641  test    rax, rax
0x14001f644  jz      short loc_14001F69D
0x14001f646  and     dword ptr [rax+10h], 0FFFFFFBFh
0x14001f64a  mov     rcx, [rsi+40h]; struct _DEVICE_OBJECT *
0x14001f64e  call    ?ACpGetSequentialID@@YA_KPEAU_DEVICE_OBJECT@@@Z; ACpGetSequentialID(_DEVICE_OBJECT *)
0x14001f653  mov     [r13+4], rax
0x14001f657  mov     rdx, r13; struct CPacketBuffer *
0x14001f65a  mov     rbx, [rbp+40h]
0x14001f65e  mov     rcx, rbx; this
0x14001f661  call    ?AssignSequence@CQueue@@QEAAXPEAVCPacketBuffer@@@Z; CQueue::AssignSequence(CPacketBuffer *)
0x14001f666  lea     rdx, [r13+4]; struct CPacketInfo *
0x14001f66a  mov     rcx, rbx; this
0x14001f66d  call    ?SetPacketInformation@CQueue@@QEAAXPEAVCPacketInfo@@@Z; CQueue::SetPacketInformation(CPacketInfo *)
0x14001f672  and     dword ptr [rbp+34h], 0FE7FFFFFh
0x14001f679  xor     edx, edx; struct _IRP *
0x14001f67b  mov     rcx, rbp; this
0x14001f67e  call    ?Store@CPacket@@QEAAJPEAU_IRP@@@Z; CPacket::Store(_IRP *)
0x14001f683  test    eax, eax
0x14001f685  js      short loc_14001F695
0x14001f687  inc     dword ptr [rsi+80h]
0x14001f68d  mov     r14, [r14]
0x14001f690  jmp     loc_14001F60E
0x14001f695  mov     [rsi+84h], eax
0x14001f69b  jmp     short loc_14001F6A7
0x14001f69d  mov     dword ptr [rsi+84h], 0C000009Ah
0x14001f6a7  cmp     dword ptr [rsi+80h], 0
0x14001f6ae  jnz     short loc_14001F6B8
0x14001f6b0  mov     eax, [rsi+84h]
0x14001f6b6  jmp     short loc_14001F6FA
0x14001f6b8  xorps   xmm0, xmm0
0x14001f6bb  mov     [rsp+78h+var_58], 0; int
0x14001f6c3  movups  xmmword ptr [r15+78h], xmm0
0x14001f6c8  lea     r9, ACCancelXactControl; void (*)(struct _DEVICE_OBJECT *, struct _IRP *)
0x14001f6cf  or      r8d, 0FFFFFFFFh; unsigned int
0x14001f6d3  movups  xmmword ptr [r15+88h], xmm0
0x14001f6db  mov     eax, [r15+90h]
0x14001f6e2  mov     rdx, r15; struct _IRP *
0x14001f6e5  and     eax, 0FFFFFFFCh
0x14001f6e8  mov     rcx, rsi; this
0x14001f6eb  or      eax, 4
0x14001f6ee  mov     [r15+90h], eax
0x14001f6f5  call    ?HoldRequest@CQueueBase@@IEAAJPEAU_IRP@@KP6AXPEAU_DEVICE_OBJECT@@0@ZH@Z; CQueueBase::HoldRequest(_IRP *,ulong,void (*)(_DEVICE_OBJECT *,_IRP *),int)
0x14001f6fa  add     rsp, 38h
0x14001f6fe  pop     r15
0x14001f700  pop     r14
0x14001f702  pop     r13
0x14001f704  pop     r12
0x14001f706  pop     rdi
0x14001f707  pop     rsi
0x14001f708  pop     rbp
0x14001f709  pop     rbx
0x14001f70a  retn
```
