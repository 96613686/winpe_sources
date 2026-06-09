# MdmInstallNullModem

- ea: `0x180040f28`
- end: `0x1800412dd`
- name: `MdmInstallNullModem`
- size: `949`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x1800360b8`

## callees

- `0x18003ce28`
- `0x18003ce6c`
- `0x180040f14`
- `0x180040f28`
- `0x18004d0d2`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800412d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d5d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800412d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004d5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800410e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800410e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800410b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800410b1`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x1800411d4`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x1800411d4`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x180041188`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x180041188`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x18004129c`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800412b8`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x18004129c`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x1800412b8`
- `SETUPAPI!SetupDiSetSelectedDriverW` at `0x1800411f5`
- `SETUPAPI!SetupDiSetSelectedDriverW` at `0x1800411f5`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180041280`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180041280`
- `SETUPAPI!SetupDiSetDeviceRegistryPropertyW` at `0x1800410db`
- `SETUPAPI!SetupDiSetDeviceRegistryPropertyW` at `0x1800410db`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180041114`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180041114`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180040fdb`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180040fdb`
- `SETUPAPI!SetupDiCreateDeviceInfoW` at `0x18004104f`
- `SETUPAPI!SetupDiCreateDeviceInfoW` at `0x18004104f`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800412c2`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18004d5c9`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x1800412c2`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18004d5c9`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180041167`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180041167`

## pseudocode

