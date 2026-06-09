# CreateTpmProtectorBindingDigestSourceData(CFveTpm *,_FVE_DATA_TPM_PROTECTOR_VERSION,bool,_FVE_TPM_STATE_INFO_PARAMS *,ulong const *,ushort const *,ushort *,_FVE_TPM_DIGEST_SOURCE_DATA * *,PPF_PREDICTIONS * *)

- ea: `0x18009f6ec`
- end: `0x1800a0839`
- name: `?CreateTpmProtectorBindingDigestSourceData@@YAJPEAVCFveTpm@@W4_FVE_DATA_TPM_PROTECTOR_VERSION@@_NPEAU_FVE_TPM_STATE_INFO_PARAMS@@PEBKPEBGPEAGPEAPEAU_FVE_TPM_DIGEST_SOURCE_DATA@@PEAPEAUPPF_PREDICTIONS@@@Z`
- size: `4429`
- prototype: `__int64 __fastcall(CFveTpm *, __int64, __int64, __int64, unsigned int *, unsigned __int16 *, unsigned __int16 *, _QWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b1450`
- `0x1800bae5c`
- `0x1800d20fc`
- `0x1800d32ac`

## callees

- `0x1800050c0`
- `0x180008d70`
- `0x1800090c0`
- `0x1800184ac`
- `0x180019128`
- `0x180037edc`
- `0x180037f50`
- `0x18003d000`
- `0x180045ea0`
- `0x180047640`
- `0x18004dba8`
- `0x180071210`
- `0x180076b1c`
- `0x1800873d0`
- `0x18008b524`
- `0x180090eb8`
- `0x18009f470`
- `0x18009f6ec`
- `0x1800a3cf4`
- `0x1800a41ec`
- `0x18011f010`

## import_xrefs

- `pcrpf!PpfGetPredictionsForInstance` at `0x18009fbf0`
- `pcrpf!PpfGetPredictionsForInstance` at `0x18009fbf0`
- `pcrpf!PpfFreePredictions` at `0x18009f895`
- `pcrpf!PpfFreePredictions` at `0x18009f895`
- `pcrpf!PpfGetPredictions` at `0x18009fd6d`
- `pcrpf!PpfGetPredictions` at `0x18009fd6d`
- `pcrpf!PpfTransformContextGetString` at `0x1800a0411`
- `pcrpf!PpfTransformContextGetString` at `0x1800a0411`

## string_xrefs

- `0x1800a040a`: `BootMgFwFilePath`
- `0x18009f87f`: `TpmContext->ReOpenPolicy`
- `0x18009fcca`: `TpmContext->ReOpenPolicy`
- `0x1800a01d8`: `TpmContext->ReOpenPolicy`
- `0x1800a0582`: `TpmContext->ReOpenPolicy`
- `0x1800a07a2`: `TpmContext->ReOpenPolicy`
- `0x1800a0645`: `Prediction->PredictedStatesBitmap incomplete (bootmgr)`
- `0x1800a06cd`: `GetEFIBootMgrFilePath`

## pseudocode

