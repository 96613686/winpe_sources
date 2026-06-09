# HandleMessage(tagPushMsgEx *)

- ea: `0x14000fff0`
- end: `0x1400107e4`
- name: `?HandleMessage@@YAJPEAUtagPushMsgEx@@@Z`
- size: `2036`
- prototype: `__int64 __fastcall(struct tagPushMsgEx *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000abe0`

## callees

- `0x140001090`
- `0x14000812c`
- `0x14000b708`
- `0x14000b860`
- `0x14000bd90`
- `0x14000c084`
- `0x14000e710`
- `0x14000edf4`
- `0x14000f6b8`
- `0x14000f76c`
- `0x14000fadc`
- `0x14000fff0`
- `0x140010bb8`
- `0x140010d08`
- `0x140010f44`
- `0x1400112f4`
- `0x140011468`
- `0x1400128d4`
- `0x14001401c`
- `0x14001490c`
- `0x140015690`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001079e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001079e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400107b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400107b3`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010114`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400102c0`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010114`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400102c0`
- `DMCmnUtils!InvStrCmpNIW` at `0x140010086`
- `DMCmnUtils!InvStrCmpNIW` at `0x140010086`
- `DMCmnUtils!GetHeader` at `0x140010055`
- `DMCmnUtils!GetHeader` at `0x140010055`
- `DMCmnUtils!DmDeleteTask` at `0x14001022d`
- `DMCmnUtils!DmDeleteTask` at `0x14001067e`
- `DMCmnUtils!DmDeleteTask` at `0x14001022d`
- `DMCmnUtils!DmDeleteTask` at `0x14001067e`
- `DMCmnUtils!InvStrCmpW` at `0x1400101c1`
- `DMCmnUtils!InvStrCmpW` at `0x1400101c1`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1400101f6`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x14001037e`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1400104d3`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1400101f6`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x14001037e`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1400104d3`
- `DMCmnUtils!BigStrcat` at `0x1400101a1`
- `DMCmnUtils!BigStrcat` at `0x1400101a1`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140010260`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x140010260`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140010161`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140010161`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400101d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010771`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010781`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010792`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1400101d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010771`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010781`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140010792`
- `omadmapi!__imp_OmaDmCloseSession` at `0x140010275`
- `omadmapi!__imp_OmaDmCloseSession` at `0x140010275`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x1400100d4`
- `omadmapi!__imp_OmaDmGetInternalAcctID` at `0x1400100d4`

## string_xrefs

