# CipReportAndReprieveUMCIFailure

- ea: `0x1800b4f38`
- end: `0x1800b56c8`
- name: `CipReportAndReprieveUMCIFailure`
- size: `1936`
- prototype: `__int64 __fastcall(int, int, int, int, int, char, int, char, __int64, PCEVENT_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e5fd0`

## callees

- `0x1800100a4`
- `0x18002c1b0`
- `0x18005c318`
- `0x180062244`
- `0x18006d284`
- `0x18006dd5c`
- `0x180073b20`
- `0x180076370`
- `0x18007a5c4`
- `0x18007fdf4`
- `0x18008f038`
- `0x18008f2d0`
- `0x1800903d4`
- `0x180090564`
- `0x1800a4350`
- `0x1800a73a0`
- `0x1800ab748`
- `0x1800b4f38`
- `0x1800b56d0`
- `0x1800c29a8`
- `0x1800cb940`
- `0x1800d8a40`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800b52c7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800b52c7`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b510f`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b55f0`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b510f`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b55f0`
- `ntoskrnl!KdDebuggerNotPresent` at `0x1800b5514`
- `ntoskrnl!DbgPrint` at `0x1800b552c`
- `ntoskrnl!DbgPrint` at `0x1800b552c`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1800b55a6`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1800b55a6`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b513e`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b5397`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b513e`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b5397`
- `ntoskrnl!PsGetProcessSignatureLevel` at `0x1800b5589`
- `ntoskrnl!PsGetProcessSignatureLevel` at `0x1800b5589`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b523e`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b525d`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b5430`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b523e`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b525d`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b5430`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800b4ffc`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800b4ffc`
- `ntoskrnl!DbgPrintEx` at `0x1800b545a`
- `ntoskrnl!DbgPrintEx` at `0x1800b5476`
- `ntoskrnl!DbgPrintEx` at `0x1800b548e`
- `ntoskrnl!DbgPrintEx` at `0x1800b54aa`
- `ntoskrnl!DbgPrintEx` at `0x1800b54c2`
- `ntoskrnl!DbgPrintEx` at `0x1800b54da`
- `ntoskrnl!DbgPrintEx` at `0x1800b54f2`
- `ntoskrnl!DbgPrintEx` at `0x1800b545a`
- `ntoskrnl!DbgPrintEx` at `0x1800b5476`
- `ntoskrnl!DbgPrintEx` at `0x1800b548e`
- `ntoskrnl!DbgPrintEx` at `0x1800b54aa`
- `ntoskrnl!DbgPrintEx` at `0x1800b54c2`
- `ntoskrnl!DbgPrintEx` at `0x1800b54da`
- `ntoskrnl!DbgPrintEx` at `0x1800b54f2`
- `ntoskrnl!KdDebuggerEnabled` at `0x1800b5509`

## string_xrefs

- `0x1800b54a0`: `* The binary was attempted to be loaded in the process: %wZ\n`

## pseudocode

```c
__int64 __fastcall CipReportAndReprieveUMCIFailure(
        __int64 a1,
        struct _KPROCESS *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        char a6,
        char a7,
        unsigned int a8,
        char *a9,
        EVENT_DESCRIPTOR *a10)
{
  unsigned int v10; // edi
  char *v11; // r13
  EVENT_DESCRIPTOR *v13; // r14
  unsigned int v15; // r15d
  __int64 v16; // r10
  UNICODE_STRING v18; // xmm0
  int v19; // esi
  int IsEnabledDeviceUsageNoInline; // eax
  int v21; // r8d
  int v22; // r9d
  char v23; // r12
  int v24; // r9d
  __int64 v25; // r14
  int v26; // edx
  BOOLEAN IsCurrentThreadPrefetching; // al
  __int64 v28; // rdx
  __int64 v29; // r14
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // r8
  unsigned __int64 v33; // rax
  __int64 v34; // rcx
  __int64 v35; // r8
  struct _UNICODE_STRING *p_UnicodeString; // rdx
  unsigned int v37; // r8d
  int v38; // r8d
  int v39; // r9d
  const EVENT_DESCRIPTOR *EventDescriptor; // rax
  __int64 v41; // r8
  unsigned int i; // r14d
  __int64 v43; // r13
  struct _KPROCESS *v44; // rsi
  char v45; // [rsp+48h] [rbp-51h] BYREF
  char v46[3]; // [rsp+49h] [rbp-50h] BYREF
  __int64 v47; // [rsp+4Ch] [rbp-4Dh] BYREF
  int v48; // [rsp+54h] [rbp-45h] BYREF
  UNICODE_STRING StringIn; // [rsp+58h] [rbp-41h] BYREF
  UNICODE_STRING v50; // [rsp+68h] [rbp-31h] BYREF
  __int64 v51; // [rsp+78h] [rbp-21h] BYREF
  __int64 v52; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp-11h] BYREF
  char v54; // [rsp+E8h] [rbp+4Fh] BYREF
  PRKPROCESS PROCESS; // [rsp+F0h] [rbp+57h]
  __int64 v56; // [rsp+F8h] [rbp+5Fh]
  __int64 v57; // [rsp+100h] [rbp+67h]

  v57 = a4;
  v56 = a3;
  PROCESS = a2;
  v10 = a8;
  v11 = a9;
  v13 = a10;
  v45 = 0;
  v46[0] = 0;
  *a9 = 0;
  LOBYTE(v13->Id) = 1;
  v50 = 0;
  v51 = 0;
  v15 = v10;
  v54 = 0;
  StringIn = 0;
  v52 = 0;
  UnicodeString = 0;
  v48 = 0;
  v47 = v10;
  if ( (unsigned __int8)CipIsAcPolicyViolation(a1 + 24) )
    return v10;
  a10 = 0;
  LOBYTE(a8) = 0;
  CipQueryProcessName(v16, &StringIn, &v52);
  if ( (int)FsRtlGetFileNameInformation(a4, 1024, &v50, &v51) < 0 )
  {
    v18 = *(UNICODE_STRING *)(a4 + 88);
    v51 = 0;
    v50 = v18;
  }
  v19 = a5 & 0x20000000;
  IsEnabledDeviceUsageNoInline = Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline();
  v23 = a6;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( v19 || *(_QWORD *)(a1 + 3616) )
    {
      LODWORD(a9) = v19;
LABEL_21:
      v25 = v57;
      goto LABEL_22;
    }
    LODWORD(a9) = 0;
  }
  else
  {
    LODWORD(a9) = v19;
    if ( v19 )
      goto LABEL_21;
  }
  *(_DWORD *)(a1 + 2368) ^= ((unsigned __int16)*(_DWORD *)(a1 + 2368)
                           ^ (unsigned __int16)((unsigned __int8)CipIsDotNetNativeImage(v57, 0) << 8))
                          & 0x100;
  LOBYTE(a8) = CipIsFileInUMCIExclusionPaths(v57);
  if ( (_BYTE)a8 )
  {
    LOBYTE(v13->Id) = a6;
    *v11 = 1;
LABEL_99:
    CiAudit(&v50, 5038);
    goto LABEL_100;
  }
  if ( (unsigned __int8)v23 <= 1u && v10 == -1073740760 )
  {
    *v11 = 1;
    LOBYTE(v13->Id) = 1;
    goto LABEL_100;
  }
  if ( (g_CiDeveloperMode & 1) == 0 )
  {
    if ( (unsigned __int8)PsGetProcessProtection(PROCESS) == 65 && (a5 & 0x10) == 0 )
      CipLsaPplPublishDllLoadFailureWnf(&v50);
    goto LABEL_21;
  }
  v24 = a5;
  LOBYTE(v13->Id) = v23;
  v25 = v57;
  v26 = v57;
  *v11 = 1;
  a10 = (EVENT_DESCRIPTOR *)CiPolicyFailureIgnored;
  CiInstrumentSignatureFailuresOnCleanStack(a1, v26, (unsigned int)&StringIn, v24, v23, v10, 1);