```c
__int64 __fastcall CreateTpmProtectorBindingDigestSourceData(
        CFveTpm *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int *a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        _QWORD *a8,
        _QWORD *a9)
{
  unsigned int v10; // r14d
  void *v11; // r15
  int v12; // r13d
  PVOID *v13; // rcx
  int EFIBootMgrFilePath; // ebx
  PVOID *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  CFveTpm *v18; // r12
  _DWORD *v19; // r14
  int v20; // eax
  unsigned int v21; // edi
  _QWORD *v22; // rcx
  unsigned int CanFveUsePpf; // eax
  __int64 v24; // rdx
  bool v25; // r15
  unsigned __int16 v26; // r12
  __int64 v27; // r9
  int v28; // eax
  unsigned __int16 *v29; // rdi
  int PcrProfileForSeal; // eax
  __int64 v31; // rdx
  __int64 v32; // r9
  PVOID *v33; // r10
  __int64 v34; // rdx
  int PredictionsForInstance; // eax
  unsigned int v36; // eax
  PVOID *v37; // r10
  __int64 v38; // rdx
  __int64 v39; // rdx
  unsigned int v40; // eax
  int Predictions; // eax
  unsigned int v42; // eax
  unsigned int v43; // ecx
  __int64 v44; // r10
  unsigned __int16 *v45; // r11
  int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // r9
  char *v49; // r9
  unsigned __int16 v50; // dx
  unsigned __int16 v51; // r13
  __int64 v52; // rdi
  _QWORD *v53; // rax
  __int64 v54; // r14
  __int64 v55; // r15
  unsigned int v56; // edx
  PVOID *v57; // rcx
  unsigned int String; // eax
  unsigned int v59; // eax
  PVOID v60; // r10
  char IsEnabled; // al
  int v62; // eax
  _QWORD *v63; // rcx
  enum ePcrBitmapSource *v65; // [rsp+28h] [rbp-91h]
  char *v66; // [rsp+40h] [rbp-79h]
  _DWORD *v67; // [rsp+48h] [rbp-71h]
  bool v69; // [rsp+58h] [rbp-61h] BYREF
  unsigned __int16 v70[2]; // [rsp+5Ch] [rbp-5Dh] BYREF
  unsigned __int16 *v71; // [rsp+60h] [rbp-59h]
  unsigned __int64 v72; // [rsp+68h] [rbp-51h] BYREF
  unsigned __int64 v73; // [rsp+70h] [rbp-49h] BYREF
  __int64 v74; // [rsp+78h] [rbp-41h]
  _QWORD *v75; // [rsp+80h] [rbp-39h]
  unsigned __int16 *v76; // [rsp+88h] [rbp-31h]
  _QWORD *v77; // [rsp+90h] [rbp-29h]
  unsigned __int16 *v78; // [rsp+98h] [rbp-21h] BYREF
  unsigned __int16 *v79; // [rsp+A0h] [rbp-19h] BYREF
  unsigned int v80; // [rsp+A8h] [rbp-11h] BYREF
  char v81[4]; // [rsp+ACh] [rbp-Dh] BYREF
  char *v82; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+3Fh]

  v10 = a2;
  v71 = a6;
  v75 = a9;
  v11 = 0;
  v74 = a4;
  v12 = (unsigned __int8)a3;
  v76 = a7;
  v77 = a8;
  v78 = 0;
  v66 = 0;
  v72 = 0;
  v73 = 0;
  v69 = 0;
  v70[0] = 0;
  v80 = 0;
  *(_DWORD *)v81 = 0;
  LODWORD(v82) = 0;
  v79 = 0;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      WPP_SF_Dl(v13[2], a2, a3, v10, v12);
  }
  if ( !a1 || (unsigned __int16)(v10 - 1) > 1u )
  {
    EFIBootMgrFilePath = -2147024809;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x9A0,
      (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
      (const char *)0x80070057LL,
      (int)"FveDataTpmProtectorVersionIsSupported",
      (const char *)v65);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
      goto LABEL_19;
    v16 = 158;
LABEL_17:
    v17 = 2147942487LL;
LABEL_18:
    WPP_SF_d(v15[2], v16, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, v17);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_19;
  }
  if ( !(_BYTE)v12 || a4 && *(_QWORD *)a4 && *(_DWORD *)(a4 + 8) != -1 && *(_DWORD *)(a4 + 12) )
  {
    if ( !a7 || !a8 || (v22 = v75) == 0 )
    {
      EFIBootMgrFilePath = -2147467261;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x9B0,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
        (const char *)0x80004003LL,
        (int)"Invalid out params",
        (const char *)v65);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_19;
      v16 = 160;
      v17 = 2147500035LL;
      goto LABEL_18;
    }
    *a7 = 0;
    *a8 = 0;
    *v22 = 0;
    CanFveUsePpf = CFveApiBase::CanFveUsePpf(&v69);
    EFIBootMgrFilePath = CanFveUsePpf;
    if ( CanFveUsePpf )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          161,
          &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
          CanFveUsePpf);
        v15 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( EFIBootMgrFilePath < 0 )
        goto LABEL_19;
    }
    else
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    v25 = v69;
    if ( (_BYTE)v12 )
    {
      v26 = 1;
      v27 = *(unsigned int *)(v74 + 8);
      v28 = *(_DWORD *)(v74 + 12);
      *(_DWORD *)v81 = v28;
      v80 = v27;
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 8) != 0 )
        WPP_SF_Dd(v15[2], 182, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, v27, (unsigned __int16)v28);
      goto LABEL_125;
    }
    if ( v69 )
    {
      v18 = a1;
      v29 = v71;
      PcrProfileForSeal = CFveTpm::GetPcrProfileForSeal(
                            a1,
                            v71,
                            1,
                            a5,
                            &v80,
                            (enum ePcrBitmapSource *)v81,
                            (unsigned int *)&v82);
      EFIBootMgrFilePath = PcrProfileForSeal;
      if ( PcrProfileForSeal < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            183,
            &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
            (unsigned int)PcrProfileForSeal);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0xA4D,
          (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
          (const char *)(unsigned int)EFIBootMgrFilePath,
          (int)"GetPcrProfileForSeal",
          (const char *)v65);
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_53;
        v31 = 184;
        goto LABEL_50;
      }
      v33 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_DDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            185,
            &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
            v80,
            *(unsigned __int16 *)v81,
            (_DWORD)v82);
          v33 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 8) != 0 )
          WPP_SF_(v33[2], 186, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids);
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
      {
        EFIBootMgrFilePath = CFveTpm::ClosePolicy(a1);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            187,
            &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
            (unsigned int)EFIBootMgrFilePath);
        if ( EFIBootMgrFilePath < 0 )
        {
          v34 = 2656;
LABEL_66:
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)v34,
            (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
            (const char *)(unsigned int)EFIBootMgrFilePath,
            (int)"TpmContext->ClosePolicy",
            (const char *)v65);
          goto LABEL_52;
        }
        PredictionsForInstance = PpfGetPredictionsForInstance(v29, L"BitLocker", v80, 0xFFFF, &v78);
        EFIBootMgrFilePath = PredictionsForInstance;
        if ( PredictionsForInstance < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              188,
              &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
              (unsigned int)PredictionsForInstance);
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)0xA69,
            (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
            (const char *)(unsigned int)EFIBootMgrFilePath,
            (int)"PpfGetPredictionsForInstance",
            (const char *)v65);
          v15 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
            goto LABEL_53;
          v31 = 189;
          goto LABEL_50;
        }
        v36 = CFveTpm::ReOpenPolicy(a1);
        EFIBootMgrFilePath = v36;
        v37 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 190, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, v36);
          v37 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( EFIBootMgrFilePath < 0 )
        {
          v38 = 2669;
LABEL_79:
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)v38,
            (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
            (const char *)(unsigned int)EFIBootMgrFilePath,
            (int)"TpmContext->ReOpenPolicy",
            (const char *)v65);
          v15 = (PVOID *)WPP_GLOBAL_Control;
          v11 = 0;
          goto LABEL_20;
        }
        if ( v37 == &WPP_GLOBAL_Control || (*((_BYTE *)v37 + 28) & 8) == 0 )
          goto LABEL_104;
        v39 = 191;
LABEL_103:
        WPP_SF_Dd(v37[2], v39, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, *((unsigned int *)v78 + 1), *v78);
LABEL_104:
        if ( (int)ULongToUShort(*((_DWORD *)v78 + 1), v70) >= 0 )
        {
          v26 = v70[0];
LABEL_125:
          LOBYTE(v24) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_TPMPV2_MultiBinding>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_BitLocker_TPMPV2_MultiBinding>::GetImpl'::`2'::impl,
            v24);
          if ( v26 > 1u && v10 == 1 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 208, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, v26);
            LODWORD(v65) = v26;
            EFIBootMgrFilePath = -2147024809;
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0xADE,
              (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
              (const char *)0x80070057LL,
              (int)"TPMPV1 does not support sealing sealing %u bindings",
              (const char *)v65);
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                209,
                &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
                2147942487LL);
              v15 = (PVOID *)WPP_GLOBAL_Control;
            }
