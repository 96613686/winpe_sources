# Date_ApplySettings(HWND__ *,int)

- ea: `0x180010c48`
- end: `0x180010f7c`
- name: `?Date_ApplySettings@@YAHPEAUHWND__@@H@Z`
- size: `820`
- prototype: `__int64 __fastcall(HWND, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010790`

## callees

- `0x180010c48`
- `0x180011040`
- `0x180011214`
- `0x1800112a0`
- `0x18001151c`
- `0x1800119d8`
- `0x1800120f0`
- `0x1800121d0`
- `0x1800245bc`
- `0x180026dc4`
- `0x180027c28`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180010ccf`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180010d3c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180010e5c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180010ccf`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180010d3c`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoEx` at `0x180010e5c`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoEx` at `0x180010db2`
- `api-ms-win-core-localization-l1-2-0!GetCalendarInfoEx` at `0x180010db2`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x180010ddd`
- `api-ms-win-core-localization-l1-2-0!SetLocaleInfoW` at `0x180010ddd`
- `KERNEL32!NlsUpdateLocale` at `0x180010ef6`
- `KERNEL32!NlsUpdateLocale` at `0x180010ef6`
- `USER32!SendNotifyMessageW` at `0x180010f0f`
- `USER32!SendNotifyMessageW` at `0x180010f0f`
- `USER32!GetDlgItem` at `0x180010c8d`
- `USER32!GetDlgItem` at `0x180010df1`
- `USER32!GetDlgItem` at `0x180010e15`
- `USER32!GetDlgItem` at `0x180010c8d`
- `USER32!GetDlgItem` at `0x180010df1`
- `USER32!GetDlgItem` at `0x180010e15`
- `USER32!GetWindowLongPtrW` at `0x180010c78`
- `USER32!GetWindowLongPtrW` at `0x180010c78`
- `USER32!GetParent` at `0x180010eb0`
- `USER32!GetParent` at `0x180010eb0`
- `USER32!SendMessageW` at `0x180010e2c`
- `USER32!SendMessageW` at `0x180010e82`
- `USER32!SendMessageW` at `0x180010ec4`
- `USER32!SendMessageW` at `0x180010e2c`
- `USER32!SendMessageW` at `0x180010e82`
- `USER32!SendMessageW` at `0x180010ec4`
- `USER32!IsWindowEnabled` at `0x180010e9c`
- `USER32!IsWindowEnabled` at `0x180010e9c`

## pseudocode

