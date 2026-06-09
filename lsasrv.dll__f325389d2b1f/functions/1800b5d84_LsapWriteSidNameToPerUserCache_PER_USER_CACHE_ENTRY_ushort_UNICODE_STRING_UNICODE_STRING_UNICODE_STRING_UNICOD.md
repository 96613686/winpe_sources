# LsapWriteSidNameToPerUserCache(_PER_USER_CACHE_ENTRY *,ushort *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)

- ea: `0x1800b5d84`
- end: `0x1800b619a`
- name: `?LsapWriteSidNameToPerUserCache@@YAJPEAU_PER_USER_CACHE_ENTRY@@PEAGPEAU_UNICODE_STRING@@2222@Z`
- size: `1046`
- prototype: `int(struct _PER_USER_CACHE_ENTRY *, unsigned __int16 *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180112978`

## callees

- `0x18005faf0`
- `0x1800626ac`
- `0x180097c3c`
- `0x1800b5d84`
- `0x1800b61a0`
- `0x1801274f8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b5fa2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800b5fa2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5ea5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b5ea5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b6158`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b6158`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b5e74`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b5f7a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b5e74`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b5f7a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b5fe6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b5fe6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b5f0f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800b5f0f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800b5ed1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800b5ed1`
- `ntdll!RtlInitUnicodeString` at `0x1800b5ddd`
- `ntdll!RtlInitUnicodeString` at `0x1800b5ddd`

## string_xrefs

- `0x1800b6119`: `SecurityPrincipalType`

## pseudocode

