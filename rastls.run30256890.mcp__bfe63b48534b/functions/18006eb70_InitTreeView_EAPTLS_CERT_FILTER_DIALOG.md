# InitTreeView(_EAPTLS_CERT_FILTER_DIALOG *)

- ea: `0x18006eb70`
- end: `0x18006eedb`
- name: `?InitTreeView@@YAXPEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z`
- size: `875`
- prototype: `void __fastcall(struct _EAPTLS_CERT_FILTER_DIALOG *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180069b5c`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180038270`
- `0x180069950`
- `0x18006eb70`
- `0x180082010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006eba9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006eba9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ec0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ec0b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006eea6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006eea6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006ed92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006edfa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006ed92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006edfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ebd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ec33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ebd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ec33`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006ed6f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006ee5e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006ee7a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006ee97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006ed6f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006ee5e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006ee7a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006ee97`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18006ec6f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18006ec6f`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18006ed3c`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18006ed3c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18006ed24`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18006ed24`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_Create` at `0x18006eca5`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_Create` at `0x18006eca5`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_ReplaceIcon` at `0x18006ed51`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_ReplaceIcon` at `0x18006ed51`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_AddMasked` at `0x18006ed15`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_AddMasked` at `0x18006ed15`

## string_xrefs

- `0x18006eb9c`: `comctl32.dll`
- `0x18006ec01`: `CreateMappedBitmap`

## pseudocode

```c
void __fastcall InitTreeView(struct _EAPTLS_CERT_FILTER_DIALOG *a1)
{
  HMODULE Library; // rax
  HMODULE v3; // rsi
  DWORD v4; // eax
  FARPROC ProcAddress; // rbx
  DWORD LastError; // eax
  LONG WindowLongW; // eax
  struct _IMAGELIST *v8; // rbp
  HINSTANCE v9; // rcx
  HBITMAP v10; // rbx
  HICON IconW; // rax
  HWND i; // rbx
  unsigned __int16 *v13; // rcx
  struct _EAPTLS_CERT_NODE *j; // rbx
  unsigned __int16 *v15; // rcx
  WCHAR Buffer[512]; // [rsp+30h] [rbp-428h] BYREF

  Library = LoadLibraryExW(L"comctl32.dll", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "CreateMappedBitmap");
    if ( ProcAddress )
    {
      WindowLongW = GetWindowLongW(*((HWND *)a1 + 26), -20);
      v8 = ImageList_Create(16, 16, (WindowLongW & 0x400000) != 0 ? 40993 : 33, 5, 1);
      if ( !v8 && WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids);
      v9 = g_hInstance;
      *((_QWORD *)a1 + 6) = v8;
      v10 = (HBITMAP)((__int64 (__fastcall *)(HINSTANCE, __int64, _QWORD))ProcAddress)(v9, 119, 0);
      ImageList_AddMasked(v8, v10, 0xFF000000);
      DeleteObject(v10);
      IconW = LoadIconW(g_hInstance, (LPCWSTR)0x73);
      ImageList_ReplaceIcon(v8, -1, IconW);
      SendMessageW(*((HWND *)a1 + 26), 0x1109u, 0, (LPARAM)v8);
      LoadStringW(g_hInstance, 0x4C1u, Buffer, 512);
      AddItemToTree(Buffer, 0, a1, 1, 1);
      for ( i = *(HWND *)a1; i; i = *(HWND *)i )
      {
        v13 = (unsigned __int16 *)*((_QWORD *)i + 4);
        if ( v13 )
          AddItemToTree(v13, (struct _EAPTLS_CERT_NODE *)i, a1, 2, 1);
      }
      LoadStringW(g_hInstance, 0x4C2u, Buffer, 512);
      AddItemToTree(Buffer, 0, a1, 1, 0);
      for ( j = (struct _EAPTLS_CERT_NODE *)*((_QWORD *)a1 + 1); j; j = *(struct _EAPTLS_CERT_NODE **)j )
      {
        v15 = (unsigned __int16 *)*((_QWORD *)j + 4);
        if ( v15 )
          AddItemToTree(v15, j, a1, 2, 0);
      }
      SendMessageW(*((HWND *)a1 + 26), 0x1102u, 2u, *((_QWORD *)a1 + 4));
      SendMessageW(*((HWND *)a1 + 26), 0x1102u, 2u, *((_QWORD *)a1 + 5));
      SendMessageW(*((HWND *)a1 + 26), 0x1114u, 0, *((_QWORD *)a1 + 4));
    }
    else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 197, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, LastError);
    }
    FreeLibrary(v3);
  }
  else if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
  {
    v4 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, v4);
  }
}

```

