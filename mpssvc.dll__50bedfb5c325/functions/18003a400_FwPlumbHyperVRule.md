# FwPlumbHyperVRule

- ea: `0x18003a400`
- end: `0x18003b0ee`
- name: `FwPlumbHyperVRule`
- size: `3310`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x1800111f8`
- `0x1800b12d0`

## callees

- `0x18000a710`
- `0x18000b030`
- `0x18003a400`
- `0x18003b0f4`
- `0x18003b134`
- `0x18003b228`
- `0x18003b318`
- `0x18003b350`
- `0x18003c508`
- `0x18003c6c4`
- `0x18006fadc`
- `0x1800729c0`
- `0x180073488`
- `0x1800b158c`

## import_xrefs

- `fwbase!FwAlloc` at `0x18003aacf`
- `fwbase!FwAlloc` at `0x18003abbd`
- `fwbase!FwAlloc` at `0x18003aacf`
- `fwbase!FwAlloc` at `0x18003abbd`
- `fwbase!FwFree` at `0x18003a946`
- `fwbase!FwFree` at `0x18003a955`
- `fwbase!FwFree` at `0x18003a965`
- `fwbase!FwFree` at `0x18003a975`
- `fwbase!FwFree` at `0x18003a985`
- `fwbase!FwFree` at `0x18003a995`
- `fwbase!FwFree` at `0x18003a9c8`
- `fwbase!FwFree` at `0x18003a946`
- `fwbase!FwFree` at `0x18003a955`
- `fwbase!FwFree` at `0x18003a965`
- `fwbase!FwFree` at `0x18003a975`
- `fwbase!FwFree` at `0x18003a985`
- `fwbase!FwFree` at `0x18003a995`
- `fwbase!FwFree` at `0x18003a9c8`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003a9a5`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003a9b8`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003a9a5`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003a9b8`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18003a58a`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18003a5ae`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18003a58a`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x18003a5ae`

## pseudocode

```c
__int64 __fastcall FwPlumbHyperVRule(__int64 a1, unsigned int a2, __int64 a3, _DWORD *a4)
{
  __int64 v6; // rbx
  char v7; // di
  _DWORD *v8; // r13
  __int64 v9; // r12
  int ModifiedRuleId; // eax
  signed int StringParameterSize; // esi
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // rcx
  bool v15; // sf
  int v16; // eax
  int v17; // eax
  _WORD *v18; // rbx
  __int64 v19; // rax
  unsigned int v20; // r13d
  int v21; // ecx
  __int64 v22; // rdx
  _BYTE *v23; // r9
  unsigned int v24; // r11d
  int v25; // r10d
  int v26; // edi
  int v27; // eax
  int v28; // ecx
  int v29; // eax
  __int64 v30; // r8
  unsigned int v31; // edi
  __int64 v32; // rbx
  int v33; // ecx
  int VfpLayerIdFromStoreType; // eax
  __int64 v35; // r9
  int v36; // eax
  char v37; // cl
  unsigned int v38; // r12d
  __int64 v39; // rdx
  __int64 v40; // rax
  _QWORD *v41; // r11
  _WORD *v42; // r8
  _WORD *v43; // r10
  _QWORD *v44; // rdi
  unsigned int v45; // eax
  size_t v46; // rbx
  _WORD *v47; // rdi
  size_t i; // rcx
  __int64 v49; // rcx
  __int64 v50; // rdx
  int v51; // r8d
  int v53; // r8d
  __int64 v54; // rcx
  int v55; // esi
  __int16 v56; // di
  __int64 v57; // rax
  _WORD *v58; // r8
  unsigned int v59; // r9d
  __int64 v60; // rdx
  __int64 v61; // r13
  int v62; // esi
  __int16 v63; // di
  __int64 v64; // rdx
  _OWORD *v65; // r8
  unsigned int v66; // r9d
  __int64 v67; // rcx
  int v68; // eax
  __int64 v69; // rdx
  __int64 v70; // r9
  __int64 v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // r9
  int v74; // eax
  __int64 v75; // rcx
  __int64 v76; // r9
  char v78; // [rsp+48h] [rbp-B8h]
  _WORD *v79; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v80; // [rsp+58h] [rbp-A8h]
  unsigned int v81; // [rsp+5Ch] [rbp-A4h]
  int v82; // [rsp+60h] [rbp-A0h]
  __int64 v83; // [rsp+68h] [rbp-98h]
  _DWORD *v84; // [rsp+70h] [rbp-90h]
  unsigned int v85; // [rsp+78h] [rbp-88h]
  __int64 v86; // [rsp+80h] [rbp-80h] BYREF
  __int64 v87; // [rsp+88h] [rbp-78h] BYREF
  __int64 v88; // [rsp+90h] [rbp-70h] BYREF
  __int64 v89; // [rsp+98h] [rbp-68h] BYREF
  __int64 v90; // [rsp+A0h] [rbp-60h]
  __int64 v91; // [rsp+A8h] [rbp-58h] BYREF
  void *v92; // [rsp+B0h] [rbp-50h]
  int v93; // [rsp+B8h] [rbp-48h]
  __int16 v94; // [rsp+C0h] [rbp-40h] BYREF
  char v95; // [rsp+C2h] [rbp-3Eh] BYREF
  char v96; // [rsp+C3h] [rbp-3Dh]
  __int16 v97; // [rsp+C4h] [rbp-3Ch]
  char v98[2]; // [rsp+C6h] [rbp-3Ah] BYREF
  char v99[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int16 v100; // [rsp+CCh] [rbp-34h]
  __int64 v101; // [rsp+D8h] [rbp-28h]
  __int64 v102; // [rsp+E0h] [rbp-20h]
  _QWORD v103[5]; // [rsp+F0h] [rbp-10h] BYREF
  _WORD v104[5]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v105[62]; // [rsp+122h] [rbp+22h] BYREF
  int v106; // [rsp+160h] [rbp+60h] BYREF
  int v107; // [rsp+164h] [rbp+64h]
  int v108; // [rsp+178h] [rbp+78h] BYREF
  __int64 v109; // [rsp+198h] [rbp+98h]
  __int64 v110; // [rsp+1A0h] [rbp+A0h]
  int v111; // [rsp+1B0h] [rbp+B0h] BYREF
  int v112; // [rsp+1B4h] [rbp+B4h]
  int v113; // [rsp+1C8h] [rbp+C8h] BYREF
  __int64 v114; // [rsp+1E8h] [rbp+E8h] BYREF

  v85 = a2;
  v6 = a1;
  v84 = a4;
  v94 = 0;
  v7 = 0;
  v8 = a4;
  memset_0(&v95, 0, 0x96u);
  v86 = 0;
  memset_0(&v106, 0, 0x48u);
  memset_0(&v111, 0, 0x48u);
  v93 = 0;
  v9 = 0;
  LODWORD(v79) = 0;
  v87 = 0;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  v91 = 0;
  if ( !a3 || !v6 )
  {
    StringParameterSize = -2147024809;
    v49 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_73;
    v50 = 18;
    goto LABEL_136;
  }
  *v8 = 0;
  ModifiedRuleId = FwGetModifiedRuleId(*(_QWORD *)(a3 + 16), a2, &v86);
  StringParameterSize = ModifiedRuleId;
  if ( ModifiedRuleId < 0 )
  {
    v49 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_73;
    v50 = 19;
    goto LABEL_121;
  }
  v12 = *(_QWORD *)(a3 + 24);
  v13 = v86;
  memset_0(&v94, 0, 0x98u);
  v94 = 152;
  v95 = 5;
  v101 = v13;
  StringParameterSize = VfcGetStringParameterSize(v13, v98);
  if ( !StringParameterSize )
  {
    v102 = v12;
    StringParameterSize = VfcGetStringParameterSize(v12, v99);
    if ( !StringParameterSize )
    {
      v14 = WPP_GLOBAL_Control;
      v97 = 8195;
      v7 = 0;
      v78 = 0;
      StringParameterSize = 0;
      goto LABEL_97;
    }
  }
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      19,
      WPP_3826686ba0cf358109adbef3a51266ac_Traceguids,
      (unsigned int)StringParameterSize);
    v14 = WPP_GLOBAL_Control;
  }
  v78 = StringParameterSize;
  v7 = StringParameterSize;
  v15 = StringParameterSize < 0;
  if ( StringParameterSize > 0 )
  {
    StringParameterSize = (unsigned __int16)StringParameterSize | 0x80070000;
LABEL_97:
    v15 = StringParameterSize < 0;
  }
  if ( v15 )
  {
    if ( (_UNKNOWN *)v14 == &WPP_GLOBAL_Control || (*(_BYTE *)(v14 + 28) & 1) == 0 )
      goto LABEL_72;
    v69 = 20;
    v70 = (unsigned int)StringParameterSize;
    goto LABEL_126;
  }
  v16 = FwPolioCopyWFAddressesContents(a3 + 64, &v106);
  StringParameterSize = v16;
  if ( v16 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_72;
    v69 = 21;
LABEL_125:
    v70 = (unsigned int)v16;
LABEL_126:
    WPP_SF_d(*(_QWORD *)(v14 + 16), v69, WPP_3ac025dd596b34dc773177d03687c214_Traceguids, v70);
LABEL_72:
    v6 = a1;
    goto LABEL_73;
  }
  v16 = FwPolioCopyWFAddressesContents(a3 + 160, &v111);
  StringParameterSize = v16;
  if ( v16 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_72;
    v69 = 22;
    goto LABEL_125;
  }
  v6 = a1;
  StringParameterSize = ResolveAddresses((struct _tag_FW_ADDRESSES *)&v106, 0, 0, 0);
  if ( StringParameterSize < 0 )
  {
    v49 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_73;
    v50 = 23;
LABEL_136:
    v73 = (unsigned int)StringParameterSize;
    goto LABEL_123;
  }
  if ( v93 )
  {
    StringParameterSize = 0;
    v49 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_73;
    v50 = 24;
    goto LABEL_122;
  }
  ModifiedRuleId = ResolveAddresses((struct _tag_FW_ADDRESSES *)&v111, 0, 0, 0);
  StringParameterSize = ModifiedRuleId;
  if ( ModifiedRuleId < 0 )
  {
    v49 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_73;
    v50 = 25;
LABEL_121:
    v73 = (unsigned int)ModifiedRuleId;
LABEL_123:
    WPP_SF_d(*(_QWORD *)(v49 + 16), v50, WPP_3ac025dd596b34dc773177d03687c214_Traceguids, v73);
    goto LABEL_73;
  }
  if ( v93 )
  {
    StringParameterSize = 0;
    v49 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_73;
    v50 = 26;
LABEL_122:
    v73 = 0;
    goto LABEL_123;
  }
  if ( (*(_BYTE *)(a3 + 260) & 4) != 0 )
  {
    v100 = 0;
  }
  else if ( *(_WORD *)(a3 + 32) )
  {
    v100 = *(_WORD *)(a3 + 32);
  }
  else
  {
    v74 = *(_DWORD *)(a3 + 256);
    if ( v74 == 3 )
    {
      v100 = 2;
    }
    else if ( v74 == 2 )
    {
      v100 = 1;
    }
  }
  v17 = *(_DWORD *)(a3 + 256);
  if ( v17 == 3 )
  {
    v96 = 1;
  }
  else if ( v17 == 2 )
  {
    v96 = 2;
  }
  v18 = (_WORD *)(a3 + 56);
  if ( *(_WORD *)(a3 + 56) != 256 )
  {
    v105[0] = 1;
    v104[0] = 1;
    v103[0] = a3 + 56;
    LODWORD(v79) = 1;
  }
  v16 = FwSetVfpRuleDescriptorPortCondition(
          (int)a3 + 144,
          (unsigned int)(*(_DWORD *)(a3 + 36) != 2) + 6,
          (unsigned int)&v94,
          (unsigned int)&v79,
          (__int64)&v87);
  StringParameterSize = v16;
  if ( v16 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_72;
    v69 = 27;
    goto LABEL_125;
  }
  v19 = *(unsigned int *)(a3 + 240);
  if ( !(_DWORD)v19 )
  {
    v20 = (unsigned int)v79;
    v21 = 1;
    v83 = 0;
    goto LABEL_26;
  }
  v55 = *(_DWORD *)(a3 + 36);
  v56 = 4 * v19;
  v57 = FwAlloc(4 * v19);
  v83 = v57;
  if ( !v57 )
  {
    v75 = WPP_GLOBAL_Control;
    StringParameterSize = -2147024882;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          15,
          WPP_3ac025dd596b34dc773177d03687c214_Traceguids,
          2147942414LL);
        v75 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v75 != &WPP_GLOBAL_Control && (*(_BYTE *)(v75 + 28) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(v75 + 16), 28, WPP_3ac025dd596b34dc773177d03687c214_Traceguids, 2147942414LL);
    }
    v7 = v78;
    goto LABEL_72;
  }
  v58 = (_WORD *)v57;
  v59 = 0;
  if ( *(_DWORD *)(a3 + 240) )
  {
    do
    {
      v60 = v59++;
      *v58 = *(_WORD *)(*(_QWORD *)(a3 + 248) + 4 * v60);
      v58 += 2;
      *(v58 - 1) = *(_WORD *)(*(_QWORD *)(a3 + 248) + 4 * v60 + 2);
    }
    while ( v59 < *(_DWORD *)(a3 + 240) );
    v18 = (_WORD *)(a3 + 56);
  }
  v61 = (unsigned int)v79;
  v21 = 1;
  v105[(unsigned int)v79] = (v55 == 2) + 6;
  v104[v61] = v56;
  v103[v61] = v57;
  v20 = v61 + 1;
  LODWORD(v79) = v20;
