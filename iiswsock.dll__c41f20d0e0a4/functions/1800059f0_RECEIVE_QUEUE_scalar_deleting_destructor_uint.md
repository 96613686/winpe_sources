# RECEIVE_QUEUE::`scalar deleting destructor'(uint)

- ea: `0x1800059f0`
- end: `0x180005a42`
- name: `??_GRECEIVE_QUEUE@@UEAAPEAXI@Z`
- size: `82`
- prototype: `RECEIVE_QUEUE *__fastcall(RECEIVE_QUEUE *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001048`
- `0x180003fcc`
- `0x1800059f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a1b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180005a1b`

## pseudocode

```c
RECEIVE_QUEUE *__fastcall RECEIVE_QUEUE::`scalar deleting destructor'(RECEIVE_QUEUE *this, char a2)
{
  *(_QWORD *)this = &RECEIVE_QUEUE::`vftable';
  QUEUE::Clear((RECEIVE_QUEUE *)((char *)this + 16));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x1800059f0  mov     [rsp+arg_0], rbx
0x1800059f5  mov     [rsp+arg_8], rsi
0x1800059fa  push    rdi
0x1800059fb  sub     rsp, 20h
0x1800059ff  lea     rax, ??_7RECEIVE_QUEUE@@6B@; const RECEIVE_QUEUE::`vftable'
0x180005a06  mov     rsi, rcx
0x180005a09  mov     [rcx], rax
0x180005a0c  mov     edi, edx
0x180005a0e  add     rcx, 10h; this
0x180005a12  call    ?Clear@QUEUE@@QEAAXXZ; QUEUE::Clear(void)
0x180005a17  lea     rcx, [rsi+10h]; lpCriticalSection
0x180005a1b  call    cs:__imp_DeleteCriticalSection
0x180005a21  test    dil, 1
0x180005a25  jz      short loc_180005A2F
0x180005a27  mov     rcx, rsi; Block
0x180005a2a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005a2f  mov     rbx, [rsp+28h+arg_0]
0x180005a34  mov     rax, rsi
0x180005a37  mov     rsi, [rsp+28h+arg_8]
0x180005a3c  add     rsp, 20h
0x180005a40  pop     rdi
0x180005a41  retn
```
