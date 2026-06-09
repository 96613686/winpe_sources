# CleanupSignatures(void)

- ea: `0x1800fec04`
- end: `0x1800fef44`
- name: `?CleanupSignatures@@YAXXZ`
- size: `832`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x18016a080`

## callees

- `0x1800fec04`
- `0x1800ff250`
- `0x1800ff4dc`
- `0x1801999b0`
- `0x18019a654`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800fedf1`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800fedf1`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800fed6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800feedc`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800fed6d`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x1800feedc`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800feca3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800feca3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fef14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fef1f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fef14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800fef1f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800fed87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800feef5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800fed87`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800feef5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800fecee`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800fee6a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800fecee`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800fee6a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fee17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800fee17`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800fec7e`
- `api-ms-win-core-registry-l1-1-0!RegLoadAppKeyW` at `0x1800fec7e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800fed4f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800feebe`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800fed4f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800feebe`

## pseudocode

```c
void CleanupSignatures(void)
{
  int v0; // r8d
  LSTATUS v1; // eax
  signed int v2; // edi
  unsigned int v3; // eax
  LSTATUS v4; // eax
  unsigned int v5; // esi
  DWORD v6; // ebx
  LSTATUS v7; // eax
  bool v8; // sf
  __int64 v9; // rax
  unsigned __int64 Version; // rbx
  HRESULT PackageVersion; // eax
  LSTATUS v12; // eax
  bool v13; // sf
  unsigned int v14; // esi
  DWORD i; // edi
  LSTATUS v16; // eax
  bool v17; // sf
  __int64 v18; // rax
  unsigned int numKeys; // [rsp+60h] [rbp-A0h] BYREF
  PACKAGE_VERSION keyNameLen; // [rsp+68h] [rbp-98h] BYREF
  HKEY__ *appKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY__ *signatureKey; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 osVersion; // [rsp+80h] [rbp-80h] BYREF
  wchar_t osVersionBuffer[20]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t keyName[264]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t filePath[264]; // [rsp+2C0h] [rbp+1C0h] BYREF

  memset_0(filePath, 0, 0x208u);
  if ( (int)GetGEHFile((wchar_t *)L"POF.dat", filePath, v0) >= 0 )
  {
    appKey = 0;
    v1 = RegLoadAppKeyW(filePath, &appKey, 0xF003Fu, 0, 0);
    v2 = v1;
    if ( v1 > 0 )
      v2 = (unsigned __int16)v1 | 0x80070000;
    osVersion = 0;
    RtlGetDeviceFamilyInfoEnum(&osVersion, 0, 0);
    v3 = 0;
    numKeys = 0;
    if ( v2 >= 0 )
    {
      v4 = RegQueryInfoKeyW(appKey, 0, 0, 0, &numKeys, 0, 0, 0, 0, 0, 0, 0);
      v2 = v4;
      if ( v4 > 0 )
        v2 = (unsigned __int16)v4 | 0x80070000;
      v3 = numKeys;
    }
    v5 = 0;
    v6 = 0;
    if ( v3 )
    {
      do
      {
        memset_0(keyName, 0, 0x208u);
        LODWORD(keyNameLen.Version) = 260;
        v7 = RegEnumKeyExW(appKey, v6, keyName, (LPDWORD)&keyNameLen, 0, 0, 0, 0);
        v8 = v7 < 0;
        if ( v7 > 0 )
          v8 = 1;
        if ( !v8 )
        {
          v9 = _o__wcstoui64(keyName, 0, 10);
          if ( v9 )
          {
            if ( v9 != osVersion && RegDeleteTreeW(appKey, keyName) >= 0 )
              --v6;
          }
        }
        ++v5;
        ++v6;
      }
      while ( v5 < numKeys );
    }
    Version = 0;
    keyNameLen.Version = 0;
    if ( v2 >= 0 )
    {
      PackageVersion = GetPackageVersion(&keyNameLen);
      Version = keyNameLen.Version;
      v2 = PackageVersion;
    }
    signatureKey = 0;
    numKeys = 0;
    if ( v2 >= 0 )
    {
      memset(osVersionBuffer, 0, sizeof(osVersionBuffer));
      if ( (unsigned int)_o__ui64tow_s(osVersion, osVersionBuffer, 19) )
        goto LABEL_24;
      v12 = RegOpenKeyExW(appKey, osVersionBuffer, 0, 0xF003Fu, &signatureKey);
      v13 = v12 < 0;
      if ( v12 > 0 )
        v13 = 1;
      if ( !v13 )
      {
LABEL_24:
        if ( signatureKey )
          RegQueryInfoKeyW(signatureKey, 0, 0, 0, &numKeys, 0, 0, 0, 0, 0, 0, 0);
      }
    }
    v14 = 0;
    for ( i = 0; v14 < numKeys; ++i )
    {
      memset_0(keyName, 0, 0x208u);
      LODWORD(keyNameLen.Version) = 260;
      v16 = RegEnumKeyExW(signatureKey, i, keyName, (LPDWORD)&keyNameLen, 0, 0, 0, 0);
      v17 = v16 < 0;
      if ( v16 > 0 )
        v17 = 1;
      if ( !v17 )
      {
        v18 = _o__wcstoui64(keyName, 0, 10);
        if ( v18 )
        {
          if ( v18 != Version && RegDeleteTreeW(signatureKey, keyName) >= 0 )
            --i;
        }
      }
      ++v14;
    }
    RegCloseKey(signatureKey);
    RegCloseKey(appKey);
  }
}

```