LABEL_26:
  v22 = 0;
  v23 = (_BYTE *)*(unsigned int *)(a3 + 36);
  StringParameterSize = 0;
  v24 = v109;
  v81 = 0;
  if ( v108 || v106 )
  {
    v25 = 1;
  }
  else
  {
    if ( !(_DWORD)v109 && !v107 )
    {
      v25 = 1;
LABEL_31:
      v26 = 1;
      goto LABEL_32;
    }
    v25 = 0;
  }
  if ( (_DWORD)v109 )
    goto LABEL_31;
  v26 = 0;
  if ( v107 )
    goto LABEL_31;
LABEL_32:
  if ( !v113 && !v111 )
  {
    if ( !(_DWORD)v114 && !v112 )
      goto LABEL_34;
    v21 = 0;
  }
  if ( (_DWORD)v114 || (v27 = 0, v112) )
LABEL_34:
    v27 = 1;
  v28 = v25 & v21;
  if ( *v18 == 1 )
  {
    v29 = 0;
  }
  else
  {
    v29 = v26 & v27;
    if ( *v18 == 58 )
      goto LABEL_38;
  }
  if ( v28 != 1 )
  {
LABEL_38:
    v30 = 2;
    goto LABEL_39;
  }
  v30 = 2;
  if ( (_DWORD)v23 == 1 )
  {
    v22 = 1;
  }
  else if ( (_DWORD)v23 == 2 )
  {
    v22 = 2;
  }
  v81 = v22;
