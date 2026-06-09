# NtSetSystemInformation

- ea: `0x1409ff3f0`
- end: `0x140a013e7`
- name: `NtSetSystemInformation`
- size: `8183`
- prototype: `__int64 __fastcall(int, __int64 p_Buf1, unsigned int)`
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
__int64 __fastcall NtSetSystemInformation(int a1, __int64 p_Buf1, unsigned int a3)
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
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  ULONG ActiveProcessorCount; // eax
  __int64 v21; // rdx
  unsigned int v22; // ecx
  ULONG v23; // eax
  char UCharFromUser; // al
  __int64 ULong64FromUser; // rax
  char v26; // al
  unsigned int v27; // eax
  int v28; // esi
  int v29; // esi
  int v30; // esi
  int v31; // esi
  void *v32; // rax
  __int64 result; // rax
  __int64 v34; // rax
  int v36; // ecx
  int v37; // ecx
  __int64 v38; // rcx
  __int64 v39; // rcx
  unsigned int ULongFromUser; // eax
  __int64 v41; // rcx
  void *v42; // rax
  int v43; // esi
  unsigned int v44; // eax
  unsigned int v45; // esi
  char v46; // si
  int SystemImage; // eax
  __int64 v48; // rdx
  __int64 v49; // r15
  __int64 v50; // rax
  __int64 v51; // r8
  __int64 v52; // rcx
  __int64 v53; // rcx
  int v54; // ebx
  unsigned __int64 v55; // r13
  unsigned __int64 v56; // rdx
  __int64 v57; // rdx
  PVOID v58; // rsi
  void *v59; // rcx
  int v60; // esi
  int v61; // esi
  int v62; // esi
  int v63; // esi
  _KPROCESS *Process; // rcx
  __int16 v65; // ax
  int v66; // ebx
  int v67; // esi
  int v68; // esi
  int v69; // esi
  int v70; // esi
  char *v71; // rcx
  int v72; // esi
  int v73; // esi
  int v74; // esi
  unsigned int v75; // ecx
  int v76; // esi
  int v77; // esi
  int v78; // esi
  int v79; // esi
  int v80; // eax
  LegacyAutoBoost *v81; // rax
  void *v82; // rdx
  LegacyAutoBoost *v83; // rbx
  ULONG *ThreadPartition; // rax
  __int64 v86; // rdx
  ULONG_PTR v87; // r9
  __int64 v88; // rcx
  ULONG_PTR v89; // rax
  void *v90; // rcx
  int v91; // esi
  int v92; // esi
  int v93; // esi
  int v94; // esi
  int v95; // r13d
  unsigned int v96; // eax
  char v97; // bl
  void *Pool2; // rax
  void *v99; // rbx
  __int64 v100; // rdx
  __int64 v101; // rcx
  __int64 CurrentServerSiloGlobals; // r8
  unsigned int v103; // r13d
  __int64 v104; // rsi
  void *v105; // rdx
  __int64 v106; // rdx
  __int64 v107; // rcx
  __int64 v108; // rdx
  __int64 v109; // rcx
  int v110; // r8d
  unsigned int v111; // r13d
  int v112; // r9d
  void *v113; // rax
  LUID v114; // rdi
  _KPROCESS *v115; // rdi
  __int64 v116; // rcx
  int v117; // esi
  int v118; // esi
  int v119; // esi
  int v120; // esi
  ULONG v121; // ecx
  unsigned int v122; // r13d
  unsigned __int64 v123; // rsi
  void *v124; // rdx
  __int64 v125; // rdx
  __int64 v126; // rcx
  int v127; // esi
  int v128; // eax
  int v129; // eax
  PVOID *Object; // [rsp+20h] [rbp-3E8h]
  KPROCESSOR_MODE v131; // [rsp+30h] [rbp-3D8h] BYREF
  bool v132; // [rsp+31h] [rbp-3D7h] BYREF
  char v133[6]; // [rsp+32h] [rbp-3D6h] BYREF
  PVOID v134; // [rsp+38h] [rbp-3D0h] BYREF
  char v135; // [rsp+40h] [rbp-3C8h]
  ULONG v136; // [rsp+44h] [rbp-3C4h]
  unsigned int v137; // [rsp+48h] [rbp-3C0h] BYREF
  __int64 v138; // [rsp+50h] [rbp-3B8h] BYREF
  __int128 v139; // [rsp+60h] [rbp-3A8h] BYREF
  ULONG v140; // [rsp+70h] [rbp-398h]
  unsigned __int64 v141[20]; // [rsp+78h] [rbp-390h] BYREF
  _QWORD Src[2]; // [rsp+118h] [rbp-2F0h] BYREF
  __int64 v143; // [rsp+128h] [rbp-2E0h] BYREF
  UNICODE_STRING DriverServiceName; // [rsp+130h] [rbp-2D8h] BYREF
  unsigned int v145; // [rsp+140h] [rbp-2C8h]
  int v146; // [rsp+144h] [rbp-2C4h]
  int v147; // [rsp+148h] [rbp-2C0h]
  unsigned int v148; // [rsp+14Ch] [rbp-2BCh]
  unsigned int v149; // [rsp+150h] [rbp-2B8h]
  ULONG_PTR v150; // [rsp+158h] [rbp-2B0h]
  int v151; // [rsp+160h] [rbp-2A8h]
  __int128 v152; // [rsp+168h] [rbp-2A0h] BYREF
  _KPROCESS *v153; // [rsp+178h] [rbp-290h]
  unsigned __int64 v154; // [rsp+188h] [rbp-280h]
  unsigned __int64 v155; // [rsp+190h] [rbp-278h]
  __int64 v156; // [rsp+198h] [rbp-270h]
  __int64 v157; // [rsp+1A0h] [rbp-268h]
  void *v158; // [rsp+1A8h] [rbp-260h]
  __int128 Buf1; // [rsp+1B0h] [rbp-258h] BYREF
  void *v160[2]; // [rsp+1C0h] [rbp-248h] BYREF
  __int128 v161; // [rsp+1D0h] [rbp-238h]
  __int128 v162; // [rsp+1E0h] [rbp-228h]
  __int64 v163; // [rsp+1F0h] [rbp-218h]
  LUID PrivilegeValue[2]; // [rsp+3B0h] [rbp-58h] BYREF

  v3 = a3;
  v6 = 0;
  v132 = 0;
  v139 = 0;
  v138 = 0;
  Src[0] = 0;
  v143 = 0;
  v134 = 0;
  memset_0(&Buf1, 0, 0x200u);
  PreviousMode = KeGetCurrentThread()->PreviousMode;
  if ( PreviousMode )
  {
    if ( a1 == 89 )
    {
      v11 = 2;
      v12 = 1;
LABEL_9:
      ProbeForRead((volatile void *)p_Buf1, v3, v11);
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
  v131 = PreviousMode;
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
                v148 = ULongFromUser;
                LOBYTE(v39) = 1;
                PsChangeQuantumTable(v39, ULongFromUser);
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
                v141[0] = 0;
                if ( (_DWORD)v3 == 16 )
                {
                  if ( PreviousMode )
                    UCharFromUser = RtlReadUCharFromUser(p_Buf1 + 8);
                  else
                    UCharFromUser = *(_BYTE *)(p_Buf1 + 8);
                  v132 = UCharFromUser;
                  if ( PreviousMode )
                    ULong64FromUser = RtlReadULong64FromUser(p_Buf1);
                  else
                    ULong64FromUser = *(_QWORD *)p_Buf1;
                  v141[0] = ULong64FromUser;
                }
                else
                {
                  if ( PreviousMode )
                    v26 = RtlReadUCharFromUser(p_Buf1 + 4);
                  else
                    v26 = *(_BYTE *)(p_Buf1 + 4);
                  v132 = v26;
                  if ( PreviousMode )
                    v27 = RtlReadULongFromUser(p_Buf1);
                  else
                    v27 = *(_DWORD *)p_Buf1;
                  v141[0] = v27;
                  if ( v27 )
                    v141[0] = MEMORY[0xFFFFF78000000300] * (unsigned __int64)(unsigned int)KeMaximumIncrement / v27;
                }
                if ( v132 )
                  v141[0] = MEMORY[0xFFFFF78000000300];
                ExAcquireTimeRefreshLockExclusive(0xFFFFF78000000300uLL);
                updated = ExpUpdateTimerConfiguration(0, v141, (char *)&v132);
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
                        RtlCopyFromUser(&Buf1, (void *)p_Buf1, 0x14u);
                      else
                        RtlCopyVolatileMemory(&Buf1, (const void *)p_Buf1, 0x14u);
                      KiMinimumDpcRate = DWORD2(Buf1);
                      KiMaximumDpcQueueDepth = DWORD1(Buf1);
                      KiAdjustDpcThreshold = HIDWORD(Buf1);
                      KiIdealDpcRate = (int)v160[0];
                      KeSynchronizeWithDynamicProcessors(v17, v16, v18, v19);
                      ActiveProcessorCount = KeQueryActiveProcessorCountEx(0xFFFFu);
                      if ( ActiveProcessorCount )
                      {
                        do
                        {
                          v21 = *((_QWORD *)&KiProcessorBlock + (unsigned int)v6);
                          *(_DWORD *)(v21 + 3304) = KiMaximumDpcQueueDepth;
                          *(_DWORD *)(v21 + 3312) = KiMinimumDpcRate;
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
                  v46 = 0;
                }
                else
                {
                  if ( (_DWORD)v3 != 56 )
                    return 3221225476LL;
                  v46 = 1;
                }
                if ( !PreviousMode )
                {
                  v139 = *(_OWORD *)p_Buf1;
                  SystemImage = MmLoadSystemImage((unsigned int)&v139, 0, 0, v15, (__int64)&v143, (__int64)&v138);
                  updated = SystemImage;
                  if ( SystemImage < 0 )
                  {
                    if ( SystemImage == -1073741411 )
                      return (unsigned int)-1073741554;
                  }
                  else
                  {
                    if ( v46 )
                    {
                      LOBYTE(v48) = 1;
                      v49 = RtlImageDirectoryEntryToData(v138, v48, 0, &v134);
                    }
                    else
                    {
                      v49 = 0;
                    }
                    v50 = RtlImageNtHeader(v138);
                    v51 = v138 + *(unsigned int *)(v50 + 40);
                    *(_QWORD *)(p_Buf1 + 16) = v138;
                    *(_QWORD *)(p_Buf1 + 24) = v143;
                    *(_QWORD *)(p_Buf1 + 32) = v51;
                    if ( v46 )
                    {
                      *(_QWORD *)(p_Buf1 + 40) = v49;
                      *(_DWORD *)(p_Buf1 + 48) = *(_DWORD *)(v50 + 80);
                    }
                    else
                    {
                      *(_DWORD *)(p_Buf1 + 40) = *(_DWORD *)(v50 + 80);
                    }
                  }
                  return updated;
                }
                return 3221225569LL;
              }
LABEL_198:
              v133[0] = 0;
              if ( (unsigned int)v3 < 0x40 )
                return 3221225476LL;
              if ( a1 == 21 )
              {
                v54 = 0;
              }
              else
              {
                if ( PreviousMode )
                  v54 = RtlReadULongFromUser(p_Buf1 + 60);
                else
                  v54 = *(_DWORD *)(p_Buf1 + 60);
                v151 = v54;
                if ( (v54 & 0xFFFFFFF0) != 0 || (v54 & 0xC) == 0xC || (v54 & 3) == 3 )
                  return 3221225712LL;
              }
              if ( SeSinglePrivilegeCheck(SeIncreaseQuotaPrivilege, PreviousMode) )
              {
                if ( PreviousMode )
                  v55 = RtlReadULong64FromUser(p_Buf1 + 24);
                else
                  v55 = *(_QWORD *)(p_Buf1 + 24);
                v154 = v55;
                if ( PreviousMode )
                  v56 = RtlReadULong64FromUser(p_Buf1 + 32);
                else
                  v56 = *(_QWORD *)(p_Buf1 + 32);
                v155 = v56;
                return MmAdjustWorkingSetSizeEx(v55, v56, 1u, 1, v54, v133);
              }
              return 3221225506LL;
            }
            if ( (_DWORD)v3 != 4 )
              return 3221225476LL;
            if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
              return 3221225506LL;
            v136 = 0;
            if ( PreviousMode )
              v22 = RtlReadULongFromUser(p_Buf1);
            else
              v22 = *(_DWORD *)p_Buf1;
            v23 = v22 & 0x92319BF0 | NtGlobalFlag & 0x6DCE640F;
            v136 = v23;
            NtGlobalFlag = v23;
            if ( !PreviousMode )
            {
              *(_DWORD *)p_Buf1 = v23;
              return updated;
            }
LABEL_42:
            RtlWriteULongToUser(p_Buf1, v23);
            return updated;
          }
          v28 = a1 - 30;
          if ( !v28 )
            return (unsigned int)MmCreateMirror();
          v29 = v28 - 1;
          if ( !v29 )
            return (unsigned int)EtwSetPerformanceTraceInformation((void *)p_Buf1, (unsigned int)v3, PreviousMode);
          v30 = v29 - 3;
          if ( v30 )
          {
            v31 = v30 - 3;
            if ( v31 )
            {
              if ( v31 != 1 )
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
                    v32 = (void *)RtlReadULong64FromUser(p_Buf1 + 8);
                    PrivilegeValue[1] = (LUID)v32;
                    v139 = *(_OWORD *)&PrivilegeValue[0].LowPart;
                    if ( LOWORD(PrivilegeValue[0].LowPart) == 62 )
                    {
                      RtlCopyFromUser(&Buf1, v32, 0x3Eu);
                      if ( !memcmp(&Buf1, L"\\SystemRoot\\System32\\win32k.sys", 0x3Eu) )
                      {
                        *((_QWORD *)&v139 + 1) = L"\\SystemRoot\\System32\\win32k.sys";
                        WORD1(v139) = 62;
                        return ZwSetSystemInformation(38, &v139, 16);
                      }
                    }
                  }
                }
                return 3221225569LL;
              }
              v139 = *(_OWORD *)p_Buf1;
              if ( !memcmp(*(const void **)(p_Buf1 + 8), L"\\SystemRoot\\System32\\win32k.sys", 0x3Eu) )
              {
                v138 = *(_QWORD *)(PsWin32kDataTableEntry + 48);
                v34 = RtlImageNtHeader(v138);
                if ( !v34 )
                {
                  MmUnloadSystemImage(PsWin32kDataTableEntry);
                  return 3221225595LL;
                }
                updated = ExpInitializeSessionDriver(v138 + *(unsigned int *)(v34 + 40), v138);
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
            || (unsigned __int8)PsIsCurrentThreadInServerSilo(v7, v13) )
          {
            return 3221225569LL;
          }
          if ( (_DWORD)v3 == 4 )
          {
            if ( PreviousMode )
            {
              if ( (p_Buf1 & 3) != 0 )
                ExRaiseDatatypeMisalignment();
              v36 = RtlReadULongFromUser(p_Buf1);
            }
            else
            {
              v36 = *(_DWORD *)p_Buf1;
            }
            v147 = v36;
            if ( !v36 )
            {
              v38 = 0;
              return (unsigned int)IoConfigureCrashDump(v38, 0);
            }
            v37 = v36 - 1;
            if ( v37 )
            {
              if ( v37 == 1 )
                return (unsigned int)WheaCrashDumpInitializationComplete();
              return 3221225485LL;
            }
          }
          v38 = 1;
          return (unsigned int)IoConfigureCrashDump(v38, 0);
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
            v41 = (unsigned int)(a1 - 46);
            if ( a1 == 46 )
            {
              if ( (_DWORD)v3 != 8 )
                return 3221225476LL;
              if ( PreviousMode && !SeSinglePrivilegeCheck(SeSystemtimePrivilege, PreviousMode) )
                return 3221225569LL;
              if ( !(unsigned __int8)PsIsCurrentThreadInServerSilo(v41, v13) )
              {
                if ( PreviousMode )
                  v42 = (void *)RtlReadULong64FromUser(p_Buf1);
                else
                  v42 = *(void **)p_Buf1;
                v150 = (ULONG_PTR)v42;
                if ( v42 )
                {
                  v134 = 0;
                  updated = ObReferenceObjectByHandle(v42, 2u, (POBJECT_TYPE)ExEventObjectType, PreviousMode, &v134, 0);
                  if ( (updated & 0x80000000) != 0 )
                    return updated;
                  v6 = v134;
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
          result = VfProbeAndCaptureUnicodeString(&v139, p_Buf1, 1);
          if ( (int)result < 0 )
            return result;
          if ( (_WORD)v139 )
          {
            p_Buf1 = (__int64)&v139;
LABEL_139:
            v43 = a1 - 40;
            if ( !v43 )
            {
              v44 = VfAddVerifierEntry((PCUNICODE_STRING)p_Buf1, v13);
              goto LABEL_522;
            }
            if ( v43 == 1 )
            {
              v44 = VfRemoveVerifierEntry(p_Buf1, v13);
LABEL_522:
              updated = v44;
              goto LABEL_523;
            }
LABEL_519:
            updated = -1073741821;
LABEL_523:
            if ( !PreviousMode )
              return updated;
            v71 = (char *)p_Buf1;
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
            return (unsigned int)PfSnSetPrefetcherInformation(v7, (void *)p_Buf1, v3, PreviousMode);
          case ';':
            if ( (_DWORD)v3 == 4 )
            {
              if ( PreviousMode )
                v45 = RtlReadULongFromUser(p_Buf1);
              else
                v45 = *(_DWORD *)p_Buf1;
              v149 = v45;
              updated = ExpUpdateComPlusPackage(v45);
              if ( (updated & 0x80000000) == 0 )
                *(_DWORD *)(MmWriteableSharedUserData + 736) = v45;
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
      v52 = (unsigned int)(*(_DWORD *)p_Buf1 - 1);
      if ( *(_DWORD *)p_Buf1 == 1
        || (v52 = (unsigned int)(*(_DWORD *)p_Buf1 - 2), *(_DWORD *)p_Buf1 == 2)
        || (v52 = (unsigned int)(*(_DWORD *)p_Buf1 - 3), *(_DWORD *)p_Buf1 == 3) )
      {
        guard_dispatch_icall_no_overrides(v52, 2, v8);
        return 0;
      }
      if ( *(_DWORD *)p_Buf1 == 4 )
        return (unsigned int)-1073741637;
      v53 = (unsigned int)(*(_DWORD *)p_Buf1 - 6);
      if ( *(_DWORD *)p_Buf1 == 6 )
      {
        LODWORD(v53) = 1;
        return (unsigned int)guard_dispatch_icall_no_overrides(v53, 2, v8);
      }
      if ( *(_DWORD *)p_Buf1 == 7 )
      {
        updated = 0;
        if ( off_140E00B38[0] == xKdEnumerateDebuggingDevices )
          return (unsigned int)-1073741822;
        return updated;
      }
      return (unsigned int)-1073741811;
    }
    if ( a1 > 93 )
    {
      if ( a1 > 106 )
      {
        v72 = a1 - 109;
        if ( v72 )
        {
          v73 = v72 - 1;
          if ( !v73 )
            return (unsigned int)-1073741822;
          v74 = v73 - 1;
          if ( !v74 )
          {
            if ( (_DWORD)v3 != 4 )
              return 3221225476LL;
            if ( SeSinglePrivilegeCheck(SeProfileSingleProcessPrivilege, PreviousMode) )
            {
              if ( PreviousMode )
                v75 = RtlReadULongFromUser(p_Buf1);
              else
                v75 = *(_DWORD *)p_Buf1;
              *(_DWORD *)(MmWriteableSharedUserData + 584) = v75;
              return 0;
            }
            return 3221225506LL;
          }
          if ( v74 != 2 )
            return (unsigned int)-1073741821;
          return (unsigned int)PsSetCpuQuotaInformation((volatile void *)p_Buf1, (unsigned int)v3, PreviousMode);
        }
        else
        {
          return (unsigned int)SmSetStoreInformation(v7, (void *)p_Buf1, v3, PreviousMode);
        }
      }
      if ( a1 == 106 )
        return (unsigned int)-1073741821;
      v67 = a1 - 94;
      if ( !v67 )
      {
        if ( SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
        {
          if ( (_DWORD)v3 == 8 )
          {
            if ( PreviousMode )
              *(_QWORD *)&Buf1 = RtlReadULong64FromUser(p_Buf1);
            else
              RtlCopyVolatileMemory(&Buf1, (const void *)p_Buf1, 8u);
            _InterlockedOr((volatile signed __int32 *)(MmWriteableSharedUserData + 928), Buf1);
            _InterlockedAnd((volatile signed __int32 *)(MmWriteableSharedUserData + 928), ~DWORD1(Buf1));
            return updated;
          }
          return (unsigned int)-1073741820;
        }
        return (unsigned int)-1073741790;
      }
      v68 = v67 - 1;
      if ( !v68 )
        return 3221225659LL;
      v69 = v68 - 2;
      if ( !v69 )
      {
        if ( (_DWORD)v3 != 40 )
          return 3221225476LL;
        if ( PreviousMode )
        {
          if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
            return 3221225569LL;
          RtlCopyFromUser(&Buf1, (void *)p_Buf1, 0x28u);
          result = VfProbeAndCaptureUnicodeStringBuffer((char *)&Buf1 + 8, 1);
          if ( (int)result < 0 )
            return result;
          updated = VfProbeAndCaptureUnicodeStringBuffer(&v160[1], 1);
          if ( (updated & 0x80000000) != 0 )
          {
            v71 = (char *)&Buf1 + 8;
            goto LABEL_525;
          }
          p_Buf1 = (__int64)&Buf1;
        }
        updated = VfFaultsSetParameters(p_Buf1, v13);
        if ( !PreviousMode )
          return updated;
        VfFreeCapturedUnicodeString(p_Buf1 + 8);
        v71 = (char *)(p_Buf1 + 24);
LABEL_525:
        VfFreeCapturedUnicodeString(v71);
        return updated;
      }
      v70 = v69 - 5;
      if ( v70 )
      {
        if ( v70 != 2 )
          return (unsigned int)-1073741821;
        LOBYTE(v8) = PreviousMode;
        return (unsigned int)ExpSetProcessorMicrocodeUpdateInformation(p_Buf1, (unsigned int)v3, v8);
      }
      v66 = 432;
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
                return (unsigned int)ExpRegisterFirmwareTableInformationHandler(p_Buf1, v3, PreviousMode);
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
              v137 = 6;
              if ( PreviousMode )
                RtlCopyFromUser(&v137, (void *)p_Buf1, 4u);
              else
                RtlCopyVolatileMemory(&v137, (const void *)p_Buf1, 4u);
              LOBYTE(v57) = PreviousMode;
              return (unsigned int)MmIssueMemoryListCommand(v137, v57, -1);
            }
            return (unsigned int)-1073741820;
          }
          if ( (unsigned int)v3 < 0x18 )
            return 3221225476LL;
          if ( !SeSinglePrivilegeCheck(SeIncreaseBasePriorityPrivilege, PreviousMode) )
            return 3221225569LL;
          if ( PreviousMode )
          {
            RtlCopyFromUser(&Buf1, (void *)p_Buf1, 0x18u);
            p_Buf1 = (__int64)&Buf1;
          }
          if ( (unsigned int)(*(_DWORD *)(p_Buf1 + 16) - 1) > 0x1E )
            return 3221225485LL;
          *(_OWORD *)&PrivilegeValue[0].LowPart = *(_OWORD *)p_Buf1;
          updated = PsLookupProcessThreadByCid(PrivilegeValue, 0, &v134);
          if ( (updated & 0x80000000) != 0 )
            return updated;
          v58 = v134;
          if ( (unsigned __int8)*((_DWORD *)v134 + 1) )
          {
            updated = -1073741749;
          }
          else
          {
            KeSetActualBasePriorityThread((ULONG_PTR)v134);
            updated = 259;
          }
          v59 = v58;
LABEL_234:
          ObfDereferenceObject(v59);
          return updated;
        }
        v60 = a1 - 86;
        if ( !v60 )
          return (unsigned int)ObSetRefTraceInformation((void *)p_Buf1, v3);
        v61 = v60 - 1;
        if ( v61 )
        {
          v62 = v61 - 2;
          if ( v62 )
          {
            v63 = v62 - 2;
            if ( v63 )
            {
              if ( v63 != 1 )
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
              return (unsigned int)DbgkRegisterErrorPort((void *)p_Buf1, (unsigned int)v3);
            v65 = WORD2(Process[3].PerProcessorCycleTimes);
            if ( v65 != 332 && v65 != 452 )
              v12 = 0;
            if ( !v12 )
              return (unsigned int)DbgkRegisterErrorPort((void *)p_Buf1, (unsigned int)v3);
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
              RtlCopyVolatileMemory(&Buf1, (const void *)p_Buf1, 8u);
            MmSpecialPoolTag = Buf1;
            MmSpecialPoolCatchOverruns = BYTE4(Buf1) & 1;
            return updated;
          }
          return (unsigned int)-1073741820;
        }
        return (unsigned int)-1073741790;
      }
      v66 = 172;
    }
    if ( (_DWORD)v3 != v66 )
      return 3221225476LL;
    if ( PreviousMode && !SeSinglePrivilegeCheck(SeTimeZonePrivilege, PreviousMode) )
      return 3221225569LL;
    return (unsigned int)ExpSetTimeZoneInformation((void *)p_Buf1, v66);
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
            return (unsigned int)sub_1409A0F34(v7, p_Buf1);
          }
          else
          {
            v76 = a1 - 127;
            if ( !v76 )
            {
              if ( (_DWORD)v3 == 16 )
              {
                if ( SeSinglePrivilegeCheck(SeProfileSingleProcessPrivilege, PreviousMode) )
                {
                  if ( PreviousMode )
                    v89 = RtlReadULong64FromUser(p_Buf1);
                  else
                    v89 = *(_QWORD *)p_Buf1;
                  v150 = v89;
                  updated = MmScrubMemory(v88, v89, Src);
                  LODWORD(v134) = updated;
                  v90 = (void *)(p_Buf1 + 8);
                  if ( PreviousMode )
                    RtlWriteULong64ToUser(v90, Src[0]);
                  else
                    RtlCopyVolatileMemory(v90, Src, 8u);
                  return updated;
                }
                return 3221225569LL;
              }
              return 3221225476LL;
            }
            v77 = v76 - 2;
            if ( v77 )
            {
              v78 = v77 - 1;
              if ( !v78 )
              {
                PrivilegeValue[0] = 0;
                if ( (((_DWORD)v3 - 16) & 0xFFFFFFE7) == 0 && (_DWORD)v3 != 40 )
                {
                  if ( SeSinglePrivilegeCheck(SeProfileSingleProcessPrivilege, PreviousMode) )
                  {
                    if ( PreviousMode )
                      RtlCopyFromUser(&Buf1, (void *)p_Buf1, v3);
                    else
                      RtlCopyVolatileMemory(&Buf1, (const void *)p_Buf1, v3);
                    ThreadPartition = (ULONG *)MiGetThreadPartition(KeGetCurrentThread());
                    LOBYTE(Object) = *(_BYTE *)(v86 + 562);
                    updated = MiCombineIdenticalPages(
                                ThreadPartition,
                                Buf1,
                                (int)v160[0],
                                v87,
                                (__int64)Object,
                                PrivilegeValue);
                    LODWORD(v134) = updated;
                    if ( PreviousMode )
                      RtlWriteULong64ToUser(p_Buf1 + 8, *(_QWORD *)PrivilegeValue);
                    else
                      *(LUID *)(p_Buf1 + 8) = PrivilegeValue[0];
                    return updated;
                  }
                  return 3221225569LL;
                }
                return 3221225476LL;
              }
              v79 = v78 - 1;
              if ( v79 )
              {
                if ( v79 != 1 )
                  return (unsigned int)-1073741821;
                if ( (_DWORD)v3 != 4 )
                  return 3221225476LL;
                *(_QWORD *)&DriverServiceName.Length = 7733364;
                DriverServiceName.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\condrv";
                if ( PreviousMode )
                {
                  v80 = RtlReadULongFromUser(p_Buf1);
                  LODWORD(Buf1) = v80;
                }
                else
                {
                  RtlCopyVolatileMemory(&Buf1, (const void *)p_Buf1, 4u);
                  LOBYTE(v80) = Buf1;
                }
                if ( (v80 & 1) != 0 )
                {
                  KeEnterCriticalRegion();
                  v81 = (LegacyAutoBoost *)KeAbPreAcquire((struct _KTHREAD *)&ExpConDrvLoadLock, 0);
                  v83 = v81;
                  if ( _interlockedbittestandset64((volatile signed __int32 *)&ExpConDrvLoadLock, 0) )
                    ExfAcquirePushLockExclusiveEx(&ExpConDrvLoadLock, v81, (struct _KTHREAD *)&ExpConDrvLoadLock);
                  if ( v83 )
                  {
                    if ( (KiAbpGlobalState & 1) != 0 )
                      AutoBoost::KiAbpPostAcquire(v83, v82);
                    else
                      *((_BYTE *)v83 + 10) = 1;
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
                                       *(_QWORD *)(p_Buf1 + 8),
                                       *(_QWORD *)(p_Buf1 + 16));
              }
            }
            else
            {
              return (unsigned int)KeProcessorProfileControlArea(p_Buf1, v3, PreviousMode);
            }
          }
        }
        v91 = a1 - 142;
        if ( !v91 )
        {
          if ( (_DWORD)v3 == 72 || (_DWORD)v3 == 48 )
          {
            if ( SeSinglePrivilegeCheck(SeShutdownPrivilege, PreviousMode) )
            {
              RtlCopyFromUser(&Buf1, (void *)p_Buf1, v3);
              Pool2 = (void *)ExAllocatePool2(64, LOWORD(v160[0]), 1347639365);
              v99 = Pool2;
              PrivilegeValue[0] = (LUID)Pool2;
              if ( !Pool2 )
                return 3221225626LL;
              RtlCopyFromUser(Pool2, v160[1], LOWORD(v160[0]));
              v160[1] = v99;
              CurrentServerSiloGlobals = PsGetCurrentServerSiloGlobals(v101, v100);
              if ( _InterlockedCompareExchange((volatile signed __int32 *)(CurrentServerSiloGlobals + 1376), Buf1, 0) )
              {
                ExFreePoolWithTag(v99, 0x50535845u);
                return 0;
              }
              *(_OWORD *)(CurrentServerSiloGlobals + 1376) = Buf1;
              *(_OWORD *)(CurrentServerSiloGlobals + 1392) = *(_OWORD *)v160;
              *(_OWORD *)(CurrentServerSiloGlobals + 1408) = v161;
              *(_OWORD *)(CurrentServerSiloGlobals + 1424) = v162;
              *(_QWORD *)(CurrentServerSiloGlobals + 1440) = v163;
              return 0;
            }
            return 3221225569LL;
          }
          return 3221225476LL;
        }
        v92 = v91 - 8;
        if ( !v92 )
        {
          if ( !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
            return 3221225569LL;
          return (unsigned int)ExpSetBootLoaderMetadata((void *)p_Buf1, (unsigned int)v3);
        }
        v93 = v92 - 1;
        if ( !v93 )
        {
          PrivilegeValue[0] = (LUID)19LL;
          if ( !SeSinglePrivilegeCheck((LUID)19LL, PreviousMode) )
            return 3221225569LL;
          v95 = v3 - 1;
          if ( v95 )
          {
            if ( v95 != 3 )
              return 3221225476LL;
            if ( PreviousMode )
              v96 = RtlReadULongFromUser(p_Buf1);
            else
              v96 = *(_DWORD *)p_Buf1;
            v145 = v96;
          }
          else
          {
            if ( PreviousMode )
              v97 = RtlReadUCharFromUser(p_Buf1);
            else
              v97 = *(_BYTE *)p_Buf1;
            v135 = v97;
            if ( v97 && !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
              return 3221225569LL;
            v96 = v97 != 0 ? 1 : 5;
          }
          return (unsigned int)ExpSetSoftRebootFlags(v96);
        }
        v94 = v93 - 1;
        if ( v94 )
        {
          if ( v94 != 3 )
            return (unsigned int)-1073741821;
          return (unsigned int)CmReconcileAndValidateAllHives(v7, 2);
        }
        if ( (_DWORD)v3 != 8 )
          return 3221225476LL;
        if ( PreviousMode )
        {
          v156 = RtlReadULong64FromUser(p_Buf1);
          return (unsigned int)ExpQueryElamCertInfo(v156);
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
            RtlCopyFromUser(&Buf1, (void *)p_Buf1, 0x18u);
          else
            RtlCopyVolatileMemory(&Buf1, (const void *)p_Buf1, 0x18u);
          result = VfProbeAndCaptureUnicodeStringBuffer(&Buf1, 1);
          if ( (int)result >= 0 )
          {
            updated = PsSetExeModerationState(&Buf1, LODWORD(v160[0]), HIDWORD(v160[0]));
            v71 = (char *)&Buf1;
            goto LABEL_525;
          }
          return result;
        }
        if ( a1 != 190 )
        {
          v116 = (unsigned int)(a1 - 191);
          if ( a1 == 191 )
          {
            if ( !(_DWORD)v3 )
            {
              if ( PreviousMode && !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
                return 3221225569LL;
              return (unsigned int)VslRelaxQuotas(v116, v13);
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
          LODWORD(v134) = 0;
          v152 = 0;
          v153 = 0;
          if ( (_DWORD)v3 != 8 )
          {
            if ( (_DWORD)v3 )
              return 3221225476LL;
            updated = 0;
            v115 = KeGetCurrentThread()->ApcState.Process;
            LODWORD(v134) = PsGetSessionIdEx(v115);
            if ( (_DWORD)v134 == -1 )
              return updated;
            v153 = v115;
            return (unsigned int)PsInvokeWin32Callout(32, &v152, 1, &v134);
          }
          if ( !SeSinglePrivilegeCheck(SeTcbPrivilege, PreviousMode) )
            return 3221225569LL;
          if ( PreviousMode )
            v113 = (void *)RtlReadULong64FromUser(p_Buf1);
          else
            v113 = *(void **)p_Buf1;
          v158 = v113;
          PrivilegeValue[0] = 0;
          updated = ObReferenceObjectByHandle(
                      v113,
                      0x1000u,
                      (POBJECT_TYPE)PsProcessType,
                      PreviousMode,
                      (PVOID *)PrivilegeValue,
                      0);
          if ( (updated & 0x80000000) != 0 )
            return updated;
          v114 = PrivilegeValue[0];
          LODWORD(v134) = PsGetSessionIdEx(*(_QWORD *)PrivilegeValue);
          if ( (_DWORD)v134 != -1 )
          {
            v153 = (_KPROCESS *)v114;
            updated = PsInvokeWin32Callout(32, &v152, 1, &v134);
          }
          v59 = (void *)v114;
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
                RtlCopyFromUser(PrivilegeValue, (void *)p_Buf1, (unsigned int)v3);
              else
                RtlCopyVolatileMemory(PrivilegeValue, (const void *)p_Buf1, (unsigned int)v3);
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
              v103 = v3 - 8;
              if ( (v103 & 7) != 0 || v103 > 0x200 )
                return 3221225476LL;
              if ( PreviousMode )
                v104 = RtlReadULong64FromUser(p_Buf1);
              else
                v104 = *(_QWORD *)p_Buf1;
              v157 = v104;
              v105 = (void *)(p_Buf1 + 8);
              if ( PreviousMode )
                RtlCopyFromUser(&Buf1, v105, v103);
              else
                RtlCopyVolatileMemory(&Buf1, v105, v103);
              LOBYTE(v107) = PreviousMode;
              updated = ExCpuSetResourceManagerAccessCheck(v107, v106);
              if ( (updated & 0x80000000) != 0 )
                return updated;
              return (unsigned int)KeSetTagCpuSets(v103 >> 3, &Buf1, v104);
            }
          }
          if ( (v3 & 7) != 0 || (unsigned int)v3 > 0x200 )
            return 3221225476LL;
          if ( PreviousMode )
            RtlCopyFromUser(&Buf1, (void *)p_Buf1, v3);
          else
            RtlCopyVolatileMemory(&Buf1, (const void *)p_Buf1, v3);
          LOBYTE(v109) = PreviousMode;
          result = ExCpuSetResourceManagerAccessCheck(v109, v108);
          if ( (int)result >= 0 )
          {
            v111 = (unsigned int)v3 >> 3;
            v112 = 0;
            return (unsigned int)KeModifySystemAllowedCpuSets(v111, (unsigned int)&Buf1, v110, v112);
          }
          return result;
        }
      }
    }
LABEL_507:
    if ( qword_140EF3020 )
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
            return (unsigned int)VfPtGenerateTraceInformation((_DWORD)v3 == 0);
          case 228:
          case 229:
            v131 = 0;
            if ( (int)RtlCheckTokenMembership(0, SeAliasAdminsSid, &v131, v9) < 0 || !v131 )
              return 3221225569LL;
            return (unsigned int)KeUpdateDpcWatchdogConfiguration((void *)p_Buf1, (unsigned int)v3);
          case 233:
            return (unsigned int)PnpIommuBlockUnblockDevice(p_Buf1, (unsigned int)v3);
          case 235:
            return (unsigned int)HvlQuerySetBootPagesInfo((_DWORD *)p_Buf1, v3, PreviousMode, 0, 0);
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
          v129 = RtlReadULongFromUser(p_Buf1);
        else
          v129 = *(_DWORD *)p_Buf1;
        v146 = v129;
        ExResourceTimeoutCount = (v129 + 3999) / 0xFA0u;
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
            v128 = RtlReadULongFromUser(p_Buf1);
          else
            v128 = *(_DWORD *)p_Buf1;
          LODWORD(Buf1) = v128;
          PspBreakOnContextUnwindFailure = v128;
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
      return (unsigned int)ObSetRefTraceInformationEx((void *)p_Buf1, v3);
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
          result = VfProbeAndCaptureUnicodeString(&v139, p_Buf1, 1);
          if ( (int)result < 0 )
            return result;
          if ( !(_WORD)v139 )
            return 3221225711LL;
          p_Buf1 = (__int64)&v139;
        }
        v127 = a1 - 219;
        if ( !v127 )
        {
          v44 = VfVolatileApplyDifVerification(p_Buf1, v13);
          goto LABEL_522;
        }
        if ( v127 == 1 )
        {
          v44 = VfVolatileRemoveDifVerification((const UNICODE_STRING *)p_Buf1);
          goto LABEL_522;
        }
        goto LABEL_519;
      case 223:
        return (unsigned int)ExPoolSetLimit((void *)p_Buf1, v3, PreviousMode);
    }
    if ( a1 != 224 )
      return (unsigned int)-1073741821;
    goto LABEL_507;
  }
  if ( a1 == 217 )
  {
    if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
      return 3221225506LL;
    return (unsigned int)VfVolatileSetDifRuleClass((void *)p_Buf1, (unsigned int)v3);
  }
  v117 = a1 - 204;
  if ( !v117 )
  {
    if ( (unsigned int)v3 < 8 )
      return 3221225476LL;
    v122 = v3 - 8;
    if ( (v122 & 7) != 0 || v122 > 0x200 )
      return 3221225476LL;
    if ( PreviousMode )
      v123 = RtlReadULong64FromUser(p_Buf1);
    else
      v123 = *(_QWORD *)p_Buf1;
    PrivilegeValue[0] = (LUID)v123;
    v124 = (void *)(p_Buf1 + 8);
    if ( PreviousMode )
      RtlCopyFromUser(&Buf1, v124, v122);
    else
      RtlCopyVolatileMemory(&Buf1, v124, v122);
    v126 = 2;
    if ( v123 >= 2 )
      return 3221225485LL;
    LOBYTE(v126) = PreviousMode;
    updated = ExCpuSetResourceManagerAccessCheck(v126, v125);
    if ( (updated & 0x80000000) != 0 )
      return updated;
    v112 = v123;
    v111 = v122 >> 3;
    return (unsigned int)KeModifySystemAllowedCpuSets(v111, (unsigned int)&Buf1, v110, v112);
  }
  v118 = v117 - 2;
  if ( v118 )
  {
    v119 = v118 - 1;
    if ( v119 )
    {
      v120 = v119 - 3;
      if ( v120 )
      {
        if ( v120 != 2 )
          return (unsigned int)-1073741821;
        return (unsigned int)CmUpdateFeatureUsageSubscription((void *)p_Buf1, (unsigned int)v3, PreviousMode);
      }
      else
      {
        return (unsigned int)CmUpdateFeatureConfiguration((void *)p_Buf1, (unsigned int)v3, PreviousMode);
      }
    }
    if ( (_DWORD)v3 != 4 )
      return 3221225476LL;
    if ( !SeSinglePrivilegeCheck(SeDebugPrivilege, PreviousMode) )
      return 3221225506LL;
    v140 = 0;
    if ( PreviousMode )
      v121 = RtlReadULongFromUser(p_Buf1);
    else
      v121 = *(_DWORD *)p_Buf1;
    v140 = v121;
    if ( (v121 & 0x2018) == 0 )
    {
      v23 = v121 | NtGlobalFlag2 & 0x2018;
      v140 = v23;
      NtGlobalFlag2 = v23;
      if ( !PreviousMode )
      {
        *(_DWORD *)p_Buf1 = v23;
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
    RtlCopyVolatileMemory(&Buf1, (const void *)p_Buf1, 8u);
  v132 = (_BYTE)Buf1 != 0;
  result = ExSetLeapSecondEnabled();
  updated = result;
  if ( (int)result >= 0 )
  {
    *(_BYTE *)ExLeapSecondData = v132;
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
