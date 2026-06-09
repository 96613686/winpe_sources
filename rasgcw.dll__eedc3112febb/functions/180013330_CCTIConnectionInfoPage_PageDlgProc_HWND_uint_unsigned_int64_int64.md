# CCTIConnectionInfoPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180013330`
- end: `0x180013a69`
- name: `?PageDlgProc@CCTIConnectionInfoPage@@CAHPEAUHWND__@@I_K_J@Z`
- size: `1849`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010c38`
- `0x180010e64`
- `0x180011940`
- `0x180011bc0`
- `0x180011dd4`
- `0x180012ed4`
- `0x180013330`
- `0x180013a70`
- `0x18002b970`
- `0x18002bbb0`
- `0x18002be68`
- `0x18002c1b0`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `USER32!GetPropW` at `0x1800133fe`
- `USER32!GetPropW` at `0x1800133fe`
- `USER32!RemovePropW` at `0x1800133a0`
- `USER32!RemovePropW` at `0x1800133a0`
- `USER32!SetWindowTextW` at `0x1800135b8`
- `USER32!SetWindowTextW` at `0x1800138d3`
- `USER32!SetWindowTextW` at `0x18001390d`
- `USER32!SetWindowTextW` at `0x180013965`
- `USER32!SetWindowTextW` at `0x1800139c9`
- `USER32!SetWindowTextW` at `0x1800135b8`
- `USER32!SetWindowTextW` at `0x1800138d3`
- `USER32!SetWindowTextW` at `0x18001390d`
- `USER32!SetWindowTextW` at `0x180013965`
- `USER32!SetWindowTextW` at `0x1800139c9`
- `USER32!DestroyIcon` at `0x1800133cb`
- `USER32!DestroyIcon` at `0x1800133cb`
- `USER32!IsDlgButtonChecked` at `0x18001347b`
- `USER32!IsDlgButtonChecked` at `0x1800134cc`
- `USER32!IsDlgButtonChecked` at `0x1800135da`
- `USER32!IsDlgButtonChecked` at `0x18001347b`
- `USER32!IsDlgButtonChecked` at `0x1800134cc`
- `USER32!IsDlgButtonChecked` at `0x1800135da`
- `USER32!SetPropW` at `0x180013389`
- `USER32!SetPropW` at `0x180013389`
- `USER32!SetWindowLongW` at `0x180013a1c`
- `USER32!SetWindowLongW` at `0x180013a1c`
- `USER32!GetDlgItem` at `0x1800133ae`
- `USER32!GetDlgItem` at `0x180013490`
- `USER32!GetDlgItem` at `0x1800134be`
- `USER32!GetDlgItem` at `0x180013536`
- `USER32!GetDlgItem` at `0x180013610`
- `USER32!GetDlgItem` at `0x1800136a1`
- `USER32!GetDlgItem` at `0x180013701`
- `USER32!GetDlgItem` at `0x1800138c5`
- `USER32!GetDlgItem` at `0x180013901`
- `USER32!GetDlgItem` at `0x180013957`
- `USER32!GetDlgItem` at `0x180013991`
- `USER32!GetDlgItem` at `0x1800133ae`
- `USER32!GetDlgItem` at `0x180013490`
- `USER32!GetDlgItem` at `0x1800134be`
- `USER32!GetDlgItem` at `0x180013536`
- `USER32!GetDlgItem` at `0x180013610`
- `USER32!GetDlgItem` at `0x1800136a1`
- `USER32!GetDlgItem` at `0x180013701`
- `USER32!GetDlgItem` at `0x1800138c5`
- `USER32!GetDlgItem` at `0x180013901`
- `USER32!GetDlgItem` at `0x180013957`
- `USER32!GetDlgItem` at `0x180013991`
- `USER32!SendMessageW` at `0x1800133c2`
- `USER32!SendMessageW` at `0x180013523`
- `USER32!SendMessageW` at `0x1800137d8`
- `USER32!SendMessageW` at `0x180013860`
- `USER32!SendMessageW` at `0x1800133c2`
- `USER32!SendMessageW` at `0x180013523`
- `USER32!SendMessageW` at `0x1800137d8`
- `USER32!SendMessageW` at `0x180013860`
- `USER32!GetParent` at `0x1800137bf`
- `USER32!GetParent` at `0x18001384c`
- `USER32!GetParent` at `0x1800137bf`
- `USER32!GetParent` at `0x18001384c`
- `USER32!GetWindowTextW` at `0x180013583`
- `USER32!GetWindowTextW` at `0x18001365d`
- `USER32!GetWindowTextW` at `0x1800136e4`
- `USER32!GetWindowTextW` at `0x180013731`
- `USER32!GetWindowTextW` at `0x180013583`
- `USER32!GetWindowTextW` at `0x18001365d`
- `USER32!GetWindowTextW` at `0x1800136e4`
- `USER32!GetWindowTextW` at `0x180013731`
- `rtutils!TracePrintfExA` at `0x180013a0d`
- `rtutils!TracePrintfExA` at `0x180013a0d`
- `TAPI32!lineTranslateDialogW` at `0x18001380d`
- `TAPI32!lineTranslateDialogW` at `0x18001380d`

## pseudocode

```c
__int64 __fastcall CCTIConnectionInfoPage::PageDlgProc(HWND a1, int a2, unsigned __int64 a3, WCHAR *a4)
{
  WCHAR *v4; // rbx
  HWND DlgItem; // rax
  HICON v9; // rax
  HANDLE PropW; // rax
  HANDLE v12; // r14
  int v13; // esi
  int v14; // esi
  int v15; // esi
  HWND v16; // rax
  HWND v17; // rbx
  unsigned __int64 v18; // rdi
  HWND v19; // r15
  int v20; // esi
  HWND v21; // rax
  __int64 v22; // rbx
  __int64 v23; // r12
  HWND v24; // r9
  __int64 v25; // rdx
  _BYTE *v26; // rcx
  __int64 v27; // rdx
  WCHAR *v28; // rax
  WCHAR *v29; // rax
  HWND v30; // rsi
  __int64 v31; // rbx
  HWND v32; // rax
  _WORD *v33; // rdi
  HWND v34; // rbx
  HWND v35; // rdx
  int v36; // eax
  HWND Parent; // rax
  LPARAM StringPcch; // rbx
  HWND v39; // rax
  __int64 v40; // rax
  __int64 v41; // r12
  __int64 v42; // rbx
  const WCHAR *v43; // rdi
  HWND v44; // rax
  __int64 v45; // rax
  HWND v46; // rax
  __int64 v47; // rbx
  HWND v48; // rax
  WCHAR *v49; // rax
  HWND v50; // rax
  unsigned __int16 *v51; // rcx
  HWND v52; // rbx
  LPCWSTR v53; // r11
  __int64 v54; // rax
  __int64 v55; // r12
  _BYTE *v56; // rax
  WCHAR String[264]; // [rsp+40h] [rbp-C0h] BYREF

  v4 = a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = (WCHAR *)*((_QWORD *)a4 + 6);
    SetPropW(a1, L"_Win32_this_", v4);
    goto LABEL_44;
  }
  if ( a2 == 2 )
  {
    RemovePropW(a1, L"_Win32_this_");
LABEL_7:
    DlgItem = GetDlgItem(a1, 1081);
    v9 = (HICON)SendMessageW(DlgItem, 0x171u, 0, 0);
    DestroyIcon(v9);
    return 0;
  }
  PropW = GetPropW(a1, L"_Win32_this_");
  v12 = PropW;
  v13 = a2 - 2;
  if ( !v13 )
    goto LABEL_7;
  v14 = v13 - 76;
  if ( !v14 )
  {
    v36 = *((_DWORD *)v4 + 4);
    if ( v36 == -207 )
    {
      v50 = GetDlgItem(a1, 1075);
      v51 = (unsigned __int16 *)(*((_QWORD *)v12 + 7) + 1038LL);
      v52 = v50;
      if ( !*v51 && *((_WORD *)v12 + 32) )
      {
        StringCchCopyW(v51, 0x101u, (unsigned __int16 *)v12 + 32);
        SetWindowTextW(v52, v53);
      }
      if ( (unsigned int)IsValidRASConnectionName(
                           v52,
                           (PCNZWCH)(*((_QWORD *)v12 + 7) + 12LL),
                           (LPCWSTR)(*((_QWORD *)v12 + 7) + 1038LL)) )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "IsValidRASConnectionName: returned invalid connection name:%S",
            (const wchar_t *)(*((_QWORD *)v12 + 7) + 1038LL));
        SetWindowLongW(a1, 0, -1);
      }
      else
      {
        v54 = *((_QWORD *)v12 + 7);
        if ( !*(_WORD *)(v54 + 1820) )
        {
          *(_DWORD *)(v54 + 2888) = 0;
          v55 = 514;
          v56 = (_BYTE *)(*((_QWORD *)v12 + 7) + 2334LL);
          do
          {
            *v56++ = 0;
            --v55;
          }
          while ( v55 );
        }
        *(_DWORD *)(*((_QWORD *)v12 + 7) + 4952LL) = 1;
      }
      return 0;
    }
    if ( v36 == -206 )
      goto LABEL_7;
    if ( v36 != -200 )
    {
      if ( ((v36 + 4) & 0xFFFFFFFD) == 0 )
      {
        if ( (unsigned int)CompareStringWrapW(v4 + 20, L"ISPInfo") )
        {
          if ( !(unsigned int)CompareStringWrapW(v4 + 20, L"DialingRules") )
            lineTranslateDialogW(0, 0, 0x10004u, a1, 0);
        }
        else
        {
          Parent = GetParent(a1);
          SendMessageW(Parent, 0x465u, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&lParam);
        }
      }
      return 0;
    }
    StringPcch = PszLoadStringPcch(hInst);
    v39 = GetParent(a1);
    SendMessageW(v39, 0x489u, 0, StringPcch);
    if ( a3 == 4294967090 )
    {
      v40 = *((_QWORD *)v12 + 7);
      v41 = 514;
      v42 = v40 + 2848;
      v43 = (const WCHAR *)(v40 + 1820);
      if ( *(_WORD *)(v40 + 2848) )
      {
        memset_0(String, 0, 0x202u);
        if ( !StringCchPrintfW(String, 0x101u, L"%s\\%s", v42, v43) )
        {
          v44 = GetDlgItem(a1, 1072);
          SetWindowTextW(v44, String);
          v45 = *((_QWORD *)v12 + 7);
          *(_OWORD *)(v45 + 2848) = 0;
          *(_OWORD *)(v45 + 2864) = 0;
          *(_WORD *)(v45 + 2880) = 0;
        }
      }
      else
      {
        v46 = GetDlgItem(a1, 1072);
        SetWindowTextW(v46, v43);
      }
      v47 = *((_QWORD *)v12 + 7);
      if ( *(_WORD *)(v47 + 2334) )
      {
        memset_0(String, 0, 0x202u);
        StringCchCopyW(String, 0x101u, (unsigned __int16 *)(v47 + 2334));
        EncodePasswordW((__int16 *)String);
        v48 = GetDlgItem(a1, 1073);
        SetWindowTextW(v48, String);
        v49 = String;
        do
        {
          *(_BYTE *)v49 = 0;
          v49 = (WCHAR *)((char *)v49 + 1);
          --v41;
        }
        while ( v41 );
      }
    }
