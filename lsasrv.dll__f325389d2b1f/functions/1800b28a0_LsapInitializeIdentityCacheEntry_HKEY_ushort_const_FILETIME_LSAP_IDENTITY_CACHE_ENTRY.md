# LsapInitializeIdentityCacheEntry(HKEY__ *,ushort const *,_FILETIME *,_LSAP_IDENTITY_CACHE_ENTRY * *)

- ea: `0x1800b28a0`
- end: `0x1800b2f88`
- name: `?LsapInitializeIdentityCacheEntry@@YAJPEAUHKEY__@@PEBGPEAU_FILETIME@@PEAPEAU_LSAP_IDENTITY_CACHE_ENTRY@@@Z`
- size: `1768`
- prototype: `__int64 __fastcall(HKEY hkey, LPCWSTR lpSubKey, struct _FILETIME *, struct _LSAP_IDENTITY_CACHE_ENTRY **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180113fd0`

## callees

- `0x180011278`
- `0x18003a848`
- `0x1800626ac`
- `0x18008e360`
- `0x1800ada18`
- `0x1800b28a0`
- `0x1800b2f90`
- `0x1800b9304`
- `0x1800bd6ec`
- `0x180112b04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2925`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2f40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b2f40`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2bec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2e70`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2bec`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b2e70`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2999`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2a07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2a6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2aea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2b52`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2c6d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2cfd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2d79`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2e2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2eb5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2999`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2a07`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2a6e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2aea`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2b52`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2c6d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2cfd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2d79`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2e2f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800b2eb5`
- `ntdll!RtlLengthSid` at `0x1800b2b92`
- `ntdll!RtlLengthSid` at `0x1800b2b92`
- `ntdll!RtlInitUnicodeString` at `0x1800b2ed0`
- `ntdll!RtlInitUnicodeString` at `0x1800b2ed0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b2915`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800b2915`

## string_xrefs

- `0x1800b2acf`: `SecurityPrincipalType`
- `0x1800b2e97`: `SecurityPrincipalType`

## pseudocode

