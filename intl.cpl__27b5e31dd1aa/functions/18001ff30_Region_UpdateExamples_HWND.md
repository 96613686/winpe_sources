# Region_UpdateExamples(HWND__ *)

- ea: `0x18001ff30`
- end: `0x1800201d1`
- name: `?Region_UpdateExamples@@YAXPEAUHWND__@@@Z`
- size: `673`
- prototype: `void __fastcall(HWND hDlg)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18001e340`
- `0x18001fcac`

## callees

- `0x18001ff30`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001ff5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18001ff5f`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180020113`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18002019c`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x180020113`
- `api-ms-win-core-datetime-l1-1-1!GetTimeFormatEx` at `0x18002019c`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18001fff5`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18002008a`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18001fff5`
- `api-ms-win-core-datetime-l1-1-1!GetDateFormatEx` at `0x18002008a`
- `USER32!GetDlgItem` at `0x18001ff6d`
- `USER32!GetDlgItem` at `0x18002001a`
- `USER32!GetDlgItem` at `0x1800200af`
- `USER32!GetDlgItem` at `0x180020138`
- `USER32!GetDlgItem` at `0x18001ff6d`
- `USER32!GetDlgItem` at `0x18002001a`
- `USER32!GetDlgItem` at `0x1800200af`
- `USER32!GetDlgItem` at `0x180020138`
- `USER32!SendMessageW` at `0x18001ff84`
- `USER32!SendMessageW` at `0x18001ffad`
- `USER32!SendMessageW` at `0x180020031`
- `USER32!SendMessageW` at `0x180020045`
- `USER32!SendMessageW` at `0x1800200c6`
- `USER32!SendMessageW` at `0x1800200da`
- `USER32!SendMessageW` at `0x18002014f`
- `USER32!SendMessageW` at `0x180020163`
- `USER32!SendMessageW` at `0x18001ff84`
- `USER32!SendMessageW` at `0x18001ffad`
- `USER32!SendMessageW` at `0x180020031`
- `USER32!SendMessageW` at `0x180020045`
- `USER32!SendMessageW` at `0x1800200c6`
- `USER32!SendMessageW` at `0x1800200da`
- `USER32!SendMessageW` at `0x18002014f`
- `USER32!SendMessageW` at `0x180020163`
- `USER32!SetDlgItemTextW` at `0x18002000c`
- `USER32!SetDlgItemTextW` at `0x1800200a1`
- `USER32!SetDlgItemTextW` at `0x18002012a`
- `USER32!SetDlgItemTextW` at `0x1800201b3`
- `USER32!SetDlgItemTextW` at `0x18002000c`
- `USER32!SetDlgItemTextW` at `0x1800200a1`
- `USER32!SetDlgItemTextW` at `0x18002012a`
- `USER32!SetDlgItemTextW` at `0x1800201b3`

## pseudocode

```c
void __fastcall Region_UpdateExamples(HWND hDlg)
{
  HWND DlgItem; // rdi
  int v3; // ebx
  const WCHAR *v4; // rax
  HWND v5; // rbx
  int v6; // eax
  const WCHAR *v7; // rax
  HWND v8; // rbx
  int v9; // eax
  const WCHAR *v10; // rax
  HWND v11; // rbx
  int v12; // eax
  const WCHAR *v13; // rax
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR DateStr[80]; // [rsp+50h] [rbp-B0h] BYREF

  SystemTime = 0;
  GetLocalTime(&SystemTime);
  DlgItem = GetDlgItem(hDlg, 1029);
  v3 = SendMessageW(DlgItem, 0x147u, 0, 0);
  memset_0(DateStr, 0, sizeof(DateStr));
  v4 = (const WCHAR *)SendMessageW(DlgItem, 0x150u, v3, 0);
  if ( v4 != (const WCHAR *)-1LL
    && GetDateFormatEx(
         *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
         0x40u,
         &SystemTime,
         v4,
         DateStr,
         80,
         0) )
  {
    SetDlgItemTextW(hDlg, 1036, DateStr);
  }
  v5 = GetDlgItem(hDlg, 1028);
  v6 = SendMessageW(v5, 0x147u, 0, 0);
  v7 = (const WCHAR *)SendMessageW(v5, 0x150u, v6, 0);
  if ( v7 != (const WCHAR *)-1LL
    && GetDateFormatEx(
         *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
         0x40u,
         &SystemTime,
         v7,
         DateStr,
         80,
         0) )
  {
    SetDlgItemTextW(hDlg, 1035, DateStr);
  }
  v8 = GetDlgItem(hDlg, 1030);
  v9 = SendMessageW(v8, 0x147u, 0, 0);
  v10 = (const WCHAR *)SendMessageW(v8, 0x150u, v9, 0);
  if ( v10 != (const WCHAR *)-1LL
    && GetTimeFormatEx(
         *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
         0,
         &SystemTime,
         v10,
         DateStr,
         80) )
  {
    SetDlgItemTextW(hDlg, 1037, DateStr);
  }
  v11 = GetDlgItem(hDlg, 1031);
  v12 = SendMessageW(v11, 0x147u, 0, 0);
  v13 = (const WCHAR *)SendMessageW(v11, 0x150u, v12, 0);
  if ( v13 != (const WCHAR *)-1LL )
  {
    if ( GetTimeFormatEx(
           *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
           0,
           &SystemTime,
           v13,
           DateStr,
           80) )
    {
      SetDlgItemTextW(hDlg, 1038, DateStr);
    }
  }
}

