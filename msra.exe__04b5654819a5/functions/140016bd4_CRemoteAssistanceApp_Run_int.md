# CRemoteAssistanceApp::Run(int)

- ea: `0x140016bd4`
- end: `0x1400171b8`
- name: `?Run@CRemoteAssistanceApp@@QEAAJH@Z`
- size: `1508`
- prototype: `__int64 __fastcall(CRemoteAssistanceApp *this)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400194c8`

## callees

- `0x1400151f0`
- `0x140016bd4`
- `0x1400187b0`
- `0x14001916c`
- `0x14001ffb8`
- `0x140033db0`
- `0x140034ce4`
- `0x140035888`
- `0x140037c8c`
- `0x14004ad80`
- `0x14004d010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140017032`
- `KERNEL32!FreeLibrary` at `0x140017032`
- `KERNEL32!SetWaitableTimer` at `0x140016ff2`
- `KERNEL32!SetWaitableTimer` at `0x140016ff2`
- `KERNEL32!CreateWaitableTimerW` at `0x140016f7c`
- `KERNEL32!CreateWaitableTimerW` at `0x140016f7c`
- `KERNEL32!LoadLibraryW` at `0x140016cb4`
- `KERNEL32!LoadLibraryW` at `0x140016cb4`
- `KERNEL32!CloseHandle` at `0x140017046`
- `KERNEL32!CloseHandle` at `0x140017046`
- `KERNEL32!GetLastError` at `0x140016f3f`
- `KERNEL32!GetLastError` at `0x140016f53`
- `KERNEL32!GetLastError` at `0x140016f98`
- `KERNEL32!GetLastError` at `0x140016fac`
- `KERNEL32!GetLastError` at `0x140016f3f`
- `KERNEL32!GetLastError` at `0x140016f53`
- `KERNEL32!GetLastError` at `0x140016f98`
- `KERNEL32!GetLastError` at `0x140016fac`
- `KERNEL32!GetCurrentThreadId` at `0x140016d79`
- `KERNEL32!GetCurrentThreadId` at `0x140016e20`
- `KERNEL32!GetCurrentThreadId` at `0x140016d79`
- `KERNEL32!GetCurrentThreadId` at `0x140016e20`
- `KERNEL32!WaitForSingleObject` at `0x1400170d3`
- `KERNEL32!WaitForSingleObject` at `0x1400170d3`
- `KERNEL32!LeaveCriticalSection` at `0x140016db4`
- `KERNEL32!LeaveCriticalSection` at `0x140016e5b`
- `KERNEL32!LeaveCriticalSection` at `0x140016db4`
- `KERNEL32!LeaveCriticalSection` at `0x140016e5b`
- `KERNEL32!EnterCriticalSection` at `0x140016d8f`
- `KERNEL32!EnterCriticalSection` at `0x140016e36`
- `KERNEL32!EnterCriticalSection` at `0x140016d8f`
- `KERNEL32!EnterCriticalSection` at `0x140016e36`
- `USER32!ShowWindow` at `0x140016ddc`
- `USER32!ShowWindow` at `0x140016e83`
- `USER32!ShowWindow` at `0x140016ddc`
- `USER32!ShowWindow` at `0x140016e83`
- `USER32!CreateWindowExW` at `0x140016f23`
- `USER32!CreateWindowExW` at `0x140016f23`
- `USER32!TranslateMessage` at `0x1400170af`
- `USER32!TranslateMessage` at `0x1400170af`
- `USER32!DispatchMessageW` at `0x1400170bf`
- `USER32!DispatchMessageW` at `0x1400170bf`
- `USER32!DestroyWindow` at `0x1400170ee`
- `USER32!DestroyWindow` at `0x1400170ee`
- `USER32!PeekMessageW` at `0x14001709a`
- `USER32!PeekMessageW` at `0x14001709a`
- `OLEAUT32!__imp_SysFreeString` at `0x140016ccb`
- `OLEAUT32!__imp_SysFreeString` at `0x140016ccb`
- `COMCTL32!InitCommonControlsEx` at `0x140016c40`
- `COMCTL32!InitCommonControlsEx` at `0x140016c40`
- `SHELL32!__imp_LinkWindow_RegisterClass` at `0x140016c7c`
- `SHELL32!__imp_LinkWindow_RegisterClass` at `0x140016c7c`

## string_xrefs

