# CFveTpm::ValidateOSLoaderAuthorityIsForWindowsBootmgr(uchar const *,ulong,ushort,ushort,int *,_TPM_API_HASH_DATA20 *)

- ea: `0x180096390`
- end: `0x180096c2d`
- name: `?ValidateOSLoaderAuthorityIsForWindowsBootmgr@CFveTpm@@MEAAJPEBEKGGPEAHPEAU_TPM_API_HASH_DATA20@@@Z`
- size: `2205`
- prototype: `__int64 __usercall@<rax>(CFveTpm *__hidden this@<rcx>, const unsigned __int8 *@<rdx>, unsigned int@<r8d>, unsigned __int16@<r9w>, unsigned __int16, int *, struct _TPM_API_HASH_DATA20 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config`

## callees

- `0x180005410`
- `0x180008d70`
- `0x1800090c0`
- `0x180009130`
- `0x180042240`
- `0x180043fac`
- `0x180046860`
- `0x18004dba8`
- `0x180053a80`
- `0x180053bac`
- `0x180076b1c`
- `0x180093b3c`
- `0x180095820`
- `0x180096390`
- `0x1800ed528`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180096629`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180096629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096b0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180096b0d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800964d4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800964d4`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180096781`
- `CRYPT32!CertVerifyCertificateChainPolicy` at `0x180096781`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180096686`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x180096686`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18009663d`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18009663d`
- `WINTRUST!WinVerifyTrust` at `0x1800965da`
- `WINTRUST!WinVerifyTrust` at `0x180096af1`
- `WINTRUST!WinVerifyTrust` at `0x1800965da`
- `WINTRUST!WinVerifyTrust` at `0x180096af1`

## pseudocode

```c
__int64 __fastcall CFveTpm::ValidateOSLoaderAuthorityIsForWindowsBootmgr(
        WCHAR *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        int *a6,
        struct _TPM_API_HASH_DATA20 *a7)
{
  __int16 v9; // r12
  HANDLE FileW; // rax
  void *v11; // rdi
  unsigned int LastHresultError; // eax
  int IsNt5; // ebx
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  CRYPT_PROVIDER_DATA *v17; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_SGNR *v19; // rsi
  __int64 v20; // rdx
  struct _CRYPT_PROVIDER_CERT *pasCertChain; // rcx
  unsigned int PredictedHash; // eax
  __int128 v23; // xmm1
  int v24; // eax
  __int128 v25; // xmm0
  __int128 v26; // xmm1
  __int64 *v27; // rax
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  HANDLE v30; // [rsp+40h] [rbp-C0h]
  int v32; // [rsp+4Ch] [rbp-B4h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h]
  __int64 v35; // [rsp+60h] [rbp-A0h]
  unsigned int v36; // [rsp+68h] [rbp-98h]
  int *v37; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v39; // [rsp+80h] [rbp-80h]
  __int64 v40; // [rsp+88h] [rbp-78h] BYREF
  __int64 *v41; // [rsp+90h] [rbp-70h]
  __int128 v42; // [rsp+98h] [rbp-68h] BYREF
  __int128 v43; // [rsp+A8h] [rbp-58h]
  _DWORD pWVTData[6]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v45; // [rsp+D8h] [rbp-28h]
  int v46; // [rsp+E0h] [rbp-20h]
  __int128 *v47; // [rsp+E8h] [rbp-18h]
  int v48; // [rsp+F0h] [rbp-10h]
  HANDLE hStateData; // [rsp+F8h] [rbp-8h]
  __int64 v50; // [rsp+108h] [rbp+8h]
  GUID pgActionID; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v52[8]; // [rsp+130h] [rbp+30h] BYREF
  HANDLE Token; // [rsp+138h] [rbp+38h]
  _CERT_CHAIN_POLICY_PARA pPolicyPara; // [rsp+140h] [rbp+40h] BYREF
  _CERT_CHAIN_POLICY_STATUS pPolicyStatus; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v56[4]; // [rsp+170h] [rbp+70h] BYREF
  int v57; // [rsp+1B0h] [rbp+B0h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v36 = a3;
  v37 = a6;
  v52[0] = 0;
  Token = 0;
  pgActionID.Data1 = 11191659;
  pPolicyPara = 0;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  memset(&pPolicyStatus, 0, sizeof(pPolicyStatus));
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  memset_0(pWVTData, 0, 0x58u);
  v32 = 0;
  v42 = 0;
  v43 = 0;
  memset_0(v56, 0, 0x44u);
  v9 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 641, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
  *a6 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 642, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, this + 853);
  FileW = CreateFileW(this + 853, 0x80000000, 5u, 0, 3u, 0x80u, 0);
  v30 = FileW;
  v11 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    *(_QWORD *)&v43 = FileW;
    LODWORD(v42) = 32;
    v48 = 1;
    v46 = 1;
    v47 = &v42;
    *((_QWORD *)&v42 + 1) = this + 853;
    pWVTData[0] = 88;
    v45 = 2;
    v50 = 1040;
    IsNt5 = CDropImpersonation::Drop((CDropImpersonation *)v52);
    if ( IsNt5 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          644,
          &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
          (unsigned int)IsNt5);
        v14 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( IsNt5 < 0 )
        goto LABEL_84;
    }
    v9 = 838;
    if ( WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData) )
    {
      IsNt5 = -2144272197;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_84;
      v15 = 645;
      goto LABEL_22;
    }
    if ( v52[0] )
    {
      SetThreadToken(0, Token);
      v52[0] = 0;
    }
    v17 = WTHelperProvDataFromStateData(hStateData);
    if ( !v17 )
    {
      IsNt5 = -2144272197;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_84;
      v15 = 647;
LABEL_22:
      v16 = 2150695099LL;
      goto LABEL_11;
    }
    ProvSignerFromChain = WTHelperGetProvSignerFromChain(v17, 0, 0, 0);
    v19 = ProvSignerFromChain;
    if ( ProvSignerFromChain )
    {
      pasCertChain = ProvSignerFromChain->pasCertChain;
      if ( pasCertChain )
      {
        IsNt5 = CFveTpm::ValidateSignerIsNt5(pasCertChain->pCert);
        if ( IsNt5 )
        {
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              650,
              &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
              (unsigned int)IsNt5);
            v14 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( IsNt5 < 0 )
            goto LABEL_84;
        }
        pPolicyPara.cbSize = 16;
        pPolicyPara.dwFlags = 0x10000;
        pPolicyStatus.cbSize = 24;
        if ( CertVerifyCertificateChainPolicy((LPCSTR)7, v19->pChainContext, &pPolicyPara, &pPolicyStatus) )
        {
          if ( !pPolicyStatus.dwError )
          {
            v9 = 839;
            IsNt5 = CFveTpm::ValidateChainContextContainsSignature(v19->pChainContext, a2, v36, &v32);
            if ( IsNt5 )
            {
              v14 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  654,
                  &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
                  (unsigned int)IsNt5);
                v14 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( IsNt5 < 0 )
                goto LABEL_84;
            }
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl'::`2'::impl) )
            {
              if ( *((_DWORD *)this + 15) != 2 )
              {
                v14 = (PVOID *)WPP_GLOBAL_Control;
                goto LABEL_84;
              }
              if ( v32 )
              {
                v14 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
                  goto LABEL_84;
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 655, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
                goto LABEL_12;
              }
              IsNt5 = -2144272197;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 656, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x25E9,
                (unsigned int)"onecore\\base\\ngscb\\cornerstone\\fveapi\\lib_base\\fvetpm.cpp",
                (const char *)0x803100BBLL,
                (int)"Bootmgr signature not found in cert chain - PPF prediction",
                dwFlagsAndAttributes);
              v14 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
                goto LABEL_84;
              v15 = 657;
              goto LABEL_22;
            }
            if ( !v32 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 659, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
              v38 = 0;
              v41 = &v40;
              v33 = 0;
              v40 = (__int64)&v40;
              v34 = 0;
              v39 = FVEAPI_OP_SECUREBOOT_AUTHORITY_SIGNATURE_NOT_IN_BOOTLOADER_CERT_CHAIN_V2;
              v35 = 0;
              FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v33, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v38);
              FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v33);
              v9 = 882;
              PredictedHash = CFveTpm::ValidateNewBootMgrSignerAndGetPredictedHash(
                                (CFveTpm *)this,
                                v19->pChainContext,
                                v36,
                                a4,
                                a5,
                                0,
                                (struct _TPM_API_HASH_DATA20 *)v56);
              IsNt5 = PredictedHash;
              if ( PredictedHash )
              {
                v14 = (PVOID *)WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    660,
                    &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids,
                    PredictedHash);
                  v14 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( IsNt5 < 0 )
                  goto LABEL_84;
              }
              v23 = v56[1];
              v24 = v57;
              *(_OWORD *)a7 = v56[0];
              v25 = v56[2];
              *((_OWORD *)a7 + 1) = v23;
              v26 = v56[3];
              *((_OWORD *)a7 + 2) = v25;
              *((_OWORD *)a7 + 3) = v26;
              *((_DWORD *)a7 + 16) = v24;
              *v37 = 1;
              goto LABEL_12;
            }
            v14 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
              goto LABEL_84;
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 658, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids);
LABEL_34:
            v14 = (PVOID *)WPP_GLOBAL_Control;
            goto LABEL_84;
          }
          IsNt5 = -2144272197;
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
            goto LABEL_84;
          v20 = 653;
        }
        else
        {
          IsNt5 = -2144272197;
          v14 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
            goto LABEL_84;
          v20 = 652;
        }
      }
      else
      {
        IsNt5 = -2144272197;
        v14 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
          goto LABEL_84;
        v20 = 649;
      }
    }
    else
    {
      IsNt5 = -2144272197;
      v14 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 )
        goto LABEL_84;
      v20 = 648;
    }
    WPP_SF_d(v14[2], v20, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, 2150695099LL);
    goto LABEL_34;
  }
  LastHresultError = GetLastHresultError();
  IsNt5 = LastHresultError;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_85;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v15 = 643;
    v16 = LastHresultError;
