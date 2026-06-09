# HotPlugSafeRemovalNotificationBase(DEVICE_COLLECTION *)

- ea: `0x180005234`
- end: `0x180005421`
- name: `?HotPlugSafeRemovalNotificationBase@@YAXPEAUDEVICE_COLLECTION@@@Z`
- size: `493`
- prototype: `void __fastcall(struct DEVICE_COLLECTION *lpParam)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, installer_update`

## callers

- `0x180005140`
- `0x180005430`
- `0x18000712c`

## callees

- `0x180005234`
- `0x180005528`
- `0x18000873a`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800053f2`
- `KERNEL32!CloseHandle` at `0x180008ba8`
- `KERNEL32!CloseHandle` at `0x1800053f2`
- `KERNEL32!CloseHandle` at `0x180008ba8`
- `KERNEL32!SetEvent` at `0x1800053e9`
- `KERNEL32!SetEvent` at `0x180008b9f`
- `KERNEL32!SetEvent` at `0x1800053e9`
- `KERNEL32!SetEvent` at `0x180008b9f`
- `KERNEL32!CreateEventW` at `0x180005324`
- `KERNEL32!CreateEventW` at `0x180005324`
- `KERNEL32!WaitForSingleObject` at `0x180005340`
- `KERNEL32!WaitForSingleObject` at `0x180005340`
- `USER32!RegisterClassW` at `0x1800052f8`
- `USER32!RegisterClassW` at `0x1800052f8`
- `USER32!IsWindow` at `0x1800053a8`
- `USER32!IsWindow` at `0x1800053a8`
- `USER32!GetClassInfoW` at `0x1800052a0`
- `USER32!GetClassInfoW` at `0x1800052a0`
- `USER32!CreateWindowExW` at `0x180005399`
- `USER32!CreateWindowExW` at `0x180005399`
- `USER32!TranslateMessage` at `0x1800053ce`
- `USER32!TranslateMessage` at `0x1800053ce`
- `USER32!DispatchMessageW` at `0x1800053d9`
- `USER32!DispatchMessageW` at `0x1800053d9`
- `USER32!GetMessageW` at `0x1800053bf`
- `USER32!GetMessageW` at `0x1800053bf`

## string_xrefs

- `0x18000530e`: `Local\Dock_TaskBarIcon_Event`
- `0x180005307`: `Local\HotPlug_TaskBarIcon_Event`

## pseudocode

```c
void __fastcall HotPlugSafeRemovalNotificationBase(struct DEVICE_COLLECTION *lpParam)
{
  _DWORD *v2; // rdi
  LRESULT (__stdcall *v3)(HWND, UINT, WPARAM, LPARAM); // rax
  const WCHAR *v4; // r9
  HANDLE EventW; // rax
  __int64 v6; // rcx
  void *v7; // rbx
  HWND Window; // rax
  __int64 v9; // rcx
  struct tagMSG Msg; // [rsp+60h] [rbp-98h] BYREF
  struct tagWNDCLASSW WndClass; // [rsp+90h] [rbp-68h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  memset_0(&WndClass, 0, sizeof(WndClass));
  if ( *((_DWORD *)lpParam + 4) )
  {
    v2 = (_DWORD *)((char *)lpParam + 20);
    if ( GetClassInfoW(hHotPlug, L"HotPlugClass", &WndClass) )
      goto LABEL_6;
    memset_0(&WndClass, 0, sizeof(WndClass));
    v3 = (LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM))SafeRemovalBalloonProc;
    if ( *v2 )
      v3 = (LRESULT (__stdcall *)(HWND, UINT, WPARAM, LPARAM))DockSafeRemovalBalloonProc;
    WndClass.lpfnWndProc = v3;
    WndClass.hInstance = hHotPlug;
    WndClass.lpszClassName = L"HotPlugClass";
    if ( RegisterClassW(&WndClass) )
    {
LABEL_6:
      v4 = L"Local\\Dock_TaskBarIcon_Event";
      if ( !*v2 )
        v4 = L"Local\\HotPlug_TaskBarIcon_Event";
      EventW = CreateEventW(0, 0, 1, v4);
      v7 = EventW;
      if ( EventW )
        WaitForSingleObject(EventW, 0xFFFFFFFF);
      if ( !*v2 )
        SysTray_EnableService(v6, 0);
      Window = CreateWindowExW(
                 0x80u,
                 L"HotPlugClass",
                 &String,
                 0x8C00000u,
                 0x80000000,
                 0x80000000,
                 0,
                 0,
                 0,
                 0,
                 hHotPlug,
                 lpParam);
      if ( Window && IsWindow(Window) )
      {
        while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
      }
      if ( v7 )
      {
        SetEvent(v7);
        CloseHandle(v7);
      }
      if ( !*((_DWORD *)lpParam + 5) )
        SysTray_EnableService(v9, 1);
    }
  }
}

