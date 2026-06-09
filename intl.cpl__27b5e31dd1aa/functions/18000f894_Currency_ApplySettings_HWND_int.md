# Currency_ApplySettings(HWND__ *,int)

- ea: `0x18000f894`
- end: `0x18000fad1`
- name: `?Currency_ApplySettings@@YAHPEAUHWND__@@H@Z`
- size: `573`
- prototype: `__int64 __fastcall(HWND, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18000f5f0`

## callees

- `0x18000f894`
- `0x18000fad8`
- `0x180010408`
- `0x1800245bc`
- `0x180027c28`

## import_xrefs

- `KERNEL32!NlsUpdateLocale` at `0x18000fa78`
- `KERNEL32!NlsUpdateLocale` at `0x18000fa78`
- `USER32!SendNotifyMessageW` at `0x18000fa9f`
- `USER32!SendNotifyMessageW` at `0x18000fa9f`
- `USER32!GetWindowLongPtrW` at `0x18000f8ab`
- `USER32!GetWindowLongPtrW` at `0x18000f8ab`
- `USER32!GetParent` at `0x18000fa3c`
- `USER32!GetParent` at `0x18000fa3c`
- `USER32!SendMessageW` at `0x18000fa50`
- `USER32!SendMessageW` at `0x18000fa50`

## pseudocode

```c
__int64 __fastcall Currency_ApplySettings(HWND a1)
{
  LONG_PTR WindowLongPtrW; // rbp
  __int64 v3; // rdi
  HWND Parent; // rax
  __int64 v6; // rcx
  _QWORD *v7; // rax
  const unsigned __int16 *v8; // [rsp+30h] [rbp-18h]

  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  v3 = *(_QWORD *)(WindowLongPtrW + 48);
  if ( v3 )
  {
    Intl_ApplyPendingLocaleChange();
    if ( (v3 & 2) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x14u, 1071, L"sCurrency", 0, 0, v8)
      || (v3 & 4) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x1Bu, 1077, L"iCurrency", 1, 0, v8)
      || (v3 & 8) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x1Cu, 1078, L"iNegCurr", 1, 0, v8)
      || (v3 & 0x10) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x16u, 1070, 0, 0, 0, v8)
      || (v3 & 0x20) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x19u, 1072, L"iCurrDigits", 1, 0, v8)
      || (v3 & 0x40) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x17u, 1073, 0, 0, 0, v8)
      || (v3 & 0x80u) != 0LL && !(unsigned int)Set_Locale_Values(a1, 0x18u, 1074, 0, 1, 0, v8) )
    {
      return 0;
    }
    Parent = GetParent(a1);
    SendMessageW(Parent, 0x46Du, (WPARAM)a1, 0);
    v6 = UserLocaleIndex;
    v7 = g_localeInfo;
    *(_QWORD *)(WindowLongPtrW + 48) = 1;
    NlsUpdateLocale(*(_QWORD *)(v7[v6] + 8LL), 4);
    if ( UserLocaleIndex == g_savedLocaleIndex )
      SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"intl");
    Currency_ClearValues(a1);
    Currency_SetValues(a1);
    g_dwCustLastChange |= 2u;
  }
  return 1;
}

```

## disassembly

