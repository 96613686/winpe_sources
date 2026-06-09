# FTP_SESSION::RestoreParentSite(void)

- ea: `0x18003607c`
- end: `0x18003625c`
- name: `?RestoreParentSite@FTP_SESSION@@QEAAJXZ`
- size: `480`
- prototype: `__int64 __fastcall(FTP_SESSION *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800344bc`

## callees

- `0x180001250`
- `0x180008f40`
- `0x180009090`
- `0x180009468`
- `0x18000a630`
- `0x18003607c`
- `0x180049010`

## import_xrefs

- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800361b2`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800361b2`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036247`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036247`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800361e6`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800361e6`
- `iisutil!WriteRefTraceLog` at `0x1800361d6`
- `iisutil!WriteRefTraceLog` at `0x18003622a`
- `iisutil!WriteRefTraceLog` at `0x1800361d6`
- `iisutil!WriteRefTraceLog` at `0x18003622a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FTP_SESSION::RestoreParentSite(FTP_SESSION *this)
{
  volatile signed __int32 *v2; // rcx
  unsigned __int32 v3; // edx
  unsigned __int32 v4; // r8d
  unsigned __int32 v5; // eax
  FTP_SITE_PERF_CTRS *i; // rdx
  unsigned __int32 v7; // eax
  int v8; // edi
  volatile signed __int32 *v9; // rdi
  __int64 v10; // rdi
  CReaderWriterLock3 *v11; // rsi
  __int64 v12; // rdx
  __int64 v13; // rdi
  unsigned __int32 v14; // ebx

  if ( !*((_QWORD *)this + 13) )
    return 0;
  _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)this + 12) + 140LL));
  _InterlockedDecrement((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 17);
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 13);
  v3 = _InterlockedIncrement(v2 + 35);
  v4 = _InterlockedIncrement((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 17);
  while ( 1 )
  {
    v5 = *((_DWORD *)v2 + 36);
    if ( v5 >= v3 )
      break;
    _InterlockedCompareExchange(v2 + 36, v3, v5);
  }
  for ( i = FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal; ; _InterlockedCompareExchange(
                                                        (volatile signed __int32 *)i + 18,
                                                        v4,
                                                        v7) )
  {
    v7 = *((_DWORD *)i + 18);
    if ( v7 >= v4 )
      break;
  }
  _InterlockedAdd(v2 + 37, 1u);
  FTP_SITE::RemoveFromSessionList(*((FTP_SITE **)this + 12), this);
  v8 = FTP_SITE::AddToSessionList(*((FTP_SITE **)this + 13), this);
  if ( v8 >= 0 )
  {
    v9 = (volatile signed __int32 *)*((_QWORD *)this + 12);
    if ( _InterlockedExchangeAdd(v9 + 44, 0xFFFFFFFF) == 1 && v9 )
    {
      FTP_SITE::~FTP_SITE((FTP_SITE *)v9);
      operator delete((void *)v9);
    }
    *((_QWORD *)this + 12) = *((_QWORD *)this + 13);
    *((_QWORD *)this + 13) = 0;
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 132) + 16LL))(*((_QWORD *)this + 132));
    v10 = *((_QWORD *)this + 12);
    v11 = (CReaderWriterLock3 *)(v10 + 208);
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v10 + 208));
    v12 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v10 + 192));
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v12);
    v13 = *(_QWORD *)(v10 + 192);
    CReaderWriterLock3::ReadUnlock(v11);
    *((_DWORD *)this + 1196) = *(_DWORD *)(v13 + 912);
    *((_DWORD *)this + 1406) = *(_DWORD *)(v13 + 156);
    *((_DWORD *)this + 1407) = *(_DWORD *)(v13 + 140);
    v14 = _InterlockedDecrement((volatile signed __int32 *)v13);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v14);
    if ( !v14 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v13);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v13);
    }
    return 0;
  }
  *((_DWORD *)this + 1405) = 0;
  (*(void (__fastcall **)(FTP_SESSION *, _QWORD, __int64, const unsigned __int16 *, int))(*(_QWORD *)this + 32LL))(
    this,
    (unsigned int)v8,
    21,
    L"Site is being stopped.",
    1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003607c  push    rbx
0x18003607e  push    rsi
0x18003607f  push    rdi
0x180036080  push    r15
0x180036082  sub     rsp, 38h
0x180036086  mov     rbx, rcx
0x180036089  cmp     qword ptr [rcx+68h], 0
0x18003608e  jz      loc_18003624E
0x180036094  mov     rax, [rcx+60h]
0x180036098  lock dec dword ptr [rax+8Ch]
0x18003609f  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x1800360a6  lock dec dword ptr [rax+44h]
0x1800360aa  mov     rcx, [rcx+68h]
0x1800360ae  mov     r15d, 1
0x1800360b4  mov     edx, r15d
0x1800360b7  lock xadd [rcx+8Ch], edx
0x1800360bf  add     edx, r15d
0x1800360c2  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x1800360c9  mov     r8d, r15d
0x1800360cc  lock xadd [rax+44h], r8d
0x1800360d2  add     r8d, r15d
0x1800360d5  jmp     short loc_1800360DF
0x1800360d7  lock cmpxchg [rcx+90h], edx
0x1800360df  mov     eax, [rcx+90h]
0x1800360e5  cmp     eax, edx
0x1800360e7  jb      short loc_1800360D7
0x1800360e9  mov     rdx, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x1800360f0  jmp     short loc_1800360F8
0x1800360f2  lock cmpxchg [rdx+48h], r8d
0x1800360f8  mov     eax, [rdx+48h]
0x1800360fb  cmp     eax, r8d
0x1800360fe  jb      short loc_1800360F2
0x180036100  lock add [rcx+94h], r15d
0x180036108  mov     rdx, rbx; struct FTP_SESSION_PUBLIC *
0x18003610b  mov     rcx, [rbx+60h]; this
0x18003610f  call    ?RemoveFromSessionList@FTP_SITE@@QEAAXPEAVFTP_SESSION_PUBLIC@@@Z; FTP_SITE::RemoveFromSessionList(FTP_SESSION_PUBLIC *)
0x180036114  mov     rdx, rbx; struct FTP_SESSION_PUBLIC *
0x180036117  mov     rcx, [rbx+68h]; this
0x18003611b  call    ?AddToSessionList@FTP_SITE@@QEAAJPEAVFTP_SESSION_PUBLIC@@@Z; FTP_SITE::AddToSessionList(FTP_SESSION_PUBLIC *)
0x180036120  mov     edi, eax
0x180036122  test    eax, eax
0x180036124  jns     short loc_180036158
0x180036126  mov     dword ptr [rbx+15F4h], 0
0x180036130  mov     rcx, [rbx]
0x180036133  mov     rax, [rcx+20h]
0x180036137  mov     [rsp+58h+var_38], r15d
0x18003613c  lea     r9, aSiteIsBeingSto; "Site is being stopped."
0x180036143  mov     r8d, 15h
0x180036149  mov     edx, edi
0x18003614b  mov     rcx, rbx
0x18003614e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036153  jmp     loc_180036250
0x180036158  mov     rdi, [rbx+60h]
0x18003615c  or      eax, 0FFFFFFFFh
0x18003615f  lock xadd [rdi+0B0h], eax
0x180036167  cmp     eax, r15d
0x18003616a  jnz     short loc_180036181
0x18003616c  test    rdi, rdi
0x18003616f  jz      short loc_180036181
0x180036171  mov     rcx, rdi; this
0x180036174  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x180036179  mov     rcx, rdi; Block
0x18003617c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036181  mov     rdx, [rbx+68h]
0x180036185  mov     [rbx+60h], rdx
0x180036189  mov     qword ptr [rbx+68h], 0
0x180036191  mov     rcx, [rbx+420h]
0x180036198  mov     rax, [rcx]
0x18003619b  mov     rax, [rax+10h]
0x18003619f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800361a4  mov     rdi, [rbx+60h]
0x1800361a8  lea     rsi, [rdi+0D0h]
0x1800361af  mov     rcx, rsi
0x1800361b2  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800361b8  mov     r8, [rdi+0C0h]
0x1800361bf  mov     edx, r15d
0x1800361c2  lock xadd [r8], edx
0x1800361c7  add     edx, r15d
0x1800361ca  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x1800361d1  test    rcx, rcx
0x1800361d4  jz      short loc_1800361DC
0x1800361d6  call    cs:__imp_WriteRefTraceLog
0x1800361dc  mov     rdi, [rdi+0C0h]
0x1800361e3  mov     rcx, rsi
0x1800361e6  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800361ec  mov     eax, [rdi+390h]
0x1800361f2  mov     [rbx+12B0h], eax
0x1800361f8  mov     eax, [rdi+9Ch]
0x1800361fe  mov     [rbx+15F8h], eax
0x180036204  mov     eax, [rdi+8Ch]
0x18003620a  mov     [rbx+15FCh], eax
0x180036210  or      ebx, 0FFFFFFFFh
0x180036213  lock xadd [rdi], ebx
0x180036217  dec     ebx
0x180036219  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180036220  test    rcx, rcx
0x180036223  jz      short loc_180036230
0x180036225  mov     r8, rdi
0x180036228  mov     edx, ebx
0x18003622a  call    cs:__imp_WriteRefTraceLog
0x180036230  test    ebx, ebx
0x180036232  jnz     short loc_18003624E
0x180036234  mov     rcx, rdi; this
0x180036237  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x18003623c  nop
0x18003623d  mov     rdx, rdi
0x180036240  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180036247  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x18003624d  nop
0x18003624e  xor     edi, edi
0x180036250  mov     eax, edi
0x180036252  add     rsp, 38h
0x180036256  pop     r15
0x180036258  pop     rdi
0x180036259  pop     rsi
0x18003625a  pop     rbx
0x18003625b  retn
```
