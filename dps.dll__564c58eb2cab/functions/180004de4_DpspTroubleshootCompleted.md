# DpspTroubleshootCompleted

- ea: `0x180004de4`
- end: `0x1800054e7`
- name: `DpspTroubleshootCompleted`
- size: `1795`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *, struct _DPS_MESSAGE *, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800104f4`

## callees

- `0x180001010`
- `0x180001100`
- `0x1800013a0`
- `0x1800013d0`
- `0x180001458`
- `0x180002090`
- `0x180002dc0`
- `0x180002f10`
- `0x180003020`
- `0x180004de4`
- `0x1800062a8`
- `0x1800067b8`
- `0x180006ae8`
- `0x180007694`
- `0x180007a64`
- `0x180007adc`
- `0x1800086d0`
- `0x180009090`
- `0x18000a856`
- `0x18000b2d0`
- `0x18000b3ec`
- `0x18000b668`
- `0x18000b6d8`
- `0x18000b7ec`
- `0x180018b3d`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005357`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f6e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005100`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005170`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005207`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f6e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005100`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005170`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005207`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005115`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800051a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005220`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004fb1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005115`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800051a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005220`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180004f0e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004eb7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180004eb7`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005292`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180005292`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800052e5`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800052e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004fe2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800054cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004fe2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800054cb`

## string_xrefs

- `0x180004e6c`: `DpspTroubleshootCompleted`
- `0x18000507e`: `DpspTroubleshootCompleted`
- `0x1800053b1`: `DpspTroubleshootCompleted`
- `0x180005419`: `DpspTroubleshootCompleted`

## pseudocode

```c
__int64 __fastcall DpspTroubleshootCompleted(struct INSTANCEINFO *a1, struct _DPS_MESSAGE *a2, __int64 a3)
{
  int v3; // r15d
  unsigned int v4; // esi
  int v8; // r8d
  int v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int Args; // eax
  struct _DPS_MESSAGE *v13; // rdx
  struct INSTANCEINFO *v14; // rcx
  int updated; // eax
  int v16; // edx
  int v17; // eax
  int v18; // eax
  struct __SESSIONINFO *SessionFromId; // r15
  __int64 v21; // rax
  unsigned int v22; // ebx
  unsigned int v23; // r15d
  PSID v24; // rax
  int v25; // ebx
  int v26; // eax
  int QueueSID; // eax
  unsigned int v28; // esi
  int v29; // r8d
  size_t LengthSid; // rbx
  void *v31; // rax
  int ResolutionSession; // eax
  signed int LastError; // eax
  int v34; // eax
  int v35; // r8d
  __int64 v36; // rsi
  int v37; // eax
  int v38; // r8d
  int CurrentSessionPosition; // eax
  __int64 v40; // rax
  __int64 v41; // rsi
  unsigned int v42[2]; // [rsp+30h] [rbp-50h] BYREF
  __int128 v43; // [rsp+40h] [rbp-40h] BYREF
  struct INSTANCEINFO *v44[2]; // [rsp+50h] [rbp-30h] BYREF
  _QWORD *v45[2]; // [rsp+60h] [rbp-20h] BYREF
  _QWORD *v46[2]; // [rsp+70h] [rbp-10h] BYREF
  int v47; // [rsp+C0h] [rbp+40h]

  v42[0] = 0;
  v44[1] = (struct INSTANCEINFO *)v44;
  v3 = 0;
  v44[0] = (struct INSTANCEINFO *)v44;
  v46[1] = v46;
  v46[0] = v46;
  v45[1] = v45;
  v45[0] = v45;
  v4 = 4;
  v47 = 4;
  if ( !a1 )
  {
    v8 = 2231;
LABEL_3:
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (int)L"DpspTroubleshootCompleted",
      v8,
      (int)L"Error = %d",
      87);
    goto LABEL_27;
  }
  if ( !a2 )
  {
    v8 = 2232;
    goto LABEL_3;
  }
  if ( (*((_BYTE *)a2 + 120) & 8) != 0 )
    _InterlockedOr((volatile signed __int32 *)a1 + 26, 0x80u);
  v10 = *((_QWORD *)a1 + 101);
  if ( !v10 )
  {
    v8 = 2242;
    goto LABEL_3;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v10 + 64));
  DpspDeleteSecurityAttributes(*(_QWORD *)(*((_QWORD *)a1 + 101) + 168LL), (RTL_SRWLOCK *)a1);
  --*(_DWORD *)(*((_QWORD *)a1 + 101) + 28LL);
  DpspGetDMDispatchInstanceList(*((_QWORD *)a1 + 101), (__int64)v44);
  DpspDispatchInstanceList(v44, (__int64)v46, (__int64)v45);
  v11 = *((_QWORD *)a1 + 101);
  if ( v11 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v11 + 64));
  Args = DpspUpdateFeedback(a1, a2);
  v9 = Args;
  if ( Args >= 0 )
  {
    if ( *((int *)a2 + 28) < 0 )
    {
      _InterlockedOr((volatile signed __int32 *)a1 + 26, 8u);
      goto LABEL_27;
    }
    updated = DpspUpdateParameterCollection(v14, v13, a3);
    v9 = updated;
    if ( updated < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspTroubleshootCompleted",
        2295,
        (int)L"Error = %d",
        updated);
      goto LABEL_27;
    }
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 2);
    v16 = *((_DWORD *)a1 + 55);
    v17 = *((_DWORD *)a1 + 53) - v16;
    *((_DWORD *)a1 + 52) = v16;
    *((_DWORD *)a1 + 54) = v16;
    *((_DWORD *)a1 + 55) = v16 + (int)((double)(25 * v17) * 0.01);
    ReleaseSRWLockExclusive((PSRWLOCK)a1 + 2);
    if ( !memcmp_0((char *)a2 + 128, qword_18001A6E0, 0x10u) )
    {
      CurrentSessionPosition = DpspGetCurrentSessionPosition(a1, v42);
      v9 = CurrentSessionPosition;
      if ( CurrentSessionPosition < 0 )
      {
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
          (int)L"DpspTroubleshootCompleted",
          2391,
          (int)L"Error = %d",
          CurrentSessionPosition);
        goto LABEL_27;
      }
      v40 = *((_QWORD *)a1 + 152);
      v41 = v42[0] + 1;
      if ( (unsigned int)v41 >= *(_DWORD *)(v40 + 24) )
      {
        GetSystemTimeAsFileTime((LPFILETIME)a1 + 21);
        v4 = 0;
        DpspRaiseScenarioDispatchEvent(
          (__int64)a1,
          (const EVENT_DESCRIPTOR *)WDI_DPS_EVENT_TROUBLESHOOT_END_NO_RESOLUTION);
        goto LABEL_27;
      }
      v37 = DpspAddDMToTraversedList(a1, *(_QWORD *)(v40 + 8 * v41 + 96));
      v9 = v37;
      if ( v37 >= 0 )
      {
        v3 = 1;
        *((_QWORD *)a1 + 101) = *(_QWORD *)(*((_QWORD *)a1 + 152) + 8 * v41 + 96);
        v37 = DpspAttemptScenarioCompletionEx(a1);
        v9 = v37;
        if ( v37 >= 0 )
          goto LABEL_80;
        v38 = 2411;
      }
      else
      {
        v38 = 2402;
      }
      goto LABEL_79;
    }
    GetSystemTimeAsFileTime((LPFILETIME)a1 + 21);
    if ( (unsigned int)DpspGetScenarioExecutionLevel(*((_QWORD *)a1 + 152)) < 2 )
    {
      v4 = 6;
      v9 = -2147020579;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspTroubleshootCompleted",
        2321,
        (int)L"Error = %d",
        221);
      goto LABEL_27;
    }
    *((_QWORD *)a1 + 22) = *((_QWORD *)a1 + 21);
    v18 = DpspUpdateResolutionContext(a1, a2);
    v9 = v18;
    if ( v18 < 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspTroubleshootCompleted",
        2333,
        (int)L"Error = %d",
        v18);
      goto LABEL_27;
    }
    v43 = *(_OWORD *)((char *)a1 + 40);
    SessionFromId = DpspGetSessionFromId(&v43);
    if ( !SessionFromId )
    {
      v9 = -2147467259;
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
        (int)L"DpspTroubleshootCompleted",
        2342,
        (int)L"Error = %d",
        5);