LABEL_11:
    WPP_SF_d(v14[2], v15, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, v16);
LABEL_12:
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_84:
  v11 = v30;
LABEL_85:
  if ( hStateData )
  {
    v48 = 2;
    WinVerifyTrust(HWND_MESSAGE|0x2LL, &pgActionID, pWVTData);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v11 != (void *)-1LL )
  {
    CloseHandle(v11);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( IsNt5 == -2144272197 )
  {
    switch ( v9 )
    {
      case 838:
        v41 = &v40;
        v40 = (__int64)&v40;
        v27 = FVEAPI_OP_SECUREBOOT_FAILED_BOOTLOADER_SIGNATURE_CHECK;
        break;
      case 839:
        v41 = &v40;
        v40 = (__int64)&v40;
        v27 = FVEAPI_OP_SECUREBOOT_AUTHORITY_SIGNATURE_NOT_IN_BOOTLOADER_CERT_CHAIN;
        break;
      case 882:
        v41 = &v40;
        v40 = (__int64)&v40;
        v27 = FVEAPI_OP_SECUREBOOT_BOOTLOADER_HASH_NOT_PREDICTED;
        break;
      default:
        goto LABEL_97;
    }
    v38 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v39 = v27;
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v33, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v38);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v33);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_97:
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 0x10) != 0 )
    WPP_SF_d(v14[2], 661, &WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids, (unsigned int)IsNt5);
  CDropImpersonation::~CDropImpersonation((CDropImpersonation *)v52);
  return (unsigned int)IsNt5;
}

