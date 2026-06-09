# I_ReaderListReaderProcessingWorker

- ea: `0x180012d90`
- end: `0x180013aa1`
- name: `I_ReaderListReaderProcessingWorker`
- size: `3345`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, __int64 *Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004600`
- `0x1800115c0`
- `0x180012d90`
- `0x180016090`
- `0x180018b58`
- `0x180018bb4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012e26`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012e35`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013450`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012e26`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180012e35`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180013450`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012ed6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800132c0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013441`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013953`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180012ed6`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800132c0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013441`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180013953`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x1800132d0`
- `api-ms-win-core-threadpool-l1-2-0!SetEventWhenCallbackReturns` at `0x1800132d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013361`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001338b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013361`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013379`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001338b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013a46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013a46`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180013a1b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800132e8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800132e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013323`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013995`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001395e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001395e`

## pseudocode

```c
void __fastcall I_ReaderListReaderProcessingWorker(PTP_CALLBACK_INSTANCE Instance, __int64 *Context, PTP_WORK Work)
{
  __int64 v5; // rcx
  __int64 v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 *v9; // rcx
  __int64 v10; // rax
  bool v11; // zf
  int v12; // eax
  unsigned int v13; // eax
  __int64 *v14; // rcx
  __int64 v15; // rax
  int v16; // eax
  __int64 *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  __int64 *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  __int64 *v23; // rcx
  __int64 v24; // rax
  int v25; // eax
  __int64 *v26; // rcx
  __int64 v27; // rax
  int v28; // eax
  __int64 *v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rbx
  char v34; // al
  void *v35; // r8
  void *v36; // r8
  __int64 v37; // rcx
  unsigned int v38; // eax
  __int64 v39; // rcx
  unsigned int v40; // r15d
  __int64 *v41; // rcx
  __int64 v42; // rax
  int v43; // eax
  unsigned int v44; // eax
  __int64 *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  __int64 *v48; // rcx
  __int64 v49; // rax
  int v50; // eax
  __int64 *v51; // rcx
  __int64 v52; // rax
  int v53; // eax
  __int64 *v54; // rcx
  __int64 v55; // rax
  int v56; // eax
  __int64 *v57; // rcx
  __int64 v58; // rax
  int v59; // eax
  __int64 *v60; // rax
  int v61; // ebx
  __int64 v62; // rbx
  char LastError; // al
  __int64 *v64; // rcx
  __int64 i; // rax
  unsigned int v66; // [rsp+38h] [rbp-D0h] BYREF
  int v67; // [rsp+3Ch] [rbp-CCh] BYREF
  int v68; // [rsp+40h] [rbp-C8h] BYREF
  int v69; // [rsp+44h] [rbp-C4h] BYREF
  int v70; // [rsp+48h] [rbp-C0h] BYREF
  int v71; // [rsp+4Ch] [rbp-BCh] BYREF
  int v72; // [rsp+50h] [rbp-B8h] BYREF
  int v73; // [rsp+54h] [rbp-B4h] BYREF
  int v74; // [rsp+58h] [rbp-B0h] BYREF
  int v75; // [rsp+5Ch] [rbp-ACh] BYREF
  int v76; // [rsp+60h] [rbp-A8h] BYREF
  int v77; // [rsp+64h] [rbp-A4h] BYREF
  unsigned int v78; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v79; // [rsp+6Ch] [rbp-9Ch]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-98h] BYREF
  int v81; // [rsp+80h] [rbp-88h] BYREF
  int v82; // [rsp+84h] [rbp-84h] BYREF
  int v83; // [rsp+88h] [rbp-80h] BYREF
  int v84; // [rsp+8Ch] [rbp-7Ch] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-78h] BYREF
  GUID v86; // [rsp+A0h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-58h] BYREF
  char *v88; // [rsp+C0h] [rbp-48h]
  int v89; // [rsp+C8h] [rbp-40h]
  int v90; // [rsp+CCh] [rbp-3Ch]
  struct _EVENT_DATA_DESCRIPTOR v91; // [rsp+D8h] [rbp-30h] BYREF
  __int16 *v92; // [rsp+E8h] [rbp-20h]
  int v93; // [rsp+F0h] [rbp-18h]
  int v94; // [rsp+F4h] [rbp-14h]
  __int64 *v95; // [rsp+F8h] [rbp-10h]
  int v96; // [rsp+100h] [rbp-8h]
  int v97; // [rsp+104h] [rbp-4h]
  unsigned int *v98; // [rsp+108h] [rbp+0h]
  __int64 v99; // [rsp+110h] [rbp+8h]
  __int64 *v100; // [rsp+118h] [rbp+10h]
  int v101; // [rsp+120h] [rbp+18h]
  int v102; // [rsp+124h] [rbp+1Ch]
  __int64 *v103; // [rsp+128h] [rbp+20h]
  int v104; // [rsp+130h] [rbp+28h]
  int v105; // [rsp+134h] [rbp+2Ch]
  __int64 *v106; // [rsp+138h] [rbp+30h]
  int v107; // [rsp+140h] [rbp+38h]
  int v108; // [rsp+144h] [rbp+3Ch]
  __int64 *v109; // [rsp+148h] [rbp+40h]
  int v110; // [rsp+150h] [rbp+48h]
  int v111; // [rsp+154h] [rbp+4Ch]
  __int64 *v112; // [rsp+158h] [rbp+50h]
  int v113; // [rsp+160h] [rbp+58h]
  int v114; // [rsp+164h] [rbp+5Ch]
  __int64 *v115; // [rsp+168h] [rbp+60h]
  int v116; // [rsp+170h] [rbp+68h]
  int v117; // [rsp+174h] [rbp+6Ch]
  int *v118; // [rsp+178h] [rbp+70h]
  __int64 v119; // [rsp+180h] [rbp+78h]
  int *v120; // [rsp+188h] [rbp+80h]
  __int64 v121; // [rsp+190h] [rbp+88h]
  int *v122; // [rsp+198h] [rbp+90h]
  __int64 v123; // [rsp+1A0h] [rbp+98h]
  int *v124; // [rsp+1A8h] [rbp+A0h]
  __int64 v125; // [rsp+1B0h] [rbp+A8h]
  int *v126; // [rsp+1B8h] [rbp+B0h]
  __int64 v127; // [rsp+1C0h] [rbp+B8h]
  int *v128; // [rsp+1C8h] [rbp+C0h]
  __int64 v129; // [rsp+1D0h] [rbp+C8h]
  int *v130; // [rsp+1D8h] [rbp+D0h]
  __int64 v131; // [rsp+1E0h] [rbp+D8h]
  int *v132; // [rsp+1E8h] [rbp+E0h]
  __int64 v133; // [rsp+1F0h] [rbp+E8h]
  int *v134; // [rsp+1F8h] [rbp+F0h]
  __int64 v135; // [rsp+200h] [rbp+F8h]
  int *v136; // [rsp+208h] [rbp+100h]
  __int64 v137; // [rsp+210h] [rbp+108h]
  int *v138; // [rsp+218h] [rbp+110h]
  __int64 v139; // [rsp+220h] [rbp+118h]
  unsigned int *v140; // [rsp+228h] [rbp+120h]
  __int64 v141; // [rsp+230h] [rbp+128h]
  int *v142; // [rsp+238h] [rbp+130h]
  __int64 v143; // [rsp+240h] [rbp+138h]
  int *v144; // [rsp+248h] [rbp+140h]
  __int64 v145; // [rsp+250h] [rbp+148h]
  int *v146; // [rsp+258h] [rbp+150h]
  __int64 v147; // [rsp+260h] [rbp+158h]
  int *v148; // [rsp+268h] [rbp+160h]
  __int64 v149; // [rsp+270h] [rbp+168h]

  WppTraceIndent(Instance, 0);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  ActivityId = 0;
  v86 = 0;
  EventActivityIdControl(5u, &ActivityId);
  EventActivityIdControl(1u, &v86);
  if ( (unsigned int)dword_180031008 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 261;
    UserData.Ptr = (ULONGLONG)off_180031010;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180031010;
    v88 = byte_18002B135;
    UserData.Reserved = 2;
    v89 = 49;
    v90 = 1;
    v66 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &v86, &ActivityId, 2u, &UserData);
  }
  if ( Context )
  {
    v6 = *Context;
    if ( *Context )
    {
      v7 = Context[1];
      if ( v7 )
      {
        v8 = -1;
        if ( (unsigned int)dword_180031008 > 5 )
        {
          v9 = *(__int64 **)v7;
          if ( *(_QWORD *)v7 )
          {
            v10 = -1;
            do
              v11 = *((_WORD *)v9 + ++v10) == 0;
            while ( !v11 );
            v12 = 2 * v10 + 2;
          }
          else
          {
            v9 = &qword_180027F58;
            v12 = 2;
          }
          v96 = v12;
          v13 = *(_DWORD *)(v7 + 8);
          v95 = v9;
          v14 = *(__int64 **)(v7 + 16);
          v66 = v13;
          v98 = &v66;
          v97 = 0;
          v99 = 4;
          if ( v14 )
          {
            v15 = -1;
            do
              v11 = *((_WORD *)v14 + ++v15) == 0;
            while ( !v11 );
            v16 = 2 * v15 + 2;
          }
          else
          {
            v14 = &qword_180027F58;
            v16 = 2;
          }
          v100 = v14;
          v17 = *(__int64 **)(v7 + 80);
          v101 = v16;
          v102 = 0;
          if ( v17 )
          {
            v18 = -1;
            do
              v11 = *((_WORD *)v17 + ++v18) == 0;
            while ( !v11 );
            v19 = 2 * v18 + 2;
          }
          else
          {
            v17 = &qword_180027F58;
            v19 = 2;
          }
          v103 = v17;
          v20 = *(__int64 **)(v7 + 88);
          v104 = v19;
          v105 = 0;
          if ( v20 )
          {
            v21 = -1;
            do
              v11 = *((_WORD *)v20 + ++v21) == 0;
            while ( !v11 );
            v22 = 2 * v21 + 2;
          }
          else
          {
            v20 = &qword_180027F58;
            v22 = 2;
          }
          v106 = v20;
          v23 = *(__int64 **)(v7 + 96);
          v107 = v22;
          v108 = 0;
          if ( v23 )
          {
            v24 = -1;
            do
              v11 = *((_WORD *)v23 + ++v24) == 0;
            while ( !v11 );
            v25 = 2 * v24 + 2;
          }
          else
          {
            v23 = &qword_180027F58;
            v25 = 2;
          }
          v109 = v23;
          v26 = *(__int64 **)(v7 + 104);
          v110 = v25;
          v111 = 0;
          if ( v26 )
          {
            v27 = -1;
            do
              v11 = *((_WORD *)v26 + ++v27) == 0;
            while ( !v11 );
            v28 = 2 * v27 + 2;
          }
          else
          {
            v26 = &qword_180027F58;
            v28 = 2;
          }
          v112 = v26;
          v29 = *(__int64 **)(v7 + 112);
          v113 = v28;
          v114 = 0;
          if ( v29 )
          {
            v30 = -1;
            do
              v11 = *((_WORD *)v29 + ++v30) == 0;
            while ( !v11 );
            v31 = 2 * v30 + 2;
          }
          else
          {
            v29 = &qword_180027F58;
            v31 = 2;
          }
          v116 = v31;
          v67 = *(_DWORD *)(v7 + 120);
          v118 = &v67;
          v68 = *(_DWORD *)(v7 + 160);
          v120 = &v68;
          v69 = *(_DWORD *)(v6 + 256);
          v122 = &v69;
          v70 = *(_DWORD *)v6;
          v124 = &v70;
          v71 = *(_DWORD *)(v6 + 4);
          v126 = &v71;
          v72 = *(_DWORD *)(v6 + 8);
          v128 = &v72;
          v73 = *(_DWORD *)(v6 + 12);
          v130 = &v73;
          v74 = *(_DWORD *)(v6 + 16);
          v132 = &v74;
          v75 = *(_DWORD *)(v6 + 20);
          v134 = &v75;
          v76 = *(_DWORD *)(v6 + 40);
          v136 = &v76;
          v77 = *(_DWORD *)(v6 + 24);
          v138 = &v77;
          *(_DWORD *)&EventDescriptor.Level = 5;
          v91.Ptr = (ULONGLONG)off_180031010;
          v115 = v29;
          v117 = 0;
          v119 = 4;
          v121 = 4;
          v123 = 4;
          v125 = 4;
          v127 = 4;
          v129 = 4;
          v131 = 4;
          v133 = 4;
          v135 = 4;
          v137 = 4;
          v139 = 4;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          v91.Size = *(unsigned __int16 *)off_180031010;
          v92 = &word_18002AEB6;
          v91.Reserved = 2;
          v93 = 627;
          v94 = 1;
          v78 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, &v86, &ActivityId, 0x15u, &v91);
        }
        SetEventWhenCallbackReturns(Instance, *(HANDLE *)(v6 + 352));
        if ( !*(_DWORD *)v6 || SetThreadToken(0, *(HANDLE *)(v6 + 248)) )
        {
          *(_QWORD *)(v7 + 216) = 0;
          v38 = I_ReaderListCollectCertificates(
                  (int *)v6,
                  v7,
                  *((_DWORD *)Context + 4),
                  (const void *)Context[3],
                  *((_DWORD *)Context + 8));
          v39 = (unsigned int)dword_180031008;
          v40 = v38;
          if ( (unsigned int)dword_180031008 > 5 )
          {
            v39 = qword_180031018;
            if ( (qword_180031018 & 0x200000000000LL) != 0 )
            {
              v39 = qword_180031020 & 0x200000000000LL;
              if ( (qword_180031020 & 0x200000000000LL) == qword_180031020 )
              {
                v41 = *(__int64 **)v7;
                if ( *(_QWORD *)v7 )
                {
                  v42 = -1;
                  do
                    v11 = *((_WORD *)v41 + ++v42) == 0;
                  while ( !v11 );
                  v43 = 2 * v42 + 2;
                }
                else
                {
                  v41 = &qword_180027F58;
                  v43 = 2;
                }
                v96 = v43;
                v44 = *(_DWORD *)(v7 + 8);
                v95 = v41;
                v45 = *(__int64 **)(v7 + 16);
                v78 = v44;
                v98 = &v78;
                v97 = 0;
                v99 = 4;
                if ( v45 )
                {
                  v46 = -1;
                  do
                    v11 = *((_WORD *)v45 + ++v46) == 0;
                  while ( !v11 );
                  v47 = 2 * v46 + 2;
                }
                else
                {
                  v45 = &qword_180027F58;
                  v47 = 2;
                }
                v100 = v45;
                v48 = *(__int64 **)(v7 + 80);
                v101 = v47;
                v102 = 0;
                if ( v48 )
                {
                  v49 = -1;
                  do
                    v11 = *((_WORD *)v48 + ++v49) == 0;
                  while ( !v11 );
                  v50 = 2 * v49 + 2;
                }
                else
                {
                  v48 = &qword_180027F58;
                  v50 = 2;
                }
                v103 = v48;
                v51 = *(__int64 **)(v7 + 88);
                v104 = v50;
                v105 = 0;
                if ( v51 )
                {
                  v52 = -1;
                  do
                    v11 = *((_WORD *)v51 + ++v52) == 0;
                  while ( !v11 );
                  v53 = 2 * v52 + 2;
                }
                else
                {
                  v51 = &qword_180027F58;
                  v53 = 2;
                }
                v106 = v51;
                v54 = *(__int64 **)(v7 + 96);
                v107 = v53;
                v108 = 0;
                if ( v54 )
                {
                  v55 = -1;
                  do
                    v11 = *((_WORD *)v54 + ++v55) == 0;
                  while ( !v11 );
                  v56 = 2 * v55 + 2;
                }
                else
                {
                  v54 = &qword_180027F58;
                  v56 = 2;
                }
                v109 = v54;
                v57 = *(__int64 **)(v7 + 104);
                v110 = v56;
                v111 = 0;
                if ( v57 )
                {
                  v58 = -1;
                  do
                    v11 = *((_WORD *)v57 + ++v58) == 0;
                  while ( !v11 );
                  v59 = 2 * v58 + 2;
                }
                else
                {
                  v57 = &qword_180027F58;
                  v59 = 2;
                }
                v113 = v59;
                v60 = *(__int64 **)(v7 + 112);
                v112 = v57;
                v114 = 0;
                if ( v60 )
                {
                  do
                    v11 = *((_WORD *)v60 + ++v8) == 0;
                  while ( !v11 );
                  v61 = 2 * v8 + 2;
                }
                else
                {
                  v60 = &qword_180027F58;
                  v61 = 2;
                }
                v115 = v60;
                v77 = *(_DWORD *)(v7 + 120);
                v118 = &v77;
                v76 = *(_DWORD *)(v7 + 160);
                v120 = &v76;
                v75 = *(_DWORD *)(v6 + 256);
                v122 = &v75;
                v74 = *(_DWORD *)v6;
                v124 = &v74;
                v73 = *(_DWORD *)(v6 + 4);
                v126 = &v73;
                v72 = *(_DWORD *)(v6 + 8);
                v128 = &v72;
                v71 = *(_DWORD *)(v6 + 12);
                v130 = &v71;
                v70 = *(_DWORD *)(v6 + 16);
                v132 = &v70;
                v69 = *(_DWORD *)(v6 + 20);
                v134 = &v69;
                v68 = *(_DWORD *)(v6 + 40);
                v136 = &v68;
                v67 = *(_DWORD *)(v6 + 24);
                v138 = &v67;
                v140 = &v66;
                v81 = *(_DWORD *)(v7 + 216);
                v142 = &v81;
                v82 = *(_DWORD *)(v7 + 220);
                v144 = &v82;
                v83 = *(_DWORD *)(v7 + 224);
                v146 = &v83;
                v84 = *(_DWORD *)(v7 + 228);
                v148 = &v84;
                v116 = v61;
                v117 = 0;
                v119 = 4;
                v121 = 4;
                v123 = 4;
                v125 = 4;
                v127 = 4;
                v129 = 4;
                v131 = 4;
                v133 = 4;
                v135 = 4;
                v137 = 4;
                v139 = 4;
                v66 = v40;
                v141 = 4;
                v143 = 4;
                v145 = 4;
                v147 = 4;
                *(_DWORD *)&EventDescriptor.Level = 5;
                v91.Ptr = (ULONGLONG)off_180031010;
                EventDescriptor.Keyword = 0x200000000000LL;
                v149 = 4;
                *(_DWORD *)&EventDescriptor.Id = 184549376;
                v91.Size = *(unsigned __int16 *)off_180031010;
                v92 = (__int16 *)byte_18002ABCD;
                v91.Reserved = 2;
                v93 = 733;
                v94 = 1;
                v79 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
                EventWriteTransfer(RegHandle, &EventDescriptor, &v86, &ActivityId, 0x1Au, &v91);
              }
            }
          }
          if ( *(_DWORD *)v6 )
          {
            if ( !RevertToSelf() )
            {
              WppTraceIndent(v39, 2);
              if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
                && (WPP_GLOBAL_Control[28] & 1) != 0
                && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
              {
                v62 = *((_QWORD *)WPP_GLOBAL_Control + 2);
                LastError = GetLastError();
                WPP_SF_sD(
                  v62,
                  205,
                  (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
                  WPP_pszIndent,
                  LastError);
              }
            }
          }
          if ( v40 )
          {
            WppTraceIndent(v39, 2);
            if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[28] & 1) != 0
              && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
            {
              WPP_SF_sD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                206,
                (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
                WPP_pszIndent,
                v40);
            }
          }
          *(_DWORD *)(v7 + 160) = v40;
          *(_QWORD *)(v7 + 240) = 0;
          EnterCriticalSection((LPCRITICAL_SECTION)(v6 + 48));
          v64 = (__int64 *)(v6 + 368);
          for ( i = *(_QWORD *)(v6 + 368); i; i = *(_QWORD *)(i + 240) )
            v64 = (__int64 *)(i + 240);
          *v64 = v7;
          LeaveCriticalSection((LPCRITICAL_SECTION)(v6 + 48));
          Context[1] = 0;
        }
        else
        {
          WppTraceIndent(v32, 2);
          if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[28] & 1) != 0
            && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
          {
            v33 = *((_QWORD *)WPP_GLOBAL_Control + 2);
            v34 = GetLastError();
            WPP_SF_sD(v33, 204, (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent, v34);
          }
        }
LABEL_53:
        v35 = (void *)Context[1];
        if ( v35 )
          HeapFree(hHeap, 0, v35);
        v36 = (void *)Context[3];
        if ( v36 )
          HeapFree(hHeap, 0, v36);
        HeapFree(hHeap, 0, Context);
        goto LABEL_58;
      }
    }
  }
  WppTraceIndent(v5, 2);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 1) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 3u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( Context )
    goto LABEL_53;
LABEL_58:
  if ( (unsigned int)dword_180031008 > 5 )
  {
    *(_DWORD *)&EventDescriptor.Level = 517;
    UserData.Ptr = (ULONGLONG)off_180031010;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = *(unsigned __int16 *)off_180031010;
    v88 = &byte_18002A057;
    UserData.Reserved = 2;
    v89 = 48;
    v90 = 1;
    v79 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, &v86, &ActivityId, 2u, &UserData);
  }
  EventActivityIdControl(2u, &ActivityId);
  WppTraceIndent(v37, 1);
  if ( WPP_GLOBAL_Control != (STRSAFE_LPSTR)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[28] & 2) != 0
    && (unsigned __int8)WPP_GLOBAL_Control[25] >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 207, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
}

```

