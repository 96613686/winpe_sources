# FwPlumbHyperVRule

- ea: `0x180038eb4`
- end: `0x180039d26`
- name: `FwPlumbHyperVRule`
- size: `3698`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800385f0`
- `0x1800ab048`

## callees

- `0x18000af3c`
- `0x18000b800`
- `0x180038eb4`
- `0x180039d2c`
- `0x180039d6c`
- `0x180039e54`
- `0x180039e8c`
- `0x18003af80`
- `0x18006c898`
- `0x18006f520`
- `0x18006ffc8`
- `0x1800ab300`

## import_xrefs

- `fwbase!FwAlloc` at `0x180039530`
- `fwbase!FwAlloc` at `0x1800395c9`
- `fwbase!FwAlloc` at `0x1800396b4`
- `fwbase!FwAlloc` at `0x180039802`
- `fwbase!FwAlloc` at `0x180039892`
- `fwbase!FwAlloc` at `0x180039530`
- `fwbase!FwAlloc` at `0x1800395c9`
- `fwbase!FwAlloc` at `0x1800396b4`
- `fwbase!FwAlloc` at `0x180039802`
- `fwbase!FwAlloc` at `0x180039892`
- `fwbase!FwFree` at `0x1800393cf`
- `fwbase!FwFree` at `0x1800393da`
- `fwbase!FwFree` at `0x1800393e4`
- `fwbase!FwFree` at `0x1800393ee`
- `fwbase!FwFree` at `0x1800393f8`
- `fwbase!FwFree` at `0x180039402`
- `fwbase!FwFree` at `0x180039424`
- `fwbase!FwFree` at `0x1800393cf`
- `fwbase!FwFree` at `0x1800393da`
- `fwbase!FwFree` at `0x1800393e4`
- `fwbase!FwFree` at `0x1800393ee`
- `fwbase!FwFree` at `0x1800393f8`
- `fwbase!FwFree` at `0x180039402`
- `fwbase!FwFree` at `0x180039424`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180039045`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180039063`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180039045`
- `FWPolicyIOMgr!FwPolioCopyWFAddressesContents` at `0x180039063`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003940c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180039419`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x18003940c`
- `FWPolicyIOMgr!FwPolioEmptyWFAddresses` at `0x180039419`

## pseudocode