LABEL_26:
      v3 = 0;
      goto LABEL_27;
    }
    v21 = *((_QWORD *)a1 + 101);
    v42[0] = *((_DWORD *)a1 + 23) & 0xF;
    v22 = v42[0];
    *(_QWORD *)&v43 = v21;
    AcquireSRWLockExclusive((PSRWLOCK)a1 + 2);
    *((_DWORD *)a1 + 55) = *((_DWORD *)a1 + 53);
    ReleaseSRWLockExclusive((PSRWLOCK)a1 + 2);
    if ( v22 )
    {
      if ( v22 != 1 )
      {
        if ( v22 == 2 )
        {
          if ( *((_DWORD *)a1 + 22) == 1 )
          {
            v25 = 0;
            AcquireSRWLockExclusive((PSRWLOCK)a1 + 2);
            v26 = *((_DWORD *)a1 + 53);
            *((_DWORD *)a1 + 52) = v26;
            *((_DWORD *)a1 + 54) = v26;
            memset_0((char *)a1 + 224, 0, 0x208u);
            *((_DWORD *)a1 + 186) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)a1 + 2);
            v4 = 1;
          }
          else
          {
            v25 = 1;
            *((_QWORD *)a1 + 96) = *((_QWORD *)a1 + 97);
          }
          v47 = v4;
          if ( v25 != 1 )
          {
            v23 = 0;
            v9 = 0;
            goto LABEL_66;
          }
          v22 = v42[0];
        }
        else
        {
          if ( v22 == 4 )
          {
            v24 = g_pAdminSid;
          }
          else
          {
            if ( v22 != 8 )
            {
              v9 = 0;
              v23 = 0;
LABEL_66:
              DpspRaiseTroubleshootSucceededEvent(a1, v43, v23, v4);
              if ( !v23 )
                goto LABEL_26;
              *(_QWORD *)v42 = 0;
              ResolutionSession = DpspGetResolutionSession((__int64)a1, (struct __SESSIONINFO **)v42);
              v9 = ResolutionSession;
              if ( ResolutionSession < 0 )
              {
                WdipTraceError(
                  (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
                  (int)L"DpspTroubleshootCompleted",
                  2370,
                  (int)L"Error = %d",
                  ResolutionSession);
                goto LABEL_26;
              }
              v36 = *(_QWORD *)v42;
              v34 = DpspAddDMToTraversedList(a1, *(_QWORD *)v42);
              v9 = v34;
              if ( v34 < 0 )
              {
                v35 = 2374;
                goto LABEL_74;
              }
              *((_QWORD *)a1 + 101) = v36;
              v3 = 1;
              v37 = DpspAttemptScenarioCompletionEx(a1);
              v9 = v37;
              if ( v37 >= 0 )
              {
LABEL_80:
                v4 = v47;
                goto LABEL_27;
              }
              v38 = 2382;
LABEL_79:
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
                (int)L"DpspTroubleshootCompleted",
                v38,
                (int)L"Error = %d",
                v37);
              goto LABEL_80;
            }
            v24 = g_pEveryoneSid;
          }
          *((_QWORD *)a1 + 96) = v24;
        }
      }
      QueueSID = DpspTransferInstanceOwnership(a1);
      v28 = QueueSID;
      if ( QueueSID < 0 )
      {
        v9 = QueueSID;
        v29 = 850;
        goto LABEL_73;
      }
      if ( (*((_BYTE *)a1 + 92) & 0x10) != 0 || ((v22 - 4) & 0xFFFFFFFB) == 0 )
      {
        *((_QWORD *)a1 + 101) = SessionFromId;
        QueueSID = DpspCreateQueueSID(a1);
        LOBYTE(v28) = QueueSID;
        if ( QueueSID >= 0 )
        {
          QueueSID = DpspQueueInstanceToUsers(*((PSID *)a1 + 95), a1);
          LOBYTE(v28) = QueueSID;
          v9 = QueueSID;
          if ( QueueSID >= 0 )
          {
            v23 = 0;
            v47 = 3;
            v4 = 3;
            goto LABEL_66;
          }
          v29 = 898;
        }
        else
        {
          v9 = QueueSID;
          v29 = 893;
        }
LABEL_73:
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
          (int)L"DpspValidateResolutionContext",
          v29,
          (int)L"Error = %d",
          QueueSID);
        LOBYTE(v34) = v28;
        v35 = 2358;