LABEL_22:
  if ( *v11 )
    goto LABEL_96;
  IsCurrentThreadPrefetching = PsIsCurrentThreadPrefetching();
  v28 = 0;
  if ( !IsCurrentThreadPrefetching && (v23 != 7 || (a5 & 0x10) != 0) && (*(_DWORD *)(a1 + 2368) & 0x100) == 0 )
  {
    v29 = 0;
    if ( !*(_DWORD *)(a1 + 1532) )
      CiCheckSmartScreenClaim(a1, 0);
    v30 = *(_QWORD *)(a1 + 2360);
    if ( v30 )
      v29 = *(_QWORD *)(v30 + 8LL * *(unsigned int *)(a1 + 968));
    if ( (a5 & 0xE41FFF87) == 0 )
    {
      v31 = *((unsigned int *)g_CipWhichLevelComparisons + (v23 & 0xF));
      if ( (v31 & 4) != 0
        && (g_CiPolicyState & 0x4000) != 0
        && (unsigned __int8)SIPolicyVerifiedAndReputableUI(v31, v28)
        && v29 )
      {
        v33 = -(__int64)(*(_DWORD *)(v29 + 40) < 6u) & 0xFFFFFFFFFFFFFD50uLL;
        v34 = *(_QWORD *)(v33 + v29 + 704) - SiPolicyIDNightsWatchDesktop;
        if ( !v34 )
          v34 = *(_QWORD *)(v33 + v29 + 712) - *((_QWORD *)&SiPolicyIDNightsWatchDesktop + 1);
        if ( !v34 )
        {
          if ( *(_DWORD *)(a1 + 1528) )
          {
            *(_DWORD *)(a1 + 2104) = 1;
          }
          else
          {
            LOBYTE(v32) = 1;
            if ( RtlFindUnicodeSubstring(&v50, L"24", v32)
              && (LOBYTE(v35) = 1, RtlFindUnicodeSubstring(&StringIn, &qword_180030600, v35)) )
            {
              HIDWORD(v47) = 1;
            }
            else
            {
              if ( (int)CipTryGetProcessAppID(PROCESS, 0) >= 0 && UnicodeString.Length )
                p_UnicodeString = &UnicodeString;
              else
                p_UnicodeString = 0;
              CiCatDbSendSmartAppControlBlockToast2(&StringIn, p_UnicodeString, &v50, v10, (__int64)&v47 + 4);
            }
            if ( UnicodeString.Buffer )
              RtlFreeUnicodeString(&UnicodeString);
            *(_DWORD *)(a1 + 2104) = (HIDWORD(v47) != 0) + 2;
            v15 = v47;
          }
        }
      }
    }
    v25 = v57;
    CiInstrumentSignatureFailuresOnCleanStack(a1, v57, (unsigned int)&StringIn, a5, v23, v10, *v11);
  }
  if ( *v11 )
  {
LABEL_96:
    if ( a10 )
    {
      if ( !(_BYTE)a8 )
      {
        LOBYTE(v22) = a7;
        LOBYTE(v21) = v23;
        CiLogPolicyEvent((int)&v50, (int)&StringIn, v21, v22, v10, a10);
        CiLogSignatureInformation(a1);
      }
      goto LABEL_99;
    }
LABEL_100:
    v15 = 0;
    goto LABEL_101;
  }
  if ( (a5 & 0xE41FFF87) == 0
    && (*((_DWORD *)g_CipWhichLevelComparisons + (v23 & 0xF)) & 4) != 0
    && (g_CiPolicyState & 0x4000) != 0
    && *(_DWORD *)(a1 + 2116) == -1 )
  {
    if ( (unsigned __int8)CiDefenderOffline(a1, 0, 3236495362LL) )
    {
      v10 = v37 + 8;
      v15 = v37 + 8;
      LODWORD(v47) = v37 + 8;
    }
    else if ( v10 != -1058471927 && v10 + 1058471925 > 2 )
    {
      v15 = v37;
      LODWORD(v47) = v37;
      v10 = v37;
    }
  }
  if ( !PsIsCurrentThreadPrefetching() && (*(_DWORD *)(a1 + 2368) & 0x100) == 0 )
  {
    LOBYTE(v39) = a7;
    EventDescriptor = (const EVENT_DESCRIPTOR *)CiIumPolicyFailure;
    if ( !(_DWORD)a9 )
      EventDescriptor = &CiPolicyFailure;
    LOBYTE(v38) = v23;
    CiLogPolicyEvent((int)&v50, (int)&StringIn, v38, v39, v10, EventDescriptor);
    CiLogSignatureInformation(a1);
    if ( v23 != 7 || (g_CiOptions & 0x400) != 0 )
    {
      for ( i = 0; i < 4; ++i )
      {
        LOBYTE(v41) = 1;
        if ( RtlFindUnicodeSubstring(&StringIn, &asc_1800305C0[8 * i], v41) )
          goto LABEL_78;
      }
      DbgPrintEx(0x65u, 0, "******************************************************************\n");
      DbgPrintEx(0x65u, 0, "* This break indicates this binary is not signed correctly: %wZ\n", &v50);
      DbgPrintEx(0x65u, 0, "* and does not meet the system policy.\n");
      DbgPrintEx(0x65u, 0, "* The binary was attempted to be loaded in the process: %wZ\n", &StringIn);
      DbgPrintEx(0x65u, 0, "* This is not a failure in CI, but a problem with the failing binary.\n");
      DbgPrintEx(0x65u, 0, "* Please contact the binary owner for getting the binary correctly signed.\n");
      DbgPrintEx(0x65u, 0, "******************************************************************\n");
      if ( (unsigned __int8)CiIsUmciDebugBreakEnabled() && (_BYTE)KdDebuggerEnabled && (_BYTE)KdDebuggerNotPresent != 1 )
      {
        DbgPrint("Code Integrity violation:  %d\n", 9314);
        __debugbreak();
      }
LABEL_78:
      v25 = v57;
    }
  }
  if ( *v11 )
    goto LABEL_101;
  if ( v19 )
    goto LABEL_101;
  if ( !*(_DWORD *)(a1 + 3020) )
    goto LABEL_101;
  v43 = v56;
  if ( !v56 )
    goto LABEL_101;
  if ( (a5 & 0x10) != 0 )
  {
    if ( v23 != 11 )
    {
      v44 = PROCESS;
      goto LABEL_87;
    }
  }
  else
  {
    v44 = PROCESS;
    if ( (unsigned __int8)PsGetProcessSignatureLevel(PROCESS, 0) != 11 )
    {
LABEL_87:
      PsQueryProcessAttributesByToken(v43, 0, &v54);
      if ( v54 && v10 != -1058471934 && v10 + 1058471929 > 6 )
      {
        if ( (((void (__fastcall *)(struct _KPROCESS *, int *))g_CiPrivateNtosApis)(v44, &v48),
              (unsigned __int8)PsGetProcessProtection(v44) != 0x81)
          && (v48 & 4) == 0
          || (int)KappxIsPackageFile(v25, &v45, v46) >= 0 && (v45 || v46[0]) )
        {
          KappxNotifyIntegrityFailureInPackagedProcess(
            v25,
            *(_QWORD *)(a1 + 3024),
            *(_DWORD *)(a1 + 3020),
            v44,
            (__int64)&v47);
          v15 = v47;
        }
      }
    }
  }
