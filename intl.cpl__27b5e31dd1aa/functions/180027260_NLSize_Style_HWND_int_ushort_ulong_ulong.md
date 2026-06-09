# NLSize_Style(HWND__ *,int,ushort *,ulong,ulong)

- ea: `0x180027260`
- end: `0x180027874`
- name: `?NLSize_Style@@YAHPEAUHWND__@@HPEAGKK@Z`
- size: `1556`
- prototype: `__int64 __fastcall(HWND hDlg, int nIDDlgItem, unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011040`
- `0x1800119d8`
- `0x180011c60`
- `0x180012688`
- `0x1800216f0`
- `0x180021d3c`

## callees

- `0x180003368`
- `0x18000626c`
- `0x180027260`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `msvcrt!wcschr` at `0x1800276e6`
- `msvcrt!wcschr` at `0x1800276fb`
- `msvcrt!wcschr` at `0x1800276e6`
- `msvcrt!wcschr` at `0x1800276fb`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027491`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800274ec`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027540`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027597`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800275ee`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027667`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800276d5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027769`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800277be`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027818`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027491`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800274ec`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027540`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027597`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800275ee`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027667`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800276d5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027769`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x1800277be`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180027818`
- `USER32!GetDlgItem` at `0x1800272ab`
- `USER32!GetDlgItem` at `0x1800272ab`
- `USER32!SendMessageW` at `0x1800272c2`
- `USER32!SendMessageW` at `0x180027318`
- `USER32!SendMessageW` at `0x180027339`
- `USER32!SendMessageW` at `0x1800272c2`
- `USER32!SendMessageW` at `0x180027318`
- `USER32!SendMessageW` at `0x180027339`
- `USER32!GetDlgItemTextW` at `0x1800272df`
- `USER32!GetDlgItemTextW` at `0x1800272df`

## pseudocode