- `0x14001010a`: `SessionAutoDeleteKey`
- `0x14001021c`: `Retry Schedule created for incomplete session`
- `0x140010641`: `TryScheduleRetryTask`
- `0x1400103e2`: `DeleteSessionRetryTask`
- `0x14001066b`: `Queued Schedule created for queued alerts`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall HandleMessage(struct tagPushMsgEx *a1)
{
  int v2; // eax
  COmaDmPrcLogger *Logger; // rax
  const unsigned __int16 *v4; // r15
  HLOCAL v5; // rbx
  int v6; // esi
  char IsStateSeparationEnabled; // al
  const wchar_t *v8; // rdx
  const unsigned __int16 *v9; // rax
  unsigned __int16 *v10; // rbx
  const WCHAR *v11; // rdi
  const unsigned __int16 *v12; // rsi
  int v13; // ebx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rcx
  int v17; // edx
  unsigned int v18; // r8d
  COmaDmPrcLogger *v19; // rax
  const unsigned __int16 *v20; // r9
  COmaDmPrcLogger *v21; // rax
  const unsigned __int16 *v22; // r9
  COmaDmPrcLogger *v23; // rax
  const unsigned __int16 *v24; // r9
  COmaDmPrcLogger *v25; // rax
  const unsigned __int16 *v26; // r9
  COmaDmPrcLogger *v27; // rax
  const unsigned __int16 *v28; // r9
  unsigned int v29; // r8d
  __int64 v30; // r8
  COmaDmPrcLogger *v31; // rax
  COmaDmPrcLogger *v32; // rax
  int v33; // eax
  __int64 *v34; // rax
  __int64 v35; // rcx
  unsigned int v36; // ecx
  HANDLE ProcessHeap; // rax
  int Header; // [rsp+50h] [rbp-89h] BYREF
  HLOCAL v40; // [rsp+58h] [rbp-81h] BYREF
  int v41; // [rsp+60h] [rbp-79h] BYREF
  __int16 v42; // [rsp+64h] [rbp-75h]
  int v43; // [rsp+68h] [rbp-71h] BYREF
  int v44; // [rsp+6Ch] [rbp-6Dh] BYREF
  unsigned int v45; // [rsp+70h] [rbp-69h] BYREF
  __int64 v46; // [rsp+78h] [rbp-61h] BYREF
  unsigned int v47[4]; // [rsp+80h] [rbp-59h] BYREF
  LPVOID lpMem[2]; // [rsp+90h] [rbp-49h]
  HLOCAL v49[2]; // [rsp+A0h] [rbp-39h]
  HLOCAL hMem; // [rsp+B0h] [rbp-29h] BYREF
  void *v51; // [rsp+B8h] [rbp-21h] BYREF
  unsigned int *v52; // [rsp+C0h] [rbp-19h]
  void *p_Header; // [rsp+C8h] [rbp-11h]
  char v54; // [rsp+D0h] [rbp-9h]
  int *v55; // [rsp+D8h] [rbp-1h]
  __int64 v56; // [rsp+E0h] [rbp+7h]

  Header = 0;
  v43 = 0;
  v44 = 0;
  hMem = 0;
  *(_OWORD *)v47 = 0;
  *(_OWORD *)lpMem = 0;
  *(_OWORD *)v49 = 0;
  v40 = 0;
  v45 = 0;
  Header = GetHeader(*((const unsigned __int16 **)a1 + 1), L"Content-Type", (unsigned __int16 **)&hMem);
  if ( Header < 0 )
    goto LABEL_67;
  if ( !hMem || InvStrCmpNIW(L"application/vnd.syncml.notification", (const unsigned __int16 *)hMem, 0x23u) )
  {
    if ( (unsigned int)dword_140023000 > 5 )
    {
      v34 = (__int64 *)hMem;
      if ( hMem )
      {
        v35 = -1;
        do
          ++v35;
        while ( *((_WORD *)hMem + v35) );
        v36 = 2 * v35 + 2;
      }
      else
      {
        v34 = &qword_14001A798;
        v36 = 2;
      }
      v55 = (int *)v34;
      v56 = v36;
      tlgWriteTransfer_EventWriteTransfer(&dword_140023000, &unk_14001E2A0, 0, 0, 3, &v51);
    }
    Header = -2147024809;
  }
  else
  {
    v2 = ParseTriggerMsg(a1, (struct tagTriggerInfo *)v47);
    Header = v2;
    if ( v2 == -2102722548 )
    {
      Header = 1;
      goto LABEL_67;
    }
    if ( v2 >= 0 )
    {
      Header = OmaDmGetInternalAcctID(lpMem[0], LODWORD(lpMem[1]), &v40);
      if ( Header >= 0 )
      {
        InitializeCVMapForDmSession((const unsigned __int16 *)v40);
        if ( !v49[0]
          || (Header = OmaDmRegistryGetDWORD(
                         HKEY_LOCAL_MACHINE,
                         (const unsigned __int16 *)v49[0],
                         L"SessionAutoDeleteKey",
                         &v45),
              Header >= 0) )
        {
          Logger = COmaDmPrcLogger::GetLogger();
          COmaDmPrcLogger::LogOmaDmPrcHandleMessage(
            Logger,
            (const unsigned __int16 *)v40,
            (const unsigned __int16 *)v49[0],
            v47[1],
            BYTE1(v47[2]),
            *((_DWORD *)a1 + 14));
          v4 = (const unsigned __int16 *)v49[0];
          v5 = v40;
          v6 = 0;
          IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
          v8 = L"OSData\\Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
          if ( !IsStateSeparationEnabled )
            v8 = L"Software\\Microsoft\\Provisioning\\OMADM\\Sessions";
          v9 = BigStrcat(5u, v8, L"\\", v5, L"\\", L"{973CC073-B7F4-4B3B-ABF8-74DF3FCAE76F}");
          v10 = (unsigned __int16 *)v9;
          if ( v9 && !InvStrCmpW(v4, v9) )
            v6 = 1;
          LocalFree(v10);
          if ( v6 )
          {
            if ( IsWvdFeatureAllowed((const unsigned __int16 *)v40) )
            {
              Header = -2147418113;
              goto LABEL_67;
            }
            v11 = (const WCHAR *)v49[0];
            v12 = (const unsigned __int16 *)v40;
            v13 = DmDeleteTask(
                    L"\\Microsoft\\Windows\\EnterpriseMgmt",
                    (const unsigned __int16 *)v40,
                    L"Retry Schedule created for incomplete session");
            if ( v13 < 0
              || (v13 = ProcessRetriableSessions(v12), v13 < 0)
              || (v13 = OmaDmRegistrySetDWORD(HKEY_LOCAL_MACHINE, v11, L"SessionState", 5u), v13 < 0) )
            {
              NotifySessionResultRecovery(v11, v13);
            }
            else
            {
              v13 = OmaDmCloseSession(v11);
            }
            Header = v13;
            if ( v13 < 0 )
              goto LABEL_47;
            v15 = DeleteRetryCount((const unsigned __int16 *)v40);
          }
          else
          {
            v41 = 0;
            if ( (int)OmaDmRegistryGetDWORD(
                        HKEY_LOCAL_MACHINE,
                        (const unsigned __int16 *)v49[0],
                        L"SessionHRESULT",
                        (unsigned int *)&v41) >= 0 )
            {
              if ( (v16 = (unsigned int)(v41 + 2147012894), (unsigned int)v16 <= 0x1E)
                && (v17 = 1476427821, _bittest(&v17, v16))
                || v41 == -2147012816
                || v41 == -2102657013 )
              {
                v18 = *(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor;
                if ( (*(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor & 4) == 0 )
                {
                  v46 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(
                                     v16,
                                     &v46);
                  v18 = v46;
                }
                v41 = 0;
                v42 = 3;
                wil::details::ReportUsageToService(
                  &qword_1400242D0,
                  57312060,
                  (v18 >> 10) & 1,
                  (v18 >> 11) & 1,
                  &v41,
                  1);
                v51 = &v40;
                v52 = v47;
                p_Header = &Header;
                v54 = 1;
                if ( IsWvdFeatureAllowed((const unsigned __int16 *)v40) )
                {
                  Header = -2147418113;
                  v19 = COmaDmPrcLogger::GetLogger();
                  COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(
                    v19,
                    (const unsigned __int16 *)v40,
                    (const unsigned __int16 *)v49[0],
                    v20,
                    L"HandleMessage",
                    Header);
                  goto LABEL_67;
                }
                Header = DeleteSessionRetryTask((const unsigned __int16 *)v40, (const unsigned __int16 *)v49[0]);
                if ( Header < 0 )
                {
                  v21 = COmaDmPrcLogger::GetLogger();
                  COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(
                    v21,
                    (const unsigned __int16 *)v40,
                    (const unsigned __int16 *)v49[0],
                    v22,
                    L"DeleteSessionRetryTask",
                    Header);
                }
                Header = TriggerSession(
                           0,
                           (const unsigned __int16 *)v40,
                           (unsigned __int16 *)v49[0],
                           0,
                           v47[1],
                           LOBYTE(v47[2]),
                           SBYTE1(v47[2]),
                           *((_DWORD *)a1 + 14),
                           0);
                if ( Header < 0 )
                {
                  v23 = COmaDmPrcLogger::GetLogger();
                  COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(
                    v23,
                    (const unsigned __int16 *)v40,
                    (const unsigned __int16 *)v49[0],
                    v24,
                    L"TriggerSession",
                    Header);
                }
                Header = ModifyRetryCountInValidRange((const unsigned __int16 *)v40, 0, 0);
                if ( Header < 0 )
                {
                  v25 = COmaDmPrcLogger::GetLogger();
                  COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(
                    v25,
                    (const unsigned __int16 *)v40,
                    (const unsigned __int16 *)v49[0],
                    v26,
                    L"ModifyRetryCountInValidRange",
                    Header);
                }
                v27 = COmaDmPrcLogger::GetLogger();
                COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(
                  v27,
                  (const unsigned __int16 *)v40,
                  (const unsigned __int16 *)v49[0],
                  v28,
                  L"HandleMessage",
                  Header);
                goto LABEL_47;
              }
            }
            if ( IsWvdFeatureAllowed((const unsigned __int16 *)v40) && *((_DWORD *)a1 + 14) != 2 && qword_140024308 )
              v15 = ProcessWvdSessions((const unsigned __int16 *)v40, (struct tagTriggerInfo *)v47);
            else
              v15 = TriggerSession(
                      0,
                      (const unsigned __int16 *)v40,
                      (unsigned __int16 *)v49[0],
                      0,
                      v47[1],
                      LOBYTE(v47[2]),
                      SBYTE1(v47[2]),
                      *((_DWORD *)a1 + 14),
                      0);
          }
          Header = v15;
LABEL_47:
          v29 = *(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor;
          if ( (*(_DWORD *)Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor & 4) == 0 )
          {
            v46 = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(
                               v14,
                               &v46);
            v29 = v46;
          }
          v41 = 0;
          v42 = 3;
          wil::details::ReportUsageToService(&qword_1400242D0, 57312060, (v29 >> 10) & 1, (v29 >> 11) & 1, &v41, 1);
          v51 = &v43;
          v52 = v47;
          p_Header = &v40;
          v54 = 1;
          v41 = 0;
          v43 = IsRetriableSession((const unsigned __int16 *)v40, (const unsigned __int16 *)v49[0], v45, &v41, &v44);
          if ( v43 >= 0
            || (v31 = COmaDmPrcLogger::GetLogger(),
                COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(
                  v31,
                  (const unsigned __int16 *)v40,
                  (const unsigned __int16 *)v49[0],
                  L"HandleMessage",
                  L"IsRetriableSession",
                  v43),
                v43 >= 0) )
          {
            if ( v41 )
            {
              v43 = TryScheduleRetryTask(v40, v49[0], v30, (unsigned int)v44);
              if ( v43 < 0 )
              {
                v32 = COmaDmPrcLogger::GetLogger();
                COmaDmPrcLogger::LogOmaDmPrcScheduleRetrySessionResult(
                  v32,
                  (const unsigned __int16 *)v40,
                  (const unsigned __int16 *)v49[0],
                  L"HandleMessage",
                  L"TryScheduleRetryTask",
                  v43);
              }
            }
          }
          wil::details::lambda_call__lambda_418bbcf486875c99c488e744bb27321b___::_lambda_call__lambda_418bbcf486875c99c488e744bb27321b___(&v51);
          v33 = DmDeleteTask(
                  L"\\Microsoft\\Windows\\EnterpriseMgmtNonCritical",
                  (const unsigned __int16 *)v40,
                  L"Queued Schedule created for queued alerts");
          Header = v33;
          if ( v33 == -2147024894 )
          {
            Header = 0;
          }
          else if ( v33 < 0 && (unsigned int)dword_140023000 > 5 )
          {
            v44 = Header;
            v55 = &v44;
            v56 = 4;
            tlgWriteTransfer_EventWriteTransfer(&dword_140023000, word_14001E26A, 0, 0, 3, &v51);
          }
        }
      }
    }
  }
LABEL_67:
  LocalFree(hMem);
  LocalFree(v49[0]);
  LocalFree(v40);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpMem[0]);
  return (unsigned int)Header;
}

```

## disassembly

```asm
0x14000fff0  push    rbp
0x14000fff2  push    rbx
0x14000fff3  push    rsi
0x14000fff4  push    rdi
0x14000fff5  push    r12
0x14000fff7  push    r13
0x14000fff9  push    r14
0x14000fffb  push    r15
0x14000fffd  lea     rbp, [rsp-1Fh]
0x140010002  sub     rsp, 0F8h
0x140010009  mov     rax, cs:__security_cookie
0x140010010  xor     rax, rsp
0x140010013  mov     [rbp+57h+var_48], rax
0x140010017  mov     rdi, rcx
0x14001001a  xor     r12d, r12d
0x14001001d  mov     [rsp+130h+var_E0], r12d
0x140010022  mov     [rbp+57h+var_C8], r12d
0x140010026  mov     [rbp+57h+var_C4], r12d
0x14001002a  mov     [rbp+57h+hMem], r12
0x14001002e  xorps   xmm0, xmm0
0x140010031  movups  xmmword ptr [rbp+57h+var_B0], xmm0
0x140010035  movups  xmmword ptr [rbp+57h+lpMem], xmm0
0x140010039  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x14001003d  mov     [rsp+130h+var_D8], r12
0x140010042  mov     [rbp+57h+var_C0], r12d
0x140010046  lea     r8, [rbp+57h+hMem]
0x14001004a  lea     rdx, ?c_szContentType@@3QBGB; "Content-Type"
0x140010051  mov     rcx, [rcx+8]
0x140010055  call    cs:__imp_?GetHeader@@YAJPEBG0PEAPEAG@Z; GetHeader(ushort const *,ushort const *,ushort * *)
0x14001005c  nop     dword ptr [rax+rax+00h]
0x140010061  mov     [rsp+130h+var_E0], eax
0x140010065  test    eax, eax
0x140010067  js      loc_14001076D
0x14001006d  mov     rdx, [rbp+57h+hMem]
0x140010071  test    rdx, rdx
0x140010074  jz      loc_1400106F9
0x14001007a  lea     r8d, [r12+23h]
0x14001007f  lea     rcx, ?c_szTriggerContentType@@3QBGB; "application/vnd.syncml.notification"
0x140010086  call    cs:__imp_?InvStrCmpNIW@@YAHPEBG0_K@Z; InvStrCmpNIW(ushort const *,ushort const *,unsigned __int64)
0x14001008d  nop     dword ptr [rax+rax+00h]
0x140010092  test    eax, eax
0x140010094  jnz     loc_1400106F9
0x14001009a  lea     rdx, [rbp+57h+var_B0]; struct tagTriggerInfo *
0x14001009e  mov     rcx, rdi; struct tagPushMsgEx *
0x1400100a1  call    ?ParseTriggerMsg@@YAJPEAUtagPushMsgEx@@PEAUtagTriggerInfo@@@Z; ParseTriggerMsg(tagPushMsgEx *,tagTriggerInfo *)
0x1400100a6  mov     [rsp+130h+var_E0], eax
0x1400100aa  cmp     eax, 82AB000Ch
0x1400100af  jnz     short loc_1400100C0
0x1400100b1  lea     r14d, [r12+1]
0x1400100b6  mov     [rsp+130h+var_E0], r14d
0x1400100bb  jmp     loc_14001076D
0x1400100c0  test    eax, eax
0x1400100c2  js      loc_14001076D
0x1400100c8  lea     r8, [rsp+130h+var_D8]
0x1400100cd  mov     edx, dword ptr [rbp+57h+lpMem+8]
0x1400100d0  mov     rcx, [rbp+57h+lpMem]
0x1400100d4  call    cs:__imp_OmaDmGetInternalAcctID
0x1400100db  nop     dword ptr [rax+rax+00h]
0x1400100e0  mov     [rsp+130h+var_E0], eax
0x1400100e4  test    eax, eax
0x1400100e6  js      loc_14001076D
0x1400100ec  mov     rcx, [rsp+130h+var_D8]; unsigned __int16 *
0x1400100f1  call    ?InitializeCVMapForDmSession@@YAJPEBG@Z; InitializeCVMapForDmSession(ushort const *)
0x1400100f6  mov     r13, 0FFFFFFFF80000002h
0x1400100fd  mov     rdx, [rbp+57h+var_90]
0x140010101  test    rdx, rdx
0x140010104  jz      short loc_14001012C
0x140010106  lea     r9, [rbp+57h+var_C0]
0x14001010a  lea     r8, aSessionautodel; "SessionAutoDeleteKey"
0x140010111  mov     rcx, r13
0x140010114  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x14001011b  nop     dword ptr [rax+rax+00h]
0x140010120  mov     [rsp+130h+var_E0], eax
0x140010124  test    eax, eax
0x140010126  js      loc_14001076D
0x14001012c  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140010131  movzx   edx, byte ptr [rbp+57h+var_B0+9]
0x140010135  mov     ecx, [rdi+38h]
0x140010138  mov     [rsp+130h+var_108], ecx; unsigned int
0x14001013c  mov     dword ptr [rsp+130h+var_110], edx; int
0x140010140  mov     r9d, [rbp+57h+var_B0+4]; unsigned int
0x140010144  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x140010148  mov     rdx, [rsp+130h+var_D8]; unsigned __int16 *
0x14001014d  mov     rcx, rax; this
0x140010150  call    ?LogOmaDmPrcHandleMessage@COmaDmPrcLogger@@QEAAXPEBG0KHK@Z; COmaDmPrcLogger::LogOmaDmPrcHandleMessage(ushort const *,ushort const *,ulong,int,ulong)
0x140010155  mov     r15, [rbp+57h+var_90]
0x140010159  mov     rbx, [rsp+130h+var_D8]
0x14001015e  mov     esi, r12d
0x140010161  call    cs:__imp_RtlIsStateSeparationEnabled
0x140010168  nop     dword ptr [rax+rax+00h]
0x14001016d  lea     rcx, aSoftwareMicros_3; "Software\\Microsoft\\Provisioning\\OMAD"...
0x140010174  lea     rdx, aOsdataSoftware_1; "OSData\\Software\\Microsoft\\Provisioni"...
0x14001017b  test    al, al
0x14001017d  cmovz   rdx, rcx
0x140010181  lea     rax, a973cc073B7f44b; "{973CC073-B7F4-4B3B-ABF8-74DF3FCAE76F}"
0x140010188  mov     qword ptr [rsp+130h+var_108], rax
0x14001018d  lea     r8, asc_140019FC8; "\\"
0x140010194  mov     [rsp+130h+var_110], r8
0x140010199  mov     r9, rbx
0x14001019c  mov     ecx, 5
0x1400101a1  call    cs:__imp_?BigStrcat@@YAPEAGIZZ; BigStrcat(uint,...)
0x1400101a8  nop     dword ptr [rax+rax+00h]
0x1400101ad  mov     rbx, rax
0x1400101b0  mov     r14d, 1
0x1400101b6  test    rax, rax
0x1400101b9  jz      short loc_1400101D3
0x1400101bb  mov     rdx, rax
0x1400101be  mov     rcx, r15
0x1400101c1  call    cs:__imp_?InvStrCmpW@@YAHPEBG0@Z; InvStrCmpW(ushort const *,ushort const *)
0x1400101c8  nop     dword ptr [rax+rax+00h]
0x1400101cd  test    eax, eax
0x1400101cf  cmovz   esi, r14d
0x1400101d3  mov     rcx, rbx; hMem
0x1400101d6  call    cs:__imp_LocalFree
0x1400101dd  nop     dword ptr [rax+rax+00h]
0x1400101e2  lea     r15, aHandlemessage; "HandleMessage"
0x1400101e9  test    esi, esi
0x1400101eb  jz      loc_1400102AA
0x1400101f1  mov     rcx, [rsp+130h+var_D8]
0x1400101f6  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x1400101fd  nop     dword ptr [rax+rax+00h]
0x140010202  test    eax, eax
0x140010204  jz      short loc_140010213
0x140010206  mov     [rsp+130h+var_E0], 8000FFFFh
0x14001020e  jmp     loc_14001076D
0x140010213  mov     rdi, [rbp+57h+var_90]
0x140010217  mov     rsi, [rsp+130h+var_D8]
0x14001021c  lea     r8, aRetryScheduleC; "Retry Schedule created for incomplete s"...
0x140010223  mov     rdx, rsi
0x140010226  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x14001022d  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x140010234  nop     dword ptr [rax+rax+00h]
0x140010239  mov     ebx, eax
0x14001023b  test    eax, eax
0x14001023d  js      short loc_140010285
0x14001023f  mov     rcx, rsi; unsigned __int16 *
0x140010242  call    ?ProcessRetriableSessions@@YAJPEBG@Z; ProcessRetriableSessions(ushort const *)
0x140010247  mov     ebx, eax
0x140010249  test    eax, eax
0x14001024b  js      short loc_140010285
0x14001024d  mov     r9d, 5
0x140010253  lea     r8, aSessionstate; "SessionState"
0x14001025a  mov     rdx, rdi
0x14001025d  mov     rcx, r13
0x140010260  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x140010267  nop     dword ptr [rax+rax+00h]
0x14001026c  mov     ebx, eax
0x14001026e  test    eax, eax
0x140010270  js      short loc_140010285
0x140010272  mov     rcx, rdi
0x140010275  call    cs:__imp_OmaDmCloseSession
0x14001027c  nop     dword ptr [rax+rax+00h]
0x140010281  mov     ebx, eax
0x140010283  jmp     short loc_14001028F
0x140010285  mov     edx, ebx
0x140010287  mov     rcx, rdi; lpSubKey
0x14001028a  call    NotifySessionResultRecovery
0x14001028f  mov     [rsp+130h+var_E0], ebx
0x140010293  test    ebx, ebx
0x140010295  js      loc_14001053F
0x14001029b  mov     rcx, [rsp+130h+var_D8]; unsigned __int16 *
0x1400102a0  call    ?DeleteRetryCount@@YAJPEBG@Z; DeleteRetryCount(ushort const *)
0x1400102a5  jmp     loc_14001053B
0x1400102aa  mov     [rbp+57h+var_D0], r12d
0x1400102ae  lea     r9, [rbp+57h+var_D0]
0x1400102b2  lea     r8, aSessionhresult; "SessionHRESULT"
0x1400102b9  mov     rdx, [rbp+57h+var_90]
0x1400102bd  mov     rcx, r13
0x1400102c0  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400102c7  nop     dword ptr [rax+rax+00h]
0x1400102cc  test    eax, eax
0x1400102ce  js      loc_1400104CE
0x1400102d4  mov     eax, [rbp+57h+var_D0]
0x1400102d7  lea     ecx, [rax+7FF8D11Eh]
0x1400102dd  cmp     ecx, 1Eh
0x1400102e0  ja      short loc_1400102EC
0x1400102e2  mov     edx, 5800802Dh
0x1400102e7  bt      edx, ecx
0x1400102ea  jb      short loc_1400102FE
0x1400102ec  cmp     eax, 80072F30h
0x1400102f1  jz      short loc_1400102FE
0x1400102f3  cmp     eax, 82AC000Bh
0x1400102f8  jnz     loc_1400104CE
0x1400102fe  mov     rax, cs:Feature_OmaDmClient_BackOff_Retry_ScheduledTask__descriptor
0x140010305  mov     r8d, [rax]
0x140010308  test    r8b, 4
0x14001030c  jnz     short loc_140010321
0x14001030e  lea     rdx, [rbp+57h+var_B8]
0x140010312  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OmaDmClient_BackOff_Retry_ScheduledTask>::GetCachedFeatureEnabledState(void)
0x140010317  mov     rcx, [rax]
0x14001031a  mov     [rbp+57h+var_B8], rcx
0x14001031e  mov     r8d, ecx
0x140010321  mov     [rbp+57h+var_D0], r12d
0x140010325  mov     [rbp+57h+var_CC], 3
0x14001032b  mov     r9d, r8d
0x14001032e  shr     r9d, 0Bh
0x140010332  and     r9d, r14d
0x140010335  shr     r8d, 0Ah
0x140010339  and     r8d, r14d
0x14001033c  mov     [rsp+130h+var_108], r14d
0x140010341  lea     rax, [rbp+57h+var_D0]
0x140010345  mov     [rsp+130h+var_110], rax
0x14001034a  mov     edx, 36A833Ch
0x14001034f  lea     rcx, qword_1400242D0
0x140010356  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x14001035b  lea     rax, [rsp+130h+var_D8]
0x140010360  mov     [rbp+57h+var_78], rax
0x140010364  lea     rax, [rbp+57h+var_B0]
0x140010368  mov     [rbp+57h+var_70], rax
0x14001036c  lea     rax, [rsp+130h+var_E0]
0x140010371  mov     [rbp+57h+var_68], rax
0x140010375  mov     [rbp+57h+var_60], r14b
0x140010379  mov     rcx, [rsp+130h+var_D8]
0x14001037e  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x140010385  nop     dword ptr [rax+rax+00h]
0x14001038a  test    eax, eax
0x14001038c  jz      short loc_1400103BF
0x14001038e  mov     [rsp+130h+var_E0], 8000FFFFh
0x140010396  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x14001039b  mov     ecx, [rsp+130h+var_E0]
0x14001039f  mov     [rsp+130h+var_108], ecx; int
0x1400103a3  mov     [rsp+130h+var_110], r15; unsigned __int16 *
0x1400103a8  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x1400103ac  mov     rdx, [rsp+130h+var_D8]; unsigned __int16 *
0x1400103b1  mov     rcx, rax; this
0x1400103b4  call    ?LogOmaDmPrcProcessRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z; COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x1400103b9  nop
0x1400103ba  jmp     loc_14001076D
0x1400103bf  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x1400103c3  mov     rcx, [rsp+130h+var_D8]; unsigned __int16 *
0x1400103c8  call    ?DeleteSessionRetryTask@@YAJPEBG0@Z; DeleteSessionRetryTask(ushort const *,ushort const *)
0x1400103cd  mov     [rsp+130h+var_E0], eax
0x1400103d1  test    eax, eax
0x1400103d3  jns     short loc_1400103FF
0x1400103d5  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x1400103da  mov     ecx, [rsp+130h+var_E0]
0x1400103de  mov     [rsp+130h+var_108], ecx; int
0x1400103e2  lea     rcx, aDeletesessionr; "DeleteSessionRetryTask"
0x1400103e9  mov     [rsp+130h+var_110], rcx; unsigned __int16 *
0x1400103ee  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x1400103f2  mov     rdx, [rsp+130h+var_D8]; unsigned __int16 *
0x1400103f7  mov     rcx, rax; this
0x1400103fa  call    ?LogOmaDmPrcProcessRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z; COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x1400103ff  movzx   ecx, byte ptr [rbp+57h+var_B0+8]
0x140010403  mov     [rsp+130h+var_F0], r12
0x140010408  mov     eax, [rdi+38h]
0x14001040b  mov     [rsp+130h+var_F8], eax
0x14001040f  mov     al, byte ptr [rbp+57h+var_B0+9]
0x140010412  mov     [rsp+130h+var_100], al
0x140010416  mov     [rsp+130h+var_108], ecx
0x14001041a  mov     eax, [rbp+57h+var_B0+4]
0x14001041d  mov     dword ptr [rsp+130h+var_110], eax
0x140010421  xor     r9d, r9d
0x140010424  mov     r8, [rbp+57h+var_90]
0x140010428  mov     rdx, [rsp+130h+var_D8]
0x14001042d  xor     ecx, ecx
0x14001042f  call    ?TriggerSession@@YAJPEBG000KW4OMADM_UIMODE@@EW4PushRouterSubmitOrigin@@PEAJ@Z; TriggerSession(ushort const *,ushort const *,ushort const *,ushort const *,ulong,OMADM_UIMODE,uchar,PushRouterSubmitOrigin,long *)
0x140010434  mov     [rsp+130h+var_E0], eax
0x140010438  test    eax, eax
0x14001043a  jns     short loc_140010466
0x14001043c  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140010441  mov     ecx, [rsp+130h+var_E0]
0x140010445  mov     [rsp+130h+var_108], ecx; int
0x140010449  lea     rcx, aTriggersession; "TriggerSession"
0x140010450  mov     [rsp+130h+var_110], rcx; unsigned __int16 *
0x140010455  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x140010459  mov     rdx, [rsp+130h+var_D8]; unsigned __int16 *
0x14001045e  mov     rcx, rax; this
0x140010461  call    ?LogOmaDmPrcProcessRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z; COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x140010466  xor     r8d, r8d; unsigned int *
0x140010469  xor     edx, edx; int
0x14001046b  mov     rcx, [rsp+130h+var_D8]; unsigned __int16 *
0x140010470  call    ?ModifyRetryCountInValidRange@@YAJPEBGHPEAK@Z; ModifyRetryCountInValidRange(ushort const *,int,ulong *)
0x140010475  mov     [rsp+130h+var_E0], eax
0x140010479  test    eax, eax
0x14001047b  jns     short loc_1400104A8
0x14001047d  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140010482  mov     ecx, [rsp+130h+var_E0]
0x140010486  mov     [rsp+130h+var_108], ecx; int
0x14001048a  lea     rcx, aModifyretrycou; "ModifyRetryCountInValidRange"
0x140010491  mov     [rsp+130h+var_110], rcx; unsigned __int16 *
0x140010496  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x14001049a  mov     rdx, [rsp+130h+var_D8]; unsigned __int16 *
0x14001049f  mov     rcx, rax; this
0x1400104a2  call    ?LogOmaDmPrcProcessRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z; COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x1400104a7  nop
0x1400104a8  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x1400104ad  mov     ecx, [rsp+130h+var_E0]
0x1400104b1  mov     [rsp+130h+var_108], ecx; int
0x1400104b5  mov     [rsp+130h+var_110], r15; unsigned __int16 *
0x1400104ba  mov     r8, [rbp+57h+var_90]; unsigned __int16 *
0x1400104be  mov     rdx, [rsp+130h+var_D8]; unsigned __int16 *
0x1400104c3  mov     rcx, rax; this
0x1400104c6  call    ?LogOmaDmPrcProcessRetrySessionResult@COmaDmPrcLogger@@QEAAXPEBG000J@Z; COmaDmPrcLogger::LogOmaDmPrcProcessRetrySessionResult(ushort const *,ushort const *,ushort const *,ushort const *,long)
0x1400104cb  nop
0x1400104cc  jmp     short loc_14001053F
0x1400104ce  mov     rcx, [rsp+130h+var_D8]
0x1400104d3  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x1400104da  nop     dword ptr [rax+rax+00h]
0x1400104df  test    eax, eax
  ... truncated ...
```
