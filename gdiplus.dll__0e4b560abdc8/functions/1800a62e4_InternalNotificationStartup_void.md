# InternalNotificationStartup(void)

- ea: `0x1800a62e4`
- end: `0x1800a6739`
- name: `?InternalNotificationStartup@@YAHXZ`
- size: `1109`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x1800a61c0`
- `0x180102a40`

## callees

- `0x18001f950`
- `0x1800a62e4`
- `0x1800a6740`
- `0x1800d3390`
- `0x1800e860c`
- `0x1800e8df0`
- `0x1800e9380`
- `0x1800ea0ec`
- `0x180102c04`
- `0x180175010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a63ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800a63ff`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a6706`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800a6706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a641d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a66d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a641d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a66d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a6715`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a6715`
- `USER32!SetWindowPos` at `0x1800a66bf`
- `USER32!SetWindowPos` at `0x1800a66bf`
- `USER32!CreateWindowExW` at `0x1800a64f5`
- `USER32!CreateWindowExW` at `0x1800a64f5`
- `USER32!RegisterWindowMessageW` at `0x1800a64a2`
- `USER32!RegisterWindowMessageW` at `0x1800a64a2`
- `USER32!RegisterClassW` at `0x1800a6367`
- `USER32!RegisterClassW` at `0x1800a6367`
- `USER32!GetDC` at `0x1800a658b`
- `USER32!GetDC` at `0x1800a658b`
- `USER32!ReleaseDC` at `0x1800a65b9`
- `USER32!ReleaseDC` at `0x1800a65b9`
- `GDI32!SelectPalette` at `0x1800a65a3`
- `GDI32!SelectPalette` at `0x1800a65a3`
- `GDI32!DeleteObject` at `0x1800a65c8`
- `GDI32!DeleteObject` at `0x1800a65c8`
- `GDI32!CreatePalette` at `0x1800a6575`
- `GDI32!CreatePalette` at `0x1800a6575`

## string_xrefs

- `0x1800a649b`: `GDI+ Accessibility`

## pseudocode

