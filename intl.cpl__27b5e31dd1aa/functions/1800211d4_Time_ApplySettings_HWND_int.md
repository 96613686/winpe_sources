# Time_ApplySettings(HWND__ *,int)

- ea: `0x1800211d4`
- end: `0x180021374`
- name: `?Time_ApplySettings@@YAHPEAUHWND__@@H@Z`
- size: `416`
- prototype: `__int64 __fastcall(HWND hDlg, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180020f40`

## callees

- `0x1800211d4`
- `0x180021418`
- `0x180023714`
- `0x1800245bc`
- `0x180027c28`

## import_xrefs

- `KERNEL32!NlsUpdateLocale` at `0x180021323`
- `KERNEL32!NlsUpdateLocale` at `0x180021323`
- `USER32!SendNotifyMessageW` at `0x18002134a`
- `USER32!SendNotifyMessageW` at `0x18002134a`
- `USER32!GetDlgItem` at `0x180021283`
- `USER32!GetDlgItem` at `0x1800212a7`
- `USER32!GetDlgItem` at `0x180021283`
- `USER32!GetDlgItem` at `0x1800212a7`
- `USER32!GetWindowLongPtrW` at `0x1800211eb`
- `USER32!GetWindowLongPtrW` at `0x1800211eb`
- `USER32!GetParent` at `0x1800212e7`
- `USER32!GetParent` at `0x1800212e7`
- `USER32!SendMessageW` at `0x180021299`
- `USER32!SendMessageW` at `0x1800212b8`
- `USER32!SendMessageW` at `0x1800212fb`
- `USER32!SendMessageW` at `0x180021299`
- `USER32!SendMessageW` at `0x1800212b8`
- `USER32!SendMessageW` at `0x1800212fb`

## pseudocode

```c
__int64 __fastcall Time_ApplySettings(HWND hDlg)
{
  LONG_PTR WindowLongPtrW; // rsi
  __int64 v3; // rdi
  HWND DlgItem; // rax
  HWND v6; // rax
  HWND Parent; // rax
  __int64 v8; // rcx
  _QWORD *v9; // rax
  const unsigned __int16 *v10; // [rsp+30h] [rbp-18h]

  WindowLongPtrW = GetWindowLongPtrW(hDlg, 16);
  v3 = *(_QWORD *)(WindowLongPtrW + 48);
  if ( v3 )
  {
    Intl_ApplyPendingLocaleChange();
    if ( (v3 & 2) != 0 && !(unsigned int)Set_Locale_Values(hDlg, 0x28u, 1091, L"s1159", 0, 0, v10)
      || (v3 & 4) != 0 && !(unsigned int)Set_Locale_Values(hDlg, 0x29u, 1092, L"s2359", 0, 0, v10) )
    {
      return 0;
    }
    if ( (v3 & 0x18) != 0 )
    {
      DlgItem = GetDlgItem(hDlg, 1091);
      SendMessageW(DlgItem, 0x14Bu, 0, 0);
      v6 = GetDlgItem(hDlg, 1092);
      SendMessageW(v6, 0x14Bu, 0, 0);
      DropDown_Use_Locale_Values(hDlg, 0x28u, 1091);
      DropDown_Use_Locale_Values(hDlg, 0x29u, 1092);
    }
    Parent = GetParent(hDlg);
    SendMessageW(Parent, 0x46Du, (WPARAM)hDlg, 0);
    v8 = UserLocaleIndex;
    v9 = g_localeInfo;
    *(_QWORD *)(WindowLongPtrW + 48) = 1;
    NlsUpdateLocale(*(_QWORD *)(v9[v8] + 8LL), 4);
    if ( UserLocaleIndex == g_savedLocaleIndex )
      SendNotifyMessageW(HWND_BROADCAST, 0x1Au, 0, (LPARAM)L"intl");
    Time_DisplaySample(hDlg);
    g_dwCustLastChange |= 4u;
  }
  return 1;
}

```

## disassembly

