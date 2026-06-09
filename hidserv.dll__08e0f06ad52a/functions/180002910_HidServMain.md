# HidServMain

- ea: `0x180002910`
- end: `0x180002e2c`
- name: `HidServMain`
- size: `1308`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x1800025b8`
- `0x1800025e0`
- `0x180002910`
- `0x18000351c`
- `0x180008450`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002cad`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002cad`
- `KERNEL32!WaitForSingleObject` at `0x180002e00`
- `KERNEL32!WaitForSingleObject` at `0x180002e00`
- `KERNEL32!CreateEventW` at `0x180002a6d`
- `KERNEL32!CreateEventW` at `0x180002a8d`
- `KERNEL32!CreateEventW` at `0x180002a6d`
- `KERNEL32!CreateEventW` at `0x180002a8d`
- `KERNEL32!CloseHandle` at `0x1800029bf`
- `KERNEL32!CloseHandle` at `0x1800029d1`
- `KERNEL32!CloseHandle` at `0x1800029e3`
- `KERNEL32!CloseHandle` at `0x1800029f5`
- `KERNEL32!CloseHandle` at `0x180002e09`
- `KERNEL32!CloseHandle` at `0x1800029bf`
- `KERNEL32!CloseHandle` at `0x1800029d1`
- `KERNEL32!CloseHandle` at `0x1800029e3`
- `KERNEL32!CloseHandle` at `0x1800029f5`
- `KERNEL32!CloseHandle` at `0x180002e09`
- `KERNEL32!CreateThread` at `0x180002d62`
- `KERNEL32!CreateThread` at `0x180002d62`
- `KERNEL32!CreateMutexW` at `0x180002956`
- `KERNEL32!CreateMutexW` at `0x180002956`
- `KERNEL32!OpenEventW` at `0x180002ab1`
- `KERNEL32!OpenEventW` at `0x180002ab1`
- `KERNEL32!GetLastError` at `0x18000296f`
- `KERNEL32!GetLastError` at `0x180002b4f`
- `KERNEL32!GetLastError` at `0x180002c6f`
- `KERNEL32!GetLastError` at `0x18000296f`
- `KERNEL32!GetLastError` at `0x180002b4f`
- `KERNEL32!GetLastError` at `0x180002c6f`
- `KERNEL32!SetEvent` at `0x180002a3f`
- `KERNEL32!SetEvent` at `0x180002dab`
- `KERNEL32!SetEvent` at `0x180002a3f`
- `KERNEL32!SetEvent` at `0x180002dab`
- `KERNEL32!GetProcAddress` at `0x180002cfc`
- `KERNEL32!GetProcAddress` at `0x180002cfc`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180002cb3`
- `KERNEL32!WTSGetActiveConsoleSessionId` at `0x180002cb3`
- `KERNEL32!FreeLibrary` at `0x180002a31`
- `KERNEL32!FreeLibrary` at `0x180002a31`
- `KERNEL32!SleepEx` at `0x180002e18`
- `KERNEL32!SleepEx` at `0x180002e18`
- `KERNEL32!LoadLibraryExW` at `0x180002cdc`
- `KERNEL32!LoadLibraryExW` at `0x180002cdc`
- `HID!HidD_GetHidGuid` at `0x180002c1a`
- `HID!HidD_GetHidGuid` at `0x180002c1a`
- `USER32!TranslateMessage` at `0x180002db7`
- `USER32!TranslateMessage` at `0x180002db7`
- `USER32!DispatchMessageW` at `0x180002dc1`
- `USER32!DispatchMessageW` at `0x180002dc1`
- `USER32!RegisterDeviceNotificationW` at `0x180002c2e`
- `USER32!RegisterDeviceNotificationW` at `0x180002c2e`
- `USER32!RegisterClassExW` at `0x180002b15`
- `USER32!RegisterClassExW` at `0x180002b15`
- `USER32!UnregisterClassW` at `0x180002a1c`
- `USER32!UnregisterClassW` at `0x180002df4`
- `USER32!UnregisterClassW` at `0x180002a1c`
- `USER32!UnregisterClassW` at `0x180002df4`
- `USER32!CreateWindowExW` at `0x180002bb5`
- `USER32!CreateWindowExW` at `0x180002bb5`
- `USER32!DestroyWindow` at `0x180002a07`
- `USER32!DestroyWindow` at `0x180002de4`
- `USER32!DestroyWindow` at `0x180002a07`
- `USER32!DestroyWindow` at `0x180002de4`
- `USER32!GetMessageW` at `0x180002dd3`
- `USER32!GetMessageW` at `0x180002dd3`

