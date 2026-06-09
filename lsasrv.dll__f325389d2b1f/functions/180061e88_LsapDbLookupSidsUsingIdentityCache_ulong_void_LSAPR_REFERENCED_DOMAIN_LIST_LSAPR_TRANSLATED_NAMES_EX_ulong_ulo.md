# LsapDbLookupSidsUsingIdentityCache(ulong,void * *,_LSAPR_REFERENCED_DOMAIN_LIST *,_LSAPR_TRANSLATED_NAMES_EX *,ulong *,ulong *,ulong)

- ea: `0x180061e88`
- end: `0x1800626a6`
- name: `?LsapDbLookupSidsUsingIdentityCache@@YAJKPEAPEAXPEAU_LSAPR_REFERENCED_DOMAIN_LIST@@PEAU_LSAPR_TRANSLATED_NAMES_EX@@PEAK3K@Z`
- size: `2078`
- prototype: `__int64 __fastcall(unsigned int, void **, struct _LSAPR_REFERENCED_DOMAIN_LIST *, struct _LSAPR_TRANSLATED_NAMES_EX *, unsigned int *, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `23`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180011cdc`
- `0x180060cf4`

## callees

- `0x18000c300`
- `0x18000d3b0`
- `0x180011278`
- `0x180014160`
- `0x1800284d4`
- `0x180038530`
- `0x180039400`
- `0x18005ec24`
- `0x18005faf0`
- `0x18005fb34`
- `0x18005fecc`
- `0x180060324`
- `0x18006064c`
- `0x180060c8c`
- `0x180061e88`
- `0x1800626ac`
- `0x180062e88`
- `0x1800b1db8`
- `0x180112890`
- `0x180112b04`
- `0x1801147c0`
- `0x180114c14`
- `0x180128560`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006244b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180062003`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006244b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800622ac`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800622ac`
- `ntdll!RtlReleaseResource` at `0x180061fd6`
- `ntdll!RtlReleaseResource` at `0x180061fd6`
- `ntdll!RtlAcquireResourceShared` at `0x18006207c`
- `ntdll!RtlAcquireResourceShared` at `0x18006207c`
- `ntdll!NtClose` at `0x180061fef`
- `ntdll!NtClose` at `0x180061fef`
- `ntdll!RtlValidSid` at `0x1800620fc`
- `ntdll!RtlValidSid` at `0x1800620fc`
- `ntdll!RtlCopyUnicodeString` at `0x1800622cd`
- `ntdll!RtlCopyUnicodeString` at `0x1800622cd`
- `ntdll!RtlInitUnicodeString` at `0x180061f1b`
- `ntdll!RtlInitUnicodeString` at `0x180061f1b`

## string_xrefs

- `0x1800624af`: `LsapSidBelongsToIdProv:LsapRefIdProvByInternetSid`
- `0x180062389`: `LsapSidBelongsToIdProv:SID Validation`

## pseudocode

```c
__int64 __fastcall LsapDbLookupSidsUsingIdentityCache(
        unsigned int a1,
        void **a2,
        struct _LSAPR_REFERENCED_DOMAIN_LIST *a3,
        struct _LSAPR_TRANSLATED_NAMES_EX *a4,
        unsigned int *a5,
        unsigned int *a6,
        signed int a7)
{
  int RpcClientLUIDAndToken; // ebx
  void *v9; // r15
  struct _RTL_BALANCED_NODE *v10; // r12
  unsigned int v11; // esi
  LsaHandleCache *v13; // rcx
  void *v15; // rdx
  HANDLE v16; // rax
  int v17; // esi
  int v18; // r14d
  int *v19; // rbx
  unsigned int v20; // eax
  struct _RTL_BALANCED_NODE *v21; // rdi
  void *v22; // rdx
  void *v23; // rbx
  int v24; // eax
  int v25; // ebx
  int v26; // eax
  struct _RTL_BALANCED_NODE *v27; // rdi
  HANDLE v28; // rsi
  int IdentityInCacheBySID; // eax
  struct _LSAP_IDENTITY_CACHE_ENTRY *v30; // rbx
  UNICODE_STRING v31; // xmm0
  _WORD *v32; // xmm0_8
  HLOCAL v33; // rax
  unsigned __int8 IsEnabled; // al
  int v35; // ecx
  const char *v36; // rcx
  int v37; // eax
  int MappedSidInternal; // eax
  int v39; // eax
  char v40; // bl
  enum _SID_NAME_USE v41; // eax
  __int64 v42; // rdx
  LsaHandleCache *v43; // r8
  __int64 i; // rcx
  __int64 v45; // [rsp+38h] [rbp-D0h]
  unsigned int v46; // [rsp+48h] [rbp-C0h]
  int *v47; // [rsp+50h] [rbp-B8h]
  int v48; // [rsp+58h] [rbp-B0h]
  int v49; // [rsp+5Ch] [rbp-ACh]
  int v50; // [rsp+60h] [rbp-A8h]
  unsigned int v51; // [rsp+64h] [rbp-A4h]
  HANDLE Handle; // [rsp+68h] [rbp-A0h] BYREF
  void *v53[3]; // [rsp+70h] [rbp-98h] BYREF
  struct _UNICODE_STRING v54; // [rsp+88h] [rbp-80h] BYREF
  struct _RTL_BALANCED_NODE *v55; // [rsp+98h] [rbp-70h] BYREF
  UNICODE_STRING SourceString; // [rsp+A8h] [rbp-60h] BYREF
  struct _UNICODE_STRING v57; // [rsp+B8h] [rbp-50h] BYREF
  struct _UNICODE_STRING v58; // [rsp+C8h] [rbp-40h] BYREF
  struct _UNICODE_STRING v59; // [rsp+D8h] [rbp-30h] BYREF
  struct _RTL_BALANCED_NODE *v60; // [rsp+E8h] [rbp-20h] BYREF
  struct _LSAP_IDENTITY_CACHE_ENTRY *v61; // [rsp+F0h] [rbp-18h] BYREF
  unsigned __int64 v62[3]; // [rsp+F8h] [rbp-10h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+110h] [rbp+8h] BYREF
  int v64; // [rsp+168h] [rbp+60h]

  RpcClientLUIDAndToken = 0;
  v61 = 0;
  v9 = 0;
  memset(v53, 0, sizeof(v53));
  memset(v62, 0, sizeof(v62));
  v10 = 0;
  Handle = 0;
  v11 = a1 - *a5;
  v55 = 0;
  v46 = v11;
  v57 = 0;
  v54 = 0;
  SourceString = 0;
  v58 = 0;
  v59 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"user");
  v13 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
  {
    WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids, a1, *a5, *a6);
    v13 = WPP_GLOBAL_Control;
  }
  if ( !LsapIdentityCacheLockInitialized || !g_bIdentityCacheEnabled || !*a6 )
    goto LABEL_4;
  RpcClientLUIDAndToken = LsapGetRpcClientLUIDAndToken(0, &Handle, 4u);
  v16 = Handle;
  if ( RpcClientLUIDAndToken < 0 )
    goto LABEL_11;
  v49 = 0;
  v17 = 8;
  v18 = 0;
  v48 = 0;
  v50 = 0;
  RtlAcquireResourceShared(&LsapIdentityCacheLock, 1u);
  v19 = (int *)*((_QWORD *)a4 + 1);
  v20 = 0;
  while ( 1 )
  {
    v47 = v19;
    v51 = v20;
    if ( v20 >= a1 )
    {
      v11 = v46;
      RpcClientLUIDAndToken = 0;
      *a5 = a1 - v46;
      *a6 = v46;
      goto LABEL_8;
    }
    v21 = 0;
    if ( v9 )
    {
      LocalFree(v9);
      v9 = 0;
      v53[0] = 0;
    }
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
      v17 = 8;
    v64 = v17;
    if ( v49 )
    {
      LsapFreeString(&v57);
      LsapFreeString(&v54);
      LsapFreeString(&v53[1]);
      LsapFreeString(&v59);
      LsapFreeString(&v58);
      v49 = 0;
    }
    if ( v10 )
    {
      LsapSubProv_FreeRoutine(v10, v22);
      v10 = 0;
      v55 = 0;
    }
    if ( *v19 != 8 )
      goto LABEL_50;
    v60 = 0;
    v23 = a2[v51];
    if ( !v23 || !RtlValidSid(a2[v51]) )
    {
      v24 = -1073741811;
      v36 = "LsapSidBelongsToIdProv:SID Validation";
      v25 = -1073741811;
LABEL_73:
      CONNECTED_TRACE_ERROR(v36, (unsigned int)v24);
      goto LABEL_38;
    }
    v18 = 0;
    v50 = 0;
    if ( !(unsigned int)LsapCheckConnectedUserEnabled() )
    {
      v25 = 0;
      goto LABEL_38;
    }
    v24 = LsapRefIdProvByInternetSid(v23, (struct _LIST_ENTRY **)&v60);
    v21 = v60;
    v25 = v24;
    if ( v24 >= 0 )
    {
      v50 = 1;
      v18 = (__int64)v60[2].Right & 1;
      goto LABEL_37;
    }
    if ( v24 != -1073741275 )
    {
      v36 = "LsapSidBelongsToIdProv:LsapRefIdProvByInternetSid";
      goto LABEL_73;
    }
LABEL_37:
    v25 = 0;
LABEL_38:
    LsapDerefIdProv(v21);
    if ( v25 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        40,
        &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids,
        (unsigned int)v25);
    if ( !v50 )
    {
      MappedSidInternal = LsapFindMappedSidInternal(a2[v51], 0, &v55);
      v10 = v55;
      if ( MappedSidInternal < 0 )
        goto LABEL_48;
      v18 = 0;
LABEL_41:
      v26 = v48;
      if ( (a7 & 0x40000000) != 0 )
        v26 = 1;
      v48 = v26;
      goto LABEL_44;
    }
    if ( !v18 )
      goto LABEL_41;
    if ( a7 < 0 )
      goto LABEL_48;
    v48 = 1;
LABEL_44:
    if ( v10 )
      v27 = v10;
    else
      v27 = (struct _RTL_BALANCED_NODE *)a2[v51];
    v28 = Handle;
    IdentityInCacheBySID = LsapFindIdentityInCacheBySID(Handle, v27, &v61);
    RpcClientLUIDAndToken = IdentityInCacheBySID;
    if ( IdentityInCacheBySID == -1073741275 )
    {
      v39 = LsapResolveIdentityInternetName(v28, v27, &v57, &v54, (struct _UNICODE_STRING *)&v53[1], &v59, &v58);
      v40 = v39;
      if ( v39 < 0 )
      {
LABEL_48:
        v17 = v64;
LABEL_49:
        v19 = v47;
        goto LABEL_50;
      }
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
      {
        v41 = LsapConvertUnicodeStringToSidNameUse(&v58);
        v17 = v41;
        v43 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
        {
          LODWORD(v45) = v41;
          WPP_SF__sid_ZZL(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            v42,
            (__int64)WPP_GLOBAL_Control,
            (char *)v27,
            &v54.Length,
            (unsigned __int16 *)&v53[1],
            v45);
          v43 = WPP_GLOBAL_Control;
        }
        if ( v17 == 8 )
        {
          for ( i = 0; (unsigned int)i < v54.Length >> 1; i = (unsigned int)(i + 1) )
          {
            if ( v54.Buffer[i] == 64 )
            {
              v17 = 1;
              LsapDuplicateString(&v58, &DestinationString);
              goto LABEL_80;
            }
          }
          if ( (*((_BYTE *)v43 + 108) & 0x10) != 0 )
            WPP_SF_ZZD(*((_QWORD *)v43 + 12), 42, (_DWORD)v43, (unsigned int)&v54, (__int64)&v58, v40);
          goto LABEL_49;
        }
      }
      else
      {
        v17 = v64;
      }
LABEL_80:
      v49 = 1;
      v37 = LsapAddSidNameToIdentityCache(Handle, v27, &v57, &v54, (struct _UNICODE_STRING *)&v53[1], &v59, &v58);
      if ( v37 < 0 && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 0x10) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          43,
          &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids,
          (unsigned int)v37);
    }
    else
    {
      if ( IdentityInCacheBySID == -1073741709 )
        goto LABEL_48;
      if ( IdentityInCacheBySID < 0 )
        goto LABEL_106;
      v30 = v61;
      v57 = *(struct _UNICODE_STRING *)((char *)v61 + 40);
      v54 = *(struct _UNICODE_STRING *)((char *)v61 + 24);
      *(_OWORD *)&v53[1] = *(_OWORD *)((char *)v61 + 8);
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl) )
      {
        v17 = *((_DWORD *)v30 + 19);
        v59 = (struct _UNICODE_STRING)*((_OWORD *)v30 + 5);
      }
      else
      {
        v17 = v64;
      }
    }
    if ( v48 )
    {
      v31 = v54;
    }
    else if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl)
           || v57.Length )
    {
      v31 = v57;
    }
    else
    {
      v31 = v59;
    }
    SourceString = v31;
    if ( !(unsigned __int16)_mm_cvtsi128_si32((__m128i)v31) )
      goto LABEL_49;
    v32 = (_WORD *)_mm_srli_si128((__m128i)v31, 8).m128i_u64[0];
    if ( !v32 || !*v32 )
      goto LABEL_49;
    if ( (int)LsapResolveDomainInternetSid((struct _UNICODE_STRING *)&v53[1], v53) < 0 )
    {
      v9 = v53[0];
      goto LABEL_49;
    }
    *(UNICODE_STRING *)(v47 + 2) = SourceString;
    if ( !SourceString.Buffer )
      goto LABEL_65;
    if ( !SourceString.MaximumLength )
    {
      *((_QWORD *)v47 + 2) = 0;
      goto LABEL_65;
    }
    v33 = LocalAlloc(0x40u, SourceString.MaximumLength);
    *((_QWORD *)v47 + 2) = v33;
    if ( !v33 )
      break;
    RtlCopyUnicodeString((PUNICODE_STRING)(v47 + 2), &SourceString);
