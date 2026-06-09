# PROTOCOL_SUPPORT_META_CONTEXT::~PROTOCOL_SUPPORT_META_CONTEXT(void)

- ea: `0x180001ba0`
- end: `0x180001bda`
- name: `??1PROTOCOL_SUPPORT_META_CONTEXT@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(PROTOCOL_SUPPORT_META_CONTEXT *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180001b70`

## import_xrefs

- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180001bb0`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180001bba`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180001bc4`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180001bb0`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180001bba`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180001bc4`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180001bd3`

## pseudocode

```c
void __fastcall PROTOCOL_SUPPORT_META_CONTEXT::~PROTOCOL_SUPPORT_META_CONTEXT(PROTOCOL_SUPPORT_META_CONTEXT *this)
{
  MULTISZA::~MULTISZA((PROTOCOL_SUPPORT_META_CONTEXT *)((char *)this + 176));
  MULTISZA::~MULTISZA((PROTOCOL_SUPPORT_META_CONTEXT *)((char *)this + 120));
  MULTISZA::~MULTISZA((PROTOCOL_SUPPORT_META_CONTEXT *)((char *)this + 64));
  MULTISZA::~MULTISZA((PROTOCOL_SUPPORT_META_CONTEXT *)((char *)this + 8));
}

```

## disassembly

```asm
0x180001ba0  push    rbx
0x180001ba2  sub     rsp, 20h
0x180001ba6  mov     rbx, rcx
0x180001ba9  add     rcx, 0B0h
0x180001bb0  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x180001bb6  lea     rcx, [rbx+78h]
0x180001bba  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x180001bc0  lea     rcx, [rbx+40h]
0x180001bc4  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x180001bca  lea     rcx, [rbx+8]
0x180001bce  add     rsp, 20h
0x180001bd2  pop     rbx
0x180001bd3  jmp     cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
```
