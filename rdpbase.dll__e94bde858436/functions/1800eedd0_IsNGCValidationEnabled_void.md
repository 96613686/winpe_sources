# IsNGCValidationEnabled(void)

- ea: `0x1800eedd0`
- end: `0x1800ef0b7`
- name: `?IsNGCValidationEnabled@@YAHXZ`
- size: `743`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800f2dd8`

## callees

- `0x180002550`
- `0x180004a94`
- `0x1800eedd0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eeef9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eef5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eefc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ef018`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eeef9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eef5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800eefc1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ef018`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef075`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef066`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ef075`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eee1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eee88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eee1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800eee88`

## string_xrefs

- `0x1800eee44`: `Failed to find RDInfraAgent key for NGC validation`
- `0x1800eedfe`: `SOFTWARE\Microsoft\RDInfraAgent`
- `0x1800eeeaf`: `Failed to find 32 RDInfraAgent key for NGC validation`
- `0x1800eee78`: `SOFTWARE\WOW6432Node\Microsoft\RDInfraAgent`

## pseudocode

```c
__int64 IsNGCValidationEnabled(void)
{
  LSTATUS v0; // eax
  int v1; // r8d
  int v2; // r9d
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  int v5; // r8d
  int v6; // r9d
  const char *v7; // rax
  char *v8; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-10h] BYREF
  const char *v11; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+60h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+28h] BYREF
  const char *v14; // [rsp+70h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+38h] BYREF

  hKey = 0;
  phkResult = 0;
  cbData = 4;
  Data = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\RDInfraAgent", 0, 0x20019u, &hKey);
  if ( v0 >= 0 )
  {
    if ( RegQueryValueExW(hKey, L"SSOCertVersion", 0, 0, (LPBYTE)&Data, &cbData) || !Data )
    {
      Data = 0;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"SSOCertVersionFeatureFlag", 0, 0, (LPBYTE)&Data, &cbData) || !Data )
        goto LABEL_4;
      if ( (unsigned int)CallbackContext <= 5 )
        goto LABEL_24;
      v7 = "IsNGCValidationEnabled returning true via automatic key";
      v8 = &byte_1801C3C6F;
    }
    else
    {
      if ( (unsigned int)CallbackContext <= 5 )
        goto LABEL_24;
      v7 = "IsNGCValidationEnabled returning true via manual key";
      v8 = byte_1801C3CEB;
    }
LABEL_23:
    v14 = v7;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (_DWORD)v8,
      0,
      v6,
      (__int64)&v14);
    goto LABEL_24;
  }
  if ( (unsigned int)CallbackContext > 5 )
  {
    LODWORD(v14) = v0;
    v11 = "Failed to find RDInfraAgent key for NGC validation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)CallbackContext,
      (unsigned int)&unk_1801C3CC0,
      v1,
      v2,
      (__int64)&v11,
      (__int64)&v14);
  }
LABEL_4:
  v3 = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\WOW6432Node\\Microsoft\\RDInfraAgent", 0, 0x20019u, &phkResult);
  if ( v4 >= 0 )
  {
    Data = 0;
    cbData = 4;
    if ( RegQueryValueExW(phkResult, L"SSOCertVersion", 0, 0, (LPBYTE)&Data, &cbData) || !Data )
    {
      Data = 0;
      cbData = 4;
      if ( RegQueryValueExW(phkResult, L"SSOCertVersionFeatureFlag", 0, 0, (LPBYTE)&Data, &cbData) || !Data )
        goto LABEL_25;
      if ( (unsigned int)CallbackContext > 5 )
      {
        v7 = "IsNGCValidationEnabled returning true via automatic key 32 bit";
        v8 = byte_1801C3C49;
        goto LABEL_23;
      }
    }
    else if ( (unsigned int)CallbackContext > 5 )
    {
      v7 = "IsNGCValidationEnabled returning true via manual key 32 bit";
      v8 = byte_1801C3C23;
      goto LABEL_23;
    }
LABEL_24:
    v3 = 1;
    goto LABEL_25;
  }
  if ( (unsigned int)CallbackContext > 5 )
  {
    LODWORD(v14) = v4;
    v11 = "Failed to find 32 RDInfraAgent key for NGC validation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)CallbackContext,
      (unsigned int)byte_1801C3C95,
      v5,
      v6,
      (__int64)&v11,
      (__int64)&v14);
  }
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( (unsigned int)CallbackContext > 5 )
  {
    v14 = "IsNGCValidationEnabled returning false, both auto/manual keys (64/32bit) appear to be off";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&CallbackContext,
      (unsigned int)byte_1801C3BFD,
      0,
      v6,
      (__int64)&v14);
  }
  return v3;
}

```

## disassembly

