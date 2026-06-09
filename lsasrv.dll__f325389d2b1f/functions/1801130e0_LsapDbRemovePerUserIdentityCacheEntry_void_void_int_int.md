# LsapDbRemovePerUserIdentityCacheEntry(void *,void *,int,int)

- ea: `0x1801130e0`
- end: `0x1801137b1`
- name: `?LsapDbRemovePerUserIdentityCacheEntry@@YAJPEAX0HH@Z`
- size: `1745`
- prototype: `__int64 __fastcall(void *, void *, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800cdc60`
- `0x1800eccb0`

## callees

- `0x180011278`
- `0x18003a848`
- `0x1800638ec`
- `0x1800642ec`
- `0x18008e360`
- `0x1800ada18`
- `0x1800b2fd4`
- `0x1800c7258`
- `0x1801130e0`
- `0x180114630`
- `0x1801146fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801134fa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801134fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011323d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113352`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011323d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113352`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801131fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113529`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011372b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113740`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113755`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113769`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801131fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113529`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18011372b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113740`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113755`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113769`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011342f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18011342f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801135eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113716`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1801135eb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113716`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011328d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113617`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18011328d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113617`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801133c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1801133c5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180113488`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180113488`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1801132ec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180113642`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1801132ec`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180113642`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801131dc`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x1801131dc`
- `ntdll!RtlAcquireResourceExclusive` at `0x18011319d`
- `ntdll!RtlAcquireResourceExclusive` at `0x18011319d`
- `ntdll!RtlReleaseResource` at `0x18011320d`
- `ntdll!RtlReleaseResource` at `0x180113690`
- `ntdll!RtlReleaseResource` at `0x1801136eb`
- `ntdll!RtlReleaseResource` at `0x18011320d`
- `ntdll!RtlReleaseResource` at `0x180113690`
- `ntdll!RtlReleaseResource` at `0x1801136eb`
- `ntdll!RtlAcquireResourceShared` at `0x1801134db`
- `ntdll!RtlAcquireResourceShared` at `0x1801134db`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113540`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113540`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18011322d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180113342`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18011322d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180113342`

## string_xrefs

- `0x1801135c9`: `IdentityCache`

## pseudocode

