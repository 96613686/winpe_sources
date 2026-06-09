# NtSetSystemInformation

- ea: `0x1409ff3f0`
- end: `0x140a013e7`
- name: `NtSetSystemInformation`
- size: `8183`
- prototype: `__int64 __fastcall(int, __int128 *p_Buf1, unsigned int)`
- caller_count: `1`
- callee_count: `105`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140c84b98`

## callees

- `0x140213760`
- `0x140214360`
- `0x140214b10`
- `0x140216480`
- `0x140250630`
- `0x1402acde0`
- `0x1402b0470`
- `0x1402e4d30`
- `0x14034a0c0`
- `0x14036f270`
- `0x14036f7d8`
- `0x1403729e0`
- `0x1403a11f0`
- `0x1403d0190`
- `0x14041fe50`
- `0x140436440`
- `0x140439420`
- `0x14046cb30`
- `0x1404857e8`
- `0x1404c35b0`
- `0x14051fe30`
- `0x14052039c`
- `0x140537570`
- `0x1405ceafc`
- `0x1405d17d0`
- `0x1405d2614`
- `0x1405e9f9c`
- `0x1405eab80`
- `0x1405f76bc`
- `0x1405f790c`
- `0x1405fa5b4`
- `0x140614598`
- `0x140614964`
- `0x14063eac4`
- `0x14063eb34`
- `0x14063ec7c`
- `0x14063ed34`
- `0x140686804`
- `0x140686940`
- `0x1406dc8c0`
- `0x1406df580`
- `0x1406e0b60`
- `0x1406e0f00`
- `0x1406eb0e0`
- `0x1406ecf80`
- `0x1406f7250`
- `0x1406f7380`
- `0x140724374`
- `0x140724e08`
- `0x140724e4c`

## import_xrefs

- `kdcom!KdInitialize` at `0x140a00c6d`
- `kdcom!KdInitialize` at `0x140a00c6d`

## string_xrefs

- `0x1409ff8b4`: `\SystemRoot\System32\win32k.sys`
- `0x1409ff90c`: `\SystemRoot\System32\win32k.sys`
- `0x140a00563`: `\Registry\Machine\System\CurrentControlSet\Services\condrv`

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
  __int64 v20; // rdx
  char UCharFromUser; // al
  __int64 ULong64FromUser; // rax
  char v23; // al
  unsigned int v24; // eax
  int v25; // esi
  int v26; // esi
  int v27; // esi
  int v28; // esi
  __int64 v29; // rdx
  void *v30; // rax
  __int64 result; // rax
  __int64 v32; // rax
  int v34; // ecx
  int v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // rcx
  unsigned int ULongFromUser; // eax
  __int64 v39; // rcx
  __int64 v40; // rdx
  void *v41; // rax
  int v42; // esi
  unsigned int v43; // eax
  unsigned int v44; // esi
  char v45; // si
  int SystemImage; // eax
  __int64 v47; // rdx
  __int64 v48; // r15
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // rcx
  __int64 v52; // rcx
  int v53; // ebx
  __int64 v54; // rdx
  int v55; // r9d
  __int64 v56; // r13
  __int64 v57; // rdx
  __int64 v58; // rdx
  PVOID v59; // rsi
  void *v60; // rcx
  int v61; // esi
  int v62; // esi
  int v63; // esi
  int v64; // esi
  _KPROCESS *Process; // rcx
  __int16 v66; // ax
  __int64 v67; // rdx
  int v68; // ebx
  int v69; // esi
  int v70; // esi
  int v71; // esi
  int v72; // esi
  char *v73; // rcx
  __int64 v74; // rdx
  int v75; // esi
  int v76; // esi
  int v77; // esi
  unsigned int v78; // ecx
  int v79; // esi
  int v80; // esi
  int v81; // esi
  int v82; // esi
  int v83; // eax
  __int64 v84; // rax
  void *v85; // rdx
  AutoBoost *v86; // rbx
  __int64 ThreadPartition; // rax
  __int64 v89; // rdx
  __int64 v90; // rcx
  __int64 v91; // rax
  void *v92; // rcx
  int v93; // esi
  int v94; // esi
  int v95; // esi
  int v96; // esi
  int v97; // r13d
  unsigned int v98; // eax
  char v99; // bl
  void *Pool2; // rax
  void *v101; // rbx
  __int64 v102; // rdx
  __int64 v103; // rcx
  __int64 CurrentServerSiloGlobals; // r8
  unsigned int v105; // r13d
  __int64 v106; // rsi
  void *v107; // rdx
  __int64 v108; // rdx
  __int64 v109; // rcx
  __int64 v110; // rdx
  __int64 v111; // rcx
  int v112; // r8d
  unsigned int v113; // r13d
  int v114; // r9d
  __int64 v115; // rdx
  void *v116; // rax
  LUID v117; // rdi
  _KPROCESS *v118; // rdi
  __int64 v119; // rcx
  int v120; // esi
  int v121; // esi
  int v122; // esi
  int v123; // esi
  ULONG v124; // ecx
  __int64 v125; // rdx
  unsigned int v126; // r13d
  unsigned __int64 v127; // rsi
  void *v128; // rdx
  __int64 v129; // rdx
  __int64 v130; // rcx
  int v131; // esi
  __int64 v132; // rcx
  int v133; // eax
  int v134; // eax
  KPROCESSOR_MODE v135; // [rsp+30h] [rbp-3D8h] BYREF
  bool v136; // [rsp+31h] [rbp-3D7h] BYREF
  char v137[6]; // [rsp+32h] [rbp-3D6h] BYREF
  PVOID Object; // [rsp+38h] [rbp-3D0h] BYREF
  char v139; // [rsp+40h] [rbp-3C8h]
  ULONG v140; // [rsp+44h] [rbp-3C4h]
  unsigned int v141; // [rsp+48h] [rbp-3C0h] BYREF
  __int64 v142; // [rsp+50h] [rbp-3B8h] BYREF
  __int128 v143; // [rsp+60h] [rbp-3A8h] BYREF
  ULONG v144; // [rsp+70h] [rbp-398h]
  unsigned __int64 v145[20]; // [rsp+78h] [rbp-390h] BYREF
  _QWORD Src[2]; // [rsp+118h] [rbp-2F0h] BYREF
  __int64 v147; // [rsp+128h] [rbp-2E0h] BYREF
  UNICODE_STRING DriverServiceName; // [rsp+130h] [rbp-2D8h] BYREF
  unsigned int v149; // [rsp+140h] [rbp-2C8h]
  int v150; // [rsp+144h] [rbp-2C4h]
  int v151; // [rsp+148h] [rbp-2C0h]
  unsigned int v152; // [rsp+14Ch] [rbp-2BCh]
  unsigned int v153; // [rsp+150h] [rbp-2B8h]
  __int64 v154; // [rsp+158h] [rbp-2B0h]
  int v155; // [rsp+160h] [rbp-2A8h]
  __int128 v156; // [rsp+168h] [rbp-2A0h] BYREF
  _KPROCESS *v157; // [rsp+178h] [rbp-290h]
  __int64 v158; // [rsp+188h] [rbp-280h]
  __int64 v159; // [rsp+190h] [rbp-278h]
  __int64 v160; // [rsp+198h] [rbp-270h]
  __int64 v161; // [rsp+1A0h] [rbp-268h]
  void *v162; // [rsp+1A8h] [rbp-260h]
  __int128 Buf1; // [rsp+1B0h] [rbp-258h] BYREF
  void *v164[2]; // [rsp+1C0h] [rbp-248h] BYREF
  __int128 v165; // [rsp+1D0h] [rbp-238h]
  __int128 v166; // [rsp+1E0h] [rbp-228h]
  __int64 v167; // [rsp+1F0h] [rbp-218h]
  LUID PrivilegeValue[2]; // [rsp+3B0h] [rbp-58h] BYREF

  v3 = a3;
  v6 = 0;
  v136 = 0;
  v143 = 0;
  v142 = 0;
  Src[0] = 0;
  v147 = 0;
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
  v135 = PreviousMode;
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
                v152 = ULongFromUser;
                LOBYTE(v37) = 1;
                PsChangeQuantumTable(v37, ULongFromUser);
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
              if ( !(unsigned __int8)PsIsCurrentThreadInServerSilo(v7, v13, v8) )
              {
                v145[0] = 0;
                if ( (_DWORD)v3 == 16 )
                {
                  if ( PreviousMode )
                    UCharFromUser = RtlReadUCharFromUser((char *)p_Buf1 + 8);
                  else
                    UCharFromUser = *((_BYTE *)p_Buf1 + 8);
                  v136 = UCharFromUser;
                  if ( PreviousMode )
                    ULong64FromUser = RtlReadULong64FromUser(p_Buf1, v20);
                  else
                    ULong64FromUser = *(_QWORD *)p_Buf1;
                  v145[0] = ULong64FromUser;
                }
                else
                {
                  if ( PreviousMode )
                    v23 = RtlReadUCharFromUser((char *)p_Buf1 + 4);
                  else
                    v23 = *((_BYTE *)p_Buf1 + 4);
                  v136 = v23;
                  if ( PreviousMode )
                    v24 = RtlReadULongFromUser(p_Buf1);
                  else
                    v24 = *(_DWORD *)p_Buf1;
                  v145[0] = v24;
                  if ( v24 )
                    v145[0] = MEMORY[0xFFFFF78000000300] * (unsigned __int64)(unsigned int)KeMaximumIncrement / v24;
                }
                if ( v136 )
                  v145[0] = MEMORY[0xFFFFF78000000300];
                ExAcquireTimeRefreshLockExclusive(0xFFFFF78000000300uLL);
                updated = ExpUpdateTimerConfiguration(0, v145, &v136);
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
                      KiIdealDpcRate = (int)v164[0];
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
                  v45 = 0;
                }
                else
                {
                  if ( (_DWORD)v3 != 56 )
                    return 3221225476LL;
                  v45 = 1;
                }
                if ( !PreviousMode )
                {
                  v143 = *p_Buf1;
                  SystemImage = MmLoadSystemImage((unsigned int)&v143, 0, 0, v15, (__int64)&v147, (__int64)&v142);
                  updated = SystemImage;
                  if ( SystemImage < 0 )
                  {
                    if ( SystemImage == -1073741411 )
                      return (unsigned int)-1073741554;
                  }
                  else
                  {
                    if ( v45 )
                    {
                      LOBYTE(v47) = 1;
                      v48 = RtlImageDirectoryEntryToData(v142, v47, 0, &Object);
                    }
                    else
                    {
                      v48 = 0;
                    }
                    v49 = RtlImageNtHeader(v142);
                    v50 = v142 + *(unsigned int *)(v49 + 40);
                    *((_QWORD *)p_Buf1 + 2) = v142;
                    *((_QWORD *)p_Buf1 + 3) = v147;
                    *((_QWORD *)p_Buf1 + 4) = v50;
                    if ( v45 )
                    {
                      *((_QWORD *)p_Buf1 + 5) = v48;
                      *((_DWORD *)p_Buf1 + 12) = *(_DWORD *)(v49 + 80);
                    }
                    else
                    {
                      *((_DWORD *)p_Buf1 + 10) = *(_DWORD *)(v49 + 80);
                    }
                  }
                  return updated;
                }
                return 3221225569LL;
              }
LABEL_198:
              v137[0] = 0;
              if ( (unsigned int)v3 < 0x40 )
                return 3221225476LL;
              if ( a1 == 21 )
              {
                v53 = 0;
              }
              else
              {
                if ( PreviousMode )
                  v53 = RtlReadULongFromUser((char *)p_Buf1 + 60);
                else
                  v53 = *((_DWORD *)p_Buf1 + 15);
                v155 = v53;
                if ( (v53 & 0xFFFFFFF0) != 0 || (v53 & 0xC) == 0xC || (v53 & 3) == 3 )
                  return 3221225712LL;
              }
              if ( SeSinglePrivilegeCheck(SeIncreaseQuotaPrivilege, PreviousMode) )
              {
                if ( PreviousMode )
                  v56 = RtlReadULong64FromUser((char *)p_Buf1 + 24, v54);
                else
                  v56 = *((_QWORD *)p_Buf1 + 3);
                v158 = v56;
                if ( PreviousMode )
                  v57 = RtlReadULong64FromUser(p_Buf1 + 2, v54);
                else
                  v57 = *((_QWORD *)p_Buf1 + 4);
                v159 = v57;
                LOBYTE(v55) = 1;
                return MmAdjustWorkingSetSizeEx(v56, v57, 1, v55, v53, (__int64)v137);
              }
              return 3221225506LL;
            }
            if ( (_DWORD)v3 != 4 )
              return 3221225476LL;
            if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
              return 3221225506LL;
            v140 = 0;
            if ( PreviousMode )
              v18 = RtlReadULongFromUser(p_Buf1);
            else
              v18 = *(_DWORD *)p_Buf1;
            v19 = v18 & 0x92319BF0 | NtGlobalFlag & 0x6DCE640F;
            v140 = v19;
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
          v25 = a1 - 30;
          if ( !v25 )
            return (unsigned int)MmCreateMirror();
          v26 = v25 - 1;
          if ( !v26 )
            return (unsigned int)EtwSetPerformanceTraceInformation(p_Buf1, (unsigned int)v3, PreviousMode);
          v27 = v26 - 3;
          if ( v27 )
          {
            v28 = v27 - 3;
            if ( v28 )
            {
              if ( v28 != 1 )
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
                    v30 = (void *)RtlReadULong64FromUser((char *)p_Buf1 + 8, v29);
                    PrivilegeValue[1] = (LUID)v30;
                    v143 = *(_OWORD *)&PrivilegeValue[0].LowPart;
                    if ( LOWORD(PrivilegeValue[0].LowPart) == 62 )
                    {
                      RtlCopyFromUser(&Buf1, v30, 0x3Eu);
                      if ( !memcmp(&Buf1, L"\\SystemRoot\\System32\\win32k.sys", 0x3Eu) )
                      {
                        *((_QWORD *)&v143 + 1) = L"\\SystemRoot\\System32\\win32k.sys";
                        WORD1(v143) = 62;
                        return ZwSetSystemInformation(38, &v143, 16);
                      }
                    }
                  }
                }
                return 3221225569LL;
              }
              v143 = *p_Buf1;
              if ( !memcmp(*((const void **)p_Buf1 + 1), L"\\SystemRoot\\System32\\win32k.sys", 0x3Eu) )
              {
                v142 = *(_QWORD *)(PsWin32kDataTableEntry + 48);
                v32 = RtlImageNtHeader(v142);
                if ( !v32 )
                {
                  MmUnloadSystemImage(PsWin32kDataTableEntry);
                  return 3221225595LL;
                }
                updated = ExpInitializeSessionDriver(v142 + *(unsigned int *)(v32 + 40));
                if ( (updated & 0x80000000) != 0
                  && !(unsigned int)PsGetSessionIdEx(KeGetCurrentThread()->ApcState.Process) )
                {
                  MmUnloadSystemImage(PsWin32kDataTableEntry);
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
            || (unsigned __int8)PsIsCurrentThreadInServerSilo(v7, v13, v8) )
          {
            return 3221225569LL;
          }
          if ( (_DWORD)v3 == 4 )
          {
            if ( PreviousMode )
            {
              if ( ((unsigned __int8)p_Buf1 & 3) != 0 )
                ExRaiseDatatypeMisalignment();
              v34 = RtlReadULongFromUser(p_Buf1);
            }
            else
            {
              v34 = *(_DWORD *)p_Buf1;
            }
            v151 = v34;
            if ( !v34 )
            {
              v36 = 0;
              return (unsigned int)IoConfigureCrashDump(v36);
            }
            v35 = v34 - 1;
            if ( v35 )
            {
              if ( v35 == 1 )
                return (unsigned int)WheaCrashDumpInitializationComplete();
              return 3221225485LL;
            }
          }
          v36 = 1;
          return (unsigned int)IoConfigureCrashDump(v36);
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
            v39 = (unsigned int)(a1 - 46);
            if ( a1 == 46 )
            {
              if ( (_DWORD)v3 != 8 )
                return 3221225476LL;
              if ( PreviousMode && !SeSinglePrivilegeCheck(SeSystemtimePrivilege, PreviousMode) )
                return 3221225569LL;
              if ( !(unsigned __int8)PsIsCurrentThreadInServerSilo(v39, v13, v8) )
              {
                if ( PreviousMode )
                  v41 = (void *)RtlReadULong64FromUser(p_Buf1, v40);
                else
                  v41 = *(void **)p_Buf1;
                v154 = (__int64)v41;
                if ( v41 )
                {
                  Object = 0;
                  updated = ObReferenceObjectByHandle(
                              v41,
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
          result = VfProbeAndCaptureUnicodeString(&v143, p_Buf1, 1);
          if ( (int)result < 0 )
            return result;
          if ( (_WORD)v143 )
          {
            p_Buf1 = &v143;
LABEL_139:
            v42 = a1 - 40;
            if ( !v42 )
            {
              v43 = VfAddVerifierEntry((PCUNICODE_STRING)p_Buf1);
              goto LABEL_522;
            }
            if ( v42 == 1 )
            {
              v43 = VfRemoveVerifierEntry(p_Buf1, v13);
LABEL_522:
              updated = v43;
              goto LABEL_523;
            }
LABEL_519:
            updated = -1073741821;
LABEL_523:
            if ( !PreviousMode )
              return updated;
            v73 = (char *)p_Buf1;
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
                v44 = RtlReadULongFromUser(p_Buf1);
              else
                v44 = *(_DWORD *)p_Buf1;
              v153 = v44;
              updated = ExpUpdateComPlusPackage(v44);
              if ( (updated & 0x80000000) == 0 )
                *(_DWORD *)(MmWriteableSharedUserData + 736) = v44;
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
      v51 = (unsigned int)(*(_DWORD *)p_Buf1 - 1);
      if ( *(_DWORD *)p_Buf1 == 1
        || (v51 = (unsigned int)(*(_DWORD *)p_Buf1 - 2), *(_DWORD *)p_Buf1 == 2)
        || (v51 = (unsigned int)(*(_DWORD *)p_Buf1 - 3), *(_DWORD *)p_Buf1 == 3) )
      {
        guard_dispatch_icall_no_overrides(v51, 2, v8, v9);
        return 0;
      }
      if ( *(_DWORD *)p_Buf1 == 4 )
        return (unsigned int)-1073741637;
      v52 = (unsigned int)(*(_DWORD *)p_Buf1 - 6);
      if ( *(_DWORD *)p_Buf1 == 6 )
      {
        LODWORD(v52) = 1;
        return (unsigned int)guard_dispatch_icall_no_overrides(v52, 2, v8, v9);
      }
      if ( *(_DWORD *)p_Buf1 == 7 )
      {
        updated = 0;
        if ( (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))off_140E00B38[0] == xKdEnumerateDebuggingDevices )
          return (unsigned int)-1073741822;
        return updated;
      }
      return (unsigned int)-1073741811;
    }
    if ( a1 > 93 )
    {
      if ( a1 > 106 )
      {
        v75 = a1 - 109;
        if ( v75 )
        {
          v76 = v75 - 1;
          if ( !v76 )
            return (unsigned int)-1073741822;
          v77 = v76 - 1;
          if ( !v77 )
          {
            if ( (_DWORD)v3 != 4 )
              return 3221225476LL;
            if ( SeSinglePrivilegeCheck(SeProfileSingleProcessPrivilege, PreviousMode) )
            {
              if ( PreviousMode )
                v78 = RtlReadULongFromUser(p_Buf1);
              else
                v78 = *(_DWORD *)p_Buf1;
              *(_DWORD *)(MmWriteableSharedUserData + 584) = v78;
              return 0;
            }
            return 3221225506LL;
          }
          if ( v77 != 2 )
            return (unsigned int)-1073741821;
          return (unsigned int)PsSetCpuQuotaInformation(p_Buf1, (unsigned int)v3, PreviousMode);
        }
        else
        {
          return (unsigned int)SmSetStoreInformation(v7, p_Buf1, v3, PreviousMode);
        }
      }
      if ( a1 == 106 )
        return (unsigned int)-1073741821;
      v69 = a1 - 94;
      if ( !v69 )
      {
        if ( SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
        {
          if ( (_DWORD)v3 == 8 )
          {
            if ( PreviousMode )
              *(_QWORD *)&Buf1 = RtlReadULong64FromUser(p_Buf1, v74);
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
      v70 = v69 - 1;
      if ( !v70 )
        return 3221225659LL;
      v71 = v70 - 2;
      if ( !v71 )
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
          updated = VfProbeAndCaptureUnicodeStringBuffer(&v164[1], 1);
          if ( (updated & 0x80000000) != 0 )
          {
            v73 = (char *)&Buf1 + 8;
            goto LABEL_525;
          }
          p_Buf1 = &Buf1;
        }
        updated = VfFaultsSetParameters(p_Buf1, v13);
        if ( !PreviousMode )
          return updated;
        VfFreeCapturedUnicodeString((char *)p_Buf1 + 8);
        v73 = (char *)p_Buf1 + 24;
LABEL_525:
        VfFreeCapturedUnicodeString(v73);
        return updated;
      }
      v72 = v71 - 5;
      if ( v72 )
      {
        if ( v72 != 2 )
          return (unsigned int)-1073741821;
        LOBYTE(v8) = PreviousMode;
        return (unsigned int)ExpSetProcessorMicrocodeUpdateInformation(p_Buf1, (unsigned int)v3, v8);
      }
      v68 = 432;
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
              v141 = 6;
              if ( PreviousMode )
                RtlCopyFromUser(&v141, p_Buf1, 4u);
              else
                RtlCopyVolatileMemory(&v141, p_Buf1, 4u);
              LOBYTE(v58) = PreviousMode;
              return (unsigned int)MmIssueMemoryListCommand(v141, v58, -1);
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
          v59 = Object;
          if ( (unsigned __int8)*((_DWORD *)Object + 1) )
          {
            updated = -1073741749;
          }
          else
          {
            KeSetActualBasePriorityThread((ULONG_PTR)Object);
            updated = 259;
          }
          v60 = v59;
LABEL_234:
          ObfDereferenceObject(v60);
          return updated;
        }
        v61 = a1 - 86;
        if ( !v61 )
          return (unsigned int)ObSetRefTraceInformation(p_Buf1);
        v62 = v61 - 1;
        if ( v62 )
        {
          v63 = v62 - 2;
          if ( v63 )
          {
            v64 = v63 - 2;
            if ( v64 )
            {
              if ( v64 != 1 )
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
            v66 = WORD2(Process[3].PerProcessorCycleTimes);
            if ( v66 != 332 && v66 != 452 )
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
              *(_QWORD *)&Buf1 = RtlReadULong64FromUser(p_Buf1, v67);
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
      v68 = 172;
    }
    if ( (_DWORD)v3 != v68 )
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
            return (unsigned int)sub_1409A0F34(v7, (char *)p_Buf1);
          }
          else
          {
            v79 = a1 - 127;
            if ( !v79 )
            {
              if ( (_DWORD)v3 == 16 )
              {
                if ( SeSinglePrivilegeCheck(SeProfileSingleProcessPrivilege, PreviousMode) )
                {
                  if ( PreviousMode )
                    v91 = RtlReadULong64FromUser(p_Buf1, v89);
                  else
                    v91 = *(_QWORD *)p_Buf1;
                  v154 = v91;
                  updated = MmScrubMemory(v90, v91, Src);
                  LODWORD(Object) = updated;
                  v92 = (char *)p_Buf1 + 8;
                  if ( PreviousMode )
                    RtlWriteULong64ToUser(v92, Src[0]);
                  else
                    RtlCopyVolatileMemory(v92, Src, 8u);
                  return updated;
                }
                return 3221225569LL;
              }
              return 3221225476LL;
            }
            v80 = v79 - 2;
            if ( v80 )
            {
              v81 = v80 - 1;
              if ( !v81 )
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
                    updated = MiCombineIdenticalPages(ThreadPartition, Buf1, LODWORD(v164[0]));
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
              v82 = v81 - 1;
              if ( v82 )
              {
                if ( v82 != 1 )
                  return (unsigned int)-1073741821;
                if ( (_DWORD)v3 != 4 )
                  return 3221225476LL;
                *(_QWORD *)&DriverServiceName.Length = 7733364;
                DriverServiceName.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\condrv";
                if ( PreviousMode )
                {
                  v83 = RtlReadULongFromUser(p_Buf1);
                  LODWORD(Buf1) = v83;
                }
                else
                {
                  RtlCopyVolatileMemory(&Buf1, p_Buf1, 4u);
                  LOBYTE(v83) = Buf1;
                }
                if ( (v83 & 1) != 0 )
                {
                  KeEnterCriticalRegion();
                  v84 = KeAbPreAcquire((struct _KTHREAD *)&ExpConDrvLoadLock, 0);
                  v86 = (AutoBoost *)v84;
                  if ( _interlockedbittestandset64((volatile signed __int32 *)&ExpConDrvLoadLock, 0) )
                    ExfAcquirePushLockExclusiveEx(&ExpConDrvLoadLock, v84, &ExpConDrvLoadLock);
                  if ( v86 )
                  {
                    if ( (KiAbpGlobalState & 1) != 0 )
                      AutoBoost::KiAbpPostAcquire(v86, v85);
                    else
                      *((_BYTE *)v86 + 10) = 1;
                  }
                  updated = ZwLoadDriver(&DriverServiceName);
                  if ( (_InterlockedExchangeAdd64((volatile signed __int64 *)&ExpConDrvLoadLock, 0xFFFFFFFFFFFFFFFFuLL)
                      & 6) == 2 )
                    ExfTryToWakePushLock(&ExpConDrvLoadLock);
                  KeAbPostRelease((ULONG_PTR)&ExpConDrvLoadLock);
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
        v93 = a1 - 142;
        if ( !v93 )
        {
          if ( (_DWORD)v3 == 72 || (_DWORD)v3 == 48 )
          {
            if ( SeSinglePrivilegeCheck(SeShutdownPrivilege, PreviousMode) )
            {
              RtlCopyFromUser(&Buf1, p_Buf1, v3);
              Pool2 = (void *)ExAllocatePool2(64, LOWORD(v164[0]), 1347639365);
              v101 = Pool2;
              PrivilegeValue[0] = (LUID)Pool2;
              if ( !Pool2 )
                return 3221225626LL;
              RtlCopyFromUser(Pool2, v164[1], LOWORD(v164[0]));
              v164[1] = v101;
              CurrentServerSiloGlobals = PsGetCurrentServerSiloGlobals(v103, v102);
              if ( _InterlockedCompareExchange((volatile signed __int32 *)(CurrentServerSiloGlobals + 1376), Buf1, 0) )
              {
                ExFreePoolWithTag(v101, 0x50535845u);
                return 0;
              }
              *(_OWORD *)(CurrentServerSiloGlobals + 1376) = Buf1;
              *(_OWORD *)(CurrentServerSiloGlobals + 1392) = *(_OWORD *)v164;
              *(_OWORD *)(CurrentServerSiloGlobals + 1408) = v165;
              *(_OWORD *)(CurrentServerSiloGlobals + 1424) = v166;
              *(_QWORD *)(CurrentServerSiloGlobals + 1440) = v167;
              return 0;
            }
            return 3221225569LL;
          }
          return 3221225476LL;
        }
        v94 = v93 - 8;
        if ( !v94 )
        {
          if ( !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
            return 3221225569LL;
          return (unsigned int)ExpSetBootLoaderMetadata(p_Buf1, (unsigned int)v3);
        }
        v95 = v94 - 1;
        if ( !v95 )
        {
          PrivilegeValue[0] = (LUID)19LL;
          if ( !SeSinglePrivilegeCheck((LUID)19LL, PreviousMode) )
            return 3221225569LL;
          v97 = v3 - 1;
          if ( v97 )
          {
            if ( v97 != 3 )
              return 3221225476LL;
            if ( PreviousMode )
              v98 = RtlReadULongFromUser(p_Buf1);
            else
              v98 = *(_DWORD *)p_Buf1;
            v149 = v98;
          }
          else
          {
            if ( PreviousMode )
              v99 = RtlReadUCharFromUser(p_Buf1);
            else
              v99 = *(_BYTE *)p_Buf1;
            v139 = v99;
            if ( v99 && !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
              return 3221225569LL;
            v98 = v99 != 0 ? 1 : 5;
          }
          return (unsigned int)ExpSetSoftRebootFlags(v98);
        }
        v96 = v95 - 1;
        if ( v96 )
        {
          if ( v96 != 3 )
            return (unsigned int)-1073741821;
          return (unsigned int)CmReconcileAndValidateAllHives(v7, 2);
        }
        if ( (_DWORD)v3 != 8 )
          return 3221225476LL;
        if ( PreviousMode )
        {
          v160 = RtlReadULong64FromUser(p_Buf1, 2);
          return (unsigned int)ExpQueryElamCertInfo(v160);
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
            updated = PsSetExeModerationState(&Buf1, LODWORD(v164[0]), HIDWORD(v164[0]));
            v73 = (char *)&Buf1;
            goto LABEL_525;
          }
          return result;
        }
        if ( a1 != 190 )
        {
          v119 = (unsigned int)(a1 - 191);
          if ( a1 == 191 )
          {
            if ( !(_DWORD)v3 )
            {
              if ( PreviousMode && !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
                return 3221225569LL;
              return (unsigned int)VslRelaxQuotas(v119, v13);
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
          v156 = 0;
          v157 = 0;
          if ( (_DWORD)v3 != 8 )
          {
            if ( (_DWORD)v3 )
              return 3221225476LL;
            updated = 0;
            v118 = KeGetCurrentThread()->ApcState.Process;
            LODWORD(Object) = PsGetSessionIdEx(v118);
            if ( (_DWORD)Object == -1 )
              return updated;
            v157 = v118;
            return (unsigned int)PsInvokeWin32Callout(32, &v156, 1, &Object);
          }
          if ( !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
            return 3221225569LL;
          if ( PreviousMode )
            v116 = (void *)RtlReadULong64FromUser(p_Buf1, v115);
          else
            v116 = *(void **)p_Buf1;
          v162 = v116;
          PrivilegeValue[0] = 0;
          updated = ObReferenceObjectByHandle(
                      v116,
                      0x1000u,
                      (POBJECT_TYPE)PsProcessType,
                      PreviousMode,
                      (PVOID *)PrivilegeValue,
                      0);
          if ( (updated & 0x80000000) != 0 )
            return updated;
          v117 = PrivilegeValue[0];
          LODWORD(Object) = PsGetSessionIdEx(*(_QWORD *)PrivilegeValue);
          if ( (_DWORD)Object != -1 )
          {
            v157 = (_KPROCESS *)v117;
            updated = PsInvokeWin32Callout(32, &v156, 1, &Object);
          }
          v60 = (void *)v117;
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
              v105 = v3 - 8;
              if ( (v105 & 7) != 0 || v105 > 0x200 )
                return 3221225476LL;
              if ( PreviousMode )
                v106 = RtlReadULong64FromUser(p_Buf1, 2);
              else
                v106 = *(_QWORD *)p_Buf1;
              v161 = v106;
              v107 = (char *)p_Buf1 + 8;
              if ( PreviousMode )
                RtlCopyFromUser(&Buf1, v107, v105);
              else
                RtlCopyVolatileMemory(&Buf1, v107, v105);
              LOBYTE(v109) = PreviousMode;
              updated = ExCpuSetResourceManagerAccessCheck(v109, v108);
              if ( (updated & 0x80000000) != 0 )
                return updated;
              return (unsigned int)KeSetTagCpuSets(v105 >> 3, &Buf1, v106);
            }
          }
          if ( (v3 & 7) != 0 || (unsigned int)v3 > 0x200 )
            return 3221225476LL;
          if ( PreviousMode )
            RtlCopyFromUser(&Buf1, p_Buf1, v3);
          else
            RtlCopyVolatileMemory(&Buf1, p_Buf1, v3);
          LOBYTE(v111) = PreviousMode;
          result = ExCpuSetResourceManagerAccessCheck(v111, v110);
          if ( (int)result >= 0 )
          {
            v113 = (unsigned int)v3 >> 3;
            v114 = 0;
            return (unsigned int)KeModifySystemAllowedCpuSets(v113, (unsigned int)&Buf1, v112, v114);
          }
          return result;
        }
      }
    }
LABEL_507:
    if ( qword_140EF3020 )
      return (unsigned int)guard_dispatch_icall_no_overrides((unsigned int)a1, p_Buf1, (unsigned int)v3, v9);
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
            LOBYTE(v132) = (_DWORD)v3 == 0;
            return (unsigned int)VfPtGenerateTraceInformation(v132);
          case 228:
          case 229:
            v135 = 0;
            if ( (int)RtlCheckTokenMembership(0, SeAliasAdminsSid, &v135, v9) < 0 || !v135 )
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
          v134 = RtlReadULongFromUser(p_Buf1);
        else
          v134 = *(_DWORD *)p_Buf1;
        v150 = v134;
        ExResourceTimeoutCount = (v134 + 3999) / 0xFA0u;
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
            v133 = RtlReadULongFromUser(p_Buf1);
          else
            v133 = *(_DWORD *)p_Buf1;
          LODWORD(Buf1) = v133;
          PspBreakOnContextUnwindFailure = v133;
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
          result = VfProbeAndCaptureUnicodeString(&v143, p_Buf1, 1);
          if ( (int)result < 0 )
            return result;
          if ( !(_WORD)v143 )
            return 3221225711LL;
          p_Buf1 = &v143;
        }
        v131 = a1 - 219;
        if ( !v131 )
        {
          v43 = VfVolatileApplyDifVerification(p_Buf1, v13);
          goto LABEL_522;
        }
        if ( v131 == 1 )
        {
          v43 = VfVolatileRemoveDifVerification(p_Buf1, v13);
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
  v120 = a1 - 204;
  if ( !v120 )
  {
    if ( (unsigned int)v3 < 8 )
      return 3221225476LL;
    v126 = v3 - 8;
    if ( (v126 & 7) != 0 || v126 > 0x200 )
      return 3221225476LL;
    if ( PreviousMode )
      v127 = RtlReadULong64FromUser(p_Buf1, 2);
    else
      v127 = *(_QWORD *)p_Buf1;
    PrivilegeValue[0] = (LUID)v127;
    v128 = (char *)p_Buf1 + 8;
    if ( PreviousMode )
      RtlCopyFromUser(&Buf1, v128, v126);
    else
      RtlCopyVolatileMemory(&Buf1, v128, v126);
    v130 = 2;
    if ( v127 >= 2 )
      return 3221225485LL;
    LOBYTE(v130) = PreviousMode;
    updated = ExCpuSetResourceManagerAccessCheck(v130, v129);
    if ( (updated & 0x80000000) != 0 )
      return updated;
    v114 = v127;
    v113 = v126 >> 3;
    return (unsigned int)KeModifySystemAllowedCpuSets(v113, (unsigned int)&Buf1, v112, v114);
  }
  v121 = v120 - 2;
  if ( v121 )
  {
    v122 = v121 - 1;
    if ( v122 )
    {
      v123 = v122 - 3;
      if ( v123 )
      {
        if ( v123 != 2 )
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
    v144 = 0;
    if ( PreviousMode )
      v124 = RtlReadULongFromUser(p_Buf1);
    else
      v124 = *(_DWORD *)p_Buf1;
    v144 = v124;
    if ( (v124 & 0x2018) == 0 )
    {
      v19 = v124 | NtGlobalFlag2 & 0x2018;
      v144 = v19;
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
  if ( (unsigned __int8)PsIsCurrentThreadInServerSilo(v7, v13, v8) )
    return 3221225506LL;
  if ( PreviousMode )
    *(_QWORD *)&Buf1 = RtlReadULong64FromUser(p_Buf1, v125);
  else
    RtlCopyVolatileMemory(&Buf1, p_Buf1, 8u);
  v136 = (_BYTE)Buf1 != 0;
  result = ExSetLeapSecondEnabled();
  updated = result;
  if ( (int)result >= 0 )
  {
    *(_BYTE *)ExLeapSecondData = v136;
    return updated;
  }
  return result;
}

```

