# LaunchColorCpl(HWND__ *)

- ea: `0x180006880`
- end: `0x180006b3e`
- name: `?LaunchColorCpl@@YAJPEAUHWND__@@@Z`
- size: `702`
- prototype: `__int64 __fastcall(HINSTANCE)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180001334`
- `0x18000134c`
- `0x180006880`
- `0x18000bd60`
- `0x18000c018`
- `0x180010ddc`
- `0x180010f08`
- `0x180015cc8`
- `0x180018500`

## import_xrefs

- `KERNEL32!GetCommandLineW` at `0x1800068b6`
- `KERNEL32!GetCommandLineW` at `0x1800068b6`
- `KERNEL32!CreateMutexW` at `0x18000699a`
- `KERNEL32!CreateMutexW` at `0x18000699a`
- `KERNEL32!WaitForSingleObject` at `0x1800069c7`
- `KERNEL32!WaitForSingleObject` at `0x1800069c7`
- `KERNEL32!ReleaseMutex` at `0x180006a7f`
- `KERNEL32!ReleaseMutex` at `0x180006a7f`
- `KERNEL32!GetLastError` at `0x1800069b1`
- `KERNEL32!GetLastError` at `0x1800069b1`
- `KERNEL32!CloseHandle` at `0x180006a8c`
- `KERNEL32!CloseHandle` at `0x180006a8c`
- `KERNEL32!LocalFree` at `0x180006b0a`
- `KERNEL32!LocalFree` at `0x180006b0a`
- `SHELL32!CommandLineToArgvW` at `0x1800068c4`
- `SHELL32!CommandLineToArgvW` at `0x1800068c4`
- `USER32!AllowSetForegroundWindow` at `0x180006a38`
- `USER32!AllowSetForegroundWindow` at `0x180006a38`
- `USER32!SendMessageTimeoutW` at `0x180006a64`
- `USER32!SendMessageTimeoutW` at `0x180006a64`
- `USER32!LoadStringW` at `0x1800069f7`
- `USER32!LoadStringW` at `0x1800069f7`
- `USER32!FindWindowW` at `0x180006a0f`
- `USER32!FindWindowW` at `0x180006a0f`
- `USER32!RegisterWindowMessageW` at `0x1800069d4`
- `USER32!RegisterWindowMessageW` at `0x1800069d4`
- `USER32!GetWindowThreadProcessId` at `0x180006a2e`
- `USER32!GetWindowThreadProcessId` at `0x180006a2e`
- `ole32!CoUninitialize` at `0x180006ae3`
- `ole32!CoUninitialize` at `0x180006ae3`
- `ole32!CoInitializeEx` at `0x1800068e6`
- `ole32!CoInitializeEx` at `0x1800068e6`
- `mscms!ColorCplUninitialize` at `0x180006add`
- `mscms!ColorCplUninitialize` at `0x180006add`
- `mscms!ColorCplInitialize` at `0x1800068f6`
- `mscms!ColorCplInitialize` at `0x1800068f6`

## pseudocode