```c
__int64 __fastcall LsapWriteSidNameToPerUserCache(
        struct _PER_USER_CACHE_ENTRY *a1,
        unsigned __int16 *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5,
        struct _UNICODE_STRING *a6,
        struct _UNICODE_STRING *a7)
{
  HKEY v10; // r13
  int v11; // edi
  signed int v12; // ebx
  const WCHAR *v13; // rdx
  LSTATUS Key; // eax
  const WCHAR *v15; // rsi
  LSTATUS InfoKeyW; // eax
  bool v18; // cc
  struct _UNICODE_STRING *p_DestinationString; // r8
  BYTE Data[8]; // [rsp+60h] [rbp-41h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-39h] BYREF
  DWORD Type; // [rsp+70h] [rbp-31h] BYREF
  DWORD lpdwDisposition; // [rsp+74h] [rbp-2Dh] BYREF
  DWORD dwDisposition[2]; // [rsp+78h] [rbp-29h] BYREF
  DWORD cbData; // [rsp+80h] [rbp-21h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+88h] [rbp-19h] BYREF
  struct _UNICODE_STRING v29; // [rsp+90h] [rbp-11h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-1h] BYREF

  cbData = 4;
  hKey = 0;
  lpdwDisposition = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  v29 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, &cchOriginalDestLength);
  if ( !a4->Length || !a5->Length || !a4->Buffer || !a5->Buffer )
    return 3221225485LL;
  v10 = 0;
  v11 = 0;
  v12 = LsapIdProvGuidStringFromName(a5, &v29);
  if ( v12 < 0 )
    goto LABEL_12;
  if ( *((_QWORD *)a1 + 55) )
    goto LABEL_19;
  v13 = (const WCHAR *)*((_QWORD *)a1 + 54);
  dwDisposition[0] = 0;
  Key = RegCreateKeyExW(g_hKeyCacheRoot, v13, 0, 0, 0, 0x2001Fu, 0, (PHKEY)a1 + 55, dwDisposition);
  v12 = Key;
  if ( !Key )
    goto LABEL_19;
  if ( Key > 0 )
    v12 = (unsigned __int16)Key | 0xC0070000;
  if ( v12 >= 0 )
  {
LABEL_19:
    v10 = (HKEY)*((_QWORD *)a1 + 55);
    v11 = 0;
    *(_DWORD *)Data = 0;
    InfoKeyW = RegQueryValueExW(v10, L"Version", 0, &Type, Data, &cbData);
    v12 = InfoKeyW;
    if ( InfoKeyW == 2 )
      goto LABEL_25;
    v18 = InfoKeyW <= 0;
    if ( InfoKeyW )
    {
      v15 = a2;
      goto LABEL_22;
    }
    if ( Type != 4 )
LABEL_25:
      *(_DWORD *)Data = 0;
    v15 = a2;
    InfoKeyW = RegCreateKeyExW(v10, a2, 0, 0, 0, 0x2011Fu, 0, &hKey, &lpdwDisposition);
    v12 = InfoKeyW;
    v18 = InfoKeyW <= 0;
    if ( !InfoKeyW )
    {
      if ( lpdwDisposition != 2 )
      {
        v11 = 1;
LABEL_34:
        v12 = LsapWriteIdentityCacheEntryStringValue(hKey, L"UserName", a4);
        if ( v12 < 0 )
          goto LABEL_13;
        if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl)
          || (p_DestinationString = &DestinationString, a3->Length) )
        {
          p_DestinationString = a3;
        }
        v12 = LsapWriteIdentityCacheEntryStringValue(hKey, L"SAMName", p_DestinationString);
        if ( v12 < 0 )
          goto LABEL_13;
        if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
          a6 = a4;
        v12 = LsapWriteIdentityCacheEntryStringValue(hKey, L"DisplayName", a6);
        if ( v12 < 0 )
          goto LABEL_13;
        v12 = LsapWriteIdentityCacheEntryStringValue(hKey, L"ProviderName", a5);
        if ( v12 < 0 )
          goto LABEL_13;
        v12 = LsapWriteIdentityCacheEntryStringValue(hKey, L"ProviderGUID", &v29);
        if ( v12 < 0 )
          goto LABEL_13;
        if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
        {
          v12 = LsapWriteIdentityCacheEntryStringValue(hKey, L"SecurityPrincipalType", a7);
          if ( v12 < 0 )
            goto LABEL_13;
        }
        ++*(_DWORD *)Data;
        InfoKeyW = RegSetValueExW(v10, L"Version", 0, 4u, Data, 4u);
        if ( !InfoKeyW )
          goto LABEL_13;
        if ( InfoKeyW <= 0 )
        {
          v12 = InfoKeyW;
          goto LABEL_13;
        }
        goto LABEL_23;
      }
      *(_QWORD *)dwDisposition = 0;
      SystemTimeAsFileTime = 0;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      InfoKeyW = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, (PFILETIME)dwDisposition);
      v12 = InfoKeyW;
      v18 = InfoKeyW <= 0;
      if ( !InfoKeyW )
      {
        if ( *(unsigned __int64 *)&SystemTimeAsFileTime < *(_QWORD *)dwDisposition + 5000000LL )
        {
          v12 = -1073741823;
          goto LABEL_13;
        }
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 12), 60, &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids, a2);
        goto LABEL_34;
      }
    }
LABEL_22:
    if ( v18 )
      goto LABEL_13;
LABEL_23:
    v12 = (unsigned __int16)InfoKeyW | 0xC0070000;
    goto LABEL_13;
  }
  v11 = 0;
LABEL_12:
  v15 = a2;
LABEL_13:
  if ( hKey )
    RegCloseKey(hKey);
  LsapFreeString(&v29);
  if ( v12 < 0 )
  {
    if ( v11 )
      RegDeleteKeyExW(v10, v15, 0x100u, 0);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800b5d84  mov     [rsp-8+arg_0], rbx
0x1800b5d89  mov     [rsp-8+lpSubKey], rdx
0x1800b5d8e  push    rbp
0x1800b5d8f  push    rsi
0x1800b5d90  push    rdi
0x1800b5d91  push    r12
0x1800b5d93  push    r13
0x1800b5d95  push    r14
0x1800b5d97  push    r15
0x1800b5d99  lea     rbp, [rsp-0Fh]
0x1800b5d9e  sub     rsp, 0B0h
0x1800b5da5  xor     ebx, ebx
0x1800b5da7  mov     [rbp+3Fh+cbData], 4
0x1800b5dae  mov     rsi, rcx
0x1800b5db1  mov     [rbp+3Fh+hKey], rbx
0x1800b5db5  xorps   xmm0, xmm0
0x1800b5db8  mov     [rbp+3Fh+var_6C], ebx
0x1800b5dbb  xorps   xmm1, xmm1
0x1800b5dbe  mov     dword ptr [rbp+3Fh+Data], ebx
0x1800b5dc1  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800b5dc5  mov     [rbp+3Fh+Type], ebx
0x1800b5dc8  lea     rdx, cchOriginalDestLength; SourceString
0x1800b5dcf  mov     r15, r9
0x1800b5dd2  movups  xmmword ptr [rbp+3Fh+var_50.Length], xmm0
0x1800b5dd6  mov     r12, r8
0x1800b5dd9  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm1
0x1800b5ddd  call    cs:__imp_RtlInitUnicodeString
0x1800b5de4  nop     dword ptr [rax+rax+00h]
0x1800b5de9  cmp     [r15], bx
0x1800b5ded  jz      loc_1800B6179
0x1800b5df3  mov     r14, [rbp+3Fh+arg_20]
0x1800b5df7  cmp     [r14], bx
0x1800b5dfb  jz      loc_1800B6179
0x1800b5e01  cmp     [r15+8], rbx
0x1800b5e05  jz      loc_1800B6179
0x1800b5e0b  cmp     [r14+8], rbx
0x1800b5e0f  jz      loc_1800B6179
0x1800b5e15  lea     rdx, [rbp+3Fh+var_50]; struct _UNICODE_STRING *
0x1800b5e19  mov     rcx, r14; struct _UNICODE_STRING *
0x1800b5e1c  mov     r13d, ebx
0x1800b5e1f  mov     edi, ebx
0x1800b5e21  call    ?LsapIdProvGuidStringFromName@@YAJPEAU_UNICODE_STRING@@0@Z; LsapIdProvGuidStringFromName(_UNICODE_STRING *,_UNICODE_STRING *)
0x1800b5e26  xor     ecx, ecx
0x1800b5e28  mov     ebx, eax
0x1800b5e2a  test    eax, eax
0x1800b5e2c  js      short loc_1800B5E98
0x1800b5e2e  lea     rdi, [rsi+1B8h]
0x1800b5e35  cmp     [rdi], rcx
0x1800b5e38  jnz     loc_1800B5EE4
0x1800b5e3e  mov     rdx, [rsi+1B0h]; lpSubKey
0x1800b5e45  lea     rax, [rbp+3Fh+dwDisposition]
0x1800b5e49  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x1800b5e4e  xor     r9d, r9d; lpClass
0x1800b5e51  mov     [rsp+0E0h+phkResult], rdi; phkResult
0x1800b5e56  xor     r8d, r8d; Reserved
0x1800b5e59  mov     [rsp+0E0h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x1800b5e5e  mov     [rbp+3Fh+dwDisposition], ecx
0x1800b5e61  mov     [rsp+0E0h+samDesired], 2001Fh; samDesired
0x1800b5e69  mov     [rsp+0E0h+dwOptions], ecx; dwOptions
0x1800b5e6d  mov     rcx, cs:?g_hKeyCacheRoot@@3PEAUHKEY__@@EA; hKey
0x1800b5e74  call    cs:__imp_RegCreateKeyExW
0x1800b5e7b  nop     dword ptr [rax+rax+00h]
0x1800b5e80  mov     ebx, eax
0x1800b5e82  test    eax, eax
0x1800b5e84  jz      short loc_1800B5EE4
0x1800b5e86  jle     short loc_1800B5E91
0x1800b5e88  movzx   ebx, ax
0x1800b5e8b  or      ebx, 0C0070000h
0x1800b5e91  test    ebx, ebx
0x1800b5e93  jns     short loc_1800B5EE4
0x1800b5e95  mov     edi, r13d
0x1800b5e98  mov     rsi, [rbp+3Fh+lpSubKey]
0x1800b5e9c  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800b5ea0  test    rcx, rcx
0x1800b5ea3  jz      short loc_1800B5EB1
0x1800b5ea5  call    cs:__imp_RegCloseKey
0x1800b5eac  nop     dword ptr [rax+rax+00h]
0x1800b5eb1  lea     rcx, [rbp+3Fh+var_50]
0x1800b5eb5  call    LsapFreeString
0x1800b5eba  test    ebx, ebx
0x1800b5ebc  jns     short loc_1800B5EDD
0x1800b5ebe  test    edi, edi
0x1800b5ec0  jz      short loc_1800B5EDD
0x1800b5ec2  xor     r9d, r9d; Reserved
0x1800b5ec5  mov     r8d, 100h; samDesired
0x1800b5ecb  mov     rdx, rsi; lpSubKey
0x1800b5ece  mov     rcx, r13; hKey
0x1800b5ed1  call    cs:__imp_RegDeleteKeyExW
0x1800b5ed8  nop     dword ptr [rax+rax+00h]
0x1800b5edd  mov     eax, ebx
0x1800b5edf  jmp     loc_1800B617E
0x1800b5ee4  mov     r13, [rdi]
0x1800b5ee7  lea     rax, [rbp+3Fh+cbData]
0x1800b5eeb  mov     qword ptr [rsp+0E0h+samDesired], rax; lpcbData
0x1800b5ef0  lea     r9, [rbp+3Fh+Type]; lpType
0x1800b5ef4  lea     rax, [rbp+3Fh+Data]
0x1800b5ef8  xor     edi, edi
0x1800b5efa  xor     r8d, r8d; lpReserved
0x1800b5efd  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x1800b5f02  lea     rdx, aVersion; "Version"
0x1800b5f09  mov     dword ptr [rbp+3Fh+Data], edi
0x1800b5f0c  mov     rcx, r13; hKey
0x1800b5f0f  call    cs:__imp_RegQueryValueExW
0x1800b5f16  nop     dword ptr [rax+rax+00h]
0x1800b5f1b  mov     ebx, eax
0x1800b5f1d  cmp     eax, 2
0x1800b5f20  jz      short loc_1800B5F44
0x1800b5f22  test    eax, eax
0x1800b5f24  jz      short loc_1800B5F3E
0x1800b5f26  mov     rsi, [rbp+3Fh+lpSubKey]
0x1800b5f2a  jle     loc_1800B5E9C
0x1800b5f30  movzx   ebx, ax
0x1800b5f33  or      ebx, 0C0070000h
0x1800b5f39  jmp     loc_1800B5E9C
0x1800b5f3e  cmp     [rbp+3Fh+Type], 4
0x1800b5f42  jz      short loc_1800B5F47
0x1800b5f44  mov     dword ptr [rbp+3Fh+Data], edi
0x1800b5f47  mov     rsi, [rbp+3Fh+lpSubKey]
0x1800b5f4b  lea     rax, [rbp+3Fh+var_6C]
0x1800b5f4f  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x1800b5f54  xor     r9d, r9d; lpClass
0x1800b5f57  lea     rax, [rbp+3Fh+hKey]
0x1800b5f5b  xor     r8d, r8d; Reserved
0x1800b5f5e  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800b5f63  mov     rdx, rsi; lpSubKey
0x1800b5f66  mov     [rsp+0E0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x1800b5f6b  mov     rcx, r13; hKey
0x1800b5f6e  mov     [rsp+0E0h+samDesired], 2011Fh; samDesired
0x1800b5f76  mov     [rsp+0E0h+dwOptions], edi; dwOptions
0x1800b5f7a  call    cs:__imp_RegCreateKeyExW
0x1800b5f81  nop     dword ptr [rax+rax+00h]
0x1800b5f86  mov     ebx, eax
0x1800b5f88  test    eax, eax
0x1800b5f8a  jnz     short loc_1800B5F2A
0x1800b5f8c  cmp     [rbp+3Fh+var_6C], 2
0x1800b5f90  jnz     loc_1800B603D
0x1800b5f96  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800b5f9a  mov     qword ptr [rbp+3Fh+dwDisposition], rdi
0x1800b5f9e  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], rdi
0x1800b5fa2  call    cs:__imp_GetSystemTimeAsFileTime
0x1800b5fa9  nop     dword ptr [rax+rax+00h]
0x1800b5fae  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800b5fb2  lea     rax, [rbp+3Fh+dwDisposition]
0x1800b5fb6  mov     [rsp+0E0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800b5fbb  xor     r9d, r9d; lpReserved
0x1800b5fbe  mov     [rsp+0E0h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x1800b5fc3  xor     r8d, r8d; lpcchClass
0x1800b5fc6  mov     [rsp+0E0h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x1800b5fcb  xor     edx, edx; lpClass
0x1800b5fcd  mov     [rsp+0E0h+lpdwDisposition], rdi; lpcbMaxValueNameLen
0x1800b5fd2  mov     [rsp+0E0h+phkResult], rdi; lpcValues
0x1800b5fd7  mov     [rsp+0E0h+lpSecurityAttributes], rdi; lpcbMaxClassLen
0x1800b5fdc  mov     qword ptr [rsp+0E0h+samDesired], rdi; lpcbMaxSubKeyLen
0x1800b5fe1  mov     qword ptr [rsp+0E0h+dwOptions], rdi; lpcSubKeys
0x1800b5fe6  call    cs:__imp_RegQueryInfoKeyW
0x1800b5fed  nop     dword ptr [rax+rax+00h]
0x1800b5ff2  mov     ebx, eax
0x1800b5ff4  test    eax, eax
0x1800b5ff6  jnz     loc_1800B5F2A
0x1800b5ffc  mov     rax, qword ptr [rbp+3Fh+dwDisposition]
0x1800b6000  add     rax, 4C4B40h
0x1800b6006  cmp     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800b600a  jnb     short loc_1800B6016
0x1800b600c  mov     ebx, 0C0000001h
0x1800b6011  jmp     loc_1800B5E9C
0x1800b6016  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b601d  test    byte ptr [rcx+6Ch], 10h
0x1800b6021  jz      short loc_1800B6042
0x1800b6023  mov     rcx, [rcx+60h]
0x1800b6027  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x1800b602e  mov     edx, 3Ch ; '<'
0x1800b6033  mov     r9, rsi
0x1800b6036  call    WPP_SF_S
0x1800b603b  jmp     short loc_1800B6042
0x1800b603d  mov     edi, 1
0x1800b6042  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800b6046  lea     rdx, aUsername_0; "UserName"
0x1800b604d  mov     r8, r15; struct _UNICODE_STRING *
0x1800b6050  call    ?LsapWriteIdentityCacheEntryStringValue@@YAJPEAUHKEY__@@PEBGPEAU_UNICODE_STRING@@@Z; LsapWriteIdentityCacheEntryStringValue(HKEY__ *,ushort const *,_UNICODE_STRING *)
0x1800b6055  mov     ebx, eax
0x1800b6057  test    eax, eax
0x1800b6059  js      loc_1800B5E9C
0x1800b605f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x1800b6066  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x1800b606b  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800b606f  lea     rdx, aSamname; "SAMName"
0x1800b6076  test    al, al
0x1800b6078  jz      short loc_1800B6087
0x1800b607a  xor     eax, eax
0x1800b607c  lea     r8, [rbp+3Fh+DestinationString]
0x1800b6080  cmp     ax, [r12]
0x1800b6085  jz      short loc_1800B608A
0x1800b6087  mov     r8, r12; struct _UNICODE_STRING *
0x1800b608a  call    ?LsapWriteIdentityCacheEntryStringValue@@YAJPEAUHKEY__@@PEBGPEAU_UNICODE_STRING@@@Z; LsapWriteIdentityCacheEntryStringValue(HKEY__ *,ushort const *,_UNICODE_STRING *)
0x1800b608f  mov     ebx, eax
0x1800b6091  test    eax, eax
0x1800b6093  js      loc_1800B5E9C
0x1800b6099  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x1800b60a0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x1800b60a5  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800b60a9  lea     rdx, aDisplayname; "DisplayName"
0x1800b60b0  mov     r8, [rbp+3Fh+arg_28]
0x1800b60b4  test    al, al
0x1800b60b6  jnz     short loc_1800B60BB
0x1800b60b8  mov     r8, r15; struct _UNICODE_STRING *
0x1800b60bb  call    ?LsapWriteIdentityCacheEntryStringValue@@YAJPEAUHKEY__@@PEBGPEAU_UNICODE_STRING@@@Z; LsapWriteIdentityCacheEntryStringValue(HKEY__ *,ushort const *,_UNICODE_STRING *)
0x1800b60c0  mov     ebx, eax
0x1800b60c2  test    eax, eax
0x1800b60c4  js      loc_1800B5E9C
0x1800b60ca  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800b60ce  lea     rdx, aProvidername; "ProviderName"
0x1800b60d5  mov     r8, r14; struct _UNICODE_STRING *
0x1800b60d8  call    ?LsapWriteIdentityCacheEntryStringValue@@YAJPEAUHKEY__@@PEBGPEAU_UNICODE_STRING@@@Z; LsapWriteIdentityCacheEntryStringValue(HKEY__ *,ushort const *,_UNICODE_STRING *)
0x1800b60dd  mov     ebx, eax
0x1800b60df  test    eax, eax
0x1800b60e1  js      loc_1800B5E9C
0x1800b60e7  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800b60eb  lea     r8, [rbp+3Fh+var_50]; struct _UNICODE_STRING *
0x1800b60ef  lea     rdx, aProviderguid; "ProviderGUID"
0x1800b60f6  call    ?LsapWriteIdentityCacheEntryStringValue@@YAJPEAUHKEY__@@PEBGPEAU_UNICODE_STRING@@@Z; LsapWriteIdentityCacheEntryStringValue(HKEY__ *,ushort const *,_UNICODE_STRING *)
0x1800b60fb  mov     ebx, eax
0x1800b60fd  test    eax, eax
0x1800b60ff  js      loc_1800B5E9C
0x1800b6105  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x1800b610c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x1800b6111  test    al, al
0x1800b6113  jz      short loc_1800B6133
0x1800b6115  mov     r8, [rbp+3Fh+arg_30]; struct _UNICODE_STRING *
0x1800b6119  lea     rdx, aSecurityprinci; "SecurityPrincipalType"
0x1800b6120  mov     rcx, [rbp+3Fh+hKey]; hKey
0x1800b6124  call    ?LsapWriteIdentityCacheEntryStringValue@@YAJPEAUHKEY__@@PEBGPEAU_UNICODE_STRING@@@Z; LsapWriteIdentityCacheEntryStringValue(HKEY__ *,ushort const *,_UNICODE_STRING *)
0x1800b6129  mov     ebx, eax
0x1800b612b  test    eax, eax
0x1800b612d  js      loc_1800B5E9C
0x1800b6133  inc     dword ptr [rbp+3Fh+Data]
0x1800b6136  lea     rax, [rbp+3Fh+Data]
0x1800b613a  mov     ecx, 4
0x1800b613f  lea     rdx, aVersion; "Version"
0x1800b6146  mov     [rsp+0E0h+samDesired], ecx; cbData
0x1800b614a  mov     r9d, ecx; dwType
0x1800b614d  mov     rcx, r13; hKey
0x1800b6150  mov     qword ptr [rsp+0E0h+dwOptions], rax; lpData
0x1800b6155  xor     r8d, r8d; Reserved
0x1800b6158  call    cs:__imp_RegSetValueExW
0x1800b615f  nop     dword ptr [rax+rax+00h]
0x1800b6164  test    eax, eax
0x1800b6166  jz      loc_1800B5E9C
0x1800b616c  jg      loc_1800B5F30
0x1800b6172  mov     ebx, eax
0x1800b6174  jmp     loc_1800B5E9C
0x1800b6179  mov     eax, 0C000000Dh
0x1800b617e  mov     rbx, [rsp+0E0h+arg_0]
0x1800b6186  add     rsp, 0B0h
0x1800b618d  pop     r15
0x1800b618f  pop     r14
0x1800b6191  pop     r13
0x1800b6193  pop     r12
0x1800b6195  pop     rdi
0x1800b6196  pop     rsi
0x1800b6197  pop     rbp
0x1800b6198  retn
```