```c
__int64 InternalNotificationStartup(void)
{
  DWORD v0; // esi
  WCHAR *v1; // r14
  int v2; // ebx
  DWORD ModuleFileNameW; // edi
  unsigned __int16 v4; // dx
  unsigned __int16 *v5; // rax
  LPWSTR v6; // rbx
  unsigned int v7; // edi
  int v8; // r8d
  __int64 v9; // rdx
  int v10; // ecx
  HPALETTE v11; // rdi
  HDC DC; // rbx
  void *v14; // rax
  void *v15; // rbx
  WNDCLASSW WndClass; // [rsp+68h] [rbp-A0h] BYREF
  int v17; // [rsp+B8h] [rbp-50h] BYREF
  LPWSTR lpFilename; // [rsp+C0h] [rbp-48h]
  char v19; // [rsp+C8h] [rbp-40h] BYREF
  int v20; // [rsp+D0h] [rbp-38h] BYREF
  unsigned __int16 *v21; // [rsp+D8h] [rbp-30h]
  char v22; // [rsp+E0h] [rbp-28h] BYREF
  LOGPALETTE plpal; // [rsp+E8h] [rbp-20h] BYREF
  WCHAR WindowName[12]; // [rsp+4F8h] [rbp+3F0h] BYREF

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
  v21 = (unsigned __int16 *)&v22;
  wcscpy(WindowName, L"GDI+ Window");
  v20 = 1;
  v1 = WindowName;
  v2 = 0;
  v17 = 1;
  lpFilename = (LPWSTR)&v19;
  do
  {
    v0 *= 2;
    AutoBuffer<unsigned short,1>::SetSize(&v17, v0);
    if ( v17 < 0 || v17 > 1 && lpFilename == (LPWSTR)&v19 )
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
    v5 = wcsrchr(lpFilename, v4);
    v6 = v5 ? v5 + 1 : lpFilename;
    v7 = ModuleFileNameW - (v6 - lpFilename) + 15;
    AutoBuffer<unsigned short,1>::SetSize(&v20, v7);
    if ( v20 >= 0
      && (v20 <= 1 || v21 != (unsigned __int16 *)&v22)
      && (int)StringCchPrintfW(v21, v7, L"%s (%s)", WindowName, v6) >= 0 )
    {
      v1 = v21;
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
    v14 = InternalNotificationShutdown();
    v15 = v14;
    if ( v14 )
    {
      SetEvent(v14);
      CloseHandle(v15);
    }
    if ( lpFilename != (LPWSTR)&v19 )
      GpFree(lpFilename);
    v17 = -1;
    lpFilename = (LPWSTR)&v19;
    if ( v21 != (unsigned __int16 *)&v22 )
      GpFree(v21);
    return 0;
  }
  if ( (unsigned int)IsUIAccessProcess() )
    SetWindowPos(Globals::HwndNotify, HWND_MESSAGE|0x2LL, 0, 0, 0, 0, 0x1Bu);
  memset_0(plpal.palPalEntry, 0, 0x404u);
  v8 = 0;
  *(_DWORD *)&plpal.palVersion = 16777984;
  v9 = 0;
  do
  {
    plpal.palPalEntry[v9].peFlags = 0;
    v10 = *(_DWORD *)((char *)qword_180187358 + v9 * 4);
    ++v8;
    plpal.palPalEntry[v9++].peBlue = v10;
    *((_BYTE *)&plpal.palVersion + v9 * 4) = BYTE2(v10);
    *((_BYTE *)&plpal.palVersion + v9 * 4 + 1) = BYTE1(v10);
  }
  while ( v8 < plpal.palNumEntries );
  v11 = CreatePalette(&plpal);
  DC = GetDC(Globals::HwndNotify);
  SelectPalette(DC, v11, 0);
  ReleaseDC(Globals::HwndNotify, DC);
  DeleteObject(v11);
  if ( Globals::g_pfnWTSRegisterSessionNotificationFunction )
    Globals::g_pfnWTSRegisterSessionNotificationFunction(Globals::HwndNotify, 0);
  if ( lpFilename != (LPWSTR)&v19 )
    GpFree(lpFilename);
  v17 = -1;
  lpFilename = (LPWSTR)&v19;
  if ( v21 != (unsigned __int16 *)&v22 )
    GpFree(v21);
  return 1;
}

```

## disassembly