```asm
0x18000f894  mov     [rsp+arg_0], rbx
0x18000f899  mov     [rsp+arg_8], rbp
0x18000f89e  push    rdi
0x18000f89f  sub     rsp, 40h
0x18000f8a3  mov     edx, 10h; nIndex
0x18000f8a8  mov     rbx, rcx
0x18000f8ab  call    cs:__imp_GetWindowLongPtrW
0x18000f8b1  mov     rbp, rax
0x18000f8b4  mov     rdi, [rax+30h]
0x18000f8b8  test    rdi, rdi
0x18000f8bb  jz      loc_18000FABC
0x18000f8c1  call    ?Intl_ApplyPendingLocaleChange@@YAHXZ; Intl_ApplyPendingLocaleChange(void)
0x18000f8c6  test    dil, 2
0x18000f8ca  jz      short loc_18000F8FE
0x18000f8cc  mov     [rsp+48h+var_20], 0; int
0x18000f8d4  lea     r9, aScurrency; "sCurrency"
0x18000f8db  mov     edx, 14h; unsigned int
0x18000f8e0  mov     [rsp+48h+var_28], 0; int
0x18000f8e8  mov     r8d, 42Fh; nIDDlgItem
0x18000f8ee  mov     rcx, rbx; hDlg
0x18000f8f1  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18000f8f6  test    eax, eax
0x18000f8f8  jz      loc_18000FA32
0x18000f8fe  test    dil, 4
0x18000f902  jz      short loc_18000F936
0x18000f904  mov     [rsp+48h+var_20], 0; int
0x18000f90c  lea     r9, aIcurrency; "iCurrency"
0x18000f913  mov     edx, 1Bh; unsigned int
0x18000f918  mov     [rsp+48h+var_28], 1; int
0x18000f920  mov     r8d, 435h; nIDDlgItem
0x18000f926  mov     rcx, rbx; hDlg
0x18000f929  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18000f92e  test    eax, eax
0x18000f930  jz      loc_18000FA32
0x18000f936  test    dil, 8
0x18000f93a  jz      short loc_18000F96E
0x18000f93c  mov     [rsp+48h+var_20], 0; int
0x18000f944  lea     r9, aInegcurr; "iNegCurr"
0x18000f94b  mov     edx, 1Ch; unsigned int
0x18000f950  mov     [rsp+48h+var_28], 1; int
0x18000f958  mov     r8d, 436h; nIDDlgItem
0x18000f95e  mov     rcx, rbx; hDlg
0x18000f961  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18000f966  test    eax, eax
0x18000f968  jz      loc_18000FA32
0x18000f96e  test    dil, 10h
0x18000f972  jz      short loc_18000F9A1
0x18000f974  xor     r9d, r9d; unsigned __int16 *
0x18000f977  mov     [rsp+48h+var_20], 0; int
0x18000f97f  mov     r8d, 42Eh; nIDDlgItem
0x18000f985  mov     [rsp+48h+var_28], 0; int
0x18000f98d  mov     rcx, rbx; hDlg
0x18000f990  lea     edx, [r9+16h]; unsigned int
0x18000f994  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18000f999  test    eax, eax
0x18000f99b  jz      loc_18000FA32
0x18000f9a1  test    dil, 20h
0x18000f9a5  jz      short loc_18000F9D5
0x18000f9a7  mov     [rsp+48h+var_20], 0; int
0x18000f9af  lea     r9, aIcurrdigits; "iCurrDigits"
0x18000f9b6  mov     edx, 19h; unsigned int
0x18000f9bb  mov     [rsp+48h+var_28], 1; int
0x18000f9c3  mov     r8d, 430h; nIDDlgItem
0x18000f9c9  mov     rcx, rbx; hDlg
0x18000f9cc  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18000f9d1  test    eax, eax
0x18000f9d3  jz      short loc_18000FA32
0x18000f9d5  test    dil, 40h
0x18000f9d9  jz      short loc_18000FA04
0x18000f9db  xor     r9d, r9d; unsigned __int16 *
0x18000f9de  mov     [rsp+48h+var_20], 0; int
0x18000f9e6  mov     r8d, 431h; nIDDlgItem
0x18000f9ec  mov     [rsp+48h+var_28], 0; int
0x18000f9f4  mov     rcx, rbx; hDlg
0x18000f9f7  lea     edx, [r9+17h]; unsigned int
0x18000f9fb  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18000fa00  test    eax, eax
0x18000fa02  jz      short loc_18000FA32
0x18000fa04  test    dil, dil
0x18000fa07  jns     short loc_18000FA39
0x18000fa09  xor     r9d, r9d; unsigned __int16 *
0x18000fa0c  mov     [rsp+48h+var_20], 0; int
0x18000fa14  mov     r8d, 432h; nIDDlgItem
0x18000fa1a  mov     [rsp+48h+var_28], 1; int
0x18000fa22  mov     rcx, rbx; hDlg
0x18000fa25  lea     edx, [r9+18h]; unsigned int
0x18000fa29  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18000fa2e  test    eax, eax
0x18000fa30  jnz     short loc_18000FA39
0x18000fa32  xor     eax, eax
0x18000fa34  jmp     loc_18000FAC1
0x18000fa39  mov     rcx, rbx; hWnd
0x18000fa3c  call    cs:__imp_GetParent
0x18000fa42  xor     r9d, r9d; lParam
0x18000fa45  mov     r8, rbx; wParam
0x18000fa48  mov     rcx, rax; hWnd
0x18000fa4b  mov     edx, 46Dh; Msg
0x18000fa50  call    cs:__imp_SendMessageW
0x18000fa56  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18000fa5c  mov     edx, 4
0x18000fa61  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18000fa68  mov     qword ptr [rbp+30h], 1
0x18000fa70  mov     rcx, [rax+rcx*8]
0x18000fa74  mov     rcx, [rcx+8]
0x18000fa78  call    cs:__imp_NlsUpdateLocale
0x18000fa7e  mov     eax, cs:?g_savedLocaleIndex@@3KA; ulong g_savedLocaleIndex
0x18000fa84  cmp     cs:?UserLocaleIndex@@3KA, eax; ulong UserLocaleIndex
0x18000fa8a  jnz     short loc_18000FAA5
0x18000fa8c  xor     r8d, r8d; wParam
0x18000fa8f  lea     r9, lParam; "intl"
0x18000fa96  mov     ecx, 0FFFFh; hWnd
0x18000fa9b  lea     edx, [r8+1Ah]; Msg
0x18000fa9f  call    cs:__imp_SendNotifyMessageW
0x18000faa5  mov     rcx, rbx; hDlg
0x18000faa8  call    ?Currency_ClearValues@@YAXPEAUHWND__@@@Z; Currency_ClearValues(HWND__ *)
0x18000faad  mov     rcx, rbx; HWND
0x18000fab0  call    ?Currency_SetValues@@YAXPEAUHWND__@@@Z; Currency_SetValues(HWND__ *)
0x18000fab5  or      cs:?g_dwCustLastChange@@3KA, 2; ulong g_dwCustLastChange
0x18000fabc  mov     eax, 1
0x18000fac1  mov     rbx, [rsp+48h+arg_0]
0x18000fac6  mov     rbp, [rsp+48h+arg_8]
0x18000facb  add     rsp, 40h
0x18000facf  pop     rdi
0x18000fad0  retn
```
