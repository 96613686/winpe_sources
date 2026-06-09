# DoTurnOnDeviceEncryption(tagDISPPARAMS *,tagVARIANT *)

- ea: `0x180007360`
- end: `0x180007af8`
- name: `?DoTurnOnDeviceEncryption@@YAJPEAUtagDISPPARAMS@@PEAUtagVARIANT@@@Z`
- size: `1944`
- prototype: `__int64 __fastcall(struct tagDISPPARAMS *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `26`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800011d0`
- `0x180001248`
- `0x180001bb0`
- `0x180002774`
- `0x1800037a0`
- `0x180004bd4`
- `0x180005018`
- `0x180007360`
- `0x18000c1a0`
- `0x18000e354`
- `0x18000e408`
- `0x18000e468`
- `0x1800106ec`
- `0x180010a48`
- `0x18001106c`
- `0x180011e28`
- `0x180012660`
- `0x180012be8`
- `0x180013b00`
- `0x180013be4`
- `0x180013c68`
- `0x1800179bc`
- `0x180017eac`
- `0x180023d1c`
- `0x180023e1c`
- `0x18002868c`

## import_xrefs

- `FVEAPI!FveInitializeDeviceEncryption3` at `0x1800075e5`
- `FVEAPI!FveInitializeDeviceEncryption3` at `0x1800075e5`
- `FVEAPI!FveFindFirstVolume` at `0x180007688`
- `FVEAPI!FveFindFirstVolume` at `0x180007688`
- `FVEAPI!FveFindNextVolume` at `0x1800078d9`
- `FVEAPI!FveFindNextVolume` at `0x1800078d9`
- `FVEAPI!FveOpenVolumeByHandle` at `0x1800076bc`
- `FVEAPI!FveOpenVolumeByHandle` at `0x1800076bc`
- `FVEAPI!FveIsVolumeEncryptable` at `0x180007731`
- `FVEAPI!FveIsVolumeEncryptable` at `0x180007731`
- `FVEAPI!FveGetVolumeNameW` at `0x180007772`
- `FVEAPI!FveGetVolumeNameW` at `0x180007772`
- `FVEAPI!FveConversionEncryptEx` at `0x18000796d`
- `FVEAPI!FveConversionEncryptEx` at `0x18000796d`

## pseudocode

