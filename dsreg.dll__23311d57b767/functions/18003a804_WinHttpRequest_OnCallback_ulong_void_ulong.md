# WinHttpRequest::OnCallback(ulong,void *,ulong)

- ea: `0x18003a804`
- end: `0x18003ada4`
- name: `?OnCallback@WinHttpRequest@@IEAAJKPEAXK@Z`
- size: `1440`
- prototype: `__int64 __fastcall(WinHttpRequest *__hidden this, unsigned int, struct _WINHTTP_ASYNC_RESULT *, unsigned int)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180077440`

## callees

- `0x180005ba0`
- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x180012948`
- `0x180034f54`
- `0x18003511c`
- `0x18003a804`
- `0x18003adac`
- `0x180042a0c`
- `0x180043ef8`
- `0x180044300`
- `0x18007775c`
- `0x1800777a4`
- `0x180077834`
- `0x180079548`
- `0x180079708`
- `0x1800797e0`
- `0x18007bcb8`
- `0x18007be54`
- `0x18009029c`
- `0x1800903c8`
- `0x18009067c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a903`
- `WINHTTP!WinHttpReceiveResponse` at `0x18003a8f5`
- `WINHTTP!WinHttpReceiveResponse` at `0x18003a8f5`

## string_xrefs

- `0x18003acbe`: `Logger::WriteWinhttpCallbackCancelledEvent`
- `0x18003acb7`: `EventWriteWinhttpCallbackCancelledEvent`
- `0x18003ad40`: `Logger::WriteWinhttpCallbackFailureEvent`
- `0x18003ad39`: `EventWriteWinhttpCallbackFailureEvent`
- `0x18003ac11`: `EventWriteWinhttpSslFailureEvent`
- `0x18003ac18`: `Logger::WriteWinhttpSslFailureEvent`
- `0x18003a9dc`: `%s: Read complete. dwSize: %d`
- `0x18003aa61`: `%s: WinHttpRequest::ReadDataTrigger failed with error code: 0x%08x`
- `0x18003aa13`: `%s: WinHttpRequest::ReadDataComplete failed with error code: 0x%08x`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::OnCallback(
        WinHttpRequest *this,
        unsigned int a2,
        struct _WINHTTP_ASYNC_RESULT *a3,
        unsigned int a4)
{
  unsigned __int64 v8; // r8
  WinHttpRequest *v9; // rcx
  signed int v10; // eax
  signed int StatusCode; // ebx
  bool v12; // sf
  unsigned __int64 v13; // r8
  const unsigned __int16 *WinHttpErrorResultName; // rax
  int v15; // eax
  int v16; // edx
  const unsigned __int16 *v17; // rcx
  __int64 v18; // r8
  const unsigned __int16 *v19; // r9
  DWORD v20; // ebx
  WinHttpRequest *v21; // rcx
  int v22; // edx
  int DataTrigger; // eax
  const unsigned __int16 *v24; // rcx
  _DWORD *v25; // r12
  void *v26; // rbp
  bool v27; // sf
  int Header; // eax
  int v29; // eax
  signed int v30; // ecx
  unsigned int v31; // ebx
  int WinhttpSslErrorCodeName; // eax
  int v33; // edx
  int v34; // ecx
  unsigned int v35; // eax
  const unsigned __int16 *WinHttpCallbackStatus; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  const WCHAR *v39; // r9
  unsigned int v40; // eax
  WinHttpRequest *v41; // rcx
  const unsigned __int16 *v42; // rax
  int v43; // edx
  const WCHAR *v44; // rcx
  unsigned int v45; // eax
  void *Block; // [rsp+30h] [rbp-468h] BYREF
  wchar_t Buffer[512]; // [rsp+40h] [rbp-458h] BYREF

  Logger::TraceVerbose((wchar_t *)L"%s: dwInternetStatus = %lu", L"WinHttpRequest::OnCallback", a2);
  if ( *((_DWORD *)this + 4) )
  {
    Logger::TraceInformation(L"%s: m_requestCanceled is TRUE.", L"WinHttpRequest::OnCallback");
    WinHttpRequest::CleanupCancelledRequest(v9, a2, a3, a4);
    return 0;
  }
  switch ( a2 )
  {
    case 0x800u:
      (*(void (__fastcall **)(WinHttpRequest *, _QWORD))(*(_QWORD *)this + 16LL))(this, *((unsigned int *)this + 40));
      return 0;
    case 0x4000u:
      DataTrigger = (*(__int64 (__fastcall **)(WinHttpRequest *, struct _WINHTTP_ASYNC_RESULT *, _QWORD))(*(_QWORD *)this + 40LL))(
                      this,
                      a3,
                      2 * a4);
      StatusCode = DataTrigger;
      if ( DataTrigger >= 0 )
        goto LABEL_77;
      v24 = L"%s: WinHttpRequest::OnRedirect failed with error code: 0x%08x";
      goto LABEL_76;
    case 0x10000u:
      v30 = *(_DWORD *)a3;
      *((_DWORD *)this + 39) = *(_DWORD *)a3;
      if ( (v30 & 2) != 0 )
      {
        v31 = 12169;
      }
      else if ( (v30 & 8) != 0 )
      {
        v31 = 12045;
      }
      else if ( (v30 & 0x10) != 0 )
      {
        v31 = 12038;
      }
      else if ( (v30 & 0x20) != 0 )
      {
        v31 = 12037;
      }
      else if ( (v30 & 4) != 0 )
      {
        v31 = 12170;
      }
      else if ( v30 >= 0 )
      {
        if ( (v30 & 1) != 0 )
        {
          v31 = 12057;
        }
        else if ( (v30 & 0x40) != 0 )
        {
          v31 = 12179;
        }
        else
        {
          v31 = v30 != 0 ? 0x2F8F : 0;
        }
      }
      else
      {
        v31 = 12157;
      }
      WinhttpSslErrorCodeName = WinHttpRequest::GetWinhttpSslErrorCodeName(v30, Buffer, v8);
      if ( WinhttpSslErrorCodeName < 0 )
        Logger::TraceWarning(
          (wchar_t *)L"%s: WinHttpRequest::GetSslErrorCodeName failed with error code: 0x%08x. Error ignored.",
          L"WinHttpRequest::OnCallback",
          (unsigned int)WinhttpSslErrorCodeName);
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
      {
        v35 = McTemplateU0qqz_EventWriteTransfer(v34, v33, v31, *((_DWORD *)this + 39), (__int64)Buffer);
        if ( v35 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteWinhttpSslFailureEvent",
            L"EventWriteWinhttpSslFailureEvent",
            v35);
      }
      Logger::TraceError(
        L"%s: SSL error code: 0x%08x. WinHTTP status: 0x%08x (%s)",
        L"WinHttpRequest::OnCallback",
        v31,
        *((unsigned int *)this + 39),
        Buffer);
      return 0;
    case 0x20000u:
      v25 = (_DWORD *)((char *)this + 140);
      v26 = 0;
      Block = 0;
      StatusCode = WinHttpRequest::QueryStatusCode(this, (unsigned int *)this + 35);
      Logger::TraceVerbose(
        (wchar_t *)L"%s: dwInternetStatus = %lu, HTTP status = %d",
        L"WinHttpRequest::OnCallback",
        0x20000,
        *((unsigned int *)this + 35));
      v27 = StatusCode < 0;
      if ( StatusCode )
      {
LABEL_43:
        if ( v27 )
          goto LABEL_77;
        Logger::TraceVerbose((wchar_t *)L"%s: Triggering the get data.", L"WinHttpRequest::OnCallback");
        goto LABEL_45;
      }
      if ( *v25 == 302 || *v25 == 307 )
      {
        Header = WinHttpRequest::QueryHeader(this, 0x21u, 0, (unsigned __int16 **)&Block);
        StatusCode = Header;
        if ( Header < 0 )
        {
          Logger::TraceError(
            L"%s: WinHttpRequest::QueryHeader failed with error code: 0x%08x",
            L"WinHttpRequest::OnCallback",
            (unsigned int)Header);
LABEL_39:
          v26 = Block;
LABEL_40:
          if ( v26 )
            operator delete(v26);
          v27 = StatusCode < 0;
          goto LABEL_43;
        }
        if ( Header )
          goto LABEL_39;
        v26 = Block;
      }
      v29 = (*(__int64 (__fastcall **)(WinHttpRequest *, _QWORD, void *))(*(_QWORD *)this + 32LL))(
              this,
              (unsigned int)*v25,
              v26);
      StatusCode = v29;
      if ( v29 < 0 )
        Logger::TraceError(
          L"%s: WinHttpRequest::OnHttpStatusReceived failed with error code: 0x%08x",
          L"WinHttpRequest::OnCallback",
          (unsigned int)v29);
      goto LABEL_40;
    case 0x40000u:
      v20 = *(_DWORD *)a3;
      Logger::TraceVerbose(
        (wchar_t *)L"%s: Data available. dwSize: %lu",
        L"WinHttpRequest::OnCallback",
        *(unsigned int *)a3);
      v21 = this;
      if ( !v20 )
      {
        v22 = 0;
LABEL_85:
        WinHttpRequest::CloseHandleTrigger(v21, v22);
        return 0;
      }
      DataTrigger = WinHttpRequest::ReadDataTrigger((HINTERNET *)this, v20);
      StatusCode = DataTrigger;
      if ( DataTrigger >= 0 )
      {
LABEL_77:
        if ( StatusCode == -2147023673 )
        {
          WinHttpCallbackStatus = WinHttpRequest::GetWinHttpCallbackStatus(a2);
          if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
          {
            v39 = &cchOriginalDestLength;
            if ( WinHttpCallbackStatus )
              v39 = WinHttpCallbackStatus;
            v40 = McTemplateU0qz_EventWriteTransfer(v38, v37, a2, v39);
            if ( v40 )
              Logger::TraceError(
                L"%s: %s failed with win32 error code: 0x%08x.",
                L"Logger::WriteWinhttpCallbackCancelledEvent",
                L"EventWriteWinhttpCallbackCancelledEvent",
                v40);
          }
          Logger::TraceInformation(L"%s: Exit code was ERROR_CANCELLED.", L"WinHttpRequest::OnCallback");
          *((_DWORD *)this + 4) = 1;
          WinHttpRequest::CleanupCancelledRequest(v41, a2, a3, a4);
          v22 = -2147023673;
        }
        else
        {
          if ( StatusCode >= 0 )
            return 0;
          v42 = WinHttpRequest::GetWinHttpCallbackStatus(a2);
          if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
          {
            v44 = &cchOriginalDestLength;
            if ( v42 )
              v44 = v42;
            v45 = McTemplateU0qdz_EventWriteTransfer((_DWORD)v44, v43, a2, StatusCode, (__int64)v44);
            if ( v45 )
              Logger::TraceError(
                L"%s: %s failed with win32 error code: 0x%08x.",
                L"Logger::WriteWinhttpCallbackFailureEvent",
                L"EventWriteWinhttpCallbackFailureEvent",
                v45);
          }
          Logger::TraceError(
            L"%s: The callback handling failed with error code: 0x%08x",
            L"WinHttpRequest::OnCallback",
            (unsigned int)StatusCode);
          v22 = StatusCode;
        }
        v21 = this;
        goto LABEL_85;
      }
      v24 = L"%s: WinHttpRequest::ReadDataTrigger failed with error code: 0x%08x";
LABEL_76:
      Logger::TraceError(v24, L"WinHttpRequest::OnCallback", (unsigned int)DataTrigger);
      goto LABEL_77;
    case 0x80000u:
      Logger::TraceVerbose((wchar_t *)L"%s: Read complete. dwSize: %d", L"WinHttpRequest::OnCallback", a4);
      if ( !a4 )
      {
        StatusCode = 0;
        WinHttpRequest::CloseHandleTrigger(this, 0);
        goto LABEL_77;
      }
      StatusCode = WinHttpRequest::ReadDataComplete(this, a4, (char *)a3);
      operator delete(a3);
      if ( StatusCode < 0 )
      {
        Logger::TraceError(
          L"%s: WinHttpRequest::ReadDataComplete failed with error code: 0x%08x",
          L"WinHttpRequest::OnCallback",
          (unsigned int)StatusCode);
        goto LABEL_77;
      }
LABEL_45:
      v10 = WinHttpRequest::QueryDataTrigger(this);
LABEL_46:
      StatusCode = v10;
      goto LABEL_77;
  }
  if ( a2 != 0x200000 )
  {
    if ( a2 == 0x400000 )
    {
      if ( WinHttpReceiveResponse(*((HINTERNET *)this + 1), 0) )
        return 0;
      StatusCode = GetLastError();
      Logger::WriteWinhttpReadFailureEvent(StatusCode);
      Logger::TraceError(
        L"%s: WinHttpReceiveResponse failed with error code: 0x%08x",
        L"WinHttpRequest::ReceiveResponseTrigger",
        (unsigned int)StatusCode);
      v12 = StatusCode < 0;
      if ( StatusCode > 0 )
      {
        StatusCode = (unsigned __int16)StatusCode | 0x80070000;
        v12 = StatusCode < 0;
      }
      if ( v12 )
        Logger::TraceError(
          L"%s: WinHttpRequest::ReceiveResponseTrigger failed with error code: 0x%08x",
          L"WinHttpRequest::OnCallback",
          (unsigned int)StatusCode);
      goto LABEL_77;
    }
    if ( a2 != 0x1000000 )
      return 0;
    v10 = WinHttpRequest::CompleteAutoProxySendRequest((DWORD_PTR)this, 0x1000000u, 0);
    goto LABEL_46;
  }
  if ( *((_DWORD *)this + 41)
    || *(_QWORD *)a3 != 6 && (*(_QWORD *)a3 != 5 || *((_DWORD *)this + 16) != 1)
    || (int)WinHttpRequest::CompleteAutoProxySendRequest((DWORD_PTR)this, 0x200000u, a3) < 0 )
  {
    v13 = *(_QWORD *)a3;
    *((_QWORD *)this + 18) = *(_QWORD *)a3;
    *((_DWORD *)this + 38) = *((_DWORD *)a3 + 2);
    WinHttpErrorResultName = WinHttpRequest::GetWinHttpErrorResultName(v13);
    v15 = IsEmptyString(WinHttpErrorResultName);
    v19 = L"Unknown";
    if ( !v15 )
      v19 = v17;
    Logger::TraceError(
      L"%s: WINHTTP_ASYNC_RESULT dwResult: %d (%s), dwError: 0x%08x",
      L"WinHttpRequest::OnCallback",
      v18,
      v19,
      v16);
    v10 = (*(__int64 (__fastcall **)(WinHttpRequest *, _QWORD, _QWORD))(*(_QWORD *)this + 8LL))(
            this,
            *(_QWORD *)a3,
            *((unsigned int *)a3 + 2));
    goto LABEL_46;
  }
  return 0;
}

```

