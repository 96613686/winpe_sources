# BGSoundDlgProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180063110`
- end: `0x180063590`
- name: `?BGSoundDlgProc@@YA_JPEAUHWND__@@I_K_J@Z`
- size: `1152`
- prototype: `INT_PTR __stdcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x18000910c`
- `0x18004bba4`
- `0x180063110`
- `0x18008e2f0`
- `0x1800cc9ba`
- `0x1800cca00`

## import_xrefs

- `MSOERT2!MessageBoxInstW` at `0x18006337b`
- `MSOERT2!MessageBoxInstW` at `0x180063429`
- `MSOERT2!MessageBoxInstW` at `0x18006337b`
- `MSOERT2!MessageBoxInstW` at `0x180063429`
- `MSOERT2!ReplaceCharsW` at `0x18006320d`
- `MSOERT2!ReplaceCharsW` at `0x18006320d`
- `MSOERT2!IsValidFileIfFileUrlW` at `0x180063320`
- `MSOERT2!IsValidFileIfFileUrlW` at `0x180063320`
- `SHLWAPI!StrToIntW` at `0x1800633cc`
- `SHLWAPI!StrToIntW` at `0x1800633cc`
- `SHLWAPI!SHAutoComplete` at `0x180063567`
- `SHLWAPI!SHAutoComplete` at `0x180063567`
- `KERNEL32!GetWindowsDirectoryW` at `0x180063288`
- `KERNEL32!GetWindowsDirectoryW` at `0x180063288`
- `USER32!MessageBoxW` at `0x180063332`
- `USER32!MessageBoxW` at `0x1800633e2`
- `USER32!LoadStringW` at `0x1800631fa`
- `USER32!LoadStringW` at `0x18006325f`
- `USER32!LoadStringW` at `0x1800631fa`
- `USER32!LoadStringW` at `0x18006325f`
- `USER32!LoadStringW` at `0x180063362`
- `USER32!LoadStringW` at `0x180063414`
- `USER32!SendDlgItemMessageA` at `0x18006352b`
- `USER32!SendDlgItemMessageA` at `0x18006352b`
- `USER32!SendMessageA` at `0x180063473`
- `USER32!SendMessageA` at `0x180063492`
- `USER32!SendMessageA` at `0x180063473`
- `USER32!SendMessageA` at `0x180063492`
- `USER32!GetDlgItem` at `0x1800631b1`
- `USER32!GetDlgItem` at `0x1800632ce`
- `USER32!GetDlgItem` at `0x180063305`
- `USER32!GetDlgItem` at `0x1800633af`
- `USER32!GetDlgItem` at `0x18006345c`
- `USER32!GetDlgItem` at `0x180063480`
- `USER32!GetDlgItem` at `0x18006349e`
- `USER32!GetDlgItem` at `0x1800634df`
- `USER32!GetDlgItem` at `0x18006354b`
- `USER32!GetDlgItem` at `0x18006355c`
- `USER32!GetDlgItem` at `0x1800631b1`
- `USER32!GetDlgItem` at `0x1800632ce`
- `USER32!GetDlgItem` at `0x180063305`
- `USER32!GetDlgItem` at `0x1800633af`
- `USER32!GetDlgItem` at `0x18006345c`
- `USER32!GetDlgItem` at `0x180063480`
- `USER32!GetDlgItem` at `0x18006349e`
- `USER32!GetDlgItem` at `0x1800634df`
- `USER32!GetDlgItem` at `0x18006354b`
- `USER32!GetDlgItem` at `0x18006355c`
- `USER32!SetWindowTextW` at `0x1800632de`
- `USER32!SetWindowTextW` at `0x1800634aa`
- `USER32!SetWindowTextW` at `0x1800634ec`
- `USER32!SetWindowTextW` at `0x1800632de`
- `USER32!SetWindowTextW` at `0x1800634aa`
- `USER32!SetWindowTextW` at `0x1800634ec`
- `USER32!CheckRadioButton` at `0x18006350c`
- `USER32!CheckRadioButton` at `0x18006350c`
- `USER32!SetWindowLongPtrA` at `0x18006353a`
- `USER32!SetWindowLongPtrA` at `0x18006353a`
- `USER32!EnableWindow` at `0x1800631bc`
- `USER32!EnableWindow` at `0x1800631bc`
- `USER32!GetWindowLongPtrA` at `0x1800632f4`
- `USER32!GetWindowLongPtrA` at `0x1800632f4`
- `USER32!GetWindowTextW` at `0x180063317`
- `USER32!GetWindowTextW` at `0x1800633c2`
- `USER32!GetWindowTextW` at `0x180063317`
- `USER32!GetWindowTextW` at `0x1800633c2`
- `USER32!IsDlgButtonChecked` at `0x180063399`
- `USER32!IsDlgButtonChecked` at `0x180063399`
- `USER32!EndDialog` at `0x180063445`
- `USER32!EndDialog` at `0x180063445`

