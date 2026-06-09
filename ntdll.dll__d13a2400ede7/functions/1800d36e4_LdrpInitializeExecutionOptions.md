# LdrpInitializeExecutionOptions

- ea: `0x1800d36e4`
- end: `0x1800d443e`
- name: `LdrpInitializeExecutionOptions`
- size: `3418`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180050718`

## callees

- `0x18000aab0`
- `0x18001eb80`
- `0x1800836d0`
- `0x180083780`
- `0x18009a470`
- `0x18009cff4`
- `0x1800c4700`
- `0x1800d3244`
- `0x1800d3468`
- `0x1800d3640`
- `0x1800d36e4`
- `0x1800d44ac`
- `0x1800d4620`
- `0x1800d4a58`
- `0x1800d5350`
- `0x1800d5428`
- `0x1800d5620`
- `0x1800d5bac`
- `0x1800ec51c`
- `0x180105d70`
- `0x180122794`
- `0x18015ecc0`
- `0x18015ed20`
- `0x180162810`

## string_xrefs

- `0x1800d3a14`: `LegacyDosDevicePaths`
- `0x1800d3fbe`: `LegacyDosDevicePaths`
- `0x1800d3947`: `UseImpersonatedDeviceMap`
- `0x1800d3ef9`: `UseImpersonatedDeviceMap`
- `0x1800d3908`: `MaxLoaderThreads`
- `0x1800d3eb9`: `MaxLoaderThreads`
- `0x1800d37f8`: `DisableHeapLookaside`
- `0x1800d3d80`: `DisableHeapLookaside`
- `0x1800d3a88`: `MinimumStackCommitInBytes`

## pseudocode

```c
__int64 __fastcall LdrpInitializeExecutionOptions(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        HANDLE *a4,
        HANDLE *a5,
        __int64 a6)
{
  bool v7; // bl
  char v8; // r15
  unsigned __int64 v9; // rdi
  int v10; // r12d
  unsigned __int64 v11; // r14
  __int64 v12; // r13
  int v13; // eax
  __int64 v14; // r15
  int v15; // edx
  int v16; // edx
  bool *v17; // rax
  unsigned __int64 v18; // r13
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  __int64 v24; // r12
  __int64 v25; // rdx
  int v26; // r8d
  int ArgList; // eax
  int v28; // ebx
  int ImageFileKeyOption; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  int v40; // eax
  int v41; // eax
  __int64 v42; // rcx
  int v43; // eax
  int ApplicationKeyOption; // eax
  int *v45; // rcx
  int v46; // eax
  int v47; // ebx
  HANDLE *v48; // rdi
  HANDLE *v49; // rdi
  unsigned int v50; // [rsp+40h] [rbp-C0h] BYREF
  int v51; // [rsp+44h] [rbp-BCh] BYREF
  int v52; // [rsp+48h] [rbp-B8h] BYREF
  int v53; // [rsp+4Ch] [rbp-B4h] BYREF
  int v54; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE Handle; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v56; // [rsp+60h] [rbp-A0h] BYREF
  void *v57; // [rsp+68h] [rbp-98h] BYREF
  void *v58; // [rsp+70h] [rbp-90h] BYREF
  int *v59; // [rsp+78h] [rbp-88h]
  __int64 v60; // [rsp+80h] [rbp-80h]
  __int64 v61[2]; // [rsp+88h] [rbp-78h] BYREF
  HANDLE *v62; // [rsp+98h] [rbp-68h]
  HANDLE *v63; // [rsp+A0h] [rbp-60h]
  __int64 v64; // [rsp+A8h] [rbp-58h]
  UNICODE_STRING DestinationString; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v66[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v67; // [rsp+E0h] [rbp-20h]
  WCHAR SourceString[200]; // [rsp+F0h] [rbp-10h] BYREF

  v60 = a1;
  v7 = 1;
  v64 = a6;
  *a4 = 0;
  v8 = 0;
  *a5 = 0;
  v9 = 0;
  v62 = a4;
  v10 = 0;
  v61[0] = a3;
  v11 = 0;
  v63 = a5;
  LODWORD(v12) = 0;
  v58 = 0;
  Handle = 0;
  v52 = 0;
  v53 = -1;
  v59 = 0;
  v56 = 0;
  v57 = 0;
  DestinationString = 0;
  v51 = 0;
  v50 = 0;
  v54 = 0;
  LdrpInitializeCriticalSectionExceptionGlobalMitigation();
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 32) + 8LL) & 0x4000) == 0 )
  {
    v13 = RtlpOpenImageFileOptionsKeyEx(v60, 9, 0, &v58);
    v9 = (unsigned __int64)v58;
    if ( v13 >= 0 )
    {
      *v62 = v58;
      if ( (*(_BYTE *)(a2 + 3) & 0x10) != 0 )
      {
        v14 = 0;
        if ( (int)LdrpConstructModernAppKeyName(SourceString) >= 0 )
        {
          RtlInitUnicodeString(&DestinationString, SourceString);
          v43 = RtlOpenModernAppOptionsKey(&DestinationString, v9, &v57);
          v11 = (unsigned __int64)v57;
          if ( v43 >= 0 )
            *v63 = v57;
        }
      }
      else
      {
        v14 = 0;
      }
      if ( v11 )
      {
        ImageFileKeyOption = RtlQueryImageFileKeyOption(
                               v11,
                               L"DisableHeapLookaside",
                               4,
                               &RtlpDisableHeapLookaside,
                               4,
                               0);
        if ( (int)(ImageFileKeyOption + 0x80000000) < 0 || ImageFileKeyOption == -2147483643 )
          goto LABEL_93;
      }
      if ( v9 )
        RtlQueryImageFileKeyOption(v9, L"DisableHeapLookaside", 4, &RtlpDisableHeapLookaside, 4, 0);
      if ( v11 )
      {
LABEL_93:
        v31 = RtlQueryImageFileKeyOption(v11, L"FrontEndHeapDebugOptions", 4, &v52, 4, 0);
        if ( (int)(v31 + 0x80000000) < 0 || v31 == -2147483643 )
        {
          v10 = v52;
          goto LABEL_97;
        }
        v10 = v52;
      }
      if ( v9 )
      {
        RtlQueryImageFileKeyOption(v9, L"FrontEndHeapDebugOptions", 4, &v52, 4, 0);
        v10 = v52;
      }
      if ( !v11 )
      {
LABEL_12:
        if ( v9 )
          RtlQueryImageFileKeyOption(v9, L"HeapFeatures", 11, &v56, 8, 0);
LABEL_14:
        if ( v56 )
        {
          ApplicationKeyOption = RtlQueryApplicationKeyOption(
                                   v11,
                                   v9,
                                   (unsigned int)L"PgSamplingOptions",
                                   4,
                                   (__int64)&v53,
                                   4);
          v45 = &v53;
          if ( ApplicationKeyOption < 0 )
            v45 = 0;
          v59 = v45;
        }
        if ( !v11
          || (v33 = RtlQueryImageFileKeyOption(v11, L"ShutdownFlags", 4, &RtlpShutdownProcessFlags, 4, 0),
              (int)(v33 + 0x80000000) >= 0)
          && v33 != -2147483643 )
        {
          if ( v9 )
            RtlQueryImageFileKeyOption(v9, L"ShutdownFlags", 4, &RtlpShutdownProcessFlags, 4, 0);
          if ( !v11 )
            goto LABEL_19;
        }
        v34 = RtlQueryImageFileKeyOption(v11, L"UnloadEventTraceDepth", 4, &v50, 4, 0);
        if ( (int)(v34 + 0x80000000) >= 0 && v34 != -2147483643 )
        {
LABEL_19:
          if ( v9 )
            RtlQueryImageFileKeyOption(v9, L"UnloadEventTraceDepth", 4, &v50, 4, 0);
        }
        if ( v50 )
          RtlpUnloadEventTraceExNumber = v50;
        v50 = 0;
        if ( !v11
          || (v35 = RtlQueryImageFileKeyOption(v11, L"MaxLoaderThreads", 4, &v50, 4, 0), (int)(v35 + 0x80000000) >= 0)
          && v35 != -2147483643 )
        {
          if ( v9 )
            RtlQueryImageFileKeyOption(v9, L"MaxLoaderThreads", 4, &v50, 4, 0);
        }
        if ( v50 )
          *(_DWORD *)(*(_QWORD *)(a2 + 32) + 1036LL) = v50;
        v50 = 0;
        if ( !v11
          || (v36 = RtlQueryImageFileKeyOption(v11, L"UseImpersonatedDeviceMap", 4, &v50, 4, 0),
              (int)(v36 + 0x80000000) >= 0)
          && v36 != -2147483643 )
        {
          if ( v9 )
            RtlQueryImageFileKeyOption(v9, L"UseImpersonatedDeviceMap", 4, &v50, 4, 0);
        }
        if ( v50 )
          LdrpUseImpersonatedDeviceMap = 1;
        v50 = 0;
        if ( !v11
          || (v37 = RtlQueryImageFileKeyOption(v11, L"TracingFlags", 4, &v50, 4, 0), (int)(v37 + 0x80000000) >= 0)
          && v37 != -2147483643 )
        {
          if ( v9 )
            RtlQueryImageFileKeyOption(v9, L"TracingFlags", 4, &v50, 4, 0);
        }
        if ( v50 )
          _InterlockedOr((volatile signed __int32 *)(a2 + 888), v50);
        v50 = 0;
        if ( v11
          && ((v38 = RtlQueryImageFileKeyOption(v11, L"RaiseExceptionOnPossibleDeadlock", 4, &v50, 4, 0),
               v15 = v38,
               (int)(v38 + 0x80000000) < 0)
           || v38 == -2147483643)
          || v9
          && ((v15 = RtlQueryImageFileKeyOption(v9, L"RaiseExceptionOnPossibleDeadlock", 4, &v50, 4, 0),
               (int)(v15 + 0x80000000) < 0)
           || v15 == -2147483643) )
        {
          if ( v15 >= 0 )
            RtlpRaiseExceptionOnPossibleDeadlock = v50 != 0;
        }
        v50 = 0;
        if ( v11
          && ((v39 = RtlQueryImageFileKeyOption(v11, L"LegacyDosDevicePaths", 4, &v50, 4, 0),
               v16 = v39,
               (int)(v39 + 0x80000000) < 0)
           || v39 == -2147483643)
          || v9
          && ((v16 = RtlQueryImageFileKeyOption(v9, L"LegacyDosDevicePaths", 4, &v50, 4, 0), (int)(v16 + 0x80000000) < 0)
           || v16 == -2147483643) )
        {
          if ( v16 >= 0 )
            RtlpInitializeLegacyDosDevicePathState(v50);
        }
        v50 = 0;
        if ( (int)RtlQueryImageFileKeyOption(v9, L"CFGOptions", 4, &v50, 4, 0) >= 0 && (v50 & 1) != 0 )
        {
          LdrProtectMrdata(0);
          RtlGuardAllowSuppressedCalls = 1;
          LdrProtectMrdata(1);
        }
        if ( (*(_BYTE *)(a2 + 3) & 1) != 0 )
        {
          v66[0] = 48;
          v66[2] = &qword_180171E20;
          v66[3] = 64;
          v66[1] = v9;
          v67 = 0;
          v46 = NtOpenKey(&LdrpLargePageDllKeyHandle, 1, v66);
          v28 = v46;
          if ( v46 == -1073741772 )
          {
            LdrpLargePageDllKeyHandle = 0;
          }
          else if ( v46 < 0 )
          {
            goto LABEL_163;
          }
        }
        RtlQueryImageFileKeyOption(v9, L"MinimumStackCommitInBytes", 4, &v50, 4, 0);
        if ( *(_QWORD *)(a2 + 792) < (unsigned __int64)v50 )
          *(_QWORD *)(a2 + 792) = v50;
        do
        {
          v50 = 0;
          RtlQueryImageFileKeyOption(v9, (&off_180170F00)[2 * v14], 4, &v50, 4, 0);
          v17 = (bool *)*(&off_180170F00 + 2 * v14++ + 1);
          *v17 = v50 != 0;
        }
        while ( v14 != 3 );
        v50 = 0;
        RtlQueryImageFileKeyOption(v9, L"MaxDeadActivationContexts", 4, &v50, 4, 0);
        v18 = 0;
        if ( v50 )
          g_SxsMaxDeadActivationContexts = v50;
        v50 = 0;
        if ( (int)RtlQueryImageFileKeyOption(v9, L"ImageExpansionMitigation", 4, &v50, 4, 0) >= 0 )
          LdrpImageExpansionMitigation = v50;
        v8 = BYTE1(*(_DWORD *)(a2 + 188)) & 1;
        if ( v11
          && ((v40 = RtlQueryImageFileKeyOption(v11, L"GlobalFlag", 4, &v51, 4, 0),
               v19 = v40,
               (int)(v40 + 0x80000000) < 0)
           || v40 == -2147483643) )
        {
          v18 = v11;
        }
        else
        {
          if ( !v9 )
            goto LABEL_65;
          v19 = RtlQueryImageFileKeyOption(v9, L"GlobalFlag", 4, &v51, 4, 0);
          if ( (int)(v19 + 0x80000000) >= 0 && v19 != -2147483643 )
            goto LABEL_65;
          v18 = v9;
        }
        if ( v19 >= 0 )
        {
          v47 = v51;
          if ( (v51 & 0x2000100) != 0 )
          {
            if ( !(unsigned int)LdrpIsVerifierActivationFilterMatched(a2, v11, v9) )
            {
              v47 &= 0xFDFFFEFF;
              v51 = v47;
            }
            if ( (v47 & 0x2000100) != 0 )
            {
              if ( (int)LdrpQueryAndUpdateVerifierLaunchCounter(v60, &v54) < 0 )
                goto LABEL_65;
              if ( !v54 )
              {
                v47 &= 0xFDFFFEFF;
                v51 = v47;
              }
            }
          }
          *(_DWORD *)(a2 + 188) = v47;
        }
LABEL_65:
        if ( v11
          && ((v41 = RtlQueryImageFileKeyOption(v11, L"GlobalFlag2", 4, &v51, 4, 0),
               v20 = v41,
               (int)(v41 + 0x80000000) < 0)
           || v41 == -2147483643)
          || v9
          && ((v20 = RtlQueryImageFileKeyOption(v9, L"GlobalFlag2", 4, &v51, 4, 0), (int)(v20 + 0x80000000) < 0)
           || v20 == -2147483643) )
        {
          if ( v20 >= 0 )
            *(_DWORD *)(a2 + 1988) = v51;
        }
        v21 = *(_DWORD *)(a2 + 188) & 0x2000100;
        v50 = 0;
        v12 = -(__int64)(v21 != 0) & v18;
        v7 = v21 == 0;
        if ( v11
          && ((v22 = RtlQueryImageFileKeyOption(v11, L"QueryProcessModuleInformationLoopDetectorCount", 4, &v50, 4, 0),
               (int)(v22 + 0x80000000) < 0)
           || v22 == -2147483643)
          || v9
          && ((v22 = RtlQueryImageFileKeyOption(v9, L"QueryProcessModuleInformationLoopDetectorCount", 4, &v50, 4, 0),
               (int)(v22 + 0x80000000) < 0)
           || v22 == -2147483643) )
        {
          if ( v22 >= 0 )
            LdrpQueryProcessModuleInformationLoopDetectorCount = v50;
        }
        goto LABEL_77;
      }
LABEL_97:
      v32 = RtlQueryImageFileKeyOption(v11, L"HeapFeatures", 11, &v56, 8, 0);
      if ( (int)(v32 + 0x80000000) < 0 || v32 == -2147483643 )
        goto LABEL_14;
      goto LABEL_12;
    }
  }