LABEL_39:
  if ( v29 == 1 )
  {
    if ( (_DWORD)v23 == 1 )
    {
      v22 = (unsigned int)v22 | 4;
    }
    else
    {
      if ( (_DWORD)v23 != 2 )
        goto LABEL_40;
      v22 = (unsigned int)v22 | 8;
    }
    v81 = v22;
  }
LABEL_40:
  v31 = v20;
  v80 = v20;
  while ( 1 )
  {
    v82 = v9;
    if ( (unsigned int)v9 >= 4 )
    {
      v8 = v84;
      v7 = v78;
      v9 = v83;
      *v84 = v22;
      goto LABEL_72;
    }
    v32 = 4LL * (int)v9;
    v33 = gFwInboxVfpGroupInfo[v32];
    if ( ((unsigned int)v22 & v33) == v33 )
      break;
LABEL_66:
    LODWORD(v9) = v9 + 1;
    v30 = 2;
  }
  if ( (unsigned int)(v33 - 1) <= 1 )
  {
    v68 = FwSetVfpRuleDescriptorIPV4AddressCondition(
            (unsigned int)&v108,
            (unsigned int)(*(_DWORD *)(a3 + 36) != 2) + 10,
            (unsigned int)&v94,
            (unsigned int)&v79,
            (__int64)&v88);
    StringParameterSize = v68;
    if ( v68 < 0 )
    {
      v71 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_186;
      v72 = 29;
    }
    else
    {
      v68 = FwSetVfpRuleDescriptorIPV4AddressCondition(
              (unsigned int)&v113,
              11 - (unsigned int)(*(_DWORD *)(a3 + 36) != 2),
              (unsigned int)&v94,
              (unsigned int)&v79,
              (__int64)&v89);
      StringParameterSize = v68;
      if ( v68 >= 0 )
        goto LABEL_110;
      v71 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      {
LABEL_186:
        v6 = a1;
        goto LABEL_187;
      }
      v72 = 30;
    }
    goto LABEL_182;
  }
  if ( ((v33 - 4) & 0xFFFFFFFB) != 0 )
    goto LABEL_45;
  if ( v24 )
  {
    v62 = *(_DWORD *)(a3 + 36);
    v63 = 32 * v24;
    v64 = FwAlloc(32LL * v24);
    if ( !v64 )
    {
      v71 = WPP_GLOBAL_Control;
      StringParameterSize = -2147024882;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_186;
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          17,
          WPP_3ac025dd596b34dc773177d03687c214_Traceguids,
          2147942414LL);
        v71 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v71 == &WPP_GLOBAL_Control || (*(_BYTE *)(v71 + 28) & 1) == 0 )
        goto LABEL_186;
      v72 = 31;
      v76 = 2147942414LL;
