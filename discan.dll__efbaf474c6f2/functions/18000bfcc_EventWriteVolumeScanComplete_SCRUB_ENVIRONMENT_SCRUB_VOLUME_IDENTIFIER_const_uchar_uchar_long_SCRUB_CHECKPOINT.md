# EventWriteVolumeScanComplete(_SCRUB_ENVIRONMENT *,_SCRUB_VOLUME_IDENTIFIER const *,uchar,uchar,long,_SCRUB_CHECKPOINT_STATS const *,ulong,ushort)

- ea: `0x18000bfcc`
- end: `0x18000d111`
- name: `?EventWriteVolumeScanComplete@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_SCRUB_VOLUME_IDENTIFIER@@EEJPEBU_SCRUB_CHECKPOINT_STATS@@KG@Z`
- size: `4421`
- prototype: `void __fastcall(struct _SCRUB_ENVIRONMENT *, const struct _SCRUB_VOLUME_IDENTIFIER *, __int64, char, int, const struct _SCRUB_CHECKPOINT_STATS *, unsigned int, char)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180021db4`

## callees

- `0x180001194`
- `0x18000166c`
- `0x18000bfcc`
- `0x180010ea8`
- `0x180011190`
- `0x180011624`
- `0x180011914`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall EventWriteVolumeScanComplete(
        struct _SCRUB_ENVIRONMENT *a1,
        const struct _SCRUB_VOLUME_IDENTIFIER *a2,
        __int64 a3,
        char a4,
        int a5,
        const struct _SCRUB_CHECKPOINT_STATS *a6,
        unsigned int a7,
        char a8)
{
  int v8; // eax
  const struct _SCRUB_CHECKPOINT_STATS *v10; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // rax
  unsigned int v17; // esi
  __int64 v18; // rcx
  __int64 v19; // r9
  __int64 v20; // r10
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  char *v24; // rdx
  __int64 v25; // rax
  int v26; // esi
  __int64 v27; // rcx
  unsigned __int16 *v28; // r9
  int v29; // r8d
  __int64 v30; // rcx
  unsigned __int16 *v31; // r9
  int v32; // r8d
  __int64 v33; // rax
  unsigned int v34; // r15d
  __int64 v35; // rcx
  __int64 v36; // rdx
  unsigned __int16 *v37; // r9
  int v38; // r8d
  __int64 v39; // rcx
  __int64 v40; // rdx
  unsigned __int16 *v41; // r9
  int v42; // r8d
  __int64 v43; // rcx
  unsigned __int16 *v44; // r9
  int v45; // r8d
  __int64 v46; // rcx
  unsigned __int16 *v47; // r9
  int v48; // r8d
  __int64 v49; // rcx
  __int64 v50; // rdx
  unsigned __int16 *v51; // r9
  int v52; // r8d
  __int64 v53; // rcx
  __int64 v54; // rdx
  unsigned __int16 *v55; // r9
  int v56; // r8d
  __int64 v57; // rax
  __int64 v58; // [rsp+E0h] [rbp-A8h]
  __int64 v59; // [rsp+100h] [rbp-88h]
  __int64 v60; // [rsp+100h] [rbp-88h]
  __int64 v61; // [rsp+100h] [rbp-88h]
  __int64 v62; // [rsp+100h] [rbp-88h]
  int v63; // [rsp+108h] [rbp-80h] BYREF
  int v64; // [rsp+10Ch] [rbp-7Ch] BYREF
  int v65; // [rsp+110h] [rbp-78h] BYREF
  __int64 v66; // [rsp+118h] [rbp-70h] BYREF
  __int64 v67; // [rsp+120h] [rbp-68h] BYREF
  __int64 v68; // [rsp+128h] [rbp-60h] BYREF
  __int64 v69; // [rsp+130h] [rbp-58h] BYREF
  __int64 v70; // [rsp+138h] [rbp-50h] BYREF
  __int64 v71; // [rsp+140h] [rbp-48h] BYREF
  __int64 v72; // [rsp+148h] [rbp-40h] BYREF
  __int64 v73; // [rsp+150h] [rbp-38h] BYREF
  __int64 v74; // [rsp+158h] [rbp-30h] BYREF
  __int64 v75; // [rsp+160h] [rbp-28h] BYREF
  __int64 v76; // [rsp+168h] [rbp-20h] BYREF
  __int64 v77; // [rsp+170h] [rbp-18h] BYREF
  __int64 v78; // [rsp+178h] [rbp-10h] BYREF
  __int64 v79[7]; // [rsp+180h] [rbp-8h] BYREF
  char v80; // [rsp+1D8h] [rbp+50h] BYREF

  v8 = *((_DWORD *)a1 + 2);
  v10 = a6;
  if ( !(_BYTE)a3 )
  {
    v26 = a5;
    if ( a4 )
    {
      if ( !v8 )
      {
        if ( a5 < 0 )
        {
          if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 2) != 0 )
          {
            v30 = *((_QWORD *)a2 + 7);
            v31 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
            v32 = *v31;
            LOWORD(v32) = (unsigned __int16)v32 >> 1;
            McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiixj_EventWriteTransfer(
              v30,
              (unsigned int)DISCAN_EVENT_VOLUME_SCAN_PARTIAL_COMPLETE_WITH_ERROR,
              v32,
              *((_QWORD *)v31 + 1),
              *(_WORD *)v30 >> 1,
              *(_QWORD *)(v30 + 8),
              a5,
              *((_QWORD *)a6 + 4),
              *((_QWORD *)a6 + 3),
              *((_QWORD *)a6 + 5),
              *((_QWORD *)a6 + 6),
              *((_QWORD *)a6 + 7),
              *((_QWORD *)a6 + 1),
              *((_QWORD *)a6 + 2),
              *((_QWORD *)a6 + 13),
              *((_QWORD *)a6 + 14),
              *((_QWORD *)a6 + 15),
              *((_QWORD *)a6 + 16),
              *((_QWORD *)a6 + 17),
              *((_QWORD *)a6 + 18),
              *((_QWORD *)a6 + 19),
              *((_QWORD *)a6 + 20),
              *((_QWORD *)a6 + 8),
              *((_QWORD *)a6 + 9),
              *((_QWORD *)a6 + 10),
              *((_QWORD *)a6 + 11),
              *(_QWORD *)a6,
              *((_QWORD *)a2 + 3));
          }
        }
        else if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 1) != 0 )
        {
          v27 = *((_QWORD *)a2 + 7);
          v28 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
          v29 = *v28;
          LOWORD(v29) = (unsigned __int16)v29 >> 1;
          McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiixj_EventWriteTransfer(
            v27,
            (unsigned int)DISCAN_EVENT_VOLUME_SCAN_PARTIAL_COMPLETE,
            v29,
            *((_QWORD *)v28 + 1),
            *(_WORD *)v27 >> 1,
            *(_QWORD *)(v27 + 8),
            a5,
            *((_QWORD *)a6 + 4),
            *((_QWORD *)a6 + 3),
            *((_QWORD *)a6 + 5),
            *((_QWORD *)a6 + 6),
            *((_QWORD *)a6 + 7),
            *((_QWORD *)a6 + 1),
            *((_QWORD *)a6 + 2),
            *((_QWORD *)a6 + 13),
            *((_QWORD *)a6 + 14),
            *((_QWORD *)a6 + 15),
            *((_QWORD *)a6 + 16),
            *((_QWORD *)a6 + 17),
            *((_QWORD *)a6 + 18),
            *((_QWORD *)a6 + 19),
            *((_QWORD *)a6 + 20),
            *((_QWORD *)a6 + 8),
            *((_QWORD *)a6 + 9),
            *((_QWORD *)a6 + 10),
            *((_QWORD *)a6 + 11),
            *(_QWORD *)a6,
            *((_QWORD *)a2 + 3));
        }
        if ( (unsigned int)dword_1800470B8 <= 5 || !(unsigned __int8)tlgKeywordOn(a1, a2, a3) )
          return;
        v23 = *((_QWORD *)a2 + 2);
        v24 = &byte_180040E1F;
        v80 = a8;
        v79[0] = *(_QWORD *)(v23 + 16);
        v33 = *(_QWORD *)(v23 + 8);
        v64 = 1;
        goto LABEL_49;
      }
      v34 = a7;
      if ( a5 < 0 )
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 0x10) != 0 )
        {
          v39 = *((_QWORD *)a2 + 2);
          v60 = *((_QWORD *)a2 + 3);
          v40 = *((_QWORD *)a2 + 7);
          v41 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
          v42 = *v41;
          LOWORD(v42) = (unsigned __int16)v42 >> 1;
          McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiiqxqiij_EventWriteTransfer(
            v39,
            (unsigned int)DISCANCR_EVENT_VOLUME_SCAN_PARTIAL_COMPLETE_WITH_ERROR,
            v42,
            *((_QWORD *)v41 + 1),
            *(_WORD *)v40 >> 1,
            *(_QWORD *)(v40 + 8),
            a5,
            *((_QWORD *)a6 + 4),
            *((_QWORD *)a6 + 3),
            *((_QWORD *)a6 + 5),
            *((_QWORD *)a6 + 6),
            *((_QWORD *)a6 + 7),
            *((_QWORD *)a6 + 1),
            *((_QWORD *)a6 + 2),
            *((_QWORD *)a6 + 13),
            *((_QWORD *)a6 + 14),
            *((_QWORD *)a6 + 15),
            *((_QWORD *)a6 + 16),
            *((_QWORD *)a6 + 17),
            *((_QWORD *)a6 + 18),
            *((_QWORD *)a6 + 19),
            *((_QWORD *)a6 + 20),
            *((_QWORD *)a6 + 8),
            *((_QWORD *)a6 + 9),
            *((_QWORD *)a6 + 10),
            *((_QWORD *)a6 + 11),
            a7,
            *(_QWORD *)a6,
            *(_DWORD *)v39,
            *(_QWORD *)(v39 + 8),
            *(_QWORD *)(v39 + 16),
            v60);
        }
      }
      else if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
      {
        v35 = *((_QWORD *)a2 + 2);
        v59 = *((_QWORD *)a2 + 3);
        v36 = *((_QWORD *)a2 + 7);
        v37 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
        v38 = *v37;
        LOWORD(v38) = (unsigned __int16)v38 >> 1;
        McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiiqxqiij_EventWriteTransfer(
          v35,
          (unsigned int)DISCANCR_EVENT_VOLUME_SCAN_PARTIAL_COMPLETE,
          v38,
          *((_QWORD *)v37 + 1),
          *(_WORD *)v36 >> 1,
          *(_QWORD *)(v36 + 8),
          a5,
          *((_QWORD *)a6 + 4),
          *((_QWORD *)a6 + 3),
          *((_QWORD *)a6 + 5),
          *((_QWORD *)a6 + 6),
          *((_QWORD *)a6 + 7),
          *((_QWORD *)a6 + 1),
          *((_QWORD *)a6 + 2),
          *((_QWORD *)a6 + 13),
          *((_QWORD *)a6 + 14),
          *((_QWORD *)a6 + 15),
          *((_QWORD *)a6 + 16),
          *((_QWORD *)a6 + 17),
          *((_QWORD *)a6 + 18),
          *((_QWORD *)a6 + 19),
          *((_QWORD *)a6 + 20),
          *((_QWORD *)a6 + 8),
          *((_QWORD *)a6 + 9),
          *((_QWORD *)a6 + 10),
          *((_QWORD *)a6 + 11),
          a7,
          *(_QWORD *)a6,
          *(_DWORD *)v35,
          *(_QWORD *)(v35 + 8),
          *(_QWORD *)(v35 + 16),
          v59);
      }
      if ( (unsigned int)dword_1800470B8 <= 5 || !(unsigned __int8)tlgKeywordOn(a1, a2, a3) )
        return;
      v24 = byte_180040CCD;
    }
    else
    {
      if ( !v8 )
      {
        if ( a5 < 0 )
        {
          if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 2) != 0 )
          {
            v46 = *((_QWORD *)a2 + 7);
            v47 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
            v48 = *v47;
            LOWORD(v48) = (unsigned __int16)v48 >> 1;
            McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiixj_EventWriteTransfer(
              v46,
              (unsigned int)DISCAN_EVENT_VOLUME_SCAN_COMPLETE_WITH_ERROR,
              v48,
              *((_QWORD *)v47 + 1),
              *(_WORD *)v46 >> 1,
              *(_QWORD *)(v46 + 8),
              a5,
              *((_QWORD *)a6 + 4),
              *((_QWORD *)a6 + 3),
              *((_QWORD *)a6 + 5),
              *((_QWORD *)a6 + 6),
              *((_QWORD *)a6 + 7),
              *((_QWORD *)a6 + 1),
              *((_QWORD *)a6 + 2),
              *((_QWORD *)a6 + 13),
              *((_QWORD *)a6 + 14),
              *((_QWORD *)a6 + 15),
              *((_QWORD *)a6 + 16),
              *((_QWORD *)a6 + 17),
              *((_QWORD *)a6 + 18),
              *((_QWORD *)a6 + 19),
              *((_QWORD *)a6 + 20),
              *((_QWORD *)a6 + 8),
              *((_QWORD *)a6 + 9),
              *((_QWORD *)a6 + 10),
              *((_QWORD *)a6 + 11),
              *(_QWORD *)a6,
              *((_QWORD *)a2 + 3));
          }
        }
        else if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 1) != 0 )
        {
          v43 = *((_QWORD *)a2 + 7);
          v44 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
          v45 = *v44;
          LOWORD(v45) = (unsigned __int16)v45 >> 1;
          McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiixj_EventWriteTransfer(
            v43,
            (unsigned int)DISCAN_EVENT_VOLUME_SCAN_COMPLETE,
            v45,
            *((_QWORD *)v44 + 1),
            *(_WORD *)v43 >> 1,
            *(_QWORD *)(v43 + 8),
            a5,
            *((_QWORD *)a6 + 4),
            *((_QWORD *)a6 + 3),
            *((_QWORD *)a6 + 5),
            *((_QWORD *)a6 + 6),
            *((_QWORD *)a6 + 7),
            *((_QWORD *)a6 + 1),
            *((_QWORD *)a6 + 2),
            *((_QWORD *)a6 + 13),
            *((_QWORD *)a6 + 14),
            *((_QWORD *)a6 + 15),
            *((_QWORD *)a6 + 16),
            *((_QWORD *)a6 + 17),
            *((_QWORD *)a6 + 18),
            *((_QWORD *)a6 + 19),
            *((_QWORD *)a6 + 20),
            *((_QWORD *)a6 + 8),
            *((_QWORD *)a6 + 9),
            *((_QWORD *)a6 + 10),
            *((_QWORD *)a6 + 11),
            *(_QWORD *)a6,
            *((_QWORD *)a2 + 3));
        }
        if ( (unsigned int)dword_1800470B8 <= 5 || !(unsigned __int8)tlgKeywordOn(a1, a2, a3) )
          return;
        v23 = *((_QWORD *)a2 + 2);
        v24 = (char *)&dword_180040B84;
        v80 = a8;
        v79[0] = *(_QWORD *)(v23 + 16);
        v33 = *(_QWORD *)(v23 + 8);
        v64 = 1;
