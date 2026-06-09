# LsapInitializePerUserCacheEntry(uchar,void *,_PER_USER_CACHE_ENTRY * *)

- ea: `0x180113920`
- end: `0x180113c7f`
- name: `?LsapInitializePerUserCacheEntry@@YAJEPEAXPEAPEAU_PER_USER_CACHE_ENTRY@@@Z`
- size: `863`
- prototype: `int(unsigned __int8, void *, struct _PER_USER_CACHE_ENTRY **)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180062e88`
- `0x1800641bc`
- `0x180064da4`

## callees

- `0x180011278`
- `0x180014954`
- `0x18003a848`
- `0x1800626ac`
- `0x18008e360`
- `0x1800bd6ec`
- `0x1801082a8`
- `0x180113920`
- `0x180113fd0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113982`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113982`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113c13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113c36`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113c13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113c36`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180113a1a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180113a1a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113c04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180113c04`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113b83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180113b83`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180113a58`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180113a7e`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180113ab7`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180113ae0`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180113a58`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180113a7e`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180113ab7`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180113ae0`
- `ntdll!RtlConvertExclusiveToShared` at `0x180113bbd`
- `ntdll!RtlConvertExclusiveToShared` at `0x180113bbd`
- `ntdll!RtlConvertSharedToExclusive` at `0x180113b9e`
- `ntdll!RtlConvertSharedToExclusive` at `0x180113b9e`
- `ntdll!RtlLengthSid` at `0x18011399f`
- `ntdll!RtlLengthSid` at `0x18011399f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180113972`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180113972`

## string_xrefs

- `0x180113b2c`: `IdentityCache`

## pseudocode

```c
__int64 __fastcall LsapInitializePerUserCacheEntry(char a1, void *a2, struct _RTL_AVL_TABLE **a3)
{
  struct _RTL_AVL_TABLE *v4; // rsi
  DWORD LastError; // eax
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  int IdentitiesPerUser; // ebx
  size_t v12; // rbx
  unsigned int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // rax
  unsigned int v18; // eax
  struct _RTL_AVL_TABLE *v19; // rax
  unsigned __int16 *v20; // rdi
  LPWSTR v21; // r9
  HKEY v22; // rcx
  LPWSTR StringSid; // [rsp+90h] [rbp+18h] BYREF

  v4 = 0;
  StringSid = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
    WPP_SF__sid_(*((_QWORD *)WPP_GLOBAL_Control + 12));
  if ( !ConvertSidToStringSidW(a2, &StringSid) )
  {
    LastError = GetLastError();
    IdentitiesPerUser = NetpApiStatusToNtStatus(LastError, v8, v9, v10);
    goto LABEL_31;
  }
  v12 = RtlLengthSid(a2);
  if ( a1 )
  {
    v13 = 24;
  }
  else
  {
    v14 = -1;
    do
      ++v14;
    while ( StringSid[v14] );
    v13 = v14 + 13;
    if ( (int)v14 + 13 < (unsigned int)v14 )
      goto LABEL_30;
  }
  v15 = v13 + 3;
  if ( (unsigned int)v15 < v13
    || (v16 = (unsigned int)v15, v17 = 2 * v15, v17 > 0xFFFFFFFF)
    || (v18 = v17 + 448, v18 < 0x1C0)
    || v18 + (unsigned int)v12 < (unsigned int)v12 )
  {
LABEL_30:
    IdentitiesPerUser = -1073741675;
    goto LABEL_31;
  }
  v19 = (struct _RTL_AVL_TABLE *)LocalAlloc(0x40u, v18 + (unsigned int)v12);
  v4 = v19;
  if ( !v19 )
  {
    IdentitiesPerUser = -1073741801;
    goto LABEL_31;
  }
  RtlInitializeGenericTableAvl(
    v19,
    LsapIdentityCache_CompareNames,
    DCInfoDiscoveryTable::StaticDiscoveryTableAllocate,
    LsapSidNameMappingCache_FreeRoutine,
    0);
  RtlInitializeGenericTableAvl(
    v4 + 1,
    LsapIdentityCache_CompareSAMNames,
    DCInfoDiscoveryTable::StaticDiscoveryTableAllocate,
    LsapSidNameMappingCache_FreeRoutine,
    0);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
    RtlInitializeGenericTableAvl(
      v4 + 3,
      LsapIdentityCache_CompareDisplayNames,
      DCInfoDiscoveryTable::StaticDiscoveryTableAllocate,
      LsapSidNameMappingCache_FreeRoutine,
      0);
  RtlInitializeGenericTableAvl(
    v4 + 2,
    LsapIdentityCache_CompareSids,
    DCInfoDiscoveryTable::StaticDiscoveryTableAllocate,
    LsapSidNameMappingCache_FreeRoutine,
    0);
  v4[4].BalancedRoot.Parent = (struct _RTL_BALANCED_LINKS *)&v4[4].OrderedPointer;
  *(_QWORD *)&v4[4].BalancedRoot.Balance = 0;
  memmove_0(&v4[4].OrderedPointer, a2, v12);
  v20 = (unsigned __int16 *)((char *)&v4[4].OrderedPointer + v12);
  v4[4].BalancedRoot.RightChild = (struct _RTL_BALANCED_LINKS *)v20;
  if ( v20 )
  {
    v21 = L"GlobalStore";
    if ( !a1 )
      v21 = StringSid;
    IdentitiesPerUser = RtlStringCchPrintfW(v20, v16, L"%s\\%s", v21, L"IdentityCache");
    if ( IdentitiesPerUser >= 0 )
    {
      if ( RegOpenKeyExW(
             g_hKeyCacheRoot,
             (LPCWSTR)v4[4].BalancedRoot.RightChild,
             0,
             0x2001Fu,
             (PHKEY)&v4[4].BalancedRoot.Balance) )
      {
        goto LABEL_31;
      }
      RtlConvertSharedToExclusive(&LsapIdentityCacheLock);
      IdentitiesPerUser = LsapReadIdentitiesPerUser((struct _PER_USER_CACHE_ENTRY *)v4, 0);
      RtlConvertExclusiveToShared(&LsapIdentityCacheLock);
      if ( IdentitiesPerUser >= 0 )
        goto LABEL_31;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          29,
          (unsigned int)&WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids,
          (_DWORD)v20,
          IdentitiesPerUser);
    }
  }
  else
  {
    IdentitiesPerUser = -1073741801;
  }
  v22 = *(HKEY *)&v4[4].BalancedRoot.Balance;
  if ( v22 )
    RegCloseKey(v22);
  LocalFree(v4);
  v4 = 0;
LABEL_31:
  if ( StringSid )
    LocalFree(StringSid);
  *a3 = v4;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 12),
      30,
      &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids,
      (unsigned int)IdentitiesPerUser);
  return (unsigned int)IdentitiesPerUser;
}

```

