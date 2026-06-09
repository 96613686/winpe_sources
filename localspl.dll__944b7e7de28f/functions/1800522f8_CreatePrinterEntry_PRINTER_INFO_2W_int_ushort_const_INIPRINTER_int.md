# CreatePrinterEntry(_PRINTER_INFO_2W *,int,ushort const *,_INIPRINTER *,int *)

- ea: `0x1800522f8`
- end: `0x1800528e9`
- name: `?CreatePrinterEntry@@YAHPEAU_PRINTER_INFO_2W@@HPEBGPEAU_INIPRINTER@@PEAH@Z`
- size: `1521`
- prototype: `__int64 __fastcall(struct _PRINTER_INFO_2W *, int, const unsigned __int16 *, struct _INIPRINTER *, int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18004fe9c`

## callees

- `0x18000e890`
- `0x18001dbf0`
- `0x180024858`
- `0x18002a8dc`
- `0x18002c780`
- `0x18002ce8c`
- `0x18002ee28`
- `0x18003ea2c`
- `0x180041ba0`
- `0x18004486c`
- `0x180046650`
- `0x180047318`
- `0x1800521e0`
- `0x180052294`
- `0x1800522f8`
- `0x180053324`
- `0x180054638`
- `0x1800547e0`
- `0x1800978dc`
- `0x1800979d4`
- `0x180098204`
- `0x1800984d0`
- `0x180098c28`
- `0x180098ccc`

## import_xrefs

- `ntdll!RtlEqualSid` at `0x1800523b4`
- `ntdll!RtlEqualSid` at `0x1800523b4`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800524c3`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x1800524c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800528a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800528a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180052848`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180052848`
- `SPOOLSS!DllFreeSplMem` at `0x1800523c1`
- `SPOOLSS!DllFreeSplMem` at `0x1800523c1`
- `SPOOLSS!DllAllocSplMem` at `0x1800527c1`
- `SPOOLSS!DllAllocSplMem` at `0x1800527c1`
- `SPOOLSS!AllocSplStr` at `0x180052613`
- `SPOOLSS!AllocSplStr` at `0x18005263c`
- `SPOOLSS!AllocSplStr` at `0x180052686`
- `SPOOLSS!AllocSplStr` at `0x1800526d2`
- `SPOOLSS!AllocSplStr` at `0x180052771`
- `SPOOLSS!AllocSplStr` at `0x18005277f`
- `SPOOLSS!AllocSplStr` at `0x180052790`
- `SPOOLSS!AllocSplStr` at `0x18005279e`
- `SPOOLSS!AllocSplStr` at `0x180052613`
- `SPOOLSS!AllocSplStr` at `0x18005263c`
- `SPOOLSS!AllocSplStr` at `0x180052686`
- `SPOOLSS!AllocSplStr` at `0x1800526d2`
- `SPOOLSS!AllocSplStr` at `0x180052771`
- `SPOOLSS!AllocSplStr` at `0x18005277f`
- `SPOOLSS!AllocSplStr` at `0x180052790`
- `SPOOLSS!AllocSplStr` at `0x18005279e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180052440`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180052440`

## string_xrefs

- `0x18005234d`: `GetUserSidFromSidString failed with hr: 0x%x`
- `0x180052357`: `CreatePrinterEntry`
- `0x180052562`: `CreatePrinterEntry`
- `0x180052629`: `CreatePrinterEntry`
- `0x180052660`: `CreatePrinterEntry`
- `0x1800526a9`: `CreatePrinterEntry`
- `0x1800526e8`: `CreatePrinterEntry`
- `0x1800523da`: `GetSplUserSid failed with hr: 0x%x`
- `0x180052558`: `FixPrinterSecurityDescriptor (AC and LPAC) failed %d`
- `0x1800525bd`: `FixPrinterSecurityDescriptor (Restricted Spooler Worker) failed %d`
- `0x180052622`: `Could not allocate per-user SID-adorned PrinterName string.`
- `0x1800526a2`: `Could not allocate ShareName string.`

## pseudocode

