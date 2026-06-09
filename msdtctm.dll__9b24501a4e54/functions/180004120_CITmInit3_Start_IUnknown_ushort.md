# CITmInit3::Start(IUnknown *,ushort *)

- ea: `0x180004120`
- end: `0x180004c7c`
- name: `?Start@CITmInit3@@UEAAHPEAUIUnknown@@PEAG@Z`
- size: `2908`
- prototype: `__int64 __fastcall(CITmInit3 *__hidden this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180004120`
- `0x1800063b0`
- `0x18000bcd0`
- `0x180015230`
- `0x180017aa8`
- `0x180018bac`
- `0x180018d14`
- `0x18001cda8`
- `0x1800240b0`
- `0x18004a978`
- `0x18006e904`
- `0x180085624`
- `0x1800b8420`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000490e`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x18000490e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004bf3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004bf3`
- `MSDTCLOG!DllGetDTCLOG` at `0x18000421b`
- `MSDTCLOG!DllGetDTCLOG` at `0x18000421b`

## string_xrefs

- `0x1800041e1`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180004249`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x1800042ec`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180004473`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x1800044dc`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180004550`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x1800045cf`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x18000462f`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x1800046e5`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180004776`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x1800047dd`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180004877`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x1800048dc`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x1800049b0`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180004b74`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180004c3c`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x1800046ca`: `Unable to open stream for write`
- `0x180004a86`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x180004190`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x180004a9b`: `com\complus\dtc\dtc\tm\src\tminit.cpp`
- `0x1800045ad`: `Failed to open log stream`
- `0x18000460d`: `pILogRead->ReadInit failed`
- `0x18000485c`: `Failed to QI for ILogWriteAsynch`
- `0x1800048c1`: `Failed to initialize log write asynch`
- `0x180004bd0`: `com\complus\dtc\dtc\tm\src\tmtrace.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CITmInit3::Start(CITmInit3 *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  CTmTrace *v6; // rcx
  unsigned int v7; // ebx
  __int64 v8; // rcx
  unsigned int DTCLOG; // ebx
  __int64 v10; // rcx
  struct ILogStorage *v11; // rbx
  unsigned int v12; // edi
  __int64 v13; // rcx
  int v14; // esi
  unsigned int v15; // edi
  void *v16; // r9
  unsigned int v17; // edi
  __int64 v18; // rcx
  unsigned int v19; // edi
  __int64 v20; // rcx
  unsigned int v21; // ebx
  __int64 v22; // rcx
  unsigned int v23; // ebx
  __int64 v24; // rcx
  unsigned int v25; // ebx
  __int64 v26; // rcx
  unsigned int v27; // ebx
  int v28; // edi
  struct ILogStorage *v29; // rdx
  CITmInit3 *v30; // rcx
  int v31; // ebx
  struct ILogWrite *v32; // r8
  __int64 v33; // rcx
  struct ILogStorage *v34; // rdx
  CITmInit3 *v35; // rcx
  struct ILogWrite *v36; // r8
  unsigned int v37; // ebx
  __int64 v38; // rcx
  unsigned int v39; // ebx
  __int64 v40; // rcx
  CTmTrace *v41; // rcx
  CCheckpoint *v42; // rax
  CCheckpoint *v43; // rdx
  int v44; // eax
  CCheckpoint *v45; // rax
  int v46; // eax
  CTmTrace *v47; // rcx
  CCheckpoint *v48; // rax
  int v49; // eax
  void *v51; // [rsp+38h] [rbp-41h]
  struct ILogStorage *v52; // [rsp+60h] [rbp-19h] BYREF
  unsigned int Block; // [rsp+68h] [rbp-11h] BYREF
  int v54; // [rsp+6Ch] [rbp-Dh] BYREF
  struct ILogRead *v55; // [rsp+70h] [rbp-9h] BYREF
  union _ULARGE_INTEGER v56; // [rsp+78h] [rbp-1h] BYREF
  union _ULARGE_INTEGER v57; // [rsp+80h] [rbp+7h] BYREF
  CCheckpoint *v58; // [rsp+88h] [rbp+Fh]
  char v59[24]; // [rsp+90h] [rbp+17h] BYREF

  v52 = 0;
  v55 = 0;
  v54 = 0;
  v57.QuadPart = 0;
  v56.QuadPart = 0;
  Block = 0;
  if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IDtcTrace **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IDtcTrace,
         &g_pIDtcTrace) )
  {
    CTmTrace::InternalError(v6, "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp", 1248);
  }
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct ITransactionTrackerFactory **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_ITransactionTrackerFactory,
         &g_pITransactionTrackerFactory);
  if ( v7 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1254,
      L"CITmInit3::Start",
      v7,
      L"Failed to QI trace etc");
    CTmTrace::StartError(v8, 13, v7);
    return 0;
  }
  DTCLOG = DllGetDTCLOG(&CLSID_CLogMgr, &IID_ILogInit2W, (void **)&v52);
  if ( DTCLOG )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1263,
      L"CITmInit3::Start",
      DTCLOG,
      L"Failed to get the DTC log");
    CTmTrace::StartError(v10, 2, DTCLOG);
    return 0;
  }
  v11 = v52;
  LODWORD(v51) = 3;
  v12 = (*(__int64 (__fastcall **)(struct ILogStorage *, unsigned int *, int *, unsigned __int16 *, _DWORD))(*(_QWORD *)v52 + 24LL))(
          v52,
          &g_ulStorageCapacity,
          &v54,
          a3,
          0);
  if ( v12 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1283,
      L"CITmInit3::Start",
      v12,
      L"Failed to initialize the log at %s",
      a3);
    CTmTrace::StartError(v13, 15, v12);
    return 0;
  }
  v14 = v54;
  v15 = g_ulStorageCapacity;
  HIDWORD(qword_180158964) = g_ulStorageCapacity >> 3;
  dword_18015896C = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, _QWORD))(*(_QWORD *)g_pCoreTmInstance
                                                                                             + 344LL))(
                      g_pCoreTmInstance,
                      L"LogWarnEnabled",
                      0);
  if ( dword_18015896C )
  {
    LODWORD(qword_180158958) = 1;
    dword_180158970 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, __int64))(*(_QWORD *)g_pCoreTmInstance
                                                                                                + 344LL))(
                        g_pCoreTmInstance,
                        L"LogWarnInLimit",
                        100);
    dword_180158974 = (*(__int64 (__fastcall **)(struct ITmInstance *, const wchar_t *, _QWORD))(*(_QWORD *)g_pCoreTmInstance
                                                                                               + 344LL))(
                        g_pCoreTmInstance,
                        L"LogWarnOutLimit",
                        0);
    dword_180158960 = dword_180158970 * (SHIDWORD(qword_180158964) / 100);
    LODWORD(qword_180158964) = dword_180158974 * (SHIDWORD(qword_180158964) / 100);
    if ( (int)(v15 - v14) <= dword_180158960 )
    {
      HIDWORD(qword_180158958) = 0;
    }
    else
    {
      HIDWORD(qword_180158958) = 1;
      DtcWriteToEventLoggerExUnFilteredA(2u, 2u, 0xC000115E, v16, 0, 1u, 0, v51, 100);
    }
  }
  else
  {
    qword_180158958 = 0;
    dword_180158960 = HIDWORD(qword_180158964);
    LODWORD(qword_180158964) = 0;
  }
  v17 = (**(__int64 (__fastcall ***)(struct ILogStorage *, GUID *, struct ILogStorage **))v11)(
          v11,
          &IID_ILogRecordPointer,
          &v52);
  if ( v17 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1293,
      L"CITmInit3::Start",
      v17,
      L"Failed to QI for ILogRecordPointer");
    CTmTrace::StartError(v18, 12, v17);
    return 0;
  }
  v19 = (**(__int64 (__fastcall ***)(struct ILogStorage *, GUID *, struct ILogStorage **))v11)(
          v11,
          &IID_ILogStorage,
          &v52);
  if ( v19 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1304,
      L"CITmInit3::Start",
      v19,
      L"Failed to QI for ILogStorage");
    CTmTrace::StartError(v20, 11, v19);
    return 0;
  }
  g_pILogStorage = v52;
  v21 = (**(__int64 (__fastcall ***)(struct ILogStorage *, GUID *, struct ILogStorage **))v11)(
          v11,
          &IID_ILogStorageInfo,
          &v52);
  if ( v21 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1314,
      L"CITmInit3::Start",
      v21,
      L"Failed to QI for ILogStorageInfo");
    CTmTrace::StartError(v22, 11, v21);
    return 0;
  }
  g_pILogStorageInfo = v52;
  v23 = (*(__int64 (__fastcall **)(struct ILogStorage *, const char *, __int64, struct ILogRead **))(*(_QWORD *)g_pILogStorage + 24LL))(
          g_pILogStorage,
          "Streamname",
          1,
          &v55);
  if ( v23 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1324,
      L"CITmInit3::Start",
      v23,
      L"Failed to open log stream");
    CTmTrace::StartError(v24, 9, v23);
    return 0;
  }
  v25 = (*(__int64 (__fastcall **)(struct ILogRead *))(*(_QWORD *)v55 + 24LL))(v55);
  if ( v25 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1332,
      L"CITmInit3::Start",
      v25,
      L"pILogRead->ReadInit failed");
    CTmTrace::StartError(v26, 5, v25);
    return 0;
  }
  v27 = (*(__int64 (__fastcall **)(struct ILogRead *, __int64, union _ULARGE_INTEGER *))(*(_QWORD *)v55 + 72LL))(
          v55,
          2,
          &v57);
  if ( v27 == -2147467259 )
  {
    v28 = 1;
  }
  else
  {
    v28 = 0;
    if ( v27 )
    {
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
        1348,
        L"CITmInit3::Start",
        v27,
        L"Unknown error from GetCheckpoint");
      CTmTrace::StartError(v33, 4, v27);
    }
    if ( !(unsigned int)CITmInit3::ReadRecovery(this, v55, &v57, &v56, &Block) )
    {
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
        1364,
        L"CITmInit3::Start",
        -2147467259,
        L"Unable to do recovery");
      return 0;
    }
  }
  (*(void (__fastcall **)(struct ILogRead *))(*(_QWORD *)v55 + 16LL))(v55);
  v31 = (*(__int64 (__fastcall **)(struct ILogStorage *, const char *, __int64, struct ILogWrite **))(*(_QWORD *)g_pILogStorage + 24LL))(
          g_pILogStorage,
          "Streamname",
          2,
          &g_pILogWrite);
  if ( v31 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1374,
      L"CITmInit3::Start",
      v31,
      L"Unable to open stream for write");
    TracedStringCchPrintfA(v59, 0x14u, "0x%x", v31);
    (*(void (__fastcall **)(struct IDtcTrace *, __int64, __int64, _QWORD, int, _DWORD, _QWORD, char *))(*(_QWORD *)g_pIDtcTrace + 24LL))(
      g_pIDtcTrace,
      4097,
      2,
      0,
      -1073737644,
      0,
      0,
      v59);
    return 0;
  }
  if ( v28 == 1 )
  {
    if ( !(unsigned int)CITmInit3::WriteEmptyCheckpoint(v30, v29, v32, &v56) )
    {
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
        1385,
        L"CITmInit3::Start",
        -2147467259,
        L"Error writing empty #1");
      return 0;
    }
    if ( !(unsigned int)CITmInit3::WriteEmptyCheckpoint(v35, v34, v36, &v56) )
    {
      TraceStringInline(
        3,
        1,
        L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
        1393,
        L"CITmInit3::Start",
        -2147467259,
        L"Error writing empty #2");
      return 0;
    }
    Block = 0;
  }
  v37 = (**(__int64 (__fastcall ***)(struct ILogWrite *, GUID *, struct ILogStorage **))g_pILogWrite)(
          g_pILogWrite,
          &IID_ILogWriteAsynch,
          &v52);
  if ( v37 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1404,
      L"CITmInit3::Start",
      v37,
      L"Failed to QI for ILogWriteAsynch");
    CTmTrace::StartError(v38, 16, v37);
    return 0;
  }
  g_pILogWriteAsynch = v52;
  v39 = (*(__int64 (__fastcall **)(struct ILogStorage *, __int64))(*(_QWORD *)v52 + 24LL))(v52, 50);
  if ( v39 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1414,
      L"CITmInit3::Start",
      v39,
      L"Failed to initialize log write asynch");
    CTmTrace::StartError(v40, 17, v39);
    return 0;
  }
  g_hevTmStarted = CreateEventA(0, 0, 0, 0);
  if ( !g_hevTmStarted )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1423,
      L"CITmInit3::Start",
      -2147024882,
      L"OOM Creating TM started event");
LABEL_65:
    CTmTrace::StartErrorNoMem(v41);
    return 0;
  }
  v42 = (CCheckpoint *)operator new(0x1E8u);
  v58 = v42;
  if ( v42 )
    v43 = CCheckpoint::CCheckpoint(v42);
  else
    v43 = 0;
  g_pCheckpoint = v43;
  if ( !v43 )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1432,
      L"CITmInit3::Start",
      -2147024882,
      L"OOM Creating CCheckpoint");
    goto LABEL_65;
  }
  if ( !(***((unsigned int (__fastcall ****)(_QWORD, CCheckpoint *, _QWORD, union _ULARGE_INTEGER))v43 + 45))(
          *((_QWORD *)v43 + 45),
          v43,
          Block,
          v56) )
  {
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1443,
      L"CITmInit3::Start",
      -2147467259,
      L"Failed to start checkpoint thingy");
    v44 = (*(__int64 (__fastcall **)(struct IDtcTrace *, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)g_pIDtcTrace + 24LL))(
            g_pIDtcTrace,
            4097,
            2,
            0,
            -1073737636,
            0,
            0,
            0);
    if ( v44 >= 0 )
      return 0;
    goto LABEL_61;
  }
  v45 = (CCheckpoint *)operator new(0x80u);
  v58 = v45;
  if ( !v45 )
  {
    g_pJoinCheckpointClique = 0;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1451,
      L"CITmInit3::Start",
      -2147024882,
      L"OOM creating join checkpoint clique");
    goto LABEL_65;
  }
  *(_QWORD *)v45 = &CJoinCheckpointClique::`vftable'{for `ICliqueCreateSink'};
  *((_QWORD *)v45 + 1) = &CJoinCheckpointClique::`vftable'{for `CCliqueSignalSink_Checkpoint'};
  *((_QWORD *)v45 + 5) = &CJoinCheckpointClique::`vftable'{for `CJoinStatusSink_Checkpoint'};
  *((_QWORD *)v45 + 12) = 0;
  *((_QWORD *)v45 + 13) = 0;
  *((_QWORD *)v45 + 14) = 0;
  *((_DWORD *)v45 + 22) = 0;
  *((_DWORD *)v45 + 30) = 0;
  g_pJoinCheckpointClique = v45;
  v46 = (*(__int64 (__fastcall **)(struct ICliqueDispenser *))(*(_QWORD *)g_pICliqueDispenser + 24LL))(g_pICliqueDispenser);
  if ( v46 < 0 )
    CTmTrace::InternalError(v47, "com\\complus\\dtc\\dtc\\tm\\src\\tmcheckp.cpp", 1668);
  if ( v46 )
    CTmTrace::InternalError(v47, "com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp", 1458);
  v48 = (CCheckpoint *)operator new(0xD8u);
  v58 = v48;
  if ( !v48 )
  {
    g_pCLLTxTrace = 0;
    TraceStringInline(
      3,
      1,
      L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
      1467,
      L"CITmInit3::Start",
      -2147024882,
      L"OOM creating long lived trace");
    goto LABEL_65;
  }
  *((_QWORD *)v48 + 6) = &UTLink<_IOMGROVERLAP *>::`vftable';
  *((_DWORD *)v48 + 20) = 0;
  *((_QWORD *)v48 + 11) = 0;
  *((_QWORD *)v48 + 7) = (char *)v48 + 8;
  *((_QWORD *)v48 + 9) = 0;
  *((_QWORD *)v48 + 8) = 0;
  *(_QWORD *)v48 = &CLLTxTrace::`vftable'{for `CImpICliqueCreateSink_LLTxTrace'};
  *((_QWORD *)v48 + 1) = &CLLTxTrace::`vftable'{for `CCliqueTimerSink_LLTxTrace'};
  *((_QWORD *)v48 + 12) = &CLLTxTrace::`vftable'{for `CJoinStatusSink_LLTxTrace'};
  *((_QWORD *)v48 + 18) = &CLLTxTrace::`vftable'{for `CCliqueSignalSink_LLTxTrace'};
  *((_QWORD *)v48 + 22) = g_CLLTxTrace_State_PreInit;
  *((_QWORD *)v48 + 23) = 0;
  *((_QWORD *)v48 + 24) = 0;
  *((_QWORD *)v48 + 25) = 0;
  *((_QWORD *)v48 + 26) = 0;
  g_pCLLTxTrace = v48;
  v49 = (*(__int64 (__fastcall **)(void ***, CCheckpoint *))g_CLLTxTrace_State_PreInit[0])(
          g_CLLTxTrace_State_PreInit,
          v48);
  if ( v49 >= 0 )
  {
    WaitForSingleObject(g_hevTmStarted, 0xFFFFFFFF);
    return 1;
  }
  TraceStringInline(
    3,
    1,
    L"com\\complus\\dtc\\dtc\\tm\\src\\tminit.cpp",
    1475,
    L"CITmInit3::Start",
    v49,
    L"Failed to init long-lived trace");
  v44 = (*(__int64 (__fastcall **)(struct IDtcTrace *, __int64, __int64, _QWORD, int, _DWORD, _QWORD, _QWORD))(*(_QWORD *)g_pIDtcTrace + 24LL))(
          g_pIDtcTrace,
          4097,
          2,
          0,
          -1073737636,
          0,
          0,
          0);
  if ( v44 < 0 )
