# CDeviceSettingsDialog::InitializeDeviceSettings(HWND__ *)

- ea: `0x180010bc8`
- end: `0x180010e25`
- name: `?InitializeDeviceSettings@CDeviceSettingsDialog@@AEAAKPEAUHWND__@@@Z`
- size: `605`
- prototype: `unsigned int __fastcall(CDeviceSettingsDialog *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011710`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000dd40`
- `0x18000dfe4`
- `0x180010864`
- `0x180010bc8`
- `0x180012670`
- `0x180012844`
- `0x1800152d8`

## import_xrefs

- `SHLWAPI!SHAutoComplete` at `0x180010dbf`
- `SHLWAPI!SHAutoComplete` at `0x180010dbf`
- `KERNEL32!GetLastError` at `0x180010d26`
- `KERNEL32!GetLastError` at `0x180010d26`
- `USER32!EnableWindow` at `0x180010d88`
- `USER32!EnableWindow` at `0x180010d88`
- `USER32!SetDlgItemTextW` at `0x180010c32`
- `USER32!SetDlgItemTextW` at `0x180010c45`
- `USER32!SetDlgItemTextW` at `0x180010c32`
- `USER32!SetDlgItemTextW` at `0x180010c45`
- `USER32!SendMessageW` at `0x180010d71`
- `USER32!SendMessageW` at `0x180010d71`
- `USER32!CheckDlgButton` at `0x180010cc1`
- `USER32!CheckDlgButton` at `0x180010df3`
- `USER32!CheckDlgButton` at `0x180010cc1`
- `USER32!CheckDlgButton` at `0x180010df3`
- `USER32!SendDlgItemMessageW` at `0x180010c00`
- `USER32!SendDlgItemMessageW` at `0x180010c1e`
- `USER32!SendDlgItemMessageW` at `0x180010c00`
- `USER32!SendDlgItemMessageW` at `0x180010c1e`
- `USER32!GetDlgItem` at `0x180010c51`
- `USER32!GetDlgItem` at `0x180010db3`
- `USER32!GetDlgItem` at `0x180010c51`
- `USER32!GetDlgItem` at `0x180010db3`

## pseudocode

```c
unsigned int __fastcall CDeviceSettingsDialog::InitializeDeviceSettings(CDeviceSettingsDialog *this, HWND a2)
{
  HWND DlgItem; // r15
  int v5; // r14d
  unsigned int *v6; // rbx
  __int64 v7; // rax
  DWORD LastError; // eax
  unsigned int i; // esi
  unsigned int result; // eax
  int v11; // esi
  HWND v12; // rax
  int v13; // ebx
  CDeviceSettingsDialog *v14; // rcx

  SendDlgItemMessageW(a2, 4545, 0xC5u, 0x14u, 0);
  SendDlgItemMessageW(a2, 4546, 0xC5u, 0x14u, 0);
  SetDlgItemTextW(a2, 4545, *(LPCWSTR *)(*((_QWORD *)this + 6) + 64LL));
  SetDlgItemTextW(a2, 4546, *(LPCWSTR *)(*((_QWORD *)this + 6) + 56LL));
  DlgItem = GetDlgItem(a2, 4547);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  v5 = FaxDeviceEnableRoutingMethod(
         *((HANDLE *)this + 7),
         *(_DWORD *)(*((_QWORD *)this + 6) + 4LL),
         L"{aec1b37c-9af2-11d0-abf7-00c04fd91a4e}");
  CheckDlgButton(a2, 4540, v5 != 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_f5b496eade1b3798203481970613ce29_Traceguids);
  }
  v6 = (unsigned int *)((char *)this + 72);
  v7 = CollectPrinterNames((char *)this + 72);
  *((_QWORD *)this + 8) = v7;
  if ( v7 )
  {
    for ( i = 0; i < *v6; ++i )
      SendMessageW(DlgItem, 0x143u, 0, *(_QWORD *)(*((_QWORD *)this + 8) + 16LL * i));
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_f5b496eade1b3798203481970613ce29_Traceguids, LastError);
    }
    *v6 = 0;
  }
  if ( !v5
    || (EnableWindow(DlgItem, v5), (result = CDeviceSettingsDialog::SetSelectedPrinterNameFromServer(this, DlgItem)) == 0) )
  {
    v11 = 0;
    SetLTREditDirection(a2, 4549);
    v12 = GetDlgItem(a2, 4549);
    SHAutoComplete(v12, 1u);
    v13 = FaxDeviceEnableRoutingMethod(
            *((HANDLE *)this + 7),
            *(_DWORD *)(*((_QWORD *)this + 6) + 4LL),
            L"{92041a90-9af2-11d0-abf7-00c04fd91a4e}");
    CheckDlgButton(a2, 4548, v13 != 0);
    if ( v13 )
    {
      CDeviceSettingsDialog::EnableStoreFolderControls(v14, a2, 1);
      return CDeviceSettingsDialog::SetSelectedStoreFolderFromServer(this, a2);
    }
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180010bc8  push    rbx
0x180010bca  push    rbp
0x180010bcb  push    rsi
0x180010bcc  push    rdi
0x180010bcd  push    r14
0x180010bcf  push    r15
0x180010bd1  sub     rsp, 38h
0x180010bd5  mov     rbp, rdx
0x180010bd8  mov     [rsp+68h+lParam], 0; lParam
0x180010be1  mov     rdi, rcx
0x180010be4  mov     esi, 14h
0x180010be9  mov     ebx, 0C5h
0x180010bee  mov     r14d, 11C1h
0x180010bf4  mov     r9d, esi; wParam
0x180010bf7  mov     r8d, ebx; Msg
0x180010bfa  mov     edx, r14d; nIDDlgItem
0x180010bfd  mov     rcx, rbp; hDlg
0x180010c00  call    cs:__imp_SendDlgItemMessageW
0x180010c06  mov     r8d, ebx; Msg
0x180010c09  mov     [rsp+68h+lParam], 0; lParam
0x180010c12  lea     ebx, [r14+1]
0x180010c16  mov     r9d, esi; wParam
0x180010c19  mov     edx, ebx; nIDDlgItem
0x180010c1b  mov     rcx, rbp; hDlg
0x180010c1e  call    cs:__imp_SendDlgItemMessageW
0x180010c24  mov     r8, [rdi+30h]
0x180010c28  mov     edx, r14d; nIDDlgItem
0x180010c2b  mov     rcx, rbp; hDlg
0x180010c2e  mov     r8, [r8+40h]; lpString
0x180010c32  call    cs:__imp_SetDlgItemTextW
0x180010c38  mov     r8, [rdi+30h]
0x180010c3c  mov     edx, ebx; nIDDlgItem
0x180010c3e  mov     rcx, rbp; hDlg
0x180010c41  mov     r8, [r8+38h]; lpString
0x180010c45  call    cs:__imp_SetDlgItemTextW
0x180010c4b  lea     edx, [rbx+1]; nIDDlgItem
0x180010c4e  mov     rcx, rbp; hDlg
0x180010c51  call    cs:__imp_GetDlgItem
0x180010c57  mov     r15, rax
0x180010c5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c61  lea     rbx, WPP_GLOBAL_Control
0x180010c68  mov     esi, 100h
0x180010c6d  cmp     rcx, rbx
0x180010c70  jz      short loc_180010C92
0x180010c72  test    [rcx+1Ch], esi
0x180010c75  jz      short loc_180010C92
0x180010c77  cmp     byte ptr [rcx+19h], 5
0x180010c7b  jb      short loc_180010C92
0x180010c7d  mov     rcx, [rcx+10h]
0x180010c81  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180010c88  mov     edx, 26h ; '&'
0x180010c8d  call    WPP_SF_
0x180010c92  mov     rdx, [rdi+30h]
0x180010c96  lea     r8, RoutingGuid; "{aec1b37c-9af2-11d0-abf7-00c04fd91a4e}"
0x180010c9d  mov     rcx, [rdi+38h]; FaxHandle
0x180010ca1  or      r9d, 0FFFFFFFFh
0x180010ca5  mov     edx, [rdx+4]; DeviceId
0x180010ca8  call    FaxDeviceEnableRoutingMethod
0x180010cad  xor     r8d, r8d
0x180010cb0  mov     edx, 11BCh; nIDButton
0x180010cb5  test    eax, eax
0x180010cb7  mov     rcx, rbp; hDlg
0x180010cba  mov     r14d, eax
0x180010cbd  setnz   r8b; uCheck
0x180010cc1  call    cs:__imp_CheckDlgButton
0x180010cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180010cce  cmp     rcx, rbx
0x180010cd1  jz      short loc_180010CF3
0x180010cd3  test    [rcx+1Ch], esi
0x180010cd6  jz      short loc_180010CF3
0x180010cd8  cmp     byte ptr [rcx+19h], 5
0x180010cdc  jb      short loc_180010CF3
0x180010cde  mov     rcx, [rcx+10h]
0x180010ce2  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180010ce9  mov     edx, 28h ; '('
0x180010cee  call    WPP_SF_
0x180010cf3  lea     rbx, [rdi+48h]
0x180010cf7  mov     rcx, rbx
0x180010cfa  call    CollectPrinterNames
0x180010cff  mov     [rdi+40h], rax
0x180010d03  test    rax, rax
0x180010d06  jnz     short loc_180010D53
0x180010d08  mov     rax, cs:WPP_GLOBAL_Control
0x180010d0f  lea     rcx, WPP_GLOBAL_Control
0x180010d16  cmp     rax, rcx
0x180010d19  jz      short loc_180010D4B
0x180010d1b  test    [rax+1Ch], esi
0x180010d1e  jz      short loc_180010D4B
0x180010d20  cmp     byte ptr [rax+19h], 3
0x180010d24  jb      short loc_180010D4B
0x180010d26  call    cs:__imp_GetLastError
0x180010d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d33  lea     r8, WPP_f5b496eade1b3798203481970613ce29_Traceguids
0x180010d3a  mov     edx, 29h ; ')'
0x180010d3f  mov     r9d, eax
0x180010d42  mov     rcx, [rcx+10h]
0x180010d46  call    WPP_SF_d
0x180010d4b  mov     dword ptr [rbx], 0
0x180010d51  jmp     short loc_180010D7D
0x180010d53  xor     esi, esi
0x180010d55  cmp     [rbx], esi
0x180010d57  jbe     short loc_180010D7D
0x180010d59  mov     r9, [rdi+40h]
0x180010d5d  xor     r8d, r8d; wParam
0x180010d60  mov     eax, esi
0x180010d62  mov     edx, 143h; Msg
0x180010d67  add     rax, rax
0x180010d6a  mov     rcx, r15; hWnd
0x180010d6d  mov     r9, [r9+rax*8]; lParam
0x180010d71  call    cs:__imp_SendMessageW
0x180010d77  inc     esi
0x180010d79  cmp     esi, [rbx]
0x180010d7b  jb      short loc_180010D59
0x180010d7d  test    r14d, r14d
0x180010d80  jz      short loc_180010D9D
0x180010d82  mov     edx, r14d; bEnable
0x180010d85  mov     rcx, r15; hWnd
0x180010d88  call    cs:__imp_EnableWindow
0x180010d8e  mov     rdx, r15; HWND
0x180010d91  mov     rcx, rdi; this
0x180010d94  call    ?SetSelectedPrinterNameFromServer@CDeviceSettingsDialog@@AEBAKPEAUHWND__@@@Z; CDeviceSettingsDialog::SetSelectedPrinterNameFromServer(HWND__ *)
0x180010d99  test    eax, eax
0x180010d9b  jnz     short loc_180010E18
0x180010d9d  mov     ebx, 11C5h
0x180010da2  mov     rcx, rbp; hDlg
0x180010da5  mov     edx, ebx; nIDDlgItem
0x180010da7  xor     esi, esi
0x180010da9  call    SetLTREditDirection
0x180010dae  mov     edx, ebx; nIDDlgItem
0x180010db0  mov     rcx, rbp; hDlg
0x180010db3  call    cs:__imp_GetDlgItem
0x180010db9  mov     rcx, rax; hwndEdit
0x180010dbc  lea     edx, [rsi+1]; dwFlags
0x180010dbf  call    cs:__imp_SHAutoComplete
0x180010dc5  mov     rdx, [rdi+30h]
0x180010dc9  lea     r8, a92041a909af211; "{92041a90-9af2-11d0-abf7-00c04fd91a4e}"
0x180010dd0  mov     rcx, [rdi+38h]; FaxHandle
0x180010dd4  or      r9d, 0FFFFFFFFh
0x180010dd8  mov     edx, [rdx+4]; DeviceId
0x180010ddb  call    FaxDeviceEnableRoutingMethod
0x180010de0  xor     r8d, r8d
0x180010de3  mov     edx, 11C4h; nIDButton
0x180010de8  test    eax, eax
0x180010dea  mov     rcx, rbp; hDlg
0x180010ded  mov     ebx, eax
0x180010def  setnz   r8b; uCheck
0x180010df3  call    cs:__imp_CheckDlgButton
0x180010df9  test    ebx, ebx
0x180010dfb  jz      short loc_180010E16
0x180010dfd  lea     r8d, [rsi+1]; int
0x180010e01  mov     rdx, rbp; HWND
0x180010e04  call    ?EnableStoreFolderControls@CDeviceSettingsDialog@@AEBAKPEAUHWND__@@H@Z; CDeviceSettingsDialog::EnableStoreFolderControls(HWND__ *,int)
0x180010e09  mov     rdx, rbp; HWND
0x180010e0c  mov     rcx, rdi; this
0x180010e0f  call    ?SetSelectedStoreFolderFromServer@CDeviceSettingsDialog@@AEBAKPEAUHWND__@@@Z; CDeviceSettingsDialog::SetSelectedStoreFolderFromServer(HWND__ *)
0x180010e14  mov     esi, eax
0x180010e16  mov     eax, esi
0x180010e18  add     rsp, 38h
0x180010e1c  pop     r15
0x180010e1e  pop     r14
0x180010e20  pop     rdi
0x180010e21  pop     rsi
0x180010e22  pop     rbp
0x180010e23  pop     rbx
0x180010e24  retn
```
