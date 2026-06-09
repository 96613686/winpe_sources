# CPipeGfxProvider::Refresh(void)

- ea: `0x1800125d0`
- end: `0x180013835`
- name: `?Refresh@CPipeGfxProvider@@IEAAJXZ`
- size: `4709`
- prototype: `__int64 __fastcall(CPipeGfxProvider *this, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800125c0`

## callees

- `0x1800015f0`
- `0x18000d0d0`
- `0x1800125d0`
- `0x180027e88`
- `0x1800280d0`
- `0x180028450`
- `0x180033964`
- `0x180033da0`
- `0x1800b9d78`
- `0x1800bbf88`
- `0x18014d010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001271b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012a8f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012b6a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012ffd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001271b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012a8f`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012b6a`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012ffd`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180012615`
- `RDPBASE!PAL_System_CritSecEnter` at `0x180012615`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180013816`
- `RDPBASE!PAL_System_CritSecLeave` at `0x180013816`
- `USER32!SetRect` at `0x180012770`
- `USER32!SetRect` at `0x180012b8d`
- `USER32!SetRect` at `0x180012770`
- `USER32!SetRect` at `0x180012b8d`

## string_xrefs

- `0x180012803`: `Failed to ReCreateSurfaces`
- `0x180012f69`: `Created new output layout`
- `0x1800131db`: `Legacy: Failed to add pointer move update`
- `0x18001308f`: `Update event processing failed`
- `0x18001332e`: `Legacy: Failed to add pointer shape update`
- `0x180013277`: `Failed to add pointer move update`
- `0x1800134bd`: `Failed to add surface commands`
- `0x1800133ca`: `Failed to add pointer shape update`
- `0x18001369d`: `Failed to add frame stat commands`
- `0x1800135ad`: `Failed to add video hints commands`

## pseudocode

