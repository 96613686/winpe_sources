# FTP_SITE::~FTP_SITE(void)

- ea: `0x180008f40`
- end: `0x180009089`
- name: `??1FTP_SITE@@AEAA@XZ`
- size: `329`
- prototype: `void __fastcall(FTP_SITE *__hidden this)`
- caller_count: `18`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18000b308`
- `0x18000b678`
- `0x18000c420`
- `0x18000cb74`
- `0x18000cfe0`
- `0x18000d400`
- `0x18000df20`
- `0x18000e3f4`
- `0x1800134b0`
- `0x1800160a0`
- `0x180016260`
- `0x1800163f0`
- `0x180016850`
- `0x180016b00`
- `0x180016dd0`
- `0x180032fa0`
- `0x18003607c`
- `0x180036bf8`

## callees

- `0x180001250`
- `0x1800082b8`
- `0x180008f40`
- `0x180009090`
- `0x1800092c0`
- `0x180026fdc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180008f5b`
- `OLEAUT32!__imp_SysFreeString` at `0x180008f5b`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009046`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009053`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009060`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009046`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009053`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x180009060`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180008fc8`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180008fc8`
- `iisutil!WriteRefTraceLog` at `0x180008fab`
- `iisutil!WriteRefTraceLog` at `0x180008fab`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180009082`

## pseudocode

```c
void __fastcall FTP_SITE::~FTP_SITE(FTP_SITE *this)
{
  OLECHAR *v2; // rcx
  FTP_LOGGING *v3; // rcx
  volatile signed __int32 *v4; // rdi
  unsigned __int32 v5; // esi
  _QWORD **v6; // rdi
  _QWORD *v7; // rax
  _QWORD *v8; // rcx
  _QWORD *v9; // rsi

  v2 = (OLECHAR *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    SysFreeString(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = (FTP_LOGGING *)*((_QWORD *)this + 23);
  if ( v3 )
  {
    FTP_LOGGING::DereferenceFtpLogging(v3);
    *((_QWORD *)this + 23) = 0;
  }
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 24);
  if ( v4 )
  {
    v5 = _InterlockedDecrement(v4);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v5);
    if ( !v5 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v4);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v4);
    }
    *((_QWORD *)this + 24) = 0;
  }
  v6 = (_QWORD **)((char *)this + 224);
  while ( 1 )
  {
    v7 = *v6;
    if ( *v6 == v6 )
      break;
    if ( (_QWORD **)v7[1] != v6 || (v8 = (_QWORD *)*v7, *(_QWORD **)(*v7 + 8LL) != v7) )
      __fastfail(3u);
    *v6 = v8;
    v8[1] = v6;
    v9 = v7 - 25;
    if ( v7 != (_QWORD *)200 )
    {
      FTP_SITE_ENDPOINT_ENTRY::~FTP_SITE_ENDPOINT_ENTRY((FTP_SITE_ENDPOINT_ENTRY *)(v7 - 25));
      operator delete(v9);
    }
  }
  _InterlockedDecrement(*((volatile signed __int32 **)this + 39));
  *((_QWORD *)this + 39) = 0;
  *(_DWORD *)this = 1953723494;
  CReaderWriterLock3::~CReaderWriterLock3((FTP_SITE *)((char *)this + 216));
  CReaderWriterLock3::~CReaderWriterLock3((FTP_SITE *)((char *)this + 208));
  CReaderWriterLock3::~CReaderWriterLock3((FTP_SITE *)((char *)this + 200));
  FTP_SITE_PERF_CTRS::~FTP_SITE_PERF_CTRS((FTP_SITE *)((char *)this + 72));
  STRU::~STRU((char *)this + 16);
}

```

## disassembly