```

## disassembly

```asm
0x180005234  mov     rax, rsp
0x180005237  mov     [rax+18h], rbx
0x18000523b  mov     [rax+20h], rsi
0x18000523f  mov     [rax+8], rcx
0x180005243  push    rdi
0x180005244  push    r14
0x180005246  push    r15
0x180005248  sub     rsp, 0E0h
0x18000524f  mov     rsi, rcx
0x180005252  xorps   xmm0, xmm0
0x180005255  movups  xmmword ptr [rsp+0F8h+Msg.hwnd], xmm0
0x18000525a  movups  xmmword ptr [rsp+0F8h+Msg.wParam], xmm0
0x18000525f  movups  xmmword ptr [rax-78h], xmm0
0x180005263  mov     ebx, 48h ; 'H'
0x180005268  mov     r8d, ebx; Size
0x18000526b  xor     edx, edx; Val
0x18000526d  lea     rcx, [rax-68h]; void *
0x180005271  call    memset_0
0x180005276  xor     r14d, r14d
0x180005279  cmp     [rsi+10h], r14d
0x18000527d  jz      loc_180005408
0x180005283  lea     rdi, [rsi+14h]
0x180005287  lea     r8, [rsp+0F8h+WndClass]; lpWndClass
0x18000528f  lea     r15, ClassName; "HotPlugClass"
0x180005296  mov     rdx, r15; lpClassName
0x180005299  mov     rcx, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; hInstance
0x1800052a0  call    cs:__imp_GetClassInfoW
0x1800052a6  test    eax, eax
0x1800052a8  jnz     short loc_180005307
0x1800052aa  mov     r8d, ebx; Size
0x1800052ad  xor     edx, edx; Val
0x1800052af  lea     rcx, [rsp+0F8h+WndClass]; void *
0x1800052b7  call    memset_0
0x1800052bc  lea     rax, ?SafeRemovalBalloonProc@@YA_JPEAUHWND__@@I_K_J@Z; SafeRemovalBalloonProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800052c3  lea     rcx, ?DockSafeRemovalBalloonProc@@YA_JPEAUHWND__@@I_K_J@Z; DockSafeRemovalBalloonProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800052ca  cmp     [rdi], r14d
0x1800052cd  cmovnz  rax, rcx
0x1800052d1  mov     [rsp+0F8h+WndClass.lpfnWndProc], rax
0x1800052d9  mov     rax, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hHotPlug
0x1800052e0  mov     [rsp+0F8h+WndClass.hInstance], rax
0x1800052e8  mov     [rsp+0F8h+WndClass.lpszClassName], r15
0x1800052f0  lea     rcx, [rsp+0F8h+WndClass]; lpWndClass
0x1800052f8  call    cs:__imp_RegisterClassW
0x1800052fe  test    ax, ax
0x180005301  jz      loc_180005408
0x180005307  lea     rax, aLocalHotplugTa; "Local\\HotPlug_TaskBarIcon_Event"
0x18000530e  lea     r9, aLocalDockTaskb; "Local\\Dock_TaskBarIcon_Event"
0x180005315  cmp     [rdi], r14d
0x180005318  cmovz   r9, rax; lpName
0x18000531c  xor     edx, edx; bManualReset
0x18000531e  xor     ecx, ecx; lpEventAttributes
0x180005320  lea     r8d, [rdx+1]; bInitialState
0x180005324  call    cs:__imp_CreateEventW
0x18000532a  mov     rbx, rax
0x18000532d  mov     [rsp+0F8h+arg_8], rax
0x180005335  test    rax, rax
0x180005338  jz      short loc_180005346
0x18000533a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000533d  mov     rcx, rax; hHandle
0x180005340  call    cs:__imp_WaitForSingleObject
0x180005346  cmp     [rdi], r14d
0x180005349  jnz     short loc_180005352
0x18000534b  xor     edx, edx; int
0x18000534d  call    ?SysTray_EnableService@@YAHHH@Z; SysTray_EnableService(int,int)
0x180005352  mov     [rsp+0F8h+lpParam], rsi; lpParam
0x180005357  mov     rax, cs:?hHotPlug@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hHotPlug
0x18000535e  mov     [rsp+0F8h+hInstance], rax; hInstance
0x180005363  mov     [rsp+0F8h+hMenu], r14; hMenu
0x180005368  mov     [rsp+0F8h+hWndParent], r14; hWndParent
0x18000536d  mov     [rsp+0F8h+nHeight], r14d; nHeight
0x180005372  mov     [rsp+0F8h+nWidth], r14d; nWidth
0x180005377  mov     eax, 80000000h
0x18000537c  mov     [rsp+0F8h+Y], eax; Y
0x180005380  mov     [rsp+0F8h+X], eax; X
0x180005384  mov     r9d, 8C00000h; dwStyle
0x18000538a  lea     r8, String; lpWindowName
0x180005391  mov     rdx, r15; lpClassName
0x180005394  mov     ecx, 80h; dwExStyle
0x180005399  call    cs:__imp_CreateWindowExW
0x18000539f  nop
0x1800053a0  test    rax, rax
0x1800053a3  jz      short loc_1800053E1
0x1800053a5  mov     rcx, rax; hWnd
0x1800053a8  call    cs:__imp_IsWindow
0x1800053ae  test    eax, eax
0x1800053b0  jz      short loc_1800053E1
0x1800053b2  xor     r9d, r9d; wMsgFilterMax
0x1800053b5  xor     r8d, r8d; wMsgFilterMin
0x1800053b8  xor     edx, edx; hWnd
0x1800053ba  lea     rcx, [rsp+0F8h+Msg]; lpMsg
0x1800053bf  call    cs:__imp_GetMessageW
0x1800053c5  test    eax, eax
0x1800053c7  jle     short loc_1800053E1
0x1800053c9  lea     rcx, [rsp+0F8h+Msg]; lpMsg
0x1800053ce  call    cs:__imp_TranslateMessage
0x1800053d4  lea     rcx, [rsp+0F8h+Msg]; lpMsg
0x1800053d9  call    cs:__imp_DispatchMessageW
0x1800053df  jmp     short loc_1800053B2
0x1800053e1  test    rbx, rbx
0x1800053e4  jz      short loc_1800053F8
0x1800053e6  mov     rcx, rbx; hEvent
0x1800053e9  call    cs:__imp_SetEvent
0x1800053ef  mov     rcx, rbx; hObject
0x1800053f2  call    cs:__imp_CloseHandle
0x1800053f8  cmp     [rsi+14h], r14d
0x1800053fc  jnz     short loc_180005408
0x1800053fe  mov     edx, 1; int
0x180005403  call    ?SysTray_EnableService@@YAHHH@Z; SysTray_EnableService(int,int)
0x180005408  lea     r11, [rsp+0F8h+var_18]
0x180005410  mov     rbx, [r11+30h]
0x180005414  mov     rsi, [r11+38h]
0x180005418  mov     rsp, r11
0x18000541b  pop     r15
0x18000541d  pop     r14
0x18000541f  pop     rdi
0x180005420  retn
0x180008b86  push    rbx
0x180008b88  push    rbp
0x180008b89  sub     rsp, 68h
0x180008b8d  mov     rbp, rdx
0x180008b90  mov     rbx, [rbp+108h]
0x180008b97  test    rbx, rbx
0x180008b9a  jz      short loc_180008BAF
0x180008b9c  mov     rcx, rbx; hEvent
0x180008b9f  call    cs:__imp_SetEvent
0x180008ba5  mov     rcx, rbx; hObject
0x180008ba8  call    cs:__imp_CloseHandle
0x180008bae  nop
0x180008baf  mov     rax, [rbp+100h]
0x180008bb6  cmp     dword ptr [rax+14h], 0
0x180008bba  jnz     short loc_180008BC7
0x180008bbc  mov     edx, 1; int
0x180008bc1  call    ?SysTray_EnableService@@YAHHH@Z; SysTray_EnableService(int,int)
0x180008bc6  nop
0x180008bc7  add     rsp, 68h
0x180008bcb  pop     rbp
0x180008bcc  pop     rbx
0x180008bcd  retn
```
