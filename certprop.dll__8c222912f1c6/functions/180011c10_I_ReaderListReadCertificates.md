# I_ReaderListReadCertificates

- ea: `0x180011c10`
- end: `0x180012686`
- name: `I_ReaderListReadCertificates`
- size: `2678`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _DWORD *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180003230`
- `0x180004600`
- `0x180005e10`
- `0x1800062e0`
- `0x180011c10`
- `0x180012690`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011cb0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011cbf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011e7e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011e8d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800125dd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011cb0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011cbf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011e7e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180011e8d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800125dd`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011d55`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011f24`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001239b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800124b0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800125ce`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011d55`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011f24`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001239b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800124b0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800125ce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001263f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001263f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012656`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180012656`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012631`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012631`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d77`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d77`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011d96`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180011d96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800124f2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800124bb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800124bb`

## pseudocode

```c
void __fastcall I_ReaderListReadCertificates(PTP_CALLBACK_INSTANCE Instance, _DWORD *Context, PTP_WORK Work)
{
  int v3; // r15d
  struct _TP_WORK *v4; // rbx
  int *v6; // rdi
  int v7; // r14d
  unsigned int v8; // r12d
  __int64 v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rbx
  char v12; // al
  __int64 v13; // rbx
  int i; // r14d
  int updated; // eax
  int CertsFromCard; // eax
  __int64 *v17; // rcx
  __int64 v18; // rax
  bool v19; // zf
  int v20; // eax
  int v21; // eax
  __int64 *v22; // rcx
  __int64 v23; // rax
  int v24; // eax
  __int64 *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  __int64 *v28; // rcx
  __int64 v29; // rax
  int v30; // eax
  __int64 *v31; // rcx
  __int64 v32; // rax
  int v33; // eax
  __int64 *v34; // rcx
  __int64 v35; // rax
  int v36; // eax
  __int64 *v37; // rcx
  __int64 v38; // rax
  int v39; // eax
  __int64 v40; // rcx
  __int64 v41; // rbx
  char LastError; // al
  __int64 v43; // rcx
  unsigned int v44; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v45; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int v46; // [rsp+38h] [rbp-C8h] BYREF
  int v47; // [rsp+3Ch] [rbp-C4h] BYREF
  int v48; // [rsp+40h] [rbp-C0h] BYREF
  int v49; // [rsp+44h] [rbp-BCh] BYREF
  PTP_WORK v50; // [rsp+48h] [rbp-B8h]
  int v51; // [rsp+50h] [rbp-B0h] BYREF
  int v52; // [rsp+54h] [rbp-ACh] BYREF
  int v53; // [rsp+58h] [rbp-A8h] BYREF
  int v54; // [rsp+5Ch] [rbp-A4h] BYREF
  int v55; // [rsp+60h] [rbp-A0h] BYREF
  int v56; // [rsp+64h] [rbp-9Ch] BYREF
  int v57; // [rsp+68h] [rbp-98h] BYREF
  int v58; // [rsp+6Ch] [rbp-94h] BYREF
  int v59; // [rsp+70h] [rbp-90h] BYREF
  int v60; // [rsp+74h] [rbp-8Ch] BYREF
  int v61; // [rsp+78h] [rbp-88h] BYREF
  EVENT_DESCRIPTOR v62; // [rsp+88h] [rbp-78h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+98h] [rbp-68h] BYREF
  GUID RelatedActivityId; // [rsp+A8h] [rbp-58h] BYREF
  GUID ActivityId; // [rsp+B8h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C8h] [rbp-38h] BYREF
  int *v67; // [rsp+D8h] [rbp-28h]
  int v68; // [rsp+E0h] [rbp-20h]
  int v69; // [rsp+E4h] [rbp-1Ch]
  struct _EVENT_DATA_DESCRIPTOR v70; // [rsp+F0h] [rbp-10h] BYREF
  char *v71; // [rsp+100h] [rbp+0h]
  int v72; // [rsp+108h] [rbp+8h]
  int v73; // [rsp+10Ch] [rbp+Ch]
  int *v74; // [rsp+110h] [rbp+10h]
  __int64 v75; // [rsp+118h] [rbp+18h]
  int *v76; // [rsp+120h] [rbp+20h]
  __int64 v77; // [rsp+128h] [rbp+28h]
  int *v78; // [rsp+130h] [rbp+30h]
  __int64 v79; // [rsp+138h] [rbp+38h]
  struct _EVENT_DATA_DESCRIPTOR v80; // [rsp+140h] [rbp+40h] BYREF
  __int16 *v81; // [rsp+150h] [rbp+50h]
  int v82; // [rsp+158h] [rbp+58h]
  int v83; // [rsp+15Ch] [rbp+5Ch]
  unsigned int *v84; // [rsp+160h] [rbp+60h]
  __int64 v85; // [rsp+168h] [rbp+68h]
  int *v86; // [rsp+170h] [rbp+70h]
  __int64 v87; // [rsp+178h] [rbp+78h]
  __int64 *v88; // [rsp+180h] [rbp+80h]
  int v89; // [rsp+188h] [rbp+88h]
  int v90; // [rsp+18Ch] [rbp+8Ch]
  int *v91; // [rsp+190h] [rbp+90h]
  __int64 v92; // [rsp+198h] [rbp+98h]
  __int64 *v93; // [rsp+1A0h] [rbp+A0h]
  int v94; // [rsp+1A8h] [rbp+A8h]
  int v95; // [rsp+1ACh] [rbp+ACh]
  __int64 *v96; // [rsp+1B0h] [rbp+B0h]
  int v97; // [rsp+1B8h] [rbp+B8h]
  int v98; // [rsp+1BCh] [rbp+BCh]
  __int64 *v99; // [rsp+1C0h] [rbp+C0h]
  int v100; // [rsp+1C8h] [rbp+C8h]
  int v101; // [rsp+1CCh] [rbp+CCh]
  __int64 *v102; // [rsp+1D0h] [rbp+D0h]
  int v103; // [rsp+1D8h] [rbp+D8h]
  int v104; // [rsp+1DCh] [rbp+DCh]
  __int64 *v105; // [rsp+1E0h] [rbp+E0h]
  int v106; // [rsp+1E8h] [rbp+E8h]
  int v107; // [rsp+1ECh] [rbp+ECh]
  __int64 *v108; // [rsp+1F0h] [rbp+F0h]
  int v109; // [rsp+1F8h] [rbp+F8h]
  int v110; // [rsp+1FCh] [rbp+FCh]
  int *v111; // [rsp+200h] [rbp+100h]
  __int64 v112; // [rsp+208h] [rbp+108h]
  int *v113; // [rsp+210h] [rbp+110h]
  __int64 v114; // [rsp+218h] [rbp+118h]
  int *v115; // [rsp+220h] [rbp+120h]
  __int64 v116; // [rsp+228h] [rbp+128h]
  int *v117; // [rsp+230h] [rbp+130h]
  __int64 v118; // [rsp+238h] [rbp+138h]
  int *v119; // [rsp+240h] [rbp+140h]
  __int64 v120; // [rsp+248h] [rbp+148h]
  int *v121; // [rsp+250h] [rbp+150h]
  __int64 v122; // [rsp+258h] [rbp+158h]
  int *v123; // [rsp+260h] [rbp+160h]
  __int64 v124; // [rsp+268h] [rbp+168h]
  int *v125; // [rsp+270h] [rbp+170h]
  __int64 v126; // [rsp+278h] [rbp+178h]
  int *v127; // [rsp+280h] [rbp+180h]
  __int64 v128; // [rsp+288h] [rbp+188h]
  unsigned int *v129; // [rsp+290h] [rbp+190h]
  __int64 v130; // [rsp+298h] [rbp+198h]
  int *v131; // [rsp+2A0h] [rbp+1A0h]
  __int64 v132; // [rsp+2A8h] [rbp+1A8h]
  int *v133; // [rsp+2B0h] [rbp+1B0h]
  __int64 v134; // [rsp+2B8h] [rbp+1B8h]

  v3 = 0;
  v4 = Work;
  v50 = Work;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  WppTraceIndent(Instance, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  RelatedActivityId = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &RelatedActivityId);
  if ( (unsigned int)dword_180031008 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_180031010;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180031010;
    v67 = &dword_18002AA34;
    UserData.Reserved = 2;
    v68 = 49;
    v69 = 1;
    v44 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &RelatedActivityId, &ActivityId, 2u, &UserData);
  }
  if ( Context )
  {
    v9 = *(_QWORD *)Context;
    if ( *(_QWORD *)Context )
    {
      v6 = *(int **)Context;
      EnterCriticalSection((LPCRITICAL_SECTION)(v9 + 48));
      v7 = 1;
      v49 = 1;
      if ( !*(_DWORD *)v9 || SetThreadToken(0, *(HANDLE *)(v9 + 248)) )
      {
        v13 = *(_QWORD *)(v9 + 112);
        for ( i = 0; v13; v13 = *(_QWORD *)(v13 + 240) )
        {
          ++v8;
          *(_QWORD *)(v13 + 216) = 0;
          if ( *(_QWORD *)(v13 + 16) )
          {
            if ( *(_DWORD *)(v13 + 144) )
            {
              updated = ReaderMonitorUpdateCerts(v6, v13);
              *(_DWORD *)(v13 + 160) = updated;
              if ( !updated )
              {
                i += *(_DWORD *)(v13 + 216);
                v3 += *(_DWORD *)(v13 + 220);
              }
            }
            else
            {
              EventDescriptor = 0;
              EventActivityIdControl(3u, (LPGUID)&EventDescriptor);
              EventActivityIdControl(2u, (LPGUID)&EventDescriptor);
              if ( (unsigned int)dword_180031008 > 5 )
              {
                *(_DWORD *)&v62.Level = 261;
                v70.Ptr = (ULONGLONG)off_180031010;
                *(_DWORD *)&v62.Id = 184549376;
                v62.Keyword = 0;
                v70.Size = *(unsigned __int16 *)off_180031010;
                v71 = byte_18002A9C1;
                v70.Reserved = 2;
                v72 = 31;
                v73 = 1;
                v44 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(RegHandle, &v62, (LPCGUID)&EventDescriptor, &RelatedActivityId, 2u, &v70);
              }
              if ( Context[2] )
              {
                CertsFromCard = I_ReaderListReadCertsFromCard(v6, v13);
                *(_DWORD *)(v13 + 160) = CertsFromCard;
                if ( !CertsFromCard )
                  i += *(_DWORD *)(v13 + 216);
              }
              if ( Context[3] )
              {
                I_ReaderListReadRootCertsFromCard(v6, v13);
                v3 += *(_DWORD *)(v13 + 220);
              }
              if ( (unsigned int)dword_180031008 > 5 )
              {
                v17 = *(__int64 **)v13;
                v44 = Context[2];
                v84 = &v44;
                v51 = Context[3];
                v86 = &v51;
                v85 = 4;
                v87 = 4;
                if ( v17 )
                {
                  v18 = -1;
                  do
                    v19 = *((_WORD *)v17 + ++v18) == 0;
                  while ( !v19 );
                  v20 = 2 * v18 + 2;
                }
                else
                {
                  v17 = &qword_180027F58;
                  v20 = 2;
                }
                v89 = v20;
                v21 = *(_DWORD *)(v13 + 8);
                v88 = v17;
                v22 = *(__int64 **)(v13 + 16);
                v52 = v21;
                v91 = &v52;
                v90 = 0;
                v92 = 4;
                if ( v22 )
                {
                  v23 = -1;
                  do
                    v19 = *((_WORD *)v22 + ++v23) == 0;
                  while ( !v19 );
                  v24 = 2 * v23 + 2;
                }
                else
                {
                  v22 = &qword_180027F58;
                  v24 = 2;
                }
                v93 = v22;
                v25 = *(__int64 **)(v13 + 80);
                v94 = v24;
                v95 = 0;
                if ( v25 )
                {
                  v26 = -1;
                  do
                    v19 = *((_WORD *)v25 + ++v26) == 0;
                  while ( !v19 );
                  v27 = 2 * v26 + 2;
                }
                else
                {
                  v25 = &qword_180027F58;
                  v27 = 2;
                }
                v96 = v25;
                v28 = *(__int64 **)(v13 + 88);
                v97 = v27;
                v98 = 0;
                if ( v28 )
                {
                  v29 = -1;
                  do
                    v19 = *((_WORD *)v28 + ++v29) == 0;
                  while ( !v19 );
                  v30 = 2 * v29 + 2;
                }
                else
                {
                  v28 = &qword_180027F58;
                  v30 = 2;
                }
                v99 = v28;
                v31 = *(__int64 **)(v13 + 96);
                v100 = v30;
                v101 = 0;
                if ( v31 )
                {
                  v32 = -1;
                  do
                    v19 = *((_WORD *)v31 + ++v32) == 0;
                  while ( !v19 );
                  v33 = 2 * v32 + 2;
                }
                else
                {
                  v31 = &qword_180027F58;
                  v33 = 2;
                }
                v102 = v31;
                v34 = *(__int64 **)(v13 + 104);
                v103 = v33;
                v104 = 0;
                if ( v34 )
                {
                  v35 = -1;
                  do
                    v19 = *((_WORD *)v34 + ++v35) == 0;
                  while ( !v19 );
                  v36 = 2 * v35 + 2;
                }
                else
                {
                  v34 = &qword_180027F58;
                  v36 = 2;
                }
                v105 = v34;
                v37 = *(__int64 **)(v13 + 112);
                v106 = v36;
                v107 = 0;
                if ( v37 )
                {
                  v38 = -1;
                  do
                    v19 = *((_WORD *)v37 + ++v38) == 0;
                  while ( !v19 );
                  v39 = 2 * v38 + 2;
                }
                else
                {
                  v37 = &qword_180027F58;
                  v39 = 2;
                }
                v109 = v39;
                v53 = *(_DWORD *)(v13 + 120);
                v111 = &v53;
                v113 = &v54;
                v55 = v6[64];
                v115 = &v55;
                v56 = *v6;
                v117 = &v56;
                v57 = v6[1];
                v119 = &v57;
                v58 = v6[2];
                v121 = &v58;
                v59 = v6[3];
                v123 = &v59;
                v60 = v6[4];
                v125 = &v60;
                v61 = v6[5];
                v127 = &v61;
                v46 = v6[10];
                v129 = &v46;
                v47 = v6[6];
                v131 = &v47;
                v133 = &v48;
                v80.Ptr = (ULONGLONG)off_180031010;
                v108 = v37;
                v54 = *(_DWORD *)(v13 + 160);
                v48 = v54;
                v110 = 0;
                v112 = 4;
                v114 = 4;
                v116 = 4;
                v118 = 4;
                v120 = 4;
                v122 = 4;
                v124 = 4;
                v126 = 4;
                v128 = 4;
                v130 = 4;
                v132 = 4;
                v134 = 4;
                UserData.Ptr = 0x2050B000000LL;
                *(_QWORD *)&UserData.Size = 0;
                v80.Size = *(unsigned __int16 *)off_180031010;
                v81 = word_18002A1C2;
                v80.Reserved = 2;
                v82 = 656;
                v83 = 1;
                v45 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(
                  RegHandle,
                  (PCEVENT_DESCRIPTOR)&UserData,
                  (LPCGUID)&EventDescriptor,
                  &RelatedActivityId,
                  0x18u,
                  &v80);
              }
            }
          }
        }
        if ( (unsigned int)dword_180031008 > 5
          && (qword_180031018 & 0x200000000000LL) != 0
          && (qword_180031020 & 0x200000000000LL) == qword_180031020 )
        {
          *(_QWORD *)&UserData.Size = 0x200000000000LL;
          v74 = (int *)&v45;
          v45 = v8;
          v76 = &v48;
          v75 = 4;
          v78 = &v47;
          v70.Ptr = (ULONGLONG)off_180031010;
          v48 = i;
          v77 = 4;
          v47 = v3;
          v79 = 4;
          UserData.Ptr = 0x50B000000LL;
          v70.Size = *(unsigned __int16 *)off_180031010;
          v71 = byte_18002AAC1;
          v70.Reserved = 2;
          v72 = 103;
          v73 = 1;
          v46 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, &RelatedActivityId, &ActivityId, 5u, &v70);
        }
        if ( *v6 )
        {
          if ( !RevertToSelf() )
          {
            WppTraceIndent(v40, 2);
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
            {
              v41 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              LastError = GetLastError();
              WPP_SF_sD(
                v41,
                184,
                (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
                WPP_pszIndent,
                LastError);
            }
          }
        }
        I_ReaderMonitorSetReaderActionEvent(v6);
        v7 = v49;
      }
      else
      {
        WppTraceIndent(v10, 2);
        if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[28] & 1) != 0
          && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
        {
          v11 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v12 = GetLastError();
          WPP_SF_sD(v11, 183, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, v12);
        }
      }
    }
    v4 = v50;
  }
  if ( (unsigned int)dword_180031008 > 5 )
  {
    v49 = v8;
    v74 = &v49;
    v70.Ptr = (ULONGLONG)off_180031010;
    v75 = 4;
    UserData.Ptr = 0x2050B000000LL;
    *(_QWORD *)&UserData.Size = 0;
    v70.Size = *(unsigned __int16 *)off_180031010;
    v71 = (char *)&unk_18002AB80;
    v70.Reserved = 2;
    v72 = 65;
    v73 = 1;
    v45 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, (PCEVENT_DESCRIPTOR)&UserData, &RelatedActivityId, &ActivityId, 3u, &v70);
  }
  EventActivityIdControl(2u, &ActivityId);
  WppTraceIndent(v43, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( v7 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 12));
  if ( v4 )
    CloseThreadpoolWork(v4);
  if ( Context )
    HeapFree(hHeap, 0, Context);
}