## disassembly

```asm
0x180012d90  mov     r11, rsp
0x180012d93  push    rbp
0x180012d94  lea     rbp, [r11-1B8h]
0x180012d9b  sub     rsp, 2B0h
0x180012da2  mov     rax, cs:__security_cookie
0x180012da9  xor     rax, rsp
0x180012dac  mov     [rbp+1B0h+var_40], rax
0x180012db3  mov     [r11+18h], rbx
0x180012db7  mov     [r11-20h], r12
0x180012dbb  mov     [r11-28h], r13
0x180012dbf  mov     [r11-30h], r14
0x180012dc3  mov     r14, rdx
0x180012dc6  mov     [r11-38h], r15
0x180012dca  xor     edx, edx
0x180012dcc  mov     r15, rcx
0x180012dcf  call    WppTraceIndent
0x180012dd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ddb  lea     rbx, WPP_GLOBAL_Control
0x180012de2  cmp     rcx, rbx
0x180012de5  jz      short loc_180012E0F
0x180012de7  test    byte ptr [rcx+1Ch], 2
0x180012deb  jz      short loc_180012E0F
0x180012ded  cmp     byte ptr [rcx+19h], 5
0x180012df1  jb      short loc_180012E0F
0x180012df3  mov     r9, cs:WPP_pszIndent
0x180012dfa  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180012e01  mov     rcx, [rcx+10h]
0x180012e05  mov     edx, 0CAh
0x180012e0a  call    WPP_SF_s
0x180012e0f  xorps   xmm0, xmm0
0x180012e12  lea     rdx, [rbp+1B0h+ActivityId]; ActivityId
0x180012e16  xorps   xmm1, xmm1
0x180012e19  mov     ecx, 5; ControlCode
0x180012e1e  movups  xmmword ptr [rbp+1B0h+ActivityId.Data1], xmm0
0x180012e22  movups  xmmword ptr [rbp+1B0h+var_218.Data1], xmm1
0x180012e26  call    cs:__imp_EventActivityIdControl
0x180012e2c  lea     rdx, [rbp+1B0h+var_218]; ActivityId
0x180012e30  mov     ecx, 1; ControlCode
0x180012e35  call    cs:__imp_EventActivityIdControl
0x180012e3b  mov     eax, cs:dword_180031008
0x180012e41  lea     r12, _TraceLoggingMetadataEnd
0x180012e48  xor     r13d, r13d
0x180012e4b  lea     rdx, _TraceLoggingMetadata
0x180012e52  cmp     eax, 5
0x180012e55  jbe     loc_180012EE3
0x180012e5b  movzx   eax, cs:word_18002B12B
0x180012e62  lea     r9, [rbp+1B0h+ActivityId]; RelatedActivityId
0x180012e66  mov     dword ptr [rsp+2B0h+EventDescriptor.Level], eax
0x180012e6a  lea     r8, [rbp+1B0h+var_218]; ActivityId
0x180012e6e  mov     rax, cs:off_180031010
0x180012e75  mov     [rbp+1B0h+var_208.Ptr], rax
0x180012e79  mov     dword ptr [rsp+2B0h+EventDescriptor.Id], 0B000000h
0x180012e81  mov     [rsp+2B0h+EventDescriptor.Keyword], r13
0x180012e86  movzx   eax, word ptr [rax]
0x180012e89  mov     [rbp+1B0h+var_208.Size], eax
0x180012e8c  lea     rax, byte_18002B135
0x180012e93  mov     [rbp+1B0h+var_1F8], rax
0x180012e97  mov     rax, r12
0x180012e9a  sub     eax, edx
0x180012e9c  mov     dword ptr [rbp+1B0h+var_208.0Ch], 2
0x180012ea3  mov     [rbp+1B0h+var_1F0], 31h ; '1'
0x180012eaa  lea     rdx, [rsp+2B0h+EventDescriptor]; EventDescriptor
0x180012eaf  mov     [rbp+1B0h+var_1EC], 1
0x180012eb6  mov     [rsp+2B0h+var_280], eax
0x180012eba  mov     eax, [rsp+2B0h+var_280]
0x180012ebe  mov     rcx, cs:RegHandle; RegHandle
0x180012ec5  lea     rax, [rbp+1B0h+var_208]
0x180012ec9  mov     [rsp+2B0h+UserData], rax; UserData
0x180012ece  mov     [rsp+2B0h+UserDataCount], 2; UserDataCount
0x180012ed6  call    cs:__imp_EventWriteTransfer
0x180012edc  lea     rdx, _TraceLoggingMetadata
0x180012ee3  mov     [rsp+2A8h], rsi
0x180012eeb  mov     [rsp+2B0h+var_10], rdi
0x180012ef3  test    r14, r14
0x180012ef6  jz      loc_180013A55
0x180012efc  mov     rsi, [r14]
0x180012eff  test    rsi, rsi
0x180012f02  jz      loc_180013A55
0x180012f08  mov     rdi, [r14+8]
0x180012f0c  test    rdi, rdi
0x180012f0f  jz      loc_180013A55
0x180012f15  mov     eax, cs:dword_180031008
0x180012f1b  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180012f22  cmp     eax, 5
0x180012f25  jbe     loc_1800132C6
0x180012f2b  mov     rcx, [rdi]
0x180012f2e  test    rcx, rcx
0x180012f31  jz      short loc_180012F55
0x180012f33  mov     rax, rbx
0x180012f36  nop     word ptr [rax+rax+00000000h]
0x180012f40  cmp     [rcx+rax*2+2], r13w
0x180012f46  lea     rax, [rax+1]
0x180012f4a  jnz     short loc_180012F40
0x180012f4c  lea     eax, ds:2[rax*2]
0x180012f53  jmp     short loc_180012F61
0x180012f55  lea     rcx, qword_180027F58
0x180012f5c  mov     eax, 2
0x180012f61  mov     [rbp+1B0h+var_1B8], eax
0x180012f64  mov     eax, [rdi+8]
0x180012f67  mov     [rbp+1B0h+var_1C0], rcx
0x180012f6b  mov     rcx, [rdi+10h]
0x180012f6f  mov     [rsp+2B0h+var_280], eax
0x180012f73  lea     rax, [rsp+2B0h+var_280]
0x180012f78  mov     [rbp+1B0h+var_1B0], rax
0x180012f7c  mov     [rbp+1B0h+var_1B4], r13d
0x180012f80  mov     [rbp+1B0h+var_1A8], 4
0x180012f88  test    rcx, rcx
0x180012f8b  jz      short loc_180012FA5
0x180012f8d  mov     rax, rbx
0x180012f90  cmp     [rcx+rax*2+2], r13w
0x180012f96  lea     rax, [rax+1]
0x180012f9a  jnz     short loc_180012F90
0x180012f9c  lea     eax, ds:2[rax*2]
0x180012fa3  jmp     short loc_180012FB1
0x180012fa5  lea     rcx, qword_180027F58
0x180012fac  mov     eax, 2
0x180012fb1  mov     [rbp+1B0h+var_1A0], rcx
0x180012fb5  mov     rcx, [rdi+50h]
0x180012fb9  mov     [rbp+1B0h+var_198], eax
0x180012fbc  mov     [rbp+1B0h+var_194], r13d
0x180012fc0  test    rcx, rcx
0x180012fc3  jz      short loc_180012FE5
0x180012fc5  mov     rax, rbx
0x180012fc8  nop     dword ptr [rax+rax+00000000h]
0x180012fd0  cmp     [rcx+rax*2+2], r13w
0x180012fd6  lea     rax, [rax+1]
0x180012fda  jnz     short loc_180012FD0
0x180012fdc  lea     eax, ds:2[rax*2]
0x180012fe3  jmp     short loc_180012FF1
0x180012fe5  lea     rcx, qword_180027F58
0x180012fec  mov     eax, 2
0x180012ff1  mov     [rbp+1B0h+var_190], rcx
0x180012ff5  mov     rcx, [rdi+58h]
0x180012ff9  mov     [rbp+1B0h+var_188], eax
0x180012ffc  mov     [rbp+1B0h+var_184], r13d
0x180013000  test    rcx, rcx
0x180013003  jz      short loc_180013025
0x180013005  mov     rax, rbx
0x180013008  nop     dword ptr [rax+rax+00000000h]
0x180013010  cmp     [rcx+rax*2+2], r13w
0x180013016  lea     rax, [rax+1]
0x18001301a  jnz     short loc_180013010
0x18001301c  lea     eax, ds:2[rax*2]
0x180013023  jmp     short loc_180013031
0x180013025  lea     rcx, qword_180027F58
0x18001302c  mov     eax, 2
0x180013031  mov     [rbp+1B0h+var_180], rcx
0x180013035  mov     rcx, [rdi+60h]
0x180013039  mov     [rbp+1B0h+var_178], eax
0x18001303c  mov     [rbp+1B0h+var_174], r13d
0x180013040  test    rcx, rcx
0x180013043  jz      short loc_180013065
0x180013045  mov     rax, rbx
0x180013048  nop     dword ptr [rax+rax+00000000h]
0x180013050  cmp     [rcx+rax*2+2], r13w
0x180013056  lea     rax, [rax+1]
0x18001305a  jnz     short loc_180013050
0x18001305c  lea     eax, ds:2[rax*2]
0x180013063  jmp     short loc_180013071
0x180013065  lea     rcx, qword_180027F58
0x18001306c  mov     eax, 2
0x180013071  mov     [rbp+1B0h+var_170], rcx
0x180013075  mov     rcx, [rdi+68h]
0x180013079  mov     [rbp+1B0h+var_168], eax
0x18001307c  mov     [rbp+1B0h+var_164], r13d
0x180013080  test    rcx, rcx
0x180013083  jz      short loc_1800130A5
0x180013085  mov     rax, rbx
0x180013088  nop     dword ptr [rax+rax+00000000h]
0x180013090  cmp     [rcx+rax*2+2], r13w
0x180013096  lea     rax, [rax+1]
0x18001309a  jnz     short loc_180013090
0x18001309c  lea     eax, ds:2[rax*2]
0x1800130a3  jmp     short loc_1800130B1
0x1800130a5  lea     rcx, qword_180027F58
0x1800130ac  mov     eax, 2
0x1800130b1  mov     [rbp+1B0h+var_160], rcx
0x1800130b5  mov     rcx, [rdi+70h]
0x1800130b9  mov     [rbp+1B0h+var_158], eax
0x1800130bc  mov     [rbp+1B0h+var_154], r13d
0x1800130c0  test    rcx, rcx
0x1800130c3  jz      short loc_1800130E5
0x1800130c5  mov     rax, rbx
0x1800130c8  nop     dword ptr [rax+rax+00000000h]
0x1800130d0  cmp     [rcx+rax*2+2], r13w
0x1800130d6  lea     rax, [rax+1]
0x1800130da  jnz     short loc_1800130D0
0x1800130dc  lea     eax, ds:2[rax*2]
0x1800130e3  jmp     short loc_1800130F1
0x1800130e5  lea     rcx, qword_180027F58
0x1800130ec  mov     eax, 2
0x1800130f1  mov     [rbp+1B0h+var_148], eax
0x1800130f4  lea     r9, [rbp+1B0h+ActivityId]; RelatedActivityId
0x1800130f8  mov     eax, [rdi+78h]
0x1800130fb  lea     r8, [rbp+1B0h+var_218]; ActivityId
0x1800130ff  mov     [rsp+2B0h+var_27C], eax
0x180013103  lea     rax, [rsp+2B0h+var_27C]
0x180013108  mov     [rbp+1B0h+var_140], rax
0x18001310c  mov     eax, [rdi+0A0h]
0x180013112  mov     [rsp+2B0h+var_278], eax
0x180013116  lea     rax, [rsp+2B0h+var_278]
0x18001311b  mov     [rbp+1B0h+var_130], rax
0x180013122  mov     eax, [rsi+100h]
0x180013128  mov     [rsp+2B0h+var_274], eax
0x18001312c  lea     rax, [rsp+2B0h+var_274]
0x180013131  mov     [rbp+1B0h+var_120], rax
0x180013138  mov     eax, [rsi]
0x18001313a  mov     [rsp+2B0h+var_270], eax
0x18001313e  lea     rax, [rsp+2B0h+var_270]
0x180013143  mov     [rbp+1B0h+var_110], rax
0x18001314a  mov     eax, [rsi+4]
0x18001314d  mov     [rsp+2B0h+var_26C], eax
0x180013151  lea     rax, [rsp+2B0h+var_26C]
0x180013156  mov     [rbp+1B0h+var_100], rax
0x18001315d  mov     eax, [rsi+8]
0x180013160  mov     [rsp+2B0h+var_268], eax
0x180013164  lea     rax, [rsp+2B0h+var_268]
0x180013169  mov     [rbp+1B0h+var_F0], rax
0x180013170  mov     eax, [rsi+0Ch]
0x180013173  mov     [rsp+2B0h+var_264], eax
0x180013177  lea     rax, [rsp+2B0h+var_264]
0x18001317c  mov     [rbp+1B0h+var_E0], rax
0x180013183  mov     eax, [rsi+10h]
0x180013186  mov     [rsp+2B0h+var_260], eax
0x18001318a  lea     rax, [rsp+2B0h+var_260]
0x18001318f  mov     [rbp+1B0h+var_D0], rax
0x180013196  mov     eax, [rsi+14h]
0x180013199  mov     [rsp+2B0h+var_25C], eax
0x18001319d  lea     rax, [rsp+2B0h+var_25C]
0x1800131a2  mov     [rbp+1B0h+var_C0], rax
0x1800131a9  mov     eax, [rsi+28h]
0x1800131ac  mov     [rsp+2B0h+var_258], eax
0x1800131b0  lea     rax, [rsp+2B0h+var_258]
0x1800131b5  mov     [rbp+1B0h+var_B0], rax
0x1800131bc  mov     eax, [rsi+18h]
0x1800131bf  mov     [rsp+2B0h+var_254], eax
0x1800131c3  lea     rax, [rsp+2B0h+var_254]
0x1800131c8  mov     [rbp+1B0h+var_A0], rax
0x1800131cf  movzx   eax, cs:word_18002AEAC
0x1800131d6  mov     dword ptr [rsp+2B0h+EventDescriptor.Level], eax
0x1800131da  mov     rax, cs:off_180031010
0x1800131e1  mov     [rbp+1B0h+var_1E0.Ptr], rax
0x1800131e5  mov     [rbp+1B0h+var_150], rcx
0x1800131e9  mov     [rbp+1B0h+var_144], r13d
0x1800131ed  mov     [rbp+1B0h+var_138], 4
0x1800131f5  mov     [rbp+1B0h+var_128], 4
0x180013200  mov     [rbp+1B0h+var_118], 4
0x18001320b  mov     [rbp+1B0h+var_108], 4
0x180013216  mov     [rbp+1B0h+var_F8], 4
0x180013221  mov     [rbp+1B0h+var_E8], 4
0x18001322c  mov     [rbp+1B0h+var_D8], 4
0x180013237  mov     [rbp+1B0h+var_C8], 4
0x180013242  mov     [rbp+1B0h+var_B8], 4
0x18001324d  mov     [rbp+1B0h+var_A8], 4
0x180013258  mov     [rbp+1B0h+var_98], 4
0x180013263  mov     dword ptr [rsp+2B0h+EventDescriptor.Id], 0B000000h
0x18001326b  mov     [rsp+2B0h+EventDescriptor.Keyword], r13
0x180013270  movzx   eax, word ptr [rax]
0x180013273  mov     [rbp+1B0h+var_1E0.Size], eax
0x180013276  lea     rax, word_18002AEB6
0x18001327d  mov     [rbp+1B0h+var_1D0], rax
0x180013281  mov     rax, r12
0x180013284  sub     eax, edx
0x180013286  mov     dword ptr [rbp+1B0h+var_1E0.0Ch], 2
0x18001328d  mov     [rbp+1B0h+var_1C8], 273h
0x180013294  lea     rdx, [rsp+2B0h+EventDescriptor]; EventDescriptor
0x180013299  mov     [rbp+1B0h+var_1C4], 1
0x1800132a0  mov     [rsp+2B0h+var_250], eax
0x1800132a4  mov     eax, [rsp+2B0h+var_250]
0x1800132a8  lea     rax, [rbp+1B0h+var_1E0]
0x1800132ac  mov     [rsp+2B0h+UserData], rax; UserData
0x1800132b1  mov     [rsp+2B0h+UserDataCount], 15h; UserDataCount
0x1800132b9  mov     rcx, cs:RegHandle; RegHandle
0x1800132c0  call    cs:__imp_EventWriteTransfer
0x1800132c6  mov     rdx, [rsi+160h]; evt
0x1800132cd  mov     rcx, r15; pci
0x1800132d0  call    cs:__imp_SetEventWhenCallbackReturns
0x1800132d6  cmp     [rsi], r13d
0x1800132d9  jz      loc_1800134C4
0x1800132df  mov     rdx, [rsi+0F8h]; Token
0x1800132e6  xor     ecx, ecx; Thread
0x1800132e8  call    cs:__imp_SetThreadToken
0x1800132ee  test    eax, eax
0x1800132f0  jnz     loc_1800134C4
0x1800132f6  mov     edx, 2
0x1800132fb  call    WppTraceIndent
0x180013300  mov     rbx, cs:WPP_GLOBAL_Control
0x180013307  lea     rax, WPP_GLOBAL_Control
0x18001330e  cmp     rbx, rax
0x180013311  jz      short loc_180013348
0x180013313  test    byte ptr [rbx+1Ch], 1
0x180013317  jz      short loc_180013348
0x180013319  cmp     byte ptr [rbx+19h], 3
0x18001331d  jb      short loc_180013348
0x18001331f  mov     rbx, [rbx+10h]
0x180013323  call    cs:__imp_GetLastError
0x180013329  mov     r9, cs:WPP_pszIndent
0x180013330  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x180013337  mov     edx, 0CCh
0x18001333c  mov     [rsp+2B0h+UserDataCount], eax
  ... truncated ...
```
