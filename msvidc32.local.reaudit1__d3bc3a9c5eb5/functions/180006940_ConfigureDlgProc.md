# ConfigureDlgProc

- ea: `0x180006940`
- end: `0x180006b61`
- name: `ConfigureDlgProc`
- size: `545`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x180001400`
- `0x180006940`
- `0x180007244`

## import_xrefs

- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x180006a9a`
- `api-ms-win-core-privateprofile-l1-1-0!GetProfileStringW` at `0x180006a9a`
- `USER32!GetScrollPos` at `0x180006989`
- `USER32!GetScrollPos` at `0x180006a42`
- `USER32!GetScrollPos` at `0x180006989`
- `USER32!GetScrollPos` at `0x180006a42`
- `USER32!SetScrollRange` at `0x180006add`
- `USER32!SetScrollRange` at `0x180006add`
- `USER32!GetDlgItem` at `0x180006a28`
- `USER32!GetDlgItem` at `0x180006ab4`
- `USER32!GetDlgItem` at `0x180006a28`
- `USER32!GetDlgItem` at `0x180006ab4`
- `USER32!SetScrollPos` at `0x1800069ee`
- `USER32!SetScrollPos` at `0x180006aef`
- `USER32!SetScrollPos` at `0x1800069ee`
- `USER32!SetScrollPos` at `0x180006aef`
- `USER32!EndDialog` at `0x180006a53`
- `USER32!EndDialog` at `0x180006a53`
- `USER32!SetDlgItemTextW` at `0x180006b40`
- `USER32!SetDlgItemTextW` at `0x180006b40`

## pseudocode

```c
INT_PTR __fastcall ConfigureDlgProc(HWND a1, int a2, __int64 a3, HWND a4)
{
  int v5; // edi
  HWND v6; // rbp
  int v7; // edx
  int v8; // edx
  int ScrollPos; // eax
  int v10; // ebx
  unsigned int v11; // edx
  INT_PTR v12; // rdx
  HWND v13; // rax
  __int64 v14; // rbx
  HWND DlgItem; // rbx
  int v17; // edi
  __int64 nSize; // [rsp+20h] [rbp-58h]
  int v19; // [rsp+28h] [rbp-50h]
  WCHAR Default[12]; // [rsp+30h] [rbp-48h] BYREF

  v5 = a3;
  v6 = a1;
  v7 = a2 - 272;
  if ( !v7 )
  {
    wcscpy(Default, L".");
    qword_18000B428 = (__int64)a4;
    GetProfileStringW(L"intl", L"sDecimal", Default, Default, 0xAu);
    word_18000B258 = Default[0];
    DlgItem = GetDlgItem(v6, 100);
    v17 = *(_DWORD *)(qword_18000B428 + 24);
    SetScrollRange(DlgItem, 2, 1, 100, 1);
    SetScrollPos(DlgItem, 2, v17, 1);
    v11 = v17 / 100;
    v19 = v17 % 100;
LABEL_28:
    LODWORD(nSize) = (unsigned __int16)word_18000B258;
    StringCchPrintfW(Default, 0xAu, L"%d%c%02d", v11, nSize, v19);
    SetDlgItemTextW(v6, 101, Default);
    return 1;
  }
  v8 = v7 - 1;
  if ( !v8 )
  {
    if ( a3 == 1 )
    {
      v13 = GetDlgItem(a1, 100);
      v14 = qword_18000B428;
      if ( qword_18000B428 )
        *(_DWORD *)(v14 + 24) = GetScrollPos(v13, 2);
      v12 = 1;
      a1 = v6;
    }
    else
    {
      if ( a3 != 2 )
        return 0;
      v12 = 0;
    }
    EndDialog(a1, v12);
    return 0;
  }
  if ( v8 != 3 )
    return 0;
  ScrollPos = GetScrollPos(a4, 2);
  if ( !(_WORD)v5 )
  {
    v10 = ScrollPos - 1;
    goto LABEL_14;
  }
  switch ( (unsigned __int16)v5 )
  {
    case 1u:
      v10 = ScrollPos + 1;
      goto LABEL_14;
    case 2u:
      v10 = ScrollPos - 10;
      goto LABEL_14;
    case 3u:
      v10 = ScrollPos + 10;
      goto LABEL_14;
  }
  if ( (unsigned int)(unsigned __int16)v5 - 4 <= 1 )
  {
    v10 = HIWORD(v5);
LABEL_14:
    if ( v10 > 100 )
    {
      v10 = 100;
    }
    else if ( v10 < 1 )
    {
      v10 = 1;
    }
    SetScrollPos(a4, 2, v10, 1);
    v11 = v10 / 100;
    v19 = v10 % 100;
    goto LABEL_28;
  }
  return 1;
}

```

