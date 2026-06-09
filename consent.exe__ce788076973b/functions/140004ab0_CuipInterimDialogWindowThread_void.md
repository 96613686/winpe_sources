# CuipInterimDialogWindowThread(void *)

- ea: `0x140004ab0`
- end: `0x140004fb2`
- name: `?CuipInterimDialogWindowThread@@YAKPEAX@Z`
- size: `1282`
- prototype: `__int64 __fastcall(HINSTANCE *Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callees

- `0x140004ab0`
- `0x14000e558`
- `0x14000fbec`
- `0x140010ad3`
- `0x140013928`
- `0x14001e050`

## import_xrefs

- `USER32!GetMessageW` at `0x140004ca0`
- `USER32!GetMessageW` at `0x140004ca0`
- `USER32!LoadStringW` at `0x140004b4c`
- `USER32!LoadStringW` at `0x140004d10`
- `USER32!LoadStringW` at `0x140004b4c`
- `USER32!LoadStringW` at `0x140004d10`
- `USER32!LoadIconW` at `0x140004bb6`
- `USER32!LoadIconW` at `0x140004bb6`
- `USER32!CreateWindowExW` at `0x140004c4f`
- `USER32!CreateWindowExW` at `0x140004c4f`
- `USER32!UnregisterClassW` at `0x140004f92`
- `USER32!UnregisterClassW` at `0x14001e187`
- `USER32!UnregisterClassW` at `0x140004f92`
- `USER32!UnregisterClassW` at `0x14001e187`
- `USER32!ShowWindow` at `0x140004c66`
- `USER32!ShowWindow` at `0x140004c66`
- `USER32!DispatchMessageW` at `0x140004cc9`
- `USER32!DispatchMessageW` at `0x140004cc9`
- `USER32!RegisterClassW` at `0x140004c03`
- `USER32!RegisterClassW` at `0x140004c03`
- `USER32!TranslateMessage` at `0x140004cbb`
- `USER32!TranslateMessage` at `0x140004cbb`
- `USER32!LoadCursorW` at `0x140004bcb`
- `USER32!LoadCursorW` at `0x140004bcb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004bf5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004da4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004dff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004e80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004eea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004f3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004faa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001e1a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140004faa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001e1a3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140004d59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140004d59`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140004b6e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140004b6e`

## string_xrefs

- `0x140004b67`: `imageres.dll`

## pseudocode