```asm
0x180008f40  mov     [rsp+arg_0], rbx
0x180008f45  mov     [rsp+arg_8], rsi
0x180008f4a  push    rdi
0x180008f4b  sub     rsp, 20h
0x180008f4f  mov     rbx, rcx
0x180008f52  mov     rcx, [rcx+8]; bstrString
0x180008f56  test    rcx, rcx
0x180008f59  jz      short loc_180008F69
0x180008f5b  call    cs:__imp_SysFreeString
0x180008f61  mov     qword ptr [rbx+8], 0
0x180008f69  mov     rcx, [rbx+0B8h]; this
0x180008f70  test    rcx, rcx
0x180008f73  jz      short loc_180008F85
0x180008f75  call    ?DereferenceFtpLogging@FTP_LOGGING@@QEAAXXZ; FTP_LOGGING::DereferenceFtpLogging(void)
0x180008f7a  mov     qword ptr [rbx+0B8h], 0
0x180008f85  mov     rdi, [rbx+0C0h]
0x180008f8c  test    rdi, rdi
0x180008f8f  jz      short loc_180008FDA
0x180008f91  or      esi, 0FFFFFFFFh
0x180008f94  lock xadd [rdi], esi
0x180008f98  dec     esi
0x180008f9a  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180008fa1  test    rcx, rcx
0x180008fa4  jz      short loc_180008FB1
0x180008fa6  mov     r8, rdi
0x180008fa9  mov     edx, esi
0x180008fab  call    cs:__imp_WriteRefTraceLog
0x180008fb1  test    esi, esi
0x180008fb3  jnz     short loc_180008FCF
0x180008fb5  mov     rcx, rdi; this
0x180008fb8  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180008fbd  nop
0x180008fbe  mov     rdx, rdi
0x180008fc1  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180008fc8  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180008fce  nop
0x180008fcf  mov     qword ptr [rbx+0C0h], 0
0x180008fda  lea     rdi, [rbx+0E0h]
0x180008fe1  mov     rax, [rdi]
0x180008fe4  cmp     rax, rdi
0x180008fe7  jz      short loc_180009024
0x180008fe9  cmp     [rax+8], rdi
0x180008fed  jnz     short loc_18000901D
0x180008fef  mov     rcx, [rax]
0x180008ff2  cmp     [rcx+8], rax
0x180008ff6  jnz     short loc_18000901D
0x180008ff8  mov     [rdi], rcx
0x180008ffb  mov     [rcx+8], rdi
0x180008fff  lea     rsi, [rax-0C8h]
0x180009006  test    rsi, rsi
0x180009009  jz      short loc_180008FE1
0x18000900b  mov     rcx, rsi; this
0x18000900e  call    ??1FTP_SITE_ENDPOINT_ENTRY@@QEAA@XZ; FTP_SITE_ENDPOINT_ENTRY::~FTP_SITE_ENDPOINT_ENTRY(void)
0x180009013  mov     rcx, rsi; Block
0x180009016  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000901b  jmp     short loc_180008FE1
0x18000901d  mov     ecx, 3
0x180009022  int     29h; Win8: RtlFailFast(ecx)
0x180009024  mov     rax, [rbx+138h]
0x18000902b  lock dec dword ptr [rax]
0x18000902e  mov     qword ptr [rbx+138h], 0
0x180009039  mov     dword ptr [rbx], 74737466h
0x18000903f  lea     rcx, [rbx+0D8h]
0x180009046  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000904c  lea     rcx, [rbx+0D0h]
0x180009053  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180009059  lea     rcx, [rbx+0C8h]
0x180009060  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180009066  lea     rcx, [rbx+48h]; this
0x18000906a  call    ??1FTP_SITE_PERF_CTRS@@QEAA@XZ; FTP_SITE_PERF_CTRS::~FTP_SITE_PERF_CTRS(void)
0x18000906f  lea     rcx, [rbx+10h]
0x180009073  mov     rbx, [rsp+28h+arg_0]
0x180009078  mov     rsi, [rsp+28h+arg_8]
0x18000907d  add     rsp, 20h
0x180009081  pop     rdi
0x180009082  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
