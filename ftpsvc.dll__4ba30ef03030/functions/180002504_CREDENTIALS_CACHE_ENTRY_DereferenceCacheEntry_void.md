# CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry(void)

- ea: `0x180002504`
- end: `0x18000256f`
- name: `?DereferenceCacheEntry@CREDENTIALS_CACHE_ENTRY@@QEAAXXZ`
- size: `107`
- prototype: `void __fastcall(CREDENTIALS_CACHE_ENTRY *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005170`
- `0x18001c998`
- `0x18001e0c0`
- `0x18001e368`
- `0x18001e7e4`

## callees

- `0x180002504`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180002547`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180002547`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000253a`
- `iisutil!??1STRA@@QEAA@XZ` at `0x18000253a`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180002562`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180002562`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000252d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002551`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000252d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002551`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CREDENTIALS_CACHE_ENTRY::DereferenceCacheEntry(CREDENTIALS_CACHE_ENTRY *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 5, 0xFFFFFFFF) == 1 )
  {
    if ( this )
    {
      *((_DWORD *)this + 4) = 1131561798;
      STRU::~STRU((char *)this + 352);
      STRA::~STRA((CREDENTIALS_CACHE_ENTRY *)((char *)this + 224));
      CReaderWriterLock3::~CReaderWriterLock3((CREDENTIALS_CACHE_ENTRY *)((char *)this + 212));
      STRU::~STRU((char *)this + 24);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry, this);
    }
  }
}

```

## disassembly

```asm
0x180002504  push    rbx
0x180002506  sub     rsp, 20h
0x18000250a  mov     rbx, rcx
0x18000250d  or      eax, 0FFFFFFFFh
0x180002510  lock xadd [rcx+14h], eax
0x180002515  cmp     eax, 1
0x180002518  jnz     short loc_180002569
0x18000251a  test    rcx, rcx
0x18000251d  jz      short loc_180002569
0x18000251f  mov     dword ptr [rcx+10h], 43724346h
0x180002526  add     rcx, 160h
0x18000252d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002533  lea     rcx, [rbx+0E0h]
0x18000253a  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x180002540  lea     rcx, [rbx+0D4h]
0x180002547  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000254d  lea     rcx, [rbx+18h]
0x180002551  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002557  nop
0x180002558  mov     rdx, rbx
0x18000255b  mov     rcx, cs:?sm_pachCredentialCacheEntry@CREDENTIALS_CACHE_ENTRY@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * CREDENTIALS_CACHE_ENTRY::sm_pachCredentialCacheEntry
0x180002562  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180002568  nop
0x180002569  add     rsp, 20h
0x18000256d  pop     rbx
0x18000256e  retn
```
