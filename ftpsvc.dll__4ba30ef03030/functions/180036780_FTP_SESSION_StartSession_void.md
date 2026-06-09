# FTP_SESSION::StartSession(void)

- ea: `0x180036780`
- end: `0x180036aaf`
- name: `?StartSession@FTP_SESSION@@UEAAJXZ`
- size: `815`
- prototype: `__int64 __fastcall(FTP_SESSION *__hidden this)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180009090`
- `0x18003393c`
- `0x1800365cc`
- `0x180036780`
- `0x180036ab8`
- `0x180036e90`
- `0x180041bbc`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180036882`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180036882`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800367b0`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800367b0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800368d0`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800368d0`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036912`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036a8b`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036912`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180036a8b`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x1800369e5`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x180036a13`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x1800369e5`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x180036a13`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800367ea`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800367ea`
- `iisutil!WriteRefTraceLog` at `0x1800367da`
- `iisutil!WriteRefTraceLog` at `0x1800368f5`
- `iisutil!WriteRefTraceLog` at `0x180036a6e`
- `iisutil!WriteRefTraceLog` at `0x1800367da`
- `iisutil!WriteRefTraceLog` at `0x1800368f5`
- `iisutil!WriteRefTraceLog` at `0x180036a6e`

## string_xrefs

- `0x180036892`: `Service not available, closing control connection.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_SESSION::StartSession(FTP_SESSION *this)
{
  __int64 v2; // rbx
  CReaderWriterLock3 *v3; // rsi
  __int64 v4; // rdx
  __int64 v5; // rbx
  volatile signed __int32 *v6; // rcx
  unsigned __int32 v7; // r8d
  unsigned __int32 v8; // r9d
  unsigned __int32 v9; // eax
  FTP_SITE_PERF_CTRS *i; // rdx
  unsigned __int32 v11; // eax
  int v12; // eax
  const char *v13; // rax
  int Command; // esi
  unsigned __int32 v15; // edi
  CSpinLock *v17; // rcx
  unsigned __int32 v18; // esi
  _BYTE v19[32]; // [rsp+30h] [rbp-88h] BYREF
  const char *v20; // [rsp+50h] [rbp-68h]
  char v21[32]; // [rsp+68h] [rbp-50h] BYREF

  v2 = *((_QWORD *)this + 12);
  v3 = (CReaderWriterLock3 *)(v2 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v2 + 208));
  v4 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v2 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v4);
  v5 = *(_QWORD *)(v2 + 192);
  CReaderWriterLock3::ReadUnlock(v3);
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 12);
  v7 = _InterlockedIncrement(v6 + 35);
  v8 = _InterlockedIncrement((volatile signed __int32 *)FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal + 17);
  while ( 1 )
  {
    v9 = *((_DWORD *)v6 + 36);
    if ( v9 >= v7 )
      break;
    _InterlockedCompareExchange(v6 + 36, v7, v9);
  }
  for ( i = FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal;
        ;
        _InterlockedCompareExchange((volatile signed __int32 *)i + 18, v8, v11) )
  {
    v11 = *((_DWORD *)i + 18);
    if ( v11 >= v8 )
      break;
  }
  _InterlockedAdd(v6 + 37, 1u);
  if ( v7 > *(_DWORD *)(v5 + 160) )
  {
    if ( !*(_DWORD *)(v5 + 164) && !*((_DWORD *)this + 1470) )
    {
      STRA::STRA((STRA *)v19, v21, 0x20u);
      if ( *(_DWORD *)(v5 + 560) )
      {
        v13 = *(const char **)(v5 + 544);
        if ( *(_DWORD *)(v5 + 684) )
        {
          Command = FTP_SESSION::ExpandMessage(this, *(const char **)(v5 + 544), (struct STRA *)v19, 0);
          if ( Command < 0 )
          {
LABEL_16:
            STRA::~STRA((STRA *)v19);
            goto LABEL_17;
          }
          v13 = v20;
        }
        v12 = FTP_SESSION::WriteResponse(this, 0xBu, "421", v13);
      }
      else
      {
        v12 = FTP_SESSION::WriteResponse(this, 0xBu, "421", "Service not available, closing control connection.");
      }
      Command = v12;
      if ( v12 >= 0 )
      {
        (*(void (__fastcall **)(FTP_SESSION *, _QWORD, __int64, const wchar_t *, _DWORD))(*(_QWORD *)this + 32LL))(
          this,
          0,
          19,
          L"Maximum connection limit was reached.",
          0);
        Command = 0;
      }
      goto LABEL_16;
    }
    (*(void (__fastcall **)(FTP_SESSION *, _QWORD, __int64, const wchar_t *, int))(*(_QWORD *)this + 32LL))(
      this,
      0,
      19,
      L"Maximum connection limit was reached.",
      1);
    Command = 0;
LABEL_17:
    if ( v5 )
    {
      v15 = _InterlockedDecrement((volatile signed __int32 *)v5);
      if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
        WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v15);
      if ( !v15 )
      {
        FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v5);
        ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v5);
      }
    }
    return (unsigned int)Command;
  }
  *((_DWORD *)this + 1196) = *(_DWORD *)(v5 + 912);
  *((_DWORD *)this + 1406) = *(_DWORD *)(v5 + 156);
  *((_DWORD *)this + 1407) = *(_DWORD *)(v5 + 140);
  v17 = (FTP_SESSION *)((char *)this + 5616);
  if ( *((_DWORD *)this + 1470) )
  {
    CSpinLock::WriteLock(v17);
    FTP_SESSION::StartTimeoutMonitor(this, *(_DWORD *)(v5 + 140));
    _InterlockedExchange(
      (volatile __int32 *)this + 1404,
      ((*((_BYTE *)this + 5616) - 1) & 3) != 0 ? *((_DWORD *)this + 1404) - 1 : 0);
  }
  else
  {
    CSpinLock::WriteLock(v17);
    FTP_SESSION::StartTimeoutMonitor(this, *(_DWORD *)(v5 + 136));
    _InterlockedExchange(
      (volatile __int32 *)this + 1404,
      ((*((_BYTE *)this + 5616) - 1) & 3) != 0 ? *((_DWORD *)this + 1404) - 1 : 0);
    Command = FTP_SESSION::SendBanner(this, (struct FTP_SITE_CONFIG *)v5);
    if ( Command < 0 )
      goto LABEL_17;
  }
  v18 = _InterlockedDecrement((volatile signed __int32 *)v5);
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v18);
  if ( !v18 )
  {
    FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v5);
    ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, (void *)v5);
  }
  Command = FTP_CONTROL_CHANNEL::ReadCommand((FTP_SESSION *)((char *)this + 1064));
  if ( Command >= 0 )
    return 0;
  return (unsigned int)Command;
}

