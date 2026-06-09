# CuiPerformAMScan(HAMSCANCONTEXT__ *,_CONSENTUI_PARAM_HEADER *,_CREDUI_CONTEXT *,int,_AM_SCAN_RESULT *,ushort * *)

- ea: `0x14000af70`
- end: `0x14000b80d`
- name: `?CuiPerformAMScan@@YAKPEAUHAMSCANCONTEXT__@@PEAU_CONSENTUI_PARAM_HEADER@@PEAU_CREDUI_CONTEXT@@HPEAW4_AM_SCAN_RESULT@@PEAPEAG@Z`
- size: `2205`
- prototype: `__int64 __fastcall(struct HAMSCANCONTEXT__ *, struct _CONSENTUI_PARAM_HEADER *, struct _CREDUI_CONTEXT *, WINBOOL, enum _AM_SCAN_RESULT *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001a080`

## callees

- `0x140005a80`
- `0x14000a0c0`
- `0x14000af70`
- `0x14000fbec`
- `0x140010514`
- `0x140013928`
- `0x14001d5a0`
- `0x14001e050`
- `0x14001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000b604`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000b604`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000b1dd`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000b1dd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b4f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14000b4f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b551`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000b551`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000b155`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000b155`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b5a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000b5a5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b5b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000b5b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b70b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b113`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b70b`
- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x14000b6e5`
- `api-ms-win-core-com-l1-1-0!CoCancelCall` at `0x14000b6e5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000b6da`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x14000b6da`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b7c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b7d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b7de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b7c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b7d5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000b7de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000aff3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b04e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b094`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b753`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000aff3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b04e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b094`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000b753`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x14000b109`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x14000b780`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x14000b109`
- `api-ms-win-core-processthreads-l1-1-0!QueueUserAPC` at `0x14000b780`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b594`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b594`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b587`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b587`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b575`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b575`

## pseudocode

```c
__int64 __fastcall CuiPerformAMScan(
        struct HAMSCANCONTEXT__ *a1,
        struct _CONSENTUI_PARAM_HEADER *a2,
        struct _CREDUI_CONTEXT *a3,
        WINBOOL a4,
        enum _AM_SCAN_RESULT *a5,
        unsigned __int16 **a6)
{
  struct HAMSCANCONTEXT__ *v7; // rdi
  int v9; // r13d
  struct AMSI_UAC_REQUEST_CONTEXT **v10; // r12
  unsigned int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  struct AMSI_UAC_REQUEST_CONTEXT *v15; // rax
  _QWORD *v16; // rax
  _QWORD *v17; // rbx
  DWORD LastError; // eax
  DWORD v19; // eax
  _QWORD *v20; // r13
  __int64 v21; // rcx
  unsigned __int64 TlgAggregateSession; // rax
  __int64 v23; // r10
  unsigned __int64 v24; // r15
  int v25; // r14d
  int v26; // esi
  int v27; // edi
  int v28; // ebx
  int v29; // r11d
  int v30; // r9d
  int v31; // r8d
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  unsigned int v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  unsigned int v44; // eax
  unsigned int v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // eax
  PTP_TIMER *v49; // rbx
  __int64 v50; // rax
  __int64 *v51; // rcx
  struct _TP_TIMER *v52; // rcx
  HANDLE ProcessHeap; // rax
  __int64 v54; // rcx
  DWORD v55; // eax
  _QWORD *v56; // rax
  HLOCAL v57; // rcx
  struct AMSI_UAC_REQUEST_CONTEXT *v58; // rcx
  WINBOOL fPending; // [rsp+30h] [rbp-59h] BYREF
  int v60; // [rsp+34h] [rbp-55h] BYREF
  LPVOID Context; // [rsp+38h] [rbp-51h] BYREF
  EVENT_DESCRIPTOR hHandle; // [rsp+40h] [rbp-49h] BYREF
  struct HAMSCANCONTEXT__ *v63; // [rsp+50h] [rbp-39h]
  HLOCAL v64; // [rsp+58h] [rbp-31h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-29h] BYREF
  char *v66; // [rsp+70h] [rbp-19h]
  int v67; // [rsp+78h] [rbp-11h]
  int v68; // [rsp+7Ch] [rbp-Dh]
  int *v69; // [rsp+80h] [rbp-9h]
  __int64 v70; // [rsp+88h] [rbp-1h]

  fPending = a4;
  Context = a3;
  v7 = a1;
  v63 = a1;
  if ( !a1 )
    return 87;
  v64 = 0;
  v9 = 0;
  v60 = 0;
  *(_DWORD *)a5 = -1;
  *a6 = 0;
  if ( ((*((_DWORD *)a2 + 1) - 4) & 0xFFFFFFFD) == 0 )
  {
    v10 = 0;
    *(_DWORD *)a5 = 2;
    goto LABEL_58;
  }
  v10 = (struct AMSI_UAC_REQUEST_CONTEXT **)LocalAlloc(0x40u, 0x18u);
  if ( !v10 )
  {
    v11 = 14;
    v12 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      goto LABEL_59;
    v13 = 24;
    goto LABEL_8;
  }
  v15 = (struct AMSI_UAC_REQUEST_CONTEXT *)LocalAlloc(0x40u, 0x68u);
  *v10 = v15;
  if ( !v15 )
  {
    v11 = 14;
    v12 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
      goto LABEL_59;
    v13 = 25;
    goto LABEL_8;
  }
  v16 = LocalAlloc(0x40u, 0x10u);
  v17 = v16;
  v10[1] = (struct AMSI_UAC_REQUEST_CONTEXT *)v16;
  if ( v16 )
  {
    v64 = v16;
    *(_QWORD *)&hHandle.Id = *((_QWORD *)v7 + 3);
    v10[2] = (struct AMSI_UAC_REQUEST_CONTEXT *)v7;
    CuipPrepareAMSIScanContext(a2, (struct _CREDUI_CONTEXT *)Context, fPending, *v10);
    if ( !QueueUserAPC(CuipAMScanAPCProc, *(HANDLE *)v7, (ULONG_PTR)v10) )
    {
      LastError = GetLastError();
      v11 = LastError;
      v12 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
        goto LABEL_59;
      v13 = 27;
      v14 = LastError;
      goto LABEL_9;
    }
    v10 = 0;
    v19 = WaitForSingleObject(*(HANDLE *)&hHandle.Id, 0x3E8u);
    if ( v19 )
    {
      if ( v19 == 258 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids);
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
          v20 = CallbackContext;
          qword_140029CB0 = (__int64)CallbackContext;
          byte_140029CB8 = 1;
          LOBYTE(v21) = 1;
          TlgAggregateSession = CreateTlgAggregateSession(v21);
          *(_QWORD *)&hHandle.Id = TlgAggregateSession;
          if ( TlgAggregateSession )
          {
            *(_QWORD *)(TlgAggregateSession + 312) = 0;
            *(_QWORD *)(TlgAggregateSession + 320) = 0;
            *(_QWORD *)(TlgAggregateSession + 328) = v20;
            v23 = v20[1];
            v24 = TlgAggregateSession >> 4;
            v25 = (unsigned __int8)(TlgAggregateSession >> 52);
            v26 = (unsigned __int8)(TlgAggregateSession >> 44);
            v27 = (unsigned __int8)(TlgAggregateSession >> 36);
            v28 = (unsigned __int8)(TlgAggregateSession >> 28);
            v29 = (unsigned __int8)(TlgAggregateSession >> 20);
            v30 = (unsigned __int8)(TlgAggregateSession >> 12);
            v31 = (unsigned __int8)(TlgAggregateSession >> 4);
            v32 = 1025
                * (*(unsigned __int8 *)(v23 - 13)
                 + ((1025
                   * (*(unsigned __int8 *)(v23 - 14)
                    + ((1025
                      * (*(unsigned __int8 *)(v23 - 15)
                       + ((1025 * *(unsigned __int8 *)(v23 - 16))
                        ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v23 - 16)) >> 6))))
                     ^ ((1025
                       * (*(unsigned __int8 *)(v23 - 15)
                        + ((1025 * *(unsigned __int8 *)(v23 - 16))
                         ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v23 - 16)) >> 6)))) >> 6))))
                  ^ ((1025
                    * (*(unsigned __int8 *)(v23 - 14)
                     + ((1025
                       * (*(unsigned __int8 *)(v23 - 15)
                        + ((1025 * *(unsigned __int8 *)(v23 - 16))
                         ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v23 - 16)) >> 6))))
                      ^ ((1025
                        * (*(unsigned __int8 *)(v23 - 15)
                         + ((1025 * *(unsigned __int8 *)(v23 - 16))
                          ^ ((1025 * (unsigned int)*(unsigned __int8 *)(v23 - 16)) >> 6)))) >> 6)))) >> 6)));
            v33 = 1025 * (*(unsigned __int8 *)(v23 - 12) + (v32 ^ (v32 >> 6)));
            v34 = 1025 * (*(unsigned __int8 *)(v23 - 11) + (v33 ^ (v33 >> 6)));
            v35 = 1025 * (*(unsigned __int8 *)(v23 - 10) + (v34 ^ (v34 >> 6)));
            v36 = 1025 * (*(unsigned __int8 *)(v23 - 9) + (v35 ^ (v35 >> 6)));
            v37 = 1025 * (*(unsigned __int8 *)(v23 - 8) + (v36 ^ (v36 >> 6)));
            v38 = 1025 * (*(unsigned __int8 *)(v23 - 7) + (v37 ^ (v37 >> 6)));
            v39 = 1025 * (*(unsigned __int8 *)(v23 - 6) + (v38 ^ (v38 >> 6)));
            v40 = 1025 * (*(unsigned __int8 *)(v23 - 5) + (v39 ^ (v39 >> 6)));
            v41 = 1025 * (*(unsigned __int8 *)(v23 - 4) + (v40 ^ (v40 >> 6)));
            v42 = 1025 * (*(unsigned __int8 *)(v23 - 3) + (v41 ^ (v41 >> 6)));
            v43 = 1025 * (*(unsigned __int8 *)(v23 - 2) + (v42 ^ (v42 >> 6)));
            v44 = 1025 * (*(unsigned __int8 *)(v23 - 1) + (v43 ^ (v43 >> 6)));
            v45 = 1025 * (v30 + ((1025 * (v31 + (v44 ^ (v44 >> 6)))) ^ ((1025 * (v31 + (v44 ^ (v44 >> 6)))) >> 6)));
            v46 = 1025 * (v28 + ((1025 * (v29 + (v45 ^ (v45 >> 6)))) ^ ((1025 * (v29 + (v45 ^ (v45 >> 6)))) >> 6)));
            v47 = 1025 * (v26 + ((1025 * (v27 + (v46 ^ (v46 >> 6)))) ^ ((1025 * (v27 + (v46 ^ (v46 >> 6)))) >> 6)));
            v48 = 1025
                * (HIBYTE(v24) + ((1025 * (v25 + (v47 ^ (v47 >> 6)))) ^ ((1025 * (v25 + (v47 ^ (v47 >> 6)))) >> 6)));
            v49 = *(PTP_TIMER **)&hHandle.Id;
            *(_DWORD *)(*(_QWORD *)&hHandle.Id + 352LL) = 32769
                                                        * ((9 * (v48 ^ (v48 >> 6))) ^ ((9 * (v48 ^ (v48 >> 6))) >> 11))
                                                        % 0x927C0
                                                        + 600000;
            if ( (int)TraceLoggingRegisterEx_EventRegister_EventSetInformation(v20) < 0 )
            {
              v20[5] = 0;
              v52 = v49[43];
              if ( v52 )
              {
                SetThreadpoolTimer(v52, 0, 0, 0);
                WaitForThreadpoolTimerCallbacks(v49[43], 1);
                CloseThreadpoolTimer(v49[43]);
                v49[43] = 0;
              }
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v49);
            }
            else
            {
              AcquireSRWLockExclusive(&stru_140029C80);
              v50 = qword_140029C88;
              if ( qword_140029C88
                || (TraceLoggingRegisterEx_EventRegister_EventSetInformation(&dword_140029078),
                    (v50 = qword_140029C88) != 0) )
              {
                while ( *(_QWORD **)(v50 + 328) != v20 )
                {
                  v51 = (__int64 *)(v50 + 336);
                  v50 = *(_QWORD *)(v50 + 336);
                  if ( !v50 )
                    goto LABEL_41;
                }
              }
              else
              {
                v51 = &qword_140029C88;
LABEL_41:
                *v51 = (__int64)v49;
              }
              ReleaseSRWLockExclusive(&stru_140029C80);
            }
            v7 = v63;
          }
          else
          {
            TraceLoggingRegisterEx_EventRegister_EventSetInformation(v20);
          }
          qword_140029CA0 = (__int64)v20;
          byte_140029CA8 = 0;
          dword_140029CAC = 1;
          (*(void (__fastcall **)(__int64 *))(qword_140029C98 + 8))(&qword_140029C98);
          InitOnceComplete(&`LUATelemetry::Instance'::`2'::wrapper, 0, &qword_140029C98);
          v9 = v60;
        }
        v54 = *((_QWORD *)Context + 1);
        if ( *(_DWORD *)v54 > 5u
          && (*(_QWORD *)(v54 + 16) & 0x400000000000LL) != 0
          && (*(_QWORD *)(v54 + 24) & 0x400000000000LL) == *(_QWORD *)(v54 + 24) )
        {
          v60 = 1000;
          v69 = &v60;
          v70 = 4;
          *(_QWORD *)&hHandle.Id = 0x50B000000LL;
          hHandle.Keyword = 0x400000000000LL;
          UserData.Ptr = *(_QWORD *)(v54 + 8);
          UserData.Size = *(unsigned __int16 *)UserData.Ptr;
          UserData.Reserved = 2;
          v66 = byte_140022ED3;
          v67 = 35;
          v68 = 1;
          fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(*(_QWORD *)(v54 + 32), &hHandle, 0, 0, 3u, &UserData);
        }
        CoCancelCall(*((_DWORD *)v7 + 2), 0);
        v11 = 1460;
      }
      else
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          v55 = GetLastError();
          WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids, v55);
        }
        v11 = 5023;
      }
      goto LABEL_59;
    }
    *(_DWORD *)a5 = *(_DWORD *)v17;
    if ( *(_DWORD *)v17 == -1 )
    {
      v11 = 1627;
      goto LABEL_59;
    }
    *a6 = (unsigned __int16 *)v17[1];
    v9 = 1;
