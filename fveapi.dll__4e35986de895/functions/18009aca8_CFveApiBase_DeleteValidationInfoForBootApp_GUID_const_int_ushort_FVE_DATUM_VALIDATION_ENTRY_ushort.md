# CFveApiBase::DeleteValidationInfoForBootApp(_GUID const *,int,ushort,_FVE_DATUM_VALIDATION_ENTRY *,ushort *)

- ea: `0x18009aca8`
- end: `0x18009ba78`
- name: `?DeleteValidationInfoForBootApp@CFveApiBase@@QEAAJPEBU_GUID@@HGPEAU_FVE_DATUM_VALIDATION_ENTRY@@PEAG@Z`
- size: `3536`
- prototype: `__int64 __fastcall(CFveApiBase *__hidden this, const struct _GUID *, int, unsigned __int16, struct _FVE_DATUM_VALIDATION_ENTRY *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x18005019c`
- `0x18009d858`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x18001b260`
- `0x18001d0a0`
- `0x180044da4`
- `0x1800476f0`
- `0x180071210`
- `0x18009aca8`
- `0x18009bc80`
- `0x18009f384`
- `0x18011efc2`
- `0x18011f010`

## import_xrefs

- `bcd!BcdQueryObject` at `0x18009afe7`
- `bcd!BcdQueryObject` at `0x18009afe7`
- `bcd!BcdCloseObject` at `0x18009b9ba`
- `bcd!BcdCloseObject` at `0x18009b9d3`
- `bcd!BcdCloseObject` at `0x18009b9ec`
- `bcd!BcdCloseObject` at `0x180124773`
- `bcd!BcdCloseObject` at `0x18012478c`
- `bcd!BcdCloseObject` at `0x1801247a5`
- `bcd!BcdCloseObject` at `0x18009b9ba`
- `bcd!BcdCloseObject` at `0x18009b9d3`
- `bcd!BcdCloseObject` at `0x18009b9ec`
- `bcd!BcdCloseObject` at `0x180124773`
- `bcd!BcdCloseObject` at `0x18012478c`
- `bcd!BcdCloseObject` at `0x1801247a5`
- `bcd!BcdGetElementData` at `0x18009b051`
- `bcd!BcdGetElementData` at `0x18009b051`
- `bcd!BcdOpenObject` at `0x18009aea2`
- `bcd!BcdOpenObject` at `0x18009b0b7`
- `bcd!BcdOpenObject` at `0x18009b272`
- `bcd!BcdOpenObject` at `0x18009aea2`
- `bcd!BcdOpenObject` at `0x18009b0b7`
- `bcd!BcdOpenObject` at `0x18009b272`
- `bcd!BcdCloseStore` at `0x18009ba00`
- `bcd!BcdCloseStore` at `0x1801247b9`
- `bcd!BcdCloseStore` at `0x18009ba00`
- `bcd!BcdCloseStore` at `0x1801247b9`
- `bcd!BcdOpenSystemStore` at `0x18009ae51`
- `bcd!BcdOpenSystemStore` at `0x18009ae51`

## pseudocode

```c
__int64 __fastcall CFveApiBase::DeleteValidationInfoForBootApp(
        CFveApiBase *this,
        struct _GUID *a2,
        int a3,
        unsigned __int16 a4,
        struct _FVE_DATUM_VALIDATION_ENTRY *a5,
        unsigned __int16 *a6)
{
  int v8; // r13d
  int First; // eax
  int BcdAppImageHash; // eax
  __int64 v11; // rdx
  int v12; // edi
  PVOID *v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // r9
  int v16; // eax
  int v17; // eax
  int v18; // eax
  unsigned __int16 v19; // r8
  __int64 v20; // rdx
  GUID *v21; // r9
  __int64 v22; // rax
  __int64 v23; // rax
  int v24; // eax
  int v25; // eax
  int ElementData; // eax
  int v27; // eax
  unsigned __int16 v28; // r8
  int v29; // eax
  int v30; // eax
  unsigned __int16 v31; // r8
  int v32; // eax
  PVOID *v33; // rcx
  int DataSegment; // eax
  int v35; // eax
  __int64 v36; // rdx
  __int64 v37; // r9
  __int64 v38; // r8
  unsigned __int16 v39; // r12
  int v40; // eax
  __int64 v41; // r9
  __int64 v42; // rdx
  struct _FVE_DATUM_VALIDATION_ENTRY *v43; // r11
  unsigned __int16 *v44; // r10
  int v45; // r15d
  __int64 v46; // r13
  __int64 v47; // rdx
  int v48; // r9d
  _OWORD *v49; // r9
  __int64 v50; // rcx
  unsigned __int16 v52; // [rsp+34h] [rbp-1C4h] BYREF
  __int16 v53; // [rsp+38h] [rbp-1C0h]
  int v54; // [rsp+3Ch] [rbp-1BCh]
  __int64 v55; // [rsp+40h] [rbp-1B8h] BYREF
  unsigned __int16 v56; // [rsp+48h] [rbp-1B0h]
  int v57; // [rsp+4Ch] [rbp-1ACh]
  int v58; // [rsp+50h] [rbp-1A8h]
  int v59; // [rsp+54h] [rbp-1A4h]
  int v60; // [rsp+58h] [rbp-1A0h]
  __int64 v61; // [rsp+60h] [rbp-198h] BYREF
  void *Buf1; // [rsp+68h] [rbp-190h]
  unsigned __int16 *v63; // [rsp+70h] [rbp-188h]
  struct _FVE_DATUM_VALIDATION_ENTRY *v64; // [rsp+78h] [rbp-180h]
  int v65; // [rsp+80h] [rbp-178h]
  int v66; // [rsp+84h] [rbp-174h]
  __int64 v67; // [rsp+88h] [rbp-170h]
  __int64 v68; // [rsp+90h] [rbp-168h] BYREF
  void *v69; // [rsp+98h] [rbp-160h] BYREF
  void *v70; // [rsp+A0h] [rbp-158h] BYREF
  void *v71; // [rsp+A8h] [rbp-150h] BYREF
  int v72; // [rsp+B0h] [rbp-148h] BYREF
  __int128 v73; // [rsp+B8h] [rbp-140h] BYREF
  GUID v74; // [rsp+C8h] [rbp-130h] BYREF
  GUID v75; // [rsp+D8h] [rbp-120h] BYREF
  _OWORD Buf2[2]; // [rsp+E8h] [rbp-110h] BYREF
  __int64 v77; // [rsp+108h] [rbp-F0h]
  _OWORD v78[2]; // [rsp+110h] [rbp-E8h] BYREF
  __int64 v79; // [rsp+130h] [rbp-C8h]
  _OWORD v80[2]; // [rsp+138h] [rbp-C0h] BYREF
  __int64 v81; // [rsp+158h] [rbp-A0h]
  unsigned __int8 v82[32]; // [rsp+160h] [rbp-98h] BYREF
  unsigned __int8 v83[32]; // [rsp+180h] [rbp-78h] BYREF
  unsigned __int8 v84[32]; // [rsp+1A0h] [rbp-58h] BYREF

  v56 = a4;
  v60 = a3;
  v64 = a5;
  v63 = a6;
  v73 = 0;
  v75 = GUID_WINDOWS_MEMORY_TESTER;
  v74 = 0;
  v72 = 0;
  memset(Buf2, 0, sizeof(Buf2));
  v77 = 0;
  memset(v78, 0, sizeof(v78));
  v79 = 0;
  memset(v80, 0, sizeof(v80));
  v81 = 0;
  v55 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v61 = 0;
  v8 = 0;
  v54 = 0;
  v52 = 0;
  v57 = 0;
  v58 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  First = FveDatasetGetFirst(*((_QWORD *)this + 146), 4, 7, &v61);
  BcdAppImageHash = FromNtStatus(First);
  v12 = BcdAppImageHash;
  if ( BcdAppImageHash < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_172;
    v14 = 64;
LABEL_8:
    v15 = (unsigned int)BcdAppImageHash;
LABEL_9:
    WPP_SF_d(v13[2], v14, &WPP_1559182127783aab3882fe828952d989_Traceguids, v15);
    goto LABEL_171;
  }
  v16 = BcdOpenSystemStore(&v68, v11);
  BcdAppImageHash = FromNtStatus(v16);
  v12 = BcdAppImageHash;
  if ( BcdAppImageHash < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_172;
    v14 = 65;
    goto LABEL_8;
  }
  v17 = BcdOpenObject(v68, a2, &v69);
  v18 = FromNtStatus(v17);
  v12 = v18;
  if ( v18 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_172;
    v20 = 66;
    v21 = a2;
LABEL_18:
    WPP_SF__guid_D(v13[2], v20, &WPP_1559182127783aab3882fe828952d989_Traceguids, v21, v18);
    goto LABEL_171;
  }
  BcdAppImageHash = CFveApiBase::GetBcdAppImageHash(v69, v82, v19);
  v12 = BcdAppImageHash;
  if ( BcdAppImageHash < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_172;
    v14 = 67;
    goto LABEL_8;
  }
  v22 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_CURRENT_BOOT_ENTRY.Data1 )
    v22 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_CURRENT_BOOT_ENTRY.Data4;
  if ( !v22 )
    goto LABEL_34;
  v23 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&GUID_DEFAULT_BOOT_ENTRY.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&GUID_DEFAULT_BOOT_ENTRY.Data1 )
    v23 = *(_QWORD *)a2->Data4 - *(_QWORD *)GUID_DEFAULT_BOOT_ENTRY.Data4;
  if ( v23 )
  {
    v74 = *a2;
  }
  else
  {
LABEL_34:
    v25 = BcdQueryObject(v69, 0, 0, &v74);
    BcdAppImageHash = FromNtStatus(v25);
    v12 = BcdAppImageHash;
    if ( BcdAppImageHash < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_172;
      v14 = 68;
      goto LABEL_8;
    }
  }
  v24 = FveDatumValidationInfoDataEntry(0, &v74, 16, Buf2);
  BcdAppImageHash = FromNtStatus(v24);
  v12 = BcdAppImageHash;
  if ( BcdAppImageHash < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_172;
    v14 = 69;
    goto LABEL_8;
  }
  v72 = 16;
  ElementData = BcdGetElementData(v69, 587202563, &v73, &v72);
  BcdAppImageHash = FromNtStatus(ElementData);
  v12 = BcdAppImageHash;
  if ( BcdAppImageHash != -2147023728 )
  {
    if ( BcdAppImageHash < 0 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_172;
      v14 = 70;
      goto LABEL_8;
    }
    v27 = BcdOpenObject(v68, &v73, &v70);
    v18 = FromNtStatus(v27);
    v12 = v18;
    if ( v18 < 0 && v18 != -2147023728 && v18 != -2147024894 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_172;
      v20 = 71;
      v21 = (GUID *)&v73;
      goto LABEL_18;
    }
    if ( v18 >= 0 )
    {
      v12 = CFveApiBase::GetBcdAppImageHash(v70, v83, v28);
      if ( (int)(v12 + 0x80000000) >= 0 && v12 != -2147024894 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_172;
        v14 = 72;
LABEL_55:
        v15 = (unsigned int)v12;
        goto LABEL_9;
      }
      if ( v12 >= 0 )
      {
        v29 = FveDatumValidationInfoDataEntry(0, &v73, 16, v78);
        BcdAppImageHash = FromNtStatus(v29);
        v12 = BcdAppImageHash;
        if ( BcdAppImageHash < 0 )
        {
          v13 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
            goto LABEL_172;
          v14 = 73;
          goto LABEL_8;
        }
        v57 = 1;
        v65 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, &WPP_1559182127783aab3882fe828952d989_Traceguids);
      }
    }
  }
  if ( !v57 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_1559182127783aab3882fe828952d989_Traceguids);
  if ( !v60 )
    goto LABEL_95;
  v30 = BcdOpenObject(v68, &v75, &v71);
  v18 = FromNtStatus(v30);
  v12 = v18;
  if ( v18 >= 0 )
  {
    v12 = CFveApiBase::GetBcdAppImageHash(v71, v84, v31);
    if ( ((v12 + 0x80000000) & 0x80000000) == 0 && v12 != -2147024894 )
    {
      v13 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_172;
      v14 = 77;
      goto LABEL_55;
    }
    if ( v12 >= 0 )
    {
      v32 = FveDatumValidationInfoDataEntry(0, &v75, 16, v80);
      BcdAppImageHash = FromNtStatus(v32);
      v12 = BcdAppImageHash;
      if ( BcdAppImageHash < 0 )
      {
        v13 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_172;
        v14 = 78;
        goto LABEL_8;
      }
      v58 = 1;
      v66 = 1;
      v33 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_91;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, &WPP_1559182127783aab3882fe828952d989_Traceguids);
    }
  }
  else if ( v18 != -2147023728 && v18 != -2147024894 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_172;
    v20 = 76;
    v21 = &v75;
    goto LABEL_18;
  }
  v33 = (PVOID *)WPP_GLOBAL_Control;