```asm
0x1800eedd0  push    rbp
0x1800eedd2  push    rbx
0x1800eedd3  push    r14
0x1800eedd5  mov     rbp, rsp
0x1800eedd8  sub     rsp, 40h
0x1800eeddc  lea     rax, [rbp+hKey]
0x1800eede0  mov     [rbp+hKey], 0
0x1800eede8  mov     r9d, 20019h; samDesired
0x1800eedee  mov     [rsp+40h+phkResult], rax; phkResult
0x1800eedf3  xor     r8d, r8d; ulOptions
0x1800eedf6  mov     [rbp+var_10], 0
0x1800eedfe  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\RDInfraAgent"
0x1800eee05  mov     [rbp+cbData], 4
0x1800eee0c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800eee13  mov     [rbp+Data], 0
0x1800eee1a  call    cs:__imp_RegOpenKeyExW
0x1800eee20  lea     r14, CallbackContext
0x1800eee27  test    eax, eax
0x1800eee29  jns     loc_1800EEED6
0x1800eee2f  mov     ecx, cs:CallbackContext
0x1800eee35  cmp     ecx, 5
0x1800eee38  jbe     short loc_1800EEE66
0x1800eee3a  mov     dword ptr [rbp+arg_10], eax
0x1800eee3d  lea     rdx, unk_1801C3CC0
0x1800eee44  lea     rax, aFailedToFindRd; "Failed to find RDInfraAgent key for NGC"...
0x1800eee4b  mov     [rbp+var_8], rax
0x1800eee4f  lea     rax, [rbp+arg_10]
0x1800eee53  mov     [rsp+40h+lpcbData], rax
0x1800eee58  lea     rax, [rbp+var_8]
0x1800eee5c  mov     [rsp+40h+phkResult], rax
0x1800eee61  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800eee66  lea     rax, [rbp+var_10]
0x1800eee6a  mov     r9d, 20019h; samDesired
0x1800eee70  xor     r8d, r8d; ulOptions
0x1800eee73  mov     [rsp+40h+phkResult], rax; phkResult
0x1800eee78  lea     rdx, aSoftwareWow643; "SOFTWARE\\WOW6432Node\\Microsoft\\RDInf"...
0x1800eee7f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800eee86  xor     ebx, ebx
0x1800eee88  call    cs:__imp_RegOpenKeyExW
0x1800eee8e  test    eax, eax
0x1800eee90  jns     loc_1800EEF94
0x1800eee96  mov     ecx, cs:CallbackContext
0x1800eee9c  cmp     ecx, 5
0x1800eee9f  jbe     loc_1800EF05D
0x1800eeea5  mov     dword ptr [rbp+arg_10], eax
0x1800eeea8  lea     rdx, byte_1801C3C95
0x1800eeeaf  lea     rax, aFailedToFind32; "Failed to find 32 RDInfraAgent key for "...
0x1800eeeb6  mov     [rbp+var_8], rax
0x1800eeeba  lea     rax, [rbp+arg_10]
0x1800eeebe  mov     [rsp+40h+lpcbData], rax
0x1800eeec3  lea     rax, [rbp+var_8]
0x1800eeec7  mov     [rsp+40h+phkResult], rax
0x1800eeecc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800eeed1  jmp     loc_1800EF05D
0x1800eeed6  mov     rcx, [rbp+hKey]; hKey
0x1800eeeda  lea     rax, [rbp+cbData]
0x1800eeede  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800eeee3  lea     rdx, aSsocertversion_0; "SSOCertVersion"
0x1800eeeea  lea     rax, [rbp+Data]
0x1800eeeee  xor     r9d, r9d; lpType
0x1800eeef1  xor     r8d, r8d; lpReserved
0x1800eeef4  mov     [rsp+40h+phkResult], rax; lpData
0x1800eeef9  call    cs:__imp_RegQueryValueExW
0x1800eeeff  test    eax, eax
0x1800eef01  jnz     short loc_1800EEF2A
0x1800eef03  cmp     [rbp+Data], eax
0x1800eef06  jbe     short loc_1800EEF2A
0x1800eef08  mov     eax, cs:CallbackContext
0x1800eef0e  cmp     eax, 5
0x1800eef11  jbe     loc_1800EF058
0x1800eef17  lea     rax, aIsngcvalidatio_1; "IsNGCValidationEnabled returning true v"...
0x1800eef1e  lea     rdx, byte_1801C3CEB
0x1800eef25  jmp     loc_1800EF040
0x1800eef2a  mov     rcx, [rbp+hKey]; hKey
0x1800eef2e  lea     rax, [rbp+cbData]
0x1800eef32  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800eef37  lea     rdx, aSsocertversion; "SSOCertVersionFeatureFlag"
0x1800eef3e  lea     rax, [rbp+Data]
0x1800eef42  mov     [rbp+Data], 0
0x1800eef49  xor     r9d, r9d; lpType
0x1800eef4c  mov     [rsp+40h+phkResult], rax; lpData
0x1800eef51  xor     r8d, r8d; lpReserved
0x1800eef54  mov     [rbp+cbData], 4
0x1800eef5b  call    cs:__imp_RegQueryValueExW
0x1800eef61  test    eax, eax
0x1800eef63  jnz     loc_1800EEE66
0x1800eef69  cmp     [rbp+Data], eax
0x1800eef6c  jbe     loc_1800EEE66
0x1800eef72  mov     eax, cs:CallbackContext
0x1800eef78  cmp     eax, 5
0x1800eef7b  jbe     loc_1800EF058
0x1800eef81  lea     rax, aIsngcvalidatio_3; "IsNGCValidationEnabled returning true v"...
0x1800eef88  lea     rdx, byte_1801C3C6F
0x1800eef8f  jmp     loc_1800EF040
0x1800eef94  mov     rcx, [rbp+var_10]; hKey
0x1800eef98  lea     rax, [rbp+cbData]
0x1800eef9c  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800eefa1  lea     rdx, aSsocertversion_0; "SSOCertVersion"
0x1800eefa8  lea     rax, [rbp+Data]
0x1800eefac  mov     [rbp+Data], ebx
0x1800eefaf  xor     r9d, r9d; lpType
0x1800eefb2  mov     [rsp+40h+phkResult], rax; lpData
0x1800eefb7  xor     r8d, r8d; lpReserved
0x1800eefba  mov     [rbp+cbData], 4
0x1800eefc1  call    cs:__imp_RegQueryValueExW
0x1800eefc7  test    eax, eax
0x1800eefc9  jnz     short loc_1800EEFEB
0x1800eefcb  cmp     [rbp+Data], ebx
0x1800eefce  jbe     short loc_1800EEFEB
0x1800eefd0  mov     eax, cs:CallbackContext
0x1800eefd6  cmp     eax, 5
0x1800eefd9  jbe     short loc_1800EF058
0x1800eefdb  lea     rax, aIsngcvalidatio; "IsNGCValidationEnabled returning true v"...
0x1800eefe2  lea     rdx, byte_1801C3C23
0x1800eefe9  jmp     short loc_1800EF040
0x1800eefeb  mov     rcx, [rbp+var_10]; hKey
0x1800eefef  lea     rax, [rbp+cbData]
0x1800eeff3  mov     [rsp+40h+lpcbData], rax; lpcbData
0x1800eeff8  lea     rdx, aSsocertversion; "SSOCertVersionFeatureFlag"
0x1800eefff  lea     rax, [rbp+Data]
0x1800ef003  mov     [rbp+Data], ebx
0x1800ef006  xor     r9d, r9d; lpType
0x1800ef009  mov     [rsp+40h+phkResult], rax; lpData
0x1800ef00e  xor     r8d, r8d; lpReserved
0x1800ef011  mov     [rbp+cbData], 4
0x1800ef018  call    cs:__imp_RegQueryValueExW
0x1800ef01e  test    eax, eax
0x1800ef020  jnz     short loc_1800EF05D
0x1800ef022  cmp     [rbp+Data], ebx
0x1800ef025  jbe     short loc_1800EF05D
0x1800ef027  mov     eax, cs:CallbackContext
0x1800ef02d  cmp     eax, 5
0x1800ef030  jbe     short loc_1800EF058
0x1800ef032  lea     rax, aIsngcvalidatio_2; "IsNGCValidationEnabled returning true v"...
0x1800ef039  lea     rdx, byte_1801C3C49
0x1800ef040  mov     [rbp+arg_10], rax
0x1800ef044  xor     r8d, r8d
0x1800ef047  lea     rax, [rbp+arg_10]
0x1800ef04b  mov     rcx, r14
0x1800ef04e  mov     [rsp+40h+phkResult], rax
0x1800ef053  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800ef058  mov     ebx, 1
0x1800ef05d  mov     rcx, [rbp+hKey]; hKey
0x1800ef061  test    rcx, rcx
0x1800ef064  jz      short loc_1800EF06C
0x1800ef066  call    cs:__imp_RegCloseKey
0x1800ef06c  mov     rcx, [rbp+var_10]; hKey
0x1800ef070  test    rcx, rcx
0x1800ef073  jz      short loc_1800EF07B
0x1800ef075  call    cs:__imp_RegCloseKey
0x1800ef07b  mov     edx, cs:CallbackContext
0x1800ef081  cmp     edx, 5
0x1800ef084  jbe     short loc_1800EF0AC
0x1800ef086  lea     rax, aIsngcvalidatio_0; "IsNGCValidationEnabled returning false,"...
0x1800ef08d  xor     r8d, r8d
0x1800ef090  mov     [rbp+arg_10], rax
0x1800ef094  lea     rdx, byte_1801C3BFD
0x1800ef09b  lea     rax, [rbp+arg_10]
0x1800ef09f  mov     rcx, r14
0x1800ef0a2  mov     [rsp+40h+phkResult], rax
0x1800ef0a7  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800ef0ac  mov     eax, ebx
0x1800ef0ae  add     rsp, 40h
0x1800ef0b2  pop     r14
0x1800ef0b4  pop     rbx
0x1800ef0b5  pop     rbp
0x1800ef0b6  retn
```
