# CQueueBase::MoveToGroup(CGroup *)

- ea: `0x14001a09c`
- end: `0x14001a129`
- name: `?MoveToGroup@CQueueBase@@QEAAXPEAVCGroup@@@Z`
- size: `141`
- prototype: `void(CQueueBase *__hidden this, struct CGroup *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140006fd8`
- `0x1400199ac`

## callees

- `0x140010e00`
- `0x140014c00`
- `0x140019dd0`
- `0x14001a09c`
- `0x14001a7d0`
- `0x140024bf0`

## pseudocode

```c
void __fastcall CQueueBase::MoveToGroup(CQueueBase *this, struct CGroup *a2)
{
  struct CGroup *v2; // rax
  struct CPacket *v5; // rax
  CPacket *v6; // rsi
  struct _IRP *Request; // rax

  v2 = (struct CGroup *)*((_QWORD *)this + 4);
  if ( a2 != v2 )
  {
    if ( v2 )
    {
      XList<CQueueBase,16>::remove(this, this);
      *((_QWORD *)this + 4) = 0;
    }
    if ( a2 )
    {
      *((_QWORD *)this + 4) = a2;
      XList<CMMFAllocator,16>::insert((char *)a2 + 72, this);
      while ( 1 )
      {
        v5 = (struct CPacket *)(*(__int64 (__fastcall **)(CQueueBase *))(*(_QWORD *)this + 64LL))(this);
        v6 = v5;
        if ( !v5 )
          break;
        Request = CQueueBase::GetRequest(a2, v5);
        if ( !Request )
          break;
        CPacket::CompleteRequest(v6, Request);
      }
    }
  }
}

```

## disassembly

```asm
0x14001a09c  mov     [rsp+arg_0], rbx
0x14001a0a1  mov     [rsp+arg_8], rsi
0x14001a0a6  push    rdi
0x14001a0a7  sub     rsp, 20h
0x14001a0ab  mov     rax, [rcx+20h]
0x14001a0af  mov     rdi, rdx
0x14001a0b2  mov     rbx, rcx
0x14001a0b5  cmp     rdx, rax
0x14001a0b8  jz      short loc_14001A118
0x14001a0ba  test    rax, rax
0x14001a0bd  jz      short loc_14001A0CF
0x14001a0bf  mov     rdx, rcx
0x14001a0c2  call    ?remove@?$XList@VCQueueBase@@$0BA@@@QEAAXPEAVCQueueBase@@@Z; XList<CQueueBase,16>::remove(CQueueBase *)
0x14001a0c7  mov     qword ptr [rbx+20h], 0
0x14001a0cf  test    rdi, rdi
0x14001a0d2  jz      short loc_14001A118
0x14001a0d4  lea     rcx, [rdi+48h]
0x14001a0d8  mov     [rbx+20h], rdi
0x14001a0dc  mov     rdx, rbx
0x14001a0df  call    ?insert@?$XList@VCMMFAllocator@@$0BA@@@QEAAXPEAVCMMFAllocator@@@Z; XList<CMMFAllocator,16>::insert(CMMFAllocator *)
0x14001a0e4  mov     rax, [rbx]
0x14001a0e7  mov     rcx, rbx
0x14001a0ea  mov     rax, [rax+40h]
0x14001a0ee  call    _guard_dispatch_icall
0x14001a0f3  mov     rsi, rax
0x14001a0f6  test    rax, rax
0x14001a0f9  jz      short loc_14001A118
0x14001a0fb  mov     rdx, rax; struct CPacket *
0x14001a0fe  mov     rcx, rdi; this
0x14001a101  call    ?GetRequest@CQueueBase@@IEAAPEAU_IRP@@PEAVCPacket@@@Z; CQueueBase::GetRequest(CPacket *)
0x14001a106  test    rax, rax
0x14001a109  jz      short loc_14001A118
0x14001a10b  mov     rdx, rax; struct _IRP *
0x14001a10e  mov     rcx, rsi; this
0x14001a111  call    ?CompleteRequest@CPacket@@QEAAJPEAU_IRP@@@Z; CPacket::CompleteRequest(_IRP *)
0x14001a116  jmp     short loc_14001A0E4
0x14001a118  mov     rbx, [rsp+28h+arg_0]
0x14001a11d  mov     rsi, [rsp+28h+arg_8]
0x14001a122  add     rsp, 20h
0x14001a126  pop     rdi
0x14001a127  retn
```
