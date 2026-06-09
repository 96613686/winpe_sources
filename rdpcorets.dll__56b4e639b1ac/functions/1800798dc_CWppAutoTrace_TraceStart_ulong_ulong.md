# CWppAutoTrace::TraceStart(ulong,ulong)

- ea: `0x1800798dc`
- end: `0x180079f4f`
- name: `?TraceStart@CWppAutoTrace@@AEAAJKK@Z`
- size: `1651`
- prototype: `__int64 __fastcall(CWppAutoTrace *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180078730`

## callees

- `0x180009088`
- `0x1800091a8`
- `0x180012200`
- `0x18002e600`
- `0x180032f60`
- `0x180033da0`
- `0x180034970`
- `0x180059838`
- `0x180063160`
- `0x180072abc`
- `0x1800789fc`
- `0x1800798dc`
- `0x180079f58`
- `0x18007a3a8`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180079e26`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180079e26`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x180079e67`
- `api-ms-win-core-threadpool-legacy-l1-1-0!ChangeTimerQueueTimer` at `0x180079e67`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180079ad2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180079ad2`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18007992a`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18007992a`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180079bda`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180079c45`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180079bda`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180079c45`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180079d7e`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x180079d7e`

## string_xrefs

- `0x180079a4d`: `CWppAutoTrace::DeleteOldFiles`

## pseudocode

