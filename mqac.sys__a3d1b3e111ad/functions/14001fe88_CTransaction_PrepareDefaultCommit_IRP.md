# CTransaction::PrepareDefaultCommit(_IRP *)

- ea: `0x14001fe88`
- end: `0x1400201b0`
- name: `?PrepareDefaultCommit@CTransaction@@QEAAJPEAU_IRP@@@Z`
- size: `808`
- prototype: `__int64 __fastcall(CTransaction *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140009540`

## callees

- `0x140001c04`
- `0x140001cb0`
- `0x1400140f4`
- `0x140019454`
- `0x140019730`
- `0x140019f04`
- `0x14001c868`
- `0x14001e888`
- `0x14001faa4`
- `0x14001fc14`
- `0x14001fe88`

## pseudocode

```c
int __fastcall CTransaction::PrepareDefaultCommit(struct _DEVICE_OBJECT **this, struct _IRP *a2)
{
  int result; // eax
  struct _DEVICE_OBJECT *v5; // r14
  struct _DEVICE_OBJECT *v6; // r15
  ULONG *p_ActiveThreadCount; // rsi
  ULONG *v8; // rax
  struct CPacketBuffer *v9; // rax
  struct CPacketBuffer *v10; // rbp
  unsigned int v11; // ecx
  CQueue *v12; // r12
  struct CXactHeader *v13; // rax
  int v14; // edx
  struct _DEVICE_OBJECT *v15; // rbx
  CQEntry *v16; // rsi
  ULONG *v17; // rax
  __int64 v18; // rbp
  struct CPacketBuffer *v19; // rax
  struct CBaseHeader *v20; // rcx
  struct CXactHeader *v21; // rax
  int v22; // eax
  ULONG *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // [rsp+30h] [rbp-48h]
  unsigned int v27; // [rsp+90h] [rbp+18h] BYREF
  unsigned int v28; // [rsp+98h] [rbp+20h] BYREF

  v27 = 0;
  v28 = 0;
  result = CTransaction::GetPacketTimeouts((CTransaction *)this, &v27, &v28);
  if ( result >= 0 )
  {
    if ( *((_DWORD *)this + 32) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 13, WPP_2411d249fb60352b0c479e189fc20775_Traceguids);
      }
      return -1073741811;
    }
    else
    {
      *((_DWORD *)this + 14) |= 2u;
      *((_DWORD *)this + 33) = 0;
      CTransaction::CompletePendingReaders((CTransaction *)this);
      v5 = (struct _DEVICE_OBJECT *)(this + 9);
      v6 = this[9];
      v26 = *((_DWORD *)this[8]->DeviceExtension + 84);
      while ( 1 )
      {
        p_ActiveThreadCount = &v6[-1].ActiveThreadCount;
        v8 = 0;
        if ( v5 != v6 )
          v8 = &v6[-1].ActiveThreadCount;
        if ( !v8 )
          break;
        if ( v5 == v6 )
          p_ActiveThreadCount = 0;
        v9 = CQEntry::Buffer((CQEntry *)p_ActiveThreadCount);
        v10 = v9;
        if ( !v9 )
        {
          *((_DWORD *)this + 33) = -1073741670;
          break;
        }
        v11 = *((_DWORD *)v9 + 4) & 0xFFFFFF7F;
        *(_OWORD *)((char *)v9 + 20) = *((_OWORD *)this + 7);
        *((_DWORD *)v9 + 4) = v11 | ~(unsigned __int8)(p_ActiveThreadCount[13] >> 19) & 0x80;
        if ( (p_ActiveThreadCount[13] & 0x4000000) == 0 )
        {
          *(_QWORD *)((char *)v9 + 4) = ACpGetSequentialID(this[8]);
          v12 = (CQueue *)*((_QWORD *)p_ActiveThreadCount + 8);
          CQueue::AssignSequence(v12, v10);
          CQueue::SetPacketInformation(v12, (struct CPacketBuffer *)((char *)v10 + 4));
          v13 = CPacketBuffer::XactHeaderSafe((struct CPacketBuffer *)((char *)v10 + 36));
          if ( !v13 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 14, WPP_2411d249fb60352b0c479e189fc20775_Traceguids);
            }
            return -2147483643;
          }
          *((_DWORD *)v10 + 12) = v27;
          *((_DWORD *)v10 + 21) = v28;
          v14 = *(_DWORD *)v13 ^ (*(_DWORD *)v13 ^ (16 * v26)) & 0xFFFFF0;
          *(_DWORD *)v13 = v14;
          if ( !*((_QWORD *)v12 + 42) )
            *(_DWORD *)v13 = v14 | 4;
          *((_QWORD *)v12 + 42) = p_ActiveThreadCount;
        }
        v6 = *(struct _DEVICE_OBJECT **)&v6->Type;
      }
      v15 = *(struct _DEVICE_OBJECT **)&v5->Type;
      if ( !*((_DWORD *)this + 33) )
      {
        while ( 1 )
        {
          v16 = (CQEntry *)&v15[-1].ActiveThreadCount;
          v17 = 0;
          if ( v5 != v15 )
            v17 = &v15[-1].ActiveThreadCount;
          if ( !v17 )
            break;
          if ( v5 == v15 )
            v16 = 0;
          if ( (*((_DWORD *)v16 + 13) & 0x4000000) == 0 )
          {
            v18 = *((_QWORD *)v16 + 8);
            if ( v16 == *(CQEntry **)(v18 + 336) )
            {
              v19 = CQEntry::Buffer(v16);
              v20 = (struct CBaseHeader *)(((unsigned __int64)v19 + 36) & -(__int64)(v19 != 0));
              if ( !v20 || (v21 = CPacketBuffer::XactHeaderSafe(v20)) == 0 )
              {
                *((_DWORD *)this + 33) = -1073741670;
                goto LABEL_42;
              }
              *(_DWORD *)v21 |= 8u;
              *(_QWORD *)(v18 + 336) = 0;
            }
          }
          if ( *(_QWORD *)(*((_QWORD *)v16 + 3) + 128LL) )
          {
            *((_DWORD *)v16 + 13) &= 0xFE7FFFFF;
            v22 = CPacket::Store(v16, 0);
            if ( v22 < 0 )
            {
              *((_DWORD *)this + 33) = v22;
              goto LABEL_42;
            }
            ++*((_DWORD *)this + 32);
          }
          v15 = *(struct _DEVICE_OBJECT **)&v15->Type;
        }
      }
      while ( 1 )
      {
LABEL_42:
        v23 = 0;
        if ( v5 != v15 )
          v23 = &v15[-1].ActiveThreadCount;
        if ( !v23 )
          break;
        if ( v5 == v15 )
        {
          v24 = 64;
          v25 = 52;
        }
        else
        {
          v24 = (__int64)(&v15[-1].Reserved + 1);
          v25 = (__int64)&v15[-1].DeviceObjectExtension + 4;
        }
        if ( (*(_DWORD *)v25 & 0x4000000) == 0 )
          *(_QWORD *)(*(_QWORD *)v24 + 336LL) = 0;
        v15 = *(struct _DEVICE_OBJECT **)&v15->Type;
      }
      if ( *((_DWORD *)this + 32) )
      {
        a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry = 0;
        *((_OWORD *)&a2->Tail.CompletionKey + 1) = 0;
        *((_DWORD *)&a2->Tail.CompletionKey + 6) = *(_DWORD *)(&a2->Tail.CompletionKey + 3) & 0xFFFFFFF8 | 4;
        return CQueueBase::HoldRequest(
                 (CQueueBase *)this,
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
  return result;
}

```

