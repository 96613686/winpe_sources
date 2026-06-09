# CPacket::Store(_IRP *)

- ea: `0x140019454`
- end: `0x1400194e4`
- name: `?Store@CPacket@@QEAAJPEAU_IRP@@@Z`
- size: `144`
- prototype: `__int64 __fastcall(CPacket *__hidden this, struct _IRP *)`
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x14001e0c0`
- `0x14001f56c`
- `0x14001f714`
- `0x14001fcc8`
- `0x14001fe88`
- `0x1400201b8`

## callees

- `0x1400104c4`
- `0x140011d68`
- `0x140011d94`
- `0x1400126fc`
- `0x140012754`
- `0x140017970`
- `0x140017ca4`
- `0x140019454`

## pseudocode

```c
__int64 __fastcall CPacket::Store(CMMFAllocator **this, struct _IRP *a2)
{
  __int64 result; // rax
  int v5; // esi
  CBaseObject *v6; // rax

  result = CMMFAllocator::MarkNotCoherent(this[3]);
  if ( (int)result >= 0 )
  {
    if ( a2 )
    {
      if ( !CIrp2Pkt::SafeAttachPacket(a2, (struct CPacket *)this) )
        return 3221225626LL;
      CBaseObject::AddRef((CBaseObject *)this);
    }
    v5 = CPacket::IssueStorage((CPacket *)this);
    if ( v5 >= 0 )
    {
      CPacket::HoldWriteRequest((CPacket *)this, a2);
      return 259;
    }
    else
    {
      if ( a2 )
      {
        v6 = CIrp2Pkt::SafeDetachPacket(a2, (struct CPacket *)this);
        CBaseObject::Release(v6);
      }
      return (unsigned int)v5;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140019454  mov     [rsp+arg_0], rbx
0x140019459  mov     [rsp+arg_8], rsi
0x14001945e  push    rdi
0x14001945f  sub     rsp, 20h
0x140019463  mov     rbx, rcx
0x140019466  mov     rdi, rdx
0x140019469  mov     rcx, [rcx+18h]; this
0x14001946d  call    ?MarkNotCoherent@CMMFAllocator@@QEAAJXZ; CMMFAllocator::MarkNotCoherent(void)
0x140019472  test    eax, eax
0x140019474  js      short loc_1400194D3
0x140019476  test    rdi, rdi
0x140019479  jz      short loc_140019499
0x14001947b  mov     rdx, rbx; struct CPacket *
0x14001947e  mov     rcx, rdi; struct _IRP *
0x140019481  call    ?SafeAttachPacket@CIrp2Pkt@@SA_NPEAU_IRP@@PEAVCPacket@@@Z; CIrp2Pkt::SafeAttachPacket(_IRP *,CPacket *)
0x140019486  test    al, al
0x140019488  jnz     short loc_140019491
0x14001948a  mov     eax, 0C000009Ah
0x14001948f  jmp     short loc_1400194D3
0x140019491  mov     rcx, rbx; this
0x140019494  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x140019499  mov     rcx, rbx; this
0x14001949c  call    ?IssueStorage@CPacket@@AEAAJXZ; CPacket::IssueStorage(void)
0x1400194a1  mov     esi, eax
0x1400194a3  test    eax, eax
0x1400194a5  jns     short loc_1400194C3
0x1400194a7  test    rdi, rdi
0x1400194aa  jz      short loc_1400194BF
0x1400194ac  mov     rdx, rbx; struct CPacket *
0x1400194af  mov     rcx, rdi; struct _IRP *
0x1400194b2  call    ?SafeDetachPacket@CIrp2Pkt@@SAPEAVCPacket@@PEAU_IRP@@PEAV2@@Z; CIrp2Pkt::SafeDetachPacket(_IRP *,CPacket *)
0x1400194b7  mov     rcx, rax; this
0x1400194ba  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x1400194bf  mov     eax, esi
0x1400194c1  jmp     short loc_1400194D3
0x1400194c3  mov     rdx, rdi; struct _IRP *
0x1400194c6  mov     rcx, rbx; this
0x1400194c9  call    ?HoldWriteRequest@CPacket@@AEAAXPEAU_IRP@@@Z; CPacket::HoldWriteRequest(_IRP *)
0x1400194ce  mov     eax, 103h
0x1400194d3  mov     rbx, [rsp+28h+arg_0]
0x1400194d8  mov     rsi, [rsp+28h+arg_8]
0x1400194dd  add     rsp, 20h
0x1400194e1  pop     rdi
0x1400194e2  retn
```
