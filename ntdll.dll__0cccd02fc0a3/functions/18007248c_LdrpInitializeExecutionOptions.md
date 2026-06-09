# LdrpInitializeExecutionOptions

- ea: `0x18007248c`
- end: `0x1800731e6`
- name: `LdrpInitializeExecutionOptions`
- size: `3418`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d6508`

## callees

- `0x18000aab0`
- `0x18001eb80`
- `0x180066cf0`
- `0x180066da0`
- `0x180071dd4`
- `0x180071ff8`
- `0x180072290`
- `0x1800723e8`
- `0x18007248c`
- `0x18007324c`
- `0x1800733c0`
- `0x1800737f8`
- `0x1800740f0`
- `0x1800741c8`
- `0x1800743c0`
- `0x18008e6a0`
- `0x180091224`
- `0x1800c0420`
- `0x1800eba3c`
- `0x180104f40`
- `0x180121ca4`
- `0x18015e4b0`
- `0x18015e510`
- `0x180162000`

## string_xrefs

- `0x1800727bc`: `LegacyDosDevicePaths`
- `0x180072d66`: `LegacyDosDevicePaths`
- `0x1800726ef`: `UseImpersonatedDeviceMap`
- `0x180072ca1`: `UseImpersonatedDeviceMap`
- `0x1800726b0`: `MaxLoaderThreads`
- `0x180072c61`: `MaxLoaderThreads`
- `0x1800725a0`: `DisableHeapLookaside`
- `0x180072b28`: `DisableHeapLookaside`
- `0x180072830`: `MinimumStackCommitInBytes`

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
          v66[2] = &qword_180171E40;
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
          RtlQueryImageFileKeyOption(v9, (&off_180170810)[2 * v14], 4, &v50, 4, 0);
          v17 = (bool *)*(&off_180170810 + 2 * v14++ + 1);
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
        10674,
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
        if ( (int)RtlQueryEnvironmentVariable_U(*(_QWORD *)(v42 + 128), &qword_180171DB0, v61) < 0
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
0x18007248c  push    rbp
0x18007248e  push    rbx
0x18007248f  push    rsi
0x180072490  push    rdi
0x180072491  push    r12
0x180072493  push    r13
0x180072495  push    r14
0x180072497  push    r15
0x180072499  lea     rbp, [rsp-198h]
0x1800724a1  sub     rsp, 298h
0x1800724a8  mov     rax, cs:__security_cookie
0x1800724af  xor     rax, rsp
0x1800724b2  mov     [rbp+1D0h+var_50], rax
0x1800724b9  mov     rax, [rbp+1D0h+arg_20]
0x1800724c0  xorps   xmm0, xmm0
0x1800724c3  mov     [rbp+1D0h+var_250], rcx
0x1800724c7  mov     rsi, rdx
0x1800724ca  mov     rcx, [rbp+1D0h+arg_28]
0x1800724d1  mov     bl, 1
0x1800724d3  mov     [rbp+1D0h+var_228], rcx
0x1800724d7  xor     ecx, ecx
0x1800724d9  mov     [r9], rcx
0x1800724dc  mov     r15b, cl
0x1800724df  mov     [rax], rcx
0x1800724e2  mov     edi, ecx
0x1800724e4  mov     [rbp+1D0h+var_238], r9
0x1800724e8  mov     r12d, ecx
0x1800724eb  mov     [rbp+1D0h+var_248], r8
0x1800724ef  mov     r14d, ecx
0x1800724f2  mov     [rbp+1D0h+var_230], rax
0x1800724f6  mov     r13d, ecx
0x1800724f9  mov     [rsp+2D0h+var_260], rcx
0x1800724fe  mov     [rsp+2D0h+Handle], rcx
0x180072503  mov     [rsp+2D0h+var_288], ecx
0x180072507  mov     [rsp+2D0h+var_284], 0FFFFFFFFh
0x18007250f  mov     [rsp+2D0h+var_258], rcx
0x180072514  mov     [rsp+2D0h+var_270], rcx
0x180072519  mov     [rsp+2D0h+var_268], rcx
0x18007251e  movups  xmmword ptr [rbp+1D0h+DestinationString.Length], xmm0
0x180072522  mov     [rsp+2D0h+var_28C], ecx
0x180072526  mov     [rsp+2D0h+var_290], ecx
0x18007252a  mov     [rsp+2D0h+var_280], ecx
0x18007252e  call    LdrpInitializeCriticalSectionExceptionGlobalMitigation
0x180072533  mov     rax, [rsi+20h]
0x180072537  test    dword ptr [rax+8], 4000h
0x18007253e  jnz     loc_180072A36
0x180072544  mov     rcx, [rbp+1D0h+var_250]
0x180072548  lea     r9, [rsp+2D0h+var_260]
0x18007254d  xor     r8d, r8d
0x180072550  lea     edx, [r13+9]
0x180072554  call    RtlpOpenImageFileOptionsKeyEx
0x180072559  mov     rdi, [rsp+2D0h+var_260]
0x18007255e  test    eax, eax
0x180072560  js      loc_180072A36
0x180072566  mov     rax, [rbp+1D0h+var_238]
0x18007256a  mov     [rax], rdi
0x18007256d  test    byte ptr [rsi+3], 10h
0x180072571  jnz     loc_180072F10
0x180072577  xor     r15d, r15d
0x18007257a  mov     ebx, 4
0x18007257f  test    r14, r14
0x180072582  jnz     loc_180072B15
0x180072588  test    rdi, rdi
0x18007258b  jz      short loc_1800725AF
0x18007258d  mov     qword ptr [rsp+2D0h+ArgList], r15
0x180072592  lea     r9, RtlpDisableHeapLookaside
0x180072599  mov     r8d, ebx
0x18007259c  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800725a0  lea     rdx, aDisableheaploo; "DisableHeapLookaside"
0x1800725a7  mov     rcx, rdi
0x1800725aa  call    RtlQueryImageFileKeyOption
0x1800725af  test    r14, r14
0x1800725b2  jnz     loc_180072B4E
0x1800725b8  test    rdi, rdi
0x1800725bb  jz      short loc_1800725E2
0x1800725bd  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800725c2  lea     r9, [rsp+2D0h+var_288]
0x1800725c7  mov     r8d, ebx
0x1800725ca  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800725ce  lea     rdx, aFrontendheapde; "FrontEndHeapDebugOptions"
0x1800725d5  mov     rcx, rdi
0x1800725d8  call    RtlQueryImageFileKeyOption
0x1800725dd  mov     r12d, [rsp+2D0h+var_288]
0x1800725e2  test    r14, r14
0x1800725e5  jnz     loc_180072B90
0x1800725eb  test    rdi, rdi
0x1800725ee  jz      short loc_180072617
0x1800725f0  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800725f5  lea     r9, [rsp+2D0h+var_270]
0x1800725fa  mov     r8d, 0Bh
0x180072600  mov     dword ptr [rsp+2D0h+Format], 8
0x180072608  lea     rdx, aHeapfeatures; "HeapFeatures"
0x18007260f  mov     rcx, rdi
0x180072612  call    RtlQueryImageFileKeyOption
0x180072617  cmp     [rsp+2D0h+var_270], r15
0x18007261c  jnz     loc_180072F5B
0x180072622  test    r14, r14
0x180072625  jnz     loc_180072BD7
0x18007262b  test    rdi, rdi
0x18007262e  jz      short loc_180072652
0x180072630  mov     qword ptr [rsp+2D0h+ArgList], r15
0x180072635  lea     r9, RtlpShutdownProcessFlags
0x18007263c  mov     r8d, ebx
0x18007263f  mov     dword ptr [rsp+2D0h+Format], ebx
0x180072643  lea     rdx, aShutdownflags; "ShutdownFlags"
0x18007264a  mov     rcx, rdi
0x18007264d  call    RtlQueryImageFileKeyOption
0x180072652  test    r14, r14
0x180072655  jnz     loc_180072C10
0x18007265b  test    rdi, rdi
0x18007265e  jz      short loc_180072680
0x180072660  mov     qword ptr [rsp+2D0h+ArgList], r15
0x180072665  lea     r9, [rsp+2D0h+var_290]
0x18007266a  mov     r8d, ebx
0x18007266d  mov     dword ptr [rsp+2D0h+Format], ebx
0x180072671  lea     rdx, aUnloadeventtra; "UnloadEventTraceDepth"
0x180072678  mov     rcx, rdi
0x18007267b  call    RtlQueryImageFileKeyOption
0x180072680  mov     eax, [rsp+2D0h+var_290]
0x180072684  test    eax, eax
0x180072686  jnz     loc_180072F98
0x18007268c  mov     [rsp+2D0h+var_290], r15d
0x180072691  test    r14, r14
0x180072694  jnz     loc_180072C50
0x18007269a  test    rdi, rdi
0x18007269d  jz      short loc_1800726BF
0x18007269f  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800726a4  lea     r9, [rsp+2D0h+var_290]
0x1800726a9  mov     r8d, ebx
0x1800726ac  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800726b0  lea     rdx, aMaxloaderthrea; "MaxLoaderThreads"
0x1800726b7  mov     rcx, rdi
0x1800726ba  call    RtlQueryImageFileKeyOption
0x1800726bf  mov     ecx, [rsp+2D0h+var_290]
0x1800726c3  test    ecx, ecx
0x1800726c5  jnz     loc_180072FA3
0x1800726cb  mov     [rsp+2D0h+var_290], r15d
0x1800726d0  test    r14, r14
0x1800726d3  jnz     loc_180072C90
0x1800726d9  test    rdi, rdi
0x1800726dc  jz      short loc_1800726FE
0x1800726de  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800726e3  lea     r9, [rsp+2D0h+var_290]
0x1800726e8  mov     r8d, ebx
0x1800726eb  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800726ef  lea     rdx, aUseimpersonate; "UseImpersonatedDeviceMap"
0x1800726f6  mov     rcx, rdi
0x1800726f9  call    RtlQueryImageFileKeyOption
0x1800726fe  cmp     [rsp+2D0h+var_290], r15d
0x180072703  jnz     loc_180072FB2
0x180072709  mov     [rsp+2D0h+var_290], r15d
0x18007270e  test    r14, r14
0x180072711  jnz     loc_180072CD0
0x180072717  test    rdi, rdi
0x18007271a  jz      short loc_18007273C
0x18007271c  mov     qword ptr [rsp+2D0h+ArgList], r15
0x180072721  lea     r9, [rsp+2D0h+var_290]
0x180072726  mov     r8d, ebx
0x180072729  mov     dword ptr [rsp+2D0h+Format], ebx
0x18007272d  lea     rdx, aTracingflags; "TracingFlags"
0x180072734  mov     rcx, rdi
0x180072737  call    RtlQueryImageFileKeyOption
0x18007273c  mov     eax, [rsp+2D0h+var_290]
0x180072740  test    eax, eax
0x180072742  jnz     loc_180072FBE
0x180072748  mov     [rsp+2D0h+var_290], r15d
0x18007274d  test    r14, r14
0x180072750  jnz     loc_180072D10
0x180072756  test    rdi, rdi
0x180072759  jz      short loc_180072798
0x18007275b  mov     qword ptr [rsp+2D0h+ArgList], r15
0x180072760  lea     r9, [rsp+2D0h+var_290]
0x180072765  mov     r8d, ebx
0x180072768  mov     dword ptr [rsp+2D0h+Format], ebx
0x18007276c  lea     rdx, aRaiseexception; "RaiseExceptionOnPossibleDeadlock"
0x180072773  mov     rcx, rdi
0x180072776  call    RtlQueryImageFileKeyOption
0x18007277b  mov     ecx, 80000000h
0x180072780  mov     edx, eax
0x180072782  add     eax, ecx
0x180072784  test    ecx, eax
0x180072786  jnz     short loc_180072790
0x180072788  cmp     edx, 80000005h
0x18007278e  jnz     short loc_180072798
0x180072790  test    edx, edx
0x180072792  jns     loc_180072FCA
0x180072798  mov     [rsp+2D0h+var_290], r15d
0x18007279d  test    r14, r14
0x1800727a0  jnz     loc_180072D55
0x1800727a6  test    rdi, rdi
0x1800727a9  jz      short loc_1800727E8
0x1800727ab  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800727b0  lea     r9, [rsp+2D0h+var_290]
0x1800727b5  mov     r8d, ebx
0x1800727b8  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800727bc  lea     rdx, aLegacydosdevic; "LegacyDosDevicePaths"
0x1800727c3  mov     rcx, rdi
0x1800727c6  call    RtlQueryImageFileKeyOption
0x1800727cb  mov     ecx, 80000000h
0x1800727d0  mov     edx, eax
0x1800727d2  add     eax, ecx
0x1800727d4  test    ecx, eax
0x1800727d6  jnz     short loc_1800727E0
0x1800727d8  cmp     edx, 80000005h
0x1800727de  jnz     short loc_1800727E8
0x1800727e0  test    edx, edx
0x1800727e2  jns     loc_180072FDB
0x1800727e8  mov     qword ptr [rsp+2D0h+ArgList], r15
0x1800727ed  lea     r9, [rsp+2D0h+var_290]
0x1800727f2  mov     r8d, ebx
0x1800727f5  mov     dword ptr [rsp+2D0h+Format], ebx
0x1800727f9  lea     rdx, aCfgoptions; "CFGOptions"
0x180072800  mov     [rsp+2D0h+var_290], r15d
0x180072805  mov     rcx, rdi
0x180072808  call    RtlQueryImageFileKeyOption
0x18007280d  test    eax, eax
0x18007280f  jns     loc_180072FE9
0x180072815  test    byte ptr [rsi+3], 1
0x180072819  jnz     loc_180073011
0x18007281f  mov     qword ptr [rsp+2D0h+ArgList], r15
0x180072824  lea     r9, [rsp+2D0h+var_290]
0x180072829  mov     r8d, ebx
0x18007282c  mov     dword ptr [rsp+2D0h+Format], ebx
0x180072830  lea     rdx, aMinimumstackco; "MinimumStackCommitInBytes"
0x180072837  mov     rcx, rdi
0x18007283a  call    RtlQueryImageFileKeyOption
0x18007283f  mov     eax, [rsp+2D0h+var_290]
0x180072843  cmp     [rsi+318h], rax
0x18007284a  jb      loc_180072E79
0x180072850  lea     r13, off_180170810; "BreakOnInitializeProcessFailure"
0x180072857  xor     ebx, ebx
0x180072859  mov     [rsp+2D0h+var_290], ebx
0x18007285d  lea     r9, [rsp+2D0h+var_290]
0x180072862  mov     eax, 4
0x180072867  mov     qword ptr [rsp+2D0h+ArgList], 0
0x180072870  mov     rbx, r15
0x180072873  mov     dword ptr [rsp+2D0h+Format], eax
0x180072877  add     rbx, rbx
0x18007287a  mov     r8d, eax
0x18007287d  mov     rcx, rdi
0x180072880  mov     rdx, [r13+rbx*8+0]
0x180072885  call    RtlQueryImageFileKeyOption
0x18007288a  mov     rax, [r13+rbx*8+8]
0x18007288f  mov     cl, 1
0x180072891  xor     ebx, ebx
0x180072893  cmp     [rsp+2D0h+var_290], ebx
0x180072897  jnz     short loc_18007289B
0x180072899  mov     cl, bl
0x18007289b  inc     r15
0x18007289e  mov     [rax], cl
0x1800728a0  cmp     r15, 3
0x1800728a4  jnz     short loc_180072859
0x1800728a6  mov     r15d, 4
0x1800728ac  mov     qword ptr [rsp+2D0h+ArgList], rbx
0x1800728b1  mov     r8d, r15d
0x1800728b4  mov     [rsp+2D0h+var_290], ebx
0x1800728b8  lea     r9, [rsp+2D0h+var_290]
0x1800728bd  mov     dword ptr [rsp+2D0h+Format], r15d
0x1800728c2  lea     rdx, aMaxdeadactivat; "MaxDeadActivationContexts"
0x1800728c9  mov     rcx, rdi
0x1800728cc  call    RtlQueryImageFileKeyOption
0x1800728d1  mov     eax, [rsp+2D0h+var_290]
0x1800728d5  mov     r13, rbx
0x1800728d8  test    eax, eax
0x1800728da  jnz     loc_180073071
0x1800728e0  mov     qword ptr [rsp+2D0h+ArgList], rbx
0x1800728e5  lea     r9, [rsp+2D0h+var_290]
0x1800728ea  mov     r8d, r15d
0x1800728ed  mov     dword ptr [rsp+2D0h+Format], r15d
0x1800728f2  lea     rdx, aImageexpansion; "ImageExpansionMitigation"
0x1800728f9  mov     [rsp+2D0h+var_290], ebx
0x1800728fd  mov     rcx, rdi
0x180072900  call    RtlQueryImageFileKeyOption
0x180072905  test    eax, eax
0x180072907  jns     loc_18007307C
0x18007290d  mov     r15d, [rsi+0BCh]
0x180072914  shr     r15d, 8
0x180072918  and     r15b, 1
0x18007291c  test    r14, r14
0x18007291f  jnz     loc_180072D9A
0x180072925  test    rdi, rdi
0x180072928  jz      short loc_18007296F
0x18007292a  mov     eax, 4
0x18007292f  mov     qword ptr [rsp+2D0h+ArgList], rbx
0x180072934  mov     r8d, eax
0x180072937  mov     dword ptr [rsp+2D0h+Format], eax
0x18007293b  lea     r9, [rsp+2D0h+var_28C]
0x180072940  mov     rcx, rdi
0x180072943  lea     rdx, aGlobalflag; "GlobalFlag"
0x18007294a  call    RtlQueryImageFileKeyOption
0x18007294f  mov     ecx, 80000000h
0x180072954  mov     edx, eax
0x180072956  add     eax, ecx
0x180072958  test    ecx, eax
0x18007295a  jnz     short loc_180072964
0x18007295c  cmp     edx, 80000005h
0x180072962  jnz     short loc_18007296F
0x180072964  mov     r13, rdi
0x180072967  test    edx, edx
0x180072969  jns     loc_18007308B
  ... truncated ...
```