## disassembly

```asm
0x14001fe88  mov     rax, rsp
0x14001fe8b  mov     [rax+8], rbx
0x14001fe8f  push    rbp
0x14001fe90  push    rsi
0x14001fe91  push    rdi
0x14001fe92  push    r12
0x14001fe94  push    r13
0x14001fe96  push    r14
0x14001fe98  push    r15
0x14001fe9a  sub     rsp, 40h
0x14001fe9e  mov     r13, rdx
0x14001fea1  lea     r8, [rax+20h]; unsigned int *
0x14001fea5  xor     r12d, r12d
0x14001fea8  lea     rdx, [rax+18h]; unsigned int *
0x14001feac  mov     [rax+18h], r12d
0x14001feb0  mov     rdi, rcx
0x14001feb3  mov     [rax+20h], r12d
0x14001feb7  call    ?GetPacketTimeouts@CTransaction@@AEAAJAEAK0@Z; CTransaction::GetPacketTimeouts(ulong &,ulong &)
0x14001febc  test    eax, eax
0x14001febe  js      loc_140020197
0x14001fec4  cmp     [rdi+80h], r12d
0x14001fecb  jz      short loc_14001FF06
0x14001fecd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fed4  lea     rax, WPP_GLOBAL_Control
0x14001fedb  cmp     rcx, rax
0x14001fede  jz      short loc_14001FEFC
0x14001fee0  mov     eax, [rcx+6Ch]
0x14001fee3  test    al, 1
0x14001fee5  jz      short loc_14001FEFC
0x14001fee7  mov     rcx, [rcx+58h]
0x14001feeb  lea     edx, [r12+0Dh]
0x14001fef0  lea     r8, WPP_2411d249fb60352b0c479e189fc20775_Traceguids
0x14001fef7  call    WPP_SF_
0x14001fefc  mov     eax, 0C000000Dh
0x14001ff01  jmp     loc_140020197
0x14001ff06  or      dword ptr [rdi+38h], 2
0x14001ff0a  mov     rcx, rdi; this
0x14001ff0d  mov     [rdi+84h], r12d
0x14001ff14  call    ?CompletePendingReaders@CTransaction@@AEAAXXZ; CTransaction::CompletePendingReaders(void)
0x14001ff19  mov     rax, [rdi+40h]
0x14001ff1d  lea     r14, [rdi+48h]
0x14001ff21  mov     r15, [r14]
0x14001ff24  mov     rcx, [rax+40h]
0x14001ff28  mov     eax, [rcx+150h]
0x14001ff2e  mov     [rsp+78h+var_48], eax
0x14001ff32  cmp     r14, r15
0x14001ff35  lea     rsi, [r15-48h]
0x14001ff39  mov     rax, r12
0x14001ff3c  cmovnz  rax, rsi
0x14001ff40  test    rax, rax
0x14001ff43  jz      loc_140020055
0x14001ff49  cmp     r14, r15
0x14001ff4c  cmovz   rsi, r12
0x14001ff50  mov     rcx, rsi; this
0x14001ff53  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001ff58  mov     rbp, rax
0x14001ff5b  test    rax, rax
0x14001ff5e  jz      loc_14002004B
0x14001ff64  movups  xmm0, xmmword ptr [rdi+70h]
0x14001ff68  mov     ecx, [rax+10h]
0x14001ff6b  btr     ecx, 7
0x14001ff6f  movdqu  xmmword ptr [rax+14h], xmm0
0x14001ff74  mov     edx, [rsi+34h]
0x14001ff77  shr     edx, 13h
0x14001ff7a  not     edx
0x14001ff7c  and     edx, 80h
0x14001ff82  or      edx, ecx
0x14001ff84  mov     [rax+10h], edx
0x14001ff87  test    dword ptr [rsi+34h], 4000000h
0x14001ff8e  jnz     short loc_14002000A
0x14001ff90  mov     rcx, [rdi+40h]; struct _DEVICE_OBJECT *
0x14001ff94  call    ?ACpGetSequentialID@@YA_KPEAU_DEVICE_OBJECT@@@Z; ACpGetSequentialID(_DEVICE_OBJECT *)
0x14001ff99  mov     [rbp+4], rax
0x14001ff9d  mov     rdx, rbp; struct CPacketBuffer *
0x14001ffa0  mov     r12, [rsi+40h]
0x14001ffa4  mov     rcx, r12; this
0x14001ffa7  call    ?AssignSequence@CQueue@@QEAAXPEAVCPacketBuffer@@@Z; CQueue::AssignSequence(CPacketBuffer *)
0x14001ffac  lea     rdx, [rbp+4]; struct CPacketInfo *
0x14001ffb0  mov     rcx, r12; this
0x14001ffb3  call    ?SetPacketInformation@CQueue@@QEAAXPEAVCPacketInfo@@@Z; CQueue::SetPacketInformation(CPacketInfo *)
0x14001ffb8  lea     rcx, [rbp+24h]; struct CBaseHeader *
0x14001ffbc  call    ?XactHeaderSafe@CPacketBuffer@@SAPEAUCXactHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::XactHeaderSafe(CBaseHeader *)
0x14001ffc1  test    rax, rax
0x14001ffc4  jz      short loc_140020012
0x14001ffc6  mov     ecx, [rsp+78h+arg_10]
0x14001ffcd  mov     edx, [rsp+78h+var_48]
0x14001ffd1  mov     [rbp+30h], ecx
0x14001ffd4  mov     ecx, [rsp+78h+arg_18]
0x14001ffdb  shl     edx, 4
0x14001ffde  mov     [rbp+54h], ecx
0x14001ffe1  mov     ecx, [rax]
0x14001ffe3  xor     edx, ecx
0x14001ffe5  and     edx, 0FFFFF0h
0x14001ffeb  xor     edx, ecx
0x14001ffed  mov     [rax], edx
0x14001ffef  cmp     qword ptr [r12+150h], 0
0x14001fff8  jnz     short loc_14001FFFF
0x14001fffa  or      edx, 4
0x14001fffd  mov     [rax], edx
0x14001ffff  mov     [r12+150h], rsi
0x140020007  xor     r12d, r12d
0x14002000a  mov     r15, [r15]
0x14002000d  jmp     loc_14001FF32
0x140020012  mov     rcx, cs:WPP_GLOBAL_Control
0x140020019  lea     rax, WPP_GLOBAL_Control
0x140020020  cmp     rcx, rax
0x140020023  jz      short loc_140020041
0x140020025  mov     eax, [rcx+6Ch]
0x140020028  test    al, 1
0x14002002a  jz      short loc_140020041
0x14002002c  mov     rcx, [rcx+58h]
0x140020030  lea     r8, WPP_2411d249fb60352b0c479e189fc20775_Traceguids
0x140020037  mov     edx, 0Eh
0x14002003c  call    WPP_SF_
0x140020041  mov     eax, 80000005h
0x140020046  jmp     loc_140020197
0x14002004b  mov     dword ptr [rdi+84h], 0C000009Ah
0x140020055  mov     rbx, [r14]
0x140020058  cmp     [rdi+84h], r12d
0x14002005f  jnz     loc_140020106
0x140020065  cmp     r14, rbx
0x140020068  lea     rsi, [rbx-48h]
0x14002006c  mov     rax, r12
0x14002006f  cmovnz  rax, rsi
0x140020073  test    rax, rax
0x140020076  jz      loc_140020106
0x14002007c  cmp     r14, rbx
0x14002007f  cmovz   rsi, r12
0x140020083  test    dword ptr [rsi+34h], 4000000h
0x14002008a  jnz     short loc_1400200C4
0x14002008c  mov     rbp, [rsi+40h]
0x140020090  cmp     rsi, [rbp+150h]
0x140020097  jnz     short loc_1400200C4
0x140020099  mov     rcx, rsi; this
0x14002009c  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x1400200a1  lea     rdx, [rax+24h]
0x1400200a5  neg     rax
0x1400200a8  sbb     rcx, rcx
0x1400200ab  and     rcx, rdx; struct CBaseHeader *
0x1400200ae  jz      short loc_1400200F4
0x1400200b0  call    ?XactHeaderSafe@CPacketBuffer@@SAPEAUCXactHeader@@PEAUCBaseHeader@@@Z; CPacketBuffer::XactHeaderSafe(CBaseHeader *)
0x1400200b5  test    rax, rax
0x1400200b8  jz      short loc_1400200F4
0x1400200ba  or      dword ptr [rax], 8
0x1400200bd  mov     [rbp+150h], r12
0x1400200c4  mov     rax, [rsi+18h]
0x1400200c8  cmp     [rax+80h], r12
0x1400200cf  jz      short loc_1400200EC
0x1400200d1  and     dword ptr [rsi+34h], 0FE7FFFFFh
0x1400200d8  xor     edx, edx; struct _IRP *
0x1400200da  mov     rcx, rsi; this
0x1400200dd  call    ?Store@CPacket@@QEAAJPEAU_IRP@@@Z; CPacket::Store(_IRP *)
0x1400200e2  test    eax, eax
0x1400200e4  js      short loc_140020100
0x1400200e6  inc     dword ptr [rdi+80h]
0x1400200ec  mov     rbx, [rbx]
0x1400200ef  jmp     loc_140020065
0x1400200f4  mov     dword ptr [rdi+84h], 0C000009Ah
0x1400200fe  jmp     short loc_140020106
0x140020100  mov     [rdi+84h], eax
0x140020106  cmp     r14, rbx
0x140020109  lea     rax, [rbx-48h]
0x14002010d  mov     rcx, r12
0x140020110  cmovnz  rcx, rax
0x140020114  test    rcx, rcx
0x140020117  jz      short loc_140020147
0x140020119  cmp     r14, rbx
0x14002011c  jnz     short loc_140020128
0x14002011e  mov     ecx, 40h ; '@'
0x140020123  lea     eax, [rcx-0Ch]
0x140020126  jmp     short loc_140020130
0x140020128  lea     rcx, [rbx-8]
0x14002012c  lea     rax, [rbx-14h]
0x140020130  test    dword ptr [rax], 4000000h
0x140020136  jnz     short loc_140020142
0x140020138  mov     rax, [rcx]
0x14002013b  mov     [rax+150h], r12
0x140020142  mov     rbx, [rbx]
0x140020145  jmp     short loc_140020106
0x140020147  cmp     [rdi+80h], r12d
0x14002014e  jnz     short loc_140020158
0x140020150  mov     eax, [rdi+84h]
0x140020156  jmp     short loc_140020197
0x140020158  xorps   xmm0, xmm0
0x14002015b  mov     [rsp+78h+var_58], r12d; int
0x140020160  movups  xmmword ptr [r13+78h], xmm0
0x140020165  lea     r9, ACCancelXactControl; void (*)(struct _DEVICE_OBJECT *, struct _IRP *)
0x14002016c  or      r8d, 0FFFFFFFFh; unsigned int
0x140020170  movups  xmmword ptr [r13+88h], xmm0
0x140020178  mov     eax, [r13+90h]
0x14002017f  mov     rdx, r13; struct _IRP *
0x140020182  and     eax, 0FFFFFFFCh
0x140020185  mov     rcx, rdi; this
0x140020188  or      eax, 4
0x14002018b  mov     [r13+90h], eax
0x140020192  call    ?HoldRequest@CQueueBase@@IEAAJPEAU_IRP@@KP6AXPEAU_DEVICE_OBJECT@@0@ZH@Z; CQueueBase::HoldRequest(_IRP *,ulong,void (*)(_DEVICE_OBJECT *,_IRP *),int)
0x140020197  mov     rbx, [rsp+78h+arg_0]
0x14002019f  add     rsp, 40h
0x1400201a3  pop     r15
0x1400201a5  pop     r14
0x1400201a7  pop     r13
0x1400201a9  pop     r12
0x1400201ab  pop     rdi
0x1400201ac  pop     rsi
0x1400201ad  pop     rbp
0x1400201ae  retn
```