LABEL_133:
            v11 = 0;
            goto LABEL_19;
          }
          EFIBootMgrFilePath = ULongLongMult(v26, 4u, &v73);
          if ( EFIBootMgrFilePath )
          {
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                214,
                &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
                (unsigned int)EFIBootMgrFilePath);
              v15 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( EFIBootMgrFilePath < 0 )
              goto LABEL_133;
          }
          v67 = CFveApiBase::ZeroAlloc(v73);
          v19 = v67;
          if ( !v67 )
          {
            EFIBootMgrFilePath = -2147024882;
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0xB07,
              (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
              (const char *)0x8007000ELL,
              (int)"LocalBindingDigestSourceDataTypes is NULL",
              (const char *)v65);
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
              goto LABEL_145;
            v47 = 215;
LABEL_143:
            v48 = 2147942414LL;
LABEL_144:
            WPP_SF_d(v15[2], v47, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, v48);
            v15 = (PVOID *)WPP_GLOBAL_Control;
LABEL_145:
            v11 = v66;
LABEL_146:
            v18 = a1;
            goto LABEL_21;
          }
          EFIBootMgrFilePath = ULongLongMult(v26, 0x248u, &v72);
          if ( EFIBootMgrFilePath )
          {
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                216,
                &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
                (unsigned int)EFIBootMgrFilePath);
              v15 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( EFIBootMgrFilePath < 0 )
              goto LABEL_145;
          }
          v66 = (char *)CFveApiBase::ZeroAlloc(v72);
          v49 = v66;
          if ( !v66 )
          {
            EFIBootMgrFilePath = -2147024882;
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0xB12,
              (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
              (const char *)0x8007000ELL,
              (int)"LocalBindingDigestSourceData is NULL",
              (const char *)v65);
            v15 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
              goto LABEL_145;
            v47 = 217;
            goto LABEL_143;
          }
          v50 = 0;
          if ( !v26 )
          {
LABEL_195:
            v63 = v75;
            v11 = 0;
            *v76 = v26;
            v18 = a1;
            *v77 = v49;
            *v63 = v78;
            v78 = 0;
LABEL_24:
            v20 = CFveTpm::ReOpenPolicy(v18);
            v21 = v20;
            if ( v20 >= 0 )
            {
              v15 = (PVOID *)WPP_GLOBAL_Control;
            }
            else
            {
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0xB9F,
                (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
                (const char *)(unsigned int)v20,
                (int)"TpmContext->ReOpenPolicy",
                (const char *)v65);
              v15 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  226,
                  &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
                  v21);
                v15 = (PVOID *)WPP_GLOBAL_Control;
              }
            }
            goto LABEL_219;
          }
          do
          {
            if ( (_BYTE)v12 )
              v67[v50] = 3;
            else
              v67[v50] = v25 + 1;
            ++v50;
          }
          while ( v50 < v26 );
          v51 = 0;
          while ( 1 )
          {
            v52 = 584LL * v51;
            *(_DWORD *)v70 = v19[v51];
            switch ( *(_DWORD *)v70 )
            {
              case 1:
                *(_DWORD *)&v49[v52 + 568] = 0;
                *(_QWORD *)&v49[v52 + 576] = 0;
                break;
              case 2:
                v54 = 1584LL * v51;
                v55 = *((_QWORD *)v78 + 3);
                *(_DWORD *)&v49[v52 + 568] = *(_DWORD *)(v54 + v55 + 32);
                *(_QWORD *)&v49[v52 + 576] = *(_QWORD *)(v54 + v55 + 24);
                *(_DWORD *)&v49[v52 + 24] = *((_DWORD *)v78 + 4);
                *(_QWORD *)&v49[v52 + 32] = v54 + v55 + 36;
                if ( (v80 & 0x90) != 0 )
                {
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
                  {
                    if ( (v80 & 0x10) == 0 )
                      goto LABEL_173;
                    if ( (*(_BYTE *)(v54 + v55 + 1576) & 0x10) == 0 )
                    {
                      EFIBootMgrFilePath = -2144272382;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        WPP_SF_D(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          218,
                          &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
                          *(unsigned int *)(v54 + v55 + 1576));
                      wil::details::in1diag3::Log_HrMsg(
                        retaddr,
                        (void *)0xB55,
                        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
                        (const char *)0x80310002LL,
                        (int)"Prediction->PredictedStatesBitmap incomplete (bootmgr)",
                        (const char *)v65);
                      v15 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          219,
                          &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
                          2150694914LL);
                        goto LABEL_205;
                      }
LABEL_206:
                      v11 = v66;
LABEL_207:
                      v19 = v67;
                      goto LABEL_146;
                    }
                    v57 = (PVOID *)WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                      {
                        WPP_SF_(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          220,
                          &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids);
LABEL_173:
                        v57 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 0x10) != 0 )
                        WPP_SF_(v57[2], 221, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids);
                    }
                    String = PpfTransformContextGetString(*(_QWORD *)(v54 + v55 + 16), L"BootMgFwFilePath", &v79);
                    EFIBootMgrFilePath = String;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        222,
                        &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
                        String);
                    if ( EFIBootMgrFilePath < 0 )
                    {
                      wil::details::in1diag3::Log_HrMsg(
                        retaddr,
                        (void *)0xB64,
                        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
                        (const char *)(unsigned int)EFIBootMgrFilePath,
                        (int)"PpfhTransformContextGetString",
                        (const char *)v65);
LABEL_205:
                      v15 = (PVOID *)WPP_GLOBAL_Control;
                      goto LABEL_206;
                    }
                    v11 = v66;
                    v59 = StringCchCopyW((unsigned __int16 *)&v66[v52 + 40], 0x104u, v79);
                    EFIBootMgrFilePath = v59;
                    if ( v59 )
                    {
                      v15 = (PVOID *)WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != v60 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                      {
                        WPP_SF_d(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          223,
                          &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
                          v59);
                        v15 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( EFIBootMgrFilePath < 0 )
                      {
                        v19 = v67;
                        goto LABEL_217;
                      }
                    }
                  }
                  else
                  {
                    v11 = v66;
                    EFIBootMgrFilePath = CFveTpm::GetEFIBootMgrFilePath((unsigned __int16 *)&v66[v52 + 40], v56);
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        224,
                        &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
                        (unsigned int)EFIBootMgrFilePath);
                    if ( EFIBootMgrFilePath < 0 )
                    {
                      wil::details::in1diag3::Log_HrMsg(
                        retaddr,
                        (void *)0xB6E,
                        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
                        (const char *)(unsigned int)EFIBootMgrFilePath,
                        (int)"GetEFIBootMgrFilePath",
                        (const char *)v65);
                      v15 = (PVOID *)WPP_GLOBAL_Control;
                      goto LABEL_207;
                    }
                  }
                }
                IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl);
                v49 = v66;
                v19 = v67;
                if ( IsEnabled )
                  *(_QWORD *)&v66[v52 + 560] = v71;
                break;
              case 3:
                v53 = (_QWORD *)v74;
                *(_DWORD *)&v49[v52 + 568] = 24;
                *(_QWORD *)&v49[v52 + 576] = *v53;
                break;
              default:
                EFIBootMgrFilePath = -2147467259;
                wil::details::in1diag3::Log_HrMsg(
                  retaddr,
                  (void *)0xB7F,
                  (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
                  (const char *)0x80004005LL,
                  (int)"Invalid FveTpmDigestSourceDataType",
                  (const char *)v65);
                v15 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                {
                  v47 = 225;
                  v48 = 2147500037LL;
                  goto LABEL_144;
                }
                goto LABEL_145;
            }
            v62 = *(_DWORD *)v70;
            *(_WORD *)&v49[v52 + 4] = v51++;
            *(_DWORD *)&v49[v52] = v62;
            *(_DWORD *)&v49[v52 + 8] = v80;
            *(_WORD *)&v49[v52 + 12] = *(_WORD *)v81;
            *(_DWORD *)&v49[v52 + 16] = (_DWORD)v82;
            if ( v51 >= v26 )
              goto LABEL_195;
          }
        }
        EFIBootMgrFilePath = -2147024809;
        if ( (PVOID *)v44 != &WPP_GLOBAL_Control && (*(_BYTE *)(v44 + 28) & 2) != 0 )
        {
          WPP_SF_D(*(_QWORD *)(v44 + 16), 197, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, v43);
          v45 = v78;
        }
        LODWORD(v65) = *((_DWORD *)v45 + 1);
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0xA8A,
          (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
          (const char *)0x80070057LL,
          (int)"PPF number of predictions %lu is too large",
          (const char *)v65);
        v15 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v31 = 198;
          v32 = 2147942487LL;
          goto LABEL_51;
        }
