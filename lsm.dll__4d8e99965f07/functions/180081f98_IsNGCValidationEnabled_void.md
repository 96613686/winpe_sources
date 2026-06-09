# IsNGCValidationEnabled(void)

- ea: `0x180081f98`
- end: `0x180082299`
- name: `?IsNGCValidationEnabled@@YAHXZ`
- size: `769`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800822f0`

## callees

- `0x18002701c`
- `0x18002772c`
- `0x180081f98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081fe0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008204d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180081fe0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18008204d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800820c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008212c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180082198`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800821f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800820c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18008212c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180082198`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800821f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180082243`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180082258`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180082243`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180082258`

## string_xrefs

- `0x180081fc4`: `SOFTWARE\Microsoft\RDInfraAgent`
- `0x180082009`: `Failed to find RDInfraAgent key for NGC validation`
- `0x18008203d`: `SOFTWARE\WOW6432Node\Microsoft\RDInfraAgent`
- `0x18008207a`: `Failed to find 32 RDInfraAgent key for NGC validation`

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
  char *v9; // rdx
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
      if ( (unsigned int)dword_1800DF020 <= 5 )
        goto LABEL_24;
      v8 = "IsNGCValidationEnabled returning true via automatic key";
      v9 = &byte_1800CD147;
    }
    else
    {
      if ( (unsigned int)dword_1800DF020 <= 5 )
        goto LABEL_24;
      v8 = "IsNGCValidationEnabled returning true via manual key";
      v9 = byte_1800CD16D;
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
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    LODWORD(v15) = v0;
    v12[0] = "Failed to find RDInfraAgent key for NGC validation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DF020,
      (unsigned int)byte_1800CD193,
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
      if ( (unsigned int)dword_1800DF020 > 5 )
      {
        v8 = "IsNGCValidationEnabled returning true via automatic key 32 bit";
        v9 = (char *)&unk_1800CD0D0;
        goto LABEL_23;
      }
    }
    else if ( (unsigned int)dword_1800DF020 > 5 )
    {
      v8 = "IsNGCValidationEnabled returning true via manual key 32 bit";
      v9 = (char *)&word_1800CD0F6;
      goto LABEL_23;
    }
LABEL_24:
    v3 = 1;
    goto LABEL_25;
  }
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    LODWORD(v15) = v4;
    v12[0] = "Failed to find 32 RDInfraAgent key for NGC validation";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      dword_1800DF020,
      (unsigned int)&dword_1800CD11C,
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
  if ( (unsigned int)dword_1800DF020 > 5 )
  {
    v15 = "IsNGCValidationEnabled returning false, both auto/manual keys (64/32bit) appear to be off";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      dword_1800DF020,
      (unsigned int)word_1800CD0AA,
      v5,
      v6,
      (__int64)&v15);
  }
  return v3;
}

