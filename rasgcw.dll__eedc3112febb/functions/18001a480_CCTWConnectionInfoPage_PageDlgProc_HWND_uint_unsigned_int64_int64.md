# CCTWConnectionInfoPage::PageDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18001a480`
- end: `0x18001a948`
- name: `?PageDlgProc@CCTWConnectionInfoPage@@CAHPEAUHWND__@@I_K_J@Z`
- size: `1224`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010c38`
- `0x180011940`
- `0x180011bc0`
- `0x18001a134`
- `0x18001a480`
- `0x18001aa54`
- `0x18002bbb0`
- `0x18002c1b0`
- `0x18002f382`

## import_xrefs

- `USER32!GetPropW` at `0x18001a516`
- `USER32!GetPropW` at `0x18001a516`
- `USER32!RemovePropW` at `0x18001a4d0`
- `USER32!RemovePropW` at `0x18001a4d0`
- `USER32!SetWindowTextW` at `0x18001a78f`
- `USER32!SetWindowTextW` at `0x18001a8cb`
- `USER32!SetWindowTextW` at `0x18001a78f`
- `USER32!SetWindowTextW` at `0x18001a8cb`
- `USER32!DestroyIcon` at `0x18001a4fb`
- `USER32!DestroyIcon` at `0x18001a4fb`
- `USER32!IsDlgButtonChecked` at `0x18001a582`
- `USER32!IsDlgButtonChecked` at `0x18001a5c7`
- `USER32!IsDlgButtonChecked` at `0x18001a640`
- `USER32!IsDlgButtonChecked` at `0x18001a672`
- `USER32!IsDlgButtonChecked` at `0x18001a582`
- `USER32!IsDlgButtonChecked` at `0x18001a5c7`
- `USER32!IsDlgButtonChecked` at `0x18001a640`
- `USER32!IsDlgButtonChecked` at `0x18001a672`
- `USER32!SetPropW` at `0x18001a4b9`
- `USER32!SetPropW` at `0x18001a4b9`
- `USER32!SetWindowLongW` at `0x18001a91e`
- `USER32!SetWindowLongW` at `0x18001a91e`
- `USER32!GetDlgItem` at `0x18001a4de`
- `USER32!GetDlgItem` at `0x18001a5b8`
- `USER32!GetDlgItem` at `0x18001a695`
- `USER32!GetDlgItem` at `0x18001a709`
- `USER32!GetDlgItem` at `0x18001a893`
- `USER32!GetDlgItem` at `0x18001a4de`
- `USER32!GetDlgItem` at `0x18001a5b8`
- `USER32!GetDlgItem` at `0x18001a695`
- `USER32!GetDlgItem` at `0x18001a709`
- `USER32!GetDlgItem` at `0x18001a893`
- `USER32!SendMessageW` at `0x18001a4f2`
- `USER32!SendMessageW` at `0x18001a61e`
- `USER32!SendMessageW` at `0x18001a4f2`
- `USER32!SendMessageW` at `0x18001a61e`
- `USER32!GetWindowTextW` at `0x18001a6d9`
- `USER32!GetWindowTextW` at `0x18001a759`
- `USER32!GetWindowTextW` at `0x18001a6d9`
- `USER32!GetWindowTextW` at `0x18001a759`
- `rtutils!TracePrintfExA` at `0x18001a90f`
- `rtutils!TracePrintfExA` at `0x18001a90f`
- `WinSCard!SCardReleaseContext` at `0x18001a86f`
- `WinSCard!SCardReleaseContext` at `0x18001a86f`
- `WinSCard!SCardEstablishContext` at `0x18001a838`
- `WinSCard!SCardEstablishContext` at `0x18001a838`
- `WinSCard!SCardListReadersW` at `0x18001a851`
- `WinSCard!SCardListReadersW` at `0x18001a851`
- `TAPI32!lineTranslateDialogW` at `0x18001a80f`
- `TAPI32!lineTranslateDialogW` at `0x18001a80f`

## pseudocode

```c
__int64 __fastcall CCTWConnectionInfoPage::PageDlgProc(HWND a1, int a2, unsigned __int64 a3, WCHAR *a4)
{
  WCHAR *v4; // r14
  HWND DlgItem; // rax
  HICON v9; // rax
  HANDLE PropW; // rax
  HANDLE v12; // rsi
  int v13; // ebx
  int v14; // ebx
  int v15; // ebx
  int v16; // ebx
  HWND v17; // rdi
  int v18; // ebx
  int v19; // ebx
  HWND v20; // rbx
  unsigned __int64 v21; // rdi
  HWND v22; // rbp
  int v23; // eax
  BOOL v24; // edi
  HWND v25; // rax
  unsigned __int16 *v26; // rcx
  HWND v27; // rdi
  LPCWSTR v28; // r11
  __int64 v29; // rax
  SCARDCONTEXT phContext[5]; // [rsp+30h] [rbp-28h] BYREF
  DWORD pcchReaders; // [rsp+68h] [rbp+10h] BYREF

  v4 = a4;
  if ( a2 == 272 )
  {
    if ( *(_DWORD *)a4 == 104 )
      v4 = (WCHAR *)*((_QWORD *)a4 + 6);
    SetPropW(a1, L"_Win32_this_", v4);
    goto LABEL_36;
  }
  if ( a2 == 2 )
  {
    RemovePropW(a1, L"_Win32_this_");
LABEL_7:
    DlgItem = GetDlgItem(a1, 1026);
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
    v23 = *((_DWORD *)v4 + 4);
    if ( v23 == -207 )
    {
      v25 = GetDlgItem(a1, 1021);
      v26 = (unsigned __int16 *)(*((_QWORD *)v12 + 5) + 1038LL);
      v27 = v25;
      if ( !*v26 && *((_WORD *)v12 + 36) )
      {
        StringCchCopyW(v26, 0x101u, (unsigned __int16 *)v12 + 36);
        SetWindowTextW(v27, v28);
      }
      if ( (unsigned int)IsValidRASConnectionName(
                           v27,
                           (PCNZWCH)(*((_QWORD *)v12 + 5) + 12LL),
                           (LPCWSTR)(*((_QWORD *)v12 + 5) + 1038LL)) )
      {
        if ( g_dwTraceId != -1 )
          TracePrintfExA(
            g_dwTraceId,
            0xCu,
            "IsValidRASConnectionName: returned invalid connection name:%S",
            (const wchar_t *)(*((_QWORD *)v12 + 5) + 1038LL));
        SetWindowLongW(a1, 0, -1);
      }
      else
      {
        v29 = *((_QWORD *)v12 + 5);
        if ( *(_DWORD *)(v29 + 1816) )
          *(_DWORD *)(v29 + 4952) = 1;
      }
      return 0;
    }
    if ( v23 == -206 )
      goto LABEL_7;
    if ( v23 != -200 )
    {
      if ( (v23 == -4 || v23 == -2) && !(unsigned int)CompareStringWrapW(v4 + 20, L"DialingRules") )
        lineTranslateDialogW(0, 0, 0x10004u, a1, 0);
      return 0;
    }
    if ( a3 == 4294967089 )
    {
      pcchReaders = 0;
      phContext[0] = 0;
      v24 = 0;
      if ( !SCardEstablishContext(0, 0, 0, phContext) && !SCardListReadersW(phContext[0], 0, 0, &pcchReaders) )
        v24 = pcchReaders > 2;
      if ( phContext[0] )
        SCardReleaseContext(phContext[0]);
      *((_DWORD *)v12 + 148) = v24;
    }
LABEL_52:
    CCTWConnectionInfoPage::UpdateDialogControls((CCTWConnectionInfoPage *)v12, a1);
    return 1;
  }
  v15 = v14 - 194;
  if ( !v15 )
  {
    v4 = (WCHAR *)PropW;
LABEL_36:
    CCTWConnectionInfoPage::InitDialogControls((CCTWConnectionInfoPage *)v4, a1);
    return 1;
  }
  if ( v15 != 1 )
    return 0;
  switch ( (unsigned __int16)a3 )
  {
    case 0x3FDu:
      v21 = a3 >> 16;
      v22 = GetDlgItem(a1, 1021);
      if ( (_WORD)v21 == 512 || (_WORD)v21 == 768 )
      {
        memset_0((void *)(*((_QWORD *)v12 + 5) + 1038LL), 0, 0x202u);
        GetWindowTextW(v22, (LPWSTR)(*((_QWORD *)v12 + 5) + 1038LL), 257);
        StrTrim((LPCWSTR)(*((_QWORD *)v12 + 5) + 1038LL));
        if ( (_WORD)v21 == 512 && !*(_WORD *)(*((_QWORD *)v12 + 5) + 1038LL) )
          SetWindowTextW(v22, (LPCWSTR)v12 + 36);
      }
      return 0;
    case 0x3FEu:
      v20 = GetDlgItem(a1, 1022);
      if ( WORD1(a3) != 768 )
        return 0;
      memset_0((void *)(*((_QWORD *)v12 + 5) + 1552LL), 0, 0x102u);
      GetWindowTextW(v20, (LPWSTR)(*((_QWORD *)v12 + 5) + 1552LL), 129);
      StrTrim((LPCWSTR)(*((_QWORD *)v12 + 5) + 1552LL));
      *((_DWORD *)v12 + 147) = *(_WORD *)(*((_QWORD *)v12 + 5) + 1552LL) != 0;
      goto LABEL_52;
    case 0x3FFu:
      v19 = 0;
      if ( WORD1(a3) )
        return 0;
      LOBYTE(v19) = IsDlgButtonChecked(a1, 1023) == 1;
      *(_DWORD *)(*((_QWORD *)v12 + 5) + 1816LL) = v19;
      goto LABEL_52;
    case 0x400u:
      v18 = 0;
      if ( WORD1(a3) )
        return 0;
      LOBYTE(v18) = IsDlgButtonChecked(a1, 1024) == 1;
      *(_DWORD *)(*((_QWORD *)v12 + 5) + 1812LL) = v18;
      goto LABEL_52;
    case 0x404u:
      if ( !WORD1(a3) )
      {
        v17 = GetDlgItem(a1, 1028);
        *(_DWORD *)(*((_QWORD *)v12 + 5) + 2884LL) = IsDlgButtonChecked(a1, 1028) == 1;
        if ( !(unsigned int)OnClickAllUserProfile(*((_QWORD *)v12 + 6), a1, *(_DWORD *)(*((_QWORD *)v12 + 5) + 2884LL)) )
        {
          *(_DWORD *)(*((_QWORD *)v12 + 5) + 2884LL) = 0;
          SendMessageW(v17, 0xF1u, *(int *)(*((_QWORD *)v12 + 5) + 2884LL), 0);
        }
        return 1;
      }
      return 0;
  }
  if ( (unsigned __int16)a3 != 1029 )
    return 0;
  v16 = 0;
  if ( WORD1(a3) )
    return 0;
  LOBYTE(v16) = IsDlgButtonChecked(a1, 1029) == 1;
  *(_DWORD *)(*((_QWORD *)v12 + 5) + 2888LL) = v16;
  return 1;
}

