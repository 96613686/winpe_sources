# WinHttpHelper::PingServer(ushort const *,int,int *,ushort * *)

- ea: `0x1800200b0`
- end: `0x18002083e`
- name: `?PingServer@WinHttpHelper@@QEAAJPEBGHPEAHPEAPEAG@Z`
- size: `1934`
- prototype: `__int64 __fastcall(WinHttpHelper *__hidden this, const unsigned __int16 *, int, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18001ffc0`

## callees

- `0x1800026d0`
- `0x18000317c`
- `0x180012f70`
- `0x1800141b0`
- `0x180019ec0`
- `0x18001e3a8`
- `0x18001e494`
- `0x1800200b0`
- `0x180021e6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020673`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020703`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020673`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020703`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800207e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020806`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800207e0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180020806`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002065a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800206ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800207cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800207f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002065a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800206ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800207cc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800207f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002028c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002029c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002041a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020574`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002028c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002029c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002041a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020566`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020574`
- `WINHTTP!WinHttpCloseHandle` at `0x180020229`
- `WINHTTP!WinHttpCloseHandle` at `0x1800207a6`
- `WINHTTP!WinHttpCloseHandle` at `0x180020229`
- `WINHTTP!WinHttpCloseHandle` at `0x1800207a6`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800205b2`
- `WINHTTP!WinHttpQueryHeaders` at `0x180020638`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800206b1`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800205b2`
- `WINHTTP!WinHttpQueryHeaders` at `0x180020638`
- `WINHTTP!WinHttpQueryHeaders` at `0x1800206b1`
- `WINHTTP!WinHttpReceiveResponse` at `0x180020544`
- `WINHTTP!WinHttpReceiveResponse` at `0x180020544`
- `WINHTTP!WinHttpSendRequest` at `0x1800203bd`
- `WINHTTP!WinHttpSendRequest` at `0x18002047d`
- `WINHTTP!WinHttpSendRequest` at `0x1800203bd`
- `WINHTTP!WinHttpSendRequest` at `0x18002047d`
- `WINHTTP!WinHttpSetOption` at `0x18002027c`
- `WINHTTP!WinHttpSetOption` at `0x18002032b`
- `WINHTTP!WinHttpSetOption` at `0x18002040a`
- `WINHTTP!WinHttpSetOption` at `0x18002027c`
- `WINHTTP!WinHttpSetOption` at `0x18002032b`
- `WINHTTP!WinHttpSetOption` at `0x18002040a`
- `WINHTTP!WinHttpOpenRequest` at `0x180020189`
- `WINHTTP!WinHttpOpenRequest` at `0x180020189`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002035c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002078f`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002035c`
- `WINHTTP!WinHttpSetStatusCallback` at `0x18002078f`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WinHttpHelper::PingServer(
        HINTERNET *this,
        const unsigned __int16 *a2,
        int a3,
        int *a4,
        unsigned __int16 **a5)
{
  wchar_t *v7; // rbx
  wchar_t *v8; // r15
  DWORD dwFlags; // eax
  void *v10; // rax
  unsigned int LastError; // ebx
  __int64 v12; // r8
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // rcx
  BOOL v18; // r15d
  signed int v19; // eax
  __int64 v20; // rcx
  DWORD v21; // eax
  __int64 v22; // r8
  signed int v23; // ecx
  int v24; // edx
  unsigned int v25; // eax
  __int64 v26; // r8
  int v27; // eax
  unsigned __int16 **v28; // r14
  DWORD v29; // ebx
  HANDLE ProcessHeap; // rax
  DWORD v31; // ecx
  int v32; // eax
  DWORD v33; // edi
  HANDLE v34; // rax
  wchar_t *v35; // rax
  wchar_t *v36; // rdi
  unsigned int v37; // edi
  HANDLE v38; // rax
  HANDLE v39; // rax
  int v40; // [rsp+40h] [rbp-C0h] BYREF
  HINTERNET hInternet; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v42; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v43; // [rsp+58h] [rbp-A8h]
  int Buffer; // [rsp+60h] [rbp-A0h] BYREF
  int v45; // [rsp+64h] [rbp-9Ch] BYREF
  int v46; // [rsp+68h] [rbp-98h] BYREF
  DWORD dwBufferLength; // [rsp+6Ch] [rbp-94h] BYREF
  const char *v48; // [rsp+70h] [rbp-90h] BYREF
  int *v49; // [rsp+78h] [rbp-88h]
  unsigned __int16 **v50; // [rsp+80h] [rbp-80h]
  _QWORD v51[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v52; // [rsp+98h] [rbp-68h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h]
  __int64 v54; // [rsp+B0h] [rbp-50h]
  int v55; // [rsp+B8h] [rbp-48h]
  char v56; // [rsp+C0h] [rbp-40h]
  char v57; // [rsp+C2h] [rbp-3Eh]
  __int64 v58; // [rsp+D0h] [rbp-30h]
  struct _EVENT_DATA_DESCRIPTOR v59; // [rsp+D8h] [rbp-28h] BYREF
  const char **v60; // [rsp+E8h] [rbp-18h]
  __int64 v61; // [rsp+F0h] [rbp-10h]
  struct _EVENT_DATA_DESCRIPTOR v62; // [rsp+F8h] [rbp-8h] BYREF
  const char **v63; // [rsp+108h] [rbp+8h]
  __int64 v64; // [rsp+110h] [rbp+10h]

  v49 = a4;
  v50 = a5;
  v40 = 0;
  v7 = 0;
  v58 = 0;
  Buffer = 256;
  v46 = 0;
  dwBufferLength = 0;
  v42 = 0;
  v8 = 0;
  v43 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v51[0] = "WinHttpHelper::PingServer";
  v51[1] = &v40;
  *a4 = 0;
  dwFlags = 256;
  if ( a3 )
  {
    dwFlags = 8388864;
    Buffer = 8388864;
  }
  v10 = WinHttpOpenRequest(this[1], L"GET", L"EnrollmentServer/Discovery.svc", L"HTTP/1.1", 0, 0, dwFlags);
  hInternet = v10;
  if ( !v10 )
  {
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80190000;
    else
      LastError = GetLastError();
    v40 = LastError;
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    {
      LODWORD(v48) = LastError;
      v63 = &v48;
      v64 = 4;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)OpenRequestFailedEvent,
        v12,
        2u,
        &v62);
      LastError = v40;
    }
    if ( hInternet )
      WinHttpCloseHandle(hInternet);
    EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v51);
    WinHttpHelper::~WinHttpHelper((WinHttpHelper *)&v52);
    return LastError;
  }
  v62.Ptr = (ULONGLONG)&hInternet;
  LOBYTE(v62.Size) = 1;
  Buffer = 2;
  if ( !WinHttpSetOption(v10, 0x3Fu, &Buffer, 4u) )
    goto LABEL_13;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
  {
    LODWORD(v48) = 0;
    v60 = &v48;
    v61 = 4;
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)HttpSendRequestDataSizeEvent,
      v15,
      2u,
      &v59);
  }
  v45 = 0;
  if ( a3 )
  {
    Buffer = 256;
    if ( !WinHttpSetOption(hInternet, 0x1Fu, &v45, 4u)
      || (*((_DWORD *)this + 8) = 0,
          WinHttpSetStatusCallback(hInternet, SecureFailureCallback, 0x10000u, 0) == (WINHTTP_STATUS_CALLBACK)-1LL) )
    {
LABEL_13:
      if ( (int)GetLastError() > 0 )
        v16 = (unsigned __int16)GetLastError() | 0x80190000;
      else
        v16 = GetLastError();
      v40 = v16;
      goto LABEL_70;
    }
  }
  v48 = "WinHttpSendRequest";
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McTemplateU0s_EventWriteTransfer(v14, EnteringScopeEvent, "WinHttpSendRequest");
  v18 = WinHttpSendRequest(hInternet, 0, 0, 0, 0, 0, (DWORD_PTR)(this + 4));
  if ( !v18 && *((_DWORD *)this + 8) == 12038 && (int)CheckCertSAN(hInternet) >= 0 )
  {
    v45 |= 0x1000u;
    if ( !WinHttpSetOption(hInternet, 0x1Fu, &v45, 4u) )
    {
      v19 = GetLastError();
      if ( v19 > 0 )
        v19 = (unsigned __int16)v19 | 0x80070000;
      v40 = v19;
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
        McTemplateU0s_EventWriteTransfer(v20, LeavingScopeEvent, "WinHttpSendRequest");
      goto LABEL_69;
    }
    v18 = WinHttpSendRequest(hInternet, 0, 0, 0, 0, 0, (DWORD_PTR)(this + 4));
  }
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 1) != 0 )
    McTemplateU0s_EventWriteTransfer(v17, LeavingScopeEvent, "WinHttpSendRequest");
  if ( !v18 )
  {
    v21 = GetLastError();
    v23 = *((_DWORD *)this + 8);
    if ( !v23 )
      v23 = v21;
    if ( (unsigned int)(v23 - 12038) <= 0x13 && (v24 = 524417, _bittest(&v24, v23 - 12038)) )
    {
      v23 = -2145910766;
    }
    else if ( v23 > 0 )
    {
      v23 = (unsigned __int16)v23 | 0x80190000;
    }
    v40 = v23;
    if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 4) != 0 )
    {
      LODWORD(v48) = v23;
      v60 = &v48;
      v61 = 4;
      McGenEventWrite_EventWriteTransfer(
        (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
        (const EVENT_DESCRIPTOR *)SendingRequestFailedEvent,
        v22,
        2u,
        &v59);
    }
    goto LABEL_69;
  }
  dwBufferLength = 4;
  if ( !WinHttpReceiveResponse(hInternet, 0)
    || !WinHttpQueryHeaders(hInternet, 0x20000013u, 0, &v46, &dwBufferLength, 0) )
  {
    goto LABEL_46;
  }
  v27 = v46;
  *v49 = v46;
  v28 = v50;
  if ( !v50 )
    goto LABEL_69;
  if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
  {
    McGenEventWrite_EventWriteTransfer(
      (REGHANDLE *)WP_ENROLLMENT_API_PROVIDER_Context,
      (const EVENT_DESCRIPTOR *)PingingServerRedirectEvent,
      v26,
      1u,
      &v62);
    v27 = v46;
  }
  *v28 = 0;
  if ( v27 != 302 )
    goto LABEL_69;
  WinHttpQueryHeaders(hInternet, 0x21u, 0, 0, &v42, 0);
  if ( !v42 || (v42 & 1) != 0 )
  {
    v40 = -2147467259;
    goto LABEL_69;
  }
  v29 = v42;
  ProcessHeap = GetProcessHeap();
  v7 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v29);
  if ( v7 )
  {
    if ( WinHttpQueryHeaders(hInternet, 0x21u, 0, v7, &v42, 0) )
    {
      v31 = v42 + 2;
      if ( v42 + 2 < v42 )
      {
        v32 = -2147024362;
        v31 = -1;
      }
      else
      {
        v32 = 0;
      }
      dwBufferLength = v31;
      v40 = v32;
      if ( v32 >= 0 )
      {
        v33 = v31;
        v34 = GetProcessHeap();
        v35 = (wchar_t *)HeapAlloc(v34, 8u, v33);
        v36 = v35;
        v8 = v35;
        if ( v35 )
        {
          o_wmemcpy_s_0(v35, (unsigned __int64)v42 >> 1, v7, (unsigned __int64)v42 >> 1);
          *(wchar_t *)((char *)v36 + (v42 & 0xFFFFFFFE)) = 0;
          v8 = 0;
          *v28 = v36;
          if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
            McTemplateU0z_EventWriteTransfer(WP_ENROLLMENT_API_PROVIDER_Context, RedirectServerReceivedEvent, v36);
        }
        else
        {
          v40 = -2147024882;
        }
        goto LABEL_70;
      }
      goto LABEL_69;
    }
LABEL_46:
    if ( (int)GetLastError() > 0 )
      v25 = (unsigned __int16)GetLastError() | 0x80190000;
    else
      v25 = GetLastError();
    v40 = v25;
    goto LABEL_69;
  }
  v40 = -2147024882;
LABEL_69:
  v8 = v43;
LABEL_70:
  v37 = v40;
  WinHttpSetStatusCallback(hInternet, 0, 0x10000u, 0);
  if ( hInternet )
    WinHttpCloseHandle(hInternet);
  EvtTraceScope::~EvtTraceScope((EvtTraceScope *)v51);
  WinHttpHelper::~WinHttpHelper((WinHttpHelper *)&v52);
  if ( v8 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, v8);
  }
  if ( v7 )
  {
    v39 = GetProcessHeap();
    HeapFree(v39, 0, v7);
  }
  return v37;
}

```