## disassembly

```asm
0x180113920  mov     rax, rsp
0x180113923  push    rbx
0x180113924  push    rbp
0x180113925  push    rsi
0x180113926  push    rdi
0x180113927  push    r12
0x180113929  push    r13
0x18011392b  push    r14
0x18011392d  push    r15
0x18011392f  sub     rsp, 38h
0x180113933  xor     edi, edi
0x180113935  mov     r13, r8
0x180113938  mov     esi, edi
0x18011393a  mov     [rax+18h], rdi
0x18011393e  mov     rbp, rdx
0x180113941  mov     r12b, cl
0x180113944  mov     rcx, cs:WPP_GLOBAL_Control
0x18011394b  test    byte ptr [rcx+6Ch], 10h
0x18011394f  jz      short loc_180113967
0x180113951  mov     rcx, [rcx+60h]; LoggerHandle
0x180113955  lea     edx, [rdi+1Ch]
0x180113958  mov     r9, rbp
0x18011395b  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x180113962  call    WPP_SF__sid_
0x180113967  lea     rdx, [rsp+78h+StringSid]; StringSid
0x18011396f  mov     rcx, rbp; Sid
0x180113972  call    cs:__imp_ConvertSidToStringSidW
0x180113979  nop     dword ptr [rax+rax+00h]
0x18011397e  test    eax, eax
0x180113980  jnz     short loc_18011399C
0x180113982  call    cs:__imp_GetLastError
0x180113989  nop     dword ptr [rax+rax+00h]
0x18011398e  mov     ecx, eax
0x180113990  call    NetpApiStatusToNtStatus
0x180113995  mov     ebx, eax
0x180113997  jmp     loc_180113C29
0x18011399c  mov     rcx, rbp; Sid
0x18011399f  call    cs:__imp_RtlLengthSid
0x1801139a6  nop     dword ptr [rax+rax+00h]
0x1801139ab  mov     ebx, eax
0x1801139ad  test    r12b, r12b
0x1801139b0  jz      short loc_1801139B9
0x1801139b2  mov     ecx, 18h
0x1801139b7  jmp     short loc_1801139D9
0x1801139b9  mov     rcx, [rsp+78h+StringSid]
0x1801139c1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801139c5  inc     rax
0x1801139c8  cmp     [rcx+rax*2], di
0x1801139cc  jnz     short loc_1801139C5
0x1801139ce  lea     ecx, [rax+0Dh]
0x1801139d1  cmp     ecx, eax
0x1801139d3  jb      loc_180113C24
0x1801139d9  lea     eax, [rcx+3]
0x1801139dc  cmp     eax, ecx
0x1801139de  jb      loc_180113C24
0x1801139e4  mov     r14d, eax
0x1801139e7  mov     ecx, 0FFFFFFFFh
0x1801139ec  add     rax, rax
0x1801139ef  cmp     rax, rcx
0x1801139f2  ja      loc_180113C24
0x1801139f8  add     eax, 1C0h
0x1801139fd  cmp     eax, 1C0h
0x180113a02  jb      loc_180113C24
0x180113a08  lea     ecx, [rax+rbx]
0x180113a0b  cmp     ecx, ebx
0x180113a0d  jb      loc_180113C24
0x180113a13  mov     edx, ecx; uBytes
0x180113a15  mov     ecx, 40h ; '@'; uFlags
0x180113a1a  call    cs:__imp_LocalAlloc
0x180113a21  nop     dword ptr [rax+rax+00h]
0x180113a26  mov     rsi, rax
0x180113a29  test    rax, rax
0x180113a2c  jnz     short loc_180113A38
0x180113a2e  mov     ebx, 0C0000017h
0x180113a33  jmp     loc_180113C29
0x180113a38  lea     r15, ?LsapSidNameMappingCache_FreeRoutine@@YAXPEAU_RTL_AVL_TABLE@@PEAX@Z; LsapSidNameMappingCache_FreeRoutine(_RTL_AVL_TABLE *,void *)
0x180113a3f  mov     [rsp+78h+TableContext], rdi; TableContext
0x180113a44  mov     r9, r15; FreeRoutine
0x180113a47  lea     r8, ?StaticDiscoveryTableAllocate@DCInfoDiscoveryTable@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180113a4e  lea     rdx, ?LsapIdentityCache_CompareNames@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180113a55  mov     rcx, rsi; Table
0x180113a58  call    cs:__imp_RtlInitializeGenericTableAvl
0x180113a5f  nop     dword ptr [rax+rax+00h]
0x180113a64  lea     rcx, [rsi+68h]; Table
0x180113a68  mov     [rsp+78h+TableContext], rdi; TableContext
0x180113a6d  mov     r9, r15; FreeRoutine
0x180113a70  lea     r8, ?StaticDiscoveryTableAllocate@DCInfoDiscoveryTable@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180113a77  lea     rdx, ?LsapIdentityCache_CompareSAMNames@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180113a7e  call    cs:__imp_RtlInitializeGenericTableAvl
0x180113a85  nop     dword ptr [rax+rax+00h]
0x180113a8a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x180113a91  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x180113a96  test    al, al
0x180113a98  jz      short loc_180113AC3
0x180113a9a  lea     rcx, [rsi+138h]; Table
0x180113aa1  mov     [rsp+78h+TableContext], rdi; TableContext
0x180113aa6  mov     r9, r15; FreeRoutine
0x180113aa9  lea     r8, ?StaticDiscoveryTableAllocate@DCInfoDiscoveryTable@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180113ab0  lea     rdx, ?LsapIdentityCache_CompareDisplayNames@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180113ab7  call    cs:__imp_RtlInitializeGenericTableAvl
0x180113abe  nop     dword ptr [rax+rax+00h]
0x180113ac3  lea     rcx, [rsi+0D0h]; Table
0x180113aca  mov     [rsp+78h+TableContext], rdi; TableContext
0x180113acf  mov     r9, r15; FreeRoutine
0x180113ad2  lea     r8, ?StaticDiscoveryTableAllocate@DCInfoDiscoveryTable@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x180113ad9  lea     rdx, ?LsapIdentityCache_CompareSids@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x180113ae0  call    cs:__imp_RtlInitializeGenericTableAvl
0x180113ae7  nop     dword ptr [rax+rax+00h]
0x180113aec  lea     rdi, [rsi+1C0h]
0x180113af3  mov     r8, rbx; Size
0x180113af6  lea     r15, [rsi+1B8h]
0x180113afd  mov     [rsi+1A0h], rdi
0x180113b04  mov     rcx, rdi; void *
0x180113b07  mov     qword ptr [r15], 0
0x180113b0e  mov     rdx, rbp; Src
0x180113b11  call    memmove_0
0x180113b16  add     rdi, rbx
0x180113b19  mov     [rsi+1B0h], rdi
0x180113b20  jnz     short loc_180113B2C
0x180113b22  mov     ebx, 0C0000017h
0x180113b27  jmp     loc_180113BF6
0x180113b2c  lea     rax, aIdentitycache; "IdentityCache"
0x180113b33  test    r12b, r12b
0x180113b36  lea     r9, aGlobalstore; "GlobalStore"
0x180113b3d  mov     [rsp+78h+TableContext], rax
0x180113b42  cmovz   r9, [rsp+78h+StringSid]
0x180113b4b  lea     r8, aSS_1; "%s\\%s"
0x180113b52  mov     rdx, r14; unsigned __int64
0x180113b55  mov     rcx, rdi; unsigned __int16 *
0x180113b58  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180113b5d  mov     ebx, eax
0x180113b5f  test    eax, eax
0x180113b61  js      loc_180113BF6
0x180113b67  mov     rdx, [rsi+1B0h]; lpSubKey
0x180113b6e  mov     r9d, 2001Fh; samDesired
0x180113b74  mov     rcx, cs:?g_hKeyCacheRoot@@3PEAUHKEY__@@EA; hKey
0x180113b7b  xor     r8d, r8d; ulOptions
0x180113b7e  mov     [rsp+78h+TableContext], r15; phkResult
0x180113b83  call    cs:__imp_RegOpenKeyExW
0x180113b8a  nop     dword ptr [rax+rax+00h]
0x180113b8f  test    eax, eax
0x180113b91  jnz     loc_180113C29
0x180113b97  lea     rcx, ?LsapIdentityCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180113b9e  call    cs:__imp_RtlConvertSharedToExclusive
0x180113ba5  nop     dword ptr [rax+rax+00h]
0x180113baa  xor     edx, edx; int
0x180113bac  mov     rcx, rsi; struct _PER_USER_CACHE_ENTRY *
0x180113baf  call    ?LsapReadIdentitiesPerUser@@YAJPEAU_PER_USER_CACHE_ENTRY@@H@Z; LsapReadIdentitiesPerUser(_PER_USER_CACHE_ENTRY *,int)
0x180113bb4  lea     rcx, ?LsapIdentityCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180113bbb  mov     ebx, eax
0x180113bbd  call    cs:__imp_RtlConvertExclusiveToShared
0x180113bc4  nop     dword ptr [rax+rax+00h]
0x180113bc9  test    ebx, ebx
0x180113bcb  jns     short loc_180113C29
0x180113bcd  mov     rcx, cs:WPP_GLOBAL_Control
0x180113bd4  test    byte ptr [rcx+6Ch], 10h
0x180113bd8  jz      short loc_180113BF6
0x180113bda  mov     rcx, [rcx+60h]
0x180113bde  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x180113be5  mov     edx, 1Dh
0x180113bea  mov     dword ptr [rsp+78h+TableContext], ebx
0x180113bee  mov     r9, rdi
0x180113bf1  call    WPP_SF_Sd
0x180113bf6  mov     rcx, [rsi+1B8h]; hKey
0x180113bfd  xor     edi, edi
0x180113bff  test    rcx, rcx
0x180113c02  jz      short loc_180113C10
0x180113c04  call    cs:__imp_RegCloseKey
0x180113c0b  nop     dword ptr [rax+rax+00h]
0x180113c10  mov     rcx, rsi; hMem
0x180113c13  call    cs:__imp_LocalFree
0x180113c1a  nop     dword ptr [rax+rax+00h]
0x180113c1f  mov     rsi, rdi
0x180113c22  jmp     short loc_180113C29
0x180113c24  mov     ebx, 0C0000095h
0x180113c29  mov     rcx, [rsp+78h+StringSid]; hMem
0x180113c31  test    rcx, rcx
0x180113c34  jz      short loc_180113C42
0x180113c36  call    cs:__imp_LocalFree
0x180113c3d  nop     dword ptr [rax+rax+00h]
0x180113c42  mov     [r13+0], rsi
0x180113c46  mov     rcx, cs:WPP_GLOBAL_Control
0x180113c4d  test    byte ptr [rcx+6Ch], 10h
0x180113c51  jz      short loc_180113C6B
0x180113c53  mov     rcx, [rcx+60h]
0x180113c57  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x180113c5e  mov     edx, 1Eh
0x180113c63  mov     r9d, ebx
0x180113c66  call    WPP_SF_d
0x180113c6b  mov     eax, ebx
0x180113c6d  add     rsp, 38h
0x180113c71  pop     r15
0x180113c73  pop     r14
0x180113c75  pop     r13
0x180113c77  pop     r12
0x180113c79  pop     rdi
0x180113c7a  pop     rsi
0x180113c7b  pop     rbp
0x180113c7c  pop     rbx
0x180113c7d  retn
```