LABEL_65:
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl'::`2'::impl);
    v35 = 1;
    if ( IsEnabled )
      v35 = v17;
    *v47 = v35;
    v9 = v53[0];
    if ( !(unsigned __int8)LsapDbLookupListReferencedDomains(a3, v53[0], v47 + 6) )
    {
      LOWORD(v62[0]) = v53[1];
      *(_DWORD *)((char *)&v62[1] + 2) = *(_DWORD *)((char *)&v53[2] + 2);
      HIWORD(v62[1]) = HIWORD(v53[2]);
      *(unsigned __int64 *)((char *)v62 + 2) = *(unsigned __int64 *)((char *)&v53[1] + 2);
      v62[2] = (unsigned __int64)v9;
      RpcClientLUIDAndToken = LsapDbLookupAddListReferencedDomains((unsigned int *)a3, v62, v47 + 6);
      if ( RpcClientLUIDAndToken < 0 )
        goto LABEL_106;
    }
    v19 = v47;
    --v46;
    v47[7] = 8;
LABEL_50:
    v20 = v51 + 1;
    v19 += 8;
  }
  v9 = v53[0];
  RpcClientLUIDAndToken = -1073741670;
LABEL_106:
  v11 = v46;
LABEL_8:
  if ( v49 )
  {
    LsapFreeString(&v57);
    LsapFreeString(&v54);
    LsapFreeString(&v53[1]);
    LsapFreeString(&v59);
    LsapFreeString(&v58);
  }
  RtlReleaseResource(&LsapIdentityCacheLock);
  v16 = Handle;