```c
__int64 __fastcall LsapDbRemovePerUserIdentityCacheEntry(void *a1, void *a2, int a3, int a4)
{
  WCHAR *v5; // rsi
  int v9; // ebx
  LsaHandleCache *v10; // r10
  __int64 v11; // rdx
  __int64 v12; // r9
  HKEY v13; // rcx
  DWORD LastError; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int v18; // eax
  unsigned int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  char v23; // al
  __int64 v24; // r10
  unsigned int v25; // eax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // r9
  unsigned int v29; // eax
  __int64 v30; // r10
  DWORD v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // r9
  unsigned int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  DWORD v39; // ecx
  unsigned __int64 v40; // rcx
  DWORD v41; // r14d
  int v42; // edi
  unsigned int v43; // eax
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // r9
  unsigned int v47; // eax
  __int64 v48; // r10
  __int64 v49; // rdx
  struct _PER_USER_CACHE_ENTRY *v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  int v54; // ecx
  unsigned int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  unsigned int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // r9
  char v63; // al
  __int64 v64; // r10
  char v65; // al
  __int64 v66; // r10
  struct _PER_USER_CACHE_ENTRY *Buffer; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-21h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-19h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-11h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp-9h] BYREF
  LPWSTR v73; // [rsp+88h] [rbp-1h] BYREF
  DWORD cbMaxValueLen; // [rsp+90h] [rbp+7h] BYREF
  DWORD cchName; // [rsp+94h] [rbp+Bh] BYREF
  struct _LSAP_IDENTITY_CACHE_ENTRY *v76[9]; // [rsp+98h] [rbp+Fh] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+108h] [rbp+7Fh] BYREF

  cSubKeys = 0;
  v5 = 0;
  cbMaxSubKeyLen = 0;
  cbMaxValueLen = 0;
  Buffer = 0;
  v76[0] = 0;
  hKey = 0;
  StringSid = 0;
  v73 = 0;
  hMem = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 67, &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids);
  if ( !a4 )
  {
    if ( !a1 )
    {
      v9 = -1073741811;
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
        goto LABEL_79;
      v11 = 68;
      v12 = 3221225485LL;
      goto LABEL_7;
    }
    RtlAcquireResourceExclusive(&LsapIdentityCacheLock, 1u);
    if ( (int)LsapFindPerLocalUserCacheEntry(a1, &Buffer) >= 0 )
    {
      LsapClearPerUserCacheEntry(Buffer);
      hKey = (HKEY)*((_QWORD *)Buffer + 55);
      if ( !RtlDeleteElementGenericTableAvl(&g_PerUserCacheTable, &Buffer) )
      {
        v9 = -1073741823;
        goto LABEL_76;
      }
      LocalFree(Buffer);
    }
    RtlReleaseResource(&LsapIdentityCacheLock);
    v13 = hKey;
    if ( hKey )
      goto LABEL_23;
    if ( !ConvertSidToStringSidW(a1, &StringSid) )
    {
      LastError = GetLastError();
      v18 = NetpApiStatusToNtStatus(LastError, v15, v16, v17);
      v9 = v18;
      v10 = WPP_GLOBAL_Control;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
        goto LABEL_79;
      v11 = 69;
LABEL_16:
      v12 = v18;
LABEL_7:
      WPP_SF_d(*((_QWORD *)v10 + 12), v11, &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids, v12);
      goto LABEL_79;
    }
    v19 = RegOpenKeyExW(g_hKeyCacheRoot, StringSid, 0, 0x2001Fu, &hKey);
    if ( (v19 - 4 <= 0x48B || v19 == 1 || v19 >= 0x491) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
    {
      v23 = NetpApiStatusToNtStatus(v19, v20, v21, v22);
      WPP_SF_Sd(
        *(_QWORD *)(v24 + 96),
        70,
        (unsigned int)&WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids,
        (_DWORD)StringSid,
        v23);
    }
    v13 = hKey;
    if ( hKey )
    {
LABEL_23:
      v25 = RegDeleteTreeW(v13, 0);
      if ( (v25 - 4 <= 0x48B || v25 == 1 || v25 >= 0x491) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
      {
        v29 = NetpApiStatusToNtStatus(v25, v26, v27, v28);
        WPP_SF_d(*(_QWORD *)(v30 + 96), 71, &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids, v29);
      }
    }
  }
  if ( !ConvertSidToStringSidW(a2, &v73) )
  {
    v31 = GetLastError();
    v18 = NetpApiStatusToNtStatus(v31, v32, v33, v34);
    v9 = v18;
    v10 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
      goto LABEL_79;
    v11 = 72;
    goto LABEL_16;
  }
  v35 = RegQueryInfoKeyW(g_hKeyCacheRoot, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, &cbMaxValueLen, 0, 0);
  if ( v35 )
  {
    v18 = NetpApiStatusToNtStatus(v35, v36, v37, v38);
    v9 = v18;
    v10 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
      goto LABEL_79;
    v11 = 73;
    goto LABEL_16;
  }
  v39 = cbMaxSubKeyLen + 13;
  if ( cbMaxSubKeyLen + 13 < cbMaxSubKeyLen || cbMaxSubKeyLen + 15 < cbMaxSubKeyLen + 13 )
  {
    v9 = -1073741675;
    cbMaxSubKeyLen = -1;
    goto LABEL_79;
  }
  cbMaxSubKeyLen += 15;
  v40 = 2LL * (v39 + 2);
  if ( v40 > 0xFFFFFFFF )
  {
    v9 = -2147483643;
    goto LABEL_79;
  }
  v5 = (WCHAR *)LocalAlloc(0x40u, (unsigned int)v40);
  if ( !v5 )
  {
    v9 = -1073741801;
    goto LABEL_79;
  }
  v41 = 0;
  v42 = 0;
  while ( v41 < cSubKeys )
  {
    cchName = cbMaxSubKeyLen;
    v43 = RegEnumKeyExW(g_hKeyCacheRoot, v41, v5, &cchName, 0, 0, 0, 0);
    if ( v43 )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) == 0 )
        goto LABEL_73;
      v47 = NetpApiStatusToNtStatus(v43, v44, v45, v46);
      v49 = 74;
      goto LABEL_44;
    }
    if ( !v42 )
    {
      RtlAcquireResourceShared(&LsapIdentityCacheLock, 1u);
      v42 = 1;
    }
    Buffer = 0;
    if ( !(unsigned int)_o__wcsicmp(L"GlobalStore", v5) )
    {
      if ( !a3 )
        goto LABEL_73;
      v50 = g_pGlobalCache;
      Buffer = g_pGlobalCache;
      goto LABEL_56;
    }
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( ConvertStringSidToSidW(v5, &hMem) )
    {
      LsapFindPerLocalUserCacheEntry(hMem, &Buffer);
      v50 = Buffer;
LABEL_56:
      if ( v50 && (int)LsapLookupIdentityInGivenCacheBySID(v50, a2, v76) >= 0 && v76[0] )
        LsapRemoveIdentityCacheEntry(Buffer, v76);
      v9 = RtlStringCchCatW(v5, cbMaxSubKeyLen, L"\\");
      if ( v9 < 0 )
        goto LABEL_75;
      v9 = RtlStringCchCatW(v5, cbMaxSubKeyLen, L"IdentityCache");
      if ( v9 < 0 )
        goto LABEL_75;
      if ( hKey )
      {
        RegCloseKey(hKey);
        hKey = 0;
      }
      v55 = RegOpenKeyExW(g_hKeyCacheRoot, v5, 0, 0x2001Fu, &hKey);
      if ( v55 - 4 <= 0x48B || v55 == 1 || v55 >= 0x491 )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
        {
          v65 = NetpApiStatusToNtStatus(v55, v56, v57, v58);
          WPP_SF_Sd(
            *(_QWORD *)(v66 + 96),
            76,
            (unsigned int)&WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids,
            (_DWORD)v5,
            v65);
        }
      }
      else
      {
        v59 = RegDeleteTreeW(hKey, v73);
        if ( v59 && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
        {
          v63 = NetpApiStatusToNtStatus(v59, v60, v61, v62);
          WPP_SF_SSD(
            *(_QWORD *)(v64 + 96),
            77,
            (unsigned int)&WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids,
            (_DWORD)v73,
            (__int64)v5,
            v63);
        }
        RtlReleaseResource(&LsapIdentityCacheLock);
        v42 = 0;
      }
      goto LABEL_73;
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
    {
      v47 = NetpApiStatusToNtStatus(0, v51, v52, v53);
      v49 = (unsigned int)(v54 + 75);
LABEL_44:
      WPP_SF_d(*(_QWORD *)(v48 + 96), v49, &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids, v47);
    }
LABEL_73:
    ++v41;
  }
  v9 = 0;
LABEL_75:
  if ( v42 )
LABEL_76:
    RtlReleaseResource(&LsapIdentityCacheLock);
LABEL_79:
  if ( hKey )
    RegCloseKey(hKey);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v73 )
    LocalFree(v73);
  if ( hMem )
    LocalFree(hMem);
  if ( v5 )
    LocalFree(v5);
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      78,
      &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids,
      (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1801130e0  push    rbp
0x1801130e2  push    rbx
0x1801130e3  push    rsi
0x1801130e4  push    rdi
0x1801130e5  push    r12
0x1801130e7  push    r13
0x1801130e9  push    r14
0x1801130eb  push    r15
0x1801130ed  lea     rbp, [rsp-1Fh]
0x1801130f2  sub     rsp, 0A8h
0x1801130f9  xor     r13d, r13d
0x1801130fc  mov     edi, r9d
0x1801130ff  mov     [rbp+57h+cSubKeys], r13d
0x180113103  mov     esi, r13d
0x180113106  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18011310a  mov     r12d, r8d
0x18011310d  mov     [rbp+57h+cbMaxValueLen], r13d
0x180113111  mov     r15, rdx
0x180113114  mov     [rbp+57h+Buffer], r13
0x180113118  mov     rbx, rcx
0x18011311b  mov     [rbp+57h+var_48], r13
0x18011311f  mov     [rbp+57h+hKey], r13
0x180113123  mov     [rbp+57h+StringSid], r13
0x180113127  mov     [rbp+57h+var_58], r13
0x18011312b  mov     [rbp+57h+hMem], r13
0x18011312f  mov     r10, cs:WPP_GLOBAL_Control
0x180113136  mov     r14b, 10h
0x180113139  test    [r10+6Ch], r14b
0x18011313d  jz      short loc_180113153
0x18011313f  mov     rcx, [r10+60h]
0x180113143  lea     edx, [r13+43h]
0x180113147  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x18011314e  call    WPP_SF_
0x180113153  test    edi, edi
0x180113155  jnz     loc_18011333B
0x18011315b  test    rbx, rbx
0x18011315e  jnz     short loc_180113194
0x180113160  mov     ebx, 0C000000Dh
0x180113165  mov     r10, cs:WPP_GLOBAL_Control
0x18011316c  test    [r10+6Ch], r14b
0x180113170  jz      loc_18011370D
0x180113176  lea     edx, [rdi+44h]
0x180113179  mov     r9d, 0C000000Dh
0x18011317f  mov     rcx, [r10+60h]
0x180113183  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x18011318a  call    WPP_SF_d
0x18011318f  jmp     loc_18011370D
0x180113194  mov     dl, 1; Wait
0x180113196  lea     rcx, ?LsapIdentityCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18011319d  call    cs:__imp_RtlAcquireResourceExclusive
0x1801131a4  nop     dword ptr [rax+rax+00h]
0x1801131a9  lea     rdx, [rbp+57h+Buffer]; struct _PER_USER_CACHE_ENTRY **
0x1801131ad  mov     rcx, rbx; void *
0x1801131b0  call    ?LsapFindPerLocalUserCacheEntry@@YAJPEAXPEAPEAU_PER_USER_CACHE_ENTRY@@@Z; LsapFindPerLocalUserCacheEntry(void *,_PER_USER_CACHE_ENTRY * *)
0x1801131b5  test    eax, eax
0x1801131b7  js      short loc_180113206
0x1801131b9  mov     rcx, [rbp+57h+Buffer]; struct _PER_USER_CACHE_ENTRY *
0x1801131bd  call    ?LsapClearPerUserCacheEntry@@YAXPEAU_PER_USER_CACHE_ENTRY@@@Z; LsapClearPerUserCacheEntry(_PER_USER_CACHE_ENTRY *)
0x1801131c2  mov     rax, [rbp+57h+Buffer]
0x1801131c6  lea     rdx, [rbp+57h+Buffer]; Buffer
0x1801131ca  mov     rcx, [rax+1B8h]
0x1801131d1  mov     [rbp+57h+hKey], rcx
0x1801131d5  lea     rcx, ?g_PerUserCacheTable@@3U_RTL_AVL_TABLE@@A; Table
0x1801131dc  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1801131e3  nop     dword ptr [rax+rax+00h]
0x1801131e8  test    al, al
0x1801131ea  jnz     short loc_1801131F6
0x1801131ec  mov     ebx, 0C0000001h
0x1801131f1  jmp     loc_1801136E4
0x1801131f6  mov     rcx, [rbp+57h+Buffer]; hMem
0x1801131fa  call    cs:__imp_LocalFree
0x180113201  nop     dword ptr [rax+rax+00h]
0x180113206  lea     rcx, ?LsapIdentityCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18011320d  call    cs:__imp_RtlReleaseResource
0x180113214  nop     dword ptr [rax+rax+00h]
0x180113219  mov     rcx, [rbp+57h+hKey]
0x18011321d  test    rcx, rcx
0x180113220  jnz     loc_1801132EA
0x180113226  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18011322a  mov     rcx, rbx; Sid
0x18011322d  call    cs:__imp_ConvertSidToStringSidW
0x180113234  nop     dword ptr [rax+rax+00h]
0x180113239  test    eax, eax
0x18011323b  jnz     short loc_180113270
0x18011323d  call    cs:__imp_GetLastError
0x180113244  nop     dword ptr [rax+rax+00h]
0x180113249  mov     ecx, eax
0x18011324b  call    NetpApiStatusToNtStatus
0x180113250  mov     ebx, eax
0x180113252  mov     r10, cs:WPP_GLOBAL_Control
0x180113259  test    [r10+6Ch], r14b
0x18011325d  jz      loc_18011370D
0x180113263  mov     edx, 45h ; 'E'
0x180113268  mov     r9d, eax
0x18011326b  jmp     loc_18011317F
0x180113270  mov     rdx, [rbp+57h+StringSid]; lpSubKey
0x180113274  lea     rax, [rbp+57h+hKey]
0x180113278  mov     rcx, cs:?g_hKeyCacheRoot@@3PEAUHKEY__@@EA; hKey
0x18011327f  mov     r9d, 2001Fh; samDesired
0x180113285  xor     r8d, r8d; ulOptions
0x180113288  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18011328d  call    cs:__imp_RegOpenKeyExW
0x180113294  nop     dword ptr [rax+rax+00h]
0x180113299  lea     ecx, [rax-4]
0x18011329c  cmp     ecx, 48Bh
0x1801132a2  jbe     short loc_1801132B0
0x1801132a4  cmp     eax, 1
0x1801132a7  jz      short loc_1801132B0
0x1801132a9  cmp     eax, 491h
0x1801132ae  jb      short loc_1801132E1
0x1801132b0  mov     r10, cs:WPP_GLOBAL_Control
0x1801132b7  test    [r10+6Ch], r14b
0x1801132bb  jz      short loc_1801132E1
0x1801132bd  mov     ecx, eax
0x1801132bf  call    NetpApiStatusToNtStatus
0x1801132c4  mov     r9, [rbp+57h+StringSid]
0x1801132c8  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x1801132cf  mov     rcx, [r10+60h]
0x1801132d3  mov     edx, 46h ; 'F'
0x1801132d8  mov     dword ptr [rsp+0E0h+phkResult], eax
0x1801132dc  call    WPP_SF_Sd
0x1801132e1  mov     rcx, [rbp+57h+hKey]; hKey
0x1801132e5  test    rcx, rcx
0x1801132e8  jz      short loc_18011333B
0x1801132ea  xor     edx, edx; lpSubKey
0x1801132ec  call    cs:__imp_RegDeleteTreeW
0x1801132f3  nop     dword ptr [rax+rax+00h]
0x1801132f8  lea     ecx, [rax-4]
0x1801132fb  cmp     ecx, 48Bh
0x180113301  jbe     short loc_18011330F
0x180113303  cmp     eax, 1
0x180113306  jz      short loc_18011330F
0x180113308  cmp     eax, 491h
0x18011330d  jb      short loc_18011333B
0x18011330f  mov     r10, cs:WPP_GLOBAL_Control
0x180113316  test    [r10+6Ch], r14b
0x18011331a  jz      short loc_18011333B
0x18011331c  mov     ecx, eax
0x18011331e  call    NetpApiStatusToNtStatus
0x180113323  mov     rcx, [r10+60h]
0x180113327  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x18011332e  mov     r9d, eax
0x180113331  mov     edx, 47h ; 'G'
0x180113336  call    WPP_SF_d
0x18011333b  lea     rdx, [rbp+57h+var_58]; StringSid
0x18011333f  mov     rcx, r15; Sid
0x180113342  call    cs:__imp_ConvertSidToStringSidW
0x180113349  nop     dword ptr [rax+rax+00h]
0x18011334e  test    eax, eax
0x180113350  jnz     short loc_180113382
0x180113352  call    cs:__imp_GetLastError
0x180113359  nop     dword ptr [rax+rax+00h]
0x18011335e  mov     ecx, eax
0x180113360  call    NetpApiStatusToNtStatus
0x180113365  mov     ebx, eax
0x180113367  mov     r10, cs:WPP_GLOBAL_Control
0x18011336e  test    [r10+6Ch], r14b
0x180113372  jz      loc_18011370D
0x180113378  mov     edx, 48h ; 'H'
0x18011337d  jmp     loc_180113268
0x180113382  mov     rcx, cs:?g_hKeyCacheRoot@@3PEAUHKEY__@@EA; hKey
0x180113389  lea     rax, [rbp+57h+cbMaxValueLen]
0x18011338d  mov     [rsp+0E0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180113392  xor     r9d, r9d; lpReserved
0x180113395  mov     [rsp+0E0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18011339a  xor     r8d, r8d; lpcchClass
0x18011339d  mov     [rsp+0E0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1801133a2  xor     edx, edx; lpClass
0x1801133a4  mov     [rsp+0E0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1801133a9  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x1801133ad  mov     [rsp+0E0h+lpcValues], r13; lpcValues
0x1801133b2  mov     [rsp+0E0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1801133b7  mov     [rsp+0E0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1801133bc  lea     rax, [rbp+57h+cSubKeys]
0x1801133c0  mov     [rsp+0E0h+phkResult], rax; lpcSubKeys
0x1801133c5  call    cs:__imp_RegQueryInfoKeyW
0x1801133cc  nop     dword ptr [rax+rax+00h]
0x1801133d1  test    eax, eax
0x1801133d3  jz      short loc_1801133F9
0x1801133d5  mov     ecx, eax
0x1801133d7  call    NetpApiStatusToNtStatus
0x1801133dc  mov     ebx, eax
0x1801133de  mov     r10, cs:WPP_GLOBAL_Control
0x1801133e5  test    [r10+6Ch], r14b
0x1801133e9  jz      loc_18011370D
0x1801133ef  mov     edx, 49h ; 'I'
0x1801133f4  jmp     loc_180113268
0x1801133f9  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1801133fc  lea     ecx, [rax+0Dh]
0x1801133ff  cmp     ecx, eax
0x180113401  jb      loc_180113700
0x180113407  lea     eax, [rcx+2]
0x18011340a  cmp     eax, ecx
0x18011340c  jb      loc_180113700
0x180113412  mov     ecx, eax
0x180113414  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x180113417  add     rcx, rcx
0x18011341a  mov     eax, 0FFFFFFFFh
0x18011341f  cmp     rcx, rax
0x180113422  ja      loc_1801136F9
0x180113428  mov     edx, ecx; uBytes
0x18011342a  mov     ecx, 40h ; '@'; uFlags
0x18011342f  call    cs:__imp_LocalAlloc
0x180113436  nop     dword ptr [rax+rax+00h]
0x18011343b  mov     rsi, rax
0x18011343e  test    rax, rax
0x180113441  jnz     short loc_18011344D
0x180113443  mov     ebx, 0C0000017h
0x180113448  jmp     loc_18011370D
0x18011344d  mov     r14d, r13d
0x180113450  mov     edi, r13d
0x180113453  cmp     r14d, [rbp+57h+cSubKeys]
0x180113457  jnb     loc_1801136DA
0x18011345d  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x180113460  lea     r9, [rbp+57h+cchName]; lpcchName
0x180113464  mov     rcx, cs:?g_hKeyCacheRoot@@3PEAUHKEY__@@EA; hKey
0x18011346b  mov     r8, rsi; lpName
0x18011346e  mov     [rsp+0E0h+lpcValues], r13; lpftLastWriteTime
0x180113473  mov     edx, r14d; dwIndex
0x180113476  mov     [rsp+0E0h+lpcbMaxClassLen], r13; lpcchClass
0x18011347b  mov     [rsp+0E0h+lpcbMaxSubKeyLen], r13; lpClass
0x180113480  mov     [rsp+0E0h+phkResult], r13; lpReserved
0x180113485  mov     [rbp+57h+cchName], eax
0x180113488  call    cs:__imp_RegEnumKeyExW
0x18011348f  nop     dword ptr [rax+rax+00h]
0x180113494  test    eax, eax
0x180113496  jz      short loc_1801134CE
0x180113498  mov     r10, cs:WPP_GLOBAL_Control
0x18011349f  test    byte ptr [r10+6Ch], 10h
0x1801134a4  jz      loc_1801136D2
0x1801134aa  mov     ecx, eax
0x1801134ac  call    NetpApiStatusToNtStatus
0x1801134b1  mov     edx, 4Ah ; 'J'
0x1801134b6  mov     rcx, [r10+60h]
0x1801134ba  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x1801134c1  mov     r9d, eax
0x1801134c4  call    WPP_SF_d
0x1801134c9  jmp     loc_1801136D2
0x1801134ce  test    edi, edi
0x1801134d0  jnz     short loc_1801134EC
0x1801134d2  mov     dl, 1; Wait
0x1801134d4  lea     rcx, ?LsapIdentityCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x1801134db  call    cs:__imp_RtlAcquireResourceShared
0x1801134e2  nop     dword ptr [rax+rax+00h]
0x1801134e7  mov     edi, 1
0x1801134ec  mov     rdx, rsi
0x1801134ef  mov     [rbp+57h+Buffer], r13
0x1801134f3  lea     rcx, aGlobalstore; "GlobalStore"
0x1801134fa  call    cs:__imp__o__wcsicmp
0x180113501  nop     dword ptr [rax+rax+00h]
0x180113506  test    eax, eax
0x180113508  jnz     short loc_180113520
0x18011350a  test    r12d, r12d
0x18011350d  jz      loc_1801136D2
0x180113513  mov     rcx, cs:?g_pGlobalCache@@3PEAU_PER_USER_CACHE_ENTRY@@EA; _PER_USER_CACHE_ENTRY * g_pGlobalCache
0x18011351a  mov     [rbp+57h+Buffer], rcx
0x18011351e  jmp     short loc_180113582
0x180113520  mov     rcx, [rbp+57h+hMem]; hMem
0x180113524  test    rcx, rcx
0x180113527  jz      short loc_180113539
0x180113529  call    cs:__imp_LocalFree
0x180113530  nop     dword ptr [rax+rax+00h]
0x180113535  mov     [rbp+57h+hMem], r13
0x180113539  lea     rdx, [rbp+57h+hMem]; Sid
0x18011353d  mov     rcx, rsi; StringSid
0x180113540  call    cs:__imp_ConvertStringSidToSidW
0x180113547  nop     dword ptr [rax+rax+00h]
0x18011354c  test    eax, eax
0x18011354e  jnz     short loc_180113571
0x180113550  mov     r10, cs:WPP_GLOBAL_Control
0x180113557  test    byte ptr [r10+6Ch], 10h
0x18011355c  jz      loc_1801136D2
0x180113562  xor     ecx, ecx
0x180113564  call    NetpApiStatusToNtStatus
0x180113569  lea     edx, [rcx+4Bh]
0x18011356c  jmp     loc_1801134B6
0x180113571  mov     rcx, [rbp+57h+hMem]; void *
0x180113575  lea     rdx, [rbp+57h+Buffer]; struct _PER_USER_CACHE_ENTRY **
0x180113579  call    ?LsapFindPerLocalUserCacheEntry@@YAJPEAXPEAPEAU_PER_USER_CACHE_ENTRY@@@Z; LsapFindPerLocalUserCacheEntry(void *,_PER_USER_CACHE_ENTRY * *)
0x18011357e  mov     rcx, [rbp+57h+Buffer]; struct _PER_USER_CACHE_ENTRY *
0x180113582  test    rcx, rcx
0x180113585  jz      short loc_1801135AA
0x180113587  lea     r8, [rbp+57h+var_48]; struct _LSAP_IDENTITY_CACHE_ENTRY **
0x18011358b  mov     rdx, r15; void *
0x18011358e  call    ?LsapLookupIdentityInGivenCacheBySID@@YAJPEAU_PER_USER_CACHE_ENTRY@@PEAXPEAPEAU_LSAP_IDENTITY_CACHE_ENTRY@@@Z; LsapLookupIdentityInGivenCacheBySID(_PER_USER_CACHE_ENTRY *,void *,_LSAP_IDENTITY_CACHE_ENTRY * *)
0x180113593  test    eax, eax
0x180113595  js      short loc_1801135AA
0x180113597  cmp     [rbp+57h+var_48], r13
0x18011359b  jz      short loc_1801135AA
0x18011359d  mov     rcx, [rbp+57h+Buffer]; struct _PER_USER_CACHE_ENTRY *
0x1801135a1  lea     rdx, [rbp+57h+var_48]; struct _LSAP_IDENTITY_CACHE_ENTRY **
0x1801135a5  call    ?LsapRemoveIdentityCacheEntry@@YAXPEAU_PER_USER_CACHE_ENTRY@@PEAPEAU_LSAP_IDENTITY_CACHE_ENTRY@@@Z; LsapRemoveIdentityCacheEntry(_PER_USER_CACHE_ENTRY *,_LSAP_IDENTITY_CACHE_ENTRY * *)
0x1801135aa  mov     edx, [rbp+57h+cbMaxSubKeyLen]; unsigned __int64
0x1801135ad  lea     r8, Source; "\\"
0x1801135b4  mov     rcx, rsi; unsigned __int16 *
0x1801135b7  call    ?RtlStringCchCatW@@YAJPEAG_KPEBG@Z; RtlStringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801135bc  mov     ebx, eax
0x1801135be  test    eax, eax
0x1801135c0  js      loc_1801136DD
0x1801135c6  mov     edx, [rbp+57h+cbMaxSubKeyLen]; unsigned __int64
  ... truncated ...
```