LABEL_62:
    CCTIConnectionInfoPage::UpdateDialogControls((CCTIConnectionInfoPage *)v12, v35);
    return 1;
  }
  v15 = v14 - 194;
  if ( !v15 )
  {
    v4 = (WCHAR *)PropW;
LABEL_44:
    *((_QWORD *)v4 + 3) = a1;
    CCTIConnectionInfoPage::InitDialogControls((CCTIConnectionInfoPage *)v4, a1);
    return 1;
  }
  if ( v15 != 1 )
    return 0;
  switch ( (unsigned __int16)a3 )
  {
    case 0x42Fu:
      if ( WORD1(a3) != 768 )
        return 0;
      v32 = GetDlgItem(a1, 1071);
      v33 = (_WORD *)(*((_QWORD *)v12 + 7) + 1552LL);
      v34 = v32;
      memset_0(v33, 0, 0x102u);
      GetWindowTextW(v34, v33, 129);
      StrTrim(v33);
      *((_DWORD *)v12 + 145) = *v33 != 0;
      goto LABEL_62;
    case 0x430u:
      v30 = GetDlgItem(a1, 1072);
      if ( WORD1(a3) != 768 )
        return 0;
      v31 = *((_QWORD *)v12 + 7);
      memset_0((void *)(v31 + 1820), 0, 0x202u);
      GetWindowTextW(v30, (LPWSTR)(v31 + 1820), 257);
      return 1;
    case 0x431u:
      if ( WORD1(a3) == 768 )
      {
        v21 = GetDlgItem(a1, 1073);
        v22 = *((_QWORD *)v12 + 7);
        v23 = 514;
        v24 = v21;
        v25 = 514;
        v26 = (_BYTE *)(v22 + 2334);
        do
        {
          *v26++ = 0;
          --v25;
        }
        while ( v25 );
        v27 = 514;
        v28 = String;
        do
        {
          *(_BYTE *)v28 = 0;
          v28 = (WCHAR *)((char *)v28 + 1);
          --v27;
        }
        while ( v27 );
        GetWindowTextW(v24, String, 257);
        EncodePasswordW((__int16 *)String);
        StringCchCopyW((unsigned __int16 *)(v22 + 2334), 0x101u, String);
        v29 = String;
        do
        {
          *(_BYTE *)v29 = 0;
          v29 = (WCHAR *)((char *)v29 + 1);
          --v23;
        }
        while ( v23 );
        return 1;
      }
      return 0;
  }
  if ( (unsigned __int16)a3 != 1074 )
  {
    if ( (unsigned __int16)a3 == 1075 )
    {
      v18 = a3 >> 16;
      v19 = GetDlgItem(a1, 1075);
      if ( (((_WORD)v18 - 512) & 0xFEFF) == 0 )
      {
        memset_0((void *)(*((_QWORD *)v12 + 7) + 1038LL), 0, 0x202u);
        GetWindowTextW(v19, (LPWSTR)(*((_QWORD *)v12 + 7) + 1038LL), 257);
        StrTrim((LPCWSTR)(*((_QWORD *)v12 + 7) + 1038LL));
        if ( (_WORD)v18 == 512 && !*(_WORD *)(*((_QWORD *)v12 + 7) + 1038LL) )
          SetWindowTextW(v19, (LPCWSTR)v12 + 32);
      }
    }
    else if ( (unsigned __int16)a3 == 1077 )
    {
      if ( !WORD1(a3) )
      {
        v17 = GetDlgItem(a1, 1077);
        *(_DWORD *)(*((_QWORD *)v12 + 7) + 2884LL) = IsDlgButtonChecked(a1, 1077) == 1;
        if ( !(unsigned int)OnClickAllUserProfile(*((_QWORD *)v12 + 6), a1, *(_DWORD *)(*((_QWORD *)v12 + 7) + 2884LL)) )
        {
          *(_DWORD *)(*((_QWORD *)v12 + 7) + 2884LL) = 0;
          SendMessageW(v17, 0xF1u, *(int *)(*((_QWORD *)v12 + 7) + 2884LL), 0);
        }
        return 1;
      }
    }
    else if ( (unsigned __int16)a3 == 1079 && !WORD1(a3) )
    {
      IsDlgButtonChecked(a1, 1079);
      v16 = GetDlgItem(a1, 1073);
      OnClickShowPassword(v16);
    }
    return 0;
  }
  v20 = 0;
  if ( WORD1(a3) )
    return 0;
  LOBYTE(v20) = IsDlgButtonChecked(a1, 1074) == 1;
  *(_DWORD *)(*((_QWORD *)v12 + 7) + 2888LL) = v20;
  return 1;
}

