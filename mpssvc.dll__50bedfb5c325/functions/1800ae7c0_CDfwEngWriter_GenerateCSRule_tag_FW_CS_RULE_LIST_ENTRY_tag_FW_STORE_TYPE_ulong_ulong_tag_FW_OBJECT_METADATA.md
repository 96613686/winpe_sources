# CDfwEngWriter::GenerateCSRule(_tag_FW_CS_RULE *,_LIST_ENTRY *,_tag_FW_STORE_TYPE,ulong,ulong,_tag_FW_OBJECT_METADATA *)

- ea: `0x1800ae7c0`
- end: `0x1800af156`
- name: `?GenerateCSRule@CDfwEngWriter@@EEAAJPEAU_tag_FW_CS_RULE@@PEAU_LIST_ENTRY@@W4_tag_FW_STORE_TYPE@@KKPEAU_tag_FW_OBJECT_METADATA@@@Z`
- size: `2454`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800089bc`
- `0x18000a710`
- `0x1800192e0`
- `0x18002dcc0`
- `0x1800424c0`
- `0x18006a710`
- `0x18006c3bc`
- `0x1800729c0`
- `0x180073488`
- `0x18007f11c`
- `0x18008ee6c`
- `0x18008f350`
- `0x180090c28`
- `0x1800ae7c0`
- `0x1800af778`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af10e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af126`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af10e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800af126`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800aed8e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800aee38`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800aed8e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800aee38`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800aedd2`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800aee7c`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800aedd2`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800aee7c`

## string_xrefs

- `0x1800aec81`: `mpssvc.dll`

## pseudocode

```c
__int64 __fastcall CDfwEngWriter::GenerateCSRule(
        CDfwEngWriter *a1,
        __int64 a2,
        struct _LIST_ENTRY *a3,
        unsigned int a4,
        int a5,
        char a6,
        struct _tag_FW_OBJECT_METADATA *a7)
{
  struct _LIST_ENTRY *v7; // rdi
  CDfwEngWriter *v9; // rsi
  __int64 v11; // r14
  __int64 v12; // rdx
  unsigned int v13; // esi
  __int64 v14; // rax
  __int64 *BlobContainerWithCriteria; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 *v20; // rax
  unsigned int i; // edx
  const wchar_t *v22; // rsi
  const wchar_t *v23; // rdx
  __int64 v24; // rax
  __int64 *v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 *v31; // rax
  unsigned int v32; // esi
  __int64 v33; // rcx
  __int64 v34; // rax
  int v35; // edx
  const WCHAR *v36; // rcx
  const WCHAR *v37; // rcx
  int CSRule; // eax
  __int64 v39; // rcx
  __int64 v40; // rdx
  _OWORD *v41; // rax
  _OWORD *v42; // rcx
  __int64 v43; // rdx
  __int128 v44; // xmm1
  __int128 v45; // xmm0
  __int128 v46; // xmm1
  __int128 v47; // xmm0
  __int128 v48; // xmm1
  __int128 v49; // xmm0
  __int128 v50; // xmm1
  struct _LIST_ENTRY *v51; // r9
  _OWORD *v52; // rcx
  _OWORD *v53; // rax
  __int128 v54; // xmm1
  __int128 v55; // xmm0
  __int128 v56; // xmm1
  __int128 v57; // xmm0
  __int128 v58; // xmm1
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  struct _LIST_ENTRY *v61; // r9
  CDfwEngWriter *v62; // rcx
  unsigned int v64; // [rsp+30h] [rbp-D0h] BYREF
  struct _LIST_ENTRY *v65; // [rsp+38h] [rbp-C8h]
  CDfwEngWriter *v66; // [rsp+40h] [rbp-C0h]
  _BYTE v67[528]; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+260h] [rbp+160h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v70[8]; // [rsp+270h] [rbp+170h] BYREF
  __int64 v71; // [rsp+278h] [rbp+178h]
  __int64 v72; // [rsp+280h] [rbp+180h]
  __int64 v73; // [rsp+288h] [rbp+188h]
  __int64 v74; // [rsp+290h] [rbp+190h]
  int v75; // [rsp+2A0h] [rbp+1A0h]
  int v76; // [rsp+30Ch] [rbp+20Ch]
  int v77; // [rsp+31Ch] [rbp+21Ch]
  PSECURITY_DESCRIPTOR v78; // [rsp+320h] [rbp+220h]
  PSECURITY_DESCRIPTOR v79; // [rsp+328h] [rbp+228h]

  v7 = a3;
  v65 = a3;
  v9 = a1;
  v66 = a1;
  memset_0(v70, 0, 0xC0u);
  v11 = 4;
  SecurityDescriptor = 0;
  hMem = 0;
  v77 = -1;
  if ( *(_DWORD *)(a2 + 336) == 4 )
    goto LABEL_96;
  v12 = *(_QWORD *)(a2 + 312);
  v13 = 0;
  v64 = 0;
  v14 = StoreOverridingDefaultSet(a4, v12, 0, 1);
  BlobContainerWithCriteria = (__int64 *)FwLookInRepoForFirstBlobContainerWithCriteria(
                                           v14 + 120,
                                           FwCryptoSetMatchesSetId,
                                           *(_QWORD *)(a2 + 312));
  if ( !BlobContainerWithCriteria )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_SS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        109,
        (unsigned int)WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
        *(_QWORD *)(a2 + 16),
        *(_QWORD *)(a2 + 312));
    *(_DWORD *)(a2 + 384) = 2097153;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_72;
    v17 = 110;
    goto LABEL_71;
  }
  v18 = *(_QWORD *)(a2 + 328);
  v71 = *BlobContainerWithCriteria;
  if ( v18 )
  {
    v19 = StoreOverridingDefaultSet(a4, v18, 0, 2);
    v20 = (__int64 *)FwLookInRepoForFirstBlobContainerWithCriteria(
                       v19 + 144,
                       FwCryptoSetMatchesSetId,
                       *(_QWORD *)(a2 + 328));
    if ( !v20 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_SS(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          111,
          (unsigned int)WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
          *(_QWORD *)(a2 + 16),
          *(_QWORD *)(a2 + 328));
      *(_DWORD *)(a2 + 384) = 2097154;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_72;
      v17 = 112;
      goto LABEL_71;
    }
    v72 = *v20;
    if ( *(_DWORD *)(v72 + 48) )
    {
      for ( i = 0; i < *(_DWORD *)(v71 + 48); ++i )
      {
        if ( *(_DWORD *)(*(_QWORD *)(v71 + 56) + 24LL * i) == 3 )
        {
          *(_DWORD *)(a2 + 384) = 2097156;
          v16 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
            {
              WPP_SF_S(
                *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                113,
                WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
                *(_QWORD *)(a2 + 16));
              v16 = WPP_GLOBAL_Control;
            }
            if ( (_UNKNOWN *)v16 != &WPP_GLOBAL_Control && (*(_BYTE *)(v16 + 28) & 1) != 0 )
            {
              v17 = 114;
              goto LABEL_71;
            }
          }
          goto LABEL_72;
        }
      }
    }
  }
  else
  {
    v72 = 0;
  }
  v22 = L"{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}";
  if ( (a6 & 4) != 0 )
    v23 = *(const wchar_t **)(a2 + 344);
  else
    v23 = L"{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}";
  v24 = StoreOverridingDefaultSet(a4, v23, 1, 1);
  if ( (a6 & 4) != 0 )
    v22 = *(const wchar_t **)(a2 + 344);
  v25 = (__int64 *)FwLookInRepoForFirstBlobContainerWithCriteria(v24 + 192, FwCryptoSetMatchesSetId, v22);
  if ( !v25 )
  {
    if ( (a6 & 4) == 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 115, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
      MicrosoftTelemetryAssertTriggeredNoArgs(v27);
      v13 = 0;
      v28 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v29 = 116;
LABEL_42:
        WPP_SF_d(*(_QWORD *)(v28 + 16), v29, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids, 0);
        goto LABEL_118;
      }
      goto LABEL_118;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_SS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        117,
        (unsigned int)WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
        *(_QWORD *)(a2 + 16),
        *(_QWORD *)(a2 + 344));
    *(_DWORD *)(a2 + 384) = 2097157;
    v13 = 0;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_72;
    v17 = 118;
