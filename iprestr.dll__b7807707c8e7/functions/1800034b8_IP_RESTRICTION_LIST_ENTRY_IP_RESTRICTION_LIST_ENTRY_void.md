# IP_RESTRICTION_LIST_ENTRY::IP_RESTRICTION_LIST_ENTRY(void)

- ea: `0x1800034b8`
- end: `0x1800034f5`
- name: `??0IP_RESTRICTION_LIST_ENTRY@@QEAA@XZ`
- size: `61`
- prototype: `IP_RESTRICTION_LIST_ENTRY *__fastcall(IP_RESTRICTION_LIST_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800030a0`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x1800034c5`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800034c5`

## pseudocode

```c
IP_RESTRICTION_LIST_ENTRY *__fastcall IP_RESTRICTION_LIST_ENTRY::IP_RESTRICTION_LIST_ENTRY(
        IP_RESTRICTION_LIST_ENTRY *this)
{
  IP_RESTRICTION_LIST_ENTRY *result; // rax

  STRU::STRU((IP_RESTRICTION_LIST_ENTRY *)((char *)this + 72));
  *(_DWORD *)this = 0;
  *(_QWORD *)((char *)this + 60) = 0;
  *((_DWORD *)this + 17) = 0;
  result = this;
  *(_OWORD *)((char *)this + 4) = 0;
  *((_OWORD *)this + 1) = 0;
  *((_OWORD *)this + 2) = 0;
  *(_OWORD *)((char *)this + 44) = 0;
  return result;
}

```

## disassembly

```asm
0x1800034b8  push    rbx
0x1800034ba  sub     rsp, 20h
0x1800034be  mov     rbx, rcx
0x1800034c1  add     rcx, 48h ; 'H'
0x1800034c5  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800034cb  xor     eax, eax
0x1800034cd  xorps   xmm0, xmm0
0x1800034d0  mov     [rbx], eax
0x1800034d2  xorps   xmm1, xmm1
0x1800034d5  mov     [rbx+3Ch], rax
0x1800034d9  mov     [rbx+44h], eax
0x1800034dc  mov     rax, rbx
0x1800034df  movups  xmmword ptr [rbx+4], xmm0
0x1800034e3  movups  xmmword ptr [rbx+10h], xmm0
0x1800034e7  movups  xmmword ptr [rbx+20h], xmm1
0x1800034eb  movups  xmmword ptr [rbx+2Ch], xmm1
0x1800034ef  add     rsp, 20h
0x1800034f3  pop     rbx
0x1800034f4  retn
```
