# IASStaticInfoInitialize

- ea: `0x18002b020`
- end: `0x18002b3be`
- name: `IASStaticInfoInitialize`
- size: `926`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800291bc`

## callees

- `0x18000c4a4`
- `0x18000e754`
- `0x1800254a0`
- `0x18002b020`
- `0x18002b4a0`

## import_xrefs

- `msvcrt!_wcsupr` at `0x18002b1cf`
- `msvcrt!_wcsupr` at `0x18002b36d`
- `msvcrt!_wcsupr` at `0x18002b1cf`
- `msvcrt!_wcsupr` at `0x18002b36d`
- `msvcrt!wcscpy_s` at `0x18002b073`
- `msvcrt!wcscpy_s` at `0x18002b073`
- `msvcrt!wcsncpy_s` at `0x18002b1bf`
- `msvcrt!wcsncpy_s` at `0x18002b1bf`
- `ntdll!RtlSubAuthoritySid` at `0x18002b268`
- `ntdll!RtlSubAuthoritySid` at `0x18002b268`
- `ntdll!RtlCopySid` at `0x18002b234`
- `ntdll!RtlCopySid` at `0x18002b234`
- `ntdll!RtlInitializeSid` at `0x18002b259`
- `ntdll!RtlInitializeSid` at `0x18002b259`
- `ntdll!RtlNtStatusToDosError` at `0x18002b188`
- `ntdll!RtlNtStatusToDosError` at `0x18002b188`
- `ntdll!RtlGetNtProductType` at `0x18002b279`
- `ntdll!RtlGetNtProductType` at `0x18002b279`
- `KERNEL32!GetLastError` at `0x18002b096`
- `KERNEL32!GetLastError` at `0x18002b096`
- `KERNEL32!GetComputerNameW` at `0x18002b08c`
- `KERNEL32!GetComputerNameW` at `0x18002b08c`
- `ADVAPI32!LsaFreeMemory` at `0x18002b23e`
- `ADVAPI32!LsaFreeMemory` at `0x18002b23e`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18002b11f`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18002b11f`
- `ADVAPI32!LsaOpenPolicy` at `0x18002b106`
- `ADVAPI32!LsaOpenPolicy` at `0x18002b106`
- `ADVAPI32!LsaClose` at `0x18002b12b`
- `ADVAPI32!LsaClose` at `0x18002b12b`
- `ADVAPI32!RegCloseKey` at `0x18002b353`
- `ADVAPI32!RegCloseKey` at `0x18002b353`
- `ADVAPI32!RegOpenKeyW` at `0x18002b313`
- `ADVAPI32!RegOpenKeyW` at `0x18002b313`
- `ADVAPI32!RegQueryValueExW` at `0x18002b347`
- `ADVAPI32!RegQueryValueExW` at `0x18002b347`

## string_xrefs

- `0x18002b38e`: `Registry override: %S`
- `0x18002b30c`: `SYSTEM\CurrentControlSet\Services\RasMan\ppp\ControlProtocols\BuiltIn`

## pseudocode

```c
DWORD IASStaticInfoInitialize()
{
  int v1; // r9d
  int v2; // ebx
  int v3; // r9d
  __int64 v4; // rdx
  LSTATUS v5; // ebx
  int v6; // r9d
  DWORD nSize; // [rsp+30h] [rbp-48h] BYREF
  _NT_PRODUCT_TYPE ProductType; // [rsp+34h] [rbp-44h] BYREF
  DWORD Type; // [rsp+38h] [rbp-40h] BYREF
  PVOID Buffer; // [rsp+40h] [rbp-38h] BYREF
  PVOID PolicyHandle; // [rsp+48h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-28h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+58h] [rbp-20h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Type = 0;
  PolicyHandle = 0;
  Buffer = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  ProductType = 0;
  phkResult = 0;
  wcscpy_s(&theLocalServer, 0x12u, L"\\\\");
  nSize = 16;
  if ( !GetComputerNameW(&::Buffer, &nSize) )
    return GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Local server: %S");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_ff64ba2978c239eaa0ea21c130ce7eb8_Traceguids,
      v1,
      (__int64)&theLocalServer);
  }
  v2 = LsaOpenPolicy(0, &theObjectAttributes, 1u, &PolicyHandle);
  if ( v2 < 0 )
    return RtlNtStatusToDosError(v2);
  v2 = LsaQueryInformationPolicy(PolicyHandle, PolicyAccountDomainInformation, &Buffer);
  LsaClose(PolicyHandle);
  if ( v2 < 0 )
    return RtlNtStatusToDosError(v2);
  if ( !Buffer )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WppDbgPrint("LsaQueryInformationPolicy succeeded with NULL buffer for PolicyAccountDomainInformation");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ff64ba2978c239eaa0ea21c130ce7eb8_Traceguids, "NPSSVC");
    }
    v2 = -1073741823;
    return RtlNtStatusToDosError(v2);
  }
  wcsncpy_s(&theAccountDomain, 0x10u, *((const wchar_t **)Buffer + 1), 0xFu);
  word_18004049E = 0;
  _wcsupr(&theAccountDomain);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Local account domain: %S");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      (unsigned int)WPP_ff64ba2978c239eaa0ea21c130ce7eb8_Traceguids,
      v3,
      (__int64)&theAccountDomain);
  }
  theAccountDomainSid = theAccountDomainSidBuffer;
  RtlCopySid(0x18u, theAccountDomainSidBuffer, *((PSID *)Buffer + 2));
  LsaFreeMemory(Buffer);
  theBuiltinDomainSid = theBuiltinDomainSidBuffer;
  RtlInitializeSid(theBuiltinDomainSidBuffer, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(theBuiltinDomainSid, 0) = 32;
  RtlGetNtProductType(&ProductType);
  if ( ProductType == NtProductWinNt )
  {
    ourProductType = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_30;
    }
    WppDbgPrint("Product Type: Workstation");
    v4 = 13;
  }
  else
  {
    ourProductType = 1;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_30;
    }
    WppDbgPrint("Product Type: Server");
    v4 = 14;
  }
  WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, WPP_ff64ba2978c239eaa0ea21c130ce7eb8_Traceguids, "NPSSVC");
