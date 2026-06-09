# WdiHandleInstance(void *,WDI_DIAGNOSTIC_MODULE_REQUEST)

- ea: `0x180004940`
- end: `0x180005041`
- name: `?WdiHandleInstance@@YAJPEAXW4WDI_DIAGNOSTIC_MODULE_REQUEST@@@Z`
- size: `1793`
- prototype: `__int64 __fastcall(void *, __int64)`
- caller_count: `0`
- callee_count: `21`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180001ff4`
- `0x1800040d4`
- `0x180004178`
- `0x18000438c`
- `0x180004694`
- `0x180004940`
- `0x180005048`
- `0x18000506c`
- `0x180005350`
- `0x180009a74`
- `0x180018660`
- `0x1800188c8`
- `0x180018ae4`
- `0x18001b094`
- `0x18001b898`
- `0x18001bb00`
- `0x18001bfc0`
- `0x18001cc54`
- `0x18002c7f6`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004ab3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004eab`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004f41`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ffa`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ab3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004eab`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004f41`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ffa`
- `KERNEL32!EnterCriticalSection` at `0x180004b01`
- `KERNEL32!EnterCriticalSection` at `0x180004bd7`
- `KERNEL32!EnterCriticalSection` at `0x180004f2a`
- `KERNEL32!EnterCriticalSection` at `0x180004b01`
- `KERNEL32!EnterCriticalSection` at `0x180004bd7`
- `KERNEL32!EnterCriticalSection` at `0x180004f2a`
- `KERNEL32!LeaveCriticalSection` at `0x180004b6b`
- `KERNEL32!LeaveCriticalSection` at `0x180004ea2`
- `KERNEL32!LeaveCriticalSection` at `0x180004f52`
- `KERNEL32!LeaveCriticalSection` at `0x180004ff1`
- `KERNEL32!LeaveCriticalSection` at `0x180004b6b`
- `KERNEL32!LeaveCriticalSection` at `0x180004ea2`
- `KERNEL32!LeaveCriticalSection` at `0x180004f52`
- `KERNEL32!LeaveCriticalSection` at `0x180004ff1`
- `wdi!WdiGetParameterData` at `0x180004c16`
- `wdi!WdiGetParameterData` at `0x180004c16`
- `wdi!WdiGetInstanceId` at `0x180004a0e`
- `wdi!WdiGetInstanceId` at `0x180004a0e`
- `wdi!WdiGetScenarioInfo` at `0x180004a27`
- `wdi!WdiGetScenarioInfo` at `0x180004a27`
- `wdi!WdiSetProblemDetectionResult` at `0x18000501b`
- `wdi!WdiSetProblemDetectionResult` at `0x18000501b`
- `wdi!WdiSetResolution` at `0x180004fdb`
- `wdi!WdiSetResolution` at `0x180004fdb`
- `wdi!WdiGetParameterByName` at `0x180004bf1`
- `wdi!WdiGetParameterByName` at `0x180004d35`
- `wdi!WdiGetParameterByName` at `0x180004bf1`
- `wdi!WdiGetParameterByName` at `0x180004d35`
- `wdi!WdiAddParameter` at `0x180004dcb`
- `wdi!WdiAddParameter` at `0x180004e56`
- `wdi!WdiAddParameter` at `0x180004e87`
- `wdi!WdiAddParameter` at `0x180004dcb`
- `wdi!WdiAddParameter` at `0x180004e56`
- `wdi!WdiAddParameter` at `0x180004e87`
- `wdi!WdiGetDiagnosticModuleId` at `0x1800049f9`
- `wdi!WdiGetDiagnosticModuleId` at `0x1800049f9`

## string_xrefs

- `0x180004cd3`: `ValidateRepair`
- `0x180004cf2`: `SelectedRepairGUID`
- `0x180004e13`: `Client does not support model with separate Repair and Validate call, running Validate as part of Repair call.`
- `0x180004d28`: `SplitRepairAndValidate`

## pseudocode

```c
__int64 __fastcall WdiHandleInstance(void *a1, __int64 a2)
{
  int v2; // ebx
  NetworkDiagnosticsEngine *v4; // r8
  __int64 v5; // rbx
  NetworkIncident *v6; // rcx
  __int64 v7; // rcx
  __int64 i; // rax
  __int64 result; // rax
  int ParameterData; // edi
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  NetworkDiagnosticsEngine *v15; // rcx
  struct DiagnosticsClient *v16; // rbx
  struct DiagnosticsClient *v17; // rcx
  struct DiagnosticsClient *v18; // r14
  NetworkDiagnosticsEngine *v19; // rbx
  NetworkDiagnosticsEngine **v20; // rax
  NetworkDiagnosticsEngine *v21; // rcx
  NetworkIncident *v22; // rbx
  unsigned int v23; // edx
  struct DiagnosticsClient *v24; // r14
  NetworkDiagnosticsEngine *v25; // rsi
  __int64 v26; // rax
  struct NetworkIncident *v27; // rdx
  int ParameterByName; // esi
  NetworkDiagnosticsEngine *v29; // rcx
  int TraceFile; // eax
  signed int v31; // ebx
  signed int v32; // eax
  NetworkDiagnosticsEngine *v33; // rcx
  struct DiagnosticsClient *v34; // rbx
  NetworkDiagnosticsEngine *v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rcx
  __int64 v39; // r8
  int v40; // eax
  NetworkDiagnosticsEngine *v41; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v42; // [rsp+38h] [rbp-81h] BYREF
  unsigned int v43; // [rsp+40h] [rbp-79h] BYREF
  struct DiagnosticsClient *v44; // [rsp+48h] [rbp-71h] BYREF
  int v45; // [rsp+50h] [rbp-69h] BYREF
  unsigned __int8 v46[4]; // [rsp+54h] [rbp-65h] BYREF
  __int64 v47; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v48; // [rsp+60h] [rbp-59h] BYREF
  void *v49; // [rsp+68h] [rbp-51h] BYREF
  int v50; // [rsp+70h] [rbp-49h]
  __int64 v51; // [rsp+78h] [rbp-41h]
  __int64 v52; // [rsp+80h] [rbp-39h]
  __int128 Buf2; // [rsp+88h] [rbp-31h] BYREF
  __int128 v54; // [rsp+98h] [rbp-21h] BYREF
  __int128 v55; // [rsp+A8h] [rbp-11h] BYREF
  __int128 v56; // [rsp+B8h] [rbp-1h] BYREF
  __int128 Buf1; // [rsp+C8h] [rbp+Fh] BYREF

  v2 = a2;
  v55 = 0;
  v54 = 0;
  v56 = 0;
  v45 = 0;
  if ( a1 || (_DWORD)a2 != 6 )
  {
    result = WdiGetDiagnosticModuleId(a1, &v55);
    if ( (int)result < 0 )
      return result;
    result = WdiGetInstanceId(a1, &v54);
    if ( (int)result < 0 )
      return result;
    result = WdiGetScenarioInfo(a1, &v56, &v45);
    ParameterData = result;
    if ( (int)result < 0 )
      return result;
    if ( v45 )
      return 2147500037LL;
    v11 = v2 - 2;
    if ( !v11 )
      return (unsigned int)WdiSetProblemDetectionResult(a1, 1);
    v12 = v11 - 1;
    if ( !v12 )
    {
      v49 = a1;
      v50 = 0;
      v51 = 0;
      v52 = 0;
      CNDFLanguageUtil::SetThreadLanguage((CNDFLanguageUtil *)&v49);
      v47 = 0;
      v34 = (struct DiagnosticsClient *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
      v44 = v34;
      if ( v34 )
      {
        *(_QWORD *)v34 = &DiagnosticsClient::`vftable';
        *((_QWORD *)v34 + 1) = a1;
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)qword_180041BB8 + 64));
        ParameterData = NetworkDiagnosticsEngine::RegisterClient(v35, v34);
        if ( ParameterData >= 0 )
        {
          if ( (byte_180041BC1 & 4) != 0 )
            McGenEventWrite_EventWriteTransfer(v36, StartNDFDiagnose, v37, 1, &Buf1);
          ParameterData = NetworkDiagnosticsEngine::Diagnose(qword_180041BB8, v34);
          if ( (byte_180041BC1 & 4) != 0 )
            McGenEventWrite_EventWriteTransfer(v38, StopNDFDiagnose, v39, 1, &Buf1);
          if ( ParameterData >= 0 )
          {
            v40 = WdiSetResolution(a1, NetDiagModuleId, 0, 0, 2, v47);
            if ( v40 < 0 )
              ParameterData = v40;
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)qword_180041BB8 + 64));
          operator delete(v34);
        }
        else
        {
          operator delete(v34);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)qword_180041BB8 + 64));
        }
      }
      else
      {
        ParameterData = -2147024882;
      }
      goto LABEL_82;
    }
    v13 = v12 - 1;
    if ( v13 )
    {
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
          return (unsigned int)ParameterData;
        v16 = (struct DiagnosticsClient *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
        v44 = v16;
        if ( v16 )
        {
          *(_QWORD *)v16 = &DiagnosticsClient::`vftable';
          *((_QWORD *)v16 + 1) = a1;
          ParameterData = NetworkDiagnosticsEngine::Cancel(v15, v16);
          v17 = v16;
LABEL_29:
          operator delete(v17);
          return (unsigned int)ParameterData;
        }
      }
      else
      {
        v18 = (struct DiagnosticsClient *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
        v44 = v18;
        if ( v18 )
        {
          *(_QWORD *)v18 = &DiagnosticsClient::`vftable';
          *((_QWORD *)v18 + 1) = a1;
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)qword_180041BB8 + 64));
          ParameterData = (*(__int64 (__fastcall **)(struct DiagnosticsClient *, __int128 *))(*(_QWORD *)v18 + 72LL))(
                            v18,
                            &v54);
          if ( ParameterData >= 0 )
          {
            v19 = qword_180041BB8;
            v20 = (NetworkDiagnosticsEngine **)std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(
                                                 (char *)qword_180041BB8 + 8,
                                                 &v44,
                                                 &v54);
            v21 = *v20;
            if ( *v20 != *((NetworkDiagnosticsEngine **)v19 + 1) )
            {
              v22 = (NetworkIncident *)*((_QWORD *)v21 + 6);
              if ( v22 )
              {
                ParameterData = NetworkDiagnosticsEngine::DeregisterClient(v21, v18);
                if ( ParameterData >= 0 )
                  NetworkIncident::`scalar deleting destructor'(v22, v23);
              }
            }
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)qword_180041BB8 + 64));
          v17 = v18;
          goto LABEL_29;
        }
      }
      return 2147942414LL;
    }
    v49 = a1;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    CNDFLanguageUtil::SetThreadLanguage((CNDFLanguageUtil *)&v49);
    v24 = (struct DiagnosticsClient *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
    v44 = v24;
    if ( !v24 )
    {
      CNDFLanguageUtil::~CNDFLanguageUtil((CNDFLanguageUtil *)&v49);
      return 2147942414LL;
    }
    *(_QWORD *)v24 = &DiagnosticsClient::`vftable';
    *((_QWORD *)v24 + 1) = a1;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)qword_180041BB8 + 64));
    v47 = 0;
    if ( (int)WdiGetParameterByName(a1, 0, L"FeedbackGUID", &v47) >= 0 && v47 )
    {
      Buf2 = 0;
      ParameterData = WdiGetParameterData(v47, &Buf2, 16);
      if ( ParameterData >= 0 )
      {
        Buf1 = 0;
        if ( !memcmp_0(&Buf1, &Buf2, 0x10u) )
        {
          v25 = qword_180041BB8;
          v26 = std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(
                  (char *)qword_180041BB8 + 8,
                  &v48,
                  &v54);
          if ( *(_QWORD *)v26 != *((_QWORD *)v25 + 1) )
          {
            v27 = *(struct NetworkIncident **)(*(_QWORD *)v26 + 48LL);
            if ( v27 )
              NetworkDiagnosticsEngine::SendReport(v25, v27);
          }
          goto LABEL_68;
        }
        goto LABEL_58;
      }
LABEL_68:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)qword_180041BB8 + 64));
      operator delete(v24);
LABEL_82:
      CNDFLanguageUtil::~CNDFLanguageUtil((CNDFLanguageUtil *)&v49);
      return (unsigned int)ParameterData;
    }
    v43 = 0;
    v48 = 0;
    LODWORD(v41) = 0;
    v42 = 0;
    Buf1 = 0;
    *(_DWORD *)v46 = 0;
    GetLastWdiParameter(a1, L"NdfGetTraceFileGuid", (unsigned __int8 *)&Buf1, 0x10u, &v43);
    GetLastWdiParameter(a1, L"ValidateRepair", v46, 4u, &v48);
    GetLastWdiParameter(a1, L"SelectedRepairGUID", 0, 0, (unsigned int *)&v41);
    GetLastWdiParameter(a1, L"FollowUpIncident", 0, 0, &v42);
    v44 = 0;
    ParameterByName = WdiGetParameterByName(*((_QWORD *)v24 + 1), 0, L"SplitRepairAndValidate", &v44);
    if ( v42 <= v43 || v42 <= v48 || v42 <= (unsigned int)v41 )
    {
      if ( v43 > v48 && v43 > (unsigned int)v41 )
      {
        Buf2 = 0;
        HIBYTE(Buf2) = 1;
        if ( !memcmp_0(&Buf2, &Buf1, 0x10u) )
        {
          TraceFile = NetworkDiagnosticsEngine::GetTraceFile(v29, v24);
LABEL_52:
          ParameterData = TraceFile;
          goto LABEL_68;
        }
LABEL_58:
        ParameterData = -2147024809;
        goto LABEL_68;
      }
      if ( v48 > (unsigned int)v41 )
      {
        if ( *(_DWORD *)v46 )
        {
          v31 = NetworkDiagnosticsEngine::Validate((NetworkDiagnosticsEngine *)(unsigned int)v41, v24);
          v43 = v31;
          WdiAddParameter(*((_QWORD *)v24 + 1), 0, L"NDFCallResult", 4, &v43);
          ParameterData = 0;
          if ( v31 >= 0 )
            ParameterData = v31;
          goto LABEL_68;
        }
        goto LABEL_58;
      }
      if ( !(_DWORD)v41 )
      {
        ParameterData = -2147467259;
        goto LABEL_68;
      }
      v32 = NetworkDiagnosticsEngine::Resolve((NetworkDiagnosticsEngine *)(unsigned int)v41, v24);
      ParameterData = v32;
      if ( v32 >= 0 )
      {
        if ( ParameterByName != -2147024809 )
        {
          v42 = v32;
          WdiAddParameter(*((_QWORD *)v24 + 1), 0, L"NDFCallResult", 4, &v42);
          goto LABEL_68;
        }
        (*(void (__fastcall **)(_QWORD, __int64, const wchar_t *))(**(_QWORD **)qword_180041BB8 + 96LL))(
          *(_QWORD *)qword_180041BB8,
          3,
          L"Client does not support model with separate Repair and Validate call, running Validate as part of Repair call.");
        TraceFile = NetworkDiagnosticsEngine::Validate(v33, v24);
        goto LABEL_52;
      }
      if ( ParameterByName == -2147024809 )
        goto LABEL_68;
      LODWORD(v41) = v32;
      WdiAddParameter(*((_QWORD *)v24 + 1), 0, L"NDFCallResult", 4, &v41);
    }
    ParameterData = 0;
    goto LABEL_68;
  }
  v4 = qword_180041BB8;
  if ( qword_180041BB8 )
  {
    v5 = **((_QWORD **)qword_180041BB8 + 1);
    while ( v5 != *((_QWORD *)v4 + 1) )
    {
      v6 = *(NetworkIncident **)(v5 + 48);
      if ( v6 )
      {
        NetworkIncident::Cancel(v6);
        v4 = qword_180041BB8;
      }
      if ( !*(_BYTE *)(v5 + 25) )
      {
        v7 = *(_QWORD *)(v5 + 16);
        if ( *(_BYTE *)(v7 + 25) )
        {
          for ( i = *(_QWORD *)(v5 + 8); !*(_BYTE *)(i + 25) && v5 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
            v5 = i;
        }
        else
        {
          i = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min(
                v7,
                a2,
                v4);
        }
        v5 = i;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180004940  push    rbp
0x180004942  push    rbx
0x180004943  push    rsi
0x180004944  push    rdi
0x180004945  push    r12
0x180004947  push    r14
0x180004949  lea     rbp, [rsp-2Fh]
0x18000494e  sub     rsp, 0E8h
0x180004955  mov     rax, cs:__security_cookie
0x18000495c  xor     rax, rsp
0x18000495f  mov     [rbp+57h+var_38], rax
0x180004963  mov     ebx, edx
0x180004965  mov     rsi, rcx
0x180004968  xorps   xmm0, xmm0
0x18000496b  movups  [rbp+57h+var_68], xmm0
0x18000496f  xorps   xmm1, xmm1
0x180004972  movups  [rbp+57h+var_78], xmm1
0x180004976  movups  [rbp+57h+var_58], xmm0
0x18000497a  xor     r12d, r12d
0x18000497d  mov     [rbp+57h+var_C0], r12d
0x180004981  test    rcx, rcx
0x180004984  jnz     short loc_1800049F5
0x180004986  cmp     edx, 6
0x180004989  jnz     short loc_1800049F5
0x18000498b  mov     r8, cs:qword_180041BB8
0x180004992  test    r8, r8
0x180004995  jz      short loc_1800049EE
0x180004997  mov     rbx, [r8+8]
0x18000499b  mov     rbx, [rbx]
0x18000499e  cmp     rbx, [r8+8]
0x1800049a2  jz      short loc_1800049EE
0x1800049a4  mov     rcx, [rbx+30h]; this
0x1800049a8  test    rcx, rcx
0x1800049ab  jz      short loc_1800049B9
0x1800049ad  call    ?Cancel@NetworkIncident@@QEAAXXZ; NetworkIncident::Cancel(void)
0x1800049b2  mov     r8, cs:qword_180041BB8
0x1800049b9  cmp     [rbx+19h], r12b
0x1800049bd  jnz     short loc_18000499E
0x1800049bf  mov     rcx, [rbx+10h]
0x1800049c3  cmp     [rcx+19h], r12b
0x1800049c7  jnz     short loc_1800049D0
0x1800049c9  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x1800049ce  jmp     short loc_1800049E9
0x1800049d0  mov     rax, [rbx+8]
0x1800049d4  jmp     short loc_1800049E3
0x1800049d6  cmp     rbx, [rax+10h]
0x1800049da  jnz     short loc_1800049E9
0x1800049dc  mov     rbx, rax
0x1800049df  mov     rax, [rax+8]
0x1800049e3  cmp     [rax+19h], r12b
0x1800049e7  jz      short loc_1800049D6
0x1800049e9  mov     rbx, rax
0x1800049ec  jmp     short loc_18000499E
0x1800049ee  xor     eax, eax
0x1800049f0  jmp     loc_180005025
0x1800049f5  lea     rdx, [rbp+57h+var_68]
0x1800049f9  call    cs:__imp_WdiGetDiagnosticModuleId
0x1800049ff  test    eax, eax
0x180004a01  js      loc_180005025
0x180004a07  lea     rdx, [rbp+57h+var_78]
0x180004a0b  mov     rcx, rsi
0x180004a0e  call    cs:__imp_WdiGetInstanceId
0x180004a14  test    eax, eax
0x180004a16  js      loc_180005025
0x180004a1c  lea     r8, [rbp+57h+var_C0]
0x180004a20  lea     rdx, [rbp+57h+var_58]
0x180004a24  mov     rcx, rsi
0x180004a27  call    cs:__imp_WdiGetScenarioInfo
0x180004a2d  mov     edi, eax
0x180004a2f  test    eax, eax
0x180004a31  js      loc_180005025
0x180004a37  cmp     [rbp+57h+var_C0], r12d
0x180004a3b  jz      short loc_180004A47
0x180004a3d  mov     eax, 80004005h
0x180004a42  jmp     loc_180005025
0x180004a47  sub     ebx, 2
0x180004a4a  jz      loc_180005013
0x180004a50  sub     ebx, 1
0x180004a53  jz      loc_180004ECA
0x180004a59  sub     ebx, 1
0x180004a5c  jz      loc_180004B79
0x180004a62  sub     ebx, 1
0x180004a65  jz      short loc_180004ABE
0x180004a67  cmp     ebx, 1
0x180004a6a  jnz     loc_180005023
0x180004a70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004a77  lea     ecx, [rbx+0Fh]; unsigned __int64
0x180004a7a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004a7f  mov     rbx, rax
0x180004a82  mov     [rbp+57h+var_C8], rax
0x180004a86  test    rax, rax
0x180004a89  jz      loc_180004EC0
0x180004a8f  lea     rax, ??_7DiagnosticsClient@@6B@; const DiagnosticsClient::`vftable'
0x180004a96  mov     [rbx], rax
0x180004a99  mov     [rbx+8], rsi
0x180004a9d  test    rbx, rbx
0x180004aa0  jz      loc_180004EC0
0x180004aa6  mov     rdx, rbx; struct DiagnosticsClient *
0x180004aa9  call    ?Cancel@NetworkDiagnosticsEngine@@QEAAJPEAVDiagnosticsClient@@@Z; NetworkDiagnosticsEngine::Cancel(DiagnosticsClient *)
0x180004aae  mov     edi, eax
0x180004ab0  mov     rcx, rbx
0x180004ab3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004ab9  jmp     loc_180005023
0x180004abe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004ac5  mov     ecx, 10h; unsigned __int64
0x180004aca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004acf  mov     r14, rax
0x180004ad2  mov     [rbp+57h+var_C8], rax
0x180004ad6  test    rax, rax
0x180004ad9  jz      loc_180004EC0
0x180004adf  lea     rax, ??_7DiagnosticsClient@@6B@; const DiagnosticsClient::`vftable'
0x180004ae6  mov     [r14], rax
0x180004ae9  mov     [r14+8], rsi
0x180004aed  test    r14, r14
0x180004af0  jz      loc_180004EC0
0x180004af6  mov     rcx, cs:qword_180041BB8
0x180004afd  add     rcx, 40h ; '@'; lpCriticalSection
0x180004b01  call    cs:__imp_EnterCriticalSection
0x180004b07  mov     rax, [r14]
0x180004b0a  lea     rdx, [rbp+57h+var_78]
0x180004b0e  mov     rcx, r14
0x180004b11  mov     rax, [rax+48h]
0x180004b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b1a  mov     edi, eax
0x180004b1c  test    eax, eax
0x180004b1e  js      short loc_180004B60
0x180004b20  mov     rbx, cs:qword_180041BB8
0x180004b27  lea     r8, [rbp+57h+var_78]
0x180004b2b  lea     rdx, [rbp+57h+var_C8]
0x180004b2f  lea     rcx, [rbx+8]
0x180004b33  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVNetworkIncident@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(_GUID const &)
0x180004b38  mov     rcx, [rax]; this
0x180004b3b  cmp     rcx, [rbx+8]
0x180004b3f  jz      short loc_180004B60
0x180004b41  mov     rbx, [rcx+30h]
0x180004b45  test    rbx, rbx
0x180004b48  jz      short loc_180004B60
0x180004b4a  mov     rdx, r14; struct DiagnosticsClient *
0x180004b4d  call    ?DeregisterClient@NetworkDiagnosticsEngine@@QEAAJPEAVDiagnosticsClient@@@Z; NetworkDiagnosticsEngine::DeregisterClient(DiagnosticsClient *)
0x180004b52  mov     edi, eax
0x180004b54  test    eax, eax
0x180004b56  js      short loc_180004B60
0x180004b58  mov     rcx, rbx; this
0x180004b5b  call    ??_GNetworkIncident@@QEAAPEAXI@Z; NetworkIncident::`scalar deleting destructor'(uint)
0x180004b60  mov     rcx, cs:qword_180041BB8
0x180004b67  add     rcx, 40h ; '@'; lpCriticalSection
0x180004b6b  call    cs:__imp_LeaveCriticalSection
0x180004b71  mov     rcx, r14
0x180004b74  jmp     loc_180004AB3
0x180004b79  mov     [rbp+57h+var_A8], rsi
0x180004b7d  mov     [rbp+57h+var_A0], r12d
0x180004b81  mov     [rbp+57h+var_98], r12
0x180004b85  mov     [rbp+57h+var_90], r12
0x180004b89  lea     rcx, [rbp+57h+var_A8]; this
0x180004b8d  call    ?SetThreadLanguage@CNDFLanguageUtil@@QEAAJXZ; CNDFLanguageUtil::SetThreadLanguage(void)
0x180004b92  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004b99  mov     ebx, 10h
0x180004b9e  mov     ecx, ebx; unsigned __int64
0x180004ba0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004ba5  mov     r14, rax
0x180004ba8  mov     [rbp+57h+var_C8], rax
0x180004bac  test    rax, rax
0x180004baf  jz      loc_180004EB7
0x180004bb5  lea     rax, ??_7DiagnosticsClient@@6B@; const DiagnosticsClient::`vftable'
0x180004bbc  mov     [r14], rax
0x180004bbf  mov     [r14+8], rsi
0x180004bc3  test    r14, r14
0x180004bc6  jz      loc_180004EB7
0x180004bcc  mov     rcx, cs:qword_180041BB8
0x180004bd3  add     rcx, 40h ; '@'; lpCriticalSection
0x180004bd7  call    cs:__imp_EnterCriticalSection
0x180004bdd  mov     [rbp+57h+var_B8], r12
0x180004be1  lea     r9, [rbp+57h+var_B8]
0x180004be5  lea     r8, aFeedbackguid; "FeedbackGUID"
0x180004bec  xor     edx, edx
0x180004bee  mov     rcx, rsi
0x180004bf1  call    cs:__imp_WdiGetParameterByName
0x180004bf7  test    eax, eax
0x180004bf9  js      loc_180004C84
0x180004bff  mov     rcx, [rbp+57h+var_B8]
0x180004c03  test    rcx, rcx
0x180004c06  jz      short loc_180004C84
0x180004c08  xorps   xmm0, xmm0
0x180004c0b  movups  [rbp+57h+Buf2], xmm0
0x180004c0f  mov     r8d, ebx
0x180004c12  lea     rdx, [rbp+57h+Buf2]
0x180004c16  call    cs:__imp_WdiGetParameterData
0x180004c1c  mov     edi, eax
0x180004c1e  test    eax, eax
0x180004c20  js      loc_180004E97
0x180004c26  xorps   xmm0, xmm0
0x180004c29  movups  [rbp+57h+Buf1], xmm0
0x180004c2d  mov     r8d, ebx; Size
0x180004c30  lea     rdx, [rbp+57h+Buf2]; Buf2
0x180004c34  lea     rcx, [rbp+57h+Buf1]; Buf1
0x180004c38  call    memcmp_0
0x180004c3d  test    eax, eax
0x180004c3f  jnz     loc_180004DDE
0x180004c45  mov     rsi, cs:qword_180041BB8
0x180004c4c  lea     r8, [rbp+57h+var_78]
0x180004c50  lea     rdx, [rbp+57h+var_B0]
0x180004c54  lea     rcx, [rsi+8]
0x180004c58  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVNetworkIncident@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVNetworkIncident@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,NetworkIncident *,std::less<_GUID>,std::allocator<std::pair<_GUID const,NetworkIncident *>>,0>>::find(_GUID const &)
0x180004c5d  mov     rdx, [rax]
0x180004c60  cmp     rdx, [rsi+8]
0x180004c64  jz      loc_180004E97
0x180004c6a  mov     rdx, [rdx+30h]; struct NetworkIncident *
0x180004c6e  test    rdx, rdx
0x180004c71  jz      loc_180004E97
0x180004c77  mov     rcx, rsi; this
0x180004c7a  call    ?SendReport@NetworkDiagnosticsEngine@@QEAAXPEAVNetworkIncident@@@Z; NetworkDiagnosticsEngine::SendReport(NetworkIncident *)
0x180004c7f  jmp     loc_180004E97
0x180004c84  mov     [rbp+57h+var_D0], r12d
0x180004c88  mov     [rbp+57h+var_B0], r12d
0x180004c8c  mov     dword ptr [rsp+110h+var_E0], r12d
0x180004c91  mov     [rsp+110h+var_D8], r12d
0x180004c96  xorps   xmm0, xmm0
0x180004c99  movups  [rbp+57h+Buf1], xmm0
0x180004c9d  mov     dword ptr [rbp+57h+var_BC], r12d
0x180004ca1  lea     rax, [rbp+57h+var_D0]
0x180004ca5  mov     [rsp+110h+var_F0], rax; unsigned int *
0x180004caa  mov     r9d, ebx; unsigned int
0x180004cad  lea     r8, [rbp+57h+Buf1]; unsigned __int8 *
0x180004cb1  lea     rdx, aNdfgettracefil; "NdfGetTraceFileGuid"
0x180004cb8  mov     rcx, rsi; void *
0x180004cbb  call    ?GetLastWdiParameter@@YAJPEAXPEBGPEAEKPEAK@Z; GetLastWdiParameter(void *,ushort const *,uchar *,ulong,ulong *)
0x180004cc0  lea     rax, [rbp+57h+var_B0]
0x180004cc4  mov     [rsp+110h+var_F0], rax; unsigned int *
0x180004cc9  mov     r9d, 4; unsigned int
0x180004ccf  lea     r8, [rbp+57h+var_BC]; unsigned __int8 *
0x180004cd3  lea     rdx, aValidaterepair; "ValidateRepair"
0x180004cda  mov     rcx, rsi; void *
0x180004cdd  call    ?GetLastWdiParameter@@YAJPEAXPEBGPEAEKPEAK@Z; GetLastWdiParameter(void *,ushort const *,uchar *,ulong,ulong *)
0x180004ce2  lea     rax, [rsp+110h+var_E0]
0x180004ce7  mov     [rsp+110h+var_F0], rax; unsigned int *
0x180004cec  xor     r9d, r9d; unsigned int
0x180004cef  xor     r8d, r8d; unsigned __int8 *
0x180004cf2  lea     rdx, aSelectedrepair; "SelectedRepairGUID"
0x180004cf9  mov     rcx, rsi; void *
0x180004cfc  call    ?GetLastWdiParameter@@YAJPEAXPEBGPEAEKPEAK@Z; GetLastWdiParameter(void *,ushort const *,uchar *,ulong,ulong *)
0x180004d01  lea     rax, [rsp+110h+var_D8]
0x180004d06  mov     [rsp+110h+var_F0], rax; unsigned int *
0x180004d0b  xor     r9d, r9d; unsigned int
0x180004d0e  xor     r8d, r8d; unsigned __int8 *
0x180004d11  lea     rdx, aFollowupincide; "FollowUpIncident"
0x180004d18  mov     rcx, rsi; void *
0x180004d1b  call    ?GetLastWdiParameter@@YAJPEAXPEBGPEAEKPEAK@Z; GetLastWdiParameter(void *,ushort const *,uchar *,ulong,ulong *)
0x180004d20  mov     [rbp+57h+var_C8], r12
0x180004d24  lea     r9, [rbp+57h+var_C8]
0x180004d28  lea     r8, aSplitrepairand; "SplitRepairAndValidate"
0x180004d2f  xor     edx, edx
0x180004d31  mov     rcx, [r14+8]
0x180004d35  call    cs:__imp_WdiGetParameterByName
0x180004d3b  mov     esi, eax
0x180004d3d  mov     edx, [rbp+57h+var_B0]
0x180004d40  mov     ecx, dword ptr [rsp+110h+var_E0]; this
0x180004d44  mov     r8d, [rsp+110h+var_D8]
0x180004d49  mov     r9d, [rbp+57h+var_D0]
0x180004d4d  cmp     r8d, r9d
0x180004d50  jbe     short loc_180004D60
0x180004d52  cmp     r8d, edx
0x180004d55  jbe     short loc_180004D60
0x180004d57  cmp     r8d, ecx
0x180004d5a  ja      loc_180004E8D
0x180004d60  cmp     r9d, edx
0x180004d63  jbe     short loc_180004D98
0x180004d65  cmp     r9d, ecx
0x180004d68  jbe     short loc_180004D98
0x180004d6a  xorps   xmm0, xmm0
0x180004d6d  movups  [rbp+57h+Buf2], xmm0
0x180004d71  mov     byte ptr [rbp+57h+Buf2+0Fh], 1
0x180004d75  mov     r8, rbx; Size
0x180004d78  lea     rdx, [rbp+57h+Buf1]; Buf2
0x180004d7c  lea     rcx, [rbp+57h+Buf2]; Buf1
0x180004d80  call    memcmp_0
0x180004d85  test    eax, eax
0x180004d87  jnz     short loc_180004DDE
0x180004d89  mov     rdx, r14; struct DiagnosticsClient *
0x180004d8c  call    ?GetTraceFile@NetworkDiagnosticsEngine@@QEAAJPEAVDiagnosticsClient@@@Z; NetworkDiagnosticsEngine::GetTraceFile(DiagnosticsClient *)
0x180004d91  mov     edi, eax
0x180004d93  jmp     loc_180004E97
0x180004d98  cmp     edx, ecx
0x180004d9a  jbe     short loc_180004DE8
0x180004d9c  cmp     dword ptr [rbp+57h+var_BC], r12d
0x180004da0  jz      short loc_180004DDE
0x180004da2  mov     rdx, r14; struct DiagnosticsClient *
0x180004da5  call    ?Validate@NetworkDiagnosticsEngine@@QEAAJPEAVDiagnosticsClient@@@Z; NetworkDiagnosticsEngine::Validate(DiagnosticsClient *)
0x180004daa  mov     ebx, eax
0x180004dac  mov     [rbp+57h+var_D0], eax
0x180004daf  lea     rax, [rbp+57h+var_D0]
0x180004db3  mov     [rsp+110h+var_F0], rax
0x180004db8  mov     r9d, 4
0x180004dbe  lea     r8, aNdfcallresult; "NDFCallResult"
0x180004dc5  xor     edx, edx
0x180004dc7  mov     rcx, [r14+8]
0x180004dcb  call    cs:__imp_WdiAddParameter
0x180004dd1  mov     edi, r12d
0x180004dd4  test    ebx, ebx
0x180004dd6  cmovns  edi, ebx
0x180004dd9  jmp     loc_180004E97
  ... truncated ...
```
