# Number_SetDigitGroupingValues(HWND__ *)

- ea: `0x18001b014`
- end: `0x18001b3ea`
- name: `?Number_SetDigitGroupingValues@@YAXPEAUHWND__@@@Z`
- size: `982`
- prototype: `void __fastcall(HWND)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b3f0`

## callees

- `0x18001b014`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18001b0a8`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18001b21a`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18001b0a8`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x18001b21a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b23d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b269`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b28d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b2b1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b2d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b311`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b23d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b269`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b28d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b2b1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b2d5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001b311`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b0eb`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b143`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b191`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b1df`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b362`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b0eb`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b143`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b191`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b1df`
- `api-ms-win-core-localization-l2-1-0!GetNumberFormatEx` at `0x18001b362`
- `USER32!GetDlgItem` at `0x18001b045`
- `USER32!GetDlgItem` at `0x18001b045`
- `USER32!SendMessageW` at `0x18001b108`
- `USER32!SendMessageW` at `0x18001b156`
- `USER32!SendMessageW` at `0x18001b1a4`
- `USER32!SendMessageW` at `0x18001b1f2`
- `USER32!SendMessageW` at `0x18001b379`
- `USER32!SendMessageW` at `0x18001b397`
- `USER32!SendMessageW` at `0x18001b3bc`
- `USER32!SendMessageW` at `0x18001b108`
- `USER32!SendMessageW` at `0x18001b156`
- `USER32!SendMessageW` at `0x18001b1a4`
- `USER32!SendMessageW` at `0x18001b1f2`
- `USER32!SendMessageW` at `0x18001b379`
- `USER32!SendMessageW` at `0x18001b397`
- `USER32!SendMessageW` at `0x18001b3bc`

## pseudocode

```c
void __fastcall Number_SetDigitGroupingValues(HWND a1)
{
  HWND DlgItem; // rdi
  int v2; // ebx
  WCHAR v3; // cx
  int v4; // eax
  NUMBERFMTW Format; // [rsp+30h] [rbp-89h] BYREF
  WCHAR LCData[4]; // [rsp+58h] [rbp-61h] BYREF
  WCHAR NumberStr; // [rsp+60h] [rbp-59h] BYREF
  WCHAR String1[63]; // [rsp+62h] [rbp-57h] BYREF

  *(_QWORD *)&Format.Grouping = 0;
  *(_QWORD *)&Format.NegativeOrder = 0;
  DlgItem = GetDlgItem(a1, 1074);
  memset_0(&NumberStr, 0, 0x80u);
  Format.lpDecimalSep = (LPWSTR)&LocaleName;
  *(_QWORD *)LCData = 0;
  Format.lpThousandSep = LCData;
  *(_QWORD *)&Format.NumDigits = 0;
  GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), 0xFu, LCData, 4);
  GetNumberFormatEx(
    *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
    0,
    L"123456789",
    &Format,
    &NumberStr,
    64);
  SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&NumberStr);
  Format.Grouping = 3;
  GetNumberFormatEx(
    *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
    0,
    L"123456789",
    &Format,
    &NumberStr,
    64);
  SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&NumberStr);
  Format.Grouping = 30;
  GetNumberFormatEx(
    *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
    0,
    L"123456789",
    &Format,
    &NumberStr,
    64);
  SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&NumberStr);
  Format.Grouping = 32;
  GetNumberFormatEx(
    *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
    0,
    L"123456789",
    &Format,
    &NumberStr,
    64);
  SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&NumberStr);
  v2 = 0;
  if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), 0x10u, &NumberStr, 64) )
  {
    if ( CompareStringOrdinal(&NumberStr, -1, L"3;0", -1, 0) == 2 )
    {
      v2 = 1;
    }
    else
    {
      if ( CompareStringOrdinal(&NumberStr, -1, L"3", -1, 0) == 2
        || CompareStringOrdinal(&NumberStr, -1, L"3;0;0", -1, 0) == 2 )
      {
        v2 = 2;
        goto LABEL_18;
      }
      if ( CompareStringOrdinal(&NumberStr, -1, L"3;2", -1, 0) == 2
        || CompareStringOrdinal(&NumberStr, -1, L"3;2;0", -1, 0) == 2 )
      {
        v2 = 3;
        goto LABEL_18;
      }
      v3 = NumberStr;
      if ( (unsigned __int16)(NumberStr - 49) <= 8u )
      {
        if ( String1[0] )
        {
          if ( CompareStringOrdinal(String1, -1, L";0", -1, 0) != 2 )
            goto LABEL_18;
          v3 = NumberStr;
        }
        Format.Grouping = v3 - 48;
        if ( GetNumberFormatEx(
               *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
               0,
               L"123456789",
               &Format,
               &NumberStr,
               64) )
        {
          v4 = SendMessageW(DlgItem, 0x14Au, 0xFFFFFFFFFFFFFFFFuLL, (LPARAM)&NumberStr);
          v2 = v4;
          if ( v4 == -1 )
            v2 = 0;
          else
            SendMessageW(DlgItem, 0x151u, v4, Format.Grouping);
        }
      }
    }
  }
LABEL_18:
  SendMessageW(DlgItem, 0x14Eu, v2, 0);
}

```

