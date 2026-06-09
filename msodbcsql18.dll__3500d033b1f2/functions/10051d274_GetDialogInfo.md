# GetDialogInfo

- ea: `0x10051d274`
- end: `0x10051d6e5`
- name: `GetDialogInfo`
- size: `1137`
- prototype: `__int64 __fastcall(HWND, int nIDDlgItem)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x1005190b0`

## callees

- `0x10046d140`
- `0x10051cf68`
- `0x10051cfa0`
- `0x10051d274`
- `0x10051d6ec`
- `0x100546a24`

## import_xrefs

- `USER32!SendDlgItemMessageW` at `0x10051d39d`
- `USER32!SendDlgItemMessageW` at `0x10051d3b9`
- `USER32!SendDlgItemMessageW` at `0x10051d39d`
- `USER32!SendDlgItemMessageW` at `0x10051d3b9`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d442`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d463`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d47e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d499`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d4b4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d4cf`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d4e6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d674`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d442`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d463`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d47e`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d499`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d4b4`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d4cf`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d4e6`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x10051d674`

## string_xrefs

- `0x10051d459`: `ActiveDirectoryIntegrated`
- `0x10051d435`: `ActiveDirectoryPassword`
- `0x10051d474`: `ActiveDirectoryInteractive`
- `0x10051d48f`: `ActiveDirectoryMSI`
- `0x10051d4aa`: `ActiveDirectoryServicePrincipal`

## pseudocode

```c
__int64 __fastcall GetDialogInfo(HWND a1, _QWORD *nIDDlgItem, __int64 a3, __int64 a4)
{
  CDlgATTRs *v4; // rdi
  __int64 v7; // rcx
  __int64 v8; // rdx
  int v9; // ebp
  signed int DlgItemTextW_0; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  int v13; // ebx
  const unsigned __int16 *v14; // rax
  int v15; // r9d
  const unsigned __int16 *AuthenticationModeOption; // rbp
  __int16 v17; // r14
  unsigned int AuthenticationModeValue; // eax
  __int64 v19; // rcx

  v4 = (CDlgATTRs *)(nIDDlgItem + 17);
  v7 = nIDDlgItem[18];
  v8 = *(_QWORD *)(nIDDlgItem[19] + 32LL);
  if ( *(_WORD *)(v8 + *(_QWORD *)(v7 + 56)) || (v9 = 5, *(_WORD *)(v8 + *(_QWORD *)(v7 + 32))) )
    v9 = 6;
  do
  {
    DlgItemTextW_0 = GetDlgItemTextW_0(a1, (int)nIDDlgItem, (LPWSTR)(unsigned int)v9, a4);
    v11 = DlgItemTextW_0;
    if ( DlgItemTextW_0 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v11;
      v12 = 1610761;
      goto LABEL_50;
    }
    ++v9;
  }
  while ( v9 < 12 );
  DlgItemTextW_0 = GetDlgItemTextW_0(a1, (int)nIDDlgItem, (LPWSTR)0x1D, a4);
  v11 = DlgItemTextW_0;
  if ( DlgItemTextW_0 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v11;
    v12 = 1614857;
    goto LABEL_50;
  }
  _mm_lfence();
  DlgItemTextW_0 = GetDlgItemTextW_0(a1, (int)nIDDlgItem, (LPWSTR)0x12, a4);
  v11 = DlgItemTextW_0;
  if ( DlgItemTextW_0 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v11;
    v12 = 1616905;
    goto LABEL_50;
  }
  _mm_lfence();
  DlgItemTextW_0 = GetDlgItemTextW_0(a1, (int)nIDDlgItem, (LPWSTR)0x1E, a4);
  v11 = DlgItemTextW_0;
  if ( DlgItemTextW_0 < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      return v11;
    v12 = 1618953;
    goto LABEL_50;
  }
  _mm_lfence();
  v13 = SendDlgItemMessageW(a1, 30012, 0x147u, 0, 0);
  v14 = (const unsigned __int16 *)SendDlgItemMessageW(a1, 30012, 0x150u, v13, 0);
  if ( !v14 || v13 == -1 )
  {
    _mm_lfence();
    DlgItemTextW_0 = GetDlgItemTextW_0(a1, (int)nIDDlgItem, (LPWSTR)0xC, v15);
    v11 = DlgItemTextW_0;
    if ( DlgItemTextW_0 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v11;
      v12 = 1632265;
      goto LABEL_50;
    }
  }
  else
  {
    _mm_lfence();
    DlgItemTextW_0 = CDlgATTRs::SetATTRValue(v4, 12, v14);
    v11 = DlgItemTextW_0;
    if ( DlgItemTextW_0 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v11;
      v12 = 1627145;
      goto LABEL_50;
    }
  }
  _mm_lfence();
  AuthenticationModeOption = GetAuthenticationModeOption(a1);
  v17 = 32;
  if ( _wcsicmp(AuthenticationModeOption, L"ActiveDirectoryPassword")
    && (_mm_lfence(), _wcsicmp(AuthenticationModeOption, L"ActiveDirectoryIntegrated"))
    && (_mm_lfence(), _wcsicmp(AuthenticationModeOption, L"ActiveDirectoryInteractive"))
    && (_mm_lfence(), _wcsicmp(AuthenticationModeOption, L"ActiveDirectoryMSI"))
    && (_mm_lfence(), _wcsicmp(AuthenticationModeOption, L"ActiveDirectoryServicePrincipal")) )
  {
    _mm_lfence();
    if ( !_wcsicmp(AuthenticationModeOption, L"No") || (_mm_lfence(), !_wcsicmp(AuthenticationModeOption, L"Yes")) )
    {
      _mm_lfence();
      *(_WORD *)(*((_QWORD *)v4 + 1) + 192LL) |= 1u;
      *(_WORD *)(*((_QWORD *)v4 + 1) + 912LL) &= ~1u;
      DlgItemTextW_0 = CDlgATTRs::SetATTRValue(v4, 8, AuthenticationModeOption);
      v11 = DlgItemTextW_0;
      if ( DlgItemTextW_0 < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          return v11;
        v12 = 1653769;
        goto LABEL_50;
      }
      _mm_lfence();
      *(_QWORD *)(nIDDlgItem[18] + 920LL) = 0;
      *(_QWORD *)(nIDDlgItem[18] + 928LL) = 0;
      *(_WORD *)(nIDDlgItem[18] + 912LL) |= 0x20u;
    }
  }
  else
  {
    _mm_lfence();
    *(_WORD *)(*((_QWORD *)v4 + 1) + 912LL) |= 1u;
    *(_WORD *)(*((_QWORD *)v4 + 1) + 192LL) &= ~1u;
    DlgItemTextW_0 = CDlgATTRs::SetATTRValue(v4, 38, AuthenticationModeOption);
    v11 = DlgItemTextW_0;
    if ( DlgItemTextW_0 < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return v11;
      v12 = 1643529;
      goto LABEL_50;
    }
    _mm_lfence();
    *(_QWORD *)(nIDDlgItem[18] + 200LL) = 0;
    *(_QWORD *)(nIDDlgItem[18] + 208LL) = 0;
    *(_WORD *)(nIDDlgItem[18] + 192LL) |= 0x20u;
  }
  _mm_lfence();
  AuthenticationModeValue = GetAuthenticationModeValue(v4);
  v19 = *((_QWORD *)v4 + 1);
  if ( (*(_BYTE *)(v19 + 192) & 1) == 0 || AuthenticationModeValue != 1 )
  {
    _mm_lfence();
    v19 = *((_QWORD *)v4 + 1);
    if ( (*(_BYTE *)(v19 + 912) & 1) == 0 || AuthenticationModeValue != 2 )
      v17 = 0;
  }
  *(_WORD *)(v19 + 144) &= ~0x20u;
  *(_WORD *)(v19 + 144) |= v17;
  *(_WORD *)(*((_QWORD *)v4 + 1) + 168LL) = v17 | *(_WORD *)(*((_QWORD *)v4 + 1) + 168LL) & 0xFFDF;
  if ( (*(_BYTE *)(*((_QWORD *)v4 + 1) + 120LL) & 1) != 0 )
  {
    _mm_lfence();
    if ( !_wcsicmp(
            (const wchar_t *)(*(_QWORD *)(*((_QWORD *)v4 + 2) + 32LL) + *(_QWORD *)(*((_QWORD *)v4 + 1) + 128LL)),
            &g_wszLocal) )
    {
      _mm_lfence();
      DlgItemTextW_0 = CDlgATTRs::SetATTRValue(v4, 5, L"(local)");
      v11 = DlgItemTextW_0;
      if ( DlgItemTextW_0 < 0 && (bidGblFlags & 2) != 0 )
      {
        v12 = 1674249;
LABEL_50:
        _mm_lfence();
        bidTraceHR(0, v12, (unsigned int)DlgItemTextW_0, a4);
      }
    }
  }
  return v11;
}