```c
__int64 __fastcall LsapInitializeIdentityCacheEntry(
        HKEY hkey,
        LPCWSTR lpSubKey,
        struct _FILETIME *a3,
        struct _FILETIME **a4)
{
  struct _FILETIME *v4; // rdi
  HLOCAL v5; // r13
  DWORD LastError; // eax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned int v13; // eax
  unsigned int v14; // ebx
  LsaHandleCache *v15; // rcx
  int v16; // edx
  unsigned int ValueW; // eax
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  unsigned int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  ULONG v37; // eax
  DWORD v38; // edx
  DWORD v39; // ecx
  DWORD v40; // edx
  unsigned int v41; // ecx
  unsigned int v42; // ebx
  struct _FILETIME *v43; // rax
  unsigned int v44; // eax
  __int64 v45; // r8
  __int64 v46; // r9
  __int64 v47; // rdx
  __int64 v48; // rbx
  __int64 v49; // rax
  unsigned int v50; // ecx
  char *pvData; // r15
  __int64 v52; // rax
  unsigned int v53; // ecx
  char *v54; // r15
  __int64 v55; // rax
  unsigned int v56; // edx
  __int64 v57; // r12
  char *v58; // r15
  enum _SID_NAME_USE v59; // eax
  PSID v60; // rcx
  DWORD pdwType; // [rsp+40h] [rbp-29h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-25h] BYREF
  DWORD v64; // [rsp+48h] [rbp-21h] BYREF
  DWORD v65; // [rsp+4Ch] [rbp-1Dh] BYREF
  DWORD v66; // [rsp+50h] [rbp-19h] BYREF
  DWORD v67; // [rsp+54h] [rbp-15h] BYREF
  PSID Sid; // [rsp+58h] [rbp-11h] BYREF
  size_t Size; // [rsp+60h] [rbp-9h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-1h] BYREF

  v4 = 0;
  pcbData = 0;
  v64 = 0;
  v5 = 0;
  v65 = 0;
  v66 = 0;
  Sid = 0;
  pdwType = 0;
  v67 = 0;
  DestinationString = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids);
  if ( ConvertStringSidToSidW(lpSubKey, &Sid) )
  {
    pcbData = 0;
    ValueW = RegGetValueW(hkey, lpSubKey, L"UserName", 2u, &pdwType, 0, &pcbData);
    if ( ValueW )
    {
      v13 = NetpApiStatusToNtStatus(ValueW, v18, v19, v20);
      v14 = v13;
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
        goto LABEL_64;
      v16 = 12;
      goto LABEL_6;
    }
    if ( pdwType != 1 )
      goto LABEL_11;
    v64 = 0;
    v21 = RegGetValueW(hkey, lpSubKey, L"SAMName", 2u, &pdwType, 0, &v64);
    if ( v21 )
    {
      v13 = NetpApiStatusToNtStatus(v21, v22, v23, v24);
      v14 = v13;
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
        goto LABEL_64;
      v16 = 13;
      goto LABEL_6;
    }
    if ( pdwType != 1 )
      goto LABEL_11;
    v65 = 0;
    v25 = RegGetValueW(hkey, lpSubKey, L"ProviderName", 2u, &pdwType, 0, &v65);
    if ( v25 )
    {
      v13 = NetpApiStatusToNtStatus(v25, v26, v27, v28);
      v14 = v13;
      v15 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
        goto LABEL_64;
      v16 = 14;
      goto LABEL_6;
    }
    if ( pdwType != 1 )
      goto LABEL_11;
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
    {
      v29 = RegGetValueW(hkey, lpSubKey, L"SecurityPrincipalType", 2u, &pdwType, 0, &v67);
      if ( v29 )
      {
        v13 = NetpApiStatusToNtStatus(v29, v30, v31, v32);
        v14 = v13;
        v15 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
          goto LABEL_64;
        v16 = 15;
        goto LABEL_6;
      }
      if ( pdwType != 1 )
        goto LABEL_11;
      v33 = RegGetValueW(hkey, lpSubKey, L"DisplayName", 2u, &pdwType, 0, &v66);
      if ( v33 )
      {
        v13 = NetpApiStatusToNtStatus(v33, v34, v35, v36);
        v14 = v13;
        v15 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
          goto LABEL_64;
        v16 = 16;
        goto LABEL_6;
      }
      if ( pdwType != 1 )
        goto LABEL_11;
    }
    v37 = RtlLengthSid(Sid);
    v38 = pcbData + 96;
    LODWORD(Size) = v37;
    if ( pcbData >= 0xFFFFFFA0
      || (v39 = v38 + v64, v38 + v64 < v38)
      || (v40 = v39 + v65, v39 + v65 < v39)
      || (v41 = v40 + v66, v40 + v66 < v40)
      || (v42 = v41 + v37, v41 + v37 < v41) )
    {
      v14 = -2147483643;
      goto LABEL_64;
    }
    v43 = (struct _FILETIME *)LocalAlloc(0x40u, v42);
    v4 = v43;
    if ( !v43 )
      goto LABEL_35;
    memset_0(v43, 0, v42);
    v4->dwLowDateTime = v42;
    _InterlockedIncrement((volatile signed __int32 *)&v4->dwHighDateTime);
    v4[9].dwHighDateTime = 8;
    v4[7] = *a3;
    HIWORD(v4[3].dwLowDateTime) = pcbData;
    v4[4] = (struct _FILETIME)&v4[12];
    pdwType = 1;
    v44 = RegGetValueW(hkey, lpSubKey, L"UserName", 0x20000002u, &pdwType, &v4[12], &pcbData);
    v47 = 0;
    if ( v44 )
      goto LABEL_37;
    v48 = -1;
    v49 = -1;
    do
      ++v49;
    while ( *(_WORD *)(*(_QWORD *)&v4[4] + 2 * v49) );
    v50 = 2 * (unsigned __int16)v49;
    if ( v50 > 0xFFFF )
    {
      LOWORD(v4[3].dwLowDateTime) = -1;
    }
    else
    {
      LOWORD(v4[3].dwLowDateTime) = v50;
      pvData = (char *)&v4[12] + HIWORD(v4[3].dwLowDateTime);
      HIWORD(v4[5].dwLowDateTime) = v64;
      v4[6] = (struct _FILETIME)pvData;
      pdwType = 1;
      v44 = RegGetValueW(hkey, lpSubKey, L"SAMName", 0x20000002u, &pdwType, pvData, &v64);
      v47 = 0;
      if ( v44 )
        goto LABEL_37;
      v52 = -1;
      do
        ++v52;
      while ( *(_WORD *)(*(_QWORD *)&v4[6] + 2 * v52) );
      v53 = 2 * (unsigned __int16)v52;
      if ( v53 > 0xFFFF )
      {
        LOWORD(v4[5].dwLowDateTime) = -1;
      }
      else
      {
        LOWORD(v4[5].dwLowDateTime) = v53;
        v54 = &pvData[HIWORD(v4[5].dwLowDateTime)];
        HIWORD(v4[1].dwLowDateTime) = v65;
        v4[2] = (struct _FILETIME)v54;
        pdwType = 1;
        v44 = RegGetValueW(hkey, lpSubKey, L"ProviderName", 0x20000002u, &pdwType, v54, &v65);
        v47 = 0;
        if ( v44 )
          goto LABEL_37;
        v55 = -1;
        do
          ++v55;
        while ( *(_WORD *)(*(_QWORD *)&v4[2] + 2 * v55) );
        v56 = 2 * (unsigned __int16)v55;
        if ( v56 > 0xFFFF )
        {
          LOWORD(v4[1].dwLowDateTime) = -1;
        }
        else
        {
          v57 = (unsigned int)Size;
          LOWORD(v4[1].dwLowDateTime) = v56;
          v58 = &v54[HIWORD(v4[1].dwLowDateTime)];
          v4[8] = (struct _FILETIME)v58;
          memmove_0(v58, Sid, (unsigned int)v57);
          if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
          {
            v14 = 0;
            goto LABEL_65;
          }
          HIWORD(v4[10].dwLowDateTime) = v66;
          v4[11] = (struct _FILETIME)&v58[v57];
          pdwType = 1;
          v44 = RegGetValueW(hkey, lpSubKey, L"DisplayName", 0x20000002u, &pdwType, &v58[v57], &v66);
          if ( v44 )
            goto LABEL_37;
          do
            ++v48;
          while ( *(_WORD *)(*(_QWORD *)&v4[11] + 2 * v48) );
          if ( 2 * (unsigned int)(unsigned __int16)v48 <= 0xFFFF )
          {
            LOWORD(v4[10].dwLowDateTime) = 2 * v48;
            v14 = 0;
            v5 = LocalAlloc(0x40u, v67);
            if ( !v5 )
            {
LABEL_35:
              v14 = -1073741801;
              goto LABEL_64;
            }
            pdwType = 1;
            v44 = RegGetValueW(hkey, lpSubKey, L"SecurityPrincipalType", 0x20000002u, &pdwType, v5, &v67);
            if ( v44 )
            {
LABEL_37:
              v14 = NetpApiStatusToNtStatus(v44, v47, v45, v46);
              goto LABEL_64;
            }
            RtlInitUnicodeString(&DestinationString, (PCWSTR)v5);
            v59 = LsapConvertUnicodeStringToSidNameUse(&DestinationString);
            v4[9].dwHighDateTime = v59;
            if ( v59 != SidTypeUnknown )
              goto LABEL_65;
LABEL_11:
            v14 = -1073741811;
            goto LABEL_64;
          }
          LOWORD(v4[10].dwLowDateTime) = -1;
        }
      }
    }
    v14 = -1073741675;
    goto LABEL_64;
  }
  LastError = GetLastError();
  v13 = NetpApiStatusToNtStatus(LastError, v10, v11, v12);
  v14 = v13;
  v15 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
  {
    v16 = 11;
LABEL_6:
    WPP_SF_Sd(
      *((_QWORD *)v15 + 12),
      v16,
      (unsigned int)&WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids,
      (_DWORD)lpSubKey,
      v13);
  }
LABEL_64:
  LsapDerefIdCacheEntry((struct _LSAP_IDENTITY_CACHE_ENTRY *)v4);
  v4 = 0;
LABEL_65:
  v60 = Sid;
  *a4 = v4;
  if ( v60 )
    LocalFree(v60);
  LocalFree(v5);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids, v14);
  return v14;
}

```