```c
__int64 __fastcall NLSize_Style(HWND hDlg, int nIDDlgItem, unsigned __int16 *a3, unsigned int a4, unsigned int a5)
{
  unsigned __int64 v6; // r14
  HWND DlgItem; // rsi
  int v10; // eax
  UINT DlgItemTextW; // eax
  WPARAM v12; // rdi
  unsigned __int64 v13; // rax
  int v14; // r14d
  unsigned __int16 *v16; // r13
  WCHAR *v17; // rsi
  BOOL v18; // ecx
  unsigned __int16 near **v19; // r12
  const wchar_t *v20; // rbp
  BOOL v21; // eax
  BOOL v22; // [rsp+50h] [rbp-168h]
  WCHAR String[128]; // [rsp+60h] [rbp-158h] BYREF
  WCHAR v24[44]; // [rsp+160h] [rbp-58h] BYREF

  v6 = a4;
  memset_0(String, 0, sizeof(String));
  DlgItem = GetDlgItem(hDlg, nIDDlgItem);
  v10 = SendMessageW(DlgItem, 0x147u, 0, 0);
  if ( v10 != -1 )
  {
    v12 = v10;
    if ( (unsigned int)SendMessageW(DlgItem, 0x149u, v10, 0) < 0x80
      && (unsigned int)SendMessageW(DlgItem, 0x148u, v12, (LPARAM)String) != -1 )
    {
      goto LABEL_8;
    }
LABEL_67:
    *a3 = 0;
    return 1;
  }
  DlgItemTextW = GetDlgItemTextW(hDlg, nIDDlgItem, String, 128);
  if ( DlgItemTextW > 0x7F )
    goto LABEL_67;
  if ( 2 * (unsigned __int64)DlgItemTextW >= 0x100 )
    _report_rangecheckfailure();
  String[DlgItemTextW] = 0;
LABEL_8:
  v13 = v6;
  v14 = 0;
  if ( !g_fStylesLocalized )
  {
    if ( StringCchCopyW(a3, v13, String) < 0 )
      goto LABEL_10;
    return 0;
  }
  v16 = &a3[v13];
  v17 = String;
  v18 = 0;
  v22 = 0;
  switch ( a5 )
  {
    case 0x1Fu:
      v19 = &g_szSDLetters;
      goto LABEL_20;
    case 0x20u:
      v19 = &g_szLDLetters;
LABEL_20:
      v20 = g_szDCaseSwap;
      break;
    case 0x79u:
    case 0x1003u:
      v19 = &g_szTLetters;
      v20 = g_szTCaseSwap;
      break;
    default:
      v19 = 0;
      v20 = 0;
      break;
  }
  while ( v17 < v24 && *v17 )
  {
    if ( a3 >= v16 )
      return 0;
    if ( *v17 == 39 )
    {
      *a3++ = 39;
      v21 = !v18;
      v18 = v21;
      v22 = v21;
      goto LABEL_57;
    }
    if ( v18 )
      goto LABEL_55;
    if ( a5 != 4099 && a5 != 121 )
    {
      v14 = 1;
      if ( a5 != 32 )
        goto LABEL_44;
      v14 = 0;
    }
    if ( CompareStringEx(
           *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
           0,
           v17,
           1,
           &g_szStyleH,
           -1,
           0,
           0,
           0) == 2 )
    {
      *a3 = 72;
    }
    else if ( CompareStringEx(
                *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
                0,
                v17,
                1,
                &g_szStyleh,
                -1,
                0,
                0,
                0) == 2 )
    {
      *a3 = 104;
    }
    else if ( CompareStringEx(
                *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
                0,
                v17,
                1,
                &g_szStylem,
                -1,
                0,
                0,
                0) == 2 )
    {
      *a3 = 109;
    }
    else if ( CompareStringEx(
                *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
                0,
                v17,
                1,
                &g_szStyles,
                -1,
                0,
                0,
                0) == 2 )
    {
      *a3 = 115;
    }
    else
    {
      if ( CompareStringEx(
             *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
             0,
             v17,
             1,
             &g_szStylet,
             -1,
             0,
             0,
             0) != 2 )
      {
        v14 = 1;
        goto LABEL_43;
      }
      *a3 = 116;
    }
    ++a3;
LABEL_43:
    v18 = v22;
LABEL_44:
    if ( a5 != 31 )
    {
      if ( a5 != 32 )
      {
        if ( !v14 )
          goto LABEL_57;
LABEL_51:
        if ( CompareStringEx(
               *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
               0,
               v17,
               1,
               L" ",
               -1,
               0,
               0,
               0) != 2
          && (wcschr((const wchar_t *)v19, *v17) || wcschr(v20, *v17)) )
        {
          *a3 = 0;
          return 1;
        }
        v18 = v22;
LABEL_55:
        *a3 = *v17;
        goto LABEL_56;
      }
      if ( !v14 )
        goto LABEL_57;
    }
    if ( CompareStringEx(
           *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
           0,
           v17,
           1,
           &g_szStyled,
           -1,
           0,
           0,
           0) == 2 )
    {
      *a3 = 100;
    }
    else if ( CompareStringEx(
                *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
                0,
                v17,
                1,
                &g_szStyleM,
                -1,
                0,
                0,
                0) == 2 )
    {
      *a3 = 77;
    }
    else
    {
      if ( CompareStringEx(
             *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
             0,
             v17,
             1,
             &g_szStyley,
             -1,
             0,
             0,
             0) == 2 )
      {
        v18 = v22;
        *a3 = 121;
        goto LABEL_56;
      }
      if ( CompareStringEx(
             *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
             0,
             v17,
             1,
             L"g",
             -1,
             0,
             0,
             0) != 2 )
        goto LABEL_51;
      *a3 = 103;
    }
    v18 = v22;
LABEL_56:
    ++a3;
LABEL_57:
    ++v17;
    v14 = 0;
  }
  if ( a3 < v16 )
LABEL_10:
    *a3 = 0;
  return 0;
}

```

## disassembly

