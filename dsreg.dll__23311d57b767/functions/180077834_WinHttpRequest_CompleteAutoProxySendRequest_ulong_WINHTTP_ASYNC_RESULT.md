# WinHttpRequest::CompleteAutoProxySendRequest(ulong,_WINHTTP_ASYNC_RESULT *)

- ea: `0x180077834`
- end: `0x180077cfe`
- name: `?CompleteAutoProxySendRequest@WinHttpRequest@@AEAAJKPEAU_WINHTTP_ASYNC_RESULT@@@Z`
- size: `1226`
- prototype: `__int64 __fastcall(DWORD_PTR dwContext, unsigned int, struct _WINHTTP_ASYNC_RESULT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003a804`

## callees

- `0x1800084f4`
- `0x18000bac0`
- `0x180012948`
- `0x180031ae0`
- `0x180077624`
- `0x180077834`
- `0x180079548`
- `0x180079708`
- `0x180090574`
- `0x180091a30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180077c17`
- `WINHTTP!WinHttpSetOption` at `0x180077c0d`
- `WINHTTP!WinHttpSetOption` at `0x180077c0d`
- `WINHTTP!WinHttpGetProxyResult` at `0x180077b01`
- `WINHTTP!WinHttpGetProxyResult` at `0x180077b01`

## string_xrefs

- `0x180077948`: `Logger::WriteWinhttpProxyUnknownFailureEvent`
- `0x180077941`: `EventWriteWinhttpProxyUnknownFailureEvent`
- `0x180077aaa`: `EventWriteWinhttpProxySendFailureEvent`
- `0x180077ab1`: `Logger::WriteWinhttpProxySendFailureEvent`
- `0x180077bc7`: `EventWriteWinhttpProxyNoMoreEntriesEvent`
- `0x180077bce`: `Logger::WriteWinhttpProxyNoMoreEntriesEvent`
- `0x180077c9c`: `EventWriteWinhttpProxySetForRequestEvent`
- `0x180077ca3`: `Logger::WriteWinhttpProxySetForRequestEvent`
- `0x1800779f6`: `Logger::WriteWinhttpProxyWPADFailedEvent`
- `0x1800779ef`: `EventWriteWinhttpProxyWPADFailedEvent`
- `0x180077b4f`: `EventWriteWinhttpProxyWPADSuccessEvent`
- `0x180077b56`: `Logger::WriteWinhttpProxyWPADSuccessEvent`
- `0x180077843`: `WinHttpRequest::CompleteAutoProxySendRequest`
- `0x180077b6c`: `%s: Proxy configuration discovered: Proxy count: %d`

## pseudocode