LABEL_53:
        v11 = 0;
        goto LABEL_20;
      }
      v40 = CFveTpm::ClosePolicy(a1);
      EFIBootMgrFilePath = v40;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 192, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, v40);
      if ( EFIBootMgrFilePath < 0 )
      {
        v34 = 2677;
        goto LABEL_66;
      }
      Predictions = PpfGetPredictions(L"BitLocker", v80, 0xFFFF, &v78);
      EFIBootMgrFilePath = Predictions;
      if ( Predictions >= 0 )
      {
        v42 = CFveTpm::ReOpenPolicy(a1);
        EFIBootMgrFilePath = v42;
        v37 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, v42);
          v37 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( EFIBootMgrFilePath < 0 )
        {
          v38 = 2686;
          goto LABEL_79;
        }
        if ( v37 == &WPP_GLOBAL_Control || (*((_BYTE *)v37 + 28) & 8) == 0 )
          goto LABEL_104;
        v39 = 196;
        goto LABEL_103;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          193,
          &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
          (unsigned int)Predictions);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xA7A,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
        (const char *)(unsigned int)EFIBootMgrFilePath,
        (int)"PpfGetPredictions",
        (const char *)v65);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_53;
      v31 = 194;
    }
    else
    {
      if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 4) != 0 )
        WPP_SF_(v15[2], 201, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids);
      v18 = a1;
      v46 = CFveTpm::GetPcrProfileForSeal(a1, v71, 0, a5, &v80, (enum ePcrBitmapSource *)v81, (unsigned int *)&v82);
      EFIBootMgrFilePath = v46;
      if ( v46 >= 0 )
      {
        v26 = 1;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_DDD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            207,
            &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
            v80,
            *(unsigned __int16 *)v81,
            (_DWORD)v82);
        goto LABEL_125;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          205,
          &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids,
          (unsigned int)v46);
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0xAC6,
        (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
        (const char *)(unsigned int)EFIBootMgrFilePath,
        (int)"GetPcrProfileForSeal",
        (const char *)v65);
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_53;
      v31 = 206;
    }
