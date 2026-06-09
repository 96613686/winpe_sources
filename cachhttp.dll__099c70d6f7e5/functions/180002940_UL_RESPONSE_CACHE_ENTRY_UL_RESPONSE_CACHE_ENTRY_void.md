# UL_RESPONSE_CACHE_ENTRY::UL_RESPONSE_CACHE_ENTRY(void)

- ea: `0x180002940`
- end: `0x1800029be`
- name: `??0UL_RESPONSE_CACHE_ENTRY@@QEAA@XZ`
- size: `126`
- prototype: `UL_RESPONSE_CACHE_ENTRY *__fastcall(UL_RESPONSE_CACHE_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800020d0`

## callees

- `0x180002610`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002996`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180002996`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000297e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000297e`

## pseudocode

```c
UL_RESPONSE_CACHE_ENTRY *__fastcall UL_RESPONSE_CACHE_ENTRY::UL_RESPONSE_CACHE_ENTRY(UL_RESPONSE_CACHE_ENTRY *this)
{
  *((_DWORD *)this + 2) = 1129466965;
  *(_QWORD *)this = &UL_RESPONSE_CACHE_ENTRY::`vftable';
  *((_DWORD *)this + 3) = 1;
  UL_RESPONSE_CACHE_KEY::UL_RESPONSE_CACHE_KEY((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 16));
  STRU::STRU((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 576), (unsigned __int16 *)this + 316, 0x40u);
  *((_QWORD *)this + 95) = 2;
  CReaderWriterLock3::CReaderWriterLock3((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 784));
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 97) = (char *)this + 768;
  *((_QWORD *)this + 96) = (char *)this + 768;
  return this;
}

```

## disassembly

```asm
0x180002940  push    rbx
0x180002942  sub     rsp, 20h
0x180002946  lea     rax, ??_7UL_RESPONSE_CACHE_ENTRY@@6B@; const UL_RESPONSE_CACHE_ENTRY::`vftable'
0x18000294d  mov     dword ptr [rcx+8], 43524C55h
0x180002954  mov     [rcx], rax
0x180002957  mov     rbx, rcx
0x18000295a  mov     dword ptr [rcx+0Ch], 1
0x180002961  add     rcx, 10h; this
0x180002965  call    ??0UL_RESPONSE_CACHE_KEY@@QEAA@XZ; UL_RESPONSE_CACHE_KEY::UL_RESPONSE_CACHE_KEY(void)
0x18000296a  lea     rdx, [rbx+278h]
0x180002971  mov     r8d, 40h ; '@'
0x180002977  lea     rcx, [rbx+240h]
0x18000297e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002984  lea     rcx, [rbx+310h]
0x18000298b  mov     qword ptr [rbx+2F8h], 2
0x180002996  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18000299c  lea     rax, [rbx+300h]
0x1800029a3  mov     qword ptr [rbx+318h], 0
0x1800029ae  mov     [rax+8], rax
0x1800029b2  mov     [rax], rax
0x1800029b5  mov     rax, rbx
0x1800029b8  add     rsp, 20h
0x1800029bc  pop     rbx
0x1800029bd  retn
```
