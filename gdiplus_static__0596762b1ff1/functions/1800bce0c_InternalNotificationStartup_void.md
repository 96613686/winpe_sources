# InternalNotificationStartup(void)

- ea: `0x1800bce0c`
- end: `0x1800bd249`
- name: `?InternalNotificationStartup@@YAHXZ`
- size: `1085`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800bd3b0`
- `0x18011c230`

## callees

- `0x180010bd0`
- `0x1800bce0c`
- `0x1800bd250`
- `0x1800bd2d0`
- `0x1800bd364`
- `0x1800bd4dc`
- `0x180105d40`
- `0x18010673c`
- `0x180172010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800bcf57`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800bcf57`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800bcf1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800bcf1b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bd216`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800bd216`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcf3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd1b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bcf3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bd1b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd225`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd225`
- `USER32!SetWindowPos` at `0x1800bd1f1`
- `USER32!SetWindowPos` at `0x1800bd1f1`
- `USER32!CreateWindowExW` at `0x1800bd021`
- `USER32!CreateWindowExW` at `0x1800bd021`
- `USER32!RegisterWindowMessageW` at `0x1800bcfce`
- `USER32!RegisterWindowMessageW` at `0x1800bcfce`
- `USER32!RegisterClassW` at `0x1800bce83`
- `USER32!RegisterClassW` at `0x1800bce83`
- `USER32!GetDC` at `0x1800bd0b3`
- `USER32!GetDC` at `0x1800bd0b3`
- `USER32!ReleaseDC` at `0x1800bd0e1`
- `USER32!ReleaseDC` at `0x1800bd0e1`
- `GDI32!SelectPalette` at `0x1800bd0cb`
- `GDI32!SelectPalette` at `0x1800bd0cb`
- `GDI32!DeleteObject` at `0x1800bd0f0`
- `GDI32!DeleteObject` at `0x1800bd0f0`
- `GDI32!CreatePalette` at `0x1800bd09d`
- `GDI32!CreatePalette` at `0x1800bd09d`

## string_xrefs

- `0x1800bcfc7`: `GDI+ Accessibility`

## pseudocode

