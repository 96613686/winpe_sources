# VARY_BY_CACHE_ENTRY::~VARY_BY_CACHE_ENTRY(void)

- ea: `0x18000759c`
- end: `0x18000760e`
- name: `??1VARY_BY_CACHE_ENTRY@@UEAA@XZ`
- size: `114`
- prototype: `void __fastcall(VARY_BY_CACHE_ENTRY *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180007620`

## callees

- `0x1800059e0`
- `0x18000759c`
- `0x180009010`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800075e0`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x1800075e0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800075ed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800075fa`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800075ed`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800075fa`

## pseudocode

```c
void __fastcall VARY_BY_CACHE_ENTRY::~VARY_BY_CACHE_ENTRY(VARY_BY_CACHE_ENTRY *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &VARY_BY_CACHE_ENTRY::`vftable';
  v2 = *((_QWORD *)this + 85);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
    *((_QWORD *)this + 85) = 0;
  }
  *((_DWORD *)this + 2) = 1701012086;
  CReaderWriterLock3::~CReaderWriterLock3((VARY_BY_CACHE_ENTRY *)((char *)this + 1320));
  STRA::~STRA((VARY_BY_CACHE_ENTRY *)((char *)this + 1008));
  STRA::~STRA((VARY_BY_CACHE_ENTRY *)((char *)this + 696));
  VARY_BY_CACHE_KEY::~VARY_BY_CACHE_KEY((VARY_BY_CACHE_ENTRY *)((char *)this + 24));
}

```

## disassembly

```asm
0x18000759c  push    rbx
0x18000759e  sub     rsp, 20h
0x1800075a2  lea     rax, ??_7VARY_BY_CACHE_ENTRY@@6B@; const VARY_BY_CACHE_ENTRY::`vftable'
0x1800075a9  mov     rbx, rcx
0x1800075ac  mov     [rcx], rax
0x1800075af  mov     rcx, [rcx+2A8h]
0x1800075b6  test    rcx, rcx
0x1800075b9  jz      short loc_1800075D2
0x1800075bb  mov     rax, [rcx]
0x1800075be  mov     rax, [rax+8]
0x1800075c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075c7  mov     qword ptr [rbx+2A8h], 0
0x1800075d2  lea     rcx, [rbx+528h]
0x1800075d9  mov     dword ptr [rbx+8], 65636276h
0x1800075e0  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x1800075e6  lea     rcx, [rbx+3F0h]
0x1800075ed  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800075f3  lea     rcx, [rbx+2B8h]
0x1800075fa  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180007600  lea     rcx, [rbx+18h]; this
0x180007604  add     rsp, 20h
0x180007608  pop     rbx
0x180007609  jmp     ??1VARY_BY_CACHE_KEY@@QEAA@XZ; VARY_BY_CACHE_KEY::~VARY_BY_CACHE_KEY(void)
```