```c
__int64 __fastcall CuipInterimDialogWindowThread(HINSTANCE *Parameter)
{
  HINSTANCE v2; // rdi
  int v3; // r14d
  HINSTANCE hInstance; // r15
  WCHAR *v5; // rsi
  HINSTANCE v6; // rcx
  HMODULE LibraryW; // rbx
  HWND Window; // rax
  int MessageW; // eax
  unsigned int v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned __int64 v14; // rbx
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  DWORD LastError; // eax
  WNDCLASSW WndClass; // [rsp+80h] [rbp-2D8h] BYREF
  tagMSG Msg; // [rsp+D0h] [rbp-288h] BYREF
  WCHAR Buffer[264]; // [rsp+100h] [rbp-258h] BYREF

  memset_0(&WndClass, 0, sizeof(WndClass));
  memset(&Msg, 0, sizeof(Msg));
  v2 = Parameter[6];
  v3 = 0;
  hInstance = *Parameter;
  v5 = 0;
  v6 = *Parameter;
  if ( v2 )
  {
    if ( !LoadStringW(v6, 0x7D0u, Buffer, 260) )
    {
      LastError = GetLastError();
      v10 = LastError;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        goto LABEL_48;
      v17 = 53;
      goto LABEL_26;
    }
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( Buffer[v12] );
    do
      ++v11;
    while ( *((_WORD *)v2 + v11) );
    v13 = (unsigned int)(v11 + 1 + v12);
    v14 = (unsigned int)v13;
    v15 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v13);
    v5 = v15;
    if ( v15 )
    {
      if ( !(unsigned int)StringCchPrintfW(v15, v14, Buffer, v2) )
        goto LABEL_4;
      v10 = 111;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        goto LABEL_48;
      v17 = 55;
      v18 = 111;
    }
    else
    {
      v10 = 14;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
        goto LABEL_48;
      v17 = 54;
      v18 = 14;
    }
LABEL_27:
    WPP_SF_D(*(_QWORD *)(v16 + 16), v17, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids, v18);
    goto LABEL_48;
  }
  if ( !LoadStringW(v6, 0x7D1u, Buffer, 260) )
  {
    LastError = GetLastError();
    v10 = LastError;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_48;
    v17 = 52;
    goto LABEL_26;
  }
  v5 = Buffer;
LABEL_4:
  LibraryW = LoadLibraryW(L"imageres.dll");
  if ( !LibraryW )
  {
    LastError = GetLastError();
    v10 = LastError;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_48;
    v17 = 56;
    goto LABEL_26;
  }
  WndClass.style = 0;
  WndClass.lpfnWndProc = (WNDPROC)InterimDialogWndProc;
  *(_QWORD *)&WndClass.cbClsExtra = 0;
  WndClass.hInstance = hInstance;
  WndClass.hIcon = LoadIconW(LibraryW, (LPCWSTR)0x4E);
  WndClass.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  *(__m128i *)&WndClass.hbrBackground = _mm_load_si128((const __m128i *)&_xmm);
  WndClass.lpszClassName = L"$$$Secure UAP Dummy Window Class For Interim Dialog";
  FreeLibrary(LibraryW);
  if ( !RegisterClassW(&WndClass) )
  {
    LastError = GetLastError();
    v10 = LastError;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_48;
    v17 = 57;
    goto LABEL_26;
  }
  v3 = 1;
  Window = CreateWindowExW(
             0,
             L"$$$Secure UAP Dummy Window Class For Interim Dialog",
             v5,
             0xA0C80000,
             0,
             0,
             0,
             0,
             0,
             0,
             hInstance,
             0);
  if ( !Window )
  {
    LastError = GetLastError();
    v10 = LastError;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
      goto LABEL_48;
    v17 = 58;
LABEL_26:
    v18 = LastError;
    goto LABEL_27;
  }
  ShowWindow(Window, 6);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 59, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
  while ( 1 )
  {
    MessageW = GetMessageW(&Msg, 0, 0, 0);
    if ( !MessageW )
    {
      v10 = 0;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 61, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids);
      goto LABEL_48;
    }
    if ( MessageW == -1 )
      break;
    TranslateMessage(&Msg);
    DispatchMessageW(&Msg);
  }
  LastError = GetLastError();
  v10 = LastError;
  v16 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    v17 = 60;
    goto LABEL_26;
  }
LABEL_48:
  if ( v3 )
    UnregisterClassW(L"$$$Secure UAP Dummy Window Class For Interim Dialog", hInstance);
  if ( v5 && v5 != Buffer )
    LocalFree(v5);
  return v10;
}

```

## disassembly

