# CPacket::DoneMove(CPacketBuffer *,CQueue *)

- ea: `0x140015ac4`
- end: `0x140015b97`
- name: `?DoneMove@CPacket@@QEAAXPEAVCPacketBuffer@@PEAVCQueue@@@Z`
- size: `211`
- prototype: `void __fastcall(CPacket *__hidden this, struct CPacketBuffer *, struct CQueue *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001f8d4`

## callees

- `0x14000baa0`
- `0x140012754`
- `0x14001428c`
- `0x140014850`
- `0x140014ba8`
- `0x140014c48`
- `0x140015ac4`
- `0x1400183c4`
- `0x14001e0c0`

## pseudocode

```c
void __fastcall CPacket::DoneMove(CPacket *this, struct CPacketBuffer *a2, struct _DEVICE_OBJECT **a3)
{
  struct CPacket *v6; // rax
  CPacket *v7; // rbp
  int v8; // eax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_qqq(
      WPP_GLOBAL_Control->Queue.ListEntry.Blink,
      42,
      &WPP_521cf5ef77973c292796e113f00b944d_Traceguids,
      this,
      a2,
      a3);
  }
  if ( (*((_DWORD *)this + 13) & 0x8000000) == 0 )
    CPacket::CacheCurrentState(this, a2);
  *((_DWORD *)this + 13) |= 0x20000u;
  CPacket::CancelTimeout(this);
  CPacket::CompleteWriter(this, 0);
  *((_DWORD *)this + 13) |= 0x40000u;
  v6 = CPacket::CloneSameForMove(this);
  v7 = v6;
  if ( v6 )
  {
    v8 = CQueue::PutPacket(a3, 0, v6, a2, 1);
    if ( v8 < 0 )
      CPacket::PacketRundown(v7, v8);
    CBaseObject::Release((CBaseObject *)a3);
    *((_DWORD *)this + 13) |= 0x80000000;
    CBaseObject::Release(this);
  }
}

```

## disassembly

```asm
0x140015ac4  push    rbx
0x140015ac6  push    rbp
0x140015ac7  push    rsi
0x140015ac8  push    rdi
0x140015ac9  sub     rsp, 38h
0x140015acd  mov     rsi, r8
0x140015ad0  mov     rdi, rdx
0x140015ad3  mov     rbx, rcx
0x140015ad6  mov     rcx, cs:WPP_GLOBAL_Control
0x140015add  lea     rax, WPP_GLOBAL_Control
0x140015ae4  cmp     rcx, rax
0x140015ae7  jz      short loc_140015B12
0x140015ae9  mov     eax, [rcx+6Ch]
0x140015aec  test    al, 4
0x140015aee  jz      short loc_140015B12
0x140015af0  mov     rcx, [rcx+58h]
0x140015af4  mov     edx, 2Ah ; '*'
0x140015af9  mov     [rsp+58h+var_30], r8
0x140015afe  mov     r9, rbx
0x140015b01  lea     r8, WPP_521cf5ef77973c292796e113f00b944d_Traceguids
0x140015b08  mov     qword ptr [rsp+58h+var_38], rdi
0x140015b0d  call    WPP_SF_qqq
0x140015b12  test    dword ptr [rbx+34h], 8000000h
0x140015b19  jnz     short loc_140015B26
0x140015b1b  mov     rdx, rdi; struct CPacketBuffer *
0x140015b1e  mov     rcx, rbx; this
0x140015b21  call    ?CacheCurrentState@CPacket@@QEAAXPEAVCPacketBuffer@@@Z; CPacket::CacheCurrentState(CPacketBuffer *)
0x140015b26  bts     dword ptr [rbx+34h], 11h
0x140015b2b  mov     rcx, rbx; this
0x140015b2e  call    ?CancelTimeout@CPacket@@AEAAXXZ; CPacket::CancelTimeout(void)
0x140015b33  xor     edx, edx; int
0x140015b35  mov     rcx, rbx; this
0x140015b38  call    ?CompleteWriter@CPacket@@QEAAXJ@Z; CPacket::CompleteWriter(long)
0x140015b3d  bts     dword ptr [rbx+34h], 12h
0x140015b42  mov     rcx, rbx; this
0x140015b45  call    ?CloneSameForMove@CPacket@@AEAAPEAV1@XZ; CPacket::CloneSameForMove(void)
0x140015b4a  mov     rbp, rax
0x140015b4d  test    rax, rax
0x140015b50  jz      short loc_140015B8D
0x140015b52  mov     r9, rdi; struct CPacketBuffer *
0x140015b55  mov     [rsp+58h+var_38], 1; int
0x140015b5d  mov     r8, rax; struct CPacket *
0x140015b60  xor     edx, edx; struct _IRP *
0x140015b62  mov     rcx, rsi; this
0x140015b65  call    ?PutPacket@CQueue@@QEAAJPEAU_IRP@@PEAVCPacket@@PEAVCPacketBuffer@@H@Z; CQueue::PutPacket(_IRP *,CPacket *,CPacketBuffer *,int)
0x140015b6a  test    eax, eax
0x140015b6c  jns     short loc_140015B78
0x140015b6e  mov     edx, eax; int
0x140015b70  mov     rcx, rbp; this
0x140015b73  call    ?PacketRundown@CPacket@@QEAAXJ@Z; CPacket::PacketRundown(long)
0x140015b78  mov     rcx, rsi; this
0x140015b7b  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140015b80  bts     dword ptr [rbx+34h], 1Fh
0x140015b85  mov     rcx, rbx; this
0x140015b88  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140015b8d  add     rsp, 38h
0x140015b91  pop     rdi
0x140015b92  pop     rsi
0x140015b93  pop     rbp
0x140015b94  pop     rbx
0x140015b95  retn
```