```asm
0x1800a62e4  mov     rax, rsp
0x1800a62e7  mov     [rax+8], rbx
0x1800a62eb  mov     [rax+10h], rsi
0x1800a62ef  mov     [rax+18h], rdi
0x1800a62f3  mov     [rax+20h], r12
0x1800a62f7  push    rbp
0x1800a62f8  push    r14
0x1800a62fa  push    r15
0x1800a62fc  lea     rbp, [rax-428h]
0x1800a6303  sub     rsp, 510h
0x1800a630a  mov     rax, cs:__security_cookie
0x1800a6311  xor     rax, rsp
0x1800a6314  mov     [rbp+420h+var_18], rax
0x1800a631b  xor     r15d, r15d
0x1800a631e  lea     rax, ?NotificationWndProc@@YA_JPEAUHWND__@@I_K_J@Z; NotificationWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x1800a6325  mov     [rsp+520h+WndClass.lpfnWndProc], rax
0x1800a632a  lea     rcx, [rsp+520h+WndClass]; lpWndClass
0x1800a632f  mov     rax, cs:?DllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DllInstance
0x1800a6336  xorps   xmm0, xmm0
0x1800a6339  mov     [rsp+520h+WndClass.hInstance], rax
0x1800a633e  lea     rax, aGdiHookWindow; "GDI+ Hook Window"
0x1800a6345  mov     [rbp+420h+WndClass.lpszMenuName], rax
0x1800a6349  lea     rax, aGdiHookWindowC; "GDI+ Hook Window Class"
0x1800a6350  mov     [rbp+420h+WndClass.lpszClassName], rax
0x1800a6354  mov     qword ptr [rsp+520h+WndClass.style], r15
0x1800a6359  mov     qword ptr [rsp+520h+WndClass.cbClsExtra], r15
0x1800a635e  movdqa  xmmword ptr [rbp+420h+WndClass.hIcon], xmm0
0x1800a6363  mov     [rbp+420h+WndClass.hbrBackground], r15
0x1800a6367  call    cs:__imp_RegisterClassW
0x1800a636e  nop     dword ptr [rax+rax+00h]
0x1800a6373  mov     cs:?WindowClassAtom@Globals@@3GA, ax; ushort Globals::WindowClassAtom
0x1800a637a  test    ax, ax
0x1800a637d  jz      loc_1800A6679
0x1800a6383  movups  xmm0, xmmword ptr cs:aGdiWindow; "GDI+ Window"
0x1800a638a  lea     rax, [rbp+420h+var_448]
0x1800a638e  mov     esi, 82h
0x1800a6393  lea     r12d, [r15+1]
0x1800a6397  mov     [rbp+420h+var_450], rax
0x1800a639b  movups  xmmword ptr [rbp+420h+WindowName], xmm0
0x1800a63a2  lea     rax, [rbp+420h+var_460]
0x1800a63a6  mov     [rbp+420h+var_458], r12d
0x1800a63aa  movsd   xmm0, qword ptr cs:aGdiWindow+10h; "dow"
0x1800a63b2  lea     r14, [rbp+420h+WindowName]
0x1800a63b9  movsd   [rbp+420h+var_20], xmm0
0x1800a63c1  mov     ebx, r15d
0x1800a63c4  mov     [rbp+420h+var_470], r12d
0x1800a63c8  mov     [rbp+420h+lpFilename], rax
0x1800a63cc  add     esi, esi
0x1800a63ce  lea     rcx, [rbp+420h+var_470]
0x1800a63d2  mov     edx, esi
0x1800a63d4  call    ?SetSize@?$AutoBuffer@G$00@@QEAAXH@Z; AutoBuffer<ushort,1>::SetSize(int)
0x1800a63d9  mov     eax, [rbp+420h+var_470]
0x1800a63dc  test    eax, eax
0x1800a63de  js      loc_1800A66FB
0x1800a63e4  mov     rdx, [rbp+420h+lpFilename]; lpFilename
0x1800a63e8  cmp     eax, r12d
0x1800a63eb  jle     short loc_1800A63FA
0x1800a63ed  lea     rax, [rbp+420h+var_460]
0x1800a63f1  cmp     rdx, rax
0x1800a63f4  jz      loc_1800A66FB
0x1800a63fa  mov     r8d, esi; nSize
0x1800a63fd  xor     ecx, ecx; hModule
0x1800a63ff  call    cs:__imp_GetModuleFileNameW
0x1800a6406  nop     dword ptr [rax+rax+00h]
0x1800a640b  mov     edi, eax
0x1800a640d  add     ebx, r12d
0x1800a6410  cmp     ebx, 4
0x1800a6413  jb      loc_1800A66D0
0x1800a6419  test    edi, edi
0x1800a641b  jz      short loc_1800A649B
0x1800a641d  call    cs:__imp_GetLastError
0x1800a6424  nop     dword ptr [rax+rax+00h]
0x1800a6429  cmp     eax, 7Ah ; 'z'
0x1800a642c  jz      short loc_1800A649B
0x1800a642e  mov     rcx, [rbp+420h+lpFilename]; unsigned __int16 *
0x1800a6432  call    ?wcsrchr@@YAPEAGPEAGG@Z; wcsrchr(ushort *,ushort)
0x1800a6437  mov     rbx, rax
0x1800a643a  test    rax, rax
0x1800a643d  jz      loc_1800A66F2
0x1800a6443  add     rbx, 2
0x1800a6447  mov     rax, rbx
0x1800a644a  lea     rcx, [rbp+420h+var_458]
0x1800a644e  sub     rax, [rbp+420h+lpFilename]
0x1800a6452  sar     rax, 1
0x1800a6455  sub     edi, eax
0x1800a6457  add     edi, 0Fh
0x1800a645a  mov     edx, edi
0x1800a645c  call    ?SetSize@?$AutoBuffer@G$00@@QEAAXH@Z; AutoBuffer<ushort,1>::SetSize(int)
0x1800a6461  mov     eax, [rbp+420h+var_458]
0x1800a6464  test    eax, eax
0x1800a6466  js      short loc_1800A649B
0x1800a6468  mov     rcx, [rbp+420h+var_450]; unsigned __int16 *
0x1800a646c  cmp     eax, r12d
0x1800a646f  jle     short loc_1800A647A
0x1800a6471  lea     rax, [rbp+420h+var_448]
0x1800a6475  cmp     rcx, rax
0x1800a6478  jz      short loc_1800A649B
0x1800a647a  mov     edx, edi; unsigned __int64
0x1800a647c  lea     r9, [rbp+420h+WindowName]
0x1800a6483  lea     r8, aSS; "%s (%s)"
0x1800a648a  mov     qword ptr [rsp+520h+X], rbx
0x1800a648f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a6494  test    eax, eax
0x1800a6496  cmovns  r14, [rbp+420h+var_450]
0x1800a649b  lea     rcx, String; "GDI+ Accessibility"
0x1800a64a2  call    cs:__imp_RegisterWindowMessageW
0x1800a64a9  nop     dword ptr [rax+rax+00h]
0x1800a64ae  movzx   edx, cs:?WindowClassAtom@Globals@@3GA; lpClassName
0x1800a64b5  mov     r9d, 80000000h; dwStyle
0x1800a64bb  mov     [rsp+520h+lpParam], r15; lpParam
0x1800a64c0  mov     r8, r14; lpWindowName
0x1800a64c3  mov     cs:?g_nAccessibilityMessage@Globals@@3IA, eax; uint Globals::g_nAccessibilityMessage
0x1800a64c9  xor     ecx, ecx; dwExStyle
0x1800a64cb  mov     rax, cs:?DllInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * DllInstance
0x1800a64d2  mov     [rsp+520h+hInstance], rax; hInstance
0x1800a64d7  mov     [rsp+520h+hMenu], r15; hMenu
0x1800a64dc  mov     [rsp+520h+hWndParent], r15; hWndParent
0x1800a64e1  mov     [rsp+520h+nHeight], r12d; nHeight
0x1800a64e6  mov     [rsp+520h+nWidth], r12d; nWidth
0x1800a64eb  mov     [rsp+520h+Y], r15d; Y
0x1800a64f0  mov     [rsp+520h+X], r15d; X
0x1800a64f5  call    cs:__imp_CreateWindowExW
0x1800a64fc  nop     dword ptr [rax+rax+00h]
0x1800a6501  mov     cs:?HwndNotify@Globals@@3PEAUHWND__@@EA, rax; HWND__ * Globals::HwndNotify
0x1800a6508  test    rax, rax
0x1800a650b  jz      loc_1800A6642
0x1800a6511  call    ?IsUIAccessProcess@@YAHXZ; IsUIAccessProcess(void)
0x1800a6516  test    eax, eax
0x1800a6518  jnz     loc_1800A669C
0x1800a651e  xor     edx, edx; Val
0x1800a6520  lea     rcx, [rbp+420h+plpal.palPalEntry]; void *
0x1800a6524  mov     r8d, 404h; Size
0x1800a652a  call    memset_0
0x1800a652f  mov     r8d, r15d
0x1800a6532  mov     dword ptr [rbp+420h+plpal.palVersion], 1000300h
0x1800a6539  mov     rdx, r15
0x1800a653c  mov     [rbp+rdx+420h+plpal.palPalEntry.peFlags], r15b
0x1800a6541  lea     rcx, qword_180187358
0x1800a6548  mov     ecx, [rdx+rcx]
0x1800a654b  add     r8d, r12d
0x1800a654e  mov     [rbp+rdx+420h+plpal.palPalEntry.peBlue], cl
0x1800a6552  lea     rdx, [rdx+4]
0x1800a6556  mov     eax, ecx
0x1800a6558  shr     eax, 10h
0x1800a655b  mov     byte ptr [rbp+rdx+420h+plpal.palVersion], al
0x1800a655f  mov     eax, ecx
0x1800a6561  shr     eax, 8
0x1800a6564  mov     byte ptr [rbp+rdx+420h+plpal.palVersion+1], al
0x1800a6568  movzx   eax, [rbp+420h+plpal.palNumEntries]
0x1800a656c  cmp     r8d, eax
0x1800a656f  jl      short loc_1800A653C
0x1800a6571  lea     rcx, [rbp+420h+plpal]; plpal
0x1800a6575  call    cs:__imp_CreatePalette
0x1800a657c  nop     dword ptr [rax+rax+00h]
0x1800a6581  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; hWnd
0x1800a6588  mov     rdi, rax
0x1800a658b  call    cs:__imp_GetDC
0x1800a6592  nop     dword ptr [rax+rax+00h]
0x1800a6597  xor     r8d, r8d; bForceBkgd
0x1800a659a  mov     rdx, rdi; hPal
0x1800a659d  mov     rcx, rax; hdc
0x1800a65a0  mov     rbx, rax
0x1800a65a3  call    cs:__imp_SelectPalette
0x1800a65aa  nop     dword ptr [rax+rax+00h]
0x1800a65af  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; hWnd
0x1800a65b6  mov     rdx, rbx; hDC
0x1800a65b9  call    cs:__imp_ReleaseDC
0x1800a65c0  nop     dword ptr [rax+rax+00h]
0x1800a65c5  mov     rcx, rdi; ho
0x1800a65c8  call    cs:__imp_DeleteObject
0x1800a65cf  nop     dword ptr [rax+rax+00h]
0x1800a65d4  mov     rax, cs:?g_pfnWTSRegisterSessionNotificationFunction@Globals@@3P6AHPEAUHWND__@@K@ZEA; int (*Globals::g_pfnWTSRegisterSessionNotificationFunction)(HWND__ *,ulong)
0x1800a65db  test    rax, rax
0x1800a65de  jnz     loc_1800A6726
0x1800a65e4  mov     rcx, [rbp+420h+lpFilename]
0x1800a65e8  lea     rax, [rbp+420h+var_460]
0x1800a65ec  cmp     rcx, rax
0x1800a65ef  jnz     loc_1800A667D
0x1800a65f5  or      [rbp+420h+var_470], 0FFFFFFFFh
0x1800a65f9  lea     rcx, [rbp+420h+var_460]
0x1800a65fd  mov     [rbp+420h+lpFilename], rcx
0x1800a6601  lea     rdx, [rbp+420h+var_448]
0x1800a6605  mov     rcx, [rbp+420h+var_450]
0x1800a6609  cmp     rcx, rdx
0x1800a660c  jnz     short loc_1800A6687
0x1800a660e  mov     eax, r12d
0x1800a6611  mov     rcx, [rbp+420h+var_18]
0x1800a6618  xor     rcx, rsp; StackCookie
0x1800a661b  call    __security_check_cookie
0x1800a6620  lea     r11, [rsp+520h+var_10]
0x1800a6628  mov     rbx, [r11+20h]
0x1800a662c  mov     rsi, [r11+28h]
0x1800a6630  mov     rdi, [r11+30h]
0x1800a6634  mov     r12, [r11+38h]
0x1800a6638  mov     rsp, r11
0x1800a663b  pop     r15
0x1800a663d  pop     r14
0x1800a663f  pop     rbp
0x1800a6640  retn
0x1800a6642  call    ?InternalNotificationShutdown@@YAPEAXXZ; InternalNotificationShutdown(void)
0x1800a6647  mov     rbx, rax
0x1800a664a  test    rax, rax
0x1800a664d  jnz     loc_1800A6703
0x1800a6653  mov     rcx, [rbp+420h+lpFilename]
0x1800a6657  lea     rax, [rbp+420h+var_460]
0x1800a665b  cmp     rcx, rax
0x1800a665e  jnz     short loc_1800A668E
0x1800a6660  or      [rbp+420h+var_470], 0FFFFFFFFh
0x1800a6664  lea     rax, [rbp+420h+var_460]
0x1800a6668  mov     rcx, [rbp+420h+var_450]
0x1800a666c  mov     [rbp+420h+lpFilename], rax
0x1800a6670  lea     rax, [rbp+420h+var_448]
0x1800a6674  cmp     rcx, rax
0x1800a6677  jnz     short loc_1800A6695
0x1800a6679  xor     eax, eax
0x1800a667b  jmp     short loc_1800A6611
0x1800a667d  call    GpFree
0x1800a6682  jmp     loc_1800A65F5
0x1800a6687  call    GpFree
0x1800a668c  jmp     short loc_1800A660E
0x1800a668e  call    GpFree
0x1800a6693  jmp     short loc_1800A6660
0x1800a6695  call    GpFree
0x1800a669a  jmp     short loc_1800A6679
0x1800a669c  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; hWnd
0x1800a66a3  xor     r9d, r9d; Y
0x1800a66a6  mov     [rsp+520h+nWidth], 1Bh; uFlags
0x1800a66ae  xor     r8d, r8d; X
0x1800a66b1  mov     [rsp+520h+Y], r15d; cy
0x1800a66b6  or      rdx, 0FFFFFFFFFFFFFFFFh; hWndInsertAfter
0x1800a66ba  mov     [rsp+520h+X], r15d; cx
0x1800a66bf  call    cs:__imp_SetWindowPos
0x1800a66c6  nop     dword ptr [rax+rax+00h]
0x1800a66cb  jmp     loc_1800A651E
0x1800a66d0  test    edi, edi
0x1800a66d2  jz      loc_1800A649B
0x1800a66d8  call    cs:__imp_GetLastError
0x1800a66df  nop     dword ptr [rax+rax+00h]
0x1800a66e4  cmp     eax, 7Ah ; 'z'
0x1800a66e7  jnz     loc_1800A6419
0x1800a66ed  jmp     loc_1800A63CC
0x1800a66f2  mov     rbx, [rbp+420h+lpFilename]
0x1800a66f6  jmp     loc_1800A6447
0x1800a66fb  mov     edi, r15d
0x1800a66fe  jmp     loc_1800A640D
0x1800a6703  mov     rcx, rbx; hEvent
0x1800a6706  call    cs:__imp_SetEvent
0x1800a670d  nop     dword ptr [rax+rax+00h]
0x1800a6712  mov     rcx, rbx; hObject
0x1800a6715  call    cs:__imp_CloseHandle
0x1800a671c  nop     dword ptr [rax+rax+00h]
0x1800a6721  jmp     loc_1800A6653
0x1800a6726  mov     rcx, cs:?HwndNotify@Globals@@3PEAUHWND__@@EA; HWND__ * Globals::HwndNotify
0x1800a672d  xor     edx, edx
0x1800a672f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6734  jmp     loc_1800A65E4
```
