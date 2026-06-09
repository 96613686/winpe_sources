# InitTreeView(_EAPTLS_CERT_FILTER_DIALOG *)

- ea: `0x18006a6a0`
- end: `0x18006a9a4`
- name: `?InitTreeView@@YAXPEAU_EAPTLS_CERT_FILTER_DIALOG@@@Z`
- size: `772`
- prototype: `void __fastcall(struct _EAPTLS_CERT_FILTER_DIALOG *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180065eb4`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x180035680`
- `0x180065cb0`
- `0x18006a6a0`
- `0x18007c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006a6d9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18006a6d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a72f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006a72f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a976`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18006a976`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006a880`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006a8e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006a880`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18006a8e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a6fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a751`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006a863`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006a940`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006a956`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006a96d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006a863`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006a940`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006a956`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x18006a96d`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18006a787`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowLongW` at `0x18006a787`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18006a83c`
- `ext-ms-win-ntuser-gui-l1-1-0!LoadIconW` at `0x18006a83c`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18006a82a`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x18006a82a`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_Create` at `0x18006a7b7`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_Create` at `0x18006a7b7`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_ReplaceIcon` at `0x18006a84b`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_ReplaceIcon` at `0x18006a84b`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_AddMasked` at `0x18006a821`
- `ext-ms-win-shell-comctl32-init-l1-1-1!ImageList_AddMasked` at `0x18006a821`

## string_xrefs

