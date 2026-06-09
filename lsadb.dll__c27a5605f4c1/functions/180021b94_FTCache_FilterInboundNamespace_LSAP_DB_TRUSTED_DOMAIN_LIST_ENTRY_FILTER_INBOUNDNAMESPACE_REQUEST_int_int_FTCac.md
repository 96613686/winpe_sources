# FTCache::FilterInboundNamespace(_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *,_FILTER_INBOUNDNAMESPACE_REQUEST *,int,int,FTCache::OwnershipState *,FTCache::OwnershipState *,int *)

- ea: `0x180021b94`
- end: `0x1800221c4`
- name: `?FilterInboundNamespace@FTCache@@AEAAJPEAU_LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY@@PEAU_FILTER_INBOUNDNAMESPACE_REQUEST@@HHPEAW4OwnershipState@1@2PEAH@Z`
- size: `1584`
- prototype: `__int64 __fastcall(FTCache *__hidden this, struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *, struct _FILTER_INBOUNDNAMESPACE_REQUEST *, int, int, enum FTCache::OwnershipState *, enum FTCache::OwnershipState *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180025474`

## callees

- `0x18000fd18`
- `0x18000fd40`
- `0x18000fde0`
- `0x180021b94`
- `0x18002a15c`
- `0x18002aea8`
- `0x18002b140`
- `0x18002b9b4`
- `0x18002c008`

## import_xrefs

