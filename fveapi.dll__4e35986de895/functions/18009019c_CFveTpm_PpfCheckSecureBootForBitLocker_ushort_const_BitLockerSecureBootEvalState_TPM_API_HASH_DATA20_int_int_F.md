# CFveTpm::PpfCheckSecureBootForBitLocker(ushort const *,BitLockerSecureBootEvalState *,_TPM_API_HASH_DATA20 *,int *,int *,_FVE_DATUM_PCR_DATA * *)

- ea: `0x18009019c`
- end: `0x180090eb1`
- name: `?PpfCheckSecureBootForBitLocker@CFveTpm@@QEAAJPEBGPEAW4BitLockerSecureBootEvalState@@PEAU_TPM_API_HASH_DATA20@@PEAH3PEAPEAU_FVE_DATUM_PCR_DATA@@@Z`
- size: `3349`
- prototype: `int(CFveTpm *__hidden this, const unsigned __int16 *, enum BitLockerSecureBootEvalState *, struct _TPM_API_HASH_DATA20 *, int *, int *, struct _FVE_DATUM_PCR_DATA **)`
- caller_count: `6`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x18005a8b8`
- `0x18007b7a8`
- `0x180080ae8`
- `0x18008b524`
- `0x1800a0988`
- `0x1800ad9fc`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x1800184ac`
- `0x180019128`
- `0x180037edc`
- `0x18003ed0c`
- `0x18003ed44`
- `0x18004dba8`
- `0x18004dfe4`
- `0x18005e158`
- `0x180076b1c`
- `0x18008686c`
- `0x18009019c`
- `0x18009f470`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `pcrpf!PpfGetPredictionsForInstance` at `0x180090411`
- `pcrpf!PpfGetPredictionsForInstance` at `0x180090411`
- `pcrpf!PpfFreePredictions` at `0x180090a80`
- `pcrpf!PpfFreePredictions` at `0x180090a80`
- `pcrpf!PpfGetPredictions` at `0x1800904b7`
- `pcrpf!PpfGetPredictions` at `0x1800904b7`
- `pcrpf!PpfTransformContextGetString` at `0x1800907e2`
- `pcrpf!PpfTransformContextGetString` at `0x180090c80`
- `pcrpf!PpfTransformContextGetString` at `0x1800907e2`
- `pcrpf!PpfTransformContextGetString` at `0x180090c80`

## string_xrefs

- `0x1800905a4`: `_FvePolicy->ReOpen`
- `0x180090a6c`: `_FvePolicy->ReOpen`
- `0x1800907db`: `BootMgFwFilePath`
- `0x180090c79`: `BootMgFwFilePath`

## pseudocode

