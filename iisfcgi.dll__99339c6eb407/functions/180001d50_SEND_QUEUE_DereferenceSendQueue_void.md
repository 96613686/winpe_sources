# SEND_QUEUE::DereferenceSendQueue(void)

- ea: `0x180001d50`
- end: `0x180001d7e`
- name: `?DereferenceSendQueue@SEND_QUEUE@@QEAAXXZ`
- size: `46`
- prototype: `void __fastcall(SEND_QUEUE *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002004`
- `0x180002128`
- `0x1800047ec`
- `0x180006480`

## callees

- `0x180001048`
- `0x180001cc4`
- `0x180001d50`

## pseudocode

```c
void __fastcall SEND_QUEUE::DereferenceSendQueue(struct _RTL_CRITICAL_SECTION *this)
{
  if ( _InterlockedExchangeAdd(&this[2].LockCount, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      SEND_QUEUE::~SEND_QUEUE(this);
      operator delete(this);
    }
  }
}

```

## disassembly

```asm
0x180001d50  push    rbx
0x180001d52  sub     rsp, 20h
0x180001d56  mov     rbx, rcx
0x180001d59  or      eax, 0FFFFFFFFh
0x180001d5c  lock xadd [rcx+58h], eax
0x180001d61  cmp     eax, 1
0x180001d64  jnz     short loc_180001D78
0x180001d66  test    rcx, rcx
0x180001d69  jz      short loc_180001D78
0x180001d6b  call    ??1SEND_QUEUE@@QEAA@XZ; SEND_QUEUE::~SEND_QUEUE(void)
0x180001d70  mov     rcx, rbx; Block
0x180001d73  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180001d78  add     rsp, 20h
0x180001d7c  pop     rbx
0x180001d7d  retn
```