- `ntdll!RtlCompareUnicodeString` at `0x180021dda`
- `ntdll!RtlCompareUnicodeString` at `0x180021e1f`
- `ntdll!RtlCompareUnicodeString` at `0x180021e6d`
- `ntdll!RtlCompareUnicodeString` at `0x180021eb2`
- `ntdll!RtlCompareUnicodeString` at `0x180021dda`
- `ntdll!RtlCompareUnicodeString` at `0x180021e1f`
- `ntdll!RtlCompareUnicodeString` at `0x180021e6d`
- `ntdll!RtlCompareUnicodeString` at `0x180021eb2`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180021d6f`
- `ntdll!RtlLookupElementGenericTableAvl` at `0x180021d6f`
- `ntdll!RtlInitUnicodeString` at `0x180021c21`
- `ntdll!RtlInitUnicodeString` at `0x180021c34`
- `ntdll!RtlInitUnicodeString` at `0x180021c21`
- `ntdll!RtlInitUnicodeString` at `0x180021c34`

## pseudocode

```c
__int64 __fastcall FTCache::FilterInboundNamespace(
        FTCache *this,
        struct _LSAP_DB_TRUSTED_DOMAIN_LIST_ENTRY *a2,
        struct _FILTER_INBOUNDNAMESPACE_REQUEST *a3,
        int a4,
        int a5,
        enum FTCache::OwnershipState *a6,
        enum FTCache::OwnershipState *a7,
        int *a8)
{
  struct FTCache::TDO_ENTRY *v8; // r13
  FTCache *v9; // r15
  const WCHAR *v11; // rdx
  const WCHAR *v14; // rdx
  struct _UNICODE_STRING *v15; // rdx
  _BYTE *v16; // rcx
  int v17; // ebx
  __int64 v18; // rdx
  unsigned int v19; // edi
  int v20; // eax
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  struct FTCache::TDO_ENTRY *v23; // rax
  struct _UNICODE_STRING *v24; // rdi
  int v25; // r15d
  FTCache *v26; // rsi
  struct FTCache::SCANNER_INFO_ENTRY *v27; // rsi
  struct FTCache::SCANNER_INFO_ENTRY *v28; // r13
  int v29; // eax
  int v30; // edx
  int v31; // eax
  int v32; // eax
  unsigned int v34; // [rsp+50h] [rbp-69h] BYREF
  PCUNICODE_STRING String2; // [rsp+58h] [rbp-61h]
  int v36; // [rsp+60h] [rbp-59h]
  int v37; // [rsp+64h] [rbp-55h]
  int v38; // [rsp+68h] [rbp-51h]
  int v39; // [rsp+6Ch] [rbp-4Dh] BYREF
  int v40; // [rsp+70h] [rbp-49h] BYREF
  struct FTCache::DOMAIN_INFO_ENTRY *v41; // [rsp+78h] [rbp-41h] BYREF
  struct FTCache::DOMAIN_INFO_ENTRY *v42; // [rsp+80h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-31h] BYREF
  struct FTCache::SCANNER_INFO_ENTRY *v44; // [rsp+98h] [rbp-21h] BYREF
  struct FTCache::SCANNER_INFO_ENTRY *v45; // [rsp+A0h] [rbp-19h] BYREF
  FTCache *v46; // [rsp+A8h] [rbp-11h]
  struct _UNICODE_STRING v47; // [rsp+B0h] [rbp-9h] BYREF
  FTCache *v48; // [rsp+100h] [rbp+47h] BYREF
  unsigned int v49; // [rsp+108h] [rbp+4Fh] BYREF
  unsigned int v50; // [rsp+110h] [rbp+57h] BYREF

  v48 = this;
  v8 = 0;
  v9 = g_FTCache;
  v11 = (const WCHAR *)*((_QWORD *)a3 + 3);
  v46 = g_FTCache;
  LODWORD(v48) = 0;
  *(_DWORD *)a6 = 3;
  v40 = 0;
  v50 = 0;
  v39 = 0;
  *(_DWORD *)a7 = 3;
  v41 = 0;
  v42 = 0;
  v49 = 0;
  *a8 = 0;
  v34 = 0;
  v44 = 0;
  v45 = 0;
  DestinationString = 0;
  v47 = 0;
  RtlInitUnicodeString(&DestinationString, v11);
  v14 = (const WCHAR *)*((_QWORD *)a3 + 4);
  if ( v14 )
  {
    RtlInitUnicodeString(&v47, v14);
    v15 = &v47;
  }
  else
  {
    v15 = 0;
  }
  String2 = v15;
  v16 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_ZZZ(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)&DestinationString, (__int64)v15);
    v16 = WPP_GLOBAL_Control;
  }
  v17 = 1;
  if ( a2 )
  {
    if ( (*((_BYTE *)a2 + 64) & 0x20) != 0 )
    {
      if ( (v16[28] & 8) == 0 )
      {
LABEL_11:
        v19 = -1073741811;
        goto LABEL_99;
      }
      v18 = 179;
LABEL_10:
      WPP_SF_(*((_QWORD *)v16 + 2), v18, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      v16 = WPP_GLOBAL_Control;
      goto LABEL_11;
    }
    if ( (*((_BYTE *)a2 + 56) & 1) == 0 )
    {
      if ( (v16[28] & 8) == 0 )
        goto LABEL_11;
      v18 = 180;
      goto LABEL_10;
    }
  }
  v20 = FTCache::RebuildCachesIfNecessary(v9, 1, 0);
  v19 = v20;
  if ( v20 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return v19;
    v22 = 181;
    goto LABEL_18;
  }
  LODWORD(a8) = 0;
  v38 = 0;
  v36 = 0;
  v37 = 0;
  if ( !a2 )
  {
    v24 = (struct _UNICODE_STRING *)String2;
LABEL_50:
    v25 = 0;
    goto LABEL_51;
  }
  if ( (*((_BYTE *)a2 + 64) & 8) == 0 )
  {
    if ( !RtlCompareUnicodeString((PCUNICODE_STRING)a2 + 2, &DestinationString, 1u) )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          182,
          &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
          (char *)a2 + 32);
      LODWORD(a8) = 1;
    }
    v24 = (struct _UNICODE_STRING *)String2;
    if ( String2 && !RtlCompareUnicodeString((PCUNICODE_STRING)a2 + 1, String2, 1u) )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Z(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          183,
          &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
          (char *)a2 + 16);
      v38 = 1;
    }
    goto LABEL_50;
  }
  v20 = FTCache::RebuildCachesIfNecessary(v9, 0, 1);
  v19 = v20;
  if ( v20 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return v19;
    v22 = 184;
    goto LABEL_18;
  }
  v23 = (struct FTCache::TDO_ENTRY *)RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)((char *)v9 + 8), (char *)a2 + 16);
  v8 = v23;
  if ( v23 )
  {
    if ( *((struct FTCache::TDO_ENTRY **)v23 + 7) == (struct FTCache::TDO_ENTRY *)((char *)v23 + 56) )
    {
LABEL_28:
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
    }
  }
  else if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_Z(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      185,
      &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
      (char *)a2 + 16);
    goto LABEL_28;
  }
  if ( !RtlCompareUnicodeString((PCUNICODE_STRING)a2 + 2, &DestinationString, 1u) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        187,
        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
        (char *)a2 + 32);
    v36 = 1;
  }
  v24 = (struct _UNICODE_STRING *)String2;
  if ( String2 && !RtlCompareUnicodeString((PCUNICODE_STRING)a2 + 1, String2, 1u) )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_Z(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        188,
        &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids,
        (char *)a2 + 16);
    v37 = 1;
  }
  v25 = 1;
