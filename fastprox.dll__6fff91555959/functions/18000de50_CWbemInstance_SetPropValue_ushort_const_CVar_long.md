# CWbemInstance::SetPropValue(ushort const *,CVar *,long)

- ea: `0x18000de50`
- end: `0x18000e713`
- name: `?SetPropValue@CWbemInstance@@UEAAJPEBGPEAVCVar@@J@Z`
- size: `2243`
- prototype: `__int64 __fastcall(int **this, unsigned __int16 *, struct CVar *, unsigned int)`
- caller_count: `0`
- callee_count: `16`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004060`
- `0x18000dde0`
- `0x18000de50`
- `0x18000fb50`
- `0x180035b08`
- `0x180037120`
- `0x18003d584`
- `0x18003d670`
- `0x18003d6e8`
- `0x18003e884`
- `0x18003eae0`
- `0x180065994`
- `0x18006fa4c`
- `0x180071c50`
- `0x1800825b4`
- `0x18009e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000e107`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000e15f`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000e4f3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000e538`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000e107`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000e15f`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000e4f3`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000e538`
- `wbemcomn!GetMemLogObject` at `0x18000e344`
- `wbemcomn!GetMemLogObject` at `0x18000e54e`
- `wbemcomn!GetMemLogObject` at `0x18000e5c9`
- `wbemcomn!GetMemLogObject` at `0x18000e6b0`
- `wbemcomn!GetMemLogObject` at `0x18000e344`
- `wbemcomn!GetMemLogObject` at `0x18000e54e`
- `wbemcomn!GetMemLogObject` at `0x18000e5c9`
- `wbemcomn!GetMemLogObject` at `0x18000e6b0`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18000e661`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18000e670`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18000e661`
- `wbemcomn!?GetType@CVar@@QEAAHXZ` at `0x18000e670`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18000e683`
- `wbemcomn!?GetLPWSTR@CVar@@QEAAPEAGXZ` at `0x18000e683`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x18000e269`
- `wbemcomn!?IsNull@CVar@@QEAAHXZ` at `0x18000e269`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18000e277`
- `wbemcomn!??0CVar@@QEAA@XZ` at `0x18000e277`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x18000e396`
- `wbemcomn!?FillVariant@CVar@@QEAAXPEAUtagVARIANT@@H@Z` at `0x18000e396`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e352`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e55c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e5d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e6be`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e352`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e55c`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e5d7`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18000e6be`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000e2bc`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000e703`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000e2bc`
- `wbemcomn!??1CVar@@QEAA@XZ` at `0x18000e703`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e3dd`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18000e3dd`
- `OLEAUT32!__imp_VariantInit` at `0x18000e386`
- `OLEAUT32!__imp_VariantInit` at `0x18000e386`
- `OLEAUT32!__imp_VariantClear` at `0x18000e3e7`
- `OLEAUT32!__imp_VariantClear` at `0x18000e403`
- `OLEAUT32!__imp_VariantClear` at `0x18000e3e7`
- `OLEAUT32!__imp_VariantClear` at `0x18000e403`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CWbemInstance::SetPropValue(int **this, unsigned __int16 *a2, struct CVar *a3, unsigned int a4)
{
  CVar *v4; // r14
  int v7; // edi
  signed __int32 i; // ecx
  signed __int32 v9; // edx
  BOOL v10; // ebx
  signed __int32 v11; // eax
  int v13; // r14d
  WCHAR *v14; // rsi
  unsigned __int16 *j; // rdi
  WCHAR v16; // bx
  WCHAR v17; // cx
  unsigned __int16 *v18; // rdi
  int *v19; // rdx
  int *v20; // r13
  unsigned int *v21; // r15
  unsigned __int16 *v22; // r14
  unsigned int *v23; // r12
  __int64 v24; // rbx
  char * near *v25; // rcx
  unsigned __int16 *v26; // rdi
  int v27; // r14d
  unsigned __int16 *m; // rsi
  WCHAR v29; // bx
  int v30; // ebx
  int v31; // ebx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  struct CPropertyInformation *v35; // rbx
  unsigned __int16 *k; // rsi
  int v37; // ebx
  CMemoryLog *v38; // rax
  JAmsi *v39; // rcx
  JAmsi *v40; // rcx
  unsigned __int16 *v41; // rbx
  int v42; // edi
  unsigned int v43; // edx
  int v44; // eax
  int v45; // eax
  CMemoryLog *v46; // rax
  CMemoryLog *MemLogObject; // rax
  const unsigned __int16 *LPWSTR; // rax
  CMemoryLog *v49; // rax
  const char *lpDestStr; // [rsp+20h] [rbp-79h]
  WCHAR DestStr; // [rsp+50h] [rbp-49h] BYREF
  WCHAR SrcStr[4]; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int16 *v53; // [rsp+60h] [rbp-39h] BYREF
  unsigned int v54[4]; // [rsp+68h] [rbp-31h] BYREF
  __int64 v55; // [rsp+78h] [rbp-21h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-11h] BYREF
  _BYTE v57[80]; // [rsp+A0h] [rbp+7h] BYREF
  struct CVar *v60; // [rsp+110h] [rbp+77h]

  v60 = a3;
  v4 = a3;
  memset(&pvarg, 0, sizeof(pvarg));
  v7 = *(_DWORD *)Feature_JAmsi__descriptor;
  if ( (*(_DWORD *)Feature_JAmsi__descriptor & 4) == 0 )
  {
    *(_QWORD *)SrcStr = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_JAmsi>::GetCachedFeatureEnabledState(
                                     this,
                                     v57);
    LOWORD(v7) = SrcStr[0];
  }
  LODWORD(v53) = 0;
  WORD2(v53) = 3;
  wcscpy(SrcStr, L"\x03");
  *(_OWORD *)v54 = 0;
  v55 = 0;
  for ( i = dword_1800D7C78; ; i = v11 )
  {
    v9 = i | 2;
    v10 = (i | 2) == i;
    if ( (i | 2) != i )
      v9 = i | 3;
    v11 = _InterlockedCompareExchange((volatile signed __int32 *)&dword_1800D7C78, v9, i);
    if ( i == v11 )
      break;
  }
  if ( (v9 & 1) != 0 && (i & 1) == 0 )
    wil::details::EnabledStateManager::QueueBackgroundUsageReporting(
      wil::details::g_enabledStateManager,
      0xF399C3u,
      (struct wil_details_FeatureReportingCache *)&dword_1800D7C78);
  if ( v54[1] )
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0xF399C3, v54[2], v54[1], a4, lpDestStr);
  if ( !v10 )
    wil::details::EnabledStateManager::EnsureSubscribedToUsageFlush(
      (wil::details::EnabledStateManager *)wil::details::g_enabledStateManager,
      (void (*)(void *))_lambda_aa194dc0bf891154933407eb98fb868a_::_lambda_invoker_cdecl_);
  if ( (v7 & 0x400) != 0 )
  {
    v43 = 2;
    if ( (v7 & 0x800) != 0 )
      v43 = -2147483646;
    wil::details::WilApi_RecordFeatureUsage((wil::details *)0xF399C3, v43, 0, a4, lpDestStr);
  }
  if ( !v10 )
  {
    if ( g_wil_details_realtimeFeatureUsageHook )
    {
      LOBYTE(a3) = 3;
      g_wil_details_realtimeFeatureUsageHook(15964611, 2, a3);
    }
    if ( g_wil_details_pfnFeatureLoggingHook )
      g_wil_details_pfnFeatureLoggingHook(15964611, &v53, 0, 1, SrcStr, 0, 0, 1);
  }
  if ( dword_1800D8070 && v4 )
  {
    VariantInit(&pvarg);
    CVar::FillVariant(v4, &pvarg, 0);
    v53 = 0;
    if ( JAmsi::JAmsiVarParameterToString(v39, &pvarg, &v53) )
    {
      v41 = v53;
      v42 = JAmsi::JAmsiProcessor(v40, L"SetPropValue", a2, v53, 0);
      if ( v41 )
        CWin32DefaultArena::WbemMemFree(v41);
      VariantClear(&pvarg);
      if ( v42 < 0 )
        return 2147749889LL;
    }
    else
    {
      VariantClear(&pvarg);
    }
  }
  v13 = 1;
LABEL_19:
  if ( v13 > 10 )
    goto LABEL_32;
  v14 = (WCHAR *)(&m_awszPropNames)[v13];
  for ( j = a2; ; ++j )
  {
    v16 = *j;
    if ( !*j )
      break;
    if ( v16 > 0x7Fu )
    {
      SrcStr[0] = *j;
      DestStr = 0;
      v44 = LCMapStringW(0x7Fu, 0x100u, SrcStr, 1, &DestStr, 1);
      v16 = DestStr;
      if ( !v44 )
        v16 = SrcStr[0];
    }
    else if ( (unsigned __int16)(v16 - 65) <= 0x19u )
    {
      v16 += 32;
    }
LABEL_25:
    v17 = *v14;
    if ( *v14 > 0x7Fu )
    {
      DestStr = *v14;
      SrcStr[0] = 0;
      v45 = LCMapStringW(0x7Fu, 0x100u, &DestStr, 1, SrcStr, 1);
      v17 = SrcStr[0];
      if ( !v45 )
        v17 = DestStr;
    }
    else if ( (unsigned __int16)(v17 - 65) <= 0x19u )
    {
      v17 += 32;
    }
    if ( v16 != v17 )
    {
      ++v13;
      goto LABEL_19;
    }
    ++v14;
  }
  if ( *v14 )
    goto LABEL_25;
  if ( v13 < 0 )
  {
LABEL_32:
    v18 = (unsigned __int16 *)(**(__int64 (__fastcall ***)(int *))this[70])(this[70]);
    v53 = v18;
    v19 = this[69];
    if ( *v19 < 1 )
      return 2147749890LL;
    v20 = v19 + 1;
    v21 = (unsigned int *)&v19[2 * *v19 - 1];
    v22 = a2;
    while ( 1 )
    {
      if ( v20 > (int *)v21 )
        return 2147749890LL;
      v23 = (unsigned int *)&v20[2 * ((((char *)v21 - (char *)v20) >> 3) / 2)];
      v24 = *v23;
      if ( CFastHeap::IsFakeAddress(*v23) )
      {
        if ( !mstatic_nNumStrings )
          mstatic_nNumStrings = 11;
        LODWORD(v24) = v24 & 0x7FFFFFFF;
        if ( (unsigned int)v24 >= 0xB )
        {
          MemLogObject = GetMemLogObject();
          CMemoryLog::Write(MemLogObject, -2);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_03fa6aa8a2c93d0e9926d9f16c5faabc_Traceguids,
              "CX_Exception()");
          }
          throw (CX_Exception *)&DestStr;
        }
        _mm_lfence();
        v25 = (&mstatic_aszStrings)[v24];
      }
      else
      {
        if ( (unsigned int)v24 > *(_DWORD *)(*((_QWORD *)v18 + 1) + 4LL) )
          throw (CX_Exception *)&DestStr;
        v25 = (char * near *)(*(_QWORD *)v18 + (unsigned int)v24);
      }
      v26 = (unsigned __int16 *)((char *)v25 + 1);
      if ( *(_BYTE *)v25 == 1 )
      {
        for ( k = v22; *v26 || *k; ++k )
        {
          v37 = wbem_towlower(*v26);
          v31 = v37 - wbem_towlower(*k);
          if ( v31 )
            goto LABEL_49;
          ++v26;
        }
        v31 = 0;
      }
      else
      {
        v27 = 117440512;
        for ( m = a2; v27 && (*(_BYTE *)v26 || *m); ++m )
        {
          v29 = *m;
          if ( *m > 0x7Fu )
          {
            SrcStr[0] = *m;
            DestStr = 0;
            if ( LCMapStringW(0x7Fu, 0x100u, SrcStr, 1, &DestStr, 1) )
              v29 = DestStr;
            else
              v29 = SrcStr[0];
          }
          else if ( (unsigned __int16)(v29 - 65) <= 0x19u )
          {
            v29 += 32;
          }
          v33 = *(unsigned __int8 *)v26;
          if ( v33 > 0x7F )
          {
            SrcStr[0] = *(unsigned __int8 *)v26;
            DestStr = 0;
            if ( LCMapStringW(0x7Fu, 0x100u, SrcStr, 1, &DestStr, 1) )
              LOWORD(v33) = DestStr;
            else
              LOWORD(v33) = SrcStr[0];
          }
          else if ( (unsigned __int16)(v33 - 65) <= 0x19u )
          {
            LOWORD(v33) = v33 + 32;
          }
          v30 = v29 - (unsigned __int16)v33;
          if ( v30 )
            goto LABEL_48;
          --v27;
          v26 = (unsigned __int16 *)((char *)v26 + 1);
        }
        v30 = 0;
LABEL_48:
        v31 = -v30;
        v22 = a2;
      }
LABEL_49:
      if ( !v31 )
        break;
      v18 = v53;
      if ( v31 <= 0 )
        v20 = (int *)(v23 + 2);
      else
        v21 = v23 - 2;
    }
    if ( !v23 )
      return 2147749890LL;
    v34 = v23[1];
    if ( v34 > this[76][1] )
      throw (CX_Exception *)&DestStr;
    v35 = (struct CPropertyInformation *)((char *)this[75] + v34);
    if ( !v35 )
      return 2147749890LL;
    if ( a4 && a4 != (*(_DWORD *)v35 & 0x2FFF) )
    {
      v38 = GetMemLogObject();
      CMemoryLog::Write(v38, -2147217403);
      if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749893LL);
      }
      return 2147749893LL;
    }
    if ( (*(_DWORD *)v35 & 0x2FFF) == 0x65 && !CVar::IsNull(v60) )
    {
      CVar::CVar((CVar *)v54);
      if ( (*((int (__fastcall **)(int **, struct CPropertyInformation *, const wchar_t *, unsigned int *, _QWORD, _QWORD))*this
            + 114))(
             this,
             v35,
             L"SUBTYPE",
             v54,
             0,
             0) >= 0
        && (CVar::GetType((CVar *)v54) == 8 || CVar::GetType((CVar *)v54) == 31) )
      {
        LPWSTR = CVar::GetLPWSTR((CVar *)v54);
        if ( !(unsigned int)wbem_wcsicmp(LPWSTR, L"interval")
          && !(unsigned int)CUntypedValue::CheckIntervalDateTime(v60) )
        {
          v49 = GetMemLogObject();
          CMemoryLog::Write(v49, -2147217403);
          if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              39,
              WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids,
              2147749893LL);
          }
          CVar::~CVar((CVar *)v54);
          return 2147749893LL;
        }
      }
      CVar::~CVar((CVar *)v54);
    }
    return CInstancePart::SetActualValue((CInstancePart *)(this + 22), v35, v60);
  }
  v46 = GetMemLogObject();
  CMemoryLog::Write(v46, -2147217373);
  if ( WPP_GLOBAL_Control != (CWbemRefreshingSvc *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_d7ef7800c65a3c6ec6a85aaaf32c693f_Traceguids, 2147749923LL);
  }
  return 2147749923LL;
}

```

