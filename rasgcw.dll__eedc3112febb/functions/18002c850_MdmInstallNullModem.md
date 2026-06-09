# MdmInstallNullModem

- ea: `0x18002c850`
- end: `0x18002cc05`
- name: `MdmInstallNullModem`
- size: `949`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180027e84`

## callees

- `0x18002c2d4`
- `0x18002c318`
- `0x18002c83c`
- `0x18002c850`
- `0x18002f382`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ca0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cbf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f95b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002cbf8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f95b`
- `KERNEL32!lstrlenW` at `0x18002c9d9`
- `KERNEL32!lstrlenW` at `0x18002c9d9`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x18002cab0`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x18002cab0`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x18002cba8`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x18002cba8`
- `SETUPAPI!SetupDiSetSelectedDriverW` at `0x18002cb1d`
- `SETUPAPI!SetupDiSetSelectedDriverW` at `0x18002cb1d`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x18002cbc4`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x18002cbe0`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x18002cbc4`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x18002cbe0`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18002ca3c`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18002ca3c`
- `SETUPAPI!SetupDiSetDeviceRegistryPropertyW` at `0x18002ca03`
- `SETUPAPI!SetupDiSetDeviceRegistryPropertyW` at `0x18002ca03`
- `SETUPAPI!SetupDiCreateDeviceInfoW` at `0x18002c977`
- `SETUPAPI!SetupDiCreateDeviceInfoW` at `0x18002c977`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18002c903`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18002c903`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18002cafc`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18002cafc`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002ca8f`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002ca8f`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18002cbea`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18002f94c`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18002cbea`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18002f94c`

## pseudocode

```c
__int64 __fastcall MdmInstallNullModem(__int64 a1)
{
  BYTE *v2; // rsi
  HDEVINFO v3; // rdi
  DWORD LastError; // ebx
  __int64 v6; // rax
  _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+60h] [rbp-E18h] BYREF
  __int64 *v8; // [rsp+120h] [rbp-D58h]
  __int64 v9; // [rsp+128h] [rbp-D50h]
  struct _SP_DEVINFO_DATA DeviceInfoData; // [rsp+130h] [rbp-D48h] BYREF
  GUID ClassGuid; // [rsp+150h] [rbp-D28h] BYREF
  _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+160h] [rbp-D18h] BYREF
  __int64 v13; // [rsp+3B0h] [rbp-AC8h] BYREF
  _BYTE v14[16]; // [rsp+3B8h] [rbp-AC0h] BYREF
  int v15; // [rsp+3C8h] [rbp-AB0h]
  _BYTE v16[1108]; // [rsp+3CCh] [rbp-AACh] BYREF
  _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+820h] [rbp-658h] BYREF

  ClassGuid = GUID_DEVCLASS_MODEM;
  memset(&DeviceInfoData, 0, sizeof(DeviceInfoData));
  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  memset_0(&DriverInfoData, 0, sizeof(DriverInfoData));
  v13 = 1128;
  memset_0(v14, 0, 0x460u);
  memset_0(&ClassInstallParams, 0, 0xD0u);
  v2 = 0;
  v3 = SetupDiCreateDeviceInfoList(&ClassGuid, 0);
  if ( v3 == (HDEVINFO)-1LL )
    return 1003;
  DeviceInfoData.cbSize = 32;
  if ( !SetupDiCreateDeviceInfoW(v3, L"PNPC031", &ClassGuid, 0, 0, 1u, &DeviceInfoData) )
    goto LABEL_4;
  v6 = MdmAlloc(40);
  v2 = (BYTE *)v6;
  if ( !v6 )
  {
    LastError = 8;
    goto LABEL_20;
  }
  LastError = StringCchCopyNWrapW(v6, 20, L"PNPC031");
  if ( LastError )
    goto LABEL_20;
  *(_WORD *)&v2[2 * lstrlenW(L"PNPC031") + 2] = 0;
  if ( !SetupDiSetDeviceRegistryPropertyW(v3, &DeviceInfoData, 1u, v2, 0x14u) )
    goto LABEL_9;
  DeviceInstallParams.cbSize = 584;
  if ( !SetupDiGetDeviceInstallParamsW(v3, &DeviceInfoData, &DeviceInstallParams) )
    goto LABEL_9;
  LastError = StringCchCopyNWrapW(DeviceInstallParams.DriverPath, 260, L"mdmhayes.inf");
  if ( LastError )
    goto LABEL_20;
  DeviceInstallParams.Flags |= 0x10000u;
  if ( !SetupDiSetDeviceInstallParamsW(v3, &DeviceInfoData, &DeviceInstallParams)
    || !SetupDiBuildDriverInfoList(v3, &DeviceInfoData, 2u)
    || (memset_0(&DriverInfoData, 0, sizeof(DriverInfoData)),
        DriverInfoData.cbSize = 1568,
        !SetupDiEnumDriverInfoW(v3, &DeviceInfoData, 2u, 0, &DriverInfoData)) )
  {
LABEL_9:
    LastError = GetLastError();
    goto LABEL_20;
  }
  if ( SetupDiSetSelectedDriverW(v3, &DeviceInfoData, &DriverInfoData) )
  {
    v15 = 2;
    LastError = StringCchCopyWrapW(v16, 32, a1);
    if ( LastError )
      goto LABEL_20;
    memset_0(&ClassInstallParams, 0, 0xD0u);
    ClassInstallParams.cbSize = 8;
    ClassInstallParams.InstallFunction = 16;
    v9 = 0;
    v8 = &v13;
    if ( SetupDiSetClassInstallParamsW(v3, &DeviceInfoData, &ClassInstallParams, 0xD0u)
      && SetupDiCallClassInstaller(0x10u, v3, &DeviceInfoData) )
    {
      SetupDiCallClassInstaller(0x11u, v3, &DeviceInfoData);
      goto LABEL_20;
    }
    goto LABEL_9;
  }
LABEL_4:
  LastError = 1003;
LABEL_20:
  SetupDiDestroyDeviceInfoList(v3);
  if ( v2 )
    LocalFree(v2);
  return LastError;
}

```