```asm
0x1800211d4  mov     [rsp+arg_0], rbx
0x1800211d9  mov     [rsp+arg_8], rsi
0x1800211de  push    rdi
0x1800211df  sub     rsp, 40h
0x1800211e3  mov     edx, 10h; nIndex
0x1800211e8  mov     rbx, rcx
0x1800211eb  call    cs:__imp_GetWindowLongPtrW
0x1800211f1  mov     rsi, rax
0x1800211f4  mov     rdi, [rax+30h]
0x1800211f8  test    rdi, rdi
0x1800211fb  jz      loc_18002135F
0x180021201  call    ?Intl_ApplyPendingLocaleChange@@YAHXZ; Intl_ApplyPendingLocaleChange(void)
0x180021206  test    dil, 2
0x18002120a  jz      short loc_18002123A
0x18002120c  mov     [rsp+48h+var_20], 0; int
0x180021214  lea     r9, aS1159; "s1159"
0x18002121b  mov     edx, 28h ; '('; unsigned int
0x180021220  mov     [rsp+48h+var_28], 0; int
0x180021228  mov     r8d, 443h; nIDDlgItem
0x18002122e  mov     rcx, rbx; hDlg
0x180021231  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x180021236  test    eax, eax
0x180021238  jz      short loc_18002126E
0x18002123a  test    dil, 4
0x18002123e  jz      short loc_180021275
0x180021240  mov     [rsp+48h+var_20], 0; int
0x180021248  lea     r9, aS2359; "s2359"
0x18002124f  mov     edx, 29h ; ')'; unsigned int
0x180021254  mov     [rsp+48h+var_28], 0; int
0x18002125c  mov     r8d, 444h; nIDDlgItem
0x180021262  mov     rcx, rbx; hDlg
0x180021265  call    ?Set_Locale_Values@@YAHPEAUHWND__@@KHPEBGHH1@Z; Set_Locale_Values(HWND__ *,ulong,int,ushort const *,int,int,ushort const *)
0x18002126a  test    eax, eax
0x18002126c  jnz     short loc_180021275
0x18002126e  xor     eax, eax
0x180021270  jmp     loc_180021364
0x180021275  test    dil, 18h
0x180021279  jz      short loc_1800212E4
0x18002127b  mov     edx, 443h; nIDDlgItem
0x180021280  mov     rcx, rbx; hDlg
0x180021283  call    cs:__imp_GetDlgItem
0x180021289  mov     edi, 14Bh
0x18002128e  xor     r9d, r9d; lParam
0x180021291  mov     rcx, rax; hWnd
0x180021294  mov     edx, edi; Msg
0x180021296  xor     r8d, r8d; wParam
0x180021299  call    cs:__imp_SendMessageW
0x18002129f  mov     edx, 444h; nIDDlgItem
0x1800212a4  mov     rcx, rbx; hDlg
0x1800212a7  call    cs:__imp_GetDlgItem
0x1800212ad  xor     r9d, r9d; lParam
0x1800212b0  xor     r8d, r8d; wParam
0x1800212b3  mov     rcx, rax; hWnd
0x1800212b6  mov     edx, edi; Msg
0x1800212b8  call    cs:__imp_SendMessageW
0x1800212be  mov     edx, 28h ; '('; LCType
0x1800212c3  mov     r8d, 443h; nIDDlgItem
0x1800212c9  mov     rcx, rbx; hWnd
0x1800212cc  call    ?DropDown_Use_Locale_Values@@YAXPEAUHWND__@@KH@Z; DropDown_Use_Locale_Values(HWND__ *,ulong,int)
0x1800212d1  mov     edx, 29h ; ')'; LCType
0x1800212d6  mov     r8d, 444h; nIDDlgItem
0x1800212dc  mov     rcx, rbx; hWnd
0x1800212df  call    ?DropDown_Use_Locale_Values@@YAXPEAUHWND__@@KH@Z; DropDown_Use_Locale_Values(HWND__ *,ulong,int)
0x1800212e4  mov     rcx, rbx; hWnd
0x1800212e7  call    cs:__imp_GetParent
0x1800212ed  xor     r9d, r9d; lParam
0x1800212f0  mov     r8, rbx; wParam
0x1800212f3  mov     rcx, rax; hWnd
0x1800212f6  mov     edx, 46Dh; Msg
0x1800212fb  call    cs:__imp_SendMessageW
0x180021301  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180021307  mov     edx, 4
0x18002130c  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180021313  mov     qword ptr [rsi+30h], 1
0x18002131b  mov     rcx, [rax+rcx*8]
0x18002131f  mov     rcx, [rcx+8]
0x180021323  call    cs:__imp_NlsUpdateLocale
0x180021329  mov     eax, cs:?g_savedLocaleIndex@@3KA; ulong g_savedLocaleIndex
0x18002132f  cmp     cs:?UserLocaleIndex@@3KA, eax; ulong UserLocaleIndex
0x180021335  jnz     short loc_180021350
0x180021337  xor     r8d, r8d; wParam
0x18002133a  lea     r9, lParam; "intl"
0x180021341  mov     ecx, 0FFFFh; hWnd
0x180021346  lea     edx, [r8+1Ah]; Msg
0x18002134a  call    cs:__imp_SendNotifyMessageW
0x180021350  mov     rcx, rbx; HWND
0x180021353  call    ?Time_DisplaySample@@YAXPEAUHWND__@@@Z; Time_DisplaySample(HWND__ *)
0x180021358  or      cs:?g_dwCustLastChange@@3KA, 4; ulong g_dwCustLastChange
0x18002135f  mov     eax, 1
0x180021364  mov     rbx, [rsp+48h+arg_0]
0x180021369  mov     rsi, [rsp+48h+arg_8]
0x18002136e  add     rsp, 40h
0x180021372  pop     rdi
0x180021373  retn
```
