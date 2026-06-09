# VARY_BY_CACHE_ENTRY::VARY_BY_CACHE_ENTRY(void)

- ea: `0x180004b0c`
- end: `0x180004bb0`
- name: `??0VARY_BY_CACHE_ENTRY@@QEAA@XZ`
- size: `164`
- prototype: `VARY_BY_CACHE_ENTRY *__fastcall(VARY_BY_CACHE_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004778`

## callees

- `0x180004bb8`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180004b90`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180004b90`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004b69`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004b83`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004b69`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180004b83`

## pseudocode

```c
VARY_BY_CACHE_ENTRY *__fastcall VARY_BY_CACHE_ENTRY::VARY_BY_CACHE_ENTRY(VARY_BY_CACHE_ENTRY *this)
{
  VARY_BY_CACHE_ENTRY *result; // rax

  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &VARY_BY_CACHE_ENTRY::`vftable';
  *((_DWORD *)this + 4) = 2;
  VARY_BY_CACHE_KEY::VARY_BY_CACHE_KEY((VARY_BY_CACHE_ENTRY *)((char *)this + 24));
  *((_DWORD *)this + 162) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_DWORD *)this + 172) = 0;
  STRA::STRA((VARY_BY_CACHE_ENTRY *)((char *)this + 696), (char *)this + 752, 0x100u);
  STRA::STRA((VARY_BY_CACHE_ENTRY *)((char *)this + 1008), (char *)this + 1064, 0x100u);
  CReaderWriterLock3::CReaderWriterLock3((VARY_BY_CACHE_ENTRY *)((char *)this + 1320));
  result = this;
  *((_DWORD *)this + 332) = 0;
  *((_DWORD *)this + 2) = 1162035798;
  return result;
}

```

## disassembly

```asm
0x180004b0c  push    rbx
0x180004b0e  sub     rsp, 20h
0x180004b12  lea     rax, ??_7VARY_BY_CACHE_ENTRY@@6B@; const VARY_BY_CACHE_ENTRY::`vftable'
0x180004b19  mov     dword ptr [rcx+0Ch], 1
0x180004b20  mov     [rcx], rax
0x180004b23  mov     rbx, rcx
0x180004b26  mov     dword ptr [rcx+10h], 2
0x180004b2d  add     rcx, 18h; this
0x180004b31  call    ??0VARY_BY_CACHE_KEY@@QEAA@XZ; VARY_BY_CACHE_KEY::VARY_BY_CACHE_KEY(void)
0x180004b36  lea     rdx, [rbx+2F0h]
0x180004b3d  mov     dword ptr [rbx+288h], 0
0x180004b47  lea     rcx, [rbx+2B8h]
0x180004b4e  mov     qword ptr [rbx+2A8h], 0
0x180004b59  mov     r8d, 100h
0x180004b5f  mov     dword ptr [rbx+2B0h], 0
0x180004b69  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180004b6f  lea     rdx, [rbx+428h]
0x180004b76  mov     r8d, 100h
0x180004b7c  lea     rcx, [rbx+3F0h]
0x180004b83  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180004b89  lea     rcx, [rbx+528h]
0x180004b90  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180004b96  mov     rax, rbx
0x180004b99  mov     dword ptr [rbx+530h], 0
0x180004ba3  mov     dword ptr [rbx+8], 45434256h
0x180004baa  add     rsp, 20h
0x180004bae  pop     rbx
0x180004baf  retn
```
