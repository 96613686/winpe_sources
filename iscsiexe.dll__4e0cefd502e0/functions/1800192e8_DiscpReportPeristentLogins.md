# DiscpReportPeristentLogins

- ea: `0x1800192e8`
- end: `0x18001a48e`
- name: `DiscpReportPeristentLogins`
- size: `4518`
- prototype: `__int64 __fastcall(_DWORD *, char *, unsigned int *, unsigned int, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180009e30`
- `0x18000b444`

## callees

- `0x180001cfe`
- `0x180018e80`
- `0x1800192e8`
- `0x18001d38c`

## import_xrefs

- `ISCSIUM!DiscpCopyString` at `0x1800195ec`
- `ISCSIUM!DiscpCopyString` at `0x1800196ca`
- `ISCSIUM!DiscpCopyString` at `0x1800195ec`
- `ISCSIUM!DiscpCopyString` at `0x1800196ca`
- `ISCSIUM!DiscpFreeMemory` at `0x18001a437`
- `ISCSIUM!DiscpFreeMemory` at `0x18001a445`
- `ISCSIUM!DiscpFreeMemory` at `0x18001a453`
- `ISCSIUM!DiscpFreeMemory` at `0x18001a461`
- `ISCSIUM!DiscpFreeMemory` at `0x18001a437`
- `ISCSIUM!DiscpFreeMemory` at `0x18001a445`
- `ISCSIUM!DiscpFreeMemory` at `0x18001a453`
- `ISCSIUM!DiscpFreeMemory` at `0x18001a461`
- `ISCSIUM!DiscpParseAllData` at `0x180019435`
- `ISCSIUM!DiscpParseAllData` at `0x180019435`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x180019636`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x180019d44`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x180019636`
- `ISCSIUM!DiscpGetStringFromDataBlock` at `0x180019d44`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001953b`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019704`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001981f`
- `ISCSIUM!DiscpPadDataBlock` at `0x1800198b9`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001998d`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019a29`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019c21`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019caa`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019db9`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001953b`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019704`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001981f`
- `ISCSIUM!DiscpPadDataBlock` at `0x1800198b9`
- `ISCSIUM!DiscpPadDataBlock` at `0x18001998d`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019a29`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019c21`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019caa`
- `ISCSIUM!DiscpPadDataBlock` at `0x180019db9`
- `ISCSIUM!DiscpQueryAllData` at `0x1800193ec`
- `ISCSIUM!DiscpQueryAllData` at `0x1800193ec`

## pseudocode

```c
__int64 __fastcall DiscpReportPeristentLogins(
        _DWORD *a1,
        char *a2,
        unsigned int *a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6)
{
  char v7; // si
  __int64 v8; // r15
  char *v9; // r14
  unsigned int v10; // eax
  unsigned int StringFromDataBlock; // edi
  int v12; // edx
  int v13; // r9d
  int v14; // r10d
  int v15; // r11d
  unsigned int i; // r8d
  __int64 v17; // r12
  unsigned int *v18; // rcx
  unsigned int v19; // eax
  unsigned int j; // r13d
  unsigned __int16 *v21; // rcx
  __int64 v22; // r9
  int v23; // r9d
  __int64 v24; // rdx
  unsigned int *v25; // rcx
  unsigned int v26; // eax
  unsigned int v27; // edx
  unsigned int *v28; // rcx
  unsigned int v29; // eax
  size_t v30; // r12
  unsigned int *v31; // rcx
  unsigned int v32; // eax
  char v33; // dl
  __int16 v34; // dx
  unsigned int v35; // ecx
  _WORD *v36; // rax
  unsigned int v37; // ecx
  __int16 v38; // dx
  unsigned int v39; // edx
  int *v40; // rcx
  unsigned int v41; // eax
  int v42; // edx
  unsigned int *v43; // rcx
  unsigned int v44; // eax
  unsigned int v45; // edx
  unsigned int *v46; // rcx
  unsigned int v47; // eax
  unsigned int v48; // edx
  unsigned int *v49; // rcx
  unsigned int v50; // eax
  unsigned int v51; // edx
  unsigned int *v52; // rcx
  unsigned int v53; // eax
  unsigned int v54; // edx
  unsigned int *v55; // rcx
  unsigned int v56; // eax
  unsigned int v57; // edx
  unsigned int *v58; // rcx
  unsigned int v59; // eax
  unsigned int v60; // edx
  unsigned int v61; // r15d
  _DWORD *v62; // rax
  unsigned int v63; // ecx
  int v64; // r14d
  unsigned int *v65; // rax
  unsigned int v66; // ecx
  unsigned int v67; // esi
  unsigned int *v68; // rdx
  unsigned int v69; // ecx
  char *v70; // rax
  char *v71; // r11
  unsigned int v72; // r8d
  unsigned int *v73; // r9
  char *v74; // r15
  unsigned int v75; // r14d
  __int64 v76; // r15
  unsigned int v77; // esi
  unsigned int v78; // eax
  char v80; // [rsp+40h] [rbp-158h]
  int v81; // [rsp+44h] [rbp-154h]
  int v82; // [rsp+48h] [rbp-150h]
  int v83; // [rsp+4Ch] [rbp-14Ch]
  int v84; // [rsp+50h] [rbp-148h]
  unsigned int *v85; // [rsp+58h] [rbp-140h] BYREF
  int v86; // [rsp+60h] [rbp-138h]
  __int64 v87; // [rsp+68h] [rbp-130h]
  char *v88; // [rsp+70h] [rbp-128h]
  __int64 v89; // [rsp+78h] [rbp-120h]
  int v90; // [rsp+80h] [rbp-118h] BYREF
  unsigned int v91; // [rsp+84h] [rbp-114h] BYREF
  int v92; // [rsp+88h] [rbp-110h]
  int v93; // [rsp+8Ch] [rbp-10Ch]
  unsigned int v94; // [rsp+90h] [rbp-108h]
  unsigned int v95; // [rsp+94h] [rbp-104h] BYREF
  unsigned int v96; // [rsp+98h] [rbp-100h] BYREF
  int v97; // [rsp+9Ch] [rbp-FCh] BYREF
  unsigned int v98; // [rsp+A0h] [rbp-F8h]
  unsigned int v99; // [rsp+A4h] [rbp-F4h]
  __int64 v100; // [rsp+A8h] [rbp-F0h] BYREF
  char *v101; // [rsp+B0h] [rbp-E8h] BYREF
  unsigned __int16 *v102; // [rsp+B8h] [rbp-E0h] BYREF
  char *v103; // [rsp+C0h] [rbp-D8h]
  char *v104; // [rsp+C8h] [rbp-D0h]
  __int64 v105; // [rsp+D0h] [rbp-C8h] BYREF
  int v106; // [rsp+D8h] [rbp-C0h]
  int v107; // [rsp+DCh] [rbp-BCh]
  int v108; // [rsp+E0h] [rbp-B8h]
  void *v109; // [rsp+E8h] [rbp-B0h]
  __int64 v110; // [rsp+F0h] [rbp-A8h] BYREF
  __int64 v111; // [rsp+F8h] [rbp-A0h] BYREF
  __int64 v112; // [rsp+100h] [rbp-98h] BYREF
  __int64 v113; // [rsp+108h] [rbp-90h] BYREF
  char *v114; // [rsp+110h] [rbp-88h]
  char *v115; // [rsp+118h] [rbp-80h]
  char *v116; // [rsp+120h] [rbp-78h]
  char v117[8]; // [rsp+128h] [rbp-70h] BYREF
  char *v118; // [rsp+130h] [rbp-68h] BYREF
  unsigned int *v119; // [rsp+138h] [rbp-60h]
  char *v120; // [rsp+140h] [rbp-58h]
  __int64 v121; // [rsp+148h] [rbp-50h]
  __int64 v122; // [rsp+150h] [rbp-48h]

  v7 = 0;
  v80 = 0;
  v112 = 0;
  v95 = 0;
  v105 = 0;
  v111 = 0;
  v110 = 0;
  v85 = 0;
  a6 = 0;
  v102 = 0;
  v121 = 0;
  v101 = 0;
  v90 = 0;
  v97 = 0;
  v100 = 0;
  v91 = 0;
  v113 = 0;
  v109 = 0;
  v116 = 0;
  v8 = 0;
  v89 = 0;
  v122 = 0;
  v9 = 0;
  v88 = 0;
  v103 = 0;
  v114 = 0;
  v104 = 0;
  v115 = 0;
  v96 = 0;
  if ( a2 )
    v99 = *a3;
  else
    v99 = 0;
  *a1 = 0;
  *a3 = 0;
  v10 = DiscpQueryAllData(MSiSCSI_PersistentLogins_GUID, 0, &v112, &v95);
  StringFromDataBlock = v10;
  if ( v10 )
  {
    if ( v10 - 4200 <= 1 )
      return (unsigned int)-268500924;
    return StringFromDataBlock;
  }
  StringFromDataBlock = DiscpParseAllData(v112, v95, &v96, &v110, &v105, &v111);
  if ( StringFromDataBlock )
    goto LABEL_160;
  v120 = a2;
  v92 = 0;
  v93 = 0;
  v98 = 0;
  v12 = 0;
  v81 = 0;
  v13 = 0;
  v84 = 0;
  v14 = 0;
  v82 = 0;
  v15 = 0;
  v83 = 0;
  while ( 2 )
  {
    for ( i = 0; ; ++i )
    {
      v94 = i;
      v108 = v13;
      v107 = v12;
      if ( i >= v96 )
        break;
      StringFromDataBlock = 0;
      v17 = i;
      v87 = i;
      v18 = *(unsigned int **)(v105 + 8LL * i);
      v119 = v18;
      v85 = v18;
      v19 = *(_DWORD *)(v111 + 4LL * i);
      a6 = v19;
      if ( !v18 )
        continue;
      if ( v19 < 8 )
      {
        StringFromDataBlock = 87;
LABEL_151:
        *(_QWORD *)(v105 + 8 * v17) = 0;
        continue;
      }
      a6 = v19 - 8;
      v85 = v18 + 2;
      if ( !v7 )
      {
        v92 = 0;
        v93 = 0;
      }
      for ( j = 0; j < *v18; ++j )
      {
        StringFromDataBlock = DiscpPadDataBlock(8, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          goto LABEL_150;
        }
        if ( v7 )
        {
          v21 = *(unsigned __int16 **)(v110 + 8 * v17);
          v102 = v21;
          v22 = *v21;
          v102 = v21 + 1;
          if ( (unsigned int)v22 > 0x100 )
            v22 = 256;
          if ( v21 == (unsigned __int16 *)-2LL )
          {
            *((_WORD *)v9 + 225) = 0;
          }
          else
          {
            v101 = v9 + 450;
            v102 = v21;
            v90 = 2 * v22 + 2;
            StringFromDataBlock = DiscpCopyString(&v101, &v97, &v102, v22, &v90);
            v86 = StringFromDataBlock;
          }
        }
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          goto LABEL_150;
        }
        StringFromDataBlock = DiscpGetStringFromDataBlock(&v100, &v91, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( !StringFromDataBlock && v7 )
        {
          v23 = v91;
          if ( v91 > 0xDF )
          {
            v23 = 223;
            v91 = 223;
          }
          if ( v100 )
          {
            v101 = v9;
            v100 -= 2;
            v90 = 2 * v23 + 2;
            StringFromDataBlock = DiscpCopyString(&v101, &v97, &v100, (unsigned int)(v23 + 1), &v90);
            v86 = StringFromDataBlock;
          }
        }
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          goto LABEL_150;
        }
        StringFromDataBlock = DiscpPadDataBlock(8, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          goto LABEL_150;
        }
        StringFromDataBlock = -268500967;
        v86 = -268500967;
        if ( a6 < 8 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          goto LABEL_150;
        }
        v24 = *(_QWORD *)v85;
        v25 = v85 + 2;
        v85 += 2;
        v26 = a6 - 8;
        a6 -= 8;
        if ( v7 )
        {
          *((_QWORD *)v9 + 250) = v24;
          v25 = v85;
          v26 = a6;
        }
        if ( v26 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          goto LABEL_150;
        }
        v27 = *v25;
        v28 = v25 + 1;
        v85 = v28;
        v29 = v26 - 4;
        a6 = v29;
        if ( v7 )
        {
          *((_DWORD *)v9 + 241) = v27;
          v28 = v85;
          v29 = a6;
        }
        if ( v29 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          goto LABEL_150;
        }
        v30 = *v28;
        v31 = v28 + 1;
        v85 = v31;
        v32 = v29 - 4;
        a6 = v32;
        if ( v7 )
        {
          *((_DWORD *)v9 + 513) = v30;
          v31 = v85;
          v32 = a6;
        }
        if ( !v32 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v33 = *(_BYTE *)v31;
        v85 = (unsigned int *)((char *)v31 + 1);
        a6 = v32 - 1;
        if ( v7 )
          v9[448] = v33;
        StringFromDataBlock = DiscpPadDataBlock(2, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        if ( a6 < 2 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v34 = *(_WORD *)v85;
        v85 = (unsigned int *)((char *)v85 + 2);
        a6 -= 2;
        if ( v7 )
        {
          if ( a5 )
          {
            v35 = v98;
            if ( v98 < a4 )
            {
              *(_WORD *)(a5 + 2LL * v98) = v34;
              v98 = v35 + 1;
            }
          }
        }
        StringFromDataBlock = DiscpPadDataBlock(4, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v113 = v8 + 744;
        v118 = v9 + 1480;
        StringFromDataBlock = DiscpGetIPAddrFromDataBlock(
                                (unsigned __int64)&v118 & -(__int64)(v7 != 0),
                                (unsigned __int64)&v113 & -(__int64)(v7 != 0),
                                256,
                                &v85,
                                &a6,
                                v117);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        StringFromDataBlock = DiscpPadDataBlock(4, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        StringFromDataBlock = -268500967;
        v86 = -268500967;
        if ( a6 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v36 = ++v85;
        v37 = a6 - 4;
        a6 = v37;
        if ( v37 < 2 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v38 = *v36;
        v85 = (unsigned int *)(v36 + 1);
        a6 = v37 - 2;
        if ( v7 )
          *((_WORD *)v9 + 996) = v38;
        StringFromDataBlock = DiscpPadDataBlock(4, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        StringFromDataBlock = -268500967;
        v86 = -268500967;
        if ( a6 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v39 = *v85;
        v40 = (int *)++v85;
        v41 = a6 - 4;
        a6 -= 4;
        if ( v7 )
        {
          *((_DWORD *)v9 + 505) = v39;
          v40 = (int *)v85;
          v41 = a6;
        }
        if ( v41 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v42 = *v40;
        v43 = (unsigned int *)(v40 + 1);
        v85 = v43;
        v44 = v41 - 4;
        a6 = v44;
        if ( v7 )
        {
          *((_DWORD *)v9 + 508) = v42;
          v43 = v85;
          v44 = a6;
        }
        if ( v44 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v45 = *v43;
        v46 = v43 + 1;
        v85 = v46;
        v47 = v44 - 4;
        a6 = v47;
        if ( v7 )
        {
          *((_DWORD *)v9 + 509) = v45;
          v46 = v85;
          v47 = a6;
        }
        if ( v47 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v48 = *v46;
        v49 = v46 + 1;
        v85 = v49;
        v50 = v47 - 4;
        a6 = v50;
        if ( v7 )
        {
          *((_DWORD *)v9 + 510) = v48;
          v49 = v85;
          v50 = a6;
        }
        if ( v50 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v51 = *v49;
        v52 = v49 + 1;
        v85 = v52;
        v53 = v50 - 4;
        a6 = v53;
        if ( v7 )
        {
          *((_DWORD *)v9 + 511) = v51;
          v52 = v85;
          v53 = a6;
        }
        if ( v53 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v54 = *v52;
        v55 = v52 + 1;
        v85 = v55;
        v56 = v53 - 4;
        a6 = v56;
        if ( v7 )
        {
          *((_DWORD *)v9 + 512) = v54;
          v55 = v85;
          v56 = a6;
        }
        if ( v56 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v57 = *v55;
        v58 = v55 + 1;
        v85 = v58;
        v59 = v56 - 4;
        a6 = v59;
        if ( v7 )
        {
          *((_DWORD *)v9 + 506) = v57;
          v58 = v85;
          v59 = a6;
        }
        if ( v59 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v60 = *v58;
        v85 = v58 + 1;
        a6 = v59 - 4;
        if ( v7 )
          *((_DWORD *)v9 + 507) = v60;
        StringFromDataBlock = DiscpPadDataBlock(8, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        if ( a6 < 4 )
        {
          v12 = v81;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v61 = *v85;
        v62 = ++v85;
        v63 = a6 - 4;
        a6 = v63;
        if ( v63 < 4 )
        {
          v12 = v81;
          v8 = v89;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v64 = *v62;
        v85 = v62 + 1;
        a6 = v63 - 4;
        StringFromDataBlock = DiscpPadDataBlock(8, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock || a6 < 8 || (v65 = v85 + 2, v85 += 2, v66 = a6 - 8, a6 = v66, v66 < 4) )
        {
          v9 = v88;
          v12 = v81;
          v8 = v89;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v67 = *v65;
        v85 = v65 + 1;
        a6 = v66 - 4;
        StringFromDataBlock = DiscpGetStringFromDataBlock(&v100, &v91, &v85, &a6);
        v86 = StringFromDataBlock;
        if ( StringFromDataBlock )
          goto LABEL_100;
        StringFromDataBlock = -268500967;
        v86 = -268500967;
        if ( !a6
          || (v85 = (unsigned int *)((char *)v85 + 1),
              --a6,
              StringFromDataBlock = DiscpPadDataBlock(8, &v85, &a6),
              (v86 = StringFromDataBlock) != 0)
          || (StringFromDataBlock = -268500967, v86 = -268500967, a6 < 8) )
        {
LABEL_100:
          v7 = v80;
          v9 = v88;
          v12 = v81;
          v8 = v89;
          v13 = v84;
          v14 = v82;
          v15 = v83;
          v17 = v87;
          goto LABEL_150;
        }
        v68 = v85 + 2;
        v85 += 2;
        v69 = a6 - 8;
        a6 -= 8;
        if ( v67 )
        {
          if ( v80 )
          {
            v70 = v103;
            *((_DWORD *)v103 + 374) = v61;
            *((_DWORD *)v70 + 375) = v64;
            *((_DWORD *)v70 + 376) = v67;
            v71 = v104;
            *((_QWORD *)v70 + 189) = v104;
            v9 = v88;
            *((_QWORD *)v88 + 251) = v70;
            v103 = v70 + 1520;
            v114 = v70 + 1520;
            v68 = v85;
            v69 = a6;
          }
          else
          {
            ++v92;
            v93 += v67;
            v9 = v88;
            v71 = v104;
          }
          v72 = 0;
          v106 = 0;
          while ( v72 < v67 )
          {
            v73 = v68;
            StringFromDataBlock = -268500967;
            v86 = -268500967;
            if ( v69 < 0x10 )
            {
              v7 = v80;
              v12 = v81;
              v8 = v89;
              v13 = v84;
              v14 = v82;
              v15 = v83;
              v17 = v87;
              goto LABEL_150;
            }
            v68 += 4;
            v85 = v68;
            v69 -= 16;
            a6 = v69;
            if ( v80 )
            {
              *((_QWORD *)v71 + 1) = *(_QWORD *)v73;
              *(_DWORD *)v71 = v73[2];
              v71 += 16;
              v104 = v71;
              v115 = v71;
              v68 = v85;
              v69 = a6;
            }
            v106 = ++v72;
          }
        }
        if ( (_DWORD)v30 )
        {
          StringFromDataBlock = -268500967;
          v86 = -268500967;
          if ( v69 < (unsigned int)v30 )
            goto LABEL_100;
          v85 = (unsigned int *)((char *)v68 + v30);
          a6 = v69 - v30;
          v7 = v80;
          v9 = v88;
          if ( v80 )
          {
            v74 = (char *)v109;
            *((_QWORD *)v88 + 258) = v109;
            memcpy_0(v74, v68, v30);
            v109 = &v74[v30];
            v116 = &v74[v30];
          }
        }
        else
        {
          v7 = v80;
          v9 = v88;
        }
        v8 = v89;
        if ( v7 )
        {
          v8 = v89 + 1088;
          v89 += 1088;
          v9 += 2080;
          v88 = v9;
        }
        v15 = v83;
        if ( !v7 )
        {
          v15 = v30 + v83;
          v83 += v30;
        }
        v18 = v119;
        v17 = v87;
      }
      v12 = v81;
      v13 = v84;
      v14 = v82;
      if ( !v7 )
      {
        v12 = *v18 + v81;
        v81 = v12;
        v13 = v92 + v84;
        v84 += v92;
        v14 = v93 + v82;
        v82 += v93;
      }
      StringFromDataBlock = 0;
LABEL_150:
      i = v94;
      if ( StringFromDataBlock )
        goto LABEL_151;
    }
    if ( !StringFromDataBlock && !v7 )
    {
      v75 = 1520 * v13;
      v76 = (unsigned int)(2080 * v12);
      v77 = 16 * v14;
      v78 = v15 + v76 + 1520 * v13 + 16 * v14;
      *a3 = v78;
      *a1 = v12;
      if ( v99 >= v78 && a2 )
      {
        memset_0(a2, 0, v78);
        v103 = &v120[v76];
        v104 = &v120[v76 + v75];
        v9 = a2;
        v88 = a2;
        v114 = &v120[v76];
        v115 = v104;
        v109 = &v104[v77];
        v116 = (char *)v109;
        v7 = 1;
        v80 = 1;
        v12 = v81;
        v8 = v89;
        v13 = v84;
        v14 = v82;
        v15 = v83;
        continue;
      }
      StringFromDataBlock = 122;
      v86 = 122;
    }
    break;
  }
  DiscpFreeMemory(v110);
  DiscpFreeMemory(v105);
  DiscpFreeMemory(v111);
LABEL_160:
  DiscpFreeMemory(v112);
  return StringFromDataBlock;
}

```

## disassembly

```asm
0x1800192e8  mov     rax, rsp
0x1800192eb  mov     [rax+20h], r9d
0x1800192ef  mov     [rax+18h], r8
0x1800192f3  mov     [rax+10h], rdx
0x1800192f7  mov     [rax+8], rcx
0x1800192fb  push    rbx
0x1800192fc  push    rsi
0x1800192fd  push    rdi
0x1800192fe  push    r12
0x180019300  push    r13
0x180019302  push    r14
0x180019304  push    r15
0x180019306  sub     rsp, 160h
0x18001930d  mov     r12, rdx
0x180019310  mov     rdx, rcx
0x180019313  xor     ebx, ebx
0x180019315  mov     sil, bl
0x180019318  mov     [rsp+198h+var_158], bl
0x18001931c  mov     [rax-98h], rbx
0x180019323  mov     [rax-104h], ebx
0x180019329  mov     [rax-0C8h], rbx
0x180019330  mov     [rax-0A0h], rbx
0x180019337  mov     [rax-0A8h], rbx
0x18001933e  mov     [rsp+198h+var_140], rbx
0x180019343  mov     [rax+30h], ebx
0x180019346  mov     [rax-0E0h], rbx
0x18001934d  mov     [rax-50h], rbx
0x180019351  mov     [rax-0E8h], rbx
0x180019358  mov     [rax-118h], ebx
0x18001935e  mov     [rax-0FCh], ebx
0x180019364  mov     [rax-0F0h], rbx
0x18001936b  mov     [rax-114h], ebx
0x180019371  mov     [rax-90h], rbx
0x180019378  mov     [rax-0B0h], rbx
0x18001937f  mov     [rax-78h], rbx
0x180019383  mov     r15d, ebx
0x180019386  mov     [rsp+198h+var_120], rbx
0x18001938b  mov     [rax-48h], rbx
0x18001938f  mov     r14d, ebx
0x180019392  mov     [rsp+198h+var_128], rbx
0x180019397  mov     [rax-0D8h], rbx
0x18001939e  mov     [rax-88h], rbx
0x1800193a5  mov     [rax-0D0h], rbx
0x1800193ac  mov     [rax-80h], rbx
0x1800193b0  mov     [rax-100h], ebx
0x1800193b6  test    r12, r12
0x1800193b9  jnz     short loc_1800193C4
0x1800193bb  mov     [rsp+198h+var_F4], ebx
0x1800193c2  jmp     short loc_1800193CE
0x1800193c4  mov     ecx, [r8]
0x1800193c7  mov     [rsp+198h+var_F4], ecx
0x1800193ce  mov     [rdx], ebx
0x1800193d0  mov     [r8], ebx
0x1800193d3  lea     r9, [rsp+198h+var_104]
0x1800193db  lea     r8, [rsp+198h+var_98]
0x1800193e3  xor     edx, edx
0x1800193e5  lea     rcx, MSiSCSI_PersistentLogins_GUID
0x1800193ec  call    cs:__imp_DiscpQueryAllData
0x1800193f2  mov     edi, eax
0x1800193f4  test    eax, eax
0x1800193f6  jnz     loc_18001A469
0x1800193fc  lea     rax, [rsp+198h+var_A0]
0x180019404  mov     [rsp+198h+var_170], rax
0x180019409  lea     rax, [rsp+198h+var_C8]
0x180019411  mov     [rsp+198h+var_178], rax
0x180019416  lea     r9, [rsp+198h+var_A8]
0x18001941e  lea     r8, [rsp+198h+var_100]
0x180019426  mov     edx, [rsp+198h+var_104]
0x18001942d  mov     rcx, [rsp+198h+var_98]
0x180019435  call    cs:__imp_DiscpParseAllData
0x18001943b  mov     edi, eax
0x18001943d  test    eax, eax
0x18001943f  jnz     loc_18001A459
0x180019445  mov     [rsp+198h+var_58], r12
0x18001944d  mov     [rsp+198h+var_110], ebx
0x180019454  mov     [rsp+198h+var_10C], ebx
0x18001945b  mov     [rsp+198h+var_F8], ebx
0x180019462  mov     edx, ebx
0x180019464  mov     [rsp+198h+var_154], ebx
0x180019468  mov     r9d, ebx
0x18001946b  mov     [rsp+198h+var_148], ebx
0x18001946f  mov     r10d, ebx
0x180019472  mov     [rsp+198h+var_150], ebx
0x180019476  mov     r11d, ebx
0x180019479  mov     [rsp+198h+var_14C], ebx
0x18001947d  mov     r8d, ebx
0x180019480  mov     [rsp+198h+var_108], r8d
0x180019488  mov     eax, r9d
0x18001948b  mov     [rsp+198h+var_B8], eax
0x180019492  mov     ecx, edx
0x180019494  mov     [rsp+198h+var_BC], edx
0x18001949b  cmp     r8d, [rsp+198h+var_100]
0x1800194a3  jnb     loc_18001A33D
0x1800194a9  mov     edi, ebx
0x1800194ab  mov     r12d, r8d
0x1800194ae  mov     [rsp+198h+var_130], r12
0x1800194b3  mov     rax, [rsp+198h+var_C8]
0x1800194bb  mov     rcx, [rax+r12*8]
0x1800194bf  mov     [rsp+198h+var_60], rcx
0x1800194c7  mov     [rsp+198h+var_140], rcx
0x1800194cc  mov     rax, [rsp+198h+var_A0]
0x1800194d4  mov     eax, [rax+r12*4]
0x1800194d8  mov     [rsp+198h+arg_28], eax
0x1800194df  test    rcx, rcx
0x1800194e2  jz      loc_18001A335
0x1800194e8  cmp     eax, 8
0x1800194eb  jnb     short loc_1800194F7
0x1800194ed  mov     edi, 57h ; 'W'
0x1800194f2  jmp     loc_18001A329
0x1800194f7  add     eax, 0FFFFFFF8h
0x1800194fa  mov     [rsp+198h+arg_28], eax
0x180019501  lea     rax, [rcx+8]
0x180019505  mov     [rsp+198h+var_140], rax
0x18001950a  test    sil, sil
0x18001950d  jnz     short loc_18001951D
0x18001950f  mov     [rsp+198h+var_110], ebx
0x180019516  mov     [rsp+198h+var_10C], ebx
0x18001951d  mov     r13d, ebx
0x180019520  cmp     r13d, [rcx]
0x180019523  jnb     loc_18001A2E8
0x180019529  lea     r8, [rsp+198h+arg_28]
0x180019531  lea     rdx, [rsp+198h+var_140]
0x180019536  mov     ecx, 8
0x18001953b  call    cs:__imp_DiscpPadDataBlock
0x180019541  mov     edi, eax
0x180019543  mov     [rsp+198h+var_138], eax
0x180019547  test    eax, eax
0x180019549  jz      short loc_180019563
0x18001954b  mov     edx, [rsp+198h+var_154]
0x18001954f  mov     r9d, [rsp+198h+var_148]
0x180019554  mov     r10d, [rsp+198h+var_150]
0x180019559  mov     r11d, [rsp+198h+var_14C]
0x18001955e  jmp     loc_18001A31D
0x180019563  test    sil, sil
0x180019566  jz      loc_1800195FD
0x18001956c  mov     rax, [rsp+198h+var_A8]
0x180019574  mov     rcx, [rax+r12*8]
0x180019578  mov     [rsp+198h+var_E0], rcx
0x180019580  movzx   r9d, word ptr [rcx]
0x180019584  lea     rax, [rcx+2]
0x180019588  mov     [rsp+198h+var_E0], rax
0x180019590  mov     edx, 100h
0x180019595  cmp     r9d, edx
0x180019598  cmova   r9d, edx
0x18001959c  lea     rdx, [r14+1C2h]
0x1800195a3  test    rax, rax
0x1800195a6  jz      short loc_1800195FA
0x1800195a8  mov     [rsp+198h+var_E8], rdx
0x1800195b0  mov     [rsp+198h+var_E0], rcx
0x1800195b8  lea     eax, ds:2[r9*2]
0x1800195c0  mov     [rsp+198h+var_118], eax
0x1800195c7  lea     rax, [rsp+198h+var_118]
0x1800195cf  mov     [rsp+198h+var_178], rax
0x1800195d4  lea     r8, [rsp+198h+var_E0]
0x1800195dc  lea     rdx, [rsp+198h+var_FC]
0x1800195e4  lea     rcx, [rsp+198h+var_E8]
0x1800195ec  call    cs:__imp_DiscpCopyString
0x1800195f2  mov     edi, eax
0x1800195f4  mov     [rsp+198h+var_138], eax
0x1800195f8  jmp     short loc_1800195FD
0x1800195fa  mov     [rdx], bx
0x1800195fd  test    edi, edi
0x1800195ff  jz      short loc_180019619
0x180019601  mov     edx, [rsp+198h+var_154]
0x180019605  mov     r9d, [rsp+198h+var_148]
0x18001960a  mov     r10d, [rsp+198h+var_150]
0x18001960f  mov     r11d, [rsp+198h+var_14C]
0x180019614  jmp     loc_18001A31D
0x180019619  lea     r9, [rsp+198h+arg_28]
0x180019621  lea     r8, [rsp+198h+var_140]
0x180019626  lea     rdx, [rsp+198h+var_114]
0x18001962e  lea     rcx, [rsp+198h+var_F0]
0x180019636  call    cs:__imp_DiscpGetStringFromDataBlock
0x18001963c  mov     edi, eax
0x18001963e  mov     [rsp+198h+var_138], eax
0x180019642  test    eax, eax
0x180019644  jnz     loc_1800196D6
0x18001964a  test    sil, sil
0x18001964d  jz      loc_1800196D6
0x180019653  mov     r9d, [rsp+198h+var_114]
0x18001965b  cmp     r9d, 0DFh
0x180019662  jbe     short loc_180019672
0x180019664  mov     r9d, 0DFh
0x18001966a  mov     [rsp+198h+var_114], r9d
0x180019672  mov     rax, [rsp+198h+var_F0]
0x18001967a  test    rax, rax
0x18001967d  jz      short loc_1800196D6
0x18001967f  mov     [rsp+198h+var_E8], r14
0x180019687  sub     rax, 2
0x18001968b  mov     [rsp+198h+var_F0], rax
0x180019693  lea     eax, ds:2[r9*2]
0x18001969b  mov     [rsp+198h+var_118], eax
0x1800196a2  inc     r9d
0x1800196a5  lea     rax, [rsp+198h+var_118]
0x1800196ad  mov     [rsp+198h+var_178], rax
0x1800196b2  lea     r8, [rsp+198h+var_F0]
0x1800196ba  lea     rdx, [rsp+198h+var_FC]
0x1800196c2  lea     rcx, [rsp+198h+var_E8]
0x1800196ca  call    cs:__imp_DiscpCopyString
0x1800196d0  mov     edi, eax
0x1800196d2  mov     [rsp+198h+var_138], eax
0x1800196d6  test    edi, edi
0x1800196d8  jz      short loc_1800196F2
0x1800196da  mov     edx, [rsp+198h+var_154]
0x1800196de  mov     r9d, [rsp+198h+var_148]
0x1800196e3  mov     r10d, [rsp+198h+var_150]
0x1800196e8  mov     r11d, [rsp+198h+var_14C]
0x1800196ed  jmp     loc_18001A31D
0x1800196f2  lea     r8, [rsp+198h+arg_28]
0x1800196fa  lea     rdx, [rsp+198h+var_140]
0x1800196ff  mov     ecx, 8
0x180019704  call    cs:__imp_DiscpPadDataBlock
0x18001970a  mov     edi, eax
0x18001970c  mov     [rsp+198h+var_138], eax
0x180019710  test    eax, eax
0x180019712  jz      short loc_18001972C
0x180019714  mov     edx, [rsp+198h+var_154]
0x180019718  mov     r9d, [rsp+198h+var_148]
0x18001971d  mov     r10d, [rsp+198h+var_150]
0x180019722  mov     r11d, [rsp+198h+var_14C]
0x180019727  jmp     loc_18001A31D
0x18001972c  mov     edi, 0EFFF0019h
0x180019731  mov     [rsp+198h+var_138], edi
0x180019735  mov     eax, [rsp+198h+arg_28]
0x18001973c  cmp     eax, 8
0x18001973f  jb      loc_18001A2A5
0x180019745  mov     rcx, [rsp+198h+var_140]
0x18001974a  mov     rdx, [rcx]
0x18001974d  add     rcx, 8
0x180019751  mov     [rsp+198h+var_140], rcx
0x180019756  add     eax, 0FFFFFFF8h
0x180019759  mov     [rsp+198h+arg_28], eax
0x180019760  test    sil, sil
0x180019763  jz      short loc_180019778
0x180019765  mov     [r14+7D0h], rdx
0x18001976c  mov     rcx, [rsp+198h+var_140]
0x180019771  mov     eax, [rsp+198h+arg_28]
0x180019778  cmp     eax, 4
0x18001977b  jb      loc_18001A290
0x180019781  mov     edx, [rcx]
0x180019783  add     rcx, 4
0x180019787  mov     [rsp+198h+var_140], rcx
0x18001978c  add     eax, 0FFFFFFFCh
0x18001978f  mov     [rsp+198h+arg_28], eax
0x180019796  test    sil, sil
0x180019799  jz      short loc_1800197AE
0x18001979b  mov     [r14+3C4h], edx
0x1800197a2  mov     rcx, [rsp+198h+var_140]
0x1800197a7  mov     eax, [rsp+198h+arg_28]
0x1800197ae  cmp     eax, 4
0x1800197b1  jb      loc_18001A278
0x1800197b7  mov     r12d, [rcx]
0x1800197ba  add     rcx, 4
0x1800197be  mov     [rsp+198h+var_140], rcx
0x1800197c3  add     eax, 0FFFFFFFCh
0x1800197c6  mov     [rsp+198h+arg_28], eax
0x1800197cd  test    sil, sil
0x1800197d0  jz      short loc_1800197E5
0x1800197d2  mov     [r14+804h], r12d
0x1800197d9  mov     rcx, [rsp+198h+var_140]
0x1800197de  mov     eax, [rsp+198h+arg_28]
0x1800197e5  cmp     eax, 1
0x1800197e8  jb      loc_18001A25B
0x1800197ee  mov     dl, [rcx]
0x1800197f0  inc     rcx
0x1800197f3  mov     [rsp+198h+var_140], rcx
0x1800197f8  dec     eax
0x1800197fa  mov     [rsp+198h+arg_28], eax
0x180019801  test    sil, sil
0x180019804  jz      short loc_18001980D
0x180019806  mov     [r14+1C0h], dl
0x18001980d  lea     r8, [rsp+198h+arg_28]
0x180019815  lea     rdx, [rsp+198h+var_140]
0x18001981a  mov     ecx, 2
0x18001981f  call    cs:__imp_DiscpPadDataBlock
0x180019825  mov     edi, eax
0x180019827  mov     [rsp+198h+var_138], eax
0x18001982b  test    eax, eax
0x18001982d  jz      short loc_18001984C
0x18001982f  mov     edx, [rsp+198h+var_154]
0x180019833  mov     r9d, [rsp+198h+var_148]
0x180019838  mov     r10d, [rsp+198h+var_150]
0x18001983d  mov     r11d, [rsp+198h+var_14C]
0x180019842  mov     r12, [rsp+198h+var_130]
0x180019847  jmp     loc_18001A31D
0x18001984c  mov     ecx, [rsp+198h+arg_28]
0x180019853  cmp     ecx, 2
0x180019856  jb      loc_18001A23E
0x18001985c  mov     rax, [rsp+198h+var_140]
0x180019861  movzx   edx, word ptr [rax]
0x180019864  add     rax, 2
0x180019868  mov     [rsp+198h+var_140], rax
0x18001986d  add     ecx, 0FFFFFFFEh
0x180019870  mov     [rsp+198h+arg_28], ecx
0x180019877  test    sil, sil
0x18001987a  jz      short loc_1800198A7
0x18001987c  mov     r8, [rsp+198h+arg_20]
0x180019884  test    r8, r8
0x180019887  jz      short loc_1800198A7
0x180019889  mov     ecx, [rsp+198h+var_F8]
  ... truncated ...
```