LABEL_58:
    v11 = 0;
    goto LABEL_59;
  }
  v11 = 14;
  v12 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) == 0 )
    goto LABEL_59;
  v13 = 26;
LABEL_8:
  v14 = 14;
LABEL_9:
  WPP_SF_D(*(_QWORD *)(v12 + 16), v13, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids, v14);
LABEL_59:
  v56 = LocalAlloc(0x40u, 0x18u);
  if ( v56 )
  {
    v56[1] = v7;
    v57 = 0;
    if ( !v10 )
      v57 = v64;
    *v56 = v57;
    *((_DWORD *)v56 + 4) = v9;
    QueueUserAPC(CuipAMUninitializeAPCProc, *(HANDLE *)v7, (ULONG_PTR)v56);
  }
  else
  {
    v11 = 14;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 30, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids, 14);
  }
  if ( v10 )
  {
    if ( *v10 )
      LocalFree(*v10);
    v58 = v10[1];
    if ( v58 )
      LocalFree(v58);
    LocalFree(v10);
  }
  return v11;
}

```

## disassembly

```asm
0x14000af70  mov     [rsp-8+arg_18], rbx
0x14000af75  push    rbp
0x14000af76  push    rsi
0x14000af77  push    rdi
0x14000af78  push    r12
0x14000af7a  push    r13
0x14000af7c  push    r14
0x14000af7e  push    r15
0x14000af80  lea     rbp, [rsp-17h]
0x14000af85  sub     rsp, 0A0h
0x14000af8c  mov     rax, cs:__security_cookie
0x14000af93  xor     rax, rsp
0x14000af96  mov     [rbp+47h+var_40], rax
0x14000af9a  mov     [rbp+47h+fPending], r9d
0x14000af9e  mov     [rbp+47h+Context], r8
0x14000afa2  mov     r15, rdx
0x14000afa5  mov     rdi, rcx
0x14000afa8  mov     [rbp+47h+var_80], rcx
0x14000afac  mov     rsi, [rbp+47h+arg_20]
0x14000afb0  mov     r14, [rbp+47h+arg_28]
0x14000afb4  test    rcx, rcx
0x14000afb7  jnz     short loc_14000AFC3
0x14000afb9  mov     eax, 57h ; 'W'
0x14000afbe  jmp     loc_14000B7E6
0x14000afc3  xor     eax, eax
0x14000afc5  mov     [rbp+47h+var_78], rax
0x14000afc9  mov     r13d, eax
0x14000afcc  mov     [rbp+47h+var_9C], eax
0x14000afcf  mov     dword ptr [rsi], 0FFFFFFFFh
0x14000afd5  mov     [r14], rax
0x14000afd8  mov     eax, [rdx+4]
0x14000afdb  sub     eax, 4
0x14000afde  test    eax, 0FFFFFFFDh
0x14000afe3  jz      loc_14000B737
0x14000afe9  mov     edx, 18h; uBytes
0x14000afee  mov     ecx, 40h ; '@'; uFlags
0x14000aff3  call    cs:__imp_LocalAlloc
0x14000aff9  mov     r12, rax
0x14000affc  test    rax, rax
0x14000afff  jnz     short loc_14000B044
0x14000b001  mov     ebx, 0Eh
0x14000b006  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b00d  lea     rsi, WPP_GLOBAL_Control
0x14000b014  cmp     rcx, rsi
0x14000b017  jz      loc_14000B749
0x14000b01d  test    byte ptr [rcx+1Ch], 2
0x14000b021  jz      loc_14000B749
0x14000b027  mov     edx, 18h
0x14000b02c  mov     r9d, ebx
0x14000b02f  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x14000b036  mov     rcx, [rcx+10h]
0x14000b03a  call    WPP_SF_D
0x14000b03f  jmp     loc_14000B749
0x14000b044  mov     edx, 68h ; 'h'; uBytes
0x14000b049  mov     ecx, 40h ; '@'; uFlags
0x14000b04e  call    cs:__imp_LocalAlloc
0x14000b054  mov     [r12], rax
0x14000b058  test    rax, rax
0x14000b05b  jnz     short loc_14000B08A
0x14000b05d  mov     ebx, 0Eh
0x14000b062  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b069  lea     rsi, WPP_GLOBAL_Control
0x14000b070  cmp     rcx, rsi
0x14000b073  jz      loc_14000B749
0x14000b079  test    byte ptr [rcx+1Ch], 2
0x14000b07d  jz      loc_14000B749
0x14000b083  mov     edx, 19h
0x14000b088  jmp     short loc_14000B02C
0x14000b08a  mov     edx, 10h; uBytes
0x14000b08f  mov     ecx, 40h ; '@'; uFlags
0x14000b094  call    cs:__imp_LocalAlloc
0x14000b09a  mov     rbx, rax
0x14000b09d  mov     [r12+8], rax
0x14000b0a2  test    rax, rax
0x14000b0a5  jnz     short loc_14000B0D7
0x14000b0a7  mov     ebx, 0Eh
0x14000b0ac  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b0b3  lea     rsi, WPP_GLOBAL_Control
0x14000b0ba  cmp     rcx, rsi
0x14000b0bd  jz      loc_14000B749
0x14000b0c3  test    byte ptr [rcx+1Ch], 2
0x14000b0c7  jz      loc_14000B749
0x14000b0cd  mov     edx, 1Ah
0x14000b0d2  jmp     loc_14000B02C
0x14000b0d7  mov     [rbp+47h+var_78], rbx
0x14000b0db  mov     rax, [rdi+18h]
0x14000b0df  mov     [rbp+47h+hHandle], rax
0x14000b0e3  mov     [r12+10h], rdi
0x14000b0e8  mov     r9, [r12]; struct AMSI_UAC_REQUEST_CONTEXT *
0x14000b0ec  mov     r8d, [rbp+47h+fPending]; int
0x14000b0f0  mov     rdx, [rbp+47h+Context]; struct _CREDUI_CONTEXT *
0x14000b0f4  mov     rcx, r15; struct _CONSENTUI_PARAM_HEADER *
0x14000b0f7  call    ?CuipPrepareAMSIScanContext@@YAXPEAU_CONSENTUI_PARAM_HEADER@@PEAU_CREDUI_CONTEXT@@HPEAUAMSI_UAC_REQUEST_CONTEXT@@@Z; CuipPrepareAMSIScanContext(_CONSENTUI_PARAM_HEADER *,_CREDUI_CONTEXT *,int,AMSI_UAC_REQUEST_CONTEXT *)
0x14000b0fc  mov     r8, r12; dwData
0x14000b0ff  mov     rdx, [rdi]; hThread
0x14000b102  lea     rcx, ?CuipAMScanAPCProc@@YAX_K@Z; pfnAPC
0x14000b109  call    cs:__imp_QueueUserAPC
0x14000b10f  test    eax, eax
0x14000b111  jnz     short loc_14000B149
0x14000b113  call    cs:__imp_GetLastError
0x14000b119  mov     ebx, eax
0x14000b11b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b122  lea     rsi, WPP_GLOBAL_Control
0x14000b129  cmp     rcx, rsi
0x14000b12c  jz      loc_14000B749
0x14000b132  test    byte ptr [rcx+1Ch], 2
0x14000b136  jz      loc_14000B749
0x14000b13c  mov     edx, 1Bh
0x14000b141  mov     r9d, eax
0x14000b144  jmp     loc_14000B02F
0x14000b149  xor     r12d, r12d
0x14000b14c  mov     edx, 3E8h; dwMilliseconds
0x14000b151  mov     rcx, [rbp+47h+hHandle]; hHandle
0x14000b155  call    cs:__imp_WaitForSingleObject
0x14000b15b  test    eax, eax
0x14000b15d  jnz     short loc_14000B18B
0x14000b15f  mov     eax, [rbx]
0x14000b161  mov     [rsi], eax
0x14000b163  lea     rsi, WPP_GLOBAL_Control
0x14000b16a  cmp     dword ptr [rbx], 0FFFFFFFFh
0x14000b16d  jz      short loc_14000B181
0x14000b16f  mov     rax, [rbx+8]
0x14000b173  mov     [r14], rax
0x14000b176  mov     r13d, 1
0x14000b17c  jmp     loc_14000B747
0x14000b181  mov     ebx, 65Bh
0x14000b186  jmp     loc_14000B749
0x14000b18b  cmp     eax, 102h
0x14000b190  jnz     loc_14000B6F2
0x14000b196  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b19d  lea     rsi, WPP_GLOBAL_Control
0x14000b1a4  cmp     rcx, rsi
0x14000b1a7  jz      short loc_14000B1C4
0x14000b1a9  test    byte ptr [rcx+1Ch], 2
0x14000b1ad  jz      short loc_14000B1C4
0x14000b1af  mov     edx, 1Ch
0x14000b1b4  lea     r8, WPP_f8d62faa3d9632b4eb7f1f826e00b979_Traceguids
0x14000b1bb  mov     rcx, [rcx+10h]
0x14000b1bf  call    WPP_SF_
0x14000b1c4  mov     [rbp+47h+Context], r12
0x14000b1c8  mov     [rbp+47h+fPending], r12d
0x14000b1cc  lea     r9, [rbp+47h+Context]; lpContext
0x14000b1d0  lea     r8, [rbp+47h+fPending]; fPending
0x14000b1d4  xor     edx, edx; dwFlags
0x14000b1d6  lea     rcx, ?wrapper@?1??Instance@LUATelemetry@@KAPEAV2@XZ@4V?$static_lazy@VLUATelemetry@@@details@wil@@A; lpInitOnce
0x14000b1dd  call    cs:__imp_InitOnceBeginInitialize
0x14000b1e3  test    eax, eax
0x14000b1e5  jz      loc_14000B60E
0x14000b1eb  cmp     [rbp+47h+fPending], r12d
0x14000b1ef  jz      loc_14000B60E
0x14000b1f5  lea     rax, qword_140029C98
0x14000b1fc  mov     [rbp+47h+Context], rax
0x14000b200  mov     cs:qword_140029CA0, r12
0x14000b207  mov     cs:byte_140029CA8, r12b
0x14000b20e  mov     cs:dword_140029CAC, r12d
0x14000b215  lea     rax, ??_7TraceLoggingAggregateProvider@@6B@; const TraceLoggingAggregateProvider::`vftable'
0x14000b21c  mov     cs:qword_140029C98, rax
0x14000b223  lea     rax, ?__hInner@?1???0StaticHandle@LUATelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `LUATelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000b22a  mov     cs:CallbackContext, rax
0x14000b231  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8fd1dd6eff698f29c42c633fb94303b5_@@CA@XZ; void (__cdecl *)()
0x14000b238  call    atexit
0x14000b23d  mov     r13, cs:CallbackContext
0x14000b244  mov     cs:qword_140029CB0, r13
0x14000b24b  mov     cs:byte_140029CB8, 1
0x14000b252  mov     cl, 1
0x14000b254  call    CreateTlgAggregateSession
0x14000b259  mov     [rbp+47h+hHandle], rax
0x14000b25d  test    rax, rax
0x14000b260  jnz     short loc_14000B274
0x14000b262  xor     r8d, r8d
0x14000b265  xor     edx, edx
0x14000b267  mov     rcx, r13; CallbackContext
0x14000b26a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000b26f  jmp     loc_14000B5C4
0x14000b274  mov     qword ptr [rax+138h], 0
0x14000b27f  mov     qword ptr [rax+140h], 0
0x14000b28a  mov     [rax+148h], r13
0x14000b291  mov     r10, [r13+8]
0x14000b295  mov     r15, rax
0x14000b298  shr     r15, 4
0x14000b29c  mov     rax, r15
0x14000b29f  shr     rax, 30h
0x14000b2a3  movzx   r14d, al
0x14000b2a7  mov     rax, r15
0x14000b2aa  shr     rax, 28h
0x14000b2ae  movzx   esi, al
0x14000b2b1  mov     rax, r15
0x14000b2b4  shr     rax, 20h
0x14000b2b8  movzx   edi, al
0x14000b2bb  mov     rax, r15
0x14000b2be  shr     rax, 18h
0x14000b2c2  movzx   ebx, al
0x14000b2c5  mov     rax, r15
0x14000b2c8  shr     rax, 10h
0x14000b2cc  movzx   r11d, al
0x14000b2d0  mov     rax, r15
0x14000b2d3  shr     rax, 8
0x14000b2d7  movzx   r9d, al
0x14000b2db  movzx   r8d, r15b
0x14000b2df  movzx   eax, byte ptr [r10-10h]
0x14000b2e4  imul    ecx, eax, 401h
0x14000b2ea  mov     edx, ecx
0x14000b2ec  shr     edx, 6
0x14000b2ef  xor     edx, ecx
0x14000b2f1  movzx   eax, byte ptr [r10-0Fh]
0x14000b2f6  add     edx, eax
0x14000b2f8  imul    eax, edx, 401h
0x14000b2fe  mov     ecx, eax
0x14000b300  shr     ecx, 6
0x14000b303  xor     ecx, eax
0x14000b305  movzx   eax, byte ptr [r10-0Eh]
0x14000b30a  add     ecx, eax
0x14000b30c  imul    eax, ecx, 401h
0x14000b312  mov     ecx, eax
0x14000b314  shr     ecx, 6
0x14000b317  xor     ecx, eax
0x14000b319  movzx   eax, byte ptr [r10-0Dh]
0x14000b31e  add     ecx, eax
0x14000b320  imul    eax, ecx, 401h
0x14000b326  mov     ecx, eax
0x14000b328  shr     ecx, 6
0x14000b32b  xor     ecx, eax
0x14000b32d  movzx   eax, byte ptr [r10-0Ch]
0x14000b332  add     ecx, eax
0x14000b334  imul    eax, ecx, 401h
0x14000b33a  mov     ecx, eax
0x14000b33c  shr     ecx, 6
0x14000b33f  xor     ecx, eax
0x14000b341  movzx   eax, byte ptr [r10-0Bh]
0x14000b346  add     ecx, eax
0x14000b348  imul    eax, ecx, 401h
0x14000b34e  mov     ecx, eax
0x14000b350  shr     ecx, 6
0x14000b353  xor     ecx, eax
0x14000b355  movzx   eax, byte ptr [r10-0Ah]
0x14000b35a  add     ecx, eax
0x14000b35c  imul    eax, ecx, 401h
0x14000b362  mov     ecx, eax
0x14000b364  shr     ecx, 6
0x14000b367  xor     ecx, eax
0x14000b369  movzx   eax, byte ptr [r10-9]
0x14000b36e  add     ecx, eax
0x14000b370  imul    eax, ecx, 401h
0x14000b376  mov     ecx, eax
0x14000b378  shr     ecx, 6
0x14000b37b  xor     ecx, eax
0x14000b37d  movzx   eax, byte ptr [r10-8]
0x14000b382  add     ecx, eax
0x14000b384  imul    eax, ecx, 401h
0x14000b38a  mov     ecx, eax
0x14000b38c  shr     ecx, 6
0x14000b38f  xor     ecx, eax
0x14000b391  movzx   eax, byte ptr [r10-7]
0x14000b396  add     ecx, eax
0x14000b398  imul    eax, ecx, 401h
0x14000b39e  mov     ecx, eax
0x14000b3a0  shr     ecx, 6
0x14000b3a3  xor     ecx, eax
0x14000b3a5  movzx   eax, byte ptr [r10-6]
0x14000b3aa  add     ecx, eax
0x14000b3ac  imul    eax, ecx, 401h
0x14000b3b2  mov     ecx, eax
0x14000b3b4  shr     ecx, 6
0x14000b3b7  xor     ecx, eax
0x14000b3b9  movzx   eax, byte ptr [r10-5]
0x14000b3be  add     ecx, eax
0x14000b3c0  imul    eax, ecx, 401h
0x14000b3c6  mov     ecx, eax
0x14000b3c8  shr     ecx, 6
0x14000b3cb  xor     ecx, eax
0x14000b3cd  movzx   eax, byte ptr [r10-4]
0x14000b3d2  add     ecx, eax
0x14000b3d4  imul    eax, ecx, 401h
0x14000b3da  mov     ecx, eax
0x14000b3dc  shr     ecx, 6
0x14000b3df  xor     ecx, eax
0x14000b3e1  movzx   eax, byte ptr [r10-3]
0x14000b3e6  add     ecx, eax
0x14000b3e8  imul    eax, ecx, 401h
0x14000b3ee  mov     ecx, eax
0x14000b3f0  shr     ecx, 6
0x14000b3f3  xor     ecx, eax
0x14000b3f5  movzx   eax, byte ptr [r10-2]
0x14000b3fa  add     ecx, eax
0x14000b3fc  imul    eax, ecx, 401h
0x14000b402  mov     ecx, eax
0x14000b404  shr     ecx, 6
0x14000b407  xor     ecx, eax
0x14000b409  movzx   eax, byte ptr [r10-1]
0x14000b40e  add     ecx, eax
0x14000b410  imul    eax, ecx, 401h
0x14000b416  mov     ecx, eax
0x14000b418  shr     ecx, 6
0x14000b41b  xor     ecx, eax
0x14000b41d  add     ecx, r8d
0x14000b420  imul    eax, ecx, 401h
0x14000b426  mov     ecx, eax
0x14000b428  shr     ecx, 6
0x14000b42b  xor     ecx, eax
0x14000b42d  add     ecx, r9d
  ... truncated ...
```