LABEL_50:
    v32 = (unsigned int)EFIBootMgrFilePath;
LABEL_51:
    WPP_SF_d(v15[2], v31, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, v32);
LABEL_52:
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_53;
  }
  EFIBootMgrFilePath = -2147024809;
  wil::details::in1diag3::Log_HrMsg(
    retaddr,
    (void *)0x9A8,
    (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpmutility.cpp",
    (const char *)0x80070057LL,
    (int)"TPM State Info is not valid",
    (const char *)v65);
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
    {
LABEL_19:
      v18 = a1;
LABEL_20:
      v19 = 0;
      goto LABEL_21;
    }
    v16 = 159;
    goto LABEL_17;
  }
  v19 = 0;
LABEL_217:
  v18 = a1;
LABEL_21:
  if ( v78 )
  {
    PpfFreePredictions(v78);
    v15 = (PVOID *)WPP_GLOBAL_Control;
    v78 = 0;
  }
  if ( v18 )
    goto LABEL_24;
LABEL_219:
  if ( v11 )
  {
    CFveApiBase::ZeroFree(v11, v72);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v19 )
  {
    CFveApiBase::ZeroFree(v19, v73);
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 0x20) != 0 )
    WPP_SF_d(v15[2], 227, &WPP_a09fb043d95a349cf604520131dfb76d_Traceguids, (unsigned int)EFIBootMgrFilePath);
  return (unsigned int)EFIBootMgrFilePath;
}

