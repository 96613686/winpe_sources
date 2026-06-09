# CallStackContextNode::`scalar deleting destructor'(uint)

- ea: `0x180004438`
- end: `0x180004457`
- name: `??_GCallStackContextNode@@QEAAPEAXI@Z`
- size: `31`
- prototype: `void *__fastcall(CallStackContextNode *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180002470`
- `0x1800046e8`

## callees

- `0x180001fd0`
- `0x1800028b0`

## pseudocode

```c
CallStackContextNode *__fastcall CallStackContextNode::`scalar deleting destructor'(
        CallStackContextNode *this,
        unsigned __int64 a2,
        unsigned __int64 a3,
        void (*a4)(void *))
{
  `vector destructor iterator'(this, a2, a3, a4);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004438  push    rbx
0x18000443a  sub     rsp, 20h
0x18000443e  mov     rbx, rcx
0x180004441  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180004446  mov     rcx, rbx; Block
0x180004449  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000444e  mov     rax, rbx
0x180004451  add     rsp, 20h
0x180004455  pop     rbx
0x180004456  retn
```