```c
__int64 __fastcall MdmInstallNullModem(const wchar_t *a1)
{
  BYTE *v2; // rsi
  HDEVINFO v3; // rdi
  unsigned int LastError; // ebx
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
  wchar_t v16[554]; // [rsp+3CCh] [rbp-AACh] BYREF
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
    LastError = StringCchCopyWrapW(v16, 0x20u, a1);
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
0x180040f28  push    rbx
0x180040f2a  push    rsi
0x180040f2b  push    rdi
0x180040f2c  push    r14
0x180040f2e  sub     rsp, 0E58h
0x180040f35  mov     rax, cs:__security_cookie
0x180040f3c  xor     rax, rsp
0x180040f3f  mov     [rsp+0E78h+var_38], rax
0x180040f47  mov     r14, rcx
0x180040f4a  movups  xmm0, xmmword ptr cs:GUID_DEVCLASS_MODEM.Data1
0x180040f51  movdqu  xmmword ptr [rsp+0E78h+ClassGuid.Data1], xmm0
0x180040f5a  xorps   xmm1, xmm1
0x180040f5d  movups  xmmword ptr [rsp+0E78h+var_D48.cbSize], xmm1
0x180040f65  movups  xmmword ptr [rsp+0E78h+var_D48.ClassGuid.Data4+4], xmm1
0x180040f6d  xor     edx, edx; Val
0x180040f6f  mov     r8d, 248h; Size
0x180040f75  lea     rcx, [rsp+0E78h+DeviceInstallParams]; void *
0x180040f7d  call    memset_0
0x180040f82  xor     edx, edx; Val
0x180040f84  mov     r8d, 620h; Size
0x180040f8a  lea     rcx, [rsp+0E78h+DriverInfoData]; void *
0x180040f92  call    memset_0
0x180040f97  mov     [rsp+0E78h+var_AC8], 468h
0x180040fa3  xor     edx, edx; Val
0x180040fa5  mov     r8d, 460h; Size
0x180040fab  lea     rcx, [rsp+0E78h+var_AC0]; void *
0x180040fb3  call    memset_0
0x180040fb8  xor     edx, edx; Val
0x180040fba  mov     r8d, 0D0h; Size
0x180040fc0  lea     rcx, [rsp+0E78h+ClassInstallParams]; void *
0x180040fc5  call    memset_0
0x180040fca  xor     esi, esi
0x180040fcc  mov     [rsp+0E78h+var_E30], rsi
0x180040fd1  xor     edx, edx; hwndParent
0x180040fd3  lea     rcx, [rsp+0E78h+ClassGuid]; ClassGuid
0x180040fdb  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180040fe1  mov     rdi, rax
0x180040fe4  mov     [rsp+0E78h+var_E28], rax
0x180040fe9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180040fed  jnz     short loc_180041011
0x180040fef  mov     eax, 3EBh
0x180040ff4  mov     rcx, [rsp+0E78h+var_38]
0x180040ffc  xor     rcx, rsp; StackCookie
0x180040fff  call    __security_check_cookie
0x180041004  add     rsp, 0E58h
0x18004100b  pop     r14
0x18004100d  pop     rdi
0x18004100e  pop     rsi
0x18004100f  pop     rbx
0x180041010  retn
0x180041011  mov     [rsp+0E78h+var_D48.cbSize], 20h ; ' '
0x18004101c  lea     rax, [rsp+0E78h+var_D48]
0x180041024  mov     [rsp+0E78h+DeviceInfoData], rax; DeviceInfoData
0x180041029  mov     [rsp+0E78h+CreationFlags], 1; CreationFlags
0x180041031  mov     [rsp+0E78h+hwndParent], 0; hwndParent
0x18004103a  xor     r9d, r9d; DeviceDescription
0x18004103d  lea     r8, [rsp+0E78h+ClassGuid]; ClassGuid
0x180041045  lea     rdx, pszNullModemId; "PNPC031"
0x18004104c  mov     rcx, rdi; DeviceInfoSet
0x18004104f  call    cs:__imp_SetupDiCreateDeviceInfoW
0x180041055  test    eax, eax
0x180041057  jnz     short loc_180041067
0x180041059  mov     ebx, 3EBh
0x18004105e  mov     [rsp+0E78h+var_E38], ebx
0x180041062  jmp     loc_1800412BF
0x180041067  mov     ecx, 28h ; '('
0x18004106c  call    MdmAlloc
0x180041071  mov     rsi, rax
0x180041074  mov     [rsp+0E78h+var_E30], rax
0x180041079  test    rax, rax
0x18004107c  jnz     short loc_180041083
0x18004107e  lea     ebx, [rax+8]
0x180041081  jmp     short loc_18004105E
0x180041083  mov     r9d, 8
0x180041089  lea     r8, pszNullModemId; "PNPC031"
0x180041090  lea     edx, [r9+0Ch]
0x180041094  mov     rcx, rsi
0x180041097  call    StringCchCopyNWrapW
0x18004109c  mov     ebx, eax
0x18004109e  mov     [rsp+0E78h+var_E38], eax
0x1800410a2  test    eax, eax
0x1800410a4  jnz     loc_1800412BF
0x1800410aa  lea     rcx, pszNullModemId; "PNPC031"
0x1800410b1  call    cs:__imp_lstrlenW
0x1800410b7  movsxd  rcx, eax
0x1800410ba  xor     eax, eax
0x1800410bc  mov     [rsi+rcx*2+2], ax
0x1800410c1  mov     dword ptr [rsp+0E78h+hwndParent], 14h; PropertyBufferSize
0x1800410c9  mov     r9, rsi; PropertyBuffer
0x1800410cc  lea     r8d, [rbx+1]; Property
0x1800410d0  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x1800410d8  mov     rcx, rdi; DeviceInfoSet
0x1800410db  call    cs:__imp_SetupDiSetDeviceRegistryPropertyW
0x1800410e1  test    eax, eax
0x1800410e3  jnz     short loc_1800410F6
0x1800410e5  call    cs:__imp_GetLastError
0x1800410eb  mov     ebx, eax
0x1800410ed  mov     [rsp+0E78h+var_E38], eax
0x1800410f1  jmp     loc_1800412BF
0x1800410f6  mov     [rsp+0E78h+DeviceInstallParams.cbSize], 248h
0x180041101  lea     r8, [rsp+0E78h+DeviceInstallParams]; DeviceInstallParams
0x180041109  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x180041111  mov     rcx, rdi; DeviceInfoSet
0x180041114  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x18004111a  test    eax, eax
0x18004111c  jz      short loc_1800410E5
0x18004111e  mov     r9d, 0Dh
0x180041124  lea     r8, pszNullModemInfFile; "mdmhayes.inf"
0x18004112b  mov     edx, 104h
0x180041130  lea     rcx, [rsp+0E78h+DeviceInstallParams.DriverPath]
0x180041138  call    StringCchCopyNWrapW
0x18004113d  mov     ebx, eax
0x18004113f  mov     [rsp+0E78h+var_E38], eax
0x180041143  test    eax, eax
0x180041145  jnz     loc_1800412BF
0x18004114b  bts     [rsp+0E78h+DeviceInstallParams.Flags], 10h
0x180041154  lea     r8, [rsp+0E78h+DeviceInstallParams]; DeviceInstallParams
0x18004115c  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x180041164  mov     rcx, rdi; DeviceInfoSet
0x180041167  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x18004116d  test    eax, eax
0x18004116f  jz      loc_1800410E5
0x180041175  mov     ebx, 2
0x18004117a  mov     r8d, ebx; DriverType
0x18004117d  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x180041185  mov     rcx, rdi; DeviceInfoSet
0x180041188  call    cs:__imp_SetupDiBuildDriverInfoList
0x18004118e  test    eax, eax
0x180041190  jz      loc_1800410E5
0x180041196  xor     edx, edx; Val
0x180041198  mov     r8d, 620h; Size
0x18004119e  lea     rcx, [rsp+0E78h+DriverInfoData]; void *
0x1800411a6  call    memset_0
0x1800411ab  mov     [rsp+0E78h+DriverInfoData.cbSize], 620h
0x1800411b6  lea     rax, [rsp+0E78h+DriverInfoData]
0x1800411be  mov     [rsp+0E78h+hwndParent], rax; DriverInfoData
0x1800411c3  xor     r9d, r9d; MemberIndex
0x1800411c6  mov     r8d, ebx; DriverType
0x1800411c9  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x1800411d1  mov     rcx, rdi; DeviceInfoSet
0x1800411d4  call    cs:__imp_SetupDiEnumDriverInfoW
0x1800411da  test    eax, eax
0x1800411dc  jz      loc_1800410E5
0x1800411e2  lea     r8, [rsp+0E78h+DriverInfoData]; DriverInfoData
0x1800411ea  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x1800411f2  mov     rcx, rdi; DeviceInfoSet
0x1800411f5  call    cs:__imp_SetupDiSetSelectedDriverW
0x1800411fb  test    eax, eax
0x1800411fd  jz      loc_180041059
0x180041203  mov     [rsp+0E78h+var_AB0], ebx
0x18004120a  mov     r8, r14
0x18004120d  lea     edx, [rbx+1Eh]
0x180041210  lea     rcx, [rsp+0E78h+var_AAC]
0x180041218  call    StringCchCopyWrapW
0x18004121d  mov     ebx, eax
0x18004121f  mov     [rsp+0E78h+var_E38], eax
0x180041223  test    eax, eax
0x180041225  jnz     loc_1800412BF
0x18004122b  xor     edx, edx; Val
0x18004122d  mov     r8d, 0D0h; Size
0x180041233  lea     rcx, [rsp+0E78h+ClassInstallParams]; void *
0x180041238  call    memset_0
0x18004123d  mov     [rsp+0E78h+ClassInstallParams.cbSize], 8
0x180041245  lea     r14d, [rbx+10h]
0x180041249  mov     [rsp+0E78h+ClassInstallParams.InstallFunction], r14d
0x18004124e  mov     [rsp+0E78h+var_D50], 0
0x18004125a  lea     rax, [rsp+0E78h+var_AC8]
0x180041262  mov     [rsp+0E78h+var_D58], rax
0x18004126a  mov     r9d, 0D0h; ClassInstallParamsSize
0x180041270  lea     r8, [rsp+0E78h+ClassInstallParams]; ClassInstallParams
0x180041275  lea     rdx, [rsp+0E78h+var_D48]; DeviceInfoData
0x18004127d  mov     rcx, rdi; DeviceInfoSet
0x180041280  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180041286  test    eax, eax
0x180041288  jz      loc_1800410E5
0x18004128e  lea     r8, [rsp+0E78h+var_D48]; DeviceInfoData
0x180041296  mov     rdx, rdi; DeviceInfoSet
0x180041299  mov     ecx, r14d; InstallFunction
0x18004129c  call    cs:__imp_SetupDiCallClassInstaller
0x1800412a2  test    eax, eax
0x1800412a4  jz      loc_1800410E5
0x1800412aa  lea     r8, [rsp+0E78h+var_D48]; DeviceInfoData
0x1800412b2  mov     rdx, rdi; DeviceInfoSet
0x1800412b5  lea     ecx, [rbx+11h]; InstallFunction
0x1800412b8  call    cs:__imp_SetupDiCallClassInstaller
0x1800412be  nop
0x1800412bf  mov     rcx, rdi; DeviceInfoSet
0x1800412c2  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x1800412c8  test    rsi, rsi
0x1800412cb  jz      short loc_1800412D6
0x1800412cd  mov     rcx, rsi; hMem
0x1800412d0  call    cs:__imp_LocalFree
0x1800412d6  mov     eax, ebx
0x1800412d8  jmp     loc_180040FF4
0x18004d5bc  push    rbp
0x18004d5be  sub     rsp, 40h
0x18004d5c2  mov     rbp, rdx
0x18004d5c5  mov     rcx, [rbp+50h]; DeviceInfoSet
0x18004d5c9  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x18004d5cf  mov     rcx, [rbp+48h]; hMem
0x18004d5d3  test    rcx, rcx
0x18004d5d6  jz      short loc_18004D5DF
0x18004d5d8  call    cs:__imp_LocalFree
0x18004d5de  nop
0x18004d5df  add     rsp, 40h
0x18004d5e3  pop     rbp
0x18004d5e4  retn
```