LABEL_77:
  if ( (unsigned int)LdrControlFlowGuardEnforced() )
    v10 |= 1u;
  v23 = v10;
  v24 = v60;
  RtlSetGlobalHeapFeatures(v60, v23, *(_DWORD *)(*(_QWORD *)(a2 + 32) + 8LL), v56, (__int64)v59);
  if ( v7 && !LdrpIsSecureProcess && (MEMORY[0x7FFE03A0] & 1) != 0 )
  {
    if ( (int)AVrfOpenCurrentUserImageFileOptionsKey(v24, v25, &Handle) < 0 )
    {
      Handle = 0;
    }
    else if ( (int)RtlQueryImageFileKeyOption(Handle, L"GlobalFlag", 4, &v51, 4, 0) >= 0 )
    {
      LODWORD(v12) = (_DWORD)Handle;
      *(_DWORD *)(a2 + 188) |= v51 & 0x2000100;
    }
  }
  if ( (*(_DWORD *)(a2 + 188) & 0x2000100) != 0 || (unsigned __int8)LdrpPayloadRestrictionMitigationsEnabled() )
  {
    LOBYTE(v26) = v8;
    ArgList = LdrpInitializeApplicationVerifierPackage(v24, a2, v26, v12, v61[0], v64);
    v28 = ArgList;
    if ( ArgList < 0 )
    {
      LdrpLogInternal(
        (int)"minkernel\\ldr\\ldrinit.c",
        10530,
        (int)"LdrpInitializeExecutionOptions",
        0,
        "Initializing the application verifier package failed with status 0x%08lx\n",
        ArgList);
      goto LABEL_163;
    }
  }
  else
  {
    v28 = 0;
    if ( !v11 && !v9 )
    {
      if ( *(_BYTE *)(a2 + 2) )
      {
        v42 = *(_QWORD *)(a2 + 32);
        v61[0] = 0x200000;
        v61[1] = (__int64)v66;
        if ( (int)RtlQueryEnvironmentVariable_U(*(_QWORD *)(v42 + 128), &qword_180171DA0, v61) < 0
          || (v28 = RtlUnicodeStringToInteger(v61, 0, &v50), v28 < 0)
          || !v50 )
        {
          *(_DWORD *)(a2 + 188) |= 0x70u;
        }
      }
    }
  }
  if ( (*(_BYTE *)(a2 + 1988) & 1) != 0 )
    *(_DWORD *)(a2 + 1984) |= 1u;
  if ( v28 >= 0 )
  {
    LdrpQueryIllegalCWDDevices(v9);
    goto LABEL_88;
  }