LABEL_101:
  CipReleaseFileName(v51);
  CipReleaseProcessName(v52);
  return v15;
}

```

## disassembly

```asm
0x1800b4f38  mov     rax, rsp
0x1800b4f3b  mov     [rax+20h], r9
0x1800b4f3f  mov     [rax+18h], r8
0x1800b4f43  mov     [rax+10h], rdx
0x1800b4f47  push    rbp
0x1800b4f48  push    rbx
0x1800b4f49  push    rsi
0x1800b4f4a  push    rdi
0x1800b4f4b  push    r12
0x1800b4f4d  push    r13
0x1800b4f4f  push    r14
0x1800b4f51  push    r15
0x1800b4f53  lea     rbp, [rax-47h]
0x1800b4f57  sub     rsp, 98h
0x1800b4f5e  mov     edi, [rbp+3Fh+arg_38]
0x1800b4f64  xor     r12d, r12d
0x1800b4f67  mov     r13, [rbp+3Fh+arg_40]
0x1800b4f6e  mov     rbx, rcx
0x1800b4f71  mov     r14, [rbp+3Fh+arg_48]
0x1800b4f78  xorps   xmm0, xmm0
0x1800b4f7b  xorps   xmm1, xmm1
0x1800b4f7e  mov     [rbp+3Fh+var_90], r12b
0x1800b4f82  add     rcx, 18h
0x1800b4f86  mov     [rbp+3Fh+var_8F], r12b
0x1800b4f8a  mov     [r13+0], r12b
0x1800b4f8e  mov     rsi, r9
0x1800b4f91  mov     byte ptr [r14], 1
0x1800b4f95  mov     r10, rdx
0x1800b4f98  movups  xmmword ptr [rbp+3Fh+var_70.Length], xmm0
0x1800b4f9c  mov     [rbp+3Fh+var_60], r12
0x1800b4fa0  mov     r15d, edi
0x1800b4fa3  mov     [rbp+3Fh+arg_0], r12b
0x1800b4fa7  movups  xmmword ptr [rbp+3Fh+StringIn.Length], xmm0
0x1800b4fab  mov     [rbp+3Fh+var_58], r12
0x1800b4faf  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm1
0x1800b4fb3  mov     [rbp+3Fh+var_84], r12d
0x1800b4fb7  mov     dword ptr [rbp+3Fh+var_8C], edi
0x1800b4fba  mov     dword ptr [rbp+3Fh+var_8C+4], r12d
0x1800b4fbe  call    CipIsAcPolicyViolation
0x1800b4fc3  test    al, al
0x1800b4fc5  jz      short loc_1800B4FCE
0x1800b4fc7  mov     eax, edi
0x1800b4fc9  jmp     loc_1800B56B3
0x1800b4fce  lea     r8, [rbp+3Fh+var_58]
0x1800b4fd2  mov     [rbp+3Fh+arg_48], r12
0x1800b4fd9  lea     rdx, [rbp+3Fh+StringIn]
0x1800b4fdd  mov     byte ptr [rbp+3Fh+arg_38], r12b
0x1800b4fe4  mov     rcx, r10
0x1800b4fe7  call    CipQueryProcessName
0x1800b4fec  lea     r9, [rbp+3Fh+var_60]
0x1800b4ff0  mov     edx, 400h
0x1800b4ff5  lea     r8, [rbp+3Fh+var_70]
0x1800b4ff9  mov     rcx, rsi
0x1800b4ffc  call    cs:__imp_FsRtlGetFileNameInformation
0x1800b5003  nop     dword ptr [rax+rax+00h]
0x1800b5008  test    eax, eax
0x1800b500a  jns     short loc_1800B5019
0x1800b500c  movups  xmm0, xmmword ptr [rsi+58h]
0x1800b5010  mov     [rbp+3Fh+var_60], r12
0x1800b5014  movdqu  xmmword ptr [rbp+3Fh+var_70.Length], xmm0
0x1800b5019  mov     esi, [rbp+3Fh+arg_20]
0x1800b501c  and     esi, 20000000h
0x1800b5022  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800b5027  movzx   r12d, [rbp+3Fh+arg_28]
0x1800b502c  xor     edx, edx
0x1800b502e  test    eax, eax
0x1800b5030  jnz     short loc_1800B5041
0x1800b5032  mov     dword ptr [rbp+3Fh+arg_40], esi
0x1800b5038  test    esi, esi
0x1800b503a  jz      short loc_1800B505C
0x1800b503c  jmp     loc_1800B5130
0x1800b5041  test    esi, esi
0x1800b5043  jnz     loc_1800B5277
0x1800b5049  cmp     [rbx+0E20h], rdx
0x1800b5050  jnz     loc_1800B5277
0x1800b5056  mov     dword ptr [rbp+3Fh+arg_40], esi
0x1800b505c  mov     rcx, [rbp+3Fh+arg_18]
0x1800b5060  call    CipIsDotNetNativeImage
0x1800b5065  movzx   ecx, al
0x1800b5068  mov     eax, [rbx+940h]
0x1800b506e  shl     ecx, 8
0x1800b5071  xor     ecx, eax
0x1800b5073  and     ecx, 100h
0x1800b5079  xor     ecx, eax
0x1800b507b  mov     [rbx+940h], ecx
0x1800b5081  mov     rcx, [rbp+3Fh+arg_18]
0x1800b5085  call    CipIsFileInUMCIExclusionPaths
0x1800b508a  xor     edx, edx
0x1800b508c  mov     byte ptr [rbp+3Fh+arg_38], al
0x1800b5092  test    al, al
0x1800b5094  jz      short loc_1800B50A6
0x1800b5096  mov     al, [rbp+3Fh+arg_28]
0x1800b5099  mov     [r14], al
0x1800b509c  mov     byte ptr [r13+0], 1
0x1800b50a1  jmp     loc_1800B568B
0x1800b50a6  cmp     r12b, 1
0x1800b50aa  ja      short loc_1800B50C2
0x1800b50ac  cmp     edi, 0C0000428h
0x1800b50b2  jnz     short loc_1800B50C2
0x1800b50b4  mov     byte ptr [r13+0], 1
0x1800b50b9  mov     byte ptr [r14], 1
0x1800b50bd  jmp     loc_1800B569B
0x1800b50c2  mov     eax, cs:g_CiDeveloperMode
0x1800b50c8  test    al, 1
0x1800b50ca  jz      short loc_1800B510B
0x1800b50cc  mov     r9d, [rbp+3Fh+arg_20]
0x1800b50d0  lea     rax, CiPolicyFailureIgnored
0x1800b50d7  mov     [r14], r12b
0x1800b50da  lea     r8, [rbp+3Fh+StringIn]
0x1800b50de  mov     r14, [rbp+3Fh+arg_18]
0x1800b50e2  mov     rcx, rbx
0x1800b50e5  mov     byte ptr [rsp+30h], 1
0x1800b50ea  mov     rdx, r14
0x1800b50ed  mov     dword ptr [rsp+0D0h+EventDescriptor], edi
0x1800b50f1  mov     byte ptr [r13+0], 1
0x1800b50f6  mov     [rbp+3Fh+arg_48], rax
0x1800b50fd  mov     [rsp+0D0h+var_B0], r12b
0x1800b5102  call    CiInstrumentSignatureFailuresOnCleanStack
0x1800b5107  xor     edx, edx
0x1800b5109  jmp     short loc_1800B5134
0x1800b510b  mov     rcx, [rbp+3Fh+PROCESS]
0x1800b510f  call    cs:__imp_PsGetProcessProtection
0x1800b5116  nop     dword ptr [rax+rax+00h]
0x1800b511b  cmp     al, 41h ; 'A'
0x1800b511d  jnz     short loc_1800B512E
0x1800b511f  test    byte ptr [rbp+3Fh+arg_20], 10h
0x1800b5123  jnz     short loc_1800B512E
0x1800b5125  lea     rcx, [rbp+3Fh+var_70]
0x1800b5129  call    CipLsaPplPublishDllLoadFailureWnf
0x1800b512e  xor     edx, edx
0x1800b5130  mov     r14, [rbp+3Fh+arg_18]
0x1800b5134  cmp     [r13+0], dl
0x1800b5138  jnz     loc_1800B5652
0x1800b513e  call    cs:__imp_PsIsCurrentThreadPrefetching
0x1800b5145  nop     dword ptr [rax+rax+00h]
0x1800b514a  xor     edx, edx
0x1800b514c  test    al, al
0x1800b514e  jnz     loc_1800B531F
0x1800b5154  cmp     r12b, 7
0x1800b5158  jnz     short loc_1800B5164
0x1800b515a  test    byte ptr [rbp+3Fh+arg_20], 10h
0x1800b515e  jz      loc_1800B531F
0x1800b5164  test    dword ptr [rbx+940h], 100h
0x1800b516e  jnz     loc_1800B531F
0x1800b5174  mov     r14, rdx
0x1800b5177  cmp     [rbx+5FCh], edx
0x1800b517d  jnz     short loc_1800B5187
0x1800b517f  mov     rcx, rbx
0x1800b5182  call    CiCheckSmartScreenClaim
0x1800b5187  mov     rcx, [rbx+938h]
0x1800b518e  test    rcx, rcx
0x1800b5191  jz      short loc_1800B519D
0x1800b5193  mov     eax, [rbx+3C8h]
0x1800b5199  mov     r14, [rcx+rax*8]
0x1800b519d  test    [rbp+3Fh+arg_20], 0E41FFF87h
0x1800b51a4  jnz     loc_1800B52F5
0x1800b51aa  mov     rax, cs:g_CipWhichLevelComparisons
0x1800b51b1  mov     rcx, r12
0x1800b51b4  and     ecx, 0Fh
0x1800b51b7  mov     ecx, [rax+rcx*4]
0x1800b51ba  test    cl, 4
0x1800b51bd  jz      loc_1800B52F5
0x1800b51c3  test    cs:g_CiPolicyState, 4000h
0x1800b51cd  jz      loc_1800B52F5
0x1800b51d3  call    SIPolicyVerifiedAndReputableUI
0x1800b51d8  test    al, al
0x1800b51da  jz      loc_1800B52F5
0x1800b51e0  test    r14, r14
0x1800b51e3  jz      loc_1800B52F5
0x1800b51e9  cmp     dword ptr [r14+28h], 6
0x1800b51ee  sbb     rax, rax
0x1800b51f1  and     rax, 0FFFFFFFFFFFFFD50h
0x1800b51f7  mov     rcx, [rax+r14+2C0h]
0x1800b51ff  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop
0x1800b5206  jnz     short loc_1800B5217
0x1800b5208  mov     rcx, [rax+r14+2C8h]
0x1800b5210  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop+8
0x1800b5217  xor     r14d, r14d
0x1800b521a  test    rcx, rcx
0x1800b521d  jnz     loc_1800B52F5
0x1800b5223  cmp     [rbx+5F8h], r14d
0x1800b522a  jnz     loc_1800B52EB
0x1800b5230  mov     r8b, 1
0x1800b5233  lea     rdx, a24; "24"
0x1800b523a  lea     rcx, [rbp+3Fh+var_70]
0x1800b523e  call    cs:__imp_RtlFindUnicodeSubstring
0x1800b5245  nop     dword ptr [rax+rax+00h]
0x1800b524a  test    rax, rax
0x1800b524d  jz      short loc_1800B5282
0x1800b524f  mov     r8b, 1
0x1800b5252  lea     rdx, qword_180030600
0x1800b5259  lea     rcx, [rbp+3Fh+StringIn]
0x1800b525d  call    cs:__imp_RtlFindUnicodeSubstring
0x1800b5264  nop     dword ptr [rax+rax+00h]
0x1800b5269  test    rax, rax
0x1800b526c  jz      short loc_1800B5282
0x1800b526e  mov     dword ptr [rbp+3Fh+var_8C+4], 1
0x1800b5275  jmp     short loc_1800B52BD
0x1800b5277  mov     dword ptr [rbp+3Fh+arg_40], esi
0x1800b527d  jmp     loc_1800B5130
0x1800b5282  mov     rcx, [rbp+3Fh+PROCESS]; PROCESS
0x1800b5286  lea     r9, [rbp+3Fh+UnicodeString]
0x1800b528a  xor     edx, edx; StringOut
0x1800b528c  call    CipTryGetProcessAppID
0x1800b5291  test    eax, eax
0x1800b5293  js      short loc_1800B52A2
0x1800b5295  cmp     [rbp+3Fh+UnicodeString.Length], r14w
0x1800b529a  jbe     short loc_1800B52A2
0x1800b529c  lea     rdx, [rbp+3Fh+UnicodeString]
0x1800b52a0  jmp     short loc_1800B52A4
0x1800b52a2  xor     edx, edx; PCUNICODE_STRING
0x1800b52a4  lea     rax, [rbp+3Fh+var_8C+4]
0x1800b52a8  mov     r9d, edi
0x1800b52ab  lea     r8, [rbp+3Fh+var_70]; PCUNICODE_STRING
0x1800b52af  mov     qword ptr [rsp+0D0h+var_B0], rax; __int64
0x1800b52b4  lea     rcx, [rbp+3Fh+StringIn]; StringIn
0x1800b52b8  call    CiCatDbSendSmartAppControlBlockToast2
0x1800b52bd  cmp     [rbp+3Fh+UnicodeString.Buffer], r14
0x1800b52c1  jz      short loc_1800B52D3
0x1800b52c3  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x1800b52c7  call    cs:__imp_RtlFreeUnicodeString
0x1800b52ce  nop     dword ptr [rax+rax+00h]
0x1800b52d3  mov     eax, dword ptr [rbp+3Fh+var_8C+4]
0x1800b52d6  neg     eax
0x1800b52d8  sbb     ecx, ecx
0x1800b52da  neg     ecx
0x1800b52dc  add     ecx, 2
0x1800b52df  mov     [rbx+838h], ecx
0x1800b52e5  mov     r15d, dword ptr [rbp+3Fh+var_8C]
0x1800b52e9  jmp     short loc_1800B52F5
0x1800b52eb  mov     dword ptr [rbx+838h], 1
0x1800b52f5  mov     al, [r13+0]
0x1800b52f9  lea     r8, [rbp+3Fh+StringIn]
0x1800b52fd  mov     r14, [rbp+3Fh+arg_18]
0x1800b5301  mov     rcx, rbx
0x1800b5304  mov     r9d, [rbp+3Fh+arg_20]
0x1800b5308  mov     rdx, r14
0x1800b530b  mov     [rsp+30h], al
0x1800b530f  mov     dword ptr [rsp+0D0h+EventDescriptor], edi
0x1800b5313  mov     [rsp+0D0h+var_B0], r12b
0x1800b5318  call    CiInstrumentSignatureFailuresOnCleanStack
0x1800b531d  xor     edx, edx
0x1800b531f  cmp     [r13+0], dl
0x1800b5323  jnz     loc_1800B5652
0x1800b5329  test    [rbp+3Fh+arg_20], 0E41FFF87h
0x1800b5330  mov     r8d, 0C0E90002h
0x1800b5336  jnz     short loc_1800B5397
0x1800b5338  mov     rax, cs:g_CipWhichLevelComparisons
0x1800b533f  mov     rcx, r12
0x1800b5342  and     ecx, 0Fh
0x1800b5345  mov     ecx, [rax+rcx*4]
0x1800b5348  test    cl, 4
0x1800b534b  jz      short loc_1800B5397
0x1800b534d  test    cs:g_CiPolicyState, 4000h
0x1800b5357  jz      short loc_1800B5397
0x1800b5359  cmp     dword ptr [rbx+844h], 0FFFFFFFFh
0x1800b5360  jnz     short loc_1800B5397
0x1800b5362  mov     rcx, rbx
0x1800b5365  call    CiDefenderOffline
0x1800b536a  test    al, al
0x1800b536c  jz      short loc_1800B537A
0x1800b536e  lea     edi, [r8+8]
0x1800b5372  mov     r15d, edi
0x1800b5375  mov     dword ptr [rbp+3Fh+var_8C], edi
0x1800b5378  jmp     short loc_1800B5397
0x1800b537a  cmp     edi, 0C0E90009h
0x1800b5380  jz      short loc_1800B5397
0x1800b5382  lea     eax, [rdi+3F16FFF5h]
0x1800b5388  cmp     eax, 2
0x1800b538b  jbe     short loc_1800B5397
0x1800b538d  mov     r15d, r8d
0x1800b5390  mov     dword ptr [rbp+3Fh+var_8C], r8d
0x1800b5394  mov     edi, r8d
0x1800b5397  call    cs:__imp_PsIsCurrentThreadPrefetching
0x1800b539e  nop     dword ptr [rax+rax+00h]
0x1800b53a3  test    al, al
0x1800b53a5  jnz     loc_1800B553D
0x1800b53ab  test    dword ptr [rbx+940h], 100h
0x1800b53b5  jnz     loc_1800B553D
0x1800b53bb  cmp     dword ptr [rbp+3Fh+arg_40], 0
0x1800b53c2  lea     rcx, CiPolicyFailure
0x1800b53c9  mov     r9b, [rbp+3Fh+arg_30]; int
0x1800b53cd  lea     rax, CiIumPolicyFailure
0x1800b53d4  cmovz   rax, rcx
0x1800b53d8  lea     rdx, [rbp+3Fh+StringIn]; int
0x1800b53dc  mov     [rsp+0D0h+EventDescriptor], rax; EventDescriptor
0x1800b53e1  lea     rcx, [rbp+3Fh+var_70]; int
0x1800b53e5  mov     r8b, r12b; int
0x1800b53e8  mov     dword ptr [rsp+0D0h+var_B0], edi; char
0x1800b53ec  call    CiLogPolicyEvent
0x1800b53f1  mov     rcx, rbx
0x1800b53f4  call    CiLogSignatureInformation
0x1800b53f9  cmp     r12b, 7
0x1800b53fd  jnz     short loc_1800B540F
0x1800b53ff  test    cs:g_CiOptions, 400h
0x1800b5409  jz      loc_1800B553D
0x1800b540f  xor     r14d, r14d
0x1800b5412  cmp     r14d, 4
0x1800b5416  jnb     short loc_1800B544A
0x1800b5418  lea     rax, asc_1800305C0; "*,"
  ... truncated ...
```