```c
__int64 __fastcall CreatePrinterEntry(
        struct _PRINTER_INFO_2W *a1,
        int a2,
        const unsigned __int16 *a3,
        struct _INIPRINTER *a4,
        int *a5)
{
  int UserSidFromSidString; // eax
  int SplUserSid; // eax
  PSID v12; // rsi
  void *v13; // rcx
  char IsEnabled; // al
  DWORD v15; // ecx
  void *PerUserSecurityDescriptor; // rax
  void *v17; // rcx
  void **v18; // rsi
  int v19; // r14d
  unsigned int v20; // r8d
  __int64 v21; // rcx
  unsigned int fixed; // eax
  unsigned int v23; // eax
  int v24; // esi
  const unsigned __int16 *pPrinterName; // rcx
  int AdornedPrinterName; // eax
  LPWSTR pShareName; // rcx
  __int64 v28; // rax
  LPWSTR pDatatype; // rcx
  __int64 v30; // rax
  DWORD Priority; // eax
  __int64 v32; // rax
  bool v33; // zf
  bool v34; // al
  unsigned int v35; // eax
  LPDEVMODEW pDevMode; // rax
  __int64 v37; // rcx
  void *v38; // rax
  DWORD TickCount; // eax
  unsigned int v40; // r8d
  PSID Sid1; // [rsp+30h] [rbp-30h] BYREF
  WORD pControl[2]; // [rsp+38h] [rbp-28h] BYREF
  int v43; // [rsp+3Ch] [rbp-24h] BYREF
  DWORD dwRevision; // [rsp+40h] [rbp-20h] BYREF
  GUID pclsid; // [rsp+48h] [rbp-18h] BYREF

  Sid1 = 0;
  if ( a3 )
  {
    UserSidFromSidString = GetUserSidFromSidString(a3, &Sid1);
    if ( UserSidFromSidString < 0 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "CreatePrinterEntry",
        L"GetUserSidFromSidString failed with hr: 0x%x",
        (unsigned int)UserSidFromSidString);
      return 0;
    }
    goto LABEL_11;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    SplUserSid = GetSplUserSid(&Sid1);
    if ( SplUserSid >= 0 )
    {
LABEL_11:
      v12 = Sid1;
      goto LABEL_12;
    }
LABEL_10:
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreatePrinterEntry",
      L"GetSplUserSid failed with hr: 0x%x",
      (unsigned int)SplUserSid);
    return 0;
  }
  SplUserSid = GetSplUserSid(&Sid1);
  if ( SplUserSid < 0 )
    goto LABEL_10;
  v12 = Sid1;
  if ( RtlEqualSid(Sid1, gRestrictedSpoolerServiceSid) )
  {
    DllFreeSplMem(v12);
    v12 = CopySid(v13);
  }
LABEL_12:
  *((_QWORD *)a4 + 59) = v12;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl);
  v15 = a1->Attributes & 0x400000;
  if ( IsEnabled )
  {
    if ( v15 )
    {
      if ( a1->pSecurityDescriptor )
        return 0;
      PerUserSecurityDescriptor = CreatePerUserSecurityDescriptor(a3);
    }
    else if ( (unsigned int)IsWindowsProtectedPrintEnabled()
           && (pclsid = 0, a1->pSecurityDescriptor)
           && CLSIDFromString(a1->pPrinterName, &pclsid) >= 0 )
    {
      PerUserSecurityDescriptor = DuplicateSecurityDescriptor(a1->pSecurityDescriptor);
    }
    else
    {
      PerUserSecurityDescriptor = CreatePrinterSecurityDescriptorAsSelf(a1->pSecurityDescriptor, a4);
    }
    v17 = PerUserSecurityDescriptor;
    v18 = (void **)((char *)a4 + 192);
  }
  else
  {
    if ( v15 )
    {
      if ( a1->pSecurityDescriptor )
        return 0;
      PerUserSecurityDescriptor = CreatePerUserSecurityDescriptor(a3);
    }
    else
    {
      PerUserSecurityDescriptor = CreatePrinterSecurityDescriptorAsSelf(a1->pSecurityDescriptor, a4);
    }
    v18 = (void **)((char *)a4 + 192);
    v17 = PerUserSecurityDescriptor;
  }
  *v18 = PerUserSecurityDescriptor;
  if ( !v17 )
    return 0;
  dwRevision = 0;
  pControl[0] = 0;
  if ( GetSecurityDescriptorControl(v17, pControl, &dwRevision) )
    v19 = pControl[0] & 8;
  else
    v19 = 1;
  v43 = 0;
  LODWORD(Sid1) = 0;
  if ( a1->pSecurityDescriptor && !ContainsAccessEntriesForAppContainer(*v18, &v43, (int *)&Sid1) )
  {
    v20 = 0;
    pclsid = 0;
    if ( !v43 )
    {
      v20 = 1;
      *(_QWORD *)&pclsid.Data1 = gAppContainerAllAppsSid;
    }
    if ( !(_DWORD)Sid1 )
    {
      v21 = v20++;
      *((_QWORD *)&pclsid.Data1 + v21) = gLPACCapabilitySid;
    }
    fixed = FixPrinterSecurityDescriptor(v18, (void **)&pclsid, v20, 0x20008u, v19);
    if ( fixed )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "CreatePrinterEntry",
        L"FixPrinterSecurityDescriptor (AC and LPAC) failed %d",
        fixed);
      return 0;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl'::`2'::impl) )
  {
    if ( a1->pSecurityDescriptor )
    {
      if ( !ContainsAccessEntriesForRestrictedSpoolerWorker(*v18) )
      {
        v23 = FixPrinterSecurityDescriptor(v18, &gRestrictedSpoolerServiceSid, 1u, 0xF000Cu, v19);
        if ( v23 )
        {
          LocalSpoolerTelemetry::WriteDbgTraceWarning(
            "CreatePrinterEntry",
            L"FixPrinterSecurityDescriptor (Restricted Spooler Worker) failed %d",
            v23);
          return 0;
        }
      }
    }
  }
  *a5 = 0;
  v24 = 0;
  *(_DWORD *)a4 = 18769;
  pPrinterName = a1->pPrinterName;
  if ( (a1->Attributes & 0x400000) != 0 )
  {
    Sid1 = 0;
    if ( a3 )
      AdornedPrinterName = CreateAdornedPrinterName(pPrinterName, a3, (unsigned __int16 **)&Sid1);
    else
      AdornedPrinterName = CreateAdornedPrinterName(pPrinterName, (unsigned __int16 **)&Sid1);
    if ( AdornedPrinterName < 0 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "CreatePrinterEntry",
        L"Could not allocate per-user SID-adorned PrinterName string.");
      v24 = 1;
    }
    else
    {
      *((_QWORD *)a4 + 3) = Sid1;
      *((_QWORD *)a4 + 68) = AllocSplStr(a1->pPrinterName);
    }
  }
  else
  {
    *((_QWORD *)a4 + 3) = AllocSplStr(pPrinterName);
  }
  *((_WORD *)a4 + 16) = HashName(*((_QWORD *)a4 + 3));
  if ( !*((_QWORD *)a4 + 3) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceWarning("CreatePrinterEntry", L"Could not allocate PrinterName string.");
    v24 = 1;
  }
  pShareName = a1->pShareName;
  if ( pShareName )
  {
    v28 = AllocSplStr(pShareName);
    *((_QWORD *)a4 + 5) = v28;
    *((_WORD *)a4 + 24) = HashName(v28);
    if ( !*((_QWORD *)a4 + 5) )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning("CreatePrinterEntry", L"Could not allocate ShareName string.");
      v24 = 1;
    }
  }
  else
  {
    *((_QWORD *)a4 + 5) = 0;
    *((_WORD *)a4 + 24) = HashName(0);
  }
  pDatatype = a1->pDatatype;
  if ( pDatatype )
  {
    v30 = AllocSplStr(pDatatype);
    *((_QWORD *)a4 + 8) = v30;
    if ( !v30 )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning("CreatePrinterEntry", L"Could not allocate Datatype string.");
      v24 = 1;
    }
  }
  else
  {
    *((_QWORD *)a4 + 8) = 0;
  }
  if ( v24 )
    return 0;
  Priority = 1;
  if ( a1->Priority )
    Priority = a1->Priority;
  *((_DWORD *)a4 + 28) = Priority;
  v32 = *((_QWORD *)a4 + 11);
  if ( !v32 || (v33 = (*(_BYTE *)(v32 + 200) & 2) == 0, v34 = 1, v33) )
    v34 = 0;
  v35 = ValidatePrinterAttributes(a1->Attributes, *((_DWORD *)a4 + 38), 0, 0, 0, v34);
  _INIPRINTER::SetAttributes(a4, v35);
  *((_DWORD *)a4 + 30) = GMT2AdjustedGMTIfDST(a1->StartTime);
  *((_DWORD *)a4 + 31) = GMT2AdjustedGMTIfDST(a1->UntilTime);
  if ( a2 )
    *((_QWORD *)a4 + 9) = AllocSplStr(a1->pParameters);
  *((_QWORD *)a4 + 16) = AllocSplStr(a1->pSepFile);
  *((_QWORD *)a4 + 10) = AllocSplStr(a1->pComment);
  *((_QWORD *)a4 + 18) = AllocSplStr(a1->pLocation);
  pDevMode = a1->pDevMode;
  if ( pDevMode )
  {
    v37 = pDevMode->dmSize + (unsigned int)pDevMode->dmDriverExtra;
    *((_DWORD *)a4 + 24) = v37;
    v38 = (void *)DllAllocSplMem(v37);
    *((_QWORD *)a4 + 13) = v38;
    if ( v38 )
    {
      memcpy_0(v38, a1->pDevMode, *((unsigned int *)a4 + 24));
      FixDevModeDeviceName(*((_QWORD *)a4 + 3), *((_QWORD *)a4 + 13), *((unsigned int *)a4 + 24));
    }
  }
  else
  {
    *((_DWORD *)a4 + 24) = 0;
    *((_QWORD *)a4 + 13) = 0;
  }
  *((_DWORD *)a4 + 29) = a1->DefaultPriority;
  *((_QWORD *)a4 + 23) = 0;
  *((_QWORD *)a4 + 22) = 0;
  *(_QWORD *)((char *)a4 + 156) = 0;
  *((_DWORD *)a4 + 41) = 0;
  *((_QWORD *)a4 + 26) = 0;
  *((_DWORD *)a4 + 54) = 0;
  *((_DWORD *)a4 + 69) = 0;
  *((_QWORD *)a4 + 28) = 0;
  GetSystemTime((LPSYSTEMTIME)((char *)a4 + 232));
  *((_QWORD *)a4 + 31) = 0;
  *((_QWORD *)a4 + 32) = 0;
  *((_QWORD *)a4 + 33) = 0;
  *((_DWORD *)a4 + 68) = 0;
  *((_DWORD *)a4 + 86) = 0;
  *((_DWORD *)a4 + 97) = 0;
  *((_QWORD *)a4 + 42) = 0;
  *((_QWORD *)a4 + 45) = 0;
  *((_QWORD *)a4 + 44) = 0;
  *((_QWORD *)a4 + 49) = 0;
  TickCount = GetTickCount();
  *((_DWORD *)a4 + 76) = TickCount;
  if ( !TickCount )
    *((_DWORD *)a4 + 76) = 1;
  v40 = *((_DWORD *)a4 + 34);
  *((_QWORD *)a4 + 51) = 0;
  *((_DWORD *)a4 + 101) = 0;
  *((_DWORD *)a4 + 104) = 0;
  _INIPRINTER::LogPrinterStatusChange(a4, 0, v40);
  return 1;
}

