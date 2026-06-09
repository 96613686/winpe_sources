# CipReportAndReprieveUMCIFailure

- ea: `0x1800b5098`
- end: `0x1800b5828`
- name: `CipReportAndReprieveUMCIFailure`
- size: `1936`
- prototype: `__int64 __fastcall(int, int, int, int, int, char, int, char, __int64, PCEVENT_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e5a50`

## callees

- `0x180010094`
- `0x18002c000`
- `0x18005c37c`
- `0x1800620e0`
- `0x18006cfa4`
- `0x18006da7c`
- `0x180073840`
- `0x180076090`
- `0x18007a2b4`
- `0x18007f3e0`
- `0x18009f148`
- `0x18009f2d8`
- `0x1800a00f8`
- `0x1800a0390`
- `0x1800a3eb0`
- `0x1800a7800`
- `0x1800ac3f8`
- `0x1800b5098`
- `0x1800b5830`
- `0x1800c2998`
- `0x1800cb930`
- `0x1800d8a30`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800b5427`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800b5427`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b526f`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b5750`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b526f`
- `ntoskrnl!PsGetProcessProtection` at `0x1800b5750`
- `ntoskrnl!KdDebuggerNotPresent` at `0x1800b5674`
- `ntoskrnl!DbgPrint` at `0x1800b568c`
- `ntoskrnl!DbgPrint` at `0x1800b568c`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1800b5706`
- `ntoskrnl!PsQueryProcessAttributesByToken` at `0x1800b5706`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b529e`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b54f7`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b529e`
- `ntoskrnl!PsIsCurrentThreadPrefetching` at `0x1800b54f7`
- `ntoskrnl!PsGetProcessSignatureLevel` at `0x1800b56e9`
- `ntoskrnl!PsGetProcessSignatureLevel` at `0x1800b56e9`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b539e`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b53bd`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b5590`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b539e`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b53bd`
- `ntoskrnl!RtlFindUnicodeSubstring` at `0x1800b5590`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800b515c`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800b515c`
- `ntoskrnl!DbgPrintEx` at `0x1800b55ba`
- `ntoskrnl!DbgPrintEx` at `0x1800b55d6`
- `ntoskrnl!DbgPrintEx` at `0x1800b55ee`
- `ntoskrnl!DbgPrintEx` at `0x1800b560a`
- `ntoskrnl!DbgPrintEx` at `0x1800b5622`
- `ntoskrnl!DbgPrintEx` at `0x1800b563a`
- `ntoskrnl!DbgPrintEx` at `0x1800b5652`
- `ntoskrnl!DbgPrintEx` at `0x1800b55ba`
- `ntoskrnl!DbgPrintEx` at `0x1800b55d6`
- `ntoskrnl!DbgPrintEx` at `0x1800b55ee`
- `ntoskrnl!DbgPrintEx` at `0x1800b560a`
- `ntoskrnl!DbgPrintEx` at `0x1800b5622`
- `ntoskrnl!DbgPrintEx` at `0x1800b563a`
- `ntoskrnl!DbgPrintEx` at `0x1800b5652`
- `ntoskrnl!KdDebuggerEnabled` at `0x1800b5669`

## string_xrefs