## disassembly

```asm
0x18001b014  mov     [rsp-8+arg_8], rbx
0x18001b019  mov     [rsp-8+arg_10], rsi
0x18001b01e  push    rbp
0x18001b01f  push    rdi
0x18001b020  push    r13
0x18001b022  push    r14
0x18001b024  push    r15
0x18001b026  lea     rbp, [rsp-37h]
0x18001b02b  sub     rsp, 0F0h
0x18001b032  mov     rax, cs:__security_cookie
0x18001b039  xor     rax, rsp
0x18001b03c  mov     [rbp+57h+var_30], rax
0x18001b040  mov     edx, 432h; nIDDlgItem
0x18001b045  call    cs:__imp_GetDlgItem
0x18001b04b  xor     r14d, r14d
0x18001b04e  lea     rcx, [rbp+57h+NumberStr]; void *
0x18001b052  xor     edx, edx; Val
0x18001b054  mov     qword ptr [rsp+110h+Format.Grouping], r14
0x18001b059  mov     r8d, 80h; Size
0x18001b05f  mov     qword ptr [rbp+57h+Format.NegativeOrder], r14
0x18001b063  mov     rdi, rax
0x18001b066  call    memset_0
0x18001b06b  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001b071  lea     rax, LocaleName
0x18001b078  mov     [rbp+57h+Format.lpDecimalSep], rax
0x18001b07c  lea     r9d, [r14+4]; cchData
0x18001b080  mov     qword ptr [rbp+57h+LCData], r14
0x18001b084  lea     rax, [rbp+57h+LCData]
0x18001b088  mov     [rbp+57h+Format.lpThousandSep], rax
0x18001b08c  lea     r8, [rbp+57h+LCData]; lpLCData
0x18001b090  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001b097  lea     edx, [r14+0Fh]; LCType
0x18001b09b  mov     qword ptr [rsp+110h+Format.NumDigits], r14
0x18001b0a0  mov     rcx, [rax+rcx*8]
0x18001b0a4  mov     rcx, [rcx+8]; lpLocaleName
0x18001b0a8  call    cs:__imp_GetLocaleInfoEx
0x18001b0ae  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001b0b5  lea     r15d, [r14+40h]
0x18001b0b9  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001b0bf  lea     rbx, a123456789; "123456789"
0x18001b0c6  mov     [rsp+110h+Format.Grouping], r14d
0x18001b0cb  lea     r9, [rsp+110h+Format]; lpFormat
0x18001b0d0  mov     [rsp+110h+cchNumber], r15d; cchNumber
0x18001b0d5  mov     r8, rbx; lpValue
0x18001b0d8  xor     edx, edx; dwFlags
0x18001b0da  mov     rcx, [rax+rcx*8]
0x18001b0de  lea     rax, [rbp+57h+NumberStr]
0x18001b0e2  mov     [rsp+110h+lpNumberStr], rax; lpNumberStr
0x18001b0e7  mov     rcx, [rcx+8]; lpLocaleName
0x18001b0eb  call    cs:__imp_GetNumberFormatEx
0x18001b0f1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001b0f5  lea     r9, [rbp+57h+NumberStr]; lParam
0x18001b0f9  mov     r13d, 14Ah
0x18001b0ff  mov     r8, rsi; wParam
0x18001b102  mov     edx, r13d; Msg
0x18001b105  mov     rcx, rdi; hWnd
0x18001b108  call    cs:__imp_SendMessageW
0x18001b10e  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001b115  lea     r9, [rsp+110h+Format]; lpFormat
0x18001b11a  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001b120  mov     r8, rbx; lpValue
0x18001b123  mov     [rsp+110h+Format.Grouping], 3
0x18001b12b  xor     edx, edx; dwFlags
0x18001b12d  mov     [rsp+110h+cchNumber], r15d; cchNumber
0x18001b132  mov     rcx, [rax+rcx*8]
0x18001b136  lea     rax, [rbp+57h+NumberStr]
0x18001b13a  mov     [rsp+110h+lpNumberStr], rax; lpNumberStr
0x18001b13f  mov     rcx, [rcx+8]; lpLocaleName
0x18001b143  call    cs:__imp_GetNumberFormatEx
0x18001b149  lea     r9, [rbp+57h+NumberStr]; lParam
0x18001b14d  mov     r8, rsi; wParam
0x18001b150  mov     edx, r13d; Msg
0x18001b153  mov     rcx, rdi; hWnd
0x18001b156  call    cs:__imp_SendMessageW
0x18001b15c  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001b163  lea     r9, [rsp+110h+Format]; lpFormat
0x18001b168  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001b16e  mov     r8, rbx; lpValue
0x18001b171  mov     [rsp+110h+Format.Grouping], 1Eh
0x18001b179  xor     edx, edx; dwFlags
0x18001b17b  mov     [rsp+110h+cchNumber], r15d; cchNumber
0x18001b180  mov     rcx, [rax+rcx*8]
0x18001b184  lea     rax, [rbp+57h+NumberStr]
0x18001b188  mov     [rsp+110h+lpNumberStr], rax; lpNumberStr
0x18001b18d  mov     rcx, [rcx+8]; lpLocaleName
0x18001b191  call    cs:__imp_GetNumberFormatEx
0x18001b197  lea     r9, [rbp+57h+NumberStr]; lParam
0x18001b19b  mov     r8, rsi; wParam
0x18001b19e  mov     edx, r13d; Msg
0x18001b1a1  mov     rcx, rdi; hWnd
0x18001b1a4  call    cs:__imp_SendMessageW
0x18001b1aa  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001b1b0  mov     [rsp+110h+Format.Grouping], 20h ; ' '
0x18001b1b8  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001b1bf  lea     r9, [rsp+110h+Format]; lpFormat
0x18001b1c4  mov     [rsp+110h+cchNumber], r15d; cchNumber
0x18001b1c9  mov     r8, rbx; lpValue
0x18001b1cc  xor     edx, edx; dwFlags
0x18001b1ce  mov     rcx, [rax+rcx*8]
0x18001b1d2  lea     rax, [rbp+57h+NumberStr]
0x18001b1d6  mov     [rsp+110h+lpNumberStr], rax; lpNumberStr
0x18001b1db  mov     rcx, [rcx+8]; lpLocaleName
0x18001b1df  call    cs:__imp_GetNumberFormatEx
0x18001b1e5  lea     r9, [rbp+57h+NumberStr]; lParam
0x18001b1e9  mov     r8, rsi; wParam
0x18001b1ec  mov     edx, r13d; Msg
0x18001b1ef  mov     rcx, rdi; hWnd
0x18001b1f2  call    cs:__imp_SendMessageW
0x18001b1f8  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001b1fe  lea     r8, [rbp+57h+NumberStr]; lpLCData
0x18001b202  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001b209  lea     edx, [rsi+11h]; LCType
0x18001b20c  mov     r9d, r15d; cchData
0x18001b20f  mov     ebx, r14d
0x18001b212  mov     rcx, [rax+rcx*8]
0x18001b216  mov     rcx, [rcx+8]; lpLocaleName
0x18001b21a  call    cs:__imp_GetLocaleInfoEx
0x18001b220  test    eax, eax
0x18001b222  jz      loc_18001B3AE
0x18001b228  mov     r9d, esi; cchCount2
0x18001b22b  mov     dword ptr [rsp+110h+lpNumberStr], r14d; bIgnoreCase
0x18001b230  lea     r8, a30; "3;0"
0x18001b237  mov     edx, esi; cchCount1
0x18001b239  lea     rcx, [rbp+57h+NumberStr]; lpString1
0x18001b23d  call    cs:__imp_CompareStringOrdinal
0x18001b243  lea     r15d, [r14+2]
0x18001b247  cmp     eax, r15d
0x18001b24a  jnz     short loc_18001B254
0x18001b24c  lea     ebx, [rsi+2]
0x18001b24f  jmp     loc_18001B3AE
0x18001b254  mov     r9d, esi; cchCount2
0x18001b257  mov     dword ptr [rsp+110h+lpNumberStr], r14d; bIgnoreCase
0x18001b25c  lea     r8, a3; "3"
0x18001b263  mov     edx, esi; cchCount1
0x18001b265  lea     rcx, [rbp+57h+NumberStr]; lpString1
0x18001b269  call    cs:__imp_CompareStringOrdinal
0x18001b26f  cmp     eax, r15d
0x18001b272  jz      loc_18001B3AB
0x18001b278  mov     r9d, esi; cchCount2
0x18001b27b  mov     dword ptr [rsp+110h+lpNumberStr], r14d; bIgnoreCase
0x18001b280  lea     r8, a300; "3;0;0"
0x18001b287  mov     edx, esi; cchCount1
0x18001b289  lea     rcx, [rbp+57h+NumberStr]; lpString1
0x18001b28d  call    cs:__imp_CompareStringOrdinal
0x18001b293  cmp     eax, r15d
0x18001b296  jz      loc_18001B3AB
0x18001b29c  mov     r9d, esi; cchCount2
0x18001b29f  mov     dword ptr [rsp+110h+lpNumberStr], r14d; bIgnoreCase
0x18001b2a4  lea     r8, a32; "3;2"
0x18001b2ab  mov     edx, esi; cchCount1
0x18001b2ad  lea     rcx, [rbp+57h+NumberStr]; lpString1
0x18001b2b1  call    cs:__imp_CompareStringOrdinal
0x18001b2b7  cmp     eax, r15d
0x18001b2ba  jz      loc_18001B3A4
0x18001b2c0  mov     r9d, esi; cchCount2
0x18001b2c3  mov     dword ptr [rsp+110h+lpNumberStr], r14d; bIgnoreCase
0x18001b2c8  lea     r8, a320; "3;2;0"
0x18001b2cf  mov     edx, esi; cchCount1
0x18001b2d1  lea     rcx, [rbp+57h+NumberStr]; lpString1
0x18001b2d5  call    cs:__imp_CompareStringOrdinal
0x18001b2db  cmp     eax, r15d
0x18001b2de  jz      loc_18001B3A4
0x18001b2e4  movzx   ecx, [rbp+57h+NumberStr]
0x18001b2e8  lea     eax, [rcx-31h]
0x18001b2eb  cmp     ax, 8
0x18001b2ef  ja      loc_18001B3AE
0x18001b2f5  cmp     [rbp+57h+String1], r14w
0x18001b2fa  jz      short loc_18001B324
0x18001b2fc  mov     r9d, esi; cchCount2
0x18001b2ff  mov     dword ptr [rsp+110h+lpNumberStr], r14d; bIgnoreCase
0x18001b304  lea     r8, a0_0; ";0"
0x18001b30b  mov     edx, esi; cchCount1
0x18001b30d  lea     rcx, [rbp+57h+String1]; lpString1
0x18001b311  call    cs:__imp_CompareStringOrdinal
0x18001b317  cmp     eax, r15d
0x18001b31a  jnz     loc_18001B3AE
0x18001b320  movzx   ecx, [rbp+57h+NumberStr]
0x18001b324  movzx   eax, cx
0x18001b327  lea     r9, [rsp+110h+Format]; lpFormat
0x18001b32c  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001b332  lea     r8, a123456789; "123456789"
0x18001b339  sub     eax, 30h ; '0'
0x18001b33c  mov     [rsp+110h+cchNumber], 40h ; '@'; cchNumber
0x18001b344  mov     [rsp+110h+Format.Grouping], eax
0x18001b348  xor     edx, edx; dwFlags
0x18001b34a  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001b351  mov     rcx, [rax+rcx*8]
0x18001b355  lea     rax, [rbp+57h+NumberStr]
0x18001b359  mov     [rsp+110h+lpNumberStr], rax; lpNumberStr
0x18001b35e  mov     rcx, [rcx+8]; lpLocaleName
0x18001b362  call    cs:__imp_GetNumberFormatEx
0x18001b368  test    eax, eax
0x18001b36a  jz      short loc_18001B3AE
0x18001b36c  lea     r9, [rbp+57h+NumberStr]; lParam
0x18001b370  mov     r8, rsi; wParam
0x18001b373  mov     edx, r13d; Msg
0x18001b376  mov     rcx, rdi; hWnd
0x18001b379  call    cs:__imp_SendMessageW
0x18001b37f  mov     rbx, rax
0x18001b382  cmp     eax, 0FFFFFFFFh
0x18001b385  jz      short loc_18001B39F
0x18001b387  mov     r9d, [rsp+110h+Format.Grouping]; lParam
0x18001b38c  mov     edx, 151h; Msg
0x18001b391  movsxd  r8, eax; wParam
0x18001b394  mov     rcx, rdi; hWnd
0x18001b397  call    cs:__imp_SendMessageW
0x18001b39d  jmp     short loc_18001B3AE
0x18001b39f  mov     ebx, r14d
0x18001b3a2  jmp     short loc_18001B3AE
0x18001b3a4  mov     ebx, 3
0x18001b3a9  jmp     short loc_18001B3AE
0x18001b3ab  mov     ebx, r15d
0x18001b3ae  movsxd  r8, ebx; wParam
0x18001b3b1  xor     r9d, r9d; lParam
0x18001b3b4  mov     edx, 14Eh; Msg
0x18001b3b9  mov     rcx, rdi; hWnd
0x18001b3bc  call    cs:__imp_SendMessageW
0x18001b3c2  mov     rcx, [rbp+57h+var_30]
0x18001b3c6  xor     rcx, rsp; StackCookie
0x18001b3c9  call    __security_check_cookie
0x18001b3ce  lea     r11, [rsp+110h+var_20]
0x18001b3d6  mov     rbx, [r11+38h]
0x18001b3da  mov     rsi, [r11+40h]
0x18001b3de  mov     rsp, r11
0x18001b3e1  pop     r15
0x18001b3e3  pop     r14
0x18001b3e5  pop     r13
0x18001b3e7  pop     rdi
0x18001b3e8  pop     rbp
0x18001b3e9  retn
```