```asm
0x180027260  push    rbx
0x180027262  push    rbp
0x180027263  push    rsi
0x180027264  push    rdi
0x180027265  push    r12
0x180027267  push    r13
0x180027269  push    r14
0x18002726b  push    r15
0x18002726d  sub     rsp, 178h
0x180027274  mov     rax, cs:__security_cookie
0x18002727b  xor     rax, rsp
0x18002727e  mov     qword ptr [rsp+1B8h+var_58], rax
0x180027286  mov     rbx, r8
0x180027289  mov     r14d, r9d
0x18002728c  mov     ebp, edx
0x18002728e  mov     rdi, rcx
0x180027291  mov     r12d, 100h
0x180027297  lea     rcx, [rsp+1B8h+String]; void *
0x18002729c  mov     r8d, r12d; Size
0x18002729f  xor     edx, edx; Val
0x1800272a1  call    memset_0
0x1800272a6  mov     edx, ebp; nIDDlgItem
0x1800272a8  mov     rcx, rdi; hDlg
0x1800272ab  call    cs:__imp_GetDlgItem
0x1800272b1  xor     r9d, r9d; lParam
0x1800272b4  lea     edx, [r12+47h]; Msg
0x1800272b9  mov     rcx, rax; hWnd
0x1800272bc  xor     r8d, r8d; wParam
0x1800272bf  mov     rsi, rax
0x1800272c2  call    cs:__imp_SendMessageW
0x1800272c8  xor     r15d, r15d
0x1800272cb  cmp     eax, 0FFFFFFFFh
0x1800272ce  jnz     short loc_180027307
0x1800272d0  lea     r9d, [r12-80h]; cchMax
0x1800272d5  mov     edx, ebp; nIDDlgItem
0x1800272d7  lea     r8, [rsp+1B8h+String]; lpString
0x1800272dc  mov     rcx, rdi; hDlg
0x1800272df  call    cs:__imp_GetDlgItemTextW
0x1800272e5  cmp     eax, 7Fh
0x1800272e8  ja      loc_180027847
0x1800272ee  mov     eax, eax
0x1800272f0  lea     rcx, [rax+rax]
0x1800272f4  cmp     rcx, r12
0x1800272f7  jnb     short loc_180027301
0x1800272f9  mov     [rsp+rcx+1B8h+String], r15w
0x1800272ff  jmp     short loc_180027348
0x180027301  call    __report_rangecheckfailure
0x180027307  movsxd  rdi, eax
0x18002730a  xor     r9d, r9d; lParam
0x18002730d  mov     r8, rdi; wParam
0x180027310  mov     edx, 149h; Msg
0x180027315  mov     rcx, rsi; hWnd
0x180027318  call    cs:__imp_SendMessageW
0x18002731e  cmp     eax, 80h
0x180027323  jnb     loc_180027847
0x180027329  lea     r9, [rsp+1B8h+String]; lParam
0x18002732e  mov     r8, rdi; wParam
0x180027331  mov     edx, 148h; Msg
0x180027336  mov     rcx, rsi; hWnd
0x180027339  call    cs:__imp_SendMessageW
0x18002733f  cmp     eax, 0FFFFFFFFh
0x180027342  jz      loc_180027847
0x180027348  mov     rax, r14
0x18002734b  xor     r14d, r14d
0x18002734e  cmp     cs:?g_fStylesLocalized@@3HA, r14d; int g_fStylesLocalized
0x180027355  jnz     short loc_180027376
0x180027357  lea     r8, [rsp+1B8h+String]; unsigned __int16 *
0x18002735c  mov     rdx, rax; unsigned __int64
0x18002735f  mov     rcx, rbx; unsigned __int16 *
0x180027362  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027367  test    eax, eax
0x180027369  jns     short loc_18002736F
0x18002736b  mov     [rbx], r14w
0x18002736f  xor     eax, eax
0x180027371  jmp     loc_180027850
0x180027376  mov     r15d, [rsp+1B8h+arg_20]
0x18002737e  lea     r13, [rbx+rax*2]
0x180027382  mov     eax, r15d
0x180027385  lea     rsi, [rsp+1B8h+String]
0x18002738a  mov     ecx, r14d
0x18002738d  mov     [rsp+1B8h+var_168], ecx
0x180027391  sub     eax, 1Fh
0x180027394  jz      short loc_1800273C8
0x180027396  sub     eax, 1
0x180027399  jz      short loc_1800273BF
0x18002739b  sub     eax, 59h ; 'Y'
0x18002739e  jz      short loc_1800273AF
0x1800273a0  cmp     eax, 0F8Ah
0x1800273a5  jz      short loc_1800273AF
0x1800273a7  mov     r12, r14
0x1800273aa  mov     rbp, r14
0x1800273ad  jmp     short loc_1800273D6
0x1800273af  lea     r12, ?g_szTLetters@@3PAGA; "Hhmst"
0x1800273b6  lea     rbp, ?g_szTCaseSwap@@3PAGA; "   MST"
0x1800273bd  jmp     short loc_1800273D6
0x1800273bf  lea     r12, ?g_szLDLetters@@3PAGA; "dgHhMmsty"
0x1800273c6  jmp     short loc_1800273CF
0x1800273c8  lea     r12, ?g_szSDLetters@@3PAGA; "dgMy"
0x1800273cf  lea     rbp, ?g_szDCaseSwap@@3PAGA; " DGmY"
0x1800273d6  mov     edx, 79h ; 'y'
0x1800273db  lea     edi, [rdx-78h]
0x1800273de  lea     rax, [rsp+1B8h+var_58]
0x1800273e6  mov     r8d, 27h ; '''
0x1800273ec  cmp     rsi, rax
0x1800273ef  jnb     loc_180027839
0x1800273f5  cmp     [rsi], r14w
0x1800273f9  jz      loc_180027839
0x1800273ff  cmp     rbx, r13
0x180027402  jnb     loc_18002736F
0x180027408  cmp     [rsi], r8w
0x18002740c  jnz     short loc_180027429
0x18002740e  mov     eax, r14d
0x180027411  mov     [rbx], r8w
0x180027415  add     rbx, 2
0x180027419  test    ecx, ecx
0x18002741b  setz    al
0x18002741e  mov     ecx, eax
0x180027420  mov     [rsp+1B8h+var_168], eax
0x180027424  jmp     loc_18002771D
0x180027429  test    ecx, ecx
0x18002742b  jnz     loc_180027713
0x180027431  cmp     r15d, 1003h
0x180027438  jz      short loc_18002744F
0x18002743a  cmp     r15d, edx
0x18002743d  jz      short loc_18002744F
0x18002743f  mov     r14d, edi
0x180027442  cmp     r15d, 20h ; ' '
0x180027446  jnz     loc_18002760F
0x18002744c  xor     r14d, r14d
0x18002744f  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180027456  mov     r9d, edi; cchCount1
0x180027459  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18002745f  mov     r8, rsi; lpString1
0x180027462  xor     edx, edx; dwCmpFlags
0x180027464  mov     rcx, [rax+rcx*8]
0x180027468  xor     eax, eax
0x18002746a  mov     [rsp+1B8h+lParam], rax; lParam
0x18002746f  mov     [rsp+1B8h+lpReserved], rax; lpReserved
0x180027474  mov     [rsp+1B8h+lpVersionInformation], rax; lpVersionInformation
0x180027479  lea     rax, ?g_szStyleH@@3PAGA; ushort near * g_szStyleH
0x180027480  mov     rcx, [rcx+8]; lpLocaleName
0x180027484  mov     [rsp+1B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002748c  mov     [rsp+1B8h+lpString2], rax; lpString2
0x180027491  call    cs:__imp_CompareStringEx
0x180027497  cmp     eax, 2
0x18002749a  jnz     short loc_1800274AA
0x18002749c  mov     word ptr [rbx], 48h ; 'H'
0x1800274a1  add     rbx, 2
0x1800274a5  jmp     loc_180027606
0x1800274aa  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800274b1  mov     r9d, edi; cchCount1
0x1800274b4  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800274ba  mov     r8, rsi; lpString1
0x1800274bd  xor     edx, edx; dwCmpFlags
0x1800274bf  mov     rcx, [rax+rcx*8]
0x1800274c3  xor     eax, eax
0x1800274c5  mov     [rsp+1B8h+lParam], rax; lParam
0x1800274ca  mov     [rsp+1B8h+lpReserved], rax; lpReserved
0x1800274cf  mov     [rsp+1B8h+lpVersionInformation], rax; lpVersionInformation
0x1800274d4  lea     rax, ?g_szStyleh@@3PAGA; ushort near * g_szStyleh
0x1800274db  mov     rcx, [rcx+8]; lpLocaleName
0x1800274df  mov     [rsp+1B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800274e7  mov     [rsp+1B8h+lpString2], rax; lpString2
0x1800274ec  call    cs:__imp_CompareStringEx
0x1800274f2  cmp     eax, 2
0x1800274f5  jnz     short loc_1800274FE
0x1800274f7  mov     word ptr [rbx], 68h ; 'h'
0x1800274fc  jmp     short loc_1800274A1
0x1800274fe  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180027505  mov     r9d, edi; cchCount1
0x180027508  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18002750e  mov     r8, rsi; lpString1
0x180027511  xor     edx, edx; dwCmpFlags
0x180027513  mov     rcx, [rax+rcx*8]
0x180027517  xor     eax, eax
0x180027519  mov     [rsp+1B8h+lParam], rax; lParam
0x18002751e  mov     [rsp+1B8h+lpReserved], rax; lpReserved
0x180027523  mov     [rsp+1B8h+lpVersionInformation], rax; lpVersionInformation
0x180027528  lea     rax, ?g_szStylem@@3PAGA; ushort near * g_szStylem
0x18002752f  mov     rcx, [rcx+8]; lpLocaleName
0x180027533  mov     [rsp+1B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002753b  mov     [rsp+1B8h+lpString2], rax; lpString2
0x180027540  call    cs:__imp_CompareStringEx
0x180027546  cmp     eax, 2
0x180027549  jnz     short loc_180027555
0x18002754b  mov     word ptr [rbx], 6Dh ; 'm'
0x180027550  jmp     loc_1800274A1
0x180027555  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18002755c  mov     r9d, edi; cchCount1
0x18002755f  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180027565  mov     r8, rsi; lpString1
0x180027568  xor     edx, edx; dwCmpFlags
0x18002756a  mov     rcx, [rax+rcx*8]
0x18002756e  xor     eax, eax
0x180027570  mov     [rsp+1B8h+lParam], rax; lParam
0x180027575  mov     [rsp+1B8h+lpReserved], rax; lpReserved
0x18002757a  mov     [rsp+1B8h+lpVersionInformation], rax; lpVersionInformation
0x18002757f  lea     rax, ?g_szStyles@@3PAGA; ushort near * g_szStyles
0x180027586  mov     rcx, [rcx+8]; lpLocaleName
0x18002758a  mov     [rsp+1B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x180027592  mov     [rsp+1B8h+lpString2], rax; lpString2
0x180027597  call    cs:__imp_CompareStringEx
0x18002759d  cmp     eax, 2
0x1800275a0  jnz     short loc_1800275AC
0x1800275a2  mov     word ptr [rbx], 73h ; 's'
0x1800275a7  jmp     loc_1800274A1
0x1800275ac  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800275b3  mov     r9d, edi; cchCount1
0x1800275b6  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800275bc  mov     r8, rsi; lpString1
0x1800275bf  xor     edx, edx; dwCmpFlags
0x1800275c1  mov     rcx, [rax+rcx*8]
0x1800275c5  xor     eax, eax
0x1800275c7  mov     [rsp+1B8h+lParam], rax; lParam
0x1800275cc  mov     [rsp+1B8h+lpReserved], rax; lpReserved
0x1800275d1  mov     [rsp+1B8h+lpVersionInformation], rax; lpVersionInformation
0x1800275d6  lea     rax, ?g_szStylet@@3PAGA; ushort near * g_szStylet
0x1800275dd  mov     rcx, [rcx+8]; lpLocaleName
0x1800275e1  mov     [rsp+1B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800275e9  mov     [rsp+1B8h+lpString2], rax; lpString2
0x1800275ee  call    cs:__imp_CompareStringEx
0x1800275f4  cmp     eax, 2
0x1800275f7  jnz     short loc_180027603
0x1800275f9  mov     word ptr [rbx], 74h ; 't'
0x1800275fe  jmp     loc_1800274A1
0x180027603  mov     r14d, edi
0x180027606  mov     ecx, [rsp+1B8h+var_168]
0x18002760a  mov     edx, 79h ; 'y'
0x18002760f  cmp     r15d, 1Fh
0x180027613  jz      short loc_180027624
0x180027615  cmp     r15d, 20h ; ' '
0x180027619  jnz     short loc_180027689
0x18002761b  test    r14d, r14d
0x18002761e  jz      loc_18002771D
0x180027624  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18002762b  xor     r14d, r14d
0x18002762e  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180027634  mov     r9d, edi; cchCount1
0x180027637  mov     [rsp+1B8h+lParam], r14; lParam
0x18002763c  mov     r8, rsi; lpString1
0x18002763f  mov     [rsp+1B8h+lpReserved], r14; lpReserved
0x180027644  xor     edx, edx; dwCmpFlags
0x180027646  mov     [rsp+1B8h+lpVersionInformation], r14; lpVersionInformation
0x18002764b  mov     rcx, [rax+rcx*8]
0x18002764f  lea     rax, ?g_szStyled@@3PAGA; ushort near * g_szStyled
0x180027656  mov     [rsp+1B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002765e  mov     [rsp+1B8h+lpString2], rax; lpString2
0x180027663  mov     rcx, [rcx+8]; lpLocaleName
0x180027667  call    cs:__imp_CompareStringEx
0x18002766d  cmp     eax, 2
0x180027670  jnz     loc_180027729
0x180027676  mov     word ptr [rbx], 64h ; 'd'
0x18002767b  mov     ecx, [rsp+1B8h+var_168]
0x18002767f  mov     edx, 79h ; 'y'
0x180027684  jmp     loc_180027719
0x180027689  test    r14d, r14d
0x18002768c  jz      loc_18002771D
0x180027692  xor     r14d, r14d
0x180027695  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18002769c  mov     r9d, edi; cchCount1
0x18002769f  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800276a5  mov     r8, rsi; lpString1
0x1800276a8  mov     [rsp+1B8h+lParam], r14; lParam
0x1800276ad  xor     edx, edx; dwCmpFlags
0x1800276af  mov     [rsp+1B8h+lpReserved], r14; lpReserved
0x1800276b4  mov     [rsp+1B8h+lpVersionInformation], r14; lpVersionInformation
0x1800276b9  mov     rcx, [rax+rcx*8]
0x1800276bd  lea     rax, asc_180032288; " "
0x1800276c4  mov     [rsp+1B8h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800276cc  mov     [rsp+1B8h+lpString2], rax; lpString2
0x1800276d1  mov     rcx, [rcx+8]; lpLocaleName
0x1800276d5  call    cs:__imp_CompareStringEx
0x1800276db  cmp     eax, 2
0x1800276de  jz      short loc_18002770A
0x1800276e0  movzx   edx, word ptr [rsi]; Ch
0x1800276e3  mov     rcx, r12; Str
0x1800276e6  call    cs:__imp_wcschr
0x1800276ec  test    rax, rax
0x1800276ef  jnz     loc_180027831
0x1800276f5  movzx   edx, word ptr [rsi]; Ch
0x1800276f8  mov     rcx, rbp; Str
0x1800276fb  call    cs:__imp_wcschr
0x180027701  test    rax, rax
0x180027704  jnz     loc_180027831
0x18002770a  mov     ecx, [rsp+1B8h+var_168]
0x18002770e  mov     edx, 79h ; 'y'
0x180027713  movzx   eax, word ptr [rsi]
0x180027716  mov     [rbx], ax
0x180027719  add     rbx, 2
0x18002771d  add     rsi, 2
0x180027721  xor     r14d, r14d
0x180027724  jmp     loc_1800273DE
0x180027729  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180027730  mov     r9d, edi; cchCount1
0x180027733  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180027739  mov     r8, rsi; lpString1
0x18002773c  mov     [rsp+1B8h+lParam], r14; lParam
0x180027741  xor     edx, edx; dwCmpFlags
0x180027743  mov     [rsp+1B8h+lpReserved], r14; lpReserved
0x180027748  mov     [rsp+1B8h+lpVersionInformation], r14; lpVersionInformation
  ... truncated ...
```
