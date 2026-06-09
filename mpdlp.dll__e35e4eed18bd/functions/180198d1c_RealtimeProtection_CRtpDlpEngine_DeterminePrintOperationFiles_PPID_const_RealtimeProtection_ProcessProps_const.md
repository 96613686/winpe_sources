# RealtimeProtection::CRtpDlpEngine::DeterminePrintOperationFiles(PPID const &,RealtimeProtection::ProcessProps const &,wchar_t const *,RealtimeProtection::MpDlpOperationOrigin,RealtimeProtection::ActionEnforcementState const &,std::vector<RealtimeProtection::FileProps,std::allocator<RealtimeProtection::FileProps>> &)

- ea: `0x180198d1c`
- end: `0x1801993eb`
- name: `?DeterminePrintOperationFiles@CRtpDlpEngine@RealtimeProtection@@AEAAJAEBUPPID@@AEBUProcessProps@2@PEB_WW4MpDlpOperationOrigin@2@AEBUActionEnforcementState@2@AEAV?$vector@UFileProps@RealtimeProtection@@V?$allocator@UFileProps@RealtimeProtection@@@std@@@std@@@Z`
- size: `1743`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800be984`

## callees

- `0x180005c28`
- `0x1800096ac`
- `0x180040cd8`
- `0x180046d10`
- `0x180079dc0`
- `0x1800809d0`
- `0x180089510`
- `0x1800943fc`
- `0x1800a46ec`
- `0x1800a7df0`
- `0x1800b3710`
- `0x1800b60f0`
- `0x1800b8fcc`
- `0x18010cb40`
- `0x180184b30`
- `0x18019820c`
- `0x180198d1c`
- `0x1801ab2f0`
- `0x1801d7b0c`
- `0x1801d8454`

## import_xrefs

- `MpClient!MpConfigClose` at `0x180198e53`
- `MpClient!MpConfigClose` at `0x180198f05`
- `MpClient!MpConfigClose` at `0x180198f5f`
- `MpClient!MpConfigClose` at `0x18019901f`
- `MpClient!MpConfigClose` at `0x180199039`
- `MpClient!MpConfigClose` at `0x180198e53`
- `MpClient!MpConfigClose` at `0x180198f05`
- `MpClient!MpConfigClose` at `0x180198f5f`
- `MpClient!MpConfigClose` at `0x18019901f`
- `MpClient!MpConfigClose` at `0x180199039`
- `MpClient!MpConfigOpen` at `0x180198e10`
- `MpClient!MpConfigOpen` at `0x180198e10`

## string_xrefs

- `0x180198e09`: `Miscellaneous Configuration`
- `0x180198e76`: `DlpDisablePrintFileHeuristic`
- `0x180199322`: `Print file heuristic returned hr=%#lx for app=%ls, docname=%ls, EnforcePrintFileHeuristic = %d.`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::CRtpDlpEngine::DeterminePrintOperationFiles(
        __int64 a1,
        unsigned int *a2,
        __int64 *a3,
        __int64 a4,
        int a5,
        __int64 a6,
        __int64 a7)
{
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  unsigned int v15; // ebx
  unsigned int ValueDword; // eax
  __int64 v17; // rdx
  enum RealtimeProtection::PrintFileHeuristicPolicy *v18; // r8
  __int64 v19; // r9
  unsigned int v20; // ebx
  PVOID *v21; // r10
  int PrintFileHeuristicPolicy; // eax
  __int64 v23; // rdx
  bool *v24; // r8
  __int64 v25; // r9
  unsigned int v26; // ebx
  int v27; // r14d
  int EngineConfigForPrintFileHeuristicEnforcement; // eax
  char v29; // al
  int v30; // eax
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v33; // r9
  int v34; // r9d
  __int64 v35; // rax
  __int64 *v36; // r8
  PVOID *v37; // rcx
  __int64 v38; // [rsp+0h] [rbp-1B8h] BYREF
  __int64 v39; // [rsp+20h] [rbp-198h]
  _BYTE v40[4]; // [rsp+C0h] [rbp-F8h] BYREF
  char v41[8]; // [rsp+C4h] [rbp-F4h] BYREF
  int v42; // [rsp+CCh] [rbp-ECh] BYREF
  int v43; // [rsp+D0h] [rbp-E8h] BYREF
  int v44; // [rsp+D4h] [rbp-E4h] BYREF
  int v45; // [rsp+D8h] [rbp-E0h] BYREF
  int v46; // [rsp+DCh] [rbp-DCh] BYREF
  int v47; // [rsp+E0h] [rbp-D8h] BYREF
  __int64 v48; // [rsp+E8h] [rbp-D0h] BYREF
  __int64 v49; // [rsp+F0h] [rbp-C8h] BYREF
  __int64 v50; // [rsp+F8h] [rbp-C0h] BYREF
  __int64 v51; // [rsp+100h] [rbp-B8h] BYREF
  __int64 v52; // [rsp+108h] [rbp-B0h] BYREF
  __int64 v53; // [rsp+110h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+118h] [rbp-A0h] BYREF
  __int64 v55; // [rsp+120h] [rbp-98h] BYREF
  __int64 v56; // [rsp+128h] [rbp-90h] BYREF
  __int64 v57; // [rsp+130h] [rbp-88h] BYREF
  const std::exception *v58; // [rsp+138h] [rbp-80h] BYREF
  _BYTE v59[16]; // [rsp+140h] [rbp-78h] BYREF
  _BYTE v60[24]; // [rsp+150h] [rbp-68h] BYREF
  __int64 v61; // [rsp+168h] [rbp-50h] BYREF

  v48 = a7;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 633, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, a2[2]);
  if ( !a4 )
    return 0;
  *(_DWORD *)&v41[4] = 0;
  if ( a5 == 6 )
  {
    v27 = 1;
    v26 = RealtimeProtection::DlpProcessCache::SetPrintFileHeuristicPolicy(a2);
  }
  else
  {
    if ( (unsigned int)RealtimeProtection::DlpPlugin::IsKillbitActive(0x20000000) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 634, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
      return 0;
    }
    v61 = 0;
    v11 = MpConfigOpen(L"Miscellaneous Configuration", &v61);
    v15 = v11;
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          635,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)v11);
      if ( v61 )
        MpConfigClose(v61, v12, v13, v14);
      return v15;
    }
    *(_DWORD *)v41 = 0;
    ValueDword = MpConfigGetValueDword(v61, L"DlpDisablePrintFileHeuristic", v41, 0);
    v20 = ValueDword;
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        636,
        &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
        ValueDword,
        *(_DWORD *)v41);
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !v20 && *(_DWORD *)v41 == 1 )
    {
      if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 2) != 0 )
        WPP_SF_(v21[2], 637, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids);
      if ( v61 )
        MpConfigClose(v61, v17, v18, v19);
      return 0;
    }
    PrintFileHeuristicPolicy = RealtimeProtection::DlpProcessCache::GetPrintFileHeuristicPolicy(
                                 (RealtimeProtection::DlpProcessCache *)a2,
                                 (const struct PPID *)&v41[4],
                                 v18);
    v26 = PrintFileHeuristicPolicy;
    if ( PrintFileHeuristicPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          638,
          &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          (unsigned int)PrintFileHeuristicPolicy);
      if ( v61 )
        MpConfigClose(v61, v23, v24, v25);
      return v26;
    }
    v27 = *(_DWORD *)&v41[4];
    if ( !*(_DWORD *)&v41[4] )
    {
      v40[0] = 0;
      EngineConfigForPrintFileHeuristicEnforcement = RealtimeProtection::DlpEngineUtils::GetEngineConfigForPrintFileHeuristicEnforcement(
                                                       (RealtimeProtection::DlpEngineUtils *)a2,
                                                       (const struct PPID *)v40,
                                                       v24);
      if ( EngineConfigForPrintFileHeuristicEnforcement >= 0 )
      {
        v29 = v40[0];
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            639,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)EngineConfigForPrintFileHeuristicEnforcement);
        v29 = 0;
      }
      v27 = 2 - (v29 != 0);
      v30 = RealtimeProtection::DlpProcessCache::SetPrintFileHeuristicPolicy(a2);
      v26 = v30;
      if ( v30 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            640,
            &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
            (unsigned int)v30);
        if ( v61 )
          MpConfigClose(v61, v23, v24, v25);
        return v26;
      }
    }
    if ( v61 )
      MpConfigClose(v61, v23, v24, v25);
  }
  try
  {
    if ( v27 == 1 )
    {
      v31 = std::vector<RealtimeProtection::FileProps>::vector<RealtimeProtection::FileProps>(v60, a6 + 88);
      v26 = RealtimeProtection::CRtpDlpEngine::DetermineEnforcedFileByPrintJobName(v32, v31, a4, v48);
      if ( v26 == -2147023728
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        LODWORD(v33) = (_DWORD)a3;
        if ( (unsigned __int64)a3[3] > 7 )
          v33 = *a3;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          641,
          (unsigned int)&WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids,
          v33,
          a4);
      }
    }
    if ( g_pcsAsimovLock )
    {
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v59);
      if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
        && (unsigned __int8)tlgKeywordOn(*(_QWORD *)&g_hMpAsimovProvider, 0x400000000000LL) )
      {
        *(_DWORD *)&v41[4] = v27;
        *(_DWORD *)v41 = v26;
        v50 = a4;
        v35 = (__int64)a3;
        if ( (unsigned __int64)a3[3] > 7 )
          v35 = *a3;
        v51 = v35;
        v42 = *((_DWORD *)g_aAsimov + 18);
        v43 = *((_DWORD *)g_aAsimov + 17);
        v44 = *((_DWORD *)g_aAsimov + 16);
        v45 = *((unsigned __int8 *)g_aAsimov + 60);
        v46 = *((unsigned __int8 *)g_aAsimov + 59);
        v47 = *((unsigned __int8 *)g_aAsimov + 58);
        LODWORD(v48) = *((unsigned __int8 *)g_aAsimov + 57);
        LODWORD(v61) = *((unsigned __int8 *)g_aAsimov + 56);
        v52 = *((_QWORD *)g_aAsimov + 6);
        v53 = *((_QWORD *)g_aAsimov + 5);
        v54 = *((_QWORD *)g_aAsimov + 4);
        v55 = *((_QWORD *)g_aAsimov + 3);
        v56 = *((_QWORD *)g_aAsimov + 2);
        v57 = *((_QWORD *)g_aAsimov + 1);
        v49 = 0x2000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v34,
          (int)&dword_1802C403C,
          (__int64)&v49,
          (__int64)&v57,
          (__int64)&v56,
          (__int64)&v55,
          (__int64)&v54,
          (__int64)&v53,
          (__int64)&v52,
          (__int64)&v61,
          (__int64)&v48,
          (__int64)&v47,
          (__int64)&v46,
          (__int64)&v45,
          (__int64)&v44,
          (__int64)&v43,
          (__int64)&v42,
          (__int64)&v51,
          (__int64)&v50,
          (__int64)v41,
          (__int64)&v41[4]);
      }
      CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::~CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(v59);
    }
    v36 = a3;
    if ( (unsigned __int64)a3[3] > 7 )
      v36 = (__int64 *)*a3;
    LODWORD(v39) = v27;
    RealtimeProtection::MpLogMessageImpl(
      (RealtimeProtection *)L"Print file heuristic returned hr=%#lx for app=%ls, docname=%ls, EnforcePrintFileHeuristic = %d.",
      (const wchar_t *)v26,
      v36,
      a4,
      v39);
    v37 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      if ( (unsigned __int64)a3[3] > 7 )
        a3 = (__int64 *)*a3;
      WPP_SF_DSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)a3, a4, v27);
      v37 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  catch ( const std::exception *v58 )
  {
    CommonUtil::HrFromStdException(v58, (const struct std::exception *)&v38);
  }
  catch ( ... )
  {
    *(_DWORD *)v41 = -2147467259;
    v26 = -2147467259;
    v37 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_76;
  }
  if ( (v26 & 0x80000000) != 0 )
  {
LABEL_76:
    if ( v37 != &WPP_GLOBAL_Control && (*((_BYTE *)v37 + 28) & 1) != 0 )
      WPP_SF_d(v37[2], 643, &WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids, v26);
  }
  return v26;
}

