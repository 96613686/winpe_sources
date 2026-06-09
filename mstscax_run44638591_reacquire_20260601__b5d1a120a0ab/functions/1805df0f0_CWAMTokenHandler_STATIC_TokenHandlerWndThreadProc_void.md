# CWAMTokenHandler::STATIC_TokenHandlerWndThreadProc(void *)

- ea: `0x1805df0f0`
- end: `0x1805df791`
- name: `?STATIC_TokenHandlerWndThreadProc@CWAMTokenHandler@@CAKPEAX@Z`
- size: `1697`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800011f4`
- `0x180001e8c`
- `0x180003920`
- `0x1805df0f0`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1805df4c2`
- `KERNEL32!CloseHandle` at `0x1805df4c2`
- `KERNEL32!GetModuleHandleExW` at `0x1805df1e1`
- `KERNEL32!GetModuleHandleExW` at `0x1805df1e1`
- `KERNEL32!GetLastError` at `0x1805df37c`
- `KERNEL32!GetLastError` at `0x1805df450`
- `KERNEL32!GetLastError` at `0x1805df54d`
- `KERNEL32!GetLastError` at `0x1805df62b`
- `KERNEL32!GetLastError` at `0x1805df6e6`
- `KERNEL32!GetLastError` at `0x1805df37c`
- `KERNEL32!GetLastError` at `0x1805df450`
- `KERNEL32!GetLastError` at `0x1805df54d`
- `KERNEL32!GetLastError` at `0x1805df62b`
- `KERNEL32!GetLastError` at `0x1805df6e6`
- `KERNEL32!SetEvent` at `0x1805df43b`
- `KERNEL32!SetEvent` at `0x1805df61d`
- `KERNEL32!SetEvent` at `0x1805df43b`
- `KERNEL32!SetEvent` at `0x1805df61d`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1805df4e7`
- `KERNEL32!FreeLibraryAndExitThread` at `0x1805df4e7`
- `USER32!DestroyWindow` at `0x1805df41e`
- `USER32!DestroyWindow` at `0x1805df41e`
- `USER32!TranslateMessage` at `0x1805df6b5`
- `USER32!TranslateMessage` at `0x1805df6b5`
- `USER32!DispatchMessageW` at `0x1805df6bf`
- `USER32!DispatchMessageW` at `0x1805df6bf`
- `USER32!GetMessageW` at `0x1805df6d1`
- `USER32!GetMessageW` at `0x1805df6d1`
- `USER32!CreateWindowExW` at `0x1805df537`
- `USER32!CreateWindowExW` at `0x1805df537`
- `USER32!GetMonitorInfoW` at `0x1805df270`
- `USER32!GetMonitorInfoW` at `0x1805df270`
- `USER32!MonitorFromPoint` at `0x1805df212`
- `USER32!MonitorFromPoint` at `0x1805df212`
- `USER32!GetClassInfoExW` at `0x1805df320`
- `USER32!GetClassInfoExW` at `0x1805df320`
- `USER32!RegisterClassExW` at `0x1805df36d`
- `USER32!RegisterClassExW` at `0x1805df36d`
- `USER32!GetDesktopWindow` at `0x1805df4ee`
- `USER32!GetDesktopWindow` at `0x1805df4ee`

## string_xrefs

- `0x1805df17c`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805df21f`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805df6f9`: `clientcore\termsrv\common\rdadalclient\lib\wamtokenhandler.cpp`
- `0x1805df166`: `STATIC_TokenHandlerWndThreadProc`
- `0x1805df218`: `STATIC_TokenHandlerWndThreadProc`
- `0x1805df6f2`: `STATIC_TokenHandlerWndThreadProc`
- `0x1805df1e7`: `Failed to set event for TokenHandlerWnd.`
- `0x1805df40b`: `Failed to set event for TokenHandlerWnd.`
- `0x1805df643`: `Failed to set event for TokenHandlerWnd.`
- `0x1805df152`: `There should only be one TokenHandlerWnd.`
- `0x1805df316`: `RdpTokenHandlerWndClass`
- `0x1805df342`: `RdpTokenHandlerWndClass`
- `0x1805df4fd`: `RdpTokenHandlerWndClass`
- `0x1805df5f1`: `Create TokenHandlerWnd succeeded`
- `0x1805df56c`: `Failed to create TokenHandlerWnd.`

## pseudocode

```c
__int64 __fastcall CWAMTokenHandler::STATIC_TokenHandlerWndThreadProc(PVOID Parameter)
{
  int v1; // ecx
  int v2; // r8d
  int v3; // r9d
  HINSTANCE hInstance; // r14
  int v6; // r13d
  int X; // r15d
  int Y; // r12d
  HMONITOR v9; // rax
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  const char *v13; // rax
  int *v14; // rdx
  DWORD v15; // eax
  int v16; // r8d
  int v17; // r9d
  DWORD v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  HWND hWndParent; // rax
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  DWORD v26; // eax
  int v27; // r8d
  int v28; // r9d
  DWORD v29; // eax
  int v30; // r8d
  int v31; // r9d
  DWORD LastError; // eax
  int v33; // r8d
  int v34; // r9d
  const char *v35; // [rsp+60h] [rbp-A0h] BYREF
  const char *v36; // [rsp+68h] [rbp-98h] BYREF
  int v37; // [rsp+70h] [rbp-90h] BYREF
  int v38; // [rsp+74h] [rbp-8Ch] BYREF
  const char *v39; // [rsp+78h] [rbp-88h] BYREF
  const char *v40; // [rsp+80h] [rbp-80h] BYREF
  const char *v41; // [rsp+88h] [rbp-78h] BYREF
  const char *v42; // [rsp+90h] [rbp-70h] BYREF
  int v43; // [rsp+98h] [rbp-68h] BYREF
  DWORD v44; // [rsp+9Ch] [rbp-64h] BYREF
  int v45; // [rsp+A0h] [rbp-60h] BYREF
  int v46; // [rsp+A4h] [rbp-5Ch] BYREF
  HMODULE phModule; // [rsp+A8h] [rbp-58h] BYREF
  struct tagWNDCLASSEXW wcx; // [rsp+B0h] [rbp-50h] BYREF
  MSG Msg; // [rsp+100h] [rbp+0h] BYREF
  struct tagMONITORINFO mi; // [rsp+130h] [rbp+30h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  memset_0(&wcx, 0, sizeof(wcx));
  phModule = 0;
  if ( CWAMTokenHandler::s_hwndTokenHandler )
  {
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v37 = 2120;
      v39 = "There should only be one TokenHandlerWnd.";
      v36 = "STATIC_TokenHandlerWndThreadProc";
      v35 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
      v38 = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v1,
        (unsigned int)&word_18088B1DE,
        v2,
        v3,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v35,
        (__int64)&v37,
        (__int64)&v36);
    }
    return 1410;
  }
  hInstance = g_hModule;
  if ( !GetModuleHandleExW(4u, (LPCWSTR)g_hModule, &phModule) || hInstance != phModule )
  {
    v6 = 0;
    LastError = GetLastError();
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      LODWORD(v39) = LastError;
      v42 = "STATIC_TokenHandlerWndThreadProc";
      v40 = "GetModuleHandleEx failed. GetLastError";
      LODWORD(v35) = 2134;
      v41 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
      LODWORD(v36) = -2147467259;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        dword_1808B5850,
        (unsigned int)byte_18088B223,
        v33,
        v34,
        (__int64)&v40,
        (__int64)&v36,
        (__int64)&v41,
        (__int64)&v35,
        (__int64)&v42,
        (__int64)&v39);
    }
    goto LABEL_20;
  }
  v6 = 1;
  X = 0;
  Y = 0;
  v9 = MonitorFromPoint(0, 1u);
  if ( v9 )
  {
    mi.cbSize = 40;
    memset(&mi.rcMonitor, 0, 36);
    if ( GetMonitorInfoW(v9, &mi) )
    {
      X = (mi.rcWork.right - mi.rcWork.left) / 2;
      Y = (mi.rcWork.bottom - mi.rcWork.top) / 2;
      goto LABEL_15;
    }
    if ( (unsigned int)dword_1808B5850 > 2 )
    {
      v38 = 2158;
      v13 = "GetMonitorInfo failed.";
      v14 = (int *)byte_18088B199;
      goto LABEL_13;
    }
  }
  else if ( (unsigned int)dword_1808B5850 > 2 )
  {
    v38 = 2146;
    v13 = "MonitorFromPoint failed.";
    v14 = &dword_18088B154;
LABEL_13:
    v39 = v13;
    v37 = -2147467259;
    v35 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
    v36 = "STATIC_TokenHandlerWndThreadProc";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v10,
      (_DWORD)v14,
      v11,
      v12,
      (__int64)&v39,
      (__int64)&v37,
      (__int64)&v35,
      (__int64)&v38,
      (__int64)&v36);
  }
