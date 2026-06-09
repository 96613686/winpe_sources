# PROTOCOL::DereferenceProtocol(void)

- ea: `0x1800033e0`
- end: `0x18000340e`
- name: `?DereferenceProtocol@PROTOCOL@@QEAAXXZ`
- size: `46`
- prototype: `void __fastcall(PROTOCOL *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800033c0`
- `0x1800035f8`
- `0x180003910`
- `0x1800047ec`
- `0x180006480`

## callees

- `0x180001048`
- `0x180002eb4`
- `0x1800033e0`

## pseudocode

```c
void __fastcall PROTOCOL::DereferenceProtocol(PROTOCOL *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 28, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      PROTOCOL::~PROTOCOL(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x1800033e0  push    rbx
0x1800033e2  sub     rsp, 20h
0x1800033e6  mov     rbx, rcx
0x1800033e9  or      eax, 0FFFFFFFFh
0x1800033ec  lock xadd [rcx+70h], eax
0x1800033f1  cmp     eax, 1
0x1800033f4  jnz     short loc_180003408
0x1800033f6  test    rcx, rcx
0x1800033f9  jz      short loc_180003408
0x1800033fb  call    ??1PROTOCOL@@AEAA@XZ; PROTOCOL::~PROTOCOL(void)
0x180003400  mov     rcx, rbx; Block
0x180003403  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003408  add     rsp, 20h
0x18000340c  pop     rbx
0x18000340d  retn
```
