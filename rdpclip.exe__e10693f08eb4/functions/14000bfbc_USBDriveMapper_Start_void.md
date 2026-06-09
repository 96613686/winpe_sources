# USBDriveMapper::Start(void)

- ea: `0x14000bfbc`
- end: `0x14000c2ae`
- name: `?Start@USBDriveMapper@@SAJXZ`
- size: `754`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140015c20`

## callees

- `0x1400030d3`
- `0x140004b1c`
- `0x140005704`
- `0x14000bfa4`
- `0x14000bfbc`
- `0x14000c2b4`
- `0x14006a120`

## import_xrefs

- `USER32!RegisterDeviceNotificationW` at `0x14000c177`
- `USER32!RegisterDeviceNotificationW` at `0x14000c208`
- `USER32!RegisterDeviceNotificationW` at `0x14000c177`
- `USER32!RegisterDeviceNotificationW` at `0x14000c208`
- `USER32!RegisterClassW` at `0x14000c0b4`
- `USER32!RegisterClassW` at `0x14000c0b4`
- `USER32!CreateWindowExW` at `0x14000c0f2`
- `USER32!CreateWindowExW` at `0x14000c0f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x14000c080`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x14000c080`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c21a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c100`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c189`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c21a`

## pseudocode

```c
__int64 USBDriveMapper::Start(void)
{
  HWND Window; // rax
  HWND v1; // rbx
  signed int LastError; // eax
  signed int v3; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  __int64 v5; // rdx
  signed int v6; // eax
  signed int v7; // eax
  HMODULE phModule; // [rsp+60h] [rbp-A0h] BYREF
  WNDCLASSW WndClass; // [rsp+70h] [rbp-90h] BYREF
  _OWORD NotificationFilter[2]; // [rsp+C0h] [rbp-40h] BYREF
  _DWORD v12[104]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR ClassName[40]; // [rsp+280h] [rbp+180h] BYREF

  wcscpy(ClassName, L"URBRedirectorDeviceNotifications");
  memset(NotificationFilter, 0, sizeof(NotificationFilter));
  phModule = 0;
  memset_0(v12, 0, sizeof(v12));
  memset_0(&WndClass, 0, sizeof(WndClass));
  g_NotificationInterfaceHandle = 0;
  g_NotificationDevNodeHandle = 0;
  GetModuleHandleExW(6u, (LPCWSTR)staticWndProc, &phModule);
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.hInstance = phModule;
  WndClass.lpszClassName = ClassName;
  WndClass.lpfnWndProc = staticWndProc;
  RegisterClassW(&WndClass);
  Window = CreateWindowExW(0, ClassName, 0, 0, 0, 0, 0, 0, 0, 0, phModule, 0);
  v1 = Window;
  if ( !Window )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 40;
    goto LABEL_22;
  }
  *(_QWORD *)((char *)NotificationFilter + 4) = 5;
  HIDWORD(NotificationFilter[1]) = 0;
  LODWORD(NotificationFilter[0]) = 32;
  *(GUID *)((char *)NotificationFilter + 12) = GUID_DEVINTERFACE_HIDDEN_VOLUME;
  g_NotificationInterfaceHandle = RegisterDeviceNotificationW(Window, NotificationFilter, 0);
  if ( !g_NotificationInterfaceHandle )
  {
    v6 = GetLastError();
    v3 = v6;
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_23;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 41;
    goto LABEL_22;
  }
  memset_0(v12, 0, sizeof(v12));
  v12[0] = 416;
  v12[1] = 7;
  v12[3] = 17;
  g_NotificationDevNodeHandle = RegisterDeviceNotificationW(v1, v12, 0);
  if ( g_NotificationDevNodeHandle )
  {
    RefreshDevices();
    return 0;
  }
  v7 = GetLastError();
  v3 = v7;
  if ( v7 > 0 )
    v3 = (unsigned __int16)v7 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 42;
LABEL_22:
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      &WPP_3dea4583c5ab37af3d845428723bde47_Traceguids,
      CurrentThreadActivityIdPrefix,
      v3);
  }
LABEL_23:
  if ( v3 < 0 )
    USBDriveMapper::Stop();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14000bfbc  mov     [rsp-8+arg_0], rbx