LABEL_183:
      WPP_SF_d(*(_QWORD *)(v71 + 16), v72, WPP_3ac025dd596b34dc773177d03687c214_Traceguids, v76);
      v7 = v78;
      v9 = v83;
      v8 = v84;
      goto LABEL_72;
    }
    v65 = (_OWORD *)v64;
    v66 = 0;
    if ( (_DWORD)v109 )
    {
      do
      {
        v67 = v66++;
        v67 *= 32;
        *v65 = *(_OWORD *)(v67 + v110);
        v65 += 2;
        *(v65 - 1) = *(_OWORD *)(v67 + v110 + 16);
      }
      while ( v66 < (unsigned int)v109 );
      LODWORD(v9) = v82;
    }
    v90 = v64;
    v105[v20] = (v62 != 2) + 12;
    v104[v20] = v63;
    v31 = v80;
    v103[v20] = v64;
    LODWORD(v79) = v20 + 1;
  }
  v68 = FwSetVfpRuleDescriptorIPV6AddressCondition(
          (unsigned int)&v114,
          13 - (unsigned int)(*(_DWORD *)(a3 + 36) != 2),
          (unsigned int)&v94,
          (unsigned int)&v79,
          (__int64)&v91);
  StringParameterSize = v68;
  if ( v68 < 0 )
  {
    v71 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_186;
    v72 = 32;
LABEL_182:
    v76 = (unsigned int)v68;
    goto LABEL_183;
  }
LABEL_110:
  v20 = (unsigned int)v79;