## disassembly

```asm
0x18002c850  push    rbx
0x18002c852  push    rsi
0x18002c853  push    rdi
0x18002c854  push    r14
0x18002c856  sub     rsp, 0E58h
0x18002c85d  mov     rax, cs:__security_cookie
0x18002c864  xor     rax, rsp
0x18002c867  mov     [rsp+0E78h+var_38], rax
0x18002c86f  mov     r14, rcx
0x18002c872  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_MODEM.Data1
0x18002c879  movdqu  xmmword ptr [rsp+0E78h+ClassGuid.Data1], xmm0
0x18002c882  xorps   xmm1, xmm1
0x18002c885  movups  xmmword ptr [rsp+0E78h+var_D48.cbSize], xmm1
0x18002c88d  movups  xmmword ptr [rsp+0E78h+var_D48.ClassGuid.Data4+4], xmm1
0x18002c895  xor     edx, edx; Val
0x18002c897  mov     r8d, 248h; Size
0x18002c89d  lea     rcx, [rsp+0E78h+DeviceInstallParams]; void *
0x18002c8a5  call    memset_0
0x18002c8aa  xor     edx, edx; Val
0x18002c8ac  mov     r8d, 620h; Size
0x18002c8b2  lea     rcx, [rsp+0E78h+DriverInfoData]; void *
0x18002c8ba  call    memset_0
0x18002c8bf  mov     [rsp+0E78h+var_AC8], 468h
0x18002c8cb  xor     edx, edx; Val
0x18002c8cd  mov     r8d, 460h; Size
0x18002c8d3  lea     rcx, [rsp+0E78h+var_AC0]; void *
0x18002c8db  call    memset_0
0x18002c8e0  xor     edx, edx; Val
0x18002c8e2  mov     r8d, 0D0h; Size
0x18002c8e8  lea     rcx, [rsp+0E78h+ClassInstallParams]; void *
0x18002c8ed  call    memset_0
0x18002c8f2  xor     esi, esi
0x18002c8f4  mov     [rsp+0E78h+var_E30], rsi
0x18002c8f9  xor     edx, edx; hwndParent
0x18002c8fb  lea     rcx, [rsp+0E78h+ClassGuid]; ClassGuid
0x18002c903  call    cs:__imp_SetupDiCreateDeviceInfoList
0x18002c909  mov     rdi, rax
0x18002c90c  mov     [rsp+0E78h+var_E28], rax
0x18002c911  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002c915  jnz     short loc_18002C939
0x18002c917  mov     eax, 3EBh
0x18002c91c  mov     rcx, [rsp+0E78h+var_38]
0x18002c924  xor     rcx, rsp; StackCookie
0x18002c927  call    __security_check_cookie
0x18002c92c  add     rsp, 0E58h
0x18002c933  pop     r14
0x18002c935  pop     rdi
0x18002c936  pop     rsi
0x18002c937  pop     rbx
0x18002c938  retn
0x18002c939  mov     [rsp+0E78h+var_D48.cbSize], 20h ; ' '
0x18002c944  lea     rax, [rsp+0E78h+var_D48]
0x18002c94c  mov     [rsp+0E78h+DeviceInfoData], rax; DeviceInfoData
0x18002c951  mov     [rsp+0E78h+CreationFlags], 1; CreationFlags
0x18002c959  mov     [rsp+0E78h+hwndParent], 0; hwndParent
0x18002c962  xor     r9d, r9d; DeviceDescription
0x18002c965  lea     r8, [rsp+0E78h+ClassGuid]; ClassGuid
0x18002c96d  lea     rdx, pszNullModemId; "PNPC031"
0x18002c974  mov     rcx, rdi; DeviceInfoSet
0x18002c977  call    cs:__imp_SetupDiCreateDeviceInfoW
0x18002c97d  test    eax, eax
0x18002c97f  jnz     short loc_18002C98F
0x18002c981  mov     ebx, 3EBh
0x18002c986  mov     [rsp+0E78h+var_E38], ebx
0x18002c98a  jmp     loc_18002CBE7
0x18002c98f  mov     ecx, 28h ; '('
0x18002c994  call    MdmAlloc
0x18002c999  mov     rsi, rax
0x18002c99c  mov     [rsp+0E78h+var_E30], rax
0x18002c9a1  test    rax, rax
0x18002c9a4  jnz     short loc_18002C9AB
0x18002c9a6  lea     ebx, [rax+8]
0x18002c9a9  jmp     short loc_18002C986
0x18002c9ab  mov     r9d, 8
0x18002c9b1  lea     r8, pszNullModemId; "PNPC031"
0x18002c9b8  lea     edx, [r9+0Ch]
0x18002c9bc  mov     rcx, rsi
0x18002c9bf  call    StringCchCopyNWrapW
0x18002c9c4  mov     ebx, eax
0x18002c9c6  mov     [rsp+0E78h+var_E38], eax
0x18002c9ca  test    eax, eax
0x18002c9cc  jnz     loc_18002CBE7
0x18002c9d2  lea     rcx, pszNullModemId; "PNPC031"
0x18002c9d9  call    cs:__imp_lstrlenW
0x18002c9df  movsxd  rcx, eax
0x18002c9e2  xor     eax, eax
0x18002c9e4  mov     [rsi+rcx*2+2], ax
0x18002c9e9  mov     dword ptr [rsp+0E78h+hwndParent], 14h; PropertyBufferSize
0x18002c9f1  mov     r9, rsi; PropertyBuffer
0x18002c9f4  lea     r8d, [rbx+1]; Property
0x18002c9f8  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x18002ca00  mov     rcx, rdi; DeviceInfoSet
0x18002ca03  call    cs:__imp_SetupDiSetDeviceRegistryPropertyW
0x18002ca09  test    eax, eax
0x18002ca0b  jnz     short loc_18002CA1E
0x18002ca0d  call    cs:__imp_GetLastError
0x18002ca13  mov     ebx, eax
0x18002ca15  mov     [rsp+0E78h+var_E38], eax
0x18002ca19  jmp     loc_18002CBE7
0x18002ca1e  mov     [rsp+0E78h+DeviceInstallParams.cbSize], 248h
0x18002ca29  lea     r8, [rsp+0E78h+DeviceInstallParams]; DeviceInstallParams
0x18002ca31  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x18002ca39  mov     rcx, rdi; DeviceInfoSet
0x18002ca3c  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x18002ca42  test    eax, eax
0x18002ca44  jz      short loc_18002CA0D
0x18002ca46  mov     r9d, 0Dh
0x18002ca4c  lea     r8, pszNullModemInfFile; "mdmhayes.inf"
0x18002ca53  mov     edx, 104h
0x18002ca58  lea     rcx, [rsp+0E78h+DeviceInstallParams.DriverPath]
0x18002ca60  call    StringCchCopyNWrapW
0x18002ca65  mov     ebx, eax
0x18002ca67  mov     [rsp+0E78h+var_E38], eax
0x18002ca6b  test    eax, eax
0x18002ca6d  jnz     loc_18002CBE7
0x18002ca73  bts     [rsp+0E78h+DeviceInstallParams.Flags], 10h
0x18002ca7c  lea     r8, [rsp+0E78h+DeviceInstallParams]; DeviceInstallParams
0x18002ca84  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x18002ca8c  mov     rcx, rdi; DeviceInfoSet
0x18002ca8f  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x18002ca95  test    eax, eax
0x18002ca97  jz      loc_18002CA0D
0x18002ca9d  mov     ebx, 2
0x18002caa2  mov     r8d, ebx; DriverType
0x18002caa5  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x18002caad  mov     rcx, rdi; DeviceInfoSet
0x18002cab0  call    cs:__imp_SetupDiBuildDriverInfoList
0x18002cab6  test    eax, eax
0x18002cab8  jz      loc_18002CA0D
0x18002cabe  xor     edx, edx; Val
0x18002cac0  mov     r8d, 620h; Size
0x18002cac6  lea     rcx, [rsp+0E78h+DriverInfoData]; void *
0x18002cace  call    memset_0
0x18002cad3  mov     [rsp+0E78h+DriverInfoData.cbSize], 620h
0x18002cade  lea     rax, [rsp+0E78h+DriverInfoData]
0x18002cae6  mov     [rsp+0E78h+hwndParent], rax; DriverInfoData
0x18002caeb  xor     r9d, r9d; MemberIndex
0x18002caee  mov     r8d, ebx; DriverType
0x18002caf1  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x18002caf9  mov     rcx, rdi; DeviceInfoSet
0x18002cafc  call    cs:__imp_SetupDiEnumDriverInfoW
0x18002cb02  test    eax, eax
0x18002cb04  jz      loc_18002CA0D
0x18002cb0a  lea     r8, [rsp+0E78h+DriverInfoData]; DriverInfoData
0x18002cb12  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x18002cb1a  mov     rcx, rdi; DeviceInfoSet
0x18002cb1d  call    cs:__imp_SetupDiSetSelectedDriverW
0x18002cb23  test    eax, eax
0x18002cb25  jz      loc_18002C981
0x18002cb2b  mov     [rsp+0E78h+var_AB0], ebx
0x18002cb32  mov     r8, r14
0x18002cb35  lea     edx, [rbx+1Eh]
0x18002cb38  lea     rcx, [rsp+0E78h+var_AAC]
0x18002cb40  call    StringCchCopyWrapW
0x18002cb45  mov     ebx, eax
0x18002cb47  mov     [rsp+0E78h+var_E38], eax
0x18002cb4b  test    eax, eax
0x18002cb4d  jnz     loc_18002CBE7
0x18002cb53  xor     edx, edx; Val
0x18002cb55  mov     r8d, 0D0h; Size
0x18002cb5b  lea     rcx, [rsp+0E78h+ClassInstallParams]; void *
0x18002cb60  call    memset_0
0x18002cb65  mov     [rsp+0E78h+ClassInstallParams.cbSize], 8
0x18002cb6d  lea     r14d, [rbx+10h]
0x18002cb71  mov     [rsp+0E78h+ClassInstallParams.InstallFunction], r14d
0x18002cb76  mov     [rsp+0E78h+var_D50], 0
0x18002cb82  lea     rax, [rsp+0E78h+var_AC8]
0x18002cb8a  mov     [rsp+0E78h+var_D58], rax
0x18002cb92  mov     r9d, 0D0h; ClassInstallParamsSize
0x18002cb98  lea     r8, [rsp+0E78h+ClassInstallParams]; ClassInstallParams
0x18002cb9d  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x18002cba5  mov     rcx, rdi; DeviceInfoSet
0x18002cba8  call    cs:__imp_SetupDiSetClassInstallParamsW
0x18002cbae  test    eax, eax
0x18002cbb0  jz      loc_18002CA0D
0x18002cbb6  lea     r8, [rsp+0E78h+var_D48]; DeviceInfoData
0x18002cbbe  mov     rdx, rdi; DeviceInfoSet
0x18002cbc1  mov     ecx, r14d; InstallFunction
0x18002cbc4  call    cs:__imp_SetupDiCallClassInstaller
0x18002cbca  test    eax, eax
0x18002cbcc  jz      loc_18002CA0D
0x18002cbd2  lea     r8, [rsp+0E78h+var_D48]; DeviceInfoData
0x18002cbda  mov     rdx, rdi; DeviceInfoSet
0x18002cbdd  lea     ecx, [rbx+11h]; InstallFunction
0x18002cbe0  call    cs:__imp_SetupDiCallClassInstaller
0x18002cbe6  nop
0x18002cbe7  mov     rcx, rdi; DeviceInfoSet
0x18002cbea  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18002cbf0  test    rsi, rsi
0x18002cbf3  jz      short loc_18002CBFE
0x18002cbf5  mov     rcx, rsi; hMem
0x18002cbf8  call    cs:__imp_LocalFree
0x18002cbfe  mov     eax, ebx
0x18002cc00  jmp     loc_18002C91C
0x18002f93f  push    rbp
0x18002f941  sub     rsp, 40h
0x18002f945  mov     rbp, rdx
0x18002f948  mov     rcx, [rbp+50h]; DeviceInfoSet
0x18002f94c  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18002f952  mov     rcx, [rbp+48h]; hMem
0x18002f956  test    rcx, rcx
0x18002f959  jz      short loc_18002F962
0x18002f95b  call    cs:__imp_LocalFree
0x18002f961  nop
0x18002f962  add     rsp, 40h
0x18002f966  pop     rbp
0x18002f967  retn
```