## disassembly

```asm
0x18003a804  push    rbx
0x18003a806  push    rbp
0x18003a807  push    rsi
0x18003a808  push    rdi
0x18003a809  push    r12
0x18003a80b  push    r13
0x18003a80d  push    r14
0x18003a80f  push    r15
0x18003a811  sub     rsp, 458h
0x18003a818  mov     rax, cs:__security_cookie
0x18003a81f  xor     rax, rsp
0x18003a822  mov     [rsp+498h+var_58], rax
0x18003a82a  mov     r14, r8
0x18003a82d  lea     r13, aWinhttprequest_10; "WinHttpRequest::OnCallback"
0x18003a834  mov     r8d, edx
0x18003a837  mov     esi, edx
0x18003a839  mov     rdi, rcx
0x18003a83c  mov     rdx, r13
0x18003a83f  lea     rcx, aSDwinternetsta_0; "%s: dwInternetStatus = %lu"
0x18003a846  mov     r15d, r9d
0x18003a849  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003a84e  cmp     dword ptr [rdi+10h], 0
0x18003a852  jz      short loc_18003A875
0x18003a854  mov     rdx, r13
0x18003a857  lea     rcx, aSMRequestcance; "%s: m_requestCanceled is TRUE."
0x18003a85e  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x18003a863  mov     r9d, r15d; unsigned int
0x18003a866  mov     r8, r14; void *
0x18003a869  mov     edx, esi; unsigned int
0x18003a86b  call    ?CleanupCancelledRequest@WinHttpRequest@@AEAAXKPEAXK@Z; WinHttpRequest::CleanupCancelledRequest(ulong,void *,ulong)
0x18003a870  jmp     loc_18003AD7E
0x18003a875  cmp     esi, 800h
0x18003a87b  jz      loc_18003AD69
0x18003a881  cmp     esi, 4000h
0x18003a887  jz      loc_18003AC53
0x18003a88d  cmp     esi, 10000h
0x18003a893  jz      loc_18003AB54
0x18003a899  cmp     esi, 20000h
0x18003a89f  jz      loc_18003AA6D
0x18003a8a5  cmp     esi, 40000h
0x18003a8ab  jz      loc_18003AA2D
0x18003a8b1  cmp     esi, 80000h
0x18003a8b7  jz      loc_18003A9D9
0x18003a8bd  mov     edx, 200000h; unsigned int
0x18003a8c2  cmp     esi, edx
0x18003a8c4  jz      loc_18003A94C
0x18003a8ca  cmp     esi, 400000h
0x18003a8d0  jz      short loc_18003A8EF
0x18003a8d2  mov     edx, 1000000h; unsigned int
0x18003a8d7  cmp     esi, edx
0x18003a8d9  jnz     loc_18003AD7E
0x18003a8df  xor     r8d, r8d; struct _WINHTTP_ASYNC_RESULT *
0x18003a8e2  mov     rcx, rdi; dwContext
0x18003a8e5  call    ?CompleteAutoProxySendRequest@WinHttpRequest@@AEAAJKPEAU_WINHTTP_ASYNC_RESULT@@@Z; WinHttpRequest::CompleteAutoProxySendRequest(ulong,_WINHTTP_ASYNC_RESULT *)
0x18003a8ea  jmp     loc_18003AB16
0x18003a8ef  mov     rcx, [rdi+8]; hRequest
0x18003a8f3  xor     edx, edx; lpReserved
0x18003a8f5  call    cs:__imp_WinHttpReceiveResponse
0x18003a8fb  test    eax, eax
0x18003a8fd  jnz     loc_18003AD7E
0x18003a903  call    cs:__imp_GetLastError
0x18003a909  mov     ecx, eax; unsigned int
0x18003a90b  mov     ebx, eax
0x18003a90d  call    ?WriteWinhttpReadFailureEvent@Logger@@SAJK@Z; Logger::WriteWinhttpReadFailureEvent(ulong)
0x18003a912  mov     r8d, ebx
0x18003a915  lea     rdx, aWinhttprequest_16; "WinHttpRequest::ReceiveResponseTrigger"
0x18003a91c  lea     rcx, aSWinhttpreceiv; "%s: WinHttpReceiveResponse failed with "...
0x18003a923  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003a928  test    ebx, ebx
0x18003a92a  jle     short loc_18003A937
0x18003a92c  movzx   ebx, bx
0x18003a92f  or      ebx, 80070000h
0x18003a935  test    ebx, ebx
0x18003a937  jns     loc_18003AC81
0x18003a93d  mov     r8d, ebx
0x18003a940  lea     rcx, aSWinhttpreques_2; "%s: WinHttpRequest::ReceiveResponseTrig"...
0x18003a947  jmp     loc_18003AC79
0x18003a94c  cmp     dword ptr [rdi+0A4h], 0
0x18003a953  jnz     short loc_18003A97A
0x18003a955  cmp     qword ptr [r14], 6
0x18003a959  jz      short loc_18003A967
0x18003a95b  cmp     qword ptr [r14], 5
0x18003a95f  jnz     short loc_18003A97A
0x18003a961  cmp     dword ptr [rdi+40h], 1
0x18003a965  jnz     short loc_18003A97A
0x18003a967  mov     r8, r14; struct _WINHTTP_ASYNC_RESULT *
0x18003a96a  mov     rcx, rdi; dwContext
0x18003a96d  call    ?CompleteAutoProxySendRequest@WinHttpRequest@@AEAAJKPEAU_WINHTTP_ASYNC_RESULT@@@Z; WinHttpRequest::CompleteAutoProxySendRequest(ulong,_WINHTTP_ASYNC_RESULT *)
0x18003a972  test    eax, eax
0x18003a974  jns     loc_18003AD7E
0x18003a97a  mov     r8, [r14]
0x18003a97d  mov     [rdi+90h], r8
0x18003a984  mov     rcx, r8; unsigned __int64
0x18003a987  mov     edx, [r14+8]
0x18003a98b  mov     [rdi+98h], edx
0x18003a991  call    ?GetWinHttpErrorResultName@WinHttpRequest@@SAPEBG_K@Z; WinHttpRequest::GetWinHttpErrorResultName(unsigned __int64)
0x18003a996  mov     rcx, rax; unsigned __int16 *
0x18003a999  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18003a99e  test    eax, eax
0x18003a9a0  mov     dword ptr [rsp+498h+var_478], edx
0x18003a9a4  lea     r9, aUnknown_2; "Unknown"
0x18003a9ab  mov     rdx, r13
0x18003a9ae  cmovz   r9, rcx
0x18003a9b2  lea     rcx, aSWinhttpAsyncR; "%s: WINHTTP_ASYNC_RESULT dwResult: %d ("...
0x18003a9b9  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003a9be  mov     rax, [rdi]
0x18003a9c1  mov     rcx, rdi
0x18003a9c4  mov     r8d, [r14+8]
0x18003a9c8  mov     rdx, [r14]
0x18003a9cb  mov     rax, [rax+8]
0x18003a9cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9d4  jmp     loc_18003AB16
0x18003a9d9  mov     r8d, r15d
0x18003a9dc  lea     rcx, aSReadCompleteD; "%s: Read complete. dwSize: %d"
0x18003a9e3  mov     rdx, r13
0x18003a9e6  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003a9eb  mov     rcx, rdi; this
0x18003a9ee  test    r15d, r15d
0x18003a9f1  jz      short loc_18003AA1F
0x18003a9f3  mov     r8, r14; char *
0x18003a9f6  mov     edx, r15d; unsigned int
0x18003a9f9  call    ?ReadDataComplete@WinHttpRequest@@AEAAJKPEAD@Z; WinHttpRequest::ReadDataComplete(ulong,char *)
0x18003a9fe  mov     rcx, r14; Block
0x18003aa01  mov     ebx, eax
0x18003aa03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003aa08  test    ebx, ebx
0x18003aa0a  jns     loc_18003AB0E
0x18003aa10  mov     r8d, ebx
0x18003aa13  lea     rcx, aSWinhttpreques_5; "%s: WinHttpRequest::ReadDataComplete fa"...
0x18003aa1a  jmp     loc_18003AC79
0x18003aa1f  xor     ebx, ebx
0x18003aa21  xor     edx, edx; int
0x18003aa23  call    ?CloseHandleTrigger@WinHttpRequest@@AEAAXJ@Z; WinHttpRequest::CloseHandleTrigger(long)
0x18003aa28  jmp     loc_18003AC81
0x18003aa2d  mov     ebx, [r14]
0x18003aa30  lea     rcx, aSDataAvailable; "%s: Data available. dwSize: %lu"
0x18003aa37  mov     r8d, ebx
0x18003aa3a  mov     rdx, r13
0x18003aa3d  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003aa42  mov     rcx, rdi; this
0x18003aa45  test    ebx, ebx
0x18003aa47  jnz     short loc_18003AA50
0x18003aa49  xor     edx, edx
0x18003aa4b  jmp     loc_18003ACF9
0x18003aa50  mov     edx, ebx; unsigned int
0x18003aa52  call    ?ReadDataTrigger@WinHttpRequest@@AEAAJK@Z; WinHttpRequest::ReadDataTrigger(ulong)
0x18003aa57  mov     ebx, eax
0x18003aa59  test    eax, eax
0x18003aa5b  jns     loc_18003AC81
0x18003aa61  lea     rcx, aSWinhttpreques_6; "%s: WinHttpRequest::ReadDataTrigger fai"...
0x18003aa68  jmp     loc_18003AC76
0x18003aa6d  lea     r12, [rdi+8Ch]
0x18003aa74  xor     ebp, ebp
0x18003aa76  mov     rdx, r12; unsigned int *
0x18003aa79  mov     [rsp+498h+Block], rbp
0x18003aa7e  mov     rcx, rdi; this
0x18003aa81  call    ?QueryStatusCode@WinHttpRequest@@AEAAJPEAK@Z; WinHttpRequest::QueryStatusCode(ulong *)
0x18003aa86  mov     r9d, [r12]
0x18003aa8a  lea     rcx, aSDwinternetsta; "%s: dwInternetStatus = %lu, HTTP status"...
0x18003aa91  mov     r8d, 20000h
0x18003aa97  mov     rdx, r13
0x18003aa9a  mov     ebx, eax
0x18003aa9c  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003aaa1  test    ebx, ebx
0x18003aaa3  jnz     short loc_18003AAF9
0x18003aaa5  cmp     dword ptr [r12], 12Eh
0x18003aaad  jz      short loc_18003AAB9
0x18003aaaf  cmp     dword ptr [r12], 133h
0x18003aab7  jnz     short loc_18003AB24
0x18003aab9  xor     r8d, r8d; unsigned __int16 *
0x18003aabc  lea     r9, [rsp+498h+Block]; unsigned __int16 **
0x18003aac1  mov     rcx, rdi; this
0x18003aac4  lea     edx, [r8+21h]; unsigned int
0x18003aac8  call    ?QueryHeader@WinHttpRequest@@QEAAJKPEBGPEAPEAG@Z; WinHttpRequest::QueryHeader(ulong,ushort const *,ushort * *)
0x18003aacd  mov     ebx, eax
0x18003aacf  test    eax, eax
0x18003aad1  jns     short loc_18003AB1D
0x18003aad3  mov     r8d, eax
0x18003aad6  lea     rcx, aSWinhttpreques_3; "%s: WinHttpRequest::QueryHeader failed "...
0x18003aadd  mov     rdx, r13
0x18003aae0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003aae5  mov     rbp, [rsp+498h+Block]
0x18003aaea  test    rbp, rbp
0x18003aaed  jz      short loc_18003AAF7
0x18003aaef  mov     rcx, rbp; Block
0x18003aaf2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003aaf7  test    ebx, ebx
0x18003aaf9  js      loc_18003AC81
0x18003aaff  mov     rdx, r13
0x18003ab02  lea     rcx, aSTriggeringThe; "%s: Triggering the get data."
0x18003ab09  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18003ab0e  mov     rcx, rdi; this
0x18003ab11  call    ?QueryDataTrigger@WinHttpRequest@@AEAAJXZ; WinHttpRequest::QueryDataTrigger(void)
0x18003ab16  mov     ebx, eax
0x18003ab18  jmp     loc_18003AC81
0x18003ab1d  jnz     short loc_18003AAE5
0x18003ab1f  mov     rbp, [rsp+498h+Block]
0x18003ab24  mov     rax, [rdi]
0x18003ab27  mov     r8, rbp
0x18003ab2a  mov     edx, [r12]
0x18003ab2e  mov     rcx, rdi
0x18003ab31  mov     rax, [rax+20h]
0x18003ab35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab3a  mov     ebx, eax
0x18003ab3c  test    eax, eax
0x18003ab3e  jns     short loc_18003AAEA
0x18003ab40  mov     r8d, eax
0x18003ab43  lea     rcx, aSWinhttpreques_0; "%s: WinHttpRequest::OnHttpStatusReceive"...
0x18003ab4a  mov     rdx, r13
0x18003ab4d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003ab52  jmp     short loc_18003AAEA
0x18003ab54  mov     ecx, [r14]; unsigned int
0x18003ab57  mov     [rdi+9Ch], ecx
0x18003ab5d  test    cl, 2
0x18003ab60  jz      short loc_18003AB69
0x18003ab62  mov     ebx, 2F89h
0x18003ab67  jmp     short loc_18003ABC8
0x18003ab69  test    cl, 8
0x18003ab6c  jz      short loc_18003AB75
0x18003ab6e  mov     ebx, 2F0Dh
0x18003ab73  jmp     short loc_18003ABC8
0x18003ab75  test    cl, 10h
0x18003ab78  jz      short loc_18003AB81
0x18003ab7a  mov     ebx, 2F06h
0x18003ab7f  jmp     short loc_18003ABC8
0x18003ab81  test    cl, 20h
0x18003ab84  jz      short loc_18003AB8D
0x18003ab86  mov     ebx, 2F05h
0x18003ab8b  jmp     short loc_18003ABC8
0x18003ab8d  test    cl, 4
0x18003ab90  jz      short loc_18003AB99
0x18003ab92  mov     ebx, 2F8Ah
0x18003ab97  jmp     short loc_18003ABC8
0x18003ab99  test    ecx, ecx
0x18003ab9b  jns     short loc_18003ABA4
0x18003ab9d  mov     ebx, 2F7Dh
0x18003aba2  jmp     short loc_18003ABC8
0x18003aba4  test    cl, 1
0x18003aba7  jz      short loc_18003ABB0
0x18003aba9  mov     ebx, 2F19h
0x18003abae  jmp     short loc_18003ABC8
0x18003abb0  test    cl, 40h
0x18003abb3  jz      short loc_18003ABBC
0x18003abb5  mov     ebx, 2F93h
0x18003abba  jmp     short loc_18003ABC8
0x18003abbc  mov     eax, ecx
0x18003abbe  neg     eax
0x18003abc0  sbb     ebx, ebx
0x18003abc2  and     ebx, 2F8Fh
0x18003abc8  lea     rdx, [rsp+498h+Buffer]; Buffer
0x18003abcd  call    ?GetWinhttpSslErrorCodeName@WinHttpRequest@@SAJKPEAG_K@Z; WinHttpRequest::GetWinhttpSslErrorCodeName(ulong,ushort *,unsigned __int64)
0x18003abd2  test    eax, eax
0x18003abd4  jns     short loc_18003ABE8
0x18003abd6  mov     r8d, eax
0x18003abd9  lea     rcx, aSWinhttpreques; "%s: WinHttpRequest::GetSslErrorCodeName"...
0x18003abe0  mov     rdx, r13
0x18003abe3  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x18003abe8  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18003abef  jz      short loc_18003AC2B
0x18003abf1  mov     r9d, [rdi+9Ch]
0x18003abf8  lea     rax, [rsp+498h+Buffer]
0x18003abfd  mov     r8d, ebx
0x18003ac00  mov     [rsp+498h+var_478], rax
0x18003ac05  call    McTemplateU0qqz_EventWriteTransfer
0x18003ac0a  test    eax, eax
0x18003ac0c  jz      short loc_18003AC2B
0x18003ac0e  mov     r9d, eax
0x18003ac11  lea     r8, aEventwritewinh_5; "EventWriteWinhttpSslFailureEvent"
0x18003ac18  lea     rdx, aLoggerWritewin_0; "Logger::WriteWinhttpSslFailureEvent"
0x18003ac1f  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x18003ac26  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003ac2b  mov     r9d, [rdi+9Ch]
0x18003ac32  lea     rax, [rsp+498h+Buffer]
0x18003ac37  mov     r8d, ebx
0x18003ac3a  mov     [rsp+498h+var_478], rax
0x18003ac3f  mov     rdx, r13
0x18003ac42  lea     rcx, aSSslErrorCode0; "%s: SSL error code: 0x%08x. WinHTTP sta"...
0x18003ac49  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003ac4e  jmp     loc_18003AD7E
0x18003ac53  mov     rax, [rdi]
0x18003ac56  lea     r8d, [r15+r15]
0x18003ac5a  mov     rdx, r14
0x18003ac5d  mov     rcx, rdi
0x18003ac60  mov     rax, [rax+28h]
0x18003ac64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac69  mov     ebx, eax
0x18003ac6b  test    eax, eax
0x18003ac6d  jns     short loc_18003AC81
0x18003ac6f  lea     rcx, aSWinhttpreques_1; "%s: WinHttpRequest::OnRedirect failed w"...
0x18003ac76  mov     r8d, eax
0x18003ac79  mov     rdx, r13
0x18003ac7c  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18003ac81  mov     ebp, 800704C7h
0x18003ac86  cmp     ebx, ebp
0x18003ac88  jnz     short loc_18003AD00
0x18003ac8a  mov     ecx, esi; unsigned int
0x18003ac8c  call    ?GetWinHttpCallbackStatus@WinHttpRequest@@SAPEBGK@Z; WinHttpRequest::GetWinHttpCallbackStatus(ulong)
0x18003ac91  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x18003ac98  jz      short loc_18003ACD1
0x18003ac9a  test    rax, rax
  ... truncated ...
```