LABEL_91:
  if ( !v58 && v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 8) != 0 )
    WPP_SF_(v33[2], 80, &WPP_1559182127783aab3882fe828952d989_Traceguids);
LABEL_95:
  DataSegment = FveDatumGetDataSegment(v61, &v55, &v52);
  v35 = FromNtStatus(DataSegment);
  v12 = v35;
  if ( v35 < 0 )
  {
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_172;
    v36 = 81;
    v37 = (unsigned int)v35;
LABEL_170:
    WPP_SF_d(v13[2], v36, &WPP_1559182127783aab3882fe828952d989_Traceguids, v37);
    goto LABEL_171;
  }
  v38 = v55;
  if ( !v55 )
  {
    v12 = -2147024883;
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_172;
    v36 = (unsigned int)(v55 + 82);
    v37 = 2147942413LL;
    goto LABEL_170;
  }
  v11 = (v52 * (unsigned __int128)0xCCCCCCCCCCCCCCCDuLL) >> 64;
  v39 = v52 / 0x28u;
  v52 = v39;
  if ( v39 > v56 )
  {
    v12 = -2147024883;
    v13 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_172;
    v40 = v56;
    v41 = v39;
    v42 = 83;
LABEL_107:
    WPP_SF_DDD(v13[2], v42, &WPP_1559182127783aab3882fe828952d989_Traceguids, v41, v40, -2147024883);
LABEL_171:
    v13 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_172;
  }
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_1559182127783aab3882fe828952d989_Traceguids, v39);
    v13 = (PVOID *)WPP_GLOBAL_Control;
    v38 = v55;
  }
  while ( 2 )
  {
    v43 = v64;
    v44 = v63;
    while ( 1 )
    {
      if ( (unsigned __int16)v8 >= v39 )
      {
        if ( *v44 >= v39 )
        {
          if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 8) == 0 )
            goto LABEL_172;
          v36 = 95;
        }
        else
        {
          if ( v13 == &WPP_GLOBAL_Control || (*((_BYTE *)v13 + 28) & 8) == 0 )
            goto LABEL_172;
          v36 = 94;
        }
        v37 = *v44;
        goto LABEL_170;
      }
      v11 = 5LL * (unsigned __int16)v8;
      v67 = v11;
      if ( *(_WORD *)(v38 + 40LL * (unsigned __int16)v8) == 4 )
        break;
      v49 = (_OWORD *)(v38 + 8 * (v11 + 1));