LABEL_51:
  v26 = v46;
  v20 = FTCache::SearchDomainInfoEntries(
          v46,
          v8,
          &DestinationString,
          v24,
          (unsigned int *)&v48,
          &v40,
          &v50,
          &v39,
          &v41,
          &v42);
  v19 = v20;
  if ( v20 < 0 )
  {
    v21 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      return v19;
    v22 = 189;
    goto LABEL_18;
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_qDqDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 190);
  v20 = FTCache::SearchScannerInfoEntries(
          v26,
          v8,
          &DestinationString,
          (struct _UNICODE_STRING *)String2,
          &v49,
          &v34,
          &v44,
          &v45);
  v19 = v20;
  if ( v20 >= 0 )
  {
    v16 = WPP_GLOBAL_Control;
    v27 = v44;
    v28 = v45;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_qDqDDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 192);
      v16 = WPP_GLOBAL_Control;
    }
    if ( v27 && v28 && v27 != v28 && (v16[28] & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)v16 + 2), 193, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids);
      v16 = WPP_GLOBAL_Control;
    }
    if ( a2 )
    {
      if ( !v25 )
      {
        v17 = a5;
        v30 = v38;
        v29 = (int)a8;
LABEL_90:
        if ( v29 )
          v31 = a4 != 0;
        else
          v31 = 3 - (a4 != 0);
        *(_DWORD *)a6 = v31;
        if ( String2 )
        {
          if ( v30 )
            v32 = v17 != 0;
          else
            v32 = 3 - (v17 != 0);
          *(_DWORD *)a7 = v32;
        }
        else
        {
          *(_DWORD *)a7 = 3;
        }
        goto LABEL_99;
      }
      if ( v36 || v27 || (v29 = 0, v41) )
        v29 = 1;
      if ( a4 || (_DWORD)v48 || (a4 = 0, v49) )
        a4 = 1;
      if ( v37 || v28 || (v30 = 0, v42) )
        v30 = 1;
      if ( a5 )
        goto LABEL_90;
    }
    else
    {
      v29 = a4;
      if ( (_DWORD)v48 || (a4 = 0, v49) )
        a4 = 1;
      v30 = a5;
    }
    if ( !v50 && !v34 )
      v17 = 0;
    goto LABEL_90;
  }
  v21 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
    return v19;
  v22 = 191;
LABEL_18:
  WPP_SF_d(v21[2], v22, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, (unsigned int)v20);
  v16 = WPP_GLOBAL_Control;
LABEL_99:
  if ( (v16[28] & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v16 + 2), 194, &WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids, v19);
  return v19;
}