```

## disassembly

```asm
0x180081f98  push    rbp
0x180081f9a  push    rbx
0x180081f9b  mov     rbp, rsp
0x180081f9e  sub     rsp, 48h
0x180081fa2  lea     rax, [rbp+hKey]
0x180081fa6  mov     [rbp+hKey], 0
0x180081fae  mov     r9d, 20019h; samDesired
0x180081fb4  mov     [rsp+48h+phkResult], rax; phkResult
0x180081fb9  xor     r8d, r8d; ulOptions
0x180081fbc  mov     [rbp+var_18], 0
0x180081fc4  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\RDInfraAgent"
0x180081fcb  mov     [rbp+cbData], 4
0x180081fd2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081fd9  mov     [rbp+Data], 0
0x180081fe0  call    cs:__imp_RegOpenKeyExW
0x180081fe7  nop     dword ptr [rax+rax+00h]
0x180081fec  test    eax, eax
0x180081fee  jns     loc_1800820A1
0x180081ff4  mov     ecx, cs:dword_1800DF020
0x180081ffa  cmp     ecx, 5
0x180081ffd  jbe     short loc_18008202B
0x180081fff  mov     dword ptr [rbp+arg_10], eax
0x180082002  lea     rdx, byte_1800CD193
0x180082009  lea     rax, aFailedToFindRd; "Failed to find RDInfraAgent key for NGC"...
0x180082010  mov     [rbp+var_10], rax
0x180082014  lea     rax, [rbp+arg_10]
0x180082018  mov     [rsp+48h+lpcbData], rax
0x18008201d  lea     rax, [rbp+var_10]
0x180082021  mov     [rsp+48h+phkResult], rax
0x180082026  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008202b  lea     rax, [rbp+var_18]
0x18008202f  mov     r9d, 20019h; samDesired
0x180082035  xor     r8d, r8d; ulOptions
0x180082038  mov     [rsp+48h+phkResult], rax; phkResult
0x18008203d  lea     rdx, aSoftwareWow643; "SOFTWARE\\WOW6432Node\\Microsoft\\RDInf"...
0x180082044  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18008204b  xor     ebx, ebx
0x18008204d  call    cs:__imp_RegOpenKeyExW
0x180082054  nop     dword ptr [rax+rax+00h]
0x180082059  test    eax, eax
0x18008205b  jns     loc_18008216B
0x180082061  mov     ecx, cs:dword_1800DF020
0x180082067  cmp     ecx, 5
0x18008206a  jbe     loc_18008223A
0x180082070  mov     dword ptr [rbp+arg_10], eax
0x180082073  lea     rdx, dword_1800CD11C
0x18008207a  lea     rax, aFailedToFind32; "Failed to find 32 RDInfraAgent key for "...
0x180082081  mov     [rbp+var_10], rax
0x180082085  lea     rax, [rbp+arg_10]
0x180082089  mov     [rsp+48h+lpcbData], rax
0x18008208e  lea     rax, [rbp+var_10]
0x180082092  mov     [rsp+48h+phkResult], rax
0x180082097  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18008209c  jmp     loc_18008223A
0x1800820a1  mov     rcx, [rbp+hKey]; hKey
0x1800820a5  lea     rax, [rbp+cbData]
0x1800820a9  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800820ae  lea     rdx, aSsocertversion_0; "SSOCertVersion"
0x1800820b5  lea     rax, [rbp+Data]
0x1800820b9  xor     r9d, r9d; lpType
0x1800820bc  xor     r8d, r8d; lpReserved
0x1800820bf  mov     [rsp+48h+phkResult], rax; lpData
0x1800820c4  call    cs:__imp_RegQueryValueExW
0x1800820cb  nop     dword ptr [rax+rax+00h]
0x1800820d0  test    eax, eax
0x1800820d2  jnz     short loc_1800820FB
0x1800820d4  cmp     [rbp+Data], eax
0x1800820d7  jbe     short loc_1800820FB
0x1800820d9  mov     eax, cs:dword_1800DF020
0x1800820df  cmp     eax, 5
0x1800820e2  jbe     loc_180082235
0x1800820e8  lea     rax, aIsngcvalidatio_1; "IsNGCValidationEnabled returning true v"...
0x1800820ef  lea     rdx, byte_1800CD16D
0x1800820f6  jmp     loc_180082223
0x1800820fb  mov     rcx, [rbp+hKey]; hKey
0x1800820ff  lea     rax, [rbp+cbData]
0x180082103  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180082108  lea     rdx, aSsocertversion; "SSOCertVersionFeatureFlag"
0x18008210f  lea     rax, [rbp+Data]
0x180082113  mov     [rbp+Data], 0
0x18008211a  xor     r9d, r9d; lpType
0x18008211d  mov     [rsp+48h+phkResult], rax; lpData
0x180082122  xor     r8d, r8d; lpReserved
0x180082125  mov     [rbp+cbData], 4
0x18008212c  call    cs:__imp_RegQueryValueExW
0x180082133  nop     dword ptr [rax+rax+00h]
0x180082138  test    eax, eax
0x18008213a  jnz     loc_18008202B
0x180082140  cmp     [rbp+Data], eax
0x180082143  jbe     loc_18008202B
0x180082149  mov     eax, cs:dword_1800DF020
0x18008214f  cmp     eax, 5
0x180082152  jbe     loc_180082235
0x180082158  lea     rax, aIsngcvalidatio_3; "IsNGCValidationEnabled returning true v"...
0x18008215f  lea     rdx, byte_1800CD147
0x180082166  jmp     loc_180082223
0x18008216b  mov     rcx, [rbp+var_18]; hKey
0x18008216f  lea     rax, [rbp+cbData]
0x180082173  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180082178  lea     rdx, aSsocertversion_0; "SSOCertVersion"
0x18008217f  lea     rax, [rbp+Data]
0x180082183  mov     [rbp+Data], ebx
0x180082186  xor     r9d, r9d; lpType
0x180082189  mov     [rsp+48h+phkResult], rax; lpData
0x18008218e  xor     r8d, r8d; lpReserved
0x180082191  mov     [rbp+cbData], 4
0x180082198  call    cs:__imp_RegQueryValueExW
0x18008219f  nop     dword ptr [rax+rax+00h]
0x1800821a4  test    eax, eax
0x1800821a6  jnz     short loc_1800821C8
0x1800821a8  cmp     [rbp+Data], ebx
0x1800821ab  jbe     short loc_1800821C8
0x1800821ad  mov     eax, cs:dword_1800DF020
0x1800821b3  cmp     eax, 5
0x1800821b6  jbe     short loc_180082235
0x1800821b8  lea     rax, aIsngcvalidatio; "IsNGCValidationEnabled returning true v"...
0x1800821bf  lea     rdx, word_1800CD0F6
0x1800821c6  jmp     short loc_180082223
0x1800821c8  mov     rcx, [rbp+var_18]; hKey
0x1800821cc  lea     rax, [rbp+cbData]
0x1800821d0  mov     [rsp+48h+lpcbData], rax; lpcbData
0x1800821d5  lea     rdx, aSsocertversion; "SSOCertVersionFeatureFlag"
0x1800821dc  lea     rax, [rbp+Data]
0x1800821e0  mov     [rbp+Data], ebx
0x1800821e3  xor     r9d, r9d; lpType
0x1800821e6  mov     [rsp+48h+phkResult], rax; lpData
0x1800821eb  xor     r8d, r8d; lpReserved
0x1800821ee  mov     [rbp+cbData], 4
0x1800821f5  call    cs:__imp_RegQueryValueExW
0x1800821fc  nop     dword ptr [rax+rax+00h]
0x180082201  test    eax, eax
0x180082203  jnz     short loc_18008223A
0x180082205  cmp     [rbp+Data], ebx
0x180082208  jbe     short loc_18008223A
0x18008220a  mov     eax, cs:dword_1800DF020
0x180082210  cmp     eax, 5
0x180082213  jbe     short loc_180082235
0x180082215  lea     rax, aIsngcvalidatio_2; "IsNGCValidationEnabled returning true v"...
0x18008221c  lea     rdx, unk_1800CD0D0
0x180082223  mov     [rbp+arg_10], rax
0x180082227  lea     rax, [rbp+arg_10]
0x18008222b  mov     [rsp+48h+phkResult], rax
0x180082230  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180082235  mov     ebx, 1
0x18008223a  mov     rcx, [rbp+hKey]; hKey
0x18008223e  test    rcx, rcx
0x180082241  jz      short loc_18008224F
0x180082243  call    cs:__imp_RegCloseKey
0x18008224a  nop     dword ptr [rax+rax+00h]
0x18008224f  mov     rcx, [rbp+var_18]; hKey
0x180082253  test    rcx, rcx
0x180082256  jz      short loc_180082264
0x180082258  call    cs:__imp_RegCloseKey
0x18008225f  nop     dword ptr [rax+rax+00h]
0x180082264  mov     ecx, cs:dword_1800DF020
0x18008226a  cmp     ecx, 5
0x18008226d  jbe     short loc_18008228F
0x18008226f  lea     rax, aIsngcvalidatio_0; "IsNGCValidationEnabled returning false,"...
0x180082276  mov     [rbp+arg_10], rax
0x18008227a  lea     rdx, word_1800CD0AA
0x180082281  lea     rax, [rbp+arg_10]
0x180082285  mov     [rsp+48h+phkResult], rax
0x18008228a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008228f  mov     eax, ebx
0x180082291  add     rsp, 48h
0x180082295  pop     rbx
0x180082296  pop     rbp
0x180082297  retn
```