LABEL_30:
  if ( RegOpenKeyW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\ppp\\ControlProtocols\\BuiltIn",
         &phkResult)
    || (nSize = 32,
        v5 = RegQueryValueExW(phkResult, L"DefaultDomain", 0, &Type, &theRegistryDomain, &nSize),
        RegCloseKey(phkResult),
        v5)
    || Type != 1 )
  {
    *(_WORD *)&theRegistryDomain = 0;
  }
  _wcsupr((wchar_t *)&theRegistryDomain);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WppDbgPrint("Registry override: %S");
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      15,
      (unsigned int)WPP_ff64ba2978c239eaa0ea21c130ce7eb8_Traceguids,
      v6,
      (__int64)&theRegistryDomain);
  }
  return 0;
}

```

## disassembly

```asm
0x18002b020  push    rbp
0x18002b022  push    rbx
0x18002b023  push    rdi
0x18002b024  push    r12
0x18002b026  push    r14
0x18002b028  push    r15
0x18002b02a  mov     rbp, rsp
0x18002b02d  sub     rsp, 78h
0x18002b031  mov     rax, cs:__security_cookie
0x18002b038  xor     rax, rsp
0x18002b03b  mov     [rbp+var_18], rax
0x18002b03f  xor     edi, edi
0x18002b041  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x18002b047  lea     rbx, theLocalServer
0x18002b04e  mov     [rbp+nSize], edi
0x18002b051  lea     r8, asc_180037B28; "\\\\"
0x18002b058  mov     [rbp+Type], edi
0x18002b05b  mov     rcx, rbx; Destination
0x18002b05e  mov     [rbp+PolicyHandle], rdi
0x18002b062  lea     edx, [rdi+12h]; SizeInWords
0x18002b065  mov     [rbp+Buffer], rdi
0x18002b069  mov     dword ptr [rbp+IdentifierAuthority.Value], edi
0x18002b06c  mov     [rbp+ProductType], edi
0x18002b06f  mov     [rbp+phkResult], rdi
0x18002b073  call    cs:__imp_wcscpy_s
0x18002b079  lea     r12d, [rdi+10h]
0x18002b07d  lea     rdx, [rbp+nSize]; nSize
0x18002b081  mov     [rbp+nSize], r12d
0x18002b085  lea     rcx, Buffer; lpBuffer
0x18002b08c  call    cs:__imp_GetComputerNameW
0x18002b092  test    eax, eax
0x18002b094  jnz     short loc_18002B0A1
0x18002b096  call    cs:__imp_GetLastError
0x18002b09c  jmp     loc_18002B18E
0x18002b0a1  mov     rax, cs:WPP_GLOBAL_Control
0x18002b0a8  lea     r14, WPP_GLOBAL_Control
0x18002b0af  lea     r15, WPP_ff64ba2978c239eaa0ea21c130ce7eb8_Traceguids
0x18002b0b6  cmp     rax, r14
0x18002b0b9  jz      short loc_18002B0F3
0x18002b0bb  cmp     byte ptr [rax+19h], 4
0x18002b0bf  jb      short loc_18002B0F3
0x18002b0c1  test    byte ptr [rax+1Ch], 4
0x18002b0c5  jz      short loc_18002B0F3
0x18002b0c7  mov     rdx, rbx
0x18002b0ca  lea     rcx, aLocalServerS; "Local server: %S"
0x18002b0d1  call    WppDbgPrint
0x18002b0d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b0dd  mov     edx, 0Ah
0x18002b0e2  mov     r8, r15
0x18002b0e5  mov     [rsp+78h+lpData], rbx
0x18002b0ea  mov     rcx, [rcx+10h]
0x18002b0ee  call    WPP_SF_sS
0x18002b0f3  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18002b0f7  mov     r8d, 1; DesiredAccess
0x18002b0fd  lea     rdx, theObjectAttributes; ObjectAttributes
0x18002b104  xor     ecx, ecx; SystemName
0x18002b106  call    cs:__imp_LsaOpenPolicy
0x18002b10c  mov     ebx, eax
0x18002b10e  test    eax, eax
0x18002b110  js      short loc_18002B186
0x18002b112  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18002b116  lea     r8, [rbp+Buffer]; Buffer
0x18002b11a  mov     edx, 5; InformationClass
0x18002b11f  call    cs:__imp_LsaQueryInformationPolicy
0x18002b125  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18002b129  mov     ebx, eax
0x18002b12b  call    cs:__imp_LsaClose
0x18002b131  test    ebx, ebx
0x18002b133  js      short loc_18002B186
0x18002b135  mov     r8, [rbp+Buffer]
0x18002b139  test    r8, r8
0x18002b13c  jnz     short loc_18002B1A8
0x18002b13e  mov     rax, cs:WPP_GLOBAL_Control
0x18002b145  cmp     rax, r14
0x18002b148  jz      short loc_18002B181
0x18002b14a  cmp     byte ptr [rax+19h], 2
0x18002b14e  jb      short loc_18002B181
0x18002b150  test    byte ptr [rax+1Ch], 4
0x18002b154  jz      short loc_18002B181
0x18002b156  lea     rcx, aLsaqueryinform; "LsaQueryInformationPolicy succeeded wit"...
0x18002b15d  call    WppDbgPrint
0x18002b162  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b169  lea     r9, aNpssvc; "NPSSVC"
0x18002b170  mov     edx, 0Bh
0x18002b175  mov     r8, r15
0x18002b178  mov     rcx, [rcx+10h]
0x18002b17c  call    WPP_SF_s
0x18002b181  mov     ebx, 0C0000001h
0x18002b186  mov     ecx, ebx; Status
0x18002b188  call    cs:__imp_RtlNtStatusToDosError
0x18002b18e  mov     rcx, [rbp+var_18]
0x18002b192  xor     rcx, rsp; StackCookie
0x18002b195  call    __security_check_cookie
0x18002b19a  add     rsp, 78h
0x18002b19e  pop     r15
0x18002b1a0  pop     r14
0x18002b1a2  pop     r12
0x18002b1a4  pop     rdi
0x18002b1a5  pop     rbx
0x18002b1a6  pop     rbp
0x18002b1a7  retn
0x18002b1a8  mov     r8, [r8+8]; Source
0x18002b1ac  lea     rbx, theAccountDomain
0x18002b1b3  mov     rcx, rbx; Destination
0x18002b1b6  mov     r9d, 0Fh; MaxCount
0x18002b1bc  mov     rdx, r12; SizeInWords
0x18002b1bf  call    cs:__imp_wcsncpy_s
0x18002b1c5  mov     rcx, rbx; String
0x18002b1c8  mov     cs:word_18004049E, di
0x18002b1cf  call    cs:__imp__wcsupr
0x18002b1d5  mov     rax, cs:WPP_GLOBAL_Control
0x18002b1dc  cmp     rax, r14
0x18002b1df  jz      short loc_18002B219
0x18002b1e1  cmp     byte ptr [rax+19h], 4
0x18002b1e5  jb      short loc_18002B219
0x18002b1e7  test    byte ptr [rax+1Ch], 4
0x18002b1eb  jz      short loc_18002B219
0x18002b1ed  mov     rdx, rbx
0x18002b1f0  lea     rcx, aLocalAccountDo; "Local account domain: %S"
0x18002b1f7  call    WppDbgPrint
0x18002b1fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b203  mov     edx, 0Ch
0x18002b208  mov     r8, r15
0x18002b20b  mov     [rsp+78h+lpData], rbx
0x18002b210  mov     rcx, [rcx+10h]
0x18002b214  call    WPP_SF_sS
0x18002b219  mov     r8, [rbp+Buffer]
0x18002b21d  lea     rdx, theAccountDomainSidBuffer; DestinationSid
0x18002b224  mov     ecx, 18h; DestinationSidLength
0x18002b229  mov     cs:theAccountDomainSid, rdx
0x18002b230  mov     r8, [r8+10h]; SourceSid
0x18002b234  call    cs:__imp_RtlCopySid
0x18002b23a  mov     rcx, [rbp+Buffer]; Buffer
0x18002b23e  call    cs:__imp_LsaFreeMemory
0x18002b244  lea     rcx, theBuiltinDomainSidBuffer; Sid
0x18002b24b  mov     r8b, 1; SubAuthorityCount
0x18002b24e  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x18002b252  mov     cs:theBuiltinDomainSid, rcx
0x18002b259  call    cs:__imp_RtlInitializeSid
0x18002b25f  mov     rcx, cs:theBuiltinDomainSid; Sid
0x18002b266  xor     edx, edx; SubAuthority
0x18002b268  call    cs:__imp_RtlSubAuthoritySid
0x18002b26e  mov     ebx, 20h ; ' '
0x18002b273  lea     rcx, [rbp+ProductType]; ProductType
0x18002b277  mov     [rax], ebx
0x18002b279  call    cs:__imp_RtlGetNtProductType
0x18002b27f  cmp     [rbp+ProductType], 1
0x18002b283  jnz     short loc_18002B2B4
0x18002b285  mov     cs:ourProductType, edi
0x18002b28b  mov     rax, cs:WPP_GLOBAL_Control
0x18002b292  cmp     rax, r14
0x18002b295  jz      short loc_18002B301
0x18002b297  cmp     byte ptr [rax+19h], 4
0x18002b29b  jb      short loc_18002B301
0x18002b29d  test    byte ptr [rax+1Ch], 4
0x18002b2a1  jz      short loc_18002B301
0x18002b2a3  lea     rcx, aProductTypeWor; "Product Type: Workstation"
0x18002b2aa  call    WppDbgPrint
0x18002b2af  lea     edx, [rbx-13h]
0x18002b2b2  jmp     short loc_18002B2E7
0x18002b2b4  mov     cs:ourProductType, 1
0x18002b2be  mov     rax, cs:WPP_GLOBAL_Control
0x18002b2c5  cmp     rax, r14
0x18002b2c8  jz      short loc_18002B301
0x18002b2ca  cmp     byte ptr [rax+19h], 4
0x18002b2ce  jb      short loc_18002B301
0x18002b2d0  test    byte ptr [rax+1Ch], 4
0x18002b2d4  jz      short loc_18002B301
0x18002b2d6  lea     rcx, aProductTypeSer; "Product Type: Server"
0x18002b2dd  call    WppDbgPrint
0x18002b2e2  mov     edx, 0Eh
0x18002b2e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b2ee  lea     r9, aNpssvc; "NPSSVC"
0x18002b2f5  mov     r8, r15
0x18002b2f8  mov     rcx, [rcx+10h]
0x18002b2fc  call    WPP_SF_s
0x18002b301  lea     r8, [rbp+phkResult]; phkResult
0x18002b305  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b30c  lea     rdx, RAS_KEYPATH_BUILTIN; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x18002b313  call    cs:__imp_RegOpenKeyW
0x18002b319  lea     r12, theRegistryDomain
0x18002b320  test    eax, eax
0x18002b322  jnz     short loc_18002B363
0x18002b324  mov     rcx, [rbp+phkResult]; hKey
0x18002b328  lea     rax, [rbp+nSize]
0x18002b32c  mov     [rsp+78h+lpcbData], rax; lpcbData
0x18002b331  lea     r9, [rbp+Type]; lpType
0x18002b335  xor     r8d, r8d; lpReserved
0x18002b338  mov     [rsp+78h+lpData], r12; lpData
0x18002b33d  lea     rdx, RAS_VALUENAME_DEFAULT_DOMAIN; "DefaultDomain"
0x18002b344  mov     [rbp+nSize], ebx
0x18002b347  call    cs:__imp_RegQueryValueExW
0x18002b34d  mov     rcx, [rbp+phkResult]; hKey
0x18002b351  mov     ebx, eax
0x18002b353  call    cs:__imp_RegCloseKey
0x18002b359  test    ebx, ebx
0x18002b35b  jnz     short loc_18002B363
0x18002b35d  cmp     [rbp+Type], 1
0x18002b361  jz      short loc_18002B36A
0x18002b363  mov     cs:theRegistryDomain, di
0x18002b36a  mov     rcx, r12; String
0x18002b36d  call    cs:__imp__wcsupr
0x18002b373  mov     rax, cs:WPP_GLOBAL_Control
0x18002b37a  cmp     rax, r14
0x18002b37d  jz      short loc_18002B3B7
0x18002b37f  cmp     byte ptr [rax+19h], 4
0x18002b383  jb      short loc_18002B3B7
0x18002b385  test    byte ptr [rax+1Ch], 4
0x18002b389  jz      short loc_18002B3B7
0x18002b38b  mov     rdx, r12
0x18002b38e  lea     rcx, aRegistryOverri; "Registry override: %S"
0x18002b395  call    WppDbgPrint
0x18002b39a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b3a1  mov     edx, 0Fh
0x18002b3a6  mov     r8, r15
0x18002b3a9  mov     [rsp+78h+lpData], r12
0x18002b3ae  mov     rcx, [rcx+10h]
0x18002b3b2  call    WPP_SF_sS
0x18002b3b7  xor     eax, eax
0x18002b3b9  jmp     loc_18002B18E
```