```

## disassembly

```asm
0x180021b94  mov     [rsp-8+arg_18], rbx
0x180021b99  mov     [rsp-8+arg_0], rcx
0x180021b9e  push    rbp
0x180021b9f  push    rsi
0x180021ba0  push    rdi
0x180021ba1  push    r12
0x180021ba3  push    r13
0x180021ba5  push    r14
0x180021ba7  push    r15
0x180021ba9  lea     rbp, [rsp-7]
0x180021bae  sub     rsp, 0C0h
0x180021bb5  mov     rax, [rbp+37h+arg_28]
0x180021bb9  xor     r13d, r13d
0x180021bbc  mov     r15, cs:?g_FTCache@@3PEAVFTCache@@EA; FTCache * g_FTCache
0x180021bc3  mov     r14, rdx
0x180021bc6  mov     rdx, [r8+18h]; SourceString
0x180021bca  xorps   xmm0, xmm0
0x180021bcd  xorps   xmm1, xmm1
0x180021bd0  mov     [rbp+37h+var_48], r15
0x180021bd4  lea     ecx, [r13+3]
0x180021bd8  mov     dword ptr [rbp+37h+arg_0], r13d
0x180021bdc  mov     [rax], ecx
0x180021bde  mov     r12d, r9d
0x180021be1  mov     rax, [rbp+37h+arg_30]
0x180021be5  mov     rbx, r8
0x180021be8  mov     [rbp+37h+var_80], r13d
0x180021bec  mov     [rbp+37h+arg_10], r13d
0x180021bf0  mov     [rbp+37h+var_84], r13d
0x180021bf4  mov     [rax], ecx
0x180021bf6  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x180021bfa  mov     rax, [rbp+37h+arg_38]
0x180021bfe  mov     [rbp+37h+var_78], r13
0x180021c02  mov     [rbp+37h+var_70], r13
0x180021c06  mov     [rbp+37h+arg_8], r13d
0x180021c0a  mov     [rax], r13d
0x180021c0d  mov     [rbp+37h+var_A0], r13d
0x180021c11  mov     [rbp+37h+var_58], r13
0x180021c15  mov     [rbp+37h+var_50], r13
0x180021c19  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x180021c1d  movups  xmmword ptr [rbp+37h+var_40.Length], xmm1
0x180021c21  call    cs:__imp_RtlInitUnicodeString
0x180021c27  mov     rdx, [rbx+20h]; SourceString
0x180021c2b  test    rdx, rdx
0x180021c2e  jz      short loc_180021C40
0x180021c30  lea     rcx, [rbp+37h+var_40]; DestinationString
0x180021c34  call    cs:__imp_RtlInitUnicodeString
0x180021c3a  lea     rdx, [rbp+37h+var_40]
0x180021c3e  jmp     short loc_180021C43
0x180021c40  mov     rdx, r13
0x180021c43  mov     [rbp+37h+String2], rdx
0x180021c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c4e  lea     rsi, [r14+10h]
0x180021c52  test    byte ptr [rcx+1Ch], 8
0x180021c56  jz      short loc_180021C82
0x180021c58  mov     rcx, [rcx+10h]; LoggerHandle
0x180021c5c  mov     rax, r14
0x180021c5f  neg     rax
0x180021c62  mov     [rsp+0F0h+var_C8], rdx; __int64
0x180021c67  lea     rax, [rbp+37h+DestinationString]
0x180021c6b  sbb     r9, r9
0x180021c6e  mov     [rsp+0F0h+var_D0], rax; __int64
0x180021c73  and     r9, rsi
0x180021c76  call    WPP_SF_ZZZ
0x180021c7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180021c82  mov     ebx, 1
0x180021c87  test    r14, r14
0x180021c8a  jz      short loc_180021CD2
0x180021c8c  test    byte ptr [r14+40h], 20h
0x180021c91  jz      short loc_180021CBF
0x180021c93  test    byte ptr [rcx+1Ch], 8
0x180021c97  jz      short loc_180021CB5
0x180021c99  mov     edx, 0B3h
0x180021c9e  mov     rcx, [rcx+10h]
0x180021ca2  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180021ca9  call    WPP_SF_
0x180021cae  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cb5  mov     edi, 0C000000Dh
0x180021cba  jmp     loc_180022189
0x180021cbf  test    [r14+38h], bl
0x180021cc3  jnz     short loc_180021CD2
0x180021cc5  test    byte ptr [rcx+1Ch], 8
0x180021cc9  jz      short loc_180021CB5
0x180021ccb  mov     edx, 0B4h
0x180021cd0  jmp     short loc_180021C9E
0x180021cd2  xor     r8d, r8d; int
0x180021cd5  mov     edx, ebx; int
0x180021cd7  mov     rcx, r15; this
0x180021cda  call    ?RebuildCachesIfNecessary@FTCache@@AEAAJHH@Z; FTCache::RebuildCachesIfNecessary(int,int)
0x180021cdf  mov     edi, eax
0x180021ce1  test    eax, eax
0x180021ce3  jns     short loc_180021D1A
0x180021ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x180021cec  test    byte ptr [rcx+1Ch], 8
0x180021cf0  jz      loc_1800221A7
0x180021cf6  mov     edx, 0B5h
0x180021cfb  mov     rcx, [rcx+10h]
0x180021cff  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180021d06  mov     r9d, eax
0x180021d09  call    WPP_SF_d
0x180021d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d15  jmp     loc_180022189
0x180021d1a  mov     dword ptr [rbp+37h+arg_38], r13d
0x180021d1e  mov     [rbp+37h+var_88], r13d
0x180021d22  mov     [rbp+37h+var_90], r13d
0x180021d26  mov     [rbp+37h+var_8C], r13d
0x180021d2a  test    r14, r14
0x180021d2d  jz      loc_180021EE6
0x180021d33  test    byte ptr [rsi+30h], 8
0x180021d37  jz      loc_180021E59
0x180021d3d  mov     r8d, ebx; int
0x180021d40  xor     edx, edx; int
0x180021d42  mov     rcx, r15; this
0x180021d45  call    ?RebuildCachesIfNecessary@FTCache@@AEAAJHH@Z; FTCache::RebuildCachesIfNecessary(int,int)
0x180021d4a  mov     edi, eax
0x180021d4c  test    eax, eax
0x180021d4e  jns     short loc_180021D68
0x180021d50  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d57  test    byte ptr [rcx+1Ch], 8
0x180021d5b  jz      loc_1800221A7
0x180021d61  mov     edx, 0B8h
0x180021d66  jmp     short loc_180021CFB
0x180021d68  lea     rcx, [r15+8]; Table
0x180021d6c  mov     rdx, rsi; Buffer
0x180021d6f  call    cs:__imp_RtlLookupElementGenericTableAvl
0x180021d75  mov     r13, rax
0x180021d78  test    rax, rax
0x180021d7b  jnz     short loc_180021DA4
0x180021d7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180021d84  test    byte ptr [rcx+1Ch], 8
0x180021d88  jz      short loc_180021DCF
0x180021d8a  mov     rcx, [rcx+10h]
0x180021d8e  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180021d95  mov     edx, 0B9h
0x180021d9a  mov     r9, rsi
0x180021d9d  call    WPP_SF_Z
0x180021da2  jmp     short loc_180021DAD
0x180021da4  add     rax, 38h ; '8'
0x180021da8  cmp     [rax], rax
0x180021dab  jnz     short loc_180021DCF
0x180021dad  mov     rcx, cs:WPP_GLOBAL_Control
0x180021db4  test    byte ptr [rcx+1Ch], 8
0x180021db8  jz      short loc_180021DCF
0x180021dba  mov     rcx, [rcx+10h]
0x180021dbe  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180021dc5  mov     edx, 0BAh
0x180021dca  call    WPP_SF_
0x180021dcf  mov     r8b, bl; CaseInsensitive
0x180021dd2  lea     rdx, [rbp+37h+DestinationString]; String2
0x180021dd6  lea     rcx, [r14+20h]; String1
0x180021dda  call    cs:__imp_RtlCompareUnicodeString
0x180021de0  test    eax, eax
0x180021de2  jnz     short loc_180021E0D
0x180021de4  mov     rcx, cs:WPP_GLOBAL_Control
0x180021deb  test    byte ptr [rcx+1Ch], 8
0x180021def  jz      short loc_180021E0A
0x180021df1  mov     rcx, [rcx+10h]
0x180021df5  lea     r9, [r14+20h]
0x180021df9  mov     edx, 0BBh
0x180021dfe  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180021e05  call    WPP_SF_Z
0x180021e0a  mov     [rbp+37h+var_90], ebx
0x180021e0d  mov     rdi, [rbp+37h+String2]
0x180021e11  test    rdi, rdi
0x180021e14  jz      short loc_180021E51
0x180021e16  mov     r8b, bl; CaseInsensitive
0x180021e19  mov     rdx, rdi; String2
0x180021e1c  mov     rcx, rsi; String1
0x180021e1f  call    cs:__imp_RtlCompareUnicodeString
0x180021e25  test    eax, eax
0x180021e27  jnz     short loc_180021E51
0x180021e29  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e30  test    byte ptr [rcx+1Ch], 8
0x180021e34  jz      short loc_180021E4E
0x180021e36  mov     rcx, [rcx+10h]
0x180021e3a  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180021e41  mov     edx, 0BCh
0x180021e46  mov     r9, rsi
0x180021e49  call    WPP_SF_Z
0x180021e4e  mov     [rbp+37h+var_8C], ebx
0x180021e51  mov     r15d, ebx
0x180021e54  jmp     loc_180021EED
0x180021e59  test    r14, r14
0x180021e5c  jz      loc_180021EE6
0x180021e62  mov     r8b, bl; CaseInsensitive
0x180021e65  lea     rdx, [rbp+37h+DestinationString]; String2
0x180021e69  lea     rcx, [rsi+10h]; String1
0x180021e6d  call    cs:__imp_RtlCompareUnicodeString
0x180021e73  test    eax, eax
0x180021e75  jnz     short loc_180021EA0
0x180021e77  mov     rcx, cs:WPP_GLOBAL_Control
0x180021e7e  test    byte ptr [rcx+1Ch], 8
0x180021e82  jz      short loc_180021E9D
0x180021e84  mov     rcx, [rcx+10h]
0x180021e88  lea     r9, [rsi+10h]
0x180021e8c  mov     edx, 0B6h
0x180021e91  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180021e98  call    WPP_SF_Z
0x180021e9d  mov     dword ptr [rbp+37h+arg_38], ebx
0x180021ea0  mov     rdi, [rbp+37h+String2]
0x180021ea4  test    rdi, rdi
0x180021ea7  jz      short loc_180021EEA
0x180021ea9  mov     r8b, bl; CaseInsensitive
0x180021eac  mov     rdx, rdi; String2
0x180021eaf  mov     rcx, rsi; String1
0x180021eb2  call    cs:__imp_RtlCompareUnicodeString
0x180021eb8  test    eax, eax
0x180021eba  jnz     short loc_180021EEA
0x180021ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180021ec3  test    byte ptr [rcx+1Ch], 8
0x180021ec7  jz      short loc_180021EE1
0x180021ec9  mov     rcx, [rcx+10h]
0x180021ecd  lea     r8, WPP_7857d0cd51573a627c8b22c75b20a347_Traceguids
0x180021ed4  mov     edx, 0B7h
0x180021ed9  mov     r9, rsi
0x180021edc  call    WPP_SF_Z
0x180021ee1  mov     [rbp+37h+var_88], ebx
0x180021ee4  jmp     short loc_180021EEA
0x180021ee6  mov     rdi, [rbp+37h+String2]
0x180021eea  xor     r15d, r15d
0x180021eed  mov     rsi, [rbp+37h+var_48]
0x180021ef1  lea     rax, [rbp+37h+var_70]
0x180021ef5  mov     [rsp+0F0h+var_A8], rax; struct FTCache::DOMAIN_INFO_ENTRY **
0x180021efa  lea     r8, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x180021efe  lea     rax, [rbp+37h+var_78]
0x180021f02  mov     r9, rdi; struct _UNICODE_STRING *
0x180021f05  mov     [rsp+0F0h+var_B0], rax; struct FTCache::DOMAIN_INFO_ENTRY **
0x180021f0a  mov     rdx, r13; struct FTCache::TDO_ENTRY *
0x180021f0d  lea     rax, [rbp+37h+var_84]
0x180021f11  mov     rcx, rsi; this
0x180021f14  mov     [rsp+0F0h+var_B8], rax; int *
0x180021f19  lea     rax, [rbp+37h+arg_10]
0x180021f1d  mov     [rsp+0F0h+var_C0], rax; unsigned int *
0x180021f22  lea     rax, [rbp+37h+var_80]
0x180021f26  mov     [rsp+0F0h+var_C8], rax; int *
0x180021f2b  lea     rax, [rbp+37h+arg_0]
0x180021f2f  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x180021f34  call    ?SearchDomainInfoEntries@FTCache@@AEAAJPEAUTDO_ENTRY@1@PEAU_UNICODE_STRING@@1PEAKPEAH23PEAPEAUDOMAIN_INFO_ENTRY@1@4@Z; FTCache::SearchDomainInfoEntries(FTCache::TDO_ENTRY *,_UNICODE_STRING *,_UNICODE_STRING *,ulong *,int *,ulong *,int *,FTCache::DOMAIN_INFO_ENTRY * *,FTCache::DOMAIN_INFO_ENTRY * *)
0x180021f39  mov     edi, eax
0x180021f3b  test    eax, eax
0x180021f3d  jns     short loc_180021F5A
0x180021f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180021f46  test    byte ptr [rcx+1Ch], 8
0x180021f4a  jz      loc_1800221A7
0x180021f50  mov     edx, 0BDh
0x180021f55  jmp     loc_180021CFB
0x180021f5a  mov     r8, cs:WPP_GLOBAL_Control
0x180021f61  test    byte ptr [r8+1Ch], 8
0x180021f66  jz      short loc_180021FBD
0x180021f68  mov     r10, [rbp+37h+var_70]
0x180021f6c  test    r10, r10
0x180021f6f  jz      short loc_180021F7A
0x180021f71  mov     ecx, [r10+80h]
0x180021f78  jmp     short loc_180021F7C
0x180021f7a  xor     ecx, ecx
0x180021f7c  mov     r9, [rbp+37h+var_78]
0x180021f80  test    r9, r9
0x180021f83  jz      short loc_180021F8E
0x180021f85  mov     eax, [r9+80h]
0x180021f8c  jmp     short loc_180021F90
0x180021f8e  xor     eax, eax
0x180021f90  mov     r11d, [rbp+37h+arg_10]
0x180021f94  mov     edx, 0BEh
0x180021f99  mov     dword ptr [rsp+0F0h+var_B0], r11d
0x180021f9e  mov     r11d, dword ptr [rbp+37h+arg_0]
0x180021fa2  mov     dword ptr [rsp+0F0h+var_B8], r11d
0x180021fa7  mov     dword ptr [rsp+0F0h+var_C0], ecx
0x180021fab  mov     rcx, [r8+10h]
0x180021faf  mov     [rsp+0F0h+var_C8], r10
0x180021fb4  mov     dword ptr [rsp+0F0h+var_D0], eax
0x180021fb8  call    WPP_SF_qDqDDD
0x180021fbd  mov     r9, [rbp+37h+String2]; struct _UNICODE_STRING *
0x180021fc1  lea     rax, [rbp+37h+var_50]
0x180021fc5  mov     [rsp+0F0h+var_B8], rax; struct FTCache::SCANNER_INFO_ENTRY **
0x180021fca  lea     r8, [rbp+37h+DestinationString]; struct _UNICODE_STRING *
0x180021fce  lea     rax, [rbp+37h+var_58]
0x180021fd2  mov     rdx, r13; struct FTCache::TDO_ENTRY *
0x180021fd5  mov     [rsp+0F0h+var_C0], rax; struct FTCache::SCANNER_INFO_ENTRY **
0x180021fda  mov     rcx, rsi; this
0x180021fdd  lea     rax, [rbp+37h+var_A0]
0x180021fe1  mov     [rsp+0F0h+var_C8], rax; unsigned int *
0x180021fe6  lea     rax, [rbp+37h+arg_8]
0x180021fea  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x180021fef  call    ?SearchScannerInfoEntries@FTCache@@AEAAJPEAUTDO_ENTRY@1@PEAU_UNICODE_STRING@@1PEAK2PEAPEAUSCANNER_INFO_ENTRY@1@3@Z; FTCache::SearchScannerInfoEntries(FTCache::TDO_ENTRY *,_UNICODE_STRING *,_UNICODE_STRING *,ulong *,ulong *,FTCache::SCANNER_INFO_ENTRY * *,FTCache::SCANNER_INFO_ENTRY * *)
0x180021ff4  xor     r9d, r9d
0x180021ff7  mov     edi, eax
0x180021ff9  test    eax, eax
0x180021ffb  jns     short loc_180022018
0x180021ffd  mov     rcx, cs:WPP_GLOBAL_Control
0x180022004  test    byte ptr [rcx+1Ch], 8
0x180022008  jz      loc_1800221A7
0x18002200e  mov     edx, 0BFh
0x180022013  jmp     loc_180021CFB
0x180022018  mov     rcx, cs:WPP_GLOBAL_Control
0x18002201f  mov     rsi, [rbp+37h+var_58]
0x180022023  mov     r13, [rbp+37h+var_50]
0x180022027  test    byte ptr [rcx+1Ch], 8
0x18002202b  jz      short loc_180022083
0x18002202d  test    r13, r13
0x180022030  jz      short loc_180022038
0x180022032  mov     r8d, [r13+60h]
  ... truncated ...
```