## disassembly

```asm
0x1800fec04  push    rbp
0x1800fec06  push    rbx
0x1800fec07  push    rsi
0x1800fec08  push    rdi
0x1800fec09  push    r14
0x1800fec0b  push    r15
0x1800fec0d  lea     rbp, [rsp-3E8h]
0x1800fec15  sub     rsp, 4E8h
0x1800fec1c  mov     rax, cs:__security_cookie
0x1800fec23  xor     rax, rsp
0x1800fec26  mov     [rbp+410h+var_40], rax
0x1800fec2d  xor     edx, edx; Val
0x1800fec2f  lea     rcx, [rbp+410h+filePath]; void *
0x1800fec36  mov     r8d, 208h; Size
0x1800fec3c  call    memset_0
0x1800fec41  lea     rdx, [rbp+410h+filePath]; filePath
0x1800fec48  lea     rcx, aPofDat; "POF.dat"
0x1800fec4f  call    ?GetGEHFile@@YAJPEAG0H@Z; GetGEHFile(ushort *,ushort *,int)
0x1800fec54  xor     r14d, r14d
0x1800fec57  test    eax, eax
0x1800fec59  js      loc_1800FEF25
0x1800fec5f  xor     r9d, r9d; dwOptions
0x1800fec62  mov     [rsp+510h+appKey], r14
0x1800fec67  mov     r8d, 0F003Fh; samDesired
0x1800fec6d  mov     [rsp+510h+Reserved], r14d; Reserved
0x1800fec72  lea     rdx, [rsp+510h+appKey]; phkResult
0x1800fec77  lea     rcx, [rbp+410h+filePath]; lpFile
0x1800fec7e  call    cs:__imp_RegLoadAppKeyW
0x1800fec84  mov     edi, eax
0x1800fec86  mov     r15d, 80070000h
0x1800fec8c  test    eax, eax
0x1800fec8e  jle     short loc_1800FEC96
0x1800fec90  movzx   edi, ax
0x1800fec93  or      edi, r15d
0x1800fec96  xor     r8d, r8d
0x1800fec99  mov     [rbp+410h+osVersion], r14
0x1800fec9d  xor     edx, edx
0x1800fec9f  lea     rcx, [rbp+410h+osVersion]
0x1800feca3  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800feca9  mov     eax, r14d
0x1800fecac  mov     [rsp+510h+numKeys], eax
0x1800fecb0  test    edi, edi
0x1800fecb2  js      short loc_1800FED04
0x1800fecb4  mov     rcx, [rsp+510h+appKey]; hKey
0x1800fecb9  lea     rax, [rsp+510h+numKeys]
0x1800fecbe  mov     [rsp+510h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800fecc3  xor     r9d, r9d; lpReserved
0x1800fecc6  mov     [rsp+510h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800feccb  xor     r8d, r8d; lpcchClass
0x1800fecce  mov     [rsp+510h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800fecd3  xor     edx, edx; lpClass
0x1800fecd5  mov     [rsp+510h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800fecda  mov     [rsp+510h+lpcValues], r14; lpcValues
0x1800fecdf  mov     [rsp+510h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800fece4  mov     [rsp+510h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800fece9  mov     qword ptr [rsp+510h+Reserved], rax; lpcSubKeys
0x1800fecee  call    cs:__imp_RegQueryInfoKeyW
0x1800fecf4  mov     edi, eax
0x1800fecf6  test    eax, eax
0x1800fecf8  jle     short loc_1800FED00
0x1800fecfa  movzx   edi, ax
0x1800fecfd  or      edi, r15d
0x1800fed00  mov     eax, [rsp+510h+numKeys]
0x1800fed04  mov     esi, r14d
0x1800fed07  mov     ebx, r14d
0x1800fed0a  test    eax, eax
0x1800fed0c  jz      loc_1800FEDA1
0x1800fed12  xor     edx, edx; Val
0x1800fed14  lea     rcx, [rbp+410h+keyName]; void *
0x1800fed18  mov     r8d, 208h; Size
0x1800fed1e  call    memset_0
0x1800fed23  mov     rcx, [rsp+510h+appKey]; hKey
0x1800fed28  lea     r9, [rsp+510h+keyNameLen]; lpcchName
0x1800fed2d  mov     [rsp+510h+lpcValues], r14; lpftLastWriteTime
0x1800fed32  lea     r8, [rbp+410h+keyName]; lpName
0x1800fed36  mov     [rsp+510h+lpcbMaxClassLen], r14; lpcchClass
0x1800fed3b  mov     edx, ebx; dwIndex
0x1800fed3d  mov     [rsp+510h+lpcbMaxSubKeyLen], r14; lpClass
0x1800fed42  mov     qword ptr [rsp+510h+Reserved], r14; lpReserved
0x1800fed47  mov     dword ptr [rsp+510h+keyNameLen], 104h
0x1800fed4f  call    cs:__imp_RegEnumKeyExW
0x1800fed55  test    eax, eax
0x1800fed57  jle     short loc_1800FED61
0x1800fed59  movzx   eax, ax
0x1800fed5c  or      eax, r15d
0x1800fed5f  test    eax, eax
0x1800fed61  js      short loc_1800FED93
0x1800fed63  xor     edx, edx
0x1800fed65  lea     rcx, [rbp+410h+keyName]
0x1800fed69  lea     r8d, [rdx+0Ah]
0x1800fed6d  call    cs:__imp__o__wcstoui64
0x1800fed73  test    rax, rax
0x1800fed76  jz      short loc_1800FED93
0x1800fed78  cmp     rax, [rbp+410h+osVersion]
0x1800fed7c  jz      short loc_1800FED93
0x1800fed7e  mov     rcx, [rsp+510h+appKey]; hKey
0x1800fed83  lea     rdx, [rbp+410h+keyName]; lpSubKey
0x1800fed87  call    cs:__imp_RegDeleteTreeW
0x1800fed8d  test    eax, eax
0x1800fed8f  js      short loc_1800FED93
0x1800fed91  dec     ebx
0x1800fed93  inc     esi
0x1800fed95  inc     ebx
0x1800fed97  cmp     esi, [rsp+510h+numKeys]
0x1800fed9b  jb      loc_1800FED12
0x1800feda1  mov     rbx, r14
0x1800feda4  mov     [rsp+510h+keyNameLen], rbx
0x1800feda9  test    edi, edi
0x1800fedab  js      short loc_1800FEDBE
0x1800fedad  lea     rcx, [rsp+510h+keyNameLen]; packageVersion
0x1800fedb2  call    ?GetPackageVersion@@YAJPEAUPACKAGE_VERSION@@@Z; GetPackageVersion(PACKAGE_VERSION *)
0x1800fedb7  mov     rbx, [rsp+510h+keyNameLen]
0x1800fedbc  mov     edi, eax
0x1800fedbe  mov     [rsp+510h+signatureKey], r14
0x1800fedc3  mov     [rsp+510h+numKeys], r14d
0x1800fedc8  test    edi, edi
0x1800fedca  js      loc_1800FEE70
0x1800fedd0  mov     rcx, [rbp+410h+osVersion]
0x1800fedd4  lea     rdx, [rbp+410h+osVersionBuffer]
0x1800fedd8  xor     eax, eax
0x1800fedda  xorps   xmm0, xmm0
0x1800feddd  movups  xmmword ptr [rbp+410h+osVersionBuffer], xmm0
0x1800fede1  mov     qword ptr [rbp+410h+osVersionBuffer+20h], rax
0x1800fede5  movups  xmmword ptr [rbp+410h+osVersionBuffer+10h], xmm0
0x1800fede9  lea     r9d, [rax+0Ah]
0x1800feded  lea     r8d, [rax+13h]
0x1800fedf1  call    cs:__imp__o__ui64tow_s
0x1800fedf7  test    eax, eax
0x1800fedf9  jnz     short loc_1800FEE2B
0x1800fedfb  mov     rcx, [rsp+510h+appKey]; hKey
0x1800fee00  lea     rax, [rsp+510h+signatureKey]
0x1800fee05  mov     r9d, 0F003Fh; samDesired
0x1800fee0b  mov     qword ptr [rsp+510h+Reserved], rax; phkResult
0x1800fee10  xor     r8d, r8d; ulOptions
0x1800fee13  lea     rdx, [rbp+410h+osVersionBuffer]; lpSubKey
0x1800fee17  call    cs:__imp_RegOpenKeyExW
0x1800fee1d  test    eax, eax
0x1800fee1f  jle     short loc_1800FEE29
0x1800fee21  movzx   eax, ax
0x1800fee24  or      eax, r15d
0x1800fee27  test    eax, eax
0x1800fee29  js      short loc_1800FEE70
0x1800fee2b  mov     rcx, [rsp+510h+signatureKey]; hKey
0x1800fee30  test    rcx, rcx
0x1800fee33  jz      short loc_1800FEE70
0x1800fee35  mov     [rsp+510h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800fee3a  lea     rax, [rsp+510h+numKeys]
0x1800fee3f  mov     [rsp+510h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800fee44  xor     r9d, r9d; lpReserved
0x1800fee47  mov     [rsp+510h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800fee4c  xor     r8d, r8d; lpcchClass
0x1800fee4f  mov     [rsp+510h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800fee54  xor     edx, edx; lpClass
0x1800fee56  mov     [rsp+510h+lpcValues], r14; lpcValues
0x1800fee5b  mov     [rsp+510h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800fee60  mov     [rsp+510h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800fee65  mov     qword ptr [rsp+510h+Reserved], rax; lpcSubKeys
0x1800fee6a  call    cs:__imp_RegQueryInfoKeyW
0x1800fee70  mov     esi, r14d
0x1800fee73  mov     edi, r14d
0x1800fee76  cmp     [rsp+510h+numKeys], r14d
0x1800fee7b  jbe     loc_1800FEF0F
0x1800fee81  xor     edx, edx; Val
0x1800fee83  lea     rcx, [rbp+410h+keyName]; void *
0x1800fee87  mov     r8d, 208h; Size
0x1800fee8d  call    memset_0
0x1800fee92  mov     rcx, [rsp+510h+signatureKey]; hKey
0x1800fee97  lea     r9, [rsp+510h+keyNameLen]; lpcchName
0x1800fee9c  mov     [rsp+510h+lpcValues], r14; lpftLastWriteTime
0x1800feea1  lea     r8, [rbp+410h+keyName]; lpName
0x1800feea5  mov     [rsp+510h+lpcbMaxClassLen], r14; lpcchClass
0x1800feeaa  mov     edx, edi; dwIndex
0x1800feeac  mov     [rsp+510h+lpcbMaxSubKeyLen], r14; lpClass
0x1800feeb1  mov     qword ptr [rsp+510h+Reserved], r14; lpReserved
0x1800feeb6  mov     dword ptr [rsp+510h+keyNameLen], 104h
0x1800feebe  call    cs:__imp_RegEnumKeyExW
0x1800feec4  test    eax, eax
0x1800feec6  jle     short loc_1800FEED0
0x1800feec8  movzx   eax, ax
0x1800feecb  or      eax, r15d
0x1800feece  test    eax, eax
0x1800feed0  js      short loc_1800FEF01
0x1800feed2  xor     edx, edx
0x1800feed4  lea     rcx, [rbp+410h+keyName]
0x1800feed8  lea     r8d, [rdx+0Ah]
0x1800feedc  call    cs:__imp__o__wcstoui64
0x1800feee2  test    rax, rax
0x1800feee5  jz      short loc_1800FEF01
0x1800feee7  cmp     rax, rbx
0x1800feeea  jz      short loc_1800FEF01
0x1800feeec  mov     rcx, [rsp+510h+signatureKey]; hKey
0x1800feef1  lea     rdx, [rbp+410h+keyName]; lpSubKey
0x1800feef5  call    cs:__imp_RegDeleteTreeW
0x1800feefb  test    eax, eax
0x1800feefd  js      short loc_1800FEF01
0x1800feeff  dec     edi
0x1800fef01  inc     esi
0x1800fef03  inc     edi
0x1800fef05  cmp     esi, [rsp+510h+numKeys]
0x1800fef09  jb      loc_1800FEE81
0x1800fef0f  mov     rcx, [rsp+510h+signatureKey]; hKey
0x1800fef14  call    cs:__imp_RegCloseKey
0x1800fef1a  mov     rcx, [rsp+510h+appKey]; hKey
0x1800fef1f  call    cs:__imp_RegCloseKey
0x1800fef25  mov     rcx, [rbp+410h+var_40]
0x1800fef2c  xor     rcx, rsp; StackCookie
0x1800fef2f  call    __security_check_cookie
0x1800fef34  add     rsp, 4E8h
0x1800fef3b  pop     r15
0x1800fef3d  pop     r14
0x1800fef3f  pop     rdi
0x1800fef40  pop     rsi
0x1800fef41  pop     rbx
0x1800fef42  pop     rbp
0x1800fef43  retn
```
