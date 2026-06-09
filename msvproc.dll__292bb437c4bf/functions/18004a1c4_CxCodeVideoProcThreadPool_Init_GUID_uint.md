# CxCodeVideoProcThreadPool::Init(_GUID,uint)

- ea: `0x18004a1c4`
- end: `0x18004a81a`
- name: `?Init@CxCodeVideoProcThreadPool@@QEAAJU_GUID@@I@Z`
- size: `1622`
- prototype: `__int64 __fastcall(CxCodeVideoProcThreadPool *__hidden this, struct _GUID *__struct_ptr, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800244c4`

## callees

- `0x18000a954`
- `0x18000c9d0`
- `0x18000ec20`
- `0x18000ecf0`
- `0x18001f1ac`
- `0x180025a64`
- `0x18003639c`
- `0x18004a1c4`
- `0x180053c48`
- `0x180054ee4`
- `0x18005a268`
- `0x1800669a4`
- `0x180066a14`
- `0x1800a422c`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a48b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a48b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a4ab`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18004a31a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18004a31a`
- `MFPlat!MFUnlockWorkQueue` at `0x18004a38d`
- `MFPlat!MFUnlockWorkQueue` at `0x18004a38d`
- `MFPlat!MFAllocateWorkQueue` at `0x18004a378`
- `MFPlat!MFAllocateWorkQueue` at `0x18004a378`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a25f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a3db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a4cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a591`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a698`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a735`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a25f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a3db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a4cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a591`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a698`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18004a735`

## string_xrefs

- `0x18004a204`: `CxCodeVideoProcThreadPool::Init`
- `0x18004a433`: `CxCodeVideoProcThreadPool::Init`
- `0x18004a527`: `CxCodeVideoProcThreadPool::Init`
- `0x18004a5e9`: `CxCodeVideoProcThreadPool::Init`
- `0x18004a6fa`: `CxCodeVideoProcThreadPool::Init`
- `0x18004a78c`: `CxCodeVideoProcThreadPool::Init`
- `0x18004a235`: `XVP is already initialized; Cannot be initialized twice`

## pseudocode