LABEL_49:
        v78 = v33;
        v57 = *(_QWORD *)a2 + 20LL;
        v63 = v26;
        v77 = v57;
        v65 = *((unsigned __int16 *)v10 + 84);
        v76 = *(_QWORD *)v10;
        v75 = *((_QWORD *)v10 + 3);
        v74 = *((_QWORD *)v10 + 4);
        goto LABEL_50;
      }
      v34 = a7;
      if ( a5 < 0 )
      {
        if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 0x10) != 0 )
        {
          v53 = *((_QWORD *)a2 + 2);
          v62 = *((_QWORD *)a2 + 3);
          v54 = *((_QWORD *)a2 + 7);
          v55 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
          v56 = *v55;
          LOWORD(v56) = (unsigned __int16)v56 >> 1;
          McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiiqxqiij_EventWriteTransfer(
            v53,
            (unsigned int)DISCANCR_EVENT_VOLUME_SCAN_COMPLETE_WITH_ERROR,
            v56,
            *((_QWORD *)v55 + 1),
            *(_WORD *)v54 >> 1,
            *(_QWORD *)(v54 + 8),
            a5,
            *((_QWORD *)a6 + 4),
            *((_QWORD *)a6 + 3),
            *((_QWORD *)a6 + 5),
            *((_QWORD *)a6 + 6),
            *((_QWORD *)a6 + 7),
            *((_QWORD *)a6 + 1),
            *((_QWORD *)a6 + 2),
            *((_QWORD *)a6 + 13),
            *((_QWORD *)a6 + 14),
            *((_QWORD *)a6 + 15),
            *((_QWORD *)a6 + 16),
            *((_QWORD *)a6 + 17),
            *((_QWORD *)a6 + 18),
            *((_QWORD *)a6 + 19),
            *((_QWORD *)a6 + 20),
            *((_QWORD *)a6 + 8),
            *((_QWORD *)a6 + 9),
            *((_QWORD *)a6 + 10),
            *((_QWORD *)a6 + 11),
            a7,
            *(_QWORD *)a6,
            *(_DWORD *)v53,
            *(_QWORD *)(v53 + 8),
            *(_QWORD *)(v53 + 16),
            v62);
        }
      }
      else if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
      {
        v49 = *((_QWORD *)a2 + 2);
        v61 = *((_QWORD *)a2 + 3);
        v50 = *((_QWORD *)a2 + 7);
        v51 = (unsigned __int16 *)*((_QWORD *)a2 + 4);
        v52 = *v51;
        LOWORD(v52) = (unsigned __int16)v52 >> 1;
        McTemplateU0hzr0hzr2dxxxxxiiiiiiiiiiiiiiqxqiij_EventWriteTransfer(
          v49,
          (unsigned int)DISCANCR_EVENT_VOLUME_SCAN_COMPLETE,
          v52,
          *((_QWORD *)v51 + 1),
          *(_WORD *)v50 >> 1,
          *(_QWORD *)(v50 + 8),
          a5,
          *((_QWORD *)a6 + 4),
          *((_QWORD *)a6 + 3),
          *((_QWORD *)a6 + 5),
          *((_QWORD *)a6 + 6),
          *((_QWORD *)a6 + 7),
          *((_QWORD *)a6 + 1),
          *((_QWORD *)a6 + 2),
          *((_QWORD *)a6 + 13),
          *((_QWORD *)a6 + 14),
          *((_QWORD *)a6 + 15),
          *((_QWORD *)a6 + 16),
          *((_QWORD *)a6 + 17),
          *((_QWORD *)a6 + 18),
          *((_QWORD *)a6 + 19),
          *((_QWORD *)a6 + 20),
          *((_QWORD *)a6 + 8),
          *((_QWORD *)a6 + 9),
          *((_QWORD *)a6 + 10),
          *((_QWORD *)a6 + 11),
          a7,
          *(_QWORD *)a6,
          *(_DWORD *)v49,
          *(_QWORD *)(v49 + 8),
          *(_QWORD *)(v49 + 16),
          v61);
      }
      if ( (unsigned int)dword_1800470B8 <= 5 || !(unsigned __int8)tlgKeywordOn(a1, a2, a3) )
        return;
      v24 = byte_180040A39;
    }
    v23 = *((_QWORD *)a2 + 2);
    v80 = a8;
    v79[0] = *(_QWORD *)(v23 + 16);
    v33 = *(_QWORD *)(v23 + 8);
    v64 = v34;
    goto LABEL_49;
  }
  if ( !v8 )
  {
    if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 1) != 0 )
    {
      v58 = *((_QWORD *)a2 + 3);
      v12 = *((_QWORD *)a2 + 7);
      McTemplateU0hzr0hzr2xxxxxiiiiiiiiiiiiiixhj_EventWriteTransfer(
        *(_WORD *)v12 >> 1,
        v12,
        **((_WORD **)a2 + 4) >> 1,
        *(_QWORD *)(*((_QWORD *)a2 + 4) + 8LL),
        *(_WORD *)v12 >> 1,
        *(_QWORD *)(v12 + 8),
        *((_QWORD *)a6 + 4),
        *((_QWORD *)a6 + 3),
        *((_QWORD *)a6 + 5),
        *((_QWORD *)a6 + 6),
        *((_QWORD *)a6 + 7),
        *((_QWORD *)a6 + 1),
        *((_QWORD *)a6 + 2),
        *((_QWORD *)a6 + 13),
        *((_QWORD *)a6 + 14),
        *((_QWORD *)a6 + 15),
        *((_QWORD *)a6 + 16),
        *((_QWORD *)a6 + 17),
        *((_QWORD *)a6 + 18),
        *((_QWORD *)a6 + 19),
        *((_QWORD *)a6 + 20),
        *((_QWORD *)a6 + 8),
        *((_QWORD *)a6 + 9),
        *((_QWORD *)a6 + 10),
        *((_QWORD *)a6 + 11),
        *(_QWORD *)a6,
        *((_WORD *)a6 + 84),
        v58);
    }
    if ( (unsigned int)dword_1800470B8 > 5 )
    {
      if ( (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
      {
        v15 = *((_QWORD *)a2 + 2);
        v80 = a8;
        v66 = *(_QWORD *)(v15 + 16);
        v67 = *(_QWORD *)(v15 + 8);
        v16 = *(_QWORD *)a2 + 20LL;
        v64 = 1;
        v68 = v16;
        v63 = *((unsigned __int16 *)v10 + 84);
        v69 = *(_QWORD *)v10;
        v70 = *((_QWORD *)v10 + 3);
        v71 = *((_QWORD *)v10 + 4);
        v65 = a5;
        v72 = *((_QWORD *)v10 + 11);
        v73 = *((_QWORD *)v10 + 10);
        v74 = *((_QWORD *)v10 + 9);
        v75 = *((_QWORD *)v10 + 8);
        v76 = *((_QWORD *)v10 + 2);
        v77 = *((_QWORD *)v10 + 1);
        v78 = *((_QWORD *)a2 + 3);
        v79[0] = (__int64)a1 + 52;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
          v15,
          (__int64)word_1800410BA,
          v13,
          v14,
          v79,
          &v78,
          (__int64)&v77,
          (__int64)&v76,
          (__int64)&v75,
          (__int64)&v74,
          (__int64)&v73,
          (__int64)&v72,
          (__int64)&v65,
          (__int64)&v71,
          (__int64)&v70,
          (__int64)&v64,
          (__int64)&v69,
          (__int64)&v63,
          &v68,
          (__int64)&v67,
          (__int64)&v66,
          (__int64)&v80);
      }
    }
    return;
  }
  v17 = a7;
  if ( (Microsoft_Windows_DataIntegrityScanEnableBits & 8) != 0 )
  {
    v18 = *((_QWORD *)a2 + 2);
    v19 = *((_QWORD *)a2 + 4);
    v20 = *((_QWORD *)a2 + 7);
    McTemplateU0hzr0hzr2xxxxxiiiiiiiiiiiiiiqxhqiij_EventWriteTransfer(
      v18,
      *(_WORD *)v20 >> 1,
      *(_WORD *)v19 >> 1,
      *(_QWORD *)(v19 + 8),
      *(_WORD *)v20 >> 1,
      *(_QWORD *)(v20 + 8),
      *((_QWORD *)a6 + 4),
      *((_QWORD *)a6 + 3),
      *((_QWORD *)a6 + 5),
      *((_QWORD *)a6 + 6),
      *((_QWORD *)a6 + 7),
      *((_QWORD *)a6 + 1),
      *((_QWORD *)a6 + 2),
      *((_QWORD *)a6 + 13),
      *((_QWORD *)a6 + 14),
      *((_QWORD *)a6 + 15),
      *((_QWORD *)a6 + 16),
      *((_QWORD *)a6 + 17),
      *((_QWORD *)a6 + 18),
      *((_QWORD *)a6 + 19),
      *((_QWORD *)a6 + 20),
      *((_QWORD *)a6 + 8),
      *((_QWORD *)a6 + 9),
      *((_QWORD *)a6 + 10),
      *((_QWORD *)a6 + 11),
      a7,
      *(_QWORD *)a6,
      *((_WORD *)a6 + 84),
      *(_DWORD *)v18,
      *(_QWORD *)(v18 + 8),
      *(_QWORD *)(v18 + 16),
      *((_QWORD *)a2 + 3));
  }
  if ( (unsigned int)dword_1800470B8 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
  {
    v23 = *((_QWORD *)a2 + 2);
    v24 = &byte_180040F6F;
    v80 = a8;
    v79[0] = *(_QWORD *)(v23 + 16);
    v78 = *(_QWORD *)(v23 + 8);
    v25 = *(_QWORD *)a2 + 20LL;
    v64 = v17;
    v77 = v25;
    v65 = *((unsigned __int16 *)v10 + 84);
    v76 = *(_QWORD *)v10;
    v75 = *((_QWORD *)v10 + 3);
    v74 = *((_QWORD *)v10 + 4);
    v63 = a5;
LABEL_50:
    v73 = *((_QWORD *)v10 + 11);
    v72 = *((_QWORD *)v10 + 10);
    v71 = *((_QWORD *)v10 + 9);
    v70 = *((_QWORD *)v10 + 8);
    v69 = *((_QWORD *)v10 + 2);
    v68 = *((_QWORD *)v10 + 1);
    v67 = *((_QWORD *)a2 + 3);
    v66 = (__int64)a1 + 52;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>>(
      v23,
      (__int64)v24,
      v21,
      v22,
      &v66,
      &v67,
      (__int64)&v68,
      (__int64)&v69,
      (__int64)&v70,
      (__int64)&v71,
      (__int64)&v72,
      (__int64)&v73,
      (__int64)&v63,
      (__int64)&v74,
      (__int64)&v75,
      (__int64)&v64,
      (__int64)&v76,
      (__int64)&v65,
      &v77,
      (__int64)&v78,
      (__int64)v79,
      (__int64)&v80);
  }
}