```

## disassembly

```asm
0x1800522f8  mov     [rsp-38h+arg_8], rbx
0x1800522fd  push    rbp
0x1800522fe  push    rsi
0x1800522ff  push    rdi
0x180052300  push    r12
0x180052302  push    r13
0x180052304  push    r14
0x180052306  push    r15
0x180052308  mov     rbp, rsp
0x18005230b  sub     rsp, 60h
0x18005230f  mov     rax, cs:__security_cookie
0x180052316  xor     rax, rsp
0x180052319  mov     [rbp+var_8], rax
0x18005231d  mov     r12, [rbp+arg_20]
0x180052321  xor     r14d, r14d
0x180052324  mov     [rbp+Sid1], r14
0x180052328  mov     rbx, r9
0x18005232b  mov     r15, r8
0x18005232e  mov     r13d, edx
0x180052331  mov     rdi, rcx
0x180052334  test    r8, r8
0x180052337  jz      short loc_180052389
0x180052339  lea     rdx, [rbp+Sid1]; void **
0x18005233d  mov     rcx, r8; unsigned __int16 *
0x180052340  call    ?GetUserSidFromSidString@@YAJPEBGPEAPEAX@Z; GetUserSidFromSidString(ushort const *,void * *)
0x180052345  test    eax, eax
0x180052347  jns     loc_1800523E6
0x18005234d  lea     rdx, aGetusersidfrom_0; "GetUserSidFromSidString failed with hr:"...
0x180052354  mov     r8d, eax
0x180052357  lea     rcx, aCreateprintere; "CreatePrinterEntry"
0x18005235e  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180052363  xor     eax, eax
0x180052365  mov     rcx, [rbp+var_8]
0x180052369  xor     rcx, rsp; StackCookie
0x18005236c  call    __security_check_cookie
0x180052371  mov     rbx, [rsp+60h+arg_8]
0x180052379  add     rsp, 60h
0x18005237d  pop     r15
0x18005237f  pop     r14
0x180052381  pop     r13
0x180052383  pop     r12
0x180052385  pop     rdi
0x180052386  pop     rsi
0x180052387  pop     rbp
0x180052388  retn
0x180052389  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x180052390  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x180052395  lea     rcx, [rbp+Sid1]
0x180052399  test    al, al
0x18005239b  jz      short loc_1800523D1
0x18005239d  call    GetSplUserSid
0x1800523a2  test    eax, eax
0x1800523a4  js      short loc_1800523DA
0x1800523a6  mov     rsi, [rbp+Sid1]
0x1800523aa  mov     rdx, cs:?gRestrictedSpoolerServiceSid@@3PEAXEA; Sid2
0x1800523b1  mov     rcx, rsi; Sid1
0x1800523b4  call    cs:__imp_RtlEqualSid
0x1800523ba  test    al, al
0x1800523bc  jz      short loc_1800523EA
0x1800523be  mov     rcx, rsi
0x1800523c1  call    cs:__imp_DllFreeSplMem
0x1800523c7  call    ?CopySid@@YAPEAXPEAX@Z; CopySid(void *)
0x1800523cc  mov     rsi, rax
0x1800523cf  jmp     short loc_1800523EA
0x1800523d1  call    GetSplUserSid
0x1800523d6  test    eax, eax
0x1800523d8  jns     short loc_1800523E6
0x1800523da  lea     rdx, aGetsplusersidF; "GetSplUserSid failed with hr: 0x%x"
0x1800523e1  jmp     loc_180052354
0x1800523e6  mov     rsi, [rbp+Sid1]
0x1800523ea  mov     [rbx+1D8h], rsi
0x1800523f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x1800523f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x1800523fd  mov     ecx, [rdi+68h]
0x180052400  and     ecx, 400000h
0x180052406  test    al, al
0x180052408  jz      short loc_180052475
0x18005240a  test    ecx, ecx
0x18005240c  jz      short loc_180052422
0x18005240e  cmp     [rdi+60h], r14
0x180052412  jnz     loc_180052363
0x180052418  mov     rcx, r15; unsigned __int16 *
0x18005241b  call    ?CreatePerUserSecurityDescriptor@@YAPEAXPEBG@Z; CreatePerUserSecurityDescriptor(ushort const *)
0x180052420  jmp     short loc_180052461
0x180052422  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x180052427  test    eax, eax
0x180052429  jz      short loc_180052455
0x18005242b  xorps   xmm0, xmm0
0x18005242e  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180052432  cmp     [rdi+60h], r14
0x180052436  jz      short loc_180052455
0x180052438  mov     rcx, [rdi+8]; lpsz
0x18005243c  lea     rdx, [rbp+pclsid]; pclsid
0x180052440  call    cs:__imp_CLSIDFromString
0x180052446  test    eax, eax
0x180052448  js      short loc_180052455
0x18005244a  mov     rcx, [rdi+60h]; pAbsoluteSecurityDescriptor
0x18005244e  call    ?DuplicateSecurityDescriptor@@YAPEAXPEAX@Z; DuplicateSecurityDescriptor(void *)
0x180052453  jmp     short loc_180052461
0x180052455  mov     rcx, [rdi+60h]; pSecurityDescriptor
0x180052459  mov     rdx, rbx; struct _INIPRINTER *
0x18005245c  call    ?CreatePrinterSecurityDescriptorAsSelf@@YAPEAXPEAXPEAU_INIPRINTER@@@Z; CreatePrinterSecurityDescriptorAsSelf(void *,_INIPRINTER *)
0x180052461  mov     rcx, rax
0x180052464  mov     rdx, rbx
0x180052467  mov     eax, 0C0h
0x18005246c  lea     rsi, [rax+rbx]
0x180052470  mov     rax, rcx
0x180052473  jmp     short loc_1800524A3
0x180052475  test    ecx, ecx
0x180052477  jz      short loc_18005248D
0x180052479  cmp     [rdi+60h], r14
0x18005247d  jnz     loc_180052363
0x180052483  mov     rcx, r15; unsigned __int16 *
0x180052486  call    ?CreatePerUserSecurityDescriptor@@YAPEAXPEBG@Z; CreatePerUserSecurityDescriptor(ushort const *)
0x18005248b  jmp     short loc_180052499
0x18005248d  mov     rcx, [rdi+60h]; pSecurityDescriptor
0x180052491  mov     rdx, rbx; struct _INIPRINTER *
0x180052494  call    ?CreatePrinterSecurityDescriptorAsSelf@@YAPEAXPEAXPEAU_INIPRINTER@@@Z; CreatePrinterSecurityDescriptorAsSelf(void *,_INIPRINTER *)
0x180052499  lea     rsi, [rbx+0C0h]
0x1800524a0  mov     rcx, rax; pSecurityDescriptor
0x1800524a3  mov     rdx, rsi
0x1800524a6  mov     [rdx], rax
0x1800524a9  test    rcx, rcx
0x1800524ac  jz      loc_180052363
0x1800524b2  lea     r8, [rbp+dwRevision]; lpdwRevision
0x1800524b6  mov     [rbp+dwRevision], r14d
0x1800524ba  lea     rdx, [rbp+pControl]; pControl
0x1800524be  mov     [rbp+pControl], r14w
0x1800524c3  call    cs:__imp_GetSecurityDescriptorControl
0x1800524c9  test    eax, eax
0x1800524cb  jz      short loc_1800524D8
0x1800524cd  movzx   r14d, [rbp+pControl]
0x1800524d2  and     r14d, 8
0x1800524d6  jmp     short loc_1800524DE
0x1800524d8  mov     r14d, 1
0x1800524de  xor     eax, eax
0x1800524e0  mov     [rbp+var_24], eax
0x1800524e3  mov     dword ptr [rbp+Sid1], eax
0x1800524e6  cmp     [rdi+60h], rax
0x1800524ea  jz      loc_180052573
0x1800524f0  mov     rcx, [rsi]; void *
0x1800524f3  lea     r8, [rbp+Sid1]; int *
0x1800524f7  lea     rdx, [rbp+var_24]; int *
0x1800524fb  call    ?ContainsAccessEntriesForAppContainer@@YA_NPEAXPEAH1@Z; ContainsAccessEntriesForAppContainer(void *,int *,int *)
0x180052500  test    al, al
0x180052502  jnz     short loc_180052573
0x180052504  xor     r8d, r8d
0x180052507  xorps   xmm0, xmm0
0x18005250a  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x18005250e  cmp     [rbp+var_24], r8d
0x180052512  jnz     short loc_180052525
0x180052514  mov     rax, cs:?gAppContainerAllAppsSid@@3PEAXEA; void * gAppContainerAllAppsSid
0x18005251b  mov     r8d, 1
0x180052521  mov     qword ptr [rbp+pclsid.Data1], rax
0x180052525  cmp     dword ptr [rbp+Sid1], 0
0x180052529  jnz     short loc_18005253D
0x18005252b  mov     rax, cs:?gLPACCapabilitySid@@3PEAXEA; void * gLPACCapabilitySid
0x180052532  mov     ecx, r8d
0x180052535  inc     r8d; unsigned int
0x180052538  mov     qword ptr [rbp+rcx*8+pclsid.Data1], rax
0x18005253d  mov     r9d, 20008h; unsigned int
0x180052543  mov     [rsp+60h+var_40], r14d; int
0x180052548  lea     rdx, [rbp+pclsid]; void **
0x18005254c  mov     rcx, rsi; void **
0x18005254f  call    ?FixPrinterSecurityDescriptor@@YAKPEAPEAX0KKH@Z; FixPrinterSecurityDescriptor(void * *,void * *,ulong,ulong,int)
0x180052554  test    eax, eax
0x180052556  jz      short loc_180052573
0x180052558  lea     rdx, aFixprintersecu; "FixPrinterSecurityDescriptor (AC and LP"...
0x18005255f  mov     r8d, eax
0x180052562  lea     rcx, aCreateprintere; "CreatePrinterEntry"
0x180052569  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18005256e  jmp     loc_180052363
0x180052573  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker> `wil::Feature<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetImpl(void)'::`2'::impl
0x18005257a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::__private_IsEnabled(void)
0x18005257f  test    al, al
0x180052581  jz      short loc_1800525C6
0x180052583  cmp     qword ptr [rdi+60h], 0
0x180052588  jz      short loc_1800525C6
0x18005258a  mov     rcx, [rsi]; void *
0x18005258d  call    ?ContainsAccessEntriesForRestrictedSpoolerWorker@@YA_NPEAX@Z; ContainsAccessEntriesForRestrictedSpoolerWorker(void *)
0x180052592  test    al, al
0x180052594  jnz     short loc_1800525C6
0x180052596  mov     r9d, 0F000Ch; unsigned int
0x18005259c  mov     [rsp+60h+var_40], r14d; int
0x1800525a1  mov     r8d, 1; unsigned int
0x1800525a7  lea     rdx, ?gRestrictedSpoolerServiceSid@@3PEAXEA; void **
0x1800525ae  mov     rcx, rsi; void **
0x1800525b1  call    ?FixPrinterSecurityDescriptor@@YAKPEAPEAX0KKH@Z; FixPrinterSecurityDescriptor(void * *,void * *,ulong,ulong,int)
0x1800525b6  xor     r14d, r14d
0x1800525b9  test    eax, eax
0x1800525bb  jz      short loc_1800525C9
0x1800525bd  lea     rdx, aFixprintersecu_1; "FixPrinterSecurityDescriptor (Restricte"...
0x1800525c4  jmp     short loc_18005255F
0x1800525c6  xor     r14d, r14d
0x1800525c9  mov     [r12], r14d
0x1800525cd  mov     esi, r14d
0x1800525d0  mov     dword ptr [rbx], 4951h
0x1800525d6  test    dword ptr [rdi+68h], 400000h
0x1800525dd  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800525e1  jz      short loc_18005263C
0x1800525e3  mov     [rbp+Sid1], r14
0x1800525e7  test    r15, r15
0x1800525ea  jz      short loc_1800525FA
0x1800525ec  lea     r8, [rbp+Sid1]; unsigned __int16 **
0x1800525f0  mov     rdx, r15; unsigned __int16 *
0x1800525f3  call    ?CreateAdornedPrinterName@@YAJPEBG0PEAPEAG@Z; CreateAdornedPrinterName(ushort const *,ushort const *,ushort * *)
0x1800525f8  jmp     short loc_180052603
0x1800525fa  lea     rdx, [rbp+Sid1]; unsigned __int16 **
0x1800525fe  call    ?CreateAdornedPrinterName@@YAJPEBGPEAPEAG@Z; CreateAdornedPrinterName(ushort const *,ushort * *)
0x180052603  test    eax, eax
0x180052605  js      short loc_180052622
0x180052607  mov     rax, [rbp+Sid1]
0x18005260b  mov     [rbx+18h], rax
0x18005260f  mov     rcx, [rdi+8]
0x180052613  call    cs:__imp_AllocSplStr
0x180052619  mov     [rbx+220h], rax
0x180052620  jmp     short loc_180052646
0x180052622  lea     rdx, aCouldNotAlloca_2; "Could not allocate per-user SID-adorned"...
0x180052629  lea     rcx, aCreateprintere; "CreatePrinterEntry"
0x180052630  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180052635  mov     esi, 1
0x18005263a  jmp     short loc_180052646
0x18005263c  call    cs:__imp_AllocSplStr
0x180052642  mov     [rbx+18h], rax
0x180052646  mov     rcx, [rbx+18h]
0x18005264a  call    HashName
0x18005264f  mov     [rbx+20h], ax
0x180052653  cmp     [rbx+18h], r14
0x180052657  jnz     short loc_180052677
0x180052659  lea     rdx, aCouldNotAlloca_0; "Could not allocate PrinterName string."
0x180052660  lea     rcx, aCreateprintere; "CreatePrinterEntry"
0x180052667  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18005266c  mov     r15d, 1
0x180052672  mov     esi, r15d
0x180052675  jmp     short loc_18005267D
0x180052677  mov     r15d, 1
0x18005267d  mov     rcx, [rdi+10h]
0x180052681  test    rcx, rcx
0x180052684  jz      short loc_1800526BA
0x180052686  call    cs:__imp_AllocSplStr
0x18005268c  mov     rcx, rax
0x18005268f  mov     [rbx+28h], rax
0x180052693  call    HashName
0x180052698  mov     [rbx+30h], ax
0x18005269c  cmp     [rbx+28h], r14
0x1800526a0  jnz     short loc_1800526C9
0x1800526a2  lea     rdx, aCouldNotAlloca_3; "Could not allocate ShareName string."
0x1800526a9  lea     rcx, aCreateprintere; "CreatePrinterEntry"
0x1800526b0  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800526b5  mov     esi, r15d
0x1800526b8  jmp     short loc_1800526C9
0x1800526ba  xor     ecx, ecx
0x1800526bc  mov     [rbx+28h], r14
0x1800526c0  call    HashName
0x1800526c5  mov     [rbx+30h], ax
0x1800526c9  mov     rcx, [rdi+50h]
0x1800526cd  test    rcx, rcx
0x1800526d0  jz      short loc_1800526F9
0x1800526d2  call    cs:__imp_AllocSplStr
0x1800526d8  mov     [rbx+40h], rax
0x1800526dc  test    rax, rax
0x1800526df  jnz     short loc_1800526FD
0x1800526e1  lea     rdx, aCouldNotAlloca_4; "Could not allocate Datatype string."
0x1800526e8  lea     rcx, aCreateprintere; "CreatePrinterEntry"
0x1800526ef  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800526f4  mov     esi, r15d
0x1800526f7  jmp     short loc_1800526FD
0x1800526f9  mov     [rbx+40h], r14
0x1800526fd  test    esi, esi
0x1800526ff  jnz     loc_180052363
0x180052705  cmp     [rdi+6Ch], r14d
0x180052709  mov     eax, r15d
0x18005270c  cmovnz  eax, [rdi+6Ch]
0x180052710  mov     [rbx+70h], eax
0x180052713  mov     rax, [rbx+58h]
0x180052717  test    rax, rax
0x18005271a  jz      short loc_180052728
0x18005271c  test    byte ptr [rax+0C8h], 2
0x180052723  mov     al, r15b
0x180052726  jnz     short loc_18005272B
0x180052728  mov     al, r14b
0x18005272b  mov     edx, [rbx+98h]; unsigned int
0x180052731  xor     r9d, r9d; int *
0x180052734  mov     ecx, [rdi+68h]; unsigned int
0x180052737  xor     r8d, r8d; unsigned __int16 *
0x18005273a  mov     [rsp+60h+var_38], al; bool
0x18005273e  mov     [rsp+60h+var_40], r14d; int
0x180052743  call    ?ValidatePrinterAttributes@@YAKKKPEAGPEAHH_N@Z; ValidatePrinterAttributes(ulong,ulong,ushort *,int *,int,bool)
0x180052748  mov     edx, eax; unsigned int
0x18005274a  mov     rcx, rbx; this
0x18005274d  call    ?SetAttributes@_INIPRINTER@@QEAAXK@Z; _INIPRINTER::SetAttributes(ulong)
0x180052752  mov     ecx, [rdi+74h]
0x180052755  call    GMT2AdjustedGMTIfDST
0x18005275a  mov     [rbx+78h], eax
0x18005275d  mov     ecx, [rdi+78h]
0x180052760  call    GMT2AdjustedGMTIfDST
0x180052765  mov     [rbx+7Ch], eax
0x180052768  test    r13d, r13d
0x18005276b  jz      short loc_18005277B
0x18005276d  mov     rcx, [rdi+58h]
  ... truncated ...
```
