# _lambda_587cf14e4f8abfa46542bace80f7f048_::operator()

- ea: `0x180067c44`
- end: `0x1800683ca`
- name: `_lambda_587cf14e4f8abfa46542bace80f7f048_::operator()`
- size: `1926`
- prototype: `_DWORD *__fastcall(__int64)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting`

## callers

- `0x180067608`

## callees

- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x180008cb8`
- `0x18000d0d8`
- `0x18000ee90`
- `0x180011f00`
- `0x1800298ac`
- `0x180031cf0`
- `0x180031f90`
- `0x1800344ac`
- `0x180034ad0`
- `0x1800430b8`
- `0x180043148`
- `0x180046650`
- `0x18004e5a4`
- `0x180054638`
- `0x1800602a8`
- `0x180067c44`
- `0x1800e3894`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006823a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068395`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006823a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068395`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067d67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067f64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068171`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800681ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800681e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006821b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006828c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800682cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068321`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006834a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067d67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067f64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068171`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800681ab`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800681e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006821b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006828c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800682cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180068321`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006834a`
- `SPOOLSS!DllFreeSplMem` at `0x1800680dc`
- `SPOOLSS!DllFreeSplMem` at `0x1800680ea`
- `SPOOLSS!DllFreeSplMem` at `0x1800680f3`
- `SPOOLSS!DllFreeSplMem` at `0x1800680dc`
- `SPOOLSS!DllFreeSplMem` at `0x1800680ea`
- `SPOOLSS!DllFreeSplMem` at `0x1800680f3`
- `SPOOLSS!DllAllocSplMem` at `0x180068064`
- `SPOOLSS!DllAllocSplMem` at `0x180068072`
- `SPOOLSS!DllAllocSplMem` at `0x180068064`
- `SPOOLSS!DllAllocSplMem` at `0x180068072`
- `SPOOLSS!CheckLocalCall` at `0x180067cf9`
- `SPOOLSS!CheckLocalCall` at `0x180067cf9`
- `SPOOLSS!AddJobW` at `0x180067dfb`
- `SPOOLSS!AddJobW` at `0x180067dfb`

## string_xrefs

- `0x180068274`: `Cannot call AddJob on printer with PRINTER_ATTRIBUTE_DIRECT set.  Failing with ERROR_INVALID_ACCESS.`
- `0x18006839e`: `Failed to create a new job entry. Error %d`

## pseudocode

```c
_DWORD *__fastcall lambda_587cf14e4f8abfa46542bace80f7f048_::operator()(__int64 a1)
{
  __int64 *v1; // rax
  unsigned __int64 *v2; // r8
  _DWORD *v4; // rcx
  unsigned __int64 v5; // r13
  __int64 v6; // rbx
  __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  unsigned int v9; // eax
  unsigned __int16 v10; // r14
  __int64 v11; // rcx
  DWORD v12; // ecx
  _DWORD *result; // rax
  _DWORD *v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // r14
  int v17; // eax
  __int64 v18; // r15
  __int64 v19; // rcx
  unsigned int NextIdInternal; // eax
  __int64 v21; // rcx
  unsigned __int64 v22; // r15
  const wchar_t *v23; // r12
  __int64 v24; // rcx
  char *v25; // rdx
  int v26; // eax
  __int64 v27; // r12
  __int64 v28; // rdx
  unsigned int v29; // edx
  __int64 *v30; // rcx
  __int64 v31; // rax
  _DWORD *v32; // rax
  unsigned int v33; // ecx
  __int64 JobEntry; // rax
  __int64 v35; // rcx
  struct INIJOB *v36; // r13
  unsigned int v37; // eax
  __int16 v38; // r8
  __int64 v39; // r10
  __int64 v40; // r11
  __int64 v41; // r14
  unsigned __int16 *v42; // rax
  unsigned __int16 *v43; // r15
  int v44; // r10d
  __int64 *i; // rcx
  __int64 v46; // rcx
  __int64 v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rcx
  const char *v50; // r9
  const char *v51; // r9
  const char *v52; // r9
  const char *v53; // r9
  DWORD LastError; // eax
  const char *v55; // r9
  const char *v56; // r9
  const char *v57; // r9
  const char *v58; // r9
  const char *v59; // r9
  __int64 v60; // rax
  DWORD v61; // eax
  const char *v62; // r9
  __int64 v63; // [rsp+28h] [rbp-D8h]
  __int64 v64; // [rsp+30h] [rbp-D0h]
  __int64 v65; // [rsp+38h] [rbp-C8h]
  __int64 v66; // [rsp+40h] [rbp-C0h]
  int v67; // [rsp+40h] [rbp-C0h]
  _QWORD *v68; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v69[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v1 = *(__int64 **)a1;
  v2 = *(unsigned __int64 **)(a1 + 8);
  v4 = *(_DWORD **)(a1 + 16);
  v5 = 0;
  v6 = *v1;
  v68 = (_QWORD *)*v2;
  v7 = (unsigned int)(*v4 - 1);
  if ( *v4 != 1 )
  {
    if ( (unsigned int)(*v4 - 2) > 1 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
        L"Invalid level for call.");
      SetLastError(0x7Cu);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x70,
        (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
        v50);
    }
    v7 = **(unsigned int **)(a1 + 24);
    if ( (unsigned int)v7 < 0x12 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
        L"Buffer size %d is insufficient for a level 3 AddJob call.  Failing with ERROR_INVALID_DATATYPE.",
        (unsigned int)v7);
      SetLastError(0x70Cu);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x57,
        (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
        v51);
    }
    v5 = *v2 + *(_QWORD *)*v2;
    if ( v5 <= *v2 || (v8 = v7 + *v2, v5 > v8) )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
        L"pData structure failed validation for a level 3 AddJob call.  Failing with ERROR_INVALID_LEVEL.");
      SetLastError(0x7Cu);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x63,
        (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
        v52);
    }
    v4 = (_DWORD *)((v8 - 2) & 0xFFFFFFFFFFFFFFFEuLL);
    *(_WORD *)v4 = 0;
  }
  v9 = CheckLocalCall(v4, v7);
  v10 = v9;
  if ( v9 == 1 )
  {
    LODWORD(v66) = 1;
  }
  else
  {
    if ( v9 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
        L"Failed to determine whether the call is local or remote.  Error 0x%x.",
        v9);
      SetLastError(v10);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x86,
        (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
        v53);
    }
    LODWORD(v66) = 0;
  }
  EnterSplSem(0);
  if ( !(unsigned int)ValidateSpoolHandle(v6, 18) )
  {
    LeaveSplSem(v11);
    LocalSpoolerTelemetry::WriteDbgTraceWarning(
      "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
      L"Handle is invalid for AddJob.");
    v12 = 6;
LABEL_13:
    SetLastError(v12);
    result = *(_DWORD **)(a1 + 32);
    *result = 0;
    return result;
  }
  if ( (*(_BYTE *)(v6 + 88) & 0x40) != 0 )
  {
    LeaveSplSem(v11);
    LocalSpoolerTelemetry::WriteDbgTraceWarning(
      "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
      L"Failed with ERROR_INVALID_PARAMETER. AddJob called on a remote handle.");
LABEL_16:
    v12 = 87;
    goto LABEL_13;
  }
  if ( (*(_BYTE *)(v6 + 88) & 4) != 0 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(v6 + 72) + 48LL) & 0x8000) != 0 )
    {
      LeaveSplSem(v11);
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
        L"Cannot invoke AddJob on a port handle when a port monitor is active. Failing with ERROR_INVALID_PARAMETER.");
      goto LABEL_16;
    }
    v14 = *(_DWORD **)(a1 + 16);
    if ( (unsigned int)(*v14 - 2) <= 1 )
      *v14 = 1;
    LeaveSplSem(v14);
    **(_DWORD **)(a1 + 32) = AddJobW(
                               *(HANDLE *)(v6 + 104),
                               **(_DWORD **)(a1 + 16),
                               **(LPBYTE **)(a1 + 8),
                               **(_DWORD **)(a1 + 24),
                               **(LPDWORD **)(a1 + 40));
    if ( !**(_DWORD **)(a1 + 32) )
    {
      LastError = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
        L"AddJob for masq printer failed.  Error %d",
        LastError);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xDD,
        (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
        v55);
    }
    EnterSplSem(0);
    *(_DWORD *)(v6 + 112) |= 0x10u;
    return (_DWORD *)LeaveSplSem(v15);
  }
  else
  {
    v16 = *(_QWORD *)(v6 + 64);
    v17 = *(_DWORD *)(v16 + 152);
    if ( (v17 & 2) != 0 )
    {
      LeaveSplSem(v11);
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
        L"Cannot call AddJob on printer with PRINTER_ATTRIBUTE_DIRECT set.  Failing with ERROR_INVALID_ACCESS.");
      SetLastError(0xCu);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xEB,
        (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
        v56);
    }
    if ( (v17 & 0x1000) != 0 )
    {
      v18 = *(_QWORD *)(v6 + 40);
      if ( !v18 )
        v18 = *(_QWORD *)(v16 + 64);
      if ( !(unsigned int)ValidRawDatatype(v18) )
      {
        LeaveSplSem(v19);
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
          L"Datatype (%ws) is not RAW, but PRINTER_ATTRIBUTE_RAW_ONLY is set on the printer.  Failing call with ERROR_INVALID_DATATYPE.",
          v18);
        SetLastError(0x70Cu);
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xFA,
          (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
          v57);
      }
    }
    NextIdInternal = GetNextIdInternal(*(void **)(*(_QWORD *)(v16 + 280) + 264LL), (*(_DWORD *)(v6 + 88) >> 10) & 1);
    v22 = NextIdInternal;
    if ( !NextIdInternal )
    {
      LeaveSplSem(v21);
      LocalSpoolerTelemetry::LogPrintQError(
        (struct _INIPRINTER *)v16,
        L"SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
        270,
        0x3Du);
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
        L"Print queue is full, cannot add a new job.  Failing with ERROR_PRINTQ_FULL.");
      SetLastError(0x3Du);
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x111,
        (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
        v58);
    }
    if ( *(_DWORD *)(v16 + 308) )
    {
      v23 = *(const wchar_t **)(**(_QWORD **)(*(_QWORD *)(v6 + 64) + 312LL) + 24LL);
      if ( !wcscmp_0(v23, L"FILE:") )
        goto LABEL_67;
      v25 = (char *)((char *)L"PORTPROMPT:" - (char *)v23);
      do
      {
        v26 = *(unsigned __int16 *)&v25[(_QWORD)v23];
        v24 = (unsigned int)*v23 - v26;
        if ( (_DWORD)v24 )
          break;
        ++v23;
      }
      while ( v26 );
      if ( !(_DWORD)v24 )
      {
LABEL_67:
        LeaveSplSem(v24);
        SetLastError(0x32u);
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x11D,
          (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
          v59);
      }
    }
    LODWORD(v63) = *(_DWORD *)(v6 + 88) & 0x40;
    GetFullNameFromId(v16, v22, 1, (__int64)v69, 260, v63, v64, v65, v66);
    v27 = -1;
    v28 = -1;
    do
      ++v28;
    while ( v69[v28] );
    v29 = 2 * v28 + 18;
    ***(_DWORD ***)(a1 + 40) = v29;
    if ( v29 <= **(_DWORD **)(a1 + 24) )
    {
      SplLogJobDiagEvent(&EVENT_TRACE_TYPE_SPL_SPOOLJOB, v22);
      v32 = *(_DWORD **)(a1 + 16);
      if ( *v32 == 2 || (v33 = 524352, *v32 == 3) )
        v33 = 537395264;
      JobEntry = CreateJobEntry((struct _SPOOL *)v6, v67, v33, v5);
      v36 = (struct INIJOB *)JobEntry;
      if ( !JobEntry )
      {
        LOBYTE(v35) = v22 & 0x1F;
        v60 = **(_QWORD **)(*(_QWORD *)(v16 + 280) + 264LL);
        *(_DWORD *)(v60 + 4 * (v22 >> 5)) &= ~(1 << (v22 & 0x1F));
        LeaveSplSem(v35);
        v61 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "SplAddJob::<lambda_587cf14e4f8abfa46542bace80f7f048>::operator ()",
          L"Failed to create a new job entry. Error %d",
          v61);
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x140,
          (unsigned int)"printscan\\print\\spooler\\localspl\\addjob.c",
          v62);
      }
      *(_DWORD *)(JobEntry + 400) = **(_DWORD **)(a1 + 16);
      v37 = ++*(_DWORD *)(v16 + 256);
      if ( v37 > *(_DWORD *)(v16 + 260) )
        *(_DWORD *)(v16 + 260) = v37;
      AddJobEntry((struct _INIPRINTER *)v16, v36);
      do
        ++v27;
      while ( v69[v27] != v38 );
      StringCchCopyW(
        (unsigned __int16 *)(((unsigned __int64)v68 + **(unsigned int **)(a1 + 24) + -2 * v27 - 2)
                           & 0xFFFFFFFFFFFFFFFEuLL),
        v27 + 1,
        v69);
      *(_QWORD *)v40 = v39;
      *(_DWORD *)(v40 + 8) = *((_DWORD *)v36 + 10);
      CheckPortConnectivity((struct _INIPRINTER *)v16);
      SetRPCClientPid((struct _INIPRINTER *)v16);
      v41 = DllAllocSplMem(24);
      v42 = (unsigned __int16 *)DllAllocSplMem(520);
      v43 = v42;
      if ( v41 && v42 )
      {
        StringCchCopyW(v42, 0x104u, v69);
        for ( i = *(__int64 **)(v6 + 272); ; i = (__int64 *)*i )
        {
          if ( !i )
          {
            *(_QWORD *)(v41 + 8) = v43;
            *(_DWORD *)(v41 + 20) = 2;
            *(_DWORD *)(v41 + 16) = v44;
            *(_QWORD *)v41 = *(_QWORD *)(v6 + 272);
            *(_QWORD *)(v6 + 272) = v41;
            goto LABEL_58;
          }
          if ( *((_DWORD *)i + 4) == v44 )
            break;
        }
        *((_DWORD *)i + 5) |= 2u;
        DllFreeSplMem(v43);
        v46 = v41;
      }
      else
      {
        DllFreeSplMem(v41);
        v46 = (__int64)v43;
      }
      DllFreeSplMem(v46);