```asm
0x140004ab0  push    rbx
0x140004ab2  push    rsi
0x140004ab3  push    rdi
0x140004ab4  push    r12
0x140004ab6  push    r14
0x140004ab8  push    r15
0x140004aba  sub     rsp, 328h
0x140004ac1  mov     rax, cs:__security_cookie
0x140004ac8  xor     rax, rsp
0x140004acb  mov     [rsp+358h+var_48], rax
0x140004ad3  mov     rbx, rcx
0x140004ad6  xor     edx, edx; Val
0x140004ad8  mov     r8d, 48h ; 'H'; Size
0x140004ade  lea     rcx, [rsp+358h+WndClass]; void *
0x140004ae6  call    memset_0
0x140004aeb  xorps   xmm0, xmm0
0x140004aee  movups  xmmword ptr [rsp+358h+Msg.hwnd], xmm0
0x140004af6  movups  xmmword ptr [rsp+358h+Msg.wParam], xmm0
0x140004afe  movups  xmmword ptr [rsp+358h+Msg.time], xmm0
0x140004b06  lea     r12, ClassName; "$$$Secure UAP Dummy Window Class For In"...
0x140004b0d  mov     [rsp+358h+var_2E0], r12
0x140004b12  mov     rdi, [rbx+30h]
0x140004b16  xor     r14d, r14d
0x140004b19  mov     [rsp+358h+var_2F4], r14d
0x140004b1e  mov     r15, [rbx]
0x140004b21  mov     [rsp+358h+var_2E8], r15
0x140004b26  xor     esi, esi
0x140004b28  mov     [rsp+358h+var_2F0], rsi
0x140004b2d  mov     r9d, 104h; cchBufferMax
0x140004b33  lea     r8, [rsp+358h+Buffer]; lpBuffer
0x140004b3b  mov     rcx, r15; hInstance
0x140004b3e  test    rdi, rdi
0x140004b41  jnz     loc_140004D0B
0x140004b47  mov     edx, 7D1h; uID
0x140004b4c  call    cs:__imp_LoadStringW
0x140004b52  test    eax, eax
0x140004b54  jz      loc_140004DA4
0x140004b5a  lea     rsi, [rsp+358h+Buffer]
0x140004b62  mov     [rsp+358h+var_2F0], rsi
0x140004b67  lea     rcx, LibFileName; "imageres.dll"
0x140004b6e  call    cs:__imp_LoadLibraryW
0x140004b74  mov     rbx, rax
0x140004b77  test    rax, rax
0x140004b7a  jz      loc_140004E80
0x140004b80  mov     [rsp+358h+WndClass.style], 0
0x140004b8b  lea     rax, ?InterimDialogWndProc@@YA_JPEAUHWND__@@I_K_J@Z; InterimDialogWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x140004b92  mov     [rsp+358h+WndClass.lpfnWndProc], rax
0x140004b9a  mov     qword ptr [rsp+358h+WndClass.cbClsExtra], 0
0x140004ba6  mov     [rsp+358h+WndClass.hInstance], r15
0x140004bae  mov     edx, 4Eh ; 'N'; lpIconName
0x140004bb3  mov     rcx, rbx; hInstance
0x140004bb6  call    cs:__imp_LoadIconW
0x140004bbc  mov     [rsp+358h+WndClass.hIcon], rax
0x140004bc4  mov     edx, 7F00h; lpCursorName
0x140004bc9  xor     ecx, ecx; hInstance
0x140004bcb  call    cs:__imp_LoadCursorW
0x140004bd1  mov     [rsp+358h+WndClass.hCursor], rax
0x140004bd9  movdqa  xmm0, cs:__xmm@00000000000000000000000000000006
0x140004be1  movdqa  xmmword ptr [rsp+358h+WndClass.hbrBackground], xmm0
0x140004bea  mov     [rsp+358h+WndClass.lpszClassName], r12
0x140004bf2  mov     rcx, rbx; hLibModule
0x140004bf5  call    cs:__imp_FreeLibrary
0x140004bfb  lea     rcx, [rsp+358h+WndClass]; lpWndClass
0x140004c03  call    cs:__imp_RegisterClassW
0x140004c09  xor     ecx, ecx; dwExStyle
0x140004c0b  cmp     cx, ax
0x140004c0e  jz      loc_140004EB7
0x140004c14  mov     r14d, 1
0x140004c1a  mov     [rsp+358h+var_2F4], r14d
0x140004c1f  mov     [rsp+358h+lpParam], rcx; lpParam
0x140004c24  mov     [rsp+358h+hInstance], r15; hInstance
0x140004c29  mov     [rsp+358h+hMenu], rcx; hMenu
0x140004c2e  mov     [rsp+358h+hWndParent], rcx; hWndParent
0x140004c33  mov     [rsp+358h+nHeight], ecx; nHeight
0x140004c37  mov     [rsp+358h+nWidth], ecx; nWidth
0x140004c3b  mov     [rsp+358h+Y], ecx; Y
0x140004c3f  mov     [rsp+358h+X], ecx; X
0x140004c43  mov     r9d, 0A0C80000h; dwStyle
0x140004c49  mov     r8, rsi; lpWindowName
0x140004c4c  mov     rdx, r12; lpClassName
0x140004c4f  call    cs:__imp_CreateWindowExW
0x140004c55  test    rax, rax
0x140004c58  jz      loc_140004EEA
0x140004c5e  mov     edx, 6; nCmdShow
0x140004c63  mov     rcx, rax; hWnd
0x140004c66  call    cs:__imp_ShowWindow
0x140004c6c  lea     rdi, WPP_GLOBAL_Control
0x140004c73  mov     rcx, cs:WPP_GLOBAL_Control
0x140004c7a  cmp     rcx, rdi
0x140004c7d  jnz     loc_140004F19
0x140004c83  nop     dword ptr [rax+00h]
0x140004c87  nop     word ptr [rax+rax+00000000h]
0x140004c90  xor     r9d, r9d; wMsgFilterMax
0x140004c93  xor     r8d, r8d; wMsgFilterMin
0x140004c96  xor     edx, edx; hWnd
0x140004c98  lea     rcx, [rsp+358h+Msg]; lpMsg
0x140004ca0  call    cs:__imp_GetMessageW
0x140004ca6  test    eax, eax
0x140004ca8  jz      short loc_140004CD1
0x140004caa  cmp     eax, 0FFFFFFFFh
0x140004cad  jz      loc_140004F3D
0x140004cb3  lea     rcx, [rsp+358h+Msg]; lpMsg
0x140004cbb  call    cs:__imp_TranslateMessage
0x140004cc1  lea     rcx, [rsp+358h+Msg]; lpMsg
0x140004cc9  call    cs:__imp_DispatchMessageW
0x140004ccf  jmp     short loc_140004C90
0x140004cd1  xor     ebx, ebx
0x140004cd3  mov     [rsp+358h+var_2F8], ebx
0x140004cd7  mov     rcx, cs:WPP_GLOBAL_Control
0x140004cde  cmp     rcx, rdi
0x140004ce1  jz      loc_140004F5F
0x140004ce7  test    byte ptr [rcx+1Ch], 4
0x140004ceb  jz      loc_140004F5F
0x140004cf1  mov     edx, 3Dh ; '='
0x140004cf6  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140004cfd  mov     rcx, [rcx+10h]
0x140004d01  call    WPP_SF_
0x140004d06  jmp     loc_140004F5F
0x140004d0b  mov     edx, 7D0h; uID
0x140004d10  call    cs:__imp_LoadStringW
0x140004d16  test    eax, eax
0x140004d18  jz      loc_140004DFF
0x140004d1e  lea     rdx, [rsp+358h+Buffer]
0x140004d26  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140004d2d  mov     rcx, rax
0x140004d30  inc     rcx
0x140004d33  cmp     word ptr [rdx+rcx*2], 0
0x140004d38  jnz     short loc_140004D30
0x140004d3a  nop     word ptr [rax+rax+00h]
0x140004d40  inc     rax
0x140004d43  cmp     word ptr [rdi+rax*2], 0
0x140004d48  jnz     short loc_140004D40
0x140004d4a  inc     eax
0x140004d4c  add     ecx, eax
0x140004d4e  mov     ebx, ecx
0x140004d50  lea     rdx, [rcx+rcx]; uBytes
0x140004d54  mov     ecx, 40h ; '@'; uFlags
0x140004d59  call    cs:__imp_LocalAlloc
0x140004d5f  mov     rsi, rax
0x140004d62  mov     [rsp+358h+var_2F0], rax
0x140004d67  test    rax, rax
0x140004d6a  jnz     loc_140004E33
0x140004d70  mov     ebx, 0Eh
0x140004d75  mov     [rsp+358h+var_2F8], ebx
0x140004d79  lea     rdi, WPP_GLOBAL_Control
0x140004d80  mov     rcx, cs:WPP_GLOBAL_Control
0x140004d87  cmp     rcx, rdi
0x140004d8a  jz      loc_140004F5F
0x140004d90  test    byte ptr [rcx+1Ch], 4
0x140004d94  jz      loc_140004F5F
0x140004d9a  mov     edx, 36h ; '6'
0x140004d9f  mov     r9d, ebx
0x140004da2  jmp     short loc_140004DEA
0x140004da4  call    cs:__imp_GetLastError
0x140004daa  mov     ebx, eax
0x140004dac  mov     [rsp+358h+var_2F8], eax
0x140004db0  lea     rdi, WPP_GLOBAL_Control
0x140004db7  mov     rcx, cs:WPP_GLOBAL_Control
0x140004dbe  cmp     rcx, rdi
0x140004dc1  jz      loc_140004F5F
0x140004dc7  test    byte ptr [rcx+1Ch], 4
0x140004dcb  jz      loc_140004F5F
0x140004dd1  mov     edx, 34h ; '4'
0x140004dd6  jmp     short loc_140004DDD
0x140004dd8  mov     edx, 3Ch ; '<'
0x140004ddd  mov     r9d, eax
0x140004de0  jmp     short loc_140004DEA
0x140004de2  mov     edx, 37h ; '7'
0x140004de7  mov     r9d, ebx
0x140004dea  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140004df1  mov     rcx, [rcx+10h]
0x140004df5  call    WPP_SF_D
0x140004dfa  jmp     loc_140004F5F
0x140004dff  call    cs:__imp_GetLastError
0x140004e05  mov     ebx, eax
0x140004e07  mov     [rsp+358h+var_2F8], eax
0x140004e0b  lea     rdi, WPP_GLOBAL_Control
0x140004e12  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e19  cmp     rcx, rdi
0x140004e1c  jz      loc_140004F5F
0x140004e22  test    byte ptr [rcx+1Ch], 4
0x140004e26  jz      loc_140004F5F
0x140004e2c  mov     edx, 35h ; '5'
0x140004e31  jmp     short loc_140004DDD
0x140004e33  mov     r9, rdi
0x140004e36  lea     r8, [rsp+358h+Buffer]; unsigned __int16 *
0x140004e3e  mov     rdx, rbx; unsigned __int64
0x140004e41  mov     rcx, rax; unsigned __int16 *
0x140004e44  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140004e49  test    eax, eax
0x140004e4b  jz      loc_140004B67
0x140004e51  mov     ebx, 6Fh ; 'o'
0x140004e56  mov     [rsp+358h+var_2F8], ebx
0x140004e5a  lea     rdi, WPP_GLOBAL_Control
0x140004e61  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e68  cmp     rcx, rdi
0x140004e6b  jz      loc_140004F5F
0x140004e71  test    byte ptr [rcx+1Ch], 4
0x140004e75  jz      loc_140004F5F
0x140004e7b  jmp     loc_140004DE2
0x140004e80  call    cs:__imp_GetLastError
0x140004e86  mov     ebx, eax
0x140004e88  mov     [rsp+358h+var_2F8], eax
0x140004e8c  lea     rdi, WPP_GLOBAL_Control
0x140004e93  mov     rcx, cs:WPP_GLOBAL_Control
0x140004e9a  cmp     rcx, rdi
0x140004e9d  jz      loc_140004F5F
0x140004ea3  test    byte ptr [rcx+1Ch], 4
0x140004ea7  jz      loc_140004F5F
0x140004ead  mov     edx, 38h ; '8'
0x140004eb2  jmp     loc_140004DDD
0x140004eb7  call    cs:__imp_GetLastError
0x140004ebd  mov     ebx, eax
0x140004ebf  mov     [rsp+358h+var_2F8], eax
0x140004ec3  lea     rdi, WPP_GLOBAL_Control
0x140004eca  mov     rcx, cs:WPP_GLOBAL_Control
0x140004ed1  cmp     rcx, rdi
0x140004ed4  jz      loc_140004F5F
0x140004eda  test    byte ptr [rcx+1Ch], 4
0x140004ede  jz      short loc_140004F5F
0x140004ee0  mov     edx, 39h ; '9'
0x140004ee5  jmp     loc_140004DDD
0x140004eea  call    cs:__imp_GetLastError
0x140004ef0  mov     ebx, eax
0x140004ef2  mov     [rsp+358h+var_2F8], eax
0x140004ef6  lea     rdi, WPP_GLOBAL_Control
0x140004efd  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f04  cmp     rcx, rdi
0x140004f07  jz      short loc_140004F5F
0x140004f09  test    byte ptr [rcx+1Ch], 4
0x140004f0d  jz      short loc_140004F5F
0x140004f0f  mov     edx, 3Ah ; ':'
0x140004f14  jmp     loc_140004DDD
0x140004f19  test    byte ptr [rcx+1Ch], 4
0x140004f1d  jz      loc_140004C90
0x140004f23  mov     edx, 3Bh ; ';'
0x140004f28  lea     r8, WPP_2ce5143529803a6454f2e220154fca2e_Traceguids
0x140004f2f  mov     rcx, [rcx+10h]
0x140004f33  call    WPP_SF_
0x140004f38  jmp     loc_140004C90
0x140004f3d  call    cs:__imp_GetLastError
0x140004f43  mov     ebx, eax
0x140004f45  mov     [rsp+358h+var_2F8], eax
0x140004f49  mov     rcx, cs:WPP_GLOBAL_Control
0x140004f50  cmp     rcx, rdi
0x140004f53  jz      short loc_140004F5F
0x140004f55  test    byte ptr [rcx+1Ch], 4
0x140004f59  jnz     loc_140004DD8
0x140004f5f  test    r14d, r14d
0x140004f62  jnz     short loc_140004F8C
0x140004f64  test    rsi, rsi
0x140004f67  jnz     short loc_140004F9A
0x140004f69  mov     eax, ebx
0x140004f6b  mov     rcx, [rsp+358h+var_48]
0x140004f73  xor     rcx, rsp; StackCookie
0x140004f76  call    __security_check_cookie
0x140004f7b  add     rsp, 328h
0x140004f82  pop     r15
0x140004f84  pop     r14
0x140004f86  pop     r12
0x140004f88  pop     rdi
0x140004f89  pop     rsi
0x140004f8a  pop     rbx
0x140004f8b  retn
0x140004f8c  mov     rdx, r15; hInstance
0x140004f8f  mov     rcx, r12; lpClassName
0x140004f92  call    cs:__imp_UnregisterClassW
0x140004f98  jmp     short loc_140004F64
0x140004f9a  lea     rax, [rsp+358h+Buffer]
0x140004fa2  cmp     rsi, rax
0x140004fa5  jz      short loc_140004F69
0x140004fa7  mov     rcx, rsi; hMem
0x140004faa  call    cs:__imp_LocalFree
0x140004fb0  jmp     short loc_140004F69
0x14001e170  push    rbp
0x14001e172  sub     rsp, 60h
0x14001e176  mov     rbp, rdx
0x14001e179  cmp     dword ptr [rbp+64h], 0
0x14001e17d  jz      short loc_14001E18E
0x14001e17f  mov     rdx, [rbp+70h]; hInstance
0x14001e183  mov     rcx, [rbp+78h]; lpClassName
0x14001e187  call    cs:__imp_UnregisterClassW
0x14001e18d  nop
0x14001e18e  mov     rcx, [rbp+68h]; hMem
0x14001e192  test    rcx, rcx
0x14001e195  jz      short loc_14001E1AA
0x14001e197  lea     rax, [rbp+100h]
0x14001e19e  cmp     rcx, rax
0x14001e1a1  jz      short loc_14001E1AA
0x14001e1a3  call    cs:__imp_LocalFree
0x14001e1a9  nop
0x14001e1aa  add     rsp, 60h
0x14001e1ae  pop     rbp
0x14001e1af  retn
```
