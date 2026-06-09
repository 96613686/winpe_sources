# FveEnableEAS::ProvisionDeviceEncryption(ushort const *)

- ea: `0x18002868c`
- end: `0x180028adc`
- name: `?ProvisionDeviceEncryption@FveEnableEAS@@QEAAJPEBG@Z`
- size: `1104`
- prototype: `__int64 __fastcall(FveEasUtil **this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180007360`
- `0x18000c1a0`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x180002804`
- `0x1800037a0`
- `0x180005018`
- `0x18000e408`
- `0x180013a4c`
- `0x180015d44`
- `0x180015f84`
- `0x180016c74`
- `0x1800179bc`
- `0x180023fe4`
- `0x180026040`
- `0x180028648`
- `0x18002868c`
- `0x180029040`
- `0x1800292c0`
- `0x18002bc10`

## import_xrefs

- `FVEAPI!FveCommitChangesEx` at `0x180028a0b`
- `FVEAPI!FveCommitChangesEx` at `0x180028a0b`
- `FVEAPI!FveCommitChanges` at `0x180028a4b`
- `FVEAPI!FveCommitChanges` at `0x180028a4b`

## string_xrefs

- `0x180028734`: `GetFveVolumePath`
- `0x1800288d8`: `GetReadWriteVolumeHandle`
- `0x1800289e0`: `FvepCreateTPMProtector`
- `0x180028a3d`: `FveCommitChangesEx`
- `0x180028a7d`: `FveCommitChanges`

## pseudocode

```c
__int64 __fastcall FveEnableEAS::ProvisionDeviceEncryption(FveEasUtil **this, const unsigned __int16 *a2)
{
  unsigned int FveVolumePath; // eax
  int ClearKeyGuid; // ebx
  const char *v6; // rax
  __int64 v7; // rdx
  unsigned int RequiredProvisioningSteps; // eax
  int v9; // edx
  int v10; // r8d
  PVOID *v11; // rcx
  char v12; // al
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int FVEVolumeHandle; // eax
  unsigned int v16; // eax
  char v17; // al
  void *v18; // rdi
  unsigned int TPMProtector; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  const char *v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  void **v25; // [rsp+38h] [rbp-C8h] BYREF
  void *v26; // [rsp+40h] [rbp-C0h]
  struct _GUID v27; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v28[264]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  memset_0(v28, 0, 0x208u);
  v24 = 0;
  v25 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  v26 = 0;
  FveVolumePath = CFveDriveType::GetFveVolumePath(a2, v28);
  ClearKeyGuid = FveVolumePath;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, FveVolumePath);
  if ( ClearKeyGuid < 0 )
  {
    v6 = "GetFveVolumePath";
    v7 = 363;
LABEL_69:
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)v7,
      (int)"base\\ngscb\\cornerstone\\fveeas\\fveenableeas\\fveenableeas.cpp",
      (const char *)(unsigned int)ClearKeyGuid,
      (__int64)v6,
      v23);
    goto LABEL_70;
  }
  RequiredProvisioningSteps = FveEasUtil::GetRequiredProvisioningSteps(
                                this[1],
                                v28,
                                (enum RequiredProvisioningSteps *)&v24);
  ClearKeyGuid = RequiredProvisioningSteps;
  v11 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      43,
      &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
      RequiredProvisioningSteps);
    v11 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( ClearKeyGuid < 0 )
  {
    v6 = "GetRequiredProvisioningSteps";
    v7 = 370;
    goto LABEL_69;
  }
  v12 = v24;
  if ( v24 )
  {
    if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
    {
      WPP_SF_SD((unsigned int)v11[2], v9, v10, (unsigned int)v28, v24);
      v12 = v24;
    }
    if ( (v12 & 3) != 0 )
    {
      v13 = FveEnableEAS::BackupRecoveryPassword(this, v28);
      ClearKeyGuid = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v13);
      if ( ClearKeyGuid < 0 )
      {
        v6 = "BackupRecoveryPassword";
        v7 = 389;
        goto LABEL_69;
      }
      v12 = v24;
    }
    if ( (v12 & 8) != 0 )
    {
      v14 = FveEasUtil::EnableAutoUnlock(v28);
      ClearKeyGuid = v14;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v14);
      if ( ClearKeyGuid < 0 )
      {
        v6 = "EnableAutoUnlock";
        v7 = 394;
        goto LABEL_69;
      }
      v12 = v24;
    }
    if ( (v12 & 0x14) != 0 )
    {
      FVEVolumeHandle = FveEasUtil::I_GetFVEVolumeHandle((__int64)v28, (__int64)&v25, 0);
      ClearKeyGuid = FVEVolumeHandle;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          48,
          &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
          FVEVolumeHandle);
      if ( ClearKeyGuid < 0 )
      {
        v6 = "GetReadWriteVolumeHandle";
        v7 = 401;
        goto LABEL_69;
      }
      v16 = FveEasUtil::EnsureVolumeDEManaged(&v25);
      ClearKeyGuid = v16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v16);
      if ( ClearKeyGuid < 0 )
      {
        v6 = "EnsureVolumeDEManaged";
        v7 = 403;
        goto LABEL_69;
      }
      v17 = v24;
      if ( (v24 & 0x10) != 0 )
      {
        v18 = v26;
        v27 = 0;
        ClearKeyGuid = CFveApiWrapper::GetClearKeyGuid(v26, &v27);
        if ( ClearKeyGuid >= 0 )
          ClearKeyGuid = FveDeleteAuthMethod_0(v18, &v27);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
            (unsigned int)ClearKeyGuid);
        if ( ClearKeyGuid < 0 )
        {
          v6 = "EnsureVolumeDEManaged";
          v7 = 413;
          goto LABEL_69;
        }
        v17 = v24;
      }
      if ( (v17 & 4) != 0 )
      {
        TPMProtector = FvepCreateTPMProtector(v26);
        ClearKeyGuid = TPMProtector;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids,
            TPMProtector);
        if ( ClearKeyGuid < 0 )
        {
          v6 = "FvepCreateTPMProtector";
          v7 = 417;
          goto LABEL_69;
        }
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::GetImpl'::`2'::impl) )
      {
        v20 = FveCommitChangesEx(v26, 10);
        ClearKeyGuid = v20;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v20);
        if ( ClearKeyGuid < 0 )
        {
          v6 = "FveCommitChangesEx";
          v7 = 421;
          goto LABEL_69;
        }
      }
      else
      {
        v21 = FveCommitChanges(v26);
        ClearKeyGuid = v21;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v21);
        if ( ClearKeyGuid < 0 )
        {
          v6 = "FveCommitChanges";
          v7 = 423;
          goto LABEL_69;
        }
      }
    }
  }
  else if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 8) != 0 )
  {
    WPP_SF_S(v11[2], (unsigned int)(v24 + 44), &WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids, v28);
  }