## disassembly

```asm
0x18006eb70  mov     [rsp+arg_8], rbx
0x18006eb75  mov     [rsp+arg_10], rbp
0x18006eb7a  push    rsi
0x18006eb7b  push    rdi
0x18006eb7c  push    r15
0x18006eb7e  sub     rsp, 440h
0x18006eb85  mov     rax, cs:__security_cookie
0x18006eb8c  xor     rax, rsp
0x18006eb8f  mov     [rsp+458h+var_28], rax
0x18006eb97  mov     rdi, rcx
0x18006eb9a  xor     edx, edx; hFile
0x18006eb9c  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18006eba3  mov     r8d, 800h; dwFlags
0x18006eba9  call    cs:__imp_LoadLibraryExW
0x18006ebb0  nop     dword ptr [rax+rax+00h]
0x18006ebb5  mov     rsi, rax
0x18006ebb8  test    rax, rax
0x18006ebbb  jnz     short loc_18006EC01
0x18006ebbd  lea     rax, WPP_GLOBAL_Control
0x18006ebc4  cmp     cs:WPP_GLOBAL_Control, rax
0x18006ebcb  jz      loc_18006EEB2
0x18006ebd1  call    cs:__imp_GetLastError
0x18006ebd8  nop     dword ptr [rax+rax+00h]
0x18006ebdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ebe4  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006ebeb  mov     edx, 0C4h
0x18006ebf0  mov     r9d, eax
0x18006ebf3  mov     rcx, [rcx+10h]
0x18006ebf7  call    WPP_SF_d
0x18006ebfc  jmp     loc_18006EEB2
0x18006ec01  lea     rdx, aCreatemappedbi; "CreateMappedBitmap"
0x18006ec08  mov     rcx, rsi; hModule
0x18006ec0b  call    cs:__imp_GetProcAddress
0x18006ec12  nop     dword ptr [rax+rax+00h]
0x18006ec17  mov     rbx, rax
0x18006ec1a  test    rax, rax
0x18006ec1d  jnz     short loc_18006EC63
0x18006ec1f  lea     rax, WPP_GLOBAL_Control
0x18006ec26  cmp     cs:WPP_GLOBAL_Control, rax
0x18006ec2d  jz      loc_18006EEA3
0x18006ec33  call    cs:__imp_GetLastError
0x18006ec3a  nop     dword ptr [rax+rax+00h]
0x18006ec3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ec46  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006ec4d  mov     edx, 0C5h
0x18006ec52  mov     r9d, eax
0x18006ec55  mov     rcx, [rcx+10h]
0x18006ec59  call    WPP_SF_d
0x18006ec5e  jmp     loc_18006EEA3
0x18006ec63  mov     rcx, [rdi+0D0h]; hWnd
0x18006ec6a  mov     edx, 0FFFFFFECh; nIndex
0x18006ec6f  call    cs:__imp_GetWindowLongW
0x18006ec76  nop     dword ptr [rax+rax+00h]
0x18006ec7b  mov     r15d, 1
0x18006ec81  and     eax, 400000h
0x18006ec86  neg     eax
0x18006ec88  mov     [rsp+458h+cGrow], r15d; cGrow
0x18006ec8d  sbb     r8d, r8d
0x18006ec90  and     r8d, 0A000h
0x18006ec97  lea     ecx, [r15+0Fh]; cx
0x18006ec9b  add     r8d, 21h ; '!'; flags
0x18006ec9f  lea     r9d, [r15+4]; cInitial
0x18006eca3  mov     edx, ecx; cy
0x18006eca5  call    cs:__imp_ImageList_Create
0x18006ecac  nop     dword ptr [rax+rax+00h]
0x18006ecb1  mov     rbp, rax
0x18006ecb4  test    rax, rax
0x18006ecb7  jnz     short loc_18006ECE1
0x18006ecb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ecc0  lea     rax, WPP_GLOBAL_Control
0x18006ecc7  cmp     rcx, rax
0x18006ecca  jz      short loc_18006ECE1
0x18006eccc  mov     rcx, [rcx+10h]
0x18006ecd0  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006ecd7  mov     edx, 0C6h
0x18006ecdc  call    WPP_SF_
0x18006ece1  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18006ece8  xor     r9d, r9d
0x18006eceb  xor     r8d, r8d
0x18006ecee  mov     [rdi+30h], rbp
0x18006ecf2  mov     rax, rbx
0x18006ecf5  mov     [rsp+458h+cGrow], 0
0x18006ecfd  lea     edx, [r9+77h]
0x18006ed01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006ed06  mov     r8d, 0FF000000h; crMask
0x18006ed0c  mov     rdx, rax; hbmImage
0x18006ed0f  mov     rcx, rbp; himl
0x18006ed12  mov     rbx, rax
0x18006ed15  call    cs:__imp_ImageList_AddMasked
0x18006ed1c  nop     dword ptr [rax+rax+00h]
0x18006ed21  mov     rcx, rbx; ho
0x18006ed24  call    cs:__imp_DeleteObject
0x18006ed2b  nop     dword ptr [rax+rax+00h]
0x18006ed30  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006ed37  mov     edx, 73h ; 's'; lpIconName
0x18006ed3c  call    cs:__imp_LoadIconW
0x18006ed43  nop     dword ptr [rax+rax+00h]
0x18006ed48  or      edx, 0FFFFFFFFh; i
0x18006ed4b  mov     rcx, rbp; himl
0x18006ed4e  mov     r8, rax; hicon
0x18006ed51  call    cs:__imp_ImageList_ReplaceIcon
0x18006ed58  nop     dword ptr [rax+rax+00h]
0x18006ed5d  mov     rcx, [rdi+0D0h]; hWnd
0x18006ed64  mov     r9, rbp; lParam
0x18006ed67  xor     r8d, r8d; wParam
0x18006ed6a  mov     edx, 1109h; Msg
0x18006ed6f  call    cs:__imp_SendMessageW
0x18006ed76  nop     dword ptr [rax+rax+00h]
0x18006ed7b  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006ed82  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x18006ed87  mov     r9d, 200h; cchBufferMax
0x18006ed8d  mov     edx, 4C1h; uID
0x18006ed92  call    cs:__imp_LoadStringW
0x18006ed99  nop     dword ptr [rax+rax+00h]
0x18006ed9e  mov     r9d, r15d; int
0x18006eda1  mov     [rsp+458h+cGrow], r15d; int
0x18006eda6  mov     r8, rdi; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006eda9  lea     rcx, [rsp+458h+Buffer]; unsigned __int16 *
0x18006edae  xor     edx, edx; struct _EAPTLS_CERT_NODE *
0x18006edb0  call    ?AddItemToTree@@YAHPEAGPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@HH@Z; AddItemToTree(ushort *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_FILTER_DIALOG *,int,int)
0x18006edb5  mov     rbx, [rdi]
0x18006edb8  mov     ebp, 2
0x18006edbd  jmp     short loc_18006EDDE
0x18006edbf  mov     rcx, [rbx+20h]; unsigned __int16 *
0x18006edc3  test    rcx, rcx
0x18006edc6  jz      short loc_18006EDDB
0x18006edc8  mov     r9d, ebp; int
0x18006edcb  mov     [rsp+458h+cGrow], r15d; int
0x18006edd0  mov     r8, rdi; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006edd3  mov     rdx, rbx; struct _EAPTLS_CERT_NODE *
0x18006edd6  call    ?AddItemToTree@@YAHPEAGPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@HH@Z; AddItemToTree(ushort *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_FILTER_DIALOG *,int,int)
0x18006eddb  mov     rbx, [rbx]
0x18006edde  test    rbx, rbx
0x18006ede1  jnz     short loc_18006EDBF
0x18006ede3  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006edea  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x18006edef  mov     r9d, 200h; cchBufferMax
0x18006edf5  mov     edx, 4C2h; uID
0x18006edfa  call    cs:__imp_LoadStringW
0x18006ee01  nop     dword ptr [rax+rax+00h]
0x18006ee06  mov     r9d, r15d; int
0x18006ee09  mov     [rsp+458h+cGrow], ebx; int
0x18006ee0d  mov     r8, rdi; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006ee10  lea     rcx, [rsp+458h+Buffer]; unsigned __int16 *
0x18006ee15  xor     edx, edx; struct _EAPTLS_CERT_NODE *
0x18006ee17  call    ?AddItemToTree@@YAHPEAGPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@HH@Z; AddItemToTree(ushort *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_FILTER_DIALOG *,int,int)
0x18006ee1c  mov     rbx, [rdi+8]
0x18006ee20  jmp     short loc_18006EE44
0x18006ee22  mov     rcx, [rbx+20h]; unsigned __int16 *
0x18006ee26  test    rcx, rcx
0x18006ee29  jz      short loc_18006EE41
0x18006ee2b  mov     r9d, ebp; int
0x18006ee2e  mov     [rsp+458h+cGrow], 0; int
0x18006ee36  mov     r8, rdi; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006ee39  mov     rdx, rbx; struct _EAPTLS_CERT_NODE *
0x18006ee3c  call    ?AddItemToTree@@YAHPEAGPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@HH@Z; AddItemToTree(ushort *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_FILTER_DIALOG *,int,int)
0x18006ee41  mov     rbx, [rbx]
0x18006ee44  test    rbx, rbx
0x18006ee47  jnz     short loc_18006EE22
0x18006ee49  mov     r9, [rdi+20h]; lParam
0x18006ee4d  mov     ebx, 1102h
0x18006ee52  mov     rcx, [rdi+0D0h]; hWnd
0x18006ee59  mov     edx, ebx; Msg
0x18006ee5b  mov     r8, rbp; wParam
0x18006ee5e  call    cs:__imp_SendMessageW
0x18006ee65  nop     dword ptr [rax+rax+00h]
0x18006ee6a  mov     r9, [rdi+28h]; lParam
0x18006ee6e  mov     r8, rbp; wParam
0x18006ee71  mov     rcx, [rdi+0D0h]; hWnd
0x18006ee78  mov     edx, ebx; Msg
0x18006ee7a  call    cs:__imp_SendMessageW
0x18006ee81  nop     dword ptr [rax+rax+00h]
0x18006ee86  mov     r9, [rdi+20h]; lParam
0x18006ee8a  lea     edx, [rbx+12h]; Msg
0x18006ee8d  mov     rcx, [rdi+0D0h]; hWnd
0x18006ee94  xor     r8d, r8d; wParam
0x18006ee97  call    cs:__imp_SendMessageW
0x18006ee9e  nop     dword ptr [rax+rax+00h]
0x18006eea3  mov     rcx, rsi; hLibModule
0x18006eea6  call    cs:__imp_FreeLibrary
0x18006eead  nop     dword ptr [rax+rax+00h]
0x18006eeb2  mov     rcx, [rsp+458h+var_28]
0x18006eeba  xor     rcx, rsp; StackCookie
0x18006eebd  call    __security_check_cookie
0x18006eec2  lea     r11, [rsp+458h+var_18]
0x18006eeca  mov     rbx, [r11+28h]
0x18006eece  mov     rbp, [r11+30h]
0x18006eed2  mov     rsp, r11
0x18006eed5  pop     r15
0x18006eed7  pop     rdi
0x18006eed8  pop     rsi
0x18006eed9  retn
```
