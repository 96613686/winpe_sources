# ShowPortableWorkspaceLauncherConfigurationUX(void)

- ea: `0x180008e20`
- end: `0x1800090fa`
- name: `?ShowPortableWorkspaceLauncherConfigurationUX@@YAXXZ`
- size: `730`
- prototype: `void(void)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002148`
- `0x18000253c`
- `0x180005528`
- `0x180008ac8`
- `0x180008b30`
- `0x180008d9c`
- `0x180008e20`
- `0x180009360`
- `0x18000946c`
- `0x180009974`
- `0x1800099bc`
- `0x18000c60c`
- `0x18000ca3c`
- `0x18000cab8`
- `0x180011010`

## import_xrefs

- `USER32!SetProcessDPIAware` at `0x180008eaf`
- `USER32!SetProcessDPIAware` at `0x180008eaf`
- `USER32!GetActiveWindow` at `0x180008f0d`
- `USER32!GetActiveWindow` at `0x180008fbf`
- `USER32!GetActiveWindow` at `0x180008f0d`
- `USER32!GetActiveWindow` at `0x180008fbf`
- `KERNEL32!LoadLibraryW` at `0x180008f2c`
- `KERNEL32!LoadLibraryW` at `0x180008f2c`
- `KERNEL32!GetProcAddress` at `0x180008f48`
- `KERNEL32!GetProcAddress` at `0x180008f48`
- `KERNEL32!FreeLibrary` at `0x180008f6a`
- `KERNEL32!FreeLibrary` at `0x180008f6a`
- `ole32!CoInitialize` at `0x180008e62`
- `ole32!CoInitialize` at `0x180008e62`
- `ole32!CoUninitialize` at `0x180009007`
- `ole32!CoUninitialize` at `0x180009007`

## string_xrefs

- `0x180008f25`: `comctl32.dll`
- `0x180008e93`: `drivers\wdm\usbpw\launcher\dll\ux.cpp`
- `0x18000906c`: `drivers\wdm\usbpw\launcher\dll\ux.cpp`
- `0x1800090c4`: `drivers\wdm\usbpw\launcher\dll\ux.cpp`
- `0x180008f3e`: `TaskDialogIndirect`

## pseudocode

