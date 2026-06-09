# UL_RESPONSE_CACHE_ENTRY::AddInvalidationUrl(ushort const *)

- ea: `0x180002670`
- end: `0x18000280e`
- name: `?AddInvalidationUrl@UL_RESPONSE_CACHE_ENTRY@@QEAAJPEBG@Z`
- size: `414`
- prototype: `__int64 __fastcall(UL_RESPONSE_CACHE_ENTRY *this, char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180002670`
- `0x180002820`
- `0x1800028a0`
- `0x180005a0c`
- `0x180005a4c`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002687`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180002687`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002752`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180002752`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002770`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002770`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800026f7`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800026f7`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002711`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180002711`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000279a`
- `iisutil!?WriteLock@CReaderWriterLock3@@QEAAXXZ` at `0x18000279a`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027b6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027fc`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027b6`
- `iisutil!?WriteUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800027fc`

## pseudocode

```c
__int64 __fastcall UL_RESPONSE_CACHE_ENTRY::AddInvalidationUrl(UL_RESPONSE_CACHE_ENTRY *this, char *a2)
{
  signed __int64 v4; // rax
  char *v5; // r8
  int v6; // r9d
  int v7; // r10d
  int v9; // ebx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  _QWORD *v12; // r14
  int v13; // ebx
  _QWORD *v14; // rax
  __int64 v15; // rcx

  v4 = (char *)STRU::QueryStr((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 576)) - a2;
  v5 = a2;
  do
  {
    v6 = *(unsigned __int16 *)&v5[v4];
    v7 = *(unsigned __int16 *)v5 - v6;
    if ( v7 )
      break;
    v5 += 2;
  }
  while ( v6 );
  if ( !v7 )
    return 0;
  if ( *((_DWORD *)this + 191) )
  {
    CReaderWriterLock3::ReadLock((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 784));
    v9 = UL_RESPONSE_CACHE_ENTRY::ContainsInvalidationUrlOnTheExtraList(this, (const unsigned __int16 *)a2);
    CReaderWriterLock3::ReadUnlock((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 784));
    if ( v9 )
      return 0;
  }
  if ( *((_DWORD *)this + 191) >= 5u )
    return 2147942404LL;
  v10 = (unsigned __int16 *)operator new(0xD0u);
  v11 = v10;
  if ( !v10 )
    return 2147942408LL;
  STRU::STRU((STRU *)(v10 + 12), v10 + 40, 0x40u);
  *(_DWORD *)v11 = 1162630473;
  v12 = v11 + 4;
  *(_OWORD *)(v11 + 4) = 0;
  v13 = STRU::Copy((STRU *)(v11 + 12), (const unsigned __int16 *)a2);
  if ( v13 >= 0 )
  {
    CReaderWriterLock3::WriteLock((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 784));
    if ( (unsigned int)UL_RESPONSE_CACHE_ENTRY::ContainsInvalidationUrlOnTheExtraList(
                         this,
                         (const unsigned __int16 *)a2) )
    {
      CReaderWriterLock3::WriteUnlock((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 784));
      INVALIDATION_URL_LIST_ENTRY::~INVALIDATION_URL_LIST_ENTRY((INVALIDATION_URL_LIST_ENTRY *)v11);
      operator delete(v11);
    }
    else
    {
      v14 = (_QWORD *)((char *)this + 768);
      v15 = *((_QWORD *)this + 96);
      if ( *(UL_RESPONSE_CACHE_ENTRY **)(v15 + 8) != (UL_RESPONSE_CACHE_ENTRY *)((char *)this + 768) )
        __fastfail(3u);
      *v12 = v15;
      *((_QWORD *)v11 + 2) = v14;
      *(_QWORD *)(v15 + 8) = v12;
      *v14 = v12;
      ++*((_DWORD *)this + 191);
      CReaderWriterLock3::WriteUnlock((UL_RESPONSE_CACHE_ENTRY *)((char *)this + 784));
    }
    return 0;
  }
  INVALIDATION_URL_LIST_ENTRY::~INVALIDATION_URL_LIST_ENTRY((INVALIDATION_URL_LIST_ENTRY *)v11);
  operator delete(v11);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180002670  mov     [rsp+arg_18], rbp
0x180002675  push    rsi
0x180002676  sub     rsp, 20h
0x18000267a  mov     rsi, rcx
0x18000267d  mov     rbp, rdx
0x180002680  add     rcx, 240h
0x180002687  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000268d  sub     rax, rbp
0x180002690  mov     r8, rbp
0x180002693  nop     dword ptr [rax+00h]
0x180002697  nop     word ptr [rax+rax+00000000h]
0x1800026a0  movzx   r10d, word ptr [r8]
0x1800026a4  movzx   r9d, word ptr [r8+rax]
0x1800026a9  sub     r10d, r9d
0x1800026ac  jnz     short loc_1800026B7
0x1800026ae  add     r8, 2
0x1800026b2  test    r9d, r9d
0x1800026b5  jnz     short loc_1800026A0
0x1800026b7  mov     [rsp+28h+arg_0], rbx
0x1800026bc  mov     [rsp+28h+arg_8], rdi
0x1800026c1  mov     [rsp+28h+arg_10], r14
0x1800026c6  test    r10d, r10d
0x1800026c9  jnz     short loc_1800026E7
0x1800026cb  xor     eax, eax
0x1800026cd  mov     r14, [rsp+28h+arg_10]
0x1800026d2  mov     rdi, [rsp+28h+arg_8]
0x1800026d7  mov     rbx, [rsp+28h+arg_0]
0x1800026dc  mov     rbp, [rsp+28h+arg_18]
0x1800026e1  add     rsp, 20h
0x1800026e5  pop     rsi
0x1800026e6  retn
0x1800026e7  cmp     dword ptr [rsi+2FCh], 0
0x1800026ee  jz      short loc_18000271B
0x1800026f0  lea     rcx, [rsi+310h]
0x1800026f7  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800026fd  mov     rdx, rbp; unsigned __int16 *
0x180002700  mov     rcx, rsi; this
0x180002703  call    ?ContainsInvalidationUrlOnTheExtraList@UL_RESPONSE_CACHE_ENTRY@@AEAAHPEBG@Z; UL_RESPONSE_CACHE_ENTRY::ContainsInvalidationUrlOnTheExtraList(ushort const *)
0x180002708  lea     rcx, [rsi+310h]
0x18000270f  mov     ebx, eax
0x180002711  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x180002717  test    ebx, ebx
0x180002719  jnz     short loc_1800026CB
0x18000271b  cmp     dword ptr [rsi+2FCh], 5
0x180002722  jnb     short loc_18000273D
0x180002724  mov     ecx, 0D0h; Size
0x180002729  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000272e  mov     rdi, rax
0x180002731  test    rax, rax
0x180002734  jnz     short loc_180002744
0x180002736  mov     eax, 80070008h
0x18000273b  jmp     short loc_1800026CD
0x18000273d  mov     eax, 80070004h
0x180002742  jmp     short loc_1800026CD
0x180002744  lea     rdx, [rax+50h]
0x180002748  mov     r8d, 40h ; '@'
0x18000274e  lea     rcx, [rax+18h]
0x180002752  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180002758  xorps   xmm0, xmm0
0x18000275b  mov     dword ptr [rdi], 454C5549h
0x180002761  lea     r14, [rdi+8]
0x180002765  mov     rdx, rbp
0x180002768  lea     rcx, [rdi+18h]
0x18000276c  movups  xmmword ptr [r14], xmm0
0x180002770  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002776  mov     ebx, eax
0x180002778  test    eax, eax
0x18000277a  jns     short loc_180002793
0x18000277c  mov     rcx, rdi; this
0x18000277f  call    ??1INVALIDATION_URL_LIST_ENTRY@@QEAA@XZ; INVALIDATION_URL_LIST_ENTRY::~INVALIDATION_URL_LIST_ENTRY(void)
0x180002784  mov     rcx, rdi; Block
0x180002787  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000278c  mov     eax, ebx
0x18000278e  jmp     loc_1800026CD
0x180002793  lea     rcx, [rsi+310h]
0x18000279a  call    cs:__imp_?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800027a0  mov     rdx, rbp; unsigned __int16 *
0x1800027a3  mov     rcx, rsi; this
0x1800027a6  call    ?ContainsInvalidationUrlOnTheExtraList@UL_RESPONSE_CACHE_ENTRY@@AEAAHPEBG@Z; UL_RESPONSE_CACHE_ENTRY::ContainsInvalidationUrlOnTheExtraList(ushort const *)
0x1800027ab  test    eax, eax
0x1800027ad  jz      short loc_1800027D1
0x1800027af  lea     rcx, [rsi+310h]
0x1800027b6  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800027bc  mov     rcx, rdi; this
0x1800027bf  call    ??1INVALIDATION_URL_LIST_ENTRY@@QEAA@XZ; INVALIDATION_URL_LIST_ENTRY::~INVALIDATION_URL_LIST_ENTRY(void)
0x1800027c4  mov     rcx, rdi; Block
0x1800027c7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800027cc  jmp     loc_1800026CB
0x1800027d1  lea     rax, [rsi+300h]
0x1800027d8  mov     rcx, [rax]
0x1800027db  cmp     [rcx+8], rax
0x1800027df  jnz     short loc_180002807
0x1800027e1  mov     [r14], rcx
0x1800027e4  mov     [r14+8], rax
0x1800027e8  mov     [rcx+8], r14
0x1800027ec  lea     rcx, [rsi+310h]
0x1800027f3  mov     [rax], r14
0x1800027f6  inc     dword ptr [rsi+2FCh]
0x1800027fc  call    cs:__imp_?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180002802  jmp     loc_1800026CB
0x180002807  mov     ecx, 3
0x18000280c  int     29h; Win8: RtlFailFast(ecx)
```
