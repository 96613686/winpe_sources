# acmdDlgProcConfigure

- ea: `0x180004300`
- end: `0x1800046fa`
- name: `acmdDlgProcConfigure`
- size: `1018`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001400`
- `0x18000426c`
- `0x180004300`
- `0x18000494c`
- `0x180004ec4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004431`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000444f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004567`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004431`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000444f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180004567`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x180004474`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x180004474`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800043df`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180004405`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000448e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800044c0`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000452c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000453d`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800043df`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180004405`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000448e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800044c0`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000452c`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x18000453d`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x1800044f6`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x1800044f6`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800043f7`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800044a6`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800044d2`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180004624`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000463a`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180004663`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180004676`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800043f7`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800044a6`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x1800044d2`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180004624`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000463a`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180004663`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180004676`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x1800043b4`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x180004699`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x1800046c8`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x1800043b4`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x180004699`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x1800046c8`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x18000450d`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x18000450d`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x180004371`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x1800046ab`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x180004371`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x1800046ab`

## pseudocode

```c
INT_PTR __fastcall acmdDlgProcConfigure(HWND a1, int a2, int a3, LONG_PTR a4)
{
  int v7; // edx
  int v8; // edx
  int v9; // edx
  LONG_PTR WindowLongPtrW; // rax
  __int64 v11; // r14
  int v12; // esi
  int v13; // esi
  int v14; // esi
  UINT v15; // esi
  HWND v16; // rax
  HWND v17; // rax
  WPARAM v18; // r8
  HWND v19; // rcx
  INT_PTR v20; // rdx
  int v21; // esi
  HWND v22; // rax
  int v23; // eax
  HWND v24; // rax
  int v25; // eax
  int v26; // r13d
  HWND DlgItem; // r15
  __int64 v28; // rsi
  HWND v29; // r12
  __int64 v30; // rbx
  __int64 v31; // r9
  __int64 v32; // rcx
  WCHAR *v33; // r8
  __int64 v34; // rdx
  wchar_t *v35; // rax
  wchar_t *v36; // rcx
  int v38; // [rsp+30h] [rbp-D0h] BYREF
  _DWORD v39[3]; // [rsp+34h] [rbp-CCh] BYREF
  wchar_t pszDest[80]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszFormat[80]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Buffer[200]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR Text[200]; // [rsp+310h] [rbp+210h] BYREF

  v38 = 0;
  v39[0] = 0;
  v7 = a2 - 2;
  if ( !v7 )
  {
    if ( *(_DWORD *)(GetWindowLongPtrW(a1, 16) + 68) )
      WinHelpW(a1, L"audiocdc.hlp", 2u, 0);
    return 0;
  }
  v8 = v7 - 81;
  if ( !v8 )
  {
    WinHelpW(*(HWND *)(a4 + 16), L"audiocdc.hlp", 0xCu, (ULONG_PTR)&dwData);
    return 1;
  }
  v9 = v8 - 189;
  if ( !v9 )
  {
    *(_DWORD *)(a4 + 68) = 0;
    SetWindowLongPtrW(a1, 16, a4);
    v26 = *(_DWORD *)(a4 + 56);
    v38 = *(_DWORD *)(a4 + 60);
    v39[0] = v26;
    DlgItem = GetDlgItem(a1, 1003);
    v28 = 0;
    v29 = GetDlgItem(a1, 1004);
    v30 = 0;
    while ( 1 )
    {
      LoadStringW(*(HINSTANCE *)(a4 + 20), *(_DWORD *)((char *)gaRateListFormat + v30 + 4), pszFormat, 80);
      if ( *(_DWORD *)((char *)gaRateListFormat + v30) == 1 )
      {
        v32 = 2147483646;
        v33 = pszFormat;
        v34 = 80;
        v35 = pszDest;
        do
        {
          if ( !v32 )
            break;
          if ( !*v33 )
            break;
          *v35++ = *v33++;
          --v32;
          --v34;
        }
        while ( v34 );
        v36 = v35 - 1;
        if ( v34 )
          v36 = v35;
        *v36 = 0;
        goto LABEL_40;
      }
      if ( *(_DWORD *)((char *)gaRateListFormat + v30) == 2 )
      {
        v31 = *(unsigned int *)((char *)&gaRateListFormat[1] + v30);
      }
      else
      {
        if ( *(_DWORD *)((char *)gaRateListFormat + v30) != 3 )
        {
          if ( *(_DWORD *)((char *)gaRateListFormat + v30) == 4 )
            StringCchPrintfW(pszDest, 0x50u, pszFormat);
          goto LABEL_40;
        }
        v31 = *(_DWORD *)((char *)&gaRateListFormat[1] + v30) >> 1;
      }
      StringCchPrintfW(pszDest, 0x50u, pszFormat, v31);
LABEL_40:
      SendMessageW(DlgItem, 0x143u, 0, (LPARAM)pszDest);
      SendMessageW(v29, 0x143u, 0, (LPARAM)pszDest);
      ++v28;
      v30 += 12;
      if ( v28 == 7 )
      {
        SendMessageW(DlgItem, 0x14Eu, v39[0], 0);
        v18 = v38;
        v19 = v29;
LABEL_42:
        SendMessageW(v19, 0x14Eu, v18, 0);
        return 1;
      }
    }
  }
  if ( v9 != 1 )
    return 0;
  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  v11 = WindowLongPtrW;
  v12 = a3 - 1;
  if ( !v12 )
  {
    v21 = 0;
    v22 = GetDlgItem(a1, 1003);
    v23 = SendMessageW(v22, 0x147u, 0, 0);
    if ( v23 != *(_DWORD *)(v11 + 56) )
    {
      *(_DWORD *)(v11 + 56) = v23;
      v21 = 1;
    }
    v24 = GetDlgItem(a1, 1004);
    v25 = SendMessageW(v24, 0x147u, 0, 0);
    if ( v25 == *(_DWORD *)(v11 + 60) )
    {
      if ( v21 != 1 )
      {
LABEL_22:
        v20 = 1;
        goto LABEL_23;
      }
    }
    else
    {
      *(_DWORD *)(v11 + 60) = v25;
    }
    configWriteConfiguration(v11);
    goto LABEL_22;
  }
  v13 = v12 - 1;
  if ( !v13 )
  {
    v20 = 0;
LABEL_23:
    EndDialog(a1, v20);
    return 1;
  }
  v14 = v13 - 999;
  if ( v14 )
  {
    if ( v14 == 1 )
    {
      *(_DWORD *)(WindowLongPtrW + 68) = 1;
      WinHelpW(a1, L"audiocdc.hlp", 1u, 0x3E9u);
    }
  }
  else
  {
    v15 = configAutoConfig(WindowLongPtrW, &v38, v39);
    if ( !v15 )
    {
      v16 = GetDlgItem(a1, 1003);
      SendMessageW(v16, 0x14Eu, v38, 0);
      v17 = GetDlgItem(a1, 1004);
      v18 = v39[0];
      v19 = v17;
      goto LABEL_42;
    }
    if ( LoadStringW(*(HINSTANCE *)(v11 + 20), 0x23u, Buffer, 200)
      && LoadStringW(*(HINSTANCE *)(v11 + 20), v15, Text, 200) )
    {
      MessageBoxW(a1, Text, Buffer, 0x30u);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180004300  mov     [rsp-8+arg_8], rbx
0x180004305  push    rbp
0x180004306  push    rsi
0x180004307  push    rdi
0x180004308  push    r12
0x18000430a  push    r13
0x18000430c  push    r14
0x18000430e  push    r15
0x180004310  lea     rbp, [rsp-3B0h]
0x180004318  sub     rsp, 4B0h
0x18000431f  mov     rax, cs:__security_cookie
0x180004326  xor     rax, rsp
0x180004329  mov     [rbp+3E0h+var_40], rax
0x180004330  xor     r15d, r15d
0x180004333  mov     r14, r9
0x180004336  mov     [rsp+4E0h+var_4B0], r15d
0x18000433b  mov     rsi, r8
0x18000433e  mov     [rsp+4E0h+var_4AC], r15d
0x180004343  mov     rbx, rcx
0x180004346  sub     edx, 2
0x180004349  jz      loc_1800046A6
0x18000434f  sub     edx, 51h ; 'Q'
0x180004352  jz      loc_180004681
0x180004358  sub     edx, 0BDh
0x18000435e  jz      loc_180004501
0x180004364  cmp     edx, 1
0x180004367  jnz     loc_1800046CE
0x18000436d  lea     edx, [r15+10h]; nIndex
0x180004371  call    cs:__imp_GetWindowLongPtrW
0x180004377  lea     edi, [r15+1]
0x18000437b  mov     r14, rax
0x18000437e  sub     esi, edi
0x180004380  jz      loc_180004483
0x180004386  sub     esi, edi
0x180004388  jz      loc_18000447F
0x18000438e  sub     esi, 3E7h
0x180004394  jz      short loc_1800043BF
0x180004396  cmp     esi, edi
0x180004398  jnz     loc_18000467C
0x18000439e  mov     r9d, 3E9h; dwData
0x1800043a4  mov     [rax+44h], edi
0x1800043a7  mov     r8d, edi; uCommand
0x1800043aa  lea     rdx, gszHelpFilename; "audiocdc.hlp"
0x1800043b1  mov     rcx, rbx; hWndMain
0x1800043b4  call    cs:__imp_WinHelpW
0x1800043ba  jmp     loc_18000467C
0x1800043bf  lea     r8, [rsp+4E0h+var_4AC]
0x1800043c4  mov     rcx, r14
0x1800043c7  lea     rdx, [rsp+4E0h+var_4B0]
0x1800043cc  call    configAutoConfig
0x1800043d1  mov     esi, eax
0x1800043d3  test    eax, eax
0x1800043d5  jnz     short loc_180004418
0x1800043d7  mov     edx, 3EBh; nIDDlgItem
0x1800043dc  mov     rcx, rbx; hDlg
0x1800043df  call    cs:__imp_GetDlgItem
0x1800043e5  movsxd  r8, [rsp+4E0h+var_4B0]; wParam
0x1800043ea  mov     esi, 14Eh
0x1800043ef  mov     edx, esi; Msg
0x1800043f1  mov     rcx, rax; hWnd
0x1800043f4  xor     r9d, r9d; lParam
0x1800043f7  call    cs:__imp_SendMessageW
0x1800043fd  mov     edx, 3ECh; nIDDlgItem
0x180004402  mov     rcx, rbx; hDlg
0x180004405  call    cs:__imp_GetDlgItem
0x18000440b  movsxd  r8, [rsp+4E0h+var_4AC]
0x180004410  mov     rcx, rax
0x180004413  jmp     loc_180004671
0x180004418  mov     rcx, [r14+14h]; hInstance
0x18000441c  lea     r8, [rbp+3E0h+Buffer]; lpBuffer
0x180004423  mov     r12d, 0C8h
0x180004429  mov     edx, 23h ; '#'; uID
0x18000442e  mov     r9d, r12d; cchBufferMax
0x180004431  call    cs:__imp_LoadStringW
0x180004437  test    eax, eax
0x180004439  jz      loc_18000467C
0x18000443f  mov     rcx, [r14+14h]; hInstance
0x180004443  lea     r8, [rbp+3E0h+Text]; lpBuffer
0x18000444a  mov     r9d, r12d; cchBufferMax
0x18000444d  mov     edx, esi; uID
0x18000444f  call    cs:__imp_LoadStringW
0x180004455  test    eax, eax
0x180004457  jz      loc_18000467C
0x18000445d  mov     r9d, 30h ; '0'; uType
0x180004463  lea     r8, [rbp+3E0h+Buffer]; lpCaption
0x18000446a  lea     rdx, [rbp+3E0h+Text]; lpText
0x180004471  mov     rcx, rbx; hWnd
0x180004474  call    cs:__imp_MessageBoxW
0x18000447a  jmp     loc_18000467C
0x18000447f  xor     edx, edx
0x180004481  jmp     short loc_1800044F3
0x180004483  mov     edx, 3EBh; nIDDlgItem
0x180004488  mov     rcx, rbx; hDlg
0x18000448b  mov     esi, r15d
0x18000448e  call    cs:__imp_GetDlgItem
0x180004494  mov     r15d, 147h
0x18000449a  xor     r9d, r9d; lParam
0x18000449d  mov     edx, r15d; Msg
0x1800044a0  mov     rcx, rax; hWnd
0x1800044a3  xor     r8d, r8d; wParam
0x1800044a6  call    cs:__imp_SendMessageW
0x1800044ac  cmp     eax, [r14+38h]
0x1800044b0  jz      short loc_1800044B8
0x1800044b2  mov     [r14+38h], eax
0x1800044b6  mov     esi, edi
0x1800044b8  mov     edx, 3ECh; nIDDlgItem
0x1800044bd  mov     rcx, rbx; hDlg
0x1800044c0  call    cs:__imp_GetDlgItem
0x1800044c6  xor     r9d, r9d; lParam
0x1800044c9  xor     r8d, r8d; wParam
0x1800044cc  mov     rcx, rax; hWnd
0x1800044cf  mov     edx, r15d; Msg
0x1800044d2  call    cs:__imp_SendMessageW
0x1800044d8  cmp     eax, [r14+3Ch]
0x1800044dc  jz      short loc_1800044E4
0x1800044de  mov     [r14+3Ch], eax
0x1800044e2  jmp     short loc_1800044E8
0x1800044e4  cmp     esi, edi
0x1800044e6  jnz     short loc_1800044F0
0x1800044e8  mov     rcx, r14
0x1800044eb  call    configWriteConfiguration
0x1800044f0  mov     rdx, rdi; nResult
0x1800044f3  mov     rcx, rbx; hDlg
0x1800044f6  call    cs:__imp_EndDialog
0x1800044fc  jmp     loc_18000467C
0x180004501  mov     r8, r14; dwNewLong
0x180004504  mov     [r9+44h], r15d
0x180004508  mov     edx, 10h; nIndex
0x18000450d  call    cs:__imp_SetWindowLongPtrW
0x180004513  mov     eax, [r14+3Ch]
0x180004517  mov     edx, 3EBh; nIDDlgItem
0x18000451c  mov     r13d, [r14+38h]
0x180004520  mov     rcx, rbx; hDlg
0x180004523  mov     [rsp+4E0h+var_4B0], eax
0x180004527  mov     [rsp+4E0h+var_4AC], r13d
0x18000452c  call    cs:__imp_GetDlgItem
0x180004532  mov     edx, 3ECh; nIDDlgItem
0x180004537  mov     rcx, rbx; hDlg
0x18000453a  mov     r15, rax
0x18000453d  call    cs:__imp_GetDlgItem
0x180004543  xor     esi, esi
0x180004545  lea     r13, gaRateListFormat
0x18000454c  mov     r12, rax
0x18000454f  xor     ebx, ebx
0x180004551  lea     edi, [rsi+1]
0x180004554  mov     edx, [rbx+r13+4]; uID
0x180004559  lea     r8, [rbp+3E0h+pszFormat]; lpBuffer
0x18000455d  mov     rcx, [r14+14h]; hInstance
0x180004561  mov     r9d, 50h ; 'P'; cchBufferMax
0x180004567  call    cs:__imp_LoadStringW
0x18000456d  mov     ecx, [rbx+r13]
0x180004571  sub     ecx, edi
0x180004573  jz      short loc_1800045CC
0x180004575  sub     ecx, edi
0x180004577  jz      short loc_1800045B2
0x180004579  sub     ecx, edi
0x18000457b  jz      short loc_1800045A8
0x18000457d  cmp     ecx, edi
0x18000457f  jnz     loc_180004614
0x180004585  mov     r9d, [rbx+r13+8]
0x18000458a  lea     r8, [rbp+3E0h+pszFormat]; pszFormat
0x18000458e  mov     eax, r9d
0x180004591  lea     rcx, [rsp+4E0h+pszDest]; pszDest
0x180004596  shr     eax, 1
0x180004598  mov     edx, 50h ; 'P'; cchDest
0x18000459d  mov     [rsp+4E0h+var_4C0], eax
0x1800045a1  call    StringCchPrintfW
0x1800045a6  jmp     short loc_180004614
0x1800045a8  mov     r9d, [rbx+r13+8]
0x1800045ad  shr     r9d, 1
0x1800045b0  jmp     short loc_1800045B7
0x1800045b2  mov     r9d, [rbx+r13+8]
0x1800045b7  lea     r8, [rbp+3E0h+pszFormat]; pszFormat
0x1800045bb  mov     edx, 50h ; 'P'; cchDest
0x1800045c0  lea     rcx, [rsp+4E0h+pszDest]; pszDest
0x1800045c5  call    StringCchPrintfW
0x1800045ca  jmp     short loc_180004614
0x1800045cc  mov     ecx, 7FFFFFFEh
0x1800045d1  lea     r8, [rbp+3E0h+pszFormat]
0x1800045d5  mov     edx, 50h ; 'P'
0x1800045da  lea     rax, [rsp+4E0h+pszDest]
0x1800045df  xor     r10d, r10d
0x1800045e2  test    rcx, rcx
0x1800045e5  jz      short loc_180004605
0x1800045e7  movzx   r9d, word ptr [r8]
0x1800045eb  test    r9w, r9w
0x1800045ef  jz      short loc_180004605
0x1800045f1  mov     [rax], r9w
0x1800045f5  add     r8, 2
0x1800045f9  add     rax, 2
0x1800045fd  sub     rcx, rdi
0x180004600  sub     rdx, rdi
0x180004603  jnz     short loc_1800045E2
0x180004605  test    rdx, rdx
0x180004608  lea     rcx, [rax-2]
0x18000460c  cmovnz  rcx, rax
0x180004610  mov     [rcx], r10w
0x180004614  lea     r9, [rsp+4E0h+pszDest]; lParam
0x180004619  xor     r8d, r8d; wParam
0x18000461c  mov     edx, 143h; Msg
0x180004621  mov     rcx, r15; hWnd
0x180004624  call    cs:__imp_SendMessageW
0x18000462a  lea     r9, [rsp+4E0h+pszDest]; lParam
0x18000462f  xor     r8d, r8d; wParam
0x180004632  mov     edx, 143h; Msg
0x180004637  mov     rcx, r12; hWnd
0x18000463a  call    cs:__imp_SendMessageW
0x180004640  inc     rsi
0x180004643  add     rbx, 0Ch
0x180004647  cmp     rsi, 7
0x18000464b  jnz     loc_180004554
0x180004651  movsxd  r8, [rsp+4E0h+var_4AC]; wParam
0x180004656  mov     esi, 14Eh
0x18000465b  mov     edx, esi; Msg
0x18000465d  xor     r9d, r9d; lParam
0x180004660  mov     rcx, r15; hWnd
0x180004663  call    cs:__imp_SendMessageW
0x180004669  movsxd  r8, [rsp+4E0h+var_4B0]; wParam
0x18000466e  mov     rcx, r12; hWnd
0x180004671  xor     r9d, r9d; lParam
0x180004674  mov     edx, esi; Msg
0x180004676  call    cs:__imp_SendMessageW
0x18000467c  mov     rax, rdi
0x18000467f  jmp     short loc_1800046D0
0x180004681  mov     rcx, [r14+10h]; hWndMain
0x180004685  lea     r9, dwData; dwData
0x18000468c  mov     r8d, 0Ch; uCommand
0x180004692  lea     rdx, gszHelpFilename; "audiocdc.hlp"
0x180004699  call    cs:__imp_WinHelpW
0x18000469f  mov     eax, 1
0x1800046a4  jmp     short loc_1800046D0
0x1800046a6  mov     edx, 10h; nIndex
0x1800046ab  call    cs:__imp_GetWindowLongPtrW
0x1800046b1  cmp     [rax+44h], r15d
0x1800046b5  jz      short loc_1800046CE
0x1800046b7  xor     r9d, r9d; dwData
0x1800046ba  lea     rdx, gszHelpFilename; "audiocdc.hlp"
0x1800046c1  mov     rcx, rbx; hWndMain
0x1800046c4  lea     r8d, [r9+2]; uCommand
0x1800046c8  call    cs:__imp_WinHelpW
0x1800046ce  xor     eax, eax
0x1800046d0  mov     rcx, [rbp+3E0h+var_40]
0x1800046d7  xor     rcx, rsp; StackCookie
0x1800046da  call    __security_check_cookie
0x1800046df  mov     rbx, [rsp+4E0h+arg_8]
0x1800046e7  add     rsp, 4B0h
0x1800046ee  pop     r15
0x1800046f0  pop     r14
0x1800046f2  pop     r13
0x1800046f4  pop     r12
0x1800046f6  pop     rdi
0x1800046f7  pop     rsi
0x1800046f8  pop     rbp
0x1800046f9  retn
```