LABEL_58:
      v47 = *(_QWORD *)(v6 + 168);
      v48 = *(_QWORD *)(v6 + 64);
      *(_DWORD *)(v6 + 112) |= 0x10u;
      *(_QWORD *)(v6 + 80) = v36;
      SetPrinterChange(v48, (_DWORD)v36, (unsigned int)NVAddJob, 258, v47);
      CheckSizeDetectionThread();
      LeaveSplSem(v49);
      result = *(_DWORD **)(a1 + 32);
      *result = 1;
    }
    else
    {
      v30 = *(__int64 **)(*(_QWORD *)(v16 + 280) + 264LL);
      v31 = *v30;
      LOBYTE(v30) = v22 & 0x1F;
      *(_DWORD *)(v31 + 4 * (v22 >> 5)) &= ~(1 << (v22 & 0x1F));
      LeaveSplSem(v30);
      SetLastError(0x7Au);
      result = *(_DWORD **)(a1 + 32);
      *result = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180067c44  push    rbp
0x180067c46  push    rbx
0x180067c47  push    rsi
0x180067c48  push    rdi
0x180067c49  push    r12
0x180067c4b  push    r13
0x180067c4d  push    r14
0x180067c4f  push    r15
0x180067c51  lea     rbp, [rsp-198h]
0x180067c59  sub     rsp, 298h
0x180067c60  mov     rax, cs:__security_cookie
0x180067c67  xor     rax, rsp
0x180067c6a  mov     [rbp+1D0h+var_50], rax
0x180067c71  mov     rax, [rcx]
0x180067c74  xor     r12d, r12d
0x180067c77  mov     r8, [rcx+8]
0x180067c7b  mov     rdi, rcx
0x180067c7e  mov     rcx, [rcx+10h]
0x180067c82  xorps   xmm0, xmm0
0x180067c85  mov     r13d, r12d
0x180067c88  mov     rbx, [rax]
0x180067c8b  mov     rax, [r8]
0x180067c8e  mov     [rsp+2D0h+var_270], rax
0x180067c93  xor     eax, eax
0x180067c95  mov     [rsp+2D0h+var_278], rax
0x180067c9a  movups  [rsp+2D0h+var_288], xmm0
0x180067c9f  mov     edx, [rcx]
0x180067ca1  sub     edx, 1
0x180067ca4  jz      short loc_180067CED
0x180067ca6  sub     edx, 1
0x180067ca9  jz      short loc_180067CB4
0x180067cab  cmp     edx, 1
0x180067cae  jnz     loc_180068159
0x180067cb4  mov     rax, [rdi+18h]
0x180067cb8  mov     edx, [rax]
0x180067cba  cmp     edx, 12h
0x180067cbd  jb      loc_180068190
0x180067cc3  mov     rcx, [r8]
0x180067cc6  mov     r13, [rcx]
0x180067cc9  add     r13, rcx
0x180067ccc  cmp     r13, rcx
0x180067ccf  jbe     loc_1800681CA
0x180067cd5  add     rcx, rdx
0x180067cd8  cmp     r13, rcx
0x180067cdb  ja      loc_1800681CA
0x180067ce1  add     rcx, 0FFFFFFFFFFFFFFFEh
0x180067ce5  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180067ce9  mov     [rcx], r12w
0x180067ced  xor     eax, eax
0x180067cef  mov     [rsp+2D0h+var_278], rax
0x180067cf4  movups  [rsp+2D0h+var_288], xmm0
0x180067cf9  call    cs:__imp_CheckLocalCall
0x180067cff  mov     esi, 1
0x180067d04  mov     r14d, eax
0x180067d07  cmp     eax, esi
0x180067d09  jnz     short loc_180067D18
0x180067d0b  mov     rax, cs:szRemoteDoc
0x180067d12  mov     dword ptr [rsp+2D0h+var_290], esi
0x180067d16  jmp     short loc_180067D2D
0x180067d18  test    r14d, r14d
0x180067d1b  jnz     loc_180068201
0x180067d21  mov     rax, cs:szLocalDoc
0x180067d28  mov     dword ptr [rsp+2D0h+var_290], r12d
0x180067d2d  xor     ecx, ecx
0x180067d2f  mov     qword ptr [rsp+2D0h+var_288], rax
0x180067d34  call    EnterSplSem
0x180067d39  mov     edx, 12h
0x180067d3e  mov     rcx, rbx
0x180067d41  call    ValidateSpoolHandle
0x180067d46  test    eax, eax
0x180067d48  jnz     short loc_180067D79
0x180067d4a  call    LeaveSplSem
0x180067d4f  lea     rdx, aHandleIsInvali_0; "Handle is invalid for AddJob."
0x180067d56  lea     rcx, aSpladdjobLambd; "SplAddJob::<lambda_587cf14e4f8abfa46542"...
0x180067d5d  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180067d62  mov     ecx, 6; dwErrCode
0x180067d67  call    cs:__imp_SetLastError
0x180067d6d  mov     rax, [rdi+20h]
0x180067d71  mov     [rax], r12d
0x180067d74  jmp     loc_180068136
0x180067d79  test    byte ptr [rbx+58h], 40h
0x180067d7d  jz      short loc_180067D9E
0x180067d7f  call    LeaveSplSem
0x180067d84  lea     rdx, aFailedWithErro_0; "Failed with ERROR_INVALID_PARAMETER. Ad"...
0x180067d8b  lea     rcx, aSpladdjobLambd; "SplAddJob::<lambda_587cf14e4f8abfa46542"...
0x180067d92  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180067d97  mov     ecx, 57h ; 'W'
0x180067d9c  jmp     short loc_180067D67
0x180067d9e  test    byte ptr [rbx+58h], 4
0x180067da2  jz      loc_180067E29
0x180067da8  mov     rax, [rbx+48h]
0x180067dac  test    dword ptr [rax+30h], 8000h
0x180067db3  jz      short loc_180067DC3
0x180067db5  call    LeaveSplSem
0x180067dba  lea     rdx, aCannotInvokeAd; "Cannot invoke AddJob on a port handle w"...
0x180067dc1  jmp     short loc_180067D8B
0x180067dc3  mov     rcx, [rdi+10h]
0x180067dc7  mov     eax, [rcx]
0x180067dc9  sub     eax, 2
0x180067dcc  cmp     eax, esi
0x180067dce  ja      short loc_180067DD2
0x180067dd0  mov     [rcx], esi
0x180067dd2  call    LeaveSplSem
0x180067dd7  mov     rax, [rdi+28h]
0x180067ddb  mov     r9, [rdi+18h]
0x180067ddf  mov     r8, [rdi+8]
0x180067de3  mov     rdx, [rdi+10h]
0x180067de7  mov     rax, [rax]
0x180067dea  mov     r9d, [r9]; cbBuf
0x180067ded  mov     r8, [r8]; pData
0x180067df0  mov     edx, [rdx]; Level
0x180067df2  mov     rcx, [rbx+68h]; hPrinter
0x180067df6  mov     [rsp+2D0h+pcbNeeded], rax; pcbNeeded
0x180067dfb  call    cs:__imp_AddJobW
0x180067e01  mov     rcx, [rdi+20h]
0x180067e05  mov     [rcx], eax
0x180067e07  mov     rax, [rdi+20h]
0x180067e0b  cmp     [rax], r12d
0x180067e0e  jz      loc_18006823A
0x180067e14  xor     ecx, ecx
0x180067e16  call    EnterSplSem
0x180067e1b  or      dword ptr [rbx+70h], 10h
0x180067e1f  call    LeaveSplSem
0x180067e24  jmp     loc_180068136
0x180067e29  mov     r14, [rbx+40h]
0x180067e2d  mov     eax, [r14+98h]
0x180067e34  test    al, 2
0x180067e36  jnz     loc_18006826F
0x180067e3c  bt      eax, 0Ch
0x180067e40  jnb     short loc_180067E5F
0x180067e42  mov     r15, [rbx+28h]
0x180067e46  test    r15, r15
0x180067e49  jnz     short loc_180067E4F
0x180067e4b  mov     r15, [r14+40h]
0x180067e4f  mov     rcx, r15
0x180067e52  call    ValidRawDatatype
0x180067e57  test    eax, eax
0x180067e59  jz      loc_1800682AB
0x180067e5f  mov     rcx, [r14+118h]
0x180067e66  mov     edx, [rbx+58h]
0x180067e69  shr     edx, 0Ah
0x180067e6c  and     edx, esi; int
0x180067e6e  mov     rcx, [rcx+108h]; void *
0x180067e75  call    ?GetNextIdInternal@@YAKPEAXH@Z; GetNextIdInternal(void *,int)
0x180067e7a  mov     r15d, eax
0x180067e7d  test    eax, eax
0x180067e7f  jz      loc_1800682EA
0x180067e85  cmp     [r14+134h], r12d
0x180067e8c  jbe     short loc_180067EDF
0x180067e8e  mov     rax, [rbx+40h]
0x180067e92  lea     rdx, aFile_0; "FILE:"
0x180067e99  mov     rcx, [rax+138h]
0x180067ea0  mov     rax, [rcx]
0x180067ea3  mov     r12, [rax+18h]
0x180067ea7  mov     rcx, r12; String1
0x180067eaa  call    wcscmp_0
0x180067eaf  test    eax, eax
0x180067eb1  jz      loc_180068340
0x180067eb7  lea     rdx, szPortPromptPort; "PORTPROMPT:"
0x180067ebe  sub     rdx, r12
0x180067ec1  movzx   ecx, word ptr [r12]
0x180067ec6  movzx   eax, word ptr [r12+rdx]
0x180067ecb  sub     ecx, eax
0x180067ecd  jnz     short loc_180067ED7
0x180067ecf  add     r12, 2
0x180067ed3  test    eax, eax
0x180067ed5  jnz     short loc_180067EC1
0x180067ed7  test    ecx, ecx
0x180067ed9  jz      loc_180068340
0x180067edf  mov     eax, [rbx+58h]
0x180067ee2  lea     r9, [rsp+2D0h+var_260]
0x180067ee7  and     eax, 40h
0x180067eea  mov     r8d, esi
0x180067eed  mov     dword ptr [rsp+2D0h+var_2A8], eax
0x180067ef1  mov     edx, r15d
0x180067ef4  mov     rcx, r14
0x180067ef7  mov     [rsp+2D0h+pcbNeeded], 104h
0x180067f00  call    GetFullNameFromId
0x180067f05  or      r12, 0FFFFFFFFFFFFFFFFh
0x180067f09  lea     rcx, [rsp+2D0h+var_260]
0x180067f0e  mov     rdx, r12
0x180067f11  xor     eax, eax
0x180067f13  inc     rdx
0x180067f16  cmp     [rcx+rdx*2], ax
0x180067f1a  jnz     short loc_180067F13
0x180067f1c  mov     rax, [rdi+28h]
0x180067f20  lea     edx, ds:12h[rdx*2]
0x180067f27  mov     rcx, [rax]
0x180067f2a  mov     [rcx], edx
0x180067f2c  mov     rax, [rdi+18h]
0x180067f30  cmp     edx, [rax]
0x180067f32  jbe     short loc_180067F79
0x180067f34  mov     rax, [r14+118h]
0x180067f3b  mov     rdx, r15
0x180067f3e  shr     rdx, 5
0x180067f42  and     r15d, 1Fh
0x180067f46  mov     rcx, [rax+108h]
0x180067f4d  mov     rax, [rcx]
0x180067f50  mov     cl, r15b
0x180067f53  shl     esi, cl
0x180067f55  not     esi
0x180067f57  and     [rax+rdx*4], esi
0x180067f5a  call    LeaveSplSem
0x180067f5f  mov     ecx, 7Ah ; 'z'; dwErrCode
0x180067f64  call    cs:__imp_SetLastError
0x180067f6a  mov     rax, [rdi+20h]
0x180067f6e  mov     dword ptr [rax], 0
0x180067f74  jmp     loc_180068136
0x180067f79  mov     edx, r15d; unsigned int
0x180067f7c  lea     rcx, EVENT_TRACE_TYPE_SPL_SPOOLJOB; struct _EVENT_DESCRIPTOR *
0x180067f83  call    ?SplLogJobDiagEvent@@YAXPEBU_EVENT_DESCRIPTOR@@K@Z; SplLogJobDiagEvent(_EVENT_DESCRIPTOR const *,ulong)
0x180067f88  mov     rax, [rdi+10h]
0x180067f8c  cmp     dword ptr [rax], 2
0x180067f8f  jz      short loc_180067F9B
0x180067f91  cmp     dword ptr [rax], 3
0x180067f94  mov     ecx, 80040h
0x180067f99  jnz     short loc_180067FA0
0x180067f9b  mov     ecx, 20080040h
0x180067fa0  mov     eax, dword ptr [rsp+2D0h+var_290]
0x180067fa4  lea     r8, [rsp+2D0h+var_288]
0x180067fa9  mov     [rsp+2D0h+var_2A0], r13; __int64
0x180067fae  mov     r9d, r15d
0x180067fb1  mov     dword ptr [rsp+2D0h+var_2A8], ecx; unsigned int
0x180067fb5  mov     edx, esi
0x180067fb7  mov     rcx, rbx; struct _SPOOL *
0x180067fba  mov     dword ptr [rsp+2D0h+pcbNeeded], eax; int
0x180067fbe  call    CreateJobEntry
0x180067fc3  xor     r8d, r8d
0x180067fc6  mov     r13, rax
0x180067fc9  test    rax, rax
0x180067fcc  jz      loc_180068369
0x180067fd2  mov     rax, [rdi+10h]
0x180067fd6  mov     ecx, [rax]
0x180067fd8  mov     [r13+190h], ecx
0x180067fdf  add     [r14+100h], esi
0x180067fe6  mov     eax, [r14+100h]
0x180067fed  cmp     eax, [r14+104h]
0x180067ff4  jbe     short loc_180067FFD
0x180067ff6  mov     [r14+104h], eax
0x180067ffd  mov     rdx, r13; struct INIJOB *
0x180068000  mov     rcx, r14; struct _INIPRINTER *
0x180068003  call    ?AddJobEntry@@YAXPEAU_INIPRINTER@@PEAVINIJOB@@@Z; AddJobEntry(_INIPRINTER *,INIJOB *)
0x180068008  lea     rcx, [rsp+2D0h+var_260]
0x18006800d  inc     r12
0x180068010  cmp     [rcx+r12*2], r8w
0x180068015  jnz     short loc_18006800D
0x180068017  mov     rax, [rdi+18h]
0x18006801b  lea     rdx, [r12+1]; unsigned __int64
0x180068020  mov     r11, [rsp+2D0h+var_270]
0x180068025  lea     r8, [rsp+2D0h+var_260]; unsigned __int16 *
0x18006802a  imul    rcx, rdx, -2
0x18006802e  mov     r10d, [rax]
0x180068031  lea     rax, [r11+rcx]
0x180068035  add     r10, rax
0x180068038  and     r10, 0FFFFFFFFFFFFFFFEh
0x18006803c  mov     rcx, r10; unsigned __int16 *
0x18006803f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180068044  mov     [r11], r10
0x180068047  mov     rcx, r14; struct _INIPRINTER *
0x18006804a  mov     eax, [r13+28h]
0x18006804e  mov     [r11+8], eax
0x180068052  call    ?CheckPortConnectivity@@YAXPEAU_INIPRINTER@@@Z; CheckPortConnectivity(_INIPRINTER *)
0x180068057  mov     rcx, r14; struct _INIPRINTER *
0x18006805a  call    ?SetRPCClientPid@@YAXPEAU_INIPRINTER@@@Z; SetRPCClientPid(_INIPRINTER *)
0x18006805f  mov     ecx, 18h
0x180068064  call    cs:__imp_DllAllocSplMem
0x18006806a  mov     ecx, 208h
0x18006806f  mov     r14, rax
0x180068072  call    cs:__imp_DllAllocSplMem
0x180068078  mov     r15, rax
0x18006807b  test    r14, r14
0x18006807e  jz      short loc_1800680E7
0x180068080  test    rax, rax
0x180068083  jz      short loc_1800680E7
0x180068085  mov     r10d, [r13+28h]
0x180068089  lea     r8, [rsp+2D0h+var_260]; unsigned __int16 *
0x18006808e  mov     edx, 104h; unsigned __int64
0x180068093  mov     rcx, rax; unsigned __int16 *
0x180068096  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006809b  mov     rcx, [rbx+110h]
0x1800680a2  jmp     short loc_1800680AD
0x1800680a4  cmp     [rcx+10h], r10d
0x1800680a8  jz      short loc_1800680D5
0x1800680aa  mov     rcx, [rcx]
0x1800680ad  test    rcx, rcx
0x1800680b0  jnz     short loc_1800680A4
0x1800680b2  mov     [r14+8], r15
0x1800680b6  mov     dword ptr [r14+14h], 2
0x1800680be  mov     [r14+10h], r10d
0x1800680c2  mov     rax, [rbx+110h]
0x1800680c9  mov     [r14], rax
0x1800680cc  mov     [rbx+110h], r14
0x1800680d3  jmp     short loc_1800680F9
0x1800680d5  or      dword ptr [rcx+14h], 2
0x1800680d9  mov     rcx, r15
0x1800680dc  call    cs:__imp_DllFreeSplMem
0x1800680e2  mov     rcx, r14
0x1800680e5  jmp     short loc_1800680F3
0x1800680e7  mov     rcx, r14
0x1800680ea  call    cs:__imp_DllFreeSplMem
  ... truncated ...
```