```c
__int64 __fastcall LaunchColorCpl(HINSTANCE a1)
{
  const WCHAR *CommandLineW; // rax
  const unsigned __int16 **v3; // r15
  int v4; // r14d
  HRESULT v5; // ebx
  HINSTANCE *v6; // rdi
  ColorDataController *v7; // rax
  HINSTANCE v8; // rdx
  ColorDataController *v9; // rax
  ColorDataController *v10; // rbp
  HRESULT v11; // eax
  HWND WindowW; // rax
  HWND v13; // rbx
  UINT fuFlags; // [rsp+20h] [rbp-278h]
  int pNumArgs; // [rsp+40h] [rbp-258h] BYREF
  DWORD dwProcessId; // [rsp+44h] [rbp-254h] BYREF
  ULONG_PTR dwResult; // [rsp+48h] [rbp-250h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-248h] BYREF

  pNumArgs = 0;
  CommandLineW = GetCommandLineW();
  v3 = (const unsigned __int16 **)CommandLineToArgvW(CommandLineW, &pNumArgs);
  if ( pNumArgs == 2 )
  {
    v4 = 1;
    goto LABEL_3;
  }
  v4 = 0;
  g_hStartupMutex = CreateMutexW(0, 1, L"Local\\Color CPL Startup Mutex");
  if ( g_hStartupMutex && GetLastError() == 183 )
    WaitForSingleObject(g_hStartupMutex, 0x2710u);
  g_uMsgActivateColorCpl = RegisterWindowMessageW(L"Microsoft.Windows.ICM.ColorCpl.Activate");
  if ( !LoadStringW(g_hInst, 6u, Buffer, 260)
    || (WindowW = FindWindowW((LPCWSTR)0x8002, Buffer), (v13 = WindowW) == 0)
    || (dwProcessId = 0,
        GetWindowThreadProcessId(WindowW, &dwProcessId),
        AllowSetForegroundWindow(dwProcessId),
        dwResult = 0,
        !SendMessageTimeoutW(v13, g_uMsgActivateColorCpl, 0, 0, 2u, 0x2710u, &dwResult)) )
  {
LABEL_3:
    v5 = CoInitializeEx(0, 2u);
    if ( v5 < 0 )
      goto LABEL_32;
    v5 = ColorCplInitialize();
    if ( v5 < 0 )
    {
LABEL_31:
      CoUninitialize();
      if ( v5 >= 0 )
      {
LABEL_33:
        if ( v3 )
          LocalFree(v3);
        return (unsigned int)v5;
      }
LABEL_32:
      Helper::ShowErrorDialog(g_hInst, a1, 0, (const unsigned __int16 *)(unsigned int)v5, fuFlags);
      goto LABEL_33;
    }
    v6 = (HINSTANCE *)operator new(0x10u);
    if ( !v6 )
    {
      v5 = -2147024882;
LABEL_30:
      ColorCplUninitialize();
      goto LABEL_31;
    }
    *v6 = g_hInst;
    *((_DWORD *)v6 + 2) = 0;
    *((_DWORD *)v6 + 3) = 1;
    v5 = *((_DWORD *)v6 + 2);
    if ( v5 < 0 )
    {
      v10 = 0;
    }
    else
    {
      v7 = (ColorDataController *)operator new(0x38u);
      if ( v7 )
      {
        v9 = ColorDataController::ColorDataController(v7, v8);
        v10 = v9;
        if ( v9 )
        {
          v5 = *((_DWORD *)v9 + 3);
          if ( v5 >= 0 )
          {
            if ( v4 )
              v11 = ColorWnd::InstallProfile(v6, v9, v3[1]);
            else
              v11 = ColorWnd::Start((ColorWnd *)v6, v9, 0);
            v5 = v11;
          }
          goto LABEL_26;
        }
      }
      else
      {
        v10 = 0;
      }
      v5 = -2147024882;
    }
LABEL_26:
    operator delete(v6);
    if ( v10 )
    {
      ColorDataController::~ColorDataController(v10);
      operator delete(v10);
    }
    goto LABEL_30;
  }
  if ( g_hStartupMutex )
  {
    ReleaseMutex(g_hStartupMutex);
    CloseHandle(g_hStartupMutex);
    g_hStartupMutex = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180006880  mov     [rsp+arg_8], rbx
0x180006885  mov     [rsp+arg_10], rbp
0x18000688a  push    rsi
0x18000688b  push    rdi
0x18000688c  push    r12
0x18000688e  push    r14
0x180006890  push    r15
0x180006892  sub     rsp, 270h
0x180006899  mov     rax, cs:__security_cookie
0x1800068a0  xor     rax, rsp
0x1800068a3  mov     [rsp+298h+var_38], rax
0x1800068ab  mov     r12, rcx
0x1800068ae  mov     [rsp+298h+pNumArgs], 0
0x1800068b6  call    cs:__imp_GetCommandLineW
0x1800068bc  mov     rcx, rax; lpCmdLine
0x1800068bf  lea     rdx, [rsp+298h+pNumArgs]; pNumArgs
0x1800068c4  call    cs:__imp_CommandLineToArgvW
0x1800068ca  mov     edi, 2
0x1800068cf  mov     r15, rax
0x1800068d2  lea     esi, [rdi-1]
0x1800068d5  cmp     [rsp+298h+pNumArgs], edi
0x1800068d9  jnz     loc_18000698C
0x1800068df  mov     r14d, esi
0x1800068e2  mov     edx, edi; dwCoInit
0x1800068e4  xor     ecx, ecx; pvReserved
0x1800068e6  call    cs:__imp_CoInitializeEx
0x1800068ec  mov     ebx, eax
0x1800068ee  test    eax, eax
0x1800068f0  js      loc_180006AED
0x1800068f6  call    cs:__imp_ColorCplInitialize
0x1800068fc  mov     ebx, eax
0x1800068fe  test    eax, eax
0x180006900  js      loc_180006AE3
0x180006906  mov     ecx, 10h; Size
0x18000690b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006910  mov     rdi, rax
0x180006913  test    rax, rax
0x180006916  jz      loc_180006AD8
0x18000691c  mov     rax, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInst
0x180006923  mov     [rdi], rax
0x180006926  mov     dword ptr [rdi+8], 0
0x18000692d  mov     [rdi+0Ch], esi
0x180006930  mov     ebx, [rdi+8]
0x180006933  test    ebx, ebx
0x180006935  js      loc_180006AB3
0x18000693b  mov     ecx, 38h ; '8'; Size
0x180006940  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006945  test    rax, rax
0x180006948  jz      loc_180006AAA
0x18000694e  mov     rcx, rax; this
0x180006951  call    ??0ColorDataController@@QEAA@PEAUHINSTANCE__@@@Z; ColorDataController::ColorDataController(HINSTANCE__ *)
0x180006956  mov     rbp, rax
0x180006959  test    rax, rax
0x18000695c  jz      loc_180006AAC
0x180006962  mov     ebx, [rax+0Ch]
0x180006965  test    ebx, ebx
0x180006967  js      loc_180006AB5
0x18000696d  mov     rdx, rax; struct ColorDataController *
0x180006970  mov     rcx, rdi; this
0x180006973  test    r14d, r14d
0x180006976  jz      loc_180006A9D
0x18000697c  mov     r8, [r15+8]; unsigned __int16 *
0x180006980  call    ?InstallProfile@ColorWnd@@QEAAJPEAVColorDataController@@PEBG@Z; ColorWnd::InstallProfile(ColorDataController *,ushort const *)
0x180006985  mov     ebx, eax
0x180006987  jmp     loc_180006AB5
0x18000698c  lea     r8, Name; "Local\\Color CPL Startup Mutex"
0x180006993  mov     edx, esi; bInitialOwner
0x180006995  xor     ecx, ecx; lpMutexAttributes
0x180006997  xor     r14d, r14d
0x18000699a  call    cs:__imp_CreateMutexW
0x1800069a0  mov     cs:?g_hStartupMutex@@3PEAXEA, rax; void * g_hStartupMutex
0x1800069a7  mov     ebp, 2710h
0x1800069ac  test    rax, rax
0x1800069af  jz      short loc_1800069CD
0x1800069b1  call    cs:__imp_GetLastError
0x1800069b7  cmp     eax, 0B7h
0x1800069bc  jnz     short loc_1800069CD
0x1800069be  mov     rcx, cs:?g_hStartupMutex@@3PEAXEA; hHandle
0x1800069c5  mov     edx, ebp; dwMilliseconds
0x1800069c7  call    cs:__imp_WaitForSingleObject
0x1800069cd  lea     rcx, String; "Microsoft.Windows.ICM.ColorCpl.Activate"
0x1800069d4  call    cs:__imp_RegisterWindowMessageW
0x1800069da  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x1800069e1  lea     r8, [rsp+298h+Buffer]; lpBuffer
0x1800069e6  mov     r9d, 104h; cchBufferMax
0x1800069ec  mov     cs:?g_uMsgActivateColorCpl@@3IA, eax; uint g_uMsgActivateColorCpl
0x1800069f2  mov     edx, 6; uID
0x1800069f7  call    cs:__imp_LoadStringW
0x1800069fd  test    eax, eax
0x1800069ff  jz      loc_1800068E2
0x180006a05  lea     rdx, [rsp+298h+Buffer]; lpWindowName
0x180006a0a  mov     ecx, 8002h; lpClassName
0x180006a0f  call    cs:__imp_FindWindowW
0x180006a15  mov     rbx, rax
0x180006a18  test    rax, rax
0x180006a1b  jz      loc_1800068E2
0x180006a21  lea     rdx, [rsp+298h+dwProcessId]; lpdwProcessId
0x180006a26  mov     [rsp+298h+dwProcessId], r14d
0x180006a2b  mov     rcx, rax; hWnd
0x180006a2e  call    cs:__imp_GetWindowThreadProcessId
0x180006a34  mov     ecx, [rsp+298h+dwProcessId]; dwProcessId
0x180006a38  call    cs:__imp_AllowSetForegroundWindow
0x180006a3e  mov     edx, cs:?g_uMsgActivateColorCpl@@3IA; Msg
0x180006a44  lea     rax, [rsp+298h+dwResult]
0x180006a49  mov     [rsp+298h+lpdwResult], rax; lpdwResult
0x180006a4e  xor     r9d, r9d; lParam
0x180006a51  mov     [rsp+298h+uTimeout], ebp; uTimeout
0x180006a55  xor     r8d, r8d; wParam
0x180006a58  mov     rcx, rbx; hWnd
0x180006a5b  mov     [rsp+298h+fuFlags], edi; fuFlags
0x180006a5f  mov     [rsp+298h+dwResult], r14
0x180006a64  call    cs:__imp_SendMessageTimeoutW
0x180006a6a  test    rax, rax
0x180006a6d  jz      loc_1800068E2
0x180006a73  mov     rcx, cs:?g_hStartupMutex@@3PEAXEA; hMutex
0x180006a7a  test    rcx, rcx
0x180006a7d  jz      short loc_180006A99
0x180006a7f  call    cs:__imp_ReleaseMutex
0x180006a85  mov     rcx, cs:?g_hStartupMutex@@3PEAXEA; hObject
0x180006a8c  call    cs:__imp_CloseHandle
0x180006a92  mov     cs:?g_hStartupMutex@@3PEAXEA, r14; void * g_hStartupMutex
0x180006a99  xor     eax, eax
0x180006a9b  jmp     short loc_180006B12
0x180006a9d  xor     r8d, r8d; HWND
0x180006aa0  call    ?Start@ColorWnd@@QEAAJPEAVColorDataController@@PEAUHWND__@@@Z; ColorWnd::Start(ColorDataController *,HWND__ *)
0x180006aa5  jmp     loc_180006985
0x180006aaa  xor     ebp, ebp
0x180006aac  mov     ebx, 8007000Eh
0x180006ab1  jmp     short loc_180006AB5
0x180006ab3  xor     ebp, ebp
0x180006ab5  mov     rcx, rdi; Block
0x180006ab8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006abd  test    rbp, rbp
0x180006ac0  jz      short loc_180006AD2
0x180006ac2  mov     rcx, rbp; this
0x180006ac5  call    ??1ColorDataController@@QEAA@XZ; ColorDataController::~ColorDataController(void)
0x180006aca  mov     rcx, rbp; Block
0x180006acd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006ad2  test    esi, esi
0x180006ad4  jz      short loc_180006AE3
0x180006ad6  jmp     short loc_180006ADD
0x180006ad8  mov     ebx, 8007000Eh
0x180006add  call    cs:__imp_ColorCplUninitialize
0x180006ae3  call    cs:__imp_CoUninitialize
0x180006ae9  test    ebx, ebx
0x180006aeb  jns     short loc_180006B02
0x180006aed  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; this
0x180006af4  mov     r9d, ebx; unsigned __int16 *
0x180006af7  xor     r8d, r8d; HWND
0x180006afa  mov     rdx, r12; HINSTANCE
0x180006afd  call    ?ShowErrorDialog@Helper@@YAJPEAUHINSTANCE__@@PEAUHWND__@@PEBGJ@Z; Helper::ShowErrorDialog(HINSTANCE__ *,HWND__ *,ushort const *,long)
0x180006b02  test    r15, r15
0x180006b05  jz      short loc_180006B10
0x180006b07  mov     rcx, r15; hMem
0x180006b0a  call    cs:__imp_LocalFree
0x180006b10  mov     eax, ebx
0x180006b12  mov     rcx, [rsp+298h+var_38]
0x180006b1a  xor     rcx, rsp; StackCookie
0x180006b1d  call    __security_check_cookie
0x180006b22  lea     r11, [rsp+298h+var_28]
0x180006b2a  mov     rbx, [r11+38h]
0x180006b2e  mov     rbp, [r11+40h]
0x180006b32  mov     rsp, r11
0x180006b35  pop     r15
0x180006b37  pop     r14
0x180006b39  pop     r12
0x180006b3b  pop     rdi
0x180006b3c  pop     rsi
0x180006b3d  retn
```
