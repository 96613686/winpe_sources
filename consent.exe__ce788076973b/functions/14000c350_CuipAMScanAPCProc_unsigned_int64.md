# CuipAMScanAPCProc(unsigned __int64)

- ea: `0x14000c350`
- end: `0x14000cfa5`
- name: `?CuipAMScanAPCProc@@YAX_K@Z`
- size: `3157`
- prototype: `void __fastcall(HLOCAL *Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000a0c0`
- `0x14000c350`
- `0x14000fbec`
- `0x140010514`
- `0x140013928`
- `0x14001d5a0`
- `0x14001e050`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000c864`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000ce2e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000c864`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000ce2e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000c457`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000ca20`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000c457`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000ca20`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c762`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000cd2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000c762`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000cd2b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c7c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000cd8b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000c7c1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000cd8b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000cf6c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000cf6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c811`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cddb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000c811`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cddb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c81f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000cde9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000c81f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000cde9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000c983`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000cf52`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000c983`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000cf52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000cf76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000cf7f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000cf76`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000cf7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c804`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000cdce`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000c804`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000cdce`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c7f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000cdc1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000c7f7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000cdc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c7e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000cdaf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000c7e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000cdaf`
- `Amsi!AmsiUacScan` at `0x14000c3df`
- `Amsi!AmsiUacScan` at `0x14000c3df`

## pseudocode

```c
void __fastcall CuipAMScanAPCProc(HLOCAL *Parameter)
{
  __int64 v2; // rcx
  _DWORD *v3; // r9
  int v4; // ebx
  _QWORD *v5; // rcx
  _WORD *v6; // rdx
  _QWORD *v7; // r13
  __int64 v8; // rcx
  unsigned __int64 v9; // rax
  __int64 v10; // r10
  unsigned __int64 v11; // r15
  int v12; // r14d
  int v13; // esi
  int v14; // edi
  int v15; // ebx
  int v16; // r11d
  int v17; // r9d
  int v18; // r8d
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  PTP_TIMER *v36; // rbx
  __int64 v37; // rax
  __int64 *v38; // rcx
  struct _TP_TIMER *v39; // rcx
  HANDLE v40; // rax
  __int64 v41; // r10
  HLOCAL v42; // rax
  __int64 *v43; // rdx
  __int64 v44; // rax
  int v45; // eax
  _QWORD *v46; // r13
  __int64 v47; // rcx
  unsigned __int64 TlgAggregateSession; // rax
  __int64 v49; // r10
  unsigned __int64 v50; // r15
  int v51; // r14d
  int v52; // esi
  int v53; // edi
  int v54; // ebx
  int v55; // r11d
  int v56; // r9d
  int v57; // r8d
  unsigned int v58; // eax
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // eax
  unsigned int v63; // eax
  unsigned int v64; // eax
  unsigned int v65; // eax
  unsigned int v66; // eax
  unsigned int v67; // eax
  unsigned int v68; // eax
  unsigned int v69; // eax
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  unsigned int v74; // eax
  PTP_TIMER *v75; // rbx
  __int64 v76; // rax
  __int64 *v77; // rcx
  struct _TP_TIMER *v78; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v80; // r10
  HLOCAL v81; // rax
  __int64 *v82; // rdx
  __int64 v83; // rax
  int v84; // eax
  WINBOOL fPending; // [rsp+30h] [rbp-69h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-61h] BYREF
  WINBOOL v87; // [rsp+40h] [rbp-59h] BYREF
  LPVOID lpMem; // [rsp+48h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+50h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  int *v91; // [rsp+70h] [rbp-29h]
  int v92; // [rsp+78h] [rbp-21h]
  int v93; // [rsp+7Ch] [rbp-1Dh]
  void *p_Context; // [rsp+80h] [rbp-19h]
  __int64 v95; // [rsp+88h] [rbp-11h]
  __int64 *v96; // [rsp+90h] [rbp-9h]
  int v97; // [rsp+98h] [rbp-1h]
  int v98; // [rsp+9Ch] [rbp+3h]

  v87 = 0;
  v2 = *((_QWORD *)Parameter[2] + 4);
  v3 = Parameter[1];
  if ( v2 )
  {
    v4 = AmsiUacScan(v2, *Parameter, &v87, v3 + 2);
    LODWORD(Context) = v4;
    if ( v4 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_D(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          20,
          WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids,
          (unsigned int)v4);
      lpMem = 0;
      fPending = 0;
      if ( InitOnceBeginInitialize(&`LUATelemetry::Instance'::`2'::wrapper, 0, &fPending, &lpMem) && fPending )
      {
        lpMem = &qword_140029C98;
        qword_140029CA0 = 0;
        byte_140029CA8 = 0;
        dword_140029CAC = 0;
        qword_140029C98 = (__int64)&TraceLoggingAggregateProvider::`vftable';
        CallbackContext = &`LUATelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_8fd1dd6eff698f29c42c633fb94303b5_::_lambda_invoker_cdecl_);
        v46 = CallbackContext;
        qword_140029CB0 = (__int64)CallbackContext;
        byte_140029CB8 = 1;
        LOBYTE(v47) = 1;
        TlgAggregateSession = CreateTlgAggregateSession(v47);
        *(_QWORD *)&EventDescriptor.Id = TlgAggregateSession;
        if ( TlgAggregateSession )
        {
          *(_QWORD *)(TlgAggregateSession + 312) = 0;
          *(_QWORD *)(TlgAggregateSession + 320) = 0;
          *(_QWORD *)(TlgAggregateSession + 328) = v46;
          v49 = v46[1];
          v50 = TlgAggregateSession >> 4;
          v51 = (unsigned __int8)(TlgAggregateSession >> 52);
          v52 = (unsigned __int8)(TlgAggregateSession >> 44);
          v53 = (unsigned __int8)(TlgAggregateSession >> 36);
          v54 = (unsigned __int8)(TlgAggregateSession >> 28);
          v55 = (unsigned __int8)(TlgAggregateSession >> 20);
          v56 = (unsigned __int8)(TlgAggregateSession >> 12);
          v57 = (unsigned __int8)(TlgAggregateSession >> 4);
          v58 = 1025
              * (*(unsigned __int8 *)(v49 - 13)
               + ((1025
                 * (*(unsigned __int8 *)(v49 - 14)
                  + ((1025
                    * (*(unsigned __int8 *)(v49 - 15)
                     + ((1025 * *(unsigned __int8 *)(v49 - 16))
                      ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v49 - 16)) >> 6))))
                   ^ ((1025
                     * (*(unsigned __int8 *)(v49 - 15)
                      + ((1025 * *(unsigned __int8 *)(v49 - 16))
                       ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v49 - 16)) >> 6)))) >> 6))))
                ^ ((1025
                  * (*(unsigned __int8 *)(v49 - 14)
                   + ((1025
                     * (*(unsigned __int8 *)(v49 - 15)
                      + ((1025 * *(unsigned __int8 *)(v49 - 16))
                       ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v49 - 16)) >> 6))))
                    ^ ((1025
                      * (*(unsigned __int8 *)(v49 - 15)
                       + ((1025 * *(unsigned __int8 *)(v49 - 16))
                        ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v49 - 16)) >> 6)))) >> 6)))) >> 6)));
          v59 = 1025 * (*(unsigned __int8 *)(v49 - 12) + (v58 ^ (v58 >> 6)));
          v60 = 1025 * (*(unsigned __int8 *)(v49 - 11) + (v59 ^ (v59 >> 6)));
          v61 = 1025 * (*(unsigned __int8 *)(v49 - 10) + (v60 ^ (v60 >> 6)));
          v62 = 1025 * (*(unsigned __int8 *)(v49 - 9) + (v61 ^ (v61 >> 6)));
          v63 = 1025 * (*(unsigned __int8 *)(v49 - 8) + (v62 ^ (v62 >> 6)));
          v64 = 1025 * (*(unsigned __int8 *)(v49 - 7) + (v63 ^ (v63 >> 6)));
          v65 = 1025 * (*(unsigned __int8 *)(v49 - 6) + (v64 ^ (v64 >> 6)));
          v66 = 1025 * (*(unsigned __int8 *)(v49 - 5) + (v65 ^ (v65 >> 6)));
          v67 = 1025 * (*(unsigned __int8 *)(v49 - 4) + (v66 ^ (v66 >> 6)));
          v68 = 1025 * (*(unsigned __int8 *)(v49 - 3) + (v67 ^ (v67 >> 6)));
          v69 = 1025 * (*(unsigned __int8 *)(v49 - 2) + (v68 ^ (v68 >> 6)));
          v70 = 1025 * (*(unsigned __int8 *)(v49 - 1) + (v69 ^ (v69 >> 6)));
          v71 = 1025 * (v56 + ((1025 * (v57 + (v70 ^ (v70 >> 6)))) ^ ((1025 * (v57 + (v70 ^ (v70 >> 6)))) >> 6)));
          v72 = 1025 * (v54 + ((1025 * (v55 + (v71 ^ (v71 >> 6)))) ^ ((1025 * (v55 + (v71 ^ (v71 >> 6)))) >> 6)));
          v73 = 1025 * (v52 + ((1025 * (v53 + (v72 ^ (v72 >> 6)))) ^ ((1025 * (v53 + (v72 ^ (v72 >> 6)))) >> 6)));
          v74 = 1025
              * (HIBYTE(v50) + ((1025 * (v51 + (v73 ^ (v73 >> 6)))) ^ ((1025 * (v51 + (v73 ^ (v73 >> 6)))) >> 6)));
          v75 = *(PTP_TIMER **)&EventDescriptor.Id;
          *(_DWORD *)(*(_QWORD *)&EventDescriptor.Id + 352LL) = 32769
                                                              * ((9 * (v74 ^ (v74 >> 6)))
                                                               ^ ((9 * (v74 ^ (v74 >> 6))) >> 11))
                                                              % 0x927C0
                                                              + 600000;
          if ( (int)TraceLoggingRegisterEx_EventRegister_EventSetInformation(v46) < 0 )
          {
            v46[5] = 0;
            v78 = v75[43];
            if ( v78 )
            {
              SetThreadpoolTimer(v78, 0, 0, 0);
              WaitForThreadpoolTimerCallbacks(v75[43], 1);
              CloseThreadpoolTimer(v75[43]);
              v75[43] = 0;
            }
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v75);
          }
          else
          {
            AcquireSRWLockExclusive(&stru_140029C80);
            v76 = qword_140029C88;
            if ( qword_140029C88
              || (TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_140029078),
                  (v76 = qword_140029C88) != 0) )
            {
              while ( *(_QWORD **)(v76 + 328) != v46 )
              {
                v77 = (__int64 *)(v76 + 336);
                v76 = *(_QWORD *)(v76 + 336);
                if ( !v76 )
                  goto LABEL_60;
              }
            }
            else
            {
              v77 = &qword_140029C88;
LABEL_60:
              *v77 = (__int64)v75;
            }
            ReleaseSRWLockExclusive(&stru_140029C80);
          }
        }
        else
        {
          TraceLoggingRegisterEx_EventRegister_EventSetInformation(v46);
        }
        qword_140029CA0 = (__int64)v46;
        byte_140029CA8 = 0;
        dword_140029CAC = 1;
        (*(void (__fastcall **)(__int64 *))(qword_140029C98 + 8))(&qword_140029C98);
        InitOnceComplete(&`LUATelemetry::Instance'::`2'::wrapper, 0, &qword_140029C98);
        v4 = (int)Context;
      }
      v80 = *((_QWORD *)lpMem + 1);
      if ( *(_DWORD *)v80 > 5u
        && (*(_QWORD *)(v80 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v80 + 24) & 0x400000000000LL) == *(_QWORD *)(v80 + 24) )
      {
        v81 = Parameter[1];
        v82 = &qword_1400210F8;
        if ( *((_QWORD *)v81 + 1) )
          v82 = (__int64 *)*((_QWORD *)v81 + 1);
        LODWORD(Context) = v4;
        if ( v82 )
        {
          v83 = -1;
          do
            ++v83;
          while ( *((_WORD *)v82 + v83) );
          v84 = 2 * v83 + 2;
        }
        else
        {
          v82 = &qword_1400210F8;
          v84 = 2;
        }
        v96 = v82;
        v97 = v84;
        v98 = 0;
        p_Context = &Context;
        v95 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 5;
        EventDescriptor.Keyword = 0x400000000000LL;
        UserData.Ptr = *(_QWORD *)(v80 + 8);
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        UserData.Reserved = 2;
        v91 = &dword_140022F94;
        v92 = 55;
        v93 = 1;
        fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*(_QWORD *)(v80 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
      }
      *(_DWORD *)Parameter[1] = -1;
    }
    else
    {
      if ( v87 >= 0x8000 && (v5 = Parameter[1], (v6 = (_WORD *)v5[1]) != 0) && *v6 )
      {
        *(_DWORD *)v5 = 0;
      }
      else if ( v87 )
      {
        if ( v87 == 1 )
        {
          *(_DWORD *)Parameter[1] = 1;
        }
        else
        {
          Context = 0;
          fPending = 0;
          if ( InitOnceBeginInitialize(&`LUATelemetry::Instance'::`2'::wrapper, 0, &fPending, &Context) && fPending )
          {
            Context = &qword_140029C98;
            qword_140029CA0 = 0;
            byte_140029CA8 = 0;
            dword_140029CAC = 0;
            qword_140029C98 = (__int64)&TraceLoggingAggregateProvider::`vftable';
            CallbackContext = &`LUATelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
            atexit(_lambda_8fd1dd6eff698f29c42c633fb94303b5_::_lambda_invoker_cdecl_);
            v7 = CallbackContext;
            qword_140029CB0 = (__int64)CallbackContext;
            byte_140029CB8 = 1;
            LOBYTE(v8) = 1;
            v9 = CreateTlgAggregateSession(v8);
            lpMem = (LPVOID)v9;
            if ( v9 )
            {
              *(_QWORD *)(v9 + 312) = 0;
              *(_QWORD *)(v9 + 320) = 0;
              *(_QWORD *)(v9 + 328) = v7;
              v10 = v7[1];
              v11 = v9 >> 4;
              v12 = (unsigned __int8)(v9 >> 52);
              v13 = (unsigned __int8)(v9 >> 44);
              v14 = (unsigned __int8)(v9 >> 36);
              v15 = (unsigned __int8)(v9 >> 28);
              v16 = (unsigned __int8)(v9 >> 20);
              v17 = (unsigned __int8)(v9 >> 12);
              v18 = (unsigned __int8)(v9 >> 4);
              v19 = 1025
                  * (*(unsigned __int8 *)(v10 - 13)
                   + ((1025
                     * (*(unsigned __int8 *)(v10 - 14)
                      + ((1025
                        * (*(unsigned __int8 *)(v10 - 15)
                         + ((1025 * *(unsigned __int8 *)(v10 - 16))
                          ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v10 - 16)) >> 6))))
                       ^ ((1025
                         * (*(unsigned __int8 *)(v10 - 15)
                          + ((1025 * *(unsigned __int8 *)(v10 - 16))
                           ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v10 - 16)) >> 6)))) >> 6))))
                    ^ ((1025
                      * (*(unsigned __int8 *)(v10 - 14)
                       + ((1025
                         * (*(unsigned __int8 *)(v10 - 15)
                          + ((1025 * *(unsigned __int8 *)(v10 - 16))
                           ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v10 - 16)) >> 6))))
                        ^ ((1025
                          * (*(unsigned __int8 *)(v10 - 15)
                           + ((1025 * *(unsigned __int8 *)(v10 - 16))
                            ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v10 - 16)) >> 6)))) >> 6)))) >> 6)));
              v20 = 1025 * (*(unsigned __int8 *)(v10 - 12) + (v19 ^ (v19 >> 6)));
              v21 = 1025 * (*(unsigned __int8 *)(v10 - 11) + (v20 ^ (v20 >> 6)));
              v22 = 1025 * (*(unsigned __int8 *)(v10 - 10) + (v21 ^ (v21 >> 6)));
              v23 = 1025 * (*(unsigned __int8 *)(v10 - 9) + (v22 ^ (v22 >> 6)));
              v24 = 1025 * (*(unsigned __int8 *)(v10 - 8) + (v23 ^ (v23 >> 6)));
              v25 = 1025 * (*(unsigned __int8 *)(v10 - 7) + (v24 ^ (v24 >> 6)));
              v26 = 1025 * (*(unsigned __int8 *)(v10 - 6) + (v25 ^ (v25 >> 6)));
              v27 = 1025 * (*(unsigned __int8 *)(v10 - 5) + (v26 ^ (v26 >> 6)));
              v28 = 1025 * (*(unsigned __int8 *)(v10 - 4) + (v27 ^ (v27 >> 6)));
              v29 = 1025 * (*(unsigned __int8 *)(v10 - 3) + (v28 ^ (v28 >> 6)));
              v30 = 1025 * (*(unsigned __int8 *)(v10 - 2) + (v29 ^ (v29 >> 6)));
              v31 = 1025 * (*(unsigned __int8 *)(v10 - 1) + (v30 ^ (v30 >> 6)));
              v32 = 1025 * (v17 + ((1025 * (v18 + (v31 ^ (v31 >> 6)))) ^ ((1025 * (v18 + (v31 ^ (v31 >> 6)))) >> 6)));
              v33 = 1025 * (v15 + ((1025 * (v16 + (v32 ^ (v32 >> 6)))) ^ ((1025 * (v16 + (v32 ^ (v32 >> 6)))) >> 6)));
              v34 = 1025 * (v13 + ((1025 * (v14 + (v33 ^ (v33 >> 6)))) ^ ((1025 * (v14 + (v33 ^ (v33 >> 6)))) >> 6)));
              v35 = 1025
                  * (HIBYTE(v11) + ((1025 * (v12 + (v34 ^ (v34 >> 6)))) ^ ((1025 * (v12 + (v34 ^ (v34 >> 6)))) >> 6)));
              v36 = (PTP_TIMER *)lpMem;
              *((_DWORD *)lpMem + 88) = 32769 * ((9 * (v35 ^ (v35 >> 6))) ^ ((9 * (v35 ^ (v35 >> 6))) >> 11)) % 0x927C0
                                      + 600000;
              if ( (int)TraceLoggingRegisterEx_EventRegister_EventSetInformation(v7) < 0 )
              {
                v7[5] = 0;
                v39 = v36[43];
                if ( v39 )
                {
                  SetThreadpoolTimer(v39, 0, 0, 0);
                  WaitForThreadpoolTimerCallbacks(v36[43], 1);
                  CloseThreadpoolTimer(v36[43]);
                  v36[43] = 0;
                }
                v40 = GetProcessHeap();
                HeapFree(v40, 0, v36);
              }
              else
              {
                AcquireSRWLockExclusive(&stru_140029C80);
                v37 = qword_140029C88;
                if ( qword_140029C88
                  || (TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_140029078),
                      (v37 = qword_140029C88) != 0) )
                {
                  while ( *(_QWORD **)(v37 + 328) != v7 )
                  {
                    v38 = (__int64 *)(v37 + 336);
                    v37 = *(_QWORD *)(v37 + 336);
                    if ( !v37 )
                      goto LABEL_25;
                  }
                }
                else
                {
                  v38 = &qword_140029C88;
LABEL_25:
                  *v38 = (__int64)v36;
                }
                ReleaseSRWLockExclusive(&stru_140029C80);
              }
            }
            else
            {
              TraceLoggingRegisterEx_EventRegister_EventSetInformation(v7);
            }
            qword_140029CA0 = (__int64)v7;
            byte_140029CA8 = 0;
            dword_140029CAC = 1;
            (*(void (__fastcall **)(__int64 *))(qword_140029C98 + 8))(&qword_140029C98);
            InitOnceComplete(&`LUATelemetry::Instance'::`2'::wrapper, 0, &qword_140029C98);
          }
          v41 = *((_QWORD *)Context + 1);
          if ( *(_DWORD *)v41 > 5u
            && (*(_QWORD *)(v41 + 16) & 0x400000000000LL) != 0
            && (*(_QWORD *)(v41 + 24) & 0x400000000000LL) == *(_QWORD *)(v41 + 24) )
          {
            v42 = Parameter[1];
            v43 = &qword_1400210F8;
            if ( *((_QWORD *)v42 + 1) )
              v43 = (__int64 *)*((_QWORD *)v42 + 1);
            fPending = v87;
            if ( v43 )
            {
              v44 = -1;
              do
                ++v44;
              while ( *((_WORD *)v43 + v44) );
              v45 = 2 * v44 + 2;
            }
            else
            {
              v43 = &qword_1400210F8;
              v45 = 2;
            }
            v96 = v43;
            v97 = v45;
            v98 = 0;
            p_Context = &fPending;
            v95 = 4;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            *(_DWORD *)&EventDescriptor.Level = 5;
            EventDescriptor.Keyword = 0x400000000000LL;
            UserData.Ptr = *(_QWORD *)(v41 + 8);
            UserData.Size = *(unsigned __int16 *)UserData.Ptr;
            UserData.Reserved = 2;
            v91 = (int *)byte_140022E8D;
            v92 = 58;
            v93 = 1;
            LODWORD(Context) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(*(_QWORD *)(v41 + 32), &EventDescriptor, 0, 0, 4u, &UserData);
          }
          *(_DWORD *)Parameter[1] = -1;
        }
      }
      else
      {
        *(_DWORD *)Parameter[1] = 2;
      }
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_D(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          19,
          WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids,
          *(unsigned int *)Parameter[1]);
    }
  }
  else
  {
    *v3 = -1;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids);
  }
  SetEvent(*((HANDLE *)Parameter[2] + 3));
  LocalFree(*Parameter);
  LocalFree(Parameter);
}