## disassembly

```asm
0x1800200b0  mov     [rsp-8+arg_8], rbx
0x1800200b5  mov     [rsp-8+arg_10], rdi
0x1800200ba  push    rbp
0x1800200bb  push    r12
0x1800200bd  push    r13
0x1800200bf  push    r14
0x1800200c1  push    r15
0x1800200c3  lea     rbp, [rsp-20h]
0x1800200c8  sub     rsp, 120h
0x1800200cf  mov     rax, cs:__security_cookie
0x1800200d6  xor     rax, rsp
0x1800200d9  mov     [rbp+40h+var_28], rax
0x1800200dd  mov     [rsp+140h+var_C8], r9
0x1800200e2  mov     r14d, r8d
0x1800200e5  mov     r13, rcx
0x1800200e8  mov     rcx, [rbp+40h+arg_20]
0x1800200ec  mov     [rbp+40h+var_C0], rcx
0x1800200f0  xor     r12d, r12d
0x1800200f3  mov     [rsp+140h+var_100], r12d
0x1800200f8  mov     ebx, r12d
0x1800200fb  mov     [rbp+40h+var_70], rbx
0x1800200ff  mov     edx, 100h
0x180020104  mov     [rsp+140h+Buffer], edx
0x180020108  mov     [rsp+140h+var_D8], r12d
0x18002010d  mov     [rsp+140h+dwBufferLength], r12d
0x180020112  mov     [rsp+140h+var_F0], r12d
0x180020117  mov     r15d, r12d
0x18002011a  mov     [rsp+140h+var_E8], r12
0x18002011f  xorps   xmm0, xmm0
0x180020122  movdqu  [rbp+40h+var_A8], xmm0
0x180020127  mov     [rbp+40h+var_98], r12
0x18002012b  mov     [rbp+40h+var_90], r12
0x18002012f  mov     [rbp+40h+var_88], r12d
0x180020133  mov     [rbp+40h+var_80], r12b
0x180020137  mov     [rbp+40h+var_7E], r12b
0x18002013b  lea     rcx, aWinhttphelperP; "WinHttpHelper::PingServer"
0x180020142  mov     [rbp+40h+var_B8], rcx
0x180020146  lea     rcx, [rsp+140h+var_100]
0x18002014b  mov     [rbp+40h+var_B0], rcx
0x18002014f  mov     [r9], r12d
0x180020152  mov     eax, edx
0x180020154  test    r8d, r8d
0x180020157  jz      short loc_180020162
0x180020159  mov     eax, 800100h
0x18002015e  mov     [rsp+140h+Buffer], eax
0x180020162  mov     [rsp+140h+dwFlags], eax; dwFlags
0x180020166  mov     [rsp+140h+ppwszAcceptTypes], r12; ppwszAcceptTypes
0x18002016b  mov     [rsp+140h+pwszReferrer], r12; pwszReferrer
0x180020170  lea     r9, pwszVersion; "HTTP/1.1"
0x180020177  lea     r8, pwszObjectName; "EnrollmentServer/Discovery.svc"
0x18002017e  lea     rdx, aGet; "GET"
0x180020185  mov     rcx, [r13+8]; hConnect
0x180020189  call    cs:__imp_WinHttpOpenRequest
0x180020190  nop     dword ptr [rax+rax+00h]
0x180020195  mov     [rsp+140h+hInternet], rax
0x18002019a  test    rax, rax
0x18002019d  jnz     loc_180020251
0x1800201a3  call    cs:__imp_GetLastError
0x1800201aa  nop     dword ptr [rax+rax+00h]
0x1800201af  test    eax, eax
0x1800201b1  jg      short loc_1800201C3
0x1800201b3  call    cs:__imp_GetLastError
0x1800201ba  nop     dword ptr [rax+rax+00h]
0x1800201bf  mov     ebx, eax
0x1800201c1  jmp     short loc_1800201D8
0x1800201c3  call    cs:__imp_GetLastError
0x1800201ca  nop     dword ptr [rax+rax+00h]
0x1800201cf  movzx   ebx, ax
0x1800201d2  or      ebx, 80190000h
0x1800201d8  mov     [rsp+140h+var_100], ebx
0x1800201dc  mov     edi, 4
0x1800201e1  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x1800201e8  jz      short loc_18002021F
0x1800201ea  mov     dword ptr [rsp+140h+var_D0], ebx
0x1800201ee  lea     rax, [rsp+140h+var_D0]
0x1800201f3  mov     [rbp+40h+var_38], rax
0x1800201f7  mov     [rbp+40h+var_30], rdi
0x1800201fb  lea     rax, [rbp+40h+var_48]
0x1800201ff  mov     [rsp+140h+pwszReferrer], rax
0x180020204  lea     r9d, [rdi-2]
0x180020208  lea     rdx, OpenRequestFailedEvent
0x18002020f  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x180020216  call    McGenEventWrite_EventWriteTransfer
0x18002021b  mov     ebx, [rsp+140h+var_100]
0x18002021f  mov     rcx, [rsp+140h+hInternet]; hInternet
0x180020224  test    rcx, rcx
0x180020227  jz      short loc_180020236
0x180020229  call    cs:__imp_WinHttpCloseHandle
0x180020230  nop     dword ptr [rax+rax+00h]
0x180020235  nop
0x180020236  lea     rcx, [rbp+40h+var_B8]; this
0x18002023a  call    ??1EvtTraceScope@@QEAA@XZ; EvtTraceScope::~EvtTraceScope(void)
0x18002023f  nop
0x180020240  lea     rcx, [rbp+40h+var_A8]; this
0x180020244  call    ??1WinHttpHelper@@QEAA@XZ; WinHttpHelper::~WinHttpHelper(void)
0x180020249  nop
0x18002024a  mov     eax, ebx
0x18002024c  jmp     loc_180020814
0x180020251  lea     rcx, [rsp+140h+hInternet]
0x180020256  mov     [rbp+40h+var_48], rcx
0x18002025a  mov     [rbp+40h+var_40], 1
0x18002025e  mov     r12d, 2
0x180020264  mov     [rsp+140h+Buffer], r12d
0x180020269  lea     edi, [r12+2]
0x18002026e  mov     r9d, edi; dwBufferLength
0x180020271  lea     r8, [rsp+140h+Buffer]; lpBuffer
0x180020276  lea     edx, [rdi+3Bh]; dwOption
0x180020279  mov     rcx, rax; hInternet
0x18002027c  call    cs:__imp_WinHttpSetOption
0x180020283  nop     dword ptr [rax+rax+00h]
0x180020288  test    eax, eax
0x18002028a  jnz     short loc_1800202C7
0x18002028c  call    cs:__imp_GetLastError
0x180020293  nop     dword ptr [rax+rax+00h]
0x180020298  test    eax, eax
0x18002029a  jg      short loc_1800202AA
0x18002029c  call    cs:__imp_GetLastError
0x1800202a3  nop     dword ptr [rax+rax+00h]
0x1800202a8  jmp     short loc_1800202BE
0x1800202aa  call    cs:__imp_GetLastError
0x1800202b1  nop     dword ptr [rax+rax+00h]
0x1800202b6  movzx   eax, ax
0x1800202b9  or      eax, 80190000h
0x1800202be  mov     [rsp+140h+var_100], eax
0x1800202c2  jmp     loc_18002077B
0x1800202c7  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x1800202ce  jz      short loc_180020304
0x1800202d0  mov     dword ptr [rsp+140h+var_D0], 0
0x1800202d8  lea     rax, [rsp+140h+var_D0]
0x1800202dd  mov     [rbp+40h+var_58], rax
0x1800202e1  mov     [rbp+40h+var_50], rdi
0x1800202e5  lea     rax, [rbp+40h+var_68]
0x1800202e9  mov     [rsp+140h+pwszReferrer], rax
0x1800202ee  mov     r9d, r12d
0x1800202f1  lea     rdx, HttpSendRequestDataSizeEvent
0x1800202f8  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x1800202ff  call    McGenEventWrite_EventWriteTransfer
0x180020304  mov     [rsp+140h+var_DC], 0
0x18002030c  test    r14d, r14d
0x18002030f  jz      short loc_180020372
0x180020311  mov     [rsp+140h+Buffer], 100h
0x180020319  mov     r9d, edi; dwBufferLength
0x18002031c  lea     r8, [rsp+140h+var_DC]; lpBuffer
0x180020321  mov     edx, 1Fh; dwOption
0x180020326  mov     rcx, [rsp+140h+hInternet]; hInternet
0x18002032b  call    cs:__imp_WinHttpSetOption
0x180020332  nop     dword ptr [rax+rax+00h]
0x180020337  test    eax, eax
0x180020339  jz      loc_18002028C
0x18002033f  mov     dword ptr [r13+20h], 0
0x180020347  xor     r9d, r9d; dwReserved
0x18002034a  mov     r8d, 10000h; dwNotificationFlags
0x180020350  lea     rdx, SecureFailureCallback; lpfnInternetCallback
0x180020357  mov     rcx, [rsp+140h+hInternet]; hInternet
0x18002035c  call    cs:__imp_WinHttpSetStatusCallback
0x180020363  nop     dword ptr [rax+rax+00h]
0x180020368  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002036c  jz      loc_18002028C
0x180020372  lea     rax, aWinhttpsendreq_0; "WinHttpSendRequest"
0x180020379  mov     [rsp+140h+var_D0], rax
0x18002037e  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x180020385  jz      short loc_180020397
0x180020387  mov     r8, rax
0x18002038a  lea     rdx, EnteringScopeEvent
0x180020391  call    McTemplateU0s_EventWriteTransfer
0x180020396  nop
0x180020397  lea     r14, [r13+20h]
0x18002039b  mov     qword ptr [rsp+140h+dwFlags], r14; dwContext
0x1800203a0  mov     dword ptr [rsp+140h+ppwszAcceptTypes], 0; dwTotalLength
0x1800203a8  mov     dword ptr [rsp+140h+pwszReferrer], 0; dwOptionalLength
0x1800203b0  xor     r9d, r9d; lpOptional
0x1800203b3  xor     r8d, r8d; dwHeadersLength
0x1800203b6  xor     edx, edx; lpszHeaders
0x1800203b8  mov     rcx, [rsp+140h+hInternet]; hRequest
0x1800203bd  call    cs:__imp_WinHttpSendRequest
0x1800203c4  nop     dword ptr [rax+rax+00h]
0x1800203c9  mov     r15d, eax
0x1800203cc  test    eax, eax
0x1800203ce  jnz     loc_18002048C
0x1800203d4  cmp     dword ptr [r14], 2F06h
0x1800203db  jnz     loc_18002048C
0x1800203e1  mov     rcx, [rsp+140h+hInternet]
0x1800203e6  call    CheckCertSAN
0x1800203eb  test    eax, eax
0x1800203ed  js      loc_18002048C
0x1800203f3  bts     [rsp+140h+var_DC], 0Ch
0x1800203f9  mov     r9d, edi; dwBufferLength
0x1800203fc  lea     r8, [rsp+140h+var_DC]; lpBuffer
0x180020401  lea     edx, [r15+1Fh]; dwOption
0x180020405  mov     rcx, [rsp+140h+hInternet]; hInternet
0x18002040a  call    cs:__imp_WinHttpSetOption
0x180020411  nop     dword ptr [rax+rax+00h]
0x180020416  test    eax, eax
0x180020418  jnz     short loc_18002045B
0x18002041a  call    cs:__imp_GetLastError
0x180020421  nop     dword ptr [rax+rax+00h]
0x180020426  test    eax, eax
0x180020428  jle     short loc_180020432
0x18002042a  movzx   eax, ax
0x18002042d  or      eax, 80070000h
0x180020432  mov     [rsp+140h+var_100], eax
0x180020436  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x18002043d  jz      loc_180020776
0x180020443  lea     r8, aWinhttpsendreq_0; "WinHttpSendRequest"
0x18002044a  lea     rdx, LeavingScopeEvent
0x180020451  call    McTemplateU0s_EventWriteTransfer
0x180020456  jmp     loc_180020776
0x18002045b  mov     qword ptr [rsp+140h+dwFlags], r14; dwContext
0x180020460  mov     dword ptr [rsp+140h+ppwszAcceptTypes], 0; dwTotalLength
0x180020468  mov     dword ptr [rsp+140h+pwszReferrer], 0; dwOptionalLength
0x180020470  xor     r9d, r9d; lpOptional
0x180020473  xor     r8d, r8d; dwHeadersLength
0x180020476  xor     edx, edx; lpszHeaders
0x180020478  mov     rcx, [rsp+140h+hInternet]; hRequest
0x18002047d  call    cs:__imp_WinHttpSendRequest
0x180020484  nop     dword ptr [rax+rax+00h]
0x180020489  mov     r15d, eax
0x18002048c  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 1
0x180020493  jz      short loc_1800204A8
0x180020495  lea     r8, aWinhttpsendreq_0; "WinHttpSendRequest"
0x18002049c  lea     rdx, LeavingScopeEvent
0x1800204a3  call    McTemplateU0s_EventWriteTransfer
0x1800204a8  test    r15d, r15d
0x1800204ab  jnz     loc_180020539
0x1800204b1  call    cs:__imp_GetLastError
0x1800204b8  nop     dword ptr [rax+rax+00h]
0x1800204bd  mov     ecx, [r13+20h]
0x1800204c1  test    ecx, ecx
0x1800204c3  cmovz   ecx, eax
0x1800204c6  lea     eax, [rcx-2F06h]
0x1800204cc  cmp     eax, 13h
0x1800204cf  ja      short loc_1800204E2
0x1800204d1  mov     edx, 80081h
0x1800204d6  bt      edx, eax
0x1800204d9  jnb     short loc_1800204E2
0x1800204db  mov     ecx, 80180012h
0x1800204e0  jmp     short loc_1800204EF
0x1800204e2  test    ecx, ecx
0x1800204e4  jle     short loc_1800204EF
0x1800204e6  movzx   ecx, cx
0x1800204e9  or      ecx, 80190000h
0x1800204ef  mov     [rsp+140h+var_100], ecx
0x1800204f3  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, dil
0x1800204fa  jz      loc_180020776
0x180020500  mov     dword ptr [rsp+140h+var_D0], ecx
0x180020504  lea     rax, [rsp+140h+var_D0]
0x180020509  mov     [rbp+40h+var_58], rax
0x18002050d  mov     [rbp+40h+var_50], 4
0x180020515  lea     rax, [rbp+40h+var_68]
0x180020519  mov     [rsp+140h+pwszReferrer], rax
0x18002051e  mov     r9d, r12d
0x180020521  lea     rdx, SendingRequestFailedEvent
0x180020528  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
0x18002052f  call    McGenEventWrite_EventWriteTransfer
0x180020534  jmp     loc_180020776
0x180020539  mov     [rsp+140h+dwBufferLength], edi
0x18002053d  xor     edx, edx; lpReserved
0x18002053f  mov     rcx, [rsp+140h+hInternet]; hRequest
0x180020544  call    cs:__imp_WinHttpReceiveResponse
0x18002054b  nop     dword ptr [rax+rax+00h]
0x180020550  xor     edi, edi
0x180020552  test    eax, eax
0x180020554  jnz     short loc_180020591
0x180020556  call    cs:__imp_GetLastError
0x18002055d  nop     dword ptr [rax+rax+00h]
0x180020562  test    eax, eax
0x180020564  jg      short loc_180020574
0x180020566  call    cs:__imp_GetLastError
0x18002056d  nop     dword ptr [rax+rax+00h]
0x180020572  jmp     short loc_180020588
0x180020574  call    cs:__imp_GetLastError
0x18002057b  nop     dword ptr [rax+rax+00h]
0x180020580  movzx   eax, ax
0x180020583  or      eax, 80190000h
0x180020588  mov     [rsp+140h+var_100], eax
0x18002058c  jmp     loc_180020776
0x180020591  mov     [rsp+140h+ppwszAcceptTypes], rdi; lpdwIndex
0x180020596  lea     rax, [rsp+140h+dwBufferLength]
0x18002059b  mov     [rsp+140h+pwszReferrer], rax; lpdwBufferLength
0x1800205a0  lea     r9, [rsp+140h+var_D8]; lpBuffer
0x1800205a5  xor     r8d, r8d; pwszName
0x1800205a8  mov     edx, 20000013h; dwInfoLevel
0x1800205ad  mov     rcx, [rsp+140h+hInternet]; hRequest
0x1800205b2  call    cs:__imp_WinHttpQueryHeaders
0x1800205b9  nop     dword ptr [rax+rax+00h]
0x1800205be  test    eax, eax
0x1800205c0  jz      short loc_180020556
0x1800205c2  mov     eax, [rsp+140h+var_D8]
0x1800205c6  mov     rcx, [rsp+140h+var_C8]
0x1800205cb  mov     [rcx], eax
0x1800205cd  mov     r14, [rbp+40h+var_C0]
0x1800205d1  test    r14, r14
0x1800205d4  jz      loc_180020776
0x1800205da  test    byte ptr cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, r12b
0x1800205e1  jz      short loc_180020609
0x1800205e3  lea     rax, [rbp+40h+var_48]
0x1800205e7  mov     [rsp+140h+pwszReferrer], rax
0x1800205ec  mov     r9d, 1
0x1800205f2  lea     rdx, PingingServerRedirectEvent
0x1800205f9  lea     rcx, WP_ENROLLMENT_API_PROVIDER_Context
  ... truncated ...
```