## disassembly

```asm
0x180006940  push    rbx
0x180006942  push    rbp
0x180006943  push    rsi
0x180006944  push    rdi
0x180006945  push    r15
0x180006947  sub     rsp, 50h
0x18000694b  mov     rax, cs:__security_cookie
0x180006952  xor     rax, rsp
0x180006955  mov     [rsp+78h+var_30], rax
0x18000695a  mov     r15, r9
0x18000695d  mov     rdi, r8
0x180006960  mov     rbp, rcx
0x180006963  sub     edx, 110h
0x180006969  jz      loc_180006A60
0x18000696f  sub     edx, 1
0x180006972  jz      loc_180006A13
0x180006978  cmp     edx, 3
0x18000697b  jnz     loc_180006A59
0x180006981  mov     edx, 2; nBar
0x180006986  mov     rcx, r9; hWnd
0x180006989  call    cs:__imp_GetScrollPos
0x18000698f  movzx   edx, di
0x180006992  mov     esi, 1
0x180006997  mov     ebx, eax
0x180006999  test    edx, edx
0x18000699b  jz      short loc_1800069CC
0x18000699d  sub     edx, esi
0x18000699f  jz      short loc_1800069C8
0x1800069a1  sub     edx, esi
0x1800069a3  jz      short loc_1800069C3
0x1800069a5  sub     edx, esi
0x1800069a7  jz      short loc_1800069BE
0x1800069a9  sub     edx, esi
0x1800069ab  jz      short loc_1800069B5
0x1800069ad  cmp     edx, esi
0x1800069af  jnz     loc_180006B46
0x1800069b5  shr     rdi, 10h
0x1800069b9  movzx   ebx, di
0x1800069bc  jmp     short loc_1800069CE
0x1800069be  add     ebx, 0Ah
0x1800069c1  jmp     short loc_1800069CE
0x1800069c3  sub     ebx, 0Ah
0x1800069c6  jmp     short loc_1800069CE
0x1800069c8  add     ebx, esi
0x1800069ca  jmp     short loc_1800069CE
0x1800069cc  sub     ebx, esi
0x1800069ce  cmp     ebx, 64h ; 'd'
0x1800069d1  jg      short loc_1800069DB
0x1800069d3  cmp     ebx, esi
0x1800069d5  jge     short loc_1800069E0
0x1800069d7  mov     ebx, esi
0x1800069d9  jmp     short loc_1800069E0
0x1800069db  mov     ebx, 64h ; 'd'
0x1800069e0  mov     r9d, esi; bRedraw
0x1800069e3  mov     r8d, ebx; nPos
0x1800069e6  mov     edx, 2; nBar
0x1800069eb  mov     rcx, r15; hWnd
0x1800069ee  call    cs:__imp_SetScrollPos
0x1800069f4  mov     eax, 51EB851Fh
0x1800069f9  imul    ebx
0x1800069fb  sar     edx, 5
0x1800069fe  mov     eax, edx
0x180006a00  shr     eax, 1Fh
0x180006a03  add     edx, eax
0x180006a05  imul    eax, edx, 64h ; 'd'
0x180006a08  sub     ebx, eax
0x180006a0a  mov     [rsp+78h+var_50], ebx
0x180006a0e  jmp     loc_180006B0F
0x180006a13  sub     rdi, 1
0x180006a17  jz      short loc_180006A23
0x180006a19  cmp     rdi, 1
0x180006a1d  jnz     short loc_180006A59
0x180006a1f  xor     edx, edx
0x180006a21  jmp     short loc_180006A53
0x180006a23  mov     edx, 64h ; 'd'; nIDDlgItem
0x180006a28  call    cs:__imp_GetDlgItem
0x180006a2e  mov     rbx, cs:qword_18000B428
0x180006a35  mov     rcx, rax; hWnd
0x180006a38  test    rbx, rbx
0x180006a3b  jz      short loc_180006A4B
0x180006a3d  mov     edx, 2; nBar
0x180006a42  call    cs:__imp_GetScrollPos
0x180006a48  mov     [rbx+18h], eax
0x180006a4b  mov     edx, 1; nResult
0x180006a50  mov     rcx, rbp; hDlg
0x180006a53  call    cs:__imp_EndDialog
0x180006a59  xor     eax, eax
0x180006a5b  jmp     loc_180006B49
0x180006a60  movzx   eax, cs:word_18000B258
0x180006a67  lea     r9, [rsp+78h+Default]; lpReturnedString
0x180006a6c  mov     [rsp+78h+Default], ax
0x180006a71  lea     r8, [rsp+78h+Default]; lpDefault
0x180006a76  xor     eax, eax
0x180006a78  mov     cs:qword_18000B428, r15
0x180006a7f  lea     rdx, KeyName; "sDecimal"
0x180006a86  mov     [rsp+78h+var_46], ax
0x180006a8b  lea     rcx, AppName; "intl"
0x180006a92  mov     dword ptr [rsp+78h+nSize], 0Ah; nSize
0x180006a9a  call    cs:__imp_GetProfileStringW
0x180006aa0  movzx   eax, [rsp+78h+Default]
0x180006aa5  mov     edx, 64h ; 'd'; nIDDlgItem
0x180006aaa  mov     rcx, rbp; hDlg
0x180006aad  mov     cs:word_18000B258, ax
0x180006ab4  call    cs:__imp_GetDlgItem
0x180006aba  mov     rcx, cs:qword_18000B428
0x180006ac1  mov     esi, 1
0x180006ac6  mov     r8d, esi; nMinPos
0x180006ac9  mov     dword ptr [rsp+78h+nSize], esi; bRedraw
0x180006acd  mov     rbx, rax
0x180006ad0  mov     edi, [rcx+18h]
0x180006ad3  lea     r9d, [rsi+63h]; nMaxPos
0x180006ad7  mov     rcx, rax; hWnd
0x180006ada  lea     edx, [rsi+1]; nBar
0x180006add  call    cs:__imp_SetScrollRange
0x180006ae3  mov     r9d, esi; bRedraw
0x180006ae6  lea     edx, [rsi+1]; nBar
0x180006ae9  mov     r8d, edi; nPos
0x180006aec  mov     rcx, rbx; hWnd
0x180006aef  call    cs:__imp_SetScrollPos
0x180006af5  mov     eax, 51EB851Fh
0x180006afa  imul    edi
0x180006afc  sar     edx, 5
0x180006aff  mov     eax, edx
0x180006b01  shr     eax, 1Fh
0x180006b04  add     edx, eax
0x180006b06  imul    eax, edx, 64h ; 'd'
0x180006b09  sub     edi, eax
0x180006b0b  mov     [rsp+78h+var_50], edi
0x180006b0f  movzx   eax, cs:word_18000B258
0x180006b16  lea     r8, aDC02d; "%d%c%02d"
0x180006b1d  mov     r9d, edx
0x180006b20  mov     dword ptr [rsp+78h+nSize], eax
0x180006b24  mov     edx, 0Ah; cchDest
0x180006b29  lea     rcx, [rsp+78h+Default]; pszDest
0x180006b2e  call    StringCchPrintfW
0x180006b33  lea     r8, [rsp+78h+Default]; lpString
0x180006b38  mov     edx, 65h ; 'e'; nIDDlgItem
0x180006b3d  mov     rcx, rbp; hDlg
0x180006b40  call    cs:__imp_SetDlgItemTextW
0x180006b46  mov     rax, rsi
0x180006b49  mov     rcx, [rsp+78h+var_30]
0x180006b4e  xor     rcx, rsp; StackCookie
0x180006b51  call    __security_check_cookie
0x180006b56  add     rsp, 50h
0x180006b5a  pop     r15
0x180006b5c  pop     rdi
0x180006b5d  pop     rsi
0x180006b5e  pop     rbp
0x180006b5f  pop     rbx
0x180006b60  retn
```