LABEL_45:
  VfpLayerIdFromStoreType = FwGetVfpLayerIdFromStoreType(v85, v22, v30, v23);
  v35 = gFwInboxVfpGroupInfo[v32 + 1];
  v6 = a1;
  v36 = FwVfpAddRule(*(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), VfpLayerIdFromStoreType, v35, (__int64)&v94);
  v78 = v36;
  if ( v36 > 0 )
    StringParameterSize = (unsigned __int16)v36 | 0x80070000;
  else
    StringParameterSize = v36;
  if ( StringParameterSize >= 0 )
  {
    if ( v31 < v20 )
    {
      v37 = v20 - v31;
      v38 = v31;
      if ( v20 - v31 >= 2 )
      {
        v39 = v31;
        v40 = v20 - 1;
        v41 = &v103[v31];
        v42 = &v104[v40];
        v92 = v41;
        v43 = &v104[v31];
        v79 = v43;
        v44 = &v103[v40];
        if ( v41 > (_QWORD *)v42 || v44 < (_QWORD *)v43 )
        {
          v23 = &v105[v39];
          if ( (v41 > (_QWORD *)&v105[v40] || v44 < (_QWORD *)v23) && (v43 > (_WORD *)&v105[v40] || v42 < (_WORD *)v23) )
          {
            v45 = v20 - (v37 & 1);
            do
              v38 += 2;
            while ( v38 < v45 );
            v46 = (v45 - v80 + 1) & 0xFFFFFFFE;
            memset_0(v23, 0, v46);
            v47 = v79;
            for ( i = v46; i; --i )
              *v47++ = 0;
            memset_0(v92, 0, 8 * v46);
          }
        }
        v31 = v80;
      }
      while ( v38 < v20 )
      {
        v54 = v38++;
        v105[v54] = 0;
        v104[v54] = 0;
        v103[v54] = 0;
      }
      LODWORD(v9) = v82;
    }
    v24 = v109;
    v20 = v31;
    v22 = v81;
    LODWORD(v79) = v31;
    goto LABEL_66;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      33,
      WPP_3ac025dd596b34dc773177d03687c214_Traceguids,
      (unsigned int)StringParameterSize);
LABEL_187:
  v7 = v78;
  v9 = v83;
  v8 = v84;
LABEL_73:
  FwFree(v87);
  FwFree(v9);
  FwFree(v88);
  FwFree(v89);
  FwFree(v90);
  FwFree(v91);
  FwPolioEmptyWFAddresses(&v106);
  FwPolioEmptyWFAddresses(&v111);
  FwFree(v86);
  if ( StringParameterSize < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_SSSd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        34,
        v51,
        *(_QWORD *)(v6 + 16),
        *(_QWORD *)(v6 + 8),
        *(_QWORD *)(a3 + 16),
        v7);
    if ( (unsigned int)FwWriterDeleteHyperVRule(v6, v85, *(_QWORD *)(a3 + 16), v8)
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_SSSd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        35,
        v53,
        *(_QWORD *)(v6 + 16),
        *(_QWORD *)(v6 + 8),
        *(_QWORD *)(a3 + 16),
        v7);
    }
  }
  return (unsigned int)StringParameterSize;
}