0x14000bfc1  mov     [rsp-8+arg_8], rsi
0x14000bfc6  push    rbp
0x14000bfc7  lea     rbp, [rsp-1E0h]
0x14000bfcf  sub     rsp, 2E0h
0x14000bfd6  mov     rax, cs:__security_cookie
0x14000bfdd  xor     rax, rsp
0x14000bfe0  mov     [rbp+1E0h+var_10], rax
0x14000bfe7  movaps  xmm0, xmmword ptr cs:aUrbredirectord; "URBRedirectorDeviceNotifications"
0x14000bfee  lea     rcx, [rbp+1E0h+var_200]; void *
0x14000bff2  movaps  xmm1, xmmword ptr cs:aUrbredirectord+10h; "ectorDeviceNotifications"
0x14000bff9  xor     esi, esi
0x14000bffb  movzx   eax, word ptr cs:aUrbredirectord+40h; ""
0x14000c002  xor     edx, edx; Val
0x14000c004  movaps  xmmword ptr [rbp+1E0h+ClassName], xmm0
0x14000c00b  mov     r8d, 1A0h; Size
0x14000c011  movaps  xmm0, xmmword ptr cs:aUrbredirectord+20h; "iceNotifications"
0x14000c018  movaps  [rbp+1E0h+var_40], xmm0
0x14000c01f  xorps   xmm0, xmm0
0x14000c022  movaps  [rbp+1E0h+var_50], xmm1
0x14000c029  movaps  xmm1, xmmword ptr cs:aUrbredirectord+30h; "ications"
0x14000c030  movups  [rbp+1E0h+NotificationFilter], xmm0
0x14000c034  mov     [rbp+1E0h+var_20], ax
0x14000c03b  movups  [rbp+1E0h+var_210], xmm0
0x14000c03f  mov     [rsp+2E0h+phModule], rsi
0x14000c044  movaps  [rbp+1E0h+var_30], xmm1
0x14000c04b  call    memset_0
0x14000c050  xor     edx, edx; Val
0x14000c052  lea     r8d, [rsi+48h]; Size
0x14000c056  lea     rcx, [rsp+2E0h+WndClass]; void *
0x14000c05b  call    memset_0
0x14000c060  lea     rbx, ?staticWndProc@@YA_JPEAUHWND__@@I_K_J@Z; staticWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x14000c067  mov     cs:?g_NotificationInterfaceHandle@@3PEAXEA, rsi; void * g_NotificationInterfaceHandle
0x14000c06e  mov     rdx, rbx; lpModuleName
0x14000c071  mov     cs:?g_NotificationDevNodeHandle@@3PEAXEA, rsi; void * g_NotificationDevNodeHandle
0x14000c078  lea     r8, [rsp+2E0h+phModule]; phModule
0x14000c07d  lea     ecx, [rsi+6]; dwFlags
0x14000c080  call    cs:__imp_GetModuleHandleExW
0x14000c086  xor     edx, edx; Val
0x14000c088  lea     r8d, [rsi+48h]; Size
0x14000c08c  lea     rcx, [rsp+2E0h+WndClass]; void *
0x14000c091  call    memset_0
0x14000c096  mov     rax, [rsp+2E0h+phModule]
0x14000c09b  lea     rcx, [rsp+2E0h+WndClass]; lpWndClass
0x14000c0a0  mov     [rbp+1E0h+WndClass.hInstance], rax
0x14000c0a4  lea     rax, [rbp+1E0h+ClassName]
0x14000c0ab  mov     [rbp+1E0h+WndClass.lpszClassName], rax
0x14000c0af  mov     [rsp+2E0h+WndClass.lpfnWndProc], rbx
0x14000c0b4  call    cs:__imp_RegisterClassW
0x14000c0ba  mov     rax, [rsp+2E0h+phModule]
0x14000c0bf  lea     rdx, [rbp+1E0h+ClassName]; lpClassName
0x14000c0c6  mov     [rsp+2E0h+lpParam], rsi; lpParam
0x14000c0cb  xor     r9d, r9d; dwStyle
0x14000c0ce  mov     [rsp+2E0h+hInstance], rax; hInstance
0x14000c0d3  xor     r8d, r8d; lpWindowName
0x14000c0d6  mov     [rsp+2E0h+hMenu], rsi; hMenu
0x14000c0db  xor     ecx, ecx; dwExStyle
0x14000c0dd  mov     [rsp+2E0h+hWndParent], rsi; hWndParent
0x14000c0e2  mov     [rsp+2E0h+nHeight], esi; nHeight
0x14000c0e6  mov     [rsp+2E0h+nWidth], esi; nWidth
0x14000c0ea  mov     [rsp+2E0h+Y], esi; Y
0x14000c0ee  mov     [rsp+2E0h+X], esi; X
0x14000c0f2  call    cs:__imp_CreateWindowExW
0x14000c0f8  mov     rbx, rax
0x14000c0fb  test    rax, rax
0x14000c0fe  jnz     short loc_14000C14F
0x14000c100  call    cs:__imp_GetLastError
0x14000c106  mov     ebx, eax
0x14000c108  test    eax, eax
0x14000c10a  jle     short loc_14000C115
0x14000c10c  movzx   ebx, ax
0x14000c10f  or      ebx, 80070000h
0x14000c115  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c11c  lea     rax, WPP_GLOBAL_Control
0x14000c123  cmp     rcx, rax
0x14000c126  jz      loc_14000C276
0x14000c12c  test    byte ptr [rcx+1Ch], 1
0x14000c130  jz      loc_14000C276
0x14000c136  cmp     byte ptr [rcx+19h], 2
0x14000c13a  jb      loc_14000C276
0x14000c140  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000c145  mov     edx, 28h ; '('
0x14000c14a  jmp     loc_14000C258
0x14000c14f  movups  xmm0, xmmword ptr cs:GUID_DEVINTERFACE_HIDDEN_VOLUME.Data1
0x14000c156  xor     r8d, r8d; Flags
0x14000c159  mov     qword ptr [rbp+1E0h+NotificationFilter+4], 5
0x14000c161  lea     rdx, [rbp+1E0h+NotificationFilter]; NotificationFilter
0x14000c165  mov     dword ptr [rbp+1E0h+var_210+0Ch], esi
0x14000c168  mov     rcx, rbx; hRecipient
0x14000c16b  mov     dword ptr [rbp+1E0h+NotificationFilter], 20h ; ' '
0x14000c172  movdqu  [rbp+1E0h+NotificationFilter+0Ch], xmm0
0x14000c177  call    cs:__imp_RegisterDeviceNotificationW
0x14000c17d  mov     cs:?g_NotificationInterfaceHandle@@3PEAXEA, rax; void * g_NotificationInterfaceHandle
0x14000c184  test    rax, rax
0x14000c187  jnz     short loc_14000C1D8
0x14000c189  call    cs:__imp_GetLastError
0x14000c18f  mov     ebx, eax
0x14000c191  test    eax, eax
0x14000c193  jle     short loc_14000C19E
0x14000c195  movzx   ebx, ax
0x14000c198  or      ebx, 80070000h
0x14000c19e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c1a5  lea     rax, WPP_GLOBAL_Control
0x14000c1ac  cmp     rcx, rax
0x14000c1af  jz      loc_14000C276
0x14000c1b5  test    byte ptr [rcx+1Ch], 1
0x14000c1b9  jz      loc_14000C276
0x14000c1bf  cmp     byte ptr [rcx+19h], 2
0x14000c1c3  jb      loc_14000C276
0x14000c1c9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000c1ce  mov     edx, 29h ; ')'
0x14000c1d3  jmp     loc_14000C258
0x14000c1d8  xor     edx, edx; Val
0x14000c1da  lea     rcx, [rbp+1E0h+var_200]; void *
0x14000c1de  mov     r8d, 1A0h; Size
0x14000c1e4  call    memset_0
0x14000c1e9  xor     r8d, r8d; Flags
0x14000c1ec  mov     [rbp+1E0h+var_200], 1A0h
0x14000c1f3  lea     rdx, [rbp+1E0h+var_200]; NotificationFilter
0x14000c1f7  mov     [rbp+1E0h+var_1FC], 7
0x14000c1fe  mov     rcx, rbx; hRecipient
0x14000c201  mov     [rbp+1E0h+var_1F4], 11h
0x14000c208  call    cs:__imp_RegisterDeviceNotificationW
0x14000c20e  mov     cs:?g_NotificationDevNodeHandle@@3PEAXEA, rax; void * g_NotificationDevNodeHandle
0x14000c215  test    rax, rax
0x14000c218  jnz     short loc_14000C281
0x14000c21a  call    cs:__imp_GetLastError
0x14000c220  mov     ebx, eax
0x14000c222  test    eax, eax
0x14000c224  jle     short loc_14000C22F
0x14000c226  movzx   ebx, ax
0x14000c229  or      ebx, 80070000h
0x14000c22f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c236  lea     rax, WPP_GLOBAL_Control
0x14000c23d  cmp     rcx, rax
0x14000c240  jz      short loc_14000C276
0x14000c242  test    byte ptr [rcx+1Ch], 1
0x14000c246  jz      short loc_14000C276
0x14000c248  cmp     byte ptr [rcx+19h], 2
0x14000c24c  jb      short loc_14000C276
0x14000c24e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14000c253  mov     edx, 2Ah ; '*'
0x14000c258  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c25f  lea     r8, WPP_3dea4583c5ab37af3d845428723bde47_Traceguids
0x14000c266  mov     r9d, eax
0x14000c269  mov     [rsp+2E0h+X], ebx
0x14000c26d  mov     rcx, [rcx+10h]
0x14000c271  call    WPP_SF_Dd
0x14000c276  test    ebx, ebx
0x14000c278  jns     short loc_14000C288
0x14000c27a  call    ?Stop@USBDriveMapper@@SAXXZ; USBDriveMapper::Stop(void)
0x14000c27f  jmp     short loc_14000C288
0x14000c281  call    ?RefreshDevices@@YAJXZ; RefreshDevices(void)
0x14000c286  mov     ebx, esi
0x14000c288  mov     eax, ebx
0x14000c28a  mov     rcx, [rbp+1E0h+var_10]
0x14000c291  xor     rcx, rsp; StackCookie
0x14000c294  call    __security_check_cookie
0x14000c299  lea     r11, [rsp+2E0h+var_s0]
0x14000c2a1  mov     rbx, [r11+10h]
0x14000c2a5  mov     rsi, [r11+18h]
0x14000c2a9  mov     rsp, r11
0x14000c2ac  pop     rbp
0x14000c2ad  retn
```