```c
__int64 __fastcall CWppAutoTrace::TraceStart(CWppAutoTrace *this, __int64 a2, __int64 a3)
{
  UCHAR v4; // r13
  char *v5; // rcx
  int v6; // r12d
  CWppAutoTrace *v7; // rcx
  __int64 v8; // r8
  unsigned int v9; // r9d
  PVOID *v10; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  unsigned int v12; // eax
  int v13; // ebx
  char *v14; // rdi
  unsigned int v15; // eax
  int v16; // edx
  const char *v17; // rcx
  unsigned int v18; // eax
  ULONG started; // ebx
  unsigned int v20; // eax
  ULONG v21; // ebx
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // r8
  const GUID *v27; // rdx
  __int64 v28; // rax
  TRACEHANDLE v29; // rcx
  unsigned int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // r8
  void *v33; // rdx
  unsigned int v34; // eax
  __int64 v35; // rdx
  unsigned int v36; // eax
  ULONGLONG MatchAllKeyword; // [rsp+28h] [rbp-D8h]
  char *v39; // [rsp+60h] [rbp-A0h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+68h] [rbp-98h] BYREF
  struct _ENABLE_TRACE_PARAMETERS EnableParameters; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_TRACE_PROPERTIES Properties; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v43[260]; // [rsp+178h] [rbp+78h] BYREF

  v4 = a3;
  v5 = (char *)this + 592;
  v6 = a2;
  v39 = v5;
  if ( *((_DWORD *)v5 + 2) )
    PAL_System_CritSecEnter(*(_QWORD *)v5, a2, a3);
  memset_0(&Properties, 0, 0x2D0u);
  SystemTime = 0;
  memset(&EnableParameters, 0, sizeof(EnableParameters));
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      CurrentThreadActivityIdPrefix);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !*((_BYTE *)this + 56) )
  {
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 2u )
    {
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
        v12,
        -2147418113);
    }
    v13 = -2147418113;
    v14 = (char *)this + 624;
    goto LABEL_69;
  }
  v14 = (char *)this + 624;
  v13 = CWppAutoTrace::DeleteOldFiles(
          v7,
          (const unsigned __int16 *)this + 352,
          (const unsigned __int16 *)this + 312,
          v9);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 42;
    v17 = "CWppAutoTrace::DeleteOldFiles";
    goto LABEL_18;
  }
  memset_0(&Properties, 0, 0x2D0u);
  Properties.Wnode.BufferSize = 720;
  Properties.Wnode.ClientContext = 1;
  Properties.Wnode.Flags = 0x20000;
  Properties.BufferSize = 512;
  Properties.MinimumBuffers = 64;
  Properties.MaximumBuffers = 128;
  Properties.MaximumFileSize = 100;
  Properties.LogFileMode = 2;
  Properties.LoggerNameOffset = 120;
  Properties.LogFileNameOffset = 200;
  GetSystemTime(&SystemTime);
  v13 = StringCchPrintfW(
          v43,
          0x104u,
          L"%s%s-WppAutoTrace-%04u%02u%02u-%02u%02u%02u-%03u.etl",
          (char *)this + 704,
          (char *)this + 624,
          SystemTime.wYear,
          SystemTime.wMonth,
          SystemTime.wDay,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds,
          v39);
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_69;
    }
    v15 = RdpWppGetCurrentThreadActivityIdPrefix();
    v16 = 43;
    v17 = "format trace file name";
LABEL_18:
    LODWORD(MatchAllKeyword) = v13;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v16,
      (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      v15,
      (__int64)v17,
      MatchAllKeyword);
    goto LABEL_69;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      44,
      (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      v18,
      (__int64)v43);
  }
  started = StartTraceW((PTRACEHANDLE)this + 8, (LPCWSTR)this + 312, &Properties);
  if ( started )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      v20 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids, v20, started);
    }
    Properties.LogFileMode = 133120;
    Properties.FlushTimer = 10;
    v21 = StartTraceW((PTRACEHANDLE)this + 8, (LPCWSTR)this + 312, &Properties);
    if ( v21 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v22 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids, v22, v21);
      }
      goto LABEL_68;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v23 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      47,
      (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      v23,
      (__int64)v43);
  }
  *((_BYTE *)this + 72) = 1;
  v24 = 0;
  v25 = *(_QWORD *)GUID_NULL.Data4;
  v26 = *(_QWORD *)&GUID_NULL.Data1;
  while ( 1 )
  {
    if ( v24 >= 0x20 )
    {
      v33 = (void *)*((_QWORD *)this + 77);
      if ( v33 == (void *)-1LL )
      {
        if ( !CreateTimerQueueTimer(
                (PHANDLE)this + 77,
                0,
                CWppAutoTrace::TimerCallback_Static,
                this,
                0x2710u,
                0x2710u,
                0) )
        {
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_68;
          }
          v34 = RdpWppGetCurrentThreadActivityIdPrefix();
          v35 = 49;
          goto LABEL_67;
        }
      }
      else if ( !ChangeTimerQueueTimer(0, v33, 0x2710u, 0x2710u) )
      {
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_68;
        }
        v34 = RdpWppGetCurrentThreadActivityIdPrefix();
        v35 = 50;
LABEL_67:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v35, &WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids, v34);
        goto LABEL_68;
      }
      v13 = 0;
      goto LABEL_71;
    }
    if ( _bittest(&v6, v24) )
    {
      v27 = (const GUID *)((char *)this + 16 * v24 + 76);
      v28 = *(_QWORD *)&v27->Data1 - v26;
      if ( *(_QWORD *)&v27->Data1 == v26 )
        v28 = *(_QWORD *)v27->Data4 - v25;
      if ( v28 )
        break;
    }
LABEL_50:
    ++v24;
  }
  v29 = *((_QWORD *)this + 8);
  memset(&EnableParameters, 0, sizeof(EnableParameters));
  EnableParameters.Version = 1;
  if ( !EnableTraceEx2(v29, v27, 1u, v4, 0xFFFFFFFF, 0, 0x1388u, &EnableParameters) )
  {
    v25 = *(_QWORD *)GUID_NULL.Data4;
    v26 = *(_QWORD *)&GUID_NULL.Data1;
    goto LABEL_50;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v30 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, v32, v30, v24 + 1);
  }
LABEL_68:
  v13 = -2147467259;
LABEL_69:
  CWppAutoTrace::TraceStop(this, 0, v8);
LABEL_71:
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v36 = RdpWppGetCurrentThreadActivityIdPrefix();
    LODWORD(MatchAllKeyword) = v13;
    WPP_SF_DSd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      51,
      (unsigned int)&WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids,
      v36,
      (__int64)v14,
      MatchAllKeyword);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v39);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800798dc  mov     [rsp-8+arg_8], rbx
0x1800798e1  push    rbp
0x1800798e2  push    rsi
0x1800798e3  push    rdi
0x1800798e4  push    r12
0x1800798e6  push    r13
0x1800798e8  push    r14
0x1800798ea  push    r15
0x1800798ec  lea     rbp, [rsp-290h]
0x1800798f4  sub     rsp, 390h
0x1800798fb  mov     rax, cs:__security_cookie
0x180079902  xor     rax, rsp
0x180079905  mov     [rbp+2C0h+var_40], rax
0x18007990c  mov     rsi, rcx
0x18007990f  mov     r13d, r8d
0x180079912  add     rcx, 250h
0x180079919  mov     r12d, edx
0x18007991c  mov     [rsp+3C0h+var_360], rcx
0x180079921  cmp     dword ptr [rcx+8], 0
0x180079925  jz      short loc_180079930
0x180079927  mov     rcx, [rcx]
0x18007992a  call    cs:__imp_PAL_System_CritSecEnter
0x180079930  xor     edx, edx; Val
0x180079932  lea     rcx, [rbp+2C0h+Properties]; void *
0x180079936  mov     r8d, 2D0h; Size
0x18007993c  call    memset_0
0x180079941  xorps   xmm1, xmm1
0x180079944  xorps   xmm0, xmm0
0x180079947  movups  xmmword ptr [rsp+3C0h+SystemTime.wYear], xmm0
0x18007994c  movups  xmmword ptr [rsp+3C0h+var_348.Version], xmm1
0x180079951  movups  xmmword ptr [rbp+2C0h+var_348.SourceId.Data2], xmm1
0x180079955  movups  xmmword ptr [rbp+2C0h+var_348.EnableFilterDesc], xmm1
0x180079959  mov     rax, cs:WPP_GLOBAL_Control
0x180079960  lea     r14, WPP_GLOBAL_Control
0x180079967  lea     r15, WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids
0x18007996e  cmp     rax, r14
0x180079971  jz      short loc_1800799A9
0x180079973  test    dword ptr [rax+1Ch], 400h
0x18007997a  jz      short loc_1800799A9
0x18007997c  cmp     byte ptr [rax+19h], 5
0x180079980  jb      short loc_1800799A9
0x180079982  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079987  mov     rcx, cs:WPP_GLOBAL_Control
0x18007998e  mov     edx, 28h ; '('
0x180079993  mov     r9d, eax
0x180079996  mov     r8, r15
0x180079999  mov     rcx, [rcx+10h]
0x18007999d  call    WPP_SF_d
0x1800799a2  mov     rax, cs:WPP_GLOBAL_Control
0x1800799a9  cmp     byte ptr [rsi+38h], 0
0x1800799ad  jnz     short loc_1800799F9
0x1800799af  cmp     rax, r14
0x1800799b2  jz      short loc_1800799E8
0x1800799b4  test    byte ptr [rax+1Ch], 8
0x1800799b8  jz      short loc_1800799E8
0x1800799ba  cmp     byte ptr [rax+19h], 2
0x1800799be  jb      short loc_1800799E8
0x1800799c0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800799c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800799cc  mov     edx, 29h ; ')'
0x1800799d1  mov     r9d, eax
0x1800799d4  mov     dword ptr [rsp+3C0h+MatchAnyKeyword], 8000FFFFh
0x1800799dc  mov     r8, r15
0x1800799df  mov     rcx, [rcx+10h]
0x1800799e3  call    WPP_SF_Dd
0x1800799e8  mov     ebx, 8000FFFFh
0x1800799ed  lea     rdi, [rsi+270h]
0x1800799f4  jmp     loc_180079EBC
0x1800799f9  lea     rdi, [rsi+270h]
0x180079a00  lea     r14, [rsi+2C0h]
0x180079a07  mov     r8, rdi; unsigned __int16 *
0x180079a0a  mov     rdx, r14; unsigned __int16 *
0x180079a0d  call    ?DeleteOldFiles@CWppAutoTrace@@AEAAJPEBG0K@Z; CWppAutoTrace::DeleteOldFiles(ushort const *,ushort const *,ulong)
0x180079a12  mov     ebx, eax
0x180079a14  test    eax, eax
0x180079a16  jns     short loc_180079A78
0x180079a18  mov     rax, cs:WPP_GLOBAL_Control
0x180079a1f  lea     r14, WPP_GLOBAL_Control
0x180079a26  cmp     rax, r14
0x180079a29  jz      loc_180079EBC
0x180079a2f  test    byte ptr [rax+1Ch], 8
0x180079a33  jz      loc_180079EBC
0x180079a39  cmp     byte ptr [rax+19h], 2
0x180079a3d  jb      loc_180079EBC
0x180079a43  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079a48  mov     edx, 2Ah ; '*'
0x180079a4d  lea     rcx, aCwppautotraceD; "CWppAutoTrace::DeleteOldFiles"
0x180079a54  mov     dword ptr [rsp+3C0h+MatchAllKeyword], ebx
0x180079a58  mov     r9d, eax
0x180079a5b  mov     [rsp+3C0h+MatchAnyKeyword], rcx
0x180079a60  mov     r8, r15
0x180079a63  mov     rcx, cs:WPP_GLOBAL_Control
0x180079a6a  mov     rcx, [rcx+10h]
0x180079a6e  call    WPP_SF_DsD
0x180079a73  jmp     loc_180079EBC
0x180079a78  mov     ebx, 2D0h
0x180079a7d  lea     rcx, [rbp+2C0h+Properties]; void *
0x180079a81  mov     r8d, ebx; Size
0x180079a84  xor     edx, edx; Val
0x180079a86  call    memset_0
0x180079a8b  lea     rcx, [rsp+3C0h+SystemTime]; lpSystemTime
0x180079a90  mov     [rbp+2C0h+Properties.Wnode.BufferSize], ebx
0x180079a93  mov     [rbp+2C0h+Properties.Wnode.ClientContext], 1
0x180079a9a  mov     [rbp+2C0h+Properties.Wnode.Flags], 20000h
0x180079aa1  mov     [rbp+2C0h+Properties.BufferSize], 200h
0x180079aa8  mov     [rbp+2C0h+Properties.MinimumBuffers], 40h ; '@'
0x180079aaf  mov     [rbp+2C0h+Properties.MaximumBuffers], 80h
0x180079ab6  mov     [rbp+2C0h+Properties.MaximumFileSize], 64h ; 'd'
0x180079abd  mov     [rbp+2C0h+Properties.LogFileMode], 2
0x180079ac4  mov     [rbp+2C0h+Properties.LoggerNameOffset], 78h ; 'x'
0x180079acb  mov     [rbp+2C0h+Properties.LogFileNameOffset], 0C8h
0x180079ad2  call    cs:__imp_GetSystemTime
0x180079ad8  movzx   ecx, [rsp+3C0h+SystemTime.wSecond]
0x180079add  mov     r9, r14
0x180079ae0  movzx   edx, [rsp+3C0h+SystemTime.wMinute]
0x180079ae5  movzx   r8d, [rsp+3C0h+SystemTime.wHour]
0x180079aeb  movzx   eax, [rsp+3C0h+SystemTime.wMilliseconds]
0x180079af0  movzx   r10d, [rsp+3C0h+SystemTime.wDay]
0x180079af6  movzx   r11d, [rsp+3C0h+SystemTime.wMonth]
0x180079afc  movzx   ebx, [rsp+3C0h+SystemTime.wYear]
0x180079b01  mov     [rsp+3C0h+var_368], eax
0x180079b05  mov     [rsp+3C0h+var_370], ecx
0x180079b09  lea     rcx, [rbp+2C0h+var_248]; unsigned __int16 *
0x180079b0d  mov     [rsp+3C0h+var_378], edx
0x180079b11  mov     edx, 104h; unsigned __int64
0x180079b16  mov     [rsp+3C0h+var_380], r8d
0x180079b1b  lea     r8, aSSWppautotrace; "%s%s-WppAutoTrace-%04u%02u%02u-%02u%02u"...
0x180079b22  mov     dword ptr [rsp+3C0h+EnableParameters], r10d
0x180079b27  mov     [rsp+3C0h+Timeout], r11d
0x180079b2c  mov     dword ptr [rsp+3C0h+MatchAllKeyword], ebx
0x180079b30  mov     [rsp+3C0h+MatchAnyKeyword], rdi
0x180079b35  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180079b3a  mov     ebx, eax
0x180079b3c  test    eax, eax
0x180079b3e  jns     short loc_180079B81
0x180079b40  mov     rax, cs:WPP_GLOBAL_Control
0x180079b47  lea     r14, WPP_GLOBAL_Control
0x180079b4e  cmp     rax, r14
0x180079b51  jz      loc_180079EBC
0x180079b57  test    byte ptr [rax+1Ch], 8
0x180079b5b  jz      loc_180079EBC
0x180079b61  cmp     byte ptr [rax+19h], 2
0x180079b65  jb      loc_180079EBC
0x180079b6b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079b70  mov     edx, 2Bh ; '+'
0x180079b75  lea     rcx, aFormatTraceFil; "format trace file name"
0x180079b7c  jmp     loc_180079A54
0x180079b81  mov     rax, cs:WPP_GLOBAL_Control
0x180079b88  lea     r14, WPP_GLOBAL_Control
0x180079b8f  cmp     rax, r14
0x180079b92  jz      short loc_180079BCC
0x180079b94  test    dword ptr [rax+1Ch], 400h
0x180079b9b  jz      short loc_180079BCC
0x180079b9d  cmp     byte ptr [rax+19h], 2
0x180079ba1  jb      short loc_180079BCC
0x180079ba3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079ba8  lea     rcx, [rbp+2C0h+var_248]
0x180079bac  mov     edx, 2Ch ; ','
0x180079bb1  mov     [rsp+3C0h+MatchAnyKeyword], rcx
0x180079bb6  mov     r9d, eax
0x180079bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180079bc0  mov     r8, r15
0x180079bc3  mov     rcx, [rcx+10h]
0x180079bc7  call    WPP_SF_DS
0x180079bcc  lea     r15, [rsi+40h]
0x180079bd0  mov     rdx, rdi; InstanceName
0x180079bd3  mov     rcx, r15; TraceHandle
0x180079bd6  lea     r8, [rbp+2C0h+Properties]; Properties
0x180079bda  call    cs:__imp_StartTraceW
0x180079be0  mov     ebx, eax
0x180079be2  test    eax, eax
0x180079be4  jz      loc_180079CA5
0x180079bea  mov     rcx, cs:WPP_GLOBAL_Control
0x180079bf1  cmp     rcx, r14
0x180079bf4  jz      short loc_180079C2D
0x180079bf6  test    dword ptr [rcx+1Ch], 400h
0x180079bfd  jz      short loc_180079C2D
0x180079bff  cmp     byte ptr [rcx+19h], 3
0x180079c03  jb      short loc_180079C2D
0x180079c05  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180079c11  lea     r8, WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids
0x180079c18  mov     edx, 2Dh ; '-'
0x180079c1d  mov     dword ptr [rsp+3C0h+MatchAnyKeyword], ebx
0x180079c21  mov     r9d, eax
0x180079c24  mov     rcx, [rcx+10h]
0x180079c28  call    WPP_SF_Dd
0x180079c2d  lea     r8, [rbp+2C0h+Properties]; Properties
0x180079c31  mov     [rbp+2C0h+Properties.LogFileMode], 20800h
0x180079c38  mov     rdx, rdi; InstanceName
0x180079c3b  mov     [rbp+2C0h+Properties.FlushTimer], 0Ah
0x180079c42  mov     rcx, r15; TraceHandle
0x180079c45  call    cs:__imp_StartTraceW
0x180079c4b  mov     ebx, eax
0x180079c4d  test    eax, eax
0x180079c4f  jz      short loc_180079CA5
0x180079c51  mov     rcx, cs:WPP_GLOBAL_Control
0x180079c58  cmp     rcx, r14
0x180079c5b  jz      loc_180079EB7
0x180079c61  test    dword ptr [rcx+1Ch], 400h
0x180079c68  jz      loc_180079EB7
0x180079c6e  cmp     byte ptr [rcx+19h], 2
0x180079c72  jb      loc_180079EB7
0x180079c78  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180079c84  lea     r8, WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids
0x180079c8b  mov     edx, 2Eh ; '.'
0x180079c90  mov     dword ptr [rsp+3C0h+MatchAnyKeyword], ebx
0x180079c94  mov     r9d, eax
0x180079c97  mov     rcx, [rcx+10h]
0x180079c9b  call    WPP_SF_Dd
0x180079ca0  jmp     loc_180079EB7
0x180079ca5  mov     rax, cs:WPP_GLOBAL_Control
0x180079cac  cmp     rax, r14
0x180079caf  jz      short loc_180079CED
0x180079cb1  test    dword ptr [rax+1Ch], 400h
0x180079cb8  jz      short loc_180079CED
0x180079cba  cmp     byte ptr [rax+19h], 4
0x180079cbe  jb      short loc_180079CED
0x180079cc0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079cc5  lea     rcx, [rbp+2C0h+var_248]
0x180079cc9  mov     edx, 2Fh ; '/'
0x180079cce  mov     [rsp+3C0h+MatchAnyKeyword], rcx
0x180079cd3  lea     r8, WPP_8807d125e2df3d017b7c96d55bcf0786_Traceguids
0x180079cda  mov     rcx, cs:WPP_GLOBAL_Control
0x180079ce1  mov     r9d, eax
0x180079ce4  mov     rcx, [rcx+10h]
0x180079ce8  call    WPP_SF_DS
0x180079ced  mov     byte ptr [rsi+48h], 1
0x180079cf1  xor     ebx, ebx
0x180079cf3  mov     rcx, qword ptr cs:GUID_NULL.Data4
0x180079cfa  mov     r8, qword ptr cs:GUID_NULL.Data1
0x180079d01  cmp     ebx, 20h ; ' '
0x180079d04  jnb     loc_180079DF2
0x180079d0a  bt      r12d, ebx
0x180079d0e  jnb     loc_180079D99
0x180079d14  mov     edx, ebx
0x180079d16  shl     rdx, 4
0x180079d1a  add     rdx, 4Ch ; 'L'
0x180079d1e  add     rdx, rsi; ProviderId
0x180079d21  mov     rax, [rdx]
0x180079d24  sub     rax, r8
0x180079d27  jnz     short loc_180079D30
0x180079d29  mov     rax, [rdx+8]
0x180079d2d  sub     rax, rcx
0x180079d30  test    rax, rax
0x180079d33  jz      short loc_180079D99
0x180079d35  mov     rcx, [r15]; TraceHandle
0x180079d38  lea     rax, [rsp+3C0h+var_348]
0x180079d3d  mov     [rsp+3C0h+EnableParameters], rax; EnableParameters
0x180079d42  xorps   xmm0, xmm0
0x180079d45  mov     [rsp+3C0h+Timeout], 1388h; Timeout
0x180079d4d  mov     eax, 0FFFFFFFFh
0x180079d52  movups  xmmword ptr [rsp+3C0h+var_348.Version], xmm0
0x180079d57  mov     [rsp+3C0h+MatchAllKeyword], 0; MatchAllKeyword
0x180079d60  mov     r9b, r13b; Level
0x180079d63  mov     r8d, 1; ControlCode
0x180079d69  mov     [rsp+3C0h+MatchAnyKeyword], rax; MatchAnyKeyword
0x180079d6e  movups  xmmword ptr [rbp+2C0h+var_348.SourceId.Data2], xmm0
0x180079d72  mov     [rsp+3C0h+var_348.Version], 1
0x180079d7a  movups  xmmword ptr [rbp+2C0h+var_348.EnableFilterDesc], xmm0
0x180079d7e  call    cs:__imp_EnableTraceEx2
0x180079d84  mov     r14d, eax
0x180079d87  test    eax, eax
0x180079d89  jnz     short loc_180079DA0
0x180079d8b  mov     rcx, qword ptr cs:GUID_NULL.Data4
0x180079d92  mov     r8, qword ptr cs:GUID_NULL.Data1
0x180079d99  inc     ebx
0x180079d9b  jmp     loc_180079D01
0x180079da0  mov     rax, cs:WPP_GLOBAL_Control
0x180079da7  lea     rcx, WPP_GLOBAL_Control
0x180079dae  cmp     rax, rcx
0x180079db1  jz      short loc_180079DE6
0x180079db3  test    dword ptr [rax+1Ch], 400h
0x180079dba  jz      short loc_180079DE6
0x180079dbc  cmp     byte ptr [rax+19h], 2
0x180079dc0  jb      short loc_180079DE6
0x180079dc2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180079dc7  lea     ecx, [rbx+1]
0x180079dca  mov     [rsp+3C0h+Timeout], r14d
0x180079dcf  mov     dword ptr [rsp+3C0h+MatchAnyKeyword], ecx
0x180079dd3  mov     r9d, eax
0x180079dd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180079ddd  mov     rcx, [rcx+10h]
0x180079de1  call    WPP_SF_DDDD
0x180079de6  lea     r14, WPP_GLOBAL_Control
0x180079ded  jmp     loc_180079EB7
0x180079df2  lea     rcx, [rsi+268h]; phNewTimer
0x180079df9  mov     r8d, 2710h; DueTime
0x180079dff  mov     rdx, [rcx]; Timer
0x180079e02  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180079e06  jnz     short loc_180079E62
0x180079e08  mov     [rsp+3C0h+Timeout], 0; Flags
0x180079e10  mov     r9, rsi; Parameter
0x180079e13  mov     dword ptr [rsp+3C0h+MatchAllKeyword], r8d; Period
0x180079e18  xor     edx, edx; TimerQueue
0x180079e1a  mov     dword ptr [rsp+3C0h+MatchAnyKeyword], r8d; DueTime
0x180079e1f  lea     r8, ?TimerCallback_Static@CWppAutoTrace@@CAXPEAXE@Z; Callback
0x180079e26  call    cs:__imp_CreateTimerQueueTimer
0x180079e2c  test    eax, eax
  ... truncated ...
```