- `0x140016c88`: `\MSFTEDIT.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRemoteAssistanceApp::Run(CRemoteAssistanceApp *this)
{
  CEventLogger *v2; // rcx
  signed int DirectoryAsBSTR; // eax
  CEventLogger *v4; // rcx
  OLECHAR *v5; // rbx
  unsigned int v6; // edx
  CEventLogger *v7; // rcx
  HMODULE LibraryW; // r14
  unsigned int v9; // ecx
  HANDLE WaitableTimerW; // rsi
  int v11; // ecx
  DWORD v12; // r15d
  int v13; // ecx
  int v14; // ecx
  HWND DialogW; // rbx
  HWND v16; // rbx
  char *v17; // rcx
  HWND Window; // rbx
  CEventLogger *v19; // rcx
  signed int LastError; // eax
  bool v21; // sf
  CEventLogger *v22; // rcx
  signed int v23; // eax
  bool v24; // sf
  CEventLogger *v25; // rcx
  signed int v27; // eax
  CEventLogger *v28; // rcx
  __int64 v29; // rcx
  LARGE_INTEGER DueTime; // [rsp+60h] [rbp-29h] BYREF
  INITCOMMONCONTROLSEX picce; // [rsp+68h] [rbp-21h] BYREF
  LPCWSTR lpLibFileName; // [rsp+70h] [rbp-19h] BYREF
  struct tagMSG Msg; // [rsp+78h] [rbp-11h] BYREF
  __m128i si128; // [rsp+A8h] [rbp+1Fh] BYREF

  DueTime.QuadPart = 0;
  memset(&Msg, 0, sizeof(Msg));
  lpLibFileName = 0;
  picce.dwSize = 8;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  picce.dwICC = 32815;
  if ( !InitCommonControlsEx(&picce) )
  {
    CEventLogger::LogError(
      v2,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x53u,
      L"CRemoteAssistanceApp::Run",
      0);
    return 0;
  }
  LinkWindow_RegisterClass();
  DirectoryAsBSTR = GetDirectoryAsBSTR(37, (unsigned __int16 **)&lpLibFileName, L"\\MSFTEDIT.DLL");
  if ( DirectoryAsBSTR < 0 )
  {
    CEventLogger::LogError(
      v4,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x5Cu,
      L"CRemoteAssistanceApp::Run",
      DirectoryAsBSTR);
    return 0;
  }
  v5 = (OLECHAR *)lpLibFileName;
  LibraryW = LoadLibraryW(lpLibFileName);
  if ( v5 )
    SysFreeString(v5);
  if ( !LibraryW )
  {
    CEventLogger::LogError(
      v7,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x5Fu,
      L"CRemoteAssistanceApp::Run",
      0x80004003);
    return 0;
  }
  v9 = *((_DWORD *)this + 205);
  WaitableTimerW = 0;
  if ( v9 - 111 <= 1 || v9 == -1 || v9 == 32 )
    *((_DWORD *)this + 206) = v9;
  else
    CWizard::ShowWizard(*((CWizard **)this + 61), v9);
  v11 = *((_DWORD *)this + 206);
  if ( v11 == -1 )
    goto LABEL_37;
  v12 = 258;
  while ( 1 )
  {
    v13 = v11 - 32;
    if ( v13 )
    {
      v14 = v13 - 79;
      if ( v14 )
      {
        if ( v14 == 1 )
        {
          *((_QWORD *)this + 21) = &si128;
          if ( this == (CRemoteAssistanceApp *)-88LL || this == (CRemoteAssistanceApp *)-72LL )
          {
            ATL::_AtlRaiseException(0xC0000005, v6);
            JUMPOUT(0x1400171B7LL);
          }
          *((_QWORD *)this + 11) = (char *)this + 72;
          *((_DWORD *)this + 24) = GetCurrentThreadId();
          EnterCriticalSection(&stru_140063978);
          *((_QWORD *)this + 13) = qword_1400639A0;
          qword_1400639A0 = (__int64)this + 88;
          LeaveCriticalSection(&stru_140063978);
          DialogW = (HWND)AtlAxCreateDialogW(hModule, (LPCWSTR)0x70);
          ShowWindow(DialogW, 5);
          PumpMessages(DialogW);
        }
      }
      else
      {
        *((_QWORD *)this + 44) = &si128;
        if ( this == (CRemoteAssistanceApp *)-288LL || this == (CRemoteAssistanceApp *)-272LL )
        {
          ATL::_AtlRaiseException(0xC0000005, v6);
          __debugbreak();
        }
        *((_QWORD *)this + 36) = (char *)this + 272;
        *((_DWORD *)this + 74) = GetCurrentThreadId();
        EnterCriticalSection(&stru_140063978);
        *((_QWORD *)this + 38) = qword_1400639A0;
        qword_1400639A0 = (__int64)this + 288;
        LeaveCriticalSection(&stru_140063978);
        v16 = (HWND)AtlAxCreateDialogW(hModule, (LPCWSTR)0x6F);
        ShowWindow(v16, 5);
        PumpMessages(v16);
        *((_DWORD *)this + 92) = 0;
      }
LABEL_45:
      *((_DWORD *)this + 206) = -1;
      goto LABEL_51;
    }
    v17 = (char *)_AtlModule + 496;
    *((_DWORD *)this + 124) = 1;
    *((_DWORD *)v17 + 7) = 7;
    CSqmManager::ProcessRAEvent(v17, 0);
    Window = CreateWindowExW(0, L"STATIC", L"MSRA", 0, 0x80000000, 0x80000000, 0x80000000, 0x80000000, 0, 0, 0, 0);
    if ( (((unsigned __int64)Window + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      if ( !GetLastError() )
      {
        LastError = -2147467259;
LABEL_54:
        CEventLogger::LogError(
          v19,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0xC2u,
          L"CRemoteAssistanceApp::Run",
          LastError);
        goto LABEL_37;
      }
      LastError = GetLastError();
      v21 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v21 = LastError < 0;
      }
      if ( v21 )
        goto LABEL_54;
    }
    WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
    if ( (((unsigned __int64)WaitableTimerW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      break;
LABEL_35:
    DueTime.QuadPart = -1200000000;
    if ( !SetWaitableTimer(WaitableTimerW, &DueTime, 0, 0, 0, 0) )
    {
      CEventLogger::LogError(
        v25,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        0xD3u,
        L"CRemoteAssistanceApp::Run",
        0);
      goto LABEL_37;
    }
    while ( *((_DWORD *)this + 206) == 32 && v12 == 258 )
    {
      if ( PeekMessageW(&Msg, 0, 0, 0, 1u) != -1 )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
        v12 = WaitForSingleObject(WaitableTimerW, 0x1F4u);
      }
    }
    DestroyWindow(Window);
    if ( v12 != 258 )
      goto LABEL_45;
    if ( *((_DWORD *)this + 206) == 111 )
    {
      *((_DWORD *)this + 92) = 1;
      v27 = CNovInterDlg::InitializeVC((CRemoteAssistanceApp *)((char *)this + 272));
      if ( v27 < 0 )
      {
        CEventLogger::LogError(
          v28,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0x104u,
          L"CRemoteAssistanceApp::Run",
          v27);
        goto LABEL_37;
      }
    }
    else
    {
      v29 = *((_QWORD *)this + 47);
      if ( !v29 )
      {
        CEventLogger::LogError(
          0,
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\app.cpp",
          0x10Cu,
          L"CRemoteAssistanceApp::Run",
          0x80004003);
        goto LABEL_37;
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 96LL))(v29);
    }
LABEL_51:
    v11 = *((_DWORD *)this + 206);
    if ( v11 == -1 )
      goto LABEL_37;
  }
  if ( GetLastError() )
  {
    v23 = GetLastError();
    v24 = v23 < 0;
    if ( v23 > 0 )
    {
      v23 = (unsigned __int16)v23 | 0x80070000;
      v24 = v23 < 0;
    }
    if ( v24 )
      goto LABEL_56;
    goto LABEL_35;
  }
  v23 = -2147467259;
LABEL_56:
  CEventLogger::LogError(
    v22,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\app.cpp",
    0xC9u,
    L"CRemoteAssistanceApp::Run",
    v23);
LABEL_37:
  FreeLibrary(LibraryW);
  if ( WaitableTimerW )
    CloseHandle(WaitableTimerW);
  return 0;
}

```