## string_xrefs

- `0x180002b78`: `HID Input Service`
- `0x180002cce`: `winsta.dll`

## pseudocode

```c
__int64 __fastcall HidServMain(PVOID Parameter)
{
  char v2; // si
  __int64 v3; // r9
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v7; // rbx
  DWORD LastError; // eax
  __int64 v9; // rdx
  DWORD active; // eax
  HMODULE Library; // rax
  HANDLE Thread; // rbx
  WNDCLASSEXW v13; // [rsp+60h] [rbp-A0h] BYREF
  MSG Msg; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD NotificationFilter[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v16; // [rsp+E8h] [rbp-18h] BYREF
  __int64 HidGuid_12; // [rsp+F8h] [rbp-8h]

  memset(&Msg, 0, sizeof(Msg));
  v2 = 0;
  hMutexOOC = CreateMutexW(0, 0, L"OOC State Mutex");
  if ( !hMutexOOC )
    goto LABEL_8;
  if ( GetLastError() == 183 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_8;
    }
    v5 = 10;
    goto LABEL_7;
  }
  hInputEvent = CreateEventW(0, 0, 0, 0);
  if ( !hInputEvent )
    goto LABEL_8;
  hInputDoneEvent = CreateEventW(0, 0, 0, 0);
  if ( !hInputDoneEvent )
    goto LABEL_8;
  hDesktopSwitch = OpenEventW(0x100000u, 0, L"WinSta0_DesktopSwitch");
  if ( !hDesktopSwitch )
    goto LABEL_8;
  *(_QWORD *)&v13.cbSize = 80;
  v13.lpfnWndProc = (WNDPROC)HidServProc;
  v13.hInstance = hInstance;
  InputThreadEnabled = 1;
  *(_QWORD *)&v13.cbClsExtra = 0;
  memset(&v13.hIcon, 0, 32);
  v13.hIconSm = 0;
  v13.lpszClassName = L"HidServClass";
  if ( !RegisterClassExW(&v13) )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
    {
      goto LABEL_8;
    }
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    v9 = 11;
    goto LABEL_33;
  }
  v2 = 1;
  hWndHidServ = CreateWindowExW(0, L"HidServClass", L"HID Input Service", 0xCF0000u, 0, 0, 0, 0, 0, 0, hInstance, 0);
  if ( !hWndHidServ )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_8;
    }
    v5 = 12;
    goto LABEL_7;
  }
  HidGuid_12 = 0;
  NotificationFilter[0] = 32;
  v16 = 0;
  NotificationFilter[1] = 5;
  HidD_GetHidGuid((LPGUID)((char *)&v16 + 4));
  hNotifyArrival = RegisterDeviceNotificationW(hWndHidServ, NotificationFilter, 0);
  if ( !hNotifyArrival )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_8;
    }
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    v9 = 13;
LABEL_33:
    WPP_SF_D(v7, v9, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, LastError);
    goto LABEL_8;
  }
  HidServSetPnP(1);
  ServiceStatus.dwControlsAccepted = 133;
  if ( hService )
  {
    ServiceStatus.dwCurrentState = 4;
    SetServiceStatus(hService, &ServiceStatus);
  }
  active = WTSGetActiveConsoleSessionId();
  IsSessionLocked = 0;
  SessionId = active;
  WinStaDll = 0;
  Library = LoadLibraryExW(L"winsta.dll", 0, 0x800u);
  WinStaDll = Library;
  if ( !Library )
    goto LABEL_8;
  WinStaProc = (__int64)GetProcAddress(Library, "WinStationSendWindowMessage");
  if ( !WinStaProc )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_8;
    }
    v5 = 14;
    goto LABEL_7;
  }
  Thread = CreateThread(0, 0, HidThreadInputProc, 0, 0, &InputThreadId);
  if ( !Thread )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_8;
    }
    v5 = 15;
LABEL_7:
    WPP_SF_(v4[2], v5, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids, v3);
LABEL_8:
    if ( hMutexOOC )
      CloseHandle(hMutexOOC);
    if ( hInputEvent )
      CloseHandle(hInputEvent);
    if ( hInputDoneEvent )
      CloseHandle(hInputDoneEvent);
    if ( hDesktopSwitch )
      CloseHandle(hDesktopSwitch);
    if ( hWndHidServ )
      DestroyWindow(hWndHidServ);
    if ( v2 )
      UnregisterClassW(L"HidServClass", hInstance);
    if ( WinStaDll )
      FreeLibrary(WinStaDll);
    if ( Parameter )
      SetEvent(Parameter);
    return 0;
  }
  if ( Parameter )
    SetEvent(Parameter);
  while ( GetMessageW(&Msg, 0, 0, 0) )
  {
    TranslateMessage(&Msg);
    DispatchMessageW(&Msg);
  }
  DestroyWindow(hWndHidServ);
  UnregisterClassW(L"HidServClass", hInstance);
  WaitForSingleObject(Thread, 0xFFFFFFFF);
  CloseHandle(Thread);
  while ( cThreadRef )
    SleepEx(0x3E8u, 0);
  return 0;
}

```