```

## disassembly

```asm
0x18001ff30  push    rbp
0x18001ff32  push    rbx
0x18001ff33  push    rsi
0x18001ff34  push    rdi
0x18001ff35  lea     rbp, [rsp-8]
0x18001ff3a  sub     rsp, 108h
0x18001ff41  mov     rax, cs:__security_cookie
0x18001ff48  xor     rax, rsp
0x18001ff4b  mov     [rbp+20h+var_30], rax
0x18001ff4f  mov     rsi, rcx
0x18001ff52  xorps   xmm0, xmm0
0x18001ff55  lea     rcx, [rsp+120h+SystemTime]; lpSystemTime
0x18001ff5a  movups  xmmword ptr [rsp+120h+SystemTime.wYear], xmm0
0x18001ff5f  call    cs:__imp_GetLocalTime
0x18001ff65  mov     edx, 405h; nIDDlgItem
0x18001ff6a  mov     rcx, rsi; hDlg
0x18001ff6d  call    cs:__imp_GetDlgItem
0x18001ff73  xor     r9d, r9d; lParam
0x18001ff76  xor     r8d, r8d; wParam
0x18001ff79  mov     rcx, rax; hWnd
0x18001ff7c  mov     edx, 147h; Msg
0x18001ff81  mov     rdi, rax
0x18001ff84  call    cs:__imp_SendMessageW
0x18001ff8a  xor     edx, edx; Val
0x18001ff8c  lea     rcx, [rsp+120h+DateStr]; void *
0x18001ff91  mov     r8d, 0A0h; Size
0x18001ff97  mov     rbx, rax
0x18001ff9a  call    memset_0
0x18001ff9f  movsxd  r8, ebx; wParam
0x18001ffa2  xor     r9d, r9d; lParam
0x18001ffa5  mov     edx, 150h; Msg
0x18001ffaa  mov     rcx, rdi; hWnd
0x18001ffad  call    cs:__imp_SendMessageW
0x18001ffb3  mov     edi, 50h ; 'P'
0x18001ffb8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ffbc  jz      short loc_180020012
0x18001ffbe  mov     edx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001ffc4  lea     r8, [rsp+120h+SystemTime]; lpDate
0x18001ffc9  mov     rcx, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001ffd0  mov     r9, rax; lpFormat
0x18001ffd3  mov     [rsp+120h+lpCalendar], 0; lpCalendar
0x18001ffdc  mov     [rsp+120h+cchDate], edi; cchDate
0x18001ffe0  mov     rcx, [rcx+rdx*8]
0x18001ffe4  lea     rdx, [rsp+120h+DateStr]
0x18001ffe9  mov     [rsp+120h+lpDateStr], rdx; lpDateStr
0x18001ffee  lea     edx, [rdi-10h]; dwFlags
0x18001fff1  mov     rcx, [rcx+8]; lpLocaleName
0x18001fff5  call    cs:__imp_GetDateFormatEx
0x18001fffb  test    eax, eax
0x18001fffd  jz      short loc_180020012
0x18001ffff  lea     r8, [rsp+120h+DateStr]; lpString
0x180020004  mov     edx, 40Ch; nIDDlgItem
0x180020009  mov     rcx, rsi; hDlg
0x18002000c  call    cs:__imp_SetDlgItemTextW
0x180020012  mov     edx, 404h; nIDDlgItem
0x180020017  mov     rcx, rsi; hDlg
0x18002001a  call    cs:__imp_GetDlgItem
0x180020020  xor     r9d, r9d; lParam
0x180020023  xor     r8d, r8d; wParam
0x180020026  mov     rcx, rax; hWnd
0x180020029  mov     edx, 147h; Msg
0x18002002e  mov     rbx, rax
0x180020031  call    cs:__imp_SendMessageW
0x180020037  movsxd  r8, eax; wParam
0x18002003a  xor     r9d, r9d; lParam
0x18002003d  mov     edx, 150h; Msg
0x180020042  mov     rcx, rbx; hWnd
0x180020045  call    cs:__imp_SendMessageW
0x18002004b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002004f  jz      short loc_1800200A7
0x180020051  mov     edx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180020057  lea     r8, [rsp+120h+SystemTime]; lpDate
0x18002005c  mov     rcx, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180020063  mov     r9, rax; lpFormat
0x180020066  mov     [rsp+120h+lpCalendar], 0; lpCalendar
0x18002006f  mov     [rsp+120h+cchDate], edi; cchDate
0x180020073  mov     rcx, [rcx+rdx*8]
0x180020077  lea     rdx, [rsp+120h+DateStr]
0x18002007c  mov     [rsp+120h+lpDateStr], rdx; lpDateStr
0x180020081  mov     edx, 40h ; '@'; dwFlags
0x180020086  mov     rcx, [rcx+8]; lpLocaleName
0x18002008a  call    cs:__imp_GetDateFormatEx
0x180020090  test    eax, eax
0x180020092  jz      short loc_1800200A7
0x180020094  lea     r8, [rsp+120h+DateStr]; lpString
0x180020099  mov     edx, 40Bh; nIDDlgItem
0x18002009e  mov     rcx, rsi; hDlg
0x1800200a1  call    cs:__imp_SetDlgItemTextW
0x1800200a7  mov     edx, 406h; nIDDlgItem
0x1800200ac  mov     rcx, rsi; hDlg
0x1800200af  call    cs:__imp_GetDlgItem
0x1800200b5  xor     r9d, r9d; lParam
0x1800200b8  xor     r8d, r8d; wParam
0x1800200bb  mov     rcx, rax; hWnd
0x1800200be  mov     edx, 147h; Msg
0x1800200c3  mov     rbx, rax
0x1800200c6  call    cs:__imp_SendMessageW
0x1800200cc  movsxd  r8, eax; wParam
0x1800200cf  xor     r9d, r9d; lParam
0x1800200d2  mov     edx, 150h; Msg
0x1800200d7  mov     rcx, rbx; hWnd
0x1800200da  call    cs:__imp_SendMessageW
0x1800200e0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800200e4  jz      short loc_180020130
0x1800200e6  mov     edx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x1800200ec  lea     r8, [rsp+120h+SystemTime]; lpTime
0x1800200f1  mov     rcx, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x1800200f8  mov     r9, rax; lpFormat
0x1800200fb  mov     [rsp+120h+cchDate], edi; cchTime
0x1800200ff  mov     rcx, [rcx+rdx*8]
0x180020103  lea     rdx, [rsp+120h+DateStr]
0x180020108  mov     [rsp+120h+lpDateStr], rdx; lpTimeStr
0x18002010d  xor     edx, edx; dwFlags
0x18002010f  mov     rcx, [rcx+8]; lpLocaleName
0x180020113  call    cs:__imp_GetTimeFormatEx
0x180020119  test    eax, eax
0x18002011b  jz      short loc_180020130
0x18002011d  lea     r8, [rsp+120h+DateStr]; lpString
0x180020122  mov     edx, 40Dh; nIDDlgItem
0x180020127  mov     rcx, rsi; hDlg
0x18002012a  call    cs:__imp_SetDlgItemTextW
0x180020130  mov     edx, 407h; nIDDlgItem
0x180020135  mov     rcx, rsi; hDlg
0x180020138  call    cs:__imp_GetDlgItem
0x18002013e  xor     r9d, r9d; lParam
0x180020141  xor     r8d, r8d; wParam
0x180020144  mov     rcx, rax; hWnd
0x180020147  mov     edx, 147h; Msg
0x18002014c  mov     rbx, rax
0x18002014f  call    cs:__imp_SendMessageW
0x180020155  movsxd  r8, eax; wParam
0x180020158  xor     r9d, r9d; lParam
0x18002015b  mov     edx, 150h; Msg
0x180020160  mov     rcx, rbx; hWnd
0x180020163  call    cs:__imp_SendMessageW
0x180020169  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002016d  jz      short loc_1800201B9
0x18002016f  mov     edx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180020175  lea     r8, [rsp+120h+SystemTime]; lpTime
0x18002017a  mov     rcx, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180020181  mov     r9, rax; lpFormat
0x180020184  mov     [rsp+120h+cchDate], edi; cchTime
0x180020188  mov     rcx, [rcx+rdx*8]
0x18002018c  lea     rdx, [rsp+120h+DateStr]
0x180020191  mov     [rsp+120h+lpDateStr], rdx; lpTimeStr
0x180020196  xor     edx, edx; dwFlags
0x180020198  mov     rcx, [rcx+8]; lpLocaleName
0x18002019c  call    cs:__imp_GetTimeFormatEx
0x1800201a2  test    eax, eax
0x1800201a4  jz      short loc_1800201B9
0x1800201a6  lea     r8, [rsp+120h+DateStr]; lpString
0x1800201ab  mov     edx, 40Eh; nIDDlgItem
0x1800201b0  mov     rcx, rsi; hDlg
0x1800201b3  call    cs:__imp_SetDlgItemTextW
0x1800201b9  mov     rcx, [rbp+20h+var_30]
0x1800201bd  xor     rcx, rsp; StackCookie
0x1800201c0  call    __security_check_cookie
0x1800201c5  add     rsp, 108h
0x1800201cc  pop     rdi
0x1800201cd  pop     rsi
0x1800201ce  pop     rbx
0x1800201cf  pop     rbp
0x1800201d0  retn
```