```c
void ShowPortableWorkspaceLauncherConfigurationUX(void)
{
  HWND v0; // rax
  int v1; // edi
  HMODULE LibraryW; // rax
  HMODULE v3; // rsi
  FARPROC ProcAddress; // rax
  HWND ActiveWindow; // rdx
  int v6; // eax
  int v7; // edi
  HWND v8; // rax
  _BYTE pExceptionObject[4]; // [rsp+30h] [rbp-F8h] BYREF
  _BYTE v10[4]; // [rsp+34h] [rbp-F4h] BYREF
  const ATL::CAtlException *v11; // [rsp+38h] [rbp-F0h] BYREF
  void **v12; // [rsp+40h] [rbp-E8h] BYREF
  char v13; // [rsp+4Ch] [rbp-DCh]
  _BYTE v14[16]; // [rsp+50h] [rbp-D8h] BYREF
  _BYTE v15[8]; // [rsp+60h] [rbp-C8h] BYREF
  _BYTE v16[4]; // [rsp+68h] [rbp-C0h] BYREF
  HWND v17; // [rsp+6Ch] [rbp-BCh]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_10512c3147f2350527aef22e4c614f89_Traceguids);
  if ( CoInitialize(0) >= 0 )
  {
    if ( !SetProcessDPIAware()
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_10512c3147f2350527aef22e4c614f89_Traceguids);
    }
    try
    {
      ux::CSingleInstanceApplication::CSingleInstanceApplication(&v12);
      if ( v13 )
      {
        if ( CLauncherUtils::IsRunningOnPortableOperatingSystem() )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_10512c3147f2350527aef22e4c614f89_Traceguids);
          ux::CLauncherErrorTaskDialog::CLauncherErrorTaskDialog((ux::CLauncherErrorTaskDialog *)v15, 210, 215);
          ActiveWindow = GetActiveWindow();
          v6 = WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal(v16, ActiveWindow);
          v7 = v6;
          if ( v6 < 0 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                (unsigned int)&WPP_10512c3147f2350527aef22e4c614f89_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\ux.cpp",
                86,
                v6);
            ATL::CAtlException::CAtlException((ATL::CAtlException *)v10, v7);
            throw (ATL::CAtlException *)v10;
          }
          ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog((ux::CLauncherErrorTaskDialog *)v15);
        }
        else
        {
          ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog((ux::CLauncherMainTaskDialog *)v15);
          v0 = GetActiveWindow();
          if ( !v17 )
            v17 = v0;
          v1 = -2147418113;
          LibraryW = LoadLibraryW(L"comctl32.dll");
          v3 = LibraryW;
          if ( !LibraryW )
            goto LABEL_32;
          ProcAddress = GetProcAddress(LibraryW, "TaskDialogIndirect");
          if ( ProcAddress )
            v1 = ((__int64 (__fastcall *)(_BYTE *, _QWORD, _QWORD, _QWORD))ProcAddress)(v16, 0, 0, 0);
          FreeLibrary(v3);
          if ( v1 < 0 )
          {
LABEL_32:
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sdD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                13,
                (unsigned int)&WPP_10512c3147f2350527aef22e4c614f89_Traceguids,
                (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\ux.cpp",
                79,
                v1);
            ATL::CAtlException::CAtlException((ATL::CAtlException *)pExceptionObject, v1);
            throw (ATL::CAtlException *)pExceptionObject;
          }
          ux::CLauncherMainTaskDialog::~CLauncherMainTaskDialog((ux::CLauncherMainTaskDialog *)v15);
        }
      }
      v12 = &ux::CSingleInstanceApplication::`vftable';
      CMutex::~CMutex((CMutex *)v14);
    }
    catch ( const ATL::CAtlException *v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sdD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)&WPP_10512c3147f2350527aef22e4c614f89_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\ux.cpp",
          92,
          *(_DWORD *)v11);
      ux::CLauncherErrorTaskDialog::CLauncherErrorTaskDialog((ux::CLauncherErrorTaskDialog *)v15, 216, 214);
      v8 = GetActiveWindow();
      if ( (int)WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal(v16, v8) < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_10512c3147f2350527aef22e4c614f89_Traceguids);
      }
      ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog((ux::CLauncherErrorTaskDialog *)v15);
    }
    catch ( ... )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          18,
          (unsigned int)&WPP_10512c3147f2350527aef22e4c614f89_Traceguids,
          (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\ux.cpp",
          102);
    }
    CoUninitialize();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_10512c3147f2350527aef22e4c614f89_Traceguids);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      (unsigned int)&WPP_10512c3147f2350527aef22e4c614f89_Traceguids,
      (unsigned int)"drivers\\wdm\\usbpw\\launcher\\dll\\ux.cpp",
      54);
  }
}

