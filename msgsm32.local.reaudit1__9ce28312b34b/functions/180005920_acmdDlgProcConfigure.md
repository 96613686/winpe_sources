# acmdDlgProcConfigure

- ea: `0x180005920`
- end: `0x180005cdb`
- name: `acmdDlgProcConfigure`
- size: `955`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180001400`
- `0x18000588c`
- `0x180005920`
- `0x180005f1c`
- `0x180006328`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005a4e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005a6c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005b81`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005a4e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005a6c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180005b81`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x180005a8e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!MessageBoxW` at `0x180005a8e`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800059ff`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005a25`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005aa8`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005ada`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005b46`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005b57`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x1800059ff`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005a25`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005aa8`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005ada`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005b46`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!GetDlgItem` at `0x180005b57`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180005b10`
- `ext-ms-win-ntuser-dialogbox-l1-1-0!EndDialog` at `0x180005b10`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005a17`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005ac0`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005aec`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005c05`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005c1b`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005c44`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005c57`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005a17`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005ac0`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005aec`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005c05`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005c1b`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005c44`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180005c57`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x1800059d4`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x180005c7a`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x180005ca9`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x1800059d4`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x180005c7a`
- `ext-ms-win-ntuser-misc-l1-1-0!WinHelpW` at `0x180005ca9`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x180005b27`
- `ext-ms-win-ntuser-windowclass-l1-1-0!SetWindowLongPtrW` at `0x180005b27`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x180005991`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x180005c8c`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x180005991`
- `ext-ms-win-ntuser-windowclass-l1-1-0!GetWindowLongPtrW` at `0x180005c8c`

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
  __int64 v31; // rcx
  WCHAR *v32; // r8
  __int64 v33; // rdx
  wchar_t *v34; // rax
  wchar_t *v35; // rcx
  int v37; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v38[3]; // [rsp+24h] [rbp-DCh] BYREF
  wchar_t pszDest[80]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszFormat[80]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Buffer[200]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR Text[200]; // [rsp+300h] [rbp+200h] BYREF

  v37 = 0;
  v38[0] = 0;
  v7 = a2 - 2;
  if ( v7 )
  {
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
      v37 = *(_DWORD *)(a4 + 60);
      v38[0] = v26;
      DlgItem = GetDlgItem(a1, 1003);
      v28 = 0;
      v29 = GetDlgItem(a1, 1004);
      v30 = 0;
      do
      {
        LoadStringW(*(HINSTANCE *)(a4 + 20), *(_DWORD *)((char *)gaRateListFormat + v30 + 4), pszFormat, 80);
        if ( *(_DWORD *)((char *)gaRateListFormat + v30) == 1 )
        {
          v31 = 2147483646;
          v32 = pszFormat;
          v33 = 80;
          v34 = pszDest;
          do
          {
            if ( !v31 )
              break;
            if ( !*v32 )
              break;
            *v34++ = *v32++;
            --v31;
            --v33;
          }
          while ( v33 );
          v35 = v34 - 1;
          if ( v33 )
            v35 = v34;
          *v35 = 0;
        }
        else if ( *(_DWORD *)((char *)gaRateListFormat + v30) == 2 )
        {
          StringCchPrintfW(pszDest, 0x50u, pszFormat, *(unsigned int *)((char *)&gaRateListFormat[1] + v30));
        }
        SendMessageW(DlgItem, 0x143u, 0, (LPARAM)pszDest);
        SendMessageW(v29, 0x143u, 0, (LPARAM)pszDest);
        ++v28;
        v30 += 12;
      }
      while ( v28 != 6 );
      SendMessageW(DlgItem, 0x14Eu, v38[0], 0);
      v18 = v37;
      v19 = v29;
LABEL_37:
      SendMessageW(v19, 0x14Eu, v18, 0);
      return 1;
    }
    if ( v9 == 1 )
    {
      WindowLongPtrW = GetWindowLongPtrW(a1, 16);
      v11 = WindowLongPtrW;
      v12 = a3 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 999;
          if ( v14 )
          {
            if ( v14 == 1 )
            {
              *(_DWORD *)(WindowLongPtrW + 68) = 1;
              WinHelpW(a1, L"audiocdc.hlp", 1u, 0x3EAu);
            }
            return 1;
          }
          v15 = configAutoConfig(WindowLongPtrW, &v37, v38);
          if ( v15 )
          {
            if ( LoadStringW(*(HINSTANCE *)(v11 + 20), 0x1Eu, Buffer, 200)
              && LoadStringW(*(HINSTANCE *)(v11 + 20), v15, Text, 200) )
            {
              MessageBoxW(a1, Text, Buffer, 0x30u);
            }
            return 1;
          }
          v16 = GetDlgItem(a1, 1003);
          SendMessageW(v16, 0x14Eu, v37, 0);
          v17 = GetDlgItem(a1, 1004);
          v18 = v38[0];
          v19 = v17;
          goto LABEL_37;
        }
        v20 = 0;