```c
__int64 __fastcall FwPlumbHyperVRule(__int64 a1, unsigned int a2, __int64 a3, int *a4)
{
  int *v4; // rbx
  __int64 v7; // r12
  char v8; // di
  unsigned int v9; // r15d
  int ModifiedRuleId; // eax
  signed int StringParameterSize; // esi
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // rcx
  bool v15; // sf
  int v16; // eax
  __int64 v17; // rdx
  int v18; // eax
  _WORD *v19; // r12
  __int64 v20; // rax
  __int64 v21; // rax
  int v22; // r9d
  int v23; // r10d
  unsigned int v24; // r11d
  int v25; // ecx
  unsigned int v26; // ebx
  int v27; // r8d
  unsigned int v28; // edi
  unsigned int v29; // eax
  int v30; // ecx
  int v31; // eax
  __int64 v32; // r8
  unsigned int i; // eax
  __int64 v34; // r12
  int v35; // ecx
  int VfpLayerIdFromStoreType; // eax
  __int64 v37; // r9
  int v38; // eax
  unsigned int v39; // r12d
  __int64 v40; // rax
  _QWORD *v41; // r11
  _WORD *v42; // r8
  _WORD *v43; // r10
  _QWORD *v44; // rdi
  _BYTE *v45; // r9
  unsigned int v46; // eax
  size_t v47; // rbx
  _WORD *v48; // rdi
  size_t k; // rcx
  __int64 v50; // rcx
  __int64 v51; // rdx
  __int64 v52; // r9
  int v53; // r8d
  int v55; // r8d
  __int64 v56; // rcx
  int v57; // esi
  __int16 v58; // bx
  __int64 v59; // rdi
  _WORD *v60; // r8
  unsigned int v61; // r9d
  __int64 v62; // rdx
  __int64 v63; // rcx
  int v64; // ebx
  __int16 v65; // di
  __int64 v66; // rax
  __int64 v67; // rdx
  _WORD *v68; // r8
  unsigned int v69; // r9d
  __int64 v70; // rdx
  int v71; // ebx
  __int64 v72; // rdx
  _OWORD *v73; // r8
  unsigned int j; // r9d
  __int64 v75; // rcx
  int v76; // eax
  __int64 v77; // rcx
  __int64 v78; // rdx
  int v79; // esi
  __int64 v80; // rbx
  __int64 v81; // rax
  unsigned int v82; // r9d
  __int64 v83; // rcx
  int v84; // esi
  __int16 v85; // bx
  __int64 v86; // rax
  unsigned int v87; // r9d
  __int64 v88; // rcx
  __int64 v89; // r9
  __int64 v90; // rdx
  __int64 v91; // r9
  int v92; // eax
  __int64 v93; // rcx
  char v94; // [rsp+40h] [rbp-C0h]
  unsigned int v97; // [rsp+58h] [rbp-A8h]
  int v98; // [rsp+5Ch] [rbp-A4h]
  _WORD *v99; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v100; // [rsp+68h] [rbp-98h]
  unsigned int v101; // [rsp+6Ch] [rbp-94h]
  __int64 v102; // [rsp+70h] [rbp-90h]
  __int64 v103; // [rsp+78h] [rbp-88h] BYREF
  __int64 v104; // [rsp+80h] [rbp-80h]
  __int64 v105; // [rsp+88h] [rbp-78h]
  __int64 v106; // [rsp+90h] [rbp-70h]
  __int64 v107; // [rsp+98h] [rbp-68h]
  __int64 v108; // [rsp+A0h] [rbp-60h] BYREF
  void *v109; // [rsp+A8h] [rbp-58h]
  int v110; // [rsp+B0h] [rbp-50h]
  __int16 v111; // [rsp+C0h] [rbp-40h] BYREF
  char v112; // [rsp+C2h] [rbp-3Eh] BYREF
  char v113; // [rsp+C3h] [rbp-3Dh]
  __int16 v114; // [rsp+C4h] [rbp-3Ch]
  char v115[2]; // [rsp+C6h] [rbp-3Ah] BYREF
  char v116[4]; // [rsp+C8h] [rbp-38h] BYREF
  __int16 v117; // [rsp+CCh] [rbp-34h]
  __int64 v118; // [rsp+D8h] [rbp-28h]
  __int64 v119; // [rsp+E0h] [rbp-20h]
  _QWORD v120[5]; // [rsp+F0h] [rbp-10h] BYREF
  _WORD v121[5]; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v122[62]; // [rsp+122h] [rbp+22h] BYREF
  int v123; // [rsp+160h] [rbp+60h] BYREF
  int v124; // [rsp+164h] [rbp+64h]
  __int64 v125; // [rsp+178h] [rbp+78h]
  __int64 v126; // [rsp+180h] [rbp+80h]
  __int64 v127; // [rsp+198h] [rbp+98h]
  __int64 v128; // [rsp+1A0h] [rbp+A0h]
  int v129; // [rsp+1B0h] [rbp+B0h] BYREF
  int v130; // [rsp+1B4h] [rbp+B4h]
  unsigned int v131; // [rsp+1C8h] [rbp+C8h]
  __int64 v132; // [rsp+1D0h] [rbp+D0h]
  __int64 v133; // [rsp+1E8h] [rbp+E8h] BYREF

  v4 = a4;
  v101 = a2;
  v7 = a1;
  v111 = 0;
  v8 = 0;
  memset_0(&v112, 0, 0x96u);
  v103 = 0;
  memset_0(&v123, 0, 0x48u);
  memset_0(&v129, 0, 0x48u);
  v110 = 0;
  v9 = 0;
  LODWORD(v99) = 0;
  v104 = 0;
  v102 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  if ( !a3 || !v7 )
  {
    StringParameterSize = -2147024809;
    v50 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_74;
    v51 = 18;
    v52 = 2147942487LL;
LABEL_150:
    WPP_SF_d(*(_QWORD *)(v50 + 16), v51, WPP_3ac025dd596b34dc773177d03687c214_Traceguids, v52);
    goto LABEL_74;
  }
  *v4 = 0;
  ModifiedRuleId = FwGetModifiedRuleId(*(_QWORD *)(a3 + 16), a2, &v103);
  StringParameterSize = ModifiedRuleId;
  if ( ModifiedRuleId < 0 )
  {
    v50 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_74;
    v51 = 19;
    v52 = (unsigned int)ModifiedRuleId;
    goto LABEL_150;
  }
  v12 = *(_QWORD *)(a3 + 24);
  v13 = v103;
  memset_0(&v111, 0, 0x98u);
  v111 = 152;
  v112 = 5;
  v118 = v13;
  StringParameterSize = VfcGetStringParameterSize(v13, v115);
  if ( !StringParameterSize )
  {
    v119 = v12;
    StringParameterSize = VfcGetStringParameterSize(v12, v116);
    if ( !StringParameterSize )
    {
      v14 = WPP_GLOBAL_Control;
      v114 = 8195;
      v8 = 0;
      v94 = 0;
      StringParameterSize = 0;
      goto LABEL_104;
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
  v94 = StringParameterSize;
  v8 = StringParameterSize;
  v15 = StringParameterSize < 0;
  if ( StringParameterSize > 0 )
  {
    StringParameterSize = (unsigned __int16)StringParameterSize | 0x80070000;
LABEL_104:
    v15 = StringParameterSize < 0;
  }
  if ( v15 )
  {
    if ( (_UNKNOWN *)v14 == &WPP_GLOBAL_Control || (*(_BYTE *)(v14 + 28) & 1) == 0 )
      goto LABEL_124;
    v90 = 20;
LABEL_154:
    v91 = (unsigned int)StringParameterSize;
LABEL_156:
    WPP_SF_d(*(_QWORD *)(v14 + 16), v90, WPP_3ac025dd596b34dc773177d03687c214_Traceguids, v91);
    goto LABEL_124;
  }
  v16 = FwPolioCopyWFAddressesContents(a3 + 64, &v123);
  StringParameterSize = v16;
  if ( v16 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_124;
    v90 = 21;
    goto LABEL_160;
  }
  v16 = FwPolioCopyWFAddressesContents(a3 + 160, &v129);
  StringParameterSize = v16;
  if ( v16 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_124;
    v90 = 22;
    goto LABEL_160;
  }
  v16 = ResolveAddresses((struct _tag_FW_ADDRESSES *)&v123, 0, 0, 0);
  StringParameterSize = v16;
  if ( v16 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_124;
    v90 = 23;
    goto LABEL_160;
  }
  if ( v110 )
  {
    StringParameterSize = 0;
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_124;
    v90 = 24;
    goto LABEL_155;
  }
  v16 = ResolveAddresses((struct _tag_FW_ADDRESSES *)&v129, 0, 0, 0);
  StringParameterSize = v16;
  if ( v16 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_124;
    v90 = 25;
LABEL_160:
    v91 = (unsigned int)v16;
    goto LABEL_156;
  }
  if ( v110 )
  {
    StringParameterSize = 0;
    v14 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_124;
    v90 = 26;
LABEL_155:
    v91 = 0;
    goto LABEL_156;
  }
  if ( (*(_BYTE *)(a3 + 260) & 4) != 0 )
  {
    v117 = 0;
LABEL_19:
    v17 = 1;
    goto LABEL_20;
  }
  if ( *(_WORD *)(a3 + 32) )
  {
    v117 = *(_WORD *)(a3 + 32);
    goto LABEL_19;
  }
  v92 = *(_DWORD *)(a3 + 256);
  if ( v92 == 3 )
  {
    v117 = 2;
    goto LABEL_19;
  }
  if ( v92 != 2 )
    goto LABEL_19;
  v17 = 1;
  v117 = 1;
LABEL_20:
  v18 = *(_DWORD *)(a3 + 256);
  if ( v18 == 3 )
  {
    v113 = 1;
  }
  else if ( v18 == 2 )
  {
    v113 = 2;
  }
  v19 = (_WORD *)(a3 + 56);
  if ( *(_WORD *)(a3 + 56) != 256 )
  {
    v122[0] = 1;
    v9 = 1;
    v121[0] = 1;
    v120[0] = a3 + 56;
    LODWORD(v99) = 1;
  }
  v20 = *(unsigned int *)(a3 + 144);
  if ( (_DWORD)v20 )
  {
    v57 = *(_DWORD *)(a3 + 36);
    v58 = 4 * v20;
    v59 = FwAlloc(4 * v20);
    if ( !v59 )
    {
      v77 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          15,
          WPP_3ac025dd596b34dc773177d03687c214_Traceguids,
          2147942414LL);
        v77 = WPP_GLOBAL_Control;
      }
      StringParameterSize = -2147024882;
      if ( (_UNKNOWN *)v77 != &WPP_GLOBAL_Control && (*(_BYTE *)(v77 + 28) & 1) != 0 )
      {
        v78 = 27;
LABEL_149:
        v89 = 2147942414LL;
LABEL_182:
        WPP_SF_d(*(_QWORD *)(v77 + 16), v78, WPP_3ac025dd596b34dc773177d03687c214_Traceguids, v89);
      }
      goto LABEL_183;
    }
    v60 = (_WORD *)v59;
    v61 = 0;
    if ( *(_DWORD *)(a3 + 144) )
    {
      do
      {
        v62 = v61++;
        *v60 = *(_WORD *)(*(_QWORD *)(a3 + 152) + 4 * v62);
        v60 += 2;
        *(v60 - 1) = *(_WORD *)(*(_QWORD *)(a3 + 152) + 4 * v62 + 2);
      }
      while ( v61 < *(_DWORD *)(a3 + 144) );
      v19 = (_WORD *)(a3 + 56);
    }
    v63 = v9;
    v17 = 1;
    v104 = v59;
    v122[v9++] = (v57 != 2) + 6;
    v121[v63] = v58;
    v120[v63] = v59;
    LODWORD(v99) = v9;
  }
  v21 = *(unsigned int *)(a3 + 240);
  if ( !(_DWORD)v21 )
  {
    StringParameterSize = 0;
    v102 = 0;
    goto LABEL_27;
  }
  v64 = *(_DWORD *)(a3 + 36);
  v65 = 4 * v21;
  v66 = FwAlloc(4 * v21);
  StringParameterSize = 0;
  v102 = v66;
  v67 = v66;
  if ( !v66 )
  {
    v93 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          15,
          WPP_3ac025dd596b34dc773177d03687c214_Traceguids,
          2147942414LL);
        v93 = WPP_GLOBAL_Control;
      }
      if ( (_UNKNOWN *)v93 != &WPP_GLOBAL_Control && (*(_BYTE *)(v93 + 28) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(v93 + 16), 28, WPP_3ac025dd596b34dc773177d03687c214_Traceguids, 2147942414LL);
    }
    v102 = 0;
    StringParameterSize = -2147024882;
LABEL_183:
    v7 = a1;
    v8 = v94;
    goto LABEL_124;
  }
  v68 = (_WORD *)v66;
  v69 = 0;
  if ( *(_DWORD *)(a3 + 240) )
  {
    do
    {
      v70 = v69++;
      *v68 = *(_WORD *)(*(_QWORD *)(a3 + 248) + 4 * v70);
      v68 += 2;
      *(v68 - 1) = *(_WORD *)(*(_QWORD *)(a3 + 248) + 4 * v70 + 2);
    }
    while ( v69 < *(_DWORD *)(a3 + 240) );
    v67 = v102;
    v19 = (_WORD *)(a3 + 56);
  }
  v122[v9] = (v64 == 2) + 6;
  v121[v9] = v65;
  v120[v9] = v67;
  v17 = 1;
  LODWORD(v99) = ++v9;
LABEL_27:
  v22 = *(_DWORD *)(a3 + 36);
  v23 = 0;
  v24 = v127;
  v25 = 0;
  v98 = 0;
  v26 = v125;
  if ( (_DWORD)v125 || v123 )
  {
    v27 = 1;
  }
  else
  {
    if ( !(_DWORD)v127 && !v124 )
    {
      v27 = 1;
      goto LABEL_32;
    }
    v27 = 0;
  }
  if ( !(_DWORD)v127 && !v124 )
    v17 = 0;
LABEL_32:
  if ( v131 || v129 )
  {
    v25 = 1;
  }
  else
  {
    if ( (_DWORD)v133 )
    {
LABEL_35:
      v28 = 1;
LABEL_36:
      v29 = v28;
      goto LABEL_37;
    }
    if ( !v130 )
    {
      v28 = v133 + 1;
      v25 = v133 + 1;
      goto LABEL_36;
    }
  }
  if ( (_DWORD)v133 )
    goto LABEL_35;
  v29 = 0;
  if ( v130 )
    goto LABEL_35;
  v28 = 1;
LABEL_37:
  v30 = v27 & v25;
  if ( *v19 == (_WORD)v28 )
  {
    v31 = 0;
  }
  else
  {
    v31 = v17 & v29;
    if ( *v19 == 58 )
      goto LABEL_40;
  }
  if ( v30 != v28 )
  {
LABEL_40:
    v32 = 2;
    goto LABEL_41;
  }
  v32 = 2;
  if ( v22 == v28 )
  {
    v23 = v28;
    v98 = v28;
  }
  else
  {
    if ( v22 == 2 )
      v23 = 2;
    v98 = v23;
  }
LABEL_41:
  if ( v31 == v28 )
  {
    if ( v22 == v28 )
    {
      v23 |= 4u;
    }
    else
    {
      if ( v22 != 2 )
        goto LABEL_42;
      v23 |= 8u;
    }
    v98 = v23;
  }
LABEL_42:
  v97 = v9;
  for ( i = 0; ; i = v28 + v100 )
  {
    v100 = i;
    if ( i >= 4 )
    {
      v4 = a4;
      v7 = a1;
      v8 = v94;
      *a4 = v23;
      goto LABEL_74;
    }
    v34 = 4LL * (int)i;
    v35 = gFwInboxVfpGroupInfo[v34];
    if ( (v35 & v23) == v35 )
      break;
LABEL_68:
    v32 = 2;
  }
  if ( v35 - 1 <= v28 )
  {
    if ( v26 )
    {
      v79 = *(_DWORD *)(a3 + 36);
      v80 = 8LL * v26;
      v81 = FwAlloc(v80);
      v82 = 0;
      if ( !v81 )
      {
        v77 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            16,
            WPP_3ac025dd596b34dc773177d03687c214_Traceguids,
            2147942414LL);
          v77 = WPP_GLOBAL_Control;
        }
        StringParameterSize = -2147024882;
        if ( (_UNKNOWN *)v77 != &WPP_GLOBAL_Control && (*(_BYTE *)(v77 + 28) & 1) != 0 )
        {
          v78 = 29;
          goto LABEL_149;
        }
        goto LABEL_183;
      }
      v32 = v81;
      if ( (_DWORD)v125 )
      {
        do
        {
          v17 = v82++;
          *(_DWORD *)v32 = _byteswap_ulong(*(_DWORD *)(v126 + 8 * v17));
          v32 += 8;
          *(_DWORD *)(v32 - 4) = _byteswap_ulong(*(_DWORD *)(v126 + 8 * v17 + 4));
        }
        while ( v82 < (unsigned int)v125 );
      }
      v83 = v9;
      v105 = v81;
      v122[v9++] = (v79 != 2) + 10;
      v121[v83] = v80;
      v120[v83] = v81;
    }
    if ( v131 )
    {
      v84 = *(_DWORD *)(a3 + 36);
      v85 = 8 * v131;
      v86 = FwAlloc(8LL * v131);
      v87 = 0;
      if ( !v86 )
      {
        v77 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            16,
            WPP_3ac025dd596b34dc773177d03687c214_Traceguids,
            2147942414LL);
          v77 = WPP_GLOBAL_Control;
        }
        StringParameterSize = -2147024882;
        if ( (_UNKNOWN *)v77 != &WPP_GLOBAL_Control && (*(_BYTE *)(v77 + 28) & 1) != 0 )
        {
          v78 = 30;
          goto LABEL_149;
        }
        goto LABEL_183;
      }
      v32 = v86;
      if ( v131 )
      {
        do
        {
          v17 = v87++;
          *(_DWORD *)v32 = _byteswap_ulong(*(_DWORD *)(v132 + 8 * v17));
          v32 += 8;
          *(_DWORD *)(v32 - 4) = _byteswap_ulong(*(_DWORD *)(v132 + 8 * v17 + 4));
        }
        while ( v87 < v131 );
      }
      v88 = v9;
      v106 = v86;
      v122[v9++] = (v84 == 2) + 10;
      v121[v88] = v85;
      v120[v88] = v86;
    }
  }
  else if ( ((v35 - 4) & 0xFFFFFFFB) == 0 )
  {
    if ( v24 )
    {
      v71 = *(_DWORD *)(a3 + 36);
      LOWORD(v28) = 32 * v24;
      v72 = FwAlloc(32LL * v24);
      if ( !v72 )
      {
        v77 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            17,
            WPP_3ac025dd596b34dc773177d03687c214_Traceguids,
            2147942414LL);
          v77 = WPP_GLOBAL_Control;
        }
        StringParameterSize = -2147024882;
        if ( (_UNKNOWN *)v77 != &WPP_GLOBAL_Control && (*(_BYTE *)(v77 + 28) & 1) != 0 )
        {
          v78 = 31;
          goto LABEL_149;
        }
        goto LABEL_183;
      }
      v73 = (_OWORD *)v72;
      for ( j = 0; j < (unsigned int)v127; *(v73 - 1) = *(_OWORD *)(v128 + v75 + 16) )
      {
        v75 = j++;
        v75 *= 32;
        *v73 = *(_OWORD *)(v128 + v75);
        v73 += 2;
      }
      v107 = v72;
      v122[v9] = (v71 != 2) + 12;
      v121[v9] = v28;
      LOBYTE(v28) = 1;
      v120[v9] = v72;
      LODWORD(v99) = v9 + 1;
    }
    v76 = FwSetVfpRuleDescriptorIPV6AddressCondition(
            (unsigned int)&v133,
            13 - (unsigned int)(*(_DWORD *)(a3 + 36) != 2),
            (unsigned int)&v111,
            (unsigned int)&v99,
            (__int64)&v108);
    StringParameterSize = v76;
    if ( v76 < 0 )
    {
      v77 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && ((unsigned __int8)v28 & *(_BYTE *)(WPP_GLOBAL_Control + 28LL)) != 0 )
      {
        v78 = 32;
        v89 = (unsigned int)v76;
        goto LABEL_182;
      }
      goto LABEL_183;
    }
    v9 = (unsigned int)v99;
  }
  VfpLayerIdFromStoreType = FwGetVfpLayerIdFromStoreType(v101, v17, v32);
  v37 = gFwInboxVfpGroupInfo[v34 + 1];
  v7 = a1;
  v38 = FwVfpAddRule(*(_QWORD *)(a1 + 8), *(_QWORD *)(a1 + 16), VfpLayerIdFromStoreType, v37, (__int64)&v111);
  v94 = v38;
  v8 = v38;
  if ( v38 > 0 )
    StringParameterSize = (unsigned __int16)v38 | 0x80070000;
  else
    StringParameterSize = v38;
  if ( StringParameterSize >= 0 )
  {
    v17 = v97;
    if ( v97 >= v9 )
    {
      v28 = 1;
    }
    else
    {
      v39 = v97;
      if ( v9 - v97 >= 2 )
      {
        v40 = v9 - 1;
        v41 = &v120[v97];
        v109 = v41;
        v42 = &v121[v40];
        v43 = &v121[v97];
        v99 = v43;
        v44 = &v120[v40];
        if ( v41 > (_QWORD *)v42 || v44 < (_QWORD *)v43 )
        {
          v45 = &v122[v97];
          if ( (v41 > (_QWORD *)&v122[v40] || v44 < (_QWORD *)v45) && (v43 > (_WORD *)&v122[v40] || v42 < (_WORD *)v45) )
          {
            v46 = v9 - (((_BYTE)v9 - (_BYTE)v97) & 1);
            do
              v39 += 2;
            while ( v39 < v46 );
            v47 = (v46 - v97 + 1) & 0xFFFFFFFE;
            memset_0(v45, 0, v47);
            v48 = v99;
            for ( k = v47; k; --k )
              *v48++ = 0;
            memset_0(v109, 0, 8 * v47);
          }
        }
        v17 = v97;
      }
      v28 = 1;
      while ( v39 < v9 )
      {
        v56 = v39++;
        v122[v56] = 0;
        v121[v56] = 0;
        v120[v56] = 0;
      }
    }
    v24 = v127;
    v9 = v17;
    v26 = v125;
    v23 = v98;
    LODWORD(v99) = v17;
    goto LABEL_68;
  }
  v14 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    v90 = 33;
    goto LABEL_154;
  }
LABEL_124:
  v4 = a4;
LABEL_74:
  FwFree(v104);
  FwFree(v102);
  FwFree(v105);
  FwFree(v106);
  FwFree(v107);
  FwFree(v108);
  FwPolioEmptyWFAddresses(&v123);
  FwPolioEmptyWFAddresses(&v129);
  FwFree(v103);
  if ( StringParameterSize < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_SSSd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        34,
        v53,
        *(_QWORD *)(v7 + 16),
        *(_QWORD *)(v7 + 8),
        *(_QWORD *)(a3 + 16),
        v8);
    if ( (unsigned int)FwWriterDeleteHyperVRule(v7, v101, *(_QWORD *)(a3 + 16), v4)
      && (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_SSSd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        35,
        v55,
        *(_QWORD *)(v7 + 16),
        *(_QWORD *)(v7 + 8),
        *(_QWORD *)(a3 + 16),
        v8);
    }
  }
  return (unsigned int)StringParameterSize;
}

```

