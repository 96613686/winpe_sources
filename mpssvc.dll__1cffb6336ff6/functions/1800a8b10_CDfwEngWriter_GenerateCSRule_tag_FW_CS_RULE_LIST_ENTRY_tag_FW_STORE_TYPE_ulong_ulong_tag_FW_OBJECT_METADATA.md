# CDfwEngWriter::GenerateCSRule(_tag_FW_CS_RULE *,_LIST_ENTRY *,_tag_FW_STORE_TYPE,ulong,ulong,_tag_FW_OBJECT_METADATA *)

- ea: `0x1800a8b10`
- end: `0x1800a9481`
- name: `?GenerateCSRule@CDfwEngWriter@@EEAAJPEAU_tag_FW_CS_RULE@@PEAU_LIST_ENTRY@@W4_tag_FW_STORE_TYPE@@KKPEAU_tag_FW_OBJECT_METADATA@@@Z`
- size: `2417`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800093b0`
- `0x18000af3c`
- `0x180017110`
- `0x18002a470`
- `0x180041e8c`
- `0x1800670c0`
- `0x18006950c`
- `0x18006f520`
- `0x18006ffc8`
- `0x18007b27c`
- `0x18008a668`
- `0x18008ab40`
- `0x18008c358`
- `0x1800a8b10`
- `0x1800a9748`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a9446`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a9458`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a9446`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a9458`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a90de`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a917c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a90de`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800a917c`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a911c`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a91ba`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a911c`
- `fwbase!FwMetaDataAddEnforcementState` at `0x1800a91ba`

## string_xrefs

- `0x1800a8fd1`: `mpssvc.dll`

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
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int64 v33; // rax
  __int64 *v34; // rax
  unsigned int v35; // esi
  __int64 v36; // rcx
  __int64 v37; // rax
  int v38; // edx
  const WCHAR *v39; // rcx
  const WCHAR *v40; // rcx
  int CSRule; // eax
  __int64 v42; // rcx
  __int64 v43; // rdx
  _OWORD *v44; // rax
  _OWORD *v45; // rcx
  __int64 v46; // rdx
  __int128 v47; // xmm1
  __int128 v48; // xmm0
  __int128 v49; // xmm1
  __int128 v50; // xmm0
  __int128 v51; // xmm1
  __int128 v52; // xmm0
  __int128 v53; // xmm1
  struct _LIST_ENTRY *v54; // r9
  _OWORD *v55; // rcx
  _OWORD *v56; // rax
  __int128 v57; // xmm1
  __int128 v58; // xmm0
  __int128 v59; // xmm1
  __int128 v60; // xmm0
  __int128 v61; // xmm1
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  struct _LIST_ENTRY *v64; // r9
  CDfwEngWriter *v65; // rcx
  unsigned int v67; // [rsp+30h] [rbp-D0h] BYREF
  struct _LIST_ENTRY *v68; // [rsp+38h] [rbp-C8h]
  CDfwEngWriter *v69; // [rsp+40h] [rbp-C0h]
  _BYTE v70[528]; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+260h] [rbp+160h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v73[8]; // [rsp+270h] [rbp+170h] BYREF
  __int64 v74; // [rsp+278h] [rbp+178h]
  __int64 v75; // [rsp+280h] [rbp+180h]
  __int64 v76; // [rsp+288h] [rbp+188h]
  __int64 v77; // [rsp+290h] [rbp+190h]
  int v78; // [rsp+2A0h] [rbp+1A0h]
  int v79; // [rsp+30Ch] [rbp+20Ch]
  int v80; // [rsp+31Ch] [rbp+21Ch]
  PSECURITY_DESCRIPTOR v81; // [rsp+320h] [rbp+220h]
  PSECURITY_DESCRIPTOR v82; // [rsp+328h] [rbp+228h]

  v7 = a3;
  v68 = a3;
  v9 = a1;
  v69 = a1;
  memset_0(v73, 0, 0xC0u);
  v11 = 4;
  SecurityDescriptor = 0;
  hMem = 0;
  v80 = -1;
  if ( *(_DWORD *)(a2 + 336) == 4 )
    goto LABEL_96;
  v12 = *(_QWORD *)(a2 + 312);
  v13 = 0;
  v67 = 0;
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
        (unsigned int)WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
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
  v74 = *BlobContainerWithCriteria;
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
          (unsigned int)WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
          *(_QWORD *)(a2 + 16),
          *(_QWORD *)(a2 + 328));
      *(_DWORD *)(a2 + 384) = 2097154;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_72;
      v17 = 112;
      goto LABEL_71;
    }
    v75 = *v20;
    if ( *(_DWORD *)(v75 + 48) )
    {
      for ( i = 0; i < *(_DWORD *)(v74 + 48); ++i )
      {
        if ( *(_DWORD *)(*(_QWORD *)(v74 + 56) + 24LL * i) == 3 )
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
                WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
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
    v75 = 0;
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
      v30 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 115, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
      MicrosoftTelemetryAssertTriggeredNoArgs(v30, v26, v28, v29);
      v13 = 0;
      v31 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v32 = 116;
LABEL_42:
        WPP_SF_d(*(_QWORD *)(v31 + 16), v32, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids, 0);
        goto LABEL_118;
      }
      goto LABEL_118;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_SS(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        117,
        (unsigned int)WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
        *(_QWORD *)(a2 + 16),
        *(_QWORD *)(a2 + 344));
    *(_DWORD *)(a2 + 384) = 2097157;
    v13 = 0;
    v16 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_72;
    v17 = 118;
LABEL_71:
    WPP_SF_d(*(_QWORD *)(v16 + 16), v17, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids, 0);
    goto LABEL_72;
  }
  v76 = *v25;
  if ( (a6 & 4) != 0 )
  {
    if ( *(_DWORD *)(a2 + 496) )
      MicrosoftTelemetryAssertTriggeredNoArgs(v27, v26, v28, v29);
    *(_DWORD *)(a2 + 496) = 7;
  }
  else
  {
    v33 = StoreOverridingDefaultSet(a4, *(_QWORD *)(a2 + 320), 1, 2);
    v34 = (__int64 *)FwLookInRepoForFirstBlobContainerWithCriteria(
                       v33 + 216,
                       FwCryptoSetMatchesSetId,
                       *(_QWORD *)(a2 + 320));
    if ( !v34 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_SS(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          119,
          (unsigned int)WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
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
    v77 = *v34;
    v67 = 0x10000;
    if ( !(unsigned int)IsAuthNoEncapRuleValid(a2, 0, v77, v74, (__int64)&v67) )
    {
      v35 = v67;
      if ( v67 == 2097158 )
      {
        v36 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          goto LABEL_68;
        v37 = *(_QWORD *)(a2 + 320);
        v38 = 121;
      }
      else
      {
        if ( v67 != 2097159 )
        {
          MicrosoftTelemetryAssertTriggeredArgs("mpssvc.dll", v67, 0);
          goto LABEL_68;
        }
        v36 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          goto LABEL_68;
        v37 = *(_QWORD *)(a2 + 312);
        v38 = 122;
      }
      WPP_SF_SS(
        *(_QWORD *)(v36 + 16),
        v38,
        (unsigned int)WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids,
        *(_QWORD *)(a2 + 16),
        v37);
LABEL_68:
      *(_DWORD *)(a2 + 384) = v35;
      v13 = 0;
      v67 = 1;
      v16 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_72:
        FwAuditLogRuntimeError(v16, *(_QWORD *)(a2 + 16), *(_QWORD *)(a2 + 24), *(unsigned int *)(a2 + 384));
        if ( v67 == 1 )
          FwEventCSRuleNotApplied(*(unsigned __int16 **)(a2 + 16), *(unsigned __int16 **)(a2 + 24));
        goto LABEL_118;
      }
      v17 = 123;
      goto LABEL_71;
    }
  }
  v39 = *(const WCHAR **)(a2 + 504);
  if ( !v39 )
  {
LABEL_86:
    v40 = *(const WCHAR **)(a2 + 512);
    if ( v40 )
    {
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v40, 1u, &hMem, 0) )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 126, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
        FwMetaDataAddEnforcementState(a7, 22);
        v13 = 0;
        *(_DWORD *)(a2 + 384) = 524309;
        v31 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          v32 = 127;
          goto LABEL_42;
        }
        goto LABEL_118;
      }
      v82 = hMem;
    }
    v7 = v68;
    v9 = v69;
LABEL_96:
    v78 = a5;
    if ( (a6 & 8) != 0 )
    {
      v79 = 12;
      CSRule = CDfwEngWriter::HelperGenerateCSRule(
                 v9,
                 (struct _tag_FW_CS_RULE *)a2,
                 (struct _FW_CS_RULE_INT_ *)v73,
                 v7,
                 a7,
                 0);
      v13 = CSRule;
      if ( CSRule >= 0 )
        goto LABEL_118;
      v42 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_116;
      v43 = 128;
    }
    else
    {
      v44 = (_OWORD *)a2;
      v45 = v70;
      v46 = 4;
      do
      {
        v47 = v44[1];
        *v45 = *v44;
        v48 = v44[2];
        v45[1] = v47;
        v49 = v44[3];
        v45[2] = v48;
        v50 = v44[4];
        v45[3] = v49;
        v51 = v44[5];
        v45[4] = v50;
        v52 = v44[6];
        v45[5] = v51;
        v53 = v44[7];
        v44 += 8;
        v45[6] = v52;
        v45[7] = v53;
        v45 += 8;
        --v46;
      }
      while ( v46 );
      v54 = v68;
      *(_QWORD *)v45 = *(_QWORD *)v44;
      v79 = (a6 & 4) != 0 ? 0xA : 0;
      CSRule = CDfwEngWriter::HelperGenerateCSRule(
                 v9,
                 (struct _tag_FW_CS_RULE *)a2,
                 (struct _FW_CS_RULE_INT_ *)v73,
                 v54,
                 a7,
                 0);
      v13 = CSRule;
      if ( CSRule >= 0 )
      {
        if ( (a6 & 2) == 0 )
          goto LABEL_118;
        if ( *(_DWORD *)(a2 + 40) == 0x7FFFFFFF )
          goto LABEL_118;
        v55 = (_OWORD *)a2;
        v56 = v70;
        do
        {
          v57 = v56[1];
          *v55 = *v56;
          v58 = v56[2];
          v55[1] = v57;
          v59 = v56[3];
          v55[2] = v58;
          v60 = v56[4];
          v55[3] = v59;
          v61 = v56[5];
          v55[4] = v60;
          v62 = v56[6];
          v55[5] = v61;
          v63 = v56[7];
          v56 += 8;
          v55[6] = v62;
          v55[7] = v63;
          v55 += 8;
          --v11;
        }
        while ( v11 );
        v64 = v68;
        *(_QWORD *)v55 = *(_QWORD *)v56;
        v65 = v69;
        *(_DWORD *)(a2 + 40) = 0x7FFFFFFF;
        v79 = (a6 & 4) != 0 ? 0xA : 0;
        CSRule = CDfwEngWriter::HelperGenerateCSRule(
                   v65,
                   (struct _tag_FW_CS_RULE *)a2,
                   (struct _FW_CS_RULE_INT_ *)v73,
                   v64,
                   a7,
                   1);
        v13 = CSRule;
        if ( CSRule >= 0 )
          goto LABEL_118;
        v42 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_116;
        v43 = 130;
      }
      else
      {
        v42 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        {
LABEL_116:
          if ( (*(_DWORD *)(a2 + 384) & 0x200000) != 0 )
            v13 = 0;
          goto LABEL_118;
        }
        v43 = 129;
      }
    }
    WPP_SF_d(*(_QWORD *)(v42 + 16), v43, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids, (unsigned int)CSRule);
    goto LABEL_116;
  }
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v39, 1u, &SecurityDescriptor, 0) )
  {
    v81 = SecurityDescriptor;
    goto LABEL_86;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 124, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids);
  FwMetaDataAddEnforcementState(a7, 21);
  v13 = 0;
  *(_DWORD *)(a2 + 384) = 524308;
  v31 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v32 = 125;
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
0x1800a8b10  push    rbp
0x1800a8b12  push    rbx
0x1800a8b13  push    rsi
0x1800a8b14  push    rdi
0x1800a8b15  push    r13
0x1800a8b17  push    r14
0x1800a8b19  push    r15
0x1800a8b1b  lea     rbp, [rsp-240h]
0x1800a8b23  sub     rsp, 340h
0x1800a8b2a  mov     rax, cs:__security_cookie
0x1800a8b31  xor     rax, rsp
0x1800a8b34  mov     [rbp+270h+var_40], rax
0x1800a8b3b  mov     r13, [rbp+270h+arg_30]
0x1800a8b42  mov     rdi, r8
0x1800a8b45  mov     [rsp+370h+var_338], r8
0x1800a8b4a  mov     rbx, rdx
0x1800a8b4d  mov     rsi, rcx
0x1800a8b50  mov     [rsp+370h+var_330], rcx
0x1800a8b55  xor     edx, edx; Val
0x1800a8b57  lea     rcx, [rbp+270h+var_100]; void *
0x1800a8b5e  mov     r8d, 0C0h; Size
0x1800a8b64  mov     r15d, r9d
0x1800a8b67  call    memset_0
0x1800a8b6c  mov     r14d, 4
0x1800a8b72  mov     [rbp+270h+SecurityDescriptor], 0
0x1800a8b7d  mov     [rbp+270h+hMem], 0
0x1800a8b88  mov     [rbp+270h+var_54], 0FFFFFFFFh
0x1800a8b92  cmp     [rbx+150h], r14d
0x1800a8b99  jz      loc_1800A9206
0x1800a8b9f  mov     rdx, [rbx+138h]
0x1800a8ba6  lea     r9d, [r14-3]
0x1800a8baa  xor     esi, esi
0x1800a8bac  xor     r8d, r8d
0x1800a8baf  mov     ecx, r15d
0x1800a8bb2  mov     [rsp+370h+var_340], esi
0x1800a8bb6  call    StoreOverridingDefaultSet
0x1800a8bbb  mov     r8, [rbx+138h]
0x1800a8bc2  lea     rdx, FwCryptoSetMatchesSetId
0x1800a8bc9  lea     rcx, [rax+78h]
0x1800a8bcd  call    FwLookInRepoForFirstBlobContainerWithCriteria
0x1800a8bd2  test    rax, rax
0x1800a8bd5  jnz     short loc_1800A8C41
0x1800a8bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8bde  lea     rdi, WPP_GLOBAL_Control
0x1800a8be5  cmp     rcx, rdi
0x1800a8be8  jz      short loc_1800A8C13
0x1800a8bea  test    [rcx+1Ch], r14b
0x1800a8bee  jz      short loc_1800A8C13
0x1800a8bf0  mov     rax, [rbx+138h]
0x1800a8bf7  lea     edx, [rsi+6Dh]
0x1800a8bfa  mov     r9, [rbx+10h]
0x1800a8bfe  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a8c05  mov     rcx, [rcx+10h]
0x1800a8c09  mov     [rsp+370h+var_350], rax
0x1800a8c0e  call    WPP_SF_SS
0x1800a8c13  mov     dword ptr [rbx+180h], 200001h
0x1800a8c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8c24  cmp     rcx, rdi
0x1800a8c27  jz      loc_1800A9070
0x1800a8c2d  test    byte ptr [rcx+1Ch], 1
0x1800a8c31  jz      loc_1800A9070
0x1800a8c37  mov     edx, 6Eh ; 'n'
0x1800a8c3c  jmp     loc_1800A905D
0x1800a8c41  mov     rdx, [rbx+148h]
0x1800a8c48  mov     rax, [rax]
0x1800a8c4b  mov     [rbp+270h+var_F8], rax
0x1800a8c52  test    rdx, rdx
0x1800a8c55  jz      loc_1800A8D93
0x1800a8c5b  mov     r9d, 2
0x1800a8c61  xor     r8d, r8d
0x1800a8c64  mov     ecx, r15d
0x1800a8c67  call    StoreOverridingDefaultSet
0x1800a8c6c  mov     r8, [rbx+148h]
0x1800a8c73  lea     rdx, FwCryptoSetMatchesSetId
0x1800a8c7a  lea     rcx, [rax+90h]
0x1800a8c81  call    FwLookInRepoForFirstBlobContainerWithCriteria
0x1800a8c86  test    rax, rax
0x1800a8c89  jnz     short loc_1800A8CF5
0x1800a8c8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8c92  lea     rdi, WPP_GLOBAL_Control
0x1800a8c99  cmp     rcx, rdi
0x1800a8c9c  jz      short loc_1800A8CC7
0x1800a8c9e  test    [rcx+1Ch], r14b
0x1800a8ca2  jz      short loc_1800A8CC7
0x1800a8ca4  mov     r9, [rbx+10h]
0x1800a8ca8  lea     edx, [rax+6Fh]
0x1800a8cab  mov     rax, [rbx+148h]
0x1800a8cb2  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a8cb9  mov     rcx, [rcx+10h]
0x1800a8cbd  mov     [rsp+370h+var_350], rax
0x1800a8cc2  call    WPP_SF_SS
0x1800a8cc7  mov     dword ptr [rbx+180h], 200002h
0x1800a8cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8cd8  cmp     rcx, rdi
0x1800a8cdb  jz      loc_1800A9070
0x1800a8ce1  test    byte ptr [rcx+1Ch], 1
0x1800a8ce5  jz      loc_1800A9070
0x1800a8ceb  mov     edx, 70h ; 'p'
0x1800a8cf0  jmp     loc_1800A905D
0x1800a8cf5  mov     rax, [rax]
0x1800a8cf8  mov     [rbp+270h+var_F0], rax
0x1800a8cff  cmp     [rax+30h], esi
0x1800a8d02  jbe     loc_1800A8D9A
0x1800a8d08  mov     rax, [rbp+270h+var_F8]
0x1800a8d0f  mov     edx, esi
0x1800a8d11  mov     r9, [rax+38h]
0x1800a8d15  mov     r8d, [rax+30h]
0x1800a8d19  cmp     edx, r8d
0x1800a8d1c  jnb     short loc_1800A8D9A
0x1800a8d1e  mov     eax, edx
0x1800a8d20  lea     rcx, [rax+rax*2]
0x1800a8d24  cmp     dword ptr [r9+rcx*8], 3
0x1800a8d29  jz      short loc_1800A8D2F
0x1800a8d2b  inc     edx
0x1800a8d2d  jmp     short loc_1800A8D19
0x1800a8d2f  mov     dword ptr [rbx+180h], 200004h
0x1800a8d39  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8d40  lea     rdi, WPP_GLOBAL_Control
0x1800a8d47  cmp     rcx, rdi
0x1800a8d4a  jz      loc_1800A9070
0x1800a8d50  test    [rcx+1Ch], r14b
0x1800a8d54  jz      short loc_1800A8D76
0x1800a8d56  mov     r9, [rbx+10h]
0x1800a8d5a  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a8d61  mov     rcx, [rcx+10h]
0x1800a8d65  mov     edx, 71h ; 'q'
0x1800a8d6a  call    WPP_SF_S
0x1800a8d6f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8d76  cmp     rcx, rdi
0x1800a8d79  jz      loc_1800A9070
0x1800a8d7f  test    byte ptr [rcx+1Ch], 1
0x1800a8d83  jz      loc_1800A9070
0x1800a8d89  mov     edx, 72h ; 'r'
0x1800a8d8e  jmp     loc_1800A905D
0x1800a8d93  mov     [rbp+270h+var_F0], rsi
0x1800a8d9a  mov     edi, dword ptr [rbp+270h+arg_28]
0x1800a8da0  lea     rsi, aE5a5d32a4bce4e_1; "{E5A5D32A-4BCE-4e4d-B07F-4AB1BA7E5FE1}"
0x1800a8da7  and     edi, r14d
0x1800a8daa  jz      short loc_1800A8DB5
0x1800a8dac  mov     rdx, [rbx+158h]
0x1800a8db3  jmp     short loc_1800A8DB8
0x1800a8db5  mov     rdx, rsi
0x1800a8db8  mov     eax, 1
0x1800a8dbd  mov     ecx, r15d
0x1800a8dc0  mov     r9d, eax
0x1800a8dc3  mov     r8d, eax
0x1800a8dc6  call    StoreOverridingDefaultSet
0x1800a8dcb  test    edi, edi
0x1800a8dcd  jz      short loc_1800A8DD6
0x1800a8dcf  mov     rsi, [rbx+158h]
0x1800a8dd6  lea     rcx, [rax+0C0h]
0x1800a8ddd  mov     r8, rsi
0x1800a8de0  lea     rdx, FwCryptoSetMatchesSetId
0x1800a8de7  call    FwLookInRepoForFirstBlobContainerWithCriteria
0x1800a8dec  test    rax, rax
0x1800a8def  jnz     loc_1800A8ECD
0x1800a8df5  test    edi, edi
0x1800a8df7  jnz     short loc_1800A8E61
0x1800a8df9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8e00  lea     rdi, WPP_GLOBAL_Control
0x1800a8e07  cmp     rcx, rdi
0x1800a8e0a  jz      short loc_1800A8E25
0x1800a8e0c  test    byte ptr [rcx+1Ch], 1
0x1800a8e10  jz      short loc_1800A8E25
0x1800a8e12  mov     rcx, [rcx+10h]
0x1800a8e16  lea     edx, [rax+73h]
0x1800a8e19  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a8e20  call    WPP_SF_
0x1800a8e25  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a8e2a  xor     esi, esi
0x1800a8e2c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8e33  cmp     rcx, rdi
0x1800a8e36  jz      loc_1800A943A
0x1800a8e3c  test    byte ptr [rcx+1Ch], 1
0x1800a8e40  jz      loc_1800A943A
0x1800a8e46  lea     edx, [rsi+74h]
0x1800a8e49  mov     rcx, [rcx+10h]
0x1800a8e4d  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a8e54  xor     r9d, r9d
0x1800a8e57  call    WPP_SF_d
0x1800a8e5c  jmp     loc_1800A943A
0x1800a8e61  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8e68  lea     rdi, WPP_GLOBAL_Control
0x1800a8e6f  cmp     rcx, rdi
0x1800a8e72  jz      short loc_1800A8E9F
0x1800a8e74  test    [rcx+1Ch], r14b
0x1800a8e78  jz      short loc_1800A8E9F
0x1800a8e7a  mov     rax, [rbx+158h]
0x1800a8e81  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a8e88  mov     r9, [rbx+10h]
0x1800a8e8c  mov     edx, 75h ; 'u'
0x1800a8e91  mov     rcx, [rcx+10h]
0x1800a8e95  mov     [rsp+370h+var_350], rax
0x1800a8e9a  call    WPP_SF_SS
0x1800a8e9f  mov     dword ptr [rbx+180h], 200005h
0x1800a8ea9  xor     esi, esi
0x1800a8eab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8eb2  cmp     rcx, rdi
0x1800a8eb5  jz      loc_1800A9070
0x1800a8ebb  test    byte ptr [rcx+1Ch], 1
0x1800a8ebf  jz      loc_1800A9070
0x1800a8ec5  lea     edx, [rsi+76h]
0x1800a8ec8  jmp     loc_1800A905D
0x1800a8ecd  mov     rax, [rax]
0x1800a8ed0  mov     [rbp+270h+var_E8], rax
0x1800a8ed7  test    edi, edi
0x1800a8ed9  jnz     loc_1800A90A8
0x1800a8edf  mov     rdx, [rbx+140h]
0x1800a8ee6  lea     r9d, [rdi+2]
0x1800a8eea  lea     r8d, [rdi+1]
0x1800a8eee  mov     ecx, r15d
0x1800a8ef1  call    StoreOverridingDefaultSet
0x1800a8ef6  mov     r8, [rbx+140h]
0x1800a8efd  lea     rdx, FwCryptoSetMatchesSetId
0x1800a8f04  lea     rcx, [rax+0D8h]
0x1800a8f0b  call    FwLookInRepoForFirstBlobContainerWithCriteria
0x1800a8f10  test    rax, rax
0x1800a8f13  jnz     short loc_1800A8F7F
0x1800a8f15  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8f1c  lea     rdi, WPP_GLOBAL_Control
0x1800a8f23  cmp     rcx, rdi
0x1800a8f26  jz      short loc_1800A8F51
0x1800a8f28  test    [rcx+1Ch], r14b
0x1800a8f2c  jz      short loc_1800A8F51
0x1800a8f2e  mov     r9, [rbx+10h]
0x1800a8f32  lea     edx, [rax+77h]
0x1800a8f35  mov     rax, [rbx+140h]
0x1800a8f3c  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a8f43  mov     rcx, [rcx+10h]
0x1800a8f47  mov     [rsp+370h+var_350], rax
0x1800a8f4c  call    WPP_SF_SS
0x1800a8f51  mov     dword ptr [rbx+180h], 200003h
0x1800a8f5b  xor     esi, esi
0x1800a8f5d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8f64  cmp     rcx, rdi
0x1800a8f67  jz      loc_1800A9070
0x1800a8f6d  test    byte ptr [rcx+1Ch], 1
0x1800a8f71  jz      loc_1800A9070
0x1800a8f77  lea     edx, [rsi+78h]
0x1800a8f7a  jmp     loc_1800A905D
0x1800a8f7f  mov     r8, [rax]
0x1800a8f82  xor     edx, edx
0x1800a8f84  mov     r9, [rbp+270h+var_F8]
0x1800a8f8b  lea     rax, [rsp+370h+var_340]
0x1800a8f90  mov     rcx, rbx
0x1800a8f93  mov     [rsp+370h+var_350], rax
0x1800a8f98  mov     [rbp+270h+var_E0], r8
0x1800a8f9f  mov     [rsp+370h+var_340], 10000h
0x1800a8fa7  call    IsAuthNoEncapRuleValid
0x1800a8fac  test    eax, eax
0x1800a8fae  jnz     loc_1800A90C0
0x1800a8fb4  mov     esi, [rsp+370h+var_340]
0x1800a8fb8  lea     rdi, WPP_GLOBAL_Control
0x1800a8fbf  mov     ecx, esi
0x1800a8fc1  sub     ecx, 200006h
0x1800a8fc7  jz      short loc_1800A9001
0x1800a8fc9  cmp     ecx, 1
0x1800a8fcc  jz      short loc_1800A8FE1
0x1800a8fce  xor     r8d, r8d
0x1800a8fd1  lea     rcx, aMpssvcDll_1; "mpssvc.dll"
0x1800a8fd8  mov     edx, esi
0x1800a8fda  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800a8fdf  jmp     short loc_1800A9038
0x1800a8fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8fe8  cmp     rcx, rdi
0x1800a8feb  jz      short loc_1800A9038
0x1800a8fed  test    [rcx+1Ch], r14b
0x1800a8ff1  jz      short loc_1800A9038
0x1800a8ff3  mov     rax, [rbx+138h]
0x1800a8ffa  mov     edx, 7Ah ; 'z'
0x1800a8fff  jmp     short loc_1800A901F
0x1800a9001  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a9008  cmp     rcx, rdi
0x1800a900b  jz      short loc_1800A9038
0x1800a900d  test    [rcx+1Ch], r14b
0x1800a9011  jz      short loc_1800A9038
0x1800a9013  mov     rax, [rbx+140h]
0x1800a901a  mov     edx, 79h ; 'y'
0x1800a901f  mov     r9, [rbx+10h]
0x1800a9023  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a902a  mov     rcx, [rcx+10h]
0x1800a902e  mov     [rsp+370h+var_350], rax
0x1800a9033  call    WPP_SF_SS
0x1800a9038  mov     [rbx+180h], esi
0x1800a903e  xor     esi, esi
0x1800a9040  mov     [rsp+370h+var_340], 1
0x1800a9048  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a904f  cmp     rcx, rdi
0x1800a9052  jz      short loc_1800A9070
0x1800a9054  test    byte ptr [rcx+1Ch], 1
0x1800a9058  jz      short loc_1800A9070
0x1800a905a  lea     edx, [rsi+7Bh]
0x1800a905d  mov     rcx, [rcx+10h]
0x1800a9061  lea     r8, WPP_07cc8a6c1dbd37da1f31f2b2c9bd7adb_Traceguids
0x1800a9068  xor     r9d, r9d
0x1800a906b  call    WPP_SF_d
0x1800a9070  mov     r9d, [rbx+180h]
0x1800a9077  mov     r8, [rbx+18h]
0x1800a907b  mov     rdx, [rbx+10h]
0x1800a907f  call    FwAuditLogRuntimeError
  ... truncated ...
```