```

## disassembly

```asm
0x180008e20  mov     [rsp+arg_0], rbx
0x180008e25  mov     [rsp+arg_8], rsi
0x180008e2a  push    rdi
0x180008e2b  sub     rsp, 120h
0x180008e32  lea     rbx, WPP_GLOBAL_Control
0x180008e39  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e40  cmp     rcx, rbx
0x180008e43  jz      short loc_180008E60
0x180008e45  test    byte ptr [rcx+1Ch], 8
0x180008e49  jz      short loc_180008E60
0x180008e4b  mov     edx, 0Ah
0x180008e50  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x180008e57  mov     rcx, [rcx+10h]
0x180008e5b  call    WPP_SF_
0x180008e60  xor     ecx, ecx; pvReserved
0x180008e62  call    cs:__imp_CoInitialize
0x180008e68  test    eax, eax
0x180008e6a  jns     short loc_180008EAF
0x180008e6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e73  cmp     rcx, rbx
0x180008e76  jz      loc_180009034
0x180008e7c  test    byte ptr [rcx+1Ch], 1
0x180008e80  jz      loc_180009034
0x180008e86  mov     edx, 0Bh
0x180008e8b  mov     [rsp+128h+var_108], 36h ; '6'
0x180008e93  lea     r9, aDriversWdmUsbp_6; "drivers\\wdm\\usbpw\\launcher\\dll\\ux."...
0x180008e9a  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x180008ea1  mov     rcx, [rcx+10h]
0x180008ea5  call    WPP_SF_sd
0x180008eaa  jmp     loc_180009034
0x180008eaf  call    cs:__imp_SetProcessDPIAware
0x180008eb5  test    eax, eax
0x180008eb7  jnz     short loc_180008EDF
0x180008eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ec0  cmp     rcx, rbx
0x180008ec3  jz      short loc_180008EDF
0x180008ec5  test    byte ptr [rcx+1Ch], 1
0x180008ec9  jz      short loc_180008EDF
0x180008ecb  lea     edx, [rax+0Ch]
0x180008ece  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x180008ed5  mov     rcx, [rcx+10h]
0x180008ed9  call    WPP_SF_
0x180008ede  nop
0x180008edf  lea     rcx, [rsp+128h+var_E8]
0x180008ee4  call    ??0CSingleInstanceApplication@ux@@QEAA@W4SingleInstanceType@1@@Z; ux::CSingleInstanceApplication::CSingleInstanceApplication(ux::SingleInstanceType)
0x180008ee9  nop
0x180008eea  cmp     [rsp+128h+var_DC], 0
0x180008eef  jz      loc_180008FE7
0x180008ef5  call    ?IsRunningOnPortableOperatingSystem@CLauncherUtils@@SA_NXZ; CLauncherUtils::IsRunningOnPortableOperatingSystem(void)
0x180008efa  test    al, al
0x180008efc  jnz     loc_180008F84
0x180008f02  lea     rcx, [rsp+128h+var_C8]; this
0x180008f07  call    ??0CLauncherMainTaskDialog@ux@@QEAA@XZ; ux::CLauncherMainTaskDialog::CLauncherMainTaskDialog(void)
0x180008f0c  nop
0x180008f0d  call    cs:__imp_GetActiveWindow
0x180008f13  cmp     [rsp+128h+var_BC], 0
0x180008f19  jnz     short loc_180008F20
0x180008f1b  mov     [rsp+128h+var_BC], rax
0x180008f20  mov     edi, 8000FFFFh
0x180008f25  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180008f2c  call    cs:__imp_LoadLibraryW
0x180008f32  mov     rsi, rax
0x180008f35  test    rax, rax
0x180008f38  jz      loc_180009049
0x180008f3e  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x180008f45  mov     rcx, rax; hModule
0x180008f48  call    cs:__imp_GetProcAddress
0x180008f4e  test    rax, rax
0x180008f51  jz      short loc_180008F67
0x180008f53  xor     r9d, r9d
0x180008f56  xor     r8d, r8d
0x180008f59  xor     edx, edx
0x180008f5b  lea     rcx, [rsp+128h+var_C0]
0x180008f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f65  mov     edi, eax
0x180008f67  mov     rcx, rsi; hLibModule
0x180008f6a  call    cs:__imp_FreeLibrary
0x180008f70  test    edi, edi
0x180008f72  js      loc_180009049
0x180008f78  lea     rcx, [rsp+128h+var_C8]; this
0x180008f7d  call    ??1CLauncherMainTaskDialog@ux@@UEAA@XZ; ux::CLauncherMainTaskDialog::~CLauncherMainTaskDialog(void)
0x180008f82  jmp     short loc_180008FE7
0x180008f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f8b  cmp     rcx, rbx
0x180008f8e  jz      short loc_180008FAB
0x180008f90  test    byte ptr [rcx+1Ch], 1
0x180008f94  jz      short loc_180008FAB
0x180008f96  mov     edx, 0Eh
0x180008f9b  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x180008fa2  mov     rcx, [rcx+10h]
0x180008fa6  call    WPP_SF_
0x180008fab  mov     edx, 0D2h; int
0x180008fb0  lea     r8d, [rdx+5]; int
0x180008fb4  lea     rcx, [rsp+128h+var_C8]; this
0x180008fb9  call    ??0CLauncherErrorTaskDialog@ux@@QEAA@HH@Z; ux::CLauncherErrorTaskDialog::CLauncherErrorTaskDialog(int,int)
0x180008fbe  nop
0x180008fbf  call    cs:__imp_GetActiveWindow
0x180008fc5  mov     rdx, rax
0x180008fc8  lea     rcx, [rsp+128h+var_C0]
0x180008fcd  call    ?DoModal@?$CTaskDialogImpl@VCLauncherErrorTaskDialog@ux@@@WTL@@QEAAJPEAUHWND__@@PEAH11@Z; WTL::CTaskDialogImpl<ux::CLauncherErrorTaskDialog>::DoModal(HWND__ *,int *,int *,int *)
0x180008fd2  mov     edi, eax
0x180008fd4  test    eax, eax
0x180008fd6  js      loc_1800090A1
0x180008fdc  lea     rcx, [rsp+128h+var_C8]; this
0x180008fe1  call    ??1CLauncherErrorTaskDialog@ux@@UEAA@XZ; ux::CLauncherErrorTaskDialog::~CLauncherErrorTaskDialog(void)
0x180008fe6  nop
0x180008fe7  lea     rax, ??_7CSingleInstanceApplication@ux@@6B@; const ux::CSingleInstanceApplication::`vftable'
0x180008fee  mov     [rsp+128h+var_E8], rax
0x180008ff3  lea     rcx, [rsp+128h+var_D8]; this
0x180008ff8  call    ??1CMutex@@UEAA@XZ; CMutex::~CMutex(void)
0x180008ffd  nop
0x180008ffe  jmp     short loc_180009007
0x180009000  lea     rbx, WPP_GLOBAL_Control
0x180009007  call    cs:__imp_CoUninitialize
0x18000900d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009014  cmp     rcx, rbx
0x180009017  jz      short loc_180009034
0x180009019  test    byte ptr [rcx+1Ch], 8
0x18000901d  jz      short loc_180009034
0x18000901f  mov     edx, 13h
0x180009024  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x18000902b  mov     rcx, [rcx+10h]
0x18000902f  call    WPP_SF_
0x180009034  lea     r11, [rsp+128h+var_8]
0x18000903c  mov     rbx, [r11+10h]
0x180009040  mov     rsi, [r11+18h]
0x180009044  mov     rsp, r11
0x180009047  pop     rdi
0x180009048  retn
0x180009049  mov     rcx, cs:WPP_GLOBAL_Control
0x180009050  cmp     rcx, rbx
0x180009053  jz      short loc_180009083
0x180009055  test    byte ptr [rcx+1Ch], 1
0x180009059  jz      short loc_180009083
0x18000905b  mov     edx, 0Dh
0x180009060  mov     [rsp+128h+var_100], edi
0x180009064  mov     [rsp+128h+var_108], 4Fh ; 'O'
0x18000906c  lea     r9, aDriversWdmUsbp_6; "drivers\\wdm\\usbpw\\launcher\\dll\\ux."...
0x180009073  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x18000907a  mov     rcx, [rcx+10h]
0x18000907e  call    WPP_SF_sdD
0x180009083  mov     edx, edi; int
0x180009085  lea     rcx, [rsp+128h+pExceptionObject]; this
0x18000908a  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x18000908f  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180009096  lea     rcx, [rsp+128h+pExceptionObject]; pExceptionObject
0x18000909b  call    _CxxThrowException_0
0x1800090a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090a8  cmp     rcx, rbx
0x1800090ab  jz      short loc_1800090DB
0x1800090ad  test    byte ptr [rcx+1Ch], 1
0x1800090b1  jz      short loc_1800090DB
0x1800090b3  mov     edx, 0Fh
0x1800090b8  mov     [rsp+128h+var_100], eax
0x1800090bc  mov     [rsp+128h+var_108], 56h ; 'V'
0x1800090c4  lea     r9, aDriversWdmUsbp_6; "drivers\\wdm\\usbpw\\launcher\\dll\\ux."...
0x1800090cb  lea     r8, WPP_10512c3147f2350527aef22e4c614f89_Traceguids
0x1800090d2  mov     rcx, [rcx+10h]
0x1800090d6  call    WPP_SF_sdD
0x1800090db  mov     edx, edi; int
0x1800090dd  lea     rcx, [rsp+128h+var_F4]; this
0x1800090e2  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x1800090e7  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x1800090ee  lea     rcx, [rsp+128h+var_F4]; pExceptionObject
0x1800090f3  call    _CxxThrowException_0
```