```c
__int64 __fastcall Date_ApplySettings(HWND a1)
{
  LONG_PTR WindowLongPtrW; // r14
  __int64 v3; // rbp
  HWND DlgItem; // r15
  CALID v5; // esi
  HWND v6; // rax
  HWND v7; // rsi
  int v8; // eax
  HWND Parent; // rax
  unsigned int v11; // eax
  bool v12; // zf
  const unsigned __int16 *lpValue; // [rsp+30h] [rbp-1E8h]
  WCHAR LCData[128]; // [rsp+40h] [rbp-1D8h] BYREF
  WCHAR CalData[88]; // [rsp+140h] [rbp-D8h] BYREF

  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  v3 = *(_QWORD *)(WindowLongPtrW + 48);
  DlgItem = GetDlgItem(a1, 1103);
  if ( v3 )
  {
    if ( (unsigned int)Intl_ApplyPendingLocaleChange()
      && !GetLocaleInfoEx(
            *(LPCWSTR *)(*((_QWORD *)g_localeInfo + RegUserLocaleIndex) + 8LL),
            0x20001009u,
            &g_dwCalendarType,
            2) )
    {
      return 0;
    }
    v5 = 0;
    if ( (v3 & 0x10) != 0 )
    {
      if ( !(unsigned int)Set_Locale_Values(a1, 0x1009u, 1101, 0, 1, 1, lpValue) )
        return 0;
      if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + RegUserLocaleIndex) + 8LL), 0x1009u, LCData, 128) )
      {
        *(_DWORD *)&g_dwCalendarType = Intl_StrToLong(LCData);
        v5 = *(_DWORD *)&g_dwCalendarType;
        Date_InitializeHijriDateComboBox(a1);
        Date_EnableHijriComboBox(a1, v5 == 6);
        if ( GetCalendarInfoEx(
               *(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL),
               v5,
               0,
               0x2Fu,
               CalData,
               85,
               0) )
        {
          SetLocaleInfoW(*(_DWORD *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 16LL), 0x1006u, CalData);
        }
      }
    }
    if ( (v3 & 0x20) != 0 )
    {
      v6 = GetDlgItem(a1, 1105);
      Date_SetHijriDate(v6);
    }
    if ( (v3 & 0x40) == 0 )
    {
LABEL_20:
      Parent = GetParent(a1);
      SendMessageW(Parent, 0x46Du, (WPARAM)a1, 0);
      v11 = UserLocaleIndex;
      v12 = UserLocaleIndex == g_savedLocaleIndex;
      *(_QWORD *)(WindowLongPtrW + 48) = 1;
      if ( v12 )
      {
        NlsUpdateLocale(*(_QWORD *)(*((_QWORD *)g_localeInfo + v11) + 8LL), 4);
        SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"intl");
      }
      Date_EnumerateDates(a1, 5u);
      Date_EnumerateDates(a1, 6u);
      Date_EnumerateDays(a1);
      Date_DisplaySample(a1);
      Date_InitializeHijriDateComboBox(a1);
      g_dwCustLastChange |= 8u;
      return 1;
    }
    if ( v5 )
    {
LABEL_17:
      if ( !Date_SetTwoDigitYearMax(a1, v5) && IsWindowEnabled(DlgItem) )
        return 0;
      goto LABEL_20;
    }
    v7 = GetDlgItem(a1, 1101);
    v8 = SendMessageW(v7, 0x147u, 0, 0);
    if ( v8 != -1 )
    {
      v5 = SendMessageW(v7, 0x150u, v8, 0);
      goto LABEL_17;
    }
    if ( GetLocaleInfoEx(*(LPCWSTR *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), 0x1009u, LCData, 128) )
    {
      v5 = Intl_StrToLong(LCData);
      goto LABEL_17;
    }
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180010c48  mov     [rsp+arg_8], rbx
0x180010c4d  mov     [rsp+arg_10], rbp
0x180010c52  push    rsi
0x180010c53  push    r14
0x180010c55  push    r15
0x180010c57  sub     rsp, 200h
0x180010c5e  mov     rax, cs:__security_cookie
0x180010c65  xor     rax, rsp
0x180010c68  mov     [rsp+218h+var_28], rax
0x180010c70  mov     edx, 10h; nIndex
0x180010c75  mov     rbx, rcx
0x180010c78  call    cs:__imp_GetWindowLongPtrW
0x180010c7e  mov     edx, 44Fh; nIDDlgItem
0x180010c83  mov     rcx, rbx; hDlg
0x180010c86  mov     r14, rax
0x180010c89  mov     rbp, [rax+30h]
0x180010c8d  call    cs:__imp_GetDlgItem
0x180010c93  mov     r15, rax
0x180010c96  test    rbp, rbp
0x180010c99  jz      loc_180010F4E
0x180010c9f  call    ?Intl_ApplyPendingLocaleChange@@YAHXZ; Intl_ApplyPendingLocaleChange(void)
0x180010ca4  test    eax, eax
0x180010ca6  jz      short loc_180010CDD
0x180010ca8  mov     ecx, cs:?RegUserLocaleIndex@@3KA; ulong RegUserLocaleIndex
0x180010cae  lea     r8, ?g_dwCalendarType@@3KA; lpLCData
0x180010cb5  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180010cbc  mov     r9d, 2; cchData
0x180010cc2  mov     edx, 20001009h; LCType
0x180010cc7  mov     rcx, [rax+rcx*8]
0x180010ccb  mov     rcx, [rcx+8]; lpLocaleName
0x180010ccf  call    cs:__imp_GetLocaleInfoEx
0x180010cd5  test    eax, eax
0x180010cd7  jz      loc_180010EA6
0x180010cdd  xor     esi, esi
0x180010cdf  test    bpl, 10h
0x180010ce3  jz      loc_180010DE3
0x180010ce9  mov     [rsp+218h+cchData], 1; int
0x180010cf1  xor     r9d, r9d; unsigned __int16 *
0x180010cf4  mov     edx, 1009h; unsigned int
0x180010cf9  mov     dword ptr [rsp+218h+lpCalData], 1; int
0x180010d01  mov     r8d, 44Dh; nIDDlgItem
0x180010d07  mov     rcx, rbx; hDlg
0x180010d0a  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x180010d0f  test    eax, eax
0x180010d11  jz      loc_180010EA6
0x180010d17  mov     ecx, cs:?RegUserLocaleIndex@@3KA; ulong RegUserLocaleIndex
0x180010d1d  lea     r8, [rsp+218h+LCData]; lpLCData
0x180010d22  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180010d29  mov     r9d, 80h; cchData
0x180010d2f  mov     edx, 1009h; LCType
0x180010d34  mov     rcx, [rax+rcx*8]
0x180010d38  mov     rcx, [rcx+8]; lpLocaleName
0x180010d3c  call    cs:__imp_GetLocaleInfoEx
0x180010d42  test    eax, eax
0x180010d44  jz      loc_180010DE3
0x180010d4a  lea     rcx, [rsp+218h+LCData]; unsigned __int16 *
0x180010d4f  call    ?Intl_StrToLong@@YAJPEBG@Z; Intl_StrToLong(ushort const *)
0x180010d54  mov     rcx, rbx; hDlg
0x180010d57  mov     cs:?g_dwCalendarType@@3KA, eax; ulong g_dwCalendarType
0x180010d5d  mov     esi, eax
0x180010d5f  call    ?Date_InitializeHijriDateComboBox@@YAXPEAUHWND__@@@Z; Date_InitializeHijriDateComboBox(HWND__ *)
0x180010d64  xor     edx, edx
0x180010d66  mov     rcx, rbx; hDlg
0x180010d69  cmp     esi, 6
0x180010d6c  setz    dl; int
0x180010d6f  call    ?Date_EnableHijriComboBox@@YAXPEAUHWND__@@H@Z; Date_EnableHijriComboBox(HWND__ *,int)
0x180010d74  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180010d7b  mov     r9d, 2Fh ; '/'; CalType
0x180010d81  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180010d87  xor     r8d, r8d; lpReserved
0x180010d8a  mov     [rsp+218h+lpValue], 0; lpValue
0x180010d93  mov     edx, esi; Calendar
0x180010d95  mov     [rsp+218h+cchData], 55h ; 'U'; cchData
0x180010d9d  mov     rcx, [rax+rcx*8]
0x180010da1  lea     rax, [rsp+218h+CalData]
0x180010da9  mov     [rsp+218h+lpCalData], rax; lpCalData
0x180010dae  mov     rcx, [rcx+8]; lpLocaleName
0x180010db2  call    cs:__imp_GetCalendarInfoEx
0x180010db8  test    eax, eax
0x180010dba  jz      short loc_180010DE3
0x180010dbc  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180010dc2  lea     r8, [rsp+218h+CalData]; lpLCData
0x180010dca  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180010dd1  mov     edx, 1006h; LCType
0x180010dd6  mov     rcx, [rax+rcx*8]
0x180010dda  mov     ecx, [rcx+10h]; Locale
0x180010ddd  call    cs:__imp_SetLocaleInfoW
0x180010de3  test    bpl, 20h
0x180010de7  jz      short loc_180010DFF
0x180010de9  mov     edx, 451h; nIDDlgItem
0x180010dee  mov     rcx, rbx; hDlg
0x180010df1  call    cs:__imp_GetDlgItem
0x180010df7  mov     rcx, rax; hWnd
0x180010dfa  call    ?Date_SetHijriDate@@YAXPEAUHWND__@@@Z; Date_SetHijriDate(HWND__ *)
0x180010dff  test    bpl, 40h
0x180010e03  jz      loc_180010EAD
0x180010e09  test    esi, esi
0x180010e0b  jnz     short loc_180010E8B
0x180010e0d  mov     edx, 44Dh; nIDDlgItem
0x180010e12  mov     rcx, rbx; hDlg
0x180010e15  call    cs:__imp_GetDlgItem
0x180010e1b  xor     r9d, r9d; lParam
0x180010e1e  xor     r8d, r8d; wParam
0x180010e21  mov     rcx, rax; hWnd
0x180010e24  mov     edx, 147h; Msg
0x180010e29  mov     rsi, rax
0x180010e2c  call    cs:__imp_SendMessageW
0x180010e32  cmp     eax, 0FFFFFFFFh
0x180010e35  jnz     short loc_180010E74
0x180010e37  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180010e3d  lea     r8, [rsp+218h+LCData]; lpLCData
0x180010e42  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180010e49  mov     r9d, 80h; cchData
0x180010e4f  mov     edx, 1009h; LCType
0x180010e54  mov     rcx, [rax+rcx*8]
0x180010e58  mov     rcx, [rcx+8]; lpLocaleName
0x180010e5c  call    cs:__imp_GetLocaleInfoEx
0x180010e62  test    eax, eax
0x180010e64  jz      short loc_180010EA6
0x180010e66  lea     rcx, [rsp+218h+LCData]; unsigned __int16 *
0x180010e6b  call    ?Intl_StrToLong@@YAJPEBG@Z; Intl_StrToLong(ushort const *)
0x180010e70  mov     esi, eax
0x180010e72  jmp     short loc_180010E8B
0x180010e74  movsxd  r8, eax; wParam
0x180010e77  xor     r9d, r9d; lParam
0x180010e7a  mov     edx, 150h; Msg
0x180010e7f  mov     rcx, rsi; hWnd
0x180010e82  call    cs:__imp_SendMessageW
0x180010e88  mov     rsi, rax
0x180010e8b  mov     edx, esi; unsigned int
0x180010e8d  mov     rcx, rbx; HWND
0x180010e90  call    ?Date_SetTwoDigitYearMax@@YAHPEAUHWND__@@K@Z; Date_SetTwoDigitYearMax(HWND__ *,ulong)
0x180010e95  test    eax, eax
0x180010e97  jnz     short loc_180010EAD
0x180010e99  mov     rcx, r15; hWnd
0x180010e9c  call    cs:__imp_IsWindowEnabled
0x180010ea2  test    eax, eax
0x180010ea4  jz      short loc_180010EAD
0x180010ea6  xor     eax, eax
0x180010ea8  jmp     loc_180010F53
0x180010ead  mov     rcx, rbx; hWnd
0x180010eb0  call    cs:__imp_GetParent
0x180010eb6  xor     r9d, r9d; lParam
0x180010eb9  mov     r8, rbx; wParam
0x180010ebc  mov     rcx, rax; hWnd
0x180010ebf  mov     edx, 46Dh; Msg
0x180010ec4  call    cs:__imp_SendMessageW
0x180010eca  mov     eax, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180010ed0  cmp     eax, cs:?g_savedLocaleIndex@@3KA; ulong g_savedLocaleIndex
0x180010ed6  mov     qword ptr [r14+30h], 1
0x180010ede  jnz     short loc_180010F15
0x180010ee0  mov     ecx, eax
0x180010ee2  mov     edx, 4
0x180010ee7  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180010eee  mov     rcx, [rax+rcx*8]
0x180010ef2  mov     rcx, [rcx+8]
0x180010ef6  call    cs:__imp_NlsUpdateLocale
0x180010efc  xor     r8d, r8d; wParam
0x180010eff  lea     r9, lParam; "intl"
0x180010f06  mov     ecx, 0FFFFh; hWnd
0x180010f0b  lea     edx, [r8+1Ah]; Msg
0x180010f0f  call    cs:__imp_SendNotifyMessageW
0x180010f15  mov     edx, 5; unsigned int
0x180010f1a  mov     rcx, rbx; hDlg
0x180010f1d  call    ?Date_EnumerateDates@@YAXPEAUHWND__@@K@Z; Date_EnumerateDates(HWND__ *,ulong)
0x180010f22  mov     edx, 6; unsigned int
0x180010f27  mov     rcx, rbx; hDlg
0x180010f2a  call    ?Date_EnumerateDates@@YAXPEAUHWND__@@K@Z; Date_EnumerateDates(HWND__ *,ulong)
0x180010f2f  mov     rcx, rbx; HWND
0x180010f32  call    ?Date_EnumerateDays@@YAXPEAUHWND__@@@Z; Date_EnumerateDays(HWND__ *)
0x180010f37  mov     rcx, rbx; hDlg
0x180010f3a  call    ?Date_DisplaySample@@YAXPEAUHWND__@@@Z; Date_DisplaySample(HWND__ *)
0x180010f3f  mov     rcx, rbx; hDlg
0x180010f42  call    ?Date_InitializeHijriDateComboBox@@YAXPEAUHWND__@@@Z; Date_InitializeHijriDateComboBox(HWND__ *)
0x180010f47  or      cs:?g_dwCustLastChange@@3KA, 8; ulong g_dwCustLastChange
0x180010f4e  mov     eax, 1
0x180010f53  mov     rcx, [rsp+218h+var_28]
0x180010f5b  xor     rcx, rsp; StackCookie
0x180010f5e  call    __security_check_cookie
0x180010f63  lea     r11, [rsp+218h+var_18]
0x180010f6b  mov     rbx, [r11+28h]
0x180010f6f  mov     rbp, [r11+30h]
0x180010f73  mov     rsp, r11
0x180010f76  pop     r15
0x180010f78  pop     r14
0x180010f7a  pop     rsi
0x180010f7b  retn
```