```

## disassembly

```asm
0x180096390  push    rbp
0x180096392  push    rbx
0x180096393  push    rsi
0x180096394  push    rdi
0x180096395  push    r12
0x180096397  push    r13
0x180096399  push    r14
0x18009639b  push    r15
0x18009639d  lea     rbp, [rsp-0D8h]
0x1800963a5  sub     rsp, 1D8h
0x1800963ac  mov     rax, cs:__security_cookie
0x1800963b3  xor     rax, rsp
0x1800963b6  mov     [rbp+110h+var_50], rax
0x1800963bd  mov     rbx, [rbp+110h+arg_28]
0x1800963c4  xor     eax, eax
0x1800963c6  mov     r15, [rbp+110h+arg_30]
0x1800963cd  mov     r13, rdx
0x1800963d0  mov     [rsp+210h+var_1A8], r8d
0x1800963d5  mov     r14, rcx
0x1800963d8  xorps   xmm0, xmm0
0x1800963db  mov     [rsp+210h+var_1C8], r9w
0x1800963e1  xorps   xmm1, xmm1
0x1800963e4  mov     [rsp+210h+var_1A0], rbx
0x1800963e9  xor     esi, esi
0x1800963eb  mov     [rbp+110h+pPolicyStatus.pvExtraPolicyStatus], rax
0x1800963ef  lea     r8d, [rax+58h]; Size
0x1800963f3  mov     [rbp+110h+var_E0], sil
0x1800963f7  xor     edx, edx; Val
0x1800963f9  mov     [rbp+110h+Token], rsi
0x1800963fd  lea     rcx, [rbp+110h+pWVTData]; void *
0x180096401  mov     [rbp+110h+pgActionID.Data1], 0AAC56Bh
0x180096408  movups  xmmword ptr [rbp+110h+pPolicyPara.cbSize], xmm0
0x18009640c  mov     dword ptr [rbp+110h+pgActionID.Data2], 11D0CD44h
0x180096413  movups  xmmword ptr [rbp+110h+pPolicyStatus.cbSize], xmm1
0x180096417  mov     dword ptr [rbp+110h+pgActionID.Data4], 0C000C28Ch
0x18009641e  mov     dword ptr [rbp+110h+pgActionID.Data4+4], 0EE95C24Fh
0x180096425  call    memset_0
0x18009642a  xorps   xmm0, xmm0
0x18009642d  mov     [rsp+210h+var_1C4], esi
0x180096431  xor     edx, edx; Val
0x180096433  lea     r8d, [rsi+44h]; Size
0x180096437  lea     rcx, [rbp+110h+var_A0]; void *
0x18009643b  movups  [rbp+110h+var_178], xmm0
0x18009643f  movups  [rbp+110h+var_168], xmm0
0x180096443  call    memset_0
0x180096448  mov     r12d, esi
0x18009644b  mov     rcx, cs:WPP_GLOBAL_Control
0x180096452  lea     rdi, WPP_GLOBAL_Control
0x180096459  cmp     rcx, rdi
0x18009645c  jz      short loc_180096479
0x18009645e  test    byte ptr [rcx+1Ch], 10h
0x180096462  jz      short loc_180096479
0x180096464  mov     rcx, [rcx+10h]
0x180096468  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x18009646f  mov     edx, 281h
0x180096474  call    WPP_SF_
0x180096479  mov     [rbx], esi
0x18009647b  mov     rcx, cs:WPP_GLOBAL_Control
0x180096482  cmp     rcx, rdi
0x180096485  jz      short loc_1800964A9
0x180096487  test    byte ptr [rcx+1Ch], 8
0x18009648b  jz      short loc_1800964A9
0x18009648d  mov     rcx, [rcx+10h]
0x180096491  lea     r9, [r14+6AAh]
0x180096498  mov     edx, 282h
0x18009649d  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x1800964a4  call    WPP_SF_S
0x1800964a9  xor     r9d, r9d; lpSecurityAttributes
0x1800964ac  mov     [rsp+210h+hTemplateFile], rsi; hTemplateFile
0x1800964b1  lea     rbx, [r14+6AAh]
0x1800964b8  mov     dword ptr [rsp+210h+dwFlagsAndAttributes], 80h; char *
0x1800964c0  mov     edx, 80000000h; dwDesiredAccess
0x1800964c5  mov     [rsp+210h+dwCreationDisposition], 3; dwCreationDisposition
0x1800964cd  mov     rcx, rbx; lpFileName
0x1800964d0  lea     r8d, [r9+5]; dwShareMode
0x1800964d4  call    cs:__imp_CreateFileW
0x1800964db  nop     dword ptr [rax+rax+00h]
0x1800964e0  mov     [rsp+210h+var_1D0], rax
0x1800964e5  mov     rdi, rax
0x1800964e8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800964ec  jnz     short loc_18009653D
0x1800964ee  call    ?GetLastHresultError@@YAJXZ; GetLastHresultError(void)
0x1800964f3  mov     ebx, eax
0x1800964f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800964fc  lea     r14, WPP_GLOBAL_Control
0x180096503  cmp     rcx, r14
0x180096506  jz      loc_180096AD8
0x18009650c  mov     dil, 40h ; '@'
0x18009650f  test    [rcx+1Ch], dil
0x180096513  jz      loc_180096AD3
0x180096519  mov     edx, 283h
0x18009651e  mov     r9d, eax
0x180096521  mov     rcx, [rcx+10h]
0x180096525  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x18009652c  call    WPP_SF_d
0x180096531  mov     rcx, cs:WPP_GLOBAL_Control
0x180096538  jmp     loc_180096AD3
0x18009653d  mov     qword ptr [rbp+110h+var_168], rax
0x180096541  lea     rcx, [rbp+110h+var_E0]; this
0x180096545  mov     eax, 1
0x18009654a  mov     dword ptr [rbp+110h+var_178], 20h ; ' '
0x180096551  mov     [rbp+110h+var_120], eax
0x180096554  mov     [rbp+110h+var_130], eax
0x180096557  lea     rax, [rbp+110h+var_178]
0x18009655b  mov     [rbp+110h+var_128], rax
0x18009655f  mov     qword ptr [rbp+110h+var_178+8], rbx
0x180096563  mov     [rbp+110h+pWVTData], 58h ; 'X'
0x18009656a  mov     [rbp+110h+var_138], 2
0x180096572  mov     [rbp+110h+var_108], 410h
0x18009657a  call    ?Drop@CDropImpersonation@@QEAAJXZ; CDropImpersonation::Drop(void)
0x18009657f  mov     ebx, eax
0x180096581  mov     dil, 40h ; '@'
0x180096584  test    eax, eax
0x180096586  jz      short loc_1800965C8
0x180096588  mov     rcx, cs:WPP_GLOBAL_Control
0x18009658f  lea     rax, WPP_GLOBAL_Control
0x180096596  cmp     rcx, rax
0x180096599  jz      short loc_1800965C0
0x18009659b  test    [rcx+1Ch], dil
0x18009659f  jz      short loc_1800965C0
0x1800965a1  mov     rcx, [rcx+10h]
0x1800965a5  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x1800965ac  mov     edx, 284h
0x1800965b1  mov     r9d, ebx
0x1800965b4  call    WPP_SF_d
0x1800965b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800965c0  test    ebx, ebx
0x1800965c2  js      loc_180096ACC
0x1800965c8  lea     r8, [rbp+110h+pWVTData]; pWVTData
0x1800965cc  or      rcx, 0FFFFFFFFFFFFFFFFh; hwnd
0x1800965d0  lea     rdx, [rbp+110h+pgActionID]; pgActionID
0x1800965d4  mov     r12d, 346h
0x1800965da  call    cs:__imp_WinVerifyTrust
0x1800965e1  nop     dword ptr [rax+rax+00h]
0x1800965e6  test    eax, eax
0x1800965e8  jz      short loc_18009661D
0x1800965ea  mov     ebx, 803100BBh
0x1800965ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800965f6  lea     r14, WPP_GLOBAL_Control
0x1800965fd  cmp     rcx, r14
0x180096600  jz      loc_180096AD3
0x180096606  test    [rcx+1Ch], dil
0x18009660a  jz      loc_180096AD3
0x180096610  mov     edx, 285h
0x180096615  mov     r9d, ebx
0x180096618  jmp     loc_180096521
0x18009661d  cmp     [rbp+110h+var_E0], sil
0x180096621  jz      short loc_180096639
0x180096623  mov     rdx, [rbp+110h+Token]; Token
0x180096627  xor     ecx, ecx; Thread
0x180096629  call    cs:__imp_SetThreadToken
0x180096630  nop     dword ptr [rax+rax+00h]
0x180096635  mov     [rbp+110h+var_E0], sil
0x180096639  mov     rcx, [rbp+110h+hStateData]; hStateData
0x18009663d  call    cs:__imp_WTHelperProvDataFromStateData
0x180096644  nop     dword ptr [rax+rax+00h]
0x180096649  test    rax, rax
0x18009664c  jnz     short loc_18009667B
0x18009664e  mov     ebx, 803100BBh
0x180096653  mov     rcx, cs:WPP_GLOBAL_Control
0x18009665a  lea     r14, WPP_GLOBAL_Control
0x180096661  cmp     rcx, r14
0x180096664  jz      loc_180096AD3
0x18009666a  test    [rcx+1Ch], dil
0x18009666e  jz      loc_180096AD3
0x180096674  mov     edx, 287h
0x180096679  jmp     short loc_180096615
0x18009667b  xor     r9d, r9d; idxCounterSigner
0x18009667e  xor     r8d, r8d; fCounterSigner
0x180096681  xor     edx, edx; idxSigner
0x180096683  mov     rcx, rax; pProvData
0x180096686  call    cs:__imp_WTHelperGetProvSignerFromChain
0x18009668d  nop     dword ptr [rax+rax+00h]
0x180096692  mov     rsi, rax
0x180096695  test    rax, rax
0x180096698  jnz     short loc_1800966DE
0x18009669a  mov     ebx, 803100BBh
0x18009669f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800966a6  lea     r14, WPP_GLOBAL_Control
0x1800966ad  cmp     rcx, r14
0x1800966b0  jz      short loc_1800966D7
0x1800966b2  test    [rcx+1Ch], dil
0x1800966b6  jz      short loc_1800966D7
0x1800966b8  mov     edx, 288h
0x1800966bd  mov     rcx, [rcx+10h]
0x1800966c1  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x1800966c8  mov     r9d, ebx
0x1800966cb  call    WPP_SF_d
0x1800966d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800966d7  xor     esi, esi
0x1800966d9  jmp     loc_180096AD3
0x1800966de  mov     rcx, [rax+10h]
0x1800966e2  test    rcx, rcx
0x1800966e5  jnz     short loc_18009670C
0x1800966e7  mov     ebx, 803100BBh
0x1800966ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800966f3  lea     r14, WPP_GLOBAL_Control
0x1800966fa  cmp     rcx, r14
0x1800966fd  jz      short loc_1800966D7
0x1800966ff  test    [rcx+1Ch], dil
0x180096703  jz      short loc_1800966D7
0x180096705  mov     edx, 289h
0x18009670a  jmp     short loc_1800966BD
0x18009670c  mov     rcx, [rcx+8]; pCertContext
0x180096710  call    ?ValidateSignerIsNt5@CFveTpm@@KAJPEBU_CERT_CONTEXT@@@Z; CFveTpm::ValidateSignerIsNt5(_CERT_CONTEXT const *)
0x180096715  mov     ebx, eax
0x180096717  test    eax, eax
0x180096719  jz      short loc_18009675B
0x18009671b  mov     rcx, cs:WPP_GLOBAL_Control
0x180096722  lea     rax, WPP_GLOBAL_Control
0x180096729  cmp     rcx, rax
0x18009672c  jz      short loc_180096753
0x18009672e  test    [rcx+1Ch], dil
0x180096732  jz      short loc_180096753
0x180096734  mov     rcx, [rcx+10h]
0x180096738  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x18009673f  mov     edx, 28Ah
0x180096744  mov     r9d, ebx
0x180096747  call    WPP_SF_d
0x18009674c  mov     rcx, cs:WPP_GLOBAL_Control
0x180096753  test    ebx, ebx
0x180096755  js      loc_180096ACA
0x18009675b  mov     [rbp+110h+pPolicyPara.cbSize], 10h
0x180096762  lea     r9, [rbp+110h+pPolicyStatus]; pPolicyStatus
0x180096766  mov     [rbp+110h+pPolicyPara.dwFlags], 10000h
0x18009676d  lea     r8, [rbp+110h+pPolicyPara]; pPolicyPara
0x180096771  mov     [rbp+110h+pPolicyStatus.cbSize], 18h
0x180096778  mov     ecx, 7; pszPolicyOID
0x18009677d  mov     rdx, [rsi+38h]; pChainContext
0x180096781  call    cs:__imp_CertVerifyCertificateChainPolicy
0x180096788  nop     dword ptr [rax+rax+00h]
0x18009678d  test    eax, eax
0x18009678f  jnz     short loc_1800967C1
0x180096791  mov     ebx, 803100BBh
0x180096796  mov     rcx, cs:WPP_GLOBAL_Control
0x18009679d  lea     r14, WPP_GLOBAL_Control
0x1800967a4  cmp     rcx, r14
0x1800967a7  jz      loc_1800966D7
0x1800967ad  test    [rcx+1Ch], dil
0x1800967b1  jz      loc_1800966D7
0x1800967b7  mov     edx, 28Ch
0x1800967bc  jmp     loc_1800966BD
0x1800967c1  cmp     [rbp+110h+pPolicyStatus.dwError], 0
0x1800967c5  jz      short loc_1800967F7
0x1800967c7  mov     ebx, 803100BBh
0x1800967cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800967d3  lea     r14, WPP_GLOBAL_Control
0x1800967da  cmp     rcx, r14
0x1800967dd  jz      loc_1800966D7
0x1800967e3  test    [rcx+1Ch], dil
0x1800967e7  jz      loc_1800966D7
0x1800967ed  mov     edx, 28Dh
0x1800967f2  jmp     loc_1800966BD
0x1800967f7  mov     r8d, [rsp+210h+var_1A8]; unsigned int
0x1800967fc  lea     r9, [rsp+210h+var_1C4]; int *
0x180096801  mov     rcx, [rsi+38h]; struct _CERT_CHAIN_CONTEXT *
0x180096805  mov     rdx, r13; unsigned __int8 *
0x180096808  mov     r12d, 347h
0x18009680e  call    ?ValidateChainContextContainsSignature@CFveTpm@@KAJPEBU_CERT_CHAIN_CONTEXT@@PEBEKPEAH@Z; CFveTpm::ValidateChainContextContainsSignature(_CERT_CHAIN_CONTEXT const *,uchar const *,ulong,int *)
0x180096813  xor     r13d, r13d
0x180096816  mov     ebx, eax
0x180096818  test    eax, eax
0x18009681a  jz      short loc_18009685C
0x18009681c  mov     rcx, cs:WPP_GLOBAL_Control
0x180096823  lea     rax, WPP_GLOBAL_Control
0x18009682a  cmp     rcx, rax
0x18009682d  jz      short loc_180096854
0x18009682f  test    [rcx+1Ch], dil
0x180096833  jz      short loc_180096854
0x180096835  mov     rcx, [rcx+10h]
0x180096839  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x180096840  mov     edx, 28Eh
0x180096845  mov     r9d, ebx
0x180096848  call    WPP_SF_d
0x18009684d  mov     rcx, cs:WPP_GLOBAL_Control
0x180096854  test    ebx, ebx
0x180096856  js      loc_180096ACA
0x18009685c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration> `wil::Feature<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::GetImpl(void)'::`2'::impl
0x180096863  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Ppf_PilotFish_Integration@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ppf_PilotFish_Integration>::__private_IsEnabled(void)
0x180096868  test    al, al
0x18009686a  jz      loc_180096948
0x180096870  xor     esi, esi
0x180096872  cmp     dword ptr [r14+3Ch], 2
0x180096877  jnz     loc_18009693C
0x18009687d  cmp     [rsp+210h+var_1C4], esi
0x180096881  jz      short loc_1800968BE
0x180096883  mov     rcx, cs:WPP_GLOBAL_Control
0x18009688a  lea     r14, WPP_GLOBAL_Control
0x180096891  cmp     rcx, r14
0x180096894  jz      loc_180096AD3
0x18009689a  test    byte ptr [rcx+1Ch], 8
0x18009689e  jz      loc_180096AD3
0x1800968a4  mov     rcx, [rcx+10h]
0x1800968a8  lea     r8, WPP_e8d5ee8888c13d5a7b90a588ecfcaed6_Traceguids
0x1800968af  mov     edx, 28Fh
0x1800968b4  call    WPP_SF_
0x1800968b9  jmp     loc_180096531
0x1800968be  mov     ebx, 803100BBh
0x1800968c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800968ca  lea     r14, WPP_GLOBAL_Control
  ... truncated ...
```