## disassembly

```asm
0x180002910  push    rbp
0x180002912  push    rbx
0x180002913  push    rsi
0x180002914  push    rdi
0x180002915  push    r14
0x180002917  push    r15
0x180002919  lea     rbp, [rsp-18h]
0x18000291e  sub     rsp, 118h
0x180002925  mov     rax, cs:__security_cookie
0x18000292c  xor     rax, rsp
0x18000292f  mov     [rbp+40h+var_40], rax
0x180002933  xorps   xmm0, xmm0
0x180002936  lea     r8, Name; "OOC State Mutex"
0x18000293d  mov     rdi, rcx
0x180002940  xor     r14d, r14d
0x180002943  xor     ecx, ecx; lpMutexAttributes
0x180002945  xor     edx, edx; bInitialOwner
0x180002947  movups  xmmword ptr [rbp+40h+Msg.hwnd], xmm0
0x18000294b  mov     sil, r14b
0x18000294e  movups  xmmword ptr [rbp+40h+Msg.wParam], xmm0
0x180002952  movups  xmmword ptr [rbp+40h+Msg.time], xmm0
0x180002956  call    cs:__imp_CreateMutexW
0x18000295c  mov     cs:hMutexOOC, rax
0x180002963  lea     r15, ClassName; "HidServClass"
0x18000296a  test    rax, rax
0x18000296d  jz      short loc_1800029B3
0x18000296f  call    cs:__imp_GetLastError
0x180002975  cmp     eax, 0B7h
0x18000297a  jnz     loc_180002A63
0x180002980  mov     rcx, cs:WPP_GLOBAL_Control
0x180002987  lea     rax, WPP_GLOBAL_Control
0x18000298e  cmp     rcx, rax
0x180002991  jz      short loc_1800029B3
0x180002993  test    byte ptr [rcx+1Ch], 10h
0x180002997  jz      short loc_1800029B3
0x180002999  cmp     byte ptr [rcx+19h], 2
0x18000299d  jb      short loc_1800029B3
0x18000299f  lea     edx, [r14+0Ah]
0x1800029a3  mov     rcx, [rcx+10h]
0x1800029a7  lea     r8, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x1800029ae  call    WPP_SF_
0x1800029b3  mov     rcx, cs:hMutexOOC; hObject
0x1800029ba  test    rcx, rcx
0x1800029bd  jz      short loc_1800029C5
0x1800029bf  call    cs:__imp_CloseHandle
0x1800029c5  mov     rcx, cs:hInputEvent; hObject
0x1800029cc  test    rcx, rcx
0x1800029cf  jz      short loc_1800029D7
0x1800029d1  call    cs:__imp_CloseHandle
0x1800029d7  mov     rcx, cs:hInputDoneEvent; hObject
0x1800029de  test    rcx, rcx
0x1800029e1  jz      short loc_1800029E9
0x1800029e3  call    cs:__imp_CloseHandle
0x1800029e9  mov     rcx, cs:hDesktopSwitch; hObject
0x1800029f0  test    rcx, rcx
0x1800029f3  jz      short loc_1800029FB
0x1800029f5  call    cs:__imp_CloseHandle
0x1800029fb  mov     rcx, cs:hWndHidServ; hWnd
0x180002a02  test    rcx, rcx
0x180002a05  jz      short loc_180002A0D
0x180002a07  call    cs:__imp_DestroyWindow
0x180002a0d  test    sil, sil
0x180002a10  jz      short loc_180002A22
0x180002a12  mov     rdx, cs:hInstance; hInstance
0x180002a19  mov     rcx, r15; lpClassName
0x180002a1c  call    cs:__imp_UnregisterClassW
0x180002a22  mov     rax, cs:WinStaDll
0x180002a29  test    rax, rax
0x180002a2c  jz      short loc_180002A37
0x180002a2e  mov     rcx, rax; hLibModule
0x180002a31  call    cs:__imp_FreeLibrary
0x180002a37  test    rdi, rdi
0x180002a3a  jz      short loc_180002A45
0x180002a3c  mov     rcx, rdi; hEvent
0x180002a3f  call    cs:__imp_SetEvent
0x180002a45  xor     eax, eax
0x180002a47  mov     rcx, [rbp+40h+var_40]
0x180002a4b  xor     rcx, rsp; StackCookie
0x180002a4e  call    __security_check_cookie
0x180002a53  add     rsp, 118h
0x180002a5a  pop     r15
0x180002a5c  pop     r14
0x180002a5e  pop     rdi
0x180002a5f  pop     rsi
0x180002a60  pop     rbx
0x180002a61  pop     rbp
0x180002a62  retn
0x180002a63  xor     r9d, r9d; lpName
0x180002a66  xor     r8d, r8d; bInitialState
0x180002a69  xor     edx, edx; bManualReset
0x180002a6b  xor     ecx, ecx; lpEventAttributes
0x180002a6d  call    cs:__imp_CreateEventW
0x180002a73  mov     cs:hInputEvent, rax
0x180002a7a  test    rax, rax
0x180002a7d  jz      loc_1800029B3
0x180002a83  xor     r9d, r9d; lpName
0x180002a86  xor     r8d, r8d; bInitialState
0x180002a89  xor     edx, edx; bManualReset
0x180002a8b  xor     ecx, ecx; lpEventAttributes
0x180002a8d  call    cs:__imp_CreateEventW
0x180002a93  mov     cs:hInputDoneEvent, rax
0x180002a9a  test    rax, rax
0x180002a9d  jz      loc_1800029B3
0x180002aa3  lea     r8, aWinsta0Desktop; "WinSta0_DesktopSwitch"
0x180002aaa  xor     edx, edx; bInheritHandle
0x180002aac  mov     ecx, 100000h; dwDesiredAccess
0x180002ab1  call    cs:__imp_OpenEventW
0x180002ab7  mov     cs:hDesktopSwitch, rax
0x180002abe  test    rax, rax
0x180002ac1  jz      loc_1800029B3
0x180002ac7  lea     rax, HidServProc
0x180002ace  mov     qword ptr [rsp+140h+var_E0.cbSize], 50h ; 'P'
0x180002ad7  mov     [rsp+140h+var_E0.lpfnWndProc], rax
0x180002adc  lea     rcx, [rsp+140h+var_E0]; WNDCLASSEXW *
0x180002ae1  mov     rax, cs:hInstance
0x180002ae8  xorps   xmm0, xmm0
0x180002aeb  mov     ebx, 1
0x180002af0  mov     [rsp+140h+var_E0.hInstance], rax
0x180002af5  mov     cs:InputThreadEnabled, ebx
0x180002afb  mov     qword ptr [rsp+140h+var_E0.cbClsExtra], r14
0x180002b00  mov     [rbp+40h+var_E0.hIcon], r14
0x180002b04  mov     [rbp+40h+var_E0.hIconSm], r14
0x180002b08  mov     [rbp+40h+var_E0.hCursor], r14
0x180002b0c  movdqa  xmmword ptr [rbp+40h+var_E0.hbrBackground], xmm0
0x180002b11  mov     [rbp+40h+var_E0.lpszClassName], r15
0x180002b15  call    cs:__imp_RegisterClassExW
0x180002b1b  test    ax, ax
0x180002b1e  jnz     short loc_180002B71
0x180002b20  mov     rbx, cs:WPP_GLOBAL_Control
0x180002b27  lea     rax, WPP_GLOBAL_Control
0x180002b2e  cmp     rbx, rax
0x180002b31  jz      loc_1800029B3
0x180002b37  test    byte ptr [rbx+1Ch], 10h
0x180002b3b  jz      loc_1800029B3
0x180002b41  cmp     byte ptr [rbx+19h], 3
0x180002b45  jb      loc_1800029B3
0x180002b4b  mov     rbx, [rbx+10h]
0x180002b4f  call    cs:__imp_GetLastError
0x180002b55  mov     edx, 0Bh
0x180002b5a  mov     r9d, eax
0x180002b5d  lea     r8, WPP_a78e9b98c57431a096020c8f92b2d1b7_Traceguids
0x180002b64  mov     rcx, rbx
0x180002b67  call    WPP_SF_D
0x180002b6c  jmp     loc_1800029B3
0x180002b71  mov     rax, cs:hInstance
0x180002b78  lea     r8, WindowName; "HID Input Service"
0x180002b7f  mov     [rsp+140h+lpParam], r14; lpParam
0x180002b84  mov     r9d, 0CF0000h; dwStyle
0x180002b8a  mov     [rsp+140h+hInstance], rax; hInstance
0x180002b8f  mov     rdx, r15; lpClassName
0x180002b92  mov     [rsp+140h+hMenu], r14; hMenu
0x180002b97  xor     ecx, ecx; dwExStyle
0x180002b99  mov     [rsp+140h+hWndParent], r14; hWndParent
0x180002b9e  mov     sil, bl
0x180002ba1  mov     [rsp+140h+nHeight], r14d; nHeight
0x180002ba6  mov     [rsp+140h+nWidth], r14d; nWidth
0x180002bab  mov     [rsp+140h+Y], r14d; Y
0x180002bb0  mov     [rsp+140h+X], r14d; X
0x180002bb5  call    cs:__imp_CreateWindowExW
0x180002bbb  mov     cs:hWndHidServ, rax
0x180002bc2  test    rax, rax
0x180002bc5  jnz     short loc_180002BFC
0x180002bc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bce  lea     rax, WPP_GLOBAL_Control
0x180002bd5  cmp     rcx, rax
0x180002bd8  jz      loc_1800029B3
0x180002bde  test    byte ptr [rcx+1Ch], 10h
0x180002be2  jz      loc_1800029B3
0x180002be8  cmp     byte ptr [rcx+19h], 2
0x180002bec  jb      loc_1800029B3
0x180002bf2  mov     edx, 0Ch
0x180002bf7  jmp     loc_1800029A3
0x180002bfc  xorps   xmm0, xmm0
0x180002bff  mov     qword ptr [rbp+40h+HidGuid+0Ch], r14
0x180002c03  lea     rcx, [rbp+40h+HidGuid]; HidGuid
0x180002c07  mov     [rbp+40h+NotificationFilter], 20h ; ' '
0x180002c0e  movdqu  xmmword ptr [rbp-18h], xmm0
0x180002c13  mov     [rbp+40h+var_5C], 5
0x180002c1a  call    cs:__imp_HidD_GetHidGuid
0x180002c20  mov     rcx, cs:hWndHidServ; hRecipient
0x180002c27  lea     rdx, [rbp+40h+NotificationFilter]; NotificationFilter
0x180002c2b  xor     r8d, r8d; Flags
0x180002c2e  call    cs:__imp_RegisterDeviceNotificationW
0x180002c34  mov     cs:hNotifyArrival, rax
0x180002c3b  test    rax, rax
0x180002c3e  jnz     short loc_180002C7F
0x180002c40  mov     rbx, cs:WPP_GLOBAL_Control
0x180002c47  lea     rax, WPP_GLOBAL_Control
0x180002c4e  cmp     rbx, rax
0x180002c51  jz      loc_1800029B3
0x180002c57  test    byte ptr [rbx+1Ch], 10h
0x180002c5b  jz      loc_1800029B3
0x180002c61  cmp     byte ptr [rbx+19h], 2
0x180002c65  jb      loc_1800029B3
0x180002c6b  mov     rbx, [rbx+10h]
0x180002c6f  call    cs:__imp_GetLastError
0x180002c75  mov     edx, 0Dh
0x180002c7a  jmp     loc_180002B5A
0x180002c7f  mov     ecx, ebx
0x180002c81  call    HidServSetPnP
0x180002c86  mov     rcx, cs:hService; hServiceStatus
0x180002c8d  mov     cs:ServiceStatus.dwControlsAccepted, 85h
0x180002c97  test    rcx, rcx
0x180002c9a  jz      short loc_180002CB3
0x180002c9c  lea     rdx, ServiceStatus; lpServiceStatus
0x180002ca3  mov     cs:ServiceStatus.dwCurrentState, 4
0x180002cad  call    cs:__imp_SetServiceStatus
0x180002cb3  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180002cb9  xor     edx, edx; hFile
0x180002cbb  mov     cs:IsSessionLocked, r14d
0x180002cc2  mov     r8d, 800h; dwFlags
0x180002cc8  mov     cs:SessionId, eax
0x180002cce  lea     rcx, LibFileName; "winsta.dll"
0x180002cd5  mov     cs:WinStaDll, r14
0x180002cdc  call    cs:__imp_LoadLibraryExW
0x180002ce2  mov     cs:WinStaDll, rax
0x180002ce9  test    rax, rax
0x180002cec  jz      loc_1800029B3
0x180002cf2  lea     rdx, ProcName; "WinStationSendWindowMessage"
0x180002cf9  mov     rcx, rax; hModule
0x180002cfc  call    cs:__imp_GetProcAddress
0x180002d02  mov     cs:WinStaProc, rax
0x180002d09  test    rax, rax
0x180002d0c  jnz     short loc_180002D43
0x180002d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d15  lea     rax, WPP_GLOBAL_Control
0x180002d1c  cmp     rcx, rax
0x180002d1f  jz      loc_1800029B3
0x180002d25  test    byte ptr [rcx+1Ch], 10h
0x180002d29  jz      loc_1800029B3
0x180002d2f  cmp     byte ptr [rcx+19h], 2
0x180002d33  jb      loc_1800029B3
0x180002d39  mov     edx, 0Eh
0x180002d3e  jmp     loc_1800029A3
0x180002d43  lea     rax, InputThreadId
0x180002d4a  xor     r9d, r9d; lpParameter
0x180002d4d  mov     qword ptr [rsp+140h+Y], rax; lpThreadId
0x180002d52  lea     r8, HidThreadInputProc; lpStartAddress
0x180002d59  xor     edx, edx; dwStackSize
0x180002d5b  mov     [rsp+140h+X], r14d; dwCreationFlags
0x180002d60  xor     ecx, ecx; lpThreadAttributes
0x180002d62  call    cs:__imp_CreateThread
0x180002d68  mov     rbx, rax
0x180002d6b  test    rax, rax
0x180002d6e  jnz     short loc_180002DA3
0x180002d70  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d77  lea     rax, WPP_GLOBAL_Control
0x180002d7e  cmp     rcx, rax
0x180002d81  jz      loc_1800029B3
0x180002d87  test    byte ptr [rcx+1Ch], 10h
0x180002d8b  jz      loc_1800029B3
0x180002d91  cmp     byte ptr [rcx+19h], 2
0x180002d95  jb      loc_1800029B3
0x180002d9b  lea     edx, [rbx+0Fh]
0x180002d9e  jmp     loc_1800029A3
0x180002da3  test    rdi, rdi
0x180002da6  jz      short loc_180002DC7
0x180002da8  mov     rcx, rdi; hEvent
0x180002dab  call    cs:__imp_SetEvent
0x180002db1  jmp     short loc_180002DC7
0x180002db3  lea     rcx, [rbp+40h+Msg]; lpMsg
0x180002db7  call    cs:__imp_TranslateMessage
0x180002dbd  lea     rcx, [rbp+40h+Msg]; lpMsg
0x180002dc1  call    cs:__imp_DispatchMessageW
0x180002dc7  xor     r9d, r9d; wMsgFilterMax
0x180002dca  lea     rcx, [rbp+40h+Msg]; lpMsg
0x180002dce  xor     r8d, r8d; wMsgFilterMin
0x180002dd1  xor     edx, edx; hWnd
0x180002dd3  call    cs:__imp_GetMessageW
0x180002dd9  test    eax, eax
0x180002ddb  jnz     short loc_180002DB3
0x180002ddd  mov     rcx, cs:hWndHidServ; hWnd
0x180002de4  call    cs:__imp_DestroyWindow
0x180002dea  mov     rdx, cs:hInstance; hInstance
0x180002df1  mov     rcx, r15; lpClassName
0x180002df4  call    cs:__imp_UnregisterClassW
0x180002dfa  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180002dfd  mov     rcx, rbx; hHandle
0x180002e00  call    cs:__imp_WaitForSingleObject
0x180002e06  mov     rcx, rbx; hObject
0x180002e09  call    cs:__imp_CloseHandle
0x180002e0f  jmp     short loc_180002E1E
0x180002e11  xor     edx, edx; bAlertable
0x180002e13  mov     ecx, 3E8h; dwMilliseconds
0x180002e18  call    cs:__imp_SleepEx
0x180002e1e  cmp     cs:cThreadRef, r14d
0x180002e25  jnz     short loc_180002E11
0x180002e27  jmp     loc_180002A45
```