```

## disassembly

```asm
0x180011c10  mov     [rsp-8+arg_0], rbx
0x180011c15  push    rbp
0x180011c16  push    rsi
0x180011c17  push    rdi
0x180011c18  push    r12
0x180011c1a  push    r13
0x180011c1c  push    r14
0x180011c1e  push    r15
0x180011c20  lea     rbp, [rsp-1D0h]
0x180011c28  sub     rsp, 2D0h
0x180011c2f  mov     rax, cs:__security_cookie
0x180011c36  xor     rax, rsp
0x180011c39  mov     [rbp+200h+var_40], rax
0x180011c40  xor     r15d, r15d
0x180011c43  mov     rbx, r8
0x180011c46  mov     rsi, rdx
0x180011c49  mov     [rsp+300h+var_2B8], rbx
0x180011c4e  xor     edx, edx
0x180011c50  mov     edi, r15d
0x180011c53  mov     r14d, r15d
0x180011c56  mov     r12d, r15d
0x180011c59  call    WppTraceIndent
0x180011c5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180011c65  lea     rax, WPP_GLOBAL_Control
0x180011c6c  cmp     rcx, rax
0x180011c6f  jz      short loc_180011C99
0x180011c71  test    byte ptr [rcx+1Ch], 2
0x180011c75  jz      short loc_180011C99
0x180011c77  cmp     byte ptr [rcx+19h], 5
0x180011c7b  jb      short loc_180011C99
0x180011c7d  mov     r9, cs:WPP_pszIndent
0x180011c84  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180011c8b  mov     rcx, [rcx+10h]
0x180011c8f  mov     edx, 0B6h
0x180011c94  call    WPP_SF_s
0x180011c99  xorps   xmm0, xmm0
0x180011c9c  lea     rdx, [rbp+200h+ActivityId]; ActivityId
0x180011ca0  xorps   xmm1, xmm1
0x180011ca3  mov     ecx, 5; ControlCode
0x180011ca8  movups  xmmword ptr [rbp+200h+ActivityId.Data1], xmm0
0x180011cac  movups  xmmword ptr [rbp+200h+RelatedActivityId.Data1], xmm1
0x180011cb0  call    cs:__imp_EventActivityIdControl
0x180011cb6  lea     rdx, [rbp+200h+RelatedActivityId]; ActivityId
0x180011cba  mov     ecx, 1; ControlCode
0x180011cbf  call    cs:__imp_EventActivityIdControl
0x180011cc5  mov     eax, cs:dword_180031008
0x180011ccb  lea     r13, _TraceLoggingMetadataEnd
0x180011cd2  lea     rcx, _TraceLoggingMetadata
0x180011cd9  cmp     eax, 5
0x180011cdc  jbe     short loc_180011D5B
0x180011cde  movzx   eax, cs:word_18002AA2A
0x180011ce5  lea     r9, [rbp+200h+ActivityId]; RelatedActivityId
0x180011ce9  mov     dword ptr [rbp+200h+EventDescriptor.Level], eax
0x180011cec  lea     r8, [rbp+200h+RelatedActivityId]; ActivityId
0x180011cf0  mov     rax, cs:off_180031010
0x180011cf7  lea     rdx, [rbp+200h+EventDescriptor]; EventDescriptor
0x180011cfb  mov     [rbp+200h+var_238.Ptr], rax
0x180011cff  mov     dword ptr [rbp+200h+EventDescriptor.Id], 0B000000h
0x180011d06  mov     [rbp+200h+EventDescriptor.Keyword], r15
0x180011d0a  movzx   eax, word ptr [rax]
0x180011d0d  mov     [rbp+200h+var_238.Size], eax
0x180011d10  lea     rax, dword_18002AA34
0x180011d17  mov     [rbp+200h+var_228], rax
0x180011d1b  mov     rax, r13
0x180011d1e  sub     eax, ecx
0x180011d20  mov     dword ptr [rbp+200h+var_238.0Ch], 2
0x180011d27  mov     [rbp+200h+var_220], 31h ; '1'
0x180011d2e  mov     [rbp+200h+var_21C], 1
0x180011d35  mov     [rsp+300h+var_2D0], eax
0x180011d39  mov     eax, [rsp+300h+var_2D0]
0x180011d3d  mov     rcx, cs:RegHandle; RegHandle
0x180011d44  lea     rax, [rbp+200h+var_238]
0x180011d48  mov     [rsp+300h+UserData], rax; UserData
0x180011d4d  mov     [rsp+300h+UserDataCount], 2; UserDataCount
0x180011d55  call    cs:__imp_EventWriteTransfer
0x180011d5b  test    rsi, rsi
0x180011d5e  jz      loc_18001252C
0x180011d64  mov     rbx, [rsi]
0x180011d67  test    rbx, rbx
0x180011d6a  jz      loc_180012527
0x180011d70  lea     rcx, [rbx+30h]; lpCriticalSection
0x180011d74  mov     rdi, rbx
0x180011d77  call    cs:__imp_EnterCriticalSection
0x180011d7d  mov     r14d, 1
0x180011d83  mov     [rsp+300h+var_2BC], r14d
0x180011d88  cmp     [rbx], r15d
0x180011d8b  jz      short loc_180011E03
0x180011d8d  mov     rdx, [rbx+0F8h]; Token
0x180011d94  xor     ecx, ecx; Thread
0x180011d96  call    cs:__imp_SetThreadToken
0x180011d9c  test    eax, eax
0x180011d9e  jnz     short loc_180011E03
0x180011da0  mov     edx, 2
0x180011da5  call    WppTraceIndent
0x180011daa  mov     rbx, cs:WPP_GLOBAL_Control
0x180011db1  lea     rax, WPP_GLOBAL_Control
0x180011db8  cmp     rbx, rax
0x180011dbb  jz      loc_180012527
0x180011dc1  test    [rbx+1Ch], r14b
0x180011dc5  jz      loc_180012527
0x180011dcb  cmp     byte ptr [rbx+19h], 3
0x180011dcf  jb      loc_180012527
0x180011dd5  mov     rbx, [rbx+10h]
0x180011dd9  call    cs:__imp_GetLastError
0x180011ddf  mov     r9, cs:WPP_pszIndent
0x180011de6  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180011ded  mov     edx, 0B7h
0x180011df2  mov     [rsp+300h+UserDataCount], eax
0x180011df6  mov     rcx, rbx
0x180011df9  call    WPP_SF_sD
0x180011dfe  jmp     loc_180012527
0x180011e03  mov     rbx, [rbx+70h]
0x180011e07  xor     r14d, r14d
0x180011e0a  test    rbx, rbx
0x180011e0d  jz      loc_1800123B1
0x180011e13  nop     dword ptr [rax+00h]
0x180011e17  nop     word ptr [rax+rax+00000000h]
0x180011e20  inc     r12d
0x180011e23  mov     qword ptr [rbx+0D8h], 0
0x180011e2e  cmp     qword ptr [rbx+10h], 0
0x180011e33  jz      loc_1800123A1
0x180011e39  cmp     dword ptr [rbx+90h], 0
0x180011e40  jz      short loc_180011E6E
0x180011e42  mov     rdx, rbx
0x180011e45  mov     rcx, rdi
0x180011e48  call    ReaderMonitorUpdateCerts
0x180011e4d  mov     [rbx+0A0h], eax
0x180011e53  test    eax, eax
0x180011e55  jnz     loc_1800123A1
0x180011e5b  add     r14d, [rbx+0D8h]
0x180011e62  add     r15d, [rbx+0DCh]
0x180011e69  jmp     loc_1800123A1
0x180011e6e  xorps   xmm0, xmm0
0x180011e71  lea     rdx, [rbp+200h+EventDescriptor]; ActivityId
0x180011e75  mov     ecx, 3; ControlCode
0x180011e7a  movups  xmmword ptr [rbp+200h+EventDescriptor.Id], xmm0
0x180011e7e  call    cs:__imp_EventActivityIdControl
0x180011e84  lea     rdx, [rbp+200h+EventDescriptor]; ActivityId
0x180011e88  mov     ecx, 2; ControlCode
0x180011e8d  call    cs:__imp_EventActivityIdControl
0x180011e93  mov     eax, cs:dword_180031008
0x180011e99  cmp     eax, 5
0x180011e9c  jbe     loc_180011F2A
0x180011ea2  movzx   eax, cs:word_18002A9B7
0x180011ea9  lea     rcx, _TraceLoggingMetadata
0x180011eb0  mov     dword ptr [rbp+200h+var_278.Level], eax
0x180011eb3  lea     r9, [rbp+200h+RelatedActivityId]; RelatedActivityId
0x180011eb7  mov     rax, cs:off_180031010
0x180011ebe  lea     r8, [rbp+200h+EventDescriptor]; ActivityId
0x180011ec2  mov     [rbp+200h+var_210.Ptr], rax
0x180011ec6  lea     rdx, [rbp+200h+var_278]; EventDescriptor
0x180011eca  mov     dword ptr [rbp+200h+var_278.Id], 0B000000h
0x180011ed1  mov     [rbp+200h+var_278.Keyword], 0
0x180011ed9  movzx   eax, word ptr [rax]
0x180011edc  mov     [rbp+200h+var_210.Size], eax
0x180011edf  lea     rax, byte_18002A9C1
0x180011ee6  mov     [rbp+200h+var_200], rax
0x180011eea  mov     rax, r13
0x180011eed  sub     eax, ecx
0x180011eef  mov     dword ptr [rbp+200h+var_210.0Ch], 2
0x180011ef6  mov     [rbp+200h+var_1F8], 1Fh
0x180011efd  mov     [rbp+200h+var_1F4], 1
0x180011f04  mov     [rsp+300h+var_2D0], eax
0x180011f08  mov     eax, [rsp+300h+var_2D0]
0x180011f0c  mov     rcx, cs:RegHandle; RegHandle
0x180011f13  lea     rax, [rbp+200h+var_210]
0x180011f17  mov     [rsp+300h+UserData], rax; UserData
0x180011f1c  mov     [rsp+300h+UserDataCount], 2; UserDataCount
0x180011f24  call    cs:__imp_EventWriteTransfer
0x180011f2a  cmp     dword ptr [rsi+8], 0
0x180011f2e  jz      short loc_180011F4C
0x180011f30  mov     rdx, rbx
0x180011f33  mov     rcx, rdi
0x180011f36  call    I_ReaderListReadCertsFromCard
0x180011f3b  mov     [rbx+0A0h], eax
0x180011f41  test    eax, eax
0x180011f43  jnz     short loc_180011F4C
0x180011f45  add     r14d, [rbx+0D8h]
0x180011f4c  cmp     dword ptr [rsi+0Ch], 0
0x180011f50  jz      short loc_180011F64
0x180011f52  mov     rdx, rbx
0x180011f55  mov     rcx, rdi
0x180011f58  call    I_ReaderListReadRootCertsFromCard
0x180011f5d  add     r15d, [rbx+0DCh]
0x180011f64  mov     eax, cs:dword_180031008
0x180011f6a  cmp     eax, 5
0x180011f6d  jbe     loc_1800123A1
0x180011f73  mov     eax, [rsi+8]
0x180011f76  xor     edx, edx
0x180011f78  mov     rcx, [rbx]
0x180011f7b  mov     [rsp+300h+var_2D0], eax
0x180011f7f  lea     rax, [rsp+300h+var_2D0]
0x180011f84  mov     [rbp+200h+var_1A0], rax
0x180011f88  mov     eax, [rsi+0Ch]
0x180011f8b  mov     [rsp+300h+var_2B0], eax
0x180011f8f  lea     rax, [rsp+300h+var_2B0]
0x180011f94  mov     [rbp+200h+var_190], rax
0x180011f98  mov     [rbp+200h+var_198], 4
0x180011fa0  mov     [rbp+200h+var_188], 4
0x180011fa8  test    rcx, rcx
0x180011fab  jz      short loc_180011FC8
0x180011fad  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180011fb4  cmp     [rcx+rax*2+2], dx
0x180011fb9  lea     rax, [rax+1]
0x180011fbd  jnz     short loc_180011FB4
0x180011fbf  lea     eax, ds:2[rax*2]
0x180011fc6  jmp     short loc_180011FD4
0x180011fc8  lea     rcx, qword_180027F58
0x180011fcf  mov     eax, 2
0x180011fd4  mov     [rbp+200h+var_178], eax
0x180011fda  mov     eax, [rbx+8]
0x180011fdd  mov     [rbp+200h+var_180], rcx
0x180011fe4  mov     rcx, [rbx+10h]
0x180011fe8  mov     [rsp+300h+var_2AC], eax
0x180011fec  lea     rax, [rsp+300h+var_2AC]
0x180011ff1  mov     [rbp+200h+var_170], rax
0x180011ff8  mov     [rbp+200h+var_174], edx
0x180011ffe  mov     [rbp+200h+var_168], 4
0x180012009  test    rcx, rcx
0x18001200c  jz      short loc_180012029
0x18001200e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012015  cmp     [rcx+rax*2+2], dx
0x18001201a  lea     rax, [rax+1]
0x18001201e  jnz     short loc_180012015
0x180012020  lea     eax, ds:2[rax*2]
0x180012027  jmp     short loc_180012035
0x180012029  lea     rcx, qword_180027F58
0x180012030  mov     eax, 2
0x180012035  mov     [rbp+200h+var_160], rcx
0x18001203c  mov     rcx, [rbx+50h]
0x180012040  mov     [rbp+200h+var_158], eax
0x180012046  mov     [rbp+200h+var_154], edx
0x18001204c  test    rcx, rcx
0x18001204f  jz      short loc_180012074
0x180012051  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012058  nop     dword ptr [rax+rax+00000000h]
0x180012060  cmp     [rcx+rax*2+2], dx
0x180012065  lea     rax, [rax+1]
0x180012069  jnz     short loc_180012060
0x18001206b  lea     eax, ds:2[rax*2]
0x180012072  jmp     short loc_180012080
0x180012074  lea     rcx, qword_180027F58
0x18001207b  mov     eax, 2
0x180012080  mov     [rbp+200h+var_150], rcx
0x180012087  mov     rcx, [rbx+58h]
0x18001208b  mov     [rbp+200h+var_148], eax
0x180012091  mov     [rbp+200h+var_144], edx
0x180012097  test    rcx, rcx
0x18001209a  jz      short loc_1800120B7
0x18001209c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800120a3  cmp     [rcx+rax*2+2], dx
0x1800120a8  lea     rax, [rax+1]
0x1800120ac  jnz     short loc_1800120A3
0x1800120ae  lea     eax, ds:2[rax*2]
0x1800120b5  jmp     short loc_1800120C3
0x1800120b7  lea     rcx, qword_180027F58
0x1800120be  mov     eax, 2
0x1800120c3  mov     [rbp+200h+var_140], rcx
0x1800120ca  mov     rcx, [rbx+60h]
0x1800120ce  mov     [rbp+200h+var_138], eax
0x1800120d4  mov     [rbp+200h+var_134], edx
0x1800120da  test    rcx, rcx
0x1800120dd  jz      short loc_180012104
0x1800120df  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800120e6  nop     word ptr [rax+rax+00000000h]
0x1800120f0  cmp     [rcx+rax*2+2], dx
0x1800120f5  lea     rax, [rax+1]
0x1800120f9  jnz     short loc_1800120F0
0x1800120fb  lea     eax, ds:2[rax*2]
0x180012102  jmp     short loc_180012110
0x180012104  lea     rcx, qword_180027F58
0x18001210b  mov     eax, 2
0x180012110  mov     [rbp+200h+var_130], rcx
0x180012117  mov     rcx, [rbx+68h]
0x18001211b  mov     [rbp+200h+var_128], eax
0x180012121  mov     [rbp+200h+var_124], edx
0x180012127  test    rcx, rcx
0x18001212a  jz      short loc_180012147
0x18001212c  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012133  cmp     [rcx+rax*2+2], dx
0x180012138  lea     rax, [rax+1]
0x18001213c  jnz     short loc_180012133
0x18001213e  lea     eax, ds:2[rax*2]
0x180012145  jmp     short loc_180012153
0x180012147  lea     rcx, qword_180027F58
0x18001214e  mov     eax, 2
0x180012153  mov     [rbp+200h+var_120], rcx
0x18001215a  mov     rcx, [rbx+70h]
0x18001215e  mov     [rbp+200h+var_118], eax
0x180012164  mov     [rbp+200h+var_114], edx
0x18001216a  test    rcx, rcx
0x18001216d  jz      short loc_180012194
0x18001216f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180012176  nop     word ptr [rax+rax+00000000h]
0x180012180  cmp     [rcx+rax*2+2], dx
0x180012185  lea     rax, [rax+1]
0x180012189  jnz     short loc_180012180
0x18001218b  lea     eax, ds:2[rax*2]
0x180012192  jmp     short loc_1800121A0
0x180012194  lea     rcx, qword_180027F58
  ... truncated ...
```