LABEL_15:
  wcx.cbSize = 80;
  if ( GetClassInfoExW(hInstance, L"RdpTokenHandlerWndClass", &wcx) )
    goto LABEL_30;
  *(_QWORD *)&wcx.cbClsExtra = 0;
  wcx.lpfnWndProc = CWAMTokenHandler::STATIC_TokenHandlerWndProc;
  wcx.hIconSm = 0;
  wcx.lpszClassName = L"RdpTokenHandlerWndClass";
  wcx.style = 3;
  wcx.hInstance = hInstance;
  memset(&wcx.hIcon, 0, 32);
  if ( RegisterClassExW(&wcx) || (v15 = GetLastError(), v15 == 1410) )
  {
LABEL_30:
    hWndParent = GetDesktopWindow();
    CWAMTokenHandler::s_hwndTokenHandler = CreateWindowExW(
                                             8u,
                                             L"RdpTokenHandlerWndClass",
                                             0,
                                             0xCF0000u,
                                             X,
                                             Y,
                                             0,
                                             0,
                                             hWndParent,
                                             0,
                                             hInstance,
                                             0);
    if ( CWAMTokenHandler::s_hwndTokenHandler )
    {
      if ( (unsigned int)dword_1808B5850 > 5 )
      {
        v36 = (const char *)CWAMTokenHandler::s_hwndTokenHandler;
        v35 = "Create TokenHandlerWnd succeeded";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v23,
          (unsigned int)&byte_18088B3F7,
          v24,
          v25,
          (__int64)&v35,
          (__int64)&v36);
      }
      if ( SetEvent(CWAMTokenHandler::s_hTokenHandlerWndCreatedEvent) )
      {
        while ( GetMessageW(&Msg, 0, 0, 0) )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      else
      {
        v29 = GetLastError();
        if ( (unsigned int)dword_1808B5850 > 2 )
        {
          LODWORD(v40) = v29;
          v36 = "STATIC_TokenHandlerWndThreadProc";
          LODWORD(v41) = 2231;
          v35 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
          LODWORD(v42) = -2147467259;
          v39 = "Failed to set event for TokenHandlerWnd.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1808B5850,
            (unsigned int)word_18088B42A,
            v30,
            v31,
            (__int64)&v39,
            (__int64)&v42,
            (__int64)&v35,
            (__int64)&v41,
            (__int64)&v36,
            (__int64)&v40);
        }
      }
    }
    else
    {
      v26 = GetLastError();
      if ( (unsigned int)dword_1808B5850 > 2 )
      {
        v44 = v26;
        v36 = "STATIC_TokenHandlerWndThreadProc";
        v39 = "Failed to create TokenHandlerWnd.";
        v45 = 2219;
        v35 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
        v46 = -2147467259;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_1808B5850,
          (unsigned int)&dword_18088B104,
          v27,
          v28,
          (__int64)&v39,
          (__int64)&v46,
          (__int64)&v35,
          (__int64)&v45,
          (__int64)&v36,
          (__int64)&v44);
      }
    }
  }
  else if ( (unsigned int)dword_1808B5850 > 2 )
  {
    v38 = v15;
    v36 = "STATIC_TokenHandlerWndThreadProc";
    v39 = "Can't register class.";
    v37 = 2194;
    v35 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
    v43 = -2147467259;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1808B5850,
      (unsigned int)&dword_18088B0B4,
      v16,
      v17,
      (__int64)&v39,
      (__int64)&v43,
      (__int64)&v35,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v38);
  }
