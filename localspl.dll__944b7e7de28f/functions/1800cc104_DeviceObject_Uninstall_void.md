# DeviceObject::Uninstall(void)

- ea: `0x1800cc104`
- end: `0x1800cc2f2`
- name: `?Uninstall@DeviceObject@@QEAAJXZ`
- size: `494`
- prototype: `__int64 __fastcall(DeviceObject *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180019394`
- `0x180031550`

## callees

- `0x1800183d4`
- `0x1800183f4`
- `0x180046650`
- `0x1800547e0`
- `0x1800cc104`
- `0x1800cc2f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc22c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc292`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc1ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc22c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800cc292`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800cc2d1`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800cc2d1`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800cc222`
- `SETUPAPI!SetupDiOpenDeviceInfoW` at `0x1800cc222`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x1800cc275`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x1800cc275`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800cc288`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800cc288`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x1800cc1d1`
- `SETUPAPI!SetupDiCreateDeviceInfoListExW` at `0x1800cc1d1`
- `CFGMGR32!SwDeviceSetLifetime` at `0x1800cc16f`
- `CFGMGR32!SwDeviceSetLifetime` at `0x1800cc16f`
- `CFGMGR32!SwDeviceClose` at `0x1800cc1b2`
- `CFGMGR32!SwDeviceClose` at `0x1800cc1b2`
- `CFGMGR32!SwDeviceSetAttributes` at `0x1800cc1a9`
- `CFGMGR32!SwDeviceSetAttributes` at `0x1800cc1a9`

## pseudocode

```c
__int64 __fastcall DeviceObject::Uninstall(DeviceObject *this)
{
  signed int v2; // ebx
  __int64 v3; // rdi
  int v4; // eax
  char v5; // r14
  const unsigned __int16 *v6; // rdx
  HDEVINFO DeviceInfoList; // rdi
  signed int LastError; // eax
  const WCHAR *v9; // rdx
  signed int v10; // eax
  signed int v11; // eax
  HKEY v13; // [rsp+30h] [rbp-48h] BYREF
  _SP_CLASSINSTALL_HEADER ClassInstallParams[2]; // [rsp+38h] [rbp-40h] BYREF
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+48h] [rbp-30h] BYREF

  v2 = 0;
  NCoreLibrary::TCriticalSection::Enter((DeviceObject *)((char *)this + 48));
  if ( *((_DWORD *)this + 6) == 2 )
  {
    v3 = 0;
    v4 = 3;
    v5 = 0;
  }
  else
  {
    v3 = *((_QWORD *)this + 2);
    v5 = 1;
    *((_QWORD *)this + 2) = 0;
    v4 = 4;
  }
  *((_DWORD *)this + 6) = v4;
  NCoreLibrary::TCriticalSection::Leave((DeviceObject *)((char *)this + 48));
  if ( !v5 )
    return (unsigned int)v2;
  if ( v3 )
  {
    SwDeviceSetLifetime(v3, 0);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
    {
      v13 = HKEY_LOCAL_MACHINE;
      if ( PrintCore::WindowsProtectedPrintHelpers::_GetRegDwordValueNoThrow(&v13, v6, L"WindowsProtectedPrintMode") )
        SwDeviceSetAttributes(v3, 1);
    }
    SwDeviceClose(v3);
  }
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  *(_OWORD *)&ClassInstallParams[0].cbSize = 0;
  DeviceInfoList = SetupDiCreateDeviceInfoListExW(0, 0, 0, 0);
  if ( DeviceInfoList != (HDEVINFO)-1LL )
    goto LABEL_14;
  LastError = GetLastError();
  v2 = LastError;
  if ( LastError > 0 )
    v2 = (unsigned __int16)LastError | 0x80070000;
  if ( !v2 )
  {
LABEL_14:
    v9 = (const WCHAR *)*((_QWORD *)this + 5);
    DeviceInfoData.cbSize = 32;
    if ( SetupDiOpenDeviceInfoW(DeviceInfoList, v9, 0, 2u, &DeviceInfoData) )
    {
LABEL_20:
      ClassInstallParams[0].cbSize = 8;
      ClassInstallParams[0].InstallFunction = 5;
      ClassInstallParams[1] = (_SP_CLASSINSTALL_HEADER)1LL;
      if ( !SetupDiSetClassInstallParamsW(DeviceInfoList, &DeviceInfoData, ClassInstallParams, 0x10u)
        || !SetupDiCallClassInstaller(5u, DeviceInfoList, &DeviceInfoData) )
      {
        v2 = GetLastError();
        if ( (v2 & 0xE0000000) == 0xE0000000 )
        {
          v2 = (unsigned __int16)v2 | 0x800F0000;
        }
        else if ( v2 > 0 )
        {
          v2 = (unsigned __int16)v2 | 0x80070000;
        }
      }
      goto LABEL_27;
    }
    v10 = GetLastError();
    v2 = v10;
    if ( v10 > 0 )
      v2 = (unsigned __int16)v10 | 0x80070000;
  }
  if ( v2 == -536870389 || v2 == -2147024883 )
  {
    v2 = 0;
  }
  else if ( v2 >= 0 )
  {
    goto LABEL_20;
  }
