# CUITrace::TraceEvent(ulong,ulong,_GUID const * const,ulong,...)

- ea: `0x180098a48`
- end: `0x180098e1a`
- name: `?TraceEvent@CUITrace@@QEAAJKKQEBU_GUID@@KZZ`
- size: `978`
- prototype: `__int64(CUITrace *__hidden this, unsigned int, unsigned int, const struct _GUID *const, unsigned int, ...)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800720c0`

## callees

- `0x1800063b0`
- `0x180007d08`
- `0x180085624`
- `0x180098a48`
- `0x1800b83ee`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180098b1c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180098b1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098def`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180098def`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180098cf2`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180098cf2`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180098c58`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180098d04`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180098c58`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceEvent` at `0x180098d04`

## string_xrefs

- `0x180098b73`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x180098d5e`: `com\complus\dtc\dtc\trace\src\uitrace.cpp`
- `0x180098afe`: `MSDTC Service`

## pseudocode

```c
__int64 CUITrace::TraceEvent(
        CUITrace *this,
        unsigned int a2,
        unsigned int a3,
        union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F *a4,
        ULONG a5,
        ...)
{
  int v7; // ecx
  unsigned int v8; // ebx
  __int64 v9; // rsi
  const wchar_t *v10; // r15
  signed __int32 v11; // r14d
  DWORD v12; // eax
  __int64 v13; // r9
  va_list v14; // rcx
  union _EVENT_TRACE_HEADER::$146F82FB58FCEC23F5D30A6BD72C4E4F v15; // xmm0
  char *v16; // rdi
  int v17; // eax
  __int64 v18; // rax
  TRACEHANDLE v19; // rcx
  signed int i; // eax
  unsigned int v21; // r9d
  signed __int32 v22; // r14d
  void *v23; // r9
  signed __int32 v24; // edi
  void *v25; // r9
  unsigned int v27; // [rsp+28h] [rbp-D8h]
  int v28; // [rsp+28h] [rbp-D8h]
  unsigned int v29; // [rsp+28h] [rbp-D8h]
  const wchar_t *v30; // [rsp+30h] [rbp-D0h]
  void *v31; // [rsp+38h] [rbp-C8h]
  int v32; // [rsp+40h] [rbp-C0h]
  signed __int32 v33; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  char *v35[2]; // [rsp+60h] [rbp-A0h] BYREF
  struct _EVENT_TRACE_HEADER EventTrace; // [rsp+70h] [rbp-90h] BYREF
  signed __int32 *v37; // [rsp+A0h] [rbp-60h]
  int v38; // [rsp+A8h] [rbp-58h]
  char v39; // [rsp+B0h] [rbp-50h] BYREF
  char v40[16]; // [rsp+1A0h] [rbp+A0h] BYREF
  char v41; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v42[111]; // [rsp+1B1h] [rbp+B1h] BYREF
  va_list va; // [rsp+2A8h] [rbp+1A8h] BYREF

  va_start(va, a5);
  v33 = _InterlockedIncrement(&dword_180168114);
  memset_0(&EventTrace, 0, 0x140u);
  v41 = 0;
  memset_0(v42, 0, 0x63u);
  v7 = *((_DWORD *)this + 2);
  v35[0] = &v41;
  pv = 0;
  if ( (unsigned int)(v7 - 1) > 2 )
  {
    v8 = -2147467263;
    goto LABEL_36;
  }
  if ( a5 - 10 > 0xF4 )
  {
    v8 = -2147024809;
    goto LABEL_36;
  }
  v9 = -1;
  v10 = L"MSDTC Service";
  v8 = 0;
  v11 = 0;
  if ( v7 == 1 )
  {
    v12 = WaitForSingleObject(*((HANDLE *)this + 204), 0x1388u);
    if ( v12 == -1 )
    {
      v8 = -1;
      v30 = L"WaitForSingleObjectEx for m_hSessionEvent Failed";
      v13 = 720;
      v28 = -1;
    }
    else
    {
      if ( v12 != 258 )
        goto LABEL_10;
      v13 = 726;
      v30 = L"WaitForSingleObjectEx for m_hSessionEvent timed out";
      v28 = 0;
    }
    *((_DWORD *)this + 2) = 2;
    TraceStringInline(14, 1, L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp", v13, L"CUITrace::TraceEvent", v28, v30);
  }
LABEL_10:
  memset_0(&EventTrace, 0, 0x140u);
  va_copy(v14, va);
  v15 = *a4;
  EventTrace.Version = a5;
  v16 = &v39;
  EventTrace.UserTime = 1179648;
  EventTrace.24 = v15;
  v37 = &v33;
  v38 = 4;
  do
  {
    v17 = *(_DWORD *)v14;
    *((_DWORD *)v16 + 2) = *(_DWORD *)v14;
    if ( !v17 )
      break;
    v18 = *((_QWORD *)v14 + 1);
    v14 += 16;
    *(_QWORD *)v16 = v18;
    v16 += 16;
  }
  while ( v16 < v40 );
  if ( g_pCoreTmInstance )
  {
    (*(void (__fastcall **)(struct ITmInstance *, LPVOID *))(*(_QWORD *)g_pCoreTmInstance + 56LL))(
      g_pCoreTmInstance,
      &pv);
    if ( pv )
      v10 = (const wchar_t *)pv;
  }
  if ( v16 < v40 )
  {
    do
      ++v9;
    while ( v10[v9] );
    *(_QWORD *)v16 = v10;
    *((_DWORD *)v16 + 2) = 2 * v9 + 2;
    LODWORD(v16) = (_DWORD)v16 + 16;
  }
  v19 = *((_QWORD *)this + 202);
  *(_DWORD *)&EventTrace.Size = (_DWORD)v16 - (unsigned int)&EventTrace;
  for ( i = TraceEvent(v19, &EventTrace); i == 8; i = TraceEvent(*((_QWORD *)this + 202), &EventTrace) )
  {
    v21 = g_dwNumTraceSleepIntervals;
    if ( g_dwNumTraceSleepIntervals <= 0xF424A )
    {
      v22 = _InterlockedExchangeAdd((volatile signed __int32 *)&g_dwNumTraceSleepIntervals, 1u);
      v21 = g_dwNumTraceSleepIntervals;
      v11 = v22 + 1;
    }
    if ( v11 == g_dwTraceSleepIntervalsLimit )
    {
      StringCchPrintfA(&v41, 0x64u, "%d", v21);
      DtcWriteToEventLoggerExUnFilteredA(2u, 0xDu, 0xC0001149, v23, 1u, v27, (const char **)v35, v31, v32);
      if ( 10 * g_dwTraceSleepIntervalsLimit <= 0xF424A )
        g_dwTraceSleepIntervalsLimit *= 10;
    }
    Sleep(0x7D0u);
  }
  if ( i )
  {
    v24 = 0;
    if ( g_dwNumTraceEventsLost <= 0xF424A )
      v24 = _InterlockedIncrement((volatile signed __int32 *)&g_dwNumTraceEventsLost);
    if ( i > 0 )
      v8 = (unsigned __int16)i | 0x80070000;
    else
      v8 = i;
    TraceStringInline(
      14,
      1,
      L"com\\complus\\dtc\\dtc\\trace\\src\\uitrace.cpp",
      844,
      L"CUITrace::TraceEvent",
      v8,
      L"::TraceEvent Failed");
    if ( v24 == g_dwTraceEventsLossLimit )
    {
      StringCchPrintfA(&v41, 0x64u, "%d, Internal Information : latest hr = 0x%x", g_dwNumTraceEventsLost, v8);
      DtcWriteToEventLoggerExUnFilteredA(1u, 0xDu, 0xC0001139, v25, 1u, v29, (const char **)v35, v31, v32);
      if ( 10 * g_dwTraceEventsLossLimit <= 0xF424A )
        g_dwTraceEventsLossLimit *= 10;
    }
  }
LABEL_36:
  CoTaskMemFree(pv);
  return v8;
}

```

## disassembly

```asm
0x180098a48  push    rbp
0x180098a4a  push    rbx
0x180098a4b  push    rsi
0x180098a4c  push    rdi
0x180098a4d  push    r12
0x180098a4f  push    r13
0x180098a51  push    r14
0x180098a53  push    r15
0x180098a55  lea     rbp, [rsp-138h]
0x180098a5d  sub     rsp, 238h
0x180098a64  mov     rax, cs:__security_cookie
0x180098a6b  xor     rax, rsp
0x180098a6e  mov     [rbp+170h+var_50], rax
0x180098a75  mov     r13, rcx
0x180098a78  mov     rdi, r9
0x180098a7b  mov     ecx, 1
0x180098a80  mov     eax, ecx
0x180098a82  lock xadd cs:dword_180168114, eax
0x180098a8a  add     eax, ecx
0x180098a8c  xor     edx, edx; Val
0x180098a8e  lea     rcx, [rsp+270h+EventTrace]; void *
0x180098a93  mov     [rsp+270h+var_220], eax
0x180098a97  mov     r8d, 140h; Size
0x180098a9d  call    memset_0
0x180098aa2  xor     r12d, r12d
0x180098aa5  lea     rcx, [rbp+170h+var_BF]; void *
0x180098aac  xor     edx, edx; Val
0x180098aae  mov     [rbp+170h+var_C0], r12b
0x180098ab5  lea     r8d, [r12+63h]; Size
0x180098aba  call    memset_0
0x180098abf  mov     ecx, [r13+8]
0x180098ac3  lea     rax, [rbp+170h+var_C0]
0x180098aca  mov     [rsp+270h+var_210], rax
0x180098acf  mov     [rsp+270h+pv], r12
0x180098ad4  lea     eax, [rcx-1]
0x180098ad7  cmp     eax, 2
0x180098ada  jbe     short loc_180098AE6
0x180098adc  mov     ebx, 80004001h
0x180098ae1  jmp     loc_180098DEA
0x180098ae6  mov     eax, [rbp+170h+arg_20]
0x180098aec  add     eax, 0FFFFFFF6h
0x180098aef  cmp     eax, 0F4h
0x180098af4  ja      loc_180098DE5
0x180098afa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180098afe  lea     r15, aMsdtcService; "MSDTC Service"
0x180098b05  mov     ebx, r12d
0x180098b08  mov     r14d, r12d
0x180098b0b  cmp     ecx, 1
0x180098b0e  jnz     short loc_180098B87
0x180098b10  mov     rcx, [r13+660h]; hHandle
0x180098b17  mov     edx, 1388h; dwMilliseconds
0x180098b1c  call    cs:__imp_WaitForSingleObject
0x180098b22  cmp     eax, 0FFFFFFFFh
0x180098b25  jnz     short loc_180098B41
0x180098b27  lea     rax, aWaitforsingleo_2; "WaitForSingleObjectEx for m_hSessionEve"...
0x180098b2e  mov     ebx, esi
0x180098b30  mov     [rsp+270h+var_240], rax
0x180098b35  mov     r9d, 2D0h
0x180098b3b  mov     [rsp+270h+var_248], esi
0x180098b3f  jmp     short loc_180098B5F
0x180098b41  cmp     eax, 102h
0x180098b46  jnz     short loc_180098B87
0x180098b48  lea     rax, aWaitforsingleo; "WaitForSingleObjectEx for m_hSessionEve"...
0x180098b4f  mov     r9d, 2D6h
0x180098b55  mov     [rsp+270h+var_240], rax
0x180098b5a  mov     qword ptr [rsp+270h+var_248], r12; unsigned int
0x180098b5f  mov     edx, 1
0x180098b64  mov     dword ptr [r13+8], 2
0x180098b6c  lea     rax, aCuitraceTracee; "CUITrace::TraceEvent"
0x180098b73  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x180098b7a  mov     qword ptr [rsp+270h+var_250], rax
0x180098b7f  lea     ecx, [rdx+0Dh]
0x180098b82  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180098b87  xor     edx, edx; Val
0x180098b89  lea     rcx, [rsp+270h+EventTrace]; void *
0x180098b8e  mov     r8d, 140h; Size
0x180098b94  call    memset_0
0x180098b99  mov     eax, [rbp+170h+arg_20]
0x180098b9f  lea     rcx, [rbp+170h+arg_28]
0x180098ba6  movups  xmm0, xmmword ptr [rdi]
0x180098ba9  mov     dword ptr [rsp+270h+EventTrace.4], eax
0x180098bad  lea     rdi, [rbp+170h+var_1C0]
0x180098bb1  lea     rax, [rsp+270h+var_220]
0x180098bb6  mov     dword ptr [rbp+170h+EventTrace.28h+4], 120000h
0x180098bbd  movdqu  xmmword ptr [rbp+170h+EventTrace.18h], xmm0
0x180098bc2  mov     [rbp+170h+var_1D0], rax
0x180098bc6  mov     [rbp+170h+var_1C8], 4
0x180098bcd  mov     eax, [rcx]
0x180098bcf  mov     [rdi+8], eax
0x180098bd2  test    eax, eax
0x180098bd4  jz      short loc_180098BF1
0x180098bd6  mov     rax, [rcx+8]
0x180098bda  add     rcx, 10h
0x180098bde  mov     [rdi], rax
0x180098be1  add     rdi, 10h
0x180098be5  lea     rax, [rbp+170h+var_D0]
0x180098bec  cmp     rdi, rax
0x180098bef  jb      short loc_180098BCD
0x180098bf1  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180098bf8  test    rcx, rcx
0x180098bfb  jz      short loc_180098C1A
0x180098bfd  mov     rax, [rcx]
0x180098c00  lea     rdx, [rsp+270h+pv]
0x180098c05  mov     rax, [rax+38h]
0x180098c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098c0e  mov     rax, [rsp+270h+pv]
0x180098c13  test    rax, rax
0x180098c16  cmovnz  r15, rax
0x180098c1a  lea     rax, [rbp+170h+var_D0]
0x180098c21  cmp     rdi, rax
0x180098c24  jnb     short loc_180098C41
0x180098c26  inc     rsi
0x180098c29  cmp     [r15+rsi*2], r12w
0x180098c2e  jnz     short loc_180098C26
0x180098c30  lea     eax, ds:2[rsi*2]
0x180098c37  mov     [rdi], r15
0x180098c3a  mov     [rdi+8], eax
0x180098c3d  add     rdi, 10h
0x180098c41  mov     rcx, [r13+650h]; TraceHandle
0x180098c48  lea     rax, [rsp+270h+EventTrace]
0x180098c4d  sub     edi, eax
0x180098c4f  lea     rdx, [rsp+270h+EventTrace]; EventTrace
0x180098c54  mov     dword ptr [rsp+270h+EventTrace.Size], edi
0x180098c58  call    cs:__imp_TraceEvent
0x180098c5e  mov     r15d, 0F424Ah
0x180098c64  cmp     eax, 8
0x180098c67  jnz     loc_180098D16
0x180098c6d  lea     r12d, [rax-7]
0x180098c71  mov     r9d, cs:?g_dwNumTraceSleepIntervals@@3KA; ulong g_dwNumTraceSleepIntervals
0x180098c78  cmp     r9d, r15d
0x180098c7b  ja      short loc_180098C93
0x180098c7d  mov     r14d, r12d
0x180098c80  lock xadd cs:?g_dwNumTraceSleepIntervals@@3KA, r14d; ulong g_dwNumTraceSleepIntervals
0x180098c89  mov     r9d, cs:?g_dwNumTraceSleepIntervals@@3KA; ulong g_dwNumTraceSleepIntervals
0x180098c90  add     r14d, r12d
0x180098c93  cmp     r14d, cs:?g_dwTraceSleepIntervalsLimit@@3KA; ulong g_dwTraceSleepIntervalsLimit
0x180098c9a  jnz     short loc_180098CED
0x180098c9c  lea     r8, aD; "%d"
0x180098ca3  mov     edx, 64h ; 'd'; unsigned __int64
0x180098ca8  lea     rcx, [rbp+170h+var_C0]; char *
0x180098caf  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180098cb4  mov     edx, 0Dh; unsigned __int16
0x180098cb9  lea     rax, [rsp+270h+var_210]
0x180098cbe  mov     [rsp+270h+var_240], rax; char **
0x180098cc3  mov     r8d, 0C0001149h; unsigned int
0x180098cc9  mov     [rsp+270h+var_250], r12w; unsigned __int16
0x180098ccf  lea     ecx, [rdx-0Bh]; unsigned __int16
0x180098cd2  call    ?DtcWriteToEventLoggerExUnFilteredA@@YAJGGKPEAXGKPEAPEBD0H@Z; DtcWriteToEventLoggerExUnFilteredA(ushort,ushort,ulong,void *,ushort,ulong,char const * *,void *,int)
0x180098cd7  mov     eax, cs:?g_dwTraceSleepIntervalsLimit@@3KA; ulong g_dwTraceSleepIntervalsLimit
0x180098cdd  lea     ecx, [rax+rax*4]
0x180098ce0  add     ecx, ecx
0x180098ce2  cmp     ecx, r15d
0x180098ce5  ja      short loc_180098CED
0x180098ce7  mov     cs:?g_dwTraceSleepIntervalsLimit@@3KA, ecx; ulong g_dwTraceSleepIntervalsLimit
0x180098ced  mov     ecx, 7D0h; dwMilliseconds
0x180098cf2  call    cs:__imp_Sleep
0x180098cf8  mov     rcx, [r13+650h]; TraceHandle
0x180098cff  lea     rdx, [rsp+270h+EventTrace]; EventTrace
0x180098d04  call    cs:__imp_TraceEvent
0x180098d0a  cmp     eax, 8
0x180098d0d  jz      loc_180098C71
0x180098d13  xor     r12d, r12d
0x180098d16  test    eax, eax
0x180098d18  jz      loc_180098DEA
0x180098d1e  cmp     cs:?g_dwNumTraceEventsLost@@3KA, r15d; ulong g_dwNumTraceEventsLost
0x180098d25  mov     edi, r12d
0x180098d28  mov     esi, 1
0x180098d2d  ja      short loc_180098D3B
0x180098d2f  mov     edi, esi
0x180098d31  lock xadd cs:?g_dwNumTraceEventsLost@@3KA, edi; ulong g_dwNumTraceEventsLost
0x180098d39  add     edi, esi
0x180098d3b  test    eax, eax
0x180098d3d  jg      short loc_180098D43
0x180098d3f  mov     ebx, eax
0x180098d41  jmp     short loc_180098D4C
0x180098d43  movzx   ebx, ax
0x180098d46  or      ebx, 80070000h
0x180098d4c  lea     rax, aTraceeventFail; "::TraceEvent Failed"
0x180098d53  mov     r9d, 34Ch
0x180098d59  mov     [rsp+270h+var_240], rax
0x180098d5e  lea     r8, aComComplusDtcD_23; "com\\complus\\dtc\\dtc\\trace\\src\\uit"...
0x180098d65  lea     rax, aCuitraceTracee; "CUITrace::TraceEvent"
0x180098d6c  mov     [rsp+270h+var_248], ebx; unsigned int
0x180098d70  mov     edx, esi
0x180098d72  mov     qword ptr [rsp+270h+var_250], rax
0x180098d77  mov     ecx, 0Eh
0x180098d7c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180098d81  cmp     edi, cs:?g_dwTraceEventsLossLimit@@3KA; ulong g_dwTraceEventsLossLimit
0x180098d87  jnz     short loc_180098DEA
0x180098d89  mov     r9d, cs:?g_dwNumTraceEventsLost@@3KA; ulong g_dwNumTraceEventsLost
0x180098d90  lea     r8, aDInternalInfor; "%d, Internal Information : latest hr = "...
0x180098d97  mov     edx, 64h ; 'd'; unsigned __int64
0x180098d9c  mov     dword ptr [rsp+270h+var_250], ebx
0x180098da0  lea     rcx, [rbp+170h+var_C0]; char *
0x180098da7  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180098dac  lea     rax, [rsp+270h+var_210]
0x180098db1  mov     edx, 0Dh; unsigned __int16
0x180098db6  mov     [rsp+270h+var_240], rax; char **
0x180098dbb  mov     ecx, esi; unsigned __int16
0x180098dbd  mov     r8d, 0C0001139h; unsigned int
0x180098dc3  mov     [rsp+270h+var_250], si; unsigned __int16
0x180098dc8  call    ?DtcWriteToEventLoggerExUnFilteredA@@YAJGGKPEAXGKPEAPEBD0H@Z; DtcWriteToEventLoggerExUnFilteredA(ushort,ushort,ulong,void *,ushort,ulong,char const * *,void *,int)
0x180098dcd  mov     eax, cs:?g_dwTraceEventsLossLimit@@3KA; ulong g_dwTraceEventsLossLimit
0x180098dd3  lea     ecx, [rax+rax*4]
0x180098dd6  add     ecx, ecx
0x180098dd8  cmp     ecx, r15d
0x180098ddb  ja      short loc_180098DEA
0x180098ddd  mov     cs:?g_dwTraceEventsLossLimit@@3KA, ecx; ulong g_dwTraceEventsLossLimit
0x180098de3  jmp     short loc_180098DEA
0x180098de5  mov     ebx, 80070057h
0x180098dea  mov     rcx, [rsp+270h+pv]; pv
0x180098def  call    cs:__imp_CoTaskMemFree
0x180098df5  mov     eax, ebx
0x180098df7  mov     rcx, [rbp+170h+var_50]
0x180098dfe  xor     rcx, rsp; StackCookie
0x180098e01  call    __security_check_cookie
0x180098e06  add     rsp, 238h
0x180098e0d  pop     r15
0x180098e0f  pop     r14
0x180098e11  pop     r13
0x180098e13  pop     r12
0x180098e15  pop     rdi
0x180098e16  pop     rsi
0x180098e17  pop     rbx
0x180098e18  pop     rbp
0x180098e19  retn
```