LABEL_20:
  if ( CWAMTokenHandler::s_hwndTokenHandler )
  {
    DestroyWindow(CWAMTokenHandler::s_hwndTokenHandler);
    CWAMTokenHandler::s_hwndTokenHandler = 0;
  }
  if ( CWAMTokenHandler::s_hTokenHandlerWndCreatedEvent )
  {
    if ( !SetEvent(CWAMTokenHandler::s_hTokenHandlerWndCreatedEvent) && (unsigned int)dword_1808B5850 > 2 )
    {
      v18 = GetLastError();
      v42 = "STATIC_TokenHandlerWndThreadProc";
      LODWORD(v36) = v18;
      LODWORD(v35) = 2261;
      v41 = "clientcore\\termsrv\\common\\rdadalclient\\lib\\wamtokenhandler.cpp";
      LODWORD(v39) = -2147467259;
      v40 = "Failed to set event for TokenHandlerWnd.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&byte_18088B3A7,
        v20,
        v21,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v41,
        (__int64)&v35,
        (__int64)&v42,
        (__int64)&v36);
    }
    CloseHandle(CWAMTokenHandler::s_hTokenHandlerWndCreatedEvent);
    CWAMTokenHandler::s_hTokenHandlerWndCreatedEvent = 0;
  }
  if ( v6 && phModule )
    FreeLibraryAndExitThread(phModule, 0);
  return 0;
}