LABEL_161:
      *((_WORD *)v43 + 20 * *v44) = *(_WORD *)(v38 + 8 * v11);
      *((_WORD *)v43 + 20 * *v44 + 1) = *(_WORD *)(v38 + 8 * v11 + 2);
      *((_DWORD *)v43 + 10 * *v44 + 1) = *(_DWORD *)(v38 + 8 * v11 + 4);
      v50 = 5LL * *v44;
      *(_OWORD *)((char *)v43 + 8 * v50 + 8) = *v49;
      *(_OWORD *)((char *)v43 + 8 * v50 + 24) = v49[1];
      LOWORD(v8) = v8 + 1;
      v54 = v8;
      v53 = v8;
      ++*v44;
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    v45 = 0;
    v59 = 0;
    v46 = (unsigned int)(unsigned __int16)v8 + 1;
    v40 = v39;
    v60 = v39;
    if ( (unsigned int)v46 >= v39 )
    {
      v12 = -2147024883;
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
      {
        v42 = 85;
        v41 = (unsigned int)v46;
        goto LABEL_107;
      }
      goto LABEL_172;
    }
    Buf1 = (void *)(v38 + 8 * (v11 + 1));
    if ( !memcmp_0(Buf1, (char *)Buf2 + 8, 0x20u) )
    {
      if ( memcmp_0((const void *)(v55 + 8 + 40 * v46), v82, 0x20u)
        && v13 != &WPP_GLOBAL_Control
        && (*((_BYTE *)v13 + 28) & 4) != 0 )
      {
        WPP_SF_(v13[2], 86, &WPP_1559182127783aab3882fe828952d989_Traceguids);
        v13 = (PVOID *)WPP_GLOBAL_Control;
      }
      v11 = 1;
      v45 = 1;
      v59 = 1;
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      {
        v47 = 87;
LABEL_135:
        WPP_SF_(v13[2], v47, &WPP_1559182127783aab3882fe828952d989_Traceguids);
        v13 = (PVOID *)WPP_GLOBAL_Control;
        v11 = 1;
      }
    }
    else if ( v57 && !memcmp_0(Buf1, (char *)v78 + 8, 0x20u) )
    {
      if ( memcmp_0((const void *)(v55 + 8 + 40 * v46), v83, 0x20u)
        && v13 != &WPP_GLOBAL_Control
        && (*((_BYTE *)v13 + 28) & 4) != 0 )
      {
        WPP_SF_(v13[2], 88, &WPP_1559182127783aab3882fe828952d989_Traceguids);
        v13 = (PVOID *)WPP_GLOBAL_Control;
      }
      v11 = 1;
      v45 = 1;
      v59 = 1;
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      {
        v47 = 89;
        goto LABEL_135;
      }
    }
    else if ( v58 && !memcmp_0(Buf1, (char *)v80 + 8, 0x20u) )
    {
      if ( memcmp_0((const void *)(v55 + 8 + 40 * v46), v84, 0x20u)
        && v13 != &WPP_GLOBAL_Control
        && (*((_BYTE *)v13 + 28) & 4) != 0 )
      {
        WPP_SF_(v13[2], 90, &WPP_1559182127783aab3882fe828952d989_Traceguids);
        v13 = (PVOID *)WPP_GLOBAL_Control;
      }
      v11 = 1;
      v45 = 1;
      v59 = 1;
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      {
        v47 = 91;
        goto LABEL_135;
      }
    }
    else
    {
      v11 = 1;
    }
    v8 = v54;
    if ( !v45 )
    {
      v38 = v55;
      v11 = v67;
      v49 = Buf1;
      v44 = v63;
      v43 = v64;
      goto LABEL_161;
    }
    LOWORD(v8) = v54 + 2;
    v54 = v8;
    v53 = v8;
    if ( (unsigned __int16)v8 < v39 )
    {
      v48 = (unsigned __int16)v8;
      v38 = v55;
      while ( *(_WORD *)(v55 + 40LL * (unsigned __int16)v8) == 2 && (unsigned __int16)v8 < v39 )
      {
        LOWORD(v8) = v8 + 1;
        v54 = v8;
        v53 = v8;
      }
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      {
        WPP_SF_d(v13[2], 93, &WPP_1559182127783aab3882fe828952d989_Traceguids, (unsigned int)(unsigned __int16)v8 - v48);
        v13 = (PVOID *)WPP_GLOBAL_Control;
        v38 = v55;
      }
      continue;
    }
    break;
  }
  v12 = -2147024883;
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
  {
    v41 = (unsigned __int16)v8;
    v42 = 92;
    v40 = v60;
    goto LABEL_107;
  }