## disassembly

```asm
0x140016bd4  mov     [rsp-8+arg_8], rbx
0x140016bd9  mov     [rsp-8+arg_10], rsi
0x140016bde  push    rbp
0x140016bdf  push    rdi
0x140016be0  push    r13
0x140016be2  push    r14
0x140016be4  push    r15
0x140016be6  lea     rbp, [rsp-37h]
0x140016beb  sub     rsp, 0C0h
0x140016bf2  mov     rax, cs:__security_cookie
0x140016bf9  xor     rax, rsp
0x140016bfc  mov     [rbp+57h+var_28], rax
0x140016c00  xorps   xmm0, xmm0
0x140016c03  mov     qword ptr [rbp+57h+DueTime], 0
0x140016c0b  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x140016c0f  mov     rdi, rcx
0x140016c12  lea     rcx, [rbp+57h+picce]; picce
0x140016c16  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x140016c1a  mov     [rbp+57h+lpLibFileName], 0
0x140016c22  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x140016c26  mov     [rbp+57h+picce.dwSize], 8
0x140016c2d  movdqa  xmm0, cs:__xmm@00000064000000640000006400000064
0x140016c35  movups  [rbp+57h+var_38], xmm0
0x140016c39  mov     [rbp+57h+picce.dwICC], 802Fh
0x140016c40  call    cs:__imp_InitCommonControlsEx
0x140016c47  nop     dword ptr [rax+rax+00h]
0x140016c4c  test    eax, eax
0x140016c4e  jnz     short loc_140016C7C
0x140016c50  mov     [rsp+0E0h+Y], eax; unsigned int
0x140016c54  lea     r9d, [rax+53h]; unsigned int
0x140016c58  lea     rax, aCremoteassista_3; "CRemoteAssistanceApp::Run"
0x140016c5f  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x140016c66  mov     qword ptr [rsp+0E0h+X], rax; unsigned __int16 *
0x140016c6b  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140016c72  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140016c77  jmp     loc_140017052
0x140016c7c  call    cs:__imp_LinkWindow_RegisterClass
0x140016c83  nop     dword ptr [rax+rax+00h]
0x140016c88  lea     r8, aMsfteditDll; "\\MSFTEDIT.DLL"
0x140016c8f  mov     ecx, 25h ; '%'; csidl
0x140016c94  lea     rdx, [rbp+57h+lpLibFileName]; unsigned __int16 **
0x140016c98  call    ?GetDirectoryAsBSTR@@YAJHPEAPEAGPEAG@Z; GetDirectoryAsBSTR(int,ushort * *,ushort *)
0x140016c9d  test    eax, eax
0x140016c9f  jns     short loc_140016CAD
0x140016ca1  mov     [rsp+0E0h+Y], eax
0x140016ca5  mov     r9d, 5Ch ; '\'
0x140016cab  jmp     short loc_140016C58
0x140016cad  mov     rbx, [rbp+57h+lpLibFileName]
0x140016cb1  mov     rcx, rbx; lpLibFileName
0x140016cb4  call    cs:__imp_LoadLibraryW
0x140016cbb  nop     dword ptr [rax+rax+00h]
0x140016cc0  mov     r14, rax
0x140016cc3  test    rbx, rbx
0x140016cc6  jz      short loc_140016CD7
0x140016cc8  mov     rcx, rbx; bstrString
0x140016ccb  call    cs:__imp_SysFreeString
0x140016cd2  nop     dword ptr [rax+rax+00h]
0x140016cd7  test    r14, r14
0x140016cda  jnz     short loc_140016CED
0x140016cdc  mov     [rsp+0E0h+Y], 80004003h
0x140016ce4  lea     r9d, [r14+5Fh]
0x140016ce8  jmp     loc_140016C58
0x140016ced  mov     ecx, [rdi+334h]
0x140016cf3  xor     esi, esi
0x140016cf5  or      r13d, 0FFFFFFFFh
0x140016cf9  lea     eax, [rcx-6Fh]
0x140016cfc  cmp     eax, 1
0x140016cff  jbe     short loc_140016D1B
0x140016d01  cmp     ecx, r13d
0x140016d04  jz      short loc_140016D1B
0x140016d06  cmp     ecx, 20h ; ' '
0x140016d09  jz      short loc_140016D1B
0x140016d0b  mov     edx, ecx; unsigned int
0x140016d0d  mov     rcx, [rdi+1E8h]; this
0x140016d14  call    ?ShowWizard@CWizard@@QEAAJI@Z; CWizard::ShowWizard(uint)
0x140016d19  jmp     short loc_140016D21
0x140016d1b  mov     [rdi+338h], ecx
0x140016d21  mov     ecx, [rdi+338h]
0x140016d27  cmp     ecx, r13d
0x140016d2a  jz      loc_14001702F
0x140016d30  mov     r15d, 102h
0x140016d36  sub     ecx, 20h ; ' '
0x140016d39  jz      loc_140016EA6
0x140016d3f  sub     ecx, 4Fh ; 'O'
0x140016d42  jz      loc_140016DF5
0x140016d48  cmp     ecx, 1
0x140016d4b  jnz     loc_140017103
0x140016d51  lea     rax, [rbp+57h+var_38]
0x140016d55  mov     [rdi+0A8h], rax
0x140016d5c  lea     rax, [rdi+48h]
0x140016d60  lea     rbx, [rax+10h]
0x140016d64  test    rbx, rbx
0x140016d67  jz      loc_1400171AD
0x140016d6d  test    rax, rax
0x140016d70  jz      loc_1400171AD
0x140016d76  mov     [rbx], rax
0x140016d79  call    cs:__imp_GetCurrentThreadId
0x140016d80  nop     dword ptr [rax+rax+00h]
0x140016d85  lea     rcx, stru_140063978; lpCriticalSection
0x140016d8c  mov     [rbx+8], eax
0x140016d8f  call    cs:__imp_EnterCriticalSection
0x140016d96  nop     dword ptr [rax+rax+00h]
0x140016d9b  mov     rax, cs:qword_1400639A0
0x140016da2  lea     rcx, stru_140063978; lpCriticalSection
0x140016da9  mov     [rbx+10h], rax
0x140016dad  mov     cs:qword_1400639A0, rbx
0x140016db4  call    cs:__imp_LeaveCriticalSection
0x140016dbb  nop     dword ptr [rax+rax+00h]
0x140016dc0  mov     rcx, cs:hModule; hInstance
0x140016dc7  mov     edx, 70h ; 'p'; lpName
0x140016dcc  call    AtlAxCreateDialogW
0x140016dd1  mov     rbx, rax
0x140016dd4  mov     edx, 5; nCmdShow
0x140016dd9  mov     rcx, rax; hWnd
0x140016ddc  call    cs:__imp_ShowWindow
0x140016de3  nop     dword ptr [rax+rax+00h]
0x140016de8  mov     rcx, rbx; hDlg
0x140016deb  call    ?PumpMessages@@YAXPEAUHWND__@@@Z; PumpMessages(HWND__ *)
0x140016df0  jmp     loc_140017103
0x140016df5  lea     rax, [rbp+57h+var_38]
0x140016df9  mov     [rdi+160h], rax
0x140016e00  lea     rax, [rdi+110h]
0x140016e07  lea     rbx, [rax+10h]
0x140016e0b  test    rbx, rbx
0x140016e0e  jz      loc_1400171A2
0x140016e14  test    rax, rax
0x140016e17  jz      loc_1400171A2
0x140016e1d  mov     [rbx], rax
0x140016e20  call    cs:__imp_GetCurrentThreadId
0x140016e27  nop     dword ptr [rax+rax+00h]
0x140016e2c  lea     rcx, stru_140063978; lpCriticalSection
0x140016e33  mov     [rbx+8], eax
0x140016e36  call    cs:__imp_EnterCriticalSection
0x140016e3d  nop     dword ptr [rax+rax+00h]
0x140016e42  mov     rax, cs:qword_1400639A0
0x140016e49  lea     rcx, stru_140063978; lpCriticalSection
0x140016e50  mov     [rbx+10h], rax
0x140016e54  mov     cs:qword_1400639A0, rbx
0x140016e5b  call    cs:__imp_LeaveCriticalSection
0x140016e62  nop     dword ptr [rax+rax+00h]
0x140016e67  mov     rcx, cs:hModule; hInstance
0x140016e6e  mov     edx, 6Fh ; 'o'; lpName
0x140016e73  call    AtlAxCreateDialogW
0x140016e78  mov     edx, 5; nCmdShow
0x140016e7d  mov     rcx, rax; hWnd
0x140016e80  mov     rbx, rax
0x140016e83  call    cs:__imp_ShowWindow
0x140016e8a  nop     dword ptr [rax+rax+00h]
0x140016e8f  mov     rcx, rbx; hDlg
0x140016e92  call    ?PumpMessages@@YAXPEAUHWND__@@@Z; PumpMessages(HWND__ *)
0x140016e97  mov     dword ptr [rdi+170h], 0
0x140016ea1  jmp     loc_140017103
0x140016ea6  mov     rcx, cs:?_AtlModule@@3PEAVCRemoteAssistanceApp@@EA; CRemoteAssistanceApp * _AtlModule
0x140016ead  xor     edx, edx
0x140016eaf  add     rcx, 1F0h
0x140016eb6  mov     dword ptr [rdi+1F0h], 1
0x140016ec0  mov     dword ptr [rcx+1Ch], 7
0x140016ec7  call    ?ProcessRAEvent@CSqmManager@@QEAAXW4_RASQM_EVENT@@@Z; CSqmManager::ProcessRAEvent(_RASQM_EVENT)
0x140016ecc  mov     [rsp+0E0h+lpParam], 0; lpParam
0x140016ed5  lea     r8, WindowName; "MSRA"
0x140016edc  mov     [rsp+0E0h+hInstance], 0; hInstance
0x140016ee5  lea     rdx, ClassName; "STATIC"
0x140016eec  mov     [rsp+0E0h+hMenu], 0; hMenu
0x140016ef5  xor     r9d, r9d; dwStyle
0x140016ef8  mov     [rsp+0E0h+hWndParent], 0; hWndParent
0x140016f01  xor     ecx, ecx; dwExStyle
0x140016f03  mov     [rsp+0E0h+nHeight], 80000000h; nHeight
0x140016f0b  mov     [rsp+0E0h+nWidth], 80000000h; nWidth
0x140016f13  mov     [rsp+0E0h+Y], 80000000h; Y
0x140016f1b  mov     [rsp+0E0h+X], 80000000h; X
0x140016f23  call    cs:__imp_CreateWindowExW
0x140016f2a  nop     dword ptr [rax+rax+00h]
0x140016f2f  mov     rbx, rax
0x140016f32  lea     rcx, [rax+1]
0x140016f36  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140016f3d  jnz     short loc_140016F73
0x140016f3f  call    cs:__imp_GetLastError
0x140016f46  nop     dword ptr [rax+rax+00h]
0x140016f4b  test    eax, eax
0x140016f4d  jz      loc_140017167
0x140016f53  call    cs:__imp_GetLastError
0x140016f5a  nop     dword ptr [rax+rax+00h]
0x140016f5f  test    eax, eax
0x140016f61  jle     short loc_140016F6D
0x140016f63  movzx   eax, ax
0x140016f66  or      eax, 80070000h
0x140016f6b  test    eax, eax
0x140016f6d  js      loc_14001716C
0x140016f73  xor     r8d, r8d; lpTimerName
0x140016f76  xor     ecx, ecx; lpTimerAttributes
0x140016f78  lea     edx, [r8+1]; bManualReset
0x140016f7c  call    cs:__imp_CreateWaitableTimerW
0x140016f83  nop     dword ptr [rax+rax+00h]
0x140016f88  mov     rsi, rax
0x140016f8b  lea     rcx, [rax+1]
0x140016f8f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140016f96  jnz     short loc_140016FCC
0x140016f98  call    cs:__imp_GetLastError
0x140016f9f  nop     dword ptr [rax+rax+00h]
0x140016fa4  test    eax, eax
0x140016fa6  jz      loc_14001717B
0x140016fac  call    cs:__imp_GetLastError
0x140016fb3  nop     dword ptr [rax+rax+00h]
0x140016fb8  test    eax, eax
0x140016fba  jle     short loc_140016FC6
0x140016fbc  movzx   eax, ax
0x140016fbf  or      eax, 80070000h
0x140016fc4  test    eax, eax
0x140016fc6  js      loc_140017180
0x140016fcc  mov     [rsp+0E0h+Y], 0; fResume
0x140016fd4  lea     rdx, [rbp+57h+DueTime]; lpDueTime
0x140016fd8  xor     r9d, r9d; pfnCompletionRoutine
0x140016fdb  mov     qword ptr [rsp+0E0h+X], 0; lpArgToCompletionRoutine
0x140016fe4  xor     r8d, r8d; lPeriod
0x140016fe7  mov     qword ptr [rbp+57h+DueTime], 0FFFFFFFFB8797400h
0x140016fef  mov     rcx, rsi; hTimer
0x140016ff2  call    cs:__imp_SetWaitableTimer
0x140016ff9  nop     dword ptr [rax+rax+00h]
0x140016ffe  test    eax, eax
0x140017000  jnz     loc_1400170E2
0x140017006  mov     [rsp+0E0h+Y], eax; unsigned int
0x14001700a  mov     r9d, 0D3h; unsigned int
0x140017010  lea     rax, aCremoteassista_3; "CRemoteAssistanceApp::Run"
0x140017017  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14001701e  mov     qword ptr [rsp+0E0h+X], rax; unsigned __int16 *
0x140017023  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001702a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001702f  mov     rcx, r14; hLibModule
0x140017032  call    cs:__imp_FreeLibrary
0x140017039  nop     dword ptr [rax+rax+00h]
0x14001703e  test    rsi, rsi
0x140017041  jz      short loc_140017052
0x140017043  mov     rcx, rsi; hObject
0x140017046  call    cs:__imp_CloseHandle
0x14001704d  nop     dword ptr [rax+rax+00h]
0x140017052  xor     eax, eax
0x140017054  mov     rcx, [rbp+57h+var_28]
0x140017058  xor     rcx, rsp; StackCookie
0x14001705b  call    __security_check_cookie
0x140017060  lea     r11, [rsp+0E0h+var_20]
0x140017068  mov     rbx, [r11+38h]
0x14001706c  mov     rsi, [r11+40h]
0x140017070  mov     rsp, r11
0x140017073  pop     r15
0x140017075  pop     r14
0x140017077  pop     r13
0x140017079  pop     rdi
0x14001707a  pop     rbp
0x14001707b  retn
0x14001707d  cmp     r15d, 102h
0x140017084  jnz     short loc_1400170EB
0x140017086  xor     r9d, r9d; wMsgFilterMax
0x140017089  mov     [rsp+0E0h+X], 1; wRemoveMsg
0x140017091  xor     r8d, r8d; wMsgFilterMin
0x140017094  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140017098  xor     edx, edx; hWnd
0x14001709a  call    cs:__imp_PeekMessageW
0x1400170a1  nop     dword ptr [rax+rax+00h]
0x1400170a6  cmp     eax, r13d
0x1400170a9  jz      short loc_1400170E2
0x1400170ab  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1400170af  call    cs:__imp_TranslateMessage
0x1400170b6  nop     dword ptr [rax+rax+00h]
0x1400170bb  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1400170bf  call    cs:__imp_DispatchMessageW
0x1400170c6  nop     dword ptr [rax+rax+00h]
0x1400170cb  mov     edx, 1F4h; dwMilliseconds
0x1400170d0  mov     rcx, rsi; hHandle
0x1400170d3  call    cs:__imp_WaitForSingleObject
0x1400170da  nop     dword ptr [rax+rax+00h]
0x1400170df  mov     r15d, eax
0x1400170e2  cmp     dword ptr [rdi+338h], 20h ; ' '
0x1400170e9  jz      short loc_14001707D
0x1400170eb  mov     rcx, rbx; hWnd
0x1400170ee  call    cs:__imp_DestroyWindow
0x1400170f5  nop     dword ptr [rax+rax+00h]
0x1400170fa  cmp     r15d, 102h
0x140017101  jz      short loc_14001710C
0x140017103  mov     [rdi+338h], r13d
0x14001710a  jmp     short loc_140017153
0x14001710c  cmp     dword ptr [rdi+338h], 6Fh ; 'o'
0x140017113  lea     rax, [rdi+110h]
0x14001711a  jnz     short loc_14001713E
0x14001711c  mov     rcx, rax; this
0x14001711f  mov     dword ptr [rax+60h], 1
0x140017126  call    ?InitializeVC@CNovInterDlg@@QEAAJXZ; CNovInterDlg::InitializeVC(void)
0x14001712b  test    eax, eax
0x14001712d  jns     short loc_140017153
0x14001712f  mov     [rsp+0E0h+Y], eax
0x140017133  mov     r9d, 104h
0x140017139  jmp     loc_140017010
0x14001713e  mov     rcx, [rax+68h]
0x140017142  test    rcx, rcx
0x140017145  jz      short loc_14001718F
0x140017147  mov     rax, [rcx]
0x14001714a  mov     rax, [rax+60h]
0x14001714e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017153  mov     ecx, [rdi+338h]
0x140017159  cmp     ecx, r13d
0x14001715c  jnz     loc_140016D36
  ... truncated ...
```