```

## disassembly

```asm
0x180036780  push    rbx
0x180036782  push    rsi
0x180036783  push    rdi
0x180036784  push    r14
0x180036786  sub     rsp, 98h
0x18003678d  mov     rax, cs:__security_cookie
0x180036794  xor     rax, rsp
0x180036797  mov     [rsp+0B8h+var_30], rax
0x18003679f  mov     rdi, rcx
0x1800367a2  mov     rbx, [rcx+60h]
0x1800367a6  lea     rsi, [rbx+0D0h]
0x1800367ad  mov     rcx, rsi
0x1800367b0  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800367b6  mov     r8, [rbx+0C0h]
0x1800367bd  mov     r14d, 1
0x1800367c3  mov     edx, r14d
0x1800367c6  lock xadd [r8], edx
0x1800367cb  add     edx, r14d
0x1800367ce  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x1800367d5  test    rcx, rcx
0x1800367d8  jz      short loc_1800367E0
0x1800367da  call    cs:__imp_WriteRefTraceLog
0x1800367e0  mov     rbx, [rbx+0C0h]
0x1800367e7  mov     rcx, rsi
0x1800367ea  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800367f0  mov     rcx, [rdi+60h]
0x1800367f4  mov     r8d, r14d
0x1800367f7  lock xadd [rcx+8Ch], r8d
0x180036800  add     r8d, r14d
0x180036803  mov     rax, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x18003680a  mov     r9d, r14d
0x18003680d  lock xadd [rax+44h], r9d
0x180036813  add     r9d, r14d
0x180036816  jmp     short loc_180036821
0x180036818  lock cmpxchg [rcx+90h], r8d
0x180036821  mov     eax, [rcx+90h]
0x180036827  cmp     eax, r8d
0x18003682a  jb      short loc_180036818
0x18003682c  mov     rdx, cs:?sm_pPerfCtrsGlobal@FTP_SITE_PERF_CTRS@@0PEAV1@EA; FTP_SITE_PERF_CTRS * FTP_SITE_PERF_CTRS::sm_pPerfCtrsGlobal
0x180036833  jmp     short loc_18003683B
0x180036835  lock cmpxchg [rdx+48h], r9d
0x18003683b  mov     eax, [rdx+48h]
0x18003683e  cmp     eax, r9d
0x180036841  jb      short loc_180036835
0x180036843  lock add [rcx+94h], r14d
0x18003684b  cmp     r8d, [rbx+0A0h]
0x180036852  jbe     loc_1800369B1
0x180036858  cmp     dword ptr [rbx+0A4h], 0
0x18003685f  jnz     loc_180036989
0x180036865  cmp     dword ptr [rdi+16F8h], 0
0x18003686c  jnz     loc_180036989
0x180036872  mov     r8d, 20h ; ' '
0x180036878  lea     rdx, [rsp+0B8h+var_50]
0x18003687d  lea     rcx, [rsp+0B8h+var_88]
0x180036882  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180036888  nop
0x180036889  cmp     dword ptr [rbx+230h], 0
0x180036890  jnz     short loc_18003689E
0x180036892  lea     rax, aServiceNotAvai; "Service not available, closing control "...
0x180036899  jmp     loc_18003693D
0x18003689e  mov     rax, [rbx+220h]
0x1800368a5  cmp     dword ptr [rbx+2ACh], 0
0x1800368ac  jz      loc_18003693D
0x1800368b2  xor     r9d, r9d; struct STRA *
0x1800368b5  lea     r8, [rsp+0B8h+var_88]; struct STRA *
0x1800368ba  mov     rdx, rax; char *
0x1800368bd  mov     rcx, rdi; this
0x1800368c0  call    ?ExpandMessage@FTP_SESSION@@QEAAJPEBDPEAVSTRA@@1@Z; FTP_SESSION::ExpandMessage(char const *,STRA *,STRA *)
0x1800368c5  mov     esi, eax
0x1800368c7  test    eax, eax
0x1800368c9  jns     short loc_180036938
0x1800368cb  lea     rcx, [rsp+0B8h+var_88]
0x1800368d0  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800368d6  test    rbx, rbx
0x1800368d9  jz      short loc_180036919
0x1800368db  or      edi, 0FFFFFFFFh
0x1800368de  lock xadd [rbx], edi
0x1800368e2  dec     edi
0x1800368e4  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x1800368eb  test    rcx, rcx
0x1800368ee  jz      short loc_1800368FB
0x1800368f0  mov     r8, rbx
0x1800368f3  mov     edx, edi
0x1800368f5  call    cs:__imp_WriteRefTraceLog
0x1800368fb  test    edi, edi
0x1800368fd  jnz     short loc_180036919
0x1800368ff  mov     rcx, rbx; this
0x180036902  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180036907  nop
0x180036908  mov     rdx, rbx
0x18003690b  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180036912  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180036918  nop
0x180036919  mov     eax, esi
0x18003691b  mov     rcx, [rsp+0B8h+var_30]
0x180036923  xor     rcx, rsp; StackCookie
0x180036926  call    __security_check_cookie
0x18003692b  add     rsp, 98h
0x180036932  pop     r14
0x180036934  pop     rdi
0x180036935  pop     rsi
0x180036936  pop     rbx
0x180036937  retn
0x180036938  mov     rax, [rsp+0B8h+var_68]
0x18003693d  mov     r9, rax; char *
0x180036940  lea     r8, a421; "421"
0x180036947  mov     edx, 0Bh; unsigned int
0x18003694c  mov     rcx, rdi; this
0x18003694f  call    ?WriteResponse@FTP_SESSION@@QEAAJKPEBD0ZZ; FTP_SESSION::WriteResponse(ulong,char const *,char const *,...)
0x180036954  mov     esi, eax
0x180036956  test    eax, eax
0x180036958  js      loc_1800368CB
0x18003695e  mov     rax, [rdi]
0x180036961  mov     [rsp+0B8h+var_98], 0
0x180036969  lea     r9, aMaximumConnect; "Maximum connection limit was reached."
0x180036970  xor     edx, edx
0x180036972  lea     r8d, [rdx+13h]
0x180036976  mov     rcx, rdi
0x180036979  mov     rax, [rax+20h]
0x18003697d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036982  xor     esi, esi
0x180036984  jmp     loc_1800368CB
0x180036989  mov     rax, [rdi]
0x18003698c  mov     [rsp+0B8h+var_98], r14d
0x180036991  lea     r9, aMaximumConnect; "Maximum connection limit was reached."
0x180036998  xor     edx, edx
0x18003699a  lea     r8d, [rdx+13h]
0x18003699e  mov     rcx, rdi
0x1800369a1  mov     rax, [rax+20h]
0x1800369a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800369aa  xor     esi, esi
0x1800369ac  jmp     loc_1800368D6
0x1800369b1  mov     eax, [rbx+390h]
0x1800369b7  mov     [rdi+12B0h], eax
0x1800369bd  mov     eax, [rbx+9Ch]
0x1800369c3  mov     [rdi+15F8h], eax
0x1800369c9  mov     eax, [rbx+8Ch]
0x1800369cf  mov     [rdi+15FCh], eax
0x1800369d5  lea     rcx, [rdi+15F0h]
0x1800369dc  cmp     dword ptr [rdi+16F8h], 0
0x1800369e3  jz      short loc_180036A13
0x1800369e5  call    cs:__imp_?WriteLock@CSpinLock@@QEAAXXZ; CSpinLock::WriteLock(void)
0x1800369eb  mov     edx, [rbx+8Ch]; unsigned int
0x1800369f1  mov     rcx, rdi; this
0x1800369f4  call    ?StartTimeoutMonitor@FTP_SESSION@@QEAAXK@Z; FTP_SESSION::StartTimeoutMonitor(ulong)
0x1800369f9  mov     edx, [rdi+15F0h]
0x1800369ff  dec     edx
0x180036a01  mov     eax, edx
0x180036a03  and     al, 3
0x180036a05  neg     al
0x180036a07  sbb     ecx, ecx
0x180036a09  and     ecx, edx
0x180036a0b  xchg    ecx, [rdi+15F0h]
0x180036a11  jmp     short loc_180036A54
0x180036a13  call    cs:__imp_?WriteLock@CSpinLock@@QEAAXXZ; CSpinLock::WriteLock(void)
0x180036a19  mov     edx, [rbx+88h]; unsigned int
0x180036a1f  mov     rcx, rdi; this
0x180036a22  call    ?StartTimeoutMonitor@FTP_SESSION@@QEAAXK@Z; FTP_SESSION::StartTimeoutMonitor(ulong)
0x180036a27  mov     edx, [rdi+15F0h]
0x180036a2d  dec     edx
0x180036a2f  mov     eax, edx
0x180036a31  and     al, 3
0x180036a33  neg     al
0x180036a35  sbb     ecx, ecx
0x180036a37  and     ecx, edx
0x180036a39  xchg    ecx, [rdi+15F0h]
0x180036a3f  mov     rdx, rbx; struct FTP_SITE_CONFIG *
0x180036a42  mov     rcx, rdi; this
0x180036a45  call    ?SendBanner@FTP_SESSION@@QEAAJPEAVFTP_SITE_CONFIG@@@Z; FTP_SESSION::SendBanner(FTP_SITE_CONFIG *)
0x180036a4a  mov     esi, eax
0x180036a4c  test    eax, eax
0x180036a4e  js      loc_1800368D6
0x180036a54  or      esi, 0FFFFFFFFh
0x180036a57  lock xadd [rbx], esi
0x180036a5b  dec     esi
0x180036a5d  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x180036a64  test    rcx, rcx
0x180036a67  jz      short loc_180036A74
0x180036a69  mov     r8, rbx
0x180036a6c  mov     edx, esi
0x180036a6e  call    cs:__imp_WriteRefTraceLog
0x180036a74  test    esi, esi
0x180036a76  jnz     short loc_180036A92
0x180036a78  mov     rcx, rbx; this
0x180036a7b  call    ??1FTP_SITE_CONFIG@@QEAA@XZ; FTP_SITE_CONFIG::~FTP_SITE_CONFIG(void)
0x180036a80  nop
0x180036a81  mov     rdx, rbx
0x180036a84  mov     rcx, cs:?sm_pAllocHandler@FTP_SITE_CONFIG@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_SITE_CONFIG::sm_pAllocHandler
0x180036a8b  call    cs:__imp_?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z; ALLOC_CACHE_HANDLER::Free(void *)
0x180036a91  nop
0x180036a92  lea     rcx, [rdi+428h]; this
0x180036a99  call    ?ReadCommand@FTP_CONTROL_CHANNEL@@QEAAJXZ; FTP_CONTROL_CHANNEL::ReadCommand(void)
0x180036a9e  mov     esi, eax
0x180036aa0  test    eax, eax
0x180036aa2  js      loc_180036919
0x180036aa8  xor     esi, esi
0x180036aaa  jmp     loc_180036919
```