LABEL_74:
        WdipTraceError(
          (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
          (int)L"DpspTroubleshootCompleted",
          v35,
          (int)L"Error = %d",
          v34);
        v4 = v47;
        goto LABEL_26;
      }
      AcquireSRWLockExclusive((PSRWLOCK)a1 + 2);
      DpspSendClientFeedback((__int64)a1, 3, v28);
      ReleaseSRWLockExclusive((PSRWLOCK)a1 + 2);
      _InterlockedOr((volatile signed __int32 *)a1 + 26, 4u);
    }
    else
    {
      LengthSid = GetLengthSid(*(PSID *)(*((_QWORD *)SessionFromId + 22) + 32LL));
      v31 = (void *)WdipAlloc(LengthSid);
      *((_QWORD *)a1 + 96) = v31;
      if ( !v31 )
      {
        v9 = -2147024882;
        LOBYTE(QueueSID) = 14;
        LOBYTE(v28) = 14;
        v29 = 772;
        goto LABEL_73;
      }
      memset_0(v31, 0, LengthSid);
      if ( CopySid(LengthSid, *((PSID *)a1 + 96), *(PSID *)(*((_QWORD *)SessionFromId + 22) + 32LL)) )
      {
        v28 = 0;
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        v28 = v9;
        if ( v9 < 0 )
        {
          v29 = 779;
          LOBYTE(QueueSID) = v9;
          goto LABEL_73;
        }
      }
      *((_DWORD *)a1 + 27) = *(_DWORD *)(*((_QWORD *)SessionFromId + 22) + 40LL);
    }
    v9 = v28;
    v23 = 1;
    v4 = v47;
    goto LABEL_66;
  }
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
    (int)L"DpspTroubleshootCompleted",
    2278,
    (int)L"Error = %d",
    Args);