- `0x18006a6cc`: `comctl32.dll`
- `0x18006a725`: `CreateMappedBitmap`

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
0x18006a6a0  mov     [rsp+arg_8], rbx
0x18006a6a5  mov     [rsp+arg_10], rbp
0x18006a6aa  push    rsi
0x18006a6ab  push    rdi
0x18006a6ac  push    r15
0x18006a6ae  sub     rsp, 440h
0x18006a6b5  mov     rax, cs:__security_cookie
0x18006a6bc  xor     rax, rsp
0x18006a6bf  mov     [rsp+458h+var_28], rax
0x18006a6c7  mov     rdi, rcx
0x18006a6ca  xor     edx, edx; hFile
0x18006a6cc  lea     rcx, aComctl32Dll; "comctl32.dll"
0x18006a6d3  mov     r8d, 800h; dwFlags
0x18006a6d9  call    cs:__imp_LoadLibraryExW
0x18006a6df  mov     rsi, rax
0x18006a6e2  test    rax, rax
0x18006a6e5  jnz     short loc_18006A725
0x18006a6e7  lea     rax, WPP_GLOBAL_Control
0x18006a6ee  cmp     cs:WPP_GLOBAL_Control, rax
0x18006a6f5  jz      loc_18006A97C
0x18006a6fb  call    cs:__imp_GetLastError
0x18006a701  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a708  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006a70f  mov     edx, 0C4h
0x18006a714  mov     r9d, eax
0x18006a717  mov     rcx, [rcx+10h]
0x18006a71b  call    WPP_SF_d
0x18006a720  jmp     loc_18006A97C
0x18006a725  lea     rdx, aCreatemappedbi; "CreateMappedBitmap"
0x18006a72c  mov     rcx, rsi; hModule
0x18006a72f  call    cs:__imp_GetProcAddress
0x18006a735  mov     rbx, rax
0x18006a738  test    rax, rax
0x18006a73b  jnz     short loc_18006A77B
0x18006a73d  lea     rax, WPP_GLOBAL_Control
0x18006a744  cmp     cs:WPP_GLOBAL_Control, rax
0x18006a74b  jz      loc_18006A973
0x18006a751  call    cs:__imp_GetLastError
0x18006a757  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a75e  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006a765  mov     edx, 0C5h
0x18006a76a  mov     r9d, eax
0x18006a76d  mov     rcx, [rcx+10h]
0x18006a771  call    WPP_SF_d
0x18006a776  jmp     loc_18006A973
0x18006a77b  mov     rcx, [rdi+0D0h]; hWnd
0x18006a782  mov     edx, 0FFFFFFECh; nIndex
0x18006a787  call    cs:__imp_GetWindowLongW
0x18006a78d  mov     r15d, 1
0x18006a793  and     eax, 400000h
0x18006a798  neg     eax
0x18006a79a  mov     [rsp+458h+cGrow], r15d; cGrow
0x18006a79f  sbb     r8d, r8d
0x18006a7a2  and     r8d, 0A000h
0x18006a7a9  lea     ecx, [r15+0Fh]; cx
0x18006a7ad  add     r8d, 21h ; '!'; flags
0x18006a7b1  lea     r9d, [r15+4]; cInitial
0x18006a7b5  mov     edx, ecx; cy
0x18006a7b7  call    cs:__imp_ImageList_Create
0x18006a7bd  mov     rbp, rax
0x18006a7c0  test    rax, rax
0x18006a7c3  jnz     short loc_18006A7ED
0x18006a7c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a7cc  lea     rax, WPP_GLOBAL_Control
0x18006a7d3  cmp     rcx, rax
0x18006a7d6  jz      short loc_18006A7ED
0x18006a7d8  mov     rcx, [rcx+10h]
0x18006a7dc  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006a7e3  mov     edx, 0C6h
0x18006a7e8  call    WPP_SF_
0x18006a7ed  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18006a7f4  xor     r9d, r9d
0x18006a7f7  xor     r8d, r8d
0x18006a7fa  mov     [rdi+30h], rbp
0x18006a7fe  mov     rax, rbx
0x18006a801  mov     [rsp+458h+cGrow], 0
0x18006a809  lea     edx, [r9+77h]
0x18006a80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006a812  mov     r8d, 0FF000000h; crMask
0x18006a818  mov     rdx, rax; hbmImage
0x18006a81b  mov     rcx, rbp; himl
0x18006a81e  mov     rbx, rax
0x18006a821  call    cs:__imp_ImageList_AddMasked
0x18006a827  mov     rcx, rbx; ho
0x18006a82a  call    cs:__imp_DeleteObject
0x18006a830  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006a837  mov     edx, 73h ; 's'; lpIconName
0x18006a83c  call    cs:__imp_LoadIconW
0x18006a842  or      edx, 0FFFFFFFFh; i
0x18006a845  mov     rcx, rbp; himl
0x18006a848  mov     r8, rax; hicon
0x18006a84b  call    cs:__imp_ImageList_ReplaceIcon
0x18006a851  mov     rcx, [rdi+0D0h]; hWnd
0x18006a858  mov     r9, rbp; lParam
0x18006a85b  xor     r8d, r8d; wParam
0x18006a85e  mov     edx, 1109h; Msg
0x18006a863  call    cs:__imp_SendMessageW
0x18006a869  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006a870  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x18006a875  mov     r9d, 200h; cchBufferMax
0x18006a87b  mov     edx, 4C1h; uID
0x18006a880  call    cs:__imp_LoadStringW
0x18006a886  mov     r9d, r15d; int
0x18006a889  mov     [rsp+458h+cGrow], r15d; int
0x18006a88e  mov     r8, rdi; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006a891  lea     rcx, [rsp+458h+Buffer]; unsigned __int16 *
0x18006a896  xor     edx, edx; struct _EAPTLS_CERT_NODE *
0x18006a898  call    ?AddItemToTree@@YAHPEAGPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@HH@Z; AddItemToTree(ushort *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_FILTER_DIALOG *,int,int)
0x18006a89d  mov     rbx, [rdi]
0x18006a8a0  mov     ebp, 2
0x18006a8a5  jmp     short loc_18006A8C6
0x18006a8a7  mov     rcx, [rbx+20h]; unsigned __int16 *
0x18006a8ab  test    rcx, rcx
0x18006a8ae  jz      short loc_18006A8C3
0x18006a8b0  mov     r9d, ebp; int
0x18006a8b3  mov     [rsp+458h+cGrow], r15d; int
0x18006a8b8  mov     r8, rdi; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006a8bb  mov     rdx, rbx; struct _EAPTLS_CERT_NODE *
0x18006a8be  call    ?AddItemToTree@@YAHPEAGPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@HH@Z; AddItemToTree(ushort *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_FILTER_DIALOG *,int,int)
0x18006a8c3  mov     rbx, [rbx]
0x18006a8c6  test    rbx, rbx
0x18006a8c9  jnz     short loc_18006A8A7
0x18006a8cb  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18006a8d2  lea     r8, [rsp+458h+Buffer]; lpBuffer
0x18006a8d7  mov     r9d, 200h; cchBufferMax
0x18006a8dd  mov     edx, 4C2h; uID
0x18006a8e2  call    cs:__imp_LoadStringW
0x18006a8e8  mov     r9d, r15d; int
0x18006a8eb  mov     [rsp+458h+cGrow], ebx; int
0x18006a8ef  mov     r8, rdi; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006a8f2  lea     rcx, [rsp+458h+Buffer]; unsigned __int16 *
0x18006a8f7  xor     edx, edx; struct _EAPTLS_CERT_NODE *
0x18006a8f9  call    ?AddItemToTree@@YAHPEAGPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@HH@Z; AddItemToTree(ushort *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_FILTER_DIALOG *,int,int)
0x18006a8fe  mov     rbx, [rdi+8]
0x18006a902  jmp     short loc_18006A926
0x18006a904  mov     rcx, [rbx+20h]; unsigned __int16 *
0x18006a908  test    rcx, rcx
0x18006a90b  jz      short loc_18006A923
0x18006a90d  mov     r9d, ebp; int
0x18006a910  mov     [rsp+458h+cGrow], 0; int
0x18006a918  mov     r8, rdi; struct _EAPTLS_CERT_FILTER_DIALOG *
0x18006a91b  mov     rdx, rbx; struct _EAPTLS_CERT_NODE *
0x18006a91e  call    ?AddItemToTree@@YAHPEAGPEAU_EAPTLS_CERT_NODE@@PEAU_EAPTLS_CERT_FILTER_DIALOG@@HH@Z; AddItemToTree(ushort *,_EAPTLS_CERT_NODE *,_EAPTLS_CERT_FILTER_DIALOG *,int,int)
0x18006a923  mov     rbx, [rbx]
0x18006a926  test    rbx, rbx
0x18006a929  jnz     short loc_18006A904
0x18006a92b  mov     r9, [rdi+20h]; lParam
0x18006a92f  mov     ebx, 1102h
0x18006a934  mov     rcx, [rdi+0D0h]; hWnd
0x18006a93b  mov     edx, ebx; Msg
0x18006a93d  mov     r8, rbp; wParam
0x18006a940  call    cs:__imp_SendMessageW
0x18006a946  mov     r9, [rdi+28h]; lParam
0x18006a94a  mov     r8, rbp; wParam
0x18006a94d  mov     rcx, [rdi+0D0h]; hWnd
0x18006a954  mov     edx, ebx; Msg
0x18006a956  call    cs:__imp_SendMessageW
0x18006a95c  mov     r9, [rdi+20h]; lParam
0x18006a960  lea     edx, [rbx+12h]; Msg
0x18006a963  mov     rcx, [rdi+0D0h]; hWnd
0x18006a96a  xor     r8d, r8d; wParam
0x18006a96d  call    cs:__imp_SendMessageW
0x18006a973  mov     rcx, rsi; hLibModule
0x18006a976  call    cs:__imp_FreeLibrary
0x18006a97c  mov     rcx, [rsp+458h+var_28]
0x18006a984  xor     rcx, rsp; StackCookie
0x18006a987  call    __security_check_cookie
0x18006a98c  lea     r11, [rsp+458h+var_18]
0x18006a994  mov     rbx, [r11+28h]
0x18006a998  mov     rbp, [r11+30h]
0x18006a99c  mov     rsp, r11
0x18006a99f  pop     r15
0x18006a9a1  pop     rdi
0x18006a9a2  pop     rsi
0x18006a9a3  retn
```
