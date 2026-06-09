# CFveApi::StoreTrustedWimData(bool)

- ea: `0x1800c7ff8`
- end: `0x1800c8b47`
- name: `?StoreTrustedWimData@CFveApi@@IEAAJ_N@Z`
- size: `2895`
- prototype: `__int64 __fastcall(CFveApi *__hidden this, bool)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config`

## callers

- `0x1800c60fc`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180018b10`
- `0x18001b260`
- `0x18001de20`
- `0x18001f010`
- `0x180037edc`
- `0x180046a90`
- `0x180047570`
- `0x18004f700`
- `0x18004fce0`
- `0x18004fddc`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180053e64`
- `0x18005f05c`
- `0x1800600c0`
- `0x18009e740`
- `0x1800c7ff8`
- `0x18011efce`
- `0x18011f010`
- `0x18011f0d0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800c8aa1`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800c8aa1`
- `bcd!BcdCloseStore` at `0x1800c8acd`
- `bcd!BcdCloseStore` at `0x1800c8acd`
- `bcd!BcdOpenSystemStore` at `0x1800c8641`
- `bcd!BcdOpenSystemStore` at `0x1800c8641`
- `ext-ms-win-reinfo-query-l1-1-0!WinReGetConfig` at `0x1800c81f1`
- `ext-ms-win-reinfo-query-l1-1-0!WinReGetConfig` at `0x1800c81f1`

## string_xrefs

- `0x1800c83a7`: `VolumePath`
- `0x1800c893f`: `VolumePath`

## pseudocode

```c
__int64 __fastcall CFveApi::StoreTrustedWimData(CFveApi *this, char a2)
{
  __int64 v3; // r13
  unsigned __int16 v4; // r14
  __int64 v5; // rdx
  _DWORD *v6; // r15
  signed int v7; // ebx
  PVOID *v8; // rcx
  unsigned int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  unsigned int DoesRegKeyExist; // eax
  unsigned __int16 v15; // r8
  unsigned int KnownLastErrorHR; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // eax
  int Next; // eax
  int v22; // r15d
  __int64 v23; // rax
  const unsigned __int16 *LoggingVolumePath; // rax
  const unsigned __int16 *v25; // rdx
  const unsigned __int16 *LoggingVolumeDriveLetter; // rax
  const unsigned __int16 *v27; // rdx
  struct _FVEAPI_EVENT_DATA_COLLECTION *v28; // rdx
  PVOID *v29; // rcx
  int v30; // eax
  __int64 v31; // rax
  unsigned __int16 v32; // r14
  __int64 v33; // rcx
  int v34; // eax
  unsigned int v35; // eax
  int appended; // eax
  unsigned int v37; // eax
  __int64 v38; // rax
  const unsigned __int16 *v39; // rax
  const unsigned __int16 *v40; // rdx
  const unsigned __int16 *v41; // rax
  const unsigned __int16 *v42; // rdx
  unsigned int v44; // [rsp+20h] [rbp-E0h]
  unsigned int v45; // [rsp+20h] [rbp-E0h]
  unsigned int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+38h] [rbp-C8h]
  int v48; // [rsp+40h] [rbp-C0h]
  _WORD v50[2]; // [rsp+54h] [rbp-ACh] BYREF
  _DWORD *v51; // [rsp+58h] [rbp-A8h]
  __int64 v52; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v53; // [rsp+68h] [rbp-98h] BYREF
  __int64 v54; // [rsp+70h] [rbp-90h]
  __int64 v55; // [rsp+78h] [rbp-88h]
  __int64 v56; // [rsp+80h] [rbp-80h] BYREF
  __int64 v57; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v58; // [rsp+90h] [rbp-70h]
  __int128 **v59; // [rsp+98h] [rbp-68h] BYREF
  __int128 *v60; // [rsp+A0h] [rbp-60h]
  __int64 v61; // [rsp+A8h] [rbp-58h] BYREF
  __int64 *v62; // [rsp+B0h] [rbp-50h]
  __int128 ****v63; // [rsp+B8h] [rbp-48h] BYREF
  __int128 *v64; // [rsp+C0h] [rbp-40h]
  unsigned int v65; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v66; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v67; // [rsp+E0h] [rbp-20h]
  __int128 v68; // [rsp+F0h] [rbp-10h]
  __int128 *v69; // [rsp+100h] [rbp+0h] BYREF
  __int128 *v70; // [rsp+108h] [rbp+8h]
  const wchar_t *v71; // [rsp+110h] [rbp+10h]
  const unsigned __int16 *v72; // [rsp+118h] [rbp+18h]
  unsigned int *v73; // [rsp+120h] [rbp+20h]
  __int64 v74; // [rsp+128h] [rbp+28h]
  __int128 ***v75; // [rsp+130h] [rbp+30h] BYREF
  __int128 *v76; // [rsp+138h] [rbp+38h]
  const wchar_t *v77; // [rsp+140h] [rbp+40h]
  const wchar_t *v78; // [rsp+148h] [rbp+48h]
  unsigned int *v79; // [rsp+150h] [rbp+50h]
  __int64 v80; // [rsp+158h] [rbp+58h]
  __int128 v81; // [rsp+160h] [rbp+60h] BYREF
  __int128 v82; // [rsp+170h] [rbp+70h]
  __int128 v83; // [rsp+180h] [rbp+80h]
  _OWORD v84[3]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v85; // [rsp+1C0h] [rbp+C0h] BYREF
  int v86; // [rsp+1C8h] [rbp+C8h]
  char v87[1856]; // [rsp+694h] [rbp+594h] BYREF
  int v88; // [rsp+DD4h] [rbp+CD4h]
  _OWORD v89[2]; // [rsp+DD8h] [rbp+CD8h] BYREF
  unsigned int v90; // [rsp+DF8h] [rbp+CF8h]

  v3 = 0;
  v65 = 0;
  v52 = 0;
  memset_0(&v85, 0, 0xEA0u);
  v4 = 0;
  v56 = 0;
  v50[0] = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 75, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
  v51 = operator new[](0x3AE8u, (const struct std::nothrow_t *)&std::nothrow);
  v6 = v51;
  if ( v51 )
  {
    v9 = CFveApiBase::CheckInited(this);
    v7 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v9);
      if ( v7 < 0 )
        goto LABEL_122;
    }
    if ( !(unsigned __int8)IsWinReGetConfigPresent() )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      {
        v13 = 78;
LABEL_17:
        WPP_SF_(v12[2], v13, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
        goto LABEL_122;
      }
      goto LABEL_122;
    }
    DoesRegKeyExist = NgscbpDoesRegKeyExist(v11, v10, &v65);
    v7 = DoesRegKeyExist;
    if ( DoesRegKeyExist )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          79,
          &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
          DoesRegKeyExist);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 < 0 )
        goto LABEL_122;
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v65 )
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      {
        v13 = 80;
        goto LABEL_17;
      }
