# FTP_SESSION::OnReadCommandCompletion(long,uchar *,ulong)

- ea: `0x18003553c`
- end: `0x180035dc5`
- name: `?OnReadCommandCompletion@FTP_SESSION@@QEAAXJPEAEK@Z`
- size: `2185`
- prototype: `void __fastcall(FTP_SESSION *this, int Command, char *, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800418e4`

## callees

- `0x180009090`
- `0x180035240`
- `0x18003553c`
- `0x1800365cc`
- `0x180036ab8`
- `0x180036b20`
- `0x18003d868`
- `0x18003dbac`
- `0x18003f9b4`
- `0x180041bbc`
- `0x180047003`
- `0x18004700f`
- `0x180047050`
- `0x180049010`

## import_xrefs

- `msvcrt!_memicmp` at `0x180035924`
- `msvcrt!_memicmp` at `0x180035924`
- `msvcrt!_stricmp` at `0x18003597d`
- `msvcrt!_stricmp` at `0x180035a12`
- `msvcrt!_stricmp` at `0x18003597d`
- `msvcrt!_stricmp` at `0x180035a12`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003576f`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x18003576f`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180035589`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x180035589`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180035c1f`
- `iisutil!?Free@ALLOC_CACHE_HANDLER@@QEAAHPEAX@Z` at `0x180035c1f`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x1800355f7`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x1800359b5`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x180035c3e`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x1800355f7`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x1800359b5`
- `iisutil!?WriteLock@CSpinLock@@QEAAXXZ` at `0x180035c3e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003578a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18003578a`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800355bf`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800355bf`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180035749`
- `iisutil!??0STRA@@QEAA@XZ` at `0x180035749`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180035723`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x180035723`
- `iisutil!WriteRefTraceLog` at `0x1800355af`
- `iisutil!WriteRefTraceLog` at `0x180035c02`
- `iisutil!WriteRefTraceLog` at `0x1800355af`
- `iisutil!WriteRefTraceLog` at `0x180035c02`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180035754`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180035798`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18003589b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800358b6`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180035754`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180035798`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18003589b`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800358b6`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180035ae6`
- `iisutil!?EtwTraceEvent@CEtwTracer@@QEAAKPEAU_EVENT_TRACE_HEADER@@@Z` at `0x180035ae6`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180035657`
- `iisutil!?Append@STRA@@QEAAJPEBDK@Z` at `0x180035657`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180035cac`
- `iisutil!?Copy@STRA@@QEAAJPEBDK@Z` at `0x180035cac`

## string_xrefs

- `0x18003593d`: `Data channel was closed by ABOR command from client.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall FTP_SESSION::OnReadCommandCompletion(FTP_SESSION *this, int Command, char *a3, int a4)
{
  unsigned int v4; // r14d
  unsigned int v8; // r13d
  __int64 v9; // r15
  CReaderWriterLock3 *v10; // rdi
  __int64 v11; // rdx
  unsigned int *v12; // r15
  unsigned int v13; // r10d
  int v14; // r8d
  int v15; // edi
  int v16; // edx
  unsigned int v17; // ecx
  int v18; // eax
  char *v19; // rdi
  __int64 v20; // rax
  bool v21; // zf
  const char *v22; // rax
  int v23; // eax
  __int64 v24; // rax
  int v25; // eax
  __int64 v26; // rax
  char *v27; // rcx
  FTP_SESSION **v28; // rdx
  __int64 *v29; // rax
  __int64 v30; // rdx
  unsigned __int32 v31; // edi
  FTP_SESSION **v32; // rdx
  FTP_SESSION *v33; // rax
  int v34; // [rsp+30h] [rbp-99h]
  int v35; // [rsp+34h] [rbp-95h] BYREF
  int v36; // [rsp+38h] [rbp-91h]
  unsigned int v37; // [rsp+3Ch] [rbp-8Dh]
  int v38; // [rsp+40h] [rbp-89h]
  int v39; // [rsp+44h] [rbp-85h]
  const char *v40; // [rsp+48h] [rbp-81h]
  unsigned __int8 *v41; // [rsp+50h] [rbp-79h]
  __int64 v42; // [rsp+58h] [rbp-71h]
  CEtwTracer *v43; // [rsp+60h] [rbp-69h]
  char *v44; // [rsp+68h] [rbp-61h]
  struct _EVENT_TRACE_HEADER v45; // [rsp+70h] [rbp-59h] BYREF
  char *v46; // [rsp+A0h] [rbp-29h]
  int v47; // [rsp+A8h] [rbp-21h]
  __int64 v48; // [rsp+B0h] [rbp-19h]
  int v49; // [rsp+B8h] [rbp-11h]
  const char *v50; // [rsp+C0h] [rbp-9h]
  int v51; // [rsp+C8h] [rbp-1h]

  v4 = a4;
  v35 = a4;
  v8 = 0;
  v34 = 0;
  v9 = *((_QWORD *)this + 12);
  v10 = (CReaderWriterLock3 *)(v9 + 208);
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v9 + 208));
  v11 = (unsigned int)_InterlockedIncrement(*(volatile signed __int32 **)(v9 + 192));
  if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
    WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v11);
  v12 = *(unsigned int **)(v9 + 192);
  CReaderWriterLock3::ReadUnlock(v10);
  if ( Command < 0 )
    goto LABEL_68;
  Command = 0;
  if ( *((_DWORD *)this + 1471) )
  {
    *((_DWORD *)this + 1471) = 0;
    if ( (int)FTP_SESSION::SendBanner(this, (struct FTP_SITE_CONFIG *)v12) >= 0 )
    {
      CSpinLock::WriteLock((FTP_SESSION *)((char *)this + 5616));
      FTP_SESSION::StartTimeoutMonitor(this, v12[34]);
      _InterlockedExchange(
        (volatile __int32 *)this + 1404,
        ((*((_BYTE *)this + 5616) - 1) & 3) != 0 ? *((_DWORD *)this + 1404) - 1 : 0);
      FTP_CONTROL_CHANNEL::ReadCommand((FTP_SESSION *)((char *)this + 1064));
    }
    goto LABEL_68;
  }
  v13 = v12[263];
  v37 = v13;
  if ( *((_DWORD *)this + 1394) )
  {
    Command = STRA::Append((FTP_SESSION *)((char *)this + 5528), a3, v4);
    if ( Command < 0 )
      goto LABEL_68;
    v4 = *((_DWORD *)this + 1394);
    a3 = (char *)*((_QWORD *)this + 695);
    v38 = 1;
    v13 = v37;
  }
  else
  {
    v38 = 0;
  }
  v14 = 1;
  v36 = 1;
  v41 = (unsigned __int8 *)&a3[v4];
  while ( 1 )
  {
    v15 = 0;
    v16 = 0;
    if ( v4 )
    {
      while ( 1 )
      {
        v17 = v16 + 1;
        if ( a3[v16] == 10 )
          break;
        ++v16;
        if ( v17 >= v4 )
          goto LABEL_17;
      }
      v15 = 1;
      v8 = v16 + 1;
    }
LABEL_17:
    if ( !v35 )
      v15 = 1;
    v39 = v15;
    v8 &= -(v35 != 0);
    v18 = *((_DWORD *)this + 1401);
    if ( !v15 )
      break;
    if ( v18 )
    {
      *((_DWORD *)this + 1401) = 0;
      v8 = v16 + 1;
      goto LABEL_62;
    }
LABEL_26:
    v19 = (char *)ALLOC_CACHE_HANDLER::Alloc((ALLOC_CACHE_HANDLER *)FTP_COMMAND::sm_pAllocHandler);
    v44 = v19;
    if ( v19 )
    {
      *(_QWORD *)v19 = &FTP_COMMAND::`vftable';
      STRA::STRA((STRA *)(v19 + 16));
      STRU::STRU(v19 + 72);
      STRA::STRA((STRA *)(v19 + 128), v19 + 184, 0x80u);
      STRU::STRU((STRU *)(v19 + 312), (unsigned __int16 *)v19 + 184, 0x80u);
      STRU::STRU(v19 + 624);
      *((_QWORD *)v19 + 101) = 0;
      *((_QWORD *)v19 + 102) = 0;
      *((_QWORD *)v19 + 103) = 0;
      *((_QWORD *)v19 + 104) = 0;
      *((_QWORD *)v19 + 105) = 0;
      *((_QWORD *)v19 + 106) = 0;
      *((_QWORD *)v19 + 107) = 0;
      *((_DWORD *)v19 + 216) = 0;
      *((_QWORD *)v19 + 110) = 0;
      *((_QWORD *)v19 + 111) = 0;
      *((_QWORD *)v19 + 116) = 0;
      *((_QWORD *)v19 + 117) = 0;
      *((_QWORD *)v19 + 118) = 0;
      *((_DWORD *)v19 + 238) = 0;
      *((_OWORD *)v19 + 56) = 0;
      *((_OWORD *)v19 + 57) = 0;
      *((_QWORD *)v19 + 109) = &DATA_STREAM_ASYNC_CONTEXT::`vftable';
      *((_QWORD *)v19 + 120) = 0;
      *((_QWORD *)v19 + 122) = 0;
      *((_DWORD *)v19 + 246) = 0;
      *((_QWORD *)v19 + 124) = 0;
      *((_QWORD *)v19 + 125) = 0;
      *((_QWORD *)v19 + 126) = 0;
      *((_DWORD *)v19 + 242) = 1396855620;
      *((_QWORD *)v19 + 127) = -1;
      *((_QWORD *)v19 + 128) = 0;
      *((_QWORD *)v19 + 132) = 0;
      *((_QWORD *)v19 + 133) = 0;
      *((_QWORD *)v19 + 134) = 0;
      *((_WORD *)v19 + 542) = 0;
      *(_QWORD *)(v19 + 1092) = 0;
      *((_QWORD *)v19 + 138) = &WideCharStr;
      STRU::STRU(v19 + 1112);
      *((_QWORD *)v19 + 146) = 0;
      *((_DWORD *)v19 + 294) = 0;
      STRU::STRU(v19 + 1184);
      *((_QWORD *)v19 + 110) = FTP_COMMAND::AsyncCompletionRoutine;
      *((_QWORD *)v19 + 117) = 0;
      *((_QWORD *)v19 + 111) = v19;
      *((_QWORD *)v19 + 118) = 0;
      *((_QWORD *)v19 + 130) = 0;
      *((_QWORD *)v19 + 131) = 0;
      *((_DWORD *)v19 + 270) = 0;
      *((_DWORD *)v19 + 2) = 1296258118;
    }
    else
    {
      v19 = 0;
    }
    if ( !v19 )
    {
      Command = -2147024888;
      goto LABEL_67;
    }
    if ( *((_QWORD *)this + 701) && v8 == 6 && !_memicmp(a3, "ABOR\r\n", 6u) )
      FTP_DATA_CHANNEL::InitiateChannelShutdown(
        (FTP_SESSION *)((char *)this + 2072),
        -2147023660,
        0x14u,
        L"Data channel was closed by ABOR command from client.",
        1);
    Command = FTP_COMMAND::Initialize(
                (FTP_COMMAND *)v19,
                this,
                (unsigned __int8 *)a3,
                v8,
                (struct FTP_SITE_CONFIG *)v12);
    if ( Command < 0 )
      goto LABEL_66;
    if ( !_stricmp(*((const char **)v19 + 6), "AUTH") && &a3[v8] < (char *)v41 )
    {
      v36 = 0;
      if ( *(v41 - 1) != 10 )
        *((_DWORD *)this + 1401) = 1;
    }
    CSpinLock::WriteLock((FTP_SESSION *)((char *)this + 5616));
    if ( *((_DWORD *)this + 1400) >= 0x14u )
    {
      Command = -2147023604;
      _InterlockedExchange(
        (volatile __int32 *)this + 1404,
        ((*((_BYTE *)this + 5616) - 1) & 3) != 0 ? *((_DWORD *)this + 1404) - 1 : 0);
LABEL_66:
      (**(void (__fastcall ***)(void *, __int64))v19)(v19, 1);
LABEL_67:
      v8 = v34;
      goto LABEL_68;
    }
    FTP_SESSION::StopTimeoutMonitor(this);
    ++*((_DWORD *)this + 1400);
    v20 = (*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
    if ( *(_DWORD *)(v20 + 8) && (*(_BYTE *)(v20 + 40) & 2) != 0 && *(_DWORD *)(v20 + 44) >= 5u )
    {
      v21 = _stricmp(*((const char **)v19 + 6), "PASS") == 0;
      v22 = "***";
      if ( !v21 )
        v22 = (const char *)*((_QWORD *)v19 + 20);
      v40 = v22;
      v42 = *((_QWORD *)v19 + 6);
      v43 = (CEtwTracer *)(*(__int64 (__fastcall **)(FTP_SERVERP *))(*(_QWORD *)g_pFtpServer + 32LL))(g_pFtpServer);
      memset_0(&v45.FieldTypeFlags, 0, 0x5Eu);
      v45.UserTime = 1703936;
      v45.Size = 96;
      v45.Class.Version = 1;
      v45.Class.Type = 4;
      v45.GuidPtr = (ULONGLONG)&`FtpCommandsEvents::GetAreaGuid'::`2'::AreaGuid;
      v46 = (char *)this + 368;
      v47 = 16;
      v48 = v42;
      if ( v42 )
      {
        v24 = -1;
        do
          ++v24;
        while ( *(_BYTE *)(v42 + v24) );
        v23 = v24 + 1;
      }
      else
      {
        v23 = 0;
      }
      v49 = v23;
      v50 = v40;
      if ( v40 )
      {
        v26 = -1;
        do
          ++v26;
        while ( v40[v26] );
        v25 = v26 + 1;
      }
      else
      {
        v25 = 0;
      }
      v51 = v25;
      CEtwTracer::EtwTraceEvent(v43, &v45);
    }
    v27 = (char *)this + 5584;
    v28 = (FTP_SESSION **)*((_QWORD *)this + 699);
    if ( *v28 != (FTP_SESSION *)((char *)this + 5584) )
      goto LABEL_76;
    *((_QWORD *)v19 + 130) = v27;
    *((_QWORD *)v19 + 131) = v28;
    *v28 = (FTP_SESSION *)(v19 + 1040);
    *((_QWORD *)this + 699) = v19 + 1040;
    if ( !*((_QWORD *)this + 701) )
    {
      v29 = *(__int64 **)v27;
      if ( *(char **)(*(_QWORD *)v27 + 8LL) != v27 )
        goto LABEL_76;
      v30 = *v29;
      if ( *(__int64 **)(*v29 + 8) != v29 )
        goto LABEL_76;
      *(_QWORD *)v27 = v30;
      *(_QWORD *)(v30 + 8) = v27;
      *((_QWORD *)this + 701) = v29 - 130;
      --*((_DWORD *)this + 1400);
      v34 = 1;
    }
    _InterlockedExchange(
      (volatile __int32 *)this + 1404,
      ((*((_BYTE *)this + 5616) - 1) & 3) != 0 ? *((_DWORD *)this + 1404) - 1 : 0);
    v15 = v39;
    v14 = v36;
LABEL_62:
    a3 += v8;
    if ( a3 >= (char *)v41 || !v14 )
      goto LABEL_82;
    v4 -= v8;
    v13 = v37;
  }
  if ( v18 )
  {
    v8 = v4;
    goto LABEL_62;
  }
  if ( v4 > v13 )
  {
    *((_DWORD *)this + 1401) = 1;
    v8 = v4;
    goto LABEL_26;
  }
  if ( v38 )
  {
    memmove_0(*((void **)this + 695), a3, v4);
    if ( v4 < *((_DWORD *)this + 1392) )
    {
      *(_BYTE *)(v4 + *((_QWORD *)this + 695)) = 0;
      *((_DWORD *)this + 1394) = v4;
    }
  }
  else
  {
    Command = STRA::Copy((FTP_SESSION *)((char *)this + 5528), a3, v4);
    if ( Command < 0 )
      goto LABEL_67;
LABEL_82:
    if ( v15 && *((_DWORD *)this + 1394) )
    {
      **((_BYTE **)this + 695) = 0;
      *((_DWORD *)this + 1394) = 0;
    }
  }
  if ( v35 )
  {
    Command = FTP_CONTROL_CHANNEL::ReadCommand((FTP_SESSION *)((char *)this + 1064));
    if ( Command < 0 )
      goto LABEL_67;
  }
  v8 = v34;
  if ( v34 )
  {
    v35 = 0;
    FTP_COMMAND::Process(*((FTP_COMMAND **)this + 701), &v35);
    if ( v35 )
      FTP_SESSION::OnCommandExecutionCompletion(this, *((struct FTP_COMMAND **)this + 701));
  }
LABEL_68:
  if ( v12 )
  {
    v31 = _InterlockedDecrement((volatile signed __int32 *)v12);
    if ( FTP_SITE_CONFIG::sm_pRefTraceLog )
      WriteRefTraceLog(FTP_SITE_CONFIG::sm_pRefTraceLog, v31);
    if ( !v31 )
    {
      FTP_SITE_CONFIG::~FTP_SITE_CONFIG((FTP_SITE_CONFIG *)v12);
      ALLOC_CACHE_HANDLER::Free((ALLOC_CACHE_HANDLER *)FTP_SITE_CONFIG::sm_pAllocHandler, v12);
    }
  }
  if ( Command < 0 )
  {
    if ( v8 )
    {
      CSpinLock::WriteLock((FTP_SESSION *)((char *)this + 5616));
      v32 = (FTP_SESSION **)*((_QWORD *)this + 699);
      if ( *v32 != (FTP_SESSION *)((char *)this + 5584) )
LABEL_76:
        __fastfail(3u);
      v33 = (FTP_SESSION *)(*((_QWORD *)this + 701) + 1040LL);
      *(_QWORD *)v33 = (char *)this + 5584;
      *((_QWORD *)v33 + 1) = v32;
      *v32 = v33;
      *((_QWORD *)this + 699) = v33;
      *((_QWORD *)this + 701) = 0;
      _InterlockedExchange(
        (volatile __int32 *)this + 1404,
        ((*((_BYTE *)this + 5616) - 1) & 3) != 0 ? *((_DWORD *)this + 1404) - 1 : 0);
    }
    (*(void (__fastcall **)(FTP_SESSION *, _QWORD, _QWORD, const OLECHAR *, int))(*(_QWORD *)this + 32LL))(
      this,
      (unsigned int)Command,
      0,
      &WideCharStr,
      1);
  }
}

