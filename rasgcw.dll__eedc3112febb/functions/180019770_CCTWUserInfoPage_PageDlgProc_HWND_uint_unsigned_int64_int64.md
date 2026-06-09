# CCTWUserInfoPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180019770`
- end: `0x180019bea`
- name: `?PageDlgProc@CCTWUserInfoPage@@CAHPEAUHWND__@@I_K_J@Z`
- size: `1146`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x180010c38`
- `0x180011ae8`
- `0x180011dd4`
- `0x1800195a4`
- `0x180019770`
- `0x180019bf0`
- `0x18002b970`
- `0x18002bbb0`
- `0x18002be68`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `USER32!GetPropW` at `0x1800197e9`
- `USER32!GetPropW` at `0x1800197e9`
- `USER32!RemovePropW` at `0x1800197de`
- `USER32!RemovePropW` at `0x1800197de`
- `USER32!SetWindowTextW` at `0x180019ae4`
- `USER32!SetWindowTextW` at `0x180019b41`
- `USER32!SetWindowTextW` at `0x180019b74`
- `USER32!SetWindowTextW` at `0x180019ae4`
- `USER32!SetWindowTextW` at `0x180019b41`
- `USER32!SetWindowTextW` at `0x180019b74`
- `USER32!IsDlgButtonChecked` at `0x1800198b7`
- `USER32!IsDlgButtonChecked` at `0x1800198ea`
- `USER32!IsDlgButtonChecked` at `0x1800198b7`
- `USER32!IsDlgButtonChecked` at `0x1800198ea`
- `USER32!SetPropW` at `0x1800197c7`
- `USER32!SetPropW` at `0x1800197c7`
- `USER32!GetDlgItem` at `0x180019845`
- `USER32!GetDlgItem` at `0x1800198ff`
- `USER32!GetDlgItem` at `0x18001992e`
- `USER32!GetDlgItem` at `0x1800199b8`
- `USER32!GetDlgItem` at `0x180019ad4`
- `USER32!GetDlgItem` at `0x180019b33`
- `USER32!GetDlgItem` at `0x180019b64`
- `USER32!GetDlgItem` at `0x180019845`
- `USER32!GetDlgItem` at `0x1800198ff`
- `USER32!GetDlgItem` at `0x18001992e`
- `USER32!GetDlgItem` at `0x1800199b8`
- `USER32!GetDlgItem` at `0x180019ad4`
- `USER32!GetDlgItem` at `0x180019b33`
- `USER32!GetDlgItem` at `0x180019b64`
- `USER32!SendMessageW` at `0x180019ab4`
- `USER32!SendMessageW` at `0x180019ab4`
- `USER32!GetParent` at `0x180019aa0`
- `USER32!GetParent` at `0x180019aa0`
- `USER32!GetWindowTextW` at `0x180019889`
- `USER32!GetWindowTextW` at `0x180019979`
- `USER32!GetWindowTextW` at `0x1800199fa`
- `USER32!GetWindowTextW` at `0x180019889`
- `USER32!GetWindowTextW` at `0x180019979`
- `USER32!GetWindowTextW` at `0x1800199fa`

## pseudocode

```c
__int64 __fastcall CCTWUserInfoPage::PageDlgProc(HWND a1, int a2, __int64 a3, char *a4)
{
  char *v4; // rbx
  char *PropW; // rax
  CCTWUserInfoPage *v9; // r14
  int v10; // edi
  int v11; // edi
  HWND v12; // rax
  __int64 v13; // rbx
  int v14; // edi
  HWND v15; // rax
  HWND v16; // rax
  __int64 v17; // rbx
  WCHAR *v18; // rcx
  __int64 v19; // rsi
  HWND v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rdx
  _BYTE *v23; // rax
  WCHAR *v24; // rax
  HWND v25; // r13
  __int64 v26; // rbx
  int valid; // eax
  char *v29; // r12
  LPARAM StringPcch; // rbx
  HWND Parent; // rax
  __int64 v32; // rbx
  HWND DlgItem; // rax
  __int64 v34; // rbx
  __int64 v35; // rsi
  HWND v36; // rax
  WCHAR *v37; // rax
  __int64 v38; // rbx
  HWND v39; // rax
  __int64 v40; // rax
  __int64 v41; // rsi
  _BYTE *v42; // rax
  WCHAR String[264]; // [rsp+30h] [rbp-D0h] BYREF

  v4 = a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = (char *)*((_QWORD *)a4 + 6);
    SetPropW(a1, L"_Win32_this_", v4);
    goto LABEL_36;
  }
  if ( a2 == 2 )
  {
    RemovePropW(a1, L"_Win32_this_");
    return 0;
  }
  PropW = (char *)GetPropW(a1, L"_Win32_this_");
  v9 = (CCTWUserInfoPage *)PropW;
  v10 = a2 - 78;
  if ( !v10 )
  {
    if ( *((_DWORD *)v4 + 4) == -207 )
    {
      v40 = *((_QWORD *)PropW + 5);
      if ( !*(_WORD *)(v40 + 1820) )
      {
        v41 = 514;
        v42 = (_BYTE *)(v40 + 2334);
        do
        {
          *v42++ = 0;
          --v41;
        }
        while ( v41 );
      }
      *(_DWORD *)(*((_QWORD *)v9 + 5) + 4952LL) = 1;
      return 0;
    }
    if ( *((_DWORD *)v4 + 4) != -200 )
      return 0;
    v29 = PropW + 40;
    StringPcch = PszLoadStringPcch(hInst);
    Parent = GetParent(a1);
    SendMessageW(Parent, 0x489u, 0, StringPcch);
    if ( a3 == 4294967090LL )
    {
      v32 = *(_QWORD *)v29;
      DlgItem = GetDlgItem(a1, 1031);
      SetWindowTextW(DlgItem, (LPCWSTR)(v32 + 1820));
      v34 = *(_QWORD *)v29;
      if ( *(_WORD *)(*(_QWORD *)v29 + 2334LL) )
      {
        v35 = 514;
        memset_0(String, 0, 0x202u);
        StringCchCopyW(String, 0x101u, (unsigned __int16 *)(v34 + 2334));
        EncodePasswordW((__int16 *)String);
        v36 = GetDlgItem(a1, 1032);
        SetWindowTextW(v36, String);
        v37 = String;
        do
        {
          *(_BYTE *)v37 = 0;
          v37 = (WCHAR *)((char *)v37 + 1);
          --v35;
        }
        while ( v35 );
      }
      v38 = *(_QWORD *)v29;
      v39 = GetDlgItem(a1, 1038);
      SetWindowTextW(v39, (LPCWSTR)(v38 + 2848));
    }
LABEL_45:
    CCTWUserInfoPage::UpdateDialogControls(v9, a1);
    return 1;
  }
  v11 = v10 - 194;
  if ( !v11 )
  {
    v4 = PropW;
LABEL_36:
    *((_QWORD *)v4 + 4) = a1;
    CCTWUserInfoPage::InitDialogControls((CCTWUserInfoPage *)v4, a1);
    return 1;
  }
  if ( v11 != 1 )
    return 0;
  if ( (unsigned __int16)a3 == 1031 )
  {
    v25 = GetDlgItem(a1, 1031);
    if ( WORD1(a3) != 768 )
      return 0;
    v26 = *((_QWORD *)v9 + 5);
    memset_0((void *)(v26 + 1820), 0, 0x202u);
    GetWindowTextW(v25, (LPWSTR)(v26 + 1820), 257);
    StrTrim((LPCWSTR)(v26 + 1820));
    if ( !*(_DWORD *)(v26 + 1812) || *(_WORD *)(v26 + 1820) )
      valid = IsValidUserName(v25, (wchar_t *)(v26 + 1820));
    else
      valid = 1;
    *((_DWORD *)v9 + 12) = valid;
    goto LABEL_45;
  }
  if ( (unsigned __int16)a3 != 1032 )
  {
    switch ( (unsigned __int16)a3 )
    {
      case 0x409u:
        if ( !WORD1(a3) )
        {
          IsDlgButtonChecked(a1, 1033);
          v15 = GetDlgItem(a1, 1032);
          OnClickShowPassword(v15);
        }
        return 0;
      case 0x40Au:
        v14 = 0;
        if ( WORD1(a3) )
          return 0;
        LOBYTE(v14) = IsDlgButtonChecked(a1, 1034) == 1;
        *(_DWORD *)(*((_QWORD *)v9 + 5) + 2888LL) = v14;
        break;
      case 0x40Eu:
        v12 = GetDlgItem(a1, 1038);
        if ( WORD1(a3) != 768 )
          return 0;
        v13 = *((_QWORD *)v9 + 5);
        *(_OWORD *)(v13 + 2848) = 0;
        *(_OWORD *)(v13 + 2864) = 0;
        *(_WORD *)(v13 + 2880) = 0;
        GetWindowTextW(v12, (LPWSTR)(v13 + 2848), 17);
        StrTrim((LPCWSTR)(v13 + 2848));
        break;
      default:
        return 0;
    }
    return 1;
  }
  if ( WORD1(a3) == 768 )
  {
    v16 = GetDlgItem(a1, 1032);
    v17 = *((_QWORD *)v9 + 5);
    v18 = String;
    v19 = 514;
    v20 = v16;
    v21 = 514;
    do
    {
      *(_BYTE *)v18 = 0;
      v18 = (WCHAR *)((char *)v18 + 1);
      --v21;
    }
    while ( v21 );
    v22 = 514;
    v23 = (_BYTE *)(v17 + 2334);
    do
    {
      *v23++ = 0;
      --v22;
    }
    while ( v22 );
    GetWindowTextW(v20, String, 257);
    EncodePasswordW((__int16 *)String);
    StringCchCopyW((unsigned __int16 *)(v17 + 2334), 0x101u, String);
    v24 = String;
    do
    {
      *(_BYTE *)v24 = 0;
      v24 = (WCHAR *)((char *)v24 + 1);
      --v19;
    }
    while ( v19 );
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180019770  mov     [rsp-8+arg_8], rbx
0x180019775  push    rbp
0x180019776  push    rsi
0x180019777  push    rdi
0x180019778  push    r12
0x18001977a  push    r13
0x18001977c  push    r14
0x18001977e  push    r15
0x180019780  lea     rbp, [rsp-150h]
0x180019788  sub     rsp, 250h
0x18001978f  mov     rax, cs:__security_cookie
0x180019796  xor     rax, rsp
0x180019799  mov     [rbp+180h+var_40], rax
0x1800197a0  mov     rbx, r9
0x1800197a3  mov     rsi, r8
0x1800197a6  mov     edi, edx
0x1800197a8  mov     r15, rcx
0x1800197ab  cmp     edx, 110h
0x1800197b1  jnz     short loc_1800197D2
0x1800197b3  cmp     dword ptr [r9], 68h ; 'h'
0x1800197b7  jnz     short loc_1800197BD
0x1800197b9  mov     rbx, [r9+30h]
0x1800197bd  mov     r8, rbx; hData
0x1800197c0  lea     rdx, aWin32This_4; "_Win32_this_"
0x1800197c7  call    cs:__imp_SetPropW
0x1800197cd  jmp     loc_180019A35
0x1800197d2  lea     rdx, aWin32This_4; "_Win32_this_"
0x1800197d9  cmp     edi, 2
0x1800197dc  jnz     short loc_1800197E9
0x1800197de  call    cs:__imp_RemovePropW
0x1800197e4  jmp     loc_180019BBE
0x1800197e9  call    cs:__imp_GetPropW
0x1800197ef  mov     r14, rax
0x1800197f2  sub     edi, 4Eh ; 'N'
0x1800197f5  jz      loc_180019A4E
0x1800197fb  sub     edi, 0C2h
0x180019801  jz      loc_180019A32
0x180019807  cmp     edi, 1
0x18001980a  jnz     loc_180019BBE
0x180019810  movzx   ecx, si
0x180019813  mov     edx, 407h; nIDDlgItem
0x180019818  sub     ecx, edx
0x18001981a  jz      loc_1800199B5
0x180019820  sub     ecx, edi
0x180019822  jz      loc_180019914
0x180019828  sub     ecx, edi
0x18001982a  jz      loc_1800198D3
0x180019830  sub     ecx, edi
0x180019832  jz      short loc_1800198A0
0x180019834  cmp     ecx, 4
0x180019837  jnz     loc_180019BBE
0x18001983d  mov     edx, 40Eh; nIDDlgItem
0x180019842  mov     rcx, r15; hDlg
0x180019845  call    cs:__imp_GetDlgItem
0x18001984b  mov     ecx, 300h
0x180019850  shr     rsi, 10h
0x180019854  cmp     si, cx
0x180019857  jnz     loc_180019BBE
0x18001985d  mov     rbx, [r14+28h]
0x180019861  lea     r8d, [rdi+10h]; nMaxCount
0x180019865  xorps   xmm0, xmm0
0x180019868  xor     ecx, ecx
0x18001986a  movups  xmmword ptr [rbx+0B20h], xmm0
0x180019871  lea     rdx, [rbx+0B20h]; lpString
0x180019878  movups  xmmword ptr [rbx+0B30h], xmm0
0x18001987f  mov     [rbx+0B40h], cx
0x180019886  mov     rcx, rax; hWnd
0x180019889  call    cs:__imp_GetWindowTextW
0x18001988f  lea     rcx, [rbx+0B20h]; lpszCurrent
0x180019896  call    StrTrim
0x18001989b  jmp     loc_180019A44
0x1800198a0  shr     rsi, 10h
0x1800198a4  xor     edi, edi
0x1800198a6  test    si, si
0x1800198a9  jnz     loc_180019BBE
0x1800198af  mov     edx, 40Ah; nIDButton
0x1800198b4  mov     rcx, r15; hDlg
0x1800198b7  call    cs:__imp_IsDlgButtonChecked
0x1800198bd  cmp     eax, 1
0x1800198c0  mov     rax, [r14+28h]
0x1800198c4  setz    dil
0x1800198c8  mov     [rax+0B48h], edi
0x1800198ce  jmp     loc_180019A44
0x1800198d3  shr     rsi, 10h
0x1800198d7  xor     edi, edi
0x1800198d9  cmp     di, si
0x1800198dc  jnz     loc_180019BBE
0x1800198e2  mov     edx, 409h; nIDButton
0x1800198e7  mov     rcx, r15; hDlg
0x1800198ea  call    cs:__imp_IsDlgButtonChecked
0x1800198f0  mov     edx, 408h; nIDDlgItem
0x1800198f5  mov     rcx, r15; hDlg
0x1800198f8  cmp     eax, 1
0x1800198fb  setz    dil
0x1800198ff  call    cs:__imp_GetDlgItem
0x180019905  mov     rcx, rax; hWnd
0x180019908  mov     edx, edi
0x18001990a  call    OnClickShowPassword
0x18001990f  jmp     loc_180019BBE
0x180019914  shr     rsi, 10h
0x180019918  mov     ecx, 300h
0x18001991d  cmp     si, cx
0x180019920  jnz     loc_180019BBE
0x180019926  mov     edx, 408h; nIDDlgItem
0x18001992b  mov     rcx, r15; hDlg
0x18001992e  call    cs:__imp_GetDlgItem
0x180019934  mov     rbx, [r14+28h]
0x180019938  lea     rcx, [rsp+280h+String]
0x18001993d  mov     esi, 202h
0x180019942  mov     r9, rax
0x180019945  mov     edx, esi
0x180019947  xor     edi, edi
0x180019949  mov     [rcx], dil
0x18001994c  inc     rcx
0x18001994f  sub     rdx, 1
0x180019953  jnz     short loc_180019949
0x180019955  mov     rdx, rsi
0x180019958  lea     rax, [rbx+91Eh]
0x18001995f  mov     [rax], dil
0x180019962  inc     rax
0x180019965  sub     rdx, 1
0x180019969  jnz     short loc_18001995F
0x18001996b  mov     r8d, 101h; nMaxCount
0x180019971  lea     rdx, [rsp+280h+String]; lpString
0x180019976  mov     rcx, r9; hWnd
0x180019979  call    cs:__imp_GetWindowTextW
0x18001997f  lea     rcx, [rsp+280h+String]
0x180019984  call    EncodePasswordW
0x180019989  lea     r8, [rsp+280h+String]; unsigned __int16 *
0x18001998e  mov     edx, 101h; unsigned __int64
0x180019993  lea     rcx, [rbx+91Eh]; unsigned __int16 *
0x18001999a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001999f  lea     rax, [rsp+280h+String]
0x1800199a4  mov     [rax], dil
0x1800199a7  inc     rax
0x1800199aa  sub     rsi, 1
0x1800199ae  jnz     short loc_1800199A4
0x1800199b0  jmp     loc_180019A44
0x1800199b5  mov     rcx, r15; hDlg
0x1800199b8  call    cs:__imp_GetDlgItem
0x1800199be  mov     ecx, 300h
0x1800199c3  shr     rsi, 10h
0x1800199c7  mov     r13, rax
0x1800199ca  cmp     si, cx
0x1800199cd  jnz     loc_180019BBE
0x1800199d3  mov     rbx, [r14+28h]
0x1800199d7  xor     edx, edx; Val
0x1800199d9  mov     r8d, 202h; Size
0x1800199df  lea     r12, [rbx+71Ch]
0x1800199e6  mov     rcx, r12; void *
0x1800199e9  call    memset_0
0x1800199ee  mov     r8d, 101h; nMaxCount
0x1800199f4  mov     rdx, r12; lpString
0x1800199f7  mov     rcx, r13; hWnd
0x1800199fa  call    cs:__imp_GetWindowTextW
0x180019a00  mov     rcx, r12; lpszCurrent
0x180019a03  call    StrTrim
0x180019a08  xor     edi, edi
0x180019a0a  cmp     [rbx+714h], edi
0x180019a10  jz      short loc_180019A1E
0x180019a12  cmp     [r12], di
0x180019a17  jnz     short loc_180019A1E
0x180019a19  lea     eax, [rdi+1]
0x180019a1c  jmp     short loc_180019A29
0x180019a1e  mov     rdx, r12; String
0x180019a21  mov     rcx, r13; hWnd
0x180019a24  call    IsValidUserName
0x180019a29  mov     [r14+30h], eax
0x180019a2d  jmp     loc_180019B7A
0x180019a32  mov     rbx, r14
0x180019a35  mov     rdx, r15; HWND
0x180019a38  mov     [rbx+20h], r15
0x180019a3c  mov     rcx, rbx; this
0x180019a3f  call    ?InitDialogControls@CCTWUserInfoPage@@AEAAXPEAUHWND__@@@Z; CCTWUserInfoPage::InitDialogControls(HWND__ *)
0x180019a44  mov     eax, 1
0x180019a49  jmp     loc_180019BC0
0x180019a4e  cmp     dword ptr [rbx+10h], 0FFFFFF31h
0x180019a55  jz      loc_180019B8A
0x180019a5b  cmp     dword ptr [rbx+10h], 0FFFFFF38h
0x180019a62  jnz     loc_180019BBE
0x180019a68  mov     rcx, cs:hInst; hModule
0x180019a6f  lea     r12, [rax+28h]
0x180019a73  mov     rax, [r12]
0x180019a77  lea     r8, [rsp+280h+var_260]
0x180019a7c  xor     edi, edi
0x180019a7e  mov     [rsp+280h+var_260], edi
0x180019a82  mov     edx, [rax+714h]
0x180019a88  neg     edx
0x180019a8a  sbb     edx, edx
0x180019a8c  and     edx, 2
0x180019a8f  add     edx, 0BFDh
0x180019a95  call    PszLoadStringPcch
0x180019a9a  mov     rcx, r15; hWnd
0x180019a9d  mov     rbx, rax
0x180019aa0  call    cs:__imp_GetParent
0x180019aa6  mov     r9, rbx; lParam
0x180019aa9  xor     r8d, r8d; wParam
0x180019aac  mov     rcx, rax; hWnd
0x180019aaf  mov     edx, 489h; Msg
0x180019ab4  call    cs:__imp_SendMessageW
0x180019aba  mov     eax, 0FFFFFF32h
0x180019abf  cmp     rsi, rax
0x180019ac2  jnz     loc_180019B7A
0x180019ac8  mov     rbx, [r12]
0x180019acc  mov     edx, 407h; nIDDlgItem
0x180019ad1  mov     rcx, r15; hDlg
0x180019ad4  call    cs:__imp_GetDlgItem
0x180019ada  mov     rcx, rax; hWnd
0x180019add  lea     rdx, [rbx+71Ch]; lpString
0x180019ae4  call    cs:__imp_SetWindowTextW
0x180019aea  mov     rbx, [r12]
0x180019aee  cmp     [rbx+91Eh], di
0x180019af5  jz      short loc_180019B58
0x180019af7  mov     esi, 202h
0x180019afc  lea     rcx, [rsp+280h+String]; void *
0x180019b01  mov     r8d, esi; Size
0x180019b04  xor     edx, edx; Val
0x180019b06  call    memset_0
0x180019b0b  lea     r8, [rbx+91Eh]; unsigned __int16 *
0x180019b12  mov     edx, 101h; unsigned __int64
0x180019b17  lea     rcx, [rsp+280h+String]; unsigned __int16 *
0x180019b1c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019b21  lea     rcx, [rsp+280h+String]
0x180019b26  call    EncodePasswordW
0x180019b2b  mov     edx, 408h; nIDDlgItem
0x180019b30  mov     rcx, r15; hDlg
0x180019b33  call    cs:__imp_GetDlgItem
0x180019b39  mov     rcx, rax; hWnd
0x180019b3c  lea     rdx, [rsp+280h+String]; lpString
0x180019b41  call    cs:__imp_SetWindowTextW
0x180019b47  lea     rax, [rsp+280h+String]
0x180019b4c  mov     [rax], dil
0x180019b4f  inc     rax
0x180019b52  sub     rsi, 1
0x180019b56  jnz     short loc_180019B4C
0x180019b58  mov     rbx, [r12]
0x180019b5c  mov     edx, 40Eh; nIDDlgItem
0x180019b61  mov     rcx, r15; hDlg
0x180019b64  call    cs:__imp_GetDlgItem
0x180019b6a  mov     rcx, rax; hWnd
0x180019b6d  lea     rdx, [rbx+0B20h]; lpString
0x180019b74  call    cs:__imp_SetWindowTextW
0x180019b7a  mov     rdx, r15; HWND
0x180019b7d  mov     rcx, r14; this
0x180019b80  call    ?UpdateDialogControls@CCTWUserInfoPage@@AEAAXPEAUHWND__@@@Z; CCTWUserInfoPage::UpdateDialogControls(HWND__ *)
0x180019b85  jmp     loc_180019A44
0x180019b8a  mov     rax, [rax+28h]
0x180019b8e  xor     edi, edi
0x180019b90  cmp     [rax+71Ch], di
0x180019b97  jnz     short loc_180019BB0
0x180019b99  mov     esi, 202h
0x180019b9e  add     rax, 91Eh
0x180019ba4  mov     [rax], dil
0x180019ba7  inc     rax
0x180019baa  sub     rsi, 1
0x180019bae  jnz     short loc_180019BA4
0x180019bb0  mov     rax, [r14+28h]
0x180019bb4  mov     dword ptr [rax+1358h], 1
0x180019bbe  xor     eax, eax
0x180019bc0  mov     rcx, [rbp+180h+var_40]
0x180019bc7  xor     rcx, rsp; StackCookie
0x180019bca  call    __security_check_cookie
0x180019bcf  mov     rbx, [rsp+280h+arg_8]
0x180019bd7  add     rsp, 250h
0x180019bde  pop     r15
0x180019be0  pop     r14
0x180019be2  pop     r13
0x180019be4  pop     r12
0x180019be6  pop     rdi
0x180019be7  pop     rsi
0x180019be8  pop     rbp
0x180019be9  retn
```