```c
__int64 __fastcall DoTurnOnDeviceEncryption(struct tagDISPPARAMS *a1, struct tagVARIANT *a2)
{
  unsigned int DomainInfo; // eax
  unsigned int v4; // edx
  int v5; // ebx
  unsigned int OSVolume; // eax
  unsigned int EncryptableVolumeNamesForBcdDevices; // eax
  char v8; // cl
  unsigned int v9; // eax
  unsigned int v10; // eax
  int v11; // ebx
  unsigned int FVEVolumeHandle; // eax
  unsigned int v13; // eax
  int v14; // eax
  int i; // eax
  int StatusFlags; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  int v21; // eax
  const struct _GUID *v22; // rdx
  _QWORD *v23; // rcx
  int v24; // edx
  unsigned int v25; // eax
  unsigned int v26; // eax
  _QWORD *v27; // rcx
  __int64 v28; // rdx
  unsigned int started; // eax
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  bool v34; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v35; // [rsp+34h] [rbp-CCh] BYREF
  int v36; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v37; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  struct PathBuffer *v39; // [rsp+48h] [rbp-B8h] BYREF
  void **v40; // [rsp+50h] [rbp-B0h] BYREF
  void *v41; // [rsp+58h] [rbp-A8h] BYREF
  void **v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h]
  BOOL v44; // [rsp+70h] [rbp-90h] BYREF
  void **v45; // [rsp+78h] [rbp-88h] BYREF
  __int64 v46; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v47[80]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v48[264]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v49[264]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v34 = 0;
  v42 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v43 = 0;
  v38 = 0;
  v45 = &Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable';
  v46 = 0;
  v35 = 0;
  v40 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v41 = 0;
  memset_0(v48, 0, 0x208u);
  v36 = 260;
  FveEnableEAS::FveEnableEAS(v47);
  v39 = 0;
  v37 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids);
  DomainInfo = FveDomain::GetDomainInfo(&v34, 0);
  v5 = DomainInfo;
  if ( DomainInfo )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, DomainInfo);
    if ( v5 < 0 )
      goto LABEL_112;
  }
  OSVolume = NgscbGetOSVolume(v49);
  v5 = OSVolume;
  if ( OSVolume )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, OSVolume);
    if ( v5 < 0 )
      goto LABEL_112;
  }
  EncryptableVolumeNamesForBcdDevices = FveBcdUtil::GetEncryptableVolumeNamesForBcdDevices(&v39, &v37);
  v5 = EncryptableVolumeNamesForBcdDevices;
  if ( EncryptableVolumeNamesForBcdDevices )
  {
    v8 = (char)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        &WPP_148a443baae43b032f4bebf0684096f9_Traceguids,
        EncryptableVolumeNamesForBcdDevices);
    if ( v5 < 0 )
      goto LABEL_112;
  }
  v9 = NgscbSetPreventDeviceEncryption(v8);
  v5 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v9);
    if ( v5 < 0 )
      goto LABEL_112;
  }
  v10 = NgscbManageDeviceEncryptionOptOutForVolume(v49);
  v5 = v10;
  if ( v10 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v10);
    if ( v5 < 0 )
      goto LABEL_112;
  }
  v11 = 0;
  if ( !v34 )
  {
    FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle(v49, &v42, 0);
    v5 = FVEVolumeHandle;
    if ( FVEVolumeHandle )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          &WPP_148a443baae43b032f4bebf0684096f9_Traceguids,
          FVEVolumeHandle);
      if ( v5 < 0 )
        goto LABEL_112;
    }
    v13 = FveInitializeDeviceEncryption3(v43, 8198, FVE_GUID_PROV_SCENARIO_MANUALDE_FVEUI_OSV);
    v5 = v13;
    if ( v13 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v13);
      if ( v5 < 0 )
        goto LABEL_112;
    }
    Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v42);
    v14 = TryProvisionOSVolume(v49, (struct FveEnableEAS *)v47);
    v11 = v14;
    if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        35,
        &WPP_148a443baae43b032f4bebf0684096f9_Traceguids,
        (unsigned int)v14);
  }
  v38 = 0xFFFFFFFF00000001uLL;
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v45);
  for ( i = FveFindFirstVolume(&v46, &v38); i >= 0; i = FveFindNextVolume(v46, &v38) )
  {
    Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v40);
    if ( (int)FveOpenVolumeByHandle(v46, 0, 0, 0xFFFFFFFFLL, 0, &v41) < 0 )
      continue;
    StatusFlags = CFveApiWrapper::GetStatusFlags(v41, &v35);
    if ( StatusFlags >= 0 )
    {
      if ( (v35 & 0x4000) != 0 || (v35 & 0x400000) != 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids);
      }
      else
      {
        StatusFlags = FveIsVolumeEncryptable(v41);
        if ( StatusFlags >= 0 )
        {
          v36 = 260;
          StatusFlags = FveGetVolumeNameW(v41, &v36, v48);
          if ( StatusFlags >= 0 )
          {
            if ( FveBcdUtil::FindExistingPath(v39, v37, v48) )
            {
              v19 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                v20 = 40;
LABEL_65:
                WPP_SF_S(v19[2], v20, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v48);
                continue;
              }
            }
            else
            {
              v21 = NgscbManageDeviceEncryptionOptOutForVolume(v48);
              if ( v21 >= 0 )
              {
                if ( !v34 )
                {
                  v21 = FveEasUtil::InitializeFDV(v48, v22);
                  if ( v21 >= 0 )
                  {
                    if ( v11 >= 0 )
                    {
                      v21 = FveEnableEAS::ProvisionDeviceEncryption((FveEnableEAS *)v47, v48);
                      if ( v21 < 0 )
                      {
                        v23 = WPP_GLOBAL_Control;
                        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                        {
                          v24 = 44;
                          goto LABEL_70;
                        }
                      }
                    }
                    else
                    {
                      v19 = WPP_GLOBAL_Control;
                      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                      {
                        v20 = 43;
                        goto LABEL_65;
                      }
                    }
                  }
                  else
                  {
                    v23 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      v24 = 42;
                      goto LABEL_70;
                    }
                  }
                }
              }
              else
              {
                v23 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  v24 = 41;
LABEL_70:
                  WPP_SF_Sd(
                    v23[2],
                    v24,
                    (unsigned int)&WPP_148a443baae43b032f4bebf0684096f9_Traceguids,
                    (unsigned int)v48,
                    v21);
                  continue;
                }
              }
            }
          }
          else
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v18 = 39;
              goto LABEL_50;
            }
          }
        }
        else
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            v18 = 38;
            goto LABEL_50;
          }
        }
      }
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        v18 = 36;
LABEL_50:
        WPP_SF_d(v17[2], v18, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, (unsigned int)StatusFlags);
        continue;
      }
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, (unsigned int)i);
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v40);
  if ( v34 )
  {
    started = BdeSvcApiStartService();
    v5 = started;
    if ( !started )
      goto LABEL_109;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, started);
    if ( v5 >= 0 )
    {
LABEL_109:
      v26 = BdeSvcApiDoTurnOnDeviceEncryption();
      v5 = v26;
      if ( v26 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v28 = 49;
LABEL_111:
          WPP_SF_d(v27[2], v28, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v26);
        }
      }
    }
  }
  else
  {
    v25 = FveEasUtil::I_GetFVEVolumeHandle(v49, &v42, 0);
    v5 = v25;
    if ( !v25 )
      goto LABEL_100;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_148a443baae43b032f4bebf0684096f9_Traceguids, v25);
    if ( v5 >= 0 )
    {
LABEL_100:
      v26 = FveConversionEncryptEx(v43, 0);
      v5 = v26;
      if ( v26 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v28 = 47;
          goto LABEL_111;
        }
      }
    }
  }
LABEL_112:
  if ( v39 )
  {
    PathBuffer::`vector deleting destructor'(v39, v4);
    v39 = 0;
  }
  a2->vt = 19;
  a2->lVal = v5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      &WPP_148a443baae43b032f4bebf0684096f9_Traceguids,
      (unsigned int)v5);
  if ( (unsigned int)dword_18003D518 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18003D518) )
  {
    v35 = v5;
    v44 = v34;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&dword_18003729C,
      v31,
      v32,
      (__int64)&v44,
      (__int64)&v35);
  }
  FveEnableEAS::~FveEnableEAS((FveEnableEAS *)v47);
  v40 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v40);
  v45 = &Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v45);
  v42 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(&v42);
  return 0;
}