```

## disassembly

```asm
0x18003553c  push    rbp
0x18003553e  push    rbx
0x18003553f  push    rsi
0x180035540  push    rdi
0x180035541  push    r12
0x180035543  push    r13
0x180035545  push    r14
0x180035547  push    r15
0x180035549  lea     rbp, [rsp-1Fh]
0x18003554e  sub     rsp, 0E8h
0x180035555  mov     rax, cs:__security_cookie
0x18003555c  xor     rax, rsp
0x18003555f  mov     [rbp+57h+var_50], rax
0x180035563  mov     r14d, r9d
0x180035566  mov     [rsp+120h+var_EC], r9d
0x18003556b  mov     r12, r8
0x18003556e  mov     esi, edx
0x180035570  mov     rbx, rcx
0x180035573  xor     r13d, r13d
0x180035576  mov     [rsp+120h+var_F0], r13d
0x18003557b  mov     r15, [rcx+60h]
0x18003557f  lea     rdi, [r15+0D0h]
0x180035586  mov     rcx, rdi
0x180035589  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18003558f  mov     r8, [r15+0C0h]
0x180035596  lea     eax, [r13+1]
0x18003559a  mov     edx, eax
0x18003559c  lock xadd [r8], edx
0x1800355a1  add     edx, eax
0x1800355a3  mov     rcx, cs:?sm_pRefTraceLog@FTP_SITE_CONFIG@@0PEAU_TRACE_LOG@@EA; _TRACE_LOG * FTP_SITE_CONFIG::sm_pRefTraceLog
0x1800355aa  test    rcx, rcx
0x1800355ad  jz      short loc_1800355B5
0x1800355af  call    cs:__imp_WriteRefTraceLog
0x1800355b5  mov     r15, [r15+0C0h]
0x1800355bc  mov     rcx, rdi
0x1800355bf  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800355c5  test    esi, esi
0x1800355c7  js      loc_180035BE2
0x1800355cd  xor     esi, esi
0x1800355cf  cmp     [rbx+16FCh], esi
0x1800355d5  jz      short loc_180035635
0x1800355d7  mov     [rbx+16FCh], esi
0x1800355dd  mov     rdx, r15; struct FTP_SITE_CONFIG *
0x1800355e0  mov     rcx, rbx; this
0x1800355e3  call    ?SendBanner@FTP_SESSION@@QEAAJPEAVFTP_SITE_CONFIG@@@Z; FTP_SESSION::SendBanner(FTP_SITE_CONFIG *)
0x1800355e8  test    eax, eax
0x1800355ea  js      loc_180035BE2
0x1800355f0  lea     rcx, [rbx+15F0h]
0x1800355f7  call    cs:__imp_?WriteLock@CSpinLock@@QEAAXXZ; CSpinLock::WriteLock(void)
0x1800355fd  mov     edx, [r15+88h]; unsigned int
0x180035604  mov     rcx, rbx; this
0x180035607  call    ?StartTimeoutMonitor@FTP_SESSION@@QEAAXK@Z; FTP_SESSION::StartTimeoutMonitor(ulong)
0x18003560c  mov     edx, [rbx+15F0h]
0x180035612  dec     edx
0x180035614  mov     eax, edx
0x180035616  and     al, 3
0x180035618  neg     al
0x18003561a  sbb     ecx, ecx
0x18003561c  and     ecx, edx
0x18003561e  xchg    ecx, [rbx+15F0h]
0x180035624  lea     rcx, [rbx+428h]; this
0x18003562b  call    ?ReadCommand@FTP_CONTROL_CHANNEL@@QEAAJXZ; FTP_CONTROL_CHANNEL::ReadCommand(void)
0x180035630  jmp     loc_180035BE2
0x180035635  mov     r10d, [r15+41Ch]
0x18003563c  mov     [rsp+120h+var_E4], r10d
0x180035641  lea     r9, [rbx+1598h]
0x180035648  cmp     [r9+30h], esi
0x18003564c  jz      short loc_180035687
0x18003564e  mov     r8d, r14d
0x180035651  mov     rdx, r12
0x180035654  mov     rcx, r9
0x180035657  call    cs:__imp_?Append@STRA@@QEAAJPEBDK@Z; STRA::Append(char const *,ulong)
0x18003565d  mov     esi, eax
0x18003565f  test    eax, eax
0x180035661  js      loc_180035BE2
0x180035667  mov     r14d, [rbx+15C8h]
0x18003566e  mov     r12, [rbx+15B8h]
0x180035675  mov     r9d, 1
0x18003567b  mov     [rsp+120h+var_E0], r9d
0x180035680  mov     r10d, [rsp+120h+var_E4]
0x180035685  jmp     short loc_180035691
0x180035687  mov     [rsp+120h+var_E0], esi
0x18003568b  mov     r9d, 1
0x180035691  mov     r8d, r9d
0x180035694  mov     [rsp+120h+var_E8], r9d
0x180035699  mov     eax, r14d
0x18003569c  add     rax, r12
0x18003569f  mov     [rbp+57h+var_D0], rax
0x1800356a3  xor     edi, edi
0x1800356a5  xor     edx, edx
0x1800356a7  test    r14d, r14d
0x1800356aa  jz      short loc_1800356C7
0x1800356ac  lea     ecx, [rdx+1]
0x1800356af  mov     eax, edx
0x1800356b1  cmp     byte ptr [rax+r12], 0Ah
0x1800356b6  jz      short loc_1800356C1
0x1800356b8  mov     edx, ecx
0x1800356ba  cmp     ecx, r14d
0x1800356bd  jb      short loc_1800356AC
0x1800356bf  jmp     short loc_1800356C7
0x1800356c1  mov     edi, r9d
0x1800356c4  mov     r13d, ecx
0x1800356c7  mov     eax, [rsp+120h+var_EC]
0x1800356cb  test    eax, eax
0x1800356cd  cmovz   edi, r9d
0x1800356d1  mov     [rsp+120h+var_DC], edi
0x1800356d5  neg     eax
0x1800356d7  sbb     ecx, ecx
0x1800356d9  and     r13d, ecx
0x1800356dc  mov     eax, [rbx+15E4h]
0x1800356e2  test    edi, edi
0x1800356e4  jz      short loc_1800356FD
0x1800356e6  test    eax, eax
0x1800356e8  jz      short loc_18003571C
0x1800356ea  mov     dword ptr [rbx+15E4h], 0
0x1800356f4  lea     r13d, [rdx+1]
0x1800356f8  jmp     loc_180035B87
0x1800356fd  test    eax, eax
0x1800356ff  jz      short loc_180035709
0x180035701  mov     r13d, r14d
0x180035704  jmp     loc_180035B87
0x180035709  cmp     r14d, r10d
0x18003570c  jbe     loc_180035C69
0x180035712  mov     [rbx+15E4h], r9d
0x180035719  mov     r13d, r14d
0x18003571c  mov     rcx, cs:?sm_pAllocHandler@FTP_COMMAND@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * FTP_COMMAND::sm_pAllocHandler
0x180035723  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x180035729  mov     rdi, rax
0x18003572c  mov     [rbp+57h+var_B8], rax
0x180035730  xor     esi, esi
0x180035732  test    rax, rax
0x180035735  jz      loc_1800358FC
0x18003573b  lea     rax, ??_7FTP_COMMAND@@6B@; const FTP_COMMAND::`vftable'
0x180035742  mov     [rdi], rax
0x180035745  lea     rcx, [rdi+10h]
0x180035749  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x18003574f  nop
0x180035750  lea     rcx, [rdi+48h]
0x180035754  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18003575a  nop
0x18003575b  lea     rdx, [rdi+0B8h]
0x180035762  lea     rcx, [rdi+80h]
0x180035769  mov     r8d, 80h
0x18003576f  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x180035775  nop
0x180035776  lea     rdx, [rdi+170h]
0x18003577d  lea     rcx, [rdi+138h]
0x180035784  mov     r8d, 80h
0x18003578a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180035790  nop
0x180035791  lea     rcx, [rdi+270h]
0x180035798  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18003579e  nop
0x18003579f  mov     [rdi+328h], rsi
0x1800357a6  mov     [rdi+330h], rsi
0x1800357ad  mov     [rdi+338h], rsi
0x1800357b4  mov     [rdi+340h], rsi
0x1800357bb  mov     [rdi+348h], rsi
0x1800357c2  mov     [rdi+350h], rsi
0x1800357c9  mov     [rdi+358h], rsi
0x1800357d0  mov     [rdi+360h], esi
0x1800357d6  mov     [rdi+370h], rsi
0x1800357dd  mov     [rdi+378h], rsi
0x1800357e4  mov     [rdi+3A0h], rsi
0x1800357eb  mov     [rdi+3A8h], rsi
0x1800357f2  mov     [rdi+3B0h], rsi
0x1800357f9  mov     [rdi+3B8h], esi
0x1800357ff  xorps   xmm0, xmm0
0x180035802  movups  xmmword ptr [rdi+380h], xmm0
0x180035809  movups  xmmword ptr [rdi+390h], xmm0
0x180035810  lea     rax, ??_7DATA_STREAM_ASYNC_CONTEXT@@6B@; const DATA_STREAM_ASYNC_CONTEXT::`vftable'
0x180035817  mov     [rdi+368h], rax
0x18003581e  mov     [rdi+3C0h], rsi
0x180035825  mov     [rdi+3D0h], rsi
0x18003582c  mov     [rdi+3D8h], esi
0x180035832  mov     [rdi+3E0h], rsi
0x180035839  mov     [rdi+3E8h], rsi
0x180035840  mov     [rdi+3F0h], rsi
0x180035847  mov     dword ptr [rdi+3C8h], 53425344h
0x180035851  mov     qword ptr [rdi+3F8h], 0FFFFFFFFFFFFFFFFh
0x18003585c  mov     [rdi+400h], rsi
0x180035863  mov     [rdi+420h], rsi
0x18003586a  mov     [rdi+428h], rsi
0x180035871  mov     [rdi+430h], rsi
0x180035878  mov     [rdi+43Ch], si
0x18003587f  mov     [rdi+444h], rsi
0x180035886  lea     rax, WideCharStr
0x18003588d  mov     [rdi+450h], rax
0x180035894  lea     rcx, [rdi+458h]
0x18003589b  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800358a1  nop
0x1800358a2  mov     [rdi+490h], rsi
0x1800358a9  mov     [rdi+498h], esi
0x1800358af  lea     rcx, [rdi+4A0h]
0x1800358b6  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800358bc  lea     rax, ?AsyncCompletionRoutine@FTP_COMMAND@@SAXPEAVFTP_ASYNC_CONTEXT@@@Z; FTP_COMMAND::AsyncCompletionRoutine(FTP_ASYNC_CONTEXT *)
0x1800358c3  mov     [rdi+370h], rax
0x1800358ca  mov     [rdi+3A8h], rsi
0x1800358d1  mov     [rdi+378h], rdi
0x1800358d8  mov     [rdi+3B0h], rsi
0x1800358df  mov     [rdi+410h], rsi
0x1800358e6  mov     [rdi+418h], rsi
0x1800358ed  mov     [rdi+438h], esi
0x1800358f3  mov     dword ptr [rdi+8], 4D435446h
0x1800358fa  jmp     short loc_1800358FF
0x1800358fc  mov     rdi, rsi
0x1800358ff  test    rdi, rdi
0x180035902  jz      loc_180035C5F
0x180035908  cmp     [rbx+15E8h], rsi
0x18003590f  jz      short loc_180035952
0x180035911  cmp     r13d, 6
0x180035915  jnz     short loc_180035952
0x180035917  mov     r8d, r13d; Size
0x18003591a  lea     rdx, aAbor_0; "ABOR\r\n"
0x180035921  mov     rcx, r12; Buf1
0x180035924  call    cs:__imp__memicmp
0x18003592a  test    eax, eax
0x18003592c  jnz     short loc_180035952
0x18003592e  lea     rcx, [rbx+818h]; this
0x180035935  mov     dword ptr [rsp+120h+var_100], 1; int
0x18003593d  lea     r9, aDataChannelWas; "Data channel was closed by ABOR command"...
0x180035944  mov     edx, 800704D4h; int
0x180035949  lea     r8d, [r13+0Eh]; unsigned int
0x18003594d  call    ?InitiateChannelShutdown@FTP_DATA_CHANNEL@@QEAAXJKPEBGH@Z; FTP_DATA_CHANNEL::InitiateChannelShutdown(long,ulong,ushort const *,int)
0x180035952  mov     [rsp+120h+var_100], r15; struct FTP_SITE_CONFIG *
0x180035957  mov     r9d, r13d; unsigned int
0x18003595a  mov     r8, r12; unsigned __int8 *
0x18003595d  mov     rdx, rbx; struct FTP_SESSION *
0x180035960  mov     rcx, rdi; this
0x180035963  call    ?Initialize@FTP_COMMAND@@QEAAJPEAVFTP_SESSION@@PEAEKPEAVFTP_SITE_CONFIG@@@Z; FTP_COMMAND::Initialize(FTP_SESSION *,uchar *,ulong,FTP_SITE_CONFIG *)
0x180035968  mov     esi, eax
0x18003596a  test    eax, eax
0x18003596c  js      loc_180035BCA
0x180035972  lea     rdx, aAuth; "AUTH"
0x180035979  mov     rcx, [rdi+30h]; String1
0x18003597d  call    cs:__imp__stricmp
0x180035983  test    eax, eax
0x180035985  jnz     short loc_1800359AE
0x180035987  mov     eax, r13d
0x18003598a  add     rax, r12
0x18003598d  mov     rcx, [rbp+57h+var_D0]
0x180035991  cmp     rax, rcx
0x180035994  jnb     short loc_1800359AE
0x180035996  mov     [rsp+120h+var_E8], 0
0x18003599e  cmp     byte ptr [rcx-1], 0Ah
0x1800359a2  jz      short loc_1800359AE
0x1800359a4  mov     dword ptr [rbx+15E4h], 1
0x1800359ae  lea     rcx, [rbx+15F0h]
0x1800359b5  call    cs:__imp_?WriteLock@CSpinLock@@QEAAXXZ; CSpinLock::WriteLock(void)
0x1800359bb  cmp     dword ptr [rbx+15E0h], 14h
0x1800359c2  jnb     loc_180035BAD
0x1800359c8  mov     rcx, rbx; this
0x1800359cb  call    ?StopTimeoutMonitor@FTP_SESSION@@QEAAXXZ; FTP_SESSION::StopTimeoutMonitor(void)
0x1800359d0  inc     dword ptr [rbx+15E0h]
0x1800359d6  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x1800359dd  mov     rax, [rcx]
0x1800359e0  mov     rax, [rax+20h]
0x1800359e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359e9  cmp     dword ptr [rax+8], 0
0x1800359ed  jz      loc_180035AEC
0x1800359f3  test    byte ptr [rax+28h], 2
0x1800359f7  jz      loc_180035AEC
0x1800359fd  cmp     dword ptr [rax+2Ch], 5
0x180035a01  jb      loc_180035AEC
0x180035a07  lea     rdx, aPass; "PASS"
0x180035a0e  mov     rcx, [rdi+30h]; String1
0x180035a12  call    cs:__imp__stricmp
0x180035a18  test    eax, eax
0x180035a1a  lea     rax, asc_180053DFC; "***"
0x180035a21  jz      short loc_180035A2A
0x180035a23  mov     rax, [rdi+0A0h]
0x180035a2a  mov     [rsp+120h+var_D8], rax
0x180035a2f  mov     rax, [rdi+30h]
0x180035a33  mov     [rbp+57h+var_C8], rax
0x180035a37  mov     rcx, cs:?g_pFtpServer@@3PEAVFTP_SERVER@@EA; FTP_SERVER * g_pFtpServer
0x180035a3e  mov     rax, [rcx]
0x180035a41  mov     rax, [rax+20h]
0x180035a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035a4a  mov     [rbp+57h+var_C0], rax
0x180035a4e  xor     edx, edx; Val
0x180035a50  lea     r8d, [rdx+5Eh]; Size
0x180035a54  lea     rcx, [rbp+57h+var_AE]; void *
0x180035a58  call    memset_0
0x180035a5d  mov     [rbp+57h+var_84], 1A0000h
0x180035a64  mov     eax, 60h ; '`'
0x180035a69  mov     [rbp+57h+var_B0], ax
0x180035a6d  mov     eax, 1
0x180035a72  mov     [rbp+57h+var_AA], ax
0x180035a76  mov     [rbp+57h+var_AC], 4
0x180035a7a  lea     rax, ?AreaGuid@?1??GetAreaGuid@FtpCommandsEvents@@SAPEBU_GUID@@XZ@4U3@B; _GUID const `FtpCommandsEvents::GetAreaGuid(void)'::`2'::AreaGuid
0x180035a81  mov     [rbp+57h+var_98], rax
0x180035a85  lea     rcx, [rbx+170h]
0x180035a8c  mov     [rbp+57h+var_80], rcx
0x180035a90  mov     [rbp+57h+var_78], 10h
0x180035a97  mov     rcx, [rbp+57h+var_C8]
0x180035a9b  mov     [rbp+57h+var_70], rcx
0x180035a9f  test    rcx, rcx
0x180035aa2  jnz     short loc_180035AA8
0x180035aa4  xor     eax, eax
0x180035aa6  jmp     short loc_180035AB7
  ... truncated ...
```