LABEL_27:
  DpspCloseInstanceList(v46, v45);
  if ( a1 && a2 && !v3 )
  {
    if ( v9 >= 0 )
      v9 = *((_DWORD *)a2 + 28);
    DpspCloseInstance((__int64)a1, v4, 15, v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180004de4  mov     [rsp-38h+arg_8], rbx
0x180004de9  push    rbp
0x180004dea  push    rsi
0x180004deb  push    rdi
0x180004dec  push    r12
0x180004dee  push    r13
0x180004df0  push    r14
0x180004df2  push    r15
0x180004df4  mov     rbp, rsp
0x180004df7  sub     rsp, 80h
0x180004dfe  lea     rax, [rbp+var_30]
0x180004e02  mov     [rbp+var_50], 0
0x180004e09  mov     [rbp+var_28], rax
0x180004e0d  xor     r15d, r15d
0x180004e10  mov     [rbp+arg_18], r15d
0x180004e14  lea     rax, [rbp+var_30]
0x180004e18  mov     [rbp+var_30], rax
0x180004e1c  lea     rax, [rbp+var_10]
0x180004e20  mov     [rbp+var_8], rax
0x180004e24  lea     rax, [rbp+var_10]
0x180004e28  mov     [rbp+var_10], rax
0x180004e2c  lea     rax, [rbp+var_20]
0x180004e30  mov     [rbp+var_18], rax
0x180004e34  lea     rax, [rbp+var_20]
0x180004e38  mov     [rbp+var_20], rax
0x180004e3c  mov     esi, 4
0x180004e41  mov     [rbp+arg_0], esi
0x180004e44  mov     r14, r8
0x180004e47  mov     r13, rdx
0x180004e4a  mov     rdi, rcx
0x180004e4d  test    rcx, rcx
0x180004e50  jnz     short loc_180004E84
0x180004e52  mov     r8d, 8B7h; int
0x180004e58  mov     ebx, 80070057h
0x180004e5d  mov     dword ptr [rsp+80h+Args], 57h ; 'W'; Args
0x180004e65  lea     r9, aErrorD; "Error = %d"
0x180004e6c  lea     rdx, aDpsptroublesho; "DpspTroubleshootCompleted"
0x180004e73  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180004e7a  call    WdipTraceError
0x180004e7f  jmp     loc_180005095
0x180004e84  test    r13, r13
0x180004e87  jnz     short loc_180004E91
0x180004e89  mov     r8d, 8B8h
0x180004e8f  jmp     short loc_180004E58
0x180004e91  test    byte ptr [rdx+78h], 8
0x180004e95  jz      short loc_180004E9F
0x180004e97  lock or dword ptr [rcx+68h], 80h
0x180004e9f  mov     rcx, [rcx+328h]
0x180004ea6  test    rcx, rcx
0x180004ea9  jnz     short loc_180004EB3
0x180004eab  mov     r8d, 8C2h
0x180004eb1  jmp     short loc_180004E58
0x180004eb3  add     rcx, 40h ; '@'; lpCriticalSection
0x180004eb7  call    cs:__imp_EnterCriticalSection
0x180004ebd  mov     rcx, [rdi+328h]
0x180004ec4  mov     rdx, rdi
0x180004ec7  mov     rcx, [rcx+0A8h]
0x180004ece  call    DpspDeleteSecurityAttributes
0x180004ed3  mov     rax, [rdi+328h]
0x180004eda  lea     rdx, [rbp+var_30]
0x180004ede  dec     dword ptr [rax+1Ch]
0x180004ee1  mov     rcx, [rdi+328h]
0x180004ee8  call    DpspGetDMDispatchInstanceList
0x180004eed  lea     r8, [rbp+var_20]
0x180004ef1  lea     rdx, [rbp+var_10]
0x180004ef5  lea     rcx, [rbp+var_30]
0x180004ef9  call    DpspDispatchInstanceList
0x180004efe  mov     rcx, [rdi+328h]
0x180004f05  test    rcx, rcx
0x180004f08  jz      short loc_180004F14
0x180004f0a  add     rcx, 40h ; '@'; lpCriticalSection
0x180004f0e  call    cs:__imp_LeaveCriticalSection
0x180004f14  mov     rdx, r13
0x180004f17  mov     rcx, rdi
0x180004f1a  call    DpspUpdateFeedback
0x180004f1f  mov     ebx, eax
0x180004f21  test    eax, eax
0x180004f23  jns     short loc_180004F37
0x180004f25  movzx   ecx, ax
0x180004f28  mov     r8d, 8E6h
0x180004f2e  mov     dword ptr [rsp+80h+Args], ecx
0x180004f32  jmp     loc_180004E65
0x180004f37  cmp     [r13+70h], r15d
0x180004f3b  jge     short loc_180004F47
0x180004f3d  lock or dword ptr [rdi+68h], 8
0x180004f42  jmp     loc_180005095
0x180004f47  mov     r8, r14; unsigned __int64
0x180004f4a  call    ?DpspUpdateParameterCollection@@YAJPEAUINSTANCEINFO@@PEAU_DPS_MESSAGE@@_K@Z; DpspUpdateParameterCollection(INSTANCEINFO *,_DPS_MESSAGE *,unsigned __int64)
0x180004f4f  mov     ebx, eax
0x180004f51  test    eax, eax
0x180004f53  jns     short loc_180004F67
0x180004f55  movzx   eax, ax
0x180004f58  mov     r8d, 8F7h
0x180004f5e  mov     dword ptr [rsp+80h+Args], eax
0x180004f62  jmp     loc_180004E65
0x180004f67  lea     r12, [rdi+10h]
0x180004f6b  mov     rcx, r12; SRWLock
0x180004f6e  call    cs:__imp_AcquireSRWLockExclusive
0x180004f74  mov     edx, [rdi+0DCh]
0x180004f7a  xorps   xmm0, xmm0
0x180004f7d  mov     eax, [rdi+0D4h]
0x180004f83  sub     eax, edx
0x180004f85  mov     [rdi+0D0h], edx
0x180004f8b  imul    ecx, eax, 19h
0x180004f8e  mov     [rdi+0D8h], edx
0x180004f94  cvtsi2sd xmm0, rcx
0x180004f99  mov     rcx, r12; SRWLock
0x180004f9c  mulsd   xmm0, cs:__real@3f847ae147ae147b
0x180004fa4  cvttsd2si rax, xmm0
0x180004fa9  add     eax, edx
0x180004fab  mov     [rdi+0DCh], eax
0x180004fb1  call    cs:__imp_ReleaseSRWLockExclusive
0x180004fb7  lea     rcx, [r13+80h]; Buf1
0x180004fbe  mov     r8d, 10h; Size
0x180004fc4  lea     rdx, qword_18001A6E0; Buf2
0x180004fcb  call    memcmp_0
0x180004fd0  test    eax, eax
0x180004fd2  jz      loc_180005438
0x180004fd8  lea     rbx, [rdi+0A8h]
0x180004fdf  mov     rcx, rbx; lpSystemTimeAsFileTime
0x180004fe2  call    cs:__imp_GetSystemTimeAsFileTime
0x180004fe8  mov     rcx, [rdi+4C0h]
0x180004fef  call    DpspGetScenarioExecutionLevel
0x180004ff4  cmp     eax, 2
0x180004ff7  jnb     short loc_180005016
0x180004ff9  mov     esi, 6
0x180004ffe  mov     dword ptr [rsp+80h+Args], 10DDh
0x180005006  mov     ebx, 800710DDh
0x18000500b  mov     r8d, 911h
0x180005011  jmp     loc_180004E65
0x180005016  mov     rax, [rbx]
0x180005019  mov     r8, r14; unsigned __int64
0x18000501c  mov     rdx, r13; struct _DPS_MESSAGE *
0x18000501f  mov     [rdi+0B0h], rax
0x180005026  mov     rcx, rdi; struct INSTANCEINFO *
0x180005029  call    ?DpspUpdateResolutionContext@@YAJPEAUINSTANCEINFO@@PEAU_DPS_MESSAGE@@_K@Z; DpspUpdateResolutionContext(INSTANCEINFO *,_DPS_MESSAGE *,unsigned __int64)
0x18000502e  mov     ebx, eax
0x180005030  test    eax, eax
0x180005032  jns     short loc_180005046
0x180005034  movzx   eax, ax
0x180005037  mov     r8d, 91Dh
0x18000503d  mov     dword ptr [rsp+80h+Args], eax
0x180005041  jmp     loc_180004E65
0x180005046  movups  xmm0, xmmword ptr [rdi+28h]
0x18000504a  lea     rcx, [rbp+var_40]
0x18000504e  movdqu  [rbp+var_40], xmm0
0x180005053  call    DpspGetSessionFromId
0x180005058  mov     r15, rax
0x18000505b  test    rax, rax
0x18000505e  jnz     loc_1800050E9
0x180005064  mov     ebx, 80004005h
0x180005069  mov     dword ptr [rsp+80h+Args], 4005h; Args
0x180005071  mov     r8d, 926h; int
0x180005077  lea     r9, aErrorD; "Error = %d"
0x18000507e  lea     rdx, aDpsptroublesho; "DpspTroubleshootCompleted"
0x180005085  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000508c  call    WdipTraceError
0x180005091  mov     r15d, [rbp+arg_18]
0x180005095  lea     rdx, [rbp+var_20]
0x180005099  lea     rcx, [rbp+var_10]
0x18000509d  call    DpspCloseInstanceList
0x1800050a2  test    rdi, rdi
0x1800050a5  jz      short loc_1800050CC
0x1800050a7  test    r13, r13
0x1800050aa  jz      short loc_1800050CC
0x1800050ac  test    r15d, r15d
0x1800050af  jnz     short loc_1800050CC
0x1800050b1  test    ebx, ebx
0x1800050b3  js      short loc_1800050B9
0x1800050b5  mov     ebx, [r13+70h]
0x1800050b9  mov     r9d, ebx
0x1800050bc  mov     r8d, 0Fh
0x1800050c2  mov     edx, esi
0x1800050c4  mov     rcx, rdi
0x1800050c7  call    DpspCloseInstance
0x1800050cc  mov     eax, ebx
0x1800050ce  mov     rbx, [rsp+80h+arg_8]
0x1800050d6  add     rsp, 80h
0x1800050dd  pop     r15
0x1800050df  pop     r14
0x1800050e1  pop     r13
0x1800050e3  pop     r12
0x1800050e5  pop     rdi
0x1800050e6  pop     rsi
0x1800050e7  pop     rbp
0x1800050e8  retn
0x1800050e9  mov     ebx, [rdi+5Ch]
0x1800050ec  mov     rcx, r12; SRWLock
0x1800050ef  mov     rax, [rdi+328h]
0x1800050f6  and     ebx, 0Fh
0x1800050f9  mov     [rbp+var_50], ebx
0x1800050fc  mov     qword ptr [rbp+var_40], rax
0x180005100  call    cs:__imp_AcquireSRWLockExclusive
0x180005106  mov     eax, [rdi+0D4h]
0x18000510c  mov     rcx, r12; SRWLock
0x18000510f  mov     [rdi+0DCh], eax
0x180005115  call    cs:__imp_ReleaseSRWLockExclusive
0x18000511b  mov     eax, ebx
0x18000511d  test    ebx, ebx
0x18000511f  jz      loc_180005287
0x180005125  mov     r14d, 1
0x18000512b  sub     eax, r14d
0x18000512e  jz      loc_1800051D6
0x180005134  sub     eax, r14d
0x180005137  jz      short loc_180005165
0x180005139  sub     eax, 2
0x18000513c  jz      short loc_18000515C
0x18000513e  cmp     eax, esi
0x180005140  jz      short loc_18000514C
0x180005142  xor     ebx, ebx
0x180005144  xor     r15d, r15d
0x180005147  jmp     loc_18000530C
0x18000514c  mov     rax, cs:g_pEveryoneSid
0x180005153  mov     [rdi+300h], rax
0x18000515a  jmp     short loc_1800051D6
0x18000515c  mov     rax, cs:g_pAdminSid
0x180005163  jmp     short loc_180005153
0x180005165  cmp     [rdi+58h], r14d
0x180005169  jnz     short loc_1800051B0
0x18000516b  mov     rcx, r12; SRWLock
0x18000516e  xor     ebx, ebx
0x180005170  call    cs:__imp_AcquireSRWLockExclusive
0x180005176  mov     eax, [rdi+0D4h]
0x18000517c  lea     rcx, [rdi+0E0h]; void *
0x180005183  xor     edx, edx; Val
0x180005185  mov     [rdi+0D0h], eax
0x18000518b  mov     r8d, 208h; Size
0x180005191  mov     [rdi+0D8h], eax
0x180005197  call    memset_0
0x18000519c  mov     rcx, r12; SRWLock
0x18000519f  mov     [rdi+2E8h], ebx
0x1800051a5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800051ab  mov     esi, r14d
0x1800051ae  jmp     short loc_1800051C1
0x1800051b0  mov     rax, [rdi+308h]
0x1800051b7  mov     ebx, r14d
0x1800051ba  mov     [rdi+300h], rax
0x1800051c1  mov     [rbp+arg_0], esi
0x1800051c4  cmp     ebx, r14d
0x1800051c7  jz      short loc_1800051D3
0x1800051c9  xor     r15d, r15d
0x1800051cc  xor     ebx, ebx
0x1800051ce  jmp     loc_18000530C
0x1800051d3  mov     ebx, [rbp+var_50]
0x1800051d6  mov     rcx, rdi; struct INSTANCEINFO *
0x1800051d9  call    ?DpspTransferInstanceOwnership@@YAJPEAUINSTANCEINFO@@@Z; DpspTransferInstanceOwnership(INSTANCEINFO *)
0x1800051de  mov     esi, eax
0x1800051e0  test    eax, eax
0x1800051e2  jns     short loc_1800051F4
0x1800051e4  mov     ebx, eax
0x1800051e6  mov     r8d, 352h
0x1800051ec  movzx   eax, si
0x1800051ef  jmp     loc_18000537F
0x1800051f4  test    byte ptr [rdi+5Ch], 10h
0x1800051f8  jnz     short loc_180005230
0x1800051fa  lea     eax, [rbx-4]
0x1800051fd  test    eax, 0FFFFFFFBh
0x180005202  jz      short loc_180005230
0x180005204  mov     rcx, r12; SRWLock
0x180005207  call    cs:__imp_AcquireSRWLockExclusive
0x18000520d  mov     r8d, esi
0x180005210  mov     edx, 3
0x180005215  mov     rcx, rdi
0x180005218  call    DpspSendClientFeedback
0x18000521d  mov     rcx, r12; SRWLock
0x180005220  call    cs:__imp_ReleaseSRWLockExclusive
0x180005226  lock or dword ptr [rdi+68h], 4
0x18000522b  jmp     loc_180005304
0x180005230  mov     rcx, rdi; struct INSTANCEINFO *
0x180005233  mov     [rdi+328h], r15
0x18000523a  call    ?DpspCreateQueueSID@@YAJPEAUINSTANCEINFO@@@Z; DpspCreateQueueSID(INSTANCEINFO *)
0x18000523f  mov     esi, eax
0x180005241  test    eax, eax
0x180005243  jns     short loc_180005255
0x180005245  mov     ebx, eax
0x180005247  mov     r8d, 37Dh
0x18000524d  movzx   eax, ax
0x180005250  jmp     loc_18000537F
0x180005255  mov     rcx, [rdi+2F8h]; pSid1
0x18000525c  mov     rdx, rdi; struct INSTANCEINFO *
0x18000525f  call    DpspQueueInstanceToUsers
0x180005264  mov     esi, eax
0x180005266  mov     ebx, eax
0x180005268  test    eax, eax
0x18000526a  jns     short loc_180005274
0x18000526c  mov     r8d, 382h
0x180005272  jmp     short loc_18000524D
0x180005274  xor     r15d, r15d
0x180005277  mov     [rbp+arg_0], 3
0x18000527e  lea     esi, [r15+3]
0x180005282  jmp     loc_18000530C
0x180005287  mov     rcx, [r15+0B0h]
0x18000528e  mov     rcx, [rcx+20h]; pSid
0x180005292  call    cs:__imp_GetLengthSid
0x180005298  mov     ecx, eax
0x18000529a  mov     ebx, eax
0x18000529c  call    WdipAlloc
0x1800052a1  mov     [rdi+300h], rax
0x1800052a8  test    rax, rax
0x1800052ab  jnz     short loc_1800052C4
  ... truncated ...
```