```

## disassembly

```asm
0x180198d1c  push    rbx
0x180198d1e  push    rsi
0x180198d1f  push    rdi
0x180198d20  push    r12
0x180198d22  push    r13
0x180198d24  push    r14
0x180198d26  push    r15
0x180198d28  sub     rsp, 180h
0x180198d2f  mov     rax, cs:__security_cookie
0x180198d36  xor     rax, rsp
0x180198d39  mov     [rsp+1B8h+var_48], rax
0x180198d41  mov     r12, r9
0x180198d44  mov     rsi, r8
0x180198d47  mov     r15, rdx
0x180198d4a  mov     r13, [rsp+1B8h+arg_28]
0x180198d52  mov     rax, [rsp+1B8h+arg_30]
0x180198d5a  mov     [rsp+1B8h+var_D0], rax
0x180198d62  lea     rdi, WPP_GLOBAL_Control
0x180198d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180198d70  cmp     rcx, rdi
0x180198d73  jz      short loc_180198D94
0x180198d75  test    byte ptr [rcx+1Ch], 10h
0x180198d79  jz      short loc_180198D94
0x180198d7b  mov     r9d, [rdx+8]
0x180198d7f  mov     edx, 279h
0x180198d84  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180198d8b  mov     rcx, [rcx+10h]
0x180198d8f  call    WPP_SF_q
0x180198d94  test    r12, r12
0x180198d97  jnz     short loc_180198DA0
0x180198d99  xor     eax, eax
0x180198d9b  jmp     loc_1801993C8
0x180198da0  mov     dword ptr [rsp+1B8h+var_F4+4], 0
0x180198dab  cmp     [rsp+1B8h+arg_20], 6
0x180198db3  jz      loc_180199041
0x180198db9  mov     ecx, 20000000h
0x180198dbe  call    ?IsKillbitActive@DlpPlugin@RealtimeProtection@@YAHW4FeatureKillbit@@@Z; RealtimeProtection::DlpPlugin::IsKillbitActive(FeatureKillbit)
0x180198dc3  test    eax, eax
0x180198dc5  jz      short loc_180198DF5
0x180198dc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180198dce  cmp     rcx, rdi
0x180198dd1  jz      short loc_180198DEE
0x180198dd3  test    byte ptr [rcx+1Ch], 2
0x180198dd7  jz      short loc_180198DEE
0x180198dd9  mov     edx, 27Ah
0x180198dde  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180198de5  mov     rcx, [rcx+10h]
0x180198de9  call    WPP_SF_
0x180198dee  xor     eax, eax
0x180198df0  jmp     loc_1801993C8
0x180198df5  mov     [rsp+1B8h+var_50], 0
0x180198e01  lea     rdx, [rsp+1B8h+var_50]
0x180198e09  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x180198e10  call    cs:__imp_MpConfigOpen
0x180198e16  mov     ebx, eax
0x180198e18  test    eax, eax
0x180198e1a  jns     short loc_180198E60
0x180198e1c  mov     rcx, cs:WPP_GLOBAL_Control
0x180198e23  cmp     rcx, rdi
0x180198e26  jz      short loc_180198E46
0x180198e28  test    byte ptr [rcx+1Ch], 1
0x180198e2c  jz      short loc_180198E46
0x180198e2e  mov     edx, 27Bh
0x180198e33  mov     r9d, eax
0x180198e36  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180198e3d  mov     rcx, [rcx+10h]
0x180198e41  call    WPP_SF_d
0x180198e46  mov     rcx, [rsp+1B8h+var_50]
0x180198e4e  test    rcx, rcx
0x180198e51  jz      short loc_180198E59
0x180198e53  call    cs:__imp_MpConfigClose
0x180198e59  mov     eax, ebx
0x180198e5b  jmp     loc_1801993C8
0x180198e60  mov     dword ptr [rsp+1B8h+var_F4], 0
0x180198e6b  xor     r9d, r9d
0x180198e6e  lea     r8, [rsp+1B8h+var_F4]
0x180198e76  lea     rdx, aDlpdisableprin_0; "DlpDisablePrintFileHeuristic"
0x180198e7d  mov     rcx, [rsp+1B8h+var_50]
0x180198e85  call    MpConfigGetValueDword
0x180198e8a  mov     ebx, eax
0x180198e8c  mov     r10, cs:WPP_GLOBAL_Control
0x180198e93  cmp     r10, rdi
0x180198e96  jz      short loc_180198EC9
0x180198e98  test    byte ptr [r10+1Ch], 4
0x180198e9d  jz      short loc_180198EC9
0x180198e9f  mov     edx, 27Ch
0x180198ea4  mov     ecx, dword ptr [rsp+1B8h+var_F4]
0x180198eab  mov     dword ptr [rsp+1B8h+var_198], ecx
0x180198eaf  mov     r9d, eax
0x180198eb2  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180198eb9  mov     rcx, [r10+10h]
0x180198ebd  call    WPP_SF_Dd
0x180198ec2  mov     r10, cs:WPP_GLOBAL_Control
0x180198ec9  test    ebx, ebx
0x180198ecb  jnz     short loc_180198F12
0x180198ecd  cmp     dword ptr [rsp+1B8h+var_F4], 1
0x180198ed5  jnz     short loc_180198F12
0x180198ed7  cmp     r10, rdi
0x180198eda  jz      short loc_180198EF8
0x180198edc  test    byte ptr [r10+1Ch], 2
0x180198ee1  jz      short loc_180198EF8
0x180198ee3  mov     edx, 27Dh
0x180198ee8  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180198eef  mov     rcx, [r10+10h]
0x180198ef3  call    WPP_SF_
0x180198ef8  mov     rcx, [rsp+1B8h+var_50]
0x180198f00  test    rcx, rcx
0x180198f03  jz      short loc_180198F0B
0x180198f05  call    cs:__imp_MpConfigClose
0x180198f0b  xor     eax, eax
0x180198f0d  jmp     loc_1801993C8
0x180198f12  lea     rdx, [rsp+1B8h+var_F4+4]; struct PPID *
0x180198f1a  mov     rcx, r15; this
0x180198f1d  call    ?GetPrintFileHeuristicPolicy@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@PEAW4PrintFileHeuristicPolicy@2@@Z; RealtimeProtection::DlpProcessCache::GetPrintFileHeuristicPolicy(PPID const &,RealtimeProtection::PrintFileHeuristicPolicy *)
0x180198f22  mov     ebx, eax
0x180198f24  test    eax, eax
0x180198f26  jns     short loc_180198F6C
0x180198f28  mov     rcx, cs:WPP_GLOBAL_Control
0x180198f2f  cmp     rcx, rdi
0x180198f32  jz      short loc_180198F52
0x180198f34  test    byte ptr [rcx+1Ch], 1
0x180198f38  jz      short loc_180198F52
0x180198f3a  mov     edx, 27Eh
0x180198f3f  mov     r9d, eax
0x180198f42  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180198f49  mov     rcx, [rcx+10h]
0x180198f4d  call    WPP_SF_d
0x180198f52  mov     rcx, [rsp+1B8h+var_50]
0x180198f5a  test    rcx, rcx
0x180198f5d  jz      short loc_180198F65
0x180198f5f  call    cs:__imp_MpConfigClose
0x180198f65  mov     eax, ebx
0x180198f67  jmp     loc_1801993C8
0x180198f6c  mov     r14d, dword ptr [rsp+1B8h+var_F4+4]
0x180198f74  test    r14d, r14d
0x180198f77  jnz     loc_18019902C
0x180198f7d  mov     [rsp+1B8h+var_F8], r14b
0x180198f85  lea     rdx, [rsp+1B8h+var_F8]; struct PPID *
0x180198f8d  mov     rcx, r15; this
0x180198f90  call    ?GetEngineConfigForPrintFileHeuristicEnforcement@DlpEngineUtils@RealtimeProtection@@YAJAEBUPPID@@PEA_N@Z; RealtimeProtection::DlpEngineUtils::GetEngineConfigForPrintFileHeuristicEnforcement(PPID const &,bool *)
0x180198f95  test    eax, eax
0x180198f97  jns     short loc_180198FC7
0x180198f99  mov     rcx, cs:WPP_GLOBAL_Control
0x180198fa0  cmp     rcx, rdi
0x180198fa3  jz      short loc_180198FC3
0x180198fa5  test    byte ptr [rcx+1Ch], 1
0x180198fa9  jz      short loc_180198FC3
0x180198fab  mov     edx, 27Fh
0x180198fb0  mov     r9d, eax
0x180198fb3  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180198fba  mov     rcx, [rcx+10h]
0x180198fbe  call    WPP_SF_d
0x180198fc3  xor     al, al
0x180198fc5  jmp     short loc_180198FCE
0x180198fc7  mov     al, [rsp+1B8h+var_F8]
0x180198fce  neg     al
0x180198fd0  sbb     r14d, r14d
0x180198fd3  add     r14d, 2
0x180198fd7  mov     edx, r14d
0x180198fda  mov     rcx, r15
0x180198fdd  call    ?SetPrintFileHeuristicPolicy@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@W4PrintFileHeuristicPolicy@2@@Z; RealtimeProtection::DlpProcessCache::SetPrintFileHeuristicPolicy(PPID const &,RealtimeProtection::PrintFileHeuristicPolicy)
0x180198fe2  mov     ebx, eax
0x180198fe4  test    eax, eax
0x180198fe6  jns     short loc_18019902C
0x180198fe8  mov     rcx, cs:WPP_GLOBAL_Control
0x180198fef  cmp     rcx, rdi
0x180198ff2  jz      short loc_180199012
0x180198ff4  test    byte ptr [rcx+1Ch], 1
0x180198ff8  jz      short loc_180199012
0x180198ffa  mov     edx, 280h
0x180198fff  mov     r9d, eax
0x180199002  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x180199009  mov     rcx, [rcx+10h]
0x18019900d  call    WPP_SF_d
0x180199012  mov     rcx, [rsp+1B8h+var_50]
0x18019901a  test    rcx, rcx
0x18019901d  jz      short loc_180199025
0x18019901f  call    cs:__imp_MpConfigClose
0x180199025  mov     eax, ebx
0x180199027  jmp     loc_1801993C8
0x18019902c  mov     rcx, [rsp+1B8h+var_50]
0x180199034  test    rcx, rcx
0x180199037  jz      short loc_180199053
0x180199039  call    cs:__imp_MpConfigClose
0x18019903f  jmp     short loc_180199053
0x180199041  mov     edx, 1
0x180199046  mov     r14d, edx
0x180199049  mov     rcx, r15
0x18019904c  call    ?SetPrintFileHeuristicPolicy@DlpProcessCache@RealtimeProtection@@YAJAEBUPPID@@W4PrintFileHeuristicPolicy@2@@Z; RealtimeProtection::DlpProcessCache::SetPrintFileHeuristicPolicy(PPID const &,RealtimeProtection::PrintFileHeuristicPolicy)
0x180199051  mov     ebx, eax
0x180199053  cmp     r14d, 1
0x180199057  jnz     short loc_1801990BF
0x180199059  lea     rdx, [r13+58h]
0x18019905d  lea     rcx, [rsp+1B8h+var_68]
0x180199065  call    ??0?$vector@UFileProps@RealtimeProtection@@V?$allocator@UFileProps@RealtimeProtection@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<RealtimeProtection::FileProps>::vector<RealtimeProtection::FileProps>(std::vector<RealtimeProtection::FileProps> const &)
0x18019906a  mov     r9, [rsp+1B8h+var_D0]
0x180199072  mov     r8, r12
0x180199075  mov     rdx, rax
0x180199078  call    ?DetermineEnforcedFileByPrintJobName@CRtpDlpEngine@RealtimeProtection@@AEAAJV?$vector@UFileProps@RealtimeProtection@@V?$allocator@UFileProps@RealtimeProtection@@@std@@@std@@PEB_WAEAV34@@Z; RealtimeProtection::CRtpDlpEngine::DetermineEnforcedFileByPrintJobName(std::vector<RealtimeProtection::FileProps>,wchar_t const *,std::vector<RealtimeProtection::FileProps> &)
0x18019907d  mov     ebx, eax
0x18019907f  cmp     eax, 80070490h
0x180199084  jnz     short loc_1801990BF
0x180199086  mov     rcx, cs:WPP_GLOBAL_Control
0x18019908d  cmp     rcx, rdi
0x180199090  jz      short loc_1801990BF
0x180199092  test    byte ptr [rcx+1Ch], 10h
0x180199096  jz      short loc_1801990BF
0x180199098  mov     r9, rsi
0x18019909b  cmp     qword ptr [rsi+18h], 7
0x1801990a0  jbe     short loc_1801990A5
0x1801990a2  mov     r9, [rsi]
0x1801990a5  mov     edx, 281h
0x1801990aa  mov     [rsp+1B8h+var_198], r12
0x1801990af  lea     r8, WPP_83c2c63735003eb06613ab19fec12cd2_Traceguids
0x1801990b6  mov     rcx, [rcx+10h]
0x1801990ba  call    WPP_SF_SS
0x1801990bf  mov     rdx, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x1801990c6  test    rdx, rdx
0x1801990c9  jz      loc_18019930B
0x1801990cf  lea     rcx, [rsp+1B8h+var_78]
0x1801990d7  call    ??0?$CGenericAutoLock@UCMpCriticalSectionFunctor@CommonUtil@@@CommonUtil@@QEAA@AEBVCMpCriticalSection@1@W4ENUM_LOCK_INITIAL_STATE@01@@Z; CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>(CommonUtil::CMpCriticalSection const &,CommonUtil::CGenericAutoLock<CommonUtil::CMpCriticalSectionFunctor>::ENUM_LOCK_INITIAL_STATE)
0x1801990dc  mov     r9, cs:g_hMpAsimovProvider
0x1801990e3  cmp     dword ptr [r9], 5
0x1801990e7  jbe     loc_1801992FE
0x1801990ed  mov     rdx, 400000000000h
0x1801990f7  mov     rcx, r9
0x1801990fa  call    _tlgKeywordOn
0x1801990ff  test    al, al
0x180199101  jz      loc_1801992FE
0x180199107  mov     dword ptr [rsp+1B8h+var_F4+4], r14d
0x18019910f  mov     dword ptr [rsp+1B8h+var_F4], ebx
0x180199116  mov     [rsp+1B8h+var_C0], r12
0x18019911e  mov     rax, rsi
0x180199121  cmp     qword ptr [rsi+18h], 7
0x180199126  jbe     short loc_18019912B
0x180199128  mov     rax, [rsi]
0x18019912b  mov     [rsp+1B8h+var_B8], rax
0x180199133  mov     rcx, cs:?g_aAsimov@@3PEAVCMpAsimov@@EA; CMpAsimov * g_aAsimov
0x18019913a  mov     eax, [rcx+48h]
0x18019913d  mov     dword ptr [rsp+1B8h+var_EC], eax
0x180199144  mov     eax, [rcx+44h]
0x180199147  mov     dword ptr [rsp+1B8h+var_EC+4], eax
0x18019914e  mov     eax, [rcx+40h]
0x180199151  mov     dword ptr [rsp+1B8h+var_E4], eax
0x180199158  movzx   eax, byte ptr [rcx+3Ch]
0x18019915c  mov     dword ptr [rsp+1B8h+var_E4+4], eax
0x180199163  movzx   eax, byte ptr [rcx+3Bh]
0x180199167  mov     [rsp+1B8h+var_DC], eax
0x18019916e  movzx   eax, byte ptr [rcx+3Ah]
0x180199172  mov     [rsp+1B8h+var_D8], eax
0x180199179  movzx   eax, byte ptr [rcx+39h]
0x18019917d  mov     dword ptr [rsp+1B8h+var_D0], eax
0x180199184  movzx   eax, byte ptr [rcx+38h]
0x180199188  mov     dword ptr [rsp+1B8h+var_50], eax
0x18019918f  mov     rax, [rcx+30h]
0x180199193  mov     [rsp+1B8h+var_B0], rax
0x18019919b  mov     rax, [rcx+28h]
0x18019919f  mov     [rsp+1B8h+var_A8], rax
0x1801991a7  mov     rax, [rcx+20h]
0x1801991ab  mov     [rsp+1B8h+var_A0], rax
0x1801991b3  mov     rax, [rcx+18h]
0x1801991b7  mov     [rsp+1B8h+var_98], rax
0x1801991bf  mov     rax, [rcx+10h]
0x1801991c3  mov     [rsp+1B8h+var_90], rax
0x1801991cb  mov     rax, [rcx+8]
0x1801991cf  mov     [rsp+1B8h+var_88], rax
0x1801991d7  mov     [rsp+1B8h+var_C8], 2000000h
0x1801991e3  lea     rax, [rsp+1B8h+var_F4+4]
0x1801991eb  mov     [rsp+1B8h+var_108], rax; __int64
0x1801991f3  lea     rax, [rsp+1B8h+var_F4]
0x1801991fb  mov     [rsp+1B8h+var_110], rax; __int64
0x180199203  lea     rax, [rsp+1B8h+var_C0]
0x18019920b  mov     [rsp+1B8h+var_118], rax; __int64
0x180199213  lea     rax, [rsp+1B8h+var_B8]
0x18019921b  mov     [rsp+1B8h+var_120], rax; __int64
0x180199223  lea     rax, [rsp+1B8h+var_EC]
0x18019922b  mov     [rsp+1B8h+var_128], rax; __int64
0x180199233  lea     rax, [rsp+1B8h+var_EC+4]
0x18019923b  mov     [rsp+1B8h+var_130], rax; __int64
0x180199243  lea     rax, [rsp+1B8h+var_E4]
0x18019924b  mov     [rsp+1B8h+var_138], rax; __int64
0x180199253  lea     rax, [rsp+1B8h+var_E4+4]
0x18019925b  mov     [rsp+1B8h+var_140], rax; __int64
0x180199260  lea     rax, [rsp+1B8h+var_DC]
0x180199268  mov     [rsp+1B8h+var_148], rax; __int64
0x18019926d  lea     rax, [rsp+1B8h+var_D8]
0x180199275  mov     [rsp+1B8h+var_150], rax; __int64
0x18019927a  lea     rax, [rsp+1B8h+var_D0]
0x180199282  mov     [rsp+1B8h+var_158], rax; __int64
0x180199287  lea     rax, [rsp+1B8h+var_50]
0x18019928f  mov     [rsp+1B8h+var_160], rax; __int64
0x180199294  lea     rax, [rsp+1B8h+var_B0]
0x18019929c  mov     [rsp+1B8h+var_168], rax; __int64
0x1801992a1  lea     rax, [rsp+1B8h+var_A8]
0x1801992a9  mov     [rsp+1B8h+var_170], rax; __int64
0x1801992ae  lea     rax, [rsp+1B8h+var_A0]
0x1801992b6  mov     [rsp+1B8h+var_178], rax; __int64
0x1801992bb  lea     rax, [rsp+1B8h+var_98]
0x1801992c3  mov     [rsp+1B8h+var_180], rax; __int64
0x1801992c8  lea     rax, [rsp+1B8h+var_90]
  ... truncated ...
```