## disassembly

```asm
0x1409ff3f0  push    rbx
0x1409ff3f2  push    rsi
0x1409ff3f3  push    rdi
0x1409ff3f4  push    r12
0x1409ff3f6  push    r13
0x1409ff3f8  push    r14
0x1409ff3fa  push    r15
0x1409ff3fc  sub     rsp, 3D0h
0x1409ff403  mov     rax, cs:__security_cookie
0x1409ff40a  xor     rax, rsp
0x1409ff40d  mov     [rsp+408h+var_48], rax
0x1409ff415  mov     r13d, r8d
0x1409ff418  mov     r14, rdx
0x1409ff41b  mov     esi, ecx
0x1409ff41d  xor     edi, edi
0x1409ff41f  mov     [rsp+408h+var_3D7], dil
0x1409ff424  xorps   xmm0, xmm0
0x1409ff427  movups  [rsp+408h+var_3A8], xmm0
0x1409ff42c  mov     [rsp+408h+var_3B8], rdi
0x1409ff431  mov     [rsp+408h+Src], rdi
0x1409ff439  mov     [rsp+408h+var_2E0], rdi
0x1409ff441  mov     [rsp+408h+var_3D0], rdi
0x1409ff446  xor     edx, edx; Val
0x1409ff448  mov     r8d, 200h; Size
0x1409ff44e  lea     rcx, [rsp+408h+Buf1]; void *
0x1409ff456  call    memset_0
0x1409ff45b  mov     rax, gs:188h
0x1409ff464  mov     r15b, [rax+232h]
0x1409ff46b  test    r15b, r15b
0x1409ff46e  jz      short loc_1409FF4D2
0x1409ff470  cmp     esi, 59h ; 'Y'
0x1409ff473  jnz     short loc_1409FF47F
0x1409ff475  lea     r8d, [rdi+2]
0x1409ff479  lea     r12d, [rdi+1]
0x1409ff47d  jmp     short loc_1409FF4BB
0x1409ff47f  cmp     esi, 97h
0x1409ff485  jnz     short loc_1409FF4AF
0x1409ff487  cmp     esi, 0CCh
0x1409ff48d  jz      short loc_1409FF4AF
0x1409ff48f  cmp     esi, 0D2h
0x1409ff495  jz      short loc_1409FF4AF
0x1409ff497  cmp     esi, 0D4h
0x1409ff49d  jz      short loc_1409FF4AF
0x1409ff49f  mov     r12d, 1
0x1409ff4a5  cmp     r13d, r12d
0x1409ff4a8  jnz     short loc_1409FF4B5
0x1409ff4aa  mov     r8d, r12d
0x1409ff4ad  jmp     short loc_1409FF4BB
0x1409ff4af  mov     r12d, 1
0x1409ff4b5  mov     r8d, 4; Alignment
0x1409ff4bb  mov     rdx, r13; Length
0x1409ff4be  mov     rcx, r14; Address
0x1409ff4c1  call    ProbeForRead
0x1409ff4c6  mov     edx, 2
0x1409ff4cb  jmp     short loc_1409FF4DB
0x1409ff4cd  jmp     loc_140A013C3
0x1409ff4d2  mov     edx, 2
0x1409ff4d7  lea     r12d, [rdx-1]
0x1409ff4db  mov     [rsp+408h+var_3D8], r15b
0x1409ff4e0  mov     ebx, edi
0x1409ff4e2  cmp     esi, 7Eh ; '~'
0x1409ff4e5  jg      loc_140A004E8
0x1409ff4eb  jz      loc_140A004C8
0x1409ff4f1  cmp     esi, 48h ; 'H'
0x1409ff4f4  jg      loc_1409FFE71
0x1409ff4fa  jz      loc_1409FFDD1
0x1409ff500  cmp     esi, 27h ; '''
0x1409ff503  jg      loc_1409FFACC
0x1409ff509  jz      loc_1409FFA7C
0x1409ff50f  cmp     esi, 1Ch
0x1409ff512  jg      loc_1409FF7D0
0x1409ff518  jz      loc_1409FF6C5
0x1409ff51e  mov     r9d, r12d
0x1409ff521  mov     ecx, esi
0x1409ff523  sub     ecx, 9
0x1409ff526  jz      loc_1409FF642
0x1409ff52c  sub     ecx, 0Ch
0x1409ff52f  jz      loc_1409FFEBE
0x1409ff535  sub     ecx, 3
0x1409ff538  jz      short loc_1409FF578
0x1409ff53a  sub     ecx, edx
0x1409ff53c  jz      loc_1409FFCE8
0x1409ff542  cmp     ecx, 1
0x1409ff545  jnz     loc_140A0042F
0x1409ff54b  cmp     r13d, 8
0x1409ff54f  jnz     loc_140A0130D
0x1409ff555  test    r15b, r15b
0x1409ff558  jnz     loc_140A0132A
0x1409ff55e  mov     rcx, [r14]
0x1409ff561  mov     [rsp+408h+var_288], rcx
0x1409ff569  call    MmUnloadSystemImage
0x1409ff56e  jmp     loc_1409FFAC0
0x1409ff573  jmp     loc_140A013C3
0x1409ff578  mov     esi, 14h
0x1409ff57d  cmp     r13d, esi
0x1409ff580  jnz     loc_140A0130D
0x1409ff586  test    r15b, r15b
0x1409ff589  jz      short loc_1409FF5A2
0x1409ff58b  mov     dl, r15b; PreviousMode
0x1409ff58e  mov     rcx, qword ptr cs:SeLoadDriverPrivilege.LowPart; PrivilegeValue
0x1409ff595  call    SeSinglePrivilegeCheck
0x1409ff59a  test    al, al
0x1409ff59c  jz      loc_140A0132A
0x1409ff5a2  mov     r8, rsi; Size
0x1409ff5a5  mov     rdx, r14; Src
0x1409ff5a8  lea     rcx, [rsp+408h+Buf1]; void *
0x1409ff5b0  test    r15b, r15b
0x1409ff5b3  jz      short loc_1409FF5BC
0x1409ff5b5  call    RtlCopyFromUser
0x1409ff5ba  jmp     short loc_1409FF5C2
0x1409ff5bc  call    RtlCopyVolatileMemory
0x1409ff5c1  nop
0x1409ff5c2  mov     eax, dword ptr [rsp+408h+Buf1+4]
0x1409ff5c9  mov     cs:KiMaximumDpcQueueDepth, eax
0x1409ff5cf  mov     eax, dword ptr [rsp+408h+Buf1+8]
0x1409ff5d6  mov     cs:KiMinimumDpcRate, eax
0x1409ff5dc  mov     eax, dword ptr [rsp+408h+Buf1+0Ch]
0x1409ff5e3  mov     cs:KiAdjustDpcThreshold, eax
0x1409ff5e9  mov     eax, dword ptr [rsp+408h+var_248]
0x1409ff5f0  mov     cs:KiIdealDpcRate, eax
0x1409ff5f6  call    KeSynchronizeWithDynamicProcessors
0x1409ff5fb  mov     ecx, 0FFFFh; GroupNumber
0x1409ff600  call    KeQueryActiveProcessorCountEx
0x1409ff605  test    eax, eax
0x1409ff607  jz      loc_140A013C1
0x1409ff60d  mov     ecx, edi
0x1409ff60f  lea     rdx, KiProcessorBlock
0x1409ff616  mov     rdx, [rdx+rcx*8]
0x1409ff61a  mov     ecx, cs:KiMaximumDpcQueueDepth
0x1409ff620  mov     [rdx+0CE8h], ecx
0x1409ff626  mov     ecx, cs:KiMinimumDpcRate
0x1409ff62c  mov     [rdx+0CF0h], ecx
0x1409ff632  inc     edi
0x1409ff634  cmp     edi, eax
0x1409ff636  jb      short loc_1409FF60D
0x1409ff638  jmp     loc_140A013C1
0x1409ff63d  jmp     loc_140A013C3
0x1409ff642  cmp     r13d, 4
0x1409ff646  jnz     loc_140A0130D
0x1409ff64c  mov     dl, r15b; PreviousMode
0x1409ff64f  mov     rcx, qword ptr cs:SeDebugPrivilege.LowPart; PrivilegeValue
0x1409ff656  call    SeSinglePrivilegeCheck
0x1409ff65b  test    al, al
0x1409ff65d  jz      loc_140A011FE
0x1409ff663  mov     [rsp+408h+var_3C4], edi
0x1409ff667  test    r15b, r15b
0x1409ff66a  jz      short loc_1409FF678
0x1409ff66c  mov     rcx, r14
0x1409ff66f  call    RtlReadULongFromUser
0x1409ff674  mov     ecx, eax
0x1409ff676  jmp     short loc_1409FF67B
0x1409ff678  mov     ecx, [r14]
0x1409ff67b  mov     [rsp+408h+var_3C4], ecx
0x1409ff67f  and     ecx, 92319BF0h
0x1409ff685  mov     [rsp+408h+var_3C4], ecx
0x1409ff689  mov     eax, cs:NtGlobalFlag
0x1409ff68f  and     eax, 6DCE640Fh
0x1409ff694  or      eax, ecx
0x1409ff696  mov     [rsp+408h+var_3C4], eax
0x1409ff69a  mov     cs:NtGlobalFlag, eax
0x1409ff6a0  test    r15b, r15b
0x1409ff6a3  jz      short loc_1409FF6B1
0x1409ff6a5  mov     edx, eax
0x1409ff6a7  mov     rcx, r14
0x1409ff6aa  call    RtlWriteULongToUser
0x1409ff6af  jmp     short loc_1409FF6B4
0x1409ff6b1  mov     [r14], eax
0x1409ff6b4  jmp     loc_140A013C1
0x1409ff6b9  mov     ebx, eax
0x1409ff6bb  jmp     loc_140A013C1
0x1409ff6c0  jmp     loc_140A013C3
0x1409ff6c5  lea     eax, [r13-8]
0x1409ff6c9  test    eax, 0FFFFFFF7h
0x1409ff6ce  jnz     loc_140A0130D
0x1409ff6d4  test    r15b, r15b
0x1409ff6d7  jz      short loc_1409FF6F0
0x1409ff6d9  mov     dl, r15b; PreviousMode
0x1409ff6dc  mov     rcx, qword ptr cs:SeSystemtimePrivilege.LowPart; PrivilegeValue
0x1409ff6e3  call    SeSinglePrivilegeCheck
0x1409ff6e8  test    al, al
0x1409ff6ea  jz      loc_140A0132A
0x1409ff6f0  call    PsIsCurrentThreadInServerSilo
0x1409ff6f5  test    al, al
0x1409ff6f7  jnz     loc_140A011FE
0x1409ff6fd  mov     [rsp+408h+var_390], rdi
0x1409ff702  cmp     r13d, 10h
0x1409ff706  jnz     short loc_1409FF772
0x1409ff708  test    r15b, r15b
0x1409ff70b  jz      short loc_1409FF718
0x1409ff70d  lea     rcx, [r14+8]
0x1409ff711  call    RtlReadUCharFromUser
0x1409ff716  jmp     short loc_1409FF71C
0x1409ff718  mov     al, [r14+8]
0x1409ff71c  mov     [rsp+408h+var_3D7], al
0x1409ff720  test    r15b, r15b
0x1409ff723  jz      short loc_1409FF72F
0x1409ff725  mov     rcx, r14
0x1409ff728  call    RtlReadULong64FromUser
0x1409ff72d  jmp     short loc_1409FF732
0x1409ff72f  mov     rax, [r14]
0x1409ff732  mov     [rsp+408h+var_390], rax
0x1409ff737  mov     rcx, 0FFFFF78000000300h
0x1409ff741  cmp     [rsp+408h+var_3D7], dil
0x1409ff746  jz      short loc_1409FF750
0x1409ff748  mov     rax, [rcx]
0x1409ff74b  mov     [rsp+408h+var_390], rax
0x1409ff750  call    ExAcquireTimeRefreshLockExclusive
0x1409ff755  lea     r8, [rsp+408h+var_3D7]
0x1409ff75a  lea     rdx, [rsp+408h+var_390]
0x1409ff75f  xor     ecx, ecx
0x1409ff761  call    ExpUpdateTimerConfiguration
0x1409ff766  mov     ebx, eax
0x1409ff768  call    ExReleaseTimeRefreshLockExclusive
0x1409ff76d  jmp     loc_140A013C1
0x1409ff772  test    r15b, r15b
0x1409ff775  jz      short loc_1409FF782
0x1409ff777  lea     rcx, [r14+4]
0x1409ff77b  call    RtlReadUCharFromUser
0x1409ff780  jmp     short loc_1409FF786
0x1409ff782  mov     al, [r14+4]
0x1409ff786  mov     [rsp+408h+var_3D7], al
0x1409ff78a  test    r15b, r15b
0x1409ff78d  jz      short loc_1409FF799
0x1409ff78f  mov     rcx, r14
0x1409ff792  call    RtlReadULongFromUser
0x1409ff797  jmp     short loc_1409FF79C
0x1409ff799  mov     eax, [r14]
0x1409ff79c  mov     r8d, eax
0x1409ff79f  mov     [rsp+408h+var_390], r8
0x1409ff7a4  test    eax, eax
0x1409ff7a6  jz      short loc_1409FF737
0x1409ff7a8  mov     eax, cs:KeMaximumIncrement
0x1409ff7ae  mov     rcx, 0FFFFF78000000300h
0x1409ff7b8  imul    rax, [rcx]
0x1409ff7bc  xor     edx, edx
0x1409ff7be  div     r8
0x1409ff7c1  mov     [rsp+408h+var_390], rax
0x1409ff7c6  jmp     loc_1409FF741
0x1409ff7cb  jmp     loc_140A013C3
0x1409ff7d0  sub     esi, 1Eh
0x1409ff7d3  jz      loc_1409FFA72
0x1409ff7d9  sub     esi, 1
0x1409ff7dc  jz      loc_1409FFA5F
0x1409ff7e2  mov     r12d, 3
0x1409ff7e8  sub     esi, r12d
0x1409ff7eb  jz      loc_1409FF9CF
0x1409ff7f1  sub     esi, r12d
0x1409ff7f4  jz      loc_1409FF99C
0x1409ff7fa  cmp     esi, 1
0x1409ff7fd  jnz     loc_140A0042F
0x1409ff803  cmp     r13d, 10h
0x1409ff807  jnz     loc_140A0130D
0x1409ff80d  test    r15b, r15b
0x1409ff810  jz      loc_1409FF8FD
0x1409ff816  mov     rax, gs:188h
0x1409ff81f  mov     rcx, [rax+0B8h]
0x1409ff826  mov     eax, [rcx+7DCh]
0x1409ff82c  test    al, 8
0x1409ff82e  jz      loc_140A0132A
0x1409ff834  mov     dl, sil; PreviousMode
0x1409ff837  mov     rcx, qword ptr cs:SeLoadDriverPrivilege.LowPart; PrivilegeValue
0x1409ff83e  call    SeSinglePrivilegeCheck
0x1409ff843  test    al, al
0x1409ff845  jz      loc_140A0132A
0x1409ff84b  xorps   xmm0, xmm0
0x1409ff84e  movups  xmmword ptr [rsp+408h+PrivilegeValue.LowPart], xmm0
0x1409ff856  mov     rcx, r14
0x1409ff859  call    RtlReadULongFromUser
0x1409ff85e  mov     [rsp+408h+PrivilegeValue.LowPart], eax
0x1409ff865  lea     rcx, [r14+8]
0x1409ff869  call    RtlReadULong64FromUser
0x1409ff86e  mov     qword ptr [rsp+408h+PrivilegeValue.LowPart+8], rax
0x1409ff876  movaps  xmm0, xmmword ptr [rsp+408h+PrivilegeValue.LowPart]
0x1409ff87e  movdqa  [rsp+408h+var_3A8], xmm0
0x1409ff884  mov     ebx, 3Eh ; '>'
0x1409ff889  cmp     word ptr [rsp+408h+PrivilegeValue.LowPart], bx
0x1409ff891  jnz     loc_140A0132A
0x1409ff897  movzx   r8d, word ptr [rsp+408h+PrivilegeValue.LowPart]; Size
0x1409ff8a0  mov     rdx, rax; Src
0x1409ff8a3  lea     rcx, [rsp+408h+Buf1]; void *
0x1409ff8ab  call    RtlCopyFromUser
0x1409ff8b0  nop
0x1409ff8b1  mov     r8, rbx; Size
0x1409ff8b4  lea     rsi, aSystemrootSyst_24; "\\SystemRoot\\System32\\win32k.sys"
0x1409ff8bb  mov     rdx, rsi; Buf2
0x1409ff8be  lea     rcx, [rsp+408h+Buf1]; Buf1
0x1409ff8c6  call    memcmp
0x1409ff8cb  test    eax, eax
0x1409ff8cd  jnz     loc_140A0132A
0x1409ff8d3  mov     qword ptr [rsp+408h+var_3A8+8], rsi
0x1409ff8d8  mov     word ptr [rsp+408h+var_3A8+2], bx
0x1409ff8dd  lea     r8d, [rax+10h]
0x1409ff8e1  lea     rdx, [rsp+408h+var_3A8]
0x1409ff8e6  lea     ecx, [rax+26h]
0x1409ff8e9  call    ZwSetSystemInformation
0x1409ff8ee  jmp     loc_140A013C3
0x1409ff8f3  jmp     loc_140A013C3
0x1409ff8f8  jmp     loc_140A013C3
0x1409ff8fd  movups  xmm0, xmmword ptr [r14]
0x1409ff901  movaps  [rsp+408h+var_3A8], xmm0
  ... truncated ...
```