```c
__int64 InternalNotificationStartup(void)
{
  DWORD v0; // esi
  WCHAR *v1; // r14
  int v2; // ebx
  DWORD ModuleFileNameW; // edi
  wchar_t *v4; // rax
  LPWSTR v5; // rbx
  unsigned int v6; // edi
  int v7; // r8d
  __int64 v8; // rdx
  int v9; // ecx
  HPALETTE v10; // rdi
  HDC DC; // rbx
  void *v13; // rax
  void *v14; // rbx
  WNDCLASSW WndClass; // [rsp+60h] [rbp-A0h] BYREF
  int v16; // [rsp+B0h] [rbp-50h] BYREF
  LPWSTR lpFilename; // [rsp+B8h] [rbp-48h]
  char v18; // [rsp+C0h] [rbp-40h] BYREF
  int v19; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v20; // [rsp+D0h] [rbp-30h]
  char v21; // [rsp+D8h] [rbp-28h] BYREF
  LOGPALETTE plpal; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR WindowName[12]; // [rsp+4F0h] [rbp+3F0h] BYREF

  WndClass.lpfnWndProc = NotificationWndProc;
  WndClass.hInstance = DllInstance;
  WndClass.lpszMenuName = L"GDI+ Hook Window";
  WndClass.lpszClassName = L"GDI+ Hook Window Class";
  *(_QWORD *)&WndClass.style = 0;
  *(_QWORD *)&WndClass.cbClsExtra = 0;
  memset(&WndClass.hIcon, 0, 24);
  Globals::WindowClassAtom = RegisterClassW(&WndClass);
  if ( !Globals::WindowClassAtom )
    return 0;
  v0 = 130;
  v20 = (unsigned __int16 *)&v21;
  v1 = WindowName;
  lpFilename = (LPWSTR)&v18;
  v2 = 0;
  wcscpy(WindowName, L"GDI+ Window");
  v19 = 1;
  v16 = 1;
  do
  {
    v0 *= 2;
    AutoBuffer<unsigned short,1>::SetSize(&v16, v0);
    if ( v16 < 0 || v16 > 1 && lpFilename == (LPWSTR)&v18 )
      ModuleFileNameW = 0;
    else
      ModuleFileNameW = GetModuleFileNameW(0, lpFilename, v0);
    if ( (unsigned int)++v2 >= 4 )
      break;
    if ( !ModuleFileNameW )
      goto LABEL_17;
  }
  while ( GetLastError() == 122 );
  if ( ModuleFileNameW && GetLastError() != 122 )
  {
    v4 = wcsrchr(lpFilename, 0x5Cu);
    v5 = v4 ? v4 + 1 : lpFilename;
    v6 = ModuleFileNameW - (v5 - lpFilename) + 15;
    AutoBuffer<unsigned short,1>::SetSize(&v19, v6);
    if ( v19 >= 0
      && (v19 <= 1 || v20 != (unsigned __int16 *)&v21)
      && (int)StringCchPrintfW(v20, v6, L"%s (%s)", WindowName, v5) >= 0 )
    {
      v1 = v20;
    }
  }
LABEL_17:
  Globals::g_nAccessibilityMessage = RegisterWindowMessageW(L"GDI+ Accessibility");
  Globals::HwndNotify = CreateWindowExW(
                          0,
                          (LPCWSTR)Globals::WindowClassAtom,
                          v1,
                          0x80000000,
                          0,
                          0,
                          1,
                          1,
                          0,
                          0,
                          DllInstance,
                          0);
  if ( !Globals::HwndNotify )
  {
    v13 = InternalNotificationShutdown();
    v14 = v13;
    if ( v13 )
    {
      SetEvent(v13);
      CloseHandle(v14);
    }
    if ( lpFilename != (LPWSTR)&v18 )
      GpFree(lpFilename);
    lpFilename = (LPWSTR)&v18;
    v16 = -1;
    if ( v20 != (unsigned __int16 *)&v21 )
      GpFree(v20);
    return 0;
  }
  if ( (unsigned int)IsUIAccessProcess() )
    SetWindowPos(Globals::HwndNotify, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x1Bu);
  memset_0(plpal.palPalEntry, 0, 0x404u);
  v7 = 0;
  *(_DWORD *)&plpal.palVersion = 16777984;
  do
  {
    v8 = v7++;
    v9 = *((_DWORD *)qword_1801856E8 + v8);
    plpal.palPalEntry[v8].peRed = BYTE2(v9);
    plpal.palPalEntry[v8].peGreen = BYTE1(v9);
    plpal.palPalEntry[v8].peBlue = v9;
    plpal.palPalEntry[v8].peFlags = 0;
  }
  while ( v7 < plpal.palNumEntries );
  v10 = CreatePalette(&plpal);
  DC = GetDC(Globals::HwndNotify);
  SelectPalette(DC, v10, 0);
  ReleaseDC(Globals::HwndNotify, DC);
  DeleteObject(v10);
  if ( Globals::g_pfnWTSRegisterSessionNotificationFunction )
    Globals::g_pfnWTSRegisterSessionNotificationFunction(Globals::HwndNotify, 0);
  if ( lpFilename != (LPWSTR)&v18 )
    GpFree(lpFilename);
  v16 = -1;
  lpFilename = (LPWSTR)&v18;
  if ( v20 != (unsigned __int16 *)&v21 )
    GpFree(v20);
  return 1;
}

```

## disassembly