LABEL_70:
  v25 = &Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close((__int64)&v25);
  return (unsigned int)ClearKeyGuid;
}

```

## disassembly

```asm
0x18002868c  mov     [rsp-8+arg_10], rbx
0x180028691  push    rbp
0x180028692  push    rsi
0x180028693  push    rdi
0x180028694  push    r12
0x180028696  push    r15
0x180028698  lea     rbp, [rsp-180h]
0x1800286a0  sub     rsp, 280h
0x1800286a7  mov     rax, cs:__security_cookie
0x1800286ae  xor     rax, rsp
0x1800286b1  mov     [rbp+1A0h+var_30], rax
0x1800286b8  mov     rbx, rdx
0x1800286bb  mov     rdi, rcx
0x1800286be  xor     edx, edx; Val
0x1800286c0  mov     r8d, 208h; Size
0x1800286c6  lea     rcx, [rsp+2A0h+var_240]; void *
0x1800286cb  call    memset_0
0x1800286d0  mov     [rsp+2A0h+var_270], 0
0x1800286d8  lea     r12, ??_7?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<FveHandleTraits>::`vftable'
0x1800286df  mov     [rsp+2A0h+var_268], r12
0x1800286e4  mov     [rsp+2A0h+var_260], 0
0x1800286ed  lea     rdx, [rsp+2A0h+var_240]; unsigned __int16 *
0x1800286f2  mov     rcx, rbx; unsigned __int16 *
0x1800286f5  call    ?GetFveVolumePath@CFveDriveType@@SAJPEBGPEAGK@Z; CFveDriveType::GetFveVolumePath(ushort const *,ushort *,ulong)
0x1800286fa  mov     ebx, eax
0x1800286fc  lea     rsi, WPP_GLOBAL_Control
0x180028703  lea     r15, WPP_5c4e39d7d92d3bb8da8dc6718826bb07_Traceguids
0x18002870a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028711  cmp     rcx, rsi
0x180028714  jz      short loc_180028730
0x180028716  test    byte ptr [rcx+1Ch], 40h
0x18002871a  jz      short loc_180028730
0x18002871c  mov     edx, 2Ah ; '*'
0x180028721  mov     r9d, eax
0x180028724  mov     r8, r15
0x180028727  mov     rcx, [rcx+10h]
0x18002872b  call    WPP_SF_d
0x180028730  test    ebx, ebx
0x180028732  jns     short loc_180028745
0x180028734  lea     rax, aGetfvevolumepa; "GetFveVolumePath"
0x18002873b  mov     edx, 16Bh
0x180028740  jmp     loc_180028A89
0x180028745  lea     r8, [rsp+2A0h+var_270]; enum RequiredProvisioningSteps *
0x18002874a  lea     rdx, [rsp+2A0h+var_240]; unsigned __int16 *
0x18002874f  mov     rcx, [rdi+8]; this
0x180028753  call    ?GetRequiredProvisioningSteps@FveEasUtil@@QEBAJPEBGPEAW4RequiredProvisioningSteps@@@Z; FveEasUtil::GetRequiredProvisioningSteps(ushort const *,RequiredProvisioningSteps *)
0x180028758  mov     ebx, eax
0x18002875a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028761  cmp     rcx, rsi
0x180028764  jz      short loc_180028787
0x180028766  test    byte ptr [rcx+1Ch], 40h
0x18002876a  jz      short loc_180028787
0x18002876c  mov     edx, 2Bh ; '+'
0x180028771  mov     r9d, eax
0x180028774  mov     r8, r15
0x180028777  mov     rcx, [rcx+10h]
0x18002877b  call    WPP_SF_d
0x180028780  mov     rcx, cs:WPP_GLOBAL_Control
0x180028787  test    ebx, ebx
0x180028789  jns     short loc_18002879C
0x18002878b  lea     rax, aGetrequiredpro; "GetRequiredProvisioningSteps"
0x180028792  mov     edx, 172h
0x180028797  jmp     loc_180028A89
0x18002879c  mov     eax, [rsp+2A0h+var_270]
0x1800287a0  test    eax, eax
0x1800287a2  jnz     short loc_1800287D0
0x1800287a4  cmp     rcx, rsi
0x1800287a7  jz      loc_180028AA5
0x1800287ad  test    byte ptr [rcx+1Ch], 8
0x1800287b1  jz      loc_180028AA5
0x1800287b7  lea     edx, [rax+2Ch]
0x1800287ba  lea     r9, [rsp+2A0h+var_240]
0x1800287bf  mov     r8, r15
0x1800287c2  mov     rcx, [rcx+10h]
0x1800287c6  call    WPP_SF_S
0x1800287cb  jmp     loc_180028AA5
0x1800287d0  cmp     rcx, rsi
0x1800287d3  jz      short loc_1800287F1
0x1800287d5  test    byte ptr [rcx+1Ch], 8
0x1800287d9  jz      short loc_1800287F1
0x1800287db  mov     [rsp+2A0h+var_280], eax
0x1800287df  lea     r9, [rsp+2A0h+var_240]
0x1800287e4  mov     rcx, [rcx+10h]
0x1800287e8  call    WPP_SF_SD
0x1800287ed  mov     eax, [rsp+2A0h+var_270]
0x1800287f1  test    al, 3
0x1800287f3  jz      short loc_180028843
0x1800287f5  lea     rdx, [rsp+2A0h+var_240]; unsigned __int16 *
0x1800287fa  mov     rcx, rdi; this
0x1800287fd  call    ?BackupRecoveryPassword@FveEnableEAS@@QEAAJPEBG@Z; FveEnableEAS::BackupRecoveryPassword(ushort const *)
0x180028802  mov     ebx, eax
0x180028804  mov     rcx, cs:WPP_GLOBAL_Control
0x18002880b  cmp     rcx, rsi
0x18002880e  jz      short loc_18002882A
0x180028810  test    byte ptr [rcx+1Ch], 40h
0x180028814  jz      short loc_18002882A
0x180028816  mov     edx, 2Eh ; '.'
0x18002881b  mov     r9d, eax
0x18002881e  mov     r8, r15
0x180028821  mov     rcx, [rcx+10h]
0x180028825  call    WPP_SF_d
0x18002882a  test    ebx, ebx
0x18002882c  jns     short loc_18002883F
0x18002882e  lea     rax, aBackuprecovery_1; "BackupRecoveryPassword"
0x180028835  mov     edx, 185h
0x18002883a  jmp     loc_180028A89
0x18002883f  mov     eax, [rsp+2A0h+var_270]
0x180028843  test    al, 8
0x180028845  jz      short loc_180028892
0x180028847  lea     rcx, [rsp+2A0h+var_240]; unsigned __int16 *
0x18002884c  call    ?EnableAutoUnlock@FveEasUtil@@SAJPEBG@Z; FveEasUtil::EnableAutoUnlock(ushort const *)
0x180028851  mov     ebx, eax
0x180028853  mov     rcx, cs:WPP_GLOBAL_Control
0x18002885a  cmp     rcx, rsi
0x18002885d  jz      short loc_180028879
0x18002885f  test    byte ptr [rcx+1Ch], 40h
0x180028863  jz      short loc_180028879
0x180028865  mov     edx, 2Fh ; '/'
0x18002886a  mov     r9d, eax
0x18002886d  mov     r8, r15
0x180028870  mov     rcx, [rcx+10h]
0x180028874  call    WPP_SF_d
0x180028879  test    ebx, ebx
0x18002887b  jns     short loc_18002888E
0x18002887d  lea     rax, aEnableautounlo; "EnableAutoUnlock"
0x180028884  mov     edx, 18Ah
0x180028889  jmp     loc_180028A89
0x18002888e  mov     eax, [rsp+2A0h+var_270]
0x180028892  test    al, 14h
0x180028894  jz      loc_180028AA5
0x18002889a  xor     r8d, r8d
0x18002889d  lea     rdx, [rsp+2A0h+var_268]
0x1800288a2  lea     rcx, [rsp+2A0h+var_240]
0x1800288a7  call    ?I_GetFVEVolumeHandle@FveEasUtil@@CAJPEBGAEAV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@_N@Z; FveEasUtil::I_GetFVEVolumeHandle(ushort const *,Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> &,bool)
0x1800288ac  mov     ebx, eax
0x1800288ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288b5  cmp     rcx, rsi
0x1800288b8  jz      short loc_1800288D4
0x1800288ba  test    byte ptr [rcx+1Ch], 40h
0x1800288be  jz      short loc_1800288D4
0x1800288c0  mov     edx, 30h ; '0'
0x1800288c5  mov     r9d, eax
0x1800288c8  mov     r8, r15
0x1800288cb  mov     rcx, [rcx+10h]
0x1800288cf  call    WPP_SF_d
0x1800288d4  test    ebx, ebx
0x1800288d6  jns     short loc_1800288E9
0x1800288d8  lea     rax, aGetreadwritevo; "GetReadWriteVolumeHandle"
0x1800288df  mov     edx, 191h
0x1800288e4  jmp     loc_180028A89
0x1800288e9  lea     rcx, [rsp+2A0h+var_268]
0x1800288ee  call    ?EnsureVolumeDEManaged@FveEasUtil@@SAJAEBV?$HandleT@UFveHandleTraits@@@Wrappers@WRL@Microsoft@@@Z; FveEasUtil::EnsureVolumeDEManaged(Microsoft::WRL::Wrappers::HandleT<FveHandleTraits> const &)
0x1800288f3  mov     ebx, eax
0x1800288f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800288fc  cmp     rcx, rsi
0x1800288ff  jz      short loc_18002891B
0x180028901  test    byte ptr [rcx+1Ch], 40h
0x180028905  jz      short loc_18002891B
0x180028907  mov     edx, 31h ; '1'
0x18002890c  mov     r9d, eax
0x18002890f  mov     r8, r15
0x180028912  mov     rcx, [rcx+10h]
0x180028916  call    WPP_SF_d
0x18002891b  test    ebx, ebx
0x18002891d  jns     short loc_180028930
0x18002891f  lea     rax, aEnsurevolumede; "EnsureVolumeDEManaged"
0x180028926  mov     edx, 193h
0x18002892b  jmp     loc_180028A89
0x180028930  mov     eax, [rsp+2A0h+var_270]
0x180028934  test    al, 10h
0x180028936  jz      short loc_1800289A6
0x180028938  mov     rdi, [rsp+2A0h+var_260]
0x18002893d  xorps   xmm0, xmm0
0x180028940  movups  xmmword ptr [rsp+2A0h+var_258.Data1], xmm0
0x180028945  lea     rdx, [rsp+2A0h+var_258]; struct _GUID *
0x18002894a  mov     rcx, rdi; void *
0x18002894d  call    ?GetClearKeyGuid@CFveApiWrapper@@SAJPEAXPEAU_GUID@@@Z; CFveApiWrapper::GetClearKeyGuid(void *,_GUID *)
0x180028952  mov     ebx, eax
0x180028954  test    eax, eax
0x180028956  js      short loc_180028967
0x180028958  lea     rdx, [rsp+2A0h+var_258]
0x18002895d  mov     rcx, rdi
0x180028960  call    FveDeleteAuthMethod_0
0x180028965  mov     ebx, eax
0x180028967  mov     rcx, cs:WPP_GLOBAL_Control
0x18002896e  cmp     rcx, rsi
0x180028971  jz      short loc_18002898D
0x180028973  test    byte ptr [rcx+1Ch], 40h
0x180028977  jz      short loc_18002898D
0x180028979  mov     edx, 32h ; '2'
0x18002897e  mov     r9d, ebx
0x180028981  mov     r8, r15
0x180028984  mov     rcx, [rcx+10h]
0x180028988  call    WPP_SF_d
0x18002898d  test    ebx, ebx
0x18002898f  jns     short loc_1800289A2
0x180028991  lea     rax, aEnsurevolumede; "EnsureVolumeDEManaged"
0x180028998  mov     edx, 19Dh
0x18002899d  jmp     loc_180028A89
0x1800289a2  mov     eax, [rsp+2A0h+var_270]
0x1800289a6  test    al, 4
0x1800289a8  jz      short loc_1800289F1
0x1800289aa  mov     rcx, [rsp+2A0h+var_260]; void *
0x1800289af  call    ?FvepCreateTPMProtector@@YAJPEAX@Z; FvepCreateTPMProtector(void *)
0x1800289b4  mov     ebx, eax
0x1800289b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800289bd  cmp     rcx, rsi
0x1800289c0  jz      short loc_1800289DC
0x1800289c2  test    byte ptr [rcx+1Ch], 40h
0x1800289c6  jz      short loc_1800289DC
0x1800289c8  mov     edx, 33h ; '3'
0x1800289cd  mov     r9d, eax
0x1800289d0  mov     r8, r15
0x1800289d3  mov     rcx, [rcx+10h]
0x1800289d7  call    WPP_SF_d
0x1800289dc  test    ebx, ebx
0x1800289de  jns     short loc_1800289F1
0x1800289e0  lea     rax, aFvepcreatetpmp; "FvepCreateTPMProtector"
0x1800289e7  mov     edx, 1A1h
0x1800289ec  jmp     loc_180028A89
0x1800289f1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption> `wil::Feature<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::GetImpl(void)'::`2'::impl
0x1800289f8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BitLocker_Block_Backup_DeviceEncryption>::__private_IsEnabled(void)
0x1800289fd  mov     rcx, [rsp+2A0h+var_260]
0x180028a02  test    al, al
0x180028a04  jz      short loc_180028A4B
0x180028a06  mov     edx, 0Ah
0x180028a0b  call    cs:__imp_FveCommitChangesEx
0x180028a11  mov     ebx, eax
0x180028a13  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a1a  cmp     rcx, rsi
0x180028a1d  jz      short loc_180028A39
0x180028a1f  test    byte ptr [rcx+1Ch], 40h
0x180028a23  jz      short loc_180028A39
0x180028a25  mov     edx, 34h ; '4'
0x180028a2a  mov     r9d, eax
0x180028a2d  mov     r8, r15
0x180028a30  mov     rcx, [rcx+10h]
0x180028a34  call    WPP_SF_d
0x180028a39  test    ebx, ebx
0x180028a3b  jns     short loc_180028AA5
0x180028a3d  lea     rax, aFvecommitchang; "FveCommitChangesEx"
0x180028a44  mov     edx, 1A5h
0x180028a49  jmp     short loc_180028A89
0x180028a4b  call    cs:__imp_FveCommitChanges
0x180028a51  mov     ebx, eax
0x180028a53  mov     rcx, cs:WPP_GLOBAL_Control
0x180028a5a  cmp     rcx, rsi
0x180028a5d  jz      short loc_180028A79
0x180028a5f  test    byte ptr [rcx+1Ch], 40h
0x180028a63  jz      short loc_180028A79
0x180028a65  mov     edx, 35h ; '5'
0x180028a6a  mov     r9d, eax
0x180028a6d  mov     r8, r15
0x180028a70  mov     rcx, [rcx+10h]
0x180028a74  call    WPP_SF_d
0x180028a79  test    ebx, ebx
0x180028a7b  jns     short loc_180028AA5
0x180028a7d  lea     rax, aFvecommitchang_0; "FveCommitChanges"
0x180028a84  mov     edx, 1A7h; void *
0x180028a89  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180028a8e  mov     r9d, ebx; char *
0x180028a91  lea     r8, aBaseNgscbCorne; "base\\ngscb\\cornerstone\\fveeas\\fveen"...
0x180028a98  mov     rcx, [rbp+1A8h]; this
0x180028a9f  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x180028aa4  nop
0x180028aa5  mov     [rsp+2A0h+var_268], r12
0x180028aaa  lea     rcx, [rsp+2A0h+var_268]
0x180028aaf  call    ?Close@?$HandleT@UFveFindHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<FveFindHandleTraits>::Close(void)
0x180028ab4  mov     eax, ebx
0x180028ab6  mov     rcx, [rbp+1A0h+var_30]
0x180028abd  xor     rcx, rsp; StackCookie
0x180028ac0  call    __security_check_cookie
0x180028ac5  mov     rbx, [rsp+2A0h+arg_10]
0x180028acd  add     rsp, 280h
0x180028ad4  pop     r15
0x180028ad6  pop     r12
0x180028ad8  pop     rdi
0x180028ad9  pop     rsi
0x180028ada  pop     rbp
0x180028adb  retn
```