LABEL_122:
      operator delete[](v51);
      if ( v3 )
        FveDatumFree(v3);
      goto LABEL_124;
    }
    v85 = 3744;
    if ( !(unsigned int)WinReGetConfig(0, &v85) )
    {
      KnownLastErrorHR = NgscbGetKnownLastErrorHR();
      v7 = KnownLastErrorHR;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_122;
      v18 = 81;
      v19 = KnownLastErrorHR;
LABEL_33:
      WPP_SF_d(v17[2], v18, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v19);
      goto LABEL_122;
    }
    if ( !v86 )
    {
      v20 = CFveApiBase::EraseAll(this, 0x11u, v15);
      v7 = v20;
      if ( v20 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 82, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v20);
          v12 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v7 < 0 )
          goto LABEL_122;
      }
      else
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      {
        v13 = 83;
        goto LABEL_17;
      }
      goto LABEL_122;
    }
    if ( (*((_BYTE *)this + 352) & 4) != 0 )
    {
      Next = FveDatasetGetNext(*((_QWORD *)this + 146), 17, 0xFFFF, 0, (__int64)&v65);
      v22 = Next;
      if ( Next >= 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 84, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
        v23 = *((_QWORD *)this + 146);
        v71 = L"IdentityGuid";
        v73 = (unsigned int *)(v23 + 16);
        v57 = 0;
        v58 = 0;
        v69 = (__int128 *)&v59;
        v53 = 0;
        v70 = (__int128 *)&v59;
        v59 = &v69;
        v60 = (__int128 *)&v69;
        v54 = 0;
        v55 = 0;
        v72 = L"GUID";
        v74 = 16;
        v81 = 0;
        v82 = 0;
        v83 = 0;
        LoggingVolumePath = CFveApiBase::GetLoggingVolumePath(this);
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v81, v25, L"VolumePath", LoggingVolumePath, v44);
        if ( *(__int128 ****)v60 == &v59 )
        {
          *((_QWORD *)&v81 + 1) = v60;
          *(_QWORD *)&v81 = &v59;
          *(_QWORD *)v60 = &v81;
          v60 = &v81;
          v66 = 0;
          v67 = 0;
          v68 = 0;
          LoggingVolumeDriveLetter = CFveApiBase::GetLoggingVolumeDriveLetter(this);
          FveApiEventLogDeclareWSTRING(
            (struct _FVEAPI_EVENT_DATA *)&v66,
            v27,
            L"VolumeDriveLetter",
            LoggingVolumeDriveLetter,
            v45);
          if ( *(__int128 ****)v60 == &v59 )
          {
            *((_QWORD *)&v66 + 1) = v60;
            *(_QWORD *)&v66 = &v59;
            *(_QWORD *)v60 = &v66;
            v77 = L"hr";
            v65 = v7;
            v78 = L"HRESULT";
            v79 = &v65;
            v80 = 4;
            if ( (__int128 ***)v66 == &v59 )
            {
              v75 = &v59;
              v28 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v57;
              v76 = &v66;
              *(_QWORD *)&v66 = &v75;
              v60 = (__int128 *)&v75;
              v58 = FVEAPI_OP_WIM_BCD_MISMATCH_DETECTED;
LABEL_121:
              FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v53, v28);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v53);
              goto LABEL_122;
            }
          }
        }
        goto LABEL_131;
      }
      if ( Next == -1073741275 )
        goto LABEL_64;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          85,
          &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
          (unsigned int)Next);
      v7 = FromNtStatus(v22);
      if ( !v7 )
      {
LABEL_64:
        v29 = (PVOID *)WPP_GLOBAL_Control;
      }
      else
      {
        v29 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            86,
            &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
            (unsigned int)v7);
          v29 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v7 < 0 )
          goto LABEL_122;
      }
      if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 8) != 0 )
        WPP_SF_(v29[2], 87, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
      v6 = v51;
    }
    v7 = CFveApiBase::EraseAll(this, 0x11u, v15);
    if ( v7 )
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          88,
          &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
          (unsigned int)v7);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v7 < 0 )
        goto LABEL_122;
    }
    else
    {
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !v88 )
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
      {
        v13 = 89;
        goto LABEL_17;
      }
      goto LABEL_122;
    }
    if ( v90 != 32 )
    {
      if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 2) != 0 )
        WPP_SF_Dd(v12[2], 90, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, 32, v90);
      goto LABEL_122;
    }
    if ( !a2 )
    {
      v30 = BcdOpenSystemStore(&v56, 377);
      v7 = FromNtStatus(v30);
      if ( v7 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_122;
        v18 = 93;
LABEL_89:
        v19 = (unsigned int)v7;
        goto LABEL_33;
      }
      LOWORD(v44) = 377;
      v7 = CFveApiBase::StoreValidationDataForAppEx(this, v56, 0, 0, v44, v6, v50, 0, 0);
      if ( v7 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_122;
        v18 = 94;
        goto LABEL_89;
      }
      v4 = v50[0];
      if ( v50[0] >= 0x179u )
      {
        v7 = -2147024883;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_122;
        v18 = 97;
        goto LABEL_89;
      }
    }
    v31 = v4;
    v32 = v4 + 1;
    v50[0] = v32;
    v33 = 5 * v31;
    v6[2 * v33] = 3;
    *(_OWORD *)&v6[2 * v33 + 2] = v89[0];
    *(_OWORD *)&v6[2 * v33 + 6] = v89[1];
    if ( !a2 )
    {
      LOBYTE(v48) = 0;
      LOBYTE(v47) = 0;
      LOWORD(v44) = 377;
      v7 = CFveApiBase::StoreValidationDataForAppEx(this, v56, v87, 4, v44, v6, v50, v47, v48);
      if ( v7 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_122;
        v18 = 98;
        goto LABEL_89;
      }
      v32 = v50[0];
    }
    v34 = FveDatumValidationInfoCreate(v6, v32, 0, &v52);
    v35 = FromNtStatus(v34);
    v7 = v35;
    if ( v35 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v35);
      if ( v7 < 0 )
      {
        v3 = v52;
        goto LABEL_122;
      }
    }
    v3 = v52;
    if ( a2 )
      *(_WORD *)(v52 + 6) |= 4u;
    appended = FveDatasetAppendDatum(*((_QWORD *)this + 146), v3, 17);
    v37 = FromNtStatus(appended);
    v7 = v37;
    if ( v37 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, v37);
      if ( v7 < 0 )
        goto LABEL_122;
    }
    v38 = *((_QWORD *)this + 146);
    v77 = L"IdentityGuid";
    v79 = (unsigned int *)(v38 + 16);
    v61 = 0;
    v62 = 0;
    v75 = (__int128 ***)&v63;
    v53 = 0;
    v76 = (__int128 *)&v63;
    v63 = &v75;
    v64 = (__int128 *)&v75;
    v54 = 0;
    v55 = 0;
    v78 = L"GUID";
    v80 = 16;
    memset(v84, 0, sizeof(v84));
    v39 = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v84, v40, L"VolumePath", v39, v44);
    if ( *(__int128 ******)v64 == &v63 )
    {
      *((_QWORD *)&v84[0] + 1) = v64;
      *(_QWORD *)&v84[0] = &v63;
      *(_QWORD *)v64 = v84;
      v64 = v84;
      v66 = 0;
      v67 = 0;
      v68 = 0;
      v41 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)&v66, v42, L"VolumeDriveLetter", v41, v46);
      if ( *(__int128 ******)v64 == &v63 )
      {
        *((_QWORD *)&v66 + 1) = v64;
        *(_QWORD *)&v66 = &v63;
        *(_QWORD *)v64 = &v66;
        v71 = L"BinaryDataSize";
        v65 = v90;
        v72 = L"ULONG";
        v73 = &v65;
        v74 = 4;
        if ( (__int128 *****)v66 == &v63 )
        {
          *((_QWORD *)&v83 + 1) = v90;
          v70 = &v66;
          *(_QWORD *)&v81 = &v63;
          *(_QWORD *)&v66 = &v69;
          *((_QWORD *)&v81 + 1) = &v69;
          *((_QWORD *)&v82 + 1) = L"BYTE";
          v69 = &v81;
          *(_QWORD *)&v82 = L"BinaryData";
          v64 = &v81;
          *(_QWORD *)&v83 = v89;
          v62 = FVEAPI_OP_BOUND_TRUSTED_WIM;
          v28 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v61;
          goto LABEL_121;
        }
      }
    }