LABEL_71:
    WPP_SF_d(*(_QWORD *)(v16 + 16), v17, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids, 0);
    goto LABEL_72;
  }
  v73 = *v25;
  if ( (a6 & 4) != 0 )
  {
    if ( *(_DWORD *)(a2 + 496) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v26);
    *(_DWORD *)(a2 + 496) = 7;
  }
  else
  {
    v30 = StoreOverridingDefaultSet(a4, *(_QWORD *)(a2 + 320), 1, 2);
    v31 = (__int64 *)FwLookInRepoForFirstBlobContainerWithCriteria(
                       v30 + 216,
                       FwCryptoSetMatchesSetId,
                       *(_QWORD *)(a2 + 320));
    if ( !v31 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_SS(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          119,
          (unsigned int)WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
          *(_QWORD *)(a2 + 16),
          *(_QWORD *)(a2 + 320));
      *(_DWORD *)(a2 + 384) = 2097155;
      v13 = 0;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_72;
      v17 = 120;
      goto LABEL_71;
    }
    v74 = *v31;
    v64 = 0x10000;
    if ( !(unsigned int)IsAuthNoEncapRuleValid(a2, 0, v74, v71, (__int64)&v64) )
    {
      v32 = v64;
      if ( v64 == 2097158 )
      {
        v33 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          goto LABEL_68;
        v34 = *(_QWORD *)(a2 + 320);
        v35 = 121;
      }
      else
      {
        if ( v64 != 2097159 )
        {
          MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v64, 0);
          goto LABEL_68;
        }
        v33 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          goto LABEL_68;
        v34 = *(_QWORD *)(a2 + 312);
        v35 = 122;
      }
      WPP_SF_SS(
        *(_QWORD *)(v33 + 16),
        v35,
        (unsigned int)WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids,
        *(_QWORD *)(a2 + 16),
        v34);
LABEL_68:
      *(_DWORD *)(a2 + 384) = v32;
      v13 = 0;
      v64 = 1;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_72:
        FwAuditLogRuntimeError(v16, *(_QWORD *)(a2 + 16), *(_QWORD *)(a2 + 24), *(unsigned int *)(a2 + 384));
        if ( v64 == 1 )
          FwEventCSRuleNotApplied(*(unsigned __int16 **)(a2 + 16), *(unsigned __int16 **)(a2 + 24));
        goto LABEL_118;
      }
      v17 = 123;
      goto LABEL_71;
    }
  }
  v36 = *(const WCHAR **)(a2 + 504);
  if ( !v36 )
  {
LABEL_86:
    v37 = *(const WCHAR **)(a2 + 512);
    if ( v37 )
    {
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v37, 1u, &hMem, 0) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 126, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
        FwMetaDataAddEnforcementState(a7, 22);
        v13 = 0;
        *(_DWORD *)(a2 + 384) = 524309;
        v28 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v29 = 127;
          goto LABEL_42;
        }
        goto LABEL_118;
      }
      v79 = hMem;
    }
    v7 = v65;
    v9 = v66;