LABEL_163:
  v48 = v62;
  if ( *v62 )
  {
    NtClose(*v62);
    *v48 = 0;
  }
  v49 = v63;
  if ( *v63 )
  {
    NtClose(*v63);
    *v49 = 0;
  }
LABEL_88:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x1800d36e4  push    rbp
0x1800d36e6  push    rbx
0x1800d36e7  push    rsi
0x1800d36e8  push    rdi
0x1800d36e9  push    r12
0x1800d36eb  push    r13
0x1800d36ed  push    r14
0x1800d36ef  push    r15
0x1800d36f1  lea     rbp, [rsp-198h]
0x1800d36f9  sub     rsp, 298h
0x1800d3700  mov     rax, cs:__security_cookie
0x1800d3707  xor     rax, rsp
0x1800d370a  mov     [rbp+1D0h+var_50], rax
0x1800d3711  mov     rax, [rbp+1D0h+arg_20]
0x1800d3718  xorps   xmm0, xmm0
0x1800d371b  mov     [rbp+1D0h+var_250], rcx
0x1800d371f  mov     rsi, rdx
0x1800d3722  mov     rcx, [rbp+1D0h+arg_28]
0x1800d3729  mov     bl, 1
0x1800d372b  mov     [rbp+1D0h+var_228], rcx
0x1800d372f  xor     ecx, ecx
0x1800d3731  mov     [r9], rcx
0x1800d3734  mov     r15b, cl
0x1800d3737  mov     [rax], rcx
0x1800d373a  mov     edi, ecx
0x1800d373c  mov     [rbp+1D0h+var_238], r9
0x1800d3740  mov     r12d, ecx
0x1800d3743  mov     [rbp+1D0h+var_248], r8
0x1800d3747  mov     r14d, ecx
0x1800d374a  mov     [rbp+1D0h+var_230], rax
0x1800d374e  mov     r13d, ecx
0x1800d3751  mov     [rsp+2D0h+var_260], rcx
0x1800d3756  mov     [rsp+2D0h+Handle], rcx
0x1800d375b  mov     [rsp+2D0h+var_288], ecx
0x1800d375f  mov     [rsp+2D0h+var_284], 0FFFFFFFFh
0x1800d3767  mov     [rsp+2D0h+var_258], rcx
0x1800d376c  mov     [rsp+2D0h+var_270], rcx
0x1800d3771  mov     [rsp+2D0h+var_268], rcx
0x1800d3776  movups  xmmword ptr [rbp+1D0h+DestinationString.Length], xmm0
0x1800d377a  mov     [rsp+2D0h+var_28C], ecx
0x1800d377e  mov     [rsp+2D0h+var_290], ecx
0x1800d3782  mov     [rsp+2D0h+var_280], ecx
0x1800d3786  call    LdrpInitializeCriticalSectionExceptionGlobalMitigation
0x1800d378b  mov     rax, [rsi+20h]
0x1800d378f  test    dword ptr [rax+8], 4000h
0x1800d3796  jnz     loc_1800D3C8E
0x1800d379c  mov     rcx, [rbp+1D0h+var_250]
0x1800d37a0  lea     r9, [rsp+2D0h+var_260]
0x1800d37a5  xor     r8d, r8d
0x1800d37a8  lea     edx, [r13+9]
0x1800d37ac  call    RtlpOpenImageFileOptionsKeyEx
0x1800d37b1  mov     rdi, [rsp+2D0h+var_260]
0x1800d37b6  test    eax, eax
0x1800d37b8  js      loc_1800D3C8E
0x1800d37be  mov     rax, [rbp+1D0h+var_238]
0x1800d37c2  mov     [rax], rdi
0x1800d37c5  test    byte ptr [rsi+3], 10h
0x1800d37c9  jnz     loc_1800D4168
0x1800d37cf  xor     r15d, r15d
0x1800d37d2  mov     ebx, 4
0x1800d37d7  test    r14, r14
0x1800d37da  jnz     loc_1800D3D6D
0x1800d37e0  test    rdi, rdi
0x1800d37e3  jz      short loc_1800D3807
0x1800d37e5  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d37ea  lea     r9, RtlpDisableHeapLookaside
0x1800d37f1  mov     r8d, ebx
0x1800d37f4  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d37f8  lea     rdx, aDisableheaploo; "DisableHeapLookaside"
0x1800d37ff  mov     rcx, rdi
0x1800d3802  call    RtlQueryImageFileKeyOption
0x1800d3807  test    r14, r14
0x1800d380a  jnz     loc_1800D3DA6
0x1800d3810  test    rdi, rdi
0x1800d3813  jz      short loc_1800D383A
0x1800d3815  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d381a  lea     r9, [rsp+2D0h+var_288]
0x1800d381f  mov     r8d, ebx
0x1800d3822  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d3826  lea     rdx, aFrontendheapde; "FrontEndHeapDebugOptions"
0x1800d382d  mov     rcx, rdi
0x1800d3830  call    RtlQueryImageFileKeyOption
0x1800d3835  mov     r12d, [rsp+2D0h+var_288]
0x1800d383a  test    r14, r14
0x1800d383d  jnz     loc_1800D3DE8
0x1800d3843  test    rdi, rdi
0x1800d3846  jz      short loc_1800D386F
0x1800d3848  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d384d  lea     r9, [rsp+2D0h+var_270]
0x1800d3852  mov     r8d, 0Bh
0x1800d3858  mov     dword ptr [rsp+2D0h+Format], 8
0x1800d3860  lea     rdx, aHeapfeatures; "HeapFeatures"
0x1800d3867  mov     rcx, rdi
0x1800d386a  call    RtlQueryImageFileKeyOption
0x1800d386f  cmp     [rsp+2D0h+var_270], r15
0x1800d3874  jnz     loc_1800D41B3
0x1800d387a  test    r14, r14
0x1800d387d  jnz     loc_1800D3E2F
0x1800d3883  test    rdi, rdi
0x1800d3886  jz      short loc_1800D38AA
0x1800d3888  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d388d  lea     r9, RtlpShutdownProcessFlags
0x1800d3894  mov     r8d, ebx
0x1800d3897  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d389b  lea     rdx, aShutdownflags; "ShutdownFlags"
0x1800d38a2  mov     rcx, rdi
0x1800d38a5  call    RtlQueryImageFileKeyOption
0x1800d38aa  test    r14, r14
0x1800d38ad  jnz     loc_1800D3E68
0x1800d38b3  test    rdi, rdi
0x1800d38b6  jz      short loc_1800D38D8
0x1800d38b8  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d38bd  lea     r9, [rsp+2D0h+var_290]
0x1800d38c2  mov     r8d, ebx
0x1800d38c5  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d38c9  lea     rdx, aUnloadeventtra; "UnloadEventTraceDepth"
0x1800d38d0  mov     rcx, rdi
0x1800d38d3  call    RtlQueryImageFileKeyOption
0x1800d38d8  mov     eax, [rsp+2D0h+var_290]
0x1800d38dc  test    eax, eax
0x1800d38de  jnz     loc_1800D41F0
0x1800d38e4  mov     [rsp+2D0h+var_290], r15d
0x1800d38e9  test    r14, r14
0x1800d38ec  jnz     loc_1800D3EA8
0x1800d38f2  test    rdi, rdi
0x1800d38f5  jz      short loc_1800D3917
0x1800d38f7  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d38fc  lea     r9, [rsp+2D0h+var_290]
0x1800d3901  mov     r8d, ebx
0x1800d3904  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d3908  lea     rdx, aMaxloaderthrea; "MaxLoaderThreads"
0x1800d390f  mov     rcx, rdi
0x1800d3912  call    RtlQueryImageFileKeyOption
0x1800d3917  mov     ecx, [rsp+2D0h+var_290]
0x1800d391b  test    ecx, ecx
0x1800d391d  jnz     loc_1800D41FB
0x1800d3923  mov     [rsp+2D0h+var_290], r15d
0x1800d3928  test    r14, r14
0x1800d392b  jnz     loc_1800D3EE8
0x1800d3931  test    rdi, rdi
0x1800d3934  jz      short loc_1800D3956
0x1800d3936  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d393b  lea     r9, [rsp+2D0h+var_290]
0x1800d3940  mov     r8d, ebx
0x1800d3943  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d3947  lea     rdx, aUseimpersonate; "UseImpersonatedDeviceMap"
0x1800d394e  mov     rcx, rdi
0x1800d3951  call    RtlQueryImageFileKeyOption
0x1800d3956  cmp     [rsp+2D0h+var_290], r15d
0x1800d395b  jnz     loc_1800D420A
0x1800d3961  mov     [rsp+2D0h+var_290], r15d
0x1800d3966  test    r14, r14
0x1800d3969  jnz     loc_1800D3F28
0x1800d396f  test    rdi, rdi
0x1800d3972  jz      short loc_1800D3994
0x1800d3974  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d3979  lea     r9, [rsp+2D0h+var_290]
0x1800d397e  mov     r8d, ebx
0x1800d3981  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d3985  lea     rdx, aTracingflags; "TracingFlags"
0x1800d398c  mov     rcx, rdi
0x1800d398f  call    RtlQueryImageFileKeyOption
0x1800d3994  mov     eax, [rsp+2D0h+var_290]
0x1800d3998  test    eax, eax
0x1800d399a  jnz     loc_1800D4216
0x1800d39a0  mov     [rsp+2D0h+var_290], r15d
0x1800d39a5  test    r14, r14
0x1800d39a8  jnz     loc_1800D3F68
0x1800d39ae  test    rdi, rdi
0x1800d39b1  jz      short loc_1800D39F0
0x1800d39b3  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d39b8  lea     r9, [rsp+2D0h+var_290]
0x1800d39bd  mov     r8d, ebx
0x1800d39c0  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d39c4  lea     rdx, aRaiseexception; "RaiseExceptionOnPossibleDeadlock"
0x1800d39cb  mov     rcx, rdi
0x1800d39ce  call    RtlQueryImageFileKeyOption
0x1800d39d3  mov     ecx, 80000000h
0x1800d39d8  mov     edx, eax
0x1800d39da  add     eax, ecx
0x1800d39dc  test    ecx, eax
0x1800d39de  jnz     short loc_1800D39E8
0x1800d39e0  cmp     edx, 80000005h
0x1800d39e6  jnz     short loc_1800D39F0
0x1800d39e8  test    edx, edx
0x1800d39ea  jns     loc_1800D4222
0x1800d39f0  mov     [rsp+2D0h+var_290], r15d
0x1800d39f5  test    r14, r14
0x1800d39f8  jnz     loc_1800D3FAD
0x1800d39fe  test    rdi, rdi
0x1800d3a01  jz      short loc_1800D3A40
0x1800d3a03  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d3a08  lea     r9, [rsp+2D0h+var_290]
0x1800d3a0d  mov     r8d, ebx
0x1800d3a10  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d3a14  lea     rdx, aLegacydosdevic; "LegacyDosDevicePaths"
0x1800d3a1b  mov     rcx, rdi
0x1800d3a1e  call    RtlQueryImageFileKeyOption
0x1800d3a23  mov     ecx, 80000000h
0x1800d3a28  mov     edx, eax
0x1800d3a2a  add     eax, ecx
0x1800d3a2c  test    ecx, eax
0x1800d3a2e  jnz     short loc_1800D3A38
0x1800d3a30  cmp     edx, 80000005h
0x1800d3a36  jnz     short loc_1800D3A40
0x1800d3a38  test    edx, edx
0x1800d3a3a  jns     loc_1800D4233
0x1800d3a40  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d3a45  lea     r9, [rsp+2D0h+var_290]
0x1800d3a4a  mov     r8d, ebx
0x1800d3a4d  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d3a51  lea     rdx, aCfgoptions; "CFGOptions"
0x1800d3a58  mov     [rsp+2D0h+var_290], r15d
0x1800d3a5d  mov     rcx, rdi
0x1800d3a60  call    RtlQueryImageFileKeyOption
0x1800d3a65  test    eax, eax
0x1800d3a67  jns     loc_1800D4241
0x1800d3a6d  test    byte ptr [rsi+3], 1
0x1800d3a71  jnz     loc_1800D4269
0x1800d3a77  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800d3a7c  lea     r9, [rsp+2D0h+var_290]
0x1800d3a81  mov     r8d, ebx
0x1800d3a84  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800d3a88  lea     rdx, aMinimumstackco; "MinimumStackCommitInBytes"
0x1800d3a8f  mov     rcx, rdi
0x1800d3a92  call    RtlQueryImageFileKeyOption
0x1800d3a97  mov     eax, [rsp+2D0h+var_290]
0x1800d3a9b  cmp     [rsi+318h], rax
0x1800d3aa2  jb      loc_1800D40D1
0x1800d3aa8  lea     r13, off_180170F00; "BreakOnInitializeProcessFailure"
0x1800d3aaf  xor     ebx, ebx
0x1800d3ab1  mov     [rsp+2D0h+var_290], ebx
0x1800d3ab5  lea     r9, [rsp+2D0h+var_290]
0x1800d3aba  mov     eax, 4
0x1800d3abf  mov     qword ptr [rsp+2D0h+ArgList], 0
0x1800d3ac8  mov     rbx, r15
0x1800d3acb  mov     dword ptr [rsp+2D0h+Format], eax
0x1800d3acf  add     rbx, rbx
0x1800d3ad2  mov     r8d, eax
0x1800d3ad5  mov     rcx, rdi
0x1800d3ad8  mov     rdx, [r13+rbx*8+0]
0x1800d3add  call    RtlQueryImageFileKeyOption
0x1800d3ae2  mov     rax, [r13+rbx*8+8]
0x1800d3ae7  mov     cl, 1
0x1800d3ae9  xor     ebx, ebx
0x1800d3aeb  cmp     [rsp+2D0h+var_290], ebx
0x1800d3aef  jnz     short loc_1800D3AF3
0x1800d3af1  mov     cl, bl
0x1800d3af3  inc     r15
0x1800d3af6  mov     [rax], cl
0x1800d3af8  cmp     r15, 3
0x1800d3afc  jnz     short loc_1800D3AB1
0x1800d3afe  mov     r15d, 4
0x1800d3b04  mov     qword ptr [rsp+2D0h+ArgList], rbx
0x1800d3b09  mov     r8d, r15d
0x1800d3b0c  mov     [rsp+2D0h+var_290], ebx
0x1800d3b10  lea     r9, [rsp+2D0h+var_290]
0x1800d3b15  mov     dword ptr [rsp+2D0h+Format], r15d
0x1800d3b1a  lea     rdx, aMaxdeadactivat; "MaxDeadActivationContexts"
0x1800d3b21  mov     rcx, rdi
0x1800d3b24  call    RtlQueryImageFileKeyOption
0x1800d3b29  mov     eax, [rsp+2D0h+var_290]
0x1800d3b2d  mov     r13, rbx
0x1800d3b30  test    eax, eax
0x1800d3b32  jnz     loc_1800D42C9
0x1800d3b38  mov     qword ptr [rsp+2D0h+ArgList], rbx
0x1800d3b3d  lea     r9, [rsp+2D0h+var_290]
0x1800d3b42  mov     r8d, r15d
0x1800d3b45  mov     dword ptr [rsp+2D0h+Format], r15d
0x1800d3b4a  lea     rdx, aImageexpansion; "ImageExpansionMitigation"
0x1800d3b51  mov     [rsp+2D0h+var_290], ebx
0x1800d3b55  mov     rcx, rdi
0x1800d3b58  call    RtlQueryImageFileKeyOption
0x1800d3b5d  test    eax, eax
0x1800d3b5f  jns     loc_1800D42D4
0x1800d3b65  mov     r15d, [rsi+0BCh]
0x1800d3b6c  shr     r15d, 8
0x1800d3b70  and     r15b, 1
0x1800d3b74  test    r14, r14
0x1800d3b77  jnz     loc_1800D3FF2
0x1800d3b7d  test    rdi, rdi
0x1800d3b80  jz      short loc_1800D3BC7
0x1800d3b82  mov     eax, 4
0x1800d3b87  mov     qword ptr [rsp+2D0h+ArgList], rbx
0x1800d3b8c  mov     r8d, eax
0x1800d3b8f  mov     dword ptr [rsp+2D0h+Format], eax
0x1800d3b93  lea     r9, [rsp+2D0h+var_28C]
0x1800d3b98  mov     rcx, rdi
0x1800d3b9b  lea     rdx, aGlobalflag; "GlobalFlag"
0x1800d3ba2  call    RtlQueryImageFileKeyOption
0x1800d3ba7  mov     ecx, 80000000h
0x1800d3bac  mov     edx, eax
0x1800d3bae  add     eax, ecx
0x1800d3bb0  test    ecx, eax
0x1800d3bb2  jnz     short loc_1800D3BBC
0x1800d3bb4  cmp     edx, 80000005h
0x1800d3bba  jnz     short loc_1800D3BC7
0x1800d3bbc  mov     r13, rdi
0x1800d3bbf  test    edx, edx
0x1800d3bc1  jns     loc_1800D42E3
  ... truncated ...
```
