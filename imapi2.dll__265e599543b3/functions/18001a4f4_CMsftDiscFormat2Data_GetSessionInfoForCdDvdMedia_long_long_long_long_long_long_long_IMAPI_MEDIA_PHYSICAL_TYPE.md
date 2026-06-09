# CMsftDiscFormat2Data::GetSessionInfoForCdDvdMedia(long *,long *,long *,long *,long *,long *,long *,_IMAPI_MEDIA_PHYSICAL_TYPE)

- ea: `0x18001a4f4`
- end: `0x18001b0fb`
- name: `?GetSessionInfoForCdDvdMedia@CMsftDiscFormat2Data@@AEAAJPEAJ000000W4_IMAPI_MEDIA_PHYSICAL_TYPE@@@Z`
- size: `3079`
- prototype: `__int64 __fastcall(CMsftDiscFormat2Data *__hidden this, int *, int *, int *, int *, int *, int *, int *, enum _IMAPI_MEDIA_PHYSICAL_TYPE)`
- caller_count: `2`
- callee_count: `24`
- tags: `service_task`

## callers

- `0x180009120`
- `0x18001a3e0`

## callees

- `0x18000a5f0`
- `0x18000a86c`
- `0x1800140f4`
- `0x180014134`
- `0x180014180`
- `0x180014250`
- `0x180016778`
- `0x18001a4f4`
- `0x1800236b4`
- `0x180023718`
- `0x180023790`
- `0x1800237d8`
- `0x180023848`
- `0x180023a14`
- `0x180049138`
- `0x1800492a8`
- `0x18004932c`
- `0x1800493a4`
- `0x1800493ec`
- `0x180049590`
- `0x18004962c`
- `0x1800496c0`
- `0x1800496e4`
- `0x18004a010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18001a643`
- `ole32!CoTaskMemFree` at `0x18001a643`

## pseudocode

