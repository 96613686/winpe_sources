# NlInitialize

- ea: `0x18003ec48`
- end: `0x18003ef22`
- name: `NlInitialize`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032230`

## callees

- `0x18002ee7c`
- `0x18002f014`
- `0x18003ec48`
- `0x180043e64`
- `0x18006d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ed7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003ed4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18003ed4a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003eeee`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18003eeee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ee27`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003ee27`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eddc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eddc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee34`
- `ntdll!RtlInitializeResource` at `0x18003eed5`
- `ntdll!RtlInitializeResource` at `0x18003eefb`
- `ntdll!RtlInitializeResource` at `0x18003eed5`
- `ntdll!RtlInitializeResource` at `0x18003eefb`
- `ntdll!RtlGetNtProductType` at `0x18003ee67`
- `ntdll!RtlGetNtProductType` at `0x18003ee67`
- `ntdll!RtlInitUnicodeString` at `0x18003ec90`
- `ntdll!RtlInitUnicodeString` at `0x18003ece2`
- `ntdll!RtlInitUnicodeString` at `0x18003ed0e`
- `ntdll!RtlInitUnicodeString` at `0x18003ee59`
- `ntdll!RtlInitUnicodeString` at `0x18003ec90`
- `ntdll!RtlInitUnicodeString` at `0x18003ece2`
- `ntdll!RtlInitUnicodeString` at `0x18003ed0e`
- `ntdll!RtlInitUnicodeString` at `0x18003ee59`
- `CRYPTSP!SystemFunction007` at `0x18003ecf4`
- `CRYPTSP!SystemFunction007` at `0x18003ecf4`
- `CRYPTSP!SystemFunction006` at `0x18003eccf`
- `CRYPTSP!SystemFunction006` at `0x18003eccf`

## pseudocode

```c
__int64 NlInitialize()
{
  int v0; // ebx
  WCHAR *v2; // rax
  const WCHAR *v3; // rdi
  DWORD LastError; // eax
  LSTATUS v5; // ebx
  DWORD Type; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  int Data; // [rsp+80h] [rbp+8h] BYREF
  enum _NT_PRODUCT_TYPE ProductType; // [rsp+88h] [rbp+10h] BYREF
  DWORD nSize; // [rsp+90h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+20h] BYREF

  nSize = 16;
  ProductType = 0;
  hKey = 0;
  cbData = 0;
  Type = 0;
  Data = 0;
  NlpEnumerationHandle = 0;
  NlpLogonAttemptCount = 0;
  NlpComputerName.Buffer = 0;
  RtlInitUnicodeString(&NlpPrimaryDomainName, 0);
  NlpSamDomainName.Buffer = 0;
  NlpSamDomainId = 0;
  NlpSamDomainHandle = 0;
  NlpSamLocalDomainId = 0;
  NlpSamLocalDomainHandle = 0;
  DestinationString = 0;
  v0 = SystemFunction006(byte_180072560, NlpNullLmOwfPassword);
  if ( v0 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, 0);
    v0 = SystemFunction007(&DestinationString, &NlpNullNtOwfPassword);
    if ( v0 >= 0 )
      RtlInitUnicodeString(&NlpGMSAPwd, L"_SA_{262E99C9-6160-4871-ACEC-4E61736B6F21}");
  }
  if ( v0 < 0 )
    return (unsigned int)v0;
  v2 = (WCHAR *)((__int64 (__fastcall *)(__int64))qword_180088390)(2LL * nSize);
  v3 = v2;
  if ( v2 && GetComputerNameExW(ComputerNameNetBIOS, v2, &nSize) )
  {
    NlpLanmanInstalled = 1;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids, LastError);
    }
    NlpLanmanInstalled = 0;
    ((void (__fastcall *)(const WCHAR *))qword_180088398)(v3);
    v3 = 0;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SafeBoot\\Option", 0, 0x20019u, &hKey) )
  {
    Data = 0;
    cbData = 4;
    v5 = RegQueryValueExW(hKey, L"OptionValue", 0, &Type, (LPBYTE)&Data, &cbData);
    RegCloseKey(hKey);
    if ( !v5 && Data == 1 )
      NlpLanmanInstalled = 0;
  }
  RtlInitUnicodeString(&NlpComputerName, v3);
  if ( !RtlGetNtProductType(&ProductType) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids);
    ProductType = NtProductWinNt;
  }
  NlpWorkstation = ProductType != NtProductLanManNt;
  qword_180086FB0 = (__int64)&NlpActiveLogonListAnchor;
  NlpActiveLogonListAnchor = (__int64)&NlpActiveLogonListAnchor;
  NlpActiveLogonTable = 0;
  RtlInitializeResource(&NlpActiveLogonLock);
  NlpCacheInitialize();
  LoadLibraryExA("netlogon", 0, 0);
  RtlInitializeResource(&SubAuthenticationCritSect);
  qword_18008A908 = (__int64)&SubAuthenticationDlls;
  SubAuthenticationDlls = (__int64)&SubAuthenticationDlls;
  return 0;
}

```

