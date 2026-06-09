# NtSetSystemInformation

- ea: `0x1409f5d70`
- end: `0x1409f7d67`
- name: `NtSetSystemInformation`
- size: `8183`
- prototype: ``
- caller_count: `1`
- callee_count: `105`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140c81d38`

## callees

- `0x140223ba0`
- `0x1402247c0`
- `0x140224f70`
- `0x1402268e0`
- `0x14023e7c0`
- `0x14029a100`
- `0x14029e8c0`
- `0x1402a1f50`
- `0x1402f3cb0`
- `0x1402f5b00`
- `0x1402f8270`
- `0x1402fac70`
- `0x140309b40`
- `0x14033da00`
- `0x140408610`
- `0x14041e430`
- `0x140421c50`
- `0x14045c620`
- `0x140474758`
- `0x1404b3ee0`
- `0x140519a14`
- `0x140519f7c`
- `0x1405304b0`
- `0x1405c7e0c`
- `0x1405caae0`
- `0x1405cb914`
- `0x1405e33bc`
- `0x1405e3fa0`
- `0x1405f0adc`
- `0x1405f0d2c`
- `0x1405f3a24`
- `0x14060e9a8`
- `0x14060ed74`
- `0x140638fd4`
- `0x140639044`
- `0x14063918c`
- `0x140639244`
- `0x140680d94`
- `0x140680ed0`
- `0x1406d9d70`
- `0x1406dca30`
- `0x1406de010`
- `0x1406de3b0`
- `0x1406e8590`
- `0x1406ea430`
- `0x1406f4750`
- `0x1406f4880`
- `0x140720384`
- `0x140720e18`
- `0x140720e5c`

## import_xrefs

- `kdcom!KdInitialize` at `0x1409f75ed`
- `kdcom!KdInitialize` at `0x1409f75ed`

## string_xrefs

- `0x1409f6234`: `\SystemRoot\System32\win32k.sys`
- `0x1409f628c`: `\SystemRoot\System32\win32k.sys`
- `0x1409f6ee3`: `\Registry\Machine\System\CurrentControlSet\Services\condrv`

## pseudocode

```c
__int64 __fastcall NtSetSystemInformation(int a1, __int128 *p_Buf1, unsigned int a3)
{
  SIZE_T v3; // r13
  PVOID v6; // rdi
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  KPROCESSOR_MODE PreviousMode; // r15
  ULONG v11; // r8d
  char v12; // r12
  __int64 v13; // rdx
  unsigned int updated; // ebx
  int v15; // r9d
  ULONG ActiveProcessorCount; // eax
  __int64 v17; // rdx
  unsigned int v18; // ecx
  ULONG v19; // eax
  char UCharFromUser; // al
  __int64 ULong64FromUser; // rax
  char v22; // al
  unsigned int v23; // eax
  int v24; // esi
  int v25; // esi
  int v26; // esi
  int v27; // esi
  void *v28; // rax
  __int64 result; // rax
  __int64 v30; // rax
  __int64 v31; // rdx
  int v33; // ecx
  int v34; // ecx
  __int64 v35; // rcx
  __int64 v36; // rcx
  unsigned int ULongFromUser; // eax
  __int64 v38; // rcx
  void *v39; // rax
  int v40; // esi
  unsigned int v41; // eax
  unsigned int v42; // esi
  char v43; // si
  int SystemImage; // eax
  __int64 v45; // rdx
  __int64 v46; // r15
  __int64 v47; // rax
  __int64 v48; // r8
  __int64 v49; // rcx
  __int64 v50; // rcx
  int v51; // ebx
  int v52; // r9d
  __int64 v53; // r13
  __int64 v54; // rdx
  __int64 v55; // rdx
  PVOID v56; // rsi
  void *v57; // rcx
  int v58; // esi
  int v59; // esi
  int v60; // esi
  int v61; // esi
  _KPROCESS *Process; // rcx
  __int16 v63; // ax
  int v64; // ebx
  int v65; // esi
  int v66; // esi
  int v67; // esi
  int v68; // esi
  char *v69; // rcx
  int v70; // esi
  int v71; // esi
  int v72; // esi
  unsigned int v73; // ecx
  int v74; // esi
  int v75; // esi
  int v76; // esi
  int v77; // esi
  int v78; // eax
  __int64 v79; // rax
  void *v80; // rdx
  AutoBoost *v81; // rbx
  __int64 ThreadPartition; // rax
  __int64 v84; // rcx
  __int64 v85; // rax
  void *v86; // rcx
  int v87; // esi
  int v88; // esi
  int v89; // esi
  int v90; // esi
  int v91; // r13d
  unsigned int v92; // eax
  char v93; // bl
  void *Pool2; // rax
  void *v95; // rbx
  __int64 v96; // rdx
  __int64 v97; // rcx
  __int64 CurrentServerSiloGlobals; // r8
  unsigned int v99; // r13d
  __int64 v100; // rsi
  void *v101; // rdx
  __int64 v102; // rcx
  __int64 v103; // rcx
  int v104; // r8d
  unsigned int v105; // r13d
  int v106; // r9d
  void *v107; // rax
  __int64 v108; // rdx
  LUID v109; // rdi
  _KPROCESS *v110; // rdi
  __int64 v111; // rcx
  int v112; // esi
  int v113; // esi
  int v114; // esi
  int v115; // esi
  ULONG v116; // ecx
  unsigned int v117; // r13d
  unsigned __int64 v118; // rsi
  void *v119; // rdx
  __int64 v120; // rcx
  int v121; // esi
  __int64 v122; // rcx
  int v123; // eax
  int v124; // eax
  KPROCESSOR_MODE v125; // [rsp+30h] [rbp-3D8h] BYREF
  bool v126; // [rsp+31h] [rbp-3D7h] BYREF
  char v127[6]; // [rsp+32h] [rbp-3D6h] BYREF
  PVOID Object; // [rsp+38h] [rbp-3D0h] BYREF
  char v129; // [rsp+40h] [rbp-3C8h]
  ULONG v130; // [rsp+44h] [rbp-3C4h]
  unsigned int v131; // [rsp+48h] [rbp-3C0h] BYREF
  __int64 v132; // [rsp+50h] [rbp-3B8h] BYREF
  __int128 v133; // [rsp+60h] [rbp-3A8h] BYREF
  ULONG v134; // [rsp+70h] [rbp-398h]
  unsigned __int64 v135[20]; // [rsp+78h] [rbp-390h] BYREF
  _QWORD Src[2]; // [rsp+118h] [rbp-2F0h] BYREF
  __int64 v137; // [rsp+128h] [rbp-2E0h] BYREF
  UNICODE_STRING DriverServiceName; // [rsp+130h] [rbp-2D8h] BYREF
  unsigned int v139; // [rsp+140h] [rbp-2C8h]
  int v140; // [rsp+144h] [rbp-2C4h]
  int v141; // [rsp+148h] [rbp-2C0h]
  unsigned int v142; // [rsp+14Ch] [rbp-2BCh]
  unsigned int v143; // [rsp+150h] [rbp-2B8h]
  __int64 v144; // [rsp+158h] [rbp-2B0h]
  int v145; // [rsp+160h] [rbp-2A8h]
  __int128 v146; // [rsp+168h] [rbp-2A0h] BYREF
  _KPROCESS *v147; // [rsp+178h] [rbp-290h]
  __int64 v148; // [rsp+188h] [rbp-280h]
  __int64 v149; // [rsp+190h] [rbp-278h]
  __int64 v150; // [rsp+198h] [rbp-270h]
  __int64 v151; // [rsp+1A0h] [rbp-268h]
  void *v152; // [rsp+1A8h] [rbp-260h]
  __int128 Buf1; // [rsp+1B0h] [rbp-258h] BYREF
  void *v154[2]; // [rsp+1C0h] [rbp-248h] BYREF
  __int128 v155; // [rsp+1D0h] [rbp-238h]
  __int128 v156; // [rsp+1E0h] [rbp-228h]
  __int64 v157; // [rsp+1F0h] [rbp-218h]
  LUID PrivilegeValue[2]; // [rsp+3B0h] [rbp-58h] BYREF

  v3 = a3;
  v6 = 0;
  v126 = 0;
  v133 = 0;
  v132 = 0;
  Src[0] = 0;
  v137 = 0;
  Object = 0;
  memset_0(&Buf1, 0, 0x200u);
  PreviousMode = KeGetCurrentThread()->PreviousMode;
  if ( PreviousMode )
  {
    if ( a1 == 89 )
    {
      v11 = 2;
      v12 = 1;
LABEL_9:
      ProbeForRead(p_Buf1, v3, v11);
      v13 = 2;
      goto LABEL_11;
    }
    if ( a1 == 151 )
    {
      v12 = 1;
      if ( (_DWORD)v3 == 1 )
      {
        v11 = 1;
        goto LABEL_9;
      }
    }
    else
    {
      v12 = 1;
    }
    v11 = 4;
    goto LABEL_9;
  }
  v13 = 2;
  v12 = 1;
LABEL_11:
  v125 = PreviousMode;
  updated = 0;
  if ( a1 <= 126 )
  {
    if ( a1 == 126 )
    {
      if ( PreviousMode )
        return 3221225569LL;
      if ( (_DWORD)v3 == 32 )
        return (unsigned int)BgkSetBootGraphicsInformation(v7, p_Buf1);
      return (unsigned int)-1073741820;
    }
    if ( a1 <= 72 )
    {
      if ( a1 != 72 )
      {
        if ( a1 <= 39 )
        {
          if ( a1 == 39 )
          {
            if ( (_DWORD)v3 == 4 )
            {
              if ( SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
              {
                if ( PreviousMode )
                  ULongFromUser = RtlReadULongFromUser(p_Buf1);
                else
                  ULongFromUser = *(_DWORD *)p_Buf1;
                v142 = ULongFromUser;
                LOBYTE(v36) = 1;
                PsChangeQuantumTable(v36, ULongFromUser);
                return 0;
              }
              return 3221225569LL;
            }
            return 3221225476LL;
          }
          if ( a1 <= 28 )
          {
            if ( a1 == 28 )
            {
              if ( (((_DWORD)v3 - 8) & 0xFFFFFFF7) != 0 )
                return 3221225476LL;
              if ( PreviousMode && !SeSinglePrivilegeCheck(SeSystemtimePrivilege, PreviousMode) )
                return 3221225569LL;
              if ( !(unsigned __int8)PsIsCurrentThreadInServerSilo(v7, v13) )
              {
                v135[0] = 0;
                if ( (_DWORD)v3 == 16 )
                {
                  if ( PreviousMode )
                    UCharFromUser = RtlReadUCharFromUser((char *)p_Buf1 + 8);
                  else
                    UCharFromUser = *((_BYTE *)p_Buf1 + 8);
                  v126 = UCharFromUser;
                  if ( PreviousMode )
                    ULong64FromUser = RtlReadULong64FromUser(p_Buf1);
                  else
                    ULong64FromUser = *(_QWORD *)p_Buf1;
                  v135[0] = ULong64FromUser;
                }
                else
                {
                  if ( PreviousMode )
                    v22 = RtlReadUCharFromUser((char *)p_Buf1 + 4);
                  else
                    v22 = *((_BYTE *)p_Buf1 + 4);
                  v126 = v22;
                  if ( PreviousMode )
                    v23 = RtlReadULongFromUser(p_Buf1);
                  else
                    v23 = *(_DWORD *)p_Buf1;
                  v135[0] = v23;
                  if ( v23 )
                    v135[0] = MEMORY[0xFFFFF78000000300] * (unsigned __int64)(unsigned int)KeMaximumIncrement / v23;
                }
                if ( v126 )
                  v135[0] = MEMORY[0xFFFFF78000000300];
                ExAcquireTimeRefreshLockExclusive(0xFFFFF78000000300uLL);
                updated = ExpUpdateTimerConfiguration(0, v135, &v126);
                ExReleaseTimeRefreshLockExclusive();
                return updated;
              }
              return 3221225506LL;
            }
            v15 = 1;
            if ( a1 != 9 )
            {
              if ( a1 != 21 )
              {
                if ( a1 == 24 )
                {
                  if ( (_DWORD)v3 == 20 )
                  {
                    if ( !PreviousMode || SeSinglePrivilegeCheck(SeLoadDriverPrivilege, PreviousMode) )
                    {
                      if ( PreviousMode )
                        RtlCopyFromUser(&Buf1, p_Buf1, 0x14u);
                      else
                        RtlCopyVolatileMemory(&Buf1, p_Buf1, 0x14u);
                      KiMinimumDpcRate = DWORD2(Buf1);
                      KiMaximumDpcQueueDepth = DWORD1(Buf1);
                      KiAdjustDpcThreshold = HIDWORD(Buf1);
                      KiIdealDpcRate = (int)v154[0];
                      KeSynchronizeWithDynamicProcessors();
                      ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
                      if ( ActiveProcessorCount )
                      {
                        do
                        {
                          v17 = *((_QWORD *)&KiProcessorBlock + (unsigned int)v6);
                          *(_DWORD *)(v17 + 3304) = KiMaximumDpcQueueDepth;
                          *(_DWORD *)(v17 + 3312) = KiMinimumDpcRate;
                          LODWORD(v6) = (_DWORD)v6 + 1;
                        }
                        while ( (unsigned int)v6 < ActiveProcessorCount );
                      }
                      return updated;
                    }
                    return 3221225569LL;
                  }
                  return 3221225476LL;
                }
                if ( a1 != 26 )
                {
                  if ( a1 == 27 )
                  {
                    if ( (_DWORD)v3 == 8 )
                    {
                      if ( !PreviousMode )
                      {
                        MmUnloadSystemImage(*(_QWORD *)p_Buf1);
                        return 0;
                      }
                      return 3221225569LL;
                    }
                    return 3221225476LL;
                  }
                  return (unsigned int)-1073741821;
                }
LABEL_160:
                if ( (_DWORD)v3 == 48 )
                {
                  v43 = 0;
                }
                else
                {
                  if ( (_DWORD)v3 != 56 )
                    return 3221225476LL;
                  v43 = 1;
                }
                if ( !PreviousMode )
                {
                  v133 = *p_Buf1;
                  SystemImage = MmLoadSystemImage((unsigned int)&v133, 0, 0, v15, (__int64)&v137, (__int64)&v132);
                  updated = SystemImage;
                  if ( SystemImage < 0 )
                  {
                    if ( SystemImage == -1073741411 )
                      return (unsigned int)-1073741554;
                  }
                  else
                  {
                    if ( v43 )
                    {
                      LOBYTE(v45) = 1;
                      v46 = RtlImageDirectoryEntryToData(v132, v45, 0, &Object);
                    }
                    else
                    {
                      v46 = 0;
                    }
                    v47 = RtlImageNtHeader(v132);
                    v48 = v132 + *(unsigned int *)(v47 + 40);
                    *((_QWORD *)p_Buf1 + 2) = v132;
                    *((_QWORD *)p_Buf1 + 3) = v137;
                    *((_QWORD *)p_Buf1 + 4) = v48;
                    if ( v43 )
                    {
                      *((_QWORD *)p_Buf1 + 5) = v46;
                      *((_DWORD *)p_Buf1 + 12) = *(_DWORD *)(v47 + 80);
                    }
                    else
                    {
                      *((_DWORD *)p_Buf1 + 10) = *(_DWORD *)(v47 + 80);
                    }
                  }
                  return updated;
                }
                return 3221225569LL;
              }
LABEL_198:
              v127[0] = 0;
              if ( (unsigned int)v3 < 0x40 )
                return 3221225476LL;
              if ( a1 == 21 )
              {
                v51 = 0;
              }
              else
              {
                if ( PreviousMode )
                  v51 = RtlReadULongFromUser((char *)p_Buf1 + 60);
                else
                  v51 = *((_DWORD *)p_Buf1 + 15);
                v145 = v51;
                if ( (v51 & 0xFFFFFFF0) != 0 || (v51 & 0xC) == 0xC || (v51 & 3) == 3 )
                  return 3221225712LL;
              }
              if ( SeSinglePrivilegeCheck(SeIncreaseQuotaPrivilege, PreviousMode) )
              {
                if ( PreviousMode )
                  v53 = RtlReadULong64FromUser((char *)p_Buf1 + 24);
                else
                  v53 = *((_QWORD *)p_Buf1 + 3);
                v148 = v53;
                if ( PreviousMode )
                  v54 = RtlReadULong64FromUser(p_Buf1 + 2);
                else
                  v54 = *((_QWORD *)p_Buf1 + 4);
                v149 = v54;
                LOBYTE(v52) = 1;
                return MmAdjustWorkingSetSizeEx(v53, v54, 1, v52, v51, (__int64)v127);
              }
              return 3221225506LL;
            }
            if ( (_DWORD)v3 != 4 )
              return 3221225476LL;
            if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
              return 3221225506LL;
            v130 = 0;
            if ( PreviousMode )
              v18 = RtlReadULongFromUser(p_Buf1);
            else
              v18 = *(_DWORD *)p_Buf1;
            v19 = v18 & 0x92319BF0 | NtGlobalFlag & 0x6DCE640F;
            v130 = v19;
            NtGlobalFlag = v19;
            if ( !PreviousMode )
            {
              *(_DWORD *)p_Buf1 = v19;
              return updated;
            }
LABEL_42:
            RtlWriteULongToUser(p_Buf1, v19);
            return updated;
          }
          v24 = a1 - 30;
          if ( !v24 )
            return (unsigned int)MmCreateMirror();
          v25 = v24 - 1;
          if ( !v25 )
            return (unsigned int)EtwSetPerformanceTraceInformation(p_Buf1, (unsigned int)v3, PreviousMode);
          v26 = v25 - 3;
          if ( v26 )
          {
            v27 = v26 - 3;
            if ( v27 )
            {
              if ( v27 != 1 )
                return (unsigned int)-1073741821;
              if ( (_DWORD)v3 != 16 )
                return 3221225476LL;
              if ( PreviousMode )
              {
                if ( (HIDWORD(KeGetCurrentThread()->ApcState.Process[4].IdealProcessorAssignmentBlock) & 8) != 0 )
                {
                  if ( SeSinglePrivilegeCheck(SeLoadDriverPrivilege, 1) )
                  {
                    *(_OWORD *)&PrivilegeValue[0].LowPart = 0;
                    PrivilegeValue[0].LowPart = RtlReadULongFromUser(p_Buf1);
                    v28 = (void *)RtlReadULong64FromUser((char *)p_Buf1 + 8);
                    PrivilegeValue[1] = (LUID)v28;
                    v133 = *(_OWORD *)&PrivilegeValue[0].LowPart;
                    if ( LOWORD(PrivilegeValue[0].LowPart) == 62 )
                    {
                      RtlCopyFromUser(&Buf1, v28, 0x3Eu);
                      if ( !memcmp(&Buf1, L"\\SystemRoot\\System32\\win32k.sys", 0x3Eu) )
                      {
                        *((_QWORD *)&v133 + 1) = L"\\SystemRoot\\System32\\win32k.sys";
                        WORD1(v133) = 62;
                        return ZwSetSystemInformation(38, &v133, 16);
                      }
                    }
                  }
                }
                return 3221225569LL;
              }
              v133 = *p_Buf1;
              if ( !memcmp(*((const void **)p_Buf1 + 1), L"\\SystemRoot\\System32\\win32k.sys", 0x3Eu) )
              {
                v132 = *(_QWORD *)(*(_QWORD *)&PsAltSystemCallRegistrationLock.SchedulerApcFill5[80] + 48LL);
                v30 = RtlImageNtHeader(v132);
                if ( !v30 )
                {
                  MmUnloadSystemImage(*(ULONG_PTR *)&PsAltSystemCallRegistrationLock.SchedulerApcFill5[80]);
                  return 3221225595LL;
                }
                updated = ExpInitializeSessionDriver(v132 + *(unsigned int *)(v30 + 40));
                if ( (updated & 0x80000000) != 0
                  && !(unsigned int)PsGetSessionIdEx(KeGetCurrentThread()->ApcState.Process, v31) )
                {
                  MmUnloadSystemImage(*(ULONG_PTR *)&PsAltSystemCallRegistrationLock.SchedulerApcFill5[80]);
                }
                return updated;
              }
              return 3221225659LL;
            }
            if ( (_DWORD)v3 != 16 )
              return 3221225476LL;
            if ( PreviousMode && !SeSinglePrivilegeCheck(SeIncreaseQuotaPrivilege, PreviousMode) )
              return 3221225569LL;
            return (unsigned int)CmSetRegistryQuotaInformation(p_Buf1, v13);
          }
          if ( PreviousMode && !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode)
            || (unsigned __int8)PsIsCurrentThreadInServerSilo(v7, v13) )
          {
            return 3221225569LL;
          }
          if ( (_DWORD)v3 == 4 )
          {
            if ( PreviousMode )
            {
              if ( ((unsigned __int8)p_Buf1 & 3) != 0 )
                ExRaiseDatatypeMisalignment();
              v33 = RtlReadULongFromUser(p_Buf1);
            }
            else
            {
              v33 = *(_DWORD *)p_Buf1;
            }
            v141 = v33;
            if ( !v33 )
            {
              v35 = 0;
              return (unsigned int)IoConfigureCrashDump(v35);
            }
            v34 = v33 - 1;
            if ( v34 )
            {
              if ( v34 == 1 )
                return (unsigned int)WheaCrashDumpInitializationComplete();
              return 3221225485LL;
            }
          }
          v35 = 1;
          return (unsigned int)IoConfigureCrashDump(v35);
        }
        if ( a1 <= 51 )
        {
          if ( a1 == 51 )
          {
            if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
              return 3221225506LL;
            return (unsigned int)VfSetVerifierInformation(p_Buf1, (unsigned int)v3, 0);
          }
          if ( a1 != 40 && a1 != 41 )
          {
            v38 = (unsigned int)(a1 - 46);
            if ( a1 == 46 )
            {
              if ( (_DWORD)v3 != 8 )
                return 3221225476LL;
              if ( PreviousMode && !SeSinglePrivilegeCheck(SeSystemtimePrivilege, PreviousMode) )
                return 3221225569LL;
              if ( !(unsigned __int8)PsIsCurrentThreadInServerSilo(v38, v13) )
              {
                if ( PreviousMode )
                  v39 = (void *)RtlReadULong64FromUser(p_Buf1);
                else
                  v39 = *(void **)p_Buf1;
                v144 = (__int64)v39;
                if ( v39 )
                {
                  Object = 0;
                  updated = ObReferenceObjectByHandle(
                              v39,
                              2u,
                              (POBJECT_TYPE)ExEventObjectType,
                              PreviousMode,
                              &Object,
                              0);
                  if ( (updated & 0x80000000) != 0 )
                    return updated;
                  v6 = Object;
                }
                else
                {
                  updated = 0;
                }
                KdUpdateTimeSlipEvent(v6);
                return updated;
              }
              return 3221225506LL;
            }
            if ( (unsigned int)(a1 - 47) > 1 )
              return (unsigned int)-1073741821;
            return 3221225474LL;
          }
          if ( (_DWORD)v3 != 16 )
            return 3221225476LL;
          if ( !PreviousMode )
            goto LABEL_139;
          if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
            return 3221225569LL;
          result = VfProbeAndCaptureUnicodeString(&v133, p_Buf1, 1);
          if ( (int)result < 0 )
            return result;
          if ( (_WORD)v133 )
          {
            p_Buf1 = &v133;
LABEL_139:
            v40 = a1 - 40;
            if ( !v40 )
            {
              v41 = VfAddVerifierEntry((PCUNICODE_STRING)p_Buf1);
              goto LABEL_522;
            }
            if ( v40 == 1 )
            {
              v41 = VfRemoveVerifierEntry(p_Buf1, v13);
LABEL_522:
              updated = v41;
              goto LABEL_523;
            }
LABEL_519:
            updated = -1073741821;
LABEL_523:
            if ( !PreviousMode )
              return updated;
            v69 = (char *)p_Buf1;
            goto LABEL_525;
          }
          return 3221225711LL;
        }
        switch ( a1 )
        {
          case '6':
            v15 = 0;
            goto LABEL_160;
          case '8':
            LOBYTE(v9) = PreviousMode;
            return (unsigned int)PfSnSetPrefetcherInformation(v7, p_Buf1, (unsigned int)v3, v9);
          case ';':
            if ( (_DWORD)v3 == 4 )
            {
              if ( PreviousMode )
                v42 = RtlReadULongFromUser(p_Buf1);
              else
                v42 = *(_DWORD *)p_Buf1;
              v143 = v42;
              updated = ExpUpdateComPlusPackage(v42);
              if ( (updated & 0x80000000) == 0 )
                *(_DWORD *)(MmWriteableSharedUserData + 736) = v42;
              return updated;
            }
            return 3221225476LL;
        }
        if ( a1 != 69 )
        {
          if ( a1 != 71 )
            return (unsigned int)-1073741821;
          return 3221225659LL;
        }
        return (unsigned int)-1073741637;
      }
      if ( PreviousMode || !p_Buf1 || (_DWORD)v3 != 8 )
        return 3221225485LL;
      if ( !*(_DWORD *)p_Buf1 )
        return (unsigned int)-1073741637;
      v49 = (unsigned int)(*(_DWORD *)p_Buf1 - 1);
      if ( *(_DWORD *)p_Buf1 == 1
        || (v49 = (unsigned int)(*(_DWORD *)p_Buf1 - 2), *(_DWORD *)p_Buf1 == 2)
        || (v49 = (unsigned int)(*(_DWORD *)p_Buf1 - 3), *(_DWORD *)p_Buf1 == 3) )
      {
        guard_dispatch_icall_no_overrides(v49, 2, v8);
        return 0;
      }
      if ( *(_DWORD *)p_Buf1 == 4 )
        return (unsigned int)-1073741637;
      v50 = (unsigned int)(*(_DWORD *)p_Buf1 - 6);
      if ( *(_DWORD *)p_Buf1 == 6 )
      {
        LODWORD(v50) = 1;
        return (unsigned int)guard_dispatch_icall_no_overrides(v50, 2, v8);
      }
      if ( *(_DWORD *)p_Buf1 == 7 )
      {
        updated = 0;
        if ( off_140E00A68[0] == xKdEnumerateDebuggingDevices )
          return (unsigned int)-1073741822;
        return updated;
      }
      return (unsigned int)-1073741811;
    }
    if ( a1 > 93 )
    {
      if ( a1 > 106 )
      {
        v70 = a1 - 109;
        if ( v70 )
        {
          v71 = v70 - 1;
          if ( !v71 )
            return (unsigned int)-1073741822;
          v72 = v71 - 1;
          if ( !v72 )
          {
            if ( (_DWORD)v3 != 4 )
              return 3221225476LL;
            if ( SeSinglePrivilegeCheck(SeProfileSingleProcessPrivilege, PreviousMode) )
            {
              if ( PreviousMode )
                v73 = RtlReadULongFromUser(p_Buf1);
              else
                v73 = *(_DWORD *)p_Buf1;
              *(_DWORD *)(MmWriteableSharedUserData + 584) = v73;
              return 0;
            }
            return 3221225506LL;
          }
          if ( v72 != 2 )
            return (unsigned int)-1073741821;
          return (unsigned int)PsSetCpuQuotaInformation(p_Buf1, (unsigned int)v3, PreviousMode);
        }
        else
        {
          LOBYTE(v9) = PreviousMode;
          return (unsigned int)SmSetStoreInformation(v7, p_Buf1, (unsigned int)v3, v9);
        }
      }
      if ( a1 == 106 )
        return (unsigned int)-1073741821;
      v65 = a1 - 94;
      if ( !v65 )
      {
        if ( SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
        {
          if ( (_DWORD)v3 == 8 )
          {
            if ( PreviousMode )
              *(_QWORD *)&Buf1 = RtlReadULong64FromUser(p_Buf1);
            else
              RtlCopyVolatileMemory(&Buf1, p_Buf1, 8u);
            _InterlockedOr((volatile signed __int32 *)(MmWriteableSharedUserData + 928), Buf1);
            _InterlockedAnd((volatile signed __int32 *)(MmWriteableSharedUserData + 928), ~DWORD1(Buf1));
            return updated;
          }
          return (unsigned int)-1073741820;
        }
        return (unsigned int)-1073741790;
      }
      v66 = v65 - 1;
      if ( !v66 )
        return 3221225659LL;
      v67 = v66 - 2;
      if ( !v67 )
      {
        if ( (_DWORD)v3 != 40 )
          return 3221225476LL;
        if ( PreviousMode )
        {
          if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
            return 3221225569LL;
          RtlCopyFromUser(&Buf1, p_Buf1, 0x28u);
          result = VfProbeAndCaptureUnicodeStringBuffer((char *)&Buf1 + 8, 1);
          if ( (int)result < 0 )
            return result;
          updated = VfProbeAndCaptureUnicodeStringBuffer(&v154[1], 1);
          if ( (updated & 0x80000000) != 0 )
          {
            v69 = (char *)&Buf1 + 8;
            goto LABEL_525;
          }
          p_Buf1 = &Buf1;
        }
        updated = VfFaultsSetParameters(p_Buf1, v13);
        if ( !PreviousMode )
          return updated;
        VfFreeCapturedUnicodeString((char *)p_Buf1 + 8);
        v69 = (char *)p_Buf1 + 24;
LABEL_525:
        VfFreeCapturedUnicodeString(v69);
        return updated;
      }
      v68 = v67 - 5;
      if ( v68 )
      {
        if ( v68 != 2 )
          return (unsigned int)-1073741821;
        LOBYTE(v8) = PreviousMode;
        return (unsigned int)ExpSetProcessorMicrocodeUpdateInformation(p_Buf1, (unsigned int)v3, v8);
      }
      v64 = 432;
    }
    else
    {
      if ( a1 != 93 )
      {
        if ( a1 <= 82 )
        {
          if ( a1 != 82 )
          {
            switch ( a1 )
            {
              case 'J':
                return 3221225474LL;
              case 'K':
                LOBYTE(v8) = PreviousMode;
                return (unsigned int)ExpRegisterFirmwareTableInformationHandler(p_Buf1, (unsigned int)v3, v8);
              case 'O':
                LOBYTE(v9) = PreviousMode;
                return (unsigned int)PfSetSuperfetchInformation(79, p_Buf1, (unsigned int)v3, v9);
            }
            if ( a1 != 80 )
            {
              if ( a1 != 81 )
                return (unsigned int)-1073741821;
              goto LABEL_198;
            }
            if ( (unsigned int)v3 >= 4 )
            {
              v131 = 6;
              if ( PreviousMode )
                RtlCopyFromUser(&v131, p_Buf1, 4u);
              else
                RtlCopyVolatileMemory(&v131, p_Buf1, 4u);
              LOBYTE(v55) = PreviousMode;
              return (unsigned int)MmIssueMemoryListCommand(v131, v55, -1);
            }
            return (unsigned int)-1073741820;
          }
          if ( (unsigned int)v3 < 0x18 )
            return 3221225476LL;
          if ( !SeSinglePrivilegeCheck(SeIncreaseBasePriorityPrivilege, PreviousMode) )
            return 3221225569LL;
          if ( PreviousMode )
          {
            RtlCopyFromUser(&Buf1, p_Buf1, 0x18u);
            p_Buf1 = &Buf1;
          }
          if ( (unsigned int)(*((_DWORD *)p_Buf1 + 4) - 1) > 0x1E )
            return 3221225485LL;
          *(_OWORD *)&PrivilegeValue[0].LowPart = *p_Buf1;
          updated = PsLookupProcessThreadByCid(PrivilegeValue, 0, &Object);
          if ( (updated & 0x80000000) != 0 )
            return updated;
          v56 = Object;
          if ( (unsigned __int8)*((_DWORD *)Object + 1) )
          {
            updated = -1073741749;
          }
          else
          {
            KeSetActualBasePriorityThread((ULONG_PTR)Object);
            updated = 259;
          }
          v57 = v56;
LABEL_234:
          ObfDereferenceObject(v57);
          return updated;
        }
        v58 = a1 - 86;
        if ( !v58 )
          return (unsigned int)ObSetRefTraceInformation(p_Buf1);
        v59 = v58 - 1;
        if ( v59 )
        {
          v60 = v59 - 2;
          if ( v60 )
          {
            v61 = v60 - 2;
            if ( v61 )
            {
              if ( v61 != 1 )
                return (unsigned int)-1073741821;
              if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
                return 3221225506LL;
              if ( (_DWORD)v3 != 40 )
                return 3221225476LL;
              return (unsigned int)VfSetVerifierInformationEx(p_Buf1);
            }
            if ( !PreviousMode )
            {
              if ( (_DWORD)v3 )
                return (unsigned int)-1073741584;
              else
                return HvlHypervisorConnected == 0 ? 0xC0351000 : 0;
            }
            return (unsigned int)-1073741790;
          }
          if ( PreviousMode != 1 )
            return (unsigned int)-1073741637;
          if ( SeSinglePrivilegeCheck(SeTcbPrivilege, 1) )
          {
            Process = KeGetCurrentThread()->ApcState.Process;
            if ( !Process[1].ReadyTime )
              return (unsigned int)DbgkRegisterErrorPort(p_Buf1, (unsigned int)v3);
            v63 = WORD2(Process[3].PerProcessorCycleTimes);
            if ( v63 != 332 && v63 != 452 )
              v12 = 0;
            if ( !v12 )
              return (unsigned int)DbgkRegisterErrorPort(p_Buf1, (unsigned int)v3);
            return (unsigned int)-1073741637;
          }
          return (unsigned int)-1073741727;
        }
        if ( SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
        {
          if ( (_DWORD)v3 == 8 )
          {
            if ( PreviousMode )
              *(_QWORD *)&Buf1 = RtlReadULong64FromUser(p_Buf1);
            else
              RtlCopyVolatileMemory(&Buf1, p_Buf1, 8u);
            MmSpecialPoolTag = Buf1;
            MmSpecialPoolCatchOverruns = BYTE4(Buf1) & 1;
            return updated;
          }
          return (unsigned int)-1073741820;
        }
        return (unsigned int)-1073741790;
      }
      v64 = 172;
    }
    if ( (_DWORD)v3 != v64 )
      return 3221225476LL;
    if ( PreviousMode && !SeSinglePrivilegeCheck(SeTimeZonePrivilege, PreviousMode) )
      return 3221225569LL;
    return (unsigned int)ExpSetTimeZoneInformation(p_Buf1);
  }
  if ( a1 <= 199 )
  {
    if ( a1 != 199 )
    {
      if ( a1 <= 159 )
      {
        if ( a1 == 159 )
          return (unsigned int)-1073741637;
        if ( a1 <= 134 )
        {
          if ( a1 == 134 )
          {
            if ( (_DWORD)v3 != 32 )
              return 3221225476LL;
            return (unsigned int)sub_140A5295C(v7, p_Buf1);
          }
          else
          {
            v74 = a1 - 127;
            if ( !v74 )
            {
              if ( (_DWORD)v3 == 16 )
              {
                if ( SeSinglePrivilegeCheck(SeProfileSingleProcessPrivilege, PreviousMode) )
                {
                  if ( PreviousMode )
                    v85 = RtlReadULong64FromUser(p_Buf1);
                  else
                    v85 = *(_QWORD *)p_Buf1;
                  v144 = v85;
                  updated = MmScrubMemory(v84, v85, Src);
                  LODWORD(Object) = updated;
                  v86 = (char *)p_Buf1 + 8;
                  if ( PreviousMode )
                    RtlWriteULong64ToUser(v86, Src[0]);
                  else
                    RtlCopyVolatileMemory(v86, Src, 8u);
                  return updated;
                }
                return 3221225569LL;
              }
              return 3221225476LL;
            }
            v75 = v74 - 2;
            if ( v75 )
            {
              v76 = v75 - 1;
              if ( !v76 )
              {
                PrivilegeValue[0] = 0;
                if ( (((_DWORD)v3 - 16) & 0xFFFFFFE7) == 0 && (_DWORD)v3 != 40 )
                {
                  if ( SeSinglePrivilegeCheck(SeProfileSingleProcessPrivilege, PreviousMode) )
                  {
                    if ( PreviousMode )
                      RtlCopyFromUser(&Buf1, p_Buf1, v3);
                    else
                      RtlCopyVolatileMemory(&Buf1, p_Buf1, v3);
                    ThreadPartition = MiGetThreadPartition(KeGetCurrentThread());
                    updated = MiCombineIdenticalPages(ThreadPartition, Buf1, LODWORD(v154[0]));
                    LODWORD(Object) = updated;
                    if ( PreviousMode )
                      RtlWriteULong64ToUser((char *)p_Buf1 + 8, *(_QWORD *)PrivilegeValue);
                    else
                      *((LUID *)p_Buf1 + 1) = PrivilegeValue[0];
                    return updated;
                  }
                  return 3221225569LL;
                }
                return 3221225476LL;
              }
              v77 = v76 - 1;
              if ( v77 )
              {
                if ( v77 != 1 )
                  return (unsigned int)-1073741821;
                if ( (_DWORD)v3 != 4 )
                  return 3221225476LL;
                *(_QWORD *)&DriverServiceName.Length = 7733364;
                DriverServiceName.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\condrv";
                if ( PreviousMode )
                {
                  v78 = RtlReadULongFromUser(p_Buf1);
                  LODWORD(Buf1) = v78;
                }
                else
                {
                  RtlCopyVolatileMemory(&Buf1, p_Buf1, 4u);
                  LOBYTE(v78) = Buf1;
                }
                if ( (v78 & 1) != 0 )
                {
                  KeEnterCriticalRegion();
                  v79 = KeAbPreAcquire((struct _KTHREAD *)&ExpPlatformBinaryLock.WaitBlockFill11[24], 0);
                  v81 = (AutoBoost *)v79;
                  if ( _interlockedbittestandset64(
                         (volatile signed __int32 *)&ExpPlatformBinaryLock.WaitBlockFill11[24],
                         0) )
                  {
                    ExfAcquirePushLockExclusiveEx(
                      &ExpPlatformBinaryLock.WaitBlockFill11[24],
                      v79,
                      &ExpPlatformBinaryLock.WaitBlockFill11[24]);
                  }
                  if ( v81 )
                  {
                    if ( (KiAbpGlobalState & 1) != 0 )
                      AutoBoost::KiAbpPostAcquire(v81, v80);
                    else
                      *((_BYTE *)v81 + 10) = 1;
                  }
                  updated = ZwLoadDriver(&DriverServiceName);
                  if ( (_InterlockedExchangeAdd64(
                          (volatile signed __int64 *)&ExpPlatformBinaryLock.WaitBlock[0].Thread,
                          0xFFFFFFFFFFFFFFFFuLL)
                      & 6) == 2 )
                    ExfTryToWakePushLock(&ExpPlatformBinaryLock.WaitBlockFill11[24]);
                  KeAbPostRelease((struct _KTHREAD *)&ExpPlatformBinaryLock.WaitBlockFill11[24]);
                  KeLeaveCriticalRegion();
                  return updated;
                }
                if ( !SeSinglePrivilegeCheck(SeLoadDriverPrivilege, PreviousMode) )
                  return 3221225569LL;
                return (unsigned int)ZwUnloadDriver(&DriverServiceName);
              }
              else
              {
                if ( PreviousMode )
                  return 3221225506LL;
                if ( (_DWORD)v3 != 24 )
                  return 3221225476LL;
                return (unsigned int)KeInitializeEntropySystem(
                                       *(_QWORD *)p_Buf1,
                                       *((_QWORD *)p_Buf1 + 1),
                                       *((_QWORD *)p_Buf1 + 2));
              }
            }
            else
            {
              LOBYTE(v8) = PreviousMode;
              return (unsigned int)KeProcessorProfileControlArea(p_Buf1, (unsigned int)v3, v8);
            }
          }
        }
        v87 = a1 - 142;
        if ( !v87 )
        {
          if ( (_DWORD)v3 == 72 || (_DWORD)v3 == 48 )
          {
            if ( SeSinglePrivilegeCheck(SeShutdownPrivilege, PreviousMode) )
            {
              RtlCopyFromUser(&Buf1, p_Buf1, v3);
              Pool2 = (void *)ExAllocatePool2(64, LOWORD(v154[0]), 1347639365);
              v95 = Pool2;
              PrivilegeValue[0] = (LUID)Pool2;
              if ( !Pool2 )
                return 3221225626LL;
              RtlCopyFromUser(Pool2, v154[1], LOWORD(v154[0]));
              v154[1] = v95;
              CurrentServerSiloGlobals = PsGetCurrentServerSiloGlobals(v97, v96);
              if ( _InterlockedCompareExchange((volatile signed __int32 *)(CurrentServerSiloGlobals + 1376), Buf1, 0) )
              {
                ExFreePoolWithTag(v95, 0x50535845u);
                return 0;
              }
              *(_OWORD *)(CurrentServerSiloGlobals + 1376) = Buf1;
              *(_OWORD *)(CurrentServerSiloGlobals + 1392) = *(_OWORD *)v154;
              *(_OWORD *)(CurrentServerSiloGlobals + 1408) = v155;
              *(_OWORD *)(CurrentServerSiloGlobals + 1424) = v156;
              *(_QWORD *)(CurrentServerSiloGlobals + 1440) = v157;
              return 0;
            }
            return 3221225569LL;
          }
          return 3221225476LL;
        }
        v88 = v87 - 8;
        if ( !v88 )
        {
          if ( !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
            return 3221225569LL;
          return (unsigned int)ExpSetBootLoaderMetadata(p_Buf1, (unsigned int)v3);
        }
        v89 = v88 - 1;
        if ( !v89 )
        {
          PrivilegeValue[0] = (LUID)19LL;
          if ( !SeSinglePrivilegeCheck((LUID)19LL, PreviousMode) )
            return 3221225569LL;
          v91 = v3 - 1;
          if ( v91 )
          {
            if ( v91 != 3 )
              return 3221225476LL;
            if ( PreviousMode )
              v92 = RtlReadULongFromUser(p_Buf1);
            else
              v92 = *(_DWORD *)p_Buf1;
            v139 = v92;
          }
          else
          {
            if ( PreviousMode )
              v93 = RtlReadUCharFromUser(p_Buf1);
            else
              v93 = *(_BYTE *)p_Buf1;
            v129 = v93;
            if ( v93 && !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
              return 3221225569LL;
            v92 = v93 != 0 ? 1 : 5;
          }
          return (unsigned int)ExpSetSoftRebootFlags(v92);
        }
        v90 = v89 - 1;
        if ( v90 )
        {
          if ( v90 != 3 )
            return (unsigned int)-1073741821;
          return (unsigned int)CmReconcileAndValidateAllHives(v7, 2);
        }
        if ( (_DWORD)v3 != 8 )
          return 3221225476LL;
        if ( PreviousMode )
        {
          v150 = RtlReadULong64FromUser(p_Buf1);
          return (unsigned int)ExpQueryElamCertInfo(v150);
        }
        return 3221225485LL;
      }
      if ( a1 > 177 )
      {
        if ( a1 == 187 )
        {
          if ( (_DWORD)v3 != 24 )
            return 3221225476LL;
          if ( PreviousMode )
            RtlCopyFromUser(&Buf1, p_Buf1, 0x18u);
          else
            RtlCopyVolatileMemory(&Buf1, p_Buf1, 0x18u);
          result = VfProbeAndCaptureUnicodeStringBuffer(&Buf1, 1);
          if ( (int)result >= 0 )
          {
            updated = PsSetExeModerationState(&Buf1, LODWORD(v154[0]), HIDWORD(v154[0]));
            v69 = (char *)&Buf1;
            goto LABEL_525;
          }
          return result;
        }
        if ( a1 != 190 )
        {
          v111 = (unsigned int)(a1 - 191);
          if ( a1 == 191 )
          {
            if ( !(_DWORD)v3 )
            {
              if ( PreviousMode && !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
                return 3221225569LL;
              return (unsigned int)VslRelaxQuotas(v111, v13);
            }
          }
          else
          {
            if ( a1 != 194 )
              return (unsigned int)-1073741821;
            if ( !(_DWORD)v3 )
            {
              if ( !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
                return 3221225569LL;
              updated = VslProvisionDumpEncryption();
              if ( (updated & 0x80000000) != 0 )
                return updated;
              return (unsigned int)IoProvisionCrashDumpKey();
            }
          }
          return (unsigned int)-1073741811;
        }
      }
      else
      {
        if ( a1 == 177 )
        {
          LODWORD(Object) = 0;
          v146 = 0;
          v147 = 0;
          if ( (_DWORD)v3 != 8 )
          {
            if ( (_DWORD)v3 )
              return 3221225476LL;
            updated = 0;
            v110 = KeGetCurrentThread()->ApcState.Process;
            LODWORD(Object) = PsGetSessionIdEx(v110, 2);
            if ( (_DWORD)Object == -1 )
              return updated;
            v147 = v110;
            return (unsigned int)PsInvokeWin32Callout(32, &v146, 1, &Object);
          }
          if ( !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
            return 3221225569LL;
          if ( PreviousMode )
            v107 = (void *)RtlReadULong64FromUser(p_Buf1);
          else
            v107 = *(void **)p_Buf1;
          v152 = v107;
          PrivilegeValue[0] = 0;
          updated = ObReferenceObjectByHandle(
                      v107,
                      0x1000u,
                      (POBJECT_TYPE)PsProcessType,
                      PreviousMode,
                      (PVOID *)PrivilegeValue,
                      0);
          if ( (updated & 0x80000000) != 0 )
            return updated;
          v109 = PrivilegeValue[0];
          LODWORD(Object) = PsGetSessionIdEx(*(_QWORD *)PrivilegeValue, v108);
          if ( (_DWORD)Object != -1 )
          {
            v147 = (_KPROCESS *)v109;
            updated = PsInvokeWin32Callout(32, &v146, 1, &Object);
          }
          v57 = (void *)v109;
          goto LABEL_234;
        }
        if ( a1 == 161 )
        {
          if ( PreviousMode )
            return 3221225506LL;
          if ( (_DWORD)v3 != 8 )
            return 3221225476LL;
          return (unsigned int)KdInitialize(3, p_Buf1, &KdpContext);
        }
        if ( a1 != 164 )
        {
          if ( a1 != 168 )
          {
            if ( a1 == 170 )
            {
              *(_OWORD *)&PrivilegeValue[0].LowPart = 0;
              if ( (_DWORD)v3 != 16 )
                return 3221225476LL;
              if ( !SeSinglePrivilegeCheck(SeIncreaseBasePriorityPrivilege, PreviousMode) )
                return 3221225569LL;
              if ( PreviousMode )
                RtlCopyFromUser(PrivilegeValue, p_Buf1, (unsigned int)v3);
              else
                RtlCopyVolatileMemory(PrivilegeValue, p_Buf1, (unsigned int)v3);
              return (unsigned int)KeIntSteerAssignCpuSetForGsiv(
                                     PrivilegeValue[0].LowPart,
                                     LOWORD(PrivilegeValue[0].HighPart),
                                     *(_QWORD *)&PrivilegeValue[1]);
            }
            else
            {
              if ( a1 != 176 )
                return (unsigned int)-1073741821;
              if ( (unsigned int)v3 < 8 )
                return 3221225476LL;
              v99 = v3 - 8;
              if ( (v99 & 7) != 0 || v99 > 0x200 )
                return 3221225476LL;
              if ( PreviousMode )
                v100 = RtlReadULong64FromUser(p_Buf1);
              else
                v100 = *(_QWORD *)p_Buf1;
              v151 = v100;
              v101 = (char *)p_Buf1 + 8;
              if ( PreviousMode )
                RtlCopyFromUser(&Buf1, v101, v99);
              else
                RtlCopyVolatileMemory(&Buf1, v101, v99);
              LOBYTE(v102) = PreviousMode;
              updated = ExCpuSetResourceManagerAccessCheck(v102);
              if ( (updated & 0x80000000) != 0 )
                return updated;
              return (unsigned int)KeSetTagCpuSets(v99 >> 3, &Buf1, v100);
            }
          }
          if ( (v3 & 7) != 0 || (unsigned int)v3 > 0x200 )
            return 3221225476LL;
          if ( PreviousMode )
            RtlCopyFromUser(&Buf1, p_Buf1, v3);
          else
            RtlCopyVolatileMemory(&Buf1, p_Buf1, v3);
          LOBYTE(v103) = PreviousMode;
          result = ExCpuSetResourceManagerAccessCheck(v103);
          if ( (int)result >= 0 )
          {
            v105 = (unsigned int)v3 >> 3;
            v106 = 0;
            return (unsigned int)KeModifySystemAllowedCpuSets(v105, (unsigned int)&Buf1, v104, v106);
          }
          return result;
        }
      }
    }
LABEL_507:
    if ( *(_QWORD *)&SepRmCapTableLock.SchedulerAssistPriorityFloor )
      return (unsigned int)guard_dispatch_icall_no_overrides((unsigned int)a1, p_Buf1, (unsigned int)v3);
    return (unsigned int)-1073741637;
  }
  if ( a1 > 225 )
  {
    if ( a1 <= 243 )
    {
      if ( a1 != 243 )
      {
        switch ( a1 )
        {
          case 226:
            if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
              return 3221225569LL;
            LOBYTE(v122) = (_DWORD)v3 == 0;
            return (unsigned int)VfPtGenerateTraceInformation(v122);
          case 228:
          case 229:
            v125 = 0;
            if ( (int)RtlCheckTokenMembership(0, SeAliasAdminsSid, &v125) < 0 || !v125 )
              return 3221225569LL;
            return (unsigned int)KeUpdateDpcWatchdogConfiguration(p_Buf1, (unsigned int)v3);
          case 233:
            return (unsigned int)PnpIommuBlockUnblockDevice(p_Buf1, (unsigned int)v3);
          case 235:
            return (unsigned int)HvlQuerySetBootPagesInfo(p_Buf1, 0);
          default:
            return (unsigned int)-1073741821;
        }
      }
      return (unsigned int)-1073741637;
    }
    if ( a1 == 245 )
    {
      if ( (_DWORD)v3 != 4 )
        return (unsigned int)-1073741820;
      if ( SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
      {
        if ( PreviousMode )
          v124 = RtlReadULongFromUser(p_Buf1);
        else
          v124 = *(_DWORD *)p_Buf1;
        v140 = v124;
        ExResourceTimeoutCount = (v124 + 3999) / 0xFA0u;
        return updated;
      }
      return (unsigned int)-1073741727;
    }
    if ( a1 == 246 )
    {
      if ( (_DWORD)v3 == 4 )
      {
        if ( SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
        {
          if ( PreviousMode )
            v123 = RtlReadULongFromUser(p_Buf1);
          else
            v123 = *(_DWORD *)p_Buf1;
          LODWORD(Buf1) = v123;
          PspBreakOnContextUnwindFailure = v123;
          return 0;
        }
        return 3221225569LL;
      }
      return 3221225476LL;
    }
    if ( a1 != 248 )
    {
      if ( a1 != 251 )
        return (unsigned int)-1073741821;
      return (unsigned int)ObSetRefTraceInformationEx(p_Buf1);
    }
    goto LABEL_507;
  }
  if ( a1 == 225 )
    goto LABEL_507;
  if ( a1 > 217 )
  {
    switch ( a1 )
    {
      case 218:
        if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
          return 3221225506LL;
        return (unsigned int)VfVolatileClearDifRuleClass();
      case 219:
      case 220:
        if ( (_DWORD)v3 != 16 )
          return 3221225476LL;
        if ( PreviousMode )
        {
          if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
            return 3221225569LL;
          result = VfProbeAndCaptureUnicodeString(&v133, p_Buf1, 1);
          if ( (int)result < 0 )
            return result;
          if ( !(_WORD)v133 )
            return 3221225711LL;
          p_Buf1 = &v133;
        }
        v121 = a1 - 219;
        if ( !v121 )
        {
          v41 = VfVolatileApplyDifVerification(p_Buf1, v13);
          goto LABEL_522;
        }
        if ( v121 == 1 )
        {
          v41 = VfVolatileRemoveDifVerification(p_Buf1, v13);
          goto LABEL_522;
        }
        goto LABEL_519;
      case 223:
        return (unsigned int)ExPoolSetLimit(p_Buf1, v3, PreviousMode);
    }
    if ( a1 != 224 )
      return (unsigned int)-1073741821;
    goto LABEL_507;
  }
  if ( a1 == 217 )
  {
    if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
      return 3221225506LL;
    return (unsigned int)VfVolatileSetDifRuleClass(p_Buf1, (unsigned int)v3);
  }
  v112 = a1 - 204;
  if ( !v112 )
  {
    if ( (unsigned int)v3 < 8 )
      return 3221225476LL;
    v117 = v3 - 8;
    if ( (v117 & 7) != 0 || v117 > 0x200 )
      return 3221225476LL;
    if ( PreviousMode )
      v118 = RtlReadULong64FromUser(p_Buf1);
    else
      v118 = *(_QWORD *)p_Buf1;
    PrivilegeValue[0] = (LUID)v118;
    v119 = (char *)p_Buf1 + 8;
    if ( PreviousMode )
      RtlCopyFromUser(&Buf1, v119, v117);
    else
      RtlCopyVolatileMemory(&Buf1, v119, v117);
    v120 = 2;
    if ( v118 >= 2 )
      return 3221225485LL;
    LOBYTE(v120) = PreviousMode;
    updated = ExCpuSetResourceManagerAccessCheck(v120);
    if ( (updated & 0x80000000) != 0 )
      return updated;
    v106 = v118;
    v105 = v117 >> 3;
    return (unsigned int)KeModifySystemAllowedCpuSets(v105, (unsigned int)&Buf1, v104, v106);
  }
  v113 = v112 - 2;
  if ( v113 )
  {
    v114 = v113 - 1;
    if ( v114 )
    {
      v115 = v114 - 3;
      if ( v115 )
      {
        if ( v115 != 2 )
          return (unsigned int)-1073741821;
        return (unsigned int)CmUpdateFeatureUsageSubscription(p_Buf1, (unsigned int)v3, PreviousMode);
      }
      else
      {
        return (unsigned int)CmUpdateFeatureConfiguration(p_Buf1, (unsigned int)v3, PreviousMode);
      }
    }
    if ( (_DWORD)v3 != 4 )
      return 3221225476LL;
    if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
      return 3221225506LL;
    v134 = 0;
    if ( PreviousMode )
      v116 = RtlReadULongFromUser(p_Buf1);
    else
      v116 = *(_DWORD *)p_Buf1;
    v134 = v116;
    if ( (v116 & 0x2018) == 0 )
    {
      v19 = v116 | NtGlobalFlag2 & 0x2018;
      v134 = v19;
      NtGlobalFlag2 = v19;
      if ( !PreviousMode )
      {
        *(_DWORD *)p_Buf1 = v19;
        return updated;
      }
      goto LABEL_42;
    }
    return 3221225485LL;
  }
  if ( (_DWORD)v3 != 8 )
    return 3221225476LL;
  if ( PreviousMode && !SeSinglePrivilegeCheck(SeSystemtimePrivilege, PreviousMode) )
    return 3221225569LL;
  if ( (unsigned __int8)PsIsCurrentThreadInServerSilo(v7, v13) )
    return 3221225506LL;
  if ( PreviousMode )
    *(_QWORD *)&Buf1 = RtlReadULong64FromUser(p_Buf1);
  else
    RtlCopyVolatileMemory(&Buf1, p_Buf1, 8u);
  v126 = (_BYTE)Buf1 != 0;
  result = ExSetLeapSecondEnabled();
  updated = result;
  if ( (int)result >= 0 )
  {
    LOBYTE(ExpKeyManipLock.Header.WaitListHead.Flink->Flink) = v126;
    return updated;
  }
  return result;
}

```

## disassembly

```asm
0x1409f5d70  push    rbx
0x1409f5d72  push    rsi
0x1409f5d73  push    rdi
0x1409f5d74  push    r12
0x1409f5d76  push    r13
0x1409f5d78  push    r14
0x1409f5d7a  push    r15
0x1409f5d7c  sub     rsp, 3D0h
0x1409f5d83  mov     rax, cs:__security_cookie
0x1409f5d8a  xor     rax, rsp
0x1409f5d8d  mov     [rsp+408h+var_48], rax
0x1409f5d95  mov     r13d, r8d
0x1409f5d98  mov     r14, rdx
0x1409f5d9b  mov     esi, ecx
0x1409f5d9d  xor     edi, edi
0x1409f5d9f  mov     [rsp+408h+var_3D7], dil
0x1409f5da4  xorps   xmm0, xmm0
0x1409f5da7  movups  [rsp+408h+var_3A8], xmm0
0x1409f5dac  mov     [rsp+408h+var_3B8], rdi
0x1409f5db1  mov     [rsp+408h+Src], rdi
0x1409f5db9  mov     [rsp+408h+var_2E0], rdi
0x1409f5dc1  mov     [rsp+408h+var_3D0], rdi
0x1409f5dc6  xor     edx, edx; Val
0x1409f5dc8  mov     r8d, 200h; Size
0x1409f5dce  lea     rcx, [rsp+408h+Buf1]; void *
0x1409f5dd6  call    memset_0
0x1409f5ddb  mov     rax, gs:188h
0x1409f5de4  mov     r15b, [rax+232h]
0x1409f5deb  test    r15b, r15b
0x1409f5dee  jz      short loc_1409F5E52
0x1409f5df0  cmp     esi, 59h ; 'Y'
0x1409f5df3  jnz     short loc_1409F5DFF
0x1409f5df5  lea     r8d, [rdi+2]
0x1409f5df9  lea     r12d, [rdi+1]
0x1409f5dfd  jmp     short loc_1409F5E3B
0x1409f5dff  cmp     esi, 97h
0x1409f5e05  jnz     short loc_1409F5E2F
0x1409f5e07  cmp     esi, 0CCh
0x1409f5e0d  jz      short loc_1409F5E2F
0x1409f5e0f  cmp     esi, 0D2h
0x1409f5e15  jz      short loc_1409F5E2F
0x1409f5e17  cmp     esi, 0D4h
0x1409f5e1d  jz      short loc_1409F5E2F
0x1409f5e1f  mov     r12d, 1
0x1409f5e25  cmp     r13d, r12d
0x1409f5e28  jnz     short loc_1409F5E35
0x1409f5e2a  mov     r8d, r12d
0x1409f5e2d  jmp     short loc_1409F5E3B
0x1409f5e2f  mov     r12d, 1
0x1409f5e35  mov     r8d, 4; Alignment
0x1409f5e3b  mov     rdx, r13; Length
0x1409f5e3e  mov     rcx, r14; Address
0x1409f5e41  call    ProbeForRead
0x1409f5e46  mov     edx, 2
0x1409f5e4b  jmp     short loc_1409F5E5B
0x1409f5e4d  jmp     loc_1409F7D43
0x1409f5e52  mov     edx, 2
0x1409f5e57  lea     r12d, [rdx-1]
0x1409f5e5b  mov     [rsp+408h+var_3D8], r15b
0x1409f5e60  mov     ebx, edi
0x1409f5e62  cmp     esi, 7Eh ; '~'
0x1409f5e65  jg      loc_1409F6E68
0x1409f5e6b  jz      loc_1409F6E48
0x1409f5e71  cmp     esi, 48h ; 'H'
0x1409f5e74  jg      loc_1409F67F1
0x1409f5e7a  jz      loc_1409F6751
0x1409f5e80  cmp     esi, 27h ; '''
0x1409f5e83  jg      loc_1409F644C
0x1409f5e89  jz      loc_1409F63FC
0x1409f5e8f  cmp     esi, 1Ch
0x1409f5e92  jg      loc_1409F6150
0x1409f5e98  jz      loc_1409F6045
0x1409f5e9e  mov     r9d, r12d
0x1409f5ea1  mov     ecx, esi
0x1409f5ea3  sub     ecx, 9
0x1409f5ea6  jz      loc_1409F5FC2
0x1409f5eac  sub     ecx, 0Ch
0x1409f5eaf  jz      loc_1409F683E
0x1409f5eb5  sub     ecx, 3
0x1409f5eb8  jz      short loc_1409F5EF8
0x1409f5eba  sub     ecx, edx
0x1409f5ebc  jz      loc_1409F6668
0x1409f5ec2  cmp     ecx, 1
0x1409f5ec5  jnz     loc_1409F6DAF
0x1409f5ecb  cmp     r13d, 8
0x1409f5ecf  jnz     loc_1409F7C8D
0x1409f5ed5  test    r15b, r15b
0x1409f5ed8  jnz     loc_1409F7CAA
0x1409f5ede  mov     rcx, [r14]
0x1409f5ee1  mov     [rsp+408h+var_288], rcx
0x1409f5ee9  call    MmUnloadSystemImage
0x1409f5eee  jmp     loc_1409F6440
0x1409f5ef3  jmp     loc_1409F7D43
0x1409f5ef8  mov     esi, 14h
0x1409f5efd  cmp     r13d, esi
0x1409f5f00  jnz     loc_1409F7C8D
0x1409f5f06  test    r15b, r15b
0x1409f5f09  jz      short loc_1409F5F22
0x1409f5f0b  mov     dl, r15b; PreviousMode
0x1409f5f0e  mov     rcx, qword ptr cs:SeLoadDriverPrivilege.LowPart; PrivilegeValue
0x1409f5f15  call    SeSinglePrivilegeCheck
0x1409f5f1a  test    al, al
0x1409f5f1c  jz      loc_1409F7CAA
0x1409f5f22  mov     r8, rsi; Size
0x1409f5f25  mov     rdx, r14; Src
0x1409f5f28  lea     rcx, [rsp+408h+Buf1]; void *
0x1409f5f30  test    r15b, r15b
0x1409f5f33  jz      short loc_1409F5F3C
0x1409f5f35  call    RtlCopyFromUser
0x1409f5f3a  jmp     short loc_1409F5F42
0x1409f5f3c  call    RtlCopyVolatileMemory
0x1409f5f41  nop
0x1409f5f42  mov     eax, dword ptr [rsp+408h+Buf1+4]
0x1409f5f49  mov     cs:KiMaximumDpcQueueDepth, eax
0x1409f5f4f  mov     eax, dword ptr [rsp+408h+Buf1+8]
0x1409f5f56  mov     cs:KiMinimumDpcRate, eax
0x1409f5f5c  mov     eax, dword ptr [rsp+408h+Buf1+0Ch]
0x1409f5f63  mov     cs:KiAdjustDpcThreshold, eax
0x1409f5f69  mov     eax, dword ptr [rsp+408h+var_248]
0x1409f5f70  mov     cs:KiIdealDpcRate, eax
0x1409f5f76  call    KeSynchronizeWithDynamicProcessors
0x1409f5f7b  mov     ecx, 0FFFFh; GroupNumber
0x1409f5f80  call    KeQueryActiveProcessorCountEx
0x1409f5f85  test    eax, eax
0x1409f5f87  jz      loc_1409F7D41
0x1409f5f8d  mov     ecx, edi
0x1409f5f8f  lea     rdx, KiProcessorBlock
0x1409f5f96  mov     rdx, [rdx+rcx*8]
0x1409f5f9a  mov     ecx, cs:KiMaximumDpcQueueDepth
0x1409f5fa0  mov     [rdx+0CE8h], ecx
0x1409f5fa6  mov     ecx, cs:KiMinimumDpcRate
0x1409f5fac  mov     [rdx+0CF0h], ecx
0x1409f5fb2  inc     edi
0x1409f5fb4  cmp     edi, eax
0x1409f5fb6  jb      short loc_1409F5F8D
0x1409f5fb8  jmp     loc_1409F7D41
0x1409f5fbd  jmp     loc_1409F7D43
0x1409f5fc2  cmp     r13d, 4
0x1409f5fc6  jnz     loc_1409F7C8D
0x1409f5fcc  mov     dl, r15b; PreviousMode
0x1409f5fcf  mov     rcx, qword ptr cs:SeDebugPrivilege.LowPart; PrivilegeValue
0x1409f5fd6  call    SeSinglePrivilegeCheck
0x1409f5fdb  test    al, al
0x1409f5fdd  jz      loc_1409F7B7E
0x1409f5fe3  mov     [rsp+408h+var_3C4], edi
0x1409f5fe7  test    r15b, r15b
0x1409f5fea  jz      short loc_1409F5FF8
0x1409f5fec  mov     rcx, r14
0x1409f5fef  call    RtlReadULongFromUser
0x1409f5ff4  mov     ecx, eax
0x1409f5ff6  jmp     short loc_1409F5FFB
0x1409f5ff8  mov     ecx, [r14]
0x1409f5ffb  mov     [rsp+408h+var_3C4], ecx
0x1409f5fff  and     ecx, 92319BF0h
0x1409f6005  mov     [rsp+408h+var_3C4], ecx
0x1409f6009  mov     eax, cs:NtGlobalFlag
0x1409f600f  and     eax, 6DCE640Fh
0x1409f6014  or      eax, ecx
0x1409f6016  mov     [rsp+408h+var_3C4], eax
0x1409f601a  mov     cs:NtGlobalFlag, eax
0x1409f6020  test    r15b, r15b
0x1409f6023  jz      short loc_1409F6031
0x1409f6025  mov     edx, eax
0x1409f6027  mov     rcx, r14
0x1409f602a  call    RtlWriteULongToUser
0x1409f602f  jmp     short loc_1409F6034
0x1409f6031  mov     [r14], eax
0x1409f6034  jmp     loc_1409F7D41
0x1409f6039  mov     ebx, eax
0x1409f603b  jmp     loc_1409F7D41
0x1409f6040  jmp     loc_1409F7D43
0x1409f6045  lea     eax, [r13-8]
0x1409f6049  test    eax, 0FFFFFFF7h
0x1409f604e  jnz     loc_1409F7C8D
0x1409f6054  test    r15b, r15b
0x1409f6057  jz      short loc_1409F6070
0x1409f6059  mov     dl, r15b; PreviousMode
0x1409f605c  mov     rcx, qword ptr cs:SeSystemtimePrivilege.LowPart; PrivilegeValue
0x1409f6063  call    SeSinglePrivilegeCheck
0x1409f6068  test    al, al
0x1409f606a  jz      loc_1409F7CAA
0x1409f6070  call    PsIsCurrentThreadInServerSilo
0x1409f6075  test    al, al
0x1409f6077  jnz     loc_1409F7B7E
0x1409f607d  mov     [rsp+408h+var_390], rdi
0x1409f6082  cmp     r13d, 10h
0x1409f6086  jnz     short loc_1409F60F2
0x1409f6088  test    r15b, r15b
0x1409f608b  jz      short loc_1409F6098
0x1409f608d  lea     rcx, [r14+8]
0x1409f6091  call    RtlReadUCharFromUser
0x1409f6096  jmp     short loc_1409F609C
0x1409f6098  mov     al, [r14+8]
0x1409f609c  mov     [rsp+408h+var_3D7], al
0x1409f60a0  test    r15b, r15b
0x1409f60a3  jz      short loc_1409F60AF
0x1409f60a5  mov     rcx, r14
0x1409f60a8  call    RtlReadULong64FromUser
0x1409f60ad  jmp     short loc_1409F60B2
0x1409f60af  mov     rax, [r14]
0x1409f60b2  mov     [rsp+408h+var_390], rax
0x1409f60b7  mov     rcx, 0FFFFF78000000300h
0x1409f60c1  cmp     [rsp+408h+var_3D7], dil
0x1409f60c6  jz      short loc_1409F60D0
0x1409f60c8  mov     rax, [rcx]
0x1409f60cb  mov     [rsp+408h+var_390], rax
0x1409f60d0  call    ExAcquireTimeRefreshLockExclusive
0x1409f60d5  lea     r8, [rsp+408h+var_3D7]
0x1409f60da  lea     rdx, [rsp+408h+var_390]
0x1409f60df  xor     ecx, ecx
0x1409f60e1  call    ExpUpdateTimerConfiguration
0x1409f60e6  mov     ebx, eax
0x1409f60e8  call    ExReleaseTimeRefreshLockExclusive
0x1409f60ed  jmp     loc_1409F7D41
0x1409f60f2  test    r15b, r15b
0x1409f60f5  jz      short loc_1409F6102
0x1409f60f7  lea     rcx, [r14+4]
0x1409f60fb  call    RtlReadUCharFromUser
0x1409f6100  jmp     short loc_1409F6106
0x1409f6102  mov     al, [r14+4]
0x1409f6106  mov     [rsp+408h+var_3D7], al
0x1409f610a  test    r15b, r15b
0x1409f610d  jz      short loc_1409F6119
0x1409f610f  mov     rcx, r14
0x1409f6112  call    RtlReadULongFromUser
0x1409f6117  jmp     short loc_1409F611C
0x1409f6119  mov     eax, [r14]
0x1409f611c  mov     r8d, eax
0x1409f611f  mov     [rsp+408h+var_390], r8
0x1409f6124  test    eax, eax
0x1409f6126  jz      short loc_1409F60B7
0x1409f6128  mov     eax, cs:KeMaximumIncrement
0x1409f612e  mov     rcx, 0FFFFF78000000300h
0x1409f6138  imul    rax, [rcx]
0x1409f613c  xor     edx, edx
0x1409f613e  div     r8
0x1409f6141  mov     [rsp+408h+var_390], rax
0x1409f6146  jmp     loc_1409F60C1
0x1409f614b  jmp     loc_1409F7D43
0x1409f6150  sub     esi, 1Eh
0x1409f6153  jz      loc_1409F63F2
0x1409f6159  sub     esi, 1
0x1409f615c  jz      loc_1409F63DF
0x1409f6162  mov     r12d, 3
0x1409f6168  sub     esi, r12d
0x1409f616b  jz      loc_1409F634F
0x1409f6171  sub     esi, r12d
0x1409f6174  jz      loc_1409F631C
0x1409f617a  cmp     esi, 1
0x1409f617d  jnz     loc_1409F6DAF
0x1409f6183  cmp     r13d, 10h
0x1409f6187  jnz     loc_1409F7C8D
0x1409f618d  test    r15b, r15b
0x1409f6190  jz      loc_1409F627D
0x1409f6196  mov     rax, gs:188h
0x1409f619f  mov     rcx, [rax+0B8h]
0x1409f61a6  mov     eax, [rcx+7DCh]
0x1409f61ac  test    al, 8
0x1409f61ae  jz      loc_1409F7CAA
0x1409f61b4  mov     dl, sil; PreviousMode
0x1409f61b7  mov     rcx, qword ptr cs:SeLoadDriverPrivilege.LowPart; PrivilegeValue
0x1409f61be  call    SeSinglePrivilegeCheck
0x1409f61c3  test    al, al
0x1409f61c5  jz      loc_1409F7CAA
0x1409f61cb  xorps   xmm0, xmm0
0x1409f61ce  movups  xmmword ptr [rsp+408h+PrivilegeValue.LowPart], xmm0
0x1409f61d6  mov     rcx, r14
0x1409f61d9  call    RtlReadULongFromUser
0x1409f61de  mov     [rsp+408h+PrivilegeValue.LowPart], eax
0x1409f61e5  lea     rcx, [r14+8]
0x1409f61e9  call    RtlReadULong64FromUser
0x1409f61ee  mov     qword ptr [rsp+408h+PrivilegeValue.LowPart+8], rax
0x1409f61f6  movaps  xmm0, xmmword ptr [rsp+408h+PrivilegeValue.LowPart]
0x1409f61fe  movdqa  [rsp+408h+var_3A8], xmm0
0x1409f6204  mov     ebx, 3Eh ; '>'
0x1409f6209  cmp     word ptr [rsp+408h+PrivilegeValue.LowPart], bx
0x1409f6211  jnz     loc_1409F7CAA
0x1409f6217  movzx   r8d, word ptr [rsp+408h+PrivilegeValue.LowPart]; Size
0x1409f6220  mov     rdx, rax; Src
0x1409f6223  lea     rcx, [rsp+408h+Buf1]; void *
0x1409f622b  call    RtlCopyFromUser
0x1409f6230  nop
0x1409f6231  mov     r8, rbx; Size
0x1409f6234  lea     rsi, aSystemrootSyst_24; "\\SystemRoot\\System32\\win32k.sys"
0x1409f623b  mov     rdx, rsi; Buf2
0x1409f623e  lea     rcx, [rsp+408h+Buf1]; Buf1
0x1409f6246  call    memcmp
0x1409f624b  test    eax, eax
0x1409f624d  jnz     loc_1409F7CAA
0x1409f6253  mov     qword ptr [rsp+408h+var_3A8+8], rsi
0x1409f6258  mov     word ptr [rsp+408h+var_3A8+2], bx
0x1409f625d  lea     r8d, [rax+10h]
0x1409f6261  lea     rdx, [rsp+408h+var_3A8]
0x1409f6266  lea     ecx, [rax+26h]
0x1409f6269  call    ZwSetSystemInformation
0x1409f626e  jmp     loc_1409F7D43
0x1409f6273  jmp     loc_1409F7D43
0x1409f6278  jmp     loc_1409F7D43
0x1409f627d  movups  xmm0, xmmword ptr [r14]
0x1409f6281  movaps  [rsp+408h+var_3A8], xmm0
  ... truncated ...
```