```c
__int64 __fastcall CxCodeVideoProcThreadPool::Init(CxCodeVideoProcThreadPool *this, struct _GUID *a2, DWORD a3)
{
  signed int v5; // ebx
  __int64 *v6; // rcx
  CallStackTracing *v7; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  DWORD *v9; // rdi
  DWORD dwNumberOfProcessors; // eax
  unsigned int MaxNumThreads; // eax
  void *v12; // rax
  CallStackTracing *v13; // rax
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  DWORD i; // r14d
  signed int LastError; // eax
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  void *v21; // rax
  CallStackTracing *v22; // rax
  struct CallStackContext *v23; // rax
  DWORD j; // r14d
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // edx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  CallStackTracing *v30; // rax
  struct CallStackContext *v31; // rax
  struct _GUID v33; // [rsp+30h] [rbp-40h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-30h] BYREF
  DWORD pdwWorkQueue; // [rsp+B0h] [rbp+40h] BYREF

  pdwWorkQueue = a3;
  if ( (Microsoft_Windows_MediaFoundation_MSVProcEnableBits & 2) != 0 )
    McTemplateU0pq_EventWriteTransfer(this, MSVProc_MFT_ThreadpoolInit_Start, this, *((unsigned int *)this + 10));
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&pdwWorkQueue, "CxCodeVideoProcThreadPool::Init", 132);
  v5 = 0;
  *(struct _GUID *)((char *)this + 24) = *a2;
  if ( *((_DWORD *)this + 5)
    && (v5 = XvpOriginateError<56>(
               "CxCodeVideoProcThreadPool::Init",
               2147549183LL,
               L"XVP is already initialized; Cannot be initialized twice"),
        v5 < 0) )
  {
    v6 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v7 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
      CallStackTracing::s_wpInstance = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_180153440;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v5 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "CxCodeVideoProcThreadPool::Init", 141, v5);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids, this, v5);
    v9 = (DWORD *)((char *)this + 16);
  }
  else
  {
    *((_DWORD *)this + 5) = 1;
    memset(&SystemInfo, 0, sizeof(SystemInfo));
    v9 = (DWORD *)((char *)this + 16);
    GetSystemInfo(&SystemInfo);
    dwNumberOfProcessors = 16;
    if ( SystemInfo.dwNumberOfProcessors < 0x10 )
      dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
    *v9 = dwNumberOfProcessors;
    if ( (unsigned __int8)byte_180153DE0 >= 0x20u )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 42),
        11,
        WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids,
        this,
        dwNumberOfProcessors);
    MaxNumThreads = xvpTestTools::CxCodeVideoProcDump::GetMaxNumThreads();
    if ( MaxNumThreads )
    {
      if ( *v9 < MaxNumThreads )
        MaxNumThreads = *v9;
      *v9 = MaxNumThreads;
    }
    pdwWorkQueue = 0;
    if ( MFAllocateWorkQueue(&pdwWorkQueue) >= 0 )
      MFUnlockWorkQueue(pdwWorkQueue);
    else
      *v9 = 1;
    if ( *v9 != 1 )
    {
      v12 = operator new[](saturated_mul(*v9, 8u));
      *((_QWORD *)this + 1) = v12;
      if ( v12 )
      {
        memset_0(v12, 0, 8LL * *v9);
        for ( i = 0; i < *v9; ++i )
        {
          *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * i) = CreateEventW(0, 0, 0, 0);
          if ( !*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * i) )
          {
            LastError = GetLastError();
            v5 = LastError;
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
            v6 = (__int64 *)CallStackTracing::s_wpInstance;
            if ( !CallStackTracing::s_wpInstance )
            {
              v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
              CallStackTracing::s_wpInstance = v18;
              if ( v18
                && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
              {
                v6 = (__int64 *)CallStackTracing::s_wpInstance;
              }
              else
              {
                v6 = &qword_180153440;
                CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
              }
            }
            if ( *((_BYTE *)v6 + 8) )
            {
              v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
              if ( v5 < 0 && *((_DWORD *)v19 + 499) != v5 )
                CallStackContext::TraceFailure(v19, "CxCodeVideoProcThreadPool::Init", 184, v5);
            }
            if ( g_wppLevels )
            {
              v20 = 13;
LABEL_94:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v20,
                WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids,
                this,
                v5);
            }
            goto LABEL_95;
          }
        }
        v21 = operator new[](saturated_mul(*v9, 8u));
        *(_QWORD *)this = v21;
        if ( v21 )
        {
          memset_0(v21, 0, 8LL * *v9);
          for ( j = 0; j < *v9; ++j )
          {
            v25 = *(_QWORD *)this;
            v26 = *((_QWORD *)this + 1);
            v33 = *(struct _GUID *)((char *)this + 24);
            v5 = CxCodeVideoProcThread::CreateInstance(
                   *(void **)(v26 + 8LL * j),
                   &v33,
                   (struct CxCodeVideoProcThread **)(v25 + 8LL * j));
            if ( v5 < 0 )
            {
              v6 = (__int64 *)CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                CallStackTracing::s_wpInstance = v30;
                if ( v30
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
                {
                  v6 = (__int64 *)CallStackTracing::s_wpInstance;
                }
                else
                {
                  v6 = &qword_180153440;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                }
              }
              if ( *((_BYTE *)v6 + 8) )
              {
                v31 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
                if ( *((_DWORD *)v31 + 499) != v5 )
                  CallStackContext::TraceFailure(v31, "CxCodeVideoProcThreadPool::Init", 194, v5);
              }
              if ( g_wppLevels )
              {
                v20 = 15;
                goto LABEL_94;
              }
              break;
            }
            v6 = *(__int64 **)(*(_QWORD *)this + 8LL * j);
            *((_DWORD *)v6 + 16) = j;
            v27 = *((_DWORD *)this + 10);
            if ( v27 != 5 )
            {
              v5 = CxCodeVideoProcThread::SetWorkQueueEx(
                     *(CxCodeVideoProcThread **)(*(_QWORD *)this + 8LL * j),
                     v27,
                     *((_DWORD *)this + 11));
              if ( v5 < 0 )
              {
                v6 = (__int64 *)CallStackTracing::s_wpInstance;
                if ( !CallStackTracing::s_wpInstance )
                {
                  v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
                  CallStackTracing::s_wpInstance = v28;
                  if ( v28
                    && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
                  {
                    v6 = (__int64 *)CallStackTracing::s_wpInstance;
                  }
                  else
                  {
                    v6 = &qword_180153440;
                    CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
                  }
                }
                if ( *((_BYTE *)v6 + 8) )
                {
                  v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
                  if ( *((_DWORD *)v29 + 499) != v5 )
                    CallStackContext::TraceFailure(v29, "CxCodeVideoProcThreadPool::Init", 202, v5);
                }
                if ( g_wppLevels )
                {
                  v20 = 16;
                  goto LABEL_94;
                }
                break;
              }
            }
          }
        }
        else
        {
          v6 = (__int64 *)CallStackTracing::s_wpInstance;
          v5 = -2147024882;
          if ( !CallStackTracing::s_wpInstance )
          {
            v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
            CallStackTracing::s_wpInstance = v22;
            if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
            {
              v6 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v6 = &qword_180153440;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
            }
          }
          if ( *((_BYTE *)v6 + 8) )
          {
            v23 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
            if ( *((_DWORD *)v23 + 499) != -2147024882 )
              CallStackContext::TraceFailure(v23, "CxCodeVideoProcThreadPool::Init", 190, -2147024882);
          }
          if ( g_wppLevels )
          {
            v15 = 14;
            goto LABEL_39;
          }
        }
      }
      else
      {
        v6 = (__int64 *)CallStackTracing::s_wpInstance;
        v5 = -2147024882;
        if ( !CallStackTracing::s_wpInstance )
        {
          v13 = (CallStackTracing *)MFGetCallStackTracingWeakReference();
          CallStackTracing::s_wpInstance = v13;
          if ( v13 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
          {
            v6 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v6 = &qword_180153440;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_180153440;
          }
        }
        if ( *((_BYTE *)v6 + 8) )
        {
          v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
          if ( *((_DWORD *)v14 + 499) != -2147024882 )
            CallStackContext::TraceFailure(v14, "CxCodeVideoProcThreadPool::Init", 179, -2147024882);
        }
        if ( g_wppLevels )
        {
          v15 = 12;
LABEL_39:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v15,
            WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids,
            this,
            -2147024882);
        }
      }
    }
  }
LABEL_95:
  *((_DWORD *)this + 5) = (v5 != 0) + 2;
  if ( (Microsoft_Windows_MediaFoundation_MSVProcEnableBits & 2) != 0 )
    McTemplateU0pqq_EventWriteTransfer((_DWORD)v6, (unsigned int)MSVProc_MFT_ThreadpoolInit_Stop, (_DWORD)this, *v9, v5);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&pdwWorkQueue);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18004a1c4  mov     [rsp-28h+arg_0], rbx
0x18004a1c9  mov     [rsp-28h+arg_8], rsi
0x18004a1ce  mov     [rsp-28h+pdwWorkQueue], r8d
0x18004a1d3  push    rbp
0x18004a1d4  push    rdi
0x18004a1d5  push    r12
0x18004a1d7  push    r13
0x18004a1d9  push    r14
0x18004a1db  mov     rbp, rsp
0x18004a1de  sub     rsp, 70h
0x18004a1e2  test    byte ptr cs:Microsoft_Windows_MediaFoundation_MSVProcEnableBits, 2
0x18004a1e9  mov     rdi, rdx
0x18004a1ec  mov     rsi, rcx
0x18004a1ef  jz      short loc_18004A204
0x18004a1f1  mov     r9d, [rcx+28h]
0x18004a1f5  lea     rdx, MSVProc_MFT_ThreadpoolInit_Start
0x18004a1fc  mov     r8, rcx
0x18004a1ff  call    McTemplateU0pq_EventWriteTransfer
0x18004a204  lea     r14, aCxcodevideopro_32; "CxCodeVideoProcThreadPool::Init"
0x18004a20b  mov     r8d, 84h; int
0x18004a211  mov     rdx, r14; char *
0x18004a214  lea     rcx, [rbp+pdwWorkQueue]; this
0x18004a218  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18004a21d  movaps  xmm0, xmmword ptr [rdi]
0x18004a220  xor     r12d, r12d
0x18004a223  mov     ebx, r12d
0x18004a226  movdqu  xmmword ptr [rsi+18h], xmm0
0x18004a22b  cmp     [rsi+14h], r12d
0x18004a22f  jz      loc_18004A2FC
0x18004a235  lea     r8, aXvpIsAlreadyIn; "XVP is already initialized; Cannot be i"...
0x18004a23c  mov     edx, 8000FFFFh
0x18004a241  mov     rcx, r14
0x18004a244  call    ??$XvpOriginateError@$0DI@@@YAJQEADJAEAY0DI@$$CBG@Z; XvpOriginateError<56>(char * const,long,ushort const (&)[56])
0x18004a249  mov     ebx, eax
0x18004a24b  test    eax, eax
0x18004a24d  jns     loc_18004A2FC
0x18004a253  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a25a  test    rcx, rcx
0x18004a25d  jnz     short loc_18004A2A0
0x18004a25f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a265  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a26c  mov     rcx, rax
0x18004a26f  test    rax, rax
0x18004a272  jz      short loc_18004A292
0x18004a274  mov     rax, [rax]
0x18004a277  mov     edx, 7F0h
0x18004a27c  mov     rax, [rax+8]
0x18004a280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a285  test    eax, eax
0x18004a287  jz      short loc_18004A292
0x18004a289  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a290  jmp     short loc_18004A2A0
0x18004a292  lea     rcx, qword_180153440; this
0x18004a299  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a2a0  cmp     [rcx+8], r12b
0x18004a2a4  jz      short loc_18004A2C7
0x18004a2a6  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a2ab  cmp     [rax+7CCh], ebx
0x18004a2b1  jz      short loc_18004A2C7
0x18004a2b3  mov     r9d, ebx; int
0x18004a2b6  mov     r8d, 8Dh; int
0x18004a2bc  mov     rdx, r14; char *
0x18004a2bf  mov     rcx, rax; this
0x18004a2c2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a2c7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004a2ce  jb      short loc_18004A2F3
0x18004a2d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a2d7  lea     r8, WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids
0x18004a2de  mov     edx, 0Ah
0x18004a2e3  mov     [rsp+70h+var_50], ebx
0x18004a2e7  mov     r9, rsi
0x18004a2ea  mov     rcx, [rcx+10h]
0x18004a2ee  call    WPP_SF_qD
0x18004a2f3  lea     rdi, [rsi+10h]
0x18004a2f7  jmp     loc_18004A7C9
0x18004a2fc  xorps   xmm0, xmm0
0x18004a2ff  mov     dword ptr [rsi+14h], 1
0x18004a306  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x18004a30a  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x18004a30e  lea     rdi, [rsi+10h]
0x18004a312  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x18004a316  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x18004a31a  call    cs:__imp_GetSystemInfo
0x18004a320  mov     eax, 10h
0x18004a325  cmp     [rbp+SystemInfo.dwNumberOfProcessors], eax
0x18004a328  cmovb   eax, [rbp+SystemInfo.dwNumberOfProcessors]
0x18004a32c  mov     [rdi], eax
0x18004a32e  cmp     cs:byte_180153DE0, 20h ; ' '
0x18004a335  lea     r13, WPP_31017d59e5fa36e4c5717ad5ebbdb595_Traceguids
0x18004a33c  jb      short loc_18004A360
0x18004a33e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a345  mov     edx, 0Bh
0x18004a34a  mov     r9, rsi
0x18004a34d  mov     [rsp+70h+var_50], eax
0x18004a351  mov     r8, r13
0x18004a354  mov     rcx, [rcx+150h]
0x18004a35b  call    WPP_SF_qD
0x18004a360  call    ?GetMaxNumThreads@CxCodeVideoProcDump@xvpTestTools@@SAKXZ; xvpTestTools::CxCodeVideoProcDump::GetMaxNumThreads(void)
0x18004a365  test    eax, eax
0x18004a367  jz      short loc_18004A370
0x18004a369  cmp     [rdi], eax
0x18004a36b  cmovb   eax, [rdi]
0x18004a36e  mov     [rdi], eax
0x18004a370  lea     rcx, [rbp+pdwWorkQueue]; pdwWorkQueue
0x18004a374  mov     [rbp+pdwWorkQueue], r12d
0x18004a378  call    cs:__imp_MFAllocateWorkQueue
0x18004a37e  test    eax, eax
0x18004a380  jns     short loc_18004A38A
0x18004a382  mov     dword ptr [rdi], 1
0x18004a388  jmp     short loc_18004A393
0x18004a38a  mov     ecx, [rbp+pdwWorkQueue]; dwWorkQueue
0x18004a38d  call    cs:__imp_MFUnlockWorkQueue
0x18004a393  cmp     dword ptr [rdi], 1
0x18004a396  jz      loc_18004A7C9
0x18004a39c  mov     ecx, [rdi]
0x18004a39e  mov     eax, 8
0x18004a3a3  mul     rcx
0x18004a3a6  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004a3ad  cmovb   rax, rcx
0x18004a3b1  mov     rcx, rax; unsigned __int64
0x18004a3b4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004a3b9  mov     [rsi+8], rax
0x18004a3bd  test    rax, rax
0x18004a3c0  jnz     loc_18004A464
0x18004a3c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a3cd  mov     r14d, 8007000Eh
0x18004a3d3  mov     ebx, r14d
0x18004a3d6  test    rcx, rcx
0x18004a3d9  jnz     short loc_18004A41C
0x18004a3db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a3e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a3e8  mov     rcx, rax
0x18004a3eb  test    rax, rax
0x18004a3ee  jz      short loc_18004A40E
0x18004a3f0  mov     rax, [rax]
0x18004a3f3  mov     edx, 7F0h
0x18004a3f8  mov     rax, [rax+8]
0x18004a3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a401  test    eax, eax
0x18004a403  jz      short loc_18004A40E
0x18004a405  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a40c  jmp     short loc_18004A41C
0x18004a40e  lea     rcx, qword_180153440; this
0x18004a415  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a41c  cmp     [rcx+8], r12b
0x18004a420  jz      short loc_18004A448
0x18004a422  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a427  cmp     [rax+7CCh], r14d
0x18004a42e  jz      short loc_18004A448
0x18004a430  mov     r9d, r14d; int
0x18004a433  lea     rdx, aCxcodevideopro_32; "CxCodeVideoProcThreadPool::Init"
0x18004a43a  mov     r8d, 0B3h; int
0x18004a440  mov     rcx, rax; this
0x18004a443  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a448  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004a44f  jb      loc_18004A7C9
0x18004a455  mov     edx, 0Ch
0x18004a45a  mov     [rsp+70h+var_50], r14d
0x18004a45f  jmp     loc_18004A7B3
0x18004a464  mov     r8d, [rdi]
0x18004a467  xor     edx, edx; Val
0x18004a469  shl     r8, 3; Size
0x18004a46d  mov     rcx, rax; void *
0x18004a470  call    memset_0
0x18004a475  mov     r14d, r12d
0x18004a478  cmp     r14d, [rdi]
0x18004a47b  jnb     loc_18004A553
0x18004a481  xor     r9d, r9d; lpName
0x18004a484  xor     r8d, r8d; bInitialState
0x18004a487  xor     edx, edx; bManualReset
0x18004a489  xor     ecx, ecx; lpEventAttributes
0x18004a48b  call    cs:__imp_CreateEventW
0x18004a491  mov     rcx, [rsi+8]
0x18004a495  mov     edx, r14d
0x18004a498  mov     [rcx+rdx*8], rax
0x18004a49c  mov     rax, [rsi+8]
0x18004a4a0  cmp     [rax+rdx*8], r12
0x18004a4a4  jz      short loc_18004A4AB
0x18004a4a6  inc     r14d
0x18004a4a9  jmp     short loc_18004A478
0x18004a4ab  call    cs:__imp_GetLastError
0x18004a4b1  mov     ebx, eax
0x18004a4b3  test    eax, eax
0x18004a4b5  jle     short loc_18004A4C0
0x18004a4b7  movzx   ebx, ax
0x18004a4ba  or      ebx, 80070000h
0x18004a4c0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a4c7  test    rcx, rcx
0x18004a4ca  jnz     short loc_18004A50D
0x18004a4cc  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a4d2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a4d9  mov     rcx, rax
0x18004a4dc  test    rax, rax
0x18004a4df  jz      short loc_18004A4FF
0x18004a4e1  mov     rax, [rax]
0x18004a4e4  mov     edx, 7F0h
0x18004a4e9  mov     rax, [rax+8]
0x18004a4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a4f2  test    eax, eax
0x18004a4f4  jz      short loc_18004A4FF
0x18004a4f6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a4fd  jmp     short loc_18004A50D
0x18004a4ff  lea     rcx, qword_180153440; this
0x18004a506  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a50d  cmp     [rcx+8], r12b
0x18004a511  jz      short loc_18004A53C
0x18004a513  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a518  test    ebx, ebx
0x18004a51a  jns     short loc_18004A53C
0x18004a51c  cmp     [rax+7CCh], ebx
0x18004a522  jz      short loc_18004A53C
0x18004a524  mov     r9d, ebx; int
0x18004a527  lea     rdx, aCxcodevideopro_32; "CxCodeVideoProcThreadPool::Init"
0x18004a52e  mov     r8d, 0B8h; int
0x18004a534  mov     rcx, rax; this
0x18004a537  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a53c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004a543  jb      loc_18004A7C9
0x18004a549  mov     edx, 0Dh
0x18004a54e  jmp     loc_18004A7AF
0x18004a553  mov     ecx, [rdi]
0x18004a555  mov     eax, 8
0x18004a55a  mul     rcx
0x18004a55d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004a564  cmovb   rax, rcx
0x18004a568  mov     rcx, rax; unsigned __int64
0x18004a56b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004a570  mov     [rsi], rax
0x18004a573  test    rax, rax
0x18004a576  jnz     loc_18004A615
0x18004a57c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a583  mov     r14d, 8007000Eh
0x18004a589  mov     ebx, r14d
0x18004a58c  test    rcx, rcx
0x18004a58f  jnz     short loc_18004A5D2
0x18004a591  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004a597  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a59e  mov     rcx, rax
0x18004a5a1  test    rax, rax
0x18004a5a4  jz      short loc_18004A5C4
0x18004a5a6  mov     rax, [rax]
0x18004a5a9  mov     edx, 7F0h
0x18004a5ae  mov     rax, [rax+8]
0x18004a5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a5b7  test    eax, eax
0x18004a5b9  jz      short loc_18004A5C4
0x18004a5bb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a5c2  jmp     short loc_18004A5D2
0x18004a5c4  lea     rcx, qword_180153440; this
0x18004a5cb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a5d2  cmp     [rcx+8], r12b
0x18004a5d6  jz      short loc_18004A5FE
0x18004a5d8  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18004a5dd  cmp     [rax+7CCh], r14d
0x18004a5e4  jz      short loc_18004A5FE
0x18004a5e6  mov     r9d, r14d; int
0x18004a5e9  lea     rdx, aCxcodevideopro_32; "CxCodeVideoProcThreadPool::Init"
0x18004a5f0  mov     r8d, 0BEh; int
0x18004a5f6  mov     rcx, rax; this
0x18004a5f9  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004a5fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004a605  jb      loc_18004A7C9
0x18004a60b  mov     edx, 0Eh
0x18004a610  jmp     loc_18004A45A
0x18004a615  mov     r8d, [rdi]
0x18004a618  xor     edx, edx; Val
0x18004a61a  shl     r8, 3; Size
0x18004a61e  mov     rcx, rax; void *
0x18004a621  call    memset_0
0x18004a626  mov     r14d, r12d
0x18004a629  cmp     r14d, [rdi]
0x18004a62c  jnb     loc_18004A7C9
0x18004a632  mov     rax, [rsi]
0x18004a635  lea     rdx, [rbp+var_40]; struct _GUID
0x18004a639  mov     rcx, [rsi+8]
0x18004a63d  movups  xmm0, xmmword ptr [rsi+18h]
0x18004a641  mov     r12d, r14d
0x18004a644  movdqu  xmmword ptr [rbp+var_40.Data1], xmm0
0x18004a649  mov     rcx, [rcx+r12*8]; void *
0x18004a64d  lea     r8, [rax+r12*8]; struct CxCodeVideoProcThread **
0x18004a651  call    ?CreateInstance@CxCodeVideoProcThread@@SAJPEAXU_GUID@@PEAPEAV1@@Z; CxCodeVideoProcThread::CreateInstance(void *,_GUID,CxCodeVideoProcThread * *)
0x18004a656  mov     ebx, eax
0x18004a658  test    eax, eax
0x18004a65a  js      loc_18004A726
0x18004a660  mov     rax, [rsi]
0x18004a663  mov     rcx, [rax+r12*8]
0x18004a667  mov     [rcx+40h], r14d
0x18004a66b  mov     edx, [rsi+28h]; unsigned int
0x18004a66e  cmp     edx, 5
0x18004a671  jz      short loc_18004A6CB
0x18004a673  mov     rcx, [rsi]
0x18004a676  mov     r8d, [rsi+2Ch]; int
0x18004a67a  mov     rcx, [rcx+r12*8]; this
0x18004a67e  call    ?SetWorkQueueEx@CxCodeVideoProcThread@@QEAAJKJ@Z; CxCodeVideoProcThread::SetWorkQueueEx(ulong,long)
0x18004a683  xor     r12d, r12d
0x18004a686  mov     ebx, eax
0x18004a688  test    eax, eax
0x18004a68a  jns     short loc_18004A6CE
0x18004a68c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004a693  test    rcx, rcx
  ... truncated ...
```