```

## disassembly

```asm
0x1805df0f0  push    rbp
0x1805df0f2  push    rbx
0x1805df0f3  push    rdi
0x1805df0f4  push    r12
0x1805df0f6  push    r13
0x1805df0f8  push    r14
0x1805df0fa  push    r15
0x1805df0fc  lea     rbp, [rsp-60h]
0x1805df101  sub     rsp, 160h
0x1805df108  mov     rax, cs:__security_cookie
0x1805df10f  xor     rax, rsp
0x1805df112  mov     [rbp+90h+var_38], rax
0x1805df116  xorps   xmm0, xmm0
0x1805df119  lea     rcx, [rbp+90h+wcx]; void *
0x1805df11d  xor     edx, edx; Val
0x1805df11f  movups  xmmword ptr [rbp+90h+Msg.hwnd], xmm0
0x1805df123  movups  xmmword ptr [rbp+90h+Msg.wParam], xmm0
0x1805df127  lea     r8d, [rdx+50h]; Size
0x1805df12b  movups  xmmword ptr [rbp+90h+Msg.time], xmm0
0x1805df12f  call    memset_0
0x1805df134  xor     ebx, ebx
0x1805df136  cmp     cs:?s_hwndTokenHandler@CWAMTokenHandler@@0PEAUHWND__@@EA, rbx; HWND__ * CWAMTokenHandler::s_hwndTokenHandler
0x1805df13d  mov     [rbp+90h+phModule], rbx
0x1805df141  jz      loc_1805DF1CE
0x1805df147  mov     eax, cs:dword_1808B5850
0x1805df14d  cmp     eax, 2
0x1805df150  jbe     short loc_1805DF1C4
0x1805df152  lea     rax, aThereShouldOnl; "There should only be one TokenHandlerWn"...
0x1805df159  mov     [rsp+190h+var_120], 848h
0x1805df161  mov     [rsp+190h+var_118], rax
0x1805df166  lea     rbx, aStaticTokenhan; "STATIC_TokenHandlerWndThreadProc"
0x1805df16d  lea     rax, [rsp+190h+var_128]
0x1805df172  mov     [rsp+190h+var_128], rbx
0x1805df177  mov     [rsp+190h+hWndParent], rax
0x1805df17c  lea     rdi, aClientcoreTerm_42; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805df183  lea     rax, [rsp+190h+var_120]
0x1805df188  mov     [rsp+190h+var_130], rdi
0x1805df18d  mov     qword ptr [rsp+190h+nHeight], rax
0x1805df192  lea     rdx, word_18088B1DE
0x1805df199  lea     rax, [rsp+190h+var_130]
0x1805df19e  mov     [rsp+190h+var_11C], 80004005h
0x1805df1a6  mov     qword ptr [rsp+190h+nWidth], rax
0x1805df1ab  lea     rax, [rsp+190h+var_11C]
0x1805df1b0  mov     qword ptr [rsp+190h+Y], rax
0x1805df1b5  lea     rax, [rsp+190h+var_118]
0x1805df1ba  mov     qword ptr [rsp+190h+X], rax
0x1805df1bf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1805df1c4  mov     eax, 582h
0x1805df1c9  jmp     loc_1805DF772
0x1805df1ce  mov     r14, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hModule
0x1805df1d5  lea     r8, [rbp+90h+phModule]; phModule
0x1805df1d9  mov     rdx, r14; lpModuleName
0x1805df1dc  mov     ecx, 4; dwFlags
0x1805df1e1  call    cs:__imp_GetModuleHandleExW
0x1805df1e7  lea     r15, aFailedToSetEve; "Failed to set event for TokenHandlerWnd"...
0x1805df1ee  test    eax, eax
0x1805df1f0  jz      loc_1805DF6E0
0x1805df1f6  cmp     r14, [rbp+90h+phModule]
0x1805df1fa  jnz     loc_1805DF6E0
0x1805df200  mov     r13d, 1
0x1805df206  mov     rcx, rbx; pt
0x1805df209  mov     edx, r13d; dwFlags
0x1805df20c  mov     r15d, ebx
0x1805df20f  mov     r12d, ebx
0x1805df212  call    cs:__imp_MonitorFromPoint
0x1805df218  lea     rbx, aStaticTokenhan; "STATIC_TokenHandlerWndThreadProc"
0x1805df21f  lea     rdi, aClientcoreTerm_42; "clientcore\\termsrv\\common\\rdadalclie"...
0x1805df226  test    rax, rax
0x1805df229  jnz     short loc_1805DF252
0x1805df22b  mov     eax, cs:dword_1808B5850
0x1805df231  cmp     eax, 2
0x1805df234  jbe     loc_1805DF30B
0x1805df23a  mov     [rsp+190h+var_11C], 862h
0x1805df242  lea     rax, aMonitorfrompoi; "MonitorFromPoint failed."
0x1805df249  lea     rdx, dword_18088B154
0x1805df250  jmp     short loc_1805DF29F
0x1805df252  xor     ecx, ecx
0x1805df254  mov     [rbp+90h+mi.cbSize], 28h ; '('
0x1805df25b  xorps   xmm0, xmm0
0x1805df25e  mov     [rbp+90h+mi.dwFlags], ecx
0x1805df261  mov     rcx, rax; hMonitor
0x1805df264  lea     rdx, [rbp+90h+mi]; lpmi
0x1805df268  movups  xmmword ptr [rbp+90h+mi.rcMonitor.left], xmm0
0x1805df26c  movups  xmmword ptr [rbp+90h+mi.rcWork.left], xmm0
0x1805df270  call    cs:__imp_GetMonitorInfoW
0x1805df276  test    eax, eax
0x1805df278  jnz     short loc_1805DF2EF
0x1805df27a  mov     eax, cs:dword_1808B5850
0x1805df280  cmp     eax, 2
0x1805df283  jbe     loc_1805DF30B
0x1805df289  mov     [rsp+190h+var_11C], 86Eh
0x1805df291  lea     rax, aGetmonitorinfo_1; "GetMonitorInfo failed."
0x1805df298  lea     rdx, byte_18088B199
0x1805df29f  mov     [rsp+190h+var_118], rax
0x1805df2a4  lea     rax, [rsp+190h+var_128]
0x1805df2a9  mov     [rsp+190h+hWndParent], rax
0x1805df2ae  lea     rax, [rsp+190h+var_11C]
0x1805df2b3  mov     qword ptr [rsp+190h+nHeight], rax
0x1805df2b8  lea     rax, [rsp+190h+var_130]
0x1805df2bd  mov     qword ptr [rsp+190h+nWidth], rax
0x1805df2c2  lea     rax, [rsp+190h+var_120]
0x1805df2c7  mov     qword ptr [rsp+190h+Y], rax
0x1805df2cc  lea     rax, [rsp+190h+var_118]
0x1805df2d1  mov     qword ptr [rsp+190h+X], rax
0x1805df2d6  mov     [rsp+190h+var_120], 80004005h
0x1805df2de  mov     [rsp+190h+var_130], rdi
0x1805df2e3  mov     [rsp+190h+var_128], rbx
0x1805df2e8  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1805df2ed  jmp     short loc_1805DF30B
0x1805df2ef  mov     eax, [rbp+90h+mi.rcWork.right]
0x1805df2f2  sub     eax, [rbp+90h+mi.rcWork.left]
0x1805df2f5  cdq
0x1805df2f6  sub     eax, edx
0x1805df2f8  sar     eax, 1
0x1805df2fa  mov     r15d, eax
0x1805df2fd  mov     eax, [rbp+90h+mi.rcWork.bottom]
0x1805df300  sub     eax, [rbp+90h+mi.rcWork.top]
0x1805df303  cdq
0x1805df304  sub     eax, edx
0x1805df306  sar     eax, 1
0x1805df308  mov     r12d, eax
0x1805df30b  lea     r8, [rbp+90h+wcx]; lpwcx
0x1805df30f  mov     [rbp+90h+wcx.cbSize], 50h ; 'P'
0x1805df316  lea     rdx, aRdptokenhandle; "RdpTokenHandlerWndClass"
0x1805df31d  mov     rcx, r14; hInstance
0x1805df320  call    cs:__imp_GetClassInfoExW
0x1805df326  xor     ecx, ecx
0x1805df328  test    eax, eax
0x1805df32a  jnz     loc_1805DF4EE
0x1805df330  lea     rax, ?STATIC_TokenHandlerWndProc@CWAMTokenHandler@@CA_JPEAUHWND__@@I_K_J@Z; CWAMTokenHandler::STATIC_TokenHandlerWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1805df337  mov     qword ptr [rbp+90h+wcx.cbClsExtra], rcx
0x1805df33b  mov     [rbp+90h+wcx.lpfnWndProc], rax
0x1805df33f  xorps   xmm0, xmm0
0x1805df342  lea     rax, aRdptokenhandle; "RdpTokenHandlerWndClass"
0x1805df349  mov     [rbp+90h+wcx.hIconSm], rcx
0x1805df34d  xorps   xmm1, xmm1
0x1805df350  mov     [rbp+90h+wcx.lpszClassName], rax
0x1805df354  lea     rcx, [rbp+90h+wcx]; WNDCLASSEXW *
0x1805df358  mov     [rbp+90h+wcx.style], 3
0x1805df35f  mov     [rbp+90h+wcx.hInstance], r14
0x1805df363  movdqa  xmmword ptr [rbp+90h+wcx.hIcon], xmm0
0x1805df368  movdqa  xmmword ptr [rbp+90h+wcx.hbrBackground], xmm1
0x1805df36d  call    cs:__imp_RegisterClassExW
0x1805df373  test    ax, ax
0x1805df376  jnz     loc_1805DF4EE
0x1805df37c  call    cs:__imp_GetLastError
0x1805df382  cmp     eax, 582h
0x1805df387  jz      loc_1805DF4EE
0x1805df38d  mov     ecx, cs:dword_1808B5850
0x1805df393  cmp     ecx, 2
0x1805df396  jbe     short loc_1805DF408
0x1805df398  mov     [rsp+190h+var_11C], eax
0x1805df39c  lea     rdx, dword_18088B0B4
0x1805df3a3  lea     rax, aCanTRegisterCl; "Can't register class."
0x1805df3aa  mov     [rsp+190h+var_128], rbx
0x1805df3af  mov     [rsp+190h+var_118], rax
0x1805df3b4  lea     rax, [rsp+190h+var_11C]
0x1805df3b9  mov     [rsp+190h+hMenu], rax
0x1805df3be  lea     rax, [rsp+190h+var_128]
0x1805df3c3  mov     [rsp+190h+hWndParent], rax
0x1805df3c8  lea     rax, [rsp+190h+var_120]
0x1805df3cd  mov     qword ptr [rsp+190h+nHeight], rax
0x1805df3d2  lea     rax, [rsp+190h+var_130]
0x1805df3d7  mov     qword ptr [rsp+190h+nWidth], rax
0x1805df3dc  lea     rax, [rbp+90h+var_F8]
0x1805df3e0  mov     qword ptr [rsp+190h+Y], rax
0x1805df3e5  lea     rax, [rsp+190h+var_118]
0x1805df3ea  mov     qword ptr [rsp+190h+X], rax
0x1805df3ef  mov     [rsp+190h+var_120], 892h
0x1805df3f7  mov     [rsp+190h+var_130], rdi
0x1805df3fc  mov     [rbp+90h+var_F8], 80004005h
0x1805df403  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1805df408  xor     r14d, r14d
0x1805df40b  lea     r15, aFailedToSetEve; "Failed to set event for TokenHandlerWnd"...
0x1805df412  mov     rcx, cs:?s_hwndTokenHandler@CWAMTokenHandler@@0PEAUHWND__@@EA; hWnd
0x1805df419  test    rcx, rcx
0x1805df41c  jz      short loc_1805DF42B
0x1805df41e  call    cs:__imp_DestroyWindow
0x1805df424  mov     cs:?s_hwndTokenHandler@CWAMTokenHandler@@0PEAUHWND__@@EA, r14; HWND__ * CWAMTokenHandler::s_hwndTokenHandler
0x1805df42b  mov     rcx, cs:?s_hTokenHandlerWndCreatedEvent@CWAMTokenHandler@@0PEAXEA; hEvent
0x1805df432  test    rcx, rcx
0x1805df435  jz      loc_1805DF4CF
0x1805df43b  call    cs:__imp_SetEvent
0x1805df441  test    eax, eax
0x1805df443  jnz     short loc_1805DF4BB
0x1805df445  mov     eax, cs:dword_1808B5850
0x1805df44b  cmp     eax, 2
0x1805df44e  jbe     short loc_1805DF4BB
0x1805df450  call    cs:__imp_GetLastError
0x1805df456  lea     rdx, byte_18088B3A7
0x1805df45d  mov     [rbp+90h+var_100], rbx
0x1805df461  mov     dword ptr [rsp+190h+var_128], eax
0x1805df465  lea     rax, [rsp+190h+var_128]
0x1805df46a  mov     [rsp+190h+hMenu], rax
0x1805df46f  lea     rax, [rbp+90h+var_100]
0x1805df473  mov     [rsp+190h+hWndParent], rax
0x1805df478  lea     rax, [rsp+190h+var_130]
0x1805df47d  mov     qword ptr [rsp+190h+nHeight], rax
0x1805df482  lea     rax, [rbp+90h+var_108]
0x1805df486  mov     qword ptr [rsp+190h+nWidth], rax
0x1805df48b  lea     rax, [rsp+190h+var_118]
0x1805df490  mov     qword ptr [rsp+190h+Y], rax
0x1805df495  lea     rax, [rbp+90h+var_110]
0x1805df499  mov     qword ptr [rsp+190h+X], rax
0x1805df49e  mov     dword ptr [rsp+190h+var_130], 8D5h
0x1805df4a6  mov     [rbp+90h+var_108], rdi
0x1805df4aa  mov     dword ptr [rsp+190h+var_118], 80004005h
0x1805df4b2  mov     [rbp+90h+var_110], r15
0x1805df4b6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1805df4bb  mov     rcx, cs:?s_hTokenHandlerWndCreatedEvent@CWAMTokenHandler@@0PEAXEA; hObject
0x1805df4c2  call    cs:__imp_CloseHandle
0x1805df4c8  mov     cs:?s_hTokenHandlerWndCreatedEvent@CWAMTokenHandler@@0PEAXEA, r14; void * CWAMTokenHandler::s_hTokenHandlerWndCreatedEvent
0x1805df4cf  test    r13d, r13d
0x1805df4d2  jz      loc_1805DF770
0x1805df4d8  mov     rcx, [rbp+90h+phModule]; hLibModule
0x1805df4dc  test    rcx, rcx
0x1805df4df  jz      loc_1805DF770
0x1805df4e5  xor     edx, edx; dwExitCode
0x1805df4e7  call    cs:__imp_FreeLibraryAndExitThread
0x1805df4ee  call    cs:__imp_GetDesktopWindow
0x1805df4f4  mov     [rsp+190h+lpParam], 0; lpParam
0x1805df4fd  lea     rdx, aRdptokenhandle; "RdpTokenHandlerWndClass"
0x1805df504  mov     [rsp+190h+hInstance], r14; hInstance
0x1805df509  mov     r9d, 0CF0000h; dwStyle
0x1805df50f  xor     r14d, r14d
0x1805df512  xor     r8d, r8d; lpWindowName
0x1805df515  mov     [rsp+190h+hMenu], r14; hMenu
0x1805df51a  mov     [rsp+190h+hWndParent], rax; hWndParent
0x1805df51f  mov     [rsp+190h+nHeight], r14d; nHeight
0x1805df524  mov     [rsp+190h+nWidth], r14d; nWidth
0x1805df529  lea     ecx, [r14+8]; dwExStyle
0x1805df52d  mov     [rsp+190h+Y], r12d; Y
0x1805df532  mov     [rsp+190h+X], r15d; X
0x1805df537  call    cs:__imp_CreateWindowExW
0x1805df53d  mov     cs:?s_hwndTokenHandler@CWAMTokenHandler@@0PEAUHWND__@@EA, rax; HWND__ * CWAMTokenHandler::s_hwndTokenHandler
0x1805df544  test    rax, rax
0x1805df547  jnz     loc_1805DF5D3
0x1805df54d  call    cs:__imp_GetLastError
0x1805df553  mov     ecx, cs:dword_1808B5850
0x1805df559  cmp     ecx, 2
0x1805df55c  jbe     loc_1805DF40B
0x1805df562  mov     [rbp+90h+var_F4], eax
0x1805df565  lea     rdx, dword_18088B104
0x1805df56c  lea     rax, aFailedToCreate_58; "Failed to create TokenHandlerWnd."
0x1805df573  mov     [rsp+190h+var_128], rbx
0x1805df578  mov     [rsp+190h+var_118], rax
0x1805df57d  lea     rax, [rbp+90h+var_F4]
0x1805df581  mov     [rsp+190h+hMenu], rax
0x1805df586  lea     rax, [rsp+190h+var_128]
0x1805df58b  mov     [rsp+190h+hWndParent], rax
0x1805df590  lea     rax, [rbp+90h+var_F0]
0x1805df594  mov     qword ptr [rsp+190h+nHeight], rax
0x1805df599  lea     rax, [rsp+190h+var_130]
0x1805df59e  mov     qword ptr [rsp+190h+nWidth], rax
0x1805df5a3  lea     rax, [rbp+90h+var_EC]
0x1805df5a7  mov     qword ptr [rsp+190h+Y], rax
0x1805df5ac  lea     rax, [rsp+190h+var_118]
0x1805df5b1  mov     qword ptr [rsp+190h+X], rax
0x1805df5b6  mov     [rbp+90h+var_F0], 8ABh
0x1805df5bd  mov     [rsp+190h+var_130], rdi
0x1805df5c2  mov     [rbp+90h+var_EC], 80004005h
0x1805df5c9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1805df5ce  jmp     loc_1805DF40B
0x1805df5d3  mov     eax, cs:dword_1808B5850
0x1805df5d9  cmp     eax, 5
0x1805df5dc  jbe     short loc_1805DF616
0x1805df5de  mov     rax, cs:?s_hwndTokenHandler@CWAMTokenHandler@@0PEAUHWND__@@EA; HWND__ * CWAMTokenHandler::s_hwndTokenHandler
0x1805df5e5  lea     rdx, byte_18088B3F7
0x1805df5ec  mov     [rsp+190h+var_128], rax
0x1805df5f1  lea     rax, aCreateTokenhan; "Create TokenHandlerWnd succeeded"
0x1805df5f8  mov     [rsp+190h+var_130], rax
0x1805df5fd  lea     rax, [rsp+190h+var_128]
0x1805df602  mov     qword ptr [rsp+190h+Y], rax
0x1805df607  lea     rax, [rsp+190h+var_130]
0x1805df60c  mov     qword ptr [rsp+190h+X], rax
0x1805df611  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1805df616  mov     rcx, cs:?s_hTokenHandlerWndCreatedEvent@CWAMTokenHandler@@0PEAXEA; hEvent
0x1805df61d  call    cs:__imp_SetEvent
0x1805df623  test    eax, eax
0x1805df625  jnz     loc_1805DF6C5
0x1805df62b  call    cs:__imp_GetLastError
0x1805df631  mov     ecx, cs:dword_1808B5850
0x1805df637  cmp     ecx, 2
0x1805df63a  jbe     loc_1805DF40B
0x1805df640  mov     dword ptr [rbp+90h+var_110], eax
0x1805df643  lea     r15, aFailedToSetEve; "Failed to set event for TokenHandlerWnd"...
0x1805df64a  lea     rax, [rbp+90h+var_110]
0x1805df64e  mov     [rsp+190h+var_128], rbx
0x1805df653  mov     [rsp+190h+hMenu], rax
0x1805df658  lea     rdx, word_18088B42A
0x1805df65f  lea     rax, [rsp+190h+var_128]
0x1805df664  mov     dword ptr [rbp+90h+var_108], 8B7h
0x1805df66b  mov     [rsp+190h+hWndParent], rax
0x1805df670  lea     rax, [rbp+90h+var_108]
0x1805df674  mov     qword ptr [rsp+190h+nHeight], rax
0x1805df679  lea     rax, [rsp+190h+var_130]
0x1805df67e  mov     qword ptr [rsp+190h+nWidth], rax
0x1805df683  lea     rax, [rbp+90h+var_100]
0x1805df687  mov     qword ptr [rsp+190h+Y], rax
0x1805df68c  lea     rax, [rsp+190h+var_118]
  ... truncated ...
```