## disassembly

```asm
0x180038eb4  push    rbp
0x180038eb6  push    rbx
0x180038eb7  push    rsi
0x180038eb8  push    rdi
0x180038eb9  push    r12
0x180038ebb  push    r13
0x180038ebd  push    r14
0x180038ebf  push    r15
0x180038ec1  lea     rbp, [rsp-118h]
0x180038ec9  sub     rsp, 218h
0x180038ed0  mov     rax, cs:__security_cookie
0x180038ed7  xor     rax, rsp
0x180038eda  mov     [rbp+150h+var_50], rax
0x180038ee1  mov     rbx, r9
0x180038ee4  mov     [rsp+250h+var_1E4], edx
0x180038ee8  mov     r13, r8
0x180038eeb  mov     [rsp+250h+var_200], rcx
0x180038ef0  mov     esi, edx
0x180038ef2  mov     [rsp+250h+var_208], rbx
0x180038ef7  mov     r12, rcx
0x180038efa  xor     r14d, r14d
0x180038efd  xor     edx, edx; Val
0x180038eff  mov     [rbp+150h+var_190], r14w
0x180038f04  mov     r8d, 96h; Size
0x180038f0a  lea     rcx, [rbp+150h+var_18E]; void *
0x180038f0e  mov     edi, r14d
0x180038f11  call    memset_0
0x180038f16  mov     [rsp+250h+var_1D8], r14
0x180038f1b  lea     rcx, [rbp+150h+var_F0]; void *
0x180038f1f  mov     r14d, 48h ; 'H'
0x180038f25  xor     edx, edx; Val
0x180038f27  mov     r8d, r14d; Size
0x180038f2a  call    memset_0
0x180038f2f  mov     r8d, r14d; Size
0x180038f32  lea     rcx, [rbp+150h+var_A0]; void *
0x180038f39  xor     edx, edx; Val
0x180038f3b  call    memset_0
0x180038f40  xor     r14d, r14d
0x180038f43  mov     [rbp+150h+var_1A0], r14d
0x180038f47  mov     r15d, r14d
0x180038f4a  mov     dword ptr [rsp+250h+var_1F0], r14d
0x180038f4f  mov     [rbp+150h+var_1D0], r14
0x180038f53  mov     [rsp+250h+var_1E0], r14
0x180038f58  mov     [rbp+150h+var_1C8], r14
0x180038f5c  mov     [rbp+150h+var_1C0], r14
0x180038f60  mov     [rbp+150h+var_1B8], r14
0x180038f64  mov     [rbp+150h+var_1B0], r14
0x180038f68  test    r13, r13
0x180038f6b  jz      loc_180039CCC
0x180038f71  test    r12, r12
0x180038f74  jz      loc_180039CCC
0x180038f7a  mov     [rbx], r14d
0x180038f7d  lea     r8, [rsp+250h+var_1D8]
0x180038f82  mov     rcx, [r13+10h]
0x180038f86  mov     edx, esi
0x180038f88  call    FwGetModifiedRuleId
0x180038f8d  mov     esi, eax
0x180038f8f  test    eax, eax
0x180038f91  js      loc_180039394
0x180038f97  mov     rbx, [r13+18h]
0x180038f9b  lea     rcx, [rbp+150h+var_190]; void *
0x180038f9f  mov     rdi, [rsp+250h+var_1D8]
0x180038fa4  mov     esi, 98h
0x180038fa9  mov     r8d, esi; Size
0x180038fac  xor     edx, edx; Val
0x180038fae  call    memset_0
0x180038fb3  lea     rdx, [rbp+150h+var_18A]
0x180038fb7  mov     [rbp+150h+var_190], si
0x180038fbb  mov     rcx, rdi
0x180038fbe  mov     [rbp+150h+var_18E], 5
0x180038fc2  mov     [rbp+150h+var_178], rdi
0x180038fc6  call    VfcGetStringParameterSize
0x180038fcb  lea     r14, WPP_GLOBAL_Control
0x180038fd2  mov     esi, eax
0x180038fd4  test    eax, eax
0x180038fd6  jnz     loc_18003938D
0x180038fdc  lea     rdx, [rbp+150h+var_188]
0x180038fe0  mov     [rbp+150h+var_170], rbx
0x180038fe4  mov     rcx, rbx
0x180038fe7  call    VfcGetStringParameterSize
0x180038fec  xor     ebx, ebx
0x180038fee  mov     esi, eax
0x180038ff0  test    eax, eax
0x180038ff2  jz      loc_1800399F0
0x180038ff8  mov     rcx, cs:WPP_GLOBAL_Control
0x180038fff  cmp     rcx, r14
0x180039002  jz      short loc_180039029
0x180039004  test    byte ptr [rcx+1Ch], 1
0x180039008  jz      short loc_180039029
0x18003900a  mov     rcx, [rcx+10h]
0x18003900e  lea     r8, WPP_3826686ba0cf358109adbef3a51266ac_Traceguids
0x180039015  mov     edx, 13h
0x18003901a  mov     r9d, esi
0x18003901d  call    WPP_SF_d
0x180039022  mov     rcx, cs:WPP_GLOBAL_Control
0x180039029  mov     dword ptr [rsp+250h+var_210], esi
0x18003902d  mov     edi, esi
0x18003902f  test    esi, esi
0x180039031  jg      loc_180039664
0x180039037  js      loc_1800397DA
0x18003903d  lea     rcx, [r13+40h]
0x180039041  lea     rdx, [rbp+150h+var_F0]
0x180039045  call    cs:__imp_FwPolioCopyWFAddressesContents
0x18003904b  mov     esi, eax
0x18003904d  test    eax, eax
0x18003904f  js      loc_180039A45
0x180039055  lea     rcx, [r13+0A0h]
0x18003905c  lea     rdx, [rbp+150h+var_A0]
0x180039063  call    cs:__imp_FwPolioCopyWFAddressesContents
0x180039069  mov     esi, eax
0x18003906b  test    eax, eax
0x18003906d  js      loc_180039A70
0x180039073  mov     edx, [r12+4Ch]
0x180039078  lea     r8, [rbp+150h+var_1A0]
0x18003907c  mov     [rsp+250h+var_220], rbx; __int64
0x180039081  lea     rcx, [rbp+150h+var_F0]; struct _tag_FW_ADDRESSES *
0x180039085  mov     dword ptr [rsp+250h+var_228], ebx; char
0x180039089  xor     r9d, r9d
0x18003908c  mov     [rsp+250h+var_230], rbx; __int64
0x180039091  call    ResolveAddresses
0x180039096  mov     esi, eax
0x180039098  test    eax, eax
0x18003909a  js      loc_180039A91
0x1800390a0  cmp     [rbp+150h+var_1A0], ebx
0x1800390a3  jnz     loc_180039AB2
0x1800390a9  mov     edx, [r12+4Ch]
0x1800390ae  lea     r8, [rbp+150h+var_1A0]
0x1800390b2  mov     [rsp+250h+var_220], rbx; __int64
0x1800390b7  lea     rcx, [rbp+150h+var_A0]; struct _tag_FW_ADDRESSES *
0x1800390be  mov     dword ptr [rsp+250h+var_228], ebx; char
0x1800390c2  xor     r9d, r9d
0x1800390c5  mov     [rsp+250h+var_230], rbx; __int64
0x1800390ca  call    ResolveAddresses
0x1800390cf  mov     esi, eax
0x1800390d1  test    eax, eax
0x1800390d3  js      loc_180039AD3
0x1800390d9  cmp     [rbp+150h+var_1A0], ebx
0x1800390dc  jnz     loc_180039AF2
0x1800390e2  test    byte ptr [r13+104h], 4
0x1800390ea  mov     ecx, 2
0x1800390ef  jz      loc_180039912
0x1800390f5  mov     [rbp+150h+var_184], bx
0x1800390f9  mov     edx, 1
0x1800390fe  mov     eax, [r13+100h]
0x180039105  cmp     eax, 3
0x180039108  jnz     loc_180039B43
0x18003910e  mov     [rbp+150h+var_18D], dl
0x180039111  lea     r12, [r13+38h]
0x180039115  mov     eax, 100h
0x18003911a  cmp     [r12], ax
0x18003911f  jz      short loc_180039133
0x180039121  mov     [rbp+150h+var_12E], dl
0x180039124  mov     r15d, edx
0x180039127  mov     [rbp+150h+var_138], dx
0x18003912b  mov     [rbp+150h+var_160], r12
0x18003912f  mov     dword ptr [rsp+250h+var_1F0], edx
0x180039133  mov     eax, [r13+90h]
0x18003913a  test    eax, eax
0x18003913c  jnz     loc_180039522
0x180039142  mov     eax, [r13+0F0h]
0x180039149  test    eax, eax
0x18003914b  jnz     loc_1800395BB
0x180039151  mov     esi, ebx
0x180039153  mov     [rsp+250h+var_1E0], rbx
0x180039158  mov     r9d, [r13+24h]
0x18003915c  mov     r10d, ebx
0x18003915f  mov     r11, [rbp+150h+var_B8]
0x180039166  xor     ecx, ecx
0x180039168  mov     eax, [rbp+150h+var_EC]
0x18003916b  mov     [rsp+250h+var_1F4], ebx
0x18003916f  mov     rbx, [rbp+150h+var_D8]
0x180039173  test    ebx, ebx
0x180039175  jnz     loc_180039682
0x18003917b  cmp     [rbp+150h+var_F0], ecx
0x18003917e  jnz     loc_180039682
0x180039184  test    r11d, r11d
0x180039187  jnz     loc_180039BDB
0x18003918d  test    eax, eax
0x18003918f  jnz     loc_180039BDB
0x180039195  mov     r8d, edx
0x180039198  mov     rax, [rbp+150h+var_68]
0x18003919f  mov     edi, [rbp+150h+var_9C]
0x1800391a5  cmp     [rbp+150h+var_88], ecx
0x1800391ab  jz      loc_1800394DC
0x1800391b1  mov     ecx, 1
0x1800391b6  test    eax, eax
0x1800391b8  jz      loc_180039BE3
0x1800391be  mov     edi, 1
0x1800391c3  mov     eax, edi
0x1800391c5  and     ecx, r8d
0x1800391c8  cmp     [r12], di
0x1800391cd  jnz     loc_180039BF5
0x1800391d3  xor     eax, eax
0x1800391d5  cmp     ecx, edi
0x1800391d7  jz      loc_180039C08
0x1800391dd  mov     r8d, 2
0x1800391e3  cmp     eax, edi
0x1800391e5  jz      loc_180039502
0x1800391eb  xor     r9d, r9d
0x1800391ee  mov     [rsp+250h+var_1F8], r15d
0x1800391f3  mov     eax, r9d
0x1800391f6  mov     [rsp+250h+var_1E8], eax
0x1800391fa  lea     rcx, gFwInboxVfpGroupInfo
0x180039201  cmp     eax, 4
0x180039204  jnb     loc_1800393BA
0x18003920a  movsxd  r12, eax
0x18003920d  mov     eax, r10d
0x180039210  shl     r12, 5
0x180039214  mov     ecx, [r12+rcx]
0x180039218  and     eax, ecx
0x18003921a  cmp     eax, ecx
0x18003921c  jnz     loc_18003937C
0x180039222  lea     eax, [rcx-1]
0x180039225  cmp     eax, edi
0x180039227  jbe     loc_1800397ED
0x18003922d  lea     eax, [rcx-4]
0x180039230  test    eax, 0FFFFFFFBh
0x180039235  jz      loc_18003969D
0x18003923b  mov     ecx, [rsp+250h+var_1E4]
0x18003923f  call    FwGetVfpLayerIdFromStoreType
0x180039244  mov     r8, rax
0x180039247  lea     r9, gFwInboxVfpGroupInfo
0x18003924e  mov     r9, [r12+r9+8]
0x180039253  lea     rax, [rbp+150h+var_190]
0x180039257  mov     r12, [rsp+250h+var_200]
0x18003925c  mov     [rsp+250h+var_230], rax
0x180039261  mov     rdx, [r12+10h]
0x180039266  mov     rcx, [r12+8]
0x18003926b  call    FwVfpAddRule
0x180039270  xor     r9d, r9d
0x180039273  mov     dword ptr [rsp+250h+var_210], eax
0x180039277  mov     edi, eax
0x180039279  test    eax, eax
0x18003927b  jg      loc_180039674
0x180039281  mov     esi, eax
0x180039283  test    esi, esi
0x180039285  js      loc_180039CAD
0x18003928b  mov     edx, [rsp+250h+var_1F8]
0x18003928f  cmp     edx, r15d
0x180039292  jnb     loc_18003965A
0x180039298  mov     ecx, r15d
0x18003929b  mov     ebx, 2
0x1800392a0  sub     ecx, edx
0x1800392a2  mov     r12d, edx
0x1800392a5  cmp     ecx, ebx
0x1800392a7  jb      loc_180039357
0x1800392ad  lea     eax, [r15-1]
0x1800392b1  lea     r11, [rbp+150h+var_160]
0x1800392b5  lea     r11, [r11+rdx*8]
0x1800392b9  lea     r8, [rbp+150h+var_138]
0x1800392bd  mov     [rbp+150h+var_1A8], r11
0x1800392c1  lea     r10, [rbp+150h+var_138]
0x1800392c5  lea     r8, [r8+rax*2]
0x1800392c9  lea     rdi, [rbp+150h+var_160]
0x1800392cd  lea     r10, [r10+rdx*2]
0x1800392d1  mov     [rsp+250h+var_1F0], r10
0x1800392d6  lea     rdi, [rdi+rax*8]
0x1800392da  cmp     r11, r8
0x1800392dd  ja      short loc_1800392E4
0x1800392df  cmp     rdi, r10
0x1800392e2  jnb     short loc_180039353
0x1800392e4  lea     r9, [rbp+150h+var_12E]
0x1800392e8  add     r9, rdx
0x1800392eb  lea     rdx, [rbp+150h+var_12E]
0x1800392ef  add     rdx, rax
0x1800392f2  cmp     r11, rdx
0x1800392f5  ja      short loc_1800392FC
0x1800392f7  cmp     rdi, r9
0x1800392fa  jnb     short loc_180039350
0x1800392fc  cmp     r10, rdx
0x1800392ff  ja      short loc_180039306
0x180039301  cmp     r8, r9
0x180039304  jnb     short loc_180039350
0x180039306  and     ecx, 1
0x180039309  mov     eax, r15d
0x18003930c  sub     eax, ecx
0x18003930e  add     r12d, ebx
0x180039311  cmp     r12d, eax
0x180039314  jb      short loc_18003930E
0x180039316  sub     eax, [rsp+250h+var_1F8]
0x18003931a  xor     edx, edx; Val
0x18003931c  mov     rcx, r9; void *
0x18003931f  lea     ebx, [rax+1]
0x180039322  and     rbx, 0FFFFFFFFFFFFFFFEh
0x180039326  mov     r8, rbx; Size
0x180039329  call    memset_0
0x18003932e  mov     rdi, [rsp+250h+var_1F0]
0x180039333  xor     eax, eax
0x180039335  movzx   eax, ax
0x180039338  mov     rcx, rbx
0x18003933b  rep stosw
0x18003933e  mov     rcx, [rbp+150h+var_1A8]; void *
0x180039342  xor     edx, edx; Val
0x180039344  shl     rbx, 3
0x180039348  mov     r8, rbx; Size
0x18003934b  call    memset_0
0x180039350  xor     r9d, r9d
0x180039353  mov     edx, [rsp+250h+var_1F8]
0x180039357  mov     edi, 1
0x18003935c  cmp     r12d, r15d
  ... truncated ...
```
