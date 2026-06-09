# CipReportAndReprieveUMCIFailure

- ea: `0x1800b3c18`
- end: `0x1800b43a8`
- name: `CipReportAndReprieveUMCIFailure`
- size: `1936`
- prototype: `__int64 __fastcall(int, int, int, int, int, char, int, char, __int64, PCEVENT_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e55e0`

## callees

- `0x180010128`
- `0x18002bfd0`
- `0x18005b66c`
- `0x18006189c`
- `0x18006c1d0`
- `0x18006cca8`
- `0x180072590`
- `0x180074ad4`
- `0x180078d04`
- `0x18007ddb4`
- `0x18009db18`
- `0x18009dca8`
- `0x18009eac8`
- `0x18009ed60`
- `0x1800a2880`
- `0x1800a6380`
- `0x1800aaf78`
- `0x1800b3c18`
- `0x1800b43b0`
- `0x1800c1518`
- `0x1800ca4b0`
- `0x1800d7b00`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800b3fa7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800b3fa7`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b3def`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b42d0`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b3def`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b42d0`
- `ntoskrnl!KdDebuggerNotPresent` at `0x1800b41f4`
- `ntoskrnl!DbgPrint` at `0x1800b420c`
- `ntoskrnl!DbgPrint` at `0x1800b420c`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1800b4286`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1800b4286`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b3e1e`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b4077`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b3e1e`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b4077`
- `ntoskrnl!PsGetProcessSignatureLevel` at `0x1800b4269`
- `ntoskrnl!PsGetProcessSignatureLevel` at `0x1800b4269`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b3f1e`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b3f3d`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b4110`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b3f1e`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b3f3d`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b4110`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800b3cdc`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800b3cdc`
- `ntoskrnl!DbgPrintEx` at `0x1800b413a`
- `ntoskrnl!DbgPrintEx` at `0x1800b4156`
- `ntoskrnl!DbgPrintEx` at `0x1800b416e`
- `ntoskrnl!DbgPrintEx` at `0x1800b418a`
- `ntoskrnl!DbgPrintEx` at `0x1800b41a2`
- `ntoskrnl!DbgPrintEx` at `0x1800b41ba`
- `ntoskrnl!DbgPrintEx` at `0x1800b41d2`
- `ntoskrnl!DbgPrintEx` at `0x1800b413a`
- `ntoskrnl!DbgPrintEx` at `0x1800b4156`
- `ntoskrnl!DbgPrintEx` at `0x1800b416e`
- `ntoskrnl!DbgPrintEx` at `0x1800b418a`
- `ntoskrnl!DbgPrintEx` at `0x1800b41a2`
- `ntoskrnl!DbgPrintEx` at `0x1800b41ba`
- `ntoskrnl!DbgPrintEx` at `0x1800b41d2`
- `ntoskrnl!KdDebuggerEnabled` at `0x1800b41e9`

## string_xrefs

- `0x1800b4180`: `* The binary was attempted to be loaded in the process: %wZ\n`

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
  __int64 v45; // rdx
  char v46; // [rsp+48h] [rbp-51h] BYREF
  char v47[3]; // [rsp+49h] [rbp-50h] BYREF
  __int64 v48; // [rsp+4Ch] [rbp-4Dh] BYREF
  int v49; // [rsp+54h] [rbp-45h] BYREF
  UNICODE_STRING StringIn; // [rsp+58h] [rbp-41h] BYREF
  UNICODE_STRING v51; // [rsp+68h] [rbp-31h] BYREF
  __int64 v52; // [rsp+78h] [rbp-21h] BYREF
  __int64 v53; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp-11h] BYREF
  char v55; // [rsp+E8h] [rbp+4Fh] BYREF
  PRKPROCESS PROCESS; // [rsp+F0h] [rbp+57h]
  __int64 v57; // [rsp+F8h] [rbp+5Fh]
  __int64 v58; // [rsp+100h] [rbp+67h]

  v58 = a4;
  v57 = a3;
  PROCESS = a2;
  v10 = a8;
  v11 = a9;
  v13 = a10;
  v46 = 0;
  v47[0] = 0;
  *a9 = 0;
  LOBYTE(v13->Id) = 1;
  v51 = 0;
  v52 = 0;
  v15 = v10;
  v55 = 0;
  StringIn = 0;
  v53 = 0;
  UnicodeString = 0;
  v49 = 0;
  v48 = v10;
  if ( (unsigned __int8)CipIsAcPolicyViolation(a1 + 24) )
    return v10;
  a10 = 0;
  LOBYTE(a8) = 0;
  CipQueryProcessName(v16, &StringIn, &v53);
  if ( (int)FsRtlGetFileNameInformation(a4, 1024, &v51, &v52) < 0 )
  {
    v18 = *(UNICODE_STRING *)(a4 + 88);
    v52 = 0;
    v51 = v18;
  }
  v19 = a5 & 0x20000000;
  IsEnabledDeviceUsageNoInline = Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline();
  v23 = a6;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( v19 || *(_QWORD *)(a1 + 3600) )
    {
      LODWORD(a9) = v19;
LABEL_21:
      v25 = v58;
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
  *(_DWORD *)(a1 + 2360) ^= ((unsigned __int16)*(_DWORD *)(a1 + 2360)
                           ^ (unsigned __int16)((unsigned __int8)CipIsDotNetNativeImage(v58, 0) << 8))
                          & 0x100;
  LOBYTE(a8) = CipIsFileInUMCIExclusionPaths(v58);
  if ( (_BYTE)a8 )
  {
    LOBYTE(v13->Id) = a6;
    *v11 = 1;
LABEL_99:
    CiAudit(&v51, 5038);
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
    if ( (unsigned __int8)PsGetProcessProtection(PROCESS, 0) == 65 && (a5 & 0x10) == 0 )
      CipLsaPplPublishDllLoadFailureWnf(&v51);
    goto LABEL_21;
  }
  v24 = a5;
  LOBYTE(v13->Id) = v23;
  v25 = v58;
  v26 = v58;
  *v11 = 1;
  a10 = (EVENT_DESCRIPTOR *)CiPolicyFailureIgnored;
  CiInstrumentSignatureFailuresOnCleanStack(a1, v26, (unsigned int)&StringIn, v24, v23, v10, 1);
LABEL_22:
  if ( *v11 )
    goto LABEL_96;
  IsCurrentThreadPrefetching = PsIsCurrentThreadPrefetching();
  v28 = 0;
  if ( !IsCurrentThreadPrefetching && (v23 != 7 || (a5 & 0x10) != 0) && (*(_DWORD *)(a1 + 2360) & 0x100) == 0 )
  {
    v29 = 0;
    if ( !*(_DWORD *)(a1 + 1532) )
      CiCheckSmartScreenClaim(a1, 0);
    v30 = *(_QWORD *)(a1 + 2352);
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
            if ( RtlFindUnicodeSubstring(&v51, L"24", v32)
              && (LOBYTE(v35) = 1, RtlFindUnicodeSubstring(&StringIn, &qword_180030590, v35)) )
            {
              HIDWORD(v48) = 1;
            }
            else
            {
              if ( (int)CipTryGetProcessAppID(PROCESS, 0) >= 0 && UnicodeString.Length )
                p_UnicodeString = &UnicodeString;
              else
                p_UnicodeString = 0;
              CiCatDbSendSmartAppControlBlockToast2(&StringIn, p_UnicodeString, &v51, v10, (__int64)&v48 + 4);
            }
            if ( UnicodeString.Buffer )
              RtlFreeUnicodeString(&UnicodeString);
            *(_DWORD *)(a1 + 2104) = (HIDWORD(v48) != 0) + 2;
            v15 = v48;
          }
        }
      }
    }
    v25 = v58;
    CiInstrumentSignatureFailuresOnCleanStack(a1, v58, (unsigned int)&StringIn, a5, v23, v10, *v11);
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
        CiLogPolicyEvent((int)&v51, (int)&StringIn, v21, v22, v10, a10);
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
      LODWORD(v48) = v37 + 8;
    }
    else if ( v10 != -1058471927 && v10 + 1058471925 > 2 )
    {
      v15 = v37;
      LODWORD(v48) = v37;
      v10 = v37;
    }
  }
  if ( !PsIsCurrentThreadPrefetching() && (*(_DWORD *)(a1 + 2360) & 0x100) == 0 )
  {
    LOBYTE(v39) = a7;
    EventDescriptor = (const EVENT_DESCRIPTOR *)CiIumPolicyFailure;
    if ( !(_DWORD)a9 )
      EventDescriptor = &CiPolicyFailure;
    LOBYTE(v38) = v23;
    CiLogPolicyEvent((int)&v51, (int)&StringIn, v38, v39, v10, EventDescriptor);
    CiLogSignatureInformation(a1);
    if ( v23 != 7 || (g_CiOptions & 0x400) != 0 )
    {
      for ( i = 0; i < 4; ++i )
      {
        LOBYTE(v41) = 1;
        if ( RtlFindUnicodeSubstring(&StringIn, &asc_180030550[8 * i], v41) )
          goto LABEL_78;
      }
      DbgPrintEx(0x65u, 0, "******************************************************************\n");
      DbgPrintEx(0x65u, 0, "* This break indicates this binary is not signed correctly: %wZ\n", &v51);
      DbgPrintEx(0x65u, 0, "* and does not meet the system policy.\n");
      DbgPrintEx(0x65u, 0, "* The binary was attempted to be loaded in the process: %wZ\n", &StringIn);
      DbgPrintEx(0x65u, 0, "* This is not a failure in CI, but a problem with the failing binary.\n");
      DbgPrintEx(0x65u, 0, "* Please contact the binary owner for getting the binary correctly signed.\n");
      DbgPrintEx(0x65u, 0, "******************************************************************\n");
      if ( (unsigned __int8)CiIsUmciDebugBreakEnabled() && (_BYTE)KdDebuggerEnabled && (_BYTE)KdDebuggerNotPresent != 1 )
      {
        DbgPrint("Code Integrity violation:  %d\n", 9269);
        __debugbreak();
      }
LABEL_78:
      v25 = v58;
    }
  }
  if ( *v11 )
    goto LABEL_101;
  if ( v19 )
    goto LABEL_101;
  if ( !*(_DWORD *)(a1 + 3012) )
    goto LABEL_101;
  v43 = v57;
  if ( !v57 )
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
      PsQueryProcessAttributesByToken(v43, 0, &v55);
      if ( v55 && v10 != -1058471934 && v10 + 1058471929 > 6 )
      {
        if ( (((void (__fastcall *)(struct _KPROCESS *, int *))g_CiPrivateNtosApis)(v44, &v49),
              (unsigned __int8)PsGetProcessProtection(v44, v45) != 0x81)
          && (v49 & 4) == 0
          || (int)KappxIsPackageFile(v25, &v46, v47) >= 0 && (v46 || v47[0]) )
        {
          KappxNotifyIntegrityFailureInPackagedProcess(
            v25,
            *(_QWORD *)(a1 + 3016),
            *(_DWORD *)(a1 + 3012),
            v44,
            (__int64)&v48);
          v15 = v48;
        }
      }
    }
  }
LABEL_101:
  CipReleaseFileName(v52);
  CipReleaseProcessName(v53);
  return v15;
}

```