LABEL_61:
    TraceFile(v44, "failed in g_pIDtcTrace->Trace", "com\\complus\\dtc\\dtc\\tm\\src\\tmtrace.cpp", 0x164u);
  return 0;
}

```

## disassembly

```asm
0x180004120  mov     [rsp-8+arg_18], rbx
0x180004125  push    rbp
0x180004126  push    rsi
0x180004127  push    rdi
0x180004128  push    r14
0x18000412a  push    r15
0x18000412c  lea     rbp, [rsp-37h]
0x180004131  sub     rsp, 0B0h
0x180004138  mov     rax, cs:__security_cookie
0x18000413f  xor     rax, rsp
0x180004142  mov     [rbp+57h+var_28], rax
0x180004146  mov     rsi, r8
0x180004149  mov     rbx, rdx
0x18000414c  mov     r14, rcx
0x18000414f  xor     r15d, r15d
0x180004152  mov     [rbp+57h+var_70], r15
0x180004156  mov     [rbp+57h+var_60], r15
0x18000415a  mov     [rbp+57h+var_64], r15d
0x18000415e  mov     qword ptr [rbp+57h+var_50], r15
0x180004162  mov     qword ptr [rbp+57h+var_58], r15
0x180004166  mov     [rbp+57h+var_68], r15d
0x18000416a  mov     rax, [rdx]
0x18000416d  lea     r8, ?g_pIDtcTrace@@3PEAUIDtcTrace@@EA; IDtcTrace * g_pIDtcTrace
0x180004174  lea     rdx, IID_IDtcTrace
0x18000417b  mov     rcx, rbx
0x18000417e  mov     rax, [rax]
0x180004181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004186  test    eax, eax
0x180004188  jz      short loc_18000419D
0x18000418a  mov     r8d, 4E0h; int
0x180004190  lea     rdx, aComComplusDtcD_27; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x180004197  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x18000419d  mov     rax, [rbx]
0x1800041a0  lea     r8, ?g_pITransactionTrackerFactory@@3PEAUITransactionTrackerFactory@@EA; ITransactionTrackerFactory * g_pITransactionTrackerFactory
0x1800041a7  lea     rdx, IID_ITransactionTrackerFactory
0x1800041ae  mov     rcx, rbx
0x1800041b1  mov     rax, [rax]
0x1800041b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b9  mov     ebx, eax
0x1800041bb  test    eax, eax
0x1800041bd  jz      short loc_180004209
0x1800041bf  lea     rax, aFailedToQiTrac; "Failed to QI trace etc"
0x1800041c6  mov     [rsp+0D0h+var_A0], rax
0x1800041cb  mov     [rsp+0D0h+var_A8], ebx
0x1800041cf  lea     rsi, aCitminit3Start; "CITmInit3::Start"
0x1800041d6  mov     [rsp+0D0h+Block], rsi
0x1800041db  mov     r9d, 4E6h
0x1800041e1  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x1800041e8  mov     edx, 1
0x1800041ed  mov     ecx, 3
0x1800041f2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800041f7  mov     r8d, ebx
0x1800041fa  mov     edx, 0Dh
0x1800041ff  call    ?StartError@CTmTrace@@QEAAXW4_Start_Error@@J@Z; CTmTrace::StartError(_Start_Error,long)
0x180004204  jmp     loc_180004C57
0x180004209  lea     r8, [rbp+57h+var_70]
0x18000420d  lea     rdx, IID_ILogInit2W
0x180004214  lea     rcx, CLSID_CLogMgr
0x18000421b  call    cs:__imp_?DllGetDTCLOG@@YAJAEBU_GUID@@0PEAPEAX@Z; DllGetDTCLOG(_GUID const &,_GUID const &,void * *)
0x180004221  mov     ebx, eax
0x180004223  test    eax, eax
0x180004225  jz      short loc_180004271
0x180004227  lea     rax, aFailedToGetThe_1; "Failed to get the DTC log"
0x18000422e  mov     [rsp+0D0h+var_A0], rax
0x180004233  mov     [rsp+0D0h+var_A8], ebx
0x180004237  lea     rsi, aCitminit3Start; "CITmInit3::Start"
0x18000423e  mov     [rsp+0D0h+Block], rsi
0x180004243  mov     r9d, 4EFh
0x180004249  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x180004250  mov     edx, 1
0x180004255  mov     ecx, 3
0x18000425a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18000425f  mov     r8d, ebx
0x180004262  mov     edx, 2
0x180004267  call    ?StartError@CTmTrace@@QEAAXW4_Start_Error@@J@Z; CTmTrace::StartError(_Start_Error,long)
0x18000426c  jmp     loc_180004C57
0x180004271  mov     rbx, [rbp+57h+var_70]
0x180004275  mov     rax, [rbx]
0x180004278  mov     [rsp+0D0h+var_88], 0C8h
0x180004280  mov     [rsp+0D0h+var_90], 64h ; 'd'; int
0x180004288  mov     dword ptr [rsp+0D0h+var_98], 3; void *
0x180004290  mov     dword ptr [rsp+0D0h+var_A0], 3
0x180004298  mov     [rsp+0D0h+var_A8], 1; unsigned int
0x1800042a0  mov     dword ptr [rsp+0D0h+Block], r15d
0x1800042a5  mov     r9, rsi
0x1800042a8  lea     r8, [rbp+57h+var_64]
0x1800042ac  lea     rdx, ?g_ulStorageCapacity@@3KA; ulong g_ulStorageCapacity
0x1800042b3  mov     rcx, rbx
0x1800042b6  mov     rax, [rax+18h]
0x1800042ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042bf  mov     edi, eax
0x1800042c1  test    eax, eax
0x1800042c3  jz      short loc_180004314
0x1800042c5  mov     [rsp+0D0h+var_98], rsi
0x1800042ca  lea     rax, aFailedToInitia_2; "Failed to initialize the log at %s"
0x1800042d1  mov     [rsp+0D0h+var_A0], rax
0x1800042d6  mov     [rsp+0D0h+var_A8], edi
0x1800042da  lea     rsi, aCitminit3Start; "CITmInit3::Start"
0x1800042e1  mov     [rsp+0D0h+Block], rsi
0x1800042e6  mov     r9d, 503h
0x1800042ec  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x1800042f3  mov     edx, 1
0x1800042f8  mov     ecx, 3
0x1800042fd  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180004302  mov     r8d, edi
0x180004305  mov     edx, 0Fh
0x18000430a  call    ?StartError@CTmTrace@@QEAAXW4_Start_Error@@J@Z; CTmTrace::StartError(_Start_Error,long)
0x18000430f  jmp     loc_180004C57
0x180004314  mov     esi, [rbp+57h+var_64]
0x180004317  mov     edi, cs:?g_ulStorageCapacity@@3KA; ulong g_ulStorageCapacity
0x18000431d  mov     eax, edi
0x18000431f  shr     eax, 3
0x180004322  mov     dword ptr cs:qword_180158964+4, eax
0x180004328  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x18000432f  mov     rax, [rcx]
0x180004332  xor     r8d, r8d
0x180004335  lea     rdx, aLogwarnenabled; "LogWarnEnabled"
0x18000433c  mov     rax, [rax+158h]
0x180004343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004348  mov     cs:dword_18015896C, eax
0x18000434e  test    eax, eax
0x180004350  jz      loc_180004418
0x180004356  mov     dword ptr cs:qword_180158958, 1
0x180004360  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180004367  mov     rax, [rcx]
0x18000436a  mov     r8d, 64h ; 'd'
0x180004370  lea     rdx, aLogwarninlimit; "LogWarnInLimit"
0x180004377  mov     rax, [rax+158h]
0x18000437e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004383  mov     cs:dword_180158970, eax
0x180004389  mov     rcx, cs:?g_pCoreTmInstance@@3PEAUITmInstance@@EA; ITmInstance * g_pCoreTmInstance
0x180004390  mov     rax, [rcx]
0x180004393  xor     r8d, r8d
0x180004396  lea     rdx, aLogwarnoutlimi; "LogWarnOutLimit"
0x18000439d  mov     rax, [rax+158h]
0x1800043a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a9  mov     r8d, eax
0x1800043ac  mov     cs:dword_180158974, eax
0x1800043b2  mov     eax, 51EB851Fh
0x1800043b7  imul    dword ptr cs:qword_180158964+4
0x1800043bd  sar     edx, 5
0x1800043c0  mov     ecx, edx
0x1800043c2  shr     ecx, 1Fh
0x1800043c5  add     edx, ecx
0x1800043c7  mov     ecx, edx
0x1800043c9  imul    ecx, cs:dword_180158970
0x1800043d0  mov     cs:dword_180158960, ecx
0x1800043d6  imul    edx, r8d
0x1800043da  mov     dword ptr cs:qword_180158964, edx
0x1800043e0  sub     edi, esi
0x1800043e2  cmp     edi, ecx
0x1800043e4  jle     short loc_18000440F
0x1800043e6  mov     dword ptr cs:qword_180158958+4, 1
0x1800043f0  mov     edx, 2; unsigned __int16
0x1800043f5  mov     ecx, edx; unsigned __int16
0x1800043f7  mov     [rsp+0D0h+var_A0], r15; char **
0x1800043fc  mov     word ptr [rsp+0D0h+Block], r15w; unsigned __int16
0x180004402  mov     r8d, 0C000115Eh; unsigned int
0x180004408  call    ?DtcWriteToEventLoggerExUnFilteredA@@YAJGGKPEAXGKPEAPEBD0H@Z; DtcWriteToEventLoggerExUnFilteredA(ushort,ushort,ulong,void *,ushort,ulong,char const * *,void *,int)
0x18000440d  jmp     short loc_180004432
0x18000440f  mov     dword ptr cs:qword_180158958+4, r15d
0x180004416  jmp     short loc_180004432
0x180004418  mov     cs:qword_180158958, r15
0x18000441f  mov     eax, dword ptr cs:qword_180158964+4
0x180004425  mov     cs:dword_180158960, eax
0x18000442b  mov     dword ptr cs:qword_180158964, r15d
0x180004432  mov     rax, [rbx]
0x180004435  lea     r8, [rbp+57h+var_70]
0x180004439  lea     rdx, IID_ILogRecordPointer
0x180004440  mov     rcx, rbx
0x180004443  mov     rax, [rax]
0x180004446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000444b  mov     edi, eax
0x18000444d  test    eax, eax
0x18000444f  jz      short loc_18000449B
0x180004451  lea     rax, aFailedToQiForI_2; "Failed to QI for ILogRecordPointer"
0x180004458  mov     [rsp+0D0h+var_A0], rax
0x18000445d  mov     [rsp+0D0h+var_A8], edi
0x180004461  lea     rsi, aCitminit3Start; "CITmInit3::Start"
0x180004468  mov     [rsp+0D0h+Block], rsi
0x18000446d  mov     r9d, 50Dh
0x180004473  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x18000447a  mov     edx, 1
0x18000447f  mov     ecx, 3
0x180004484  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180004489  mov     r8d, edi
0x18000448c  mov     edx, 0Ch
0x180004491  call    ?StartError@CTmTrace@@QEAAXW4_Start_Error@@J@Z; CTmTrace::StartError(_Start_Error,long)
0x180004496  jmp     loc_180004C57
0x18000449b  mov     rax, [rbx]
0x18000449e  lea     r8, [rbp+57h+var_70]
0x1800044a2  lea     rdx, IID_ILogStorage
0x1800044a9  mov     rcx, rbx
0x1800044ac  mov     rax, [rax]
0x1800044af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044b4  mov     edi, eax
0x1800044b6  test    eax, eax
0x1800044b8  jz      short loc_180004504
0x1800044ba  lea     rax, aFailedToQiForI_0; "Failed to QI for ILogStorage"
0x1800044c1  mov     [rsp+0D0h+var_A0], rax
0x1800044c6  mov     [rsp+0D0h+var_A8], edi
0x1800044ca  lea     rsi, aCitminit3Start; "CITmInit3::Start"
0x1800044d1  mov     [rsp+0D0h+Block], rsi
0x1800044d6  mov     r9d, 518h
0x1800044dc  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x1800044e3  mov     edx, 1
0x1800044e8  mov     ecx, 3
0x1800044ed  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800044f2  mov     r8d, edi
0x1800044f5  mov     edx, 0Bh
0x1800044fa  call    ?StartError@CTmTrace@@QEAAXW4_Start_Error@@J@Z; CTmTrace::StartError(_Start_Error,long)
0x1800044ff  jmp     loc_180004C57
0x180004504  mov     rax, [rbp+57h+var_70]
0x180004508  mov     cs:?g_pILogStorage@@3PEAUILogStorage@@EA, rax; ILogStorage * g_pILogStorage
0x18000450f  mov     rax, [rbx]
0x180004512  lea     r8, [rbp+57h+var_70]
0x180004516  lea     rdx, IID_ILogStorageInfo
0x18000451d  mov     rcx, rbx
0x180004520  mov     rax, [rax]
0x180004523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004528  mov     ebx, eax
0x18000452a  test    eax, eax
0x18000452c  jz      short loc_180004578
0x18000452e  lea     rax, aFailedToQiForI_1; "Failed to QI for ILogStorageInfo"
0x180004535  mov     [rsp+0D0h+var_A0], rax
0x18000453a  mov     [rsp+0D0h+var_A8], ebx
0x18000453e  lea     rsi, aCitminit3Start; "CITmInit3::Start"
0x180004545  mov     [rsp+0D0h+Block], rsi
0x18000454a  mov     r9d, 522h
0x180004550  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x180004557  mov     edx, 1
0x18000455c  mov     ecx, 3
0x180004561  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180004566  mov     r8d, ebx
0x180004569  mov     edx, 0Bh
0x18000456e  call    ?StartError@CTmTrace@@QEAAXW4_Start_Error@@J@Z; CTmTrace::StartError(_Start_Error,long)
0x180004573  jmp     loc_180004C57
0x180004578  mov     rax, [rbp+57h+var_70]
0x18000457c  mov     cs:?g_pILogStorageInfo@@3PEAUILogStorageInfo@@EA, rax; ILogStorageInfo * g_pILogStorageInfo
0x180004583  mov     rcx, cs:?g_pILogStorage@@3PEAUILogStorage@@EA; ILogStorage * g_pILogStorage
0x18000458a  mov     rax, [rcx]
0x18000458d  lea     r9, [rbp+57h+var_60]
0x180004591  mov     r8d, 1
0x180004597  lea     rdx, aStreamname_0; "Streamname"
0x18000459e  mov     rax, [rax+18h]
0x1800045a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045a7  mov     ebx, eax
0x1800045a9  test    eax, eax
0x1800045ab  jz      short loc_1800045F7
0x1800045ad  lea     rax, aFailedToOpenLo; "Failed to open log stream"
0x1800045b4  mov     [rsp+0D0h+var_A0], rax
0x1800045b9  mov     [rsp+0D0h+var_A8], ebx
0x1800045bd  lea     rsi, aCitminit3Start; "CITmInit3::Start"
0x1800045c4  mov     [rsp+0D0h+Block], rsi
0x1800045c9  mov     r9d, 52Ch
0x1800045cf  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x1800045d6  mov     edx, 1
0x1800045db  mov     ecx, 3
0x1800045e0  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800045e5  mov     r8d, ebx
0x1800045e8  mov     edx, 9
0x1800045ed  call    ?StartError@CTmTrace@@QEAAXW4_Start_Error@@J@Z; CTmTrace::StartError(_Start_Error,long)
0x1800045f2  jmp     loc_180004C57
0x1800045f7  mov     rcx, [rbp+57h+var_60]
0x1800045fb  mov     rax, [rcx]
0x1800045fe  mov     rax, [rax+18h]
0x180004602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004607  mov     ebx, eax
0x180004609  test    eax, eax
0x18000460b  jz      short loc_180004657
0x18000460d  lea     rax, aPilogreadReadi; "pILogRead->ReadInit failed"
0x180004614  mov     [rsp+0D0h+var_A0], rax
0x180004619  mov     [rsp+0D0h+var_A8], ebx
0x18000461d  lea     rsi, aCitminit3Start; "CITmInit3::Start"
0x180004624  mov     [rsp+0D0h+Block], rsi
0x180004629  mov     r9d, 534h
0x18000462f  lea     r8, aComComplusDtcD_86; "com\\complus\\dtc\\dtc\\tm\\src\\tminit"...
0x180004636  mov     edx, 1
0x18000463b  mov     ecx, 3
0x180004640  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180004645  mov     r8d, ebx
0x180004648  mov     edx, 5
0x18000464d  call    ?StartError@CTmTrace@@QEAAXW4_Start_Error@@J@Z; CTmTrace::StartError(_Start_Error,long)
0x180004652  jmp     loc_180004C57
0x180004657  mov     rcx, [rbp+57h+var_60]
0x18000465b  mov     rax, [rcx]
0x18000465e  lea     r8, [rbp+57h+var_50]
0x180004662  mov     edx, 2
0x180004667  mov     rax, [rax+48h]
0x18000466b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004670  mov     ebx, eax
0x180004672  lea     rsi, aCitminit3Start; "CITmInit3::Start"
0x180004679  cmp     eax, 80004005h
0x18000467e  jnz     loc_180004754
0x180004684  mov     edi, 1
0x180004689  mov     rcx, [rbp+57h+var_60]
0x18000468d  mov     rax, [rcx]
0x180004690  mov     rax, [rax+10h]
0x180004694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004699  mov     rcx, cs:?g_pILogStorage@@3PEAUILogStorage@@EA; ILogStorage * g_pILogStorage
  ... truncated ...
```