```asm
0x1800bce0c  push    rbp
0x1800bce0e  push    rbx
0x1800bce0f  push    rsi
0x1800bce10  push    rdi
0x1800bce11  push    r12
0x1800bce13  push    r14
0x1800bce15  push    r15
0x1800bce17  lea     rbp, [rsp-410h]
0x1800bce1f  sub     rsp, 510h
0x1800bce26  mov     rax, cs:__security_cookie
0x1800bce2d  xor     rax, rsp
0x1800bce30  mov     [rbp+440h+var_38], rax
0x1800bce37  xor     r15d, r15d
0x1800bce3a  lea     rax, ?NotificationWndProc@@YA_JPEAUHWND__@@I_K_J@Z; NotificationWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800bce41  mov     [rsp+540h+WndClass.lpfnWndProc], rax
0x1800bce46  lea     rcx, [rsp+540h+WndClass]; lpWndClass
0x1800bce4b  mov     rax, cs:?DllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DllInstance
0x1800bce52  xorps   xmm0, xmm0
0x1800bce55  mov     [rsp+540h+WndClass.hInstance], rax
0x1800bce5a  lea     rax, aGdiHookWindow; "GDI+ Hook Window"
0x1800bce61  mov     [rbp+440h+WndClass.lpszMenuName], rax
0x1800bce65  lea     rax, aGdiHookWindowC; "GDI+ Hook Window Class"
0x1800bce6c  mov     [rbp+440h+WndClass.lpszClassName], rax
0x1800bce70  mov     qword ptr [rsp+540h+WndClass.style], r15
0x1800bce75  mov     qword ptr [rsp+540h+WndClass.cbClsExtra], r15
0x1800bce7a  movdqa  xmmword ptr [rbp+440h+WndClass.hIcon], xmm0
0x1800bce7f  mov     [rbp+440h+WndClass.hbrBackground], r15
0x1800bce83  call    cs:__imp_RegisterClassW
0x1800bce8a  nop     dword ptr [rax+rax+00h]
0x1800bce8f  mov     cs:?WindowClassAtom@Globals@@3GA, ax; ushort Globals::WindowClassAtom
0x1800bce96  test    ax, ax
0x1800bce99  jz      loc_1800BD1A8
0x1800bce9f  movups  xmm0, xmmword ptr cs:aGdiWindow; "GDI+ Window"
0x1800bcea6  lea     rax, [rbp+440h+var_468]
0x1800bceaa  mov     esi, 82h
0x1800bceaf  movsd   xmm1, qword ptr cs:aGdiWindow+10h; "dow"
0x1800bceb7  lea     r12d, [r15+1]
0x1800bcebb  mov     [rbp+440h+var_470], rax
0x1800bcebf  lea     r14, [rbp+440h+WindowName]
0x1800bcec6  lea     rax, [rbp+440h+var_480]
0x1800bceca  movsd   [rbp+440h+var_40], xmm1
0x1800bced2  mov     [rbp+440h+lpFilename], rax
0x1800bced6  mov     ebx, r15d
0x1800bced9  movups  xmmword ptr [rbp+440h+WindowName], xmm0
0x1800bcee0  mov     [rbp+440h+var_478], r12d
0x1800bcee4  mov     [rbp+440h+var_490], r12d
0x1800bcee8  add     esi, esi
0x1800bceea  lea     rcx, [rbp+440h+var_490]
0x1800bceee  mov     edx, esi
0x1800bcef0  call    ?SetSize@?$AutoBuffer@G$00@@QEAAXH@Z; AutoBuffer<ushort,1>::SetSize(int)
0x1800bcef5  mov     eax, [rbp+440h+var_490]
0x1800bcef8  test    eax, eax
0x1800bcefa  js      loc_1800BD202
0x1800bcf00  mov     rdx, [rbp+440h+lpFilename]; lpFilename
0x1800bcf04  cmp     eax, r12d
0x1800bcf07  jle     short loc_1800BCF16
0x1800bcf09  lea     rax, [rbp+440h+var_480]
0x1800bcf0d  cmp     rdx, rax
0x1800bcf10  jz      loc_1800BD202
0x1800bcf16  mov     r8d, esi; nSize
0x1800bcf19  xor     ecx, ecx; hModule
0x1800bcf1b  call    cs:__imp_GetModuleFileNameW
0x1800bcf22  nop     dword ptr [rax+rax+00h]
0x1800bcf27  mov     edi, eax
0x1800bcf29  add     ebx, r12d
0x1800bcf2c  cmp     ebx, 4
0x1800bcf2f  jb      loc_1800BD1AC
0x1800bcf35  test    edi, edi
0x1800bcf37  jz      loc_1800BCFC7
0x1800bcf3d  call    cs:__imp_GetLastError
0x1800bcf44  nop     dword ptr [rax+rax+00h]
0x1800bcf49  cmp     eax, 7Ah ; 'z'
0x1800bcf4c  jz      short loc_1800BCFC7
0x1800bcf4e  mov     rcx, [rbp+440h+lpFilename]; Str
0x1800bcf52  mov     edx, 5Ch ; '\'; Ch
0x1800bcf57  call    cs:__imp_wcsrchr
0x1800bcf5e  nop     dword ptr [rax+rax+00h]
0x1800bcf63  mov     rbx, rax
0x1800bcf66  test    rax, rax
0x1800bcf69  jz      loc_1800BD20A
0x1800bcf6f  add     rbx, 2
0x1800bcf73  mov     rax, rbx
0x1800bcf76  lea     rcx, [rbp+440h+var_478]
0x1800bcf7a  sub     rax, [rbp+440h+lpFilename]
0x1800bcf7e  sar     rax, 1
0x1800bcf81  sub     edi, eax
0x1800bcf83  add     edi, 0Fh
0x1800bcf86  mov     edx, edi
0x1800bcf88  call    ?SetSize@?$AutoBuffer@G$00@@QEAAXH@Z; AutoBuffer<ushort,1>::SetSize(int)
0x1800bcf8d  mov     eax, [rbp+440h+var_478]
0x1800bcf90  test    eax, eax
0x1800bcf92  js      short loc_1800BCFC7
0x1800bcf94  mov     rcx, [rbp+440h+var_470]; unsigned __int16 *
0x1800bcf98  cmp     eax, r12d
0x1800bcf9b  jle     short loc_1800BCFA6
0x1800bcf9d  lea     rax, [rbp+440h+var_468]
0x1800bcfa1  cmp     rcx, rax
0x1800bcfa4  jz      short loc_1800BCFC7
0x1800bcfa6  mov     edx, edi; unsigned __int64
0x1800bcfa8  lea     r9, [rbp+440h+WindowName]
0x1800bcfaf  lea     r8, aSS; "%s (%s)"
0x1800bcfb6  mov     qword ptr [rsp+540h+X], rbx
0x1800bcfbb  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bcfc0  test    eax, eax
0x1800bcfc2  cmovns  r14, [rbp+440h+var_470]
0x1800bcfc7  lea     rcx, String; "GDI+ Accessibility"
0x1800bcfce  call    cs:__imp_RegisterWindowMessageW
0x1800bcfd5  nop     dword ptr [rax+rax+00h]
0x1800bcfda  movzx   edx, cs:?WindowClassAtom@Globals@@3GA; lpClassName
0x1800bcfe1  mov     r9d, 80000000h; dwStyle
0x1800bcfe7  mov     [rsp+540h+lpParam], r15; lpParam
0x1800bcfec  mov     r8, r14; lpWindowName
0x1800bcfef  mov     cs:?g_nAccessibilityMessage@Globals@@3IA, eax; uint Globals::g_nAccessibilityMessage
0x1800bcff5  xor     ecx, ecx; dwExStyle
0x1800bcff7  mov     rax, cs:?DllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DllInstance
0x1800bcffe  mov     [rsp+540h+hInstance], rax; hInstance
0x1800bd003  mov     [rsp+540h+hMenu], r15; hMenu
0x1800bd008  mov     [rsp+540h+hWndParent], r15; hWndParent
0x1800bd00d  mov     [rsp+540h+nHeight], r12d; nHeight
0x1800bd012  mov     [rsp+540h+nWidth], r12d; nWidth
0x1800bd017  mov     [rsp+540h+Y], r15d; Y
0x1800bd01c  mov     [rsp+540h+X], r15d; X
0x1800bd021  call    cs:__imp_CreateWindowExW
0x1800bd028  nop     dword ptr [rax+rax+00h]
0x1800bd02d  mov     cs:?HwndNotify@Globals@@3PEAUHWND__@@EA, rax; HWND__ * Globals::HwndNotify
0x1800bd034  test    rax, rax
0x1800bd037  jz      loc_1800BD164
0x1800bd03d  call    ?IsUIAccessProcess@@YAHXZ; IsUIAccessProcess(void)
0x1800bd042  test    eax, eax
0x1800bd044  jnz     loc_1800BD1CE
0x1800bd04a  xor     edx, edx; Val
0x1800bd04c  lea     rcx, [rbp+440h+plpal.palPalEntry]; void *
0x1800bd050  mov     r8d, 404h; Size
0x1800bd056  call    memset_0
0x1800bd05b  mov     r8d, r15d
0x1800bd05e  mov     dword ptr [rbp+440h+plpal.palVersion], 1000300h
0x1800bd065  movsxd  rdx, r8d
0x1800bd068  lea     rcx, qword_1801856E8
0x1800bd06f  add     r8d, r12d
0x1800bd072  mov     ecx, [rcx+rdx*4]
0x1800bd075  mov     eax, ecx
0x1800bd077  shr     eax, 10h
0x1800bd07a  mov     [rbp+rdx*4+440h+plpal.palPalEntry.peRed], al
0x1800bd07e  mov     eax, ecx
0x1800bd080  shr     eax, 8
0x1800bd083  mov     [rbp+rdx*4+440h+plpal.palPalEntry.peGreen], al
0x1800bd087  mov     [rbp+rdx*4+440h+plpal.palPalEntry.peBlue], cl
0x1800bd08b  mov     [rbp+rdx*4+440h+plpal.palPalEntry.peFlags], r15b
0x1800bd090  movzx   eax, [rbp+440h+plpal.palNumEntries]
0x1800bd094  cmp     r8d, eax
0x1800bd097  jl      short loc_1800BD065
0x1800bd099  lea     rcx, [rbp+440h+plpal]; plpal
0x1800bd09d  call    cs:__imp_CreatePalette
0x1800bd0a4  nop     dword ptr [rax+rax+00h]
0x1800bd0a9  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; hWnd
0x1800bd0b0  mov     rdi, rax
0x1800bd0b3  call    cs:__imp_GetDC
0x1800bd0ba  nop     dword ptr [rax+rax+00h]
0x1800bd0bf  xor     r8d, r8d; bForceBkgd
0x1800bd0c2  mov     rdx, rdi; hPal
0x1800bd0c5  mov     rcx, rax; hdc
0x1800bd0c8  mov     rbx, rax
0x1800bd0cb  call    cs:__imp_SelectPalette
0x1800bd0d2  nop     dword ptr [rax+rax+00h]
0x1800bd0d7  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; hWnd
0x1800bd0de  mov     rdx, rbx; hDC
0x1800bd0e1  call    cs:__imp_ReleaseDC
0x1800bd0e8  nop     dword ptr [rax+rax+00h]
0x1800bd0ed  mov     rcx, rdi; ho
0x1800bd0f0  call    cs:__imp_DeleteObject
0x1800bd0f7  nop     dword ptr [rax+rax+00h]
0x1800bd0fc  mov     rax, cs:?g_pfnWTSRegisterSessionNotificationFunction@Globals@@3P6AHPEAUHWND__@@K@ZEA; int (*Globals::g_pfnWTSRegisterSessionNotificationFunction)(HWND__ *,ulong)
0x1800bd103  test    rax, rax
0x1800bd106  jnz     loc_1800BD236
0x1800bd10c  mov     rcx, [rbp+440h+lpFilename]
0x1800bd110  lea     rax, [rbp+440h+var_480]
0x1800bd114  cmp     rcx, rax
0x1800bd117  jz      short loc_1800BD11E
0x1800bd119  call    GpFree
0x1800bd11e  lea     rcx, [rbp+440h+var_480]
0x1800bd122  mov     [rbp+440h+var_490], 0FFFFFFFFh
0x1800bd129  mov     [rbp+440h+lpFilename], rcx
0x1800bd12d  lea     rdx, [rbp+440h+var_468]
0x1800bd131  mov     rcx, [rbp+440h+var_470]
0x1800bd135  cmp     rcx, rdx
0x1800bd138  jz      short loc_1800BD13F
0x1800bd13a  call    GpFree
0x1800bd13f  mov     eax, r12d
0x1800bd142  mov     rcx, [rbp+440h+var_38]
0x1800bd149  xor     rcx, rsp; StackCookie
0x1800bd14c  call    __security_check_cookie
0x1800bd151  add     rsp, 510h
0x1800bd158  pop     r15
0x1800bd15a  pop     r14
0x1800bd15c  pop     r12
0x1800bd15e  pop     rdi
0x1800bd15f  pop     rsi
0x1800bd160  pop     rbx
0x1800bd161  pop     rbp
0x1800bd162  retn
0x1800bd164  call    ?InternalNotificationShutdown@@YAPEAXXZ; InternalNotificationShutdown(void)
0x1800bd169  mov     rbx, rax
0x1800bd16c  test    rax, rax
0x1800bd16f  jnz     loc_1800BD213
0x1800bd175  mov     rcx, [rbp+440h+lpFilename]
0x1800bd179  lea     rax, [rbp+440h+var_480]
0x1800bd17d  cmp     rcx, rax
0x1800bd180  jz      short loc_1800BD187
0x1800bd182  call    GpFree
0x1800bd187  mov     rcx, [rbp+440h+var_470]
0x1800bd18b  lea     rax, [rbp+440h+var_480]
0x1800bd18f  mov     [rbp+440h+lpFilename], rax
0x1800bd193  lea     rax, [rbp+440h+var_468]
0x1800bd197  mov     [rbp+440h+var_490], 0FFFFFFFFh
0x1800bd19e  cmp     rcx, rax
0x1800bd1a1  jz      short loc_1800BD1A8
0x1800bd1a3  call    GpFree
0x1800bd1a8  xor     eax, eax
0x1800bd1aa  jmp     short loc_1800BD142
0x1800bd1ac  test    edi, edi
0x1800bd1ae  jz      loc_1800BCFC7
0x1800bd1b4  call    cs:__imp_GetLastError
0x1800bd1bb  nop     dword ptr [rax+rax+00h]
0x1800bd1c0  cmp     eax, 7Ah ; 'z'
0x1800bd1c3  jnz     loc_1800BCF35
0x1800bd1c9  jmp     loc_1800BCEE8
0x1800bd1ce  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; hWnd
0x1800bd1d5  xor     r9d, r9d; Y
0x1800bd1d8  mov     [rsp+540h+nWidth], 1Bh; uFlags
0x1800bd1e0  xor     r8d, r8d; X
0x1800bd1e3  mov     [rsp+540h+Y], r15d; cy
0x1800bd1e8  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x1800bd1ec  mov     [rsp+540h+X], r15d; cx
0x1800bd1f1  call    cs:__imp_SetWindowPos
0x1800bd1f8  nop     dword ptr [rax+rax+00h]
0x1800bd1fd  jmp     loc_1800BD04A
0x1800bd202  mov     edi, r15d
0x1800bd205  jmp     loc_1800BCF29
0x1800bd20a  mov     rbx, [rbp+440h+lpFilename]
0x1800bd20e  jmp     loc_1800BCF73
0x1800bd213  mov     rcx, rbx; hEvent
0x1800bd216  call    cs:__imp_SetEvent
0x1800bd21d  nop     dword ptr [rax+rax+00h]
0x1800bd222  mov     rcx, rbx; hObject
0x1800bd225  call    cs:__imp_CloseHandle
0x1800bd22c  nop     dword ptr [rax+rax+00h]
0x1800bd231  jmp     loc_1800BD175
0x1800bd236  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; HWND__ * Globals::HwndNotify
0x1800bd23d  xor     edx, edx
0x1800bd23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd244  jmp     loc_1800BD10C
```
