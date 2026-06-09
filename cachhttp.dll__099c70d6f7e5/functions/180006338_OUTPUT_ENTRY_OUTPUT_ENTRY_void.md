# OUTPUT_ENTRY::~OUTPUT_ENTRY(void)

- ea: `0x180006338`
- end: `0x180006383`
- name: `??1OUTPUT_ENTRY@@AEAA@XZ`
- size: `75`
- prototype: `void __fastcall(OUTPUT_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000657c`

## callees

- `0x180005270`
- `0x1800064bc`
- `0x1800064fc`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000636f`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000636f`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006362`
- `iisutil!??1STRA@@QEAA@XZ` at `0x180006362`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180006355`
- `iisutil!??1MULTISZA@@QEAA@XZ` at `0x180006355`

## pseudocode

```c
void __fastcall OUTPUT_ENTRY::~OUTPUT_ENTRY(OUTPUT_ENTRY *this)
{
  OUTPUT_ENTRY::ClearIdentityResponseEntry(this);
  OUTPUT_ENTRY::ClearAlternateResponseEntry(this);
  MULTISZA::~MULTISZA((OUTPUT_ENTRY *)((char *)this + 896));
  STRA::~STRA((OUTPUT_ENTRY *)((char *)this + 840));
  CReaderWriterLock3::~CReaderWriterLock3((OUTPUT_ENTRY *)((char *)this + 816));
  OUTPUT_KEY::~OUTPUT_KEY((OUTPUT_ENTRY *)((char *)this + 8));
}

```

## disassembly

```asm
0x180006338  push    rbx
0x18000633a  sub     rsp, 20h
0x18000633e  mov     rbx, rcx
0x180006341  call    ?ClearIdentityResponseEntry@OUTPUT_ENTRY@@QEAAXXZ; OUTPUT_ENTRY::ClearIdentityResponseEntry(void)
0x180006346  mov     rcx, rbx; this
0x180006349  call    ?ClearAlternateResponseEntry@OUTPUT_ENTRY@@QEAAXXZ; OUTPUT_ENTRY::ClearAlternateResponseEntry(void)
0x18000634e  lea     rcx, [rbx+380h]
0x180006355  call    cs:__imp_??1MULTISZA@@QEAA@XZ; MULTISZA::~MULTISZA(void)
0x18000635b  lea     rcx, [rbx+348h]
0x180006362  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180006368  lea     rcx, [rbx+330h]
0x18000636f  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180006375  lea     rcx, [rbx+8]; this
0x180006379  add     rsp, 20h
0x18000637d  pop     rbx
0x18000637e  jmp     ??1OUTPUT_KEY@@QEAA@XZ; OUTPUT_KEY::~OUTPUT_KEY(void)
```
