# Number_ApplySettings(HWND__ *,int)

- ea: `0x18001a444`
- end: `0x18001a710`
- name: `?Number_ApplySettings@@YAHPEAUHWND__@@H@Z`
- size: `716`
- prototype: `__int64 __fastcall(HWND, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18001a110`

## callees

- `0x18001a444`
- `0x18001a718`
- `0x18001b3f0`
- `0x1800245bc`
- `0x180027c28`

## import_xrefs

- `KERNEL32!NlsUpdateLocale` at `0x18001a69f`
- `KERNEL32!NlsUpdateLocale` at `0x18001a69f`
- `USER32!SendNotifyMessageW` at `0x18001a6c6`
- `USER32!SendNotifyMessageW` at `0x18001a6c6`
- `USER32!GetWindowLongPtrW` at `0x18001a457`
- `USER32!GetWindowLongPtrW` at `0x18001a457`
- `USER32!GetParent` at `0x18001a6cf`
- `USER32!GetParent` at `0x18001a6cf`
- `USER32!SendMessageW` at `0x18001a6e3`
- `USER32!SendMessageW` at `0x18001a6e3`

## pseudocode

```c
__int64 __fastcall Number_ApplySettings(HWND a1)
{
  LONG_PTR WindowLongPtrW; // rbp
  __int64 v3; // rbx
  HWND Parent; // rax
  const unsigned __int16 *v6; // [rsp+30h] [rbp-38h]

  WindowLongPtrW = GetWindowLongPtrW(a1, 16);
  v3 = *(_QWORD *)(WindowLongPtrW + 48);
  if ( !v3 )
    return 1;
  Intl_ApplyPendingLocaleChange();
  if ( (v3 & 2) != 0 && !(unsigned int)Set_Locale_Values(a1, 0xEu, 1070, L"sDecimal", 0, 0, v6)
    || (v3 & 4) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x51u, 1076, 0, 0, 0, v6)
    || (v3 & 8) != 0 && !(unsigned int)Set_Locale_Values(a1, 0xCu, 1079, L"sList", 0, 0, v6)
    || (v3 & 0x10) != 0 && !(unsigned int)Set_Locale_Values(a1, 0xFu, 1073, L"sThousand", 0, 0, v6)
    || (v3 & 0x20) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x11u, 1072, L"iDigits", 1, 0, v6)
    || (v3 & 0x40) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x10u, 1074, 0, 1, 0, v6)
    || (v3 & 0x80u) != 0LL && !(unsigned int)Set_Locale_Values(a1, 0x12u, 1080, L"iLzero", 1, 0, v6)
    || (v3 & 0x100) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x1010u, 1078, 0, 1, 0, v6)
    || (v3 & 0x200) != 0 && !(unsigned int)Set_Locale_Values(a1, 0xDu, 1081, L"iMeasure", 1, 0, v6)
    || (v3 & 0x400) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x13u, 1083, L"sNativeDigits", 0, 0, v6)
    || (v3 & 0x800) != 0 && !(unsigned int)Set_Locale_Values(a1, 0x1014u, 1085, L"NumShape", 1, 0, v6) )
  {
    return 0;
  }
  NlsUpdateLocale(*(_QWORD *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 8LL), 4);
  if ( UserLocaleIndex == g_savedLocaleIndex )
    SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"intl");
  Parent = GetParent(a1);
  SendMessageW(Parent, 0x46Du, (WPARAM)a1, 0);
  *(_QWORD *)(WindowLongPtrW + 48) = 1;
  Number_ClearValues(a1);
  Number_SetValues(a1);
  g_dwCustLastChange |= 1u;
  return 1;
}

```

## disassembly