LABEL_172:
  if ( v68 )
  {
    if ( v69 )
      BcdCloseObject(v69);
    if ( v70 )
      BcdCloseObject(v70);
    if ( v71 )
      BcdCloseObject(v71);
    BcdCloseStore(v68, v11);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v61 )
  {
    FveDatumFree(v61);
    v13 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x20) != 0 )
    WPP_SF_d(v13[2], 96, &WPP_1559182127783aab3882fe828952d989_Traceguids, (unsigned int)v12);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18009aca8  mov     r11, rsp
0x18009acab  mov     [r11+18h], rbx
0x18009acaf  mov     [r11+20h], rsi
0x18009acb3  push    rdi
0x18009acb4  push    r12
0x18009acb6  push    r13
0x18009acb8  push    r14
0x18009acba  push    r15
0x18009acbc  sub     rsp, 1D0h
0x18009acc3  mov     rax, cs:__security_cookie
0x18009acca  xor     rax, rsp
0x18009accd  mov     [rsp+1F8h+var_38], rax
0x18009acd5  mov     [rsp+1F8h+var_1B0], r9w
0x18009acdb  mov     [rsp+1F8h+var_1A0], r8d
0x18009ace0  mov     r14, rdx
0x18009ace3  mov     rbx, rcx
0x18009ace6  mov     rax, [rsp+1F8h+arg_20]
0x18009acee  mov     [rsp+1F8h+var_180], rax
0x18009acf3  mov     rax, [rsp+1F8h+arg_28]
0x18009acfb  mov     [rsp+1F8h+var_188], rax
0x18009ad00  xorps   xmm0, xmm0
0x18009ad03  movups  [rsp+1F8h+var_140], xmm0
0x18009ad0b  movups  xmm1, xmmword ptr cs:GUID_WINDOWS_MEMORY_TESTER.Data1
0x18009ad12  movdqu  [rsp+1F8h+var_120], xmm1
0x18009ad1b  movups  [rsp+1F8h+var_130], xmm0
0x18009ad23  xor     r15d, r15d
0x18009ad26  mov     [r11-148h], r15d
0x18009ad2d  xor     eax, eax
0x18009ad2f  movups  [rsp+1F8h+Buf2], xmm0
0x18009ad37  movups  [rsp+1F8h+var_100], xmm0
0x18009ad3f  mov     [r11-0F0h], rax
0x18009ad46  xorps   xmm1, xmm1
0x18009ad49  movups  [rsp+1F8h+var_E8], xmm1
0x18009ad51  movups  [rsp+1F8h+var_D8], xmm1
0x18009ad59  mov     [r11-0C8h], rax
0x18009ad60  movups  [rsp+1F8h+var_C0], xmm0
0x18009ad68  movups  [rsp+1F8h+var_B0], xmm0
0x18009ad70  mov     [r11-0A0h], rax
0x18009ad77  mov     [rsp+1F8h+var_1B8], r15
0x18009ad7c  mov     [r11-168h], r15
0x18009ad83  mov     [r11-160h], r15
0x18009ad8a  mov     [r11-158h], r15
0x18009ad91  mov     [r11-150h], r15
0x18009ad98  mov     [rsp+1F8h+var_198], r15
0x18009ad9d  mov     r13d, r15d
0x18009ada0  mov     [rsp+1F8h+var_1BC], r15d
0x18009ada5  mov     [rsp+1F8h+var_1C4], ax
0x18009adaa  mov     [rsp+1F8h+var_1AC], r15d
0x18009adaf  mov     [rsp+1F8h+var_1A8], r15d
0x18009adb4  lea     r12, WPP_GLOBAL_Control
0x18009adbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18009adc2  lea     rsi, WPP_1559182127783aab3882fe828952d989_Traceguids
0x18009adc9  cmp     rcx, r12
0x18009adcc  jz      short loc_18009ADE4
0x18009adce  test    byte ptr [rcx+1Ch], 20h
0x18009add2  jz      short loc_18009ADE4
0x18009add4  lea     edx, [rax+3Fh]
0x18009add7  mov     r8, rsi
0x18009adda  mov     rcx, [rcx+10h]
0x18009adde  call    WPP_SF_
0x18009ade3  nop
0x18009ade4  mov     edx, 4
0x18009ade9  lea     r8d, [rdx+3]
0x18009aded  lea     r9, [rsp+1F8h+var_198]
0x18009adf2  mov     rcx, [rbx+490h]
0x18009adf9  call    FveDatasetGetFirst
0x18009adfe  mov     ecx, eax; int
0x18009ae00  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009ae05  mov     edi, eax
0x18009ae07  mov     [rsp+1F8h+var_1C8], eax
0x18009ae0b  test    eax, eax
0x18009ae0d  jns     short loc_18009AE49
0x18009ae0f  mov     rbx, cs:WPP_GLOBAL_Control
0x18009ae16  cmp     rbx, r12
0x18009ae19  jz      loc_18009B378
0x18009ae1f  test    byte ptr [rbx+1Ch], 2
0x18009ae23  jz      loc_18009B378
0x18009ae29  mov     edx, 40h ; '@'
0x18009ae2e  mov     r9d, eax
0x18009ae31  mov     r8, rsi
0x18009ae34  mov     rcx, [rbx+10h]
0x18009ae38  call    WPP_SF_d
0x18009ae3d  lea     r15, WPP_GLOBAL_Control
0x18009ae44  jmp     loc_18009B99B
0x18009ae49  lea     rcx, [rsp+1F8h+var_168]
0x18009ae51  call    cs:__imp_BcdOpenSystemStore
0x18009ae58  nop     dword ptr [rax+rax+00h]
0x18009ae5d  mov     ecx, eax; int
0x18009ae5f  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009ae64  mov     edi, eax
0x18009ae66  mov     [rsp+1F8h+var_1C8], eax
0x18009ae6a  test    eax, eax
0x18009ae6c  jns     short loc_18009AE8F
0x18009ae6e  mov     rbx, cs:WPP_GLOBAL_Control
0x18009ae75  cmp     rbx, r12
0x18009ae78  jz      loc_18009B378
0x18009ae7e  test    byte ptr [rbx+1Ch], 2
0x18009ae82  jz      loc_18009B378
0x18009ae88  mov     edx, 41h ; 'A'
0x18009ae8d  jmp     short loc_18009AE2E
0x18009ae8f  lea     r8, [rsp+1F8h+var_160]
0x18009ae97  mov     rdx, r14
0x18009ae9a  mov     rcx, [rsp+1F8h+var_168]
0x18009aea2  call    cs:__imp_BcdOpenObject
0x18009aea9  nop     dword ptr [rax+rax+00h]
0x18009aeae  mov     ecx, eax; int
0x18009aeb0  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009aeb5  mov     edi, eax
0x18009aeb7  mov     [rsp+1F8h+var_1C8], eax
0x18009aebb  test    eax, eax
0x18009aebd  jns     short loc_18009AEF6
0x18009aebf  mov     rbx, cs:WPP_GLOBAL_Control
0x18009aec6  cmp     rbx, r12
0x18009aec9  jz      loc_18009B378
0x18009aecf  test    byte ptr [rbx+1Ch], 2
0x18009aed3  jz      loc_18009B378
0x18009aed9  mov     edx, 42h ; 'B'
0x18009aede  mov     r9, r14
0x18009aee1  mov     [rsp+1F8h+var_1D8], eax
0x18009aee5  mov     r8, rsi
0x18009aee8  mov     rcx, [rbx+10h]
0x18009aeec  call    WPP_SF__guid_D
0x18009aef1  jmp     loc_18009AE3D
0x18009aef6  lea     rdx, [rsp+1F8h+var_98]; unsigned __int8 *
0x18009aefe  mov     rcx, [rsp+1F8h+var_160]; void *
0x18009af06  call    ?GetBcdAppImageHash@CFveApiBase@@SAJPEAXPEAEG@Z; CFveApiBase::GetBcdAppImageHash(void *,uchar *,ushort)
0x18009af0b  mov     edi, eax
0x18009af0d  mov     [rsp+1F8h+var_1C8], eax
0x18009af11  test    eax, eax
0x18009af13  jns     short loc_18009AF39
0x18009af15  mov     rbx, cs:WPP_GLOBAL_Control
0x18009af1c  cmp     rbx, r12
0x18009af1f  jz      loc_18009B378
0x18009af25  test    byte ptr [rbx+1Ch], 2
0x18009af29  jz      loc_18009B378
0x18009af2f  mov     edx, 43h ; 'C'
0x18009af34  jmp     loc_18009AE2E
0x18009af39  mov     rax, [r14]
0x18009af3c  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data1
0x18009af43  jnz     short loc_18009AF50
0x18009af45  mov     rax, [r14+8]
0x18009af49  sub     rax, qword ptr cs:GUID_CURRENT_BOOT_ENTRY.Data4
0x18009af50  test    rax, rax
0x18009af53  jz      short loc_18009AFD2
0x18009af55  mov     rax, [r14]
0x18009af58  sub     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data1
0x18009af5f  jnz     short loc_18009AF6C
0x18009af61  mov     rax, [r14+8]
0x18009af65  sub     rax, qword ptr cs:GUID_DEFAULT_BOOT_ENTRY.Data4
0x18009af6c  test    rax, rax
0x18009af6f  jz      short loc_18009AFD2
0x18009af71  movups  xmm0, xmmword ptr [r14]
0x18009af75  movdqu  [rsp+1F8h+var_130], xmm0
0x18009af7e  lea     r9, [rsp+1F8h+Buf2]
0x18009af86  mov     r14d, 10h
0x18009af8c  mov     r8d, r14d
0x18009af8f  lea     rdx, [rsp+1F8h+var_130]
0x18009af97  xor     ecx, ecx
0x18009af99  call    FveDatumValidationInfoDataEntry
0x18009af9e  mov     ecx, eax; int
0x18009afa0  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009afa5  mov     edi, eax
0x18009afa7  mov     [rsp+1F8h+var_1C8], eax
0x18009afab  test    eax, eax
0x18009afad  jns     short loc_18009B02C
0x18009afaf  mov     rbx, cs:WPP_GLOBAL_Control
0x18009afb6  cmp     rbx, r12
0x18009afb9  jz      loc_18009B378
0x18009afbf  test    byte ptr [rbx+1Ch], 2
0x18009afc3  jz      loc_18009B378
0x18009afc9  lea     edx, [r14+35h]
0x18009afcd  jmp     loc_18009AE2E
0x18009afd2  lea     r9, [rsp+1F8h+var_130]
0x18009afda  xor     r8d, r8d
0x18009afdd  xor     edx, edx
0x18009afdf  mov     rcx, [rsp+1F8h+var_160]
0x18009afe7  call    cs:__imp_BcdQueryObject
0x18009afee  nop     dword ptr [rax+rax+00h]
0x18009aff3  mov     ecx, eax; int
0x18009aff5  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009affa  mov     edi, eax
0x18009affc  mov     [rsp+1F8h+var_1C8], eax
0x18009b000  test    eax, eax
0x18009b002  jns     loc_18009AF7E
0x18009b008  mov     rbx, cs:WPP_GLOBAL_Control
0x18009b00f  cmp     rbx, r12
0x18009b012  jz      loc_18009B378
0x18009b018  test    byte ptr [rbx+1Ch], 2
0x18009b01c  jz      loc_18009B378
0x18009b022  mov     edx, 44h ; 'D'
0x18009b027  jmp     loc_18009AE2E
0x18009b02c  mov     [rsp+1F8h+var_148], r14d
0x18009b034  lea     r9, [rsp+1F8h+var_148]
0x18009b03c  lea     r8, [rsp+1F8h+var_140]
0x18009b044  mov     edx, 23000003h
0x18009b049  mov     rcx, [rsp+1F8h+var_160]
0x18009b051  call    cs:__imp_BcdGetElementData
0x18009b058  nop     dword ptr [rax+rax+00h]
0x18009b05d  mov     ecx, eax; int
0x18009b05f  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009b064  mov     edi, eax
0x18009b066  mov     [rsp+1F8h+var_1C8], eax
0x18009b06a  mov     ebx, 80070490h
0x18009b06f  cmp     eax, ebx
0x18009b071  jz      loc_18009B208
0x18009b077  test    eax, eax
0x18009b079  jns     short loc_18009B09F
0x18009b07b  mov     rbx, cs:WPP_GLOBAL_Control
0x18009b082  cmp     rbx, r12
0x18009b085  jz      loc_18009B378
0x18009b08b  test    byte ptr [rbx+1Ch], 2
0x18009b08f  jz      loc_18009B378
0x18009b095  mov     edx, 46h ; 'F'
0x18009b09a  jmp     loc_18009AE2E
0x18009b09f  lea     r8, [rsp+1F8h+var_158]
0x18009b0a7  lea     rdx, [rsp+1F8h+var_140]
0x18009b0af  mov     rcx, [rsp+1F8h+var_168]
0x18009b0b7  call    cs:__imp_BcdOpenObject
0x18009b0be  nop     dword ptr [rax+rax+00h]
0x18009b0c3  mov     ecx, eax; int
0x18009b0c5  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009b0ca  mov     edi, eax
0x18009b0cc  mov     [rsp+1F8h+var_1C8], eax
0x18009b0d0  test    eax, eax
0x18009b0d2  jns     short loc_18009B10D
0x18009b0d4  cmp     eax, ebx
0x18009b0d6  jz      short loc_18009B10D
0x18009b0d8  mov     ebx, 80070002h
0x18009b0dd  cmp     eax, ebx
0x18009b0df  jz      short loc_18009B112
0x18009b0e1  mov     rbx, cs:WPP_GLOBAL_Control
0x18009b0e8  cmp     rbx, r12
0x18009b0eb  jz      loc_18009B378
0x18009b0f1  test    byte ptr [rbx+1Ch], 2
0x18009b0f5  jz      loc_18009B378
0x18009b0fb  mov     edx, 47h ; 'G'
0x18009b100  lea     r9, [rsp+1F8h+var_140]
0x18009b108  jmp     loc_18009AEE1
0x18009b10d  mov     ebx, 80070002h
0x18009b112  test    eax, eax
0x18009b114  js      loc_18009B20D
0x18009b11a  lea     rdx, [rsp+1F8h+var_78]; unsigned __int8 *
0x18009b122  mov     rcx, [rsp+1F8h+var_158]; void *
0x18009b12a  call    ?GetBcdAppImageHash@CFveApiBase@@SAJPEAXPEAEG@Z; CFveApiBase::GetBcdAppImageHash(void *,uchar *,ushort)
0x18009b12f  mov     edi, eax
0x18009b131  mov     [rsp+1F8h+var_1C8], eax
0x18009b135  mov     r15d, 80000000h
0x18009b13b  add     eax, r15d
0x18009b13e  test    r15d, eax
0x18009b141  jnz     short loc_18009B16E
0x18009b143  cmp     edi, ebx
0x18009b145  jz      short loc_18009B16E
0x18009b147  mov     rbx, cs:WPP_GLOBAL_Control
0x18009b14e  cmp     rbx, r12
0x18009b151  jz      loc_18009B378
0x18009b157  test    byte ptr [rbx+1Ch], 2
0x18009b15b  jz      loc_18009B378
0x18009b161  mov     edx, 48h ; 'H'
0x18009b166  mov     r9d, edi
0x18009b169  jmp     loc_18009AE31
0x18009b16e  test    edi, edi
0x18009b170  js      loc_18009B213
0x18009b176  lea     r9, [rsp+1F8h+var_E8]
0x18009b17e  mov     r8d, r14d
0x18009b181  lea     rdx, [rsp+1F8h+var_140]
0x18009b189  xor     ecx, ecx
0x18009b18b  call    FveDatumValidationInfoDataEntry
0x18009b190  mov     ecx, eax; int
0x18009b192  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x18009b197  mov     edi, eax
0x18009b199  mov     [rsp+1F8h+var_1C8], eax
0x18009b19d  test    eax, eax
0x18009b19f  jns     short loc_18009B1C5
0x18009b1a1  mov     rbx, cs:WPP_GLOBAL_Control
0x18009b1a8  cmp     rbx, r12
0x18009b1ab  jz      loc_18009B378
0x18009b1b1  test    byte ptr [rbx+1Ch], 2
0x18009b1b5  jz      loc_18009B378
0x18009b1bb  mov     edx, 49h ; 'I'
0x18009b1c0  jmp     loc_18009AE2E
0x18009b1c5  mov     r12d, 1
0x18009b1cb  mov     ecx, r12d
0x18009b1ce  mov     [rsp+1F8h+var_1AC], ecx
0x18009b1d2  mov     [rsp+1F8h+var_178], ecx
0x18009b1d9  mov     rcx, cs:WPP_GLOBAL_Control
0x18009b1e0  lea     rax, WPP_GLOBAL_Control
0x18009b1e7  mov     r14b, 8
0x18009b1ea  cmp     rcx, rax
0x18009b1ed  jz      short loc_18009B223
0x18009b1ef  test    [rcx+1Ch], r14b
0x18009b1f3  jz      short loc_18009B223
0x18009b1f5  lea     edx, [r12+49h]
0x18009b1fa  mov     r8, rsi
0x18009b1fd  mov     rcx, [rcx+10h]
0x18009b201  call    WPP_SF_
0x18009b206  jmp     short loc_18009B21C
0x18009b208  mov     ebx, 80070002h
0x18009b20d  mov     r15d, 80000000h
0x18009b213  mov     r12d, 1
0x18009b219  mov     r14b, 8
  ... truncated ...
```