## disassembly

```asm
0x18000de50  mov     [rsp-8+arg_18], r9d
0x18000de55  mov     [rsp-8+arg_10], r8
0x18000de5a  mov     [rsp-8+arg_8], rdx
0x18000de5f  mov     [rsp-8+arg_0], rcx
0x18000de64  push    rbp
0x18000de65  push    rbx
0x18000de66  push    rsi
0x18000de67  push    rdi
0x18000de68  push    r12
0x18000de6a  push    r13
0x18000de6c  push    r14
0x18000de6e  push    r15
0x18000de70  lea     rbp, [rsp-1Fh]
0x18000de75  sub     rsp, 0B8h
0x18000de7c  mov     r14, r8
0x18000de7f  mov     r15, rdx
0x18000de82  mov     r12, rcx
0x18000de85  xorps   xmm0, xmm0
0x18000de88  xor     eax, eax
0x18000de8a  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x18000de8e  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x18000de92  mov     rax, cs:Feature_JAmsi__descriptor
0x18000de99  mov     edi, [rax]
0x18000de9b  test    dil, 4
0x18000de9f  jz      loc_18000E31E
0x18000dea5  xor     eax, eax
0x18000dea7  mov     dword ptr [rbp+57h+var_90], eax
0x18000deaa  mov     word ptr [rbp+57h+var_90+4], 3
0x18000deb0  mov     dword ptr [rbp+57h+SrcStr], 3
0x18000deb7  xorps   xmm0, xmm0
0x18000deba  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x18000debe  mov     [rbp+57h+var_78], rax
0x18000dec2  mov     ecx, cs:dword_1800D7C78
0x18000dec8  mov     edx, ecx
0x18000deca  or      edx, 2
0x18000decd  xor     ebx, ebx
0x18000decf  cmp     edx, ecx
0x18000ded1  setz    bl
0x18000ded4  mov     eax, edx
0x18000ded6  or      eax, 1
0x18000ded9  cmp     edx, ecx
0x18000dedb  cmovnz  edx, eax
0x18000dede  mov     eax, ecx
0x18000dee0  lock cmpxchg cs:dword_1800D7C78, edx
0x18000dee8  jnz     loc_18000E198
0x18000deee  test    dl, 1
0x18000def1  jnz     loc_18000E495
0x18000def7  xor     eax, eax
0x18000def9  mov     esi, [rbp+57h+var_88+4]
0x18000defc  test    eax, eax
0x18000defe  jnz     loc_18000E2D8
0x18000df04  test    esi, esi
0x18000df06  jnz     loc_18000E4A8
0x18000df0c  test    ebx, ebx
0x18000df0e  jz      loc_18000E306
0x18000df14  bt      edi, 0Ah
0x18000df18  jb      loc_18000E478
0x18000df1e  test    ebx, ebx
0x18000df20  jz      loc_18000E40E
0x18000df26  cmp     cs:dword_1800D8070, 0
0x18000df2d  jnz     loc_18000E379
0x18000df33  mov     r14d, 1
0x18000df39  lea     rsi, __ImageBase
0x18000df40  cmp     r14d, 0Ah
0x18000df44  jg      short loc_18000DFB6
0x18000df46  movsxd  rax, r14d
0x18000df49  mov     rsi, ds:rva ?m_awszPropNames@@3PAPEAGA[rsi+rax*8]; ushort * near * m_awszPropNames ...
0x18000df51  mov     rdi, r15
0x18000df54  movzx   ebx, word ptr [rdi]
0x18000df57  test    bx, bx
0x18000df5a  jz      short loc_18000DFA0
0x18000df5c  cmp     bx, 7Fh
0x18000df60  ja      loc_18000E4C4
0x18000df66  lea     eax, [rbx-41h]
0x18000df69  cmp     ax, 19h
0x18000df6d  ja      short loc_18000DF73
0x18000df6f  add     bx, 20h ; ' '
0x18000df73  movzx   ecx, word ptr [rsi]
0x18000df76  cmp     cx, 7Fh
0x18000df7a  ja      loc_18000E509
0x18000df80  lea     eax, [rcx-41h]
0x18000df83  cmp     ax, 19h
0x18000df87  ja      short loc_18000DF8D
0x18000df89  add     cx, 20h ; ' '
0x18000df8d  cmp     bx, cx
0x18000df90  jnz     loc_18000E08C
0x18000df96  add     rdi, 2
0x18000df9a  add     rsi, 2
0x18000df9e  jmp     short loc_18000DF54
0x18000dfa0  cmp     word ptr [rsi], 0
0x18000dfa4  jnz     short loc_18000DF73
0x18000dfa6  test    r14d, r14d
0x18000dfa9  jns     loc_18000E54E
0x18000dfaf  lea     rsi, __ImageBase
0x18000dfb6  mov     rcx, [r12+230h]
0x18000dfbe  mov     rax, [rcx]
0x18000dfc1  mov     rax, [rax]
0x18000dfc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfc9  mov     rdi, rax
0x18000dfcc  mov     [rbp+57h+var_90], rax
0x18000dfd0  mov     rdx, [r12+228h]
0x18000dfd8  mov     ecx, [rdx]
0x18000dfda  cmp     ecx, 1
0x18000dfdd  jl      loc_18000E0BF
0x18000dfe3  lea     r13, [rdx+4]
0x18000dfe7  lea     ecx, ds:0FFFFFFFFFFFFFFFCh[rcx*8]
0x18000dfee  movsxd  r15, ecx
0x18000dff1  add     r15, rdx
0x18000dff4  mov     r14, [rbp+57h+arg_8]
0x18000dff8  cmp     r13, r15
0x18000dffb  ja      loc_18000E0BF
0x18000e001  mov     rax, r15
0x18000e004  sub     rax, r13
0x18000e007  sar     rax, 3
0x18000e00b  test    rax, rax
0x18000e00e  jns     short loc_18000E013
0x18000e010  inc     rax
0x18000e013  sar     rax, 1
0x18000e016  lea     r12, ds:0[rax*8]
0x18000e01e  add     r12, r13
0x18000e021  mov     ebx, [r12]
0x18000e025  mov     ecx, ebx; unsigned int
0x18000e027  call    ?IsFakeAddress@CFastHeap@@SA_NK@Z; CFastHeap::IsFakeAddress(ulong)
0x18000e02c  test    al, al
0x18000e02e  jnz     loc_18000E19F
0x18000e034  mov     rax, [rdi+8]
0x18000e038  cmp     ebx, [rax+4]
0x18000e03b  ja      loc_18000E2C7
0x18000e041  mov     ecx, ebx
0x18000e043  add     rcx, [rdi]
0x18000e046  lea     rdi, [rcx+1]
0x18000e04a  cmp     byte ptr [rcx], 1
0x18000e04d  jz      loc_18000E232
0x18000e053  mov     r14d, 7000000h
0x18000e059  mov     rsi, [rbp+57h+arg_8]
0x18000e05d  test    r14d, r14d
0x18000e060  jz      short loc_18000E094
0x18000e062  cmp     byte ptr [rdi], 0
0x18000e065  jnz     short loc_18000E06D
0x18000e067  cmp     word ptr [rsi], 0
0x18000e06b  jz      short loc_18000E094
0x18000e06d  movzx   ebx, word ptr [rsi]
0x18000e070  cmp     bx, 7Fh
0x18000e074  ja      short loc_18000E0D8
0x18000e076  lea     eax, [rbx-41h]
0x18000e079  cmp     ax, 19h
0x18000e07d  ja      loc_18000E119
0x18000e083  add     bx, 20h ; ' '
0x18000e087  jmp     loc_18000E119
0x18000e08c  inc     r14d
0x18000e08f  jmp     loc_18000DF39
0x18000e094  xor     ebx, ebx
0x18000e096  neg     ebx
0x18000e098  mov     r14, [rbp+57h+arg_8]
0x18000e09c  test    ebx, ebx
0x18000e09e  jz      loc_18000E1CF
0x18000e0a4  mov     rdi, [rbp+57h+var_90]
0x18000e0a8  lea     rsi, __ImageBase
0x18000e0af  jle     loc_18000E18E
0x18000e0b5  lea     r15, [r12-8]
0x18000e0ba  jmp     loc_18000DFF8
0x18000e0bf  mov     eax, 80041002h
0x18000e0c4  add     rsp, 0B8h
0x18000e0cb  pop     r15
0x18000e0cd  pop     r14
0x18000e0cf  pop     r13
0x18000e0d1  pop     r12
0x18000e0d3  pop     rdi
0x18000e0d4  pop     rsi
0x18000e0d5  pop     rbx
0x18000e0d6  pop     rbp
0x18000e0d7  retn
0x18000e0d8  mov     [rbp+57h+SrcStr], bx
0x18000e0dc  xor     eax, eax
0x18000e0de  mov     [rbp+57h+DestStr], ax
0x18000e0e2  mov     [rsp+0F0h+cchDest], 1; cchDest
0x18000e0ea  lea     rax, [rbp+57h+DestStr]
0x18000e0ee  mov     [rsp+0F0h+lpDestStr], rax; lpDestStr
0x18000e0f3  mov     r9d, 1; cchSrc
0x18000e0f9  lea     r8, [rbp+57h+SrcStr]; lpSrcStr
0x18000e0fd  mov     edx, 100h; dwMapFlags
0x18000e102  mov     ecx, 7Fh; Locale
0x18000e107  call    cs:__imp_LCMapStringW
0x18000e10d  test    eax, eax
0x18000e10f  jnz     loc_18000E5B7
0x18000e115  movzx   ebx, [rbp+57h+SrcStr]
0x18000e119  movzx   ecx, byte ptr [rdi]
0x18000e11c  cmp     ecx, 7Fh
0x18000e11f  ja      short loc_18000E130
0x18000e121  lea     eax, [rcx-41h]
0x18000e124  cmp     ax, 19h
0x18000e128  ja      short loc_18000E171
0x18000e12a  add     cx, 20h ; ' '
0x18000e12e  jmp     short loc_18000E171
0x18000e130  mov     [rbp+57h+SrcStr], cx
0x18000e134  xor     eax, eax
0x18000e136  mov     [rbp+57h+DestStr], ax
0x18000e13a  mov     [rsp+0F0h+cchDest], 1; cchDest
0x18000e142  lea     rax, [rbp+57h+DestStr]
0x18000e146  mov     [rsp+0F0h+lpDestStr], rax; lpDestStr
0x18000e14b  mov     r9d, 1; cchSrc
0x18000e151  lea     r8, [rbp+57h+SrcStr]; lpSrcStr
0x18000e155  mov     edx, 100h; dwMapFlags
0x18000e15a  mov     ecx, 7Fh; Locale
0x18000e15f  call    cs:__imp_LCMapStringW
0x18000e165  test    eax, eax
0x18000e167  jnz     loc_18000E5C0
0x18000e16d  movzx   ecx, [rbp+57h+SrcStr]
0x18000e171  movzx   eax, cx
0x18000e174  movzx   ebx, bx
0x18000e177  sub     ebx, eax
0x18000e179  jnz     loc_18000E096
0x18000e17f  dec     r14d
0x18000e182  inc     rdi
0x18000e185  add     rsi, 2
0x18000e189  jmp     loc_18000E05D
0x18000e18e  lea     r13, [r12+8]
0x18000e193  jmp     loc_18000DFF8
0x18000e198  mov     ecx, eax
0x18000e19a  jmp     loc_18000DEC8
0x18000e19f  cmp     cs:?mstatic_nNumStrings@@3HA, 0; int mstatic_nNumStrings
0x18000e1a6  jnz     short loc_18000E1B2
0x18000e1a8  mov     cs:?mstatic_nNumStrings@@3HA, 0Bh; int mstatic_nNumStrings
0x18000e1b2  btr     ebx, 1Fh
0x18000e1b6  cmp     ebx, 0Bh
0x18000e1b9  jnb     loc_18000E5C9
0x18000e1bf  lfence
0x18000e1c2  mov     rcx, ds:rva ?mstatic_aszStrings@@3PAPEADA[rsi+rbx*8]; char * near * mstatic_aszStrings ...
0x18000e1ca  jmp     loc_18000E046
0x18000e1cf  test    r12, r12
0x18000e1d2  jz      loc_18000E0BF
0x18000e1d8  mov     ecx, [r12+4]
0x18000e1dd  mov     rdi, [rbp+57h+arg_0]
0x18000e1e1  mov     rax, [rdi+260h]
0x18000e1e8  cmp     ecx, [rax+4]
0x18000e1eb  ja      loc_18000E2F5
0x18000e1f1  mov     ebx, ecx
0x18000e1f3  add     rbx, [rdi+258h]
0x18000e1fa  jz      loc_18000E0BF
0x18000e200  mov     ecx, [rbp+57h+arg_18]
0x18000e203  test    ecx, ecx
0x18000e205  jnz     loc_18000E335
0x18000e20b  mov     eax, [rbx]
0x18000e20d  and     eax, 2FFFh
0x18000e212  mov     rsi, [rbp+57h+arg_10]
0x18000e216  cmp     eax, 65h ; 'e'
0x18000e219  jz      short loc_18000E266
0x18000e21b  lea     rcx, [rdi+0B0h]; this
0x18000e222  mov     r8, rsi; struct CVar *
0x18000e225  mov     rdx, rbx; struct CPropertyInformation *
0x18000e228  call    ?SetActualValue@CInstancePart@@QEAAJPEAVCPropertyInformation@@PEAVCVar@@@Z; CInstancePart::SetActualValue(CPropertyInformation *,CVar *)
0x18000e22d  jmp     loc_18000E0C4
0x18000e232  mov     rsi, r14
0x18000e235  movzx   ecx, word ptr [rdi]; unsigned __int16
0x18000e238  test    cx, cx
0x18000e23b  jz      loc_18000E5A6
0x18000e241  call    ?wbem_towlower@@YAGG@Z; wbem_towlower(ushort)
0x18000e246  movzx   ebx, ax
0x18000e249  movzx   ecx, word ptr [rsi]; unsigned __int16
0x18000e24c  call    ?wbem_towlower@@YAGG@Z; wbem_towlower(ushort)
0x18000e251  movzx   eax, ax
0x18000e254  sub     ebx, eax
0x18000e256  jnz     loc_18000E09C
0x18000e25c  add     rdi, 2
0x18000e260  add     rsi, 2
0x18000e264  jmp     short loc_18000E235
0x18000e266  mov     rcx, rsi
0x18000e269  call    cs:__imp_?IsNull@CVar@@QEAAHXZ; CVar::IsNull(void)
0x18000e26f  test    eax, eax
0x18000e271  jnz     short loc_18000E21B
0x18000e273  lea     rcx, [rbp+57h+var_88]
0x18000e277  call    cs:__imp_??0CVar@@QEAA@XZ; CVar::CVar(void)
0x18000e27d  nop
0x18000e27e  mov     rax, [rdi]
0x18000e281  mov     qword ptr [rsp+0F0h+cchDest], 0
0x18000e28a  mov     [rsp+0F0h+lpDestStr], 0
0x18000e293  lea     r9, [rbp+57h+var_88]
0x18000e297  lea     r8, aSubtype; "SUBTYPE"
0x18000e29e  mov     rdx, rbx
0x18000e2a1  mov     rcx, rdi
0x18000e2a4  mov     rax, [rax+390h]
0x18000e2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2b0  test    eax, eax
0x18000e2b2  jns     loc_18000E65D
0x18000e2b8  lea     rcx, [rbp+57h+var_88]
0x18000e2bc  call    cs:__imp_??1CVar@@QEAA@XZ; CVar::~CVar(void)
0x18000e2c2  jmp     loc_18000E21B
0x18000e2c7  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18000e2ce  lea     rcx, [rbp+57h+DestStr]; pExceptionObject
0x18000e2d2  call    _CxxThrowException_0
0x18000e2d8  lea     r8, dword_1800D7C78; struct wil_details_FeatureReportingCache *
0x18000e2df  mov     edx, 0F399C3h; unsigned int
0x18000e2e4  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; pv
0x18000e2eb  call    ?QueueBackgroundUsageReporting@EnabledStateManager@details@wil@@QEAAXIPEAUwil_details_FeatureReportingCache@@@Z; wil::details::EnabledStateManager::QueueBackgroundUsageReporting(uint,wil_details_FeatureReportingCache *)
0x18000e2f0  jmp     loc_18000DF04
0x18000e2f5  lea     rdx, _TI1?AVCX_Exception@@; pThrowInfo
0x18000e2fc  lea     rcx, [rbp+57h+DestStr]; pExceptionObject
0x18000e300  call    _CxxThrowException_0
0x18000e306  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_aa194dc0bf891154933407eb98fb868a_@@CA@PEAX@Z; void (*)(void *)
0x18000e30d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
  ... truncated ...
```