```

## disassembly

```asm
0x18003a400  push    rbp
0x18003a402  push    rbx
0x18003a403  push    rsi
0x18003a404  push    rdi
0x18003a405  push    r12
0x18003a407  push    r13
0x18003a409  push    r14
0x18003a40b  push    r15
0x18003a40d  lea     rbp, [rsp-118h]
0x18003a415  sub     rsp, 218h
0x18003a41c  mov     rax, cs:__security_cookie
0x18003a423  xor     rax, rsp
0x18003a426  mov     [rbp+150h+var_50], rax
0x18003a42d  mov     r15, r8
0x18003a430  mov     [rsp+250h+var_1D8], edx
0x18003a434  mov     esi, edx
0x18003a436  mov     [rsp+250h+var_210], rcx
0x18003a43b  mov     rbx, rcx
0x18003a43e  mov     [rsp+250h+var_1E0], r9
0x18003a443  xor     r14d, r14d
0x18003a446  lea     rcx, [rbp+150h+var_18E]; void *
0x18003a44a  xor     edx, edx; Val
0x18003a44c  mov     [rbp+150h+var_190], r14w
0x18003a451  mov     r8d, 96h; Size
0x18003a457  mov     edi, r14d
0x18003a45a  mov     r13, r9
0x18003a45d  call    memset_0
0x18003a462  mov     [rbp+150h+var_1D0], r14
0x18003a466  lea     rcx, [rbp+150h+var_F0]; void *
0x18003a46a  mov     r14d, 48h ; 'H'
0x18003a470  xor     edx, edx; Val
0x18003a472  mov     r8d, r14d; Size
0x18003a475  call    memset_0
0x18003a47a  mov     r8d, r14d; Size
0x18003a47d  lea     rcx, [rbp+150h+var_A0]; void *
0x18003a484  xor     edx, edx; Val
0x18003a486  call    memset_0
0x18003a48b  xor     r14d, r14d
0x18003a48e  mov     [rbp+150h+var_198], r14d
0x18003a492  mov     r12d, r14d
0x18003a495  mov     dword ptr [rsp+250h+var_200], r14d
0x18003a49a  mov     [rbp+150h+var_1C8], r14
0x18003a49e  mov     [rbp+150h+var_1C0], r14
0x18003a4a2  mov     [rbp+150h+var_1B8], r14
0x18003a4a6  mov     [rbp+150h+var_1B0], r14
0x18003a4aa  mov     [rbp+150h+var_1A8], r14
0x18003a4ae  test    r15, r15
0x18003a4b1  jz      loc_18003B096
0x18003a4b7  test    rbx, rbx
0x18003a4ba  jz      loc_18003B096
0x18003a4c0  mov     [r13+0], r14d
0x18003a4c4  lea     r8, [rbp+150h+var_1D0]
0x18003a4c8  mov     rcx, [r15+10h]
0x18003a4cc  mov     edx, esi
0x18003a4ce  call    FwGetModifiedRuleId
0x18003a4d3  mov     esi, eax
0x18003a4d5  test    eax, eax
0x18003a4d7  js      loc_18003A908
0x18003a4dd  mov     rbx, [r15+18h]
0x18003a4e1  lea     rcx, [rbp+150h+var_190]; void *
0x18003a4e5  mov     rdi, [rbp+150h+var_1D0]
0x18003a4e9  mov     esi, 98h
0x18003a4ee  mov     r8d, esi; Size
0x18003a4f1  xor     edx, edx; Val
0x18003a4f3  call    memset_0
0x18003a4f8  lea     rdx, [rbp+150h+var_18A]
0x18003a4fc  mov     [rbp+150h+var_190], si
0x18003a500  mov     rcx, rdi
0x18003a503  mov     [rbp+150h+var_18E], 5
0x18003a507  mov     [rbp+150h+var_178], rdi
0x18003a50b  call    VfcGetStringParameterSize
0x18003a510  lea     r14, WPP_GLOBAL_Control
0x18003a517  mov     esi, eax
0x18003a519  test    eax, eax
0x18003a51b  jnz     loc_18003A901
0x18003a521  lea     rdx, [rbp+150h+var_188]
0x18003a525  mov     [rbp+150h+var_170], rbx
0x18003a529  mov     rcx, rbx
0x18003a52c  call    VfcGetStringParameterSize
0x18003a531  xor     ebx, ebx
0x18003a533  mov     esi, eax
0x18003a535  test    eax, eax
0x18003a537  jz      loc_18003AD7E
0x18003a53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a544  cmp     rcx, r14
0x18003a547  jz      short loc_18003A56E
0x18003a549  test    byte ptr [rcx+1Ch], 1
0x18003a54d  jz      short loc_18003A56E
0x18003a54f  mov     rcx, [rcx+10h]
0x18003a553  lea     r8, WPP_3826686ba0cf358109adbef3a51266ac_Traceguids
0x18003a55a  mov     edx, 13h
0x18003a55f  mov     r9d, esi
0x18003a562  call    WPP_SF_d
0x18003a567  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a56e  mov     dword ptr [rsp+250h+var_208], esi
0x18003a572  mov     edi, esi
0x18003a574  test    esi, esi
0x18003a576  jg      loc_18003AB6C
0x18003a57c  js      loc_18003AC92
0x18003a582  lea     rcx, [r15+40h]
0x18003a586  lea     rdx, [rbp+150h+var_F0]
0x18003a58a  call    cs:__imp_FwPolioCopyWFAddressesContents
0x18003a591  nop     dword ptr [rax+rax+00h]
0x18003a596  mov     esi, eax
0x18003a598  test    eax, eax
0x18003a59a  js      loc_18003ADB8
0x18003a5a0  lea     rcx, [r15+0A0h]
0x18003a5a7  lea     rdx, [rbp+150h+var_A0]
0x18003a5ae  call    cs:__imp_FwPolioCopyWFAddressesContents
0x18003a5b5  nop     dword ptr [rax+rax+00h]
0x18003a5ba  mov     esi, eax
0x18003a5bc  test    eax, eax
0x18003a5be  js      loc_18003ADD4
0x18003a5c4  mov     [rsp+250h+var_220], rbx; __int64
0x18003a5c9  lea     r8, [rbp+150h+var_198]
0x18003a5cd  mov     dword ptr [rsp+250h+var_228], ebx; char
0x18003a5d1  lea     rcx, [rbp+150h+var_F0]; struct _tag_FW_ADDRESSES *
0x18003a5d5  mov     [rsp+250h+var_230], rbx; __int64
0x18003a5da  xor     r9d, r9d
0x18003a5dd  mov     rbx, [rsp+250h+var_210]
0x18003a5e2  mov     edx, [rbx+4Ch]
0x18003a5e5  call    ResolveAddresses
0x18003a5ea  mov     esi, eax
0x18003a5ec  xor     eax, eax
0x18003a5ee  test    esi, esi
0x18003a5f0  js      loc_18003ADF5
0x18003a5f6  cmp     [rbp+150h+var_198], eax
0x18003a5f9  jnz     loc_18003AE23
0x18003a5ff  mov     edx, [rbx+4Ch]
0x18003a602  lea     r8, [rbp+150h+var_198]
0x18003a606  mov     [rsp+250h+var_220], rax; __int64
0x18003a60b  lea     rcx, [rbp+150h+var_A0]; struct _tag_FW_ADDRESSES *
0x18003a612  mov     dword ptr [rsp+250h+var_228], eax; char
0x18003a616  xor     r9d, r9d
0x18003a619  mov     [rsp+250h+var_230], rax; __int64
0x18003a61e  call    ResolveAddresses
0x18003a623  xor     ecx, ecx
0x18003a625  mov     esi, eax
0x18003a627  test    eax, eax
0x18003a629  js      loc_18003AE44
0x18003a62f  cmp     [rbp+150h+var_198], ecx
0x18003a632  jnz     loc_18003AE63
0x18003a638  test    byte ptr [r15+104h], 4
0x18003a640  lea     r8d, [rcx+2]
0x18003a644  jz      loc_18003AD40
0x18003a64a  mov     [rbp+150h+var_184], cx
0x18003a64e  mov     edx, 1
0x18003a653  mov     eax, [r15+100h]
0x18003a65a  cmp     eax, 3
0x18003a65d  jnz     loc_18003AEB6
0x18003a663  mov     [rbp+150h+var_18D], dl
0x18003a666  lea     rbx, [r15+38h]
0x18003a66a  mov     eax, 100h
0x18003a66f  cmp     [rbx], ax
0x18003a672  jz      short loc_18003A683
0x18003a674  mov     [rbp+150h+var_12E], dl
0x18003a677  mov     [rbp+150h+var_138], dx
0x18003a67b  mov     [rbp+150h+var_160], rbx
0x18003a67f  mov     dword ptr [rsp+250h+var_200], edx
0x18003a683  cmp     [r15+24h], r8d
0x18003a687  lea     rax, [rbp+150h+var_1C8]
0x18003a68b  mov     edx, ecx
0x18003a68d  mov     [rsp+250h+var_230], rax
0x18003a692  setnz   dl
0x18003a695  lea     rcx, [r15+90h]
0x18003a69c  add     edx, 6
0x18003a69f  lea     r9, [rsp+250h+var_200]
0x18003a6a4  lea     r8, [rbp+150h+var_190]
0x18003a6a8  call    FwSetVfpRuleDescriptorPortCondition
0x18003a6ad  mov     esi, eax
0x18003a6af  test    eax, eax
0x18003a6b1  js      loc_18003AEC8
0x18003a6b7  mov     eax, [r15+0F0h]
0x18003a6be  test    eax, eax
0x18003a6c0  jnz     loc_18003AAC1
0x18003a6c6  mov     r13d, dword ptr [rsp+250h+var_200]
0x18003a6cb  lea     ecx, [rax+1]
0x18003a6ce  mov     [rsp+250h+var_1E8], r12
0x18003a6d3  mov     edx, r12d
0x18003a6d6  mov     r9d, [r15+24h]
0x18003a6da  mov     esi, r12d
0x18003a6dd  mov     r11, [rbp+150h+var_B8]
0x18003a6e4  mov     eax, [rbp+150h+var_EC]
0x18003a6e7  mov     [rsp+250h+var_1F4], edx
0x18003a6eb  cmp     [rbp+150h+var_D8], r12d
0x18003a6ef  jnz     loc_18003AB8A
0x18003a6f5  cmp     [rbp+150h+var_F0], r12d
0x18003a6f9  jnz     loc_18003AB8A
0x18003a6ff  test    r11d, r11d
0x18003a702  jnz     loc_18003AF4E
0x18003a708  test    eax, eax
0x18003a70a  jnz     loc_18003AF4E
0x18003a710  mov     r10d, ecx
0x18003a713  mov     edi, ecx
0x18003a715  mov     rax, [rbp+150h+var_68]
0x18003a71c  mov     r8d, [rbp+150h+var_9C]
0x18003a723  cmp     [rbp+150h+var_88], r12d
0x18003a72a  jz      loc_18003AA86
0x18003a730  test    eax, eax
0x18003a732  jz      loc_18003AF64
0x18003a738  mov     eax, 1
0x18003a73d  and     ecx, r10d
0x18003a740  mov     r10d, 1
0x18003a746  cmp     [rbx], r10w
0x18003a74a  jnz     loc_18003AF75
0x18003a750  mov     eax, r12d
0x18003a753  cmp     ecx, r10d
0x18003a756  jz      loc_18003AF86
0x18003a75c  mov     r8d, 2
0x18003a762  cmp     eax, r10d
0x18003a765  jz      loc_18003AAA3
0x18003a76b  mov     edi, r13d
0x18003a76e  mov     [rsp+250h+var_1F8], r13d
0x18003a773  mov     [rsp+250h+var_1F0], r12d
0x18003a778  lea     rax, gFwInboxVfpGroupInfo
0x18003a77f  cmp     r12d, 4
0x18003a783  jnb     loc_18003A92B
0x18003a789  movsxd  rbx, r12d
0x18003a78c  shl     rbx, 5
0x18003a790  mov     ecx, [rbx+rax]
0x18003a793  mov     eax, ecx
0x18003a795  and     eax, edx
0x18003a797  cmp     eax, ecx
0x18003a799  jnz     loc_18003A8F3
0x18003a79f  lea     eax, [rcx-1]
0x18003a7a2  cmp     eax, r10d
0x18003a7a5  jbe     loc_18003ACB2
0x18003a7ab  lea     eax, [rcx-4]
0x18003a7ae  test    eax, 0FFFFFFFBh
0x18003a7b3  jz      loc_18003ABA6
0x18003a7b9  mov     ecx, [rsp+250h+var_1D8]
0x18003a7bd  call    FwGetVfpLayerIdFromStoreType
0x18003a7c2  mov     r8, rax
0x18003a7c5  lea     r9, gFwInboxVfpGroupInfo
0x18003a7cc  mov     r9, [rbx+r9+8]
0x18003a7d1  lea     rax, [rbp+150h+var_190]
0x18003a7d5  mov     rbx, [rsp+250h+var_210]
0x18003a7da  mov     [rsp+250h+var_230], rax
0x18003a7df  mov     rdx, [rbx+10h]
0x18003a7e3  mov     rcx, [rbx+8]
0x18003a7e7  call    FwVfpAddRule
0x18003a7ec  mov     dword ptr [rsp+250h+var_208], eax
0x18003a7f0  test    eax, eax
0x18003a7f2  jg      loc_18003AB7C
0x18003a7f8  mov     esi, eax
0x18003a7fa  test    esi, esi
0x18003a7fc  js      loc_18003B04E
0x18003a802  cmp     edi, r13d
0x18003a805  jnb     loc_18003AB61
0x18003a80b  mov     ecx, r13d
0x18003a80e  mov     ebx, 2
0x18003a813  sub     ecx, edi
0x18003a815  mov     r12d, edi
0x18003a818  cmp     ecx, ebx
0x18003a81a  jb      loc_18003A8CD
0x18003a820  mov     edx, edi
0x18003a822  lea     eax, [r13-1]
0x18003a826  lea     r11, [rbp+150h+var_160]
0x18003a82a  lea     r8, [rbp+150h+var_138]
0x18003a82e  lea     r10, [rbp+150h+var_138]
0x18003a832  lea     r11, [r11+rdx*8]
0x18003a836  lea     r8, [r8+rax*2]
0x18003a83a  mov     [rbp+150h+var_1A0], r11
0x18003a83e  lea     rdi, [rbp+150h+var_160]
0x18003a842  lea     r10, [r10+rdx*2]
0x18003a846  mov     [rsp+250h+var_200], r10
0x18003a84b  lea     rdi, [rdi+rax*8]
0x18003a84f  cmp     r11, r8
0x18003a852  ja      short loc_18003A859
0x18003a854  cmp     rdi, r10
0x18003a857  jnb     short loc_18003A8C9
0x18003a859  lea     r9, [rbp+150h+var_12E]
0x18003a85d  add     r9, rdx
0x18003a860  lea     rdx, [rbp+150h+var_12E]
0x18003a864  add     rdx, rax
0x18003a867  cmp     r11, rdx
0x18003a86a  ja      short loc_18003A871
0x18003a86c  cmp     rdi, r9
0x18003a86f  jnb     short loc_18003A8C9
0x18003a871  cmp     r10, rdx
0x18003a874  ja      short loc_18003A87B
0x18003a876  cmp     r8, r9
0x18003a879  jnb     short loc_18003A8C9
0x18003a87b  mov     edx, 1
0x18003a880  mov     eax, r13d
0x18003a883  and     ecx, edx
0x18003a885  sub     eax, ecx
0x18003a887  add     r12d, ebx
0x18003a88a  cmp     r12d, eax
0x18003a88d  jb      short loc_18003A887
0x18003a88f  sub     eax, [rsp+250h+var_1F8]
0x18003a893  mov     rcx, r9; void *
0x18003a896  lea     ebx, [rdx+rax]
0x18003a899  xor     edx, edx; Val
0x18003a89b  and     rbx, 0FFFFFFFFFFFFFFFEh
0x18003a89f  mov     r8, rbx; Size
0x18003a8a2  call    memset_0
0x18003a8a7  mov     rdi, [rsp+250h+var_200]
0x18003a8ac  xor     eax, eax
0x18003a8ae  movzx   eax, ax
  ... truncated ...
```