```c
__int64 __fastcall WinHttpRequest::CompleteAutoProxySendRequest(
        DWORD_PTR dwContext,
        unsigned int a2,
        struct _WINHTTP_ASYNC_RESULT *a3)
{
  signed int v6; // ebx
  const unsigned __int16 *WinHttpCallbackStatus; // r14
  const unsigned __int16 *WinHttpErrorResultName; // rbp
  unsigned int v9; // ecx
  const WCHAR *v10; // rdx
  const WCHAR *v11; // rax
  unsigned int v12; // eax
  const WCHAR *v13; // rdx
  const WCHAR *v14; // rax
  unsigned int v15; // eax
  const WCHAR *v16; // rdx
  const WCHAR *v17; // rax
  unsigned int v18; // eax
  unsigned int *v19; // rsi
  signed int ProxyResult; // eax
  __int64 v21; // r9
  const wchar_t *v22; // r8
  unsigned int v23; // eax
  __int64 v24; // rax
  unsigned int v25; // eax
  signed int LastError; // eax
  __int64 v27; // rcx
  const wchar_t *v28; // r8
  __int64 v29; // rdx
  const wchar_t *v30; // r9
  unsigned int v31; // eax
  int v32; // eax
  __int64 v34; // [rsp+30h] [rbp-48h]

  Logger::TraceVerbose((wchar_t *)L"%s started", L"WinHttpRequest::CompleteAutoProxySendRequest");
  if ( a2 == 0x1000000 )
  {
    v19 = (unsigned int *)(dwContext + 72);
    ProxyResult = WinHttpGetProxyResult(
                    *(HINTERNET *)(*(_QWORD *)(dwContext + 120) + 8LL),
                    (WINHTTP_PROXY_RESULT *)(dwContext + 72));
    v6 = ProxyResult;
    if ( ProxyResult > 0 )
      v6 = (unsigned __int16)ProxyResult | 0x80070000;
    if ( v6 < 0 )
    {
      v21 = (unsigned int)v6;
      v22 = L"WinHttpGetProxyResult";
      goto LABEL_74;
    }
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v23 = McTemplateU0q_EventWriteTransfer(
              &UserDeviceRegistrationEventProvider_Context,
              WinhttpProxyWPADSuccessEvent,
              *v19);
      if ( v23 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteWinhttpProxyWPADSuccessEvent",
          L"EventWriteWinhttpProxyWPADSuccessEvent",
          v23);
    }
    Logger::TraceInformation(
      L"%s: Proxy configuration discovered: Proxy count: %d",
      L"WinHttpRequest::CompleteAutoProxySendRequest",
      *v19);
    if ( *v19 )
      *(_DWORD *)(dwContext + 64) = 1;
  }
  else
  {
    if ( !a3 )
    {
      v6 = -2147024809;
      Logger::TraceError(L"%s: Invalid arguments. Code: %d", L"WinHttpRequest::CompleteAutoProxySendRequest", a2);
      goto LABEL_75;
    }
    WinHttpCallbackStatus = WinHttpRequest::GetWinHttpCallbackStatus(a2);
    WinHttpErrorResultName = WinHttpRequest::GetWinHttpErrorResultName(*(_QWORD *)a3);
    if ( *(_QWORD *)a3 == 6 )
    {
      v9 = *((_DWORD *)a3 + 2);
      if ( v9 > 0x2EF1 )
      {
        if ( v9 != 12166 && v9 != 12167 && v9 != 12178 && v9 != 12180 )
          goto LABEL_12;
      }
      else if ( v9 != 12017 && v9 && v9 != 87 && v9 != 12002 && v9 != 12006 && v9 != 12015 )
      {
LABEL_12:
        if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
        {
          v10 = &cchOriginalDestLength;
          v11 = &cchOriginalDestLength;
          if ( WinHttpErrorResultName )
            v11 = WinHttpErrorResultName;
          if ( WinHttpCallbackStatus )
            v10 = WinHttpCallbackStatus;
          v12 = McTemplateU0qxqzz_EventWriteTransfer(
                  *((_DWORD *)a3 + 2),
                  (unsigned int)WinhttpProxyUnknownFailureEvent,
                  a2,
                  *(_QWORD *)a3,
                  *((_DWORD *)a3 + 2),
                  (__int64)v10,
                  (__int64)v11);
          if ( v12 )
            Logger::TraceError(
              L"%s: %s failed with win32 error code: 0x%08x.",
              L"Logger::WriteWinhttpProxyUnknownFailureEvent",
              L"EventWriteWinhttpProxyUnknownFailureEvent",
              v12);
        }
        LODWORD(v34) = *((_DWORD *)a3 + 2);
        Logger::TraceError(
          L"%s: Unexpected error. dwInternetStatus: 0x%08x (%s). dwResult: %d (%s). dwError: 0x%08x.",
          L"WinHttpRequest::CompleteAutoProxySendRequest",
          a2,
          WinHttpCallbackStatus,
          *(_QWORD *)a3,
          WinHttpErrorResultName,
          v34);
        v6 = -2147467259;
        goto LABEL_75;
      }
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
      {
        v13 = &cchOriginalDestLength;
        v14 = &cchOriginalDestLength;
        if ( WinHttpErrorResultName )
          v14 = WinHttpErrorResultName;
        if ( WinHttpCallbackStatus )
          v13 = WinHttpCallbackStatus;
        v15 = McTemplateU0qxqzz_EventWriteTransfer(
                v9,
                (unsigned int)WinhttpProxyWPADFailedEvent,
                a2,
                6,
                v9,
                (__int64)v13,
                (__int64)v14);
        if ( v15 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteWinhttpProxyWPADFailedEvent",
            L"EventWriteWinhttpProxyWPADFailedEvent",
            v15);
      }
      LODWORD(v34) = *((_DWORD *)a3 + 2);
      Logger::TraceInformation(
        L"%s: Proxy discovery did not find proxy. dwInternetStatus: 0x%08x (%s). dwResult: %d (%s). dwError: 0x%08x.",
        L"WinHttpRequest::CompleteAutoProxySendRequest",
        a2,
        WinHttpCallbackStatus,
        *(_QWORD *)a3,
        WinHttpErrorResultName,
        v34);
    }
    else
    {
      if ( *(_QWORD *)a3 != 5
        || *((_DWORD *)a3 + 2) != 12002
        && *((_DWORD *)a3 + 2) != 12007
        && (unsigned int)(*((_DWORD *)a3 + 2) - 12029) > 1 )
      {
        goto LABEL_12;
      }
      if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
      {
        v16 = &cchOriginalDestLength;
        v17 = &cchOriginalDestLength;
        if ( WinHttpErrorResultName )
          v17 = WinHttpErrorResultName;
        if ( WinHttpCallbackStatus )
          v16 = WinHttpCallbackStatus;
        v18 = McTemplateU0qxqzz_EventWriteTransfer(
                *((_DWORD *)a3 + 2),
                (unsigned int)WinhttpProxySendFailureEvent,
                a2,
                5,
                *((_DWORD *)a3 + 2),
                (__int64)v16,
                (__int64)v17);
        if ( v18 )
          Logger::TraceError(
            L"%s: %s failed with win32 error code: 0x%08x.",
            L"Logger::WriteWinhttpProxySendFailureEvent",
            L"EventWriteWinhttpProxySendFailureEvent",
            v18);
      }
      LODWORD(v34) = *((_DWORD *)a3 + 2);
      Logger::TraceError(
        L"%s: Proxy send error. dwInternetStatus: 0x%08x (%s). dwResult: %d (%s). dwError: 0x%08x.",
        L"WinHttpRequest::CompleteAutoProxySendRequest",
        a2,
        WinHttpCallbackStatus,
        *(_QWORD *)a3,
        WinHttpErrorResultName,
        v34);
    }
  }
  if ( !*(_DWORD *)(dwContext + 64) )
  {
LABEL_72:
    v32 = WinHttpRequest::BeginSendRequest(dwContext);
    v6 = v32;
    if ( v32 >= 0 )
      goto LABEL_75;
    v21 = (unsigned int)v32;
    v22 = L"BeginSendRequest";
LABEL_74:
    Logger::TraceError(
      L"%s: %s failed with error code: 0x%08x.",
      L"WinHttpRequest::CompleteAutoProxySendRequest",
      v22,
      v21);
    goto LABEL_75;
  }
  v24 = *(unsigned int *)(dwContext + 68);
  if ( *(_DWORD *)(dwContext + 72) > (unsigned int)v24 )
  {
    if ( !WinHttpSetOption(
            *(HINTERNET *)(dwContext + 8),
            0x27u,
            (LPVOID)(*(_QWORD *)(dwContext + 80) + 32 * v24),
            0x20u) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      if ( v6 < 0 )
      {
        v21 = (unsigned int)v6;
        v22 = L"WinHttpSetOption";
        goto LABEL_74;
      }
    }
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 1) != 0 )
    {
      v27 = *(_QWORD *)(dwContext + 80);
      v28 = L"TRUE";
      v29 = 32LL * *(unsigned int *)(dwContext + 68);
      v30 = L"TRUE";
      if ( !*(_DWORD *)(v29 + v27 + 4) )
        v30 = L"FALSE";
      if ( !*(_DWORD *)(v29 + v27) )
        v28 = L"FALSE";
      v31 = McTemplateU0zzqzq_EventWriteTransfer(
              v27,
              v29,
              (_DWORD)v28,
              (_DWORD)v30,
              *(_DWORD *)(v29 + v27 + 8),
              *(_QWORD *)(v29 + v27 + 16),
              *(_WORD *)(v29 + v27 + 24));
      if ( v31 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteWinhttpProxySetForRequestEvent",
          L"EventWriteWinhttpProxySetForRequestEvent",
          v31);
    }
    ++*(_DWORD *)(dwContext + 68);
    goto LABEL_72;
  }
  v6 = -2147024637;
  if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
  {
    v25 = McTemplateU0q_EventWriteTransfer(
            &UserDeviceRegistrationEventProvider_Context,
            WinhttpProxyNoMoreEntriesEvent,
            2147942659LL);
    if ( v25 )
      Logger::TraceError(
        L"%s: %s failed with win32 error code: 0x%08x.",
        L"Logger::WriteWinhttpProxyNoMoreEntriesEvent",
        L"EventWriteWinhttpProxyNoMoreEntriesEvent",
        v25);
  }
  Logger::TraceError(
    L"%s: No more out-bound proxy servers are available for this request.",
    L"WinHttpRequest::CompleteAutoProxySendRequest");
LABEL_75:
  Logger::TraceVerbose((wchar_t *)L"%s finished", L"WinHttpRequest::CompleteAutoProxySendRequest");
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180077834  push    rbx
0x180077836  push    rbp
0x180077837  push    rsi
0x180077838  push    rdi
0x180077839  push    r14
0x18007783b  push    r15
0x18007783d  sub     rsp, 48h
0x180077841  mov     esi, edx
0x180077843  lea     r15, aWinhttprequest_15; "WinHttpRequest::CompleteAutoProxySendRe"...
0x18007784a  mov     rdi, rcx
0x18007784d  mov     rdx, r15
0x180077850  lea     rcx, aSStarted; "%s started"
0x180077857  mov     rbx, r8
0x18007785a  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x18007785f  cmp     esi, 1000000h
0x180077865  jz      loc_180077AF2
0x18007786b  test    rbx, rbx
0x18007786e  jnz     short loc_18007788C
0x180077870  mov     r8d, esi
0x180077873  lea     rcx, aSInvalidArgume_0; "%s: Invalid arguments. Code: %d"
0x18007787a  mov     rdx, r15
0x18007787d  mov     ebx, 80070057h
0x180077882  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077887  jmp     loc_180077CE0
0x18007788c  mov     ecx, esi; unsigned int
0x18007788e  call    ?GetWinHttpCallbackStatus@WinHttpRequest@@SAPEBGK@Z; WinHttpRequest::GetWinHttpCallbackStatus(ulong)
0x180077893  mov     rcx, [rbx]; unsigned __int64
0x180077896  mov     r14, rax
0x180077899  call    ?GetWinHttpErrorResultName@WinHttpRequest@@SAPEBG_K@Z; WinHttpRequest::GetWinHttpErrorResultName(unsigned __int64)
0x18007789e  mov     r9d, 6
0x1800778a4  mov     rbp, rax
0x1800778a7  cmp     [rbx], r9
0x1800778aa  jnz     loc_180077A37
0x1800778b0  mov     ecx, [rbx+8]
0x1800778b3  mov     eax, 2EF1h
0x1800778b8  cmp     ecx, eax
0x1800778ba  ja      loc_18007798E
0x1800778c0  jz      loc_1800779AA
0x1800778c6  mov     eax, ecx
0x1800778c8  test    ecx, ecx
0x1800778ca  jz      loc_1800779AA
0x1800778d0  sub     eax, 57h ; 'W'
0x1800778d3  jz      loc_1800779AA
0x1800778d9  sub     eax, 2E8Bh
0x1800778de  jz      loc_1800779AA
0x1800778e4  sub     eax, 4
0x1800778e7  jz      loc_1800779AA
0x1800778ed  cmp     eax, 9
0x1800778f0  jz      loc_1800779AA
0x1800778f6  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x1800778fd  jz      short loc_18007795B
0x1800778ff  mov     ecx, [rbx+8]
0x180077902  lea     rdx, cchOriginalDestLength
0x180077909  mov     r9, [rbx]
0x18007790c  mov     rax, rdx
0x18007790f  test    rbp, rbp
0x180077912  mov     r8d, esi
0x180077915  cmovnz  rax, rbp
0x180077919  test    r14, r14
0x18007791c  mov     [rsp+78h+var_48], rax
0x180077921  cmovnz  rdx, r14
0x180077925  mov     [rsp+78h+var_50], rdx
0x18007792a  lea     rdx, WinhttpProxyUnknownFailureEvent
0x180077931  mov     dword ptr [rsp+78h+var_58], ecx
0x180077935  call    McTemplateU0qxqzz_EventWriteTransfer
0x18007793a  test    eax, eax
0x18007793c  jz      short loc_18007795B
0x18007793e  mov     r9d, eax
0x180077941  lea     r8, aEventwritewinh_7; "EventWriteWinhttpProxyUnknownFailureEve"...
0x180077948  lea     rdx, aLoggerWritewin_13; "Logger::WriteWinhttpProxyUnknownFailure"...
0x18007794f  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180077956  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18007795b  mov     eax, [rbx+8]
0x18007795e  lea     rcx, aSUnexpectedErr; "%s: Unexpected error. dwInternetStatus:"...
0x180077965  mov     dword ptr [rsp+78h+var_48], eax
0x180077969  mov     r9, r14
0x18007796c  mov     rax, [rbx]
0x18007796f  mov     r8d, esi
0x180077972  mov     [rsp+78h+var_50], rbp
0x180077977  mov     rdx, r15
0x18007797a  mov     [rsp+78h+var_58], rax
0x18007797f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077984  mov     ebx, 80004005h
0x180077989  jmp     loc_180077CE0
0x18007798e  mov     eax, ecx
0x180077990  sub     eax, 2F86h
0x180077995  jz      short loc_1800779AA
0x180077997  sub     eax, 1
0x18007799a  jz      short loc_1800779AA
0x18007799c  sub     eax, 0Bh
0x18007799f  jz      short loc_1800779AA
0x1800779a1  cmp     eax, 2
0x1800779a4  jnz     loc_1800778F6
0x1800779aa  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x1800779b1  jz      short loc_180077A09
0x1800779b3  lea     rdx, cchOriginalDestLength
0x1800779ba  test    rbp, rbp
0x1800779bd  mov     rax, rdx
0x1800779c0  mov     r8d, esi
0x1800779c3  cmovnz  rax, rbp
0x1800779c7  test    r14, r14
0x1800779ca  mov     [rsp+78h+var_48], rax
0x1800779cf  cmovnz  rdx, r14
0x1800779d3  mov     [rsp+78h+var_50], rdx
0x1800779d8  lea     rdx, WinhttpProxyWPADFailedEvent
0x1800779df  mov     dword ptr [rsp+78h+var_58], ecx
0x1800779e3  call    McTemplateU0qxqzz_EventWriteTransfer
0x1800779e8  test    eax, eax
0x1800779ea  jz      short loc_180077A09
0x1800779ec  mov     r9d, eax
0x1800779ef  lea     r8, aEventwritewinh_4; "EventWriteWinhttpProxyWPADFailedEvent"
0x1800779f6  lea     rdx, aLoggerWritewin_11; "Logger::WriteWinhttpProxyWPADFailedEven"...
0x1800779fd  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180077a04  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077a09  mov     eax, [rbx+8]
0x180077a0c  lea     rcx, aSProxyDiscover; "%s: Proxy discovery did not find proxy."...
0x180077a13  mov     dword ptr [rsp+78h+var_48], eax
0x180077a17  mov     r9, r14
0x180077a1a  mov     rax, [rbx]
0x180077a1d  mov     r8d, esi
0x180077a20  mov     [rsp+78h+var_50], rbp
0x180077a25  mov     rdx, r15
0x180077a28  mov     [rsp+78h+var_58], rax
0x180077a2d  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180077a32  jmp     loc_180077B87
0x180077a37  mov     r9d, 5
0x180077a3d  cmp     [rbx], r9
0x180077a40  jnz     loc_1800778F6
0x180077a46  mov     ecx, [rbx+8]
0x180077a49  mov     eax, ecx
0x180077a4b  sub     eax, 2EE2h
0x180077a50  jz      short loc_180077A65
0x180077a52  sub     eax, r9d
0x180077a55  jz      short loc_180077A65
0x180077a57  sub     eax, 16h
0x180077a5a  jz      short loc_180077A65
0x180077a5c  cmp     eax, 1
0x180077a5f  jnz     loc_1800778F6
0x180077a65  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180077a6c  jz      short loc_180077AC4
0x180077a6e  lea     rdx, cchOriginalDestLength
0x180077a75  test    rbp, rbp
0x180077a78  mov     rax, rdx
0x180077a7b  mov     r8d, esi
0x180077a7e  cmovnz  rax, rbp
0x180077a82  test    r14, r14
0x180077a85  mov     [rsp+78h+var_48], rax
0x180077a8a  cmovnz  rdx, r14
0x180077a8e  mov     [rsp+78h+var_50], rdx
0x180077a93  lea     rdx, WinhttpProxySendFailureEvent
0x180077a9a  mov     dword ptr [rsp+78h+var_58], ecx
0x180077a9e  call    McTemplateU0qxqzz_EventWriteTransfer
0x180077aa3  test    eax, eax
0x180077aa5  jz      short loc_180077AC4
0x180077aa7  mov     r9d, eax
0x180077aaa  lea     r8, aEventwritewinh_16; "EventWriteWinhttpProxySendFailureEvent"
0x180077ab1  lea     rdx, aLoggerWritewin_3; "Logger::WriteWinhttpProxySendFailureEve"...
0x180077ab8  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180077abf  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077ac4  mov     eax, [rbx+8]
0x180077ac7  lea     rcx, aSProxySendErro; "%s: Proxy send error. dwInternetStatus:"...
0x180077ace  mov     dword ptr [rsp+78h+var_48], eax
0x180077ad2  mov     r9, r14
0x180077ad5  mov     rax, [rbx]
0x180077ad8  mov     r8d, esi
0x180077adb  mov     [rsp+78h+var_50], rbp
0x180077ae0  mov     rdx, r15
0x180077ae3  mov     [rsp+78h+var_58], rax
0x180077ae8  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077aed  jmp     loc_180077B87
0x180077af2  mov     rcx, [rdi+78h]
0x180077af6  lea     rsi, [rdi+48h]
0x180077afa  mov     rdx, rsi; pProxyResult
0x180077afd  mov     rcx, [rcx+8]; hResolver
0x180077b01  call    cs:__imp_WinHttpGetProxyResult
0x180077b07  mov     ebx, eax
0x180077b09  test    eax, eax
0x180077b0b  jle     short loc_180077B16
0x180077b0d  movzx   ebx, ax
0x180077b10  or      ebx, 80070000h
0x180077b16  test    ebx, ebx
0x180077b18  jns     short loc_180077B29
0x180077b1a  mov     r9d, ebx
0x180077b1d  lea     r8, aWinhttpgetprox_2; "WinHttpGetProxyResult"
0x180077b24  jmp     loc_180077CD1
0x180077b29  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x180077b30  jz      short loc_180077B69
0x180077b32  mov     r8d, [rsi]
0x180077b35  lea     rdx, WinhttpProxyWPADSuccessEvent
0x180077b3c  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180077b43  call    McTemplateU0q_EventWriteTransfer
0x180077b48  test    eax, eax
0x180077b4a  jz      short loc_180077B69
0x180077b4c  mov     r9d, eax
0x180077b4f  lea     r8, aEventwritewinh_10; "EventWriteWinhttpProxyWPADSuccessEvent"
0x180077b56  lea     rdx, aLoggerWritewin_16; "Logger::WriteWinhttpProxyWPADSuccessEve"...
0x180077b5d  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180077b64  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077b69  mov     r8d, [rsi]
0x180077b6c  lea     rcx, aSProxyConfigur; "%s: Proxy configuration discovered: Pro"...
0x180077b73  mov     rdx, r15
0x180077b76  call    ?TraceInformation@Logger@@SAJPEBGZZ; Logger::TraceInformation(ushort const *,...)
0x180077b7b  cmp     dword ptr [rsi], 0
0x180077b7e  jbe     short loc_180077B87
0x180077b80  mov     dword ptr [rdi+40h], 1
0x180077b87  cmp     dword ptr [rdi+40h], 0
0x180077b8b  jz      loc_180077CB9
0x180077b91  mov     eax, [rdi+44h]
0x180077b94  cmp     [rdi+48h], eax
0x180077b97  ja      short loc_180077BF5
0x180077b99  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x180077ba0  mov     ebx, 80070103h
0x180077ba5  jz      short loc_180077BE1
0x180077ba7  mov     r8d, 80070103h
0x180077bad  lea     rdx, WinhttpProxyNoMoreEntriesEvent
0x180077bb4  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x180077bbb  call    McTemplateU0q_EventWriteTransfer
0x180077bc0  test    eax, eax
0x180077bc2  jz      short loc_180077BE1
0x180077bc4  mov     r9d, eax
0x180077bc7  lea     r8, aEventwritewinh_0; "EventWriteWinhttpProxyNoMoreEntriesEven"...
0x180077bce  lea     rdx, aLoggerWritewin_14; "Logger::WriteWinhttpProxyNoMoreEntriesE"...
0x180077bd5  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180077bdc  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077be1  mov     rdx, r15
0x180077be4  lea     rcx, aSNoMoreOutBoun; "%s: No more out-bound proxy servers are"...
0x180077beb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077bf0  jmp     loc_180077CE0
0x180077bf5  mov     rcx, [rdi+8]; hInternet
0x180077bf9  mov     edx, 27h ; '''; dwOption
0x180077bfe  mov     r8, rax
0x180077c01  shl     r8, 5
0x180077c05  add     r8, [rdi+50h]; lpBuffer
0x180077c09  lea     r9d, [rdx-7]; dwBufferLength
0x180077c0d  call    cs:__imp_WinHttpSetOption
0x180077c13  test    eax, eax
0x180077c15  jnz     short loc_180077C3F
0x180077c17  call    cs:__imp_GetLastError
0x180077c1d  mov     ebx, eax
0x180077c1f  test    eax, eax
0x180077c21  jle     short loc_180077C2C
0x180077c23  movzx   ebx, ax
0x180077c26  or      ebx, 80070000h
0x180077c2c  test    ebx, ebx
0x180077c2e  jns     short loc_180077C3F
0x180077c30  mov     r9d, ebx
0x180077c33  lea     r8, aWinhttpsetopti_0; "WinHttpSetOption"
0x180077c3a  jmp     loc_180077CD1
0x180077c3f  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 1
0x180077c46  jz      short loc_180077CB6
0x180077c48  mov     rcx, [rdi+50h]
0x180077c4c  lea     r10, aFalse_0; "FALSE"
0x180077c53  mov     edx, [rdi+44h]
0x180077c56  lea     r8, aTrue_0; "TRUE"
0x180077c5d  shl     rdx, 5
0x180077c61  mov     r9, r8
0x180077c64  cmp     dword ptr [rdx+rcx+4], 0
0x180077c69  movzx   eax, word ptr [rdx+rcx+18h]
0x180077c6e  mov     dword ptr [rsp+78h+var_48], eax
0x180077c72  cmovz   r9, r10
0x180077c76  mov     rax, [rdx+rcx+10h]
0x180077c7b  cmp     dword ptr [rdx+rcx], 0
0x180077c7f  mov     [rsp+78h+var_50], rax
0x180077c84  mov     eax, [rdx+rcx+8]
0x180077c88  cmovz   r8, r10
0x180077c8c  mov     dword ptr [rsp+78h+var_58], eax
0x180077c90  call    McTemplateU0zzqzq_EventWriteTransfer
0x180077c95  test    eax, eax
0x180077c97  jz      short loc_180077CB6
0x180077c99  mov     r9d, eax
0x180077c9c  lea     r8, aEventwritewinh_14; "EventWriteWinhttpProxySetForRequestEven"...
0x180077ca3  lea     rdx, aLoggerWritewin_15; "Logger::WriteWinhttpProxySetForRequestE"...
0x180077caa  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180077cb1  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077cb6  inc     dword ptr [rdi+44h]
0x180077cb9  mov     rcx, rdi; dwContext
0x180077cbc  call    ?BeginSendRequest@WinHttpRequest@@AEAAJXZ; WinHttpRequest::BeginSendRequest(void)
0x180077cc1  mov     ebx, eax
0x180077cc3  test    eax, eax
0x180077cc5  jns     short loc_180077CE0
0x180077cc7  mov     r9d, eax
0x180077cca  lea     r8, aBeginsendreque; "BeginSendRequest"
0x180077cd1  mov     rdx, r15
0x180077cd4  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x180077cdb  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180077ce0  mov     rdx, r15
0x180077ce3  lea     rcx, aSFinished; "%s finished"
0x180077cea  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x180077cef  mov     eax, ebx
0x180077cf1  add     rsp, 48h
0x180077cf5  pop     r15
0x180077cf7  pop     r14
0x180077cf9  pop     rdi
0x180077cfa  pop     rsi
0x180077cfb  pop     rbp
0x180077cfc  pop     rbx
0x180077cfd  retn
```
