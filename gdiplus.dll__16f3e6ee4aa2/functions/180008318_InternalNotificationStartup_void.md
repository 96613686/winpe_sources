# InternalNotificationStartup(void)

- ea: `0x180008318`
- end: `0x1800086f6`
- name: `?InternalNotificationStartup@@YAHXZ`
- size: `990`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180008930`
- `0x180114430`

## callees

- `0x180008318`
- `0x1800086fc`
- `0x180008778`
- `0x1800088e4`
- `0x180008a24`
- `0x18001ec80`
- `0x1800fe680`
- `0x1800ff04c`
- `0x180169010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000844d`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18000844d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008421`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180008421`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800086cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800086cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008439`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008439`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008679`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086d8`
- `USER32!SetWindowPos` at `0x1800086b0`
- `USER32!SetWindowPos` at `0x1800086b0`
- `USER32!CreateWindowExW` at `0x18000850b`
- `USER32!CreateWindowExW` at `0x18000850b`
- `USER32!RegisterWindowMessageW` at `0x1800084be`
- `USER32!RegisterWindowMessageW` at `0x1800084be`
- `USER32!RegisterClassW` at `0x18000838f`
- `USER32!RegisterClassW` at `0x18000838f`
- `USER32!GetDC` at `0x180008591`
- `USER32!GetDC` at `0x180008591`
- `USER32!ReleaseDC` at `0x1800085b3`
- `USER32!ReleaseDC` at `0x1800085b3`
- `GDI32!SelectPalette` at `0x1800085a3`
- `GDI32!SelectPalette` at `0x1800085a3`
- `GDI32!DeleteObject` at `0x1800085bc`
- `GDI32!DeleteObject` at `0x1800085bc`
- `GDI32!CreatePalette` at `0x180008581`
- `GDI32!CreatePalette` at `0x180008581`

## string_xrefs

- `0x1800084b7`: `GDI+ Accessibility`

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
    v9 = *((_DWORD *)qword_180176748 + v8);
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
0x180008318  push    rbp
0x18000831a  push    rbx
0x18000831b  push    rsi
0x18000831c  push    rdi
0x18000831d  push    r12
0x18000831f  push    r14
0x180008321  push    r15
0x180008323  lea     rbp, [rsp-410h]
0x18000832b  sub     rsp, 510h
0x180008332  mov     rax, cs:__security_cookie
0x180008339  xor     rax, rsp
0x18000833c  mov     [rbp+440h+var_38], rax
0x180008343  xor     r15d, r15d
0x180008346  lea     rax, ?NotificationWndProc@@YA_JPEAUHWND__@@I_K_J@Z; NotificationWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000834d  mov     [rsp+540h+WndClass.lpfnWndProc], rax
0x180008352  lea     rcx, [rsp+540h+WndClass]; lpWndClass
0x180008357  mov     rax, cs:?DllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DllInstance
0x18000835e  xorps   xmm0, xmm0
0x180008361  mov     [rsp+540h+WndClass.hInstance], rax
0x180008366  lea     rax, aGdiHookWindow; "GDI+ Hook Window"
0x18000836d  mov     [rbp+440h+WndClass.lpszMenuName], rax
0x180008371  lea     rax, aGdiHookWindowC; "GDI+ Hook Window Class"
0x180008378  mov     [rbp+440h+WndClass.lpszClassName], rax
0x18000837c  mov     qword ptr [rsp+540h+WndClass.style], r15
0x180008381  mov     qword ptr [rsp+540h+WndClass.cbClsExtra], r15
0x180008386  movdqa  xmmword ptr [rbp+440h+WndClass.hIcon], xmm0
0x18000838b  mov     [rbp+440h+WndClass.hbrBackground], r15
0x18000838f  call    cs:__imp_RegisterClassW
0x180008395  mov     cs:?WindowClassAtom@Globals@@3GA, ax; ushort Globals::WindowClassAtom
0x18000839c  test    ax, ax
0x18000839f  jz      loc_18000866D
0x1800083a5  movups  xmm0, xmmword ptr cs:aGdiWindow; "GDI+ Window"
0x1800083ac  lea     rax, [rbp+440h+var_468]
0x1800083b0  mov     esi, 82h
0x1800083b5  movsd   xmm1, qword ptr cs:aGdiWindow+10h; "dow"
0x1800083bd  lea     r12d, [r15+1]
0x1800083c1  mov     [rbp+440h+var_470], rax
0x1800083c5  lea     r14, [rbp+440h+WindowName]
0x1800083cc  lea     rax, [rbp+440h+var_480]
0x1800083d0  movsd   [rbp+440h+var_40], xmm1
0x1800083d8  mov     [rbp+440h+lpFilename], rax
0x1800083dc  mov     ebx, r15d
0x1800083df  movups  xmmword ptr [rbp+440h+WindowName], xmm0
0x1800083e6  mov     [rbp+440h+var_478], r12d
0x1800083ea  mov     [rbp+440h+var_490], r12d
0x1800083ee  add     esi, esi
0x1800083f0  lea     rcx, [rbp+440h+var_490]
0x1800083f4  mov     edx, esi
0x1800083f6  call    ?SetSize@?$AutoBuffer@G$00@@QEAAXH@Z; AutoBuffer<ushort,1>::SetSize(int)
0x1800083fb  mov     eax, [rbp+440h+var_490]
0x1800083fe  test    eax, eax
0x180008400  js      loc_1800086BB
0x180008406  mov     rdx, [rbp+440h+lpFilename]; lpFilename
0x18000840a  cmp     eax, r12d
0x18000840d  jle     short loc_18000841C
0x18000840f  lea     rax, [rbp+440h+var_480]
0x180008413  cmp     rdx, rax
0x180008416  jz      loc_1800086BB
0x18000841c  mov     r8d, esi; nSize
0x18000841f  xor     ecx, ecx; hModule
0x180008421  call    cs:__imp_GetModuleFileNameW
0x180008427  mov     edi, eax
0x180008429  add     ebx, r12d
0x18000842c  cmp     ebx, 4
0x18000842f  jb      loc_180008671
0x180008435  test    edi, edi
0x180008437  jz      short loc_1800084B7
0x180008439  call    cs:__imp_GetLastError
0x18000843f  cmp     eax, 7Ah ; 'z'
0x180008442  jz      short loc_1800084B7
0x180008444  mov     rcx, [rbp+440h+lpFilename]; Str
0x180008448  mov     edx, 5Ch ; '\'; Ch
0x18000844d  call    cs:__imp_wcsrchr
0x180008453  mov     rbx, rax
0x180008456  test    rax, rax
0x180008459  jz      loc_1800086C3
0x18000845f  add     rbx, 2
0x180008463  mov     rax, rbx
0x180008466  lea     rcx, [rbp+440h+var_478]
0x18000846a  sub     rax, [rbp+440h+lpFilename]
0x18000846e  sar     rax, 1
0x180008471  sub     edi, eax
0x180008473  add     edi, 0Fh
0x180008476  mov     edx, edi
0x180008478  call    ?SetSize@?$AutoBuffer@G$00@@QEAAXH@Z; AutoBuffer<ushort,1>::SetSize(int)
0x18000847d  mov     eax, [rbp+440h+var_478]
0x180008480  test    eax, eax
0x180008482  js      short loc_1800084B7
0x180008484  mov     rcx, [rbp+440h+var_470]; unsigned __int16 *
0x180008488  cmp     eax, r12d
0x18000848b  jle     short loc_180008496
0x18000848d  lea     rax, [rbp+440h+var_468]
0x180008491  cmp     rcx, rax
0x180008494  jz      short loc_1800084B7
0x180008496  mov     edx, edi; unsigned __int64
0x180008498  lea     r9, [rbp+440h+WindowName]
0x18000849f  lea     r8, aSS; "%s (%s)"
0x1800084a6  mov     qword ptr [rsp+540h+X], rbx
0x1800084ab  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800084b0  test    eax, eax
0x1800084b2  cmovns  r14, [rbp+440h+var_470]
0x1800084b7  lea     rcx, String; "GDI+ Accessibility"
0x1800084be  call    cs:__imp_RegisterWindowMessageW
0x1800084c4  movzx   edx, cs:?WindowClassAtom@Globals@@3GA; lpClassName
0x1800084cb  mov     r9d, 80000000h; dwStyle
0x1800084d1  mov     [rsp+540h+lpParam], r15; lpParam
0x1800084d6  mov     r8, r14; lpWindowName
0x1800084d9  mov     cs:?g_nAccessibilityMessage@Globals@@3IA, eax; uint Globals::g_nAccessibilityMessage
0x1800084df  xor     ecx, ecx; dwExStyle
0x1800084e1  mov     rax, cs:?DllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DllInstance
0x1800084e8  mov     [rsp+540h+hInstance], rax; hInstance
0x1800084ed  mov     [rsp+540h+hMenu], r15; hMenu
0x1800084f2  mov     [rsp+540h+hWndParent], r15; hWndParent
0x1800084f7  mov     [rsp+540h+nHeight], r12d; nHeight
0x1800084fc  mov     [rsp+540h+nWidth], r12d; nWidth
0x180008501  mov     [rsp+540h+Y], r15d; Y
0x180008506  mov     [rsp+540h+X], r15d; X
0x18000850b  call    cs:__imp_CreateWindowExW
0x180008511  mov     cs:?HwndNotify@Globals@@3PEAUHWND__@@EA, rax; HWND__ * Globals::HwndNotify
0x180008518  test    rax, rax
0x18000851b  jz      loc_180008629
0x180008521  call    ?IsUIAccessProcess@@YAHXZ; IsUIAccessProcess(void)
0x180008526  test    eax, eax
0x180008528  jnz     loc_18000868D
0x18000852e  xor     edx, edx; Val
0x180008530  lea     rcx, [rbp+440h+plpal.palPalEntry]; void *
0x180008534  mov     r8d, 404h; Size
0x18000853a  call    memset_0
0x18000853f  mov     r8d, r15d
0x180008542  mov     dword ptr [rbp+440h+plpal.palVersion], 1000300h
0x180008549  movsxd  rdx, r8d
0x18000854c  lea     rcx, qword_180176748
0x180008553  add     r8d, r12d
0x180008556  mov     ecx, [rcx+rdx*4]
0x180008559  mov     eax, ecx
0x18000855b  shr     eax, 10h
0x18000855e  mov     [rbp+rdx*4+440h+plpal.palPalEntry.peRed], al
0x180008562  mov     eax, ecx
0x180008564  shr     eax, 8
0x180008567  mov     [rbp+rdx*4+440h+plpal.palPalEntry.peGreen], al
0x18000856b  mov     [rbp+rdx*4+440h+plpal.palPalEntry.peBlue], cl
0x18000856f  mov     [rbp+rdx*4+440h+plpal.palPalEntry.peFlags], r15b
0x180008574  movzx   eax, [rbp+440h+plpal.palNumEntries]
0x180008578  cmp     r8d, eax
0x18000857b  jl      short loc_180008549
0x18000857d  lea     rcx, [rbp+440h+plpal]; plpal
0x180008581  call    cs:__imp_CreatePalette
0x180008587  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; hWnd
0x18000858e  mov     rdi, rax
0x180008591  call    cs:__imp_GetDC
0x180008597  xor     r8d, r8d; bForceBkgd
0x18000859a  mov     rdx, rdi; hPal
0x18000859d  mov     rcx, rax; hdc
0x1800085a0  mov     rbx, rax
0x1800085a3  call    cs:__imp_SelectPalette
0x1800085a9  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; hWnd
0x1800085b0  mov     rdx, rbx; hDC
0x1800085b3  call    cs:__imp_ReleaseDC
0x1800085b9  mov     rcx, rdi; ho
0x1800085bc  call    cs:__imp_DeleteObject
0x1800085c2  mov     rax, cs:?g_pfnWTSRegisterSessionNotificationFunction@Globals@@3P6AHPEAUHWND__@@K@ZEA; int (*Globals::g_pfnWTSRegisterSessionNotificationFunction)(HWND__ *,ulong)
0x1800085c9  test    rax, rax
0x1800085cc  jnz     loc_1800086E3
0x1800085d2  mov     rcx, [rbp+440h+lpFilename]
0x1800085d6  lea     rax, [rbp+440h+var_480]
0x1800085da  cmp     rcx, rax
0x1800085dd  jz      short loc_1800085E4
0x1800085df  call    GpFree
0x1800085e4  lea     rcx, [rbp+440h+var_480]
0x1800085e8  mov     [rbp+440h+var_490], 0FFFFFFFFh
0x1800085ef  mov     [rbp+440h+lpFilename], rcx
0x1800085f3  lea     rdx, [rbp+440h+var_468]
0x1800085f7  mov     rcx, [rbp+440h+var_470]
0x1800085fb  cmp     rcx, rdx
0x1800085fe  jz      short loc_180008605
0x180008600  call    GpFree
0x180008605  mov     eax, r12d
0x180008608  mov     rcx, [rbp+440h+var_38]
0x18000860f  xor     rcx, rsp; StackCookie
0x180008612  call    __security_check_cookie
0x180008617  add     rsp, 510h
0x18000861e  pop     r15
0x180008620  pop     r14
0x180008622  pop     r12
0x180008624  pop     rdi
0x180008625  pop     rsi
0x180008626  pop     rbx
0x180008627  pop     rbp
0x180008628  retn
0x180008629  call    ?InternalNotificationShutdown@@YAPEAXXZ; InternalNotificationShutdown(void)
0x18000862e  mov     rbx, rax
0x180008631  test    rax, rax
0x180008634  jnz     loc_1800086CC
0x18000863a  mov     rcx, [rbp+440h+lpFilename]
0x18000863e  lea     rax, [rbp+440h+var_480]
0x180008642  cmp     rcx, rax
0x180008645  jz      short loc_18000864C
0x180008647  call    GpFree
0x18000864c  mov     rcx, [rbp+440h+var_470]
0x180008650  lea     rax, [rbp+440h+var_480]
0x180008654  mov     [rbp+440h+lpFilename], rax
0x180008658  lea     rax, [rbp+440h+var_468]
0x18000865c  mov     [rbp+440h+var_490], 0FFFFFFFFh
0x180008663  cmp     rcx, rax
0x180008666  jz      short loc_18000866D
0x180008668  call    GpFree
0x18000866d  xor     eax, eax
0x18000866f  jmp     short loc_180008608
0x180008671  test    edi, edi
0x180008673  jz      loc_1800084B7
0x180008679  call    cs:__imp_GetLastError
0x18000867f  cmp     eax, 7Ah ; 'z'
0x180008682  jnz     loc_180008435
0x180008688  jmp     loc_1800083EE
0x18000868d  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; hWnd
0x180008694  xor     r9d, r9d; Y
0x180008697  mov     [rsp+540h+nWidth], 1Bh; uFlags
0x18000869f  xor     r8d, r8d; X
0x1800086a2  mov     [rsp+540h+Y], r15d; cy
0x1800086a7  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x1800086ab  mov     [rsp+540h+X], r15d; cx
0x1800086b0  call    cs:__imp_SetWindowPos
0x1800086b6  jmp     loc_18000852E
0x1800086bb  mov     edi, r15d
0x1800086be  jmp     loc_180008429
0x1800086c3  mov     rbx, [rbp+440h+lpFilename]
0x1800086c7  jmp     loc_180008463
0x1800086cc  mov     rcx, rbx; hEvent
0x1800086cf  call    cs:__imp_SetEvent
0x1800086d5  mov     rcx, rbx; hObject
0x1800086d8  call    cs:__imp_CloseHandle
0x1800086de  jmp     loc_18000863A
0x1800086e3  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; HWND__ * Globals::HwndNotify
0x1800086ea  xor     edx, edx
0x1800086ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f1  jmp     loc_1800085D2
```