```

## disassembly

```asm
0x18001a480  mov     [rsp+arg_0], rbx
0x18001a485  mov     [rsp+arg_10], rbp
0x18001a48a  push    rsi
0x18001a48b  push    rdi
0x18001a48c  push    r14
0x18001a48e  sub     rsp, 40h
0x18001a492  mov     r14, r9
0x18001a495  mov     rdi, r8
0x18001a498  mov     ebx, edx
0x18001a49a  mov     rbp, rcx
0x18001a49d  cmp     edx, 110h
0x18001a4a3  jnz     short loc_18001A4C4
0x18001a4a5  cmp     dword ptr [r9], 68h ; 'h'
0x18001a4a9  jnz     short loc_18001A4AF
0x18001a4ab  mov     r14, [r9+30h]
0x18001a4af  mov     r8, r14; hData
0x18001a4b2  lea     rdx, aWin32This_5; "_Win32_this_"
0x18001a4b9  call    cs:__imp_SetPropW
0x18001a4bf  jmp     loc_18001A79D
0x18001a4c4  lea     rdx, aWin32This_5; "_Win32_this_"
0x18001a4cb  cmp     ebx, 2
0x18001a4ce  jnz     short loc_18001A516
0x18001a4d0  call    cs:__imp_RemovePropW
0x18001a4d6  mov     edx, 402h; nIDDlgItem
0x18001a4db  mov     rcx, rbp; hDlg
0x18001a4de  call    cs:__imp_GetDlgItem
0x18001a4e4  xor     r9d, r9d; lParam
0x18001a4e7  xor     r8d, r8d; wParam
0x18001a4ea  mov     rcx, rax; hWnd
0x18001a4ed  mov     edx, 171h; Msg
0x18001a4f2  call    cs:__imp_SendMessageW
0x18001a4f8  mov     rcx, rax; hIcon
0x18001a4fb  call    cs:__imp_DestroyIcon
0x18001a501  xor     eax, eax
0x18001a503  mov     rbx, [rsp+58h+arg_0]
0x18001a508  mov     rbp, [rsp+58h+arg_10]
0x18001a50d  add     rsp, 40h
0x18001a511  pop     r14
0x18001a513  pop     rdi
0x18001a514  pop     rsi
0x18001a515  retn
0x18001a516  call    cs:__imp_GetPropW
0x18001a51c  mov     rsi, rax
0x18001a51f  sub     ebx, 2
0x18001a522  jz      short loc_18001A4D6
0x18001a524  sub     ebx, 4Ch ; 'L'
0x18001a527  jz      loc_18001A7B2
0x18001a52d  sub     ebx, 0C2h
0x18001a533  jz      loc_18001A79A
0x18001a539  cmp     ebx, 1
0x18001a53c  jnz     short loc_18001A501
0x18001a53e  movzx   ecx, di
0x18001a541  mov     edx, 3FDh; nIDDlgItem
0x18001a546  sub     ecx, edx
0x18001a548  jz      loc_18001A706
0x18001a54e  sub     ecx, ebx
0x18001a550  jz      loc_18001A68D
0x18001a556  sub     ecx, ebx
0x18001a558  jz      loc_18001A65B
0x18001a55e  sub     ecx, ebx
0x18001a560  jz      loc_18001A629
0x18001a566  sub     ecx, 4
0x18001a569  jz      short loc_18001A59D
0x18001a56b  cmp     ecx, ebx
0x18001a56d  jnz     short loc_18001A501
0x18001a56f  shr     rdi, 10h
0x18001a573  xor     ebx, ebx
0x18001a575  test    di, di
0x18001a578  jnz     short loc_18001A501
0x18001a57a  mov     edx, 405h; nIDButton
0x18001a57f  mov     rcx, rbp; hDlg
0x18001a582  call    cs:__imp_IsDlgButtonChecked
0x18001a588  mov     rcx, [rsi+28h]
0x18001a58c  cmp     eax, 1
0x18001a58f  setz    bl
0x18001a592  mov     [rcx+0B48h], ebx
0x18001a598  jmp     loc_18001A7A8
0x18001a59d  shr     rdi, 10h
0x18001a5a1  xor     ebx, ebx
0x18001a5a3  test    di, di
0x18001a5a6  jnz     loc_18001A501
0x18001a5ac  mov     r14d, 404h
0x18001a5b2  mov     rcx, rbp; hDlg
0x18001a5b5  mov     edx, r14d; nIDDlgItem
0x18001a5b8  call    cs:__imp_GetDlgItem
0x18001a5be  mov     edx, r14d; nIDButton
0x18001a5c1  mov     rcx, rbp; hDlg
0x18001a5c4  mov     rdi, rax
0x18001a5c7  call    cs:__imp_IsDlgButtonChecked
0x18001a5cd  mov     rcx, [rsi+28h]
0x18001a5d1  mov     edx, ebx
0x18001a5d3  cmp     eax, 1
0x18001a5d6  setz    dl
0x18001a5d9  mov     [rcx+0B44h], edx
0x18001a5df  mov     rdx, rbp
0x18001a5e2  mov     r8, [rsi+28h]
0x18001a5e6  mov     rcx, [rsi+30h]
0x18001a5ea  mov     r8d, [r8+0B44h]
0x18001a5f1  call    OnClickAllUserProfile
0x18001a5f6  test    eax, eax
0x18001a5f8  jnz     loc_18001A7A8
0x18001a5fe  mov     rax, [rsi+28h]
0x18001a602  xor     r9d, r9d; lParam
0x18001a605  mov     edx, 0F1h; Msg
0x18001a60a  mov     rcx, rdi; hWnd
0x18001a60d  mov     [rax+0B44h], ebx
0x18001a613  mov     rax, [rsi+28h]
0x18001a617  movsxd  r8, dword ptr [rax+0B44h]; wParam
0x18001a61e  call    cs:__imp_SendMessageW
0x18001a624  jmp     loc_18001A7A8
0x18001a629  shr     rdi, 10h
0x18001a62d  xor     ebx, ebx
0x18001a62f  test    di, di
0x18001a632  jnz     loc_18001A501
0x18001a638  mov     edx, 400h; nIDButton
0x18001a63d  mov     rcx, rbp; hDlg
0x18001a640  call    cs:__imp_IsDlgButtonChecked
0x18001a646  cmp     eax, 1
0x18001a649  mov     rax, [rsi+28h]
0x18001a64d  setz    bl
0x18001a650  mov     [rax+714h], ebx
0x18001a656  jmp     loc_18001A87B
0x18001a65b  shr     rdi, 10h
0x18001a65f  xor     ebx, ebx
0x18001a661  test    di, di
0x18001a664  jnz     loc_18001A501
0x18001a66a  mov     edx, 3FFh; nIDButton
0x18001a66f  mov     rcx, rbp; hDlg
0x18001a672  call    cs:__imp_IsDlgButtonChecked
0x18001a678  cmp     eax, 1
0x18001a67b  mov     rax, [rsi+28h]
0x18001a67f  setz    bl
0x18001a682  mov     [rax+718h], ebx
0x18001a688  jmp     loc_18001A87B
0x18001a68d  mov     edx, 3FEh; nIDDlgItem
0x18001a692  mov     rcx, rbp; hDlg
0x18001a695  call    cs:__imp_GetDlgItem
0x18001a69b  mov     ecx, 300h
0x18001a6a0  shr     rdi, 10h
0x18001a6a4  mov     rbx, rax
0x18001a6a7  cmp     di, cx
0x18001a6aa  jnz     loc_18001A501
0x18001a6b0  mov     rcx, [rsi+28h]
0x18001a6b4  mov     edi, 610h
0x18001a6b9  add     rcx, rdi; void *
0x18001a6bc  xor     edx, edx; Val
0x18001a6be  mov     r8d, 102h; Size
0x18001a6c4  call    memset_0
0x18001a6c9  mov     rdx, [rsi+28h]
0x18001a6cd  mov     r8d, 81h; nMaxCount
0x18001a6d3  add     rdx, rdi; lpString
0x18001a6d6  mov     rcx, rbx; hWnd
0x18001a6d9  call    cs:__imp_GetWindowTextW
0x18001a6df  mov     rcx, [rsi+28h]
0x18001a6e3  add     rcx, rdi; lpszCurrent
0x18001a6e6  call    StrTrim
0x18001a6eb  mov     rax, [rsi+28h]
0x18001a6ef  xor     ebx, ebx
0x18001a6f1  cmp     [rax+610h], bx
0x18001a6f8  setnz   bl
0x18001a6fb  mov     [rsi+24Ch], ebx
0x18001a701  jmp     loc_18001A87B
0x18001a706  mov     rcx, rbp; hDlg
0x18001a709  call    cs:__imp_GetDlgItem
0x18001a70f  shr     rdi, 10h
0x18001a713  mov     r14d, 200h
0x18001a719  mov     rbp, rax
0x18001a71c  cmp     di, r14w
0x18001a720  jz      short loc_18001A730
0x18001a722  mov     ecx, 300h
0x18001a727  cmp     di, cx
0x18001a72a  jnz     loc_18001A501
0x18001a730  mov     rcx, [rsi+28h]
0x18001a734  mov     ebx, 40Eh
0x18001a739  add     rcx, rbx; void *
0x18001a73c  xor     edx, edx; Val
0x18001a73e  mov     r8d, 202h; Size
0x18001a744  call    memset_0
0x18001a749  mov     rdx, [rsi+28h]
0x18001a74d  mov     r8d, 101h; nMaxCount
0x18001a753  add     rdx, rbx; lpString
0x18001a756  mov     rcx, rbp; hWnd
0x18001a759  call    cs:__imp_GetWindowTextW
0x18001a75f  mov     rcx, [rsi+28h]
0x18001a763  add     rcx, rbx; lpszCurrent
0x18001a766  call    StrTrim
0x18001a76b  cmp     r14w, di
0x18001a76f  jnz     loc_18001A501
0x18001a775  mov     rax, [rsi+28h]
0x18001a779  xor     ebx, ebx
0x18001a77b  cmp     [rax+40Eh], bx
0x18001a782  jnz     loc_18001A501
0x18001a788  lea     rdx, [rsi+48h]; lpString
0x18001a78c  mov     rcx, rbp; hWnd
0x18001a78f  call    cs:__imp_SetWindowTextW
0x18001a795  jmp     loc_18001A501
0x18001a79a  mov     r14, rsi
0x18001a79d  mov     rdx, rbp; HWND
0x18001a7a0  mov     rcx, r14; this
0x18001a7a3  call    ?InitDialogControls@CCTWConnectionInfoPage@@AEAAXPEAUHWND__@@@Z; CCTWConnectionInfoPage::InitDialogControls(HWND__ *)
0x18001a7a8  mov     eax, 1
0x18001a7ad  jmp     loc_18001A503
0x18001a7b2  mov     eax, [r14+10h]
0x18001a7b6  mov     ecx, 0FFFFFF31h
0x18001a7bb  cmp     eax, ecx
0x18001a7bd  jz      loc_18001A88B
0x18001a7c3  cmp     eax, 0FFFFFF32h
0x18001a7c8  jz      loc_18001A4D6
0x18001a7ce  cmp     eax, 0FFFFFF38h
0x18001a7d3  jz      short loc_18001A81A
0x18001a7d5  cmp     eax, 0FFFFFFFCh
0x18001a7d8  jz      short loc_18001A7E3
0x18001a7da  cmp     eax, 0FFFFFFFEh
0x18001a7dd  jnz     loc_18001A501
0x18001a7e3  lea     rcx, [r14+28h]; lpString1
0x18001a7e7  lea     rdx, aDialingrules; "DialingRules"
0x18001a7ee  call    CompareStringWrapW
0x18001a7f3  xor     ebx, ebx
0x18001a7f5  test    eax, eax
0x18001a7f7  jnz     loc_18001A501
0x18001a7fd  mov     r9, rbp; hwndOwner
0x18001a800  mov     [rsp+58h+lpszAddressIn], rbx; lpszAddressIn
0x18001a805  xor     edx, edx; dwDeviceID
0x18001a807  xor     ecx, ecx; hLineApp
0x18001a809  mov     r8d, 10004h; dwAPIVersion
0x18001a80f  call    cs:__imp_lineTranslateDialogW
0x18001a815  jmp     loc_18001A501
0x18001a81a  cmp     rdi, rcx
0x18001a81d  jnz     short loc_18001A87B
0x18001a81f  xor     ebx, ebx
0x18001a821  lea     r9, [rsp+58h+phContext]; phContext
0x18001a826  xor     r8d, r8d; pvReserved2
0x18001a829  mov     [rsp+58h+pcchReaders], ebx
0x18001a82d  xor     edx, edx; pvReserved1
0x18001a82f  mov     [rsp+58h+phContext], rbx
0x18001a834  xor     ecx, ecx; dwScope
0x18001a836  mov     edi, ebx
0x18001a838  call    cs:__imp_SCardEstablishContext
0x18001a83e  test    eax, eax
0x18001a840  jnz     short loc_18001A865
0x18001a842  mov     rcx, [rsp+58h+phContext]; hContext
0x18001a847  lea     r9, [rsp+58h+pcchReaders]; pcchReaders
0x18001a84c  xor     r8d, r8d; mszReaders
0x18001a84f  xor     edx, edx; mszGroups
0x18001a851  call    cs:__imp_SCardListReadersW
0x18001a857  test    eax, eax
0x18001a859  jnz     short loc_18001A865
0x18001a85b  cmp     [rsp+58h+pcchReaders], 2
0x18001a860  jbe     short loc_18001A865
0x18001a862  lea     edi, [rbx+1]
0x18001a865  mov     rcx, [rsp+58h+phContext]; hContext
0x18001a86a  test    rcx, rcx
0x18001a86d  jz      short loc_18001A875
0x18001a86f  call    cs:__imp_SCardReleaseContext
0x18001a875  mov     [rsi+250h], edi
0x18001a87b  mov     rdx, rbp; HWND
0x18001a87e  mov     rcx, rsi; this
0x18001a881  call    ?UpdateDialogControls@CCTWConnectionInfoPage@@AEAAXPEAUHWND__@@@Z; CCTWConnectionInfoPage::UpdateDialogControls(HWND__ *)
0x18001a886  jmp     loc_18001A7A8
0x18001a88b  mov     edx, 3FDh; nIDDlgItem
0x18001a890  mov     rcx, rbp; hDlg
0x18001a893  call    cs:__imp_GetDlgItem
0x18001a899  mov     rcx, [rsi+28h]
0x18001a89d  xor     ebx, ebx
0x18001a89f  add     rcx, 40Eh; unsigned __int16 *
0x18001a8a6  mov     rdi, rax
0x18001a8a9  cmp     [rcx], bx
0x18001a8ac  jnz     short loc_18001A8D1
0x18001a8ae  lea     r11, [rsi+48h]
0x18001a8b2  cmp     [r11], bx
0x18001a8b6  jz      short loc_18001A8D1
0x18001a8b8  mov     r8, r11; unsigned __int16 *
0x18001a8bb  mov     edx, 101h; unsigned __int64
0x18001a8c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a8c5  mov     rdx, r11; lpString
0x18001a8c8  mov     rcx, rdi; hWnd
0x18001a8cb  call    cs:__imp_SetWindowTextW
0x18001a8d1  mov     rdx, [rsi+28h]
0x18001a8d5  mov     rcx, rdi; hWnd
0x18001a8d8  lea     r8, [rdx+40Eh]; LPCWSTR
0x18001a8df  add     rdx, 0Ch; lpString2
0x18001a8e3  call    IsValidRASConnectionName
0x18001a8e8  test    eax, eax
0x18001a8ea  jz      short loc_18001A929
0x18001a8ec  mov     ecx, cs:g_dwTraceId; dwTraceID
0x18001a8f2  cmp     ecx, 0FFFFFFFFh
0x18001a8f5  jz      short loc_18001A915
0x18001a8f7  mov     r9, [rsi+28h]
0x18001a8fb  lea     r8, aIsvalidrasconn; "IsValidRASConnectionName: returned inva"...
0x18001a902  mov     ebx, 40Eh
0x18001a907  mov     edx, 0Ch; dwFlags
0x18001a90c  add     r9, rbx
0x18001a90f  call    cs:__imp_TracePrintfExA
0x18001a915  or      r8d, 0FFFFFFFFh; dwNewLong
0x18001a919  xor     edx, edx; nIndex
0x18001a91b  mov     rcx, rbp; hWnd
0x18001a91e  call    cs:__imp_SetWindowLongW
0x18001a924  jmp     loc_18001A501
0x18001a929  mov     rax, [rsi+28h]
0x18001a92d  cmp     [rax+718h], ebx
  ... truncated ...
```
