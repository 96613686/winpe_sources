# DsSamCreateFirstMachineAccount(void *)

- ea: `0x1803a72f4`
- end: `0x1803a7e60`
- name: `?DsSamCreateFirstMachineAccount@@YAJPEAX@Z`
- size: `2924`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1803a8168`

## callees

- `0x18000b0b0`
- `0x18000bb20`
- `0x18000ff94`
- `0x180010510`
- `0x18001e090`
- `0x18001e0d0`
- `0x180030af8`
- `0x1803a72f4`
- `0x1803a8e08`
- `0x1803a92a8`
- `0x1803a9450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803a7437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803a7437`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a7e20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a7e2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a7e20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1803a7e2f`
- `KERNEL32!GetComputerNameW` at `0x1803a73c6`
- `KERNEL32!GetComputerNameW` at `0x1803a73c6`
- `SAMSRV!SamrCloseHandle` at `0x1803a7dfc`
- `SAMSRV!SamrCloseHandle` at `0x1803a7dfc`
- `SAMSRV!SamILookupNamesInDomain` at `0x1803a7563`
- `SAMSRV!SamILookupNamesInDomain` at `0x1803a7563`
- `SAMSRV!SamrOpenUser` at `0x1803a76d4`
- `SAMSRV!SamrOpenUser` at `0x1803a76d4`
- `SAMSRV!SampGenerateRandomPassword` at `0x1803a7505`
- `SAMSRV!SampGenerateRandomPassword` at `0x1803a7505`
- `SAMSRV!SampAllocateNextCurrentRidFromIndex` at `0x1803a7587`
- `SAMSRV!SampAllocateNextCurrentRidFromIndex` at `0x1803a7587`
- `SAMSRV!SampCreateUserInDomain` at `0x1803a75d3`
- `SAMSRV!SampCreateUserInDomain` at `0x1803a75d3`
- `SAMSRV!SamrQueryInformationUser2` at `0x1803a77d4`
- `SAMSRV!SamrQueryInformationUser2` at `0x1803a77d4`
- `SAMSRV!SamrSetInformationUser` at `0x1803a7900`
- `SAMSRV!SamrSetInformationUser` at `0x1803a7900`
- `SAMSRV!SampSetPassword` at `0x1803a79f9`
- `SAMSRV!SampSetPassword` at `0x1803a79f9`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1803a7e11`
- `SAMSRV!SamIFree_SAMPR_USER_INFO_BUFFER` at `0x1803a7e11`

## pseudocode

```c
__int64 __fastcall DsSamCreateFirstMachineAccount(unsigned int *a1)
{
  __int64 v2; // rcx
  WCHAR *v3; // rax
  __int64 v4; // rcx
  WCHAR *v5; // rax
  __int64 v6; // r15
  WCHAR *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  HLOCAL *v10; // rax
  __int64 v11; // rcx
  HLOCAL *v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  BOOL v19; // esi
  int v20; // eax
  int v21; // ecx
  int RandomPassword; // esi
  DWORD v23; // ecx
  unsigned __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // rcx
  BOOL v29; // r14d
  int v30; // eax
  int v31; // ecx
  __int64 v32; // rdx
  __int64 v33; // rcx
  BOOL v34; // r14d
  int v35; // eax
  int v36; // ecx
  __int64 v37; // rdx
  __int64 v38; // rcx
  BOOL v39; // r14d
  int v40; // eax
  int v41; // ecx
  unsigned int v42; // ecx
  __int64 v43; // rdx
  __int64 v44; // rcx
  BOOL v45; // r14d
  int v46; // eax
  int v47; // ecx
  __int64 v48; // rdx
  __int64 v49; // rcx
  BOOL v50; // r14d
  int v51; // eax
  int v52; // ecx
  __int64 v53; // rdx
  __int64 v54; // rcx
  BOOL v55; // r14d
  int v56; // eax
  int v57; // ecx
  __int64 v58; // rdx
  __int64 v59; // rcx
  BOOL v60; // edi
  int v61; // eax
  int v62; // ecx
  __int64 v63; // rdx
  __int64 v64; // rcx
  BOOL v65; // r14d
  int v66; // eax
  int v67; // ecx
  WCHAR *v68; // rax
  int v70; // [rsp+20h] [rbp-E0h]
  int v71; // [rsp+28h] [rbp-D8h]
  unsigned int NextCurrentRidFromIndex; // [rsp+60h] [rbp-A0h] BYREF
  void *v73; // [rsp+68h] [rbp-98h] BYREF
  unsigned int *v74; // [rsp+70h] [rbp-90h] BYREF
  DWORD nSize; // [rsp+78h] [rbp-88h] BYREF
  int v76; // [rsp+7Ch] [rbp-84h] BYREF
  __int128 v77; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem[2]; // [rsp+90h] [rbp-70h] BYREF
  HLOCAL v79[2]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[24]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR SourceString[264]; // [rsp+E0h] [rbp-20h] BYREF

  nSize = 16;
  NextCurrentRidFromIndex = 0;
  v73 = 0;
  v74 = 0;
  v2 = 24;
  v77 = 0;
  v3 = Buffer;
  *(_OWORD *)hMem = 0;
  *(_OWORD *)v79 = 0;
  do
  {
    *(_BYTE *)v3 = 0;
    v3 = (WCHAR *)((char *)v3 + 1);
    --v2;
  }
  while ( v2 );
  v4 = 34;
  v5 = Buffer;
  do
  {
    *(_BYTE *)v5 = 0;
    v5 = (WCHAR *)((char *)v5 + 1);
    --v4;
  }
  while ( v4 );
  v6 = 514;
  v7 = SourceString;
  v8 = 514;
  do
  {
    *(_BYTE *)v7 = 0;
    v7 = (WCHAR *)((char *)v7 + 1);
    --v8;
  }
  while ( v8 );
  v9 = 16;
  v10 = hMem;
  do
  {
    *(_BYTE *)v10 = 0;
    v10 = (HLOCAL *)((char *)v10 + 1);
    --v9;
  }
  while ( v9 );
  v11 = 16;
  v12 = v79;
  do
  {
    *(_BYTE *)v12 = 0;
    v12 = (HLOCAL *)((char *)v12 + 1);
    --v11;
  }
  while ( v11 );
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
      || (unsigned int)THStateCheckForTraceOverride(v14, v13)
      || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
      || gfTraceToSecondProvider
      && ((unsigned int)THStateCheckForTraceOverride(v16, v15)
       || (unsigned int)ThStateCheckIfTraceToSecondProvier()
       && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
    {
      GetLastError();
      v18 = (unsigned int)gfTraceToSecondProvider;
      v19 = gfTraceToSecondProvider
         && ((unsigned int)THStateCheckForTraceOverride((unsigned int)gfTraceToSecondProvider, v17)
          || (unsigned int)ThStateCheckIfTraceToSecondProvier()
          && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
      if ( (unsigned int)THStateCheckForTraceOverride(v18, v17)
        || (v20 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v21 = 0, v20) )
      {
        v21 = 1;
      }
      WPP_SF__ATTRTYP_LOG_(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        521734661,
        2,
        13,
        v21,
        v19,
        24,
        (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
    }
    RandomPassword = -1073741823;
    goto LABEL_181;
  }
  v23 = nSize;
  Buffer[nSize] = 36;
  v24 = v23 + 1;
  if ( v24 >= 17 )
    _report_rangecheckfailure();
  Buffer[v24] = 0;
  RandomPassword = SampGenerateRandomPassword(SourceString, 257);
  if ( RandomPassword >= 0 )
  {
    v25 = -1;
    do
      ++v25;
    while ( Buffer[v25] );
    LOWORD(v77) = 2 * v25;
    WORD1(v77) = 2 * v25 + 2;
    *((_QWORD *)&v77 + 1) = Buffer;
    RandomPassword = SamILookupNamesInDomain(a1, 512, 1, &v77, hMem, v79);
    if ( RandomPassword == -1073741709 )
    {
      v26 = a1[50];
      v76 = 0;
      NextCurrentRidFromIndex = SampAllocateNextCurrentRidFromIndex(v26);
      LOBYTE(v71) = 0;
      LOBYTE(v70) = 0;
      RandomPassword = SampCreateUserInDomain(
                         a1,
                         &v77,
                         256,
                         0x10000000,
                         v70,
                         v71,
                         &v73,
                         &v76,
                         &NextCurrentRidFromIndex,
                         0,
                         0);
      if ( RandomPassword < 0 )
      {
        if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
          || (unsigned int)THStateCheckForTraceOverride(v28, v27)
          || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
          || gfTraceToSecondProvider
          && ((unsigned int)THStateCheckForTraceOverride(v28, v27)
           || (unsigned int)ThStateCheckIfTraceToSecondProvier()
           && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v29 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v28, v27)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v28, v27)
            || (v30 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v31 = 0, v30) )
          {
            v31 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            521734740,
            2,
            13,
            v31,
            v29,
            25,
            (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
        }
        goto LABEL_181;
      }
      goto LABEL_73;
    }
    if ( RandomPassword )
    {
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v64, v63)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v65 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v64, v63)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v64, v63)
          || (v66 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v67 = 0, v66) )
        {
          v67 = 1;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521734771,
          2,
          13,
          v67,
          v65,
          27,
          (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
      }
    }
    else
    {
      RandomPassword = SamrOpenUser(a1, 0x10000000, *(unsigned int *)hMem[1], &v73);
      if ( RandomPassword >= 0 )
      {
        NextCurrentRidFromIndex = *(_DWORD *)hMem[1];
LABEL_73:
        RandomPassword = SamrQueryInformationUser2(v73, 16, &v74);
        if ( RandomPassword >= 0 )
        {
          *v74 &= ~4u;
          v42 = *v74 & 0xFFFFFFFE;
          *v74 = v42;
          v42 &= 0xFFFFFE27;
          *v74 = v42;
          v42 |= 0x100u;
          *v74 = v42;
          *v74 = v42 | 0x2000;
          RandomPassword = SamrSetInformationUser(v73, 16, v74);
          if ( RandomPassword >= 0 )
          {
            RandomPassword = SampSetPassword(v73, &v77, NextCurrentRidFromIndex, SourceString);
            if ( RandomPassword >= 0 )
            {
              RandomPassword = DsSamSetMachineAccountSecret(SourceString);
              if ( RandomPassword >= 0 )
              {
                if ( (int)DsSamSetLsaMachineAccountInfo(v73) < 0
                  && ((unsigned int)IncrementWPPPerfCountersForLevel(3)
                   || (unsigned int)THStateCheckForTraceOverride(v59, v58)
                   || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 3, 13)
                   || gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v59, v58)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13))) )
                {
                  v60 = gfTraceToSecondProvider
                     && ((unsigned int)THStateCheckForTraceOverride(v59, v58)
                      || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                      && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 3, 13));
                  if ( (unsigned int)THStateCheckForTraceOverride(v59, v58)
                    || (v61 = CheckWPPLevelFlagsEnabledForProvider(0, 3, 13), v62 = 0, v61) )
                  {
                    v62 = 1;
                  }
                  WPP_SF__ATTRTYP_LOG_(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    521734851,
                    3,
                    13,
                    v62,
                    v60,
                    32,
                    (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
                }
                RandomPassword = DsSamSetNtDsaLink(*((struct _DSNAME **)v73 + 22));
              }
              else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                     || (unsigned int)THStateCheckForTraceOverride(v54, v53)
                     || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
                     || gfTraceToSecondProvider
                     && ((unsigned int)THStateCheckForTraceOverride(v54, v53)
                      || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                      && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
              {
                v55 = gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v54, v53)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
                if ( (unsigned int)THStateCheckForTraceOverride(v54, v53)
                  || (v56 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v57 = 0, v56) )
                {
                  v57 = 1;
                }
                WPP_SF__ATTRTYP_LOG_(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  521734837,
                  2,
                  13,
                  v57,
                  v55,
                  31,
                  (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
              }
            }
            else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                   || (unsigned int)THStateCheckForTraceOverride(v49, v48)
                   || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
                   || gfTraceToSecondProvider
                   && ((unsigned int)THStateCheckForTraceOverride(v49, v48)
                    || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                    && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
            {
              v50 = gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v49, v48)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
              if ( (unsigned int)THStateCheckForTraceOverride(v49, v48)
                || (v51 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v52 = 0, v51) )
              {
                v52 = 1;
              }
              WPP_SF__ATTRTYP_LOG_(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                521734826,
                2,
                13,
                v52,
                v50,
                30,
                (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
            }
          }
          else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
                 || (unsigned int)THStateCheckForTraceOverride(v44, v43)
                 || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
                 || gfTraceToSecondProvider
                 && ((unsigned int)THStateCheckForTraceOverride(v44, v43)
                  || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                  && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
          {
            v45 = gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v44, v43)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
            if ( (unsigned int)THStateCheckForTraceOverride(v44, v43)
              || (v46 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v47 = 0, v46) )
            {
              v47 = 1;
            }
            WPP_SF__ATTRTYP_LOG_(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              521734808,
              2,
              13,
              v47,
              v45,
              29,
              (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
          }
        }
        else if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
               || (unsigned int)THStateCheckForTraceOverride(v38, v37)
               || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
               || gfTraceToSecondProvider
               && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
                || (unsigned int)ThStateCheckIfTraceToSecondProvier()
                && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
        {
          v39 = gfTraceToSecondProvider
             && ((unsigned int)THStateCheckForTraceOverride(v38, v37)
              || (unsigned int)ThStateCheckIfTraceToSecondProvier()
              && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
          if ( (unsigned int)THStateCheckForTraceOverride(v38, v37)
            || (v40 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v41 = 0, v40) )
          {
            v41 = 1;
          }
          WPP_SF__ATTRTYP_LOG_(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            521734789,
            2,
            13,
            v41,
            v39,
            28,
            (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
        }
        goto LABEL_181;
      }
      if ( (unsigned int)IncrementWPPPerfCountersForLevel(2)
        || (unsigned int)THStateCheckForTraceOverride(v33, v32)
        || (unsigned int)CheckWPPLevelFlagsEnabledForProvider(0, 2, 13)
        || gfTraceToSecondProvider
        && ((unsigned int)THStateCheckForTraceOverride(v33, v32)
         || (unsigned int)ThStateCheckIfTraceToSecondProvier()
         && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13)) )
      {
        v34 = gfTraceToSecondProvider
           && ((unsigned int)THStateCheckForTraceOverride(v33, v32)
            || (unsigned int)ThStateCheckIfTraceToSecondProvier()
            && (unsigned int)CheckWPPLevelFlagsEnabledForProvider(1, 2, 13));
        if ( (unsigned int)THStateCheckForTraceOverride(v33, v32)
          || (v35 = CheckWPPLevelFlagsEnabledForProvider(0, 2, 13), v36 = 0, v35) )
        {
          v36 = 1;
        }
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          521734761,
          2,
          13,
          v36,
          v34,
          26,
          (__int64)&WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids);
      }
    }
  }
LABEL_181:
  v68 = SourceString;
  do
  {
    *(_BYTE *)v68 = 0;
    v68 = (WCHAR *)((char *)v68 + 1);
    --v6;
  }
  while ( v6 );
  if ( v73 )
    SamrCloseHandle(&v73);
  if ( v74 )
    SamIFree_SAMPR_USER_INFO_BUFFER(v74, 16);
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( v79[1] )
    LocalFree(v79[1]);
  return (unsigned int)RandomPassword;
}

```

## disassembly

```asm
0x1803a72f4  push    rbp
0x1803a72f6  push    rbx
0x1803a72f7  push    rsi
0x1803a72f8  push    rdi
0x1803a72f9  push    r12
0x1803a72fb  push    r13
0x1803a72fd  push    r14
0x1803a72ff  push    r15
0x1803a7301  lea     rbp, [rsp-208h]
0x1803a7309  sub     rsp, 308h
0x1803a7310  mov     rax, cs:__security_cookie
0x1803a7317  xor     rax, rsp
0x1803a731a  mov     [rbp+240h+var_50], rax
0x1803a7321  xor     r12d, r12d
0x1803a7324  mov     [rsp+340h+nSize], 10h
0x1803a732c  xorps   xmm0, xmm0
0x1803a732f  mov     [rsp+340h+var_2E0], r12d
0x1803a7334  xorps   xmm1, xmm1
0x1803a7337  mov     [rsp+340h+var_2D8], r12
0x1803a733c  mov     rbx, rcx
0x1803a733f  mov     [rsp+340h+var_2D0], r12
0x1803a7344  lea     ecx, [r12+18h]
0x1803a7349  lea     r13d, [r12+1]
0x1803a734e  movups  [rbp+240h+var_2C0], xmm0
0x1803a7352  lea     rax, [rbp+240h+Buffer]
0x1803a7356  movups  xmmword ptr [rbp+240h+hMem], xmm0
0x1803a735a  movups  xmmword ptr [rbp+240h+var_2A0], xmm1
0x1803a735e  mov     [rax], r12b
0x1803a7361  add     rax, r13
0x1803a7364  sub     rcx, r13
0x1803a7367  jnz     short loc_1803A735E
0x1803a7369  mov     ecx, 22h ; '"'
0x1803a736e  lea     rax, [rbp+240h+Buffer]
0x1803a7372  mov     [rax], r12b
0x1803a7375  add     rax, r13
0x1803a7378  sub     rcx, r13
0x1803a737b  jnz     short loc_1803A7372
0x1803a737d  mov     r15d, 202h
0x1803a7383  lea     rax, [rbp+240h+SourceString]
0x1803a7387  mov     ecx, r15d
0x1803a738a  mov     [rax], r12b
0x1803a738d  add     rax, r13
0x1803a7390  sub     rcx, r13
0x1803a7393  jnz     short loc_1803A738A
0x1803a7395  mov     ecx, 10h
0x1803a739a  lea     rax, [rbp+240h+hMem]
0x1803a739e  mov     [rax], r12b
0x1803a73a1  add     rax, r13
0x1803a73a4  sub     rcx, r13
0x1803a73a7  jnz     short loc_1803A739E
0x1803a73a9  mov     ecx, 10h
0x1803a73ae  lea     rax, [rbp+240h+var_2A0]
0x1803a73b2  mov     [rax], r12b
0x1803a73b5  add     rax, r13
0x1803a73b8  sub     rcx, r13
0x1803a73bb  jnz     short loc_1803A73B2
0x1803a73bd  lea     rdx, [rsp+340h+nSize]; nSize
0x1803a73c2  lea     rcx, [rbp+240h+Buffer]; lpBuffer
0x1803a73c6  call    cs:__imp_GetComputerNameW
0x1803a73cc  test    eax, eax
0x1803a73ce  jnz     loc_1803A74D9
0x1803a73d4  lea     edi, [rax+2]
0x1803a73d7  mov     ecx, edi
0x1803a73d9  call    IncrementWPPPerfCountersForLevel
0x1803a73de  lea     ebx, [rdi+0Bh]
0x1803a73e1  test    eax, eax
0x1803a73e3  jnz     short loc_1803A7437
0x1803a73e5  call    THStateCheckForTraceOverride
0x1803a73ea  test    eax, eax
0x1803a73ec  jnz     short loc_1803A7437
0x1803a73ee  mov     r8d, ebx
0x1803a73f1  mov     edx, edi
0x1803a73f3  xor     ecx, ecx
0x1803a73f5  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a73fa  test    eax, eax
0x1803a73fc  jnz     short loc_1803A7437
0x1803a73fe  mov     eax, cs:gfTraceToSecondProvider
0x1803a7404  test    eax, eax
0x1803a7406  jz      loc_1803A74CF
0x1803a740c  call    THStateCheckForTraceOverride
0x1803a7411  test    eax, eax
0x1803a7413  jnz     short loc_1803A7437
0x1803a7415  call    ThStateCheckIfTraceToSecondProvier
0x1803a741a  test    eax, eax
0x1803a741c  jz      loc_1803A74CF
0x1803a7422  mov     r8d, ebx
0x1803a7425  mov     edx, edi
0x1803a7427  mov     ecx, r13d
0x1803a742a  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a742f  test    eax, eax
0x1803a7431  jz      loc_1803A74CF
0x1803a7437  call    cs:__imp_GetLastError
0x1803a743d  mov     ecx, cs:gfTraceToSecondProvider
0x1803a7443  mov     r14d, eax
0x1803a7446  test    ecx, ecx
0x1803a7448  jz      short loc_1803A7472
0x1803a744a  call    THStateCheckForTraceOverride
0x1803a744f  test    eax, eax
0x1803a7451  jnz     short loc_1803A746D
0x1803a7453  call    ThStateCheckIfTraceToSecondProvier
0x1803a7458  test    eax, eax
0x1803a745a  jz      short loc_1803A7472
0x1803a745c  mov     r8d, ebx
0x1803a745f  mov     edx, edi
0x1803a7461  mov     ecx, r13d
0x1803a7464  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a7469  test    eax, eax
0x1803a746b  jz      short loc_1803A7472
0x1803a746d  mov     esi, r13d
0x1803a7470  jmp     short loc_1803A7475
0x1803a7472  mov     esi, r12d
0x1803a7475  call    THStateCheckForTraceOverride
0x1803a747a  test    eax, eax
0x1803a747c  jnz     short loc_1803A7491
0x1803a747e  mov     r8d, ebx
0x1803a7481  mov     edx, edi
0x1803a7483  xor     ecx, ecx
0x1803a7485  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a748a  mov     ecx, r12d
0x1803a748d  test    eax, eax
0x1803a748f  jz      short loc_1803A7494
0x1803a7491  mov     ecx, r13d
0x1803a7494  mov     dword ptr [rsp+340h+var_300], r14d
0x1803a7499  lea     rax, WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids
0x1803a74a0  mov     [rsp+340h+var_308], rax
0x1803a74a5  mov     r9d, ebx
0x1803a74a8  mov     word ptr [rsp+340h+var_310], 18h
0x1803a74af  mov     r8d, edi
0x1803a74b2  mov     dword ptr [rsp+340h+var_318], esi
0x1803a74b6  mov     edx, 1F190A05h
0x1803a74bb  mov     dword ptr [rsp+340h+var_320], ecx
0x1803a74bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1803a74c6  mov     rcx, [rcx+10h]
0x1803a74ca  call    WPP_SF__ATTRTYP_LOG_
0x1803a74cf  mov     esi, 0C0000001h
0x1803a74d4  jmp     loc_1803A7DE1
0x1803a74d9  mov     ecx, [rsp+340h+nSize]
0x1803a74dd  mov     edx, 24h ; '$'
0x1803a74e2  mov     [rbp+rcx*2+240h+Buffer], dx
0x1803a74e7  inc     ecx
0x1803a74e9  add     rcx, rcx
0x1803a74ec  cmp     rcx, 22h ; '"'
0x1803a74f0  jnb     loc_1803A7E5A
0x1803a74f6  mov     [rbp+rcx+240h+Buffer], r12w
0x1803a74fc  mov     edx, 101h
0x1803a7501  lea     rcx, [rbp+240h+SourceString]
0x1803a7505  call    cs:__imp_SampGenerateRandomPassword
0x1803a750b  mov     esi, eax
0x1803a750d  test    eax, eax
0x1803a750f  js      loc_1803A7DE1
0x1803a7515  lea     rcx, [rbp+240h+Buffer]
0x1803a7519  or      rax, 0FFFFFFFFFFFFFFFFh
0x1803a751d  inc     rax
0x1803a7520  cmp     [rcx+rax*2], r12w
0x1803a7525  jnz     short loc_1803A751D
0x1803a7527  add     ax, ax
0x1803a752a  lea     r9, [rbp+240h+var_2C0]
0x1803a752e  mov     word ptr [rbp+240h+var_2C0], ax
0x1803a7532  mov     edi, 2
0x1803a7537  add     ax, di
0x1803a753a  mov     r8d, r13d
0x1803a753d  mov     word ptr [rbp+240h+var_2C0+2], ax
0x1803a7541  mov     edx, 200h
0x1803a7546  lea     rax, [rbp+240h+Buffer]
0x1803a754a  mov     rcx, rbx
0x1803a754d  mov     qword ptr [rbp+240h+var_2C0+8], rax
0x1803a7551  lea     rax, [rbp+240h+var_2A0]
0x1803a7555  mov     [rsp+340h+var_318], rax
0x1803a755a  lea     rax, [rbp+240h+hMem]
0x1803a755e  mov     [rsp+340h+var_320], rax
0x1803a7563  call    cs:__imp_SamILookupNamesInDomain
0x1803a7569  mov     esi, eax
0x1803a756b  mov     r14d, 100h
0x1803a7571  cmp     eax, 0C0000073h
0x1803a7576  jnz     loc_1803A76B8
0x1803a757c  mov     ecx, [rbx+0C8h]
0x1803a7582  mov     [rsp+340h+var_2C4], r12d
0x1803a7587  call    cs:__imp_SampAllocateNextCurrentRidFromIndex
0x1803a758d  mov     [rsp+340h+var_2F0], r12b
0x1803a7592  lea     rdx, [rbp+240h+var_2C0]
0x1803a7596  mov     [rsp+340h+var_2F8], r12b
0x1803a759b  mov     r9d, 10000000h
0x1803a75a1  mov     [rsp+340h+var_2E0], eax
0x1803a75a5  mov     r8d, r14d
0x1803a75a8  lea     rax, [rsp+340h+var_2E0]
0x1803a75ad  mov     rcx, rbx
0x1803a75b0  mov     [rsp+340h+var_300], rax
0x1803a75b5  lea     rax, [rsp+340h+var_2C4]
0x1803a75ba  mov     [rsp+340h+var_308], rax
0x1803a75bf  lea     rax, [rsp+340h+var_2D8]
0x1803a75c4  mov     [rsp+340h+var_310], rax
0x1803a75c9  mov     byte ptr [rsp+340h+var_318], r12b
0x1803a75ce  mov     byte ptr [rsp+340h+var_320], r12b
0x1803a75d3  call    cs:__imp_SampCreateUserInDomain
0x1803a75d9  mov     esi, eax
0x1803a75db  test    eax, eax
0x1803a75dd  jns     loc_1803A77C5
0x1803a75e3  mov     ecx, edi
0x1803a75e5  call    IncrementWPPPerfCountersForLevel
0x1803a75ea  lea     ebx, [rdi+0Bh]
0x1803a75ed  test    eax, eax
0x1803a75ef  jnz     short loc_1803A7643
0x1803a75f1  call    THStateCheckForTraceOverride
0x1803a75f6  test    eax, eax
0x1803a75f8  jnz     short loc_1803A7643
0x1803a75fa  mov     r8d, ebx
0x1803a75fd  mov     edx, edi
0x1803a75ff  xor     ecx, ecx
0x1803a7601  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a7606  test    eax, eax
0x1803a7608  jnz     short loc_1803A7643
0x1803a760a  mov     eax, cs:gfTraceToSecondProvider
0x1803a7610  test    eax, eax
0x1803a7612  jz      loc_1803A7DE1
0x1803a7618  call    THStateCheckForTraceOverride
0x1803a761d  test    eax, eax
0x1803a761f  jnz     short loc_1803A7643
0x1803a7621  call    ThStateCheckIfTraceToSecondProvier
0x1803a7626  test    eax, eax
0x1803a7628  jz      loc_1803A7DE1
0x1803a762e  mov     r8d, ebx
0x1803a7631  mov     edx, edi
0x1803a7633  mov     ecx, r13d
0x1803a7636  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a763b  test    eax, eax
0x1803a763d  jz      loc_1803A7DE1
0x1803a7643  mov     eax, cs:gfTraceToSecondProvider
0x1803a7649  test    eax, eax
0x1803a764b  jz      short loc_1803A7675
0x1803a764d  call    THStateCheckForTraceOverride
0x1803a7652  test    eax, eax
0x1803a7654  jnz     short loc_1803A7670
0x1803a7656  call    ThStateCheckIfTraceToSecondProvier
0x1803a765b  test    eax, eax
0x1803a765d  jz      short loc_1803A7675
0x1803a765f  mov     r8d, ebx
0x1803a7662  mov     edx, edi
0x1803a7664  mov     ecx, r13d
0x1803a7667  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a766c  test    eax, eax
0x1803a766e  jz      short loc_1803A7675
0x1803a7670  mov     r14d, r13d
0x1803a7673  jmp     short loc_1803A7678
0x1803a7675  mov     r14d, r12d
0x1803a7678  call    THStateCheckForTraceOverride
0x1803a767d  test    eax, eax
0x1803a767f  jnz     short loc_1803A7694
0x1803a7681  mov     r8d, ebx
0x1803a7684  mov     edx, edi
0x1803a7686  xor     ecx, ecx
0x1803a7688  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a768d  mov     ecx, r12d
0x1803a7690  test    eax, eax
0x1803a7692  jz      short loc_1803A7697
0x1803a7694  mov     ecx, r13d
0x1803a7697  mov     dword ptr [rsp+340h+var_300], esi
0x1803a769b  lea     rax, WPP_6f8e4ca745443eef45ccf16f9252d675_Traceguids
0x1803a76a2  mov     [rsp+340h+var_308], rax
0x1803a76a7  mov     edx, 1F190A54h
0x1803a76ac  mov     word ptr [rsp+340h+var_310], 19h
0x1803a76b3  jmp     loc_1803A7DC2
0x1803a76b8  test    esi, esi
0x1803a76ba  jnz     loc_1803A7CF0
0x1803a76c0  mov     r8, [rbp+240h+hMem+8]
0x1803a76c4  lea     r9, [rsp+340h+var_2D8]
0x1803a76c9  mov     edx, 10000000h
0x1803a76ce  mov     rcx, rbx
0x1803a76d1  mov     r8d, [r8]
0x1803a76d4  call    cs:__imp_SamrOpenUser
0x1803a76da  mov     esi, eax
0x1803a76dc  test    eax, eax
0x1803a76de  jns     loc_1803A77BB
0x1803a76e4  mov     ecx, edi
0x1803a76e6  call    IncrementWPPPerfCountersForLevel
0x1803a76eb  mov     ebx, 0Dh
0x1803a76f0  test    eax, eax
0x1803a76f2  jnz     short loc_1803A7746
0x1803a76f4  call    THStateCheckForTraceOverride
0x1803a76f9  test    eax, eax
0x1803a76fb  jnz     short loc_1803A7746
0x1803a76fd  mov     r8d, ebx
0x1803a7700  mov     edx, edi
0x1803a7702  xor     ecx, ecx
0x1803a7704  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a7709  test    eax, eax
0x1803a770b  jnz     short loc_1803A7746
0x1803a770d  mov     eax, cs:gfTraceToSecondProvider
0x1803a7713  test    eax, eax
0x1803a7715  jz      loc_1803A7DE1
0x1803a771b  call    THStateCheckForTraceOverride
0x1803a7720  test    eax, eax
0x1803a7722  jnz     short loc_1803A7746
0x1803a7724  call    ThStateCheckIfTraceToSecondProvier
0x1803a7729  test    eax, eax
0x1803a772b  jz      loc_1803A7DE1
0x1803a7731  mov     r8d, ebx
0x1803a7734  mov     edx, edi
0x1803a7736  mov     ecx, r13d
0x1803a7739  call    CheckWPPLevelFlagsEnabledForProvider
0x1803a773e  test    eax, eax
  ... truncated ...
```
