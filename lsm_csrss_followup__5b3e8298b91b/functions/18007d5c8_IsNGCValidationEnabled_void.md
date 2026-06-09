# IsNGCValidationEnabled(void)

- ea: `0x18007d5c8`
- end: `0x18007d898`
- name: `?IsNGCValidationEnabled@@YAHXZ`
- size: `720`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18007d8f0`

## callees

- `0x180025070`
- `0x180025890`
- `0x18007d5c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d610`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d677`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d610`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007d677`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d6e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d74a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d7b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d807`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d6e8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d74a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d7b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007d807`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d84f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d85e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d84f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007d85e`

## string_xrefs

- `0x18007d633`: `Failed to find RDInfraAgent key for NGC validation`
- `0x18007d5f4`: `SOFTWARE\Microsoft\RDInfraAgent`
- `0x18007d69e`: `Failed to find 32 RDInfraAgent key for NGC validation`
- `0x18007d667`: `SOFTWARE\WOW6432Node\Microsoft\RDInfraAgent`

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
  int v7; // ecx
  const char *v8; // rax
  __int16 *v9; // rdx
  HKEY phkResult; // [rsp+30h] [rbp-18h] BYREF
  _QWORD v12[2]; // [rsp+38h] [rbp-10h] BYREF
  int Data; // [rsp+60h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+68h] [rbp+20h] BYREF
  const char *v15; // [rsp+70h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+30h] BYREF

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
      if ( (unsigned int)dword_1800DA020 <= 5 )
        goto LABEL_24;
      v8 = "IsNGCValidationEnabled returning true via automatic key";
      v9 = (__int16 *)&dword_1800C7F94;
    }
    else
    {
      if ( (unsigned int)dword_1800DA020 <= 5 )
        goto LABEL_24;
      v8 = "IsNGCValidationEnabled returning true via manual key";
      v9 = (__int16 *)&unk_1800C8010;
    }
LABEL_23:
    v15 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      v7,
      (_DWORD)v9,
      v5,
      v6,
      (__int64)&v15);
    goto LABEL_24;
  }
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    LODWORD(v15) = v0;
    v12[0] = "Failed to find RDInfraAgent key for NGC validation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DA020,
      (unsigned int)byte_1800C7FE5,
      v1,
      v2,
      (__int64)v12,
      (__int64)&v15);
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
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        v8 = "IsNGCValidationEnabled returning true via automatic key 32 bit";
        v9 = &word_1800C7F6E;
        goto LABEL_23;
      }
    }
    else if ( (unsigned int)dword_1800DA020 > 5 )
    {
      v8 = "IsNGCValidationEnabled returning true via manual key 32 bit";
      v9 = (__int16 *)&unk_1800C7F48;
      goto LABEL_23;
    }
LABEL_24:
    v3 = 1;
    goto LABEL_25;
  }
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    LODWORD(v15) = v4;
    v12[0] = "Failed to find 32 RDInfraAgent key for NGC validation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DA020,
      (unsigned int)word_1800C7FBA,
      v5,
      v6,
      (__int64)v12,
      (__int64)&v15);
  }
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( (unsigned int)dword_1800DA020 > 5 )
  {
    v15 = "IsNGCValidationEnabled returning false, both auto/manual keys (64/32bit) appear to be off";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      dword_1800DA020,
      (unsigned int)word_1800C7F22,
      v5,
      v6,
      (__int64)&v15);
  }
  return v3;
}

```

## disassembly

