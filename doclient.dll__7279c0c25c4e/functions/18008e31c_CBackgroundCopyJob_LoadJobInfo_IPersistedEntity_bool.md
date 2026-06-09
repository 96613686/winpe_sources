# CBackgroundCopyJob::_LoadJobInfo(IPersistedEntity &,bool *)

- ea: `0x18008e31c`
- end: `0x18008eb3c`
- name: `?_LoadJobInfo@CBackgroundCopyJob@@AEAAJAEAVIPersistedEntity@@PEA_N@Z`
- size: `2080`
- prototype: `__int64 __fastcall(CBackgroundCopyJob *__hidden this, struct IPersistedEntity *, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting`

## callers

- `0x180088104`

## callees

- `0x180008d14`
- `0x18000933c`
- `0x18000c4b0`
- `0x180027090`
- `0x18008e31c`
- `0x18008f628`
- `0x18008f728`
- `0x1800934d4`
- `0x180094c40`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800f82f0`
- `0x1800f8314`
- `0x180108e50`
- `0x180109290`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18008e8ad`
- `api-ms-win-core-sysinfo-l1-2-0!GetSystemTimePreciseAsFileTime` at `0x18008e8ad`

## string_xrefs

- `0x18008e3e4`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008e439`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008e48e`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008e4e8`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008e572`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008e5bf`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008e625`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008e715`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008e750`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008ea76`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008eaa3`: `C:\__w\1\s\src\DeliveryOptimization\DeliveryOptimization\BackgroundCopyJob.cpp`
- `0x18008e395`: `CBackgroundCopyJob::_LoadJobInfo`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CBackgroundCopyJob::_LoadJobInfo(CBackgroundCopyJob *this, struct IPersistedEntity *a2, bool *a3)
{
  bool v6; // al
  const char *v8; // r15
  __int64 v9; // r14
  unsigned int v10; // esi
  int DownloadProperties; // eax
  unsigned int v12; // esi
  int v13; // eax
  unsigned int v14; // esi
  int v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  unsigned int v18; // esi
  unsigned int v19; // ecx
  int v20; // eax
  int v21; // eax
  _BYTE *v22; // r8
  _BYTE *v23; // rdx
  size_t v24; // r8
  unsigned __int64 v25; // rcx
  __int128 *v26; // rax
  _BYTE *v27; // r8
  _BYTE *v28; // rdx
  size_t v29; // r8
  bool v30; // al
  void *v31; // rcx
  int NewCv; // eax
  int SavedFiles; // eax
  unsigned int v34; // ebx
  int v35; // [rsp+20h] [rbp-168h]
  int v36; // [rsp+20h] [rbp-168h]
  __int64 v37; // [rsp+40h] [rbp-148h] BYREF
  unsigned int v38; // [rsp+48h] [rbp-140h] BYREF
  TraceLoggingCorrelationVector *v39; // [rsp+50h] [rbp-138h] BYREF
  __int64 v40; // [rsp+58h] [rbp-130h] BYREF
  char *v41[2]; // [rsp+60h] [rbp-128h] BYREF
  void *Src[2]; // [rsp+70h] [rbp-118h] BYREF
  __int64 v43; // [rsp+80h] [rbp-108h]
  __int128 v44; // [rsp+88h] [rbp-100h] BYREF
  __int64 v45; // [rsp+98h] [rbp-F0h]
  __int64 v46; // [rsp+A0h] [rbp-E8h]
  char v47[144]; // [rsp+B0h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+188h] [rbp+0h]

  v6 = (*(int (__fastcall **)(struct IPersistedEntity *, _QWORD))(*(_QWORD *)a2 + 128LL))(a2, 0) >= 0;
  *a3 = v6;
  if ( !v6 )
    return 0;
  v8 = (const char *)(*(__int64 (__fastcall **)(struct IPersistedEntity *))(*(_QWORD *)a2 + 152LL))(a2);
  v9 = 4;
  LogMessage(4u, "CBackgroundCopyJob::_LoadJobInfo", 0x59Bu, "Job %s, Loading", v8);
  *(_OWORD *)v41 = 0;
  (*(void (__fastcall **)(struct IPersistedEntity *, char **, _QWORD))(*(_QWORD *)a2 + 8LL))(a2, v41, 0);
  v10 = (unsigned int)v41[1];
  if ( SLODWORD(v41[1]) < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59E,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)LODWORD(v41[1]),
      v35);
    if ( SLODWORD(v41[1]) >= 0 )
      (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v41[0] + 136LL))(v41[0], 0);
    return v10;
  }
  DownloadProperties = CBackgroundCopyJob::_LoadDownloadProperties(this, a2, 0);
  v12 = DownloadProperties;
  if ( DownloadProperties < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A1,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)(unsigned int)DownloadProperties,
      v35);
    if ( SLODWORD(v41[1]) >= 0 )
      (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v41[0] + 136LL))(v41[0], 0);
    return v12;
  }
  v13 = CBackgroundCopyJob::_LoadDownloadProperties(this, a2, 1);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A4,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)(unsigned int)v13,
      v35);
    if ( SLODWORD(v41[1]) >= 0 )
      (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v41[0] + 136LL))(v41[0], 0);
    return v14;
  }
  v15 = CJobSharedData::Load(*((CJobSharedData **)this + 31), a2, (CBackgroundCopyJob *)((char *)this + 16));
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A6,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)(unsigned int)v15,
      v35);
    if ( SLODWORD(v41[1]) >= 0 )
      (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v41[0] + 136LL))(v41[0], 0);
    return v16;
  }
  v38 = 0;
  if ( (*(int (__fastcall **)(struct IPersistedEntity *, const char *, unsigned int *))(*(_QWORD *)a2 + 16LL))(
         a2,
         "DoState",
         &v38) >= 0 )
  {
    v19 = v38;
  }
  else
  {
    v17 = (*(__int64 (__fastcall **)(struct IPersistedEntity *, const char *, unsigned int *))(*(_QWORD *)a2 + 16LL))(
            a2,
            "State",
            &v38);
    v18 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5BA,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)v17,
        v35);
      if ( SLODWORD(v41[1]) >= 0 )
        (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v41[0] + 136LL))(v41[0], 0);
      return v18;
    }
    if ( v38 >= 9 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5BB,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)0x8007000DLL,
        v35);
      if ( SLODWORD(v41[1]) >= 0 )
        (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v41[0] + 136LL))(v41[0], 0);
      return 2147942413LL;
    }
    v19 = *((_DWORD *)qword_1801368F8 + v38);
    v38 = v19;
  }
  if ( v19 < 8 )
  {
    *((_DWORD *)this + 98) = v19;
    LogMessage(5u, "CBackgroundCopyJob::_LoadJobInfo", 0x5C3u, "Job %s, State %d", v8, v19);
    if ( (*(int (__fastcall **)(struct IPersistedEntity *, const char *, unsigned int *))(*(_QWORD *)a2 + 16LL))(
           a2,
           "ErrorCode",
           &v38) >= 0 )
      *((_DWORD *)this + 78) = v38;
    if ( (*(int (__fastcall **)(struct IPersistedEntity *, const char *, unsigned int *))(*(_QWORD *)a2 + 16LL))(
           a2,
           "ExtendedErrorCode",
           &v38) >= 0 )
      *((_DWORD *)this + 79) = v38;
    *(_OWORD *)Src = 0;
    v43 = 0;
    v20 = (*(__int64 (__fastcall **)(struct IPersistedEntity *, const char *, void **))(*(_QWORD *)a2 + 48LL))(
            a2,
            "DoTimes",
            Src);
    if ( v20 >= 0 )
    {
      *((_QWORD *)&v44 + 1) = 0;
      v45 = 0;
      v46 = 0;
      v26 = &v44;
      do
      {
        *(_QWORD *)v26 = 0;
        v26 = (__int128 *)((char *)v26 + 8);
        --v9;
      }
      while ( v9 );
      v27 = Src[1];
      v28 = Src[0];
      if ( (void *)((char *)Src[1] - (char *)Src[0]) != (void *)32 )
      {
        LogMessage(
          2u,
          "CBackgroundCopyJob::_LoadJobInfo",
          0x5D4u,
          "TelemetryAssert (%s): %s (0x%x, 0x%x)",
          "spBinaryVal.size() == sizeof(times)",
          "Failed",
          LODWORD(Src[1]) - LODWORD(Src[0]),
          32);
        DOTelemetryAssertTriggered(LODWORD(Src[1]) - LODWORD(Src[0]), 0x20u);
        v27 = Src[1];
        v28 = Src[0];
      }
      v29 = v27 - v28;
      if ( v29 > 0x20 )
        v29 = 32;
      memmove(&v44, v28, v29);
      *(_OWORD *)((char *)this + 264) = v44;
      *((_QWORD *)this + 35) = v45;
      *((_QWORD *)this + 36) = v46;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5CF,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)v20,
        v36);
      v21 = (*(__int64 (__fastcall **)(struct IPersistedEntity *, const char *, void **))(*(_QWORD *)a2 + 48LL))(
              a2,
              "Times",
              Src);
      if ( v21 >= 0 )
      {
        v44 = 0;
        v45 = 0;
        v22 = Src[1];
        v23 = Src[0];
        if ( (void *)((char *)Src[1] - (char *)Src[0]) != (void *)24 )
        {
          LogMessage(
            2u,
            "CBackgroundCopyJob::_LoadJobInfo",
            0x5E2u,
            "TelemetryAssert (%s): %s (0x%x, 0x%x)",
            "spBinaryVal.size() == sizeof(times)",
            "Failed",
            LODWORD(Src[1]) - LODWORD(Src[0]),
            24);
          DOTelemetryAssertTriggered(LODWORD(Src[1]) - LODWORD(Src[0]), 0x18u);
          v22 = Src[1];
          v23 = Src[0];
        }
        v24 = v22 - v23;
        if ( v24 > 0x18 )
          v24 = 24;
        memmove(&v44, v23, v24);
        *((_QWORD *)this + 33) = v44 - 116444736000000000LL;
        *((_QWORD *)this + 34) = *((_QWORD *)&v44 + 1) - 116444736000000000LL;
        *((_QWORD *)this + 35) = v45 - 116444736000000000LL;
        v40 = 0;
        if ( (*(int (__fastcall **)(struct IPersistedEntity *, const char *, __int64 *))(*(_QWORD *)a2 + 24LL))(
               a2,
               "ExpireAtTimeFT",
               &v40) < 0 )
        {
          v37 = 0;
          GetSystemTimePreciseAsFileTime(&v37);
          v25 = ((unsigned __int64)HIDWORD(v37) << 32) - 116438688000000000LL + (unsigned int)v37;
        }
        else
        {
          v25 = v40 - 116444736000000000LL;
        }
        *((_QWORD *)this + 36) = v25;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x5DD,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)v21,
          v36);
      }
    }
    v39 = 0;
    if ( (*(int (__fastcall **)(struct IPersistedEntity *, TraceLoggingCorrelationVector **))(*(_QWORD *)a2 + 56LL))(
           a2,
           &v39) < 0 )
    {
      NewCv = CBackgroundCopyJob::_CreateNewCv(this);
      if ( NewCv < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x603,
          (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
          (const char *)(unsigned int)NewCv,
          v36);
    }
    else
    {
      if ( g_loggingProvider )
        v30 = *(_DWORD *)g_loggingProvider > 5u;
      else
        v30 = 0;
      if ( v30 )
      {
        TraceLoggingCorrelationVector::ToStringImpl(
          v39,
          _InterlockedExchangeAdd64((volatile signed __int64 *)v39 + 17, 0),
          v47);
        LogMessage(5u, "CBackgroundCopyJob::_LoadJobInfo", 0x5FDu, "Job %s, CorrelationVector %s", v8, v47);
      }
      v31 = (void *)*((_QWORD *)this + 11);
      *((_QWORD *)this + 11) = v39;
      if ( v31 )
        operator delete(v31);
    }
    SavedFiles = CBackgroundCopyJob::_LoadSavedFiles(this, a2);
    v34 = SavedFiles;
    if ( SavedFiles >= 0 )
    {
      std::vector<unsigned char>::_Tidy(Src);
      if ( SLODWORD(v41[1]) >= 0 )
        (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v41[0] + 136LL))(v41[0], 0);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x606,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
        (const char *)(unsigned int)SavedFiles,
        v36);
      std::vector<unsigned char>::_Tidy(Src);
      if ( SLODWORD(v41[1]) >= 0 )
        (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v41[0] + 136LL))(v41[0], 0);
      return v34;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C1,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\DeliveryOptimization\\BackgroundCopyJob.cpp",
      (const char *)0x8007000DLL,
      v35);
    if ( SLODWORD(v41[1]) >= 0 )
      (*(void (__fastcall **)(char *, _QWORD))(*(_QWORD *)v41[0] + 136LL))(v41[0], 0);
    return 2147942413LL;
  }
}