```c
__int64 __fastcall CMsftDiscFormat2Data::GetSessionInfoForCdDvdMedia(
        CMsftDiscFormat2Data *this,
        unsigned int *a2,
        unsigned int *a3,
        int *a4,
        int *a5,
        int *a6,
        int *a7,
        int *a8,
        enum _IMAPI_MEDIA_PHYSICAL_TYPE a9)
{
  bool v10; // zf
  char v11; // r14
  unsigned int v12; // esi
  __int64 v13; // rcx
  int v14; // edi
  void *v15; // rcx
  int v16; // eax
  unsigned int FirstTrackOfLastSession; // ebx
  unsigned int LastTrackOfLastSession; // ebx
  unsigned int v19; // eax
  __int64 v20; // rcx
  _QWORD *v21; // rcx
  __int128 v22; // xmm0
  __int64 v23; // rdx
  unsigned int v24; // ebx
  unsigned int NumberOfSessions; // r13d
  _BYTE *v26; // r8
  char v27; // al
  unsigned int v28; // r9d
  int v29; // r12d
  int v30; // r14d
  __int64 v31; // rdx
  unsigned int v32; // r11d
  unsigned int v33; // r14d
  PVOID *v34; // r10
  __int64 v35; // r8
  unsigned int v36; // eax
  int v37; // r10d
  unsigned int v38; // eax
  int v39; // eax
  unsigned int TrackSize; // eax
  unsigned int v41; // r15d
  int LastRecordedAddress; // r13d
  char v43; // al
  unsigned int v44; // esi
  unsigned int SessionNumber; // eax
  int v46; // esi
  unsigned int v47; // r12d
  _QWORD *v48; // rcx
  int v49; // edx
  __int64 v50; // rcx
  unsigned int LastPossibleLeadoutStartTimeAsLba; // [rsp+68h] [rbp-71h]
  __int128 v53; // [rsp+78h] [rbp-61h] BYREF
  LPVOID pv[2]; // [rsp+88h] [rbp-51h] BYREF
  unsigned __int8 *v55; // [rsp+98h] [rbp-41h] BYREF
  __int64 v56; // [rsp+A0h] [rbp-39h]
  unsigned int v57; // [rsp+A8h] [rbp-31h]
  _BYTE *v58; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-21h]
  _BYTE *v60; // [rsp+C0h] [rbp-19h] BYREF
  __int64 v61; // [rsp+C8h] [rbp-11h]

  *a2 = 0;
  v10 = a9 == IMAPI_MEDIA_TYPE_CDR;
  v11 = 0;
  *a5 = -1;
  v12 = 0;
  *a3 = 0;
  *a4 = -1;
  v55 = 0;
  *a6 = -1;
  v56 = 0;
  v60 = 0;
  v61 = 0;
  *a7 = 0;
  v58 = 0;
  v59 = 0;
  *a8 = 0;
  if ( v10 || a9 == IMAPI_MEDIA_TYPE_CDRW )
  {
    v13 = *((_QWORD *)this + 27);
    pv[0] = 0;
    a9 = IMAPI_MEDIA_TYPE_UNKNOWN;
    v14 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, LPVOID *, enum _IMAPI_MEDIA_PHYSICAL_TYPE *))(*(_QWORD *)v13 + 104LL))(
            v13,
            5,
            0,
            pv,
            &a9);
    if ( v14 < 0 )
      goto LABEL_146;
    v15 = pv[0];
    if ( (*((_BYTE *)pv[0] + 2) & 0xF) == 0 && (*((_BYTE *)pv[0] + 3) & 0x20) != 0 )
    {
      v12 = *((unsigned __int8 *)pv[0] + 13)
          | ((*((unsigned __int8 *)pv[0] + 12)
            | ((*((unsigned __int8 *)pv[0] + 11) | (*((unsigned __int8 *)pv[0] + 10) << 8)) << 8)) << 8);
      if ( v12 )
      {
        v11 = 1;
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            317,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            (unsigned int)v14);
          v15 = pv[0];
        }
        v14 = -1062599937;
      }
    }
    CoTaskMemFree(v15);
    if ( v14 < 0 )
      goto LABEL_146;
  }
  v16 = CMsftDiscInformation::Init((CMsftDiscInformation *)&v55, *((struct IDiscRecorder2Ex **)this + 27));
  v14 = v16;
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        318,
        &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
        (unsigned int)v16);
    }
    goto LABEL_146;
  }
  FirstTrackOfLastSession = CMsftDiscInformation::get_FirstTrackOfLastSession((CMsftDiscInformation *)&v55);
  if ( FirstTrackOfLastSession != CMsftDiscInformation::get_LastTrackOfLastSession((CMsftDiscInformation *)&v55) )
  {
    v14 = -1062599678;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 2u )
    {
      pv[0] = (LPVOID)0x7FFF;
      pv[1] = v55;
      if ( (unsigned int)v56 <= 0x7FFF )
        LOWORD(pv[0]) = v56;
      LastTrackOfLastSession = CMsftDiscInformation::get_LastTrackOfLastSession((CMsftDiscInformation *)&v55);
      v19 = CMsftDiscInformation::get_FirstTrackOfLastSession((CMsftDiscInformation *)&v55);
      v20 = *((_QWORD *)WPP_GLOBAL_Control + 37);
      v53 = *(_OWORD *)pv;
      WPP_SF_DD_HEX_(v20, 319, (unsigned int)&v53, v19, LastTrackOfLastSession, (__int64)&v53);
    }
    goto LABEL_146;
  }
  if ( !CMsftDiscInformation::get_NumberOfSessions((CMsftDiscInformation *)&v55) )
  {
    v14 = -1062599937;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 2u )
    {
      goto LABEL_146;
    }
    pv[0] = (LPVOID)0x7FFF;
    pv[1] = v55;
    if ( (unsigned int)v56 <= 0x7FFF )
      LOWORD(pv[0]) = v56;
    v22 = *(_OWORD *)pv;
    v23 = 320;
    goto LABEL_145;
  }
  LastPossibleLeadoutStartTimeAsLba = CMsftDiscInformation::get_LastPossibleLeadoutStartTimeAsLba((CMsftDiscInformation *)&v55);
  v57 = CMsftDiscInformation::get_LastTrackOfLastSession((CMsftDiscInformation *)&v55);
  v24 = v57;
  NumberOfSessions = CMsftDiscInformation::get_NumberOfSessions((CMsftDiscInformation *)&v55);
  v14 = CMsftTrackInformation::Init(
          (CMsftTrackInformation *)&v60,
          *((struct IDiscRecorder2Ex **)this + 27),
          v24,
          IMAPI_READ_TRACK_ADDRESS_TYPE_TRACK,
          0);
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
    {
      WPP_SF_ddD(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        321,
        &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
        v24,
        v24,
        v14);
    }
    goto LABEL_146;
  }
  v26 = v60;
  v27 = v60[6];
  if ( v27 < 0 )
  {
    v14 = -1062599678;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 2u )
    {
      goto LABEL_146;
    }
    pv[0] = (LPVOID)0x7FFF;
    pv[1] = v60;
    if ( (unsigned int)v61 <= 0x7FFF )
      LOWORD(pv[0]) = v61;
    v22 = *(_OWORD *)pv;
    v23 = 322;
LABEL_145:
    v50 = v21[37];
    v53 = v22;
    WPP_SF__HEX_(v50, v23, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, &v53);
    goto LABEL_146;
  }
  if ( (v27 & 0x40) == 0 )
  {
    v14 = -1062599678;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 2u )
    {
      goto LABEL_146;
    }
    *(_QWORD *)&v53 = 0x7FFF;
    *((_QWORD *)&v53 + 1) = v60;
    if ( (unsigned int)v61 <= 0x7FFF )
      LOWORD(v53) = v61;
    v23 = 323;
    goto LABEL_144;
  }
  v28 = v61;
  if ( (unsigned int)v61 < 0x1C )
  {
    v14 = -1062599937;
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 305) < 2u )
    {
      goto LABEL_146;
    }
    *(_QWORD *)&v53 = 0x7FFF;
    *((_QWORD *)&v53 + 1) = v60;
    LOWORD(v53) = v61;
    v23 = 324;
LABEL_144:
    v22 = v53;
    goto LABEL_145;
  }
  v29 = (unsigned __int8)v60[11]
      | (((unsigned __int8)v60[10] | (((unsigned __int8)v60[9] | ((unsigned __int8)v60[8] << 8)) << 8)) << 8);
  v10 = v11 == 0;
  LODWORD(pv[0]) = v29;
  v30 = (unsigned __int8)v60[16];
  if ( v10 )
  {
    v33 = (unsigned __int8)v60[19] | (((unsigned __int8)v60[18] | (((unsigned __int8)v60[17] | (v30 << 8)) << 8)) << 8);
    TrackSize = CMsftTrackInformation::get_TrackSize((CMsftTrackInformation *)&v60);
    v34 = (PVOID *)WPP_GLOBAL_Control;
    v35 = v29 + TrackSize;
    LastPossibleLeadoutStartTimeAsLba = v29 + TrackSize;
  }
  else
  {
    v31 = (LastPossibleLeadoutStartTimeAsLba - v29 + 5) % (v12 + 7);
    v32 = v12 * ((LastPossibleLeadoutStartTimeAsLba - v29 + 5) / (v12 + 7));
    v33 = (unsigned __int8)v60[19] | (((unsigned __int8)v60[18] | (((unsigned __int8)v60[17] | (v30 << 8)) << 8)) << 8);
    if ( v33 == v32 )
    {
      v33 = (v12 + 7) * v33 / v12;
      v36 = CMsftTrackInformation::get_TrackSize((CMsftTrackInformation *)&v60);
      v38 = v37 * v36;
      v34 = (PVOID *)WPP_GLOBAL_Control;
      v31 = v38 % v12;
      v39 = v38 / v12;
      v35 = (unsigned int)(v29 + v39);
      LastPossibleLeadoutStartTimeAsLba = v29 + v39;
    }
    else
    {
      if ( v33 > v12 + LastPossibleLeadoutStartTimeAsLba - v29 + 11
        || v33 < LastPossibleLeadoutStartTimeAsLba - v29 - v12 - 1 )
      {
        v33 = 0;
        v14 = -1062599937;
      }
      else
      {
        LastPossibleLeadoutStartTimeAsLba = v29 + CMsftTrackInformation::get_TrackSize((CMsftTrackInformation *)&v60);
      }
      v34 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 2u )
      {
        *((_QWORD *)&v53 + 1) = v26;
        *(_QWORD *)&v53 = 0x7FFF;
        if ( v28 <= 0x7FFF )
          LOWORD(v53) = v28;
        WPP_SF_DD_HEX_(*((_QWORD *)WPP_GLOBAL_Control + 37), 325, (_DWORD)v26, v32, v12, (__int64)&v53);
        v34 = (PVOID *)WPP_GLOBAL_Control;
      }
      v35 = LastPossibleLeadoutStartTimeAsLba;
    }
    if ( v14 < 0 )
      goto LABEL_146;
  }
  v41 = NumberOfSessions - 1;
  LastRecordedAddress = -1;
  if ( v41 )
  {
    v43 = 0;
    v44 = v41;
LABEL_66:
    LOBYTE(a9) = v43;
    while ( v44 < v57 )
    {
      if ( v43 )
      {
        v35 = LastPossibleLeadoutStartTimeAsLba;
        goto LABEL_91;
      }
      v14 = CMsftTrackInformation::Init(
              (CMsftTrackInformation *)&v58,
              *((struct IDiscRecorder2Ex **)this + 27),
              v44,
              IMAPI_READ_TRACK_ADDRESS_TYPE_TRACK,
              1u);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          WPP_SF_ddD(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            326,
            &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            v44,
            v44,
            v14);
        }
        goto LABEL_146;
      }
      if ( (unsigned int)v59 < 0x1C )
      {
        v14 = -1062599937;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
        {
          *((_QWORD *)&v53 + 1) = v58;
          *(_QWORD *)&v53 = 0x7FFF;
          LOWORD(v53) = v59;
          WPP_SF_dD_HEX_(
            *((_QWORD *)WPP_GLOBAL_Control + 37),
            327,
            (unsigned int)&WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
            v44,
            v44,
            (__int64)&v53);
        }
        goto LABEL_146;
      }
      SessionNumber = CMsftTrackInformation::get_SessionNumber((CMsftTrackInformation *)&v58);
      if ( SessionNumber == v41 )
      {
        v34 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 5u )
        {
          WPP_SF_DDDd(*((_QWORD *)WPP_GLOBAL_Control + 37), 328, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
          v34 = (PVOID *)WPP_GLOBAL_Control;
        }
        v43 = 1;
        ++v44;
        goto LABEL_66;
      }
      v34 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_dDdDdD(
          *((_QWORD *)WPP_GLOBAL_Control + 37),
          329,
          &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids,
          v44,
          v44,
          SessionNumber,
          SessionNumber,
          v41,
          v41);
        v34 = (PVOID *)WPP_GLOBAL_Control;
      }
      v43 = a9;
      ++v44;
    }
    goto LABEL_92;
  }
LABEL_91:
  v46 = -1;
  if ( v41 )
  {
LABEL_92:
    if ( CMsftTrackInformation::get_SessionNumber((CMsftTrackInformation *)&v58) != v41 )
    {
      v14 = -1062599678;
      if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 308) & 4) != 0 && *((_BYTE *)v34 + 305) >= 2u )
        WPP_SF_DDDd(v34[37], 330, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
      goto LABEL_146;
    }
    LastPossibleLeadoutStartTimeAsLba = v35;
    if ( (v58[5] & 4) != 0 )
    {
      LastPossibleLeadoutStartTimeAsLba = v35;
      v46 = (unsigned __int8)v58[11]
          | (((unsigned __int8)v58[10] | (((unsigned __int8)v58[9] | ((unsigned __int8)v58[8] << 8)) << 8)) << 8);
    }
    else
    {
      if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 308) & 4) != 0 && *((_BYTE *)v34 + 305) >= 3u )
      {
        WPP_SF_(v34[37], 331, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids);
        v34 = (PVOID *)WPP_GLOBAL_Control;
      }
      v46 = -1;
    }
  }
  if ( v57 > v55[3] )
  {
    v47 = v57 - 1;
    v14 = CMsftTrackInformation::Init(
            (CMsftTrackInformation *)&v58,
            *((struct IDiscRecorder2Ex **)this + 27),
            v57 - 1,
            IMAPI_READ_TRACK_ADDRESS_TYPE_TRACK,
            1u);
    if ( v14 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 305) >= 3u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 37), 332, &WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, v47, v14);
      }
      goto LABEL_146;
    }
    if ( (v58[6] & 0x40) != 0 )
    {
      v14 = -1062599678;
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 2u )
      {
        goto LABEL_146;
      }
      *((_QWORD *)&v53 + 1) = v58;
      *(_QWORD *)&v53 = 0x7FFF;
      if ( (unsigned int)v59 <= 0x7FFF )
        LOWORD(v53) = v59;
      v49 = 333;
      goto LABEL_118;
    }
    if ( (v58[5] & 0x20) != 0 )
    {
      v14 = -1062599678;
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 308) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 305) < 2u )
      {
        goto LABEL_146;
      }
      *((_QWORD *)&v53 + 1) = v58;
      *(_QWORD *)&v53 = 0x7FFF;
      if ( (unsigned int)v59 <= 0x7FFF )
        LOWORD(v53) = v59;
      v49 = 334;
LABEL_118:
      WPP_SF_d_HEX_(v48[37], v49, (unsigned int)&WPP_539367e8d73e3780733cc4391ef3a150_Traceguids, v47, (__int64)&v53);
      goto LABEL_146;
    }
    if ( CMsftTrackInformation::get_LastRecordedAddressValid((CMsftTrackInformation *)&v58) )
      LastRecordedAddress = CMsftTrackInformation::get_LastRecordedAddress((CMsftTrackInformation *)&v58);
    v34 = (PVOID *)WPP_GLOBAL_Control;
    v29 = (int)pv[0];
  }
  if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 308) & 4) != 0 && *((_BYTE *)v34 + 305) >= 4u )
    WPP_SF_dDdDdDdD(v34[37], v31, v35, v33, v33, v29, v29, v46, v46, LastRecordedAddress, LastRecordedAddress);
  *a2 = LastPossibleLeadoutStartTimeAsLba;
  *a3 = v33;
  *a4 = v29;
  *a5 = v46;
  *a6 = LastRecordedAddress;
  *a7 = v41 + 1;
  *a8 = v57;
LABEL_146:
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&v58);
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&v60);
  CMsftDiscInformation::~CMsftDiscInformation((CMsftDiscInformation *)&v55);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001a4f4  mov     rax, rsp
0x18001a4f7  mov     [rax+20h], r9
0x18001a4fb  mov     [rax+18h], r8
0x18001a4ff  mov     [rax+10h], rdx
0x18001a503  mov     [rax+8], rcx
0x18001a507  push    rbp
0x18001a508  push    rbx
0x18001a509  push    rsi
0x18001a50a  push    rdi
0x18001a50b  push    r12
0x18001a50d  push    r13
0x18001a50f  push    r14
0x18001a511  push    r15
0x18001a513  lea     rbp, [rax-47h]
0x18001a517  sub     rsp, 0D8h
0x18001a51e  mov     rax, [rbp+3Fh+arg_20]
0x18001a522  lea     rbx, WPP_GLOBAL_Control
0x18001a529  xor     r15d, r15d
0x18001a52c  mov     r12, rcx
0x18001a52f  or      ecx, 0FFFFFFFFh
0x18001a532  mov     [rdx], r15d
0x18001a535  cmp     [rbp+3Fh+arg_40], 2
0x18001a53c  mov     r14b, r15b
0x18001a53f  mov     [rax], ecx
0x18001a541  mov     esi, r15d
0x18001a544  mov     rax, [rbp+3Fh+arg_28]
0x18001a548  mov     r13b, 4
0x18001a54b  mov     [r8], r15d
0x18001a54e  mov     [r9], ecx
0x18001a551  mov     [rbp+3Fh+var_80], r15
0x18001a555  mov     [rax], ecx
0x18001a557  mov     rax, [rbp+3Fh+arg_30]
0x18001a55b  mov     [rbp+3Fh+var_78], r15
0x18001a55f  mov     [rbp+3Fh+var_58], r15
0x18001a563  mov     [rbp+3Fh+var_50], r15
0x18001a567  mov     [rax], r15d
0x18001a56a  mov     rax, [rbp+3Fh+arg_38]
0x18001a571  mov     [rbp+3Fh+var_68], r15
0x18001a575  mov     [rbp+3Fh+var_60], r15
0x18001a579  mov     [rax], r15d
0x18001a57c  jz      short loc_18001A58B
0x18001a57e  cmp     [rbp+3Fh+arg_40], 3
0x18001a585  jnz     loc_18001A651
0x18001a58b  mov     rcx, [r12+0D8h]
0x18001a593  lea     rdx, [rbp+3Fh+arg_40]
0x18001a59a  mov     [rbp+3Fh+pv], r15
0x18001a59e  lea     r9, [rbp+3Fh+pv]
0x18001a5a2  mov     [rbp+3Fh+arg_40], r15d
0x18001a5a9  xor     r8d, r8d
0x18001a5ac  mov     qword ptr [rsp+110h+var_F0], rdx
0x18001a5b1  mov     rax, [rcx]
0x18001a5b4  lea     edx, [r8+5]
0x18001a5b8  mov     rax, [rax+68h]
0x18001a5bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5c1  mov     edi, eax
0x18001a5c3  test    eax, eax
0x18001a5c5  js      loc_18001B0CA
0x18001a5cb  mov     rcx, [rbp+3Fh+pv]
0x18001a5cf  test    byte ptr [rcx+2], 0Fh
0x18001a5d3  jnz     short loc_18001A643
0x18001a5d5  test    byte ptr [rcx+3], 20h
0x18001a5d9  jz      short loc_18001A643
0x18001a5db  movzx   eax, byte ptr [rcx+0Bh]
0x18001a5df  movzx   esi, byte ptr [rcx+0Ah]
0x18001a5e3  shl     esi, 8
0x18001a5e6  or      esi, eax
0x18001a5e8  movzx   eax, byte ptr [rcx+0Ch]
0x18001a5ec  shl     esi, 8
0x18001a5ef  or      esi, eax
0x18001a5f1  movzx   eax, byte ptr [rcx+0Dh]
0x18001a5f5  shl     esi, 8
0x18001a5f8  or      esi, eax
0x18001a5fa  jbe     short loc_18001A601
0x18001a5fc  mov     r14b, 1
0x18001a5ff  jmp     short loc_18001A643
0x18001a601  mov     rax, cs:WPP_GLOBAL_Control
0x18001a608  cmp     rax, rbx
0x18001a60b  jz      short loc_18001A63E
0x18001a60d  test    [rax+134h], r13b
0x18001a614  jz      short loc_18001A63E
0x18001a616  cmp     byte ptr [rax+131h], 3
0x18001a61d  jb      short loc_18001A63E
0x18001a61f  mov     rcx, [rax+128h]
0x18001a626  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18001a62d  mov     edx, 13Dh
0x18001a632  mov     r9d, edi
0x18001a635  call    WPP_SF_d
0x18001a63a  mov     rcx, [rbp+3Fh+pv]; pv
0x18001a63e  mov     edi, 0C0AA02FFh
0x18001a643  call    cs:__imp_CoTaskMemFree
0x18001a649  test    edi, edi
0x18001a64b  js      loc_18001B0CA
0x18001a651  mov     rdx, [r12+0D8h]; struct IDiscRecorder2Ex *
0x18001a659  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a65d  call    ?Init@CMsftDiscInformation@@QEAAJPEAUIDiscRecorder2Ex@@@Z; CMsftDiscInformation::Init(IDiscRecorder2Ex *)
0x18001a662  mov     edi, eax
0x18001a664  test    eax, eax
0x18001a666  jns     short loc_18001A6B2
0x18001a668  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a66f  cmp     rcx, rbx
0x18001a672  jz      loc_18001B0CA
0x18001a678  test    [rcx+134h], r13b
0x18001a67f  jz      loc_18001B0CA
0x18001a685  cmp     byte ptr [rcx+131h], 3
0x18001a68c  jb      loc_18001B0CA
0x18001a692  mov     rcx, [rcx+128h]
0x18001a699  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18001a6a0  mov     edx, 13Eh
0x18001a6a5  mov     r9d, eax
0x18001a6a8  call    WPP_SF_d
0x18001a6ad  jmp     loc_18001B0CA
0x18001a6b2  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a6b6  call    ?get_FirstTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_FirstTrackOfLastSession(void)
0x18001a6bb  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a6bf  mov     ebx, eax
0x18001a6c1  call    ?get_LastTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_LastTrackOfLastSession(void)
0x18001a6c6  cmp     ebx, eax
0x18001a6c8  jz      loc_18001A771
0x18001a6ce  mov     edi, 0C0AA0402h
0x18001a6d3  mov     rax, cs:WPP_GLOBAL_Control
0x18001a6da  lea     rdx, WPP_GLOBAL_Control
0x18001a6e1  cmp     rax, rdx
0x18001a6e4  jz      loc_18001B0CA
0x18001a6ea  test    [rax+134h], r13b
0x18001a6f1  jz      loc_18001B0CA
0x18001a6f7  cmp     byte ptr [rax+131h], 2
0x18001a6fe  jb      loc_18001B0CA
0x18001a704  mov     rax, [rbp+3Fh+var_80]
0x18001a708  mov     ebx, 7FFFh
0x18001a70d  xorps   xmm0, xmm0
0x18001a710  movups  xmmword ptr [rbp+3Fh+pv], xmm0
0x18001a714  mov     [rbp+3Fh+pv+8], rax
0x18001a718  mov     eax, dword ptr [rbp+3Fh+var_78]
0x18001a71b  mov     word ptr [rbp+3Fh+pv], bx
0x18001a71f  cmp     eax, ebx
0x18001a721  ja      short loc_18001A727
0x18001a723  mov     word ptr [rbp+3Fh+pv], ax
0x18001a727  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a72b  call    ?get_LastTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_LastTrackOfLastSession(void)
0x18001a730  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a734  mov     ebx, eax
0x18001a736  call    ?get_FirstTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_FirstTrackOfLastSession(void)
0x18001a73b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a742  lea     r8, [rbp+3Fh+var_A0]
0x18001a746  movaps  xmm0, xmmword ptr [rbp+3Fh+pv]
0x18001a74a  mov     edx, 13Fh
0x18001a74f  mov     qword ptr [rsp+110h+var_E8], r8
0x18001a754  mov     r9d, eax
0x18001a757  mov     dword ptr [rsp+110h+var_F0], ebx
0x18001a75b  mov     rcx, [rcx+128h]
0x18001a762  movdqa  [rbp+3Fh+var_A0], xmm0
0x18001a767  call    WPP_SF_DD_HEX_
0x18001a76c  jmp     loc_18001B0CA
0x18001a771  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a775  call    ?get_NumberOfSessions@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_NumberOfSessions(void)
0x18001a77a  test    eax, eax
0x18001a77c  jnz     short loc_18001A7E5
0x18001a77e  mov     edi, 0C0AA02FFh
0x18001a783  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a78a  lea     rax, WPP_GLOBAL_Control
0x18001a791  cmp     rcx, rax
0x18001a794  jz      loc_18001B0CA
0x18001a79a  test    [rcx+134h], r13b
0x18001a7a1  jz      loc_18001B0CA
0x18001a7a7  cmp     byte ptr [rcx+131h], 2
0x18001a7ae  jb      loc_18001B0CA
0x18001a7b4  mov     rax, [rbp+3Fh+var_80]
0x18001a7b8  mov     ebx, 7FFFh
0x18001a7bd  xorps   xmm0, xmm0
0x18001a7c0  movups  xmmword ptr [rbp+3Fh+pv], xmm0
0x18001a7c4  mov     [rbp+3Fh+pv+8], rax
0x18001a7c8  mov     eax, dword ptr [rbp+3Fh+var_78]
0x18001a7cb  mov     word ptr [rbp+3Fh+pv], bx
0x18001a7cf  cmp     eax, ebx
0x18001a7d1  ja      short loc_18001A7D7
0x18001a7d3  mov     word ptr [rbp+3Fh+pv], ax
0x18001a7d7  movaps  xmm0, xmmword ptr [rbp+3Fh+pv]
0x18001a7db  mov     edx, 140h
0x18001a7e0  jmp     loc_18001B0AE
0x18001a7e5  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a7e9  call    ?get_LastPossibleLeadoutStartTimeAsLba@CMsftDiscInformation@@QEAAJXZ; CMsftDiscInformation::get_LastPossibleLeadoutStartTimeAsLba(void)
0x18001a7ee  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a7f2  mov     [rbp+3Fh+var_B0], eax
0x18001a7f5  mov     r15d, eax
0x18001a7f8  call    ?get_LastTrackOfLastSession@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_LastTrackOfLastSession(void)
0x18001a7fd  lea     rcx, [rbp+3Fh+var_80]; this
0x18001a801  mov     [rbp+3Fh+var_70], eax
0x18001a804  mov     ebx, eax
0x18001a806  call    ?get_NumberOfSessions@CMsftDiscInformation@@QEAAKXZ; CMsftDiscInformation::get_NumberOfSessions(void)
0x18001a80b  mov     rdx, [r12+0D8h]; struct IDiscRecorder2Ex *
0x18001a813  lea     rcx, [rbp+3Fh+var_58]; this
0x18001a817  mov     r9d, 1; enum _IMAPI_READ_TRACK_ADDRESS_TYPE
0x18001a81d  mov     [rsp+110h+var_F0], 0; unsigned __int8
0x18001a822  mov     r8d, ebx; unsigned int
0x18001a825  mov     r13d, eax
0x18001a828  call    ?Init@CMsftTrackInformation@@QEAAJPEAUIDiscRecorder2Ex@@KW4_IMAPI_READ_TRACK_ADDRESS_TYPE@@E@Z; CMsftTrackInformation::Init(IDiscRecorder2Ex *,ulong,_IMAPI_READ_TRACK_ADDRESS_TYPE,uchar)
0x18001a82d  mov     edi, eax
0x18001a82f  test    eax, eax
0x18001a831  jns     short loc_18001A88C
0x18001a833  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a83a  lea     rax, WPP_GLOBAL_Control
0x18001a841  cmp     rcx, rax
0x18001a844  jz      loc_18001B0CA
0x18001a84a  test    byte ptr [rcx+134h], 4
0x18001a851  jz      loc_18001B0CA
0x18001a857  cmp     byte ptr [rcx+131h], 3
0x18001a85e  jb      loc_18001B0CA
0x18001a864  mov     [rsp+110h+var_E8], edi
0x18001a868  mov     edx, 141h
0x18001a86d  mov     dword ptr [rsp+110h+var_F0], ebx
0x18001a871  mov     r9d, ebx
0x18001a874  mov     rcx, [rcx+128h]
0x18001a87b  lea     r8, WPP_539367e8d73e3780733cc4391ef3a150_Traceguids
0x18001a882  call    WPP_SF_ddD
0x18001a887  jmp     loc_18001B0CA
0x18001a88c  mov     r8, [rbp+3Fh+var_58]
0x18001a890  mov     al, [r8+6]
0x18001a894  test    al, al
0x18001a896  jns     short loc_18001A8FB
0x18001a898  mov     edi, 0C0AA0402h
0x18001a89d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a8a4  lea     rax, WPP_GLOBAL_Control
0x18001a8ab  cmp     rcx, rax
0x18001a8ae  jz      loc_18001B0CA
0x18001a8b4  test    byte ptr [rcx+134h], 4
0x18001a8bb  jz      loc_18001B0CA
0x18001a8c1  cmp     byte ptr [rcx+131h], 2
0x18001a8c8  jb      loc_18001B0CA
0x18001a8ce  mov     eax, dword ptr [rbp+3Fh+var_50]
0x18001a8d1  mov     ebx, 7FFFh
0x18001a8d6  xorps   xmm0, xmm0
0x18001a8d9  movups  xmmword ptr [rbp+3Fh+pv], xmm0
0x18001a8dd  mov     [rbp+3Fh+pv+8], r8
0x18001a8e1  mov     word ptr [rbp+3Fh+pv], bx
0x18001a8e5  cmp     eax, ebx
0x18001a8e7  ja      short loc_18001A8ED
0x18001a8e9  mov     word ptr [rbp+3Fh+pv], ax
0x18001a8ed  movaps  xmm0, xmmword ptr [rbp+3Fh+pv]
0x18001a8f1  mov     edx, 142h
0x18001a8f6  jmp     loc_18001B0AE
0x18001a8fb  test    al, 40h
0x18001a8fd  jz      loc_18001B05C
0x18001a903  mov     r9d, dword ptr [rbp+3Fh+var_50]
0x18001a907  cmp     r9d, 1Ch
0x18001a90b  jb      loc_18001B001
0x18001a911  movzx   eax, byte ptr [r8+9]
0x18001a916  mov     ebx, 7FFFh
0x18001a91b  movzx   r12d, byte ptr [r8+8]
0x18001a920  shl     r12d, 8
0x18001a924  or      r12d, eax
0x18001a927  movzx   eax, byte ptr [r8+0Ah]
0x18001a92c  shl     r12d, 8
0x18001a930  or      r12d, eax
0x18001a933  movzx   eax, byte ptr [r8+0Bh]
0x18001a938  shl     r12d, 8
0x18001a93c  or      r12d, eax
0x18001a93f  test    r14b, r14b
0x18001a942  mov     dword ptr [rbp+3Fh+pv], r12d
0x18001a946  movzx   r14d, byte ptr [r8+10h]
0x18001a94b  jz      loc_18001AA78
0x18001a951  shl     r14d, 8
0x18001a955  lea     r10d, [rsi+7]
0x18001a959  xor     edx, edx
0x18001a95b  mov     ecx, r15d
0x18001a95e  sub     ecx, r12d
0x18001a961  lea     eax, [rcx+5]
0x18001a964  div     r10d
0x18001a967  mov     r11d, eax
0x18001a96a  movzx   eax, byte ptr [r8+11h]
0x18001a96f  or      r14d, eax
0x18001a972  imul    r11d, esi
0x18001a976  movzx   eax, byte ptr [r8+12h]
0x18001a97b  shl     r14d, 8
0x18001a97f  or      r14d, eax
0x18001a982  movzx   eax, byte ptr [r8+13h]
0x18001a987  shl     r14d, 8
0x18001a98b  or      r14d, eax
0x18001a98e  cmp     r14d, r11d
0x18001a991  jz      loc_18001AA48
0x18001a997  mov     eax, r15d
0x18001a99a  sub     eax, r12d
0x18001a99d  add     eax, 0Bh
0x18001a9a0  add     eax, esi
0x18001a9a2  cmp     r14d, eax
0x18001a9a5  ja      short loc_18001A9C1
0x18001a9a7  sub     ecx, esi
0x18001a9a9  dec     ecx
0x18001a9ab  cmp     r14d, ecx
0x18001a9ae  jb      short loc_18001A9C1
0x18001a9b0  lea     rcx, [rbp+3Fh+var_58]; this
0x18001a9b4  call    ?get_TrackSize@CMsftTrackInformation@@QEAAKXZ; CMsftTrackInformation::get_TrackSize(void)
0x18001a9b9  add     eax, r12d
0x18001a9bc  mov     [rbp+3Fh+var_B0], eax
0x18001a9bf  jmp     short loc_18001A9C9
0x18001a9c1  xor     r14d, r14d
0x18001a9c4  mov     edi, 0C0AA02FFh
0x18001a9c9  mov     r10, cs:WPP_GLOBAL_Control
0x18001a9d0  lea     rax, WPP_GLOBAL_Control
0x18001a9d7  cmp     r10, rax
0x18001a9da  jz      short loc_18001AA3A
  ... truncated ...
```