## disassembly

```asm
0x1800b28a0  mov     [rsp-8+arg_18], r9
0x1800b28a5  push    rbp
0x1800b28a6  push    rbx
0x1800b28a7  push    rsi
0x1800b28a8  push    rdi
0x1800b28a9  push    r12
0x1800b28ab  push    r13
0x1800b28ad  push    r14
0x1800b28af  push    r15
0x1800b28b1  lea     rbp, [rsp-1Fh]
0x1800b28b6  sub     rsp, 88h
0x1800b28bd  xor     ebx, ebx
0x1800b28bf  xorps   xmm0, xmm0
0x1800b28c2  mov     edi, ebx
0x1800b28c4  mov     [rbp+57h+var_7C], ebx
0x1800b28c7  mov     [rbp+57h+var_78], ebx
0x1800b28ca  mov     r13d, ebx
0x1800b28cd  mov     [rbp+57h+var_74], ebx
0x1800b28d0  mov     r12, r8
0x1800b28d3  mov     [rbp+57h+var_70], ebx
0x1800b28d6  mov     rsi, rdx
0x1800b28d9  mov     [rbp+57h+Sid], rbx
0x1800b28dd  mov     r14, rcx
0x1800b28e0  mov     [rbp+57h+var_80], ebx
0x1800b28e3  mov     [rbp+57h+var_6C], ebx
0x1800b28e6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800b28ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b28f1  lea     r15d, [rbx+10h]
0x1800b28f5  test    [rcx+6Ch], r15b
0x1800b28f9  jz      short loc_1800B290E
0x1800b28fb  mov     rcx, [rcx+60h]
0x1800b28ff  lea     edx, [rbx+0Ah]
0x1800b2902  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x1800b2909  call    WPP_SF_
0x1800b290e  lea     rdx, [rbp+57h+Sid]; Sid
0x1800b2912  mov     rcx, rsi; StringSid
0x1800b2915  call    cs:__imp_ConvertStringSidToSidW
0x1800b291c  nop     dword ptr [rax+rax+00h]
0x1800b2921  test    eax, eax
0x1800b2923  jnz     short loc_1800B296C
0x1800b2925  call    cs:__imp_GetLastError
0x1800b292c  nop     dword ptr [rax+rax+00h]
0x1800b2931  mov     ecx, eax
0x1800b2933  call    NetpApiStatusToNtStatus
0x1800b2938  mov     ebx, eax
0x1800b293a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2941  test    [rcx+6Ch], r15b
0x1800b2945  jz      loc_1800B2F17
0x1800b294b  mov     edx, 0Bh
0x1800b2950  mov     rcx, [rcx+60h]
0x1800b2954  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x1800b295b  mov     r9, rsi
0x1800b295e  mov     dword ptr [rsp+0C0h+pdwType], eax
0x1800b2962  call    WPP_SF_Sd
0x1800b2967  jmp     loc_1800B2F17
0x1800b296c  lea     rax, [rbp+57h+var_7C]
0x1800b2970  mov     [rbp+57h+var_7C], ebx
0x1800b2973  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800b2978  lea     r8, aUsername_0; "UserName"
0x1800b297f  lea     rax, [rbp+57h+var_80]
0x1800b2983  mov     [rsp+0C0h+pvData], rbx; pvData
0x1800b2988  mov     r9d, 2; dwFlags
0x1800b298e  mov     [rsp+0C0h+pdwType], rax; pdwType
0x1800b2993  mov     rdx, rsi; lpSubKey
0x1800b2996  mov     rcx, r14; hkey
0x1800b2999  call    cs:__imp_RegGetValueW
0x1800b29a0  nop     dword ptr [rax+rax+00h]
0x1800b29a5  test    eax, eax
0x1800b29a7  jz      short loc_1800B29CA
0x1800b29a9  mov     ecx, eax
0x1800b29ab  call    NetpApiStatusToNtStatus
0x1800b29b0  mov     ebx, eax
0x1800b29b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b29b9  test    [rcx+6Ch], r15b
0x1800b29bd  jz      loc_1800B2F17
0x1800b29c3  mov     edx, 0Ch
0x1800b29c8  jmp     short loc_1800B2950
0x1800b29ca  cmp     [rbp+57h+var_80], 1
0x1800b29ce  jz      short loc_1800B29DA
0x1800b29d0  mov     ebx, 0C000000Dh
0x1800b29d5  jmp     loc_1800B2F17
0x1800b29da  lea     rax, [rbp+57h+var_78]
0x1800b29de  mov     [rbp+57h+var_78], ebx
0x1800b29e1  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800b29e6  lea     r8, aSamname; "SAMName"
0x1800b29ed  lea     rax, [rbp+57h+var_80]
0x1800b29f1  mov     [rsp+0C0h+pvData], rbx; pvData
0x1800b29f6  mov     r9d, 2; dwFlags
0x1800b29fc  mov     [rsp+0C0h+pdwType], rax; pdwType
0x1800b2a01  mov     rdx, rsi; lpSubKey
0x1800b2a04  mov     rcx, r14; hkey
0x1800b2a07  call    cs:__imp_RegGetValueW
0x1800b2a0e  nop     dword ptr [rax+rax+00h]
0x1800b2a13  test    eax, eax
0x1800b2a15  jz      short loc_1800B2A3B
0x1800b2a17  mov     ecx, eax
0x1800b2a19  call    NetpApiStatusToNtStatus
0x1800b2a1e  mov     ebx, eax
0x1800b2a20  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2a27  test    [rcx+6Ch], r15b
0x1800b2a2b  jz      loc_1800B2F17
0x1800b2a31  mov     edx, 0Dh
0x1800b2a36  jmp     loc_1800B2950
0x1800b2a3b  cmp     [rbp+57h+var_80], 1
0x1800b2a3f  jnz     short loc_1800B29D0
0x1800b2a41  lea     rax, [rbp+57h+var_74]
0x1800b2a45  mov     [rbp+57h+var_74], ebx
0x1800b2a48  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800b2a4d  lea     r8, aProvidername; "ProviderName"
0x1800b2a54  lea     rax, [rbp+57h+var_80]
0x1800b2a58  mov     [rsp+0C0h+pvData], rbx; pvData
0x1800b2a5d  mov     r9d, 2; dwFlags
0x1800b2a63  mov     [rsp+0C0h+pdwType], rax; pdwType
0x1800b2a68  mov     rdx, rsi; lpSubKey
0x1800b2a6b  mov     rcx, r14; hkey
0x1800b2a6e  call    cs:__imp_RegGetValueW
0x1800b2a75  nop     dword ptr [rax+rax+00h]
0x1800b2a7a  test    eax, eax
0x1800b2a7c  jz      short loc_1800B2AA2
0x1800b2a7e  mov     ecx, eax
0x1800b2a80  call    NetpApiStatusToNtStatus
0x1800b2a85  mov     ebx, eax
0x1800b2a87  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2a8e  test    [rcx+6Ch], r15b
0x1800b2a92  jz      loc_1800B2F17
0x1800b2a98  mov     edx, 0Eh
0x1800b2a9d  jmp     loc_1800B2950
0x1800b2aa2  cmp     [rbp+57h+var_80], 1
0x1800b2aa6  jnz     loc_1800B29D0
0x1800b2aac  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x1800b2ab3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x1800b2ab8  test    al, al
0x1800b2aba  jz      loc_1800B2B8E
0x1800b2ac0  lea     rax, [rbp+57h+var_6C]
0x1800b2ac4  mov     r9d, 2; dwFlags
0x1800b2aca  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800b2acf  lea     r8, aSecurityprinci; "SecurityPrincipalType"
0x1800b2ad6  lea     rax, [rbp+57h+var_80]
0x1800b2ada  mov     [rsp+0C0h+pvData], rbx; pvData
0x1800b2adf  mov     rdx, rsi; lpSubKey
0x1800b2ae2  mov     [rsp+0C0h+pdwType], rax; pdwType
0x1800b2ae7  mov     rcx, r14; hkey
0x1800b2aea  call    cs:__imp_RegGetValueW
0x1800b2af1  nop     dword ptr [rax+rax+00h]
0x1800b2af6  test    eax, eax
0x1800b2af8  jz      short loc_1800B2B1E
0x1800b2afa  mov     ecx, eax
0x1800b2afc  call    NetpApiStatusToNtStatus
0x1800b2b01  mov     ebx, eax
0x1800b2b03  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2b0a  test    [rcx+6Ch], r15b
0x1800b2b0e  jz      loc_1800B2F17
0x1800b2b14  mov     edx, 0Fh
0x1800b2b19  jmp     loc_1800B2950
0x1800b2b1e  cmp     [rbp+57h+var_80], 1
0x1800b2b22  jnz     loc_1800B29D0
0x1800b2b28  lea     rax, [rbp+57h+var_70]
0x1800b2b2c  mov     r9d, 2; dwFlags
0x1800b2b32  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800b2b37  lea     r8, aDisplayname; "DisplayName"
0x1800b2b3e  lea     rax, [rbp+57h+var_80]
0x1800b2b42  mov     [rsp+0C0h+pvData], rbx; pvData
0x1800b2b47  mov     rdx, rsi; lpSubKey
0x1800b2b4a  mov     [rsp+0C0h+pdwType], rax; pdwType
0x1800b2b4f  mov     rcx, r14; hkey
0x1800b2b52  call    cs:__imp_RegGetValueW
0x1800b2b59  nop     dword ptr [rax+rax+00h]
0x1800b2b5e  test    eax, eax
0x1800b2b60  jz      short loc_1800B2B84
0x1800b2b62  mov     ecx, eax
0x1800b2b64  call    NetpApiStatusToNtStatus
0x1800b2b69  mov     ebx, eax
0x1800b2b6b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b2b72  test    [rcx+6Ch], r15b
0x1800b2b76  jz      loc_1800B2F17
0x1800b2b7c  mov     edx, r15d
0x1800b2b7f  jmp     loc_1800B2950
0x1800b2b84  cmp     [rbp+57h+var_80], 1
0x1800b2b88  jnz     loc_1800B29D0
0x1800b2b8e  mov     rcx, [rbp+57h+Sid]; Sid
0x1800b2b92  call    cs:__imp_RtlLengthSid
0x1800b2b99  nop     dword ptr [rax+rax+00h]
0x1800b2b9e  mov     edx, [rbp+57h+var_7C]
0x1800b2ba1  add     edx, 60h ; '`'
0x1800b2ba4  mov     dword ptr [rbp+57h+Size], eax
0x1800b2ba7  cmp     edx, 60h ; '`'
0x1800b2baa  jb      loc_1800B2F12
0x1800b2bb0  mov     ecx, [rbp+57h+var_78]
0x1800b2bb3  add     ecx, edx
0x1800b2bb5  cmp     ecx, edx
0x1800b2bb7  jb      loc_1800B2F12
0x1800b2bbd  mov     edx, [rbp+57h+var_74]
0x1800b2bc0  add     edx, ecx
0x1800b2bc2  cmp     edx, ecx
0x1800b2bc4  jb      loc_1800B2F12
0x1800b2bca  mov     ecx, [rbp+57h+var_70]
0x1800b2bcd  add     ecx, edx
0x1800b2bcf  cmp     ecx, edx
0x1800b2bd1  jb      loc_1800B2F12
0x1800b2bd7  lea     ebx, [rcx+rax]
0x1800b2bda  cmp     ebx, ecx
0x1800b2bdc  jb      loc_1800B2F12
0x1800b2be2  mov     edx, ebx; uBytes
0x1800b2be4  mov     ecx, 40h ; '@'; uFlags
0x1800b2be9  mov     r15d, ebx
0x1800b2bec  call    cs:__imp_LocalAlloc
0x1800b2bf3  nop     dword ptr [rax+rax+00h]
0x1800b2bf8  mov     rdi, rax
0x1800b2bfb  test    rax, rax
0x1800b2bfe  jnz     short loc_1800B2C0A
0x1800b2c00  mov     ebx, 0C0000017h
0x1800b2c05  jmp     loc_1800B2F17
0x1800b2c0a  mov     r8, r15; Size
0x1800b2c0d  xor     edx, edx; Val
0x1800b2c0f  mov     rcx, rdi; void *
0x1800b2c12  call    memset_0
0x1800b2c17  mov     [rdi], ebx
0x1800b2c19  lock inc dword ptr [rdi+4]
0x1800b2c1d  mov     dword ptr [rdi+4Ch], 8
0x1800b2c24  lea     r15, [rdi+60h]
0x1800b2c28  mov     rax, [r12]
0x1800b2c2c  lea     r8, aUsername_0; "UserName"
0x1800b2c33  mov     [rdi+38h], rax
0x1800b2c37  mov     r9d, 20000002h; dwFlags
0x1800b2c3d  movzx   eax, word ptr [rbp+57h+var_7C]
0x1800b2c41  mov     rdx, rsi; lpSubKey
0x1800b2c44  mov     [rdi+1Ah], ax
0x1800b2c48  mov     rcx, r14; hkey
0x1800b2c4b  lea     rax, [rbp+57h+var_7C]
0x1800b2c4f  mov     [rdi+20h], r15
0x1800b2c53  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800b2c58  lea     rax, [rbp+57h+var_80]
0x1800b2c5c  mov     [rsp+0C0h+pvData], r15; pvData
0x1800b2c61  mov     [rsp+0C0h+pdwType], rax; pdwType
0x1800b2c66  mov     [rbp+57h+var_80], 1
0x1800b2c6d  call    cs:__imp_RegGetValueW
0x1800b2c74  nop     dword ptr [rax+rax+00h]
0x1800b2c79  xor     edx, edx
0x1800b2c7b  test    eax, eax
0x1800b2c7d  jz      short loc_1800B2C8D
0x1800b2c7f  mov     ecx, eax
0x1800b2c81  call    NetpApiStatusToNtStatus
0x1800b2c86  mov     ebx, eax
0x1800b2c88  jmp     loc_1800B2F17
0x1800b2c8d  mov     rcx, [rdi+20h]
0x1800b2c91  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800b2c95  mov     rax, rbx
0x1800b2c98  inc     rax
0x1800b2c9b  cmp     [rcx+rax*2], dx
0x1800b2c9f  jnz     short loc_1800B2C98
0x1800b2ca1  movzx   ecx, ax
0x1800b2ca4  mov     r12d, 0FFFFh
0x1800b2caa  add     ecx, ecx
0x1800b2cac  cmp     ecx, r12d
0x1800b2caf  ja      loc_1800B2F06
0x1800b2cb5  mov     [rdi+18h], cx
0x1800b2cb9  lea     r8, aSamname; "SAMName"
0x1800b2cc0  movzx   eax, word ptr [rdi+1Ah]
0x1800b2cc4  mov     r9d, 20000002h; dwFlags
0x1800b2cca  add     r15, rax
0x1800b2ccd  mov     rdx, rsi; lpSubKey
0x1800b2cd0  movzx   eax, word ptr [rbp+57h+var_78]
0x1800b2cd4  mov     rcx, r14; hkey
0x1800b2cd7  mov     [rdi+2Ah], ax
0x1800b2cdb  lea     rax, [rbp+57h+var_78]
0x1800b2cdf  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800b2ce4  lea     rax, [rbp+57h+var_80]
0x1800b2ce8  mov     [rdi+30h], r15
0x1800b2cec  mov     [rsp+0C0h+pvData], r15; pvData
0x1800b2cf1  mov     [rsp+0C0h+pdwType], rax; pdwType
0x1800b2cf6  mov     [rbp+57h+var_80], 1
0x1800b2cfd  call    cs:__imp_RegGetValueW
0x1800b2d04  nop     dword ptr [rax+rax+00h]
0x1800b2d09  xor     edx, edx
0x1800b2d0b  test    eax, eax
0x1800b2d0d  jnz     loc_1800B2C7F
0x1800b2d13  mov     rcx, [rdi+30h]
0x1800b2d17  mov     rax, rbx
0x1800b2d1a  inc     rax
0x1800b2d1d  cmp     [rcx+rax*2], dx
0x1800b2d21  jnz     short loc_1800B2D1A
0x1800b2d23  movzx   ecx, ax
0x1800b2d26  add     ecx, ecx
0x1800b2d28  cmp     ecx, r12d
0x1800b2d2b  ja      loc_1800B2EFF
0x1800b2d31  mov     [rdi+28h], cx
0x1800b2d35  lea     r8, aProvidername; "ProviderName"
0x1800b2d3c  movzx   eax, word ptr [rdi+2Ah]
0x1800b2d40  mov     r9d, 20000002h; dwFlags
0x1800b2d46  add     r15, rax
0x1800b2d49  mov     rdx, rsi; lpSubKey
0x1800b2d4c  movzx   eax, word ptr [rbp+57h+var_74]
0x1800b2d50  mov     rcx, r14; hkey
0x1800b2d53  mov     [rdi+0Ah], ax
0x1800b2d57  lea     rax, [rbp+57h+var_74]
0x1800b2d5b  mov     [rsp+0C0h+pcbData], rax; pcbData
0x1800b2d60  lea     rax, [rbp+57h+var_80]
0x1800b2d64  mov     [rdi+10h], r15
0x1800b2d68  mov     [rsp+0C0h+pvData], r15; pvData
0x1800b2d6d  mov     [rsp+0C0h+pdwType], rax; pdwType
  ... truncated ...
```