```

## disassembly

```asm
0x180007360  mov     [rsp-8+arg_0], rbx
0x180007365  mov     [rsp-8+arg_10], rsi
0x18000736a  push    rbp
0x18000736b  push    r12
0x18000736d  push    r15
0x18000736f  lea     rbp, [rsp-410h]
0x180007377  sub     rsp, 510h
0x18000737e  mov     rax, cs:__security_cookie
0x180007385  xor     rax, rsp
0x180007388  mov     [rbp+420h+var_20], rax
0x18000738f  mov     rsi, rdx
0x180007392  mov     [rsp+520h+var_4F0], 0
0x180007397  lea     rax, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x18000739e  mov     [rsp+520h+var_4C0], rax
0x1800073a3  mov     [rsp+520h+var_4B8], 0
0x1800073ac  mov     [rsp+520h+var_4E0], 0
0x1800073b5  lea     rcx, ??_7?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::`vftable'
0x1800073bc  mov     [rsp+520h+var_4A8], rcx
0x1800073c1  mov     [rbp+420h+var_4A0], 0
0x1800073c9  mov     [rsp+520h+var_4EC], 0
0x1800073d1  mov     [rsp+520h+var_4D0], rax
0x1800073d6  mov     [rsp+520h+var_4C8], 0
0x1800073df  xor     edx, edx; Val
0x1800073e1  mov     r8d, 208h; Size
0x1800073e7  lea     rcx, [rbp+420h+var_440]; void *
0x1800073eb  call    memset_0
0x1800073f0  mov     [rsp+520h+var_4E8], 104h
0x1800073f8  lea     rcx, [rbp+420h+var_490]
0x1800073fc  call    ??0FveEnableEAS@@QEAA@W4BackupOptions@0@@Z; FveEnableEAS::FveEnableEAS(FveEnableEAS::BackupOptions)
0x180007401  nop
0x180007402  mov     [rsp+520h+var_4D8], 0
0x18000740b  mov     [rsp+520h+var_4E4], 0
0x180007413  lea     r15, WPP_GLOBAL_Control
0x18000741a  lea     r12, WPP_148a443baae43b032f4bebf0684096f9_Traceguids
0x180007421  mov     rcx, cs:WPP_GLOBAL_Control
0x180007428  cmp     rcx, r15
0x18000742b  jz      short loc_180007444
0x18000742d  test    byte ptr [rcx+1Ch], 20h
0x180007431  jz      short loc_180007444
0x180007433  mov     edx, 1Bh
0x180007438  mov     r8, r12
0x18000743b  mov     rcx, [rcx+10h]
0x18000743f  call    WPP_SF_
0x180007444  xor     edx, edx; struct _GUID *
0x180007446  lea     rcx, [rsp+520h+var_4F0]; bool *
0x18000744b  call    ?GetDomainInfo@FveDomain@@SAJPEA_NPEAU_GUID@@@Z; FveDomain::GetDomainInfo(bool *,_GUID *)
0x180007450  mov     ebx, eax
0x180007452  test    eax, eax
0x180007454  jz      short loc_180007484
0x180007456  mov     rcx, cs:WPP_GLOBAL_Control
0x18000745d  cmp     rcx, r15
0x180007460  jz      short loc_18000747C
0x180007462  test    byte ptr [rcx+1Ch], 40h
0x180007466  jz      short loc_18000747C
0x180007468  mov     edx, 1Ch
0x18000746d  mov     r9d, eax
0x180007470  mov     r8, r12
0x180007473  mov     rcx, [rcx+10h]
0x180007477  call    WPP_SF_d
0x18000747c  test    ebx, ebx
0x18000747e  js      loc_1800079F8
0x180007484  lea     rcx, [rbp+420h+var_230]
0x18000748b  call    NgscbGetOSVolume
0x180007490  mov     ebx, eax
0x180007492  test    eax, eax
0x180007494  jz      short loc_1800074C4
0x180007496  mov     rcx, cs:WPP_GLOBAL_Control
0x18000749d  cmp     rcx, r15
0x1800074a0  jz      short loc_1800074BC
0x1800074a2  test    byte ptr [rcx+1Ch], 40h
0x1800074a6  jz      short loc_1800074BC
0x1800074a8  mov     edx, 1Dh
0x1800074ad  mov     r9d, eax
0x1800074b0  mov     r8, r12
0x1800074b3  mov     rcx, [rcx+10h]
0x1800074b7  call    WPP_SF_d
0x1800074bc  test    ebx, ebx
0x1800074be  js      loc_1800079F8
0x1800074c4  lea     rdx, [rsp+520h+var_4E4]; unsigned int *
0x1800074c9  lea     rcx, [rsp+520h+var_4D8]; struct PathBuffer **
0x1800074ce  call    ?GetEncryptableVolumeNamesForBcdDevices@FveBcdUtil@@SAJPEAPEAVPathBuffer@@PEAK@Z; FveBcdUtil::GetEncryptableVolumeNamesForBcdDevices(PathBuffer * *,ulong *)
0x1800074d3  mov     ebx, eax
0x1800074d5  test    eax, eax
0x1800074d7  jz      short loc_180007507
0x1800074d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074e0  cmp     rcx, r15
0x1800074e3  jz      short loc_1800074FF
0x1800074e5  test    byte ptr [rcx+1Ch], 40h
0x1800074e9  jz      short loc_1800074FF
0x1800074eb  mov     edx, 1Eh
0x1800074f0  mov     r9d, eax
0x1800074f3  mov     r8, r12
0x1800074f6  mov     rcx, [rcx+10h]
0x1800074fa  call    WPP_SF_d
0x1800074ff  test    ebx, ebx
0x180007501  js      loc_1800079F8
0x180007507  call    ?NgscbSetPreventDeviceEncryption@@YAJ_N@Z; NgscbSetPreventDeviceEncryption(bool)
0x18000750c  mov     ebx, eax
0x18000750e  test    eax, eax
0x180007510  jz      short loc_180007540
0x180007512  mov     rcx, cs:WPP_GLOBAL_Control
0x180007519  cmp     rcx, r15
0x18000751c  jz      short loc_180007538
0x18000751e  test    byte ptr [rcx+1Ch], 40h
0x180007522  jz      short loc_180007538
0x180007524  mov     edx, 1Fh
0x180007529  mov     r9d, eax
0x18000752c  mov     r8, r12
0x18000752f  mov     rcx, [rcx+10h]
0x180007533  call    WPP_SF_d
0x180007538  test    ebx, ebx
0x18000753a  js      loc_1800079F8
0x180007540  lea     rcx, [rbp+420h+var_230]
0x180007547  call    ?NgscbManageDeviceEncryptionOptOutForVolume@@YAJPEBGW4NgscbManageDEVolumeOptOutOption@@@Z; NgscbManageDeviceEncryptionOptOutForVolume(ushort const *,NgscbManageDEVolumeOptOutOption)
0x18000754c  mov     ebx, eax
0x18000754e  test    eax, eax
0x180007550  jz      short loc_180007580
0x180007552  mov     rcx, cs:WPP_GLOBAL_Control
0x180007559  cmp     rcx, r15
0x18000755c  jz      short loc_180007578
0x18000755e  test    byte ptr [rcx+1Ch], 40h
0x180007562  jz      short loc_180007578
0x180007564  mov     edx, 20h ; ' '
0x180007569  mov     r9d, eax
0x18000756c  mov     r8, r12
0x18000756f  mov     rcx, [rcx+10h]
0x180007573  call    WPP_SF_d
0x180007578  test    ebx, ebx
0x18000757a  js      loc_1800079F8
0x180007580  xor     ebx, ebx
0x180007582  cmp     [rsp+520h+var_4F0], bl
0x180007586  jnz     loc_180007665
0x18000758c  xor     r8d, r8d
0x18000758f  lea     rdx, [rsp+520h+var_4C0]
0x180007594  lea     rcx, [rbp+420h+var_230]
0x18000759b  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x1800075a0  mov     ebx, eax
0x1800075a2  test    eax, eax
0x1800075a4  jz      short loc_1800075D4
0x1800075a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075ad  cmp     rcx, r15
0x1800075b0  jz      short loc_1800075CC
0x1800075b2  test    byte ptr [rcx+1Ch], 40h
0x1800075b6  jz      short loc_1800075CC
0x1800075b8  mov     edx, 21h ; '!'
0x1800075bd  mov     r9d, eax
0x1800075c0  mov     r8, r12
0x1800075c3  mov     rcx, [rcx+10h]
0x1800075c7  call    WPP_SF_d
0x1800075cc  test    ebx, ebx
0x1800075ce  js      loc_1800079F8
0x1800075d4  lea     r8, FVE_GUID_PROV_SCENARIO_MANUALDE_FVEUI_OSV
0x1800075db  mov     edx, 2006h
0x1800075e0  mov     rcx, [rsp+520h+var_4B8]
0x1800075e5  call    cs:__imp_FveInitializeDeviceEncryption3
0x1800075eb  mov     ebx, eax
0x1800075ed  test    eax, eax
0x1800075ef  jz      short loc_18000761F
0x1800075f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075f8  cmp     rcx, r15
0x1800075fb  jz      short loc_180007617
0x1800075fd  test    byte ptr [rcx+1Ch], 40h
0x180007601  jz      short loc_180007617
0x180007603  mov     edx, 22h ; '"'
0x180007608  mov     r9d, eax
0x18000760b  mov     r8, r12
0x18000760e  mov     rcx, [rcx+10h]
0x180007612  call    WPP_SF_d
0x180007617  test    ebx, ebx
0x180007619  js      loc_1800079F8
0x18000761f  lea     rcx, [rsp+520h+var_4C0]
0x180007624  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180007629  lea     rdx, [rbp+420h+var_490]; struct FveEnableEAS *
0x18000762d  lea     rcx, [rbp+420h+var_230]; unsigned __int16 *
0x180007634  call    ?TryProvisionOSVolume@@YAJPEBGAEAVFveEnableEAS@@@Z; TryProvisionOSVolume(ushort const *,FveEnableEAS &)
0x180007639  mov     ebx, eax
0x18000763b  test    eax, eax
0x18000763d  jns     short loc_180007665
0x18000763f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007646  cmp     rcx, r15
0x180007649  jz      short loc_180007665
0x18000764b  test    byte ptr [rcx+1Ch], 2
0x18000764f  jz      short loc_180007665
0x180007651  mov     edx, 23h ; '#'
0x180007656  mov     r9d, eax
0x180007659  mov     r8, r12
0x18000765c  mov     rcx, [rcx+10h]
0x180007660  call    WPP_SF_d
0x180007665  mov     dword ptr [rsp+520h+var_4E0], 1
0x18000766d  mov     dword ptr [rsp+520h+var_4E0+4], 0FFFFFFFFh
0x180007675  lea     rcx, [rsp+520h+var_4A8]
0x18000767a  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x18000767f  lea     rdx, [rsp+520h+var_4E0]
0x180007684  lea     rcx, [rbp+420h+var_4A0]
0x180007688  call    cs:__imp_FveFindFirstVolume
0x18000768e  jmp     loc_1800078DF
0x180007693  lea     rcx, [rsp+520h+var_4D0]
0x180007698  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x18000769d  lea     rax, [rsp+520h+var_4C8]
0x1800076a2  mov     [rsp+520h+var_4F8], rax
0x1800076a7  mov     dword ptr [rsp+520h+var_500], 0
0x1800076af  or      r9d, 0FFFFFFFFh
0x1800076b3  xor     r8d, r8d
0x1800076b6  xor     edx, edx
0x1800076b8  mov     rcx, [rbp+420h+var_4A0]
0x1800076bc  call    cs:__imp_FveOpenVolumeByHandle
0x1800076c2  test    eax, eax
0x1800076c4  js      loc_1800078D0
0x1800076ca  lea     rdx, [rsp+520h+var_4EC]; unsigned int *
0x1800076cf  mov     rcx, [rsp+520h+var_4C8]; void *
0x1800076d4  call    ?GetStatusFlags@CFveApiWrapper@@SAJPEAXPEAK@Z; CFveApiWrapper::GetStatusFlags(void *,ulong *)
0x1800076d9  test    eax, eax
0x1800076db  jns     short loc_180007710
0x1800076dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076e4  cmp     rcx, r15
0x1800076e7  jz      loc_1800078D0
0x1800076ed  test    byte ptr [rcx+1Ch], 2
0x1800076f1  jz      loc_1800078D0
0x1800076f7  mov     edx, 24h ; '$'
0x1800076fc  mov     r9d, eax
0x1800076ff  mov     r8, r12
0x180007702  mov     rcx, [rcx+10h]
0x180007706  call    WPP_SF_d
0x18000770b  jmp     loc_1800078D0
0x180007710  test    [rsp+520h+var_4EC], 4000h
0x180007718  jnz     loc_1800078AD
0x18000771e  test    [rsp+520h+var_4EC], 400000h
0x180007726  jnz     loc_1800078AD
0x18000772c  mov     rcx, [rsp+520h+var_4C8]
0x180007731  call    cs:__imp_FveIsVolumeEncryptable
0x180007737  test    eax, eax
0x180007739  jns     short loc_18000775C
0x18000773b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007742  cmp     rcx, r15
0x180007745  jz      loc_1800078D0
0x18000774b  test    byte ptr [rcx+1Ch], 8
0x18000774f  jz      loc_1800078D0
0x180007755  mov     edx, 26h ; '&'
0x18000775a  jmp     short loc_1800076FC
0x18000775c  mov     [rsp+520h+var_4E8], 104h
0x180007764  lea     r8, [rbp+420h+var_440]
0x180007768  lea     rdx, [rsp+520h+var_4E8]
0x18000776d  mov     rcx, [rsp+520h+var_4C8]
0x180007772  call    cs:__imp_FveGetVolumeNameW
0x180007778  test    eax, eax
0x18000777a  jns     short loc_1800077A0
0x18000777c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007783  cmp     rcx, r15
0x180007786  jz      loc_1800078D0
0x18000778c  test    byte ptr [rcx+1Ch], 2
0x180007790  jz      loc_1800078D0
0x180007796  mov     edx, 27h ; '''
0x18000779b  jmp     loc_1800076FC
0x1800077a0  lea     r8, [rbp+420h+var_440]; unsigned __int16 *
0x1800077a4  mov     edx, [rsp+520h+var_4E4]; unsigned int
0x1800077a8  mov     rcx, [rsp+520h+var_4D8]; struct PathBuffer *
0x1800077ad  call    ?FindExistingPath@FveBcdUtil@@SA_NPEAVPathBuffer@@KPEBG@Z; FveBcdUtil::FindExistingPath(PathBuffer *,ulong,ushort const *)
0x1800077b2  test    al, al
0x1800077b4  jz      short loc_1800077EA
0x1800077b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077bd  cmp     rcx, r15
0x1800077c0  jz      loc_1800078D0
0x1800077c6  test    byte ptr [rcx+1Ch], 8
0x1800077ca  jz      loc_1800078D0
0x1800077d0  mov     edx, 28h ; '('
0x1800077d5  lea     r9, [rbp+420h+var_440]
0x1800077d9  mov     r8, r12
0x1800077dc  mov     rcx, [rcx+10h]
0x1800077e0  call    WPP_SF_S
0x1800077e5  jmp     loc_1800078D0
0x1800077ea  lea     rcx, [rbp+420h+var_440]
0x1800077ee  call    ?NgscbManageDeviceEncryptionOptOutForVolume@@YAJPEBGW4NgscbManageDEVolumeOptOutOption@@@Z; NgscbManageDeviceEncryptionOptOutForVolume(ushort const *,NgscbManageDEVolumeOptOutOption)
0x1800077f3  test    eax, eax
0x1800077f5  jns     short loc_18000782F
0x1800077f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077fe  cmp     rcx, r15
0x180007801  jz      loc_1800078D0
0x180007807  test    byte ptr [rcx+1Ch], 2
0x18000780b  jz      loc_1800078D0
0x180007811  mov     edx, 29h ; ')'
0x180007816  mov     dword ptr [rsp+520h+var_500], eax
0x18000781a  lea     r9, [rbp+420h+var_440]
0x18000781e  mov     r8, r12
0x180007821  mov     rcx, [rcx+10h]
0x180007825  call    WPP_SF_Sd
0x18000782a  jmp     loc_1800078D0
0x18000782f  cmp     [rsp+520h+var_4F0], 0
0x180007834  jnz     loc_1800078D0
0x18000783a  lea     rcx, [rbp+420h+var_440]; unsigned __int16 *
0x18000783e  call    ?InitializeFDV@FveEasUtil@@SAJPEBGPEBU_GUID@@@Z; FveEasUtil::InitializeFDV(ushort const *,_GUID const *)
0x180007843  test    eax, eax
0x180007845  jns     short loc_180007860
0x180007847  mov     rcx, cs:WPP_GLOBAL_Control
0x18000784e  cmp     rcx, r15
0x180007851  jz      short loc_1800078D0
0x180007853  test    byte ptr [rcx+1Ch], 2
0x180007857  jz      short loc_1800078D0
0x180007859  mov     edx, 2Ah ; '*'
0x18000785e  jmp     short loc_180007816
0x180007860  test    ebx, ebx
  ... truncated ...
```