```

## disassembly

```asm
0x180013330  mov     [rsp-8+arg_8], rbx
0x180013335  mov     [rsp-8+arg_10], rsi
0x18001333a  push    rbp
0x18001333b  push    rdi
0x18001333c  push    r12
0x18001333e  push    r14
0x180013340  push    r15
0x180013342  lea     rbp, [rsp-160h]
0x18001334a  sub     rsp, 260h
0x180013351  mov     rax, cs:__security_cookie
0x180013358  xor     rax, rsp
0x18001335b  mov     [rbp+180h+var_30], rax
0x180013362  mov     rbx, r9
0x180013365  mov     rdi, r8
0x180013368  mov     esi, edx
0x18001336a  mov     r15, rcx
0x18001336d  cmp     edx, 110h
0x180013373  jnz     short loc_180013394
0x180013375  cmp     dword ptr [r9], 68h ; 'h'
0x180013379  jnz     short loc_18001337F
0x18001337b  mov     rbx, [r9+30h]
0x18001337f  mov     r8, rbx; hData
0x180013382  lea     rdx, String; "_Win32_this_"
0x180013389  call    cs:__imp_SetPropW
0x18001338f  jmp     loc_180013757
0x180013394  lea     rdx, String; "_Win32_this_"
0x18001339b  cmp     esi, 2
0x18001339e  jnz     short loc_1800133FE
0x1800133a0  call    cs:__imp_RemovePropW
0x1800133a6  mov     edx, 439h; nIDDlgItem
0x1800133ab  mov     rcx, r15; hDlg
0x1800133ae  call    cs:__imp_GetDlgItem
0x1800133b4  xor     r9d, r9d; lParam
0x1800133b7  xor     r8d, r8d; wParam
0x1800133ba  mov     rcx, rax; hWnd
0x1800133bd  mov     edx, 171h; Msg
0x1800133c2  call    cs:__imp_SendMessageW
0x1800133c8  mov     rcx, rax; hIcon
0x1800133cb  call    cs:__imp_DestroyIcon
0x1800133d1  xor     eax, eax
0x1800133d3  mov     rcx, [rbp+180h+var_30]
0x1800133da  xor     rcx, rsp; StackCookie
0x1800133dd  call    __security_check_cookie
0x1800133e2  lea     r11, [rsp+280h+var_20]
0x1800133ea  mov     rbx, [r11+38h]
0x1800133ee  mov     rsi, [r11+40h]
0x1800133f2  mov     rsp, r11
0x1800133f5  pop     r15
0x1800133f7  pop     r14
0x1800133f9  pop     r12
0x1800133fb  pop     rdi
0x1800133fc  pop     rbp
0x1800133fd  retn
0x1800133fe  call    cs:__imp_GetPropW
0x180013404  mov     r14, rax
0x180013407  sub     esi, 2
0x18001340a  jz      short loc_1800133A6
0x18001340c  sub     esi, 4Ch ; 'L'
0x18001340f  jz      loc_180013770
0x180013415  sub     esi, 0C2h
0x18001341b  jz      loc_180013754
0x180013421  cmp     esi, 1
0x180013424  jnz     short loc_1800133D1
0x180013426  movzx   ecx, di
0x180013429  mov     edx, 42Fh; nIDDlgItem
0x18001342e  sub     ecx, edx
0x180013430  jz      loc_1800136EC
0x180013436  sub     ecx, esi
0x180013438  jz      loc_180013699
0x18001343e  sub     ecx, esi
0x180013440  jz      loc_1800135F6
0x180013446  sub     ecx, esi
0x180013448  jz      loc_1800135C3
0x18001344e  sub     ecx, esi
0x180013450  jz      loc_18001352E
0x180013456  sub     ecx, 2
0x180013459  jz      short loc_1800134A5
0x18001345b  cmp     ecx, 2
0x18001345e  jnz     loc_1800133D1
0x180013464  shr     rdi, 10h
0x180013468  xor     esi, esi
0x18001346a  cmp     si, di
0x18001346d  jnz     loc_1800133D1
0x180013473  mov     edx, 437h; nIDButton
0x180013478  mov     rcx, r15; hDlg
0x18001347b  call    cs:__imp_IsDlgButtonChecked
0x180013481  mov     edx, 431h; nIDDlgItem
0x180013486  mov     rcx, r15; hDlg
0x180013489  cmp     eax, 1
0x18001348c  setz    sil
0x180013490  call    cs:__imp_GetDlgItem
0x180013496  mov     rcx, rax; hWnd
0x180013499  mov     edx, esi
0x18001349b  call    OnClickShowPassword
0x1800134a0  jmp     loc_1800133D1
0x1800134a5  shr     rdi, 10h
0x1800134a9  xor     esi, esi
0x1800134ab  test    di, di
0x1800134ae  jnz     loc_1800133D1
0x1800134b4  mov     edi, 435h
0x1800134b9  mov     rcx, r15; hDlg
0x1800134bc  mov     edx, edi; nIDDlgItem
0x1800134be  call    cs:__imp_GetDlgItem
0x1800134c4  mov     edx, edi; nIDButton
0x1800134c6  mov     rcx, r15; hDlg
0x1800134c9  mov     rbx, rax
0x1800134cc  call    cs:__imp_IsDlgButtonChecked
0x1800134d2  mov     rcx, [r14+38h]
0x1800134d6  mov     edx, esi
0x1800134d8  cmp     eax, 1
0x1800134db  setz    dl
0x1800134de  mov     [rcx+0B44h], edx
0x1800134e4  mov     rdx, r15
0x1800134e7  mov     r8, [r14+38h]
0x1800134eb  mov     rcx, [r14+30h]
0x1800134ef  mov     r8d, [r8+0B44h]
0x1800134f6  call    OnClickAllUserProfile
0x1800134fb  test    eax, eax
0x1800134fd  jnz     loc_180013766
0x180013503  mov     rax, [r14+38h]
0x180013507  xor     r9d, r9d; lParam
0x18001350a  mov     edx, 0F1h; Msg
0x18001350f  mov     rcx, rbx; hWnd
0x180013512  mov     [rax+0B44h], esi
0x180013518  mov     rax, [r14+38h]
0x18001351c  movsxd  r8, dword ptr [rax+0B44h]; wParam
0x180013523  call    cs:__imp_SendMessageW
0x180013529  jmp     loc_180013766
0x18001352e  mov     edx, 433h; nIDDlgItem
0x180013533  mov     rcx, r15; hDlg
0x180013536  call    cs:__imp_GetDlgItem
0x18001353c  shr     rdi, 10h
0x180013540  mov     esi, 200h
0x180013545  movzx   ecx, di
0x180013548  mov     r15, rax
0x18001354b  sub     cx, si
0x18001354e  mov     eax, 0FEFFh
0x180013553  test    ax, cx
0x180013556  jnz     loc_1800133D1
0x18001355c  mov     rcx, [r14+38h]
0x180013560  lea     r8d, [rsi+2]; Size
0x180013564  mov     ebx, 40Eh
0x180013569  xor     edx, edx; Val
0x18001356b  add     rcx, rbx; void *
0x18001356e  call    memset_0
0x180013573  mov     rdx, [r14+38h]
0x180013577  mov     r8d, 101h; nMaxCount
0x18001357d  add     rdx, rbx; lpString
0x180013580  mov     rcx, r15; hWnd
0x180013583  call    cs:__imp_GetWindowTextW
0x180013589  mov     rcx, [r14+38h]
0x18001358d  add     rcx, rbx; lpszCurrent
0x180013590  call    StrTrim
0x180013595  cmp     si, di
0x180013598  jnz     loc_1800133D1
0x18001359e  mov     rax, [r14+38h]
0x1800135a2  xor     esi, esi
0x1800135a4  cmp     [rax+40Eh], si
0x1800135ab  jnz     loc_1800133D1
0x1800135b1  lea     rdx, [r14+40h]; lpString
0x1800135b5  mov     rcx, r15; hWnd
0x1800135b8  call    cs:__imp_SetWindowTextW
0x1800135be  jmp     loc_1800133D1
0x1800135c3  shr     rdi, 10h
0x1800135c7  xor     esi, esi
0x1800135c9  test    di, di
0x1800135cc  jnz     loc_1800133D1
0x1800135d2  mov     edx, 432h; nIDButton
0x1800135d7  mov     rcx, r15; hDlg
0x1800135da  call    cs:__imp_IsDlgButtonChecked
0x1800135e0  mov     rcx, [r14+38h]
0x1800135e4  cmp     eax, 1
0x1800135e7  setz    sil
0x1800135eb  mov     [rcx+0B48h], esi
0x1800135f1  jmp     loc_180013766
0x1800135f6  shr     rdi, 10h
0x1800135fa  mov     eax, 300h
0x1800135ff  cmp     di, ax
0x180013602  jnz     loc_1800133D1
0x180013608  mov     edx, 431h; nIDDlgItem
0x18001360d  mov     rcx, r15; hDlg
0x180013610  call    cs:__imp_GetDlgItem
0x180013616  mov     rbx, [r14+38h]
0x18001361a  mov     r12d, 202h
0x180013620  mov     r9, rax
0x180013623  mov     edx, r12d
0x180013626  xor     esi, esi
0x180013628  lea     rcx, [rbx+91Eh]
0x18001362f  mov     [rcx], sil
0x180013632  inc     rcx
0x180013635  sub     rdx, 1
0x180013639  jnz     short loc_18001362F
0x18001363b  mov     rdx, r12
0x18001363e  lea     rax, [rsp+280h+String]
0x180013643  mov     [rax], sil
0x180013646  inc     rax
0x180013649  sub     rdx, 1
0x18001364d  jnz     short loc_180013643
0x18001364f  mov     r8d, 101h; nMaxCount
0x180013655  lea     rdx, [rsp+280h+String]; lpString
0x18001365a  mov     rcx, r9; hWnd
0x18001365d  call    cs:__imp_GetWindowTextW
0x180013663  lea     rcx, [rsp+280h+String]
0x180013668  call    EncodePasswordW
0x18001366d  lea     r8, [rsp+280h+String]; unsigned __int16 *
0x180013672  mov     edx, 101h; unsigned __int64
0x180013677  lea     rcx, [rbx+91Eh]; unsigned __int16 *
0x18001367e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013683  lea     rax, [rsp+280h+String]
0x180013688  mov     [rax], sil
0x18001368b  inc     rax
0x18001368e  sub     r12, 1
0x180013692  jnz     short loc_180013688
0x180013694  jmp     loc_180013766
0x180013699  mov     edx, 430h; nIDDlgItem
0x18001369e  mov     rcx, r15; hDlg
0x1800136a1  call    cs:__imp_GetDlgItem
0x1800136a7  mov     rsi, rax
0x1800136aa  shr     rdi, 10h
0x1800136ae  mov     eax, 300h
0x1800136b3  cmp     di, ax
0x1800136b6  jnz     loc_1800133D1
0x1800136bc  mov     rbx, [r14+38h]
0x1800136c0  xor     edx, edx; Val
0x1800136c2  mov     r8d, 202h; Size
0x1800136c8  lea     rcx, [rbx+71Ch]; void *
0x1800136cf  call    memset_0
0x1800136d4  mov     r8d, 101h; nMaxCount
0x1800136da  lea     rdx, [rbx+71Ch]; lpString
0x1800136e1  mov     rcx, rsi; hWnd
0x1800136e4  call    cs:__imp_GetWindowTextW
0x1800136ea  jmp     short loc_180013766
0x1800136ec  shr     rdi, 10h
0x1800136f0  mov     eax, 300h
0x1800136f5  cmp     di, ax
0x1800136f8  jnz     loc_1800133D1
0x1800136fe  mov     rcx, r15; hDlg
0x180013701  call    cs:__imp_GetDlgItem
0x180013707  mov     rdi, [r14+38h]
0x18001370b  xor     edx, edx; Val
0x18001370d  add     rdi, 610h
0x180013714  mov     r8d, 102h; Size
0x18001371a  mov     rcx, rdi; void *
0x18001371d  mov     rbx, rax
0x180013720  call    memset_0
0x180013725  mov     r8d, 81h; nMaxCount
0x18001372b  mov     rdx, rdi; lpString
0x18001372e  mov     rcx, rbx; hWnd
0x180013731  call    cs:__imp_GetWindowTextW
0x180013737  mov     rcx, rdi; lpszCurrent
0x18001373a  call    StrTrim
0x18001373f  xor     esi, esi
0x180013741  cmp     [rdi], si
0x180013744  setnz   sil
0x180013748  mov     [r14+244h], esi
0x18001374f  jmp     loc_18001397C
0x180013754  mov     rbx, r14
0x180013757  mov     rdx, r15; HWND
0x18001375a  mov     [rbx+18h], r15
0x18001375e  mov     rcx, rbx; this
0x180013761  call    ?InitDialogControls@CCTIConnectionInfoPage@@AEAAXPEAUHWND__@@@Z; CCTIConnectionInfoPage::InitDialogControls(HWND__ *)
0x180013766  mov     eax, 1
0x18001376b  jmp     loc_1800133D3
0x180013770  mov     eax, [rbx+10h]
0x180013773  cmp     eax, 0FFFFFF31h
0x180013778  jz      loc_180013989
0x18001377e  mov     r12d, 0FFFFFF32h
0x180013784  cmp     eax, r12d
0x180013787  jz      loc_1800133A6
0x18001378d  cmp     eax, 0FFFFFF38h
0x180013792  jz      loc_180013818
0x180013798  add     eax, 4
0x18001379b  test    eax, 0FFFFFFFDh
0x1800137a0  jnz     loc_1800133D1
0x1800137a6  lea     rdx, aIspinfo; "ISPInfo"
0x1800137ad  lea     rcx, [rbx+28h]; lpString1
0x1800137b1  call    CompareStringWrapW
0x1800137b6  xor     esi, esi
0x1800137b8  test    eax, eax
0x1800137ba  jnz     short loc_1800137E3
0x1800137bc  mov     rcx, r15; hWnd
0x1800137bf  call    cs:__imp_GetParent
0x1800137c5  lea     r9, lParam; lParam
0x1800137cc  or      r8, 0FFFFFFFFFFFFFFFFh; wParam
0x1800137d0  mov     rcx, rax; hWnd
0x1800137d3  mov     edx, 465h; Msg
0x1800137d8  call    cs:__imp_SendMessageW
0x1800137de  jmp     loc_1800133D1
0x1800137e3  lea     rdx, aDialingrules; "DialingRules"
0x1800137ea  lea     rcx, [rbx+28h]; lpString1
0x1800137ee  call    CompareStringWrapW
0x1800137f3  test    eax, eax
0x1800137f5  jnz     loc_1800133D1
0x1800137fb  mov     r9, r15; hwndOwner
0x1800137fe  mov     [rsp+280h+lpszAddressIn], rsi; lpszAddressIn
0x180013803  xor     edx, edx; dwDeviceID
0x180013805  xor     ecx, ecx; hLineApp
0x180013807  mov     r8d, 10004h; dwAPIVersion
0x18001380d  call    cs:__imp_lineTranslateDialogW
0x180013813  jmp     loc_1800133D1
  ... truncated ...
```