```c
__int64 __fastcall CPipeGfxProvider::Refresh(CPipeGfxProvider *this, __int64 a2, __int64 a3)
{
  _QWORD *v3; // rbx
  __int64 v5; // rcx
  int updated; // edi
  int Surfaces; // eax
  int v8; // r8d
  int v9; // r9d
  char *v10; // r14
  __int64 v11; // rax
  __int64 v12; // rcx
  int v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  const char *v17; // rcx
  _DWORD *v18; // rax
  int v19; // ecx
  int v20; // r9d
  _QWORD *v21; // rax
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  _QWORD *v25; // rdi
  unsigned int v26; // r10d
  __int64 v27; // rdx
  __int64 v28; // r8
  _DWORD *v29; // r8
  _DWORD *v30; // r9
  int v31; // r14d
  int v32; // eax
  __int64 v33; // r8
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  char *v37; // r14
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  int v59; // ecx
  int v60; // r8d
  int v61; // r9d
  __int64 v62; // rcx
  unsigned int v64; // [rsp+50h] [rbp-B0h] BYREF
  const char *v65; // [rsp+58h] [rbp-A8h] BYREF
  const char *v66; // [rsp+60h] [rbp-A0h] BYREF
  const char *v67; // [rsp+68h] [rbp-98h] BYREF
  const char *v68; // [rsp+70h] [rbp-90h] BYREF
  EVENT_DESCRIPTOR v69; // [rsp+78h] [rbp-88h] BYREF
  __int64 v70; // [rsp+88h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+90h] [rbp-70h] BYREF
  int v72; // [rsp+A0h] [rbp-60h] BYREF
  struct UMRDP_EVENT_HEADER *v73; // [rsp+A8h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-50h] BYREF
  char *v75; // [rsp+C0h] [rbp-40h]
  int v76; // [rsp+C8h] [rbp-38h]
  int v77; // [rsp+CCh] [rbp-34h]
  const char *v78; // [rsp+D0h] [rbp-30h]
  __int64 v79; // [rsp+D8h] [rbp-28h]
  const char **v80; // [rsp+E0h] [rbp-20h]
  __int64 v81; // [rsp+E8h] [rbp-18h]
  const char **v82; // [rsp+F0h] [rbp-10h]
  __int64 v83; // [rsp+F8h] [rbp-8h]
  unsigned int *v84; // [rsp+100h] [rbp+0h]
  __int64 v85; // [rsp+108h] [rbp+8h]
  const char *v86; // [rsp+110h] [rbp+10h]
  __int64 v87; // [rsp+118h] [rbp+18h]

  v3 = (_QWORD *)((char *)this + 9696);
  v73 = 0;
  v72 = 0;
  v70 = 0;
  if ( *((_DWORD *)this + 2426) )
    PAL_System_CritSecEnter(*v3, a2, a3);
  v5 = *((_QWORD *)this + 1576);
  if ( !v5 )
  {
    updated = 1;
    if ( (unsigned int)dword_1801B76C8 > 3 )
    {
      EventDescriptor.Keyword = 0;
      v82 = &v66;
      LODWORD(v66) = 1;
      v80 = (const char **)"m_spVideoDriver is NULL: Refresh skipped";
      v84 = (unsigned int *)"Refresh";
      v78 = "Error condition failed";
      *(_DWORD *)&EventDescriptor.Level = 3;
      UserData.Ptr = (ULONGLONG)off_1801B76D0;
      v85 = 8;
      v83 = 4;
      v81 = 41;
      v79 = 23;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      UserData.Size = *(unsigned __int16 *)off_1801B76D0;
      v75 = (char *)&unk_1801A4C58;
      UserData.Reserved = 2;
      v76 = 52;
      v77 = 1;
      v64 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(qword_1801B76E8, &EventDescriptor, 0, 0, 6u, &UserData);
    }
    goto LABEL_92;
  }
  (*(void (**)(void))(*(_QWORD *)v5 + 56LL))();
  *((_DWORD *)this + 2832) = 1080;
  *((_DWORD *)this + 2833) = 5;
  *((_QWORD *)this + 1418) = 0;
  SetRect((LPRECT)((char *)this + 11352), 0, 0, 0, 0);
  *((_QWORD *)this + 1417) = -1;
  *(_QWORD *)((char *)this + 12596) = 0;
  *((_DWORD *)this + 3154) = 1136;
  *((_DWORD *)this + 3155) = 13;
  *(_OWORD *)((char *)this + 13688) = 0;
  *(_OWORD *)((char *)this + 13704) = 0;
  *(_OWORD *)((char *)this + 13720) = 0;
  *(_OWORD *)((char *)this + 13736) = 0;
  *((_DWORD *)this + 3438) = 0;
  CPipeGfxProvider::ReleaseLastFrameContext(this);
  if ( !*((_DWORD *)this + 3848) || *((_BYTE *)this + 15420) )
  {
LABEL_12:
    v10 = (char *)this + 12560;
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1570) + 64LL))((char *)this + 12560);
    while ( (*(unsigned int (__fastcall **)(char *, __int64 *))(*(_QWORD *)v10 + 72LL))((char *)this + 12560, &v70) )
    {
      v11 = v70;
      v12 = *(_QWORD *)(v70 + 32);
      if ( v12 )
      {
        v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v12 + 64LL))(v12, 0, 3000);
        updated = v13;
        if ( *((_DWORD *)this + 3852) )
        {
          if ( v13 < 0 )
          {
            if ( (unsigned int)dword_1801B76C8 > 2 )
            {
              *(_QWORD *)&v69.Id = "Refresh";
              v67 = "Failed to acquire Dx texture keyed mutex";
              LODWORD(v65) = 1851;
              v66 = "Error HResult failed";
              v68 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
              v64 = v13;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v14,
                (unsigned int)byte_1801A4BFB,
                v15,
                v16,
                (__int64)&v66,
                (__int64)&v64,
                (__int64)&v68,
                (__int64)&v65,
                (__int64)&v69,
                (__int64)&v67);
            }
            goto LABEL_90;
          }
        }
        else if ( v13 < 0 && (unsigned int)dword_1801B76C8 > 2 )
        {
          v64 = 1856;
          EventDescriptor.Keyword = 0;
          v84 = &v64;
          LODWORD(v66) = v13;
          v80 = &v66;
          v86 = "Refresh";
          v78 = "Failed to acquire Dx texture keyed mutex";
          *(_DWORD *)&EventDescriptor.Level = 2;
          UserData.Ptr = (ULONGLONG)off_1801B76D0;
          v87 = 8;
          v85 = 4;
          v82 = (const char **)"clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v83 = 70;
          v81 = 4;
          v79 = 41;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          UserData.Size = *(unsigned __int16 *)off_1801B76D0;
          v75 = byte_1801A4B33;
          UserData.Reserved = 2;
          v76 = 62;
          v77 = 1;
          LODWORD(v65) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(qword_1801B76E8, &EventDescriptor, 0, 0, 7u, &UserData);
        }
        if ( (unsigned int)dword_1801B76C8 > 5 )
        {
          LODWORD(v65) = updated;
          v83 = 4;
          v81 = 8;
          v17 = *(const char **)v70;
          v82 = &v65;
          v80 = &v67;
          v78 = "Dx texture keyed mutex acquired";
          *(_DWORD *)&v69.Level = 5;
          UserData.Ptr = (ULONGLONG)off_1801B76D0;
          v67 = v17;
          v69.Keyword = 0;
          v79 = 32;
          *(_DWORD *)&v69.Id = 184549376;
          UserData.Size = *(unsigned __int16 *)off_1801B76D0;
          v75 = byte_1801A4B7D;
          UserData.Reserved = 2;
          v76 = 43;
          v77 = 1;
          v64 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(qword_1801B76E8, &v69, 0, 0, 5u, &UserData);
        }
        v11 = v70;
      }
      *(_DWORD *)(v11 + 80) = 0;
      SetRect((LPRECT)(v70 + 88), 0, 0, 0, 0);
      *(_DWORD *)(v70 + 52) = 0;
      *(_DWORD *)(v70 + 56) = 0;
    }
    if ( *((_DWORD *)this + 3148) )
    {
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 64LL))((char *)this + 12560);
      while ( 1 )
      {
        if ( !(*(unsigned int (__fastcall **)(char *, __int64 *))(*(_QWORD *)v10 + 72LL))((char *)this + 12560, &v70) )
        {
          *((_QWORD *)this + 1177) = -1;
          *((_QWORD *)this + 1178) = -1;
          *((_QWORD *)this + 1179) = -1;
          *((_QWORD *)this + 1180) = -1;
          *((_QWORD *)this + 1181) = -1;
          *((_QWORD *)this + 1182) = -1;
          *((_QWORD *)this + 1183) = -1;
          *((_QWORD *)this + 1184) = -1;
          *((_QWORD *)this + 1185) = -1;
          *((_QWORD *)this + 1186) = -1;
          *((_QWORD *)this + 1187) = -1;
          *((_QWORD *)this + 1188) = -1;
          *((_QWORD *)this + 1189) = -1;
          *((_QWORD *)this + 1190) = -1;
          *((_QWORD *)this + 1191) = -1;
          *((_QWORD *)this + 1192) = -1;
          CPipeGfxProvider::FreeDeletedSurfaces(this);
          *((_DWORD *)this + 3148) = 0;
          goto LABEL_34;
        }
        v18 = operator new(0x438u);
        if ( !v18 )
          break;
        *v18 = 1080;
        v18[1] = 12;
        *((_QWORD *)v18 + 1) = *(_QWORD *)v70;
        (*(void (__fastcall **)(char *, _DWORD *))(*((_QWORD *)this + 1562) + 8LL))((char *)this + 12496, v18);
      }
      updated = -2147024882;
      if ( (unsigned int)dword_1801B76C8 > 2 )
      {
        *(_QWORD *)&v69.Id = "Refresh";
        v67 = "BYTE allocation failed";
        LODWORD(v65) = 1887;
        v66 = "Error condition failed";
        v68 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
        v64 = -2147024882;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v19,
          (unsigned int)&dword_1801A4A84,
          0,
          v20,
          (__int64)&v66,
          (__int64)&v64,
          (__int64)&v68,
          (__int64)&v65,
          (__int64)&v69,
          (__int64)&v67);
      }
      goto LABEL_90;
    }
LABEL_34:
    if ( *((_DWORD *)this + 3439) )
    {
      v21 = operator new(0x640u);
      v25 = v21;
      if ( !v21 )
      {
        updated = -2147024882;
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          *(_QWORD *)&v69.Id = "Refresh";
          v67 = "BYTE allocation failed";
          LODWORD(v65) = 1920;
          v66 = "Error condition failed";
          v68 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v64 = -2147024882;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v22,
            (unsigned int)&word_1801A4AD6,
            v23,
            v24,
            (__int64)&v66,
            (__int64)&v64,
            (__int64)&v68,
            (__int64)&v65,
            (__int64)&v69,
            (__int64)&v67);
        }
        goto LABEL_90;
      }
      v21[1] = -1;
      *((_DWORD *)v21 + 266) = 0;
      v26 = 0;
      *(_DWORD *)v21 = 1600;
      *((_DWORD *)v21 + 1) = 23;
      *((_DWORD *)v21 + 269) = *((_DWORD *)this + 29);
      *((_DWORD *)v21 + 270) = *((_DWORD *)this + 28);
      for ( *((_DWORD *)v21 + 268) = *((_DWORD *)this + 31); v26 < *((_DWORD *)this + 31); v29[275] = v30[112] )
      {
        v27 = v26;
        v28 = v26++;
        v29 = &v21[4 * v28];
        v30 = (_DWORD *)((char *)this + 20 * v27);
        v29[271] = v30[32];
        LODWORD(v21[4 * v27 + 136]) = v30[33];
        v29[273] = v30[34];
        v29[274] = v30[35];
        v29[278] = v30[36] & 1;
        v29[277] = v30[114];
        v29[276] = v30[113];
      }
      (*(void (__fastcall **)(char *, _QWORD *))(*((_QWORD *)this + 1562) + 8LL))((char *)this + 12496, v21);
      *((_DWORD *)this + 3439) = 0;
      if ( (unsigned int)dword_1801B76C8 > 4 )
      {
        LODWORD(v65) = *((_DWORD *)v25 + 270);
        v64 = *((_DWORD *)v25 + 269);
        v82 = &v65;
        v80 = (const char **)&v64;
        v78 = "Created new output layout";
        *(_DWORD *)&EventDescriptor.Level = 4;
        UserData.Ptr = (ULONGLONG)off_1801B76D0;
        v83 = 4;
        v81 = 4;
        v79 = 26;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_1801B76D0;
        v75 = (char *)word_1801A4A5A;
        UserData.Reserved = 2;
        v76 = 41;
        v77 = 1;
        LODWORD(v66) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(qword_1801B76E8, &EventDescriptor, 0, 0, 5u, &UserData);
      }
    }
    v31 = 4096;
    do
    {
      v32 = (*(__int64 (__fastcall **)(_QWORD, struct UMRDP_EVENT_HEADER **, int *))(**((_QWORD **)this + 1576) + 128LL))(
              *((_QWORD *)this + 1576),
              &v73,
              &v72);
      if ( v32 )
      {
        if ( v32 == -2147483638 )
          break;
        if ( v32 < 0 )
          goto LABEL_53;
      }
      else
      {
        updated = CPipeGfxProvider::ProcessUpdateEvent(this, v73, v33);
        if ( updated < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            *(_QWORD *)&v69.Id = "Refresh";
            v67 = "Update event processing failed";
            LODWORD(v65) = 1973;
            v66 = "Error HResult failed";
            v68 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
            v64 = updated;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v34,
              (unsigned int)byte_1801A49FD,
              v35,
              v36,
              (__int64)&v66,
              (__int64)&v64,
              (__int64)&v68,
              (__int64)&v65,
              (__int64)&v69,
              (__int64)&v67);
          }
          goto LABEL_90;
        }
        (*(void (__fastcall **)(_QWORD, struct UMRDP_EVENT_HEADER *))(**((_QWORD **)this + 1576) + 136LL))(
          *((_QWORD *)this + 1576),
          v73);
        --v31;
      }
    }
    while ( v31 );
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 1576) + 144LL))(*((_QWORD *)this + 1576));
LABEL_53:
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1558) + 64LL))((char *)this + 12464);
    v65 = 0;
    v37 = (char *)this + 11296;
    while ( (*(unsigned int (__fastcall **)(char *, const char **))(*((_QWORD *)this + 1558) + 72LL))(
              (char *)this + 12464,
              &v65) )
    {
      v37 = (char *)this + 11296;
      (*(void (__fastcall **)(char *, const char *))(*((_QWORD *)this + 1412) + 8LL))((char *)this + 11296, v65);
    }
    if ( *((_DWORD *)this + 3149) )
    {
      updated = (*(__int64 (__fastcall **)(char *, char *))(*(_QWORD *)v37 + 8LL))(v37, (char *)this + 11328);
      if ( updated < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          *(_QWORD *)&v69.Id = "Refresh";
          v67 = "Legacy: Failed to add pointer move update";
          LODWORD(v65) = 2022;
          v66 = "Error HResult failed";
          v68 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v64 = updated;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v38,
            (unsigned int)byte_1801A4959,
            v39,
            v40,
            (__int64)&v66,
            (__int64)&v64,
            (__int64)&v68,
            (__int64)&v65,
            (__int64)&v69,
            (__int64)&v67);
        }
        goto LABEL_90;
      }
    }
    else
    {
      updated = CPipeGfxProvider::ProcessPointerMoveEvent(this);
      if ( updated < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          *(_QWORD *)&v69.Id = "Refresh";
          v67 = "Failed to add pointer move update";
          LODWORD(v65) = 2028;
          v66 = "Error HResult failed";
          v68 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v64 = updated;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v41,
            (unsigned int)byte_1801A49AB,
            v42,
            v43,
            (__int64)&v66,
            (__int64)&v64,
            (__int64)&v68,
            (__int64)&v65,
            (__int64)&v69,
            (__int64)&v67);
        }
        goto LABEL_90;
      }
    }
    if ( *((_DWORD *)this + 3150) )
    {
      updated = (*(__int64 (__fastcall **)(char *, _QWORD))(*(_QWORD *)v37 + 8LL))(v37, *((_QWORD *)this + 1551));
      if ( updated < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          *(_QWORD *)&v69.Id = "Refresh";
          v67 = "Legacy: Failed to add pointer shape update";
          LODWORD(v65) = 2035;
          v66 = "Error HResult failed";
          v68 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v64 = updated;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v44,
            (unsigned int)byte_1801A48B5,
            v45,
            v46,
            (__int64)&v66,
            (__int64)&v64,
            (__int64)&v68,
            (__int64)&v65,
            (__int64)&v69,
            (__int64)&v67);
        }
        goto LABEL_90;
      }
    }
    else
    {
      updated = CPipeGfxProvider::ProcessPointerShapeEvent(this);
      if ( updated < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          *(_QWORD *)&v69.Id = "Refresh";
          v67 = "Failed to add pointer shape update";
          LODWORD(v65) = 2041;
          v66 = "Error HResult failed";
          v68 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v64 = updated;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v47,
            (unsigned int)&byte_1801A4907,
            v48,
            v49,
            (__int64)&v66,
            (__int64)&v64,
            (__int64)&v68,
            (__int64)&v65,
            (__int64)&v69,
            (__int64)&v67);
        }
        goto LABEL_90;
      }
    }
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1562) + 64LL))((char *)this + 12496);
    v66 = 0;
    while ( (*(unsigned int (__fastcall **)(char *, const char **))(*((_QWORD *)this + 1562) + 72LL))(
              (char *)this + 12496,
              &v66) )
    {
      updated = (*(__int64 (__fastcall **)(char *, const char *))(*(_QWORD *)v37 + 8LL))(v37, v66);
      if ( updated < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          *(_QWORD *)&v69.Id = "Refresh";
          v67 = "Failed to add surface commands";
          LODWORD(v65) = 2054;
          *(_QWORD *)&EventDescriptor.Id = "Error HResult failed";
          v68 = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v64 = updated;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v50,
            (unsigned int)byte_1801A4811,
            v51,
            v52,
            (__int64)&EventDescriptor,
            (__int64)&v64,
            (__int64)&v68,
            (__int64)&v65,
            (__int64)&v69,
            (__int64)&v67);
        }
        goto LABEL_90;
      }
    }
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1554) + 64LL))((char *)this + 12432);
    v66 = 0;
    while ( (*(unsigned int (__fastcall **)(char *, const char **))(*((_QWORD *)this + 1554) + 72LL))(
              (char *)this + 12432,
              &v66) )
    {
      updated = (*(__int64 (__fastcall **)(char *, const char *))(*(_QWORD *)v37 + 8LL))(v37, v66);
      if ( updated < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v67 = "Refresh";
          *(_QWORD *)&EventDescriptor.Id = "Failed to add video hints commands";
          LODWORD(v65) = 2070;
          v68 = "Error HResult failed";
          *(_QWORD *)&v69.Id = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v64 = updated;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v53,
            (unsigned int)byte_1801A4863,
            v54,
            v55,
            (__int64)&v68,
            (__int64)&v64,
            (__int64)&v69,
            (__int64)&v65,
            (__int64)&v67,
            (__int64)&EventDescriptor);
        }
        goto LABEL_90;
      }
    }
    (*(void (__fastcall **)(char *))(*((_QWORD *)this + 1566) + 64LL))((char *)this + 12528);
    v66 = 0;
    while ( (*(unsigned int (__fastcall **)(char *, const char **))(*((_QWORD *)this + 1566) + 72LL))(
              (char *)this + 12528,
              &v66) )
    {
      updated = (*(__int64 (__fastcall **)(char *, const char *))(*(_QWORD *)v37 + 8LL))(v37, v66);
      if ( updated < 0 )
      {
        if ( (unsigned int)dword_1801B76C8 > 2 )
        {
          v67 = "Refresh";
          *(_QWORD *)&EventDescriptor.Id = "Failed to add frame stat commands";
          LODWORD(v65) = 2083;
          v68 = "Error HResult failed";
          *(_QWORD *)&v69.Id = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
          v64 = updated;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v56,
            (unsigned int)byte_1801A476D,
            v57,
            v58,
            (__int64)&v68,
            (__int64)&v64,
            (__int64)&v69,
            (__int64)&v65,
            (__int64)&v67,
            (__int64)&EventDescriptor);
        }
        goto LABEL_90;
      }
    }
    if ( !*((_DWORD *)this + 3438) )
      goto LABEL_92;
    updated = (*(__int64 (__fastcall **)(char *, char *))(*(_QWORD *)v37 + 8LL))(v37, (char *)this + 12616);
    if ( updated >= 0 )
      goto LABEL_92;
    if ( (unsigned int)dword_1801B76C8 > 2 )
    {
      v67 = "Refresh";
      *(_QWORD *)&EventDescriptor.Id = "Failed to add frame tag";
      LODWORD(v65) = 2091;
      v68 = "Error HResult failed";
      *(_QWORD *)&v69.Id = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
      v64 = updated;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v59,
        (unsigned int)&byte_1801A47BF,
        v60,
        v61,
        (__int64)&v68,
        (__int64)&v64,
        (__int64)&v69,
        (__int64)&v65,
        (__int64)&v67,
        (__int64)&EventDescriptor);
    }
    goto LABEL_90;
  }
  Surfaces = CPipeGfxProvider::ReCreateSurfaces(this);
  updated = Surfaces;
  if ( Surfaces >= 0 )
  {
    *((_DWORD *)this + 3848) = 0;
    goto LABEL_12;
  }
  if ( (unsigned int)dword_1801B76C8 > 2 )
  {
    v64 = 1833;
    v65 = "Failed to ReCreateSurfaces";
    v68 = "Refresh";
    v67 = "Error HResult failed";
    *(_QWORD *)&v69.Id = "clientcore\\termsrv\\rdpplatform\\gfxpipe\\gfxsource\\umrdpgfxprovider.cpp";
    LODWORD(v66) = Surfaces;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      dword_1801B76C8,
      (unsigned int)byte_1801A4BA9,
      v8,
      v9,
      (__int64)&v67,
      (__int64)&v66,
      (__int64)&v69,
      (__int64)&v64,
      (__int64)&v68,
      (__int64)&v65);
  }
LABEL_90:
  v62 = *((_QWORD *)this + 1576);
  if ( v62 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 64LL))(v62);
LABEL_92:
  if ( v3 && *((_DWORD *)v3 + 2) )
    PAL_System_CritSecLeave(*v3);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800125d0  push    rbp
0x1800125d2  push    rbx
0x1800125d3  push    rdi
0x1800125d4  lea     rbp, [rsp-40h]
0x1800125d9  sub     rsp, 140h
0x1800125e0  mov     rax, cs:__security_cookie
0x1800125e7  xor     rax, rsp
0x1800125ea  mov     [rbp+50h+var_30], rax
0x1800125ee  xor     edi, edi
0x1800125f0  mov     [rsp+150h+arg_8], rsi
0x1800125f8  lea     rbx, [rcx+25E0h]
0x1800125ff  mov     [rbp+50h+var_A8], rdi
0x180012603  mov     rsi, rcx
0x180012606  mov     [rbp+50h+var_B0], edi
0x180012609  mov     [rbp+50h+var_C8], rdi
0x18001260d  cmp     [rbx+8], edi
0x180012610  jz      short loc_18001261B
0x180012612  mov     rcx, [rbx]
0x180012615  call    cs:__imp_PAL_System_CritSecEnter
0x18001261b  mov     rcx, [rsi+3140h]
0x180012622  mov     [rsp+150h+arg_10], r12
0x18001262a  mov     [rsp+150h+var_20], r15
0x180012632  test    rcx, rcx
0x180012635  jnz     loc_180012726
0x18001263b  mov     eax, cs:dword_1801B76C8
0x180012641  mov     edi, 1
0x180012646  cmp     eax, 3
0x180012649  jbe     loc_1800137F0
0x18001264f  mov     [rbp+50h+EventDescriptor.Keyword], rcx
0x180012653  lea     rax, [rsp+150h+var_F0]
0x180012658  mov     [rbp+50h+var_60], rax
0x18001265c  lea     r12, aRefresh; "Refresh"
0x180012663  mov     dword ptr [rsp+150h+var_F0], edi
0x180012667  lea     rax, aMSpvideodriver_2; "m_spVideoDriver is NULL: Refresh skippe"...
0x18001266e  mov     [rbp+50h+var_70], rax
0x180012672  lea     r15, _TraceLoggingMetadataEnd
0x180012679  lea     rax, aErrorCondition; "Error condition failed"
0x180012680  mov     [rbp+50h+var_50], r12
0x180012684  mov     [rbp+50h+var_80], rax
0x180012688  lea     rdx, [rbp+50h+EventDescriptor]; EventDescriptor
0x18001268c  movzx   eax, cs:word_1801A4C4E
0x180012693  xor     r9d, r9d; RelatedActivityId
0x180012696  mov     dword ptr [rbp+50h+EventDescriptor.Level], eax
0x180012699  xor     r8d, r8d; ActivityId
0x18001269c  mov     rax, cs:off_1801B76D0
0x1800126a3  mov     [rbp+50h+var_A0.Ptr], rax
0x1800126a7  mov     [rbp+50h+var_48], 8
0x1800126af  mov     [rbp+50h+var_58], 4
0x1800126b7  mov     [rbp+50h+var_68], 29h ; ')'
0x1800126bf  mov     [rbp+50h+var_78], 17h
0x1800126c7  mov     dword ptr [rbp+50h+EventDescriptor.Id], 0B000000h
0x1800126ce  movzx   eax, word ptr [rax]
0x1800126d1  mov     [rbp+50h+var_A0.Size], eax
0x1800126d4  lea     rax, unk_1801A4C58
0x1800126db  mov     [rbp+50h+var_90], rax
0x1800126df  lea     rax, _TraceLoggingMetadata
0x1800126e6  sub     r15d, eax
0x1800126e9  mov     dword ptr [rbp+50h+var_A0.0Ch], 2
0x1800126f0  mov     [rbp+50h+var_88], 34h ; '4'
0x1800126f7  mov     [rbp+50h+var_84], edi
0x1800126fa  mov     [rsp+150h+var_100], r15d
0x1800126ff  mov     eax, [rsp+150h+var_100]
0x180012703  mov     rcx, cs:qword_1801B76E8; RegHandle
0x18001270a  lea     rax, [rbp+50h+var_A0]
0x18001270e  mov     [rsp+150h+UserData], rax; UserData
0x180012713  mov     [rsp+150h+UserDataCount], 6; UserDataCount
0x18001271b  call    cs:__imp_EventWriteTransfer
0x180012721  jmp     loc_1800137F0
0x180012726  mov     rax, [rcx]
0x180012729  mov     [rsp+150h+arg_18], r13
0x180012731  mov     [rsp+150h+var_18], r14
0x180012739  mov     rax, [rax+38h]
0x18001273d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012742  lea     rcx, [rsi+2C58h]; lprc
0x180012749  mov     dword ptr [rsi+2C40h], 438h
0x180012753  xor     r9d, r9d; xRight
0x180012756  mov     dword ptr [rsi+2C44h], 5
0x180012760  xor     r8d, r8d; yTop
0x180012763  mov     [rsi+2C50h], rdi
0x18001276a  xor     edx, edx; xLeft
0x18001276c  mov     [rsp+150h+UserDataCount], edi; yBottom
0x180012770  call    cs:__imp_SetRect
0x180012776  xorps   xmm0, xmm0
0x180012779  mov     qword ptr [rsi+2C48h], 0FFFFFFFFFFFFFFFFh
0x180012784  mov     [rsi+3134h], rdi
0x18001278b  mov     rcx, rsi; this
0x18001278e  mov     dword ptr [rsi+3148h], 470h
0x180012798  mov     dword ptr [rsi+314Ch], 0Dh
0x1800127a2  movups  xmmword ptr [rsi+3578h], xmm0
0x1800127a9  movups  xmmword ptr [rsi+3588h], xmm0
0x1800127b0  movups  xmmword ptr [rsi+3598h], xmm0
0x1800127b7  movups  xmmword ptr [rsi+35A8h], xmm0
0x1800127be  mov     [rsi+35B8h], edi
0x1800127c4  call    ?ReleaseLastFrameContext@CPipeGfxProvider@@IEAAXXZ; CPipeGfxProvider::ReleaseLastFrameContext(void)
0x1800127c9  cmp     [rsi+3C20h], edi
0x1800127cf  jz      loc_180012894
0x1800127d5  cmp     [rsi+3C3Ch], dil
0x1800127dc  jnz     loc_180012894
0x1800127e2  mov     rcx, rsi; this
0x1800127e5  call    ?ReCreateSurfaces@CPipeGfxProvider@@IEAAJXZ; CPipeGfxProvider::ReCreateSurfaces(void)
0x1800127ea  mov     edi, eax
0x1800127ec  test    eax, eax
0x1800127ee  jns     loc_18001288C
0x1800127f4  mov     ecx, cs:dword_1801B76C8
0x1800127fa  cmp     ecx, 2
0x1800127fd  jbe     loc_1800137C8
0x180012803  lea     rax, aFailedToRecrea_0; "Failed to ReCreateSurfaces"
0x18001280a  mov     [rsp+150h+var_100], 729h
0x180012812  mov     [rsp+150h+var_F8], rax
0x180012817  lea     r12, aRefresh; "Refresh"
0x18001281e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180012825  mov     [rsp+150h+var_E0], r12
0x18001282a  mov     [rsp+150h+var_E8], rax
0x18001282f  lea     r13, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x180012836  lea     rax, [rsp+150h+var_F8]
0x18001283b  mov     qword ptr [rsp+150h+var_D8.Id], r13
0x180012840  mov     [rsp+150h+var_108], rax
0x180012845  lea     rdx, byte_1801A4BA9
0x18001284c  lea     rax, [rsp+150h+var_E0]
0x180012851  mov     dword ptr [rsp+150h+var_F0], edi
0x180012855  mov     [rsp+150h+var_110], rax
0x18001285a  lea     rax, [rsp+150h+var_100]
0x18001285f  mov     [rsp+150h+var_118], rax
0x180012864  lea     rax, [rsp+150h+var_D8]
0x180012869  mov     [rsp+150h+var_120], rax
0x18001286e  lea     rax, [rsp+150h+var_F0]
0x180012873  mov     [rsp+150h+UserData], rax
0x180012878  lea     rax, [rsp+150h+var_E8]
0x18001287d  mov     qword ptr [rsp+150h+UserDataCount], rax
0x180012882  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180012887  jmp     loc_1800137C8
0x18001288c  xor     edi, edi
0x18001288e  mov     [rsi+3C20h], edi
0x180012894  lea     r14, [rsi+3110h]
0x18001289b  mov     rax, [r14]
0x18001289e  mov     rcx, r14
0x1800128a1  mov     rax, [rax+40h]
0x1800128a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128aa  lea     r12, aRefresh; "Refresh"
0x1800128b1  lea     r15, _TraceLoggingMetadataEnd
0x1800128b8  lea     r13, aClientcoreTerm_0; "clientcore\\termsrv\\rdpplatform\\gfxpi"...
0x1800128bf  nop
0x1800128c0  mov     rax, [r14]
0x1800128c3  lea     rdx, [rbp+50h+var_C8]
0x1800128c7  mov     rcx, r14
0x1800128ca  mov     rax, [rax+48h]
0x1800128ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128d3  test    eax, eax
0x1800128d5  jz      loc_180012BA6
0x1800128db  mov     rax, [rbp+50h+var_C8]
0x1800128df  mov     rcx, [rax+20h]
0x1800128e3  test    rcx, rcx
0x1800128e6  jz      loc_180012B76
0x1800128ec  mov     rax, [rcx]
0x1800128ef  xor     edx, edx
0x1800128f1  mov     r8d, 0BB8h
0x1800128f7  mov     rax, [rax+40h]
0x1800128fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012900  cmp     dword ptr [rsi+3C30h], 0
0x180012907  mov     edi, eax
0x180012909  jz      loc_1800129A1
0x18001290f  test    eax, eax
0x180012911  jns     loc_180012A95
0x180012917  mov     eax, cs:dword_1801B76C8
0x18001291d  cmp     eax, 2
0x180012920  jbe     loc_1800137C8
0x180012926  lea     rax, aFailedToAcquir_0; "Failed to acquire Dx texture keyed mute"...
0x18001292d  mov     qword ptr [rsp+150h+var_D8.Id], r12
0x180012932  mov     [rsp+150h+var_E8], rax
0x180012937  lea     rdx, byte_1801A4BFB
0x18001293e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180012945  mov     dword ptr [rsp+150h+var_F8], 73Bh
0x18001294d  mov     [rsp+150h+var_F0], rax
0x180012952  lea     rax, [rsp+150h+var_E8]
0x180012957  mov     [rsp+150h+var_108], rax
0x18001295c  lea     rax, [rsp+150h+var_D8]
0x180012961  mov     [rsp+150h+var_110], rax
0x180012966  lea     rax, [rsp+150h+var_F8]
0x18001296b  mov     [rsp+150h+var_118], rax
0x180012970  lea     rax, [rsp+150h+var_E0]
0x180012975  mov     [rsp+150h+var_120], rax
0x18001297a  lea     rax, [rsp+150h+var_100]
0x18001297f  mov     [rsp+150h+UserData], rax
0x180012984  lea     rax, [rsp+150h+var_F0]
0x180012989  mov     qword ptr [rsp+150h+UserDataCount], rax
0x18001298e  mov     [rsp+150h+var_E0], r13
0x180012993  mov     [rsp+150h+var_100], edi
0x180012997  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001299c  jmp     loc_1800137C8
0x1800129a1  test    edi, edi
0x1800129a3  jns     loc_180012A95
0x1800129a9  mov     eax, cs:dword_1801B76C8
0x1800129af  cmp     eax, 2
0x1800129b2  jbe     loc_180012A95
0x1800129b8  xor     ecx, ecx
0x1800129ba  mov     [rsp+150h+var_100], 740h
0x1800129c2  mov     [rbp+50h+EventDescriptor.Keyword], rcx
0x1800129c6  lea     rax, [rsp+150h+var_100]
0x1800129cb  mov     [rbp+50h+var_50], rax
0x1800129cf  lea     rcx, _TraceLoggingMetadata
0x1800129d6  mov     dword ptr [rsp+150h+var_F0], edi
0x1800129da  lea     rax, [rsp+150h+var_F0]
0x1800129df  mov     [rbp+50h+var_70], rax
0x1800129e3  lea     rdx, [rbp+50h+EventDescriptor]; EventDescriptor
0x1800129e7  lea     rax, aFailedToAcquir_0; "Failed to acquire Dx texture keyed mute"...
0x1800129ee  mov     [rbp+50h+var_40], r12
0x1800129f2  mov     [rbp+50h+var_80], rax
0x1800129f6  xor     r9d, r9d; RelatedActivityId
0x1800129f9  movzx   eax, cs:word_1801A4B29
0x180012a00  xor     r8d, r8d; ActivityId
0x180012a03  mov     dword ptr [rbp+50h+EventDescriptor.Level], eax
0x180012a06  mov     rax, cs:off_1801B76D0
0x180012a0d  mov     [rbp+50h+var_A0.Ptr], rax
0x180012a11  mov     [rbp+50h+var_38], 8
0x180012a19  mov     [rbp+50h+var_48], 4
0x180012a21  mov     [rbp+50h+var_60], r13
0x180012a25  mov     [rbp+50h+var_58], 46h ; 'F'
0x180012a2d  mov     [rbp+50h+var_68], 4
0x180012a35  mov     [rbp+50h+var_78], 29h ; ')'
0x180012a3d  mov     dword ptr [rbp+50h+EventDescriptor.Id], 0B000000h
0x180012a44  movzx   eax, word ptr [rax]
0x180012a47  mov     [rbp+50h+var_A0.Size], eax
0x180012a4a  lea     rax, byte_1801A4B33
0x180012a51  mov     [rbp+50h+var_90], rax
0x180012a55  mov     rax, r15
0x180012a58  sub     eax, ecx
0x180012a5a  mov     dword ptr [rbp+50h+var_A0.0Ch], 2
0x180012a61  mov     [rbp+50h+var_88], 3Eh ; '>'
0x180012a68  mov     [rbp+50h+var_84], 1
0x180012a6f  mov     dword ptr [rsp+150h+var_F8], eax
0x180012a73  mov     eax, dword ptr [rsp+150h+var_F8]
0x180012a77  mov     rcx, cs:qword_1801B76E8; RegHandle
0x180012a7e  lea     rax, [rbp+50h+var_A0]
0x180012a82  mov     [rsp+150h+UserData], rax; UserData
0x180012a87  mov     [rsp+150h+UserDataCount], 7; UserDataCount
0x180012a8f  call    cs:__imp_EventWriteTransfer
0x180012a95  mov     eax, cs:dword_1801B76C8
0x180012a9b  cmp     eax, 5
0x180012a9e  jbe     loc_180012B70
0x180012aa4  mov     rax, [rbp+50h+var_C8]
0x180012aa8  lea     rdx, [rsp+150h+var_D8]; EventDescriptor
0x180012aad  mov     dword ptr [rsp+150h+var_F8], edi
0x180012ab1  xor     r9d, r9d; RelatedActivityId
0x180012ab4  mov     [rbp+50h+var_58], 4
0x180012abc  xor     r8d, r8d; ActivityId
0x180012abf  mov     [rbp+50h+var_68], 8
0x180012ac7  mov     rcx, [rax]
0x180012aca  lea     rax, [rsp+150h+var_F8]
0x180012acf  mov     [rbp+50h+var_60], rax
0x180012ad3  lea     rax, [rsp+150h+var_E8]
0x180012ad8  mov     [rbp+50h+var_70], rax
0x180012adc  lea     rax, aDxTextureKeyed; "Dx texture keyed mutex acquired"
0x180012ae3  mov     [rbp+50h+var_80], rax
0x180012ae7  movzx   eax, cs:word_1801A4B73
0x180012aee  mov     dword ptr [rsp+150h+var_D8.Level], eax
0x180012af2  mov     rax, cs:off_1801B76D0
0x180012af9  mov     [rbp+50h+var_A0.Ptr], rax
0x180012afd  mov     [rsp+150h+var_E8], rcx
0x180012b02  xor     ecx, ecx
0x180012b04  mov     [rbp+50h+var_D8.Keyword], rcx
0x180012b08  lea     rcx, _TraceLoggingMetadata
0x180012b0f  mov     [rbp+50h+var_78], 20h ; ' '
0x180012b17  mov     dword ptr [rsp+150h+var_D8.Id], 0B000000h
0x180012b1f  movzx   eax, word ptr [rax]
0x180012b22  mov     [rbp+50h+var_A0.Size], eax
0x180012b25  lea     rax, byte_1801A4B7D
0x180012b2c  mov     [rbp+50h+var_90], rax
0x180012b30  mov     rax, r15
0x180012b33  sub     eax, ecx
0x180012b35  mov     dword ptr [rbp+50h+var_A0.0Ch], 2
0x180012b3c  mov     [rbp+50h+var_88], 2Bh ; '+'
0x180012b43  mov     [rbp+50h+var_84], 1
0x180012b4a  mov     [rsp+150h+var_100], eax
0x180012b4e  mov     eax, [rsp+150h+var_100]
0x180012b52  mov     rcx, cs:qword_1801B76E8; RegHandle
0x180012b59  lea     rax, [rbp+50h+var_A0]
0x180012b5d  mov     [rsp+150h+UserData], rax; UserData
0x180012b62  mov     [rsp+150h+UserDataCount], 5; UserDataCount
0x180012b6a  call    cs:__imp_EventWriteTransfer
0x180012b70  mov     rax, [rbp+50h+var_C8]
0x180012b74  xor     edi, edi
0x180012b76  mov     [rax+50h], edi
0x180012b79  xor     r9d, r9d; xRight
0x180012b7c  mov     rcx, [rbp+50h+var_C8]
0x180012b80  xor     r8d, r8d; yTop
0x180012b83  add     rcx, 58h ; 'X'; lprc
0x180012b87  mov     [rsp+150h+UserDataCount], edi; yBottom
0x180012b8b  xor     edx, edx; xLeft
0x180012b8d  call    cs:__imp_SetRect
0x180012b93  mov     rax, [rbp+50h+var_C8]
0x180012b97  mov     [rax+34h], edi
0x180012b9a  mov     rax, [rbp+50h+var_C8]
0x180012b9e  mov     [rax+38h], edi
0x180012ba1  jmp     loc_1800128C0
0x180012ba6  cmp     dword ptr [rsi+3130h], 0
0x180012bad  jz      loc_180012D6C
0x180012bb3  mov     rax, [r14]
0x180012bb6  mov     rcx, r14
0x180012bb9  mov     rax, [rax+40h]
0x180012bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