LABEL_23:
        EndDialog(a1, v20);
        return 1;
      }
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
  }
  else if ( *(_DWORD *)(GetWindowLongPtrW(a1, 16) + 68) )
  {
    WinHelpW(a1, L"audiocdc.hlp", 2u, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x180005920  mov     [rsp-8+arg_8], rbx
0x180005925  push    rbp
0x180005926  push    rsi
0x180005927  push    rdi
0x180005928  push    r12
0x18000592a  push    r13
0x18000592c  push    r14
0x18000592e  push    r15
0x180005930  lea     rbp, [rsp-3A0h]
0x180005938  sub     rsp, 4A0h
0x18000593f  mov     rax, cs:__security_cookie
0x180005946  xor     rax, rsp
0x180005949  mov     [rbp+3D0h+var_40], rax
0x180005950  xor     r15d, r15d
0x180005953  mov     r14, r9
0x180005956  mov     [rsp+4D0h+var_4B0], r15d
0x18000595b  mov     rsi, r8
0x18000595e  mov     [rsp+4D0h+var_4AC], r15d
0x180005963  mov     rbx, rcx
0x180005966  sub     edx, 2
0x180005969  jz      loc_180005C87
0x18000596f  sub     edx, 51h ; 'Q'
0x180005972  jz      loc_180005C62
0x180005978  sub     edx, 0BDh
0x18000597e  jz      loc_180005B1B
0x180005984  cmp     edx, 1
0x180005987  jnz     loc_180005CAF
0x18000598d  lea     edx, [r15+10h]; nIndex
0x180005991  call    cs:__imp_GetWindowLongPtrW
0x180005997  lea     edi, [r15+1]
0x18000599b  mov     r14, rax
0x18000599e  sub     esi, edi
0x1800059a0  jz      loc_180005A9D
0x1800059a6  sub     esi, edi
0x1800059a8  jz      loc_180005A99
0x1800059ae  sub     esi, 3E7h
0x1800059b4  jz      short loc_1800059DF
0x1800059b6  cmp     esi, edi
0x1800059b8  jnz     loc_180005C5D
0x1800059be  mov     r9d, 3EAh; dwData
0x1800059c4  mov     [rax+44h], edi
0x1800059c7  mov     r8d, edi; uCommand
0x1800059ca  lea     rdx, gszHelpFilename; "audiocdc.hlp"
0x1800059d1  mov     rcx, rbx; hWndMain
0x1800059d4  call    cs:__imp_WinHelpW
0x1800059da  jmp     loc_180005C5D
0x1800059df  lea     r8, [rsp+4D0h+var_4AC]
0x1800059e4  mov     rcx, r14
0x1800059e7  lea     rdx, [rsp+4D0h+var_4B0]
0x1800059ec  call    configAutoConfig
0x1800059f1  mov     esi, eax
0x1800059f3  test    eax, eax
0x1800059f5  jnz     short loc_180005A38
0x1800059f7  mov     edx, 3EBh; nIDDlgItem
0x1800059fc  mov     rcx, rbx; hDlg
0x1800059ff  call    cs:__imp_GetDlgItem
0x180005a05  movsxd  r8, [rsp+4D0h+var_4B0]; wParam
0x180005a0a  mov     esi, 14Eh
0x180005a0f  mov     edx, esi; Msg
0x180005a11  mov     rcx, rax; hWnd
0x180005a14  xor     r9d, r9d; lParam
0x180005a17  call    cs:__imp_SendMessageW
0x180005a1d  mov     edx, 3ECh; nIDDlgItem
0x180005a22  mov     rcx, rbx; hDlg
0x180005a25  call    cs:__imp_GetDlgItem
0x180005a2b  movsxd  r8, [rsp+4D0h+var_4AC]
0x180005a30  mov     rcx, rax
0x180005a33  jmp     loc_180005C52
0x180005a38  mov     rcx, [r14+14h]; hInstance
0x180005a3c  lea     r8, [rbp+3D0h+Buffer]; lpBuffer
0x180005a40  mov     r12d, 0C8h
0x180005a46  mov     edx, 1Eh; uID
0x180005a4b  mov     r9d, r12d; cchBufferMax
0x180005a4e  call    cs:__imp_LoadStringW
0x180005a54  test    eax, eax
0x180005a56  jz      loc_180005C5D
0x180005a5c  mov     rcx, [r14+14h]; hInstance
0x180005a60  lea     r8, [rbp+3D0h+Text]; lpBuffer
0x180005a67  mov     r9d, r12d; cchBufferMax
0x180005a6a  mov     edx, esi; uID
0x180005a6c  call    cs:__imp_LoadStringW
0x180005a72  test    eax, eax
0x180005a74  jz      loc_180005C5D
0x180005a7a  mov     r9d, 30h ; '0'; uType
0x180005a80  lea     r8, [rbp+3D0h+Buffer]; lpCaption
0x180005a84  lea     rdx, [rbp+3D0h+Text]; lpText
0x180005a8b  mov     rcx, rbx; hWnd
0x180005a8e  call    cs:__imp_MessageBoxW
0x180005a94  jmp     loc_180005C5D
0x180005a99  xor     edx, edx
0x180005a9b  jmp     short loc_180005B0D
0x180005a9d  mov     edx, 3EBh; nIDDlgItem
0x180005aa2  mov     rcx, rbx; hDlg
0x180005aa5  mov     esi, r15d
0x180005aa8  call    cs:__imp_GetDlgItem
0x180005aae  mov     r15d, 147h
0x180005ab4  xor     r9d, r9d; lParam
0x180005ab7  mov     edx, r15d; Msg
0x180005aba  mov     rcx, rax; hWnd
0x180005abd  xor     r8d, r8d; wParam
0x180005ac0  call    cs:__imp_SendMessageW
0x180005ac6  cmp     eax, [r14+38h]
0x180005aca  jz      short loc_180005AD2
0x180005acc  mov     [r14+38h], eax
0x180005ad0  mov     esi, edi
0x180005ad2  mov     edx, 3ECh; nIDDlgItem
0x180005ad7  mov     rcx, rbx; hDlg
0x180005ada  call    cs:__imp_GetDlgItem
0x180005ae0  xor     r9d, r9d; lParam
0x180005ae3  xor     r8d, r8d; wParam
0x180005ae6  mov     rcx, rax; hWnd
0x180005ae9  mov     edx, r15d; Msg
0x180005aec  call    cs:__imp_SendMessageW
0x180005af2  cmp     eax, [r14+3Ch]
0x180005af6  jz      short loc_180005AFE
0x180005af8  mov     [r14+3Ch], eax
0x180005afc  jmp     short loc_180005B02
0x180005afe  cmp     esi, edi
0x180005b00  jnz     short loc_180005B0A
0x180005b02  mov     rcx, r14
0x180005b05  call    configWriteConfiguration
0x180005b0a  mov     rdx, rdi; nResult
0x180005b0d  mov     rcx, rbx; hDlg
0x180005b10  call    cs:__imp_EndDialog
0x180005b16  jmp     loc_180005C5D
0x180005b1b  mov     r8, r14; dwNewLong
0x180005b1e  mov     [r9+44h], r15d
0x180005b22  mov     edx, 10h; nIndex
0x180005b27  call    cs:__imp_SetWindowLongPtrW
0x180005b2d  mov     eax, [r14+3Ch]
0x180005b31  mov     edx, 3EBh; nIDDlgItem
0x180005b36  mov     r13d, [r14+38h]
0x180005b3a  mov     rcx, rbx; hDlg
0x180005b3d  mov     [rsp+4D0h+var_4B0], eax
0x180005b41  mov     [rsp+4D0h+var_4AC], r13d
0x180005b46  call    cs:__imp_GetDlgItem
0x180005b4c  mov     edx, 3ECh; nIDDlgItem
0x180005b51  mov     rcx, rbx; hDlg
0x180005b54  mov     r15, rax
0x180005b57  call    cs:__imp_GetDlgItem
0x180005b5d  xor     esi, esi
0x180005b5f  lea     r13, gaRateListFormat
0x180005b66  mov     r12, rax
0x180005b69  xor     ebx, ebx
0x180005b6b  lea     edi, [rsi+1]
0x180005b6e  mov     edx, [rbx+r13+4]; uID
0x180005b73  lea     r8, [rbp+3D0h+pszFormat]; lpBuffer
0x180005b77  mov     rcx, [r14+14h]; hInstance
0x180005b7b  mov     r9d, 50h ; 'P'; cchBufferMax
0x180005b81  call    cs:__imp_LoadStringW
0x180005b87  mov     ecx, [rbx+r13]
0x180005b8b  sub     ecx, edi
0x180005b8d  jz      short loc_180005BAD
0x180005b8f  cmp     ecx, edi
0x180005b91  jnz     short loc_180005BF5
0x180005b93  mov     r9d, [rbx+r13+8]
0x180005b98  lea     r8, [rbp+3D0h+pszFormat]; pszFormat
0x180005b9c  mov     edx, 50h ; 'P'; cchDest
0x180005ba1  lea     rcx, [rsp+4D0h+pszDest]; pszDest
0x180005ba6  call    StringCchPrintfW
0x180005bab  jmp     short loc_180005BF5
0x180005bad  mov     ecx, 7FFFFFFEh
0x180005bb2  lea     r8, [rbp+3D0h+pszFormat]
0x180005bb6  mov     edx, 50h ; 'P'
0x180005bbb  lea     rax, [rsp+4D0h+pszDest]
0x180005bc0  xor     r10d, r10d
0x180005bc3  test    rcx, rcx
0x180005bc6  jz      short loc_180005BE6
0x180005bc8  movzx   r9d, word ptr [r8]
0x180005bcc  test    r9w, r9w
0x180005bd0  jz      short loc_180005BE6
0x180005bd2  mov     [rax], r9w
0x180005bd6  add     r8, 2
0x180005bda  add     rax, 2
0x180005bde  sub     rcx, rdi
0x180005be1  sub     rdx, rdi
0x180005be4  jnz     short loc_180005BC3
0x180005be6  test    rdx, rdx
0x180005be9  lea     rcx, [rax-2]
0x180005bed  cmovnz  rcx, rax
0x180005bf1  mov     [rcx], r10w
0x180005bf5  lea     r9, [rsp+4D0h+pszDest]; lParam
0x180005bfa  xor     r8d, r8d; wParam
0x180005bfd  mov     edx, 143h; Msg
0x180005c02  mov     rcx, r15; hWnd
0x180005c05  call    cs:__imp_SendMessageW
0x180005c0b  lea     r9, [rsp+4D0h+pszDest]; lParam
0x180005c10  xor     r8d, r8d; wParam
0x180005c13  mov     edx, 143h; Msg
0x180005c18  mov     rcx, r12; hWnd
0x180005c1b  call    cs:__imp_SendMessageW
0x180005c21  inc     rsi
0x180005c24  add     rbx, 0Ch
0x180005c28  cmp     rsi, 6
0x180005c2c  jnz     loc_180005B6E
0x180005c32  movsxd  r8, [rsp+4D0h+var_4AC]; wParam
0x180005c37  mov     esi, 14Eh
0x180005c3c  mov     edx, esi; Msg
0x180005c3e  xor     r9d, r9d; lParam
0x180005c41  mov     rcx, r15; hWnd
0x180005c44  call    cs:__imp_SendMessageW
0x180005c4a  movsxd  r8, [rsp+4D0h+var_4B0]; wParam
0x180005c4f  mov     rcx, r12; hWnd
0x180005c52  xor     r9d, r9d; lParam
0x180005c55  mov     edx, esi; Msg
0x180005c57  call    cs:__imp_SendMessageW
0x180005c5d  mov     rax, rdi
0x180005c60  jmp     short loc_180005CB1
0x180005c62  mov     rcx, [r14+10h]; hWndMain
0x180005c66  lea     r9, dwData; dwData
0x180005c6d  mov     r8d, 0Ch; uCommand
0x180005c73  lea     rdx, gszHelpFilename; "audiocdc.hlp"
0x180005c7a  call    cs:__imp_WinHelpW
0x180005c80  mov     eax, 1
0x180005c85  jmp     short loc_180005CB1
0x180005c87  mov     edx, 10h; nIndex
0x180005c8c  call    cs:__imp_GetWindowLongPtrW
0x180005c92  cmp     [rax+44h], r15d
0x180005c96  jz      short loc_180005CAF
0x180005c98  xor     r9d, r9d; dwData
0x180005c9b  lea     rdx, gszHelpFilename; "audiocdc.hlp"
0x180005ca2  mov     rcx, rbx; hWndMain
0x180005ca5  lea     r8d, [r9+2]; uCommand
0x180005ca9  call    cs:__imp_WinHelpW
0x180005caf  xor     eax, eax
0x180005cb1  mov     rcx, [rbp+3D0h+var_40]
0x180005cb8  xor     rcx, rsp; StackCookie
0x180005cbb  call    __security_check_cookie
0x180005cc0  mov     rbx, [rsp+4D0h+arg_8]
0x180005cc8  add     rsp, 4A0h
0x180005ccf  pop     r15
0x180005cd1  pop     r14
0x180005cd3  pop     r13
0x180005cd5  pop     r12
0x180005cd7  pop     rdi
0x180005cd8  pop     rsi
0x180005cd9  pop     rbp
0x180005cda  retn
```