```

## disassembly

```asm
0x14000c350  push    rbp
0x14000c352  push    rbx
0x14000c353  push    rsi
0x14000c354  push    rdi
0x14000c355  push    r12
0x14000c357  push    r13
0x14000c359  push    r14
0x14000c35b  push    r15
0x14000c35d  lea     rbp, [rsp-1Fh]
0x14000c362  sub     rsp, 0B8h
0x14000c369  mov     rax, cs:__security_cookie
0x14000c370  xor     rax, rsp
0x14000c373  mov     [rbp+57h+var_50], rax
0x14000c377  mov     r12, rcx
0x14000c37a  xor     edi, edi
0x14000c37c  mov     [rbp+57h+var_B0], edi
0x14000c37f  mov     rax, [rcx+10h]
0x14000c383  mov     rcx, [rax+20h]
0x14000c387  mov     r9, [r12+8]
0x14000c38c  test    rcx, rcx
0x14000c38f  jnz     short loc_14000C3D3
0x14000c391  mov     dword ptr [r9], 0FFFFFFFFh
0x14000c398  lea     rax, WPP_GLOBAL_Control
0x14000c39f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c3a6  cmp     rcx, rax
0x14000c3a9  jz      loc_14000CF63
0x14000c3af  test    byte ptr [rcx+1Ch], 2
0x14000c3b3  jz      loc_14000CF63
0x14000c3b9  mov     edx, 12h
0x14000c3be  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x14000c3c5  mov     rcx, [rcx+10h]
0x14000c3c9  call    WPP_SF_
0x14000c3ce  jmp     loc_14000CF63
0x14000c3d3  add     r9, 8
0x14000c3d7  lea     r8, [rbp+57h+var_B0]
0x14000c3db  mov     rdx, [r12]
0x14000c3df  call    cs:__imp_AmsiUacScan
0x14000c3e5  mov     ebx, eax
0x14000c3e7  mov     dword ptr [rbp+57h+Context], eax
0x14000c3ea  test    eax, eax
0x14000c3ec  js      loc_14000C9D7
0x14000c3f2  mov     eax, [rbp+57h+var_B0]
0x14000c3f5  cmp     eax, 8000h
0x14000c3fa  jl      short loc_14000C416
0x14000c3fc  mov     rcx, [r12+8]
0x14000c401  mov     rdx, [rcx+8]
0x14000c405  test    rdx, rdx
0x14000c408  jz      short loc_14000C416
0x14000c40a  cmp     [rdx], di
0x14000c40d  jz      short loc_14000C416
0x14000c40f  mov     [rcx], edi
0x14000c411  jmp     loc_14000C994
0x14000c416  test    eax, eax
0x14000c418  jnz     short loc_14000C42A
0x14000c41a  mov     rax, [r12+8]
0x14000c41f  mov     dword ptr [rax], 2
0x14000c425  jmp     loc_14000C994
0x14000c42a  cmp     eax, 1
0x14000c42d  jnz     short loc_14000C43F
0x14000c42f  mov     rax, [r12+8]
0x14000c434  mov     dword ptr [rax], 1
0x14000c43a  jmp     loc_14000C994
0x14000c43f  mov     [rbp+57h+Context], rdi
0x14000c443  mov     [rbp+57h+fPending], edi
0x14000c446  lea     r9, [rbp+57h+Context]; lpContext
0x14000c44a  lea     r8, [rbp+57h+fPending]; fPending
0x14000c44e  xor     edx, edx; dwFlags
0x14000c450  lea     rcx, ?wrapper@?1??Instance@LUATelemetry@@KAPEAV2@XZ@4V?$static_lazy@VLUATelemetry@@@details@wil@@A; lpInitOnce
0x14000c457  call    cs:__imp_InitOnceBeginInitialize
0x14000c45d  test    eax, eax
0x14000c45f  jz      loc_14000C86A
0x14000c465  cmp     [rbp+57h+fPending], edi
0x14000c468  jz      loc_14000C86A
0x14000c46e  lea     rax, qword_140029C98
0x14000c475  mov     [rbp+57h+Context], rax
0x14000c479  mov     cs:qword_140029CA0, rdi
0x14000c480  mov     cs:byte_140029CA8, dil
0x14000c487  mov     cs:dword_140029CAC, edi
0x14000c48d  lea     rax, ??_7TraceLoggingAggregateProvider@@6B@; const TraceLoggingAggregateProvider::`vftable'
0x14000c494  mov     cs:qword_140029C98, rax
0x14000c49b  lea     rax, ?__hInner@?1???0StaticHandle@LUATelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `LUATelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000c4a2  mov     cs:CallbackContext, rax
0x14000c4a9  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8fd1dd6eff698f29c42c633fb94303b5_@@CA@XZ; void (__cdecl *)()
0x14000c4b0  call    atexit
0x14000c4b5  mov     r13, cs:CallbackContext
0x14000c4bc  mov     cs:qword_140029CB0, r13
0x14000c4c3  mov     cs:byte_140029CB8, 1
0x14000c4ca  mov     cl, 1
0x14000c4cc  call    CreateTlgAggregateSession
0x14000c4d1  mov     [rbp+57h+lpMem], rax
0x14000c4d5  test    rax, rax
0x14000c4d8  jnz     short loc_14000C4EC
0x14000c4da  xor     r8d, r8d
0x14000c4dd  xor     edx, edx
0x14000c4df  mov     rcx, r13; CallbackContext
0x14000c4e2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000c4e7  jmp     loc_14000C825
0x14000c4ec  mov     [rax+138h], rdi
0x14000c4f3  mov     [rax+140h], rdi
0x14000c4fa  mov     [rax+148h], r13
0x14000c501  mov     r10, [r13+8]
0x14000c505  mov     r15, rax
0x14000c508  shr     r15, 4
0x14000c50c  mov     rax, r15
0x14000c50f  shr     rax, 30h
0x14000c513  movzx   r14d, al
0x14000c517  mov     rax, r15
0x14000c51a  shr     rax, 28h
0x14000c51e  movzx   esi, al
0x14000c521  mov     rax, r15
0x14000c524  shr     rax, 20h
0x14000c528  movzx   edi, al
0x14000c52b  mov     rax, r15
0x14000c52e  shr     rax, 18h
0x14000c532  movzx   ebx, al
0x14000c535  mov     rax, r15
0x14000c538  shr     rax, 10h
0x14000c53c  movzx   r11d, al
0x14000c540  mov     rax, r15
0x14000c543  shr     rax, 8
0x14000c547  movzx   r9d, al
0x14000c54b  movzx   r8d, r15b
0x14000c54f  movzx   eax, byte ptr [r10-10h]
0x14000c554  imul    ecx, eax, 401h
0x14000c55a  mov     edx, ecx
0x14000c55c  shr     edx, 6
0x14000c55f  xor     edx, ecx
0x14000c561  movzx   eax, byte ptr [r10-0Fh]
0x14000c566  add     edx, eax
0x14000c568  imul    eax, edx, 401h
0x14000c56e  mov     ecx, eax
0x14000c570  shr     ecx, 6
0x14000c573  xor     ecx, eax
0x14000c575  movzx   eax, byte ptr [r10-0Eh]
0x14000c57a  add     ecx, eax
0x14000c57c  imul    eax, ecx, 401h
0x14000c582  mov     ecx, eax
0x14000c584  shr     ecx, 6
0x14000c587  xor     ecx, eax
0x14000c589  movzx   eax, byte ptr [r10-0Dh]
0x14000c58e  add     ecx, eax
0x14000c590  imul    eax, ecx, 401h
0x14000c596  mov     ecx, eax
0x14000c598  shr     ecx, 6
0x14000c59b  xor     ecx, eax
0x14000c59d  movzx   eax, byte ptr [r10-0Ch]
0x14000c5a2  add     ecx, eax
0x14000c5a4  imul    eax, ecx, 401h
0x14000c5aa  mov     ecx, eax
0x14000c5ac  shr     ecx, 6
0x14000c5af  xor     ecx, eax
0x14000c5b1  movzx   eax, byte ptr [r10-0Bh]
0x14000c5b6  add     ecx, eax
0x14000c5b8  imul    eax, ecx, 401h
0x14000c5be  mov     ecx, eax
0x14000c5c0  shr     ecx, 6
0x14000c5c3  xor     ecx, eax
0x14000c5c5  movzx   eax, byte ptr [r10-0Ah]
0x14000c5ca  add     ecx, eax
0x14000c5cc  imul    eax, ecx, 401h
0x14000c5d2  mov     ecx, eax
0x14000c5d4  shr     ecx, 6
0x14000c5d7  xor     ecx, eax
0x14000c5d9  movzx   eax, byte ptr [r10-9]
0x14000c5de  add     ecx, eax
0x14000c5e0  imul    eax, ecx, 401h
0x14000c5e6  mov     ecx, eax
0x14000c5e8  shr     ecx, 6
0x14000c5eb  xor     ecx, eax
0x14000c5ed  movzx   eax, byte ptr [r10-8]
0x14000c5f2  add     ecx, eax
0x14000c5f4  imul    eax, ecx, 401h
0x14000c5fa  mov     ecx, eax
0x14000c5fc  shr     ecx, 6
0x14000c5ff  xor     ecx, eax
0x14000c601  movzx   eax, byte ptr [r10-7]
0x14000c606  add     ecx, eax
0x14000c608  imul    eax, ecx, 401h
0x14000c60e  mov     ecx, eax
0x14000c610  shr     ecx, 6
0x14000c613  xor     ecx, eax
0x14000c615  movzx   eax, byte ptr [r10-6]
0x14000c61a  add     ecx, eax
0x14000c61c  imul    eax, ecx, 401h
0x14000c622  mov     ecx, eax
0x14000c624  shr     ecx, 6
0x14000c627  xor     ecx, eax
0x14000c629  movzx   eax, byte ptr [r10-5]
0x14000c62e  add     ecx, eax
0x14000c630  imul    eax, ecx, 401h
0x14000c636  mov     ecx, eax
0x14000c638  shr     ecx, 6
0x14000c63b  xor     ecx, eax
0x14000c63d  movzx   eax, byte ptr [r10-4]
0x14000c642  add     ecx, eax
0x14000c644  imul    eax, ecx, 401h
0x14000c64a  mov     ecx, eax
0x14000c64c  shr     ecx, 6
0x14000c64f  xor     ecx, eax
0x14000c651  movzx   eax, byte ptr [r10-3]
0x14000c656  add     ecx, eax
0x14000c658  imul    eax, ecx, 401h
0x14000c65e  mov     ecx, eax
0x14000c660  shr     ecx, 6
0x14000c663  xor     ecx, eax
0x14000c665  movzx   eax, byte ptr [r10-2]
0x14000c66a  add     ecx, eax
0x14000c66c  imul    eax, ecx, 401h
0x14000c672  mov     ecx, eax
0x14000c674  shr     ecx, 6
0x14000c677  xor     ecx, eax
0x14000c679  movzx   eax, byte ptr [r10-1]
0x14000c67e  add     ecx, eax
0x14000c680  imul    eax, ecx, 401h
0x14000c686  mov     ecx, eax
0x14000c688  shr     ecx, 6
0x14000c68b  xor     ecx, eax
0x14000c68d  add     ecx, r8d
0x14000c690  imul    eax, ecx, 401h
0x14000c696  mov     ecx, eax
0x14000c698  shr     ecx, 6
0x14000c69b  xor     ecx, eax
0x14000c69d  add     ecx, r9d
0x14000c6a0  imul    eax, ecx, 401h
0x14000c6a6  mov     ecx, eax
0x14000c6a8  shr     ecx, 6
0x14000c6ab  xor     ecx, eax
0x14000c6ad  add     ecx, r11d
0x14000c6b0  imul    eax, ecx, 401h
0x14000c6b6  mov     ecx, eax
0x14000c6b8  shr     ecx, 6
0x14000c6bb  xor     ecx, eax
0x14000c6bd  add     ecx, ebx
0x14000c6bf  imul    eax, ecx, 401h
0x14000c6c5  mov     ecx, eax
0x14000c6c7  shr     ecx, 6
0x14000c6ca  xor     ecx, eax
0x14000c6cc  add     ecx, edi
0x14000c6ce  imul    eax, ecx, 401h
0x14000c6d4  mov     ecx, eax
0x14000c6d6  shr     ecx, 6
0x14000c6d9  xor     ecx, eax
0x14000c6db  add     ecx, esi
0x14000c6dd  imul    eax, ecx, 401h
0x14000c6e3  mov     ecx, eax
0x14000c6e5  shr     ecx, 6
0x14000c6e8  xor     ecx, eax
0x14000c6ea  add     ecx, r14d
0x14000c6ed  imul    eax, ecx, 401h
0x14000c6f3  mov     ecx, eax
0x14000c6f5  shr     ecx, 6
0x14000c6f8  xor     ecx, eax
0x14000c6fa  shr     r15, 38h
0x14000c6fe  add     ecx, r15d
0x14000c701  imul    eax, ecx, 401h
0x14000c707  mov     ecx, eax
0x14000c709  shr     ecx, 6
0x14000c70c  xor     ecx, eax
0x14000c70e  lea     eax, [rcx+rcx*8]
0x14000c711  mov     ecx, eax
0x14000c713  shr     ecx, 0Bh
0x14000c716  xor     ecx, eax
0x14000c718  imul    r8d, ecx, 8001h
0x14000c71f  mov     eax, 6FD91D85h
0x14000c724  mul     r8d
0x14000c727  shr     edx, 12h
0x14000c72a  imul    eax, edx, 927C0h
0x14000c730  sub     r8d, eax
0x14000c733  add     r8d, 927C0h
0x14000c73a  mov     rbx, [rbp+57h+lpMem]
0x14000c73e  mov     [rbx+160h], r8d
0x14000c745  mov     r8, rbx
0x14000c748  lea     rdx, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x14000c74f  mov     rcx, r13; CallbackContext
0x14000c752  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000c757  test    eax, eax
0x14000c759  js      short loc_14000C7CB
0x14000c75b  lea     rcx, stru_140029C80; SRWLock
0x14000c762  call    cs:__imp_AcquireSRWLockExclusive
0x14000c768  mov     rax, cs:qword_140029C88
0x14000c76f  test    rax, rax
0x14000c772  jnz     short loc_14000C796
0x14000c774  xor     r8d, r8d
0x14000c777  lea     rdx, ?TlgAggregateInternalProviderCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalProviderCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x14000c77e  lea     rcx, dword_140029078; CallbackContext
0x14000c785  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000c78a  mov     rax, cs:qword_140029C88
0x14000c791  test    rax, rax
0x14000c794  jz      short loc_14000C7B0
0x14000c796  cmp     [rax+148h], r13
0x14000c79d  jz      short loc_14000C7BA
0x14000c79f  lea     rcx, [rax+150h]
0x14000c7a6  mov     rax, [rcx]
0x14000c7a9  test    rax, rax
0x14000c7ac  jnz     short loc_14000C796
0x14000c7ae  jmp     short loc_14000C7B7
0x14000c7b0  lea     rcx, qword_140029C88
0x14000c7b7  mov     [rcx], rbx
0x14000c7ba  lea     rcx, stru_140029C80; SRWLock
0x14000c7c1  call    cs:__imp_ReleaseSRWLockExclusive
  ... truncated ...
```