- `0x1800b5600`: `* The binary was attempted to be loaded in the process: %wZ\n`

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
              && (LOBYTE(v35) = 1, RtlFindUnicodeSubstring(&StringIn, &qword_180030630, v35)) )
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
        if ( RtlFindUnicodeSubstring(&StringIn, &asc_1800305F0[8 * i], v41) )
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
        DbgPrint("Code Integrity violation:  %d\n", 9304);
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
0x1800b5098  mov     rax, rsp
0x1800b509b  mov     [rax+20h], r9
0x1800b509f  mov     [rax+18h], r8
0x1800b50a3  mov     [rax+10h], rdx
0x1800b50a7  push    rbp
0x1800b50a8  push    rbx
0x1800b50a9  push    rsi
0x1800b50aa  push    rdi
0x1800b50ab  push    r12
0x1800b50ad  push    r13
0x1800b50af  push    r14
0x1800b50b1  push    r15
0x1800b50b3  lea     rbp, [rax-47h]
0x1800b50b7  sub     rsp, 98h
0x1800b50be  mov     edi, [rbp+3Fh+arg_38]
0x1800b50c4  xor     r12d, r12d
0x1800b50c7  mov     r13, [rbp+3Fh+arg_40]
0x1800b50ce  mov     rbx, rcx
0x1800b50d1  mov     r14, [rbp+3Fh+arg_48]
0x1800b50d8  xorps   xmm0, xmm0
0x1800b50db  xorps   xmm1, xmm1
0x1800b50de  mov     [rbp+3Fh+var_90], r12b
0x1800b50e2  add     rcx, 18h
0x1800b50e6  mov     [rbp+3Fh+var_8F], r12b
0x1800b50ea  mov     [r13+0], r12b
0x1800b50ee  mov     rsi, r9
0x1800b50f1  mov     byte ptr [r14], 1
0x1800b50f5  mov     r10, rdx
0x1800b50f8  movups  xmmword ptr [rbp+3Fh+var_70.Length], xmm0
0x1800b50fc  mov     [rbp+3Fh+var_60], r12
0x1800b5100  mov     r15d, edi
0x1800b5103  mov     [rbp+3Fh+arg_0], r12b
0x1800b5107  movups  xmmword ptr [rbp+3Fh+StringIn.Length], xmm0
0x1800b510b  mov     [rbp+3Fh+var_58], r12
0x1800b510f  movups  xmmword ptr [rbp+3Fh+UnicodeString.Length], xmm1
0x1800b5113  mov     [rbp+3Fh+var_84], r12d
0x1800b5117  mov     dword ptr [rbp+3Fh+var_8C], edi
0x1800b511a  mov     dword ptr [rbp+3Fh+var_8C+4], r12d
0x1800b511e  call    CipIsAcPolicyViolation
0x1800b5123  test    al, al
0x1800b5125  jz      short loc_1800B512E
0x1800b5127  mov     eax, edi
0x1800b5129  jmp     loc_1800B5813
0x1800b512e  lea     r8, [rbp+3Fh+var_58]
0x1800b5132  mov     [rbp+3Fh+arg_48], r12
0x1800b5139  lea     rdx, [rbp+3Fh+StringIn]
0x1800b513d  mov     byte ptr [rbp+3Fh+arg_38], r12b
0x1800b5144  mov     rcx, r10
0x1800b5147  call    CipQueryProcessName
0x1800b514c  lea     r9, [rbp+3Fh+var_60]
0x1800b5150  mov     edx, 400h
0x1800b5155  lea     r8, [rbp+3Fh+var_70]
0x1800b5159  mov     rcx, rsi
0x1800b515c  call    cs:__imp_FsRtlGetFileNameInformation
0x1800b5163  nop     dword ptr [rax+rax+00h]
0x1800b5168  test    eax, eax
0x1800b516a  jns     short loc_1800B5179
0x1800b516c  movups  xmm0, xmmword ptr [rsi+58h]
0x1800b5170  mov     [rbp+3Fh+var_60], r12
0x1800b5174  movdqu  xmmword ptr [rbp+3Fh+var_70.Length], xmm0
0x1800b5179  mov     esi, [rbp+3Fh+arg_20]
0x1800b517c  and     esi, 20000000h
0x1800b5182  call    Feature_TrustedLaunch__private_IsEnabledDeviceUsageNoInline
0x1800b5187  movzx   r12d, [rbp+3Fh+arg_28]
0x1800b518c  xor     edx, edx
0x1800b518e  test    eax, eax
0x1800b5190  jnz     short loc_1800B51A1
0x1800b5192  mov     dword ptr [rbp+3Fh+arg_40], esi
0x1800b5198  test    esi, esi
0x1800b519a  jz      short loc_1800B51BC
0x1800b519c  jmp     loc_1800B5290
0x1800b51a1  test    esi, esi
0x1800b51a3  jnz     loc_1800B53D7
0x1800b51a9  cmp     [rbx+0E10h], rdx
0x1800b51b0  jnz     loc_1800B53D7
0x1800b51b6  mov     dword ptr [rbp+3Fh+arg_40], esi
0x1800b51bc  mov     rcx, [rbp+3Fh+arg_18]
0x1800b51c0  call    CipIsDotNetNativeImage
0x1800b51c5  movzx   ecx, al
0x1800b51c8  mov     eax, [rbx+938h]
0x1800b51ce  shl     ecx, 8
0x1800b51d1  xor     ecx, eax
0x1800b51d3  and     ecx, 100h
0x1800b51d9  xor     ecx, eax
0x1800b51db  mov     [rbx+938h], ecx
0x1800b51e1  mov     rcx, [rbp+3Fh+arg_18]
0x1800b51e5  call    CipIsFileInUMCIExclusionPaths
0x1800b51ea  xor     edx, edx
0x1800b51ec  mov     byte ptr [rbp+3Fh+arg_38], al
0x1800b51f2  test    al, al
0x1800b51f4  jz      short loc_1800B5206
0x1800b51f6  mov     al, [rbp+3Fh+arg_28]
0x1800b51f9  mov     [r14], al
0x1800b51fc  mov     byte ptr [r13+0], 1
0x1800b5201  jmp     loc_1800B57EB
0x1800b5206  cmp     r12b, 1
0x1800b520a  ja      short loc_1800B5222
0x1800b520c  cmp     edi, 0C0000428h
0x1800b5212  jnz     short loc_1800B5222
0x1800b5214  mov     byte ptr [r13+0], 1
0x1800b5219  mov     byte ptr [r14], 1
0x1800b521d  jmp     loc_1800B57FB
0x1800b5222  mov     eax, cs:g_CiDeveloperMode
0x1800b5228  test    al, 1
0x1800b522a  jz      short loc_1800B526B
0x1800b522c  mov     r9d, [rbp+3Fh+arg_20]
0x1800b5230  lea     rax, CiPolicyFailureIgnored
0x1800b5237  mov     [r14], r12b
0x1800b523a  lea     r8, [rbp+3Fh+StringIn]
0x1800b523e  mov     r14, [rbp+3Fh+arg_18]
0x1800b5242  mov     rcx, rbx
0x1800b5245  mov     byte ptr [rsp+30h], 1
0x1800b524a  mov     rdx, r14
0x1800b524d  mov     dword ptr [rsp+0D0h+EventDescriptor], edi
0x1800b5251  mov     byte ptr [r13+0], 1
0x1800b5256  mov     [rbp+3Fh+arg_48], rax
0x1800b525d  mov     [rsp+0D0h+var_B0], r12b
0x1800b5262  call    CiInstrumentSignatureFailuresOnCleanStack
0x1800b5267  xor     edx, edx
0x1800b5269  jmp     short loc_1800B5294
0x1800b526b  mov     rcx, [rbp+3Fh+PROCESS]
0x1800b526f  call    cs:__imp_PsGetProcessProtection
0x1800b5276  nop     dword ptr [rax+rax+00h]
0x1800b527b  cmp     al, 41h ; 'A'
0x1800b527d  jnz     short loc_1800B528E
0x1800b527f  test    byte ptr [rbp+3Fh+arg_20], 10h
0x1800b5283  jnz     short loc_1800B528E
0x1800b5285  lea     rcx, [rbp+3Fh+var_70]
0x1800b5289  call    CipLsaPplPublishDllLoadFailureWnf
0x1800b528e  xor     edx, edx
0x1800b5290  mov     r14, [rbp+3Fh+arg_18]
0x1800b5294  cmp     [r13+0], dl
0x1800b5298  jnz     loc_1800B57B2
0x1800b529e  call    cs:__imp_PsIsCurrentThreadPrefetching
0x1800b52a5  nop     dword ptr [rax+rax+00h]
0x1800b52aa  xor     edx, edx
0x1800b52ac  test    al, al
0x1800b52ae  jnz     loc_1800B547F
0x1800b52b4  cmp     r12b, 7
0x1800b52b8  jnz     short loc_1800B52C4
0x1800b52ba  test    byte ptr [rbp+3Fh+arg_20], 10h
0x1800b52be  jz      loc_1800B547F
0x1800b52c4  test    dword ptr [rbx+938h], 100h
0x1800b52ce  jnz     loc_1800B547F
0x1800b52d4  mov     r14, rdx
0x1800b52d7  cmp     [rbx+5FCh], edx
0x1800b52dd  jnz     short loc_1800B52E7
0x1800b52df  mov     rcx, rbx
0x1800b52e2  call    CiCheckSmartScreenClaim
0x1800b52e7  mov     rcx, [rbx+930h]
0x1800b52ee  test    rcx, rcx
0x1800b52f1  jz      short loc_1800B52FD
0x1800b52f3  mov     eax, [rbx+3C8h]
0x1800b52f9  mov     r14, [rcx+rax*8]
0x1800b52fd  test    [rbp+3Fh+arg_20], 0E41FFF87h
0x1800b5304  jnz     loc_1800B5455
0x1800b530a  mov     rax, cs:g_CipWhichLevelComparisons
0x1800b5311  mov     rcx, r12
0x1800b5314  and     ecx, 0Fh
0x1800b5317  mov     ecx, [rax+rcx*4]
0x1800b531a  test    cl, 4
0x1800b531d  jz      loc_1800B5455
0x1800b5323  test    cs:g_CiPolicyState, 4000h
0x1800b532d  jz      loc_1800B5455
0x1800b5333  call    SIPolicyVerifiedAndReputableUI
0x1800b5338  test    al, al
0x1800b533a  jz      loc_1800B5455
0x1800b5340  test    r14, r14
0x1800b5343  jz      loc_1800B5455
0x1800b5349  cmp     dword ptr [r14+28h], 6
0x1800b534e  sbb     rax, rax
0x1800b5351  and     rax, 0FFFFFFFFFFFFFD50h
0x1800b5357  mov     rcx, [rax+r14+2C0h]
0x1800b535f  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop
0x1800b5366  jnz     short loc_1800B5377
0x1800b5368  mov     rcx, [rax+r14+2C8h]
0x1800b5370  sub     rcx, qword ptr cs:SiPolicyIDNightsWatchDesktop+8
0x1800b5377  xor     r14d, r14d
0x1800b537a  test    rcx, rcx
0x1800b537d  jnz     loc_1800B5455
0x1800b5383  cmp     [rbx+5F8h], r14d
0x1800b538a  jnz     loc_1800B544B
0x1800b5390  mov     r8b, 1
0x1800b5393  lea     rdx, a24; "24"
0x1800b539a  lea     rcx, [rbp+3Fh+var_70]
0x1800b539e  call    cs:__imp_RtlFindUnicodeSubstring
0x1800b53a5  nop     dword ptr [rax+rax+00h]
0x1800b53aa  test    rax, rax
0x1800b53ad  jz      short loc_1800B53E2
0x1800b53af  mov     r8b, 1
0x1800b53b2  lea     rdx, qword_180030630
0x1800b53b9  lea     rcx, [rbp+3Fh+StringIn]
0x1800b53bd  call    cs:__imp_RtlFindUnicodeSubstring
0x1800b53c4  nop     dword ptr [rax+rax+00h]
0x1800b53c9  test    rax, rax
0x1800b53cc  jz      short loc_1800B53E2
0x1800b53ce  mov     dword ptr [rbp+3Fh+var_8C+4], 1
0x1800b53d5  jmp     short loc_1800B541D
0x1800b53d7  mov     dword ptr [rbp+3Fh+arg_40], esi
0x1800b53dd  jmp     loc_1800B5290
0x1800b53e2  mov     rcx, [rbp+3Fh+PROCESS]; PROCESS
0x1800b53e6  lea     r9, [rbp+3Fh+UnicodeString]
0x1800b53ea  xor     edx, edx; StringOut
0x1800b53ec  call    CipTryGetProcessAppID
0x1800b53f1  test    eax, eax
0x1800b53f3  js      short loc_1800B5402
0x1800b53f5  cmp     [rbp+3Fh+UnicodeString.Length], r14w
0x1800b53fa  jbe     short loc_1800B5402
0x1800b53fc  lea     rdx, [rbp+3Fh+UnicodeString]
0x1800b5400  jmp     short loc_1800B5404
0x1800b5402  xor     edx, edx; PCUNICODE_STRING
0x1800b5404  lea     rax, [rbp+3Fh+var_8C+4]
0x1800b5408  mov     r9d, edi
0x1800b540b  lea     r8, [rbp+3Fh+var_70]; PCUNICODE_STRING
0x1800b540f  mov     qword ptr [rsp+0D0h+var_B0], rax; __int64
0x1800b5414  lea     rcx, [rbp+3Fh+StringIn]; StringIn
0x1800b5418  call    CiCatDbSendSmartAppControlBlockToast2
0x1800b541d  cmp     [rbp+3Fh+UnicodeString.Buffer], r14
0x1800b5421  jz      short loc_1800B5433
0x1800b5423  lea     rcx, [rbp+3Fh+UnicodeString]; UnicodeString
0x1800b5427  call    cs:__imp_RtlFreeUnicodeString
0x1800b542e  nop     dword ptr [rax+rax+00h]
0x1800b5433  mov     eax, dword ptr [rbp+3Fh+var_8C+4]
0x1800b5436  neg     eax
0x1800b5438  sbb     ecx, ecx
0x1800b543a  neg     ecx
0x1800b543c  add     ecx, 2
0x1800b543f  mov     [rbx+838h], ecx
0x1800b5445  mov     r15d, dword ptr [rbp+3Fh+var_8C]
0x1800b5449  jmp     short loc_1800B5455
0x1800b544b  mov     dword ptr [rbx+838h], 1
0x1800b5455  mov     al, [r13+0]
0x1800b5459  lea     r8, [rbp+3Fh+StringIn]
0x1800b545d  mov     r14, [rbp+3Fh+arg_18]
0x1800b5461  mov     rcx, rbx
0x1800b5464  mov     r9d, [rbp+3Fh+arg_20]
0x1800b5468  mov     rdx, r14
0x1800b546b  mov     [rsp+30h], al
0x1800b546f  mov     dword ptr [rsp+0D0h+EventDescriptor], edi
0x1800b5473  mov     [rsp+0D0h+var_B0], r12b
0x1800b5478  call    CiInstrumentSignatureFailuresOnCleanStack
0x1800b547d  xor     edx, edx
0x1800b547f  cmp     [r13+0], dl
0x1800b5483  jnz     loc_1800B57B2
0x1800b5489  test    [rbp+3Fh+arg_20], 0E41FFF87h
0x1800b5490  mov     r8d, 0C0E90002h
0x1800b5496  jnz     short loc_1800B54F7
0x1800b5498  mov     rax, cs:g_CipWhichLevelComparisons
0x1800b549f  mov     rcx, r12
0x1800b54a2  and     ecx, 0Fh
0x1800b54a5  mov     ecx, [rax+rcx*4]
0x1800b54a8  test    cl, 4
0x1800b54ab  jz      short loc_1800B54F7
0x1800b54ad  test    cs:g_CiPolicyState, 4000h
0x1800b54b7  jz      short loc_1800B54F7
0x1800b54b9  cmp     dword ptr [rbx+844h], 0FFFFFFFFh
0x1800b54c0  jnz     short loc_1800B54F7
0x1800b54c2  mov     rcx, rbx
0x1800b54c5  call    CiDefenderOffline
0x1800b54ca  test    al, al
0x1800b54cc  jz      short loc_1800B54DA
0x1800b54ce  lea     edi, [r8+8]
0x1800b54d2  mov     r15d, edi
0x1800b54d5  mov     dword ptr [rbp+3Fh+var_8C], edi
0x1800b54d8  jmp     short loc_1800B54F7
0x1800b54da  cmp     edi, 0C0E90009h
0x1800b54e0  jz      short loc_1800B54F7
0x1800b54e2  lea     eax, [rdi+3F16FFF5h]
0x1800b54e8  cmp     eax, 2
0x1800b54eb  jbe     short loc_1800B54F7
0x1800b54ed  mov     r15d, r8d
0x1800b54f0  mov     dword ptr [rbp+3Fh+var_8C], r8d
0x1800b54f4  mov     edi, r8d
0x1800b54f7  call    cs:__imp_PsIsCurrentThreadPrefetching
0x1800b54fe  nop     dword ptr [rax+rax+00h]
0x1800b5503  test    al, al
0x1800b5505  jnz     loc_1800B569D
0x1800b550b  test    dword ptr [rbx+938h], 100h
0x1800b5515  jnz     loc_1800B569D
0x1800b551b  cmp     dword ptr [rbp+3Fh+arg_40], 0
0x1800b5522  lea     rcx, CiPolicyFailure
0x1800b5529  mov     r9b, [rbp+3Fh+arg_30]; int
0x1800b552d  lea     rax, CiIumPolicyFailure
0x1800b5534  cmovz   rax, rcx
0x1800b5538  lea     rdx, [rbp+3Fh+StringIn]; int
0x1800b553c  mov     [rsp+0D0h+EventDescriptor], rax; EventDescriptor
0x1800b5541  lea     rcx, [rbp+3Fh+var_70]; int
0x1800b5545  mov     r8b, r12b; int
0x1800b5548  mov     dword ptr [rsp+0D0h+var_B0], edi; char
0x1800b554c  call    CiLogPolicyEvent
0x1800b5551  mov     rcx, rbx
0x1800b5554  call    CiLogSignatureInformation
0x1800b5559  cmp     r12b, 7
0x1800b555d  jnz     short loc_1800B556F
0x1800b555f  test    cs:g_CiOptions, 400h
0x1800b5569  jz      loc_1800B569D
0x1800b556f  xor     r14d, r14d
0x1800b5572  cmp     r14d, 4
0x1800b5576  jnb     short loc_1800B55AA
0x1800b5578  lea     rax, asc_1800305F0; "*,"
  ... truncated ...
```