```c
__int64 __fastcall CFveTpm::PpfCheckSecureBootForBitLocker(
        CFveTpm *this,
        const unsigned __int16 *a2,
        enum BitLockerSecureBootEvalState *a3,
        struct _TPM_API_HASH_DATA20 *a4,
        int *a5,
        int *a6)
{
  CFveTpm *v6; // rsi
  CFveTpm *v8; // r15
  unsigned int CanFveUsePpf; // eax
  int PredictionsForInstance; // ebx
  PVOID *v11; // rcx
  const char *v12; // rax
  __int64 v13; // rdx
  unsigned int v14; // edx
  PVOID *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rax
  unsigned int v18; // eax
  __int64 v19; // rax
  unsigned int v20; // eax
  PVOID *v21; // rcx
  unsigned int v22; // r12d
  CFveTpm *v23; // rax
  CFveTpm *v24; // rax
  unsigned int v25; // eax
  PVOID *v26; // r10
  char v27; // r13
  unsigned int v28; // r15d
  __int64 v29; // rdi
  __int64 v30; // r14
  unsigned int v31; // edx
  void *v32; // rdx
  __int64 v33; // rdx
  unsigned int v34; // eax
  const char *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rax
  int v38; // eax
  unsigned int v39; // edi
  const char *v41; // rax
  __int64 v42; // rdx
  __int64 v43; // rdx
  enum BitLockerSecureBootEvalState *v44; // r14
  __int64 v45; // rdi
  unsigned int v46; // edx
  unsigned int String; // eax
  void *v48; // rdx
  unsigned int EFIBootMgrFilePath; // eax
  unsigned int v50; // eax
  char *v51; // [rsp+28h] [rbp-D8h]
  char *v52; // [rsp+28h] [rbp-D8h]
  char *v53; // [rsp+28h] [rbp-D8h]
  bool v54; // [rsp+40h] [rbp-C0h] BYREF
  CFveTpm *v55; // [rsp+48h] [rbp-B8h]
  enum BitLockerSecureBootEvalState *v56; // [rsp+50h] [rbp-B0h]
  char *v57; // [rsp+58h] [rbp-A8h]
  int *v58; // [rsp+60h] [rbp-A0h]
  unsigned __int16 *v59; // [rsp+68h] [rbp-98h] BYREF
  char *v60; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v61; // [rsp+78h] [rbp-88h] BYREF
  int v62; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned __int16 v63[264]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v6 = 0;
  v58 = a5;
  v56 = a3;
  v8 = this;
  v55 = this;
  v57 = (char *)a6;
  v59 = 0;
  v62 = 0;
  v54 = 0;
  v61 = 0;
  v60 = 0;
  memset_0(v63, 0, 0x208u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 237, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
  CanFveUsePpf = CFveApiBase::CanFveUsePpf(&v54);
  PredictionsForInstance = CanFveUsePpf;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 238, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, CanFveUsePpf);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( PredictionsForInstance < 0 )
  {
    v12 = "CanFveUsePpf";
    v13 = 4222;
LABEL_9:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
      (const char *)(unsigned int)PredictionsForInstance,
      (int)v12,
      v51);
LABEL_10:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_114;
  }
  if ( !v54 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 2) != 0 )
      WPP_SF_(v11[2], 239, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
    PredictionsForInstance = -2147024809;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x1083,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
      (const char *)0x80070057LL,
      (int)"FVE cannot use PPF",
      v51);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_114;
    v16 = 240;
    goto LABEL_18;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
    WPP_SF_(v11[2], 241, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
  v17 = *((_QWORD *)v8 + 1);
  if ( v17 )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v17 + 8) + 176LL) + 56LL))(*(_QWORD *)(*(_QWORD *)(v17 + 8) + 176LL));
    PredictionsForInstance = v18;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 242, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v18);
    if ( PredictionsForInstance < 0 )
    {
      v12 = "_FvePolicy->Close";
      v13 = 4240;
      goto LABEL_9;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
  {
    PredictionsForInstance = PpfGetPredictionsForInstance(a2, L"BitLocker", 2176, 0xFFFF, &v59);
    if ( PredictionsForInstance < 0 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x10A1,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
        (const char *)(unsigned int)PredictionsForInstance,
        (int)"PpfGetPredictionsForInstance",
        v51);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_114;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          243,
          &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
          (unsigned int)PredictionsForInstance);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 )
        goto LABEL_114;
      v16 = 244;
      goto LABEL_18;
    }
  }
  else
  {
    PredictionsForInstance = PpfGetPredictions(L"BitLocker", 2176, 0xFFFF, &v59);
    if ( PredictionsForInstance < 0 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x10AD,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
        (const char *)(unsigned int)PredictionsForInstance,
        (int)"PpfGetPredictions",
        v51);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_114;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          245,
          &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
          (unsigned int)PredictionsForInstance);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 )
        goto LABEL_114;
      v16 = 246;
      goto LABEL_18;
    }
  }
  v19 = *((_QWORD *)v8 + 1);
  if ( v19 )
  {
    v20 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v19 + 8) + 176LL) + 64LL))(*(_QWORD *)(*(_QWORD *)(v19 + 8) + 176LL));
    PredictionsForInstance = v20;
    v21 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 247, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v20);
      v21 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( PredictionsForInstance < 0 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x10B5,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
        (const char *)(unsigned int)PredictionsForInstance,
        (int)"_FvePolicy->ReOpen",
        v51);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_114;
    }
  }
  else
  {
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
  {
    WPP_SF_(v21[2], 248, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
    v21 = (PVOID *)WPP_GLOBAL_Control;
  }
  v22 = *((_DWORD *)v59 + 1);
  if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 8) != 0 )
    WPP_SF_Dd(v21[2], 249, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v22, *v59);
  if ( !v22 )
  {
    PredictionsForInstance = -2147418113;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x10C6,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
      (const char *)0x8000FFFFLL,
      (int)"No CountPredictions",
      v51);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_114;
    v16 = 250;
LABEL_18:
    WPP_SF_d(v15[2], v16, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned int)PredictionsForInstance);
    goto LABEL_10;
  }
  v23 = (CFveTpm *)operator new(0x8E8u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v23
    || (v24 = CFveTpm::CFveTpm(v23, *((const struct CFvePolicy **)v8 + 1), *((_BYTE *)v8 + 84)), (v6 = v24) == 0) )
  {
    PredictionsForInstance = -2147024882;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x10D2,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
      (const char *)0x8007000ELL,
      (int)"CFveTpm",
      v51);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_114;
    v16 = 251;
    goto LABEL_18;
  }
  v25 = CFveTpm::Bindings(v24);
  PredictionsForInstance = v25;
  v26 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v25);
    v26 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( PredictionsForInstance < 0 )
  {
    v12 = "Bindings";
    v13 = 4311;
    goto LABEL_9;
  }
  v27 = 0;
  v28 = 0;
  v61 = *((_DWORD *)v59 + 4);
  do
  {
    if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 8) != 0 )
      WPP_SF_Dd(v26[2], 253, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v28, v22);
    v29 = 1584LL * v28;
    v30 = *((_QWORD *)v59 + 3);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
    {
      PredictionsForInstance = CFveTpm::GetEFIBootMgrFilePath(v63, v31);
      if ( PredictionsForInstance )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v33 = 257;
          goto LABEL_90;
        }
LABEL_91:
        if ( PredictionsForInstance < 0 )
          goto LABEL_113;
      }
LABEL_92:
      v32 = v63;
      v60 = (char *)v63;
      goto LABEL_93;
    }
    if ( (*(_BYTE *)(v29 + v30 + 1576) & 0x2F) != 0x2F )
    {
      v27 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          254,
          &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
          *(unsigned int *)(v29 + v30 + 1576));
    }
    if ( (*(_BYTE *)(v29 + v30 + 1576) & 0x20) == 0 )
    {
      PredictionsForInstance = CFveTpm::GetEFIBootMgrFilePath(v63, v31);
      if ( PredictionsForInstance )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v33 = 256;
LABEL_90:
          WPP_SF_d(v15[2], v33, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned int)PredictionsForInstance);
          v15 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_91;
        }
        goto LABEL_91;
      }
      goto LABEL_92;
    }
    PredictionsForInstance = PpfTransformContextGetString(*(_QWORD *)(v29 + v30 + 16), L"BootMgFwFilePath", &v60);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        255,
        &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
        (unsigned int)PredictionsForInstance);
    if ( PredictionsForInstance < 0 )
    {
      v41 = "PpfhTransformContextGetString 1";
      v42 = 4351;
LABEL_129:
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)v42,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
        (const char *)(unsigned int)PredictionsForInstance,
        (int)v41,
        v51);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_113;
    }
    v32 = v60;
LABEL_93:
    PredictionsForInstance = (*(__int64 (__fastcall **)(CFveTpm *, __int64, _QWORD, _QWORD, __int64, void *))(*(_QWORD *)v6 + 32LL))(
                               v6,
                               2,
                               *(_QWORD *)(v29 + v30 + 24),
                               *(unsigned int *)(v29 + v30 + 32),
                               v29 + v30 + 36,
                               v32);
    if ( PredictionsForInstance < 0 )
    {
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x1112,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
        (const char *)(unsigned int)PredictionsForInstance,
        (int)"SetLogData",
        v52);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        goto LABEL_113;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          258,
          &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
          (unsigned int)PredictionsForInstance);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 )
        goto LABEL_113;
      v43 = 259;
      goto LABEL_138;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl)
      && v27 )
    {
      goto LABEL_106;
    }
    PredictionsForInstance = CFveTpm::CheckSecureBootForBitLockerEx(
                               v6,
                               &v61,
                               (enum BitLockerSecureBootEvalState *)&v62,
                               0,
                               0,
                               0,
                               0);
    v26 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        260,
        &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
        (unsigned int)PredictionsForInstance);
      v26 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( PredictionsForInstance < 0 )
    {
      v41 = "CheckSecureBootForBitLockerEx";
      v42 = 4387;
      goto LABEL_129;
    }
    if ( v26 != &WPP_GLOBAL_Control && (*((_BYTE *)v26 + 28) & 8) != 0 )
    {
      WPP_SF_D(v26[2], 261, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned __int16)v62);
      v26 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v62 != 3 )
      goto LABEL_106;
    ++v28;
  }
  while ( v28 < v22 );
  if ( !v27 )
  {
    v44 = v56;
    v45 = *((_QWORD *)v59 + 3);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
    {
      String = PpfTransformContextGetString(*(_QWORD *)(v45 + 16), L"BootMgFwFilePath", &v60);
      PredictionsForInstance = String;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 263, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, String);
      if ( PredictionsForInstance < 0 )
      {
        v35 = "PpfhTransformContextGetString 2";
        v36 = 4428;
LABEL_111:
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)v36,
          (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
          (const char *)(unsigned int)PredictionsForInstance,
          (int)v35,
          v51);
LABEL_112:
        v15 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_113;
      }
      v48 = v60;
    }
    else
    {
      EFIBootMgrFilePath = CFveTpm::GetEFIBootMgrFilePath(v63, v46);
      PredictionsForInstance = EFIBootMgrFilePath;
      if ( EFIBootMgrFilePath )
      {
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            264,
            &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
            EFIBootMgrFilePath);
          v15 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( PredictionsForInstance < 0 )
          goto LABEL_113;
      }
      v48 = v63;
      v60 = (char *)v63;
    }
    PredictionsForInstance = (*(__int64 (__fastcall **)(CFveTpm *, __int64, _QWORD, _QWORD, __int64, void *))(*(_QWORD *)v6 + 32LL))(
                               v6,
                               2,
                               *(_QWORD *)(v45 + 24),
                               *(unsigned int *)(v45 + 32),
                               v45 + 36,
                               v48);
    if ( PredictionsForInstance >= 0 )
    {
      v50 = CFveTpm::CheckSecureBootForBitLockerEx(v6, &v61, v44, 0, v58, (int *)v57, 0);
      PredictionsForInstance = v50;
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 267, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v50);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( PredictionsForInstance >= 0 )
        goto LABEL_113;
      v35 = "CheckSecureBootForBitLockerEx2";
      v36 = 4451;
      goto LABEL_111;
    }
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x1158,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
      (const char *)(unsigned int)PredictionsForInstance,
      (int)"SetLogData",
      v53);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_113;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        265,
        &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
        (unsigned int)PredictionsForInstance);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 == &WPP_GLOBAL_Control || (*((_BYTE *)v15 + 28) & 0x40) == 0 )
      goto LABEL_113;
    v43 = 266;
LABEL_138:
    WPP_SF_d(v15[2], v43, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned int)PredictionsForInstance);
    goto LABEL_112;
  }
LABEL_106:
  v34 = CFveTpm::CheckSecureBootForBitLockerEx(v6, &v61, v56, 0, v58, (int *)v57, 0);
  PredictionsForInstance = v34;
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 262, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v34);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( PredictionsForInstance < 0 )
  {
    v35 = "CheckSecureBootForBitLockerEx1";
    v36 = 4409;
    goto LABEL_111;
  }
LABEL_113:
  v8 = v55;
LABEL_114:
  if ( v59 )
  {
    PpfFreePredictions(v59);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    v59 = 0;
  }
  v37 = *((_QWORD *)v8 + 1);
  if ( v37 )
  {
    v38 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v37 + 8) + 176LL) + 64LL))(*(_QWORD *)(*(_QWORD *)(v37 + 8) + 176LL));
    v39 = v38;
    if ( v38 >= 0 )
      goto LABEL_121;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x1170,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
      (const char *)(unsigned int)v38,
      (int)"_FvePolicy->ReOpen",
      v51);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 268, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v39);
LABEL_121:
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v6 )
  {
    CFveTpm::`scalar deleting destructor'(v6, v14);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x10) != 0 )
    WPP_SF_d(v15[2], 269, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned int)PredictionsForInstance);
  return (unsigned int)PredictionsForInstance;
}