```

## disassembly

```asm
0x18008e31c  push    rbx
0x18008e31e  push    rsi
0x18008e31f  push    rdi
0x18008e320  push    r12
0x18008e322  push    r13
0x18008e324  push    r14
0x18008e326  push    r15
0x18008e328  sub     rsp, 150h
0x18008e32f  mov     rax, cs:__security_cookie
0x18008e336  xor     rax, rsp
0x18008e339  mov     [rsp+188h+var_48], rax
0x18008e341  mov     rsi, r8
0x18008e344  mov     rbx, rdx
0x18008e347  mov     rdi, rcx
0x18008e34a  mov     rax, [rdx]
0x18008e34d  xor     edx, edx
0x18008e34f  mov     rcx, rbx
0x18008e352  mov     rax, [rax+80h]
0x18008e359  call    _guard_dispatch_icall
0x18008e35e  shr     eax, 1Fh
0x18008e361  xor     al, 1
0x18008e363  mov     [rsi], al
0x18008e365  jnz     short loc_18008E36E
0x18008e367  xor     eax, eax
0x18008e369  jmp     loc_18008EB18
0x18008e36e  mov     rax, [rbx]
0x18008e371  mov     rcx, rbx
0x18008e374  mov     rax, [rax+98h]
0x18008e37b  call    _guard_dispatch_icall
0x18008e380  mov     r15, rax
0x18008e383  mov     qword ptr [rsp+188h+var_168], rax; int
0x18008e388  lea     r9, aJobSLoading; "Job %s, Loading"
0x18008e38f  mov     r8d, 59Bh; unsigned int
0x18008e395  lea     r13, aCbackgroundcop_26; "CBackgroundCopyJob::_LoadJobInfo"
0x18008e39c  mov     rdx, r13; char *
0x18008e39f  mov     r14d, 4
0x18008e3a5  mov     ecx, r14d; unsigned __int8
0x18008e3a8  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18008e3ad  xorps   xmm0, xmm0
0x18008e3b0  movups  xmmword ptr [rsp+188h+var_128], xmm0
0x18008e3b5  mov     rcx, [rbx]
0x18008e3b8  mov     rax, [rcx+8]
0x18008e3bc  xor     r8d, r8d
0x18008e3bf  lea     rdx, [rsp+188h+var_128]
0x18008e3c4  mov     rcx, rbx
0x18008e3c7  call    _guard_dispatch_icall
0x18008e3cc  nop
0x18008e3cd  mov     rsi, [rsp+188h+var_128+8]
0x18008e3d2  xor     r12d, r12d
0x18008e3d5  test    esi, esi
0x18008e3d7  jns     short loc_18008E41A
0x18008e3d9  mov     rcx, [rsp+188h]; this
0x18008e3e1  mov     r9d, esi; char *
0x18008e3e4  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008e3eb  mov     edx, 59Eh; void *
0x18008e3f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e3f5  nop
0x18008e3f6  cmp     dword ptr [rsp+188h+var_128+8], r12d
0x18008e3fb  jl      short loc_18008E413
0x18008e3fd  mov     rcx, [rsp+188h+var_128]
0x18008e402  mov     rax, [rcx]
0x18008e405  xor     edx, edx
0x18008e407  mov     rax, [rax+88h]
0x18008e40e  call    _guard_dispatch_icall
0x18008e413  mov     eax, esi
0x18008e415  jmp     loc_18008EB18
0x18008e41a  xor     r8d, r8d; bool
0x18008e41d  mov     rdx, rbx; struct IPersistedEntity *
0x18008e420  mov     rcx, rdi; this
0x18008e423  call    ?_LoadDownloadProperties@CBackgroundCopyJob@@AEAAJAEBVIPersistedEntity@@_N@Z; CBackgroundCopyJob::_LoadDownloadProperties(IPersistedEntity const &,bool)
0x18008e428  mov     esi, eax
0x18008e42a  test    eax, eax
0x18008e42c  jns     short loc_18008E46F
0x18008e42e  mov     rcx, [rsp+188h]; this
0x18008e436  mov     r9d, eax; char *
0x18008e439  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008e440  mov     edx, 5A1h; void *
0x18008e445  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e44a  nop
0x18008e44b  cmp     dword ptr [rsp+188h+var_128+8], r12d
0x18008e450  jl      short loc_18008E468
0x18008e452  mov     rcx, [rsp+188h+var_128]
0x18008e457  mov     rax, [rcx]
0x18008e45a  xor     edx, edx
0x18008e45c  mov     rax, [rax+88h]
0x18008e463  call    _guard_dispatch_icall
0x18008e468  mov     eax, esi
0x18008e46a  jmp     loc_18008EB18
0x18008e46f  mov     r8b, 1; bool
0x18008e472  mov     rdx, rbx; struct IPersistedEntity *
0x18008e475  mov     rcx, rdi; this
0x18008e478  call    ?_LoadDownloadProperties@CBackgroundCopyJob@@AEAAJAEBVIPersistedEntity@@_N@Z; CBackgroundCopyJob::_LoadDownloadProperties(IPersistedEntity const &,bool)
0x18008e47d  mov     esi, eax
0x18008e47f  test    eax, eax
0x18008e481  jns     short loc_18008E4C4
0x18008e483  mov     rcx, [rsp+188h]; this
0x18008e48b  mov     r9d, eax; char *
0x18008e48e  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008e495  mov     edx, 5A4h; void *
0x18008e49a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e49f  nop
0x18008e4a0  cmp     dword ptr [rsp+188h+var_128+8], r12d
0x18008e4a5  jl      short loc_18008E4BD
0x18008e4a7  mov     rcx, [rsp+188h+var_128]
0x18008e4ac  mov     rax, [rcx]
0x18008e4af  xor     edx, edx
0x18008e4b1  mov     rax, [rax+88h]
0x18008e4b8  call    _guard_dispatch_icall
0x18008e4bd  mov     eax, esi
0x18008e4bf  jmp     loc_18008EB18
0x18008e4c4  lea     r8, [rdi+10h]; struct CConfigStore *
0x18008e4c8  mov     rdx, rbx; struct IPersistedEntity *
0x18008e4cb  mov     rcx, [rdi+0F8h]; this
0x18008e4d2  call    ?Load@CJobSharedData@@QEAAJAEBVIPersistedEntity@@AEAVCConfigStore@@@Z; CJobSharedData::Load(IPersistedEntity const &,CConfigStore &)
0x18008e4d7  mov     esi, eax
0x18008e4d9  test    eax, eax
0x18008e4db  jns     short loc_18008E51E
0x18008e4dd  mov     rcx, [rsp+188h]; this
0x18008e4e5  mov     r9d, eax; char *
0x18008e4e8  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008e4ef  mov     edx, 5A6h; void *
0x18008e4f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e4f9  nop
0x18008e4fa  cmp     dword ptr [rsp+188h+var_128+8], r12d
0x18008e4ff  jl      short loc_18008E517
0x18008e501  mov     rcx, [rsp+188h+var_128]
0x18008e506  mov     rax, [rcx]
0x18008e509  xor     edx, edx
0x18008e50b  mov     rax, [rax+88h]
0x18008e512  call    _guard_dispatch_icall
0x18008e517  mov     eax, esi
0x18008e519  jmp     loc_18008EB18
0x18008e51e  mov     [rsp+188h+var_140], r12d
0x18008e523  mov     rax, [rbx]
0x18008e526  lea     r8, [rsp+188h+var_140]
0x18008e52b  lea     rdx, aDostate; "DoState"
0x18008e532  mov     rcx, rbx
0x18008e535  mov     rax, [rax+10h]
0x18008e539  call    _guard_dispatch_icall
0x18008e53e  test    eax, eax
0x18008e540  jns     loc_18008E60C
0x18008e546  mov     rax, [rbx]
0x18008e549  lea     r8, [rsp+188h+var_140]
0x18008e54e  lea     rdx, aState_0; "State"
0x18008e555  mov     rcx, rbx
0x18008e558  mov     rax, [rax+10h]
0x18008e55c  call    _guard_dispatch_icall
0x18008e561  mov     esi, eax
0x18008e563  test    eax, eax
0x18008e565  jns     short loc_18008E5A8
0x18008e567  mov     rcx, [rsp+188h]; this
0x18008e56f  mov     r9d, eax; char *
0x18008e572  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008e579  mov     edx, 5BAh; void *
0x18008e57e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e583  nop
0x18008e584  cmp     dword ptr [rsp+188h+var_128+8], r12d
0x18008e589  jl      short loc_18008E5A1
0x18008e58b  mov     rcx, [rsp+188h+var_128]
0x18008e590  mov     rax, [rcx]
0x18008e593  xor     edx, edx
0x18008e595  mov     rax, [rax+88h]
0x18008e59c  call    _guard_dispatch_icall
0x18008e5a1  mov     eax, esi
0x18008e5a3  jmp     loc_18008EB18
0x18008e5a8  cmp     [rsp+188h+var_140], 9
0x18008e5ad  jb      short loc_18008E5F8
0x18008e5af  mov     rcx, [rsp+188h]; this
0x18008e5b7  mov     ebx, 8007000Dh
0x18008e5bc  mov     r9d, ebx; char *
0x18008e5bf  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008e5c6  mov     edx, 5BBh; void *
0x18008e5cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e5d0  nop
0x18008e5d1  cmp     dword ptr [rsp+188h+var_128+8], r12d
0x18008e5d6  jl      short loc_18008E5F1
0x18008e5d8  mov     r8, [rsp+188h+var_128]
0x18008e5dd  mov     rcx, [r8]
0x18008e5e0  mov     rax, [rcx+88h]
0x18008e5e7  xor     edx, edx
0x18008e5e9  mov     rcx, r8
0x18008e5ec  call    _guard_dispatch_icall
0x18008e5f1  mov     eax, ebx
0x18008e5f3  jmp     loc_18008EB18
0x18008e5f8  mov     eax, [rsp+188h+var_140]
0x18008e5fc  lea     rcx, qword_1801368F8
0x18008e603  mov     ecx, [rcx+rax*4]
0x18008e606  mov     [rsp+188h+var_140], ecx
0x18008e60a  jmp     short loc_18008E610
0x18008e60c  mov     ecx, [rsp+188h+var_140]
0x18008e610  cmp     ecx, 8
0x18008e613  jb      short loc_18008E65B
0x18008e615  mov     rcx, [rsp+188h]; this
0x18008e61d  mov     ebx, 8007000Dh
0x18008e622  mov     r9d, ebx; char *
0x18008e625  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008e62c  mov     edx, 5C1h; void *
0x18008e631  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008e636  nop
0x18008e637  cmp     dword ptr [rsp+188h+var_128+8], r12d
0x18008e63c  jl      short loc_18008E654
0x18008e63e  mov     rcx, [rsp+188h+var_128]
0x18008e643  mov     rax, [rcx]
0x18008e646  xor     edx, edx
0x18008e648  mov     rax, [rax+88h]
0x18008e64f  call    _guard_dispatch_icall
0x18008e654  mov     eax, ebx
0x18008e656  jmp     loc_18008EB18
0x18008e65b  mov     [rdi+188h], ecx
0x18008e661  mov     dword ptr [rsp+188h+var_160], ecx
0x18008e665  mov     qword ptr [rsp+188h+var_168], r15; int
0x18008e66a  lea     r9, aJobSStateD; "Job %s, State %d"
0x18008e671  mov     r8d, 5C3h; unsigned int
0x18008e677  mov     rdx, r13; char *
0x18008e67a  mov     ecx, 5; unsigned __int8
0x18008e67f  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18008e684  mov     rax, [rbx]
0x18008e687  lea     r8, [rsp+188h+var_140]
0x18008e68c  lea     rdx, aErrorcode; "ErrorCode"
0x18008e693  mov     rcx, rbx
0x18008e696  mov     rax, [rax+10h]
0x18008e69a  call    _guard_dispatch_icall
0x18008e69f  test    eax, eax
0x18008e6a1  js      short loc_18008E6AD
0x18008e6a3  mov     eax, [rsp+188h+var_140]
0x18008e6a7  mov     [rdi+138h], eax
0x18008e6ad  mov     rax, [rbx]
0x18008e6b0  lea     r8, [rsp+188h+var_140]
0x18008e6b5  lea     rdx, aExtendederrorc; "ExtendedErrorCode"
0x18008e6bc  mov     rcx, rbx
0x18008e6bf  mov     rax, [rax+10h]
0x18008e6c3  call    _guard_dispatch_icall
0x18008e6c8  test    eax, eax
0x18008e6ca  js      short loc_18008E6D6
0x18008e6cc  mov     eax, [rsp+188h+var_140]
0x18008e6d0  mov     [rdi+13Ch], eax
0x18008e6d6  xorps   xmm1, xmm1
0x18008e6d9  movdqu  xmmword ptr [rsp+188h+Src], xmm1
0x18008e6df  mov     [rsp+188h+var_108], r12
0x18008e6e7  mov     rax, [rbx]
0x18008e6ea  lea     r8, [rsp+188h+Src]
0x18008e6ef  lea     rdx, aDotimes; "DoTimes"
0x18008e6f6  mov     rcx, rbx
0x18008e6f9  mov     rax, [rax+30h]
0x18008e6fd  call    _guard_dispatch_icall
0x18008e702  mov     rcx, [rsp+188h]; this
0x18008e70a  test    eax, eax
0x18008e70c  jns     loc_18008E8D1
0x18008e712  mov     r9d, eax; char *
0x18008e715  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008e71c  mov     edx, 5CFh; void *
0x18008e721  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e726  mov     rax, [rbx]
0x18008e729  lea     r8, [rsp+188h+Src]
0x18008e72e  lea     rdx, aTimes; "Times"
0x18008e735  mov     rcx, rbx
0x18008e738  mov     rax, [rax+30h]
0x18008e73c  call    _guard_dispatch_icall
0x18008e741  mov     rcx, [rsp+188h]; this
0x18008e749  test    eax, eax
0x18008e74b  jns     short loc_18008E766
0x18008e74d  mov     r9d, eax; char *
0x18008e750  lea     r8, aCW1SSrcDeliver_24; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18008e757  mov     edx, 5DDh; void *
0x18008e75c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008e761  jmp     loc_18008E9BB
0x18008e766  xorps   xmm0, xmm0
0x18008e769  xor     eax, eax
0x18008e76b  movups  [rsp+188h+var_100], xmm0
0x18008e773  mov     [rsp+188h+var_F0], rax
0x18008e77b  mov     r8, [rsp+188h+Src+8]
0x18008e780  mov     rax, r8
0x18008e783  mov     rdx, [rsp+188h+Src]
0x18008e788  sub     rax, rdx
0x18008e78b  mov     esi, 18h
0x18008e790  cmp     rax, rsi
0x18008e793  jz      short loc_18008E7E6
0x18008e795  mov     [rsp+188h+var_150], esi
0x18008e799  mov     [rsp+188h+var_158], eax
0x18008e79d  lea     rax, aFailed; "Failed"
0x18008e7a4  mov     [rsp+188h+var_160], rax
0x18008e7a9  lea     rax, aSpbinaryvalSiz; "spBinaryVal.size() == sizeof(times)"
0x18008e7b0  mov     qword ptr [rsp+188h+var_168], rax
0x18008e7b5  lea     r9, aTelemetryasser_0; "TelemetryAssert (%s): %s (0x%x, 0x%x)"
0x18008e7bc  mov     r8d, 5E2h; unsigned int
0x18008e7c2  mov     rdx, r13; char *
0x18008e7c5  lea     ecx, [rsi-16h]; unsigned __int8
0x18008e7c8  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18008e7cd  mov     ecx, dword ptr [rsp+188h+Src+8]
0x18008e7d1  sub     ecx, dword ptr [rsp+188h+Src]; unsigned int
0x18008e7d5  mov     edx, esi; unsigned int
0x18008e7d7  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x18008e7dc  mov     r8, [rsp+188h+Src+8]
0x18008e7e1  mov     rdx, [rsp+188h+Src]; Src
0x18008e7e6  sub     r8, rdx
0x18008e7e9  cmp     r8, rsi
0x18008e7ec  cmova   r8, rsi; Size
0x18008e7f0  lea     rcx, [rsp+188h+var_100]; void *
0x18008e7f8  call    memmove
0x18008e7fd  mov     ecx, dword ptr [rsp+188h+var_100+4]
  ... truncated ...
```
