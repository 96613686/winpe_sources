# FireNotificationAndTelemetryEventForBlockedAction(uint,void *,_SP_DEVINFO_DATA *)

- ea: `0x180014cf8`
- end: `0x180014eb3`
- name: `?FireNotificationAndTelemetryEventForBlockedAction@@YAXIPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `443`
- prototype: `void(unsigned int, void *, struct _SP_DEVINFO_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180013260`

## callees

- `0x180012b54`
- `0x180014cf8`
- `0x18001c5c0`
- `0x180026820`
- `0x180038be0`
- `0x180038cb4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014e19`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014e2e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014e43`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014e19`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014e2e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014e43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014df3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014df3`

## string_xrefs

- `0x180014da1`: `AllowInstall`
- `0x180014d8f`: `GetWindowsUpdateInfo`
- `0x180014d57`: `InstallDevice`
- `0x180014d69`: `InstallDeviceFiles`
- `0x180014d4e`: `MoveDevice`
- `0x180014d86`: `FinishInstallAction`
- `0x180014d45`: `InstallWizard`
- `0x180014d98`: `NewDeviceWizardFinishInstall`

## pseudocode

```c
void __fastcall FireNotificationAndTelemetryEventForBlockedAction(
        unsigned int a1,
        void *a2,
        struct _SP_DEVINFO_DATA *a3)
{
  const wchar_t *v4; // rax
  const wchar_t *v5; // rdi
  __int64 v6; // rax
  void *v7; // rsi
  __int64 v8; // rcx
  const wchar_t *v9; // rax
  unsigned int v10; // [rsp+40h] [rbp-30h] BYREF
  const wchar_t *v11; // [rsp+48h] [rbp-28h] BYREF
  __int64 v12; // [rsp+50h] [rbp-20h] BYREF
  __int64 v13; // [rsp+58h] [rbp-18h] BYREF
  const wchar_t *v14; // [rsp+60h] [rbp-10h] BYREF
  DWORD LastError; // [rsp+90h] [rbp+20h] BYREF
  int v16; // [rsp+A8h] [rbp+38h] BYREF

  v11 = L"UnexpectedAction";
  if ( a1 > 0x15 )
  {
    switch ( a1 )
    {
      case 0x18u:
        v4 = L"AllowInstall";
        break;
      case 0x1Eu:
        v4 = L"NewDeviceWizardFinishInstall";
        break;
      case 0x25u:
        v4 = L"GetWindowsUpdateInfo";
        break;
      case 0x2Au:
        v4 = L"FinishInstallAction";
        break;
      default:
        goto LABEL_23;
    }
  }
  else
  {
    switch ( a1 )
    {
      case 0x15u:
        v4 = L"InstallDeviceFiles";
        break;
      case 1u:
        v4 = L"SelectDevice";
        break;
      case 2u:
        v4 = L"InstallDevice";
        break;
      case 0xEu:
        v4 = L"MoveDevice";
        break;
      case 0x10u:
        v4 = L"InstallWizard";
        break;
      case 0x11u:
        v4 = L"DestroyWizardData";
        break;
      default:
        goto LABEL_23;
    }
  }
  v11 = v4;
LABEL_23:
  v5 = 0;
  v14 = 0;
  v13 = 0;
  v12 = 0;
  LastError = 0;
  v6 = BuildInternalData((int)a2, (int)a3);
  v7 = (void *)v6;
  if ( v6 )
  {
    v5 = *(const wchar_t **)v6;
    v13 = *(_QWORD *)(v6 + 40);
    v8 = *(_QWORD *)(v6 + 8);
    v9 = v5;
    v12 = v8;
    v14 = v5;
  }
  else
  {
    LastError = GetLastError();
    v9 = 0;
  }
  v16 = 0;
  if ( a1 == 21 && v9 && !wcsstr(v5, L"prnms012.inf") && !wcsstr(v5, L"prnms014.inf") && !wcsstr(v5, L"prnms015.inf") )
  {
    if ( IsActiveSessionCountLimited() )
      WindowsProtectedPrintNotificationHelper::ShowToastForWindowsProtectedPrintEvent();
    v16 = 1;
  }
  v10 = a1;
  ClassInstallerTelemetry::BlockedAction<unsigned short const * &,unsigned int,unsigned short const * &,unsigned short const * &,unsigned short const * &,int &,unsigned long &>(
    (unsigned int)&v11,
    (unsigned int)&v10,
    (unsigned int)&v14,
    (unsigned int)&v13,
    (__int64)&v12,
    (__int64)&v16,
    (__int64)&LastError);
  if ( v7 )
    DestroyLocalData(v7);
}

```

## disassembly

```asm
0x180014cf8  mov     [rsp-18h+arg_8], rbx
0x180014cfd  push    rbp
0x180014cfe  push    rsi
0x180014cff  push    rdi
0x180014d00  mov     rbp, rsp
0x180014d03  sub     rsp, 70h
0x180014d07  lea     rax, aUnexpectedacti; "UnexpectedAction"
0x180014d0e  mov     r9, r8
0x180014d11  mov     [rbp+var_28], rax
0x180014d15  mov     r10, rdx
0x180014d18  mov     ebx, ecx
0x180014d1a  cmp     ecx, 15h
0x180014d1d  ja      short loc_180014D72
0x180014d1f  jz      short loc_180014D69
0x180014d21  mov     eax, ecx
0x180014d23  sub     eax, 1
0x180014d26  jz      short loc_180014D60
0x180014d28  sub     eax, 1
0x180014d2b  jz      short loc_180014D57
0x180014d2d  sub     eax, 0Ch
0x180014d30  jz      short loc_180014D4E
0x180014d32  sub     eax, 2
0x180014d35  jz      short loc_180014D45
0x180014d37  cmp     eax, 1
0x180014d3a  jnz     short loc_180014DAC
0x180014d3c  lea     rax, aDestroywizardd; "DestroyWizardData"
0x180014d43  jmp     short loc_180014DA8
0x180014d45  lea     rax, aInstallwizard; "InstallWizard"
0x180014d4c  jmp     short loc_180014DA8
0x180014d4e  lea     rax, aMovedevice; "MoveDevice"
0x180014d55  jmp     short loc_180014DA8
0x180014d57  lea     rax, aInstalldevice; "InstallDevice"
0x180014d5e  jmp     short loc_180014DA8
0x180014d60  lea     rax, aSelectdevice; "SelectDevice"
0x180014d67  jmp     short loc_180014DA8
0x180014d69  lea     rax, aInstalldevicef; "InstallDeviceFiles"
0x180014d70  jmp     short loc_180014DA8
0x180014d72  cmp     ebx, 18h
0x180014d75  jz      short loc_180014DA1
0x180014d77  cmp     ebx, 1Eh
0x180014d7a  jz      short loc_180014D98
0x180014d7c  cmp     ebx, 25h ; '%'
0x180014d7f  jz      short loc_180014D8F
0x180014d81  cmp     ebx, 2Ah ; '*'
0x180014d84  jnz     short loc_180014DAC
0x180014d86  lea     rax, aFinishinstalla; "FinishInstallAction"
0x180014d8d  jmp     short loc_180014DA8
0x180014d8f  lea     rax, aGetwindowsupda; "GetWindowsUpdateInfo"
0x180014d96  jmp     short loc_180014DA8
0x180014d98  lea     rax, aNewdevicewizar; "NewDeviceWizardFinishInstall"
0x180014d9f  jmp     short loc_180014DA8
0x180014da1  lea     rax, aAllowinstall; "AllowInstall"
0x180014da8  mov     [rbp+var_28], rax
0x180014dac  mov     r8d, cs:MyPlatform
0x180014db3  xor     edi, edi
0x180014db5  mov     rdx, r9; int
0x180014db8  mov     [rbp+var_10], rdi
0x180014dbc  mov     rcx, r10; int
0x180014dbf  mov     [rbp+var_18], rdi
0x180014dc3  mov     [rbp+var_20], rdi
0x180014dc7  mov     [rbp+arg_0], edi
0x180014dca  call    BuildInternalData
0x180014dcf  mov     rsi, rax
0x180014dd2  test    rax, rax
0x180014dd5  jz      short loc_180014DF3
0x180014dd7  mov     rcx, [rax+28h]
0x180014ddb  mov     rdi, [rax]
0x180014dde  mov     [rbp+var_18], rcx
0x180014de2  mov     rcx, [rax+8]
0x180014de6  mov     rax, rdi
0x180014de9  mov     [rbp+var_20], rcx
0x180014ded  mov     [rbp+var_10], rdi
0x180014df1  jmp     short loc_180014DFE
0x180014df3  call    cs:__imp_GetLastError
0x180014df9  mov     [rbp+arg_0], eax
0x180014dfc  xor     eax, eax
0x180014dfe  mov     [rbp+arg_18], 0
0x180014e05  cmp     ebx, 15h
0x180014e08  jnz     short loc_180014E63
0x180014e0a  test    rax, rax
0x180014e0d  jz      short loc_180014E63
0x180014e0f  lea     rdx, aPrnms012Inf; "prnms012.inf"
0x180014e16  mov     rcx, rdi; Str
0x180014e19  call    cs:__imp_wcsstr
0x180014e1f  test    rax, rax
0x180014e22  jnz     short loc_180014E63
0x180014e24  lea     rdx, aPrnms014Inf; "prnms014.inf"
0x180014e2b  mov     rcx, rdi; Str
0x180014e2e  call    cs:__imp_wcsstr
0x180014e34  test    rax, rax
0x180014e37  jnz     short loc_180014E63
0x180014e39  lea     rdx, aPrnms015Inf; "prnms015.inf"
0x180014e40  mov     rcx, rdi; Str
0x180014e43  call    cs:__imp_wcsstr
0x180014e49  test    rax, rax
0x180014e4c  jnz     short loc_180014E63
0x180014e4e  call    ?IsActiveSessionCountLimited@@YA_NXZ; IsActiveSessionCountLimited(void)
0x180014e53  test    al, al
0x180014e55  jz      short loc_180014E5C
0x180014e57  call    ?ShowToastForWindowsProtectedPrintEvent@WindowsProtectedPrintNotificationHelper@@YAJW4NotificationType@WindowsProtectedPrint@Printing@Internal@Graphics@Windows@@@Z; WindowsProtectedPrintNotificationHelper::ShowToastForWindowsProtectedPrintEvent(Windows::Graphics::Internal::Printing::WindowsProtectedPrint::NotificationType)
0x180014e5c  mov     [rbp+arg_18], 1
0x180014e63  lea     rax, [rbp+arg_0]
0x180014e67  mov     [rbp+var_30], ebx
0x180014e6a  mov     [rsp+70h+var_40], rax
0x180014e6f  lea     r9, [rbp+var_18]
0x180014e73  lea     rax, [rbp+arg_18]
0x180014e77  mov     [rsp+70h+var_48], rax
0x180014e7c  lea     r8, [rbp+var_10]
0x180014e80  lea     rax, [rbp+var_20]
0x180014e84  lea     rdx, [rbp+var_30]
0x180014e88  mov     [rsp+70h+var_50], rax
0x180014e8d  lea     rcx, [rbp+var_28]
0x180014e91  call    ??$BlockedAction@AEAPEBGIAEAPEBGAEAPEBGAEAPEBGAEAHAEAK@ClassInstallerTelemetry@@SAXAEAPEBG$$QEAI000AEAHAEAK@Z; ClassInstallerTelemetry::BlockedAction<ushort const * &,uint,ushort const * &,ushort const * &,ushort const * &,int &,ulong &>(ushort const * &,uint &&,ushort const * &,ushort const * &,ushort const * &,int &,ulong &)
0x180014e96  test    rsi, rsi
0x180014e99  jz      short loc_180014EA3
0x180014e9b  mov     rcx, rsi; hMem
0x180014e9e  call    DestroyLocalData
0x180014ea3  mov     rbx, [rsp+70h+arg_8]
0x180014eab  add     rsp, 70h
0x180014eaf  pop     rdi
0x180014eb0  pop     rsi
0x180014eb1  pop     rbp
0x180014eb2  retn
```