## disassembly

```asm
0x1800b3c18  mov     rax, rsp
0x1800b3c1b  mov     [rax+20h], r9
0x1800b3c1f  mov     [rax+18h], r8
0x1800b3c23  mov     [rax+10h], rdx
0x1800b3c27  push    rbp
0x1800b3c28  push    rbx
0x1800b3c29  push    rsi
0x1800b3c2a  push    rdi
0x1800b3c2b  push    r12
0x1800b3c2d  push    r13
0x1800b3c2f  push    r14
0x1800b3c31  push    r15
0x1800b3c33  lea     rbp, [rax-47h]
0x1800b3c37  sub     rsp, 98h
0x1800b3c3e  mov     edi, [rbp+3Fh+arg_38]
0x1800b3c44  xor     r12d, r12d
0x1800b3c47  mov     r13, [rbp+3Fh+arg_40]
0x1800b3c4e  mov     rbx, rcx
0x1800b3c51  mov     r14, [rbp+3Fh+arg_48]
0x1800b3c58  xorps   xmm0, xmm0
0x1800b3c5b  xorps   xmm1, xmm1
0x1800b3c5e  mov     [rbp+3Fh+var_90], r12b
0x1800b3c62  add     rcx, 18h
0x1800b3c66  mov     [rbp+3Fh+var_8F], r12b
0x1800b3c6a  mov     [r13+0], r12b
0x1800b3c6e  mov     rsi, r9
0x1800b3c71  mov     byte ptr [r14], 1
0x1800b3c75  mov     r10, rdx
0x1800b3c78  movups  xmmword ptr [rbp+3Fh+var_70.Length], xmm0
0x1800b3c7c  mov     [rbp+3Fh+var_60], r12
0x1800b3c80  mov     r15d, edi
0x1800b3c83  mov     [rbp+3Fh+arg_0], r12b
0x1800b3c87  movups  xmmword ptr [rbp+3Fh+StringIn.Length], xmm0
0x1800b3c8b  mov     [rbp+3Fh+var_58], r12
0x1800b3c8f  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm1
0x1800b3c93  mov     [rbp+3Fh+var_84], r12d
0x1800b3c97  mov     dword ptr [rbp+3Fh+var_8C], edi
0x1800b3c9a  mov     dword ptr [rbp+3Fh+var_8C+4], r12d
0x1800b3c9e  call    CipIsAcPolicyViolation
0x1800b3ca3  test    al, al
0x1800b3ca5  jz      short loc_1800B3CAE
0x1800b3ca7  mov     eax, edi
0x1800b3ca9  jmp     loc_1800B4393
0x1800b3cae  lea     r8, [rbp+3Fh+var_58]
0x1800b3cb2  mov     [rbp+3Fh+arg_48], r12
0x1800b3cb9  lea     rdx, [rbp+3Fh+StringIn]
0x1800b3cbd  mov     byte ptr [rbp+3Fh+arg_38], r12b
0x1800b3cc4  mov     rcx, r10
0x1800b3cc7  call    CipQueryProcessName
0x1800b3ccc  lea     r9, [rbp+3Fh+var_60]
0x1800b3cd0  mov     edx, 400h
0x1800b3cd5  lea     r8, [rbp+3Fh+var_70]
0x1800b3cd9  mov     rcx, rsi
0x1800b3cdc  call    cs:__imp_FsRtlGetFileNameInformation
0x1800b3ce3  nop     dword ptr [rax+rax+00h]
0x1800b3ce8  test    eax, eax
0x1800b3cea  jns     short loc_1800B3CF9
0x1800b3cec  movups  xmm0, xmmword ptr [rsi+58h]
0x1800b3cf0  mov     [rbp+3Fh+var_60], r12
0x1800b3cf4  movdqu  xmmword ptr [rbp+3Fh+var_70.Length], xmm0
0x1800b3cf9  mov     esi, [rbp+3Fh+arg_20]
0x1800b3cfc  and     esi, 20000000h
0x1800b3d02  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800b3d07  movzx   r12d, [rbp+3Fh+arg_28]
0x1800b3d0c  xor     edx, edx
0x1800b3d0e  test    eax, eax
0x1800b3d10  jnz     short loc_1800B3D21
0x1800b3d12  mov     dword ptr [rbp+3Fh+arg_40], esi
0x1800b3d18  test    esi, esi
0x1800b3d1a  jz      short loc_1800B3D3C
0x1800b3d1c  jmp     loc_1800B3E10
0x1800b3d21  test    esi, esi
0x1800b3d23  jnz     loc_1800B3F57
0x1800b3d29  cmp     [rbx+0E10h], rdx
0x1800b3d30  jnz     loc_1800B3F57
0x1800b3d36  mov     dword ptr [rbp+3Fh+arg_40], esi
0x1800b3d3c  mov     rcx, [rbp+3Fh+arg_18]
0x1800b3d40  call    CipIsDotNetNativeImage
0x1800b3d45  movzx   ecx, al
0x1800b3d48  mov     eax, [rbx+938h]
0x1800b3d4e  shl     ecx, 8
0x1800b3d51  xor     ecx, eax
0x1800b3d53  and     ecx, 100h
0x1800b3d59  xor     ecx, eax
0x1800b3d5b  mov     [rbx+938h], ecx
0x1800b3d61  mov     rcx, [rbp+3Fh+arg_18]
0x1800b3d65  call    CipIsFileInUMCIExclusionPaths
0x1800b3d6a  xor     edx, edx
0x1800b3d6c  mov     byte ptr [rbp+3Fh+arg_38], al
0x1800b3d72  test    al, al
0x1800b3d74  jz      short loc_1800B3D86
0x1800b3d76  mov     al, [rbp+3Fh+arg_28]
0x1800b3d79  mov     [r14], al
0x1800b3d7c  mov     byte ptr [r13+0], 1
0x1800b3d81  jmp     loc_1800B436B
0x1800b3d86  cmp     r12b, 1
0x1800b3d8a  ja      short loc_1800B3DA2
0x1800b3d8c  cmp     edi, 0C0000428h
0x1800b3d92  jnz     short loc_1800B3DA2
0x1800b3d94  mov     byte ptr [r13+0], 1
0x1800b3d99  mov     byte ptr [r14], 1
0x1800b3d9d  jmp     loc_1800B437B
0x1800b3da2  mov     eax, cs:g_CiDeveloperMode
0x1800b3da8  test    al, 1
0x1800b3daa  jz      short loc_1800B3DEB
0x1800b3dac  mov     r9d, [rbp+3Fh+arg_20]
0x1800b3db0  lea     rax, CiPolicyFailureIgnored
0x1800b3db7  mov     [r14], r12b
0x1800b3dba  lea     r8, [rbp+3Fh+StringIn]
0x1800b3dbe  mov     r14, [rbp+3Fh+arg_18]
0x1800b3dc2  mov     rcx, rbx
0x1800b3dc5  mov     byte ptr [rsp+30h], 1
0x1800b3dca  mov     rdx, r14
0x1800b3dcd  mov     dword ptr [rsp+0D0h+EventDescriptor], edi
0x1800b3dd1  mov     byte ptr [r13+0], 1
0x1800b3dd6  mov     [rbp+3Fh+arg_48], rax
0x1800b3ddd  mov     [rsp+0D0h+var_B0], r12b
0x1800b3de2  call    CiInstrumentSignatureFailuresOnCleanStack
0x1800b3de7  xor     edx, edx
0x1800b3de9  jmp     short loc_1800B3E14
0x1800b3deb  mov     rcx, [rbp+3Fh+PROCESS]
0x1800b3def  call    cs:__imp_PsGetProcessProtection
0x1800b3df6  nop     dword ptr [rax+rax+00h]
0x1800b3dfb  cmp     al, 41h ; 'A'
0x1800b3dfd  jnz     short loc_1800B3E0E
0x1800b3dff  test    byte ptr [rbp+3Fh+arg_20], 10h
0x1800b3e03  jnz     short loc_1800B3E0E
0x1800b3e05  lea     rcx, [rbp+3Fh+var_70]
0x1800b3e09  call    CipLsaPplPublishDllLoadFailureWnf
0x1800b3e0e  xor     edx, edx
0x1800b3e10  mov     r14, [rbp+3Fh+arg_18]
0x1800b3e14  cmp     [r13+0], dl
0x1800b3e18  jnz     loc_1800B4332
0x1800b3e1e  call    cs:__imp_PsIsCurrentThreadPrefetching
0x1800b3e25  nop     dword ptr [rax+rax+00h]
0x1800b3e2a  xor     edx, edx
0x1800b3e2c  test    al, al
0x1800b3e2e  jnz     loc_1800B3FFF
0x1800b3e34  cmp     r12b, 7
0x1800b3e38  jnz     short loc_1800B3E44
0x1800b3e3a  test    byte ptr [rbp+3Fh+arg_20], 10h
0x1800b3e3e  jz      loc_1800B3FFF
0x1800b3e44  test    dword ptr [rbx+938h], 100h
0x1800b3e4e  jnz     loc_1800B3FFF
0x1800b3e54  mov     r14, rdx
0x1800b3e57  cmp     [rbx+5FCh], edx
0x1800b3e5d  jnz     short loc_1800B3E67
0x1800b3e5f  mov     rcx, rbx
0x1800b3e62  call    CiCheckSmartScreenClaim
0x1800b3e67  mov     rcx, [rbx+930h]
0x1800b3e6e  test    rcx, rcx
0x1800b3e71  jz      short loc_1800B3E7D
0x1800b3e73  mov     eax, [rbx+3C8h]
0x1800b3e79  mov     r14, [rcx+rax*8]
0x1800b3e7d  test    [rbp+3Fh+arg_20], 0E41FFF87h
0x1800b3e84  jnz     loc_1800B3FD5
0x1800b3e8a  mov     rax, cs:g_CipWhichLevelComparisons
0x1800b3e91  mov     rcx, r12
0x1800b3e94  and     ecx, 0Fh
0x1800b3e97  mov     ecx, [rax+rcx*4]
0x1800b3e9a  test    cl, 4
0x1800b3e9d  jz      loc_1800B3FD5
0x1800b3ea3  test    cs:g_CiPolicyState, 4000h
0x1800b3ead  jz      loc_1800B3FD5
0x1800b3eb3  call    SIPolicyVerifiedAndReputableUI
0x1800b3eb8  test    al, al
0x1800b3eba  jz      loc_1800B3FD5
0x1800b3ec0  test    r14, r14
0x1800b3ec3  jz      loc_1800B3FD5
0x1800b3ec9  cmp     dword ptr [r14+28h], 6
0x1800b3ece  sbb     rax, rax
0x1800b3ed1  and     rax, 0FFFFFFFFFFFFFD50h
0x1800b3ed7  mov     rcx, [rax+r14+2C0h]
0x1800b3edf  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop
0x1800b3ee6  jnz     short loc_1800B3EF7
0x1800b3ee8  mov     rcx, [rax+r14+2C8h]
0x1800b3ef0  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop+8
0x1800b3ef7  xor     r14d, r14d
0x1800b3efa  test    rcx, rcx
0x1800b3efd  jnz     loc_1800B3FD5
0x1800b3f03  cmp     [rbx+5F8h], r14d
0x1800b3f0a  jnz     loc_1800B3FCB
0x1800b3f10  mov     r8b, 1
0x1800b3f13  lea     rdx, a24; "24"
0x1800b3f1a  lea     rcx, [rbp+3Fh+var_70]
0x1800b3f1e  call    cs:__imp_RtlFindUnicodeSubstring
0x1800b3f25  nop     dword ptr [rax+rax+00h]
0x1800b3f2a  test    rax, rax
0x1800b3f2d  jz      short loc_1800B3F62
0x1800b3f2f  mov     r8b, 1
0x1800b3f32  lea     rdx, qword_180030590
0x1800b3f39  lea     rcx, [rbp+3Fh+StringIn]
0x1800b3f3d  call    cs:__imp_RtlFindUnicodeSubstring
0x1800b3f44  nop     dword ptr [rax+rax+00h]
0x1800b3f49  test    rax, rax
0x1800b3f4c  jz      short loc_1800B3F62
0x1800b3f4e  mov     dword ptr [rbp+3Fh+var_8C+4], 1
0x1800b3f55  jmp     short loc_1800B3F9D
0x1800b3f57  mov     dword ptr [rbp+3Fh+arg_40], esi
0x1800b3f5d  jmp     loc_1800B3E10
0x1800b3f62  mov     rcx, [rbp+3Fh+PROCESS]; PROCESS
0x1800b3f66  lea     r9, [rbp+3Fh+UnicodeString]
0x1800b3f6a  xor     edx, edx; StringOut
0x1800b3f6c  call    CipTryGetProcessAppID
0x1800b3f71  test    eax, eax
0x1800b3f73  js      short loc_1800B3F82
0x1800b3f75  cmp     [rbp+3Fh+UnicodeString.Length], r14w
0x1800b3f7a  jbe     short loc_1800B3F82
0x1800b3f7c  lea     rdx, [rbp+3Fh+UnicodeString]
0x1800b3f80  jmp     short loc_1800B3F84
0x1800b3f82  xor     edx, edx; PCUNICODE_STRING
0x1800b3f84  lea     rax, [rbp+3Fh+var_8C+4]
0x1800b3f88  mov     r9d, edi
0x1800b3f8b  lea     r8, [rbp+3Fh+var_70]; PCUNICODE_STRING
0x1800b3f8f  mov     qword ptr [rsp+0D0h+var_B0], rax; __int64
0x1800b3f94  lea     rcx, [rbp+3Fh+StringIn]; StringIn
0x1800b3f98  call    CiCatDbSendSmartAppControlBlockToast2
0x1800b3f9d  cmp     [rbp+3Fh+UnicodeString.Buffer], r14
0x1800b3fa1  jz      short loc_1800B3FB3
0x1800b3fa3  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x1800b3fa7  call    cs:__imp_RtlFreeUnicodeString
0x1800b3fae  nop     dword ptr [rax+rax+00h]
0x1800b3fb3  mov     eax, dword ptr [rbp+3Fh+var_8C+4]
0x1800b3fb6  neg     eax
0x1800b3fb8  sbb     ecx, ecx
0x1800b3fba  neg     ecx
0x1800b3fbc  add     ecx, 2
0x1800b3fbf  mov     [rbx+838h], ecx
0x1800b3fc5  mov     r15d, dword ptr [rbp+3Fh+var_8C]
0x1800b3fc9  jmp     short loc_1800B3FD5
0x1800b3fcb  mov     dword ptr [rbx+838h], 1
0x1800b3fd5  mov     al, [r13+0]
0x1800b3fd9  lea     r8, [rbp+3Fh+StringIn]
0x1800b3fdd  mov     r14, [rbp+3Fh+arg_18]
0x1800b3fe1  mov     rcx, rbx
0x1800b3fe4  mov     r9d, [rbp+3Fh+arg_20]
0x1800b3fe8  mov     rdx, r14
0x1800b3feb  mov     [rsp+30h], al
0x1800b3fef  mov     dword ptr [rsp+0D0h+EventDescriptor], edi
0x1800b3ff3  mov     [rsp+0D0h+var_B0], r12b
0x1800b3ff8  call    CiInstrumentSignatureFailuresOnCleanStack
0x1800b3ffd  xor     edx, edx
0x1800b3fff  cmp     [r13+0], dl
0x1800b4003  jnz     loc_1800B4332
0x1800b4009  test    [rbp+3Fh+arg_20], 0E41FFF87h
0x1800b4010  mov     r8d, 0C0E90002h
0x1800b4016  jnz     short loc_1800B4077
0x1800b4018  mov     rax, cs:g_CipWhichLevelComparisons
0x1800b401f  mov     rcx, r12
0x1800b4022  and     ecx, 0Fh
0x1800b4025  mov     ecx, [rax+rcx*4]
0x1800b4028  test    cl, 4
0x1800b402b  jz      short loc_1800B4077
0x1800b402d  test    cs:g_CiPolicyState, 4000h
0x1800b4037  jz      short loc_1800B4077
0x1800b4039  cmp     dword ptr [rbx+844h], 0FFFFFFFFh
0x1800b4040  jnz     short loc_1800B4077
0x1800b4042  mov     rcx, rbx
0x1800b4045  call    CiDefenderOffline
0x1800b404a  test    al, al
0x1800b404c  jz      short loc_1800B405A
0x1800b404e  lea     edi, [r8+8]
0x1800b4052  mov     r15d, edi
0x1800b4055  mov     dword ptr [rbp+3Fh+var_8C], edi
0x1800b4058  jmp     short loc_1800B4077
0x1800b405a  cmp     edi, 0C0E90009h
0x1800b4060  jz      short loc_1800B4077
0x1800b4062  lea     eax, [rdi+3F16FFF5h]
0x1800b4068  cmp     eax, 2
0x1800b406b  jbe     short loc_1800B4077
0x1800b406d  mov     r15d, r8d
0x1800b4070  mov     dword ptr [rbp+3Fh+var_8C], r8d
0x1800b4074  mov     edi, r8d
0x1800b4077  call    cs:__imp_PsIsCurrentThreadPrefetching
0x1800b407e  nop     dword ptr [rax+rax+00h]
0x1800b4083  test    al, al
0x1800b4085  jnz     loc_1800B421D
0x1800b408b  test    dword ptr [rbx+938h], 100h
0x1800b4095  jnz     loc_1800B421D
0x1800b409b  cmp     dword ptr [rbp+3Fh+arg_40], 0
0x1800b40a2  lea     rcx, CiPolicyFailure
0x1800b40a9  mov     r9b, [rbp+3Fh+arg_30]; int
0x1800b40ad  lea     rax, CiIumPolicyFailure
0x1800b40b4  cmovz   rax, rcx
0x1800b40b8  lea     rdx, [rbp+3Fh+StringIn]; int
0x1800b40bc  mov     [rsp+0D0h+EventDescriptor], rax; EventDescriptor
0x1800b40c1  lea     rcx, [rbp+3Fh+var_70]; int
0x1800b40c5  mov     r8b, r12b; int
0x1800b40c8  mov     dword ptr [rsp+0D0h+var_B0], edi; char
0x1800b40cc  call    CiLogPolicyEvent
0x1800b40d1  mov     rcx, rbx
0x1800b40d4  call    CiLogSignatureInformation
0x1800b40d9  cmp     r12b, 7
0x1800b40dd  jnz     short loc_1800B40EF
0x1800b40df  test    cs:g_CiOptions, 400h
0x1800b40e9  jz      loc_1800B421D
0x1800b40ef  xor     r14d, r14d
0x1800b40f2  cmp     r14d, 4
0x1800b40f6  jnb     short loc_1800B412A
0x1800b40f8  lea     rax, asc_180030550; "*,"
  ... truncated ...
```