```

## disassembly

```asm
0x10051d274  mov     rax, rsp
0x10051d277  mov     [rax+8], rbx
0x10051d27b  mov     [rax+10h], rbp
0x10051d27f  mov     [rax+18h], rsi
0x10051d283  mov     [rax+20h], rdi
0x10051d287  push    r12
0x10051d289  push    r14
0x10051d28b  push    r15
0x10051d28d  sub     rsp, 30h
0x10051d291  lea     rdi, [rdx+88h]
0x10051d298  mov     r14, rcx
0x10051d29b  mov     rax, [rdi+10h]
0x10051d29f  mov     rsi, rdx
0x10051d2a2  mov     rcx, [rdi+8]
0x10051d2a6  xor     r15d, r15d
0x10051d2a9  mov     rdx, [rax+20h]
0x10051d2ad  mov     rax, [rcx+38h]
0x10051d2b1  cmp     [rdx+rax], r15w
0x10051d2b6  jnz     short loc_10051D2C7
0x10051d2b8  mov     rax, [rcx+20h]
0x10051d2bc  lea     ebp, [r15+5]
0x10051d2c0  cmp     [rdx+rax], r15w
0x10051d2c5  jz      short loc_10051D2CC
0x10051d2c7  mov     ebp, 6
0x10051d2cc  mov     r12d, 1
0x10051d2d2  mov     r8d, ebp; lpString
0x10051d2d5  mov     rdx, rsi; nIDDlgItem
0x10051d2d8  mov     rcx, r14; hDlg
0x10051d2db  call    GetDlgItemTextW_0
0x10051d2e0  mov     ebx, eax
0x10051d2e2  test    eax, eax
0x10051d2e4  js      loc_10051D6A9
0x10051d2ea  add     ebp, r12d
0x10051d2ed  cmp     ebp, 0Ch
0x10051d2f0  jl      short loc_10051D2D2
0x10051d2f2  mov     r8d, 1Dh; lpString
0x10051d2f8  mov     rdx, rsi; nIDDlgItem
0x10051d2fb  mov     rcx, r14; hDlg
0x10051d2fe  call    GetDlgItemTextW_0
0x10051d303  mov     ebx, eax
0x10051d305  test    eax, eax
0x10051d307  jns     short loc_10051D320
0x10051d309  test    byte ptr cs:_bidGblFlags, 2
0x10051d310  jz      loc_10051D6C4
0x10051d316  mov     edx, 18A409h
0x10051d31b  jmp     loc_10051D6B7
0x10051d320  lfence
0x10051d323  mov     r8d, 12h; lpString
0x10051d329  mov     rdx, rsi; nIDDlgItem
0x10051d32c  mov     rcx, r14; hDlg
0x10051d32f  call    GetDlgItemTextW_0
0x10051d334  mov     ebx, eax
0x10051d336  test    eax, eax
0x10051d338  jns     short loc_10051D351
0x10051d33a  test    byte ptr cs:_bidGblFlags, 2
0x10051d341  jz      loc_10051D6C4
0x10051d347  mov     edx, 18AC09h
0x10051d34c  jmp     loc_10051D6B7
0x10051d351  lfence
0x10051d354  mov     r8d, 1Eh; lpString
0x10051d35a  mov     rdx, rsi; nIDDlgItem
0x10051d35d  mov     rcx, r14; hDlg
0x10051d360  call    GetDlgItemTextW_0
0x10051d365  mov     ebx, eax
0x10051d367  test    eax, eax
0x10051d369  jns     short loc_10051D382
0x10051d36b  test    byte ptr cs:_bidGblFlags, 2
0x10051d372  jz      loc_10051D6C4
0x10051d378  mov     edx, 18B409h
0x10051d37d  jmp     loc_10051D6B7
0x10051d382  lfence
0x10051d385  mov     ebp, 753Ch
0x10051d38a  mov     [rsp+48h+lParam], r15; lParam
0x10051d38f  mov     edx, ebp; nIDDlgItem
0x10051d391  xor     r9d, r9d; wParam
0x10051d394  mov     r8d, 147h; Msg
0x10051d39a  mov     rcx, r14; hDlg
0x10051d39d  call    cs:__imp_SendDlgItemMessageW
0x10051d3a3  mov     r8d, 150h; Msg
0x10051d3a9  mov     [rsp+48h+lParam], r15; lParam
0x10051d3ae  movsxd  r9, eax; wParam
0x10051d3b1  mov     edx, ebp; nIDDlgItem
0x10051d3b3  mov     rcx, r14; hDlg
0x10051d3b6  mov     rbx, rax
0x10051d3b9  call    cs:__imp_SendDlgItemMessageW
0x10051d3bf  test    rax, rax
0x10051d3c2  jz      short loc_10051D3F9
0x10051d3c4  cmp     ebx, 0FFFFFFFFh
0x10051d3c7  jz      short loc_10051D3F9
0x10051d3c9  lfence
0x10051d3cc  mov     r8, rax; unsigned __int16 *
0x10051d3cf  mov     edx, 0Ch; int
0x10051d3d4  mov     rcx, rdi; this
0x10051d3d7  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x10051d3dc  mov     ebx, eax
0x10051d3de  test    eax, eax
0x10051d3e0  jns     short loc_10051D42A
0x10051d3e2  test    byte ptr cs:_bidGblFlags, 2
0x10051d3e9  jz      loc_10051D6C4
0x10051d3ef  mov     edx, 18D409h
0x10051d3f4  jmp     loc_10051D6B7
0x10051d3f9  lfence
0x10051d3fc  mov     r8d, 0Ch; lpString
0x10051d402  mov     rdx, rsi; nIDDlgItem
0x10051d405  mov     rcx, r14; hDlg
0x10051d408  call    GetDlgItemTextW_0
0x10051d40d  mov     ebx, eax
0x10051d40f  test    eax, eax
0x10051d411  jns     short loc_10051D42A
0x10051d413  test    byte ptr cs:_bidGblFlags, 2
0x10051d41a  jz      loc_10051D6C4
0x10051d420  mov     edx, 18E809h
0x10051d425  jmp     loc_10051D6B7
0x10051d42a  lfence
0x10051d42d  mov     rcx, r14; HWND
0x10051d430  call    ?GetAuthenticationModeOption@@YAPEBGPEAUHWND__@@@Z; GetAuthenticationModeOption(HWND__ *)
0x10051d435  lea     rdx, aActivedirector_2; "ActiveDirectoryPassword"
0x10051d43c  mov     rcx, rax; String1
0x10051d43f  mov     rbp, rax
0x10051d442  call    cs:__imp__wcsicmp
0x10051d448  mov     r14d, 20h ; ' '
0x10051d44e  test    eax, eax
0x10051d450  jz      loc_10051D570
0x10051d456  lfence
0x10051d459  lea     rdx, aActivedirector_1; "ActiveDirectoryIntegrated"
0x10051d460  mov     rcx, rbp; String1
0x10051d463  call    cs:__imp__wcsicmp
0x10051d469  test    eax, eax
0x10051d46b  jz      loc_10051D570
0x10051d471  lfence
0x10051d474  lea     rdx, aActivedirector; "ActiveDirectoryInteractive"
0x10051d47b  mov     rcx, rbp; String1
0x10051d47e  call    cs:__imp__wcsicmp
0x10051d484  test    eax, eax
0x10051d486  jz      loc_10051D570
0x10051d48c  lfence
0x10051d48f  lea     rdx, aActivedirector_3; "ActiveDirectoryMSI"
0x10051d496  mov     rcx, rbp; String1
0x10051d499  call    cs:__imp__wcsicmp
0x10051d49f  test    eax, eax
0x10051d4a1  jz      loc_10051D570
0x10051d4a7  lfence
0x10051d4aa  lea     rdx, aActivedirector_0; "ActiveDirectoryServicePrincipal"
0x10051d4b1  mov     rcx, rbp; String1
0x10051d4b4  call    cs:__imp__wcsicmp
0x10051d4ba  test    eax, eax
0x10051d4bc  jz      loc_10051D570
0x10051d4c2  lfence
0x10051d4c5  lea     rdx, aNo; "No"
0x10051d4cc  mov     rcx, rbp; String1
0x10051d4cf  call    cs:__imp__wcsicmp
0x10051d4d5  test    eax, eax
0x10051d4d7  jz      short loc_10051D4F4
0x10051d4d9  lfence
0x10051d4dc  lea     rdx, aYes_1; "Yes"
0x10051d4e3  mov     rcx, rbp; String1
0x10051d4e6  call    cs:__imp__wcsicmp
0x10051d4ec  test    eax, eax
0x10051d4ee  jnz     loc_10051D5EA
0x10051d4f4  lfence
0x10051d4f7  mov     rax, [rdi+8]
0x10051d4fb  mov     ecx, 0FFFEh
0x10051d500  mov     r8, rbp; unsigned __int16 *
0x10051d503  mov     edx, 8; int
0x10051d508  or      [rax+0C0h], r12w
0x10051d510  mov     rax, [rdi+8]
0x10051d514  and     [rax+390h], cx
0x10051d51b  mov     rcx, rdi; this
0x10051d51e  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x10051d523  mov     ebx, eax
0x10051d525  test    eax, eax
0x10051d527  jns     short loc_10051D540
0x10051d529  test    byte ptr cs:_bidGblFlags, 2
0x10051d530  jz      loc_10051D6C4
0x10051d536  mov     edx, 193C09h
0x10051d53b  jmp     loc_10051D6B7
0x10051d540  lfence
0x10051d543  mov     rax, [rsi+90h]
0x10051d54a  mov     [rax+398h], r15
0x10051d551  mov     rax, [rsi+90h]
0x10051d558  mov     [rax+3A0h], r15
0x10051d55f  mov     rax, [rsi+90h]
0x10051d566  or      [rax+390h], r14w
0x10051d56e  jmp     short loc_10051D5EA
0x10051d570  lfence
0x10051d573  mov     rax, [rdi+8]
0x10051d577  mov     ecx, 0FFFEh
0x10051d57c  mov     r8, rbp; unsigned __int16 *
0x10051d57f  mov     edx, 26h ; '&'; int
0x10051d584  or      [rax+390h], r12w
0x10051d58c  mov     rax, [rdi+8]
0x10051d590  and     [rax+0C0h], cx
0x10051d597  mov     rcx, rdi; this
0x10051d59a  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x10051d59f  mov     ebx, eax
0x10051d5a1  test    eax, eax
0x10051d5a3  jns     short loc_10051D5BC
0x10051d5a5  test    byte ptr cs:_bidGblFlags, 2
0x10051d5ac  jz      loc_10051D6C4
0x10051d5b2  mov     edx, 191409h
0x10051d5b7  jmp     loc_10051D6B7
0x10051d5bc  lfence
0x10051d5bf  mov     rax, [rsi+90h]
0x10051d5c6  mov     [rax+0C8h], r15
0x10051d5cd  mov     rax, [rsi+90h]
0x10051d5d4  mov     [rax+0D0h], r15
0x10051d5db  mov     rax, [rsi+90h]
0x10051d5e2  or      [rax+0C0h], r14w
0x10051d5ea  lfence
0x10051d5ed  mov     rcx, rdi; struct CDlgATTRs *
0x10051d5f0  call    ?GetAuthenticationModeValue@@YAKAEAVCDlgATTRs@@@Z; GetAuthenticationModeValue(CDlgATTRs &)
0x10051d5f5  mov     rcx, [rdi+8]
0x10051d5f9  test    [rcx+0C0h], r12b
0x10051d600  jz      short loc_10051D607
0x10051d602  cmp     eax, r12d
0x10051d605  jz      short loc_10051D620
0x10051d607  lfence
0x10051d60a  mov     rcx, [rdi+8]
0x10051d60e  test    [rcx+390h], r12b
0x10051d615  jz      short loc_10051D61C
0x10051d617  cmp     eax, 2
0x10051d61a  jz      short loc_10051D620
0x10051d61c  movzx   r14d, r15w
0x10051d620  mov     edx, 0FFDFh
0x10051d625  and     [rcx+90h], dx
0x10051d62c  or      [rcx+90h], r14w
0x10051d634  mov     rcx, [rdi+8]
0x10051d638  movzx   eax, word ptr [rcx+0A8h]
0x10051d63f  and     ax, dx
0x10051d642  or      ax, r14w
0x10051d646  mov     [rcx+0A8h], ax
0x10051d64d  mov     rax, [rdi+8]
0x10051d651  test    [rax+78h], r12b
0x10051d655  jz      short loc_10051D6C4
0x10051d657  lfence
0x10051d65a  mov     rax, [rdi+8]
0x10051d65e  lea     rdx, ?g_wszLocal@@3PAGA; String2
0x10051d665  mov     r8, [rdi+10h]
0x10051d669  mov     rcx, [rax+80h]
0x10051d670  add     rcx, [r8+20h]; String1
0x10051d674  call    cs:__imp__wcsicmp
0x10051d67a  test    eax, eax
0x10051d67c  jnz     short loc_10051D6C4
0x10051d67e  lfence
0x10051d681  lea     r8, aLocal; "(local)"
0x10051d688  mov     rcx, rdi; this
0x10051d68b  lea     edx, [rax+5]; int
0x10051d68e  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x10051d693  mov     ebx, eax
0x10051d695  test    eax, eax
0x10051d697  jns     short loc_10051D6C4
0x10051d699  test    byte ptr cs:_bidGblFlags, 2
0x10051d6a0  jz      short loc_10051D6C4
0x10051d6a2  mov     edx, 198C09h
0x10051d6a7  jmp     short loc_10051D6B7
0x10051d6a9  test    byte ptr cs:_bidGblFlags, 2
0x10051d6b0  jz      short loc_10051D6C4
0x10051d6b2  mov     edx, 189409h
0x10051d6b7  lfence
0x10051d6ba  mov     r8d, eax
0x10051d6bd  xor     ecx, ecx
0x10051d6bf  call    _bidTraceHR
0x10051d6c4  mov     rbp, [rsp+48h+arg_8]
0x10051d6c9  mov     eax, ebx
0x10051d6cb  mov     rbx, [rsp+48h+arg_0]
0x10051d6d0  mov     rsi, [rsp+48h+arg_10]
0x10051d6d5  mov     rdi, [rsp+48h+arg_18]
0x10051d6da  add     rsp, 30h
0x10051d6de  pop     r15
0x10051d6e0  pop     r14
0x10051d6e2  pop     r12
0x10051d6e4  retn
```