```asm
0x18007d5c8  push    rbp
0x18007d5ca  push    rbx
0x18007d5cb  mov     rbp, rsp
0x18007d5ce  sub     rsp, 48h
0x18007d5d2  lea     rax, [rbp+hKey]
0x18007d5d6  mov     [rbp+hKey], 0
0x18007d5de  mov     r9d, 20019h; samDesired
0x18007d5e4  mov     [rsp+48h+phkResult], rax; phkResult
0x18007d5e9  xor     r8d, r8d; ulOptions
0x18007d5ec  mov     [rbp+var_18], 0
0x18007d5f4  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\RDInfraAgent"
0x18007d5fb  mov     [rbp+cbData], 4
0x18007d602  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d609  mov     [rbp+Data], 0
0x18007d610  call    cs:__imp_RegOpenKeyExW
0x18007d616  test    eax, eax
0x18007d618  jns     loc_18007D6C5
0x18007d61e  mov     ecx, cs:dword_1800DA020
0x18007d624  cmp     ecx, 5
0x18007d627  jbe     short loc_18007D655
0x18007d629  mov     dword ptr [rbp+arg_10], eax
0x18007d62c  lea     rdx, byte_1800C7FE5
0x18007d633  lea     rax, aFailedToFindRd; "Failed to find RDInfraAgent key for NGC"...
0x18007d63a  mov     [rbp+var_10], rax
0x18007d63e  lea     rax, [rbp+arg_10]
0x18007d642  mov     [rsp+48h+lpcbData], rax
0x18007d647  lea     rax, [rbp+var_10]
0x18007d64b  mov     [rsp+48h+phkResult], rax
0x18007d650  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007d655  lea     rax, [rbp+var_18]
0x18007d659  mov     r9d, 20019h; samDesired
0x18007d65f  xor     r8d, r8d; ulOptions
0x18007d662  mov     [rsp+48h+phkResult], rax; phkResult
0x18007d667  lea     rdx, aSoftwareWow643; "SOFTWARE\\WOW6432Node\\Microsoft\\RDInf"...
0x18007d66e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007d675  xor     ebx, ebx
0x18007d677  call    cs:__imp_RegOpenKeyExW
0x18007d67d  test    eax, eax
0x18007d67f  jns     loc_18007D783
0x18007d685  mov     ecx, cs:dword_1800DA020
0x18007d68b  cmp     ecx, 5
0x18007d68e  jbe     loc_18007D846
0x18007d694  mov     dword ptr [rbp+arg_10], eax
0x18007d697  lea     rdx, word_1800C7FBA
0x18007d69e  lea     rax, aFailedToFind32; "Failed to find 32 RDInfraAgent key for "...
0x18007d6a5  mov     [rbp+var_10], rax
0x18007d6a9  lea     rax, [rbp+arg_10]
0x18007d6ad  mov     [rsp+48h+lpcbData], rax
0x18007d6b2  lea     rax, [rbp+var_10]
0x18007d6b6  mov     [rsp+48h+phkResult], rax
0x18007d6bb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007d6c0  jmp     loc_18007D846
0x18007d6c5  mov     rcx, [rbp+hKey]; hKey
0x18007d6c9  lea     rax, [rbp+cbData]
0x18007d6cd  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18007d6d2  lea     rdx, aSsocertversion_0; "SSOCertVersion"
0x18007d6d9  lea     rax, [rbp+Data]
0x18007d6dd  xor     r9d, r9d; lpType
0x18007d6e0  xor     r8d, r8d; lpReserved
0x18007d6e3  mov     [rsp+48h+phkResult], rax; lpData
0x18007d6e8  call    cs:__imp_RegQueryValueExW
0x18007d6ee  test    eax, eax
0x18007d6f0  jnz     short loc_18007D719
0x18007d6f2  cmp     [rbp+Data], eax
0x18007d6f5  jbe     short loc_18007D719
0x18007d6f7  mov     eax, cs:dword_1800DA020
0x18007d6fd  cmp     eax, 5
0x18007d700  jbe     loc_18007D841
0x18007d706  lea     rax, aIsngcvalidatio_1; "IsNGCValidationEnabled returning true v"...
0x18007d70d  lea     rdx, unk_1800C8010
0x18007d714  jmp     loc_18007D82F
0x18007d719  mov     rcx, [rbp+hKey]; hKey
0x18007d71d  lea     rax, [rbp+cbData]
0x18007d721  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18007d726  lea     rdx, aSsocertversion; "SSOCertVersionFeatureFlag"
0x18007d72d  lea     rax, [rbp+Data]
0x18007d731  mov     [rbp+Data], 0
0x18007d738  xor     r9d, r9d; lpType
0x18007d73b  mov     [rsp+48h+phkResult], rax; lpData
0x18007d740  xor     r8d, r8d; lpReserved
0x18007d743  mov     [rbp+cbData], 4
0x18007d74a  call    cs:__imp_RegQueryValueExW
0x18007d750  test    eax, eax
0x18007d752  jnz     loc_18007D655
0x18007d758  cmp     [rbp+Data], eax
0x18007d75b  jbe     loc_18007D655
0x18007d761  mov     eax, cs:dword_1800DA020
0x18007d767  cmp     eax, 5
0x18007d76a  jbe     loc_18007D841
0x18007d770  lea     rax, aIsngcvalidatio_3; "IsNGCValidationEnabled returning true v"...
0x18007d777  lea     rdx, dword_1800C7F94
0x18007d77e  jmp     loc_18007D82F
0x18007d783  mov     rcx, [rbp+var_18]; hKey
0x18007d787  lea     rax, [rbp+cbData]
0x18007d78b  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18007d790  lea     rdx, aSsocertversion_0; "SSOCertVersion"
0x18007d797  lea     rax, [rbp+Data]
0x18007d79b  mov     [rbp+Data], ebx
0x18007d79e  xor     r9d, r9d; lpType
0x18007d7a1  mov     [rsp+48h+phkResult], rax; lpData
0x18007d7a6  xor     r8d, r8d; lpReserved
0x18007d7a9  mov     [rbp+cbData], 4
0x18007d7b0  call    cs:__imp_RegQueryValueExW
0x18007d7b6  test    eax, eax
0x18007d7b8  jnz     short loc_18007D7DA
0x18007d7ba  cmp     [rbp+Data], ebx
0x18007d7bd  jbe     short loc_18007D7DA
0x18007d7bf  mov     eax, cs:dword_1800DA020
0x18007d7c5  cmp     eax, 5
0x18007d7c8  jbe     short loc_18007D841
0x18007d7ca  lea     rax, aIsngcvalidatio; "IsNGCValidationEnabled returning true v"...
0x18007d7d1  lea     rdx, unk_1800C7F48
0x18007d7d8  jmp     short loc_18007D82F
0x18007d7da  mov     rcx, [rbp+var_18]; hKey
0x18007d7de  lea     rax, [rbp+cbData]
0x18007d7e2  mov     [rsp+48h+lpcbData], rax; lpcbData
0x18007d7e7  lea     rdx, aSsocertversion; "SSOCertVersionFeatureFlag"
0x18007d7ee  lea     rax, [rbp+Data]
0x18007d7f2  mov     [rbp+Data], ebx
0x18007d7f5  xor     r9d, r9d; lpType
0x18007d7f8  mov     [rsp+48h+phkResult], rax; lpData
0x18007d7fd  xor     r8d, r8d; lpReserved
0x18007d800  mov     [rbp+cbData], 4
0x18007d807  call    cs:__imp_RegQueryValueExW
0x18007d80d  test    eax, eax
0x18007d80f  jnz     short loc_18007D846
0x18007d811  cmp     [rbp+Data], ebx
0x18007d814  jbe     short loc_18007D846
0x18007d816  mov     eax, cs:dword_1800DA020
0x18007d81c  cmp     eax, 5
0x18007d81f  jbe     short loc_18007D841
0x18007d821  lea     rax, aIsngcvalidatio_2; "IsNGCValidationEnabled returning true v"...
0x18007d828  lea     rdx, word_1800C7F6E
0x18007d82f  mov     [rbp+arg_10], rax
0x18007d833  lea     rax, [rbp+arg_10]
0x18007d837  mov     [rsp+48h+phkResult], rax
0x18007d83c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007d841  mov     ebx, 1
0x18007d846  mov     rcx, [rbp+hKey]; hKey
0x18007d84a  test    rcx, rcx
0x18007d84d  jz      short loc_18007D855
0x18007d84f  call    cs:__imp_RegCloseKey
0x18007d855  mov     rcx, [rbp+var_18]; hKey
0x18007d859  test    rcx, rcx
0x18007d85c  jz      short loc_18007D864
0x18007d85e  call    cs:__imp_RegCloseKey
0x18007d864  mov     ecx, cs:dword_1800DA020
0x18007d86a  cmp     ecx, 5
0x18007d86d  jbe     short loc_18007D88F
0x18007d86f  lea     rax, aIsngcvalidatio_0; "IsNGCValidationEnabled returning false,"...
0x18007d876  mov     [rbp+arg_10], rax
0x18007d87a  lea     rdx, word_1800C7F22
0x18007d881  lea     rax, [rbp+arg_10]
0x18007d885  mov     [rsp+48h+phkResult], rax
0x18007d88a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18007d88f  mov     eax, ebx
0x18007d891  add     rsp, 48h
0x18007d895  pop     rbx
0x18007d896  pop     rbp
0x18007d897  retn
```