LABEL_96:
    v75 = a5;
    if ( (a6 & 8) != 0 )
    {
      v76 = 12;
      CSRule = CDfwEngWriter::HelperGenerateCSRule(
                 v9,
                 (struct _tag_FW_CS_RULE *)a2,
                 (struct _FW_CS_RULE_INT_ *)v70,
                 v7,
                 a7,
                 0);
      v13 = CSRule;
      if ( CSRule >= 0 )
        goto LABEL_118;
      v39 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_116;
      v40 = 128;
    }
    else
    {
      v41 = (_OWORD *)a2;
      v42 = v67;
      v43 = 4;
      do
      {
        v44 = v41[1];
        *v42 = *v41;
        v45 = v41[2];
        v42[1] = v44;
        v46 = v41[3];
        v42[2] = v45;
        v47 = v41[4];
        v42[3] = v46;
        v48 = v41[5];
        v42[4] = v47;
        v49 = v41[6];
        v42[5] = v48;
        v50 = v41[7];
        v41 += 8;
        v42[6] = v49;
        v42[7] = v50;
        v42 += 8;
        --v43;
      }
      while ( v43 );
      v51 = v65;
      *(_QWORD *)v42 = *(_QWORD *)v41;
      v76 = (a6 & 4) != 0 ? 0xA : 0;
      CSRule = CDfwEngWriter::HelperGenerateCSRule(
                 v9,
                 (struct _tag_FW_CS_RULE *)a2,
                 (struct _FW_CS_RULE_INT_ *)v70,
                 v51,
                 a7,
                 0);
      v13 = CSRule;
      if ( CSRule >= 0 )
      {
        if ( (a6 & 2) == 0 )
          goto LABEL_118;
        if ( *(_DWORD *)(a2 + 40) == 0x7FFFFFFF )
          goto LABEL_118;
        v52 = (_OWORD *)a2;
        v53 = v67;
        do
        {
          v54 = v53[1];
          *v52 = *v53;
          v55 = v53[2];
          v52[1] = v54;
          v56 = v53[3];
          v52[2] = v55;
          v57 = v53[4];
          v52[3] = v56;
          v58 = v53[5];
          v52[4] = v57;
          v59 = v53[6];
          v52[5] = v58;
          v60 = v53[7];
          v53 += 8;
          v52[6] = v59;
          v52[7] = v60;
          v52 += 8;
          --v11;
        }
        while ( v11 );
        v61 = v65;
        *(_QWORD *)v52 = *(_QWORD *)v53;
        v62 = v66;
        *(_DWORD *)(a2 + 40) = 0x7FFFFFFF;
        v76 = (a6 & 4) != 0 ? 0xA : 0;
        CSRule = CDfwEngWriter::HelperGenerateCSRule(
                   v62,
                   (struct _tag_FW_CS_RULE *)a2,
                   (struct _FW_CS_RULE_INT_ *)v70,
                   v61,
                   a7,
                   1);
        v13 = CSRule;
        if ( CSRule >= 0 )
          goto LABEL_118;
        v39 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_116;
        v40 = 130;
      }
      else
      {
        v39 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
LABEL_116:
          if ( (*(_DWORD *)(a2 + 384) & 0x200000) != 0 )
            v13 = 0;
          goto LABEL_118;
        }
        v40 = 129;
      }
    }
    WPP_SF_d(*(_QWORD *)(v39 + 16), v40, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids, (unsigned int)CSRule);
    goto LABEL_116;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v36, 1u, &SecurityDescriptor, 0) )
  {
    v78 = SecurityDescriptor;
    goto LABEL_86;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 124, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids);
  FwMetaDataAddEnforcementState(a7, 21);
  v13 = 0;
  *(_DWORD *)(a2 + 384) = 524308;
  v28 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v29 = 125;
    goto LABEL_42;
  }