```

## disassembly

```asm
0x18009019c  mov     [rsp-8+arg_18], rbx
0x1800901a1  push    rbp
0x1800901a2  push    rsi
0x1800901a3  push    rdi
0x1800901a4  push    r12
0x1800901a6  push    r13
0x1800901a8  push    r14
0x1800901aa  push    r15
0x1800901ac  lea     rbp, [rsp-1A0h]
0x1800901b4  sub     rsp, 2A0h
0x1800901bb  mov     rax, cs:__security_cookie
0x1800901c2  xor     rax, rsp
0x1800901c5  mov     [rbp+1D0h+var_40], rax
0x1800901cc  mov     rax, [rbp+1D0h+arg_20]
0x1800901d3  xor     esi, esi
0x1800901d5  mov     [rsp+2D0h+var_270], rax
0x1800901da  mov     r14, r8
0x1800901dd  mov     rax, [rbp+1D0h+arg_28]
0x1800901e4  mov     rdi, rdx
0x1800901e7  mov     [rsp+2D0h+var_280], r8
0x1800901ec  mov     r15, rcx
0x1800901ef  mov     [rsp+2D0h+var_288], rcx
0x1800901f4  xor     edx, edx; Val
0x1800901f6  mov     r8d, 208h; Size
0x1800901fc  mov     [rsp+2D0h+var_278], rax
0x180090201  lea     rcx, [rbp+1D0h+var_250]; void *
0x180090205  mov     [rsp+2D0h+var_268], 0
0x18009020e  mov     [rsp+2D0h+var_254], 0
0x180090216  mov     [rsp+2D0h+var_290], sil
0x18009021b  mov     [rsp+2D0h+var_258], esi
0x18009021f  mov     [rsp+2D0h+var_260], rsi
0x180090224  call    memset_0
0x180090229  mov     rcx, cs:WPP_GLOBAL_Control
0x180090230  lea     r13, WPP_GLOBAL_Control
0x180090237  cmp     rcx, r13
0x18009023a  jz      short loc_180090257
0x18009023c  test    byte ptr [rcx+1Ch], 10h
0x180090240  jz      short loc_180090257
0x180090242  mov     rcx, [rcx+10h]
0x180090246  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x18009024d  mov     edx, 0EDh
0x180090252  call    WPP_SF_
0x180090257  lea     rcx, [rsp+2D0h+var_290]; bool *
0x18009025c  call    ?CanFveUsePpf@CFveApiBase@@SAJPEA_N@Z; CFveApiBase::CanFveUsePpf(bool *)
0x180090261  mov     ebx, eax
0x180090263  mov     rcx, cs:WPP_GLOBAL_Control
0x18009026a  mov     r12b, 40h ; '@'
0x18009026d  cmp     rcx, r13
0x180090270  jz      short loc_180090297
0x180090272  test    [rcx+1Ch], r12b
0x180090276  jz      short loc_180090297
0x180090278  mov     rcx, [rcx+10h]
0x18009027c  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x180090283  mov     edx, 0EEh
0x180090288  mov     r9d, eax
0x18009028b  call    WPP_SF_d
0x180090290  mov     rcx, cs:WPP_GLOBAL_Control
0x180090297  test    ebx, ebx
0x180090299  jns     short loc_1800902CE
0x18009029b  lea     rax, aCanfveuseppf; "CanFveUsePpf"
0x1800902a2  mov     edx, 107Eh; void *
0x1800902a7  mov     rcx, [rbp+1D8h]; this
0x1800902ae  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800902b5  mov     r9d, ebx; char *
0x1800902b8  mov     [rsp+2D0h+var_2B0], rax; int
0x1800902bd  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800902c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800902c9  jmp     loc_180090A6C
0x1800902ce  cmp     [rsp+2D0h+var_290], sil
0x1800902d3  jnz     loc_18009035C
0x1800902d9  cmp     rcx, r13
0x1800902dc  jz      short loc_1800902F9
0x1800902de  test    byte ptr [rcx+1Ch], 2
0x1800902e2  jz      short loc_1800902F9
0x1800902e4  mov     rcx, [rcx+10h]
0x1800902e8  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x1800902ef  mov     edx, 0EFh
0x1800902f4  call    WPP_SF_
0x1800902f9  mov     rcx, [rbp+1D8h]; this
0x180090300  lea     rax, aFveCannotUsePp; "FVE cannot use PPF"
0x180090307  mov     ebx, 80070057h
0x18009030c  mov     [rsp+2D0h+var_2B0], rax; int
0x180090311  mov     r9d, ebx; char *
0x180090314  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x18009031b  mov     edx, 1083h; void *
0x180090320  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180090325  mov     rcx, cs:WPP_GLOBAL_Control
0x18009032c  cmp     rcx, r13
0x18009032f  jz      loc_180090A6C
0x180090335  test    [rcx+1Ch], r12b
0x180090339  jz      loc_180090A6C
0x18009033f  mov     edx, 0F0h
0x180090344  mov     rcx, [rcx+10h]
0x180090348  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x18009034f  mov     r9d, ebx
0x180090352  call    WPP_SF_d
0x180090357  jmp     loc_1800902C2
0x18009035c  cmp     rcx, r13
0x18009035f  jz      short loc_18009037C
0x180090361  test    byte ptr [rcx+1Ch], 8
0x180090365  jz      short loc_18009037C
0x180090367  mov     rcx, [rcx+10h]
0x18009036b  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x180090372  mov     edx, 0F1h
0x180090377  call    WPP_SF_
0x18009037c  mov     rax, [r15+8]
0x180090380  test    rax, rax
0x180090383  jz      short loc_1800903DD
0x180090385  mov     rax, [rax+8]
0x180090389  mov     rcx, [rax+0B0h]
0x180090390  mov     rax, [rcx]
0x180090393  mov     rax, [rax+38h]
0x180090397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009039c  mov     ebx, eax
0x18009039e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800903a5  cmp     rcx, r13
0x1800903a8  jz      short loc_1800903C8
0x1800903aa  test    [rcx+1Ch], r12b
0x1800903ae  jz      short loc_1800903C8
0x1800903b0  mov     rcx, [rcx+10h]
0x1800903b4  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x1800903bb  mov     edx, 0F2h
0x1800903c0  mov     r9d, eax
0x1800903c3  call    WPP_SF_d
0x1800903c8  test    ebx, ebx
0x1800903ca  jns     short loc_1800903DD
0x1800903cc  lea     rax, aFvepolicyClose; "_FvePolicy->Close"
0x1800903d3  mov     edx, 1090h
0x1800903d8  jmp     loc_1800902A7
0x1800903dd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x1800903e4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x1800903e9  test    al, al
0x1800903eb  jz      loc_1800904A0
0x1800903f1  lea     rax, [rsp+2D0h+var_268]
0x1800903f6  mov     r9d, 0FFFFh
0x1800903fc  mov     r8d, 880h
0x180090402  mov     [rsp+2D0h+var_2B0], rax
0x180090407  lea     rdx, aBitlocker_1; "BitLocker"
0x18009040e  mov     rcx, rdi
0x180090411  call    cs:__imp_PpfGetPredictionsForInstance
0x180090418  nop     dword ptr [rax+rax+00h]
0x18009041d  mov     ebx, eax
0x18009041f  test    eax, eax
0x180090421  jns     loc_180090542
0x180090427  mov     rcx, [rbp+1D8h]; this
0x18009042e  lea     rax, aPpfgetpredicti_1; "PpfGetPredictionsForInstance"
0x180090435  mov     r9d, ebx; char *
0x180090438  mov     [rsp+2D0h+var_2B0], rax; int
0x18009043d  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x180090444  mov     edx, 10A1h; void *
0x180090449  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009044e  mov     rcx, cs:WPP_GLOBAL_Control
0x180090455  cmp     rcx, r13
0x180090458  jz      loc_180090A6C
0x18009045e  test    byte ptr [rcx+1Ch], 2
0x180090462  jz      short loc_180090483
0x180090464  mov     rcx, [rcx+10h]
0x180090468  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x18009046f  mov     edx, 0F3h
0x180090474  mov     r9d, ebx
0x180090477  call    WPP_SF_d
0x18009047c  mov     rcx, cs:WPP_GLOBAL_Control
0x180090483  cmp     rcx, r13
0x180090486  jz      loc_180090A6C
0x18009048c  test    [rcx+1Ch], r12b
0x180090490  jz      loc_180090A6C
0x180090496  mov     edx, 0F4h
0x18009049b  jmp     loc_180090344
0x1800904a0  mov     r8d, 0FFFFh
0x1800904a6  lea     r9, [rsp+2D0h+var_268]
0x1800904ab  mov     edx, 880h
0x1800904b0  lea     rcx, aBitlocker_1; "BitLocker"
0x1800904b7  call    cs:__imp_PpfGetPredictions
0x1800904be  nop     dword ptr [rax+rax+00h]
0x1800904c3  mov     ebx, eax
0x1800904c5  test    eax, eax
0x1800904c7  jns     short loc_180090542
0x1800904c9  mov     rcx, [rbp+1D8h]; this
0x1800904d0  lea     rax, aPpfgetpredicti_2; "PpfGetPredictions"
0x1800904d7  mov     r9d, ebx; char *
0x1800904da  mov     [rsp+2D0h+var_2B0], rax; int
0x1800904df  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800904e6  mov     edx, 10ADh; void *
0x1800904eb  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800904f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800904f7  cmp     rcx, r13
0x1800904fa  jz      loc_180090A6C
0x180090500  test    byte ptr [rcx+1Ch], 2
0x180090504  jz      short loc_180090525
0x180090506  mov     rcx, [rcx+10h]
0x18009050a  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x180090511  mov     edx, 0F5h
0x180090516  mov     r9d, ebx
0x180090519  call    WPP_SF_d
0x18009051e  mov     rcx, cs:WPP_GLOBAL_Control
0x180090525  cmp     rcx, r13
0x180090528  jz      loc_180090A6C
0x18009052e  test    [rcx+1Ch], r12b
0x180090532  jz      loc_180090A6C
0x180090538  mov     edx, 0F6h
0x18009053d  jmp     loc_180090344
0x180090542  mov     rax, [r15+8]
0x180090546  test    rax, rax
0x180090549  jz      loc_1800905D0
0x18009054f  mov     rax, [rax+8]
0x180090553  mov     rcx, [rax+0B0h]
0x18009055a  mov     rax, [rcx]
0x18009055d  mov     rax, [rax+40h]
0x180090561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090566  mov     ebx, eax
0x180090568  mov     rcx, cs:WPP_GLOBAL_Control
0x18009056f  cmp     rcx, r13
0x180090572  jz      short loc_180090599
0x180090574  test    [rcx+1Ch], r12b
0x180090578  jz      short loc_180090599
0x18009057a  mov     rcx, [rcx+10h]
0x18009057e  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x180090585  mov     edx, 0F7h
0x18009058a  mov     r9d, eax
0x18009058d  call    WPP_SF_d
0x180090592  mov     rcx, cs:WPP_GLOBAL_Control
0x180090599  test    ebx, ebx
0x18009059b  jns     short loc_1800905D7
0x18009059d  mov     rcx, [rbp+1D8h]; this
0x1800905a4  lea     r14, aFvepolicyReope; "_FvePolicy->ReOpen"
0x1800905ab  mov     r9d, ebx; char *
0x1800905ae  mov     [rsp+2D0h+var_2B0], r14; int
0x1800905b3  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x1800905ba  mov     edx, 10B5h; void *
0x1800905bf  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800905c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800905cb  jmp     loc_180090A73
0x1800905d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800905d7  cmp     rcx, r13
0x1800905da  jz      short loc_1800905FE
0x1800905dc  test    byte ptr [rcx+1Ch], 8
0x1800905e0  jz      short loc_1800905FE
0x1800905e2  mov     rcx, [rcx+10h]
0x1800905e6  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x1800905ed  mov     edx, 0F8h
0x1800905f2  call    WPP_SF_
0x1800905f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800905fe  mov     rax, [rsp+2D0h+var_268]
0x180090603  mov     r12d, [rax+4]
0x180090607  cmp     rcx, r13
0x18009060a  jz      short loc_180090631
0x18009060c  test    byte ptr [rcx+1Ch], 8
0x180090610  jz      short loc_180090631
0x180090612  movzx   eax, word ptr [rax]
0x180090615  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x18009061c  mov     rcx, [rcx+10h]
0x180090620  mov     edx, 0F9h
0x180090625  mov     r9d, r12d
0x180090628  mov     dword ptr [rsp+2D0h+var_2B0], eax
0x18009062c  call    WPP_SF_Dd
0x180090631  test    r12d, r12d
0x180090634  jnz     short loc_180090686
0x180090636  mov     rcx, [rbp+1D8h]; this
0x18009063d  lea     rax, aNoCountpredict; "No CountPredictions"
0x180090644  mov     ebx, 8000FFFFh
0x180090649  mov     [rsp+2D0h+var_2B0], rax; int
0x18009064e  mov     r9d, ebx; char *
0x180090651  lea     r8, aOnecoreBaseNgs_2; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x180090658  mov     edx, 10C6h; void *
0x18009065d  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180090662  mov     rcx, cs:WPP_GLOBAL_Control
0x180090669  cmp     rcx, r13
0x18009066c  jz      loc_180090A6C
0x180090672  test    byte ptr [rcx+1Ch], 40h
0x180090676  jz      loc_180090A6C
0x18009067c  mov     edx, 0FAh
0x180090681  jmp     loc_180090344
0x180090686  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18009068d  mov     ecx, 8E8h; unsigned __int64
0x180090692  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180090697  test    rax, rax
0x18009069a  jz      loc_180090E61
0x1800906a0  mov     r8b, [r15+54h]; bool
0x1800906a4  mov     rcx, rax; this
0x1800906a7  mov     rdx, [r15+8]; struct CFvePolicy *
0x1800906ab  call    ??0CFveTpm@@QEAA@PEBVCFvePolicy@@_N@Z; CFveTpm::CFveTpm(CFvePolicy const *,bool)
0x1800906b0  mov     rsi, rax
0x1800906b3  test    rax, rax
0x1800906b6  jz      loc_180090E61
0x1800906bc  mov     rcx, rax; this
0x1800906bf  call    ?Bindings@CFveTpm@@QEAAJXZ; CFveTpm::Bindings(void)
0x1800906c4  mov     ebx, eax
0x1800906c6  mov     r10, cs:WPP_GLOBAL_Control
0x1800906cd  cmp     r10, r13
0x1800906d0  jz      short loc_1800906F8
0x1800906d2  test    byte ptr [r10+1Ch], 40h
0x1800906d7  jz      short loc_1800906F8
0x1800906d9  mov     rcx, [r10+10h]
0x1800906dd  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x1800906e4  mov     edx, 0FCh
0x1800906e9  mov     r9d, eax
0x1800906ec  call    WPP_SF_d
0x1800906f1  mov     r10, cs:WPP_GLOBAL_Control
0x1800906f8  test    ebx, ebx
0x1800906fa  jns     short loc_18009070D
  ... truncated ...
```