```

## disassembly

```asm
0x18000bfcc  mov     r11, rsp
0x18000bfcf  push    rbp
0x18000bfd0  push    rbx
0x18000bfd1  push    rsi
0x18000bfd2  push    rdi
0x18000bfd3  push    r14
0x18000bfd5  push    r15
0x18000bfd7  lea     rbp, [r11-38h]
0x18000bfdb  sub     rsp, 188h
0x18000bfe2  mov     eax, [rcx+8]
0x18000bfe5  mov     rdi, rdx
0x18000bfe8  mov     rbx, [rbp+30h+arg_28]
0x18000bfec  mov     r14, rcx
0x18000bfef  test    r8b, r8b
0x18000bff2  jz      loc_18000C470
0x18000bff8  test    eax, eax
0x18000bffa  jnz     loc_18000C294
0x18000c000  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 1
0x18000c007  jz      loc_18000C12A
0x18000c00d  mov     rax, [rdi+18h]
0x18000c011  mov     [r11-0E0h], rax
0x18000c018  movzx   eax, word ptr [rbx+0A8h]
0x18000c01f  mov     word ptr [rsp+1B0h+var_E0], ax
0x18000c027  mov     rax, [rbx]
0x18000c02a  mov     [r11-0F0h], rax
0x18000c031  mov     rax, [rbx+58h]
0x18000c035  mov     [r11-0F8h], rax
0x18000c03c  mov     rax, [rbx+50h]
0x18000c040  mov     [r11-100h], rax
0x18000c047  mov     rax, [rbx+48h]
0x18000c04b  mov     [r11-108h], rax
0x18000c052  mov     rax, [rbx+40h]
0x18000c056  mov     [r11-110h], rax
0x18000c05d  mov     rax, [rbx+0A0h]
0x18000c064  mov     rdx, [rdx+38h]
0x18000c068  mov     r9, [rdi+20h]
0x18000c06c  mov     [r11-118h], rax
0x18000c073  mov     rax, [rbx+98h]
0x18000c07a  movzx   ecx, word ptr [rdx]
0x18000c07d  movzx   r8d, word ptr [r9]
0x18000c081  mov     r9, [r9+8]
0x18000c085  mov     [r11-120h], rax
0x18000c08c  mov     rax, [rbx+90h]
0x18000c093  mov     [r11-128h], rax
0x18000c09a  mov     rax, [rbx+88h]
0x18000c0a1  mov     [r11-130h], rax
0x18000c0a8  mov     rax, [rbx+80h]
0x18000c0af  mov     [r11-138h], rax
0x18000c0b6  mov     rax, [rbx+78h]
0x18000c0ba  mov     [rsp+1B0h+var_138], rax
0x18000c0bf  mov     rax, [rbx+70h]
0x18000c0c3  mov     [rsp+1B0h+var_140], rax
0x18000c0c8  mov     rax, [rbx+68h]
0x18000c0cc  mov     [rsp+1B0h+var_148], rax
0x18000c0d1  mov     rax, [rbx+10h]
0x18000c0d5  mov     [rsp+1B0h+var_150], rax
0x18000c0da  mov     rax, [rbx+8]
0x18000c0de  mov     [rsp+1B0h+var_158], rax
0x18000c0e3  mov     rax, [rbx+38h]
0x18000c0e7  mov     [rsp+1B0h+var_160], rax
0x18000c0ec  mov     rax, [rbx+30h]
0x18000c0f0  mov     [rsp+1B0h+var_168], rax
0x18000c0f5  mov     rax, [rbx+28h]
0x18000c0f9  mov     [rsp+1B0h+var_170], rax
0x18000c0fe  mov     rax, [rbx+18h]
0x18000c102  mov     [rsp+1B0h+var_178], rax
0x18000c107  mov     rax, [rbx+20h]
0x18000c10b  mov     [rsp+1B0h+var_180], rax
0x18000c110  mov     rax, [rdx+8]
0x18000c114  shr     cx, 1
0x18000c117  mov     [rsp+1B0h+var_188], rax
0x18000c11c  shr     r8w, 1
0x18000c120  mov     word ptr [rsp+1B0h+var_190], cx
0x18000c125  call    McTemplateU0hzr0hzr2xxxxxiiiiiiiiiiiiiixhj_EventWriteTransfer
0x18000c12a  mov     eax, cs:dword_1800470B8
0x18000c130  cmp     eax, 5
0x18000c133  jbe     loc_18000D101
0x18000c139  call    _tlgKeywordOn
0x18000c13e  test    al, al
0x18000c140  jz      loc_18000D101
0x18000c146  mov     rcx, [rdi+10h]
0x18000c14a  lea     rdx, word_1800410BA
0x18000c151  mov     al, [rbp+30h+arg_38]
0x18000c154  mov     [rbp+30h+arg_10], al
0x18000c157  mov     rax, [rcx+10h]
0x18000c15b  mov     [rbp+30h+var_A0], rax
0x18000c15f  mov     rax, [rcx+8]
0x18000c163  mov     [rbp+30h+var_98], rax
0x18000c167  mov     rax, [rdi]
0x18000c16a  add     rax, 14h
0x18000c16e  mov     [rbp+30h+var_AC], 1
0x18000c175  mov     [rbp+30h+var_90], rax
0x18000c179  movzx   eax, word ptr [rbx+0A8h]
0x18000c180  mov     [rbp+30h+var_B0], eax
0x18000c183  mov     rax, [rbx]
0x18000c186  mov     [rbp+30h+var_88], rax
0x18000c18a  mov     rax, [rbx+18h]
0x18000c18e  mov     [rbp+30h+var_80], rax
0x18000c192  mov     rax, [rbx+20h]
0x18000c196  mov     [rbp+30h+var_78], rax
0x18000c19a  mov     eax, [rbp+30h+arg_20]
0x18000c19d  mov     [rbp+30h+var_A8], eax
0x18000c1a0  mov     rax, [rbx+58h]
0x18000c1a4  mov     [rbp+30h+var_70], rax
0x18000c1a8  mov     rax, [rbx+50h]
0x18000c1ac  mov     [rbp+30h+var_68], rax
0x18000c1b0  mov     rax, [rbx+48h]
0x18000c1b4  mov     [rbp+30h+var_60], rax
0x18000c1b8  mov     rax, [rbx+40h]
0x18000c1bc  mov     [rbp+30h+var_58], rax
0x18000c1c0  mov     rax, [rbx+10h]
0x18000c1c4  mov     [rbp+30h+var_50], rax
0x18000c1c8  mov     rax, [rbx+8]
0x18000c1cc  mov     [rbp+30h+var_48], rax
0x18000c1d0  mov     rax, [rdi+18h]
0x18000c1d4  mov     [rbp+30h+var_40], rax
0x18000c1d8  lea     rax, [r14+34h]
0x18000c1dc  mov     [rbp+30h+var_38], rax
0x18000c1e0  lea     rax, [rbp+30h+arg_10]
0x18000c1e4  mov     [rsp+1B0h+var_108], rax
0x18000c1ec  lea     rax, [rbp+30h+var_A0]
0x18000c1f0  mov     [rsp+1B0h+var_110], rax
0x18000c1f8  lea     rax, [rbp+30h+var_98]
0x18000c1fc  mov     [rsp+1B0h+var_118], rax
0x18000c204  lea     rax, [rbp+30h+var_90]
0x18000c208  mov     [rsp+1B0h+var_120], rax
0x18000c210  lea     rax, [rbp+30h+var_B0]
0x18000c214  mov     [rsp+1B0h+var_128], rax
0x18000c21c  lea     rax, [rbp+30h+var_88]
0x18000c220  mov     [rsp+1B0h+var_130], rax
0x18000c228  lea     rax, [rbp+30h+var_AC]
0x18000c22c  mov     [rsp+1B0h+var_138], rax
0x18000c231  lea     rax, [rbp+30h+var_80]
0x18000c235  mov     [rsp+1B0h+var_140], rax
0x18000c23a  lea     rax, [rbp+30h+var_78]
0x18000c23e  mov     [rsp+1B0h+var_148], rax
0x18000c243  lea     rax, [rbp+30h+var_A8]
0x18000c247  mov     [rsp+1B0h+var_150], rax
0x18000c24c  lea     rax, [rbp+30h+var_70]
0x18000c250  mov     [rsp+1B0h+var_158], rax
0x18000c255  lea     rax, [rbp+30h+var_68]
0x18000c259  mov     [rsp+1B0h+var_160], rax
0x18000c25e  lea     rax, [rbp+30h+var_60]
0x18000c262  mov     [rsp+1B0h+var_168], rax
0x18000c267  lea     rax, [rbp+30h+var_58]
0x18000c26b  mov     [rsp+1B0h+var_170], rax
0x18000c270  lea     rax, [rbp+30h+var_50]
0x18000c274  mov     [rsp+1B0h+var_178], rax
0x18000c279  lea     rax, [rbp+30h+var_48]
0x18000c27d  mov     [rsp+1B0h+var_180], rax
0x18000c282  lea     rax, [rbp+30h+var_40]
0x18000c286  mov     [rsp+1B0h+var_188], rax
0x18000c28b  lea     rax, [rbp+30h+var_38]
0x18000c28f  jmp     loc_18000D0F7
0x18000c294  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 8
0x18000c29b  mov     esi, [rbp+30h+arg_30]
0x18000c29e  jz      loc_18000C3F9
0x18000c2a4  mov     rcx, [rdx+10h]
0x18000c2a8  mov     rax, [rdi+18h]
0x18000c2ac  mov     [rsp+0F8h], rax
0x18000c2b4  mov     r9, [rdx+20h]
0x18000c2b8  mov     rax, [rcx+10h]
0x18000c2bc  mov     [rsp+1B0h+var_C0], rax
0x18000c2c4  mov     rax, [rcx+8]
0x18000c2c8  mov     [rsp+1B0h+var_C8], rax
0x18000c2d0  mov     eax, [rcx]
0x18000c2d2  mov     dword ptr [rsp+1B0h+var_D0], eax
0x18000c2d9  movzx   eax, word ptr [rbx+0A8h]
0x18000c2e0  mov     word ptr [rsp+1B0h+var_D8], ax
0x18000c2e8  mov     rax, [rbx]
0x18000c2eb  mov     [rsp+1B0h+var_E0], rax
0x18000c2f3  mov     rax, [rbx+58h]
0x18000c2f7  mov     r10, [rdx+38h]
0x18000c2fb  movzx   r8d, word ptr [r9]
0x18000c2ff  mov     r9, [r9+8]
0x18000c303  mov     dword ptr [rsp+1B0h+var_E8], esi
0x18000c30a  mov     [rsp+1B0h+var_F0], rax
0x18000c312  mov     rax, [rbx+50h]
0x18000c316  mov     [rsp+1B0h+var_F8], rax
0x18000c31e  mov     rax, [rbx+48h]
0x18000c322  mov     [rsp+1B0h+var_100], rax
0x18000c32a  mov     rax, [rbx+40h]
0x18000c32e  mov     [rsp+1B0h+var_108], rax
0x18000c336  mov     rax, [rbx+0A0h]
0x18000c33d  movzx   edx, word ptr [r10]
0x18000c341  mov     [rsp+1B0h+var_110], rax
0x18000c349  mov     rax, [rbx+98h]
0x18000c350  mov     [rsp+1B0h+var_118], rax
0x18000c358  mov     rax, [rbx+90h]
0x18000c35f  mov     [rsp+1B0h+var_120], rax
0x18000c367  mov     rax, [rbx+88h]
0x18000c36e  mov     [rsp+1B0h+var_128], rax
0x18000c376  mov     rax, [rbx+80h]
0x18000c37d  mov     [rsp+1B0h+var_130], rax
0x18000c385  mov     rax, [rbx+78h]
0x18000c389  mov     [rsp+1B0h+var_138], rax
0x18000c38e  mov     rax, [rbx+70h]
0x18000c392  mov     [rsp+1B0h+var_140], rax
0x18000c397  mov     rax, [rbx+68h]
0x18000c39b  mov     [rsp+1B0h+var_148], rax
0x18000c3a0  mov     rax, [rbx+10h]
0x18000c3a4  mov     [rsp+1B0h+var_150], rax
0x18000c3a9  mov     rax, [rbx+8]
0x18000c3ad  mov     [rsp+1B0h+var_158], rax
0x18000c3b2  mov     rax, [rbx+38h]
0x18000c3b6  mov     [rsp+1B0h+var_160], rax
0x18000c3bb  mov     rax, [rbx+30h]
0x18000c3bf  mov     [rsp+1B0h+var_168], rax
0x18000c3c4  mov     rax, [rbx+28h]
0x18000c3c8  mov     [rsp+1B0h+var_170], rax
0x18000c3cd  mov     rax, [rbx+18h]
0x18000c3d1  mov     [rsp+1B0h+var_178], rax
0x18000c3d6  mov     rax, [rbx+20h]
0x18000c3da  mov     [rsp+1B0h+var_180], rax
0x18000c3df  mov     rax, [r10+8]
0x18000c3e3  shr     dx, 1
0x18000c3e6  mov     [rsp+1B0h+var_188], rax
0x18000c3eb  shr     r8w, 1
0x18000c3ef  mov     word ptr [rsp+1B0h+var_190], dx
0x18000c3f4  call    McTemplateU0hzr0hzr2xxxxxiiiiiiiiiiiiiiqxhqiij_EventWriteTransfer
0x18000c3f9  mov     eax, cs:dword_1800470B8
0x18000c3ff  cmp     eax, 5
0x18000c402  jbe     loc_18000D101
0x18000c408  call    _tlgKeywordOn
0x18000c40d  test    al, al
0x18000c40f  jz      loc_18000D101
0x18000c415  mov     rcx, [rdi+10h]
0x18000c419  lea     rdx, byte_180040F6F
0x18000c420  mov     al, [rbp+30h+arg_38]
0x18000c423  mov     [rbp+30h+arg_10], al
0x18000c426  mov     rax, [rcx+10h]
0x18000c42a  mov     [rbp+30h+var_38], rax
0x18000c42e  mov     rax, [rcx+8]
0x18000c432  mov     [rbp+30h+var_40], rax
0x18000c436  mov     rax, [rdi]
0x18000c439  add     rax, 14h
0x18000c43d  mov     [rbp+30h+var_AC], esi
0x18000c440  mov     [rbp+30h+var_48], rax
0x18000c444  movzx   eax, word ptr [rbx+0A8h]
0x18000c44b  mov     [rbp+30h+var_A8], eax
0x18000c44e  mov     rax, [rbx]
0x18000c451  mov     [rbp+30h+var_50], rax
0x18000c455  mov     rax, [rbx+18h]
0x18000c459  mov     [rbp+30h+var_58], rax
0x18000c45d  mov     rax, [rbx+20h]
0x18000c461  mov     [rbp+30h+var_60], rax
0x18000c465  mov     eax, [rbp+30h+arg_20]
0x18000c468  mov     [rbp+30h+var_B0], eax
0x18000c46b  jmp     loc_18000D008
0x18000c470  mov     esi, [rbp+30h+arg_20]
0x18000c473  test    r9b, r9b
0x18000c476  jz      loc_18000CA1E
0x18000c47c  test    eax, eax
0x18000c47e  jnz     loc_18000C735
0x18000c484  test    esi, esi
0x18000c486  js      loc_18000C5BC
0x18000c48c  test    cs:Microsoft_Windows_DataIntegrityScanEnableBits, 1
0x18000c493  jz      loc_18000C6F0
0x18000c499  mov     rcx, [rdx+38h]
0x18000c49d  mov     r9, [rdx+20h]
0x18000c4a1  mov     rax, [rdi+18h]
0x18000c4a5  mov     [rsp+1B0h+var_D8], rax
0x18000c4ad  mov     rax, [rbx]
0x18000c4b0  mov     [rsp+1B0h+var_E0], rax
0x18000c4b8  mov     rax, [rbx+58h]
0x18000c4bc  mov     [rsp+1B0h+var_E8], rax
0x18000c4c4  mov     rax, [rbx+50h]
0x18000c4c8  mov     [rsp+1B0h+var_F0], rax
0x18000c4d0  mov     rax, [rbx+48h]
0x18000c4d4  mov     [rsp+1B0h+var_F8], rax
0x18000c4dc  mov     rax, [rbx+40h]
0x18000c4e0  mov     [rsp+1B0h+var_100], rax
0x18000c4e8  mov     rax, [rbx+0A0h]
0x18000c4ef  movzx   edx, word ptr [rcx]
0x18000c4f2  mov     [rsp+1B0h+var_108], rax
0x18000c4fa  mov     rax, [rbx+98h]
0x18000c501  movzx   r8d, word ptr [r9]
0x18000c505  mov     [rsp+1B0h+var_110], rax
0x18000c50d  mov     rax, [rbx+90h]
0x18000c514  mov     [rsp+1B0h+var_118], rax
0x18000c51c  mov     rax, [rbx+88h]
0x18000c523  mov     [rsp+1B0h+var_120], rax
0x18000c52b  mov     rax, [rbx+80h]
0x18000c532  mov     [rsp+1B0h+var_128], rax
0x18000c53a  mov     rax, [rbx+78h]
0x18000c53e  mov     [rsp+1B0h+var_130], rax
0x18000c546  mov     rax, [rbx+70h]
0x18000c54a  mov     [rsp+1B0h+var_138], rax
0x18000c54f  mov     rax, [rbx+68h]
0x18000c553  mov     [rsp+1B0h+var_140], rax
0x18000c558  mov     rax, [rbx+10h]
0x18000c55c  mov     [rsp+1B0h+var_148], rax
0x18000c561  mov     rax, [rbx+8]
0x18000c565  mov     [rsp+1B0h+var_150], rax
0x18000c56a  mov     rax, [rbx+38h]
0x18000c56e  mov     [rsp+1B0h+var_158], rax
0x18000c573  mov     rax, [rbx+30h]
0x18000c577  mov     [rsp+1B0h+var_160], rax
0x18000c57c  mov     rax, [rbx+28h]
0x18000c580  mov     [rsp+1B0h+var_168], rax
  ... truncated ...
```