## disassembly

```asm
0x18003ec48  mov     rax, rsp
0x18003ec4b  push    rbx
0x18003ec4c  push    rsi
0x18003ec4d  push    rdi
0x18003ec4e  push    r14
0x18003ec50  sub     rsp, 58h
0x18003ec54  mov     dword ptr [rax+18h], 10h
0x18003ec5b  xor     r14d, r14d
0x18003ec5e  mov     [rax+10h], r14d
0x18003ec62  mov     [rax-40h], r14
0x18003ec66  mov     [rax+20h], r14d
0x18003ec6a  mov     [rax-48h], r14d
0x18003ec6e  mov     [rax+8], r14d
0x18003ec72  mov     cs:NlpEnumerationHandle, r14d
0x18003ec79  mov     cs:NlpLogonAttemptCount, r14d
0x18003ec80  mov     cs:NlpComputerName.Buffer, r14
0x18003ec87  xor     edx, edx; SourceString
0x18003ec89  lea     rcx, NlpPrimaryDomainName; DestinationString
0x18003ec90  call    cs:__imp_RtlInitUnicodeString
0x18003ec96  mov     cs:NlpSamDomainName.Buffer, r14
0x18003ec9d  mov     cs:NlpSamDomainId, r14
0x18003eca4  mov     cs:NlpSamDomainHandle, r14
0x18003ecab  mov     cs:NlpSamLocalDomainId, r14
0x18003ecb2  mov     cs:NlpSamLocalDomainHandle, r14
0x18003ecb9  xorps   xmm0, xmm0
0x18003ecbc  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x18003ecc1  lea     rdx, NlpNullLmOwfPassword
0x18003ecc8  lea     rcx, byte_180072560
0x18003eccf  call    cs:__imp_SystemFunction006
0x18003ecd5  mov     ebx, eax
0x18003ecd7  test    eax, eax
0x18003ecd9  js      short loc_18003ED14
0x18003ecdb  xor     edx, edx; SourceString
0x18003ecdd  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x18003ece2  call    cs:__imp_RtlInitUnicodeString
0x18003ece8  lea     rdx, NlpNullNtOwfPassword
0x18003ecef  lea     rcx, [rsp+78h+DestinationString]
0x18003ecf4  call    cs:__imp_SystemFunction007
0x18003ecfa  mov     ebx, eax
0x18003ecfc  test    eax, eax
0x18003ecfe  js      short loc_18003ED14
0x18003ed00  lea     rdx, aSa262e99c96160; "_SA_{262E99C9-6160-4871-ACEC-4E61736B6F"...
0x18003ed07  lea     rcx, NlpGMSAPwd; DestinationString
0x18003ed0e  call    cs:__imp_RtlInitUnicodeString
0x18003ed14  test    ebx, ebx
0x18003ed16  jns     short loc_18003ED1F
0x18003ed18  mov     eax, ebx
0x18003ed1a  jmp     loc_18003EF18
0x18003ed1f  mov     ecx, [rsp+78h+nSize]
0x18003ed26  add     rcx, rcx
0x18003ed29  mov     rax, cs:qword_180088390
0x18003ed30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed35  mov     rdi, rax
0x18003ed38  test    rax, rax
0x18003ed3b  jz      short loc_18003ED64
0x18003ed3d  lea     r8, [rsp+78h+nSize]; nSize
0x18003ed45  mov     rdx, rax; lpBuffer
0x18003ed48  xor     ecx, ecx; NameType
0x18003ed4a  call    cs:__imp_GetComputerNameExW
0x18003ed50  test    eax, eax
0x18003ed52  jz      short loc_18003ED64
0x18003ed54  mov     cs:NlpLanmanInstalled, 1
0x18003ed5b  lea     rsi, WPP_GLOBAL_Control
0x18003ed62  jmp     short loc_18003EDBB
0x18003ed64  lea     rsi, WPP_GLOBAL_Control
0x18003ed6b  mov     rax, cs:WPP_GLOBAL_Control
0x18003ed72  cmp     rax, rsi
0x18003ed75  jz      short loc_18003EDA2
0x18003ed77  test    byte ptr [rax+1Ch], 8
0x18003ed7b  jz      short loc_18003EDA2
0x18003ed7d  call    cs:__imp_GetLastError
0x18003ed83  mov     edx, 0Ah
0x18003ed88  mov     r9d, eax
0x18003ed8b  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003ed92  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ed99  mov     rcx, [rcx+10h]
0x18003ed9d  call    WPP_SF_d
0x18003eda2  mov     cs:NlpLanmanInstalled, r14b
0x18003eda9  mov     rcx, rdi
0x18003edac  mov     rax, cs:qword_180088398
0x18003edb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edb8  mov     rdi, r14
0x18003edbb  lea     rax, [rsp+78h+hKey]
0x18003edc0  mov     [rsp+78h+phkResult], rax; phkResult
0x18003edc5  mov     r9d, 20019h; samDesired
0x18003edcb  xor     r8d, r8d; ulOptions
0x18003edce  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Saf"...
0x18003edd5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003eddc  call    cs:__imp_RegOpenKeyExW
0x18003ede2  test    eax, eax
0x18003ede4  jnz     short loc_18003EE4F
0x18003ede6  mov     [rsp+78h+Data], r14d
0x18003edee  mov     [rsp+78h+cbData], 4
0x18003edf9  lea     rax, [rsp+78h+cbData]
0x18003ee01  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18003ee06  lea     rax, [rsp+78h+Data]
0x18003ee0e  mov     [rsp+78h+phkResult], rax; lpData
0x18003ee13  lea     r9, [rsp+78h+Type]; lpType
0x18003ee18  xor     r8d, r8d; lpReserved
0x18003ee1b  lea     rdx, aOptionvalue; "OptionValue"
0x18003ee22  mov     rcx, [rsp+78h+hKey]; hKey
0x18003ee27  call    cs:__imp_RegQueryValueExW
0x18003ee2d  mov     ebx, eax
0x18003ee2f  mov     rcx, [rsp+78h+hKey]; hKey
0x18003ee34  call    cs:__imp_RegCloseKey
0x18003ee3a  test    ebx, ebx
0x18003ee3c  jnz     short loc_18003EE4F
0x18003ee3e  cmp     [rsp+78h+Data], 1
0x18003ee46  jnz     short loc_18003EE4F
0x18003ee48  mov     cs:NlpLanmanInstalled, r14b
0x18003ee4f  mov     rdx, rdi; SourceString
0x18003ee52  lea     rcx, NlpComputerName; DestinationString
0x18003ee59  call    cs:__imp_RtlInitUnicodeString
0x18003ee5f  lea     rcx, [rsp+78h+ProductType]; ProductType
0x18003ee67  call    cs:__imp_RtlGetNtProductType
0x18003ee6d  test    al, al
0x18003ee6f  jnz     short loc_18003EEA3
0x18003ee71  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ee78  cmp     rcx, rsi
0x18003ee7b  jz      short loc_18003EE98
0x18003ee7d  test    byte ptr [rcx+1Ch], 8
0x18003ee81  jz      short loc_18003EE98
0x18003ee83  mov     edx, 0Bh
0x18003ee88  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x18003ee8f  mov     rcx, [rcx+10h]
0x18003ee93  call    WPP_SF_
0x18003ee98  mov     [rsp+78h+ProductType], 1
0x18003eea3  cmp     [rsp+78h+ProductType], 2
0x18003eeab  setnz   cs:NlpWorkstation
0x18003eeb2  lea     rax, NlpActiveLogonListAnchor
0x18003eeb9  mov     cs:qword_180086FB0, rax
0x18003eec0  mov     cs:NlpActiveLogonListAnchor, rax
0x18003eec7  mov     cs:NlpActiveLogonTable, r14
0x18003eece  lea     rcx, NlpActiveLogonLock; Resource
0x18003eed5  call    cs:__imp_RtlInitializeResource
0x18003eedb  jmp     short $+2
0x18003eedd  call    NlpCacheInitialize
0x18003eee2  xor     r8d, r8d; dwFlags
0x18003eee5  xor     edx, edx; hFile
0x18003eee7  lea     rcx, aNetlogon_0; "netlogon"
0x18003eeee  call    cs:__imp_LoadLibraryExA
0x18003eef4  lea     rcx, SubAuthenticationCritSect; Resource
0x18003eefb  call    cs:__imp_RtlInitializeResource
0x18003ef01  lea     rax, SubAuthenticationDlls
0x18003ef08  mov     cs:qword_18008A908, rax
0x18003ef0f  mov     cs:SubAuthenticationDlls, rax
0x18003ef16  xor     eax, eax
0x18003ef18  add     rsp, 58h
0x18003ef1c  pop     r14
0x18003ef1e  pop     rdi
0x18003ef1f  pop     rsi
0x18003ef20  pop     rbx
0x18003ef21  retn
```