LABEL_118:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( hMem )
    LocalFree(hMem);
  return v13;
}

```

## disassembly

```asm
0x1800ae7c0  push    rbp
0x1800ae7c2  push    rbx
0x1800ae7c3  push    rsi
0x1800ae7c4  push    rdi
0x1800ae7c5  push    r13
0x1800ae7c7  push    r14
0x1800ae7c9  push    r15
0x1800ae7cb  lea     rbp, [rsp-240h]
0x1800ae7d3  sub     rsp, 340h
0x1800ae7da  mov     rax, cs:__security_cookie
0x1800ae7e1  xor     rax, rsp
0x1800ae7e4  mov     [rbp+270h+var_40], rax
0x1800ae7eb  mov     r13, [rbp+270h+arg_30]
0x1800ae7f2  mov     rdi, r8
0x1800ae7f5  mov     [rsp+370h+var_338], r8
0x1800ae7fa  mov     rbx, rdx
0x1800ae7fd  mov     rsi, rcx
0x1800ae800  mov     [rsp+370h+var_330], rcx
0x1800ae805  xor     edx, edx; Val
0x1800ae807  lea     rcx, [rbp+270h+var_100]; void *
0x1800ae80e  mov     r8d, 0C0h; Size
0x1800ae814  mov     r15d, r9d
0x1800ae817  call    memset_0
0x1800ae81c  mov     r14d, 4
0x1800ae822  mov     [rbp+270h+SecurityDescriptor], 0
0x1800ae82d  mov     [rbp+270h+hMem], 0
0x1800ae838  mov     [rbp+270h+var_54], 0FFFFFFFFh
0x1800ae842  cmp     [rbx+150h], r14d
0x1800ae849  jz      loc_1800AEECE
0x1800ae84f  mov     rdx, [rbx+138h]
0x1800ae856  lea     r9d, [r14-3]
0x1800ae85a  xor     esi, esi
0x1800ae85c  xor     r8d, r8d
0x1800ae85f  mov     ecx, r15d
0x1800ae862  mov     [rsp+370h+var_340], esi
0x1800ae866  call    StoreOverridingDefaultSet
0x1800ae86b  mov     r8, [rbx+138h]
0x1800ae872  lea     rdx, FwCryptoSetMatchesSetId
0x1800ae879  lea     rcx, [rax+78h]
0x1800ae87d  call    FwLookInRepoForFirstBlobContainerWithCriteria
0x1800ae882  test    rax, rax
0x1800ae885  jnz     short loc_1800AE8F1
0x1800ae887  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae88e  lea     rdi, WPP_GLOBAL_Control
0x1800ae895  cmp     rcx, rdi
0x1800ae898  jz      short loc_1800AE8C3
0x1800ae89a  test    [rcx+1Ch], r14b
0x1800ae89e  jz      short loc_1800AE8C3
0x1800ae8a0  mov     rax, [rbx+138h]
0x1800ae8a7  lea     edx, [rsi+6Dh]
0x1800ae8aa  mov     r9, [rbx+10h]
0x1800ae8ae  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800ae8b5  mov     rcx, [rcx+10h]
0x1800ae8b9  mov     [rsp+370h+var_350], rax
0x1800ae8be  call    WPP_SF_SS
0x1800ae8c3  mov     dword ptr [rbx+180h], 200001h
0x1800ae8cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae8d4  cmp     rcx, rdi
0x1800ae8d7  jz      loc_1800AED20
0x1800ae8dd  test    byte ptr [rcx+1Ch], 1
0x1800ae8e1  jz      loc_1800AED20
0x1800ae8e7  mov     edx, 6Eh ; 'n'
0x1800ae8ec  jmp     loc_1800AED0D
0x1800ae8f1  mov     rdx, [rbx+148h]
0x1800ae8f8  mov     rax, [rax]
0x1800ae8fb  mov     [rbp+270h+var_F8], rax
0x1800ae902  test    rdx, rdx
0x1800ae905  jz      loc_1800AEA43
0x1800ae90b  mov     r9d, 2
0x1800ae911  xor     r8d, r8d
0x1800ae914  mov     ecx, r15d
0x1800ae917  call    StoreOverridingDefaultSet
0x1800ae91c  mov     r8, [rbx+148h]
0x1800ae923  lea     rdx, FwCryptoSetMatchesSetId
0x1800ae92a  lea     rcx, [rax+90h]
0x1800ae931  call    FwLookInRepoForFirstBlobContainerWithCriteria
0x1800ae936  test    rax, rax
0x1800ae939  jnz     short loc_1800AE9A5
0x1800ae93b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae942  lea     rdi, WPP_GLOBAL_Control
0x1800ae949  cmp     rcx, rdi
0x1800ae94c  jz      short loc_1800AE977
0x1800ae94e  test    [rcx+1Ch], r14b
0x1800ae952  jz      short loc_1800AE977
0x1800ae954  mov     r9, [rbx+10h]
0x1800ae958  lea     edx, [rax+6Fh]
0x1800ae95b  mov     rax, [rbx+148h]
0x1800ae962  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800ae969  mov     rcx, [rcx+10h]
0x1800ae96d  mov     [rsp+370h+var_350], rax
0x1800ae972  call    WPP_SF_SS
0x1800ae977  mov     dword ptr [rbx+180h], 200002h
0x1800ae981  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae988  cmp     rcx, rdi
0x1800ae98b  jz      loc_1800AED20
0x1800ae991  test    byte ptr [rcx+1Ch], 1
0x1800ae995  jz      loc_1800AED20
0x1800ae99b  mov     edx, 70h ; 'p'
0x1800ae9a0  jmp     loc_1800AED0D
0x1800ae9a5  mov     rax, [rax]
0x1800ae9a8  mov     [rbp+270h+var_F0], rax
0x1800ae9af  cmp     [rax+30h], esi
0x1800ae9b2  jbe     loc_1800AEA4A
0x1800ae9b8  mov     rax, [rbp+270h+var_F8]
0x1800ae9bf  mov     edx, esi
0x1800ae9c1  mov     r9, [rax+38h]
0x1800ae9c5  mov     r8d, [rax+30h]
0x1800ae9c9  cmp     edx, r8d
0x1800ae9cc  jnb     short loc_1800AEA4A
0x1800ae9ce  mov     eax, edx
0x1800ae9d0  lea     rcx, [rax+rax*2]
0x1800ae9d4  cmp     dword ptr [r9+rcx*8], 3
0x1800ae9d9  jz      short loc_1800AE9DF
0x1800ae9db  inc     edx
0x1800ae9dd  jmp     short loc_1800AE9C9
0x1800ae9df  mov     dword ptr [rbx+180h], 200004h
0x1800ae9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae9f0  lea     rdi, WPP_GLOBAL_Control
0x1800ae9f7  cmp     rcx, rdi
0x1800ae9fa  jz      loc_1800AED20
0x1800aea00  test    [rcx+1Ch], r14b
0x1800aea04  jz      short loc_1800AEA26
0x1800aea06  mov     r9, [rbx+10h]
0x1800aea0a  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800aea11  mov     rcx, [rcx+10h]
0x1800aea15  mov     edx, 71h ; 'q'
0x1800aea1a  call    WPP_SF_S
0x1800aea1f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aea26  cmp     rcx, rdi
0x1800aea29  jz      loc_1800AED20
0x1800aea2f  test    byte ptr [rcx+1Ch], 1
0x1800aea33  jz      loc_1800AED20
0x1800aea39  mov     edx, 72h ; 'r'
0x1800aea3e  jmp     loc_1800AED0D
0x1800aea43  mov     [rbp+270h+var_F0], rsi
0x1800aea4a  mov     edi, dword ptr [rbp+270h+arg_28]
0x1800aea50  lea     rsi, aE5a5d32a4bce4e_1; "{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}"
0x1800aea57  and     edi, r14d
0x1800aea5a  jz      short loc_1800AEA65
0x1800aea5c  mov     rdx, [rbx+158h]
0x1800aea63  jmp     short loc_1800AEA68
0x1800aea65  mov     rdx, rsi
0x1800aea68  mov     eax, 1
0x1800aea6d  mov     ecx, r15d
0x1800aea70  mov     r9d, eax
0x1800aea73  mov     r8d, eax
0x1800aea76  call    StoreOverridingDefaultSet
0x1800aea7b  test    edi, edi
0x1800aea7d  jz      short loc_1800AEA86
0x1800aea7f  mov     rsi, [rbx+158h]
0x1800aea86  lea     rcx, [rax+0C0h]
0x1800aea8d  mov     r8, rsi
0x1800aea90  lea     rdx, FwCryptoSetMatchesSetId
0x1800aea97  call    FwLookInRepoForFirstBlobContainerWithCriteria
0x1800aea9c  test    rax, rax
0x1800aea9f  jnz     loc_1800AEB7D
0x1800aeaa5  test    edi, edi
0x1800aeaa7  jnz     short loc_1800AEB11
0x1800aeaa9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeab0  lea     rdi, WPP_GLOBAL_Control
0x1800aeab7  cmp     rcx, rdi
0x1800aeaba  jz      short loc_1800AEAD5
0x1800aeabc  test    byte ptr [rcx+1Ch], 1
0x1800aeac0  jz      short loc_1800AEAD5
0x1800aeac2  mov     rcx, [rcx+10h]
0x1800aeac6  lea     edx, [rax+73h]
0x1800aeac9  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800aead0  call    WPP_SF_
0x1800aead5  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "FALSE", "failed to find Phase 1 Crypto Set")
0x1800aeada  xor     esi, esi
0x1800aeadc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeae3  cmp     rcx, rdi
0x1800aeae6  jz      loc_1800AF102
0x1800aeaec  test    byte ptr [rcx+1Ch], 1
0x1800aeaf0  jz      loc_1800AF102
0x1800aeaf6  lea     edx, [rsi+74h]
0x1800aeaf9  mov     rcx, [rcx+10h]
0x1800aeafd  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800aeb04  xor     r9d, r9d
0x1800aeb07  call    WPP_SF_d
0x1800aeb0c  jmp     loc_1800AF102
0x1800aeb11  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeb18  lea     rdi, WPP_GLOBAL_Control
0x1800aeb1f  cmp     rcx, rdi
0x1800aeb22  jz      short loc_1800AEB4F
0x1800aeb24  test    [rcx+1Ch], r14b
0x1800aeb28  jz      short loc_1800AEB4F
0x1800aeb2a  mov     rax, [rbx+158h]
0x1800aeb31  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800aeb38  mov     r9, [rbx+10h]
0x1800aeb3c  mov     edx, 75h ; 'u'
0x1800aeb41  mov     rcx, [rcx+10h]
0x1800aeb45  mov     [rsp+370h+var_350], rax
0x1800aeb4a  call    WPP_SF_SS
0x1800aeb4f  mov     dword ptr [rbx+180h], 200005h
0x1800aeb59  xor     esi, esi
0x1800aeb5b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeb62  cmp     rcx, rdi
0x1800aeb65  jz      loc_1800AED20
0x1800aeb6b  test    byte ptr [rcx+1Ch], 1
0x1800aeb6f  jz      loc_1800AED20
0x1800aeb75  lea     edx, [rsi+76h]
0x1800aeb78  jmp     loc_1800AED0D
0x1800aeb7d  mov     rax, [rax]
0x1800aeb80  mov     [rbp+270h+var_E8], rax
0x1800aeb87  test    edi, edi
0x1800aeb89  jnz     loc_1800AED58
0x1800aeb8f  mov     rdx, [rbx+140h]
0x1800aeb96  lea     r9d, [rdi+2]
0x1800aeb9a  lea     r8d, [rdi+1]
0x1800aeb9e  mov     ecx, r15d
0x1800aeba1  call    StoreOverridingDefaultSet
0x1800aeba6  mov     r8, [rbx+140h]
0x1800aebad  lea     rdx, FwCryptoSetMatchesSetId
0x1800aebb4  lea     rcx, [rax+0D8h]
0x1800aebbb  call    FwLookInRepoForFirstBlobContainerWithCriteria
0x1800aebc0  test    rax, rax
0x1800aebc3  jnz     short loc_1800AEC2F
0x1800aebc5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aebcc  lea     rdi, WPP_GLOBAL_Control
0x1800aebd3  cmp     rcx, rdi
0x1800aebd6  jz      short loc_1800AEC01
0x1800aebd8  test    [rcx+1Ch], r14b
0x1800aebdc  jz      short loc_1800AEC01
0x1800aebde  mov     r9, [rbx+10h]
0x1800aebe2  lea     edx, [rax+77h]
0x1800aebe5  mov     rax, [rbx+140h]
0x1800aebec  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800aebf3  mov     rcx, [rcx+10h]
0x1800aebf7  mov     [rsp+370h+var_350], rax
0x1800aebfc  call    WPP_SF_SS
0x1800aec01  mov     dword ptr [rbx+180h], 200003h
0x1800aec0b  xor     esi, esi
0x1800aec0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aec14  cmp     rcx, rdi
0x1800aec17  jz      loc_1800AED20
0x1800aec1d  test    byte ptr [rcx+1Ch], 1
0x1800aec21  jz      loc_1800AED20
0x1800aec27  lea     edx, [rsi+78h]
0x1800aec2a  jmp     loc_1800AED0D
0x1800aec2f  mov     r8, [rax]
0x1800aec32  xor     edx, edx
0x1800aec34  mov     r9, [rbp+270h+var_F8]
0x1800aec3b  lea     rax, [rsp+370h+var_340]
0x1800aec40  mov     rcx, rbx
0x1800aec43  mov     [rsp+370h+var_350], rax
0x1800aec48  mov     [rbp+270h+var_E0], r8
0x1800aec4f  mov     [rsp+370h+var_340], 10000h
0x1800aec57  call    IsAuthNoEncapRuleValid
0x1800aec5c  test    eax, eax
0x1800aec5e  jnz     loc_1800AED70
0x1800aec64  mov     esi, [rsp+370h+var_340]
0x1800aec68  lea     rdi, WPP_GLOBAL_Control
0x1800aec6f  mov     ecx, esi
0x1800aec71  sub     ecx, 200006h
0x1800aec77  jz      short loc_1800AECB1
0x1800aec79  cmp     ecx, 1
0x1800aec7c  jz      short loc_1800AEC91
0x1800aec7e  xor     r8d, r8d; __annotation("Debug", "TelemetryAssert", "FALSE", "unexpected rule status")
0x1800aec81  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800aec88  mov     edx, esi
0x1800aec8a  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800aec8f  jmp     short loc_1800AECE8
0x1800aec91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aec98  cmp     rcx, rdi
0x1800aec9b  jz      short loc_1800AECE8
0x1800aec9d  test    [rcx+1Ch], r14b
0x1800aeca1  jz      short loc_1800AECE8
0x1800aeca3  mov     rax, [rbx+138h]
0x1800aecaa  mov     edx, 7Ah ; 'z'
0x1800aecaf  jmp     short loc_1800AECCF
0x1800aecb1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aecb8  cmp     rcx, rdi
0x1800aecbb  jz      short loc_1800AECE8
0x1800aecbd  test    [rcx+1Ch], r14b
0x1800aecc1  jz      short loc_1800AECE8
0x1800aecc3  mov     rax, [rbx+140h]
0x1800aecca  mov     edx, 79h ; 'y'
0x1800aeccf  mov     r9, [rbx+10h]
0x1800aecd3  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800aecda  mov     rcx, [rcx+10h]
0x1800aecde  mov     [rsp+370h+var_350], rax
0x1800aece3  call    WPP_SF_SS
0x1800aece8  mov     [rbx+180h], esi
0x1800aecee  xor     esi, esi
0x1800aecf0  mov     [rsp+370h+var_340], 1
0x1800aecf8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aecff  cmp     rcx, rdi
0x1800aed02  jz      short loc_1800AED20
0x1800aed04  test    byte ptr [rcx+1Ch], 1
0x1800aed08  jz      short loc_1800AED20
0x1800aed0a  lea     edx, [rsi+7Bh]
0x1800aed0d  mov     rcx, [rcx+10h]
0x1800aed11  lea     r8, WPP_3c7e6a8ed2243f5f50ae31d23a3e4908_Traceguids
0x1800aed18  xor     r9d, r9d
0x1800aed1b  call    WPP_SF_d
0x1800aed20  mov     r9d, [rbx+180h]
0x1800aed27  mov     r8, [rbx+18h]
0x1800aed2b  mov     rdx, [rbx+10h]
0x1800aed2f  call    FwAuditLogRuntimeError
  ... truncated ...
```