LABEL_11:
  if ( v16 )
    NtClose(v16);
  if ( v9 )
    LocalFree(v9);
  if ( v10 )
    LsapSubProv_FreeRoutine(v10, v15);
  v13 = WPP_GLOBAL_Control;
LABEL_4:
  if ( (*((_BYTE *)v13 + 108) & 0x10) != 0 )
    WPP_SF_Dd(*((_QWORD *)v13 + 12), 44, &WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids, v11, RpcClientLUIDAndToken);
  return (unsigned int)RpcClientLUIDAndToken;
}

```

## disassembly

```asm
0x180061e88  mov     rax, rsp
0x180061e8b  mov     [rax+20h], rbx
0x180061e8f  mov     [rax+18h], r8
0x180061e93  mov     [rax+10h], rdx
0x180061e97  push    rbp
0x180061e98  push    rsi
0x180061e99  push    rdi
0x180061e9a  push    r12
0x180061e9c  push    r13
0x180061e9e  push    r14
0x180061ea0  push    r15
0x180061ea2  lea     rbp, [rax-58h]
0x180061ea6  sub     rsp, 120h
0x180061ead  mov     rax, [rbp+50h+arg_20]
0x180061eb4  lea     rdx, aUser; "user"
0x180061ebb  xorps   xmm0, xmm0
0x180061ebe  mov     r13d, ecx
0x180061ec1  xor     ecx, ecx
0x180061ec3  xorps   xmm1, xmm1
0x180061ec6  mov     ebx, ecx
0x180061ec8  mov     [rbp+50h+var_68], rcx
0x180061ecc  mov     r15d, ecx
0x180061ecf  mov     qword ptr [rsp+150h+var_E8], rcx
0x180061ed4  mov     [rbp+50h+var_60], cx
0x180061ed8  mov     r12d, ecx
0x180061edb  mov     [rsp+150h+Handle], rcx
0x180061ee0  mov     esi, r13d
0x180061ee3  sub     esi, [rax]
0x180061ee5  mov     rdi, r9
0x180061ee8  xor     eax, eax
0x180061eea  mov     [rbp+50h+var_C0], rcx
0x180061eee  movups  xmmword ptr [rbp+50h+var_5E], xmm0
0x180061ef2  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x180061ef6  mov     qword ptr [rbp+50h+var_5E+0Eh], rax
0x180061efa  mov     dword ptr [rsp+150h+var_110], esi
0x180061efe  movups  xmmword ptr [rbp+50h+var_A0.Length], xmm0
0x180061f02  movups  xmmword ptr [rbp+50h+var_D0.Length], xmm1
0x180061f06  movups  xmmword ptr [rsp+150h+var_E8+8], xmm0
0x180061f0b  movups  xmmword ptr [rbp+50h+SourceString.Length], xmm1
0x180061f0f  movups  xmmword ptr [rbp+50h+var_90.Length], xmm0
0x180061f13  movups  xmmword ptr [rbp+50h+var_80.Length], xmm1
0x180061f17  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm0
0x180061f1b  call    cs:__imp_RtlInitUnicodeString
0x180061f22  nop     dword ptr [rax+rax+00h]
0x180061f27  mov     rcx, cs:WPP_GLOBAL_Control
0x180061f2e  mov     r14, [rbp+50h+arg_28]
0x180061f35  test    byte ptr [rcx+6Ch], 10h
0x180061f39  jnz     short loc_180061F71
0x180061f3b  xor     eax, eax
0x180061f3d  cmp     cs:?LsapIdentityCacheLockInitialized@@3EA, al; uchar LsapIdentityCacheLockInitialized
0x180061f43  jnz     loc_180062028
0x180061f49  test    byte ptr [rcx+6Ch], 10h
0x180061f4d  jnz     loc_180062685
0x180061f53  mov     eax, ebx
0x180061f55  mov     rbx, [rsp+150h+arg_18]
0x180061f5d  add     rsp, 120h
0x180061f64  pop     r15
0x180061f66  pop     r14
0x180061f68  pop     r13
0x180061f6a  pop     r12
0x180061f6c  pop     rdi
0x180061f6d  pop     rsi
0x180061f6e  pop     rbp
0x180061f6f  retn
0x180061f71  mov     eax, [r14]
0x180061f74  lea     r8, WPP_4b8dd4c0b987363f52d3f64d5c7fdc37_Traceguids
0x180061f7b  mov     rcx, [rcx+60h]
0x180061f7f  mov     edx, 27h ; '''
0x180061f84  mov     dword ptr [rsp+150h+var_128], eax
0x180061f88  mov     r9d, r13d
0x180061f8b  mov     rax, [rbp+50h+arg_20]
0x180061f92  mov     eax, [rax]
0x180061f94  mov     dword ptr [rsp+150h+var_130], eax
0x180061f98  call    WPP_SF_DDD
0x180061f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061fa4  jmp     short loc_180061F3B
0x180061fa6  mov     rax, [rbp+50h+arg_20]
0x180061fad  mov     esi, dword ptr [rsp+150h+var_110]
0x180061fb1  sub     r13d, esi
0x180061fb4  xor     edi, edi
0x180061fb6  mov     ebx, edi
0x180061fb8  mov     [rax], r13d
0x180061fbb  mov     rax, [rbp+50h+arg_28]
0x180061fc2  mov     [rax], esi
0x180061fc4  cmp     [rsp+150h+var_FC], 0
0x180061fc9  jnz     loc_180062652
0x180061fcf  lea     rcx, ?LsapIdentityCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180061fd6  call    cs:__imp_RtlReleaseResource
0x180061fdd  nop     dword ptr [rax+rax+00h]
0x180061fe2  mov     rax, [rsp+150h+Handle]
0x180061fe7  test    rax, rax
0x180061fea  jz      short loc_180061FFB
0x180061fec  mov     rcx, rax; Handle
0x180061fef  call    cs:__imp_NtClose
0x180061ff6  nop     dword ptr [rax+rax+00h]
0x180061ffb  test    r15, r15
0x180061ffe  jz      short loc_18006200F
0x180062000  mov     rcx, r15; hMem
0x180062003  call    cs:__imp_LocalFree
0x18006200a  nop     dword ptr [rax+rax+00h]
0x18006200f  test    r12, r12
0x180062012  jz      short loc_18006201C
0x180062014  mov     rcx, r12; struct _RTL_BALANCED_NODE *
0x180062017  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x18006201c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062023  jmp     loc_180061F49
0x180062028  cmp     cs:?g_bIdentityCacheEnabled@@3EA, al; uchar g_bIdentityCacheEnabled
0x18006202e  jz      loc_180061F49
0x180062034  cmp     [r14], eax
0x180062037  jz      loc_180061F49
0x18006203d  mov     r8d, 4; unsigned int
0x180062043  lea     rdx, [rsp+150h+Handle]; void **
0x180062048  xor     ecx, ecx; struct _LUID *
0x18006204a  call    ?LsapGetRpcClientLUIDAndToken@@YAJPEAU_LUID@@PEAPEAXK@Z; LsapGetRpcClientLUIDAndToken(_LUID *,void * *,ulong)
0x18006204f  mov     ebx, eax
0x180062051  xor     ecx, ecx
0x180062053  mov     rax, [rsp+150h+Handle]
0x180062058  mov     [rsp+150h+Handle], rax
0x18006205d  test    ebx, ebx
0x18006205f  js      short loc_180061FE7
0x180062061  mov     [rsp+150h+var_FC], ecx
0x180062065  lea     esi, [rcx+8]
0x180062068  mov     r14d, ecx
0x18006206b  mov     [rsp+150h+var_100], ecx
0x18006206f  mov     dword ptr [rsp+150h+var_F8], ecx
0x180062073  mov     dl, 1; Wait
0x180062075  lea     rcx, ?LsapIdentityCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18006207c  call    cs:__imp_RtlAcquireResourceShared
0x180062083  nop     dword ptr [rax+rax+00h]
0x180062088  mov     rbx, [rdi+8]
0x18006208c  xor     eax, eax
0x18006208e  mov     qword ptr [rsp+150h+var_108], rbx
0x180062093  mov     dword ptr [rsp+150h+var_F8+4], eax
0x180062097  cmp     eax, r13d
0x18006209a  jnb     loc_180061FA6
0x1800620a0  xor     edi, edi
0x1800620a2  test    r15, r15
0x1800620a5  jnz     loc_180062448
0x1800620ab  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x1800620b2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x1800620b7  test    al, al
0x1800620b9  mov     eax, 8
0x1800620be  cmovnz  esi, eax
0x1800620c1  mov     [rbp+50h+arg_0], esi
0x1800620c4  cmp     [rsp+150h+var_FC], edi
0x1800620c8  jnz     loc_180062464
0x1800620ce  test    r12, r12
0x1800620d1  jnz     loc_18006249B
0x1800620d7  cmp     dword ptr [rbx], 8
0x1800620da  jnz     loc_1800621CC
0x1800620e0  mov     esi, dword ptr [rsp+150h+var_F8+4]
0x1800620e4  mov     rax, [rbp+50h+arg_8]
0x1800620e8  mov     [rbp+50h+var_70], rdi
0x1800620ec  mov     rbx, [rax+rsi*8]
0x1800620f0  test    rbx, rbx
0x1800620f3  jz      loc_180062384
0x1800620f9  mov     rcx, rbx; Sid
0x1800620fc  call    cs:__imp_RtlValidSid
0x180062103  nop     dword ptr [rax+rax+00h]
0x180062108  test    al, al
0x18006210a  jz      loc_180062384
0x180062110  xor     r14d, r14d
0x180062113  mov     dword ptr [rsp+150h+var_F8], r14d
0x180062118  call    ?LsapCheckConnectedUserEnabled@@YAHXZ; LsapCheckConnectedUserEnabled(void)
0x18006211d  test    eax, eax
0x18006211f  jz      loc_180062367
0x180062125  lea     rdx, [rbp+50h+var_70]; struct _LSAP_IDPROV_REG_ENTRY **
0x180062129  mov     rcx, rbx; Sid
0x18006212c  call    ?LsapRefIdProvByInternetSid@@YAJPEAXPEAPEAU_LSAP_IDPROV_REG_ENTRY@@@Z; LsapRefIdProvByInternetSid(void *,_LSAP_IDPROV_REG_ENTRY * *)
0x180062131  mov     rdi, [rbp+50h+var_70]
0x180062135  mov     ebx, eax
0x180062137  test    eax, eax
0x180062139  jns     loc_18006236F
0x18006213f  cmp     eax, 0C0000225h
0x180062144  jnz     loc_1800624AF
0x18006214a  xor     ebx, ebx
0x18006214c  mov     rcx, rdi; struct _RTL_BALANCED_NODE *
0x18006214f  call    ?LsapDerefIdProv@@YAXPEAU_LSAP_IDPROV_REG_ENTRY@@@Z; LsapDerefIdProv(_LSAP_IDPROV_REG_ENTRY *)
0x180062154  xor     edi, edi
0x180062156  test    ebx, ebx
0x180062158  js      loc_1800624BB
0x18006215e  cmp     dword ptr [rsp+150h+var_F8], edi
0x180062162  jz      loc_1800624E9
0x180062168  test    r14d, r14d
0x18006216b  jnz     loc_180062510
0x180062171  mov     eax, [rsp+150h+var_100]
0x180062175  mov     ecx, 1
0x18006217a  test    [rbp+50h+arg_30], 40000000h
0x180062184  cmovnz  eax, ecx
0x180062187  mov     [rsp+150h+var_100], eax
0x18006218b  test    r12, r12
0x18006218e  jnz     loc_18006239E
0x180062194  mov     rax, [rbp+50h+arg_8]
0x180062198  mov     rdi, [rax+rsi*8]
0x18006219c  mov     rsi, [rsp+150h+Handle]
0x1800621a1  lea     r8, [rbp+50h+var_68]; struct _LSAP_IDENTITY_CACHE_ENTRY **
0x1800621a5  mov     rcx, rsi; TokenHandle
0x1800621a8  mov     rdx, rdi; void *
0x1800621ab  call    ?LsapFindIdentityInCacheBySID@@YAJPEAX0PEAPEAU_LSAP_IDENTITY_CACHE_ENTRY@@@Z; LsapFindIdentityInCacheBySID(void *,void *,_LSAP_IDENTITY_CACHE_ENTRY * *)
0x1800621b0  mov     ebx, eax
0x1800621b2  cmp     eax, 0C0000225h
0x1800621b7  jz      loc_180062529
0x1800621bd  cmp     eax, 0C0000073h
0x1800621c2  jnz     short loc_1800621DB
0x1800621c4  mov     esi, [rbp+50h+arg_0]
0x1800621c7  mov     rbx, qword ptr [rsp+150h+var_108]
0x1800621cc  mov     eax, dword ptr [rsp+150h+var_F8+4]
0x1800621d0  inc     eax
0x1800621d2  add     rbx, 20h ; ' '
0x1800621d6  jmp     loc_18006208E
0x1800621db  xor     edi, edi
0x1800621dd  test    eax, eax
0x1800621df  js      loc_180062649
0x1800621e5  mov     rbx, [rbp+50h+var_68]
0x1800621e9  movups  xmm0, xmmword ptr [rbx+28h]
0x1800621ed  movdqu  xmmword ptr [rbp+50h+var_A0.Length], xmm0
0x1800621f2  movups  xmm1, xmmword ptr [rbx+18h]
0x1800621f6  movdqu  xmmword ptr [rbp+50h+var_D0.Length], xmm1
0x1800621fb  movups  xmm0, xmmword ptr [rbx+8]
0x1800621ff  movdqu  xmmword ptr [rsp+150h+var_E8+8], xmm0
0x180062205  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x18006220c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x180062211  test    al, al
0x180062213  jnz     loc_18006261B
0x180062219  mov     esi, [rbp+50h+arg_0]
0x18006221c  cmp     [rsp+150h+var_100], 0
0x180062221  jnz     loc_18006262C
0x180062227  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x18006222e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x180062233  test    al, al
0x180062235  jnz     loc_1800623AF
0x18006223b  movaps  xmm0, xmmword ptr [rbp+50h+var_A0.Length]
0x18006223f  movd    eax, xmm0
0x180062243  movaps  xmmword ptr [rbp+50h+SourceString.Length], xmm0
0x180062247  cmp     di, ax
0x18006224a  jz      loc_1800621C7
0x180062250  psrldq  xmm0, 8
0x180062255  movq    rcx, xmm0
0x18006225a  test    rcx, rcx
0x18006225d  jz      loc_1800621C7
0x180062263  cmp     di, [rcx]
0x180062266  jz      loc_1800621C7
0x18006226c  lea     rdx, [rsp+150h+var_E8]; void **
0x180062271  lea     rcx, [rsp+150h+var_E8+8]; struct _UNICODE_STRING *
0x180062276  call    ?LsapResolveDomainInternetSid@@YAJPEAU_UNICODE_STRING@@PEAPEAX@Z; LsapResolveDomainInternetSid(_UNICODE_STRING *,void * *)
0x18006227b  test    eax, eax
0x18006227d  js      loc_180062635
0x180062283  mov     r15, qword ptr [rsp+150h+var_108]
0x180062288  movaps  xmm0, xmmword ptr [rbp+50h+SourceString.Length]
0x18006228c  movdqu  xmmword ptr [r15+8], xmm0
0x180062292  cmp     [rbp+50h+SourceString.Buffer], rdi
0x180062296  jz      short loc_1800622D9
0x180062298  movzx   eax, [rbp+50h+SourceString.MaximumLength]
0x18006229c  test    ax, ax
0x18006229f  jz      loc_1800623A6
0x1800622a5  mov     edx, eax; uBytes
0x1800622a7  mov     ecx, 40h ; '@'; uFlags
0x1800622ac  call    cs:__imp_LocalAlloc
0x1800622b3  nop     dword ptr [rax+rax+00h]
0x1800622b8  mov     [r15+10h], rax
0x1800622bc  test    rax, rax
0x1800622bf  jz      loc_18006263F
0x1800622c5  lea     rdx, [rbp+50h+SourceString]; SourceString
0x1800622c9  lea     rcx, [r15+8]; DestinationString
0x1800622cd  call    cs:__imp_RtlCopyUnicodeString
0x1800622d4  nop     dword ptr [rax+rax+00h]
0x1800622d9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support> `wil::Feature<__WilFeatureTraits_Feature_AADSidToNameV2Support>::GetImpl(void)'::`2'::impl
0x1800622e0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AADSidToNameV2Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AADSidToNameV2Support>::__private_IsEnabled(void)
0x1800622e5  test    al, al
0x1800622e7  lea     rbx, [r15+18h]
0x1800622eb  mov     ecx, 1
0x1800622f0  mov     r8, rbx
0x1800622f3  cmovnz  ecx, esi
0x1800622f6  mov     [r15], ecx
0x1800622f9  mov     r15, qword ptr [rsp+150h+var_E8]
0x1800622fe  mov     rdi, [rbp+50h+arg_10]
0x180062302  mov     rdx, r15
0x180062305  mov     rcx, rdi
0x180062308  call    LsapDbLookupListReferencedDomains
0x18006230d  test    al, al
0x18006230f  jnz     short loc_180062352
0x180062311  movzx   eax, word ptr [rsp+150h+var_E8+8]
0x180062316  lea     rdx, [rbp+50h+var_60]
0x18006231a  movsd   xmm0, qword ptr [rsp+150h+var_E8+0Ah]
0x180062320  mov     r8, rbx
0x180062323  mov     [rbp+50h+var_60], ax
0x180062327  mov     rcx, rdi
0x18006232a  mov     eax, dword ptr [rsp+150h+var_E8+12h]
0x18006232e  mov     dword ptr [rbp+50h+var_5E+8], eax
0x180062331  movzx   eax, word ptr [rsp+150h+var_E8+16h]
0x180062336  mov     word ptr [rbp+50h+var_5E+0Ch], ax
0x18006233a  movsd   qword ptr [rbp+50h+var_5E], xmm0
0x18006233f  mov     qword ptr [rbp+50h+var_5E+0Eh], r15
0x180062343  call    LsapDbLookupAddListReferencedDomains
0x180062348  mov     ebx, eax
0x18006234a  test    eax, eax
0x18006234c  js      loc_180062649
0x180062352  mov     rbx, qword ptr [rsp+150h+var_108]
0x180062357  dec     dword ptr [rsp+150h+var_110]
0x18006235b  mov     dword ptr [rbx+1Ch], 8
  ... truncated ...
```