LABEL_27:
  v11 = 0;
  if ( v2 != -536870389 )
    v11 = v2;
  v2 = v11;
  if ( DeviceInfoList != (HDEVINFO)-1LL )
    SetupDiDestroyDeviceInfoList(DeviceInfoList);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800cc104  push    rbp
0x1800cc106  push    rbx
0x1800cc107  push    rsi
0x1800cc108  push    rdi
0x1800cc109  push    r14
0x1800cc10b  push    r15
0x1800cc10d  mov     rbp, rsp
0x1800cc110  sub     rsp, 78h
0x1800cc114  mov     rax, cs:__security_cookie
0x1800cc11b  xor     rax, rsp
0x1800cc11e  mov     [rbp+var_10], rax
0x1800cc122  mov     rsi, rcx
0x1800cc125  xor     ebx, ebx
0x1800cc127  add     rcx, 30h ; '0'; this
0x1800cc12b  call    ?Enter@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Enter(void)
0x1800cc130  cmp     dword ptr [rsi+18h], 2
0x1800cc134  jnz     short loc_1800CC140
0x1800cc136  xor     edi, edi
0x1800cc138  lea     eax, [rbx+3]
0x1800cc13b  xor     r14b, r14b
0x1800cc13e  jmp     short loc_1800CC150
0x1800cc140  mov     rdi, [rsi+10h]
0x1800cc144  mov     r14b, 1
0x1800cc147  mov     [rsi+10h], rbx
0x1800cc14b  mov     eax, 4
0x1800cc150  lea     rcx, [rsi+30h]; this
0x1800cc154  mov     [rsi+18h], eax
0x1800cc157  call    ?Leave@TCriticalSection@NCoreLibrary@@QEBAXXZ; NCoreLibrary::TCriticalSection::Leave(void)
0x1800cc15c  test    r14b, r14b
0x1800cc15f  jz      loc_1800CC2D7
0x1800cc165  test    rdi, rdi
0x1800cc168  jz      short loc_1800CC1B8
0x1800cc16a  xor     edx, edx
0x1800cc16c  mov     rcx, rdi
0x1800cc16f  call    cs:__imp_SwDeviceSetLifetime
0x1800cc175  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800cc17c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800cc181  test    al, al
0x1800cc183  jz      short loc_1800CC1AF
0x1800cc185  lea     r8, aWindowsprotect_0; "WindowsProtectedPrintMode"
0x1800cc18c  mov     [rbp+var_48], 0FFFFFFFF80000002h
0x1800cc194  lea     rcx, [rbp+var_48]; HKEY *
0x1800cc198  call    ?_GetRegDwordValueNoThrow@WindowsProtectedPrintHelpers@PrintCore@@CAKAEBQEAUHKEY__@@PEBG1@Z; PrintCore::WindowsProtectedPrintHelpers::_GetRegDwordValueNoThrow(HKEY__ * const &,ushort const *,ushort const *)
0x1800cc19d  test    eax, eax
0x1800cc19f  jz      short loc_1800CC1AF
0x1800cc1a1  mov     edx, 1
0x1800cc1a6  mov     rcx, rdi
0x1800cc1a9  call    cs:__imp_SwDeviceSetAttributes
0x1800cc1af  mov     rcx, rdi
0x1800cc1b2  call    cs:__imp_SwDeviceClose
0x1800cc1b8  xorps   xmm0, xmm0
0x1800cc1bb  xor     r9d, r9d; Reserved
0x1800cc1be  xor     r8d, r8d; MachineName
0x1800cc1c1  xor     edx, edx; hwndParent
0x1800cc1c3  xor     ecx, ecx; ClassGuid
0x1800cc1c5  movups  xmmword ptr [rbp+var_30.cbSize], xmm0
0x1800cc1c9  movups  xmmword ptr [rbp+var_30.ClassGuid.Data4+4], xmm0
0x1800cc1cd  movups  xmmword ptr [rbp+ClassInstallParams.cbSize], xmm0
0x1800cc1d1  call    cs:__imp_SetupDiCreateDeviceInfoListExW
0x1800cc1d7  mov     r15d, 0E000020Bh
0x1800cc1dd  mov     r14d, 80070000h
0x1800cc1e3  mov     rdi, rax
0x1800cc1e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800cc1ea  jnz     short loc_1800CC202
0x1800cc1ec  call    cs:__imp_GetLastError
0x1800cc1f2  mov     ebx, eax
0x1800cc1f4  test    eax, eax
0x1800cc1f6  jle     short loc_1800CC1FE
0x1800cc1f8  movzx   ebx, ax
0x1800cc1fb  or      ebx, r14d
0x1800cc1fe  test    ebx, ebx
0x1800cc200  jnz     short loc_1800CC23E
0x1800cc202  mov     rdx, [rsi+28h]; DeviceInstanceId
0x1800cc206  lea     rax, [rbp+var_30]
0x1800cc20a  mov     r9d, 2; OpenFlags
0x1800cc210  mov     [rsp+78h+DeviceInfoData], rax; DeviceInfoData
0x1800cc215  xor     r8d, r8d; hwndParent
0x1800cc218  mov     [rbp+var_30.cbSize], 20h ; ' '
0x1800cc21f  mov     rcx, rdi; DeviceInfoSet
0x1800cc222  call    cs:__imp_SetupDiOpenDeviceInfoW
0x1800cc228  test    eax, eax
0x1800cc22a  jnz     short loc_1800CC24F
0x1800cc22c  call    cs:__imp_GetLastError
0x1800cc232  mov     ebx, eax
0x1800cc234  test    eax, eax
0x1800cc236  jle     short loc_1800CC23E
0x1800cc238  movzx   ebx, ax
0x1800cc23b  or      ebx, r14d
0x1800cc23e  cmp     ebx, r15d
0x1800cc241  jz      short loc_1800CC2B0
0x1800cc243  cmp     ebx, 8007000Dh
0x1800cc249  jz      short loc_1800CC2B0
0x1800cc24b  test    ebx, ebx
0x1800cc24d  js      short loc_1800CC2BE
0x1800cc24f  mov     esi, 5
0x1800cc254  mov     [rbp+ClassInstallParams.cbSize], 8
0x1800cc25b  lea     r8, [rbp+ClassInstallParams]; ClassInstallParams
0x1800cc25f  mov     [rbp+ClassInstallParams.InstallFunction], esi
0x1800cc262  lea     rdx, [rbp+var_30]; DeviceInfoData
0x1800cc266  mov     qword ptr [rbp+ClassInstallParams.cbSize+8], 1
0x1800cc26e  mov     rcx, rdi; DeviceInfoSet
0x1800cc271  lea     r9d, [rsi+0Bh]; ClassInstallParamsSize
0x1800cc275  call    cs:__imp_SetupDiSetClassInstallParamsW
0x1800cc27b  test    eax, eax
0x1800cc27d  jz      short loc_1800CC292
0x1800cc27f  lea     r8, [rbp+var_30]; DeviceInfoData
0x1800cc283  mov     rdx, rdi; DeviceInfoSet
0x1800cc286  mov     ecx, esi; InstallFunction
0x1800cc288  call    cs:__imp_SetupDiCallClassInstaller
0x1800cc28e  test    eax, eax
0x1800cc290  jnz     short loc_1800CC2BE
0x1800cc292  call    cs:__imp_GetLastError
0x1800cc298  mov     ecx, 0E0000000h
0x1800cc29d  mov     ebx, eax
0x1800cc29f  and     eax, ecx
0x1800cc2a1  cmp     eax, ecx
0x1800cc2a3  jnz     short loc_1800CC2B4
0x1800cc2a5  movzx   ebx, bx
0x1800cc2a8  or      ebx, 800F0000h
0x1800cc2ae  jmp     short loc_1800CC2BE
0x1800cc2b0  xor     ebx, ebx
0x1800cc2b2  jmp     short loc_1800CC2BE
0x1800cc2b4  test    ebx, ebx
0x1800cc2b6  jle     short loc_1800CC2BE
0x1800cc2b8  movzx   ebx, bx
0x1800cc2bb  or      ebx, r14d
0x1800cc2be  xor     eax, eax
0x1800cc2c0  cmp     ebx, r15d
0x1800cc2c3  cmovnz  eax, ebx
0x1800cc2c6  mov     ebx, eax
0x1800cc2c8  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800cc2cc  jz      short loc_1800CC2D7
0x1800cc2ce  mov     rcx, rdi; DeviceInfoSet
0x1800cc2d1  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800cc2d7  mov     eax, ebx
0x1800cc2d9  mov     rcx, [rbp+var_10]
0x1800cc2dd  xor     rcx, rsp; StackCookie
0x1800cc2e0  call    __security_check_cookie
0x1800cc2e5  add     rsp, 78h
0x1800cc2e9  pop     r15
0x1800cc2eb  pop     r14
0x1800cc2ed  pop     rdi
0x1800cc2ee  pop     rsi
0x1800cc2ef  pop     rbx
0x1800cc2f0  pop     rbp
0x1800cc2f1  retn
```
