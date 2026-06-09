# ReadFindOrFilterValues(HWND__ *,CSources *,CFindFilterBase *)

- ea: `0x180020658`
- end: `0x1800209dc`
- name: `?ReadFindOrFilterValues@@YAHPEAUHWND__@@PEAVCSources@@PEAVCFindFilterBase@@@Z`
- size: `900`
- prototype: `__int64 __fastcall(HWND hWnd, struct CSources *this, struct CFindFilterBase *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180011b40`
- `0x180012da4`

## callees

- `0x180004710`
- `0x180011580`
- `0x18001f1f0`
- `0x180020580`
- `0x180020658`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800208bd`
- `msvcrt!wcscpy_s` at `0x1800208bd`
- `KERNEL32!lstrcmpW` at `0x1800206bf`
- `KERNEL32!lstrcmpW` at `0x18002084d`
- `KERNEL32!lstrcmpW` at `0x180020891`
- `KERNEL32!lstrcmpW` at `0x1800206bf`
- `KERNEL32!lstrcmpW` at `0x18002084d`
- `KERNEL32!lstrcmpW` at `0x180020891`
- `USER32!IsWindowEnabled` at `0x1800206f7`
- `USER32!IsWindowEnabled` at `0x180020728`
- `USER32!IsWindowEnabled` at `0x18002075a`
- `USER32!IsWindowEnabled` at `0x18002078c`
- `USER32!IsWindowEnabled` at `0x1800207be`
- `USER32!IsWindowEnabled` at `0x1800206f7`
- `USER32!IsWindowEnabled` at `0x180020728`
- `USER32!IsWindowEnabled` at `0x18002075a`
- `USER32!IsWindowEnabled` at `0x18002078c`
- `USER32!IsWindowEnabled` at `0x1800207be`
- `USER32!GetDlgItemInt` at `0x180020952`
- `USER32!GetDlgItemInt` at `0x180020952`
- `USER32!GetWindowTextLengthW` at `0x18002092d`
- `USER32!GetWindowTextLengthW` at `0x18002092d`
- `USER32!SendMessageW` at `0x18002098a`
- `USER32!SendMessageW` at `0x18002098a`
- `USER32!GetDlgItem` at `0x1800206ee`
- `USER32!GetDlgItem` at `0x18002071f`
- `USER32!GetDlgItem` at `0x180020751`
- `USER32!GetDlgItem` at `0x180020783`
- `USER32!GetDlgItem` at `0x1800207b5`
- `USER32!GetDlgItem` at `0x180020924`
- `USER32!GetDlgItem` at `0x180020973`
- `USER32!GetDlgItem` at `0x1800206ee`
- `USER32!GetDlgItem` at `0x18002071f`
- `USER32!GetDlgItem` at `0x180020751`
- `USER32!GetDlgItem` at `0x180020783`
- `USER32!GetDlgItem` at `0x1800207b5`
- `USER32!GetDlgItem` at `0x180020924`
- `USER32!GetDlgItem` at `0x180020973`
- `USER32!GetDlgItemTextW` at `0x1800206ab`
- `USER32!GetDlgItemTextW` at `0x1800207ee`
- `USER32!GetDlgItemTextW` at `0x18002083b`
- `USER32!GetDlgItemTextW` at `0x1800208f2`
- `USER32!GetDlgItemTextW` at `0x1800206ab`
- `USER32!GetDlgItemTextW` at `0x1800207ee`
- `USER32!GetDlgItemTextW` at `0x18002083b`
- `USER32!GetDlgItemTextW` at `0x1800208f2`
- `USER32!IsDlgButtonChecked` at `0x180020707`
- `USER32!IsDlgButtonChecked` at `0x180020738`
- `USER32!IsDlgButtonChecked` at `0x18002076a`
- `USER32!IsDlgButtonChecked` at `0x18002079c`
- `USER32!IsDlgButtonChecked` at `0x1800207ce`
- `USER32!IsDlgButtonChecked` at `0x180020707`
- `USER32!IsDlgButtonChecked` at `0x180020738`
- `USER32!IsDlgButtonChecked` at `0x18002076a`
- `USER32!IsDlgButtonChecked` at `0x18002079c`
- `USER32!IsDlgButtonChecked` at `0x1800207ce`
- `USER32!CharLowerBuffW` at `0x1800208d7`
- `USER32!CharLowerBuffW` at `0x1800208d7`
- `USER32!SetFocus` at `0x180020993`
- `USER32!SetFocus` at `0x180020993`

## pseudocode

```c
__int64 __fastcall ReadFindOrFilterValues(HWND hWnd, struct CSources *this, wchar_t *a3)
{
  unsigned int v5; // r15d
  wchar_t v7; // bx
  int v8; // ebx
  HWND DlgItem; // rax
  HWND v10; // rax
  HWND v11; // rax
  HWND v12; // rax
  HWND v13; // rax
  struct CCategories *Categories; // r14
  unsigned int i; // ebx
  __int64 v16; // rdx
  wchar_t *v17; // rcx
  HWND v18; // rax
  UINT DlgItemInt; // eax
  HWND v20; // rbx
  BOOL Translated; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR String1[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String[264]; // [rsp+240h] [rbp+140h] BYREF

  v5 = 1;
  GetDlgItemTextW(hWnd, 125, String, 260);
  if ( lstrcmpW(String, (LPCWSTR)&g_wszAll) )
  {
    CFindFilterBase::SetSource((CFindFilterBase *)a3, String);
    GetDlgItemTextW(hWnd, 127, String1, 260);
    if ( lstrcmpW(String1, (LPCWSTR)&g_wszAll) )
    {
      Categories = CSources::GetCategories(this, String);
      if ( Categories )
      {
        for ( i = 0; i < *(_DWORD *)Categories; ++i )
        {
          if ( !lstrcmpW(String1, *(LPCWSTR *)(*((_QWORD *)Categories + 1) + 8LL * i)) )
          {
            v7 = i + 1;
            goto LABEL_4;
          }
        }
      }
    }
  }
  else
  {
    a3[6] = 0;
  }
  v7 = 0;
LABEL_4:
  a3[266] = v7;
  v8 = 0;
  DlgItem = GetDlgItem(hWnd, 121);
  if ( IsWindowEnabled(DlgItem) )
    v8 = IsDlgButtonChecked(hWnd, 121) != 0;
  v10 = GetDlgItem(hWnd, 120);
  if ( IsWindowEnabled(v10) && IsDlgButtonChecked(hWnd, 120) )
    v8 |= 2u;
  v11 = GetDlgItem(hWnd, 119);
  if ( IsWindowEnabled(v11) && IsDlgButtonChecked(hWnd, 119) )
    v8 |= 4u;
  v12 = GetDlgItem(hWnd, 122);
  if ( IsWindowEnabled(v12) && IsDlgButtonChecked(hWnd, 122) )
    v8 |= 8u;
  v13 = GetDlgItem(hWnd, 123);
  if ( IsWindowEnabled(v13) && IsDlgButtonChecked(hWnd, 123) )
    v8 |= 0x10u;
  *((_DWORD *)a3 + 2) = v8;
  GetDlgItemTextW(hWnd, 129, String1, 260);
  if ( String1[0] )
    CopyStrippingLeadTrailSpace(a3 + 267, String1, 0x104u);
  else
    a3[267] = 0;
  wcscpy_s(a3 + 527, 0x104u, a3 + 267);
  v16 = -1;
  do
    ++v16;
  while ( a3[v16 + 527] );
  CharLowerBuffW(a3 + 527, v16);
  GetDlgItemTextW(hWnd, 131, String1, 261);
  v17 = a3 + 787;
  if ( String1[0] )
    CopyStrippingLeadTrailSpace(v17, String1, 0x105u);
  else
    *v17 = 0;
  v18 = GetDlgItem(hWnd, 133);
  if ( GetWindowTextLengthW(v18) )
  {
    Translated = 0;
    DlgItemInt = GetDlgItemInt(hWnd, 133, &Translated, 0);
    if ( Translated )
    {
      *((_DWORD *)a3 + 524) = 1;
      *((_DWORD *)a3 + 525) = DlgItemInt;
    }
    else
    {
      v20 = GetDlgItem(hWnd, 133);
      SendMessageW(v20, 0xB1u, 0, -1);
      SetFocus(v20);
      MsgBox(hWnd, 0x113u, 0x10u);
      return 0;
    }
  }
  else
  {
    *((_QWORD *)a3 + 262) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180020658  mov     [rsp-8+arg_18], rbx
0x18002065d  push    rbp
0x18002065e  push    rsi
0x18002065f  push    rdi
0x180020660  push    r12
0x180020662  push    r13
0x180020664  push    r14
0x180020666  push    r15
0x180020668  lea     rbp, [rsp-360h]
0x180020670  sub     rsp, 460h
0x180020677  mov     rax, cs:__security_cookie
0x18002067e  xor     rax, rsp
0x180020681  mov     [rbp+390h+var_40], rax
0x180020688  mov     rsi, r8
0x18002068b  mov     rbx, rdx
0x18002068e  mov     r15d, 1
0x180020694  lea     r8, [rbp+390h+String]; lpString
0x18002069b  mov     r13d, 104h
0x1800206a1  mov     rdi, rcx
0x1800206a4  mov     r9d, r13d; cchMax
0x1800206a7  lea     edx, [r15+7Ch]; nIDDlgItem
0x1800206ab  call    cs:__imp_GetDlgItemTextW
0x1800206b1  lea     rdx, ?g_wszAll@@3PAGA; lpString2
0x1800206b8  lea     rcx, [rbp+390h+String]; lpString1
0x1800206bf  call    cs:__imp_lstrcmpW
0x1800206c5  xor     r12d, r12d
0x1800206c8  test    eax, eax
0x1800206ca  jnz     loc_18002081C
0x1800206d0  mov     [rsi+0Ch], r12w
0x1800206d5  mov     ebx, r12d
0x1800206d8  mov     [rsi+214h], bx
0x1800206df  mov     r14d, 79h ; 'y'
0x1800206e5  mov     edx, r14d; nIDDlgItem
0x1800206e8  mov     rcx, rdi; hDlg
0x1800206eb  mov     ebx, r12d
0x1800206ee  call    cs:__imp_GetDlgItem
0x1800206f4  mov     rcx, rax; hWnd
0x1800206f7  call    cs:__imp_IsWindowEnabled
0x1800206fd  test    eax, eax
0x1800206ff  jz      short loc_180020713
0x180020701  mov     edx, r14d; nIDButton
0x180020704  mov     rcx, rdi; hDlg
0x180020707  call    cs:__imp_IsDlgButtonChecked
0x18002070d  test    eax, eax
0x18002070f  cmovnz  ebx, r15d
0x180020713  mov     r14d, 78h ; 'x'
0x180020719  mov     rcx, rdi; hDlg
0x18002071c  mov     edx, r14d; nIDDlgItem
0x18002071f  call    cs:__imp_GetDlgItem
0x180020725  mov     rcx, rax; hWnd
0x180020728  call    cs:__imp_IsWindowEnabled
0x18002072e  test    eax, eax
0x180020730  jz      short loc_180020745
0x180020732  mov     edx, r14d; nIDButton
0x180020735  mov     rcx, rdi; hDlg
0x180020738  call    cs:__imp_IsDlgButtonChecked
0x18002073e  test    eax, eax
0x180020740  jz      short loc_180020745
0x180020742  or      ebx, 2
0x180020745  mov     r14d, 77h ; 'w'
0x18002074b  mov     rcx, rdi; hDlg
0x18002074e  mov     edx, r14d; nIDDlgItem
0x180020751  call    cs:__imp_GetDlgItem
0x180020757  mov     rcx, rax; hWnd
0x18002075a  call    cs:__imp_IsWindowEnabled
0x180020760  test    eax, eax
0x180020762  jz      short loc_180020777
0x180020764  mov     edx, r14d; nIDButton
0x180020767  mov     rcx, rdi; hDlg
0x18002076a  call    cs:__imp_IsDlgButtonChecked
0x180020770  test    eax, eax
0x180020772  jz      short loc_180020777
0x180020774  or      ebx, 4
0x180020777  mov     r14d, 7Ah ; 'z'
0x18002077d  mov     rcx, rdi; hDlg
0x180020780  mov     edx, r14d; nIDDlgItem
0x180020783  call    cs:__imp_GetDlgItem
0x180020789  mov     rcx, rax; hWnd
0x18002078c  call    cs:__imp_IsWindowEnabled
0x180020792  test    eax, eax
0x180020794  jz      short loc_1800207A9
0x180020796  mov     edx, r14d; nIDButton
0x180020799  mov     rcx, rdi; hDlg
0x18002079c  call    cs:__imp_IsDlgButtonChecked
0x1800207a2  test    eax, eax
0x1800207a4  jz      short loc_1800207A9
0x1800207a6  or      ebx, 8
0x1800207a9  mov     r14d, 7Bh ; '{'
0x1800207af  mov     rcx, rdi; hDlg
0x1800207b2  mov     edx, r14d; nIDDlgItem
0x1800207b5  call    cs:__imp_GetDlgItem
0x1800207bb  mov     rcx, rax; hWnd
0x1800207be  call    cs:__imp_IsWindowEnabled
0x1800207c4  test    eax, eax
0x1800207c6  jz      short loc_1800207DB
0x1800207c8  mov     edx, r14d; nIDButton
0x1800207cb  mov     rcx, rdi; hDlg
0x1800207ce  call    cs:__imp_IsDlgButtonChecked
0x1800207d4  test    eax, eax
0x1800207d6  jz      short loc_1800207DB
0x1800207d8  or      ebx, 10h
0x1800207db  mov     r9d, r13d; cchMax
0x1800207de  mov     [rsi+8], ebx
0x1800207e1  lea     r8, [rsp+490h+String1]; lpString
0x1800207e6  mov     edx, 81h; nIDDlgItem
0x1800207eb  mov     rcx, rdi; hDlg
0x1800207ee  call    cs:__imp_GetDlgItemTextW
0x1800207f4  lea     rbx, [rsi+216h]
0x1800207fb  cmp     [rsp+490h+String1], r12w
0x180020801  jz      loc_1800208A9
0x180020807  mov     r8d, r13d; SizeInWords
0x18002080a  lea     rdx, [rsp+490h+String1]; String
0x18002080f  mov     rcx, rbx; Destination
0x180020812  call    ?CopyStrippingLeadTrailSpace@@YAXPEAGPEBGK@Z; CopyStrippingLeadTrailSpace(ushort *,ushort const *,ulong)
0x180020817  jmp     loc_1800208AD
0x18002081c  lea     rdx, [rbp+390h+String]; unsigned __int16 *
0x180020823  mov     rcx, rsi; this
0x180020826  call    ?SetSource@CFindFilterBase@@QEAAXPEBG@Z; CFindFilterBase::SetSource(ushort const *)
0x18002082b  mov     r9d, r13d; cchMax
0x18002082e  lea     r8, [rsp+490h+String1]; lpString
0x180020833  mov     edx, 7Fh; nIDDlgItem
0x180020838  mov     rcx, rdi; hDlg
0x18002083b  call    cs:__imp_GetDlgItemTextW
0x180020841  lea     rdx, ?g_wszAll@@3PAGA; lpString2
0x180020848  lea     rcx, [rsp+490h+String1]; lpString1
0x18002084d  call    cs:__imp_lstrcmpW
0x180020853  test    eax, eax
0x180020855  jz      loc_1800206D5
0x18002085b  lea     rdx, [rbp+390h+String]; unsigned __int16 *
0x180020862  mov     rcx, rbx; this
0x180020865  call    ?GetCategories@CSources@@QEAAPEAVCCategories@@PEBG@Z; CSources::GetCategories(ushort const *)
0x18002086a  mov     r14, rax
0x18002086d  test    rax, rax
0x180020870  jz      loc_1800206D5
0x180020876  mov     ebx, r12d
0x180020879  cmp     ebx, [r14]
0x18002087c  jnb     loc_1800206D5
0x180020882  mov     rdx, [r14+8]
0x180020886  mov     ecx, ebx
0x180020888  mov     rdx, [rdx+rcx*8]; lpString2
0x18002088c  lea     rcx, [rsp+490h+String1]; lpString1
0x180020891  call    cs:__imp_lstrcmpW
0x180020897  test    eax, eax
0x180020899  jz      short loc_1800208A0
0x18002089b  add     ebx, r15d
0x18002089e  jmp     short loc_180020879
0x1800208a0  add     bx, r15w
0x1800208a4  jmp     loc_1800206D8
0x1800208a9  mov     [rbx], r12w
0x1800208ad  lea     r14, [rsi+41Eh]
0x1800208b4  mov     r8, rbx; Source
0x1800208b7  mov     rcx, r14; Destination
0x1800208ba  mov     rdx, r13; SizeInWords
0x1800208bd  call    cs:__imp_wcscpy_s
0x1800208c3  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800208c7  mov     rdx, r13
0x1800208ca  inc     rdx; cchLength
0x1800208cd  cmp     [r14+rdx*2], r12w
0x1800208d2  jnz     short loc_1800208CA
0x1800208d4  mov     rcx, r14; lpsz
0x1800208d7  call    cs:__imp_CharLowerBuffW
0x1800208dd  mov     ebx, 105h
0x1800208e2  lea     r8, [rsp+490h+String1]; lpString
0x1800208e7  mov     r9d, ebx; cchMax
0x1800208ea  mov     edx, 83h; nIDDlgItem
0x1800208ef  mov     rcx, rdi; hDlg
0x1800208f2  call    cs:__imp_GetDlgItemTextW
0x1800208f8  lea     rcx, [rsi+626h]; Destination
0x1800208ff  cmp     [rsp+490h+String1], r12w
0x180020905  jz      short loc_180020916
0x180020907  mov     r8d, ebx; SizeInWords
0x18002090a  lea     rdx, [rsp+490h+String1]; String
0x18002090f  call    ?CopyStrippingLeadTrailSpace@@YAXPEAGPEBGK@Z; CopyStrippingLeadTrailSpace(ushort *,ushort const *,ulong)
0x180020914  jmp     short loc_18002091A
0x180020916  mov     [rcx], r12w
0x18002091a  mov     ebx, 85h
0x18002091f  mov     rcx, rdi; hDlg
0x180020922  mov     edx, ebx; nIDDlgItem
0x180020924  call    cs:__imp_GetDlgItem
0x18002092a  mov     rcx, rax; hWnd
0x18002092d  call    cs:__imp_GetWindowTextLengthW
0x180020933  test    eax, eax
0x180020935  jnz     short loc_180020940
0x180020937  mov     [rsi+830h], r12
0x18002093e  jmp     short loc_1800209AF
0x180020940  xor     r9d, r9d; bSigned
0x180020943  mov     [rsp+490h+Translated], r12d
0x180020948  lea     r8, [rsp+490h+Translated]; lpTranslated
0x18002094d  mov     edx, ebx; nIDDlgItem
0x18002094f  mov     rcx, rdi; hDlg
0x180020952  call    cs:__imp_GetDlgItemInt
0x180020958  cmp     [rsp+490h+Translated], r12d
0x18002095d  jz      short loc_18002096E
0x18002095f  mov     [rsi+830h], r15d
0x180020966  mov     [rsi+834h], eax
0x18002096c  jmp     short loc_1800209AF
0x18002096e  mov     edx, ebx; nIDDlgItem
0x180020970  mov     rcx, rdi; hDlg
0x180020973  call    cs:__imp_GetDlgItem
0x180020979  mov     r9, r13; lParam
0x18002097c  xor     r8d, r8d; wParam
0x18002097f  mov     rcx, rax; hWnd
0x180020982  mov     edx, 0B1h; Msg
0x180020987  mov     rbx, rax
0x18002098a  call    cs:__imp_SendMessageW
0x180020990  mov     rcx, rbx; hWnd
0x180020993  call    cs:__imp_SetFocus
0x180020999  mov     edx, 113h; uID
0x18002099e  mov     r8d, 10h; unsigned int
0x1800209a4  mov     rcx, rdi; hWnd
0x1800209a7  call    ?MsgBox@@YAHPEAUHWND__@@KKZZ; MsgBox(HWND__ *,ulong,ulong,...)
0x1800209ac  mov     r15d, r12d
0x1800209af  mov     eax, r15d
0x1800209b2  mov     rcx, [rbp+390h+var_40]
0x1800209b9  xor     rcx, rsp; StackCookie
0x1800209bc  call    __security_check_cookie
0x1800209c1  mov     rbx, [rsp+490h+arg_18]
0x1800209c9  add     rsp, 460h
0x1800209d0  pop     r15
0x1800209d2  pop     r14
0x1800209d4  pop     r13
0x1800209d6  pop     r12
0x1800209d8  pop     rdi
0x1800209d9  pop     rsi
0x1800209da  pop     rbp
0x1800209db  retn
```