LABEL_131:
    __fastfail(3u);
  }
  v7 = -2147024882;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids);
LABEL_124:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v56 )
  {
    BcdCloseStore(v56, v5);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    v56 = 0;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 0x20) != 0 )
    WPP_SF_d(v8[2], 101, &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800c7ff8  mov     [rsp-8+arg_8], rbx
0x1800c7ffd  mov     [rsp-8+arg_10], rsi
0x1800c8002  push    rbp
0x1800c8003  push    rdi
0x1800c8004  push    r13
0x1800c8006  push    r14
0x1800c8008  push    r15
0x1800c800a  lea     rbp, [rsp-0F70h]
0x1800c8012  mov     eax, 1070h
0x1800c8017  call    _alloca_probe
0x1800c801c  sub     rsp, rax
0x1800c801f  mov     rax, cs:__security_cookie
0x1800c8026  xor     rax, rsp
0x1800c8029  mov     [rbp+0F90h+var_30], rax
0x1800c8030  mov     [rsp+1090h+var_1040], dl
0x1800c8034  mov     rsi, rcx
0x1800c8037  xor     r13d, r13d
0x1800c803a  mov     [rbp+0F90h+var_FC8], 0
0x1800c8041  xor     edx, edx; Val
0x1800c8043  mov     [rsp+1090h+var_1030], r13
0x1800c8048  lea     rcx, [rbp+0F90h+var_ED0]; void *
0x1800c804f  mov     r8d, 0EA0h; Size
0x1800c8055  call    memset_0
0x1800c805a  xor     r14d, r14d
0x1800c805d  mov     [rbp+0F90h+var_1010], r13
0x1800c8061  mov     [rsp+1090h+var_103C], r14w
0x1800c8067  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c806e  lea     rdi, WPP_GLOBAL_Control
0x1800c8075  cmp     rcx, rdi
0x1800c8078  jz      short loc_1800C8094
0x1800c807a  test    byte ptr [rcx+1Ch], 20h
0x1800c807e  jz      short loc_1800C8094
0x1800c8080  mov     rcx, [rcx+10h]
0x1800c8084  lea     edx, [r13+4Bh]
0x1800c8088  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c808f  call    WPP_SF_
0x1800c8094  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c809b  mov     ecx, 3AE8h; unsigned __int64
0x1800c80a0  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c80a5  mov     [rsp+1090h+var_1038], rax
0x1800c80aa  mov     r15, rax
0x1800c80ad  test    rax, rax
0x1800c80b0  jnz     short loc_1800C80EC
0x1800c80b2  mov     ebx, 8007000Eh
0x1800c80b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c80be  cmp     rcx, rdi
0x1800c80c1  jz      loc_1800C8AC1
0x1800c80c7  mov     dil, 2
0x1800c80ca  test    [rcx+1Ch], dil
0x1800c80ce  jz      loc_1800C8AC1
0x1800c80d4  mov     rcx, [rcx+10h]
0x1800c80d8  lea     edx, [rax+4Ch]
0x1800c80db  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c80e2  call    WPP_SF_
0x1800c80e7  jmp     loc_1800C8ABA
0x1800c80ec  mov     rcx, rsi; this
0x1800c80ef  call    ?CheckInited@CFveApiBase@@QEBAJXZ; CFveApiBase::CheckInited(void)
0x1800c80f4  mov     ebx, eax
0x1800c80f6  test    eax, eax
0x1800c80f8  jz      short loc_1800C812C
0x1800c80fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8101  cmp     rcx, rdi
0x1800c8104  jz      short loc_1800C8124
0x1800c8106  test    byte ptr [rcx+1Ch], 40h
0x1800c810a  jz      short loc_1800C8124
0x1800c810c  mov     rcx, [rcx+10h]
0x1800c8110  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c8117  mov     edx, 4Dh ; 'M'
0x1800c811c  mov     r9d, eax
0x1800c811f  call    WPP_SF_d
0x1800c8124  test    ebx, ebx
0x1800c8126  js      loc_1800C8A9C
0x1800c812c  call    IsWinReGetConfigPresent
0x1800c8131  test    al, al
0x1800c8133  jnz     short loc_1800C8169
0x1800c8135  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c813c  cmp     rcx, rdi
0x1800c813f  jz      loc_1800C8A9C
0x1800c8145  test    byte ptr [rcx+1Ch], 8
0x1800c8149  jz      loc_1800C8A9C
0x1800c814f  mov     edx, 4Eh ; 'N'
0x1800c8154  mov     rcx, [rcx+10h]
0x1800c8158  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c815f  call    WPP_SF_
0x1800c8164  jmp     loc_1800C8A9C
0x1800c8169  lea     r8, [rbp+0F90h+var_FC8]
0x1800c816d  call    NgscbpDoesRegKeyExist
0x1800c8172  mov     ebx, eax
0x1800c8174  test    eax, eax
0x1800c8176  jz      short loc_1800C81B3
0x1800c8178  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c817f  cmp     rcx, rdi
0x1800c8182  jz      short loc_1800C81A9
0x1800c8184  test    byte ptr [rcx+1Ch], 40h
0x1800c8188  jz      short loc_1800C81A9
0x1800c818a  mov     rcx, [rcx+10h]
0x1800c818e  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c8195  mov     edx, 4Fh ; 'O'
0x1800c819a  mov     r9d, eax
0x1800c819d  call    WPP_SF_d
0x1800c81a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c81a9  test    ebx, ebx
0x1800c81ab  js      loc_1800C8A9C
0x1800c81b1  jmp     short loc_1800C81BA
0x1800c81b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c81ba  cmp     [rbp+0F90h+var_FC8], r13d
0x1800c81be  jz      short loc_1800C81DD
0x1800c81c0  cmp     rcx, rdi
0x1800c81c3  jz      loc_1800C8A9C
0x1800c81c9  test    byte ptr [rcx+1Ch], 8
0x1800c81cd  jz      loc_1800C8A9C
0x1800c81d3  mov     edx, 50h ; 'P'
0x1800c81d8  jmp     loc_1800C8154
0x1800c81dd  lea     rdx, [rbp+0F90h+var_ED0]
0x1800c81e4  mov     [rbp+0F90h+var_ED0], 0EA0h
0x1800c81ef  xor     ecx, ecx
0x1800c81f1  call    cs:__imp_WinReGetConfig
0x1800c81f8  nop     dword ptr [rax+rax+00h]
0x1800c81fd  test    eax, eax
0x1800c81ff  jnz     short loc_1800C823F
0x1800c8201  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800c8206  mov     ebx, eax
0x1800c8208  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c820f  cmp     rcx, rdi
0x1800c8212  jz      loc_1800C8A9C
0x1800c8218  test    byte ptr [rcx+1Ch], 40h
0x1800c821c  jz      loc_1800C8A9C
0x1800c8222  mov     edx, 51h ; 'Q'
0x1800c8227  mov     r9d, eax
0x1800c822a  mov     rcx, [rcx+10h]
0x1800c822e  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c8235  call    WPP_SF_d
0x1800c823a  jmp     loc_1800C8A9C
0x1800c823f  cmp     [rbp+0F90h+var_EC8], r13d
0x1800c8246  jnz     short loc_1800C82BA
0x1800c8248  mov     edx, 11h; unsigned __int16
0x1800c824d  mov     rcx, rsi; this
0x1800c8250  call    ?EraseAll@CFveApiBase@@QEAAJGG@Z; CFveApiBase::EraseAll(ushort,ushort)
0x1800c8255  mov     ebx, eax
0x1800c8257  test    eax, eax
0x1800c8259  jz      short loc_1800C8296
0x1800c825b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8262  cmp     rcx, rdi
0x1800c8265  jz      short loc_1800C828C
0x1800c8267  test    byte ptr [rcx+1Ch], 40h
0x1800c826b  jz      short loc_1800C828C
0x1800c826d  mov     rcx, [rcx+10h]
0x1800c8271  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c8278  mov     edx, 52h ; 'R'
0x1800c827d  mov     r9d, eax
0x1800c8280  call    WPP_SF_d
0x1800c8285  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c828c  test    ebx, ebx
0x1800c828e  js      loc_1800C8A9C
0x1800c8294  jmp     short loc_1800C829D
0x1800c8296  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c829d  cmp     rcx, rdi
0x1800c82a0  jz      loc_1800C8A9C
0x1800c82a6  test    byte ptr [rcx+1Ch], 8
0x1800c82aa  jz      loc_1800C8A9C
0x1800c82b0  mov     edx, 53h ; 'S'
0x1800c82b5  jmp     loc_1800C8154
0x1800c82ba  test    byte ptr [rsi+160h], 4
0x1800c82c1  mov     dil, 2
0x1800c82c4  jz      loc_1800C855D
0x1800c82ca  mov     rcx, [rsi+490h]
0x1800c82d1  lea     rax, [rbp+0F90h+var_FC8]
0x1800c82d5  mov     edx, 11h
0x1800c82da  mov     qword ptr [rsp+1090h+var_1070], rax; unsigned int
0x1800c82df  mov     r8d, 0FFFFh
0x1800c82e5  xor     r9d, r9d
0x1800c82e8  call    FveDatasetGetNext
0x1800c82ed  mov     r15d, eax
0x1800c82f0  test    eax, eax
0x1800c82f2  js      loc_1800C849C
0x1800c82f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c82ff  lea     rdx, WPP_GLOBAL_Control
0x1800c8306  cmp     rcx, rdx
0x1800c8309  jz      short loc_1800C8326
0x1800c830b  test    byte ptr [rcx+1Ch], 4
0x1800c830f  jz      short loc_1800C8326
0x1800c8311  mov     rcx, [rcx+10h]
0x1800c8315  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c831c  mov     edx, 54h ; 'T'
0x1800c8321  call    WPP_SF_
0x1800c8326  mov     rax, [rsi+490h]
0x1800c832d  lea     rcx, aIdentityguid; "IdentityGuid"
0x1800c8334  add     rax, 10h
0x1800c8338  mov     [rbp+0F90h+var_F80], rcx
0x1800c833c  mov     [rbp+0F90h+var_F70], rax
0x1800c8340  lea     rdx, aGuid; "GUID"
0x1800c8347  xorps   xmm0, xmm0
0x1800c834a  mov     [rbp+0F90h+var_1008], r13
0x1800c834e  lea     rax, [rbp+0F90h+var_FF8]
0x1800c8352  mov     [rbp+0F90h+var_1000], r13
0x1800c8356  mov     [rbp+0F90h+var_F90], rax
0x1800c835a  mov     rcx, rsi; this
0x1800c835d  lea     rax, [rbp+0F90h+var_FF8]
0x1800c8361  mov     [rsp+1090h+var_1028], r13
0x1800c8366  mov     [rbp+0F90h+var_F88], rax
0x1800c836a  lea     rax, [rbp+0F90h+var_F90]
0x1800c836e  mov     [rbp+0F90h+var_FF8], rax
0x1800c8372  lea     rax, [rbp+0F90h+var_F90]
0x1800c8376  mov     [rbp+0F90h+var_FF0], rax
0x1800c837a  mov     [rsp+1090h+var_1020], r13
0x1800c837f  mov     [rsp+1090h+var_1018], r13
0x1800c8384  mov     [rbp+0F90h+var_F78], rdx
0x1800c8388  mov     [rbp+0F90h+var_F68], 10h
0x1800c8390  movups  [rbp+0F90h+var_F30], xmm0
0x1800c8394  movups  [rbp+0F90h+var_F20], xmm0
0x1800c8398  movups  [rbp+0F90h+var_F10], xmm0
0x1800c839f  call    ?GetLoggingVolumePath@CFveApiBase@@QEAAPEBGXZ; CFveApiBase::GetLoggingVolumePath(void)
0x1800c83a4  mov     r9, rax; unsigned __int16 *
0x1800c83a7  lea     r8, aVolumepath; "VolumePath"
0x1800c83ae  lea     rcx, [rbp+0F90h+var_F30]; struct _FVEAPI_EVENT_DATA *
0x1800c83b2  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x1800c83b7  mov     rcx, [rbp+0F90h+var_FF0]
0x1800c83bb  lea     rax, [rbp+0F90h+var_FF8]
0x1800c83bf  cmp     [rcx], rax
0x1800c83c2  jnz     loc_1800C8B40
0x1800c83c8  xorps   xmm0, xmm0
0x1800c83cb  mov     qword ptr [rbp+0F90h+var_F30+8], rcx
0x1800c83cf  lea     rax, [rbp+0F90h+var_FF8]
0x1800c83d3  mov     qword ptr [rbp+0F90h+var_F30], rax
0x1800c83d7  lea     rax, [rbp+0F90h+var_F30]
0x1800c83db  mov     [rcx], rax
0x1800c83de  lea     rax, [rbp+0F90h+var_F30]
0x1800c83e2  mov     rcx, rsi; this
0x1800c83e5  mov     [rbp+0F90h+var_FF0], rax
0x1800c83e9  movups  [rbp+0F90h+var_FC0], xmm0
0x1800c83ed  movups  [rbp+0F90h+var_FB0], xmm0
0x1800c83f1  movups  [rbp+0F90h+var_FA0], xmm0
0x1800c83f5  call    ?GetLoggingVolumeDriveLetter@CFveApiBase@@QEAAPEBGXZ; CFveApiBase::GetLoggingVolumeDriveLetter(void)
0x1800c83fa  mov     r9, rax; unsigned __int16 *
0x1800c83fd  lea     r8, aVolumedrivelet; "VolumeDriveLetter"
0x1800c8404  lea     rcx, [rbp+0F90h+var_FC0]; struct _FVEAPI_EVENT_DATA *
0x1800c8408  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x1800c840d  mov     rcx, [rbp+0F90h+var_FF0]
0x1800c8411  lea     rax, [rbp+0F90h+var_FF8]
0x1800c8415  cmp     [rcx], rax
0x1800c8418  jnz     loc_1800C8B40
0x1800c841e  lea     rax, [rbp+0F90h+var_FF8]
0x1800c8422  mov     qword ptr [rbp+0F90h+var_FC0+8], rcx
0x1800c8426  mov     qword ptr [rbp+0F90h+var_FC0], rax
0x1800c842a  lea     rdx, [rbp+0F90h+var_FC8]
0x1800c842e  lea     rax, [rbp+0F90h+var_FC0]
0x1800c8432  mov     [rcx], rax
0x1800c8435  lea     rax, aHr; "hr"
0x1800c843c  mov     [rbp+0F90h+var_F50], rax
0x1800c8440  lea     rcx, aHresult; "HRESULT"
0x1800c8447  lea     rax, [rbp+0F90h+var_FF8]
0x1800c844b  mov     [rbp+0F90h+var_FC8], ebx
0x1800c844e  mov     [rbp+0F90h+var_F48], rcx
0x1800c8452  mov     [rbp+0F90h+var_F40], rdx
0x1800c8456  mov     [rbp+0F90h+var_F38], 4
0x1800c845e  cmp     qword ptr [rbp+0F90h+var_FC0], rax
0x1800c8462  jnz     loc_1800C8B40
0x1800c8468  lea     rax, [rbp+0F90h+var_FF8]
0x1800c846c  mov     [rbp+0F90h+var_F60], rax
0x1800c8470  lea     rdx, [rbp+0F90h+var_1008]
0x1800c8474  lea     rax, [rbp+0F90h+var_FC0]
0x1800c8478  mov     [rbp+0F90h+var_F58], rax
0x1800c847c  lea     rax, [rbp+0F90h+var_F60]
0x1800c8480  mov     qword ptr [rbp+0F90h+var_FC0], rax
0x1800c8484  lea     rax, [rbp+0F90h+var_F60]
0x1800c8488  mov     [rbp+0F90h+var_FF0], rax
0x1800c848c  lea     rax, FVEAPI_OP_WIM_BCD_MISMATCH_DETECTED
0x1800c8493  mov     [rbp+0F90h+var_1000], rax
0x1800c8497  jmp     loc_1800C8A88
0x1800c849c  cmp     r15d, 0C0000225h
0x1800c84a3  jz      loc_1800C852A
0x1800c84a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c84b0  lea     rdx, WPP_GLOBAL_Control
0x1800c84b7  cmp     rcx, rdx
0x1800c84ba  jz      short loc_1800C84DA
0x1800c84bc  test    [rcx+1Ch], dil
0x1800c84c0  jz      short loc_1800C84DA
0x1800c84c2  mov     rcx, [rcx+10h]
0x1800c84c6  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c84cd  mov     edx, 55h ; 'U'
0x1800c84d2  mov     r9d, r15d
0x1800c84d5  call    WPP_SF_d
0x1800c84da  mov     ecx, r15d; int
0x1800c84dd  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800c84e2  mov     ebx, eax
0x1800c84e4  test    eax, eax
0x1800c84e6  jz      short loc_1800C852A
0x1800c84e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c84ef  lea     rax, WPP_GLOBAL_Control
0x1800c84f6  cmp     rcx, rax
0x1800c84f9  jz      short loc_1800C8520
0x1800c84fb  test    byte ptr [rcx+1Ch], 40h
0x1800c84ff  jz      short loc_1800C8520
0x1800c8501  mov     rcx, [rcx+10h]
0x1800c8505  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x1800c850c  mov     edx, 56h ; 'V'
0x1800c8511  mov     r9d, ebx
0x1800c8514  call    WPP_SF_d
0x1800c8519  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8520  test    ebx, ebx
  ... truncated ...
```
