# wWinMain

- ea: `0x14000e16c`
- end: `0x14000e672`
- name: `wWinMain`
- size: `1286`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400024b0`

## callees

- `0x140001010`
- `0x1400011f4`
- `0x140005a08`
- `0x140005c90`
- `0x140007e90`
- `0x140007f54`
- `0x1400084f8`
- `0x140009938`
- `0x14000dd38`
- `0x14000dd5c`
- `0x14000dd8c`
- `0x14000def8`
- `0x14000df20`
- `0x14000dfc0`
- `0x14000e0a8`
- `0x14000e16c`
- `0x14001706c`
- `0x14001b51c`
- `0x14001b674`
- `0x14001b6f0`
- `0x14001b858`
- `0x140025d70`

## import_xrefs

- `KERNEL32!SetProcessShutdownParameters` at `0x14000e454`
- `KERNEL32!SetProcessShutdownParameters` at `0x14000e454`
- `KERNEL32!CreateMutexW` at `0x14000e2fb`
- `KERNEL32!CreateMutexW` at `0x14000e2fb`
- `KERNEL32!ReleaseMutex` at `0x14000e5ab`
- `KERNEL32!ReleaseMutex` at `0x14000e5ab`
- `KERNEL32!GetTickCount64` at `0x14000e464`
- `KERNEL32!GetTickCount64` at `0x14000e561`
- `KERNEL32!GetTickCount64` at `0x14000e464`
- `KERNEL32!GetTickCount64` at `0x14000e561`
- `KERNEL32!GetLastError` at `0x14000e30d`
- `KERNEL32!GetLastError` at `0x14000e30d`
- `KERNEL32!CloseHandle` at `0x14000e5cd`
- `KERNEL32!CloseHandle` at `0x14000e5cd`
- `KERNEL32!HeapSetInformation` at `0x14000e446`
- `KERNEL32!HeapSetInformation` at `0x14000e446`
- `KERNEL32!RegisterApplicationRestart` at `0x14000e45e`
- `KERNEL32!RegisterApplicationRestart` at `0x14000e45e`
- `USER32!PostMessageW` at `0x14000e41c`
- `USER32!PostMessageW` at `0x14000e41c`
- `USER32!LoadStringW` at `0x14000e362`
- `USER32!LoadStringW` at `0x14000e362`
- `USER32!ShowWindow` at `0x14000e3d9`
- `USER32!ShowWindow` at `0x14000e3d9`
- `USER32!FindWindowW` at `0x14000e373`
- `USER32!FindWindowW` at `0x14000e373`
- `USER32!IsIconic` at `0x14000e3c7`
- `USER32!IsIconic` at `0x14000e3c7`
- `gdiplus!GdiplusStartup` at `0x14000e4bc`
- `gdiplus!GdiplusStartup` at `0x14000e4bc`
- `gdiplus!GdiplusShutdown` at `0x14000e546`
- `gdiplus!GdiplusShutdown` at `0x14000e546`
- `ntdll!WinSqmIsOptedIn` at `0x14000e557`
- `ntdll!WinSqmIsOptedIn` at `0x14000e557`
- `ntdll!WinSqmIncrementDWORD` at `0x14000e478`
- `ntdll!WinSqmIncrementDWORD` at `0x14000e58e`
- `ntdll!WinSqmIncrementDWORD` at `0x14000e478`
- `ntdll!WinSqmIncrementDWORD` at `0x14000e58e`
- `ole32!CoUninitialize` at `0x14000e551`
- `ole32!CoUninitialize` at `0x14000e551`
- `ole32!CoInitialize` at `0x14000e480`
- `ole32!CoInitialize` at `0x14000e480`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e640`
- `OLEAUT32!__imp_SysFreeString` at `0x14000e640`
- `WINMM!waveOutGetNumDevs` at `0x14000e4ca`
- `WINMM!waveOutGetNumDevs` at `0x14000e4ca`
- `DUI70!UnInitThread` at `0x14000e52a`
- `DUI70!UnInitThread` at `0x14000e52a`
- `DUI70!UnInitProcessPriv` at `0x14000e53b`
- `DUI70!UnInitProcessPriv` at `0x14000e53b`
- `DUI70!InitThread` at `0x14000e4f8`
- `DUI70!InitThread` at `0x14000e4f8`
- `DUI70!InitProcessPriv` at `0x14000e4e7`
- `DUI70!InitProcessPriv` at `0x14000e4e7`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  __int64 v6; // rdx
  __int64 v7; // rdx
  __int64 v8; // r8
  PVOID v9; // rcx
  int v10; // esi
  HRESULT inited; // ebx
  int v12; // r14d
  bool ShouldRunSecure; // al
  const WCHAR *v14; // r8
  HWND v15; // rdx
  unsigned int v16; // ecx
  HANDLE MutexW; // r15
  HWND WindowW; // rax
  HWND v19; // rdi
  HWND v20; // rcx
  LPARAM v21; // r9
  WPARAM v22; // r8
  UINT v23; // edx
  char v24; // di
  ULONGLONG TickCount64; // r12
  __int64 v26; // r8
  ULONGLONG v27; // rax
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v31[3]; // [rsp+40h] [rbp-C0h] BYREF
  int v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  BSTR bstrString[2]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF

  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_OSK;
  qword_140037428 = 0;
  WPP_MAIN_CB = 0;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  qword_140037430 = 1;
  WppInitUm(hInstance, hPrevInstance, lpCmdLine, nShowCmd);
  McGenEventRegister_EventRegister(MS_OSK_Provider, v6, &MS_OSK_Provider_Context, &MS_OSK_Provider_Context);
  McGenEventRegister_EventRegister(
    Microsoft_Windows_TabletPC_InputPanel,
    v7,
    Microsoft_Windows_TabletPC_InputPanel_Context,
    Microsoft_Windows_TabletPC_InputPanel_Context);
  TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_140036048);
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids);
  if ( (Microsoft_Windows_oskEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(v9, LaunchApp_Start, v8, 1, bstrString);
  v29 = 0;
  bstrString[0] = 0;
  v10 = 0;
  inited = ATL::CComBSTR::Append((ATL::CComBSTR *)bstrString, lpCmdLine);
  if ( inited >= 0 )
  {
    inited = ProcessCommandLine(bstrString[0]);
    if ( inited >= 0 )
    {
      g_hInstance = hInstance;
      memset(v31, 0, sizeof(v31));
      v12 = ATL::CRegKey::Open((ATL::CRegKey *)v31, HKEY_CURRENT_USER, L"Software\\Microsoft\\Osk", 0x20006u);
      ShouldRunSecure = COSKUtils::ShouldRunSecure();
      v14 = L"SecureOSKRunning";
      if ( !ShouldRunSecure )
        v14 = L"OSKRunning";
      MutexW = CreateMutexW(0, 1, v14);
      if ( !MutexW )
        goto LABEL_46;
      if ( GetLastError() == 183 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids);
        LoadStringW(g_hInstance, 0x3E8u, Buffer, 260);
        WindowW = FindWindowW(L"OSKMainClass", Buffer);
        v19 = WindowW;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids,
            (unsigned int)WindowW);
        if ( v19 )
        {
          v20 = v19;
          if ( byte_1400375B0 )
          {
            v21 = 0;
            v22 = 0;
            v23 = 16;
LABEL_26:
            PostMessageW(v20, v23, v22, v21);
            goto LABEL_45;
          }
          if ( IsIconic(v19) )
            ShowWindow(v19, 9);
          if ( g_OSKCmdLineArgs || byte_1400375AD )
          {
            v23 = 1038;
            v21 = byte_1400375AF != 0 ? 65537LL : 1LL;
            v20 = v19;
            v22 = g_OSKCmdLineArgs != 0;
            goto LABEL_26;
          }
        }
      }
      else
      {
        v24 = 0;
        if ( !byte_1400375AE )
        {
          COSKUtils::SetTempConfig();
          v24 = 1;
        }
        HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
        SetProcessShutdownParameters(0x64u, 1u);
        RegisterApplicationRestart(0, 0);
        TickCount64 = GetTickCount64();
        WinSqmIncrementDWORD(0, 6834, 1);
        inited = CoInitialize(0);
        if ( inited >= 0 )
        {
          v30 = 0;
          v32 = 1;
          v33 = 0;
          v34 = 0;
          v35 = 1;
          if ( !(unsigned int)GdiplusStartup(&v30, &v32, 0) )
          {
            waveOutGetNumDevs();
            LOBYTE(v26) = 1;
            inited = InitProcessPriv(14, &_ImageBase, v26);
            if ( inited >= 0 )
            {
              inited = InitThread(2);
              if ( inited >= 0 )
              {
                if ( !v12 )
                  ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v31, L"RunningState", 1u);
                inited = PresentOSK(&v29);
                UnInitThread();
                v10 = v29;
              }
              UnInitProcessPriv(&_ImageBase);
            }
            GdiplusShutdown(v30);
            v30 = 0;
          }
          CoUninitialize();
        }
        if ( (unsigned int)WinSqmIsOptedIn() )
        {
          v27 = GetTickCount64();
          WinSqmIncrementDWORD(0, 3761, (v27 - TickCount64) / 0x3E8);
        }
        OSKSettingsManager::ClearTransferKey();
        if ( v24 )
          COSKUtils::SetOSKWinlogonRegValue(2u);
        ReleaseMutex(MutexW);
        if ( !v12 )
          ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v31, L"RunningState", 0);
      }
