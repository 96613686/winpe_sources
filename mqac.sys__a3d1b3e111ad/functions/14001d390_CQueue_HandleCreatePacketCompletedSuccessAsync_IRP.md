# CQueue::HandleCreatePacketCompletedSuccessAsync(_IRP *)

- ea: `0x14001d390`
- end: `0x14001d475`
- name: `?HandleCreatePacketCompletedSuccessAsync@CQueue@@UEAAJPEAU_IRP@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CQueue *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140001cb0`
- `0x14000d728`
- `0x140012754`
- `0x1400183c4`
- `0x14001d390`
- `0x14001d54c`
- `0x14001e0c0`
- `0x140020278`

## pseudocode

```c
__int64 __fastcall CQueue::HandleCreatePacketCompletedSuccessAsync(CQueue *this, struct _IRP *a2)
{
  CBaseObject *Information; // rdi
  CTransaction *v5; // rbx
  unsigned int v6; // ebx
  struct CPacketBuffer *v7; // rax
  int v8; // eax
  CTransaction *v10; // [rsp+50h] [rbp+8h] BYREF
  CQueue *v11; // [rsp+58h] [rbp+10h] BYREF

  Information = (CBaseObject *)a2->IoStatus.Information;
  a2->IoStatus.Information = 0;
  CBaseObject::Release(Information);
  v5 = (CTransaction *)*((_QWORD *)Information + 5);
  v11 = this;
  v10 = v5;
  *((_QWORD *)Information + 4) = 0;
  *((_QWORD *)Information + 5) = 0;
  CQueue::HandleValidTransactionUsage(this, v5 != 0, Information);
  if ( v5 )
  {
    if ( (*((_DWORD *)v5 + 14) & 2) != 0 )
    {
      v6 = -1072824239;
LABEL_7:
      CBaseObject::Release(Information);
      goto LABEL_10;
    }
    CTransaction::SendPacket(v5, this, Information);
    v6 = 0;
  }
  else
  {
    v7 = CQEntry::Buffer(Information);
    if ( !v7 )
    {
      v6 = -1073741670;
      goto LABEL_7;
    }
    v8 = CQueue::PutPacket((struct _DEVICE_OBJECT **)this, a2, Information, v7, 0);
    v6 = v8;
    if ( v8 < 0 )
      CPacket::PacketRundown(Information, v8);
  }
LABEL_10:
  R<CTransaction>::~R<CTransaction>(&v10);
  R<CTransaction>::~R<CTransaction>(&v11);
  return v6;
}

```

## disassembly

```asm
0x14001d390  mov     [rsp+arg_10], rbx
0x14001d395  push    rbp
0x14001d396  push    rsi
0x14001d397  push    rdi
0x14001d398  sub     rsp, 30h
0x14001d39c  mov     rdi, [rdx+38h]
0x14001d3a0  mov     rsi, rcx
0x14001d3a3  mov     rcx, rdi; this
0x14001d3a6  mov     qword ptr [rdx+38h], 0
0x14001d3ae  mov     rbp, rdx
0x14001d3b1  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001d3b6  mov     rbx, [rdi+28h]
0x14001d3ba  xor     edx, edx
0x14001d3bc  test    rbx, rbx
0x14001d3bf  mov     [rsp+48h+arg_8], rsi
0x14001d3c4  mov     r8, rdi; struct CPacket *
0x14001d3c7  mov     [rsp+48h+arg_0], rbx
0x14001d3cc  setnz   dl; int
0x14001d3cf  mov     qword ptr [rdi+20h], 0
0x14001d3d7  mov     rcx, rsi; this
0x14001d3da  mov     qword ptr [rdi+28h], 0
0x14001d3e2  call    ?HandleValidTransactionUsage@CQueue@@QEBAXHPEAVCPacket@@@Z; CQueue::HandleValidTransactionUsage(int,CPacket *)
0x14001d3e7  test    rbx, rbx
0x14001d3ea  jz      short loc_14001D40C
0x14001d3ec  mov     eax, [rbx+38h]
0x14001d3ef  test    al, 2
0x14001d3f1  jz      short loc_14001D3FA
0x14001d3f3  mov     ebx, 0C00E0051h
0x14001d3f8  jmp     short loc_14001D41E
0x14001d3fa  mov     r8, rdi; struct CPacket *
0x14001d3fd  mov     rdx, rsi; struct CQueue *
0x14001d400  mov     rcx, rbx; this
0x14001d403  call    ?SendPacket@CTransaction@@QEAAXPEAVCQueue@@PEAVCPacket@@@Z; CTransaction::SendPacket(CQueue *,CPacket *)
0x14001d408  xor     ebx, ebx
0x14001d40a  jmp     short loc_14001D451
0x14001d40c  mov     rcx, rdi; this
0x14001d40f  call    ?Buffer@CQEntry@@QEBAPEAVCPacketBuffer@@XZ; CQEntry::Buffer(void)
0x14001d414  test    rax, rax
0x14001d417  jnz     short loc_14001D428
0x14001d419  mov     ebx, 0C000009Ah
0x14001d41e  mov     rcx, rdi; this
0x14001d421  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001d426  jmp     short loc_14001D451
0x14001d428  mov     r9, rax; struct CPacketBuffer *
0x14001d42b  mov     [rsp+48h+var_28], 0; int
0x14001d433  mov     r8, rdi; struct CPacket *
0x14001d436  mov     rdx, rbp; struct _IRP *
0x14001d439  mov     rcx, rsi; this
0x14001d43c  call    ?PutPacket@CQueue@@QEAAJPEAU_IRP@@PEAVCPacket@@PEAVCPacketBuffer@@H@Z; CQueue::PutPacket(_IRP *,CPacket *,CPacketBuffer *,int)
0x14001d441  mov     ebx, eax
0x14001d443  test    eax, eax
0x14001d445  jns     short loc_14001D451
0x14001d447  mov     edx, eax; int
0x14001d449  mov     rcx, rdi; this
0x14001d44c  call    ?PacketRundown@CPacket@@QEAAXJ@Z; CPacket::PacketRundown(long)
0x14001d451  lea     rcx, [rsp+48h+arg_0]
0x14001d456  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14001d45b  lea     rcx, [rsp+48h+arg_8]
0x14001d460  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14001d465  mov     eax, ebx
0x14001d467  mov     rbx, [rsp+48h+arg_10]
0x14001d46c  add     rsp, 30h
0x14001d470  pop     rdi
0x14001d471  pop     rsi
0x14001d472  pop     rbp
0x14001d473  retn
```