## pseudocode

```c
INT_PTR __fastcall BGSoundDlgProc(HWND a1, int a2, unsigned __int16 a3, LONG_PTR a4)
{
  int v8; // ebx
  HWND v9; // rax
  HWND v10; // rax
  LONG_PTR WindowLongPtrA; // r15
  HWND v13; // rax
  HWND v14; // rax
  int v15; // eax
  HWND DlgItem; // rax
  HWND v17; // rax
  HWND v18; // rax
  int v19; // eax
  __int64 v20; // r9
  HWND v21; // rax
  int v22; // r9d
  HWND v23; // rax
  struct tagOFNW v24; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszSrc[16]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR v26[264]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR String[264]; // [rsp+330h] [rbp+230h] BYREF
  WCHAR Buffer[512]; // [rsp+540h] [rbp+440h] BYREF
  WCHAR v29[512]; // [rsp+940h] [rbp+840h] BYREF

  memset_0(&v24, 0, sizeof(v24));
  v8 = a2 - 272;
  if ( !v8 )
  {
    DlgItem = GetDlgItem(a1, 800);
    SendMessageA(DlgItem, 0xC5u, 0x103u, 0);
    v17 = GetDlgItem(a1, 803);
    SendMessageA(v17, 0xC5u, 3u, 0);
    v18 = GetDlgItem(a1, 800);
    SetWindowTextW(v18, (LPCWSTR)a4);
    v19 = *(_DWORD *)(a4 + 520);
    v20 = 1;
    if ( v19 > 1 )
      v20 = (unsigned int)v19;
    StringCchPrintfW(pszSrc, 0xAu, L"%d", v20);
    v21 = GetDlgItem(a1, 803);
    SetWindowTextW(v21, pszSrc);
    v22 = 804;
    if ( *(_DWORD *)(a4 + 520) != -1 )
      v22 = 802;
    CheckRadioButton(a1, 802, 804, v22);
    SendDlgItemMessageA(a1, 708, 0x465u, 0, 66535);
    SetWindowLongPtrA(a1, 16, a4);
    if ( a1 && GetDlgItem(a1, 800) )
    {
      v23 = GetDlgItem(a1, 800);
      SHAutoComplete(v23, 1u);
    }
    return 0;
  }
  if ( v8 == 1 )
  {
    if ( a3 != 1 )
    {
      if ( a3 != 2 )
      {
        if ( a3 != 801 )
        {
          if ( a3 == 802 || a3 == 804 )
          {
            v9 = GetDlgItem(a1, 803);
            EnableWindow(v9, a3 == 802);
          }
          return 0;
        }
        String[0] = 0;
        Buffer[0] = 0;
        v29[0] = 0;
        LoadStringW(g_hLocRes, 0x507u, Buffer, 512);
        ReplaceCharsW(Buffer, 124);
        memset_0(&v24, 0, sizeof(v24));
        v24.lpstrFile = String;
        v24.lStructSize = 152;
        v24.lpstrFilter = Buffer;
        v24.hwndOwner = a1;
        LoadStringW(g_hLocRes, 0x508u, v29, 512);
        v24.Flags = 135180;
        v24.nMaxFile = 260;
        v24.lpstrTitle = v29;
        if ( GetWindowsDirectoryW(v26, 0x104u) > 0x104 || (int)StringCchCatW(v26, 0x104u, L"\\Media") < 0 )
          v26[0] = 0;
        v24.lpstrInitialDir = v26;
        if ( !(unsigned int)HrAthGetFileNameW(&v24, 1) )
        {
          v10 = GetDlgItem(a1, 800);
          SetWindowTextW(v10, String);
        }
        return 1;
      }
      goto LABEL_21;
    }
    WindowLongPtrA = GetWindowLongPtrA(a1, 16);
    v13 = GetDlgItem(a1, 800);
    GetWindowTextW(v13, (LPWSTR)WindowLongPtrA, 260);
    if ( (unsigned int)IsValidFileIfFileUrlW(WindowLongPtrA)
      || (unsigned int)MessageBoxInstW(g_hLocRes, a1, 1285, 1286, 0, 4, LoadStringW, MessageBoxW, 0, 0, 0, 0) != 7 )
    {
      *(_DWORD *)(WindowLongPtrA + 520) = 1;
      if ( !IsDlgButtonChecked(a1, 802) )
      {
        *(_DWORD *)(WindowLongPtrA + 520) = -1;
        goto LABEL_21;
      }
      v14 = GetDlgItem(a1, 803);
      GetWindowTextW(v14, pszSrc, 10);
      v15 = StrToIntW(pszSrc);
      *(_DWORD *)(WindowLongPtrA + 520) = v15;
      if ( (unsigned int)(v15 - 1) <= 0x3E6 )
      {
LABEL_21:
        EndDialog(a1, a3);
        return 1;
      }
      MessageBoxInstW(g_hLocRes, a1, 1285, 1289, 0, 0, LoadStringW, MessageBoxW, 0, 0, 0, 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180063110  push    rbp
0x180063112  push    rbx
0x180063113  push    rsi
0x180063114  push    rdi
0x180063115  push    r12
0x180063117  push    r14
0x180063119  push    r15
0x18006311b  lea     rbp, [rsp-0C50h]
0x180063123  sub     rsp, 0D50h
0x18006312a  mov     rax, cs:__security_cookie
0x180063131  xor     rax, rsp
0x180063134  mov     [rbp+0C80h+var_40], rax
0x18006313b  mov     rsi, r8
0x18006313e  mov     ebx, edx
0x180063140  mov     rdi, rcx
0x180063143  xor     edx, edx; Val
0x180063145  mov     r8d, 98h; Size
0x18006314b  lea     rcx, [rsp+0D80h+var_D20]; void *
0x180063150  mov     r15, r9
0x180063153  call    memset_0
0x180063158  sub     ebx, 110h
0x18006315e  jz      loc_180063450
0x180063164  cmp     ebx, 1
0x180063167  jnz     loc_18006356D
0x18006316d  movzx   r12d, si
0x180063171  mov     esi, ebx
0x180063173  mov     ecx, r12d
0x180063176  sub     ecx, esi
0x180063178  jz      loc_1800632EC
0x18006317e  sub     ecx, esi
0x180063180  jz      loc_18006343F
0x180063186  sub     ecx, 31Fh
0x18006318c  jz      short loc_1800631C7
0x18006318e  sub     ecx, esi
0x180063190  jz      short loc_18006319B
0x180063192  cmp     ecx, 2
0x180063195  jnz     loc_18006356D
0x18006319b  mov     edx, 322h
0x1800631a0  xor     ebx, ebx
0x1800631a2  cmp     r12w, dx
0x1800631a6  mov     rcx, rdi; hDlg
0x1800631a9  mov     edx, 323h; nIDDlgItem
0x1800631ae  setz    bl
0x1800631b1  call    cs:__imp_GetDlgItem
0x1800631b7  mov     rcx, rax; hWnd
0x1800631ba  mov     edx, ebx; bEnable
0x1800631bc  call    cs:__imp_EnableWindow
0x1800631c2  jmp     loc_18006356D
0x1800631c7  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x1800631ce  lea     r8, [rbp+0C80h+Buffer]; lpBuffer
0x1800631d5  xor     ebx, ebx
0x1800631d7  mov     r14d, 200h
0x1800631dd  mov     r9d, r14d; cchBufferMax
0x1800631e0  mov     [rbp+0C80h+String], bx
0x1800631e7  mov     edx, 507h; uID
0x1800631ec  mov     [rbp+0C80h+Buffer], bx
0x1800631f3  mov     [rbp+0C80h+var_440], bx
0x1800631fa  call    cs:__imp_LoadStringW
0x180063200  xor     r8d, r8d
0x180063203  lea     edx, [rbx+7Ch]
0x180063206  lea     rcx, [rbp+0C80h+Buffer]
0x18006320d  call    cs:__imp_ReplaceCharsW
0x180063213  xor     edx, edx; Val
0x180063215  lea     rcx, [rsp+0D80h+var_D20]; void *
0x18006321a  mov     r8d, 98h; Size
0x180063220  call    memset_0
0x180063225  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; hInstance
0x18006322c  lea     rax, [rbp+0C80h+String]
0x180063233  mov     [rbp+0C80h+var_D20.lpstrFile], rax
0x180063237  lea     r8, [rbp+0C80h+var_440]; lpBuffer
0x18006323e  lea     rax, [rbp+0C80h+Buffer]
0x180063245  mov     [rsp+0D80h+var_D20.lStructSize], 98h
0x18006324d  mov     r9d, r14d; cchBufferMax
0x180063250  mov     [rsp+0D80h+var_D20.lpstrFilter], rax
0x180063255  mov     edx, 508h; uID
0x18006325a  mov     [rsp+0D80h+var_D20.hwndOwner], rdi
0x18006325f  call    cs:__imp_LoadStringW
0x180063265  mov     r14d, 104h
0x18006326b  mov     [rbp+0C80h+var_D20.Flags], 2100Ch
0x180063272  lea     rax, [rbp+0C80h+var_440]
0x180063279  mov     [rbp+0C80h+var_D20.nMaxFile], r14d
0x18006327d  mov     edx, r14d; uSize
0x180063280  mov     [rbp+0C80h+var_D20.lpstrTitle], rax
0x180063284  lea     rcx, [rbp+0C80h+var_C60]; lpBuffer
0x180063288  call    cs:__imp_GetWindowsDirectoryW
0x18006328e  cmp     eax, r14d
0x180063291  ja      short loc_1800632AA
0x180063293  lea     r8, aMedia; "\\Media"
0x18006329a  mov     edx, r14d; unsigned __int64
0x18006329d  lea     rcx, [rbp+0C80h+var_C60]; unsigned __int16 *
0x1800632a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800632a6  test    eax, eax
0x1800632a8  jns     short loc_1800632AE
0x1800632aa  mov     [rbp+0C80h+var_C60], bx
0x1800632ae  lea     rax, [rbp+0C80h+var_C60]
0x1800632b2  mov     edx, esi
0x1800632b4  lea     rcx, [rsp+0D80h+var_D20]; LPOPENFILENAMEW
0x1800632b9  mov     [rbp+0C80h+var_D20.lpstrInitialDir], rax
0x1800632bd  call    HrAthGetFileNameW
0x1800632c2  test    eax, eax
0x1800632c4  jnz     short loc_1800632E4
0x1800632c6  mov     edx, 320h; nIDDlgItem
0x1800632cb  mov     rcx, rdi; hDlg
0x1800632ce  call    cs:__imp_GetDlgItem
0x1800632d4  mov     rcx, rax; hWnd
0x1800632d7  lea     rdx, [rbp+0C80h+String]; lpString
0x1800632de  call    cs:__imp_SetWindowTextW
0x1800632e4  mov     rax, rsi
0x1800632e7  jmp     loc_18006356F
0x1800632ec  mov     edx, 10h; nIndex
0x1800632f1  mov     rcx, rdi; hWnd
0x1800632f4  call    cs:__imp_GetWindowLongPtrA
0x1800632fa  mov     edx, 320h; nIDDlgItem
0x1800632ff  mov     rcx, rdi; hDlg
0x180063302  mov     r15, rax
0x180063305  call    cs:__imp_GetDlgItem
0x18006330b  mov     r8d, 104h; nMaxCount
0x180063311  mov     rdx, r15; lpString
0x180063314  mov     rcx, rax; hWnd
0x180063317  call    cs:__imp_GetWindowTextW
0x18006331d  mov     rcx, r15
0x180063320  call    cs:__imp_IsValidFileIfFileUrlW
0x180063326  xor     ebx, ebx
0x180063328  mov     r14d, 505h
0x18006332e  test    eax, eax
0x180063330  jnz     short loc_18006338A
0x180063332  mov     rax, cs:__imp_MessageBoxW
0x180063339  lea     r9d, [r14+1]
0x18006333d  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x180063344  mov     r8d, r14d
0x180063347  mov     [rsp+0D80h+var_D28], ebx
0x18006334b  mov     rdx, rdi
0x18006334e  mov     [rsp+0D80h+var_D30], rbx
0x180063353  mov     [rsp+0D80h+var_D38], rbx
0x180063358  mov     [rsp+0D80h+var_D40], rbx
0x18006335d  mov     [rsp+0D80h+var_D48], rax
0x180063362  mov     rax, cs:__imp_LoadStringW
0x180063369  mov     [rsp+0D80h+var_D50], rax
0x18006336e  mov     [rsp+0D80h+var_D58], 4
0x180063376  mov     [rsp+0D80h+lParam], rbx
0x18006337b  call    cs:__imp_MessageBoxInstW
0x180063381  cmp     eax, 7
0x180063384  jz      loc_18006356D
0x18006338a  mov     edx, 322h; nIDButton
0x18006338f  mov     [r15+208h], esi
0x180063396  mov     rcx, rdi; hDlg
0x180063399  call    cs:__imp_IsDlgButtonChecked
0x18006339f  test    eax, eax
0x1800633a1  jz      loc_180063434
0x1800633a7  mov     edx, 323h; nIDDlgItem
0x1800633ac  mov     rcx, rdi; hDlg
0x1800633af  call    cs:__imp_GetDlgItem
0x1800633b5  mov     r8d, 0Ah; nMaxCount
0x1800633bb  lea     rdx, [rbp+0C80h+pszSrc]; lpString
0x1800633bf  mov     rcx, rax; hWnd
0x1800633c2  call    cs:__imp_GetWindowTextW
0x1800633c8  lea     rcx, [rbp+0C80h+pszSrc]; pszSrc
0x1800633cc  call    cs:__imp_StrToIntW
0x1800633d2  mov     [r15+208h], eax
0x1800633d9  dec     eax
0x1800633db  cmp     eax, 3E6h
0x1800633e0  jbe     short loc_18006343F
0x1800633e2  mov     rax, cs:__imp_MessageBoxW
0x1800633e9  mov     r9d, 509h
0x1800633ef  mov     rcx, cs:?g_hLocRes@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hLocRes
0x1800633f6  mov     r8, r14
0x1800633f9  mov     [rsp+0D80h+var_D28], ebx
0x1800633fd  mov     rdx, rdi
0x180063400  mov     [rsp+0D80h+var_D30], rbx
0x180063405  mov     [rsp+0D80h+var_D38], rbx
0x18006340a  mov     [rsp+0D80h+var_D40], rbx
0x18006340f  mov     [rsp+0D80h+var_D48], rax
0x180063414  mov     rax, cs:__imp_LoadStringW
0x18006341b  mov     [rsp+0D80h+var_D50], rax
0x180063420  mov     [rsp+0D80h+var_D58], ebx
0x180063424  mov     [rsp+0D80h+lParam], rbx
0x180063429  call    cs:__imp_MessageBoxInstW
0x18006342f  jmp     loc_18006356D
0x180063434  mov     dword ptr [r15+208h], 0FFFFFFFFh
0x18006343f  mov     rdx, r12; nResult
0x180063442  mov     rcx, rdi; hDlg
0x180063445  call    cs:__imp_EndDialog
0x18006344b  jmp     loc_1800632E4
0x180063450  mov     r14d, 320h
0x180063456  mov     rcx, rdi; hDlg
0x180063459  mov     edx, r14d; nIDDlgItem
0x18006345c  call    cs:__imp_GetDlgItem
0x180063462  mov     ebx, 0C5h
0x180063467  xor     r9d, r9d; lParam
0x18006346a  mov     rcx, rax; hWnd
0x18006346d  mov     edx, ebx; Msg
0x18006346f  lea     r8d, [rbx+3Eh]; wParam
0x180063473  call    cs:__imp_SendMessageA
0x180063479  lea     edx, [r14+3]; nIDDlgItem
0x18006347d  mov     rcx, rdi; hDlg
0x180063480  call    cs:__imp_GetDlgItem
0x180063486  xor     r9d, r9d; lParam
0x180063489  mov     edx, ebx; Msg
0x18006348b  mov     rcx, rax; hWnd
0x18006348e  lea     r8d, [r9+3]; wParam
0x180063492  call    cs:__imp_SendMessageA
0x180063498  mov     edx, r14d; nIDDlgItem
0x18006349b  mov     rcx, rdi; hDlg
0x18006349e  call    cs:__imp_GetDlgItem
0x1800634a4  mov     rcx, rax; hWnd
0x1800634a7  mov     rdx, r15; lpString
0x1800634aa  call    cs:__imp_SetWindowTextW
0x1800634b0  mov     eax, [r15+208h]
0x1800634b7  lea     r8, aD; "%d"
0x1800634be  mov     esi, 1
0x1800634c3  lea     rcx, [rbp+0C80h+pszSrc]; unsigned __int16 *
0x1800634c7  cmp     eax, esi
0x1800634c9  mov     r9d, esi
0x1800634cc  cmovg   r9d, eax
0x1800634d0  lea     edx, [rsi+9]; unsigned __int64
0x1800634d3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800634d8  lea     edx, [r14+3]; nIDDlgItem
0x1800634dc  mov     rcx, rdi; hDlg
0x1800634df  call    cs:__imp_GetDlgItem
0x1800634e5  mov     rcx, rax; hWnd
0x1800634e8  lea     rdx, [rbp+0C80h+pszSrc]; lpString
0x1800634ec  call    cs:__imp_SetWindowTextW
0x1800634f2  cmp     dword ptr [r15+208h], 0FFFFFFFFh
0x1800634fa  lea     r8d, [r14+4]; nIDLastButton
0x1800634fe  mov     r9d, r8d
0x180063501  lea     edx, [r14+2]; nIDFirstButton
0x180063505  cmovnz  r9d, edx; nIDCheckButton
0x180063509  mov     rcx, rdi; hDlg
0x18006350c  call    cs:__imp_CheckRadioButton
0x180063512  xor     r9d, r9d; wParam
0x180063515  mov     [rsp+0D80h+lParam], 103E7h; lParam
0x18006351e  lea     edx, [r14-5Ch]; nIDDlgItem
0x180063522  mov     r8d, 465h; Msg
0x180063528  mov     rcx, rdi; hDlg
0x18006352b  call    cs:__imp_SendDlgItemMessageA
0x180063531  mov     r8, r15; dwNewLong
0x180063534  lea     edx, [rsi+0Fh]; nIndex
0x180063537  mov     rcx, rdi; hWnd
0x18006353a  call    cs:__imp_SetWindowLongPtrA
0x180063540  test    rdi, rdi
0x180063543  jz      short loc_18006356D
0x180063545  mov     edx, r14d; nIDDlgItem
0x180063548  mov     rcx, rdi; hDlg
0x18006354b  call    cs:__imp_GetDlgItem
0x180063551  test    rax, rax
0x180063554  jz      short loc_18006356D
0x180063556  mov     edx, r14d; nIDDlgItem
0x180063559  mov     rcx, rdi; hDlg
0x18006355c  call    cs:__imp_GetDlgItem
0x180063562  mov     rcx, rax; hwndEdit
0x180063565  mov     edx, esi; dwFlags
0x180063567  call    cs:__imp_SHAutoComplete
0x18006356d  xor     eax, eax
0x18006356f  mov     rcx, [rbp+0C80h+var_40]
0x180063576  xor     rcx, rsp; StackCookie
0x180063579  call    __security_check_cookie
0x18006357e  add     rsp, 0D50h
0x180063585  pop     r15
0x180063587  pop     r14
0x180063589  pop     r12
0x18006358b  pop     rdi
0x18006358c  pop     rsi
0x18006358d  pop     rbx
0x18006358e  pop     rbp
0x18006358f  retn
```