LABEL_45:
      CloseHandle(MutexW);
      if ( inited >= 0 )
      {
LABEL_47:
        WppCleanupUm();
        McGenEventUnregister_EventUnregister(Microsoft_Windows_TabletPC_InputPanel_Context);
        McGenEventUnregister_EventUnregister(&MS_OSK_Provider_Context);
        TraceLoggingUnregister_EventUnregister(&dword_140036048);
        ATL::CRegKey::Close((ATL::CRegKey *)v31);
        goto LABEL_51;
      }
LABEL_46:
      DisplayErrorMessage(v16, v15);
      goto LABEL_47;
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids,
      (unsigned int)inited);
LABEL_51:
  SysFreeString(bstrString[0]);
  return v10;
}

```

## disassembly

```asm
0x14000e16c  mov     [rsp-8+arg_8], rbx
0x14000e171  push    rbp
0x14000e172  push    rsi
0x14000e173  push    rdi
0x14000e174  push    r12
0x14000e176  push    r13
0x14000e178  push    r14
0x14000e17a  push    r15
0x14000e17c  lea     rbp, [rsp-1A0h]
0x14000e184  sub     rsp, 2A0h
0x14000e18b  mov     rax, cs:__security_cookie
0x14000e192  xor     rax, rsp
0x14000e195  mov     [rbp+1D0h+var_40], rax
0x14000e19c  mov     rbx, r8
0x14000e19f  mov     rdi, rcx
0x14000e1a2  xor     r13d, r13d
0x14000e1a5  lea     rax, WPP_ThisDir_CTLGUID_OSK
0x14000e1ac  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x14000e1b3  lea     rax, WPP_MAIN_CB
0x14000e1ba  mov     cs:qword_140037428, r13
0x14000e1c1  mov     cs:WPP_MAIN_CB, r13
0x14000e1c8  lea     r12d, [r13+1]
0x14000e1cc  mov     cs:WPP_GLOBAL_Control, rax
0x14000e1d3  mov     cs:qword_140037430, r12
0x14000e1da  call    WppInitUm
0x14000e1df  lea     r9, MS_OSK_Provider_Context
0x14000e1e6  lea     r8, MS_OSK_Provider_Context
0x14000e1ed  lea     rcx, MS_OSK_Provider
0x14000e1f4  call    McGenEventRegister_EventRegister
0x14000e1f9  lea     r9, Microsoft_Windows_TabletPC_InputPanel_Context
0x14000e200  lea     r8, Microsoft_Windows_TabletPC_InputPanel_Context
0x14000e207  lea     rcx, Microsoft_Windows_TabletPC_InputPanel
0x14000e20e  call    McGenEventRegister_EventRegister
0x14000e213  lea     rcx, dword_140036048; CallbackContext
0x14000e21a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000e21f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e226  lea     r14, WPP_GLOBAL_Control
0x14000e22d  cmp     rcx, r14
0x14000e230  jz      short loc_14000E24C
0x14000e232  test    byte ptr [rcx+1Ch], 10h
0x14000e236  jz      short loc_14000E24C
0x14000e238  mov     rcx, [rcx+10h]
0x14000e23c  lea     edx, [r13+0Eh]
0x14000e240  lea     r8, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids
0x14000e247  call    WPP_SF_
0x14000e24c  test    cs:Microsoft_Windows_oskEnableBits, r12b
0x14000e253  jz      short loc_14000E26E
0x14000e255  lea     rax, [rsp+2D0h+bstrString]
0x14000e25a  mov     r9d, r12d
0x14000e25d  lea     rdx, LaunchApp_Start
0x14000e264  mov     [rsp+2D0h+var_2B0], rax
0x14000e269  call    McGenEventWrite_EventWriteTransfer
0x14000e26e  mov     rdx, rbx; unsigned __int16 *
0x14000e271  mov     [rsp+2D0h+var_2A0], r13d
0x14000e276  lea     rcx, [rsp+2D0h+bstrString]; this
0x14000e27b  mov     [rsp+2D0h+bstrString], r13
0x14000e280  mov     esi, r13d
0x14000e283  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x14000e288  mov     ebx, eax
0x14000e28a  test    eax, eax
0x14000e28c  js      loc_14000E611
0x14000e292  mov     rcx, [rsp+2D0h+bstrString]; unsigned __int16 *
0x14000e297  call    ?ProcessCommandLine@@YAJPEAG@Z; ProcessCommandLine(ushort *)
0x14000e29c  mov     ebx, eax
0x14000e29e  test    eax, eax
0x14000e2a0  js      loc_14000E611
0x14000e2a6  mov     r9d, 20006h; unsigned int
0x14000e2ac  mov     cs:?g_hInstance@@3PEAUHINSTANCE__@@EA, rdi; HINSTANCE__ * g_hInstance
0x14000e2b3  lea     r8, aSoftwareMicros_7; "Software\\Microsoft\\Osk"
0x14000e2ba  mov     [rsp+2D0h+var_290], r13
0x14000e2bf  mov     rdx, 0FFFFFFFF80000001h; hKey
0x14000e2c6  mov     [rsp+2D0h+var_288], r13
0x14000e2cb  lea     rcx, [rsp+2D0h+var_290]; this
0x14000e2d0  mov     [rsp+2D0h+var_280], r13
0x14000e2d5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000e2da  mov     r14d, eax
0x14000e2dd  call    ?ShouldRunSecure@COSKUtils@@SA_NXZ; COSKUtils::ShouldRunSecure(void)
0x14000e2e2  test    al, al
0x14000e2e4  lea     rcx, Name; "OSKRunning"
0x14000e2eb  lea     r8, aSecureoskrunni; "SecureOSKRunning"
0x14000e2f2  mov     edx, r12d; bInitialOwner
0x14000e2f5  cmovz   r8, rcx; lpName
0x14000e2f9  xor     ecx, ecx; lpMutexAttributes
0x14000e2fb  call    cs:__imp_CreateMutexW
0x14000e301  mov     r15, rax
0x14000e304  test    rax, rax
0x14000e307  jz      loc_14000E5D7
0x14000e30d  call    cs:__imp_GetLastError
0x14000e313  cmp     eax, 0B7h
0x14000e318  jnz     loc_14000E427
0x14000e31e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e325  lea     r14, WPP_GLOBAL_Control
0x14000e32c  cmp     rcx, r14
0x14000e32f  jz      short loc_14000E34C
0x14000e331  test    byte ptr [rcx+1Ch], 10h
0x14000e335  jz      short loc_14000E34C
0x14000e337  mov     rcx, [rcx+10h]
0x14000e33b  lea     r8, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids
0x14000e342  mov     edx, 10h
0x14000e347  call    WPP_SF_
0x14000e34c  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x14000e353  lea     r8, [rbp+1D0h+Buffer]; lpBuffer
0x14000e357  mov     r9d, 104h; cchBufferMax
0x14000e35d  mov     edx, 3E8h; uID
0x14000e362  call    cs:__imp_LoadStringW
0x14000e368  lea     rdx, [rbp+1D0h+Buffer]; lpWindowName
0x14000e36c  lea     rcx, ClassName; "OSKMainClass"
0x14000e373  call    cs:__imp_FindWindowW
0x14000e379  mov     rdi, rax
0x14000e37c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e383  cmp     rcx, r14
0x14000e386  jz      short loc_14000E3A6
0x14000e388  test    byte ptr [rcx+1Ch], 10h
0x14000e38c  jz      short loc_14000E3A6
0x14000e38e  mov     rcx, [rcx+10h]
0x14000e392  lea     r8, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids
0x14000e399  mov     r9d, edi
0x14000e39c  mov     edx, 11h
0x14000e3a1  call    WPP_SF_d
0x14000e3a6  test    rdi, rdi
0x14000e3a9  jz      loc_14000E5CA
0x14000e3af  cmp     cs:byte_1400375B0, r13b
0x14000e3b6  mov     rcx, rdi; hWnd
0x14000e3b9  jz      short loc_14000E3C7
0x14000e3bb  xor     r9d, r9d
0x14000e3be  xor     r8d, r8d
0x14000e3c1  lea     edx, [r9+10h]
0x14000e3c5  jmp     short loc_14000E41C
0x14000e3c7  call    cs:__imp_IsIconic
0x14000e3cd  test    eax, eax
0x14000e3cf  jz      short loc_14000E3DF
0x14000e3d1  mov     edx, 9; nCmdShow
0x14000e3d6  mov     rcx, rdi; hWnd
0x14000e3d9  call    cs:__imp_ShowWindow
0x14000e3df  mov     cl, cs:?g_OSKCmdLineArgs@@3UOSKCmdLineArgs@@A; OSKCmdLineArgs g_OSKCmdLineArgs
0x14000e3e5  test    cl, cl
0x14000e3e7  jnz     short loc_14000E3F6
0x14000e3e9  cmp     cs:byte_1400375AD, r13b
0x14000e3f0  jz      loc_14000E5CA
0x14000e3f6  mov     al, cs:byte_1400375AF
0x14000e3fc  mov     r8, r13
0x14000e3ff  neg     al
0x14000e401  mov     edx, 40Eh; Msg
0x14000e406  sbb     r9, r9
0x14000e409  and     r9d, 10000h
0x14000e410  add     r9, r12; lParam
0x14000e413  test    cl, cl
0x14000e415  mov     rcx, rdi; hWnd
0x14000e418  setnz   r8b; wParam
0x14000e41c  call    cs:__imp_PostMessageW
0x14000e422  jmp     loc_14000E5CA
0x14000e427  cmp     cs:byte_1400375AE, r13b
0x14000e42e  mov     dil, r13b
0x14000e431  jnz     short loc_14000E43B
0x14000e433  call    ?SetTempConfig@COSKUtils@@SAXXZ; COSKUtils::SetTempConfig(void)
0x14000e438  mov     dil, r12b
0x14000e43b  xor     r9d, r9d; HeapInformationLength
0x14000e43e  xor     r8d, r8d; HeapInformation
0x14000e441  mov     edx, r12d; HeapInformationClass
0x14000e444  xor     ecx, ecx; HeapHandle
0x14000e446  call    cs:__imp_HeapSetInformation
0x14000e44c  mov     edx, r12d; dwFlags
0x14000e44f  mov     ecx, 64h ; 'd'; dwLevel
0x14000e454  call    cs:__imp_SetProcessShutdownParameters
0x14000e45a  xor     edx, edx; dwFlags
0x14000e45c  xor     ecx, ecx; pwzCommandline
0x14000e45e  call    cs:__imp_RegisterApplicationRestart
0x14000e464  call    cs:__imp_GetTickCount64
0x14000e46a  xor     ecx, ecx
0x14000e46c  mov     edx, 1AB2h
0x14000e471  mov     r12, rax
0x14000e474  lea     r8d, [rcx+1]
0x14000e478  call    cs:__imp_WinSqmIncrementDWORD
0x14000e47e  xor     ecx, ecx; pvReserved
0x14000e480  call    cs:__imp_CoInitialize
0x14000e486  mov     ebx, eax
0x14000e488  test    eax, eax
0x14000e48a  js      loc_14000E557
0x14000e490  xor     r8d, r8d
0x14000e493  mov     [rsp+2D0h+var_298], r13
0x14000e498  lea     rdx, [rsp+2D0h+var_278]
0x14000e49d  mov     [rsp+2D0h+var_278], 1
0x14000e4a5  lea     rcx, [rsp+2D0h+var_298]
0x14000e4aa  mov     [rsp+2D0h+var_270], r13
0x14000e4af  mov     [rsp+2D0h+var_268], r13d
0x14000e4b4  mov     [rsp+2D0h+var_264], 1
0x14000e4bc  call    cs:__imp_GdiplusStartup
0x14000e4c2  test    eax, eax
0x14000e4c4  jnz     loc_14000E551
0x14000e4ca  call    cs:__imp_waveOutGetNumDevs
0x14000e4d0  mov     r9b, 1
0x14000e4d3  mov     byte ptr [rsp+2D0h+var_2B0], 1
0x14000e4d8  mov     r8b, r9b
0x14000e4db  lea     rdx, __ImageBase
0x14000e4e2  mov     ecx, 0Eh
0x14000e4e7  call    cs:__imp_InitProcessPriv
0x14000e4ed  mov     ebx, eax
0x14000e4ef  test    eax, eax
0x14000e4f1  js      short loc_14000E541
0x14000e4f3  mov     ecx, 2
0x14000e4f8  call    cs:__imp_InitThread
0x14000e4fe  mov     ebx, eax
0x14000e500  test    eax, eax
0x14000e502  js      short loc_14000E534
0x14000e504  test    r14d, r14d
0x14000e507  jnz     short loc_14000E51E
0x14000e509  lea     r8d, [r14+1]; unsigned int
0x14000e50d  lea     rdx, aRunningstate; "RunningState"
0x14000e514  lea     rcx, [rsp+2D0h+var_290]; this
0x14000e519  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x14000e51e  lea     rcx, [rsp+2D0h+var_2A0]; int *
0x14000e523  call    ?PresentOSK@@YAJPEAH@Z; PresentOSK(int *)
0x14000e528  mov     ebx, eax
0x14000e52a  call    cs:__imp_UnInitThread
0x14000e530  mov     esi, [rsp+2D0h+var_2A0]
0x14000e534  lea     rcx, __ImageBase
0x14000e53b  call    cs:__imp_UnInitProcessPriv
0x14000e541  mov     rcx, [rsp+2D0h+var_298]
0x14000e546  call    cs:__imp_GdiplusShutdown
0x14000e54c  mov     [rsp+2D0h+var_298], r13
0x14000e551  call    cs:__imp_CoUninitialize
0x14000e557  call    cs:__imp_WinSqmIsOptedIn
0x14000e55d  test    eax, eax
0x14000e55f  jz      short loc_14000E594
0x14000e561  call    cs:__imp_GetTickCount64
0x14000e567  mov     r8, rax
0x14000e56a  xor     ecx, ecx
0x14000e56c  sub     r8, r12
0x14000e56f  mov     rax, 624DD2F1A9FBE77h
0x14000e579  mul     r8
0x14000e57c  sub     r8, rdx
0x14000e57f  shr     r8, 1
0x14000e582  add     r8, rdx
0x14000e585  mov     edx, 0EB1h
0x14000e58a  shr     r8, 9
0x14000e58e  call    cs:__imp_WinSqmIncrementDWORD
0x14000e594  call    ?ClearTransferKey@OSKSettingsManager@@SAXXZ; OSKSettingsManager::ClearTransferKey(void)
0x14000e599  test    dil, dil
0x14000e59c  jz      short loc_14000E5A8
0x14000e59e  mov     ecx, 2; unsigned int
0x14000e5a3  call    ?SetOSKWinlogonRegValue@COSKUtils@@CAXK@Z; COSKUtils::SetOSKWinlogonRegValue(ulong)
0x14000e5a8  mov     rcx, r15; hMutex
0x14000e5ab  call    cs:__imp_ReleaseMutex
0x14000e5b1  test    r14d, r14d
0x14000e5b4  jnz     short loc_14000E5CA
0x14000e5b6  xor     r8d, r8d; unsigned int
0x14000e5b9  lea     rdx, aRunningstate; "RunningState"
0x14000e5c0  lea     rcx, [rsp+2D0h+var_290]; this
0x14000e5c5  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x14000e5ca  mov     rcx, r15; hObject
0x14000e5cd  call    cs:__imp_CloseHandle
0x14000e5d3  test    ebx, ebx
0x14000e5d5  jns     short loc_14000E5DC
0x14000e5d7  call    ?DisplayErrorMessage@@YAXKPEAUHWND__@@@Z; DisplayErrorMessage(ulong,HWND__ *)
0x14000e5dc  call    WppCleanupUm
0x14000e5e1  lea     rcx, Microsoft_Windows_TabletPC_InputPanel_Context
0x14000e5e8  call    McGenEventUnregister_EventUnregister
0x14000e5ed  lea     rcx, MS_OSK_Provider_Context
0x14000e5f4  call    McGenEventUnregister_EventUnregister
0x14000e5f9  lea     rcx, dword_140036048
0x14000e600  call    TraceLoggingUnregister_EventUnregister
0x14000e605  lea     rcx, [rsp+2D0h+var_290]; this
0x14000e60a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000e60f  jmp     short loc_14000E63B
0x14000e611  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e618  cmp     rcx, r14
0x14000e61b  jz      short loc_14000E63B
0x14000e61d  test    [rcx+1Ch], r12b
0x14000e621  jz      short loc_14000E63B
0x14000e623  mov     rcx, [rcx+10h]
0x14000e627  lea     r8, WPP_45cd2bf34f4235acf12ddc09e96c1ec9_Traceguids
0x14000e62e  mov     edx, 0Fh
0x14000e633  mov     r9d, ebx
0x14000e636  call    WPP_SF_d
0x14000e63b  mov     rcx, [rsp+2D0h+bstrString]; bstrString
0x14000e640  call    cs:__imp_SysFreeString
0x14000e646  mov     eax, esi
0x14000e648  mov     rcx, [rbp+1D0h+var_40]
0x14000e64f  xor     rcx, rsp; StackCookie
0x14000e652  call    __security_check_cookie
0x14000e657  mov     rbx, [rsp+2D0h+arg_8]
0x14000e65f  add     rsp, 2A0h
0x14000e666  pop     r15
0x14000e668  pop     r14
0x14000e66a  pop     r13
0x14000e66c  pop     r12
0x14000e66e  pop     rdi
0x14000e66f  pop     rsi
0x14000e670  pop     rbp
0x14000e671  retn
```