```

## disassembly

```asm
0x18009f6ec  mov     [rsp-8+arg_10], rbx
0x18009f6f1  push    rbp
0x18009f6f2  push    rsi
0x18009f6f3  push    rdi
0x18009f6f4  push    r12
0x18009f6f6  push    r13
0x18009f6f8  push    r14
0x18009f6fa  push    r15
0x18009f6fc  lea     rbp, [rsp-7]
0x18009f701  sub     rsp, 0C0h
0x18009f708  mov     rax, cs:__security_cookie
0x18009f70f  xor     rax, rsp
0x18009f712  mov     [rbp+37h+var_38], rax
0x18009f716  mov     rax, [rbp+37h+arg_28]
0x18009f71a  mov     rbx, r9
0x18009f71d  mov     rsi, [rbp+37h+arg_30]
0x18009f721  mov     r14d, edx
0x18009f724  mov     r12, [rbp+37h+arg_38]
0x18009f728  mov     rdi, [rbp+37h+arg_20]
0x18009f72c  mov     [rbp+37h+var_90], rax
0x18009f730  mov     rax, [rbp+37h+arg_40]
0x18009f737  mov     [rbp+37h+var_A0], rcx
0x18009f73b  xor     ecx, ecx
0x18009f73d  mov     [rbp+37h+var_70], rax
0x18009f741  mov     r15d, ecx
0x18009f744  mov     [rbp+37h+var_78], rbx
0x18009f748  movzx   r13d, r8b
0x18009f74c  mov     [rbp+37h+var_68], rsi
0x18009f750  mov     [rbp+37h+var_60], r12
0x18009f754  mov     [rbp+37h+var_58], rcx
0x18009f758  mov     [rbp+37h+var_B0], rcx
0x18009f75c  mov     [rbp+37h+var_88], rcx
0x18009f760  mov     [rbp+37h+var_80], rcx
0x18009f764  mov     [rbp+37h+var_98], cl
0x18009f767  mov     [rbp+37h+var_94], cx
0x18009f76b  mov     [rbp+37h+var_48], ecx
0x18009f76e  mov     dword ptr [rbp+37h+var_44], ecx
0x18009f771  mov     dword ptr [rbp+37h+var_40], ecx
0x18009f774  mov     [rbp+37h+var_50], rcx
0x18009f778  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f77f  lea     rax, WPP_GLOBAL_Control
0x18009f786  cmp     rcx, rax
0x18009f789  jz      short loc_18009F7D0
0x18009f78b  test    byte ptr [rcx+1Ch], 20h
0x18009f78f  jz      short loc_18009F7B4
0x18009f791  mov     rcx, [rcx+10h]
0x18009f795  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009f79c  mov     edx, 9Ch
0x18009f7a1  call    WPP_SF_
0x18009f7a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f7ad  lea     rax, WPP_GLOBAL_Control
0x18009f7b4  cmp     rcx, rax
0x18009f7b7  jz      short loc_18009F7D0
0x18009f7b9  test    byte ptr [rcx+1Ch], 8
0x18009f7bd  jz      short loc_18009F7D0
0x18009f7bf  mov     rcx, [rcx+10h]
0x18009f7c3  mov     r9d, r14d
0x18009f7c6  mov     dword ptr [rsp+0F0h+var_D0], r13d
0x18009f7cb  call    WPP_SF_Dl
0x18009f7d0  xor     edx, edx
0x18009f7d2  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x18009f7d9  cmp     [rbp+37h+var_A0], rdx
0x18009f7dd  jz      loc_1800A0749
0x18009f7e3  lea     ecx, [rdx+1]
0x18009f7e6  movzx   eax, r14w
0x18009f7ea  sub     ax, cx
0x18009f7ed  cmp     ax, cx
0x18009f7f0  ja      loc_1800A0749
0x18009f7f6  test    r13b, r13b
0x18009f7f9  jz      loc_18009F92D
0x18009f7ff  test    rbx, rbx
0x18009f802  jz      short loc_18009F818
0x18009f804  cmp     [rbx], rdx
0x18009f807  jz      short loc_18009F818
0x18009f809  cmp     dword ptr [rbx+8], 0FFFFFFFFh
0x18009f80d  jz      short loc_18009F818
0x18009f80f  cmp     [rbx+0Ch], edx
0x18009f812  jnz     loc_18009F92D
0x18009f818  mov     rcx, [rbp+3Fh]; this
0x18009f81c  lea     rax, aTpmStateInfoIs; "TPM State Info is not valid"
0x18009f823  mov     edi, 80070057h
0x18009f828  mov     [rsp+0F0h+var_D0], rax; int
0x18009f82d  mov     r9d, edi; char *
0x18009f830  mov     edx, 9A8h; void *
0x18009f835  mov     ebx, edi
0x18009f837  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009f83c  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f843  lea     r10, WPP_GLOBAL_Control
0x18009f84a  cmp     rcx, r10
0x18009f84d  jz      loc_1800A079B
0x18009f853  mov     sil, 40h ; '@'
0x18009f856  test    [rcx+1Ch], sil
0x18009f85a  jz      short loc_18009F87B
0x18009f85c  mov     edx, 9Fh
0x18009f861  mov     r9d, edi
0x18009f864  mov     rcx, [rcx+10h]
0x18009f868  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009f86f  call    WPP_SF_d
0x18009f874  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f87b  mov     r12, [rbp+37h+var_A0]
0x18009f87f  lea     rsi, aTpmcontextReop; "TpmContext->ReOpenPolicy"
0x18009f886  mov     r14, r15
0x18009f889  mov     rax, [rbp+37h+var_58]
0x18009f88d  test    rax, rax
0x18009f890  jz      short loc_18009F8B0
0x18009f892  mov     rcx, rax
0x18009f895  call    cs:__imp_PpfFreePredictions
0x18009f89c  nop     dword ptr [rax+rax+00h]
0x18009f8a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f8a8  mov     [rbp+37h+var_58], 0
0x18009f8b0  test    r12, r12
0x18009f8b3  jz      loc_1800A07B5
0x18009f8b9  mov     rcx, r12; this
0x18009f8bc  call    ?ReOpenPolicy@CFveTpm@@QEAAJXZ; CFveTpm::ReOpenPolicy(void)
0x18009f8c1  mov     edi, eax
0x18009f8c3  test    eax, eax
0x18009f8c5  jns     loc_1800A07AE
0x18009f8cb  mov     rcx, [rbp+3Fh]; this
0x18009f8cf  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x18009f8d6  mov     r9d, eax; char *
0x18009f8d9  mov     [rsp+0F0h+var_D0], rsi; int
0x18009f8de  mov     edx, 0B9Fh; void *
0x18009f8e3  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009f8e8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f8ef  lea     rsi, WPP_GLOBAL_Control
0x18009f8f6  cmp     rcx, rsi
0x18009f8f9  jz      loc_1800A07BC
0x18009f8ff  test    byte ptr [rcx+1Ch], 4
0x18009f903  jz      loc_1800A07BC
0x18009f909  mov     rcx, [rcx+10h]
0x18009f90d  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009f914  mov     edx, 0E2h
0x18009f919  mov     r9d, edi
0x18009f91c  call    WPP_SF_d
0x18009f921  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f928  jmp     loc_1800A07BC
0x18009f92d  test    rsi, rsi
0x18009f930  jz      loc_1800A06F6
0x18009f936  test    r12, r12
0x18009f939  jz      loc_1800A06F6
0x18009f93f  mov     rcx, [rbp+37h+var_70]
0x18009f943  test    rcx, rcx
0x18009f946  jz      loc_1800A06F6
0x18009f94c  mov     [rsi], dx
0x18009f94f  mov     [r12], rdx
0x18009f953  mov     [rcx], rdx
0x18009f956  lea     rcx, [rbp+37h+var_98]; bool *
0x18009f95a  call    ?CanFveUsePpf@CFveApiBase@@SAJPEA_N@Z; CFveApiBase::CanFveUsePpf(bool *)
0x18009f95f  mov     ebx, eax
0x18009f961  mov     sil, 40h ; '@'
0x18009f964  test    eax, eax
0x18009f966  jz      short loc_18009F9AA
0x18009f968  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f96f  lea     r12, WPP_GLOBAL_Control
0x18009f976  cmp     rcx, r12
0x18009f979  jz      short loc_18009F9A0
0x18009f97b  test    [rcx+1Ch], sil
0x18009f97f  jz      short loc_18009F9A0
0x18009f981  mov     rcx, [rcx+10h]
0x18009f985  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009f98c  mov     edx, 0A1h
0x18009f991  mov     r9d, eax
0x18009f994  call    WPP_SF_d
0x18009f999  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f9a0  test    ebx, ebx
0x18009f9a2  js      loc_18009F87B
0x18009f9a8  jmp     short loc_18009F9B8
0x18009f9aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f9b1  lea     r12, WPP_GLOBAL_Control
0x18009f9b8  mov     r15b, [rbp+37h+var_98]
0x18009f9bc  test    r13b, r13b
0x18009f9bf  jz      short loc_18009FA17
0x18009f9c1  mov     rax, [rbp+37h+var_78]
0x18009f9c5  mov     ebx, 1
0x18009f9ca  movzx   r12d, bx
0x18009f9ce  mov     r9d, [rax+8]
0x18009f9d2  mov     eax, [rax+0Ch]
0x18009f9d5  mov     dword ptr [rbp+37h+var_44], eax
0x18009f9d8  mov     [rbp+37h+var_48], r9d
0x18009f9dc  lea     rdi, WPP_GLOBAL_Control
0x18009f9e3  cmp     rcx, rdi
0x18009f9e6  jz      loc_1800A003D
0x18009f9ec  test    byte ptr [rcx+1Ch], 8
0x18009f9f0  jz      loc_1800A003D
0x18009f9f6  mov     rcx, [rcx+10h]
0x18009f9fa  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009fa01  movzx   eax, ax
0x18009fa04  mov     edx, 0B6h
0x18009fa09  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18009fa0d  call    WPP_SF_Dd
0x18009fa12  jmp     loc_1800A003D
0x18009fa17  test    r15b, r15b
0x18009fa1a  jz      loc_18009FF23
0x18009fa20  mov     r12, [rbp+37h+var_A0]
0x18009fa24  lea     rax, [rbp+37h+var_40]
0x18009fa28  mov     [rsp+0F0h+var_C0], rax; unsigned int *
0x18009fa2d  mov     r9, rdi; unsigned int *
0x18009fa30  mov     rdi, [rbp+37h+var_90]
0x18009fa34  lea     rax, [rbp+37h+var_44]
0x18009fa38  mov     [rsp+0F0h+var_C8], rax; char *
0x18009fa3d  mov     r8b, 1; bool
0x18009fa40  lea     rax, [rbp+37h+var_48]
0x18009fa44  mov     rdx, rdi; unsigned __int16 *
0x18009fa47  mov     rcx, r12; this
0x18009fa4a  mov     [rsp+0F0h+var_D0], rax; unsigned int *
0x18009fa4f  call    ?GetPcrProfileForSeal@CFveTpm@@QEAAJPEBG_NPEBKPEAKPEAW4ePcrBitmapSource@@3@Z; CFveTpm::GetPcrProfileForSeal(ushort const *,bool,ulong const *,ulong *,ePcrBitmapSource *,ulong *)
0x18009fa54  mov     ebx, eax
0x18009fa56  test    eax, eax
0x18009fa58  jns     loc_18009FAED
0x18009fa5e  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fa65  lea     rdi, WPP_GLOBAL_Control
0x18009fa6c  cmp     rcx, rdi
0x18009fa6f  jz      short loc_18009FA8F
0x18009fa71  test    byte ptr [rcx+1Ch], 2
0x18009fa75  jz      short loc_18009FA8F
0x18009fa77  mov     rcx, [rcx+10h]
0x18009fa7b  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009fa82  mov     edx, 0B7h
0x18009fa87  mov     r9d, eax
0x18009fa8a  call    WPP_SF_d
0x18009fa8f  mov     rcx, [rbp+3Fh]; this
0x18009fa93  lea     rax, aGetpcrprofilef_0; "GetPcrProfileForSeal"
0x18009fa9a  mov     r9d, ebx; char *
0x18009fa9d  mov     [rsp+0F0h+var_D0], rax; int
0x18009faa2  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x18009faa9  mov     edx, 0A4Dh; void *
0x18009faae  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009fab3  mov     rcx, cs:WPP_GLOBAL_Control
0x18009faba  cmp     rcx, rdi
0x18009fabd  jz      short loc_18009FAE4
0x18009fabf  test    [rcx+1Ch], sil
0x18009fac3  jz      short loc_18009FAE4
0x18009fac5  mov     edx, 0B8h
0x18009faca  mov     r9d, ebx
0x18009facd  mov     rcx, [rcx+10h]
0x18009fad1  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009fad8  call    WPP_SF_d
0x18009fadd  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fae4  mov     r15, [rbp+37h+var_B0]
0x18009fae8  jmp     loc_18009F87F
0x18009faed  mov     r10, cs:WPP_GLOBAL_Control
0x18009faf4  lea     rbx, WPP_GLOBAL_Control
0x18009fafb  cmp     r10, rbx
0x18009fafe  jz      short loc_18009FB57
0x18009fb00  test    byte ptr [r10+1Ch], 8
0x18009fb05  jz      short loc_18009FB36
0x18009fb07  movzx   ecx, word ptr [rbp+37h+var_44]
0x18009fb0b  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009fb12  mov     eax, dword ptr [rbp+37h+var_40]
0x18009fb15  mov     edx, 0B9h
0x18009fb1a  mov     r9d, [rbp+37h+var_48]
0x18009fb1e  mov     dword ptr [rsp+0F0h+var_C8], eax; char *
0x18009fb22  mov     dword ptr [rsp+0F0h+var_D0], ecx
0x18009fb26  mov     rcx, [r10+10h]
0x18009fb2a  call    WPP_SF_DDD
0x18009fb2f  mov     r10, cs:WPP_GLOBAL_Control
0x18009fb36  cmp     r10, rbx
0x18009fb39  jz      short loc_18009FB57
0x18009fb3b  test    byte ptr [r10+1Ch], 8
0x18009fb40  jz      short loc_18009FB57
0x18009fb42  mov     rcx, [r10+10h]
0x18009fb46  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009fb4d  mov     edx, 0BAh
0x18009fb52  call    WPP_SF_
0x18009fb57  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x18009fb5e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x18009fb63  mov     rcx, r12; this
0x18009fb66  test    al, al
0x18009fb68  jz      loc_18009FD13
0x18009fb6e  call    ?ClosePolicy@CFveTpm@@QEAAJXZ; CFveTpm::ClosePolicy(void)
0x18009fb73  mov     ebx, eax
0x18009fb75  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fb7c  lea     rax, WPP_GLOBAL_Control
0x18009fb83  cmp     rcx, rax
0x18009fb86  jz      short loc_18009FBA6
0x18009fb88  test    [rcx+1Ch], sil
0x18009fb8c  jz      short loc_18009FBA6
0x18009fb8e  mov     rcx, [rcx+10h]
0x18009fb92  lea     r8, WPP_a09fb043d95a349cf604520131dfb76d_Traceguids
0x18009fb99  mov     edx, 0BBh
0x18009fb9e  mov     r9d, ebx
0x18009fba1  call    WPP_SF_d
0x18009fba6  test    ebx, ebx
0x18009fba8  jns     short loc_18009FBD3
0x18009fbaa  mov     edx, 0A60h; void *
0x18009fbaf  mov     rcx, [rbp+3Fh]; this
0x18009fbb3  lea     rax, aTpmcontextClos; "TpmContext->ClosePolicy"
0x18009fbba  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\cornerstone\\fvea"...
0x18009fbc1  mov     [rsp+0F0h+var_D0], rax; int
0x18009fbc6  mov     r9d, ebx; char *
0x18009fbc9  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18009fbce  jmp     loc_18009FADD
0x18009fbd3  mov     r8d, [rbp+37h+var_48]
0x18009fbd7  lea     rax, [rbp+37h+var_58]
0x18009fbdb  mov     r9d, 0FFFFh
0x18009fbe1  mov     [rsp+0F0h+var_D0], rax
0x18009fbe6  lea     rdx, aBitlocker_1; "BitLocker"
0x18009fbed  mov     rcx, rdi
0x18009fbf0  call    cs:__imp_PpfGetPredictionsForInstance
0x18009fbf7  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