```asm
0x18001a444  push    rbx
0x18001a446  push    rbp
0x18001a447  push    rsi
0x18001a448  push    rdi
0x18001a449  push    r14
0x18001a44b  sub     rsp, 40h
0x18001a44f  mov     edx, 10h; nIndex
0x18001a454  mov     rdi, rcx
0x18001a457  call    cs:__imp_GetWindowLongPtrW
0x18001a45d  xor     r14d, r14d
0x18001a460  mov     rbp, rax
0x18001a463  mov     rbx, [rax+30h]
0x18001a467  test    rbx, rbx
0x18001a46a  jnz     short loc_18001A474
0x18001a46c  lea     eax, [rbx+1]
0x18001a46f  jmp     loc_18001A705
0x18001a474  call    ?Intl_ApplyPendingLocaleChange@@YAHXZ; Intl_ApplyPendingLocaleChange(void)
0x18001a479  test    bl, 2
0x18001a47c  jz      short loc_18001A4AA
0x18001a47e  mov     [rsp+68h+var_40], r14d; int
0x18001a483  lea     r9, aSdecimal; "sDecimal"
0x18001a48a  mov     edx, 0Eh; unsigned int
0x18001a48f  mov     [rsp+68h+var_48], r14d; int
0x18001a494  mov     r8d, 42Eh; nIDDlgItem
0x18001a49a  mov     rcx, rdi; hDlg
0x18001a49d  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a4a2  test    eax, eax
0x18001a4a4  jz      loc_18001A67E
0x18001a4aa  test    bl, 4
0x18001a4ad  jz      short loc_18001A4D6
0x18001a4af  xor     r9d, r9d; unsigned __int16 *
0x18001a4b2  mov     [rsp+68h+var_40], r14d; int
0x18001a4b7  mov     r8d, 434h; nIDDlgItem
0x18001a4bd  mov     [rsp+68h+var_48], r14d; int
0x18001a4c2  mov     rcx, rdi; hDlg
0x18001a4c5  lea     edx, [r9+51h]; unsigned int
0x18001a4c9  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a4ce  test    eax, eax
0x18001a4d0  jz      loc_18001A67E
0x18001a4d6  test    bl, 8
0x18001a4d9  jz      short loc_18001A507
0x18001a4db  mov     [rsp+68h+var_40], r14d; int
0x18001a4e0  lea     r9, aSlist; "sList"
0x18001a4e7  mov     edx, 0Ch; unsigned int
0x18001a4ec  mov     [rsp+68h+var_48], r14d; int
0x18001a4f1  mov     r8d, 437h; nIDDlgItem
0x18001a4f7  mov     rcx, rdi; hDlg
0x18001a4fa  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a4ff  test    eax, eax
0x18001a501  jz      loc_18001A67E
0x18001a507  test    bl, 10h
0x18001a50a  jz      short loc_18001A538
0x18001a50c  mov     [rsp+68h+var_40], r14d; int
0x18001a511  lea     r9, aSthousand; "sThousand"
0x18001a518  mov     edx, 0Fh; unsigned int
0x18001a51d  mov     [rsp+68h+var_48], r14d; int
0x18001a522  mov     r8d, 431h; nIDDlgItem
0x18001a528  mov     rcx, rdi; hDlg
0x18001a52b  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a530  test    eax, eax
0x18001a532  jz      loc_18001A67E
0x18001a538  mov     esi, 1
0x18001a53d  test    bl, 20h
0x18001a540  jz      short loc_18001A56B
0x18001a542  mov     [rsp+68h+var_40], r14d; int
0x18001a547  lea     r9, aIdigits; "iDigits"
0x18001a54e  lea     edx, [rsi+10h]; unsigned int
0x18001a551  mov     [rsp+68h+var_48], esi; int
0x18001a555  mov     r8d, 430h; nIDDlgItem
0x18001a55b  mov     rcx, rdi; hDlg
0x18001a55e  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a563  test    eax, eax
0x18001a565  jz      loc_18001A67E
0x18001a56b  test    bl, 40h
0x18001a56e  jz      short loc_18001A596
0x18001a570  xor     r9d, r9d; unsigned __int16 *
0x18001a573  mov     [rsp+68h+var_40], r14d; int
0x18001a578  mov     r8d, 432h; nIDDlgItem
0x18001a57e  mov     [rsp+68h+var_48], esi; int
0x18001a582  mov     rcx, rdi; hDlg
0x18001a585  lea     edx, [r9+10h]; unsigned int
0x18001a589  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a58e  test    eax, eax
0x18001a590  jz      loc_18001A67E
0x18001a596  test    bl, bl
0x18001a598  jns     short loc_18001A5C5
0x18001a59a  mov     [rsp+68h+var_40], r14d; int
0x18001a59f  lea     r9, aIlzero; "iLzero"
0x18001a5a6  mov     edx, 12h; unsigned int
0x18001a5ab  mov     [rsp+68h+var_48], esi; int
0x18001a5af  mov     r8d, 438h; nIDDlgItem
0x18001a5b5  mov     rcx, rdi; hDlg
0x18001a5b8  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a5bd  test    eax, eax
0x18001a5bf  jz      loc_18001A67E
0x18001a5c5  bt      rbx, 8
0x18001a5ca  jnb     short loc_18001A5F3
0x18001a5cc  mov     [rsp+68h+var_40], r14d; int
0x18001a5d1  xor     r9d, r9d; unsigned __int16 *
0x18001a5d4  mov     edx, 1010h; unsigned int
0x18001a5d9  mov     [rsp+68h+var_48], esi; int
0x18001a5dd  mov     r8d, 436h; nIDDlgItem
0x18001a5e3  mov     rcx, rdi; hDlg
0x18001a5e6  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a5eb  test    eax, eax
0x18001a5ed  jz      loc_18001A67E
0x18001a5f3  bt      rbx, 9
0x18001a5f8  jnb     short loc_18001A621
0x18001a5fa  mov     [rsp+68h+var_40], r14d; int
0x18001a5ff  lea     r9, aImeasure; "iMeasure"
0x18001a606  mov     edx, 0Dh; unsigned int
0x18001a60b  mov     [rsp+68h+var_48], esi; int
0x18001a60f  mov     r8d, 439h; nIDDlgItem
0x18001a615  mov     rcx, rdi; hDlg
0x18001a618  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a61d  test    eax, eax
0x18001a61f  jz      short loc_18001A67E
0x18001a621  bt      rbx, 0Ah
0x18001a626  jnb     short loc_18001A650
0x18001a628  mov     [rsp+68h+var_40], r14d; int
0x18001a62d  lea     r9, aSnativedigits; "sNativeDigits"
0x18001a634  mov     edx, 13h; unsigned int
0x18001a639  mov     [rsp+68h+var_48], r14d; int
0x18001a63e  mov     r8d, 43Bh; nIDDlgItem
0x18001a644  mov     rcx, rdi; hDlg
0x18001a647  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a64c  test    eax, eax
0x18001a64e  jz      short loc_18001A67E
0x18001a650  bt      rbx, 0Bh
0x18001a655  jnb     short loc_18001A685
0x18001a657  mov     [rsp+68h+var_40], r14d; int
0x18001a65c  lea     r9, aNumshape; "NumShape"
0x18001a663  mov     edx, 1014h; unsigned int
0x18001a668  mov     [rsp+68h+var_48], esi; int
0x18001a66c  mov     r8d, 43Dh; nIDDlgItem
0x18001a672  mov     rcx, rdi; hDlg
0x18001a675  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18001a67a  test    eax, eax
0x18001a67c  jnz     short loc_18001A685
0x18001a67e  xor     eax, eax
0x18001a680  jmp     loc_18001A705
0x18001a685  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x18001a68b  mov     edx, 4
0x18001a690  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x18001a697  mov     rcx, [rax+rcx*8]
0x18001a69b  mov     rcx, [rcx+8]
0x18001a69f  call    cs:__imp_NlsUpdateLocale
0x18001a6a5  mov     eax, cs:?g_savedLocaleIndex@@3KA; ulong g_savedLocaleIndex
0x18001a6ab  cmp     cs:?UserLocaleIndex@@3KA, eax; ulong UserLocaleIndex
0x18001a6b1  jnz     short loc_18001A6CC
0x18001a6b3  xor     r8d, r8d; wParam
0x18001a6b6  lea     r9, lParam; "intl"
0x18001a6bd  mov     ecx, 0FFFFh; hWnd
0x18001a6c2  lea     edx, [r8+1Ah]; Msg
0x18001a6c6  call    cs:__imp_SendNotifyMessageW
0x18001a6cc  mov     rcx, rdi; hWnd
0x18001a6cf  call    cs:__imp_GetParent
0x18001a6d5  xor     r9d, r9d; lParam
0x18001a6d8  mov     r8, rdi; wParam
0x18001a6db  mov     rcx, rax; hWnd
0x18001a6de  mov     edx, 46Dh; Msg
0x18001a6e3  call    cs:__imp_SendMessageW
0x18001a6e9  mov     rcx, rdi; hDlg
0x18001a6ec  mov     [rbp+30h], rsi
0x18001a6f0  call    ?Number_ClearValues@@YAXPEAUHWND__@@@Z; Number_ClearValues(HWND__ *)
0x18001a6f5  mov     rcx, rdi; HWND
0x18001a6f8  call    ?Number_SetValues@@YAXPEAUHWND__@@@Z; Number_SetValues(HWND__ *)
0x18001a6fd  or      cs:?g_dwCustLastChange@@3KA, esi; ulong g_dwCustLastChange
0x18001a703  mov     eax, esi
0x18001a705  add     rsp, 40h
0x18001a709  pop     r14
0x18001a70b  pop     rdi
0x18001a70c  pop     rsi
0x18001a70d  pop     rbp
0x18001a70e  pop     rbx
0x18001a70f  retn
```
