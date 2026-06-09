# OUTPUT_ENTRY::OUTPUT_ENTRY(void)

- ea: `0x180004d18`
- end: `0x180004d8a`
- name: `??0OUTPUT_ENTRY@@QEAA@XZ`
- size: `114`
- prototype: `OUTPUT_ENTRY *__fastcall(OUTPUT_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004220`

## callees

- `0x180005200`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180004d4b`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180004d4b`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180004d7b`
- `iisutil!??0MULTISZA@@QEAA@XZ` at `0x180004d7b`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180004d6e`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180004d6e`

## pseudocode

```c
OUTPUT_ENTRY *__fastcall OUTPUT_ENTRY::OUTPUT_ENTRY(OUTPUT_ENTRY *this)
{
  *(_DWORD *)this = 1;
  OUTPUT_KEY::OUTPUT_KEY((OUTPUT_ENTRY *)((char *)this + 8));
  *((_DWORD *)this + 202) = 0;
  *((_DWORD *)this + 203) = 1;
  CReaderWriterLock3::CReaderWriterLock3((OUTPUT_ENTRY *)((char *)this + 816));
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 104) = 0;
  STRA::STRA((OUTPUT_ENTRY *)((char *)this + 840));
  MULTISZA::MULTISZA((OUTPUT_ENTRY *)((char *)this + 896));
  return this;
}

```

## disassembly

```asm
0x180004d18  push    rbx
0x180004d1a  sub     rsp, 20h
0x180004d1e  mov     rbx, rcx
0x180004d21  mov     dword ptr [rcx], 1
0x180004d27  add     rcx, 8; this
0x180004d2b  call    ??0OUTPUT_KEY@@QEAA@XZ; OUTPUT_KEY::OUTPUT_KEY(void)
0x180004d30  lea     rcx, [rbx+330h]
0x180004d37  mov     dword ptr [rbx+328h], 0
0x180004d41  mov     dword ptr [rbx+32Ch], 1
0x180004d4b  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180004d51  lea     rcx, [rbx+348h]
0x180004d58  mov     qword ptr [rbx+338h], 0
0x180004d63  mov     qword ptr [rbx+340h], 0
0x180004d6e  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x180004d74  lea     rcx, [rbx+380h]
0x180004d7b  call    cs:__imp_??0MULTISZA@@QEAA@XZ; MULTISZA::MULTISZA(void)
0x180004d81  mov     rax, rbx
0x180004d84  add     rsp, 20h
0x180004d88  pop     rbx
0x180004d89  retn
```
