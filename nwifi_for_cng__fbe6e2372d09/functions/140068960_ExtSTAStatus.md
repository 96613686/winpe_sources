# ExtSTAStatus

- ea: `0x140068960`
- end: `0x1400690d6`
- name: `ExtSTAStatus`
- size: `1910`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, int, struct DOT11_ROAMING_COMPLETION_PARAMETERS *, unsigned int)`
- caller_count: `0`
- callee_count: `40`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14000d21c`
- `0x14000d24c`
- `0x1400188fc`
- `0x140018984`
- `0x14001a734`
- `0x140020dc0`
- `0x140020f20`
- `0x1400390dc`
- `0x14005dc5c`
- `0x14005e1fc`
- `0x14005f348`
- `0x14005f8f4`
- `0x140060044`
- `0x140060374`
- `0x1400609c8`
- `0x140060de4`
- `0x140062bb8`
- `0x140063a20`
- `0x1400640c4`
- `0x1400641b4`
- `0x1400643ac`
- `0x1400645ac`
- `0x1400648d8`
- `0x140067a08`
- `0x140067aa0`
- `0x140067b50`
- `0x140067df0`
- `0x140067e64`
- `0x140067efc`
- `0x1400681f4`
- `0x1400682c0`
- `0x140068500`
- `0x1400685b0`
- `0x14006886c`
- `0x140068960`
- `0x1400690dc`
- `0x140069460`
- `0x14007e914`
- `0x14009bbb0`
- `0x14009bfc0`

## import_xrefs

- `NDIS!NdisFIndicateStatus` at `0x14006908d`
- `NDIS!NdisFIndicateStatus` at `0x14006908d`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068a33`
- `NDIS!NdisAcquireRWLockWrite` at `0x140068a33`
- `NDIS!NdisReleaseRWLock` at `0x1400690ab`
- `NDIS!NdisReleaseRWLock` at `0x1400690ab`

## pseudocode

```c
void __fastcall ExtSTAStatus(struct EXTSTA_VELAN *a1, int a2, struct DOT11_PHY_STATE_PARAMETERS *a3, unsigned int a4)
{
  unsigned int v8; // r8d
  _VELAN *pGenVElan; // rax
  __int64 uPhyId; // r9
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  _VELAN *v13; // r9
  __int64 v14; // rcx
  struct DOT11_MAC_STATE_ENTRY *v15; // rax
  unsigned int Header; // edx
  void *hMiniport; // rbx
  struct _LOCK_STATE_EX LockState[5]; // [rsp+30h] [rbp-69h] BYREF
  struct _NDIS_STATUS_INDICATION StatusIndication; // [rsp+40h] [rbp-59h] BYREF

  LockState[0].OldIrql = 0;
  *(_WORD *)&LockState[0].LockState = 0;
  if ( (a1->ModuleStatus.uValue & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
    {
      WPP_SF_dqD(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_76e11202d3fc32571e344eea390caf41_Traceguids,
        a1->pGenVElan->pAdapt->IfIndex,
        a1,
        a2);
    }
    return;
  }
  if ( a2 == 1073807378 )
  {
    ExtSTAIHVSpecificIndication(a1, a3, a4);
    return;
  }
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, LockState, 0);
  switch ( a2 )
  {
    case 1073938443:
      ExtSTAPhyStateChange(a1, a3, v8);
      break;
    case 1073807383:
      if ( !a3 || a4 < 0x28 )
        break;
      if ( a3->uPhyId != 1 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
LABEL_18:
          a3->Header = (NDIS_OBJECT_HEADER)2621824;
          a3->uPhyId = a1->RoD.LinkState.MediaConnectState;
          *(_OWORD *)&a1->RoD.LinkState.Header.Type = *(_OWORD *)&a3->Header.Type;
          *(_OWORD *)&a1->RoD.LinkState.XmitLinkSpeed = *(_OWORD *)&a3[1].uPhyId;
          *(_QWORD *)&a1->RoD.LinkState.PauseFunctions = *(_QWORD *)&a3[2].bHardwarePhyState;
          ExtSTALinkState(a1, a3);
          break;
        }
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_76e11202d3fc32571e344eea390caf41_Traceguids);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_dDD(
          WPP_GLOBAL_Control->AttachedDevice,
          *(_QWORD *)&a3[1].uPhyId / 0xF4240uLL,
          *(_QWORD *)&a3[2].Header.Type / 0xF4240uLL,
          a1->pGenVElan->pAdapt->IfIndex,
          *(_QWORD *)&a3[1].uPhyId / 0xF4240uLL,
          *(_QWORD *)&a3[2].Header.Type / 0xF4240uLL,
          *(_DWORD *)&LockState[0].OldIrql);
      goto LABEL_18;
    case 1073807365:
      if ( a3 && a4 >= 4 && *(_DWORD *)&a3->Header == -1073676280 )
        ExtSTADriverResetIndication(a1);
      break;
    case 1073938467:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_76e11202d3fc32571e344eea390caf41_Traceguids,
          a1->pGenVElan->pAdapt->IfIndex);
      if ( a1->AssocMgr.bResumeRoamInProgressForNLO )
      {
        pGenVElan = a1->pGenVElan;
        if ( !pGenVElan->bAOACPlatform || !a1->bAOACSupported || !a1->AssocMgr.uNumAssoc )
        {
          if ( pGenVElan->pAdapt->PtDevicePowerState > NdisDeviceStateD0 )
          {
            _InterlockedExchange(&a1->lDeferredNloChangedOp, 1);
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_76e11202d3fc32571e344eea390caf41_Traceguids);
            ExtSTACancelConnRoamingTimer(a1);
            ExtSTATerminateConnection(a1);
          }
        }
      }
      ExtSTAUpcallNLODiscovery(a1);
      break;
    case 1073807395:
      if ( a3 && a4 >= 0xC )
      {
        uPhyId = a3->uPhyId;
        if ( (_DWORD)uPhyId == 1 )
        {
          if ( a1->RoD.LinkState.MediaConnectState != MediaConnectStateConnected )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_76e11202d3fc32571e344eea390caf41_Traceguids);
            *(_DWORD *)&a3->bHardwarePhyState |= 1u;
            a3->uPhyId = 2;
          }
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_76e11202d3fc32571e344eea390caf41_Traceguids, uPhyId);
        }
        break;
      }
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v12 = 18;
LABEL_72:
        WPP_SF_(v11->AttachedDevice, v12, WPP_76e11202d3fc32571e344eea390caf41_Traceguids);
      }
      break;
    case 1073938469:
      ExtSTAANQPQueryCompletion(a1, (struct _DOT11_ANQP_QUERY_COMPLETE_PARAMETERS *)a3, a4);
      break;
    case 1073938481:
      ExtSTAFtmResponse(a1, (struct _DOT11_FTM_RESPONSE_PARAMS *)a3, a4);
      break;
    case 1073938479:
      ExtSTADeviceServiceEvent(a1, a3, a4);
      break;
    default:
      v13 = a1->pGenVElan;
      if ( !v13->bInitState )
      {
        if ( a2 > 1073938473 )
        {
          if ( a2 > 1073938480 )
          {
            switch ( a2 )
            {
              case 1073938482:
                ExtSTANwfPmkidListRequested(a1, (struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *)a3, a4);
                break;
              case 1073938483:
                ExtSTAReceiveCipherKeyParameterIndication(a1, a3, a4);
                break;
              case 1073938484:
                ExtSTASecondaryStaConnectivity(a1, (struct DOT11_SECONDARY_STA_CONNECTIVITY_PARAMS *)a3, a4);
                break;
              case 1073938485:
                ExtSTAReceiveConnectivityInModernStandbyIndication(
                  a1,
                  (struct DOT11_CONNECTIVITY_IN_MODERN_STANDBY_PARAMS *)a3,
                  a4);
                break;
              case 1073938487:
                ExtSTAReceiveTelemetryInfo(a1, a3, a4);
                break;
            }
          }
          else
          {
            switch ( a2 )
            {
              case 1073938480:
                ExtSTASAEParametersNeeded(a1, (struct _DOT11_SAE_AUTH_PARAMS_NEEDED *)a3, a4);
                break;
              case 1073938474:
                v14 = a3[8].uPhyId;
                v15 = 0;
                Header = 0;
                if ( (_DWORD)v14 && *(_DWORD *)&a3[8].bHardwarePhyState )
                {
                  Header = (unsigned int)a3[8].Header;
                  v15 = (struct DOT11_MAC_STATE_ENTRY *)(&a3->Header.Type + v14);
                }
                ExtSTAAssocCompletion((__int64)a1, Header, (__int64)a3, a4, v15);
                break;
              case 1073938475:
                ExtSTARoamingAttemptsExhausted(a1, (struct _DOT11_ROAMING_ATTEMPTS_EXHAUSTED_PARAMETERS *)a3, a4);
                break;
              case 1073938476:
                ExtSTALinkDegraded(a1, a3, a4);
                break;
              case 1073938477:
                ExtSTALinkImproved(a1, a3, a4);
                break;
              default:
                ExtSTACipherKeyCountersUpdated(a1, a3, a4);
                break;
            }
          }
          break;
        }
        if ( a2 == 1073938473 )
        {
          ExtSTAFTParametersNeeded(a1, (struct _DOT11_FT_AUTHENTICATION_RESPONSE_PARAMETERS *)a3, a4);
          break;
        }
        if ( a2 > 1073938438 )
        {
          switch ( a2 )
          {
            case 1073938439:
              ExtSTARoamingCompletion(a1, (struct DOT11_ROAMING_COMPLETION_PARAMETERS *)a3, a4);
              break;
            case 1073938440:
              ExtSTADisAssoc(a1, (struct DOT11_DISASSOCIATION_PARAMETERS *)a3, a4);
              break;
            case 1073938441:
              ExtSTATKIPMICFailure(a1, (struct DOT11_TKIPMIC_FAILURE_PARAMETERS *)a3, a4);
              break;
            case 1073938442:
              ExtSTAPMKIDCandidateList(a1, (struct DOT11_PMKID_CANDIDATE_LIST_PARAMETERS *)a3, a4);
              break;
            case 1073938444:
              ExtSTALinkQuality(a1, a3, a4);
              break;
          }
          break;
        }
        if ( a2 == 1073938438 )
        {
          ExtSTARoamingStart(a1, (struct DOT11_ROAMING_START_PARAMETERS *)a3, a4);
          break;
        }
        if ( a2 != 1073807396 )
        {
          switch ( a2 )
          {
            case 1073938434:
              ExtSTAAssocStart(a1, (struct DOT11_ASSOCIATION_START_PARAMETERS *)a3, a4);
              break;
            case 1073938435:
              ExtSTAAssocCompletion((__int64)a1, 0, (__int64)a3, a4, 0);
              break;
            case 1073938436:
              ExtSTAConnStart(a1, (struct DOT11_CONNECTION_START_PARAMETERS *)a3, a4);
              break;
            case 1073938437:
              ExtSTAConnCompletion(a1, (struct DOT11_CONNECTION_COMPLETION_PARAMETERS *)a3, a4);
              break;
          }
          break;
        }
        if ( a4 >= 4 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              20,
              WPP_76e11202d3fc32571e344eea390caf41_Traceguids,
              v13->pAdapt->IfIndex,
              *(_DWORD *)&a3->Header);
          break;
        }
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          v12 = 19;
          goto LABEL_72;
        }
      }
      break;
  }
  if ( a1->pWFDRole )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_76e11202d3fc32571e344eea390caf41_Traceguids,
        a1->pGenVElan->pAdapt->IfIndex);
    WFDProcessStatus(a1->pWFDRole, a2, a3, a4);
  }
  hMiniport = a1->pGenVElan->hMiniport;
  memset(&StatusIndication.Header.Revision, 0, 0x6Fu);
  StatusIndication.Header = (_NDIS_OBJECT_HEADER)7340440;
  StatusIndication.SourceHandle = hMiniport;
  StatusIndication.StatusCode = a2;
  StatusIndication.StatusBuffer = a3;
  StatusIndication.StatusBufferSize = a4;
  NdisFIndicateStatus(hMiniport, &StatusIndication);
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, LockState);
}

```

## disassembly

```asm
0x140068960  push    rbp
0x140068962  push    rbx
0x140068963  push    rsi
0x140068964  push    rdi
0x140068965  push    r12
0x140068967  push    r14
0x140068969  push    r15
0x14006896b  lea     rbp, [rsp-27h]
0x140068970  sub     rsp, 0C0h
0x140068977  mov     rax, cs:__security_cookie
0x14006897e  xor     rax, rsp
0x140068981  mov     [rbp+57h+var_40], rax
0x140068985  xor     eax, eax
0x140068987  mov     [rbp+57h+LockState.OldIrql], 0
0x14006898b  mov     word ptr [rbp+57h+LockState.LockState], ax
0x14006898f  mov     r14d, r9d
0x140068992  mov     eax, [rcx]
0x140068994  mov     rsi, r8
0x140068997  mov     r15d, edx
0x14006899a  mov     rdi, rcx
0x14006899d  test    al, 4
0x14006899f  jz      short loc_140068A05
0x1400689a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400689a8  lea     rbx, WPP_GLOBAL_Control
0x1400689af  cmp     rcx, rbx
0x1400689b2  jz      loc_1400690B7
0x1400689b8  cmp     byte ptr [rcx+29h], 3
0x1400689bc  jb      loc_1400690B7
0x1400689c2  test    dword ptr [rcx+2Ch], 100h
0x1400689c9  jz      loc_1400690B7
0x1400689cf  mov     rax, [rdi+0A38h]
0x1400689d6  lea     r8, WPP_76e11202d3fc32571e344eea390caf41_Traceguids
0x1400689dd  mov     rcx, [rcx+18h]
0x1400689e1  mov     edx, 0Bh
0x1400689e6  mov     [rsp+0F0h+var_C8], r15d
0x1400689eb  mov     [rsp+0F0h+var_D0], rdi
0x1400689f0  mov     r9, [rax+10h]
0x1400689f4  mov     r9d, [r9+6ACh]
0x1400689fb  call    WPP_SF_dqD
0x140068a00  jmp     loc_1400690B7
0x140068a05  cmp     r15d, 40010012h
0x140068a0c  jnz     short loc_140068A1E
0x140068a0e  mov     r8d, r14d; unsigned int
0x140068a11  mov     rdx, rsi; void *
0x140068a14  call    ?ExtSTAIHVSpecificIndication@@YAXPEAUEXTSTA_VELAN@@PEAXK@Z; ExtSTAIHVSpecificIndication(EXTSTA_VELAN *,void *,ulong)
0x140068a19  jmp     loc_1400690B7
0x140068a1e  mov     rcx, [rcx+0A38h]
0x140068a25  lea     rdx, [rbp+57h+LockState]; LockState
0x140068a29  xor     r8d, r8d; Flags
0x140068a2c  mov     rcx, [rcx+90h]; Lock
0x140068a33  call    cs:__imp_NdisAcquireRWLockWrite
0x140068a3a  nop     dword ptr [rax+rax+00h]
0x140068a3f  lea     rbx, WPP_GLOBAL_Control
0x140068a46  lea     r12, WPP_76e11202d3fc32571e344eea390caf41_Traceguids
0x140068a4d  cmp     r15d, 4003000Bh
0x140068a54  jnz     short loc_140068A66
0x140068a56  mov     rdx, rsi; struct DOT11_PHY_STATE_PARAMETERS *
0x140068a59  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068a5c  call    ?ExtSTAPhyStateChange@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_PHY_STATE_PARAMETERS@@K@Z; ExtSTAPhyStateChange(EXTSTA_VELAN *,DOT11_PHY_STATE_PARAMETERS *,ulong)
0x140068a61  jmp     loc_140069002
0x140068a66  cmp     r15d, 40010017h
0x140068a6d  jnz     loc_140068B3D
0x140068a73  test    rsi, rsi
0x140068a76  jz      loc_140069002
0x140068a7c  cmp     r14d, 28h ; '('
0x140068a80  jb      loc_140069002
0x140068a86  cmp     dword ptr [rsi+4], 1
0x140068a8a  jz      short loc_140068AA9
0x140068a8c  mov     rcx, cs:WPP_GLOBAL_Control
0x140068a93  cmp     rcx, rbx
0x140068a96  jz      short loc_140068AFC
0x140068a98  mov     rcx, [rcx+18h]
0x140068a9c  mov     edx, 0Ch
0x140068aa1  mov     r8, r12
0x140068aa4  call    WPP_SF_
0x140068aa9  mov     rcx, cs:WPP_GLOBAL_Control
0x140068ab0  cmp     rcx, rbx
0x140068ab3  jz      short loc_140068AFC
0x140068ab5  mov     rcx, [rcx+18h]
0x140068ab9  mov     r9, 431BDE82D7B634DBh
0x140068ac3  mov     rax, r9
0x140068ac6  mul     qword ptr [rsi+18h]
0x140068aca  mov     rax, r9
0x140068acd  mov     r8, rdx
0x140068ad0  mul     qword ptr [rsi+10h]
0x140068ad4  mov     rax, [rdi+0A38h]
0x140068adb  shr     r8, 12h
0x140068adf  shr     rdx, 12h
0x140068ae3  mov     [rsp+0F0h+var_C8], r8d
0x140068ae8  mov     r9, [rax+10h]
0x140068aec  mov     dword ptr [rsp+0F0h+var_D0], edx
0x140068af0  mov     r9d, [r9+6ACh]
0x140068af7  call    WPP_SF_dDD
0x140068afc  mov     dword ptr [rsi], 280180h
0x140068b02  mov     rdx, rsi
0x140068b05  mov     eax, [rdi+61Ch]
0x140068b0b  mov     rcx, rdi
0x140068b0e  mov     [rsi+4], eax
0x140068b11  movups  xmm0, xmmword ptr [rsi]
0x140068b14  movups  xmmword ptr [rdi+618h], xmm0
0x140068b1b  movups  xmm1, xmmword ptr [rsi+10h]
0x140068b1f  movups  xmmword ptr [rdi+628h], xmm1
0x140068b26  movsd   xmm0, qword ptr [rsi+20h]
0x140068b2b  movsd   qword ptr [rdi+638h], xmm0
0x140068b33  call    ExtSTALinkState
0x140068b38  jmp     loc_140069002
0x140068b3d  cmp     r15d, 40010005h
0x140068b44  jnz     short loc_140068B72
0x140068b46  test    rsi, rsi
0x140068b49  jz      loc_140069002
0x140068b4f  cmp     r14d, 4
0x140068b53  jb      loc_140069002
0x140068b59  cmp     dword ptr [rsi], 0C0010008h
0x140068b5f  jnz     loc_140069002
0x140068b65  mov     rcx, rdi
0x140068b68  call    ExtSTADriverResetIndication
0x140068b6d  jmp     loc_140069002
0x140068b72  cmp     r15d, 40030023h
0x140068b79  jnz     loc_140068C2D
0x140068b7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140068b86  cmp     rcx, rbx
0x140068b89  jz      short loc_140068BAE
0x140068b8b  mov     rax, [rdi+0A38h]
0x140068b92  mov     edx, 0Eh
0x140068b97  mov     rcx, [rcx+18h]
0x140068b9b  mov     r8, r12
0x140068b9e  mov     r9, [rax+10h]
0x140068ba2  mov     r9d, [r9+6ACh]
0x140068ba9  call    WPP_SF_d
0x140068bae  cmp     dword ptr [rdi+32Ch], 0
0x140068bb5  jz      short loc_140068C20
0x140068bb7  mov     rax, [rdi+0A38h]
0x140068bbe  cmp     byte ptr [rax+1F90h], 0
0x140068bc5  jz      short loc_140068BD9
0x140068bc7  cmp     byte ptr [rdi+0A4Ch], 0
0x140068bce  jz      short loc_140068BD9
0x140068bd0  cmp     dword ptr [rdi+14Ch], 0
0x140068bd7  jnz     short loc_140068C20
0x140068bd9  mov     rax, [rax+10h]
0x140068bdd  cmp     dword ptr [rax+108h], 1
0x140068be4  jg      short loc_140068C15
0x140068be6  mov     rcx, cs:WPP_GLOBAL_Control
0x140068bed  cmp     rcx, rbx
0x140068bf0  jz      short loc_140068C03
0x140068bf2  mov     rcx, [rcx+18h]
0x140068bf6  mov     edx, 0Fh
0x140068bfb  mov     r8, r12
0x140068bfe  call    WPP_SF_
0x140068c03  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068c06  call    ?ExtSTACancelConnRoamingTimer@@YAEPEAUEXTSTA_VELAN@@@Z; ExtSTACancelConnRoamingTimer(EXTSTA_VELAN *)
0x140068c0b  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068c0e  call    ?ExtSTATerminateConnection@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTATerminateConnection(EXTSTA_VELAN *)
0x140068c13  jmp     short loc_140068C20
0x140068c15  mov     eax, 1
0x140068c1a  xchg    eax, [rdi+0A48h]
0x140068c20  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068c23  call    ?ExtSTAUpcallNLODiscovery@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTAUpcallNLODiscovery(EXTSTA_VELAN *)
0x140068c28  jmp     loc_140069002
0x140068c2d  cmp     r15d, 40010023h
0x140068c34  jnz     loc_140068CC8
0x140068c3a  test    rsi, rsi
0x140068c3d  jz      short loc_140068CAE
0x140068c3f  cmp     r14d, 0Ch
0x140068c43  jb      short loc_140068CAE
0x140068c45  mov     r9d, [rsi+4]
0x140068c49  cmp     r9d, 1
0x140068c4d  jnz     short loc_140068C88
0x140068c4f  cmp     [rdi+61Ch], r9d
0x140068c56  jz      loc_140069002
0x140068c5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140068c63  cmp     rcx, rbx
0x140068c66  jz      short loc_140068C78
0x140068c68  mov     rcx, [rcx+18h]
0x140068c6c  lea     edx, [r9+0Fh]
0x140068c70  mov     r8, r12
0x140068c73  call    WPP_SF_
0x140068c78  or      dword ptr [rsi+8], 1
0x140068c7c  mov     dword ptr [rsi+4], 2
0x140068c83  jmp     loc_140069002
0x140068c88  mov     rcx, cs:WPP_GLOBAL_Control
0x140068c8f  cmp     rcx, rbx
0x140068c92  jz      loc_140069002
0x140068c98  mov     rcx, [rcx+18h]
0x140068c9c  mov     edx, 11h
0x140068ca1  mov     r8, r12
0x140068ca4  call    WPP_SF_d
0x140068ca9  jmp     loc_140069002
0x140068cae  mov     rcx, cs:WPP_GLOBAL_Control
0x140068cb5  cmp     rcx, rbx
0x140068cb8  jz      loc_140069002
0x140068cbe  mov     edx, 12h
0x140068cc3  jmp     loc_140068DF1
0x140068cc8  cmp     r15d, 40030025h
0x140068ccf  jnz     short loc_140068CE4
0x140068cd1  mov     r8d, r14d; unsigned int
0x140068cd4  mov     rdx, rsi; struct _DOT11_ANQP_QUERY_COMPLETE_PARAMETERS *
0x140068cd7  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068cda  call    ?ExtSTAANQPQueryCompletion@@YAXPEAUEXTSTA_VELAN@@PEAU_DOT11_ANQP_QUERY_COMPLETE_PARAMETERS@@K@Z; ExtSTAANQPQueryCompletion(EXTSTA_VELAN *,_DOT11_ANQP_QUERY_COMPLETE_PARAMETERS *,ulong)
0x140068cdf  jmp     loc_140069002
0x140068ce4  cmp     r15d, 40030031h
0x140068ceb  jnz     short loc_140068D00
0x140068ced  mov     r8d, r14d; unsigned int
0x140068cf0  mov     rdx, rsi; struct _DOT11_FTM_RESPONSE_PARAMS *
0x140068cf3  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068cf6  call    ?ExtSTAFtmResponse@@YAXPEAUEXTSTA_VELAN@@PEAU_DOT11_FTM_RESPONSE_PARAMS@@K@Z; ExtSTAFtmResponse(EXTSTA_VELAN *,_DOT11_FTM_RESPONSE_PARAMS *,ulong)
0x140068cfb  jmp     loc_140069002
0x140068d00  cmp     r15d, 4003002Fh
0x140068d07  jnz     short loc_140068D1C
0x140068d09  mov     r8d, r14d
0x140068d0c  mov     rdx, rsi
0x140068d0f  mov     rcx, rdi
0x140068d12  call    ExtSTADeviceServiceEvent
0x140068d17  jmp     loc_140069002
0x140068d1c  mov     r9, [rdi+0A38h]
0x140068d23  cmp     dword ptr [r9+15F0h], 0
0x140068d2b  jnz     loc_140069002
0x140068d31  mov     eax, 40030029h
0x140068d36  cmp     r15d, eax
0x140068d39  jg      loc_140068EE1
0x140068d3f  jz      loc_140068ECE
0x140068d45  mov     eax, 40030006h
0x140068d4a  cmp     r15d, eax
0x140068d4d  jg      loc_140068E4C
0x140068d53  jz      loc_140068E39
0x140068d59  mov     ecx, r15d
0x140068d5c  sub     ecx, 40010024h
0x140068d62  jz      short loc_140068DD6
0x140068d64  sub     ecx, 1FFDEh
0x140068d6a  jz      short loc_140068DC3
0x140068d6c  sub     ecx, 1
0x140068d6f  jz      short loc_140068DA5
0x140068d71  sub     ecx, 1
0x140068d74  jz      short loc_140068D92
0x140068d76  cmp     ecx, 1
0x140068d79  jnz     loc_140069002
0x140068d7f  mov     r8d, r14d; unsigned int
0x140068d82  mov     rdx, rsi; struct DOT11_CONNECTION_COMPLETION_PARAMETERS *
0x140068d85  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068d88  call    ?ExtSTAConnCompletion@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_CONNECTION_COMPLETION_PARAMETERS@@K@Z; ExtSTAConnCompletion(EXTSTA_VELAN *,DOT11_CONNECTION_COMPLETION_PARAMETERS *,ulong)
0x140068d8d  jmp     loc_140069002
0x140068d92  mov     r8d, r14d; unsigned int
0x140068d95  mov     rdx, rsi; struct DOT11_CONNECTION_START_PARAMETERS *
0x140068d98  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068d9b  call    ?ExtSTAConnStart@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_CONNECTION_START_PARAMETERS@@K@Z; ExtSTAConnStart(EXTSTA_VELAN *,DOT11_CONNECTION_START_PARAMETERS *,ulong)
0x140068da0  jmp     loc_140069002
0x140068da5  mov     [rsp+0F0h+var_D0], 0
0x140068dae  xor     edx, edx
0x140068db0  mov     r8, rsi
0x140068db3  mov     r9d, r14d
0x140068db6  mov     rcx, rdi
0x140068db9  call    ?ExtSTAAssocCompletion@@YAXPEAUEXTSTA_VELAN@@W4_DOT11_ASSOCIATION_TYPE@@QEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@KPEAUDOT11_CONNECTION_INFO@@@Z; ExtSTAAssocCompletion(EXTSTA_VELAN *,_DOT11_ASSOCIATION_TYPE,DOT11_ASSOCIATION_COMPLETION_PARAMETERS * const,ulong,DOT11_CONNECTION_INFO *)
0x140068dbe  jmp     loc_140069002
0x140068dc3  mov     r8d, r14d; unsigned int
0x140068dc6  mov     rdx, rsi; struct DOT11_ASSOCIATION_START_PARAMETERS *
0x140068dc9  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068dcc  call    ?ExtSTAAssocStart@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_ASSOCIATION_START_PARAMETERS@@K@Z; ExtSTAAssocStart(EXTSTA_VELAN *,DOT11_ASSOCIATION_START_PARAMETERS *,ulong)
0x140068dd1  jmp     loc_140069002
0x140068dd6  cmp     r14d, 4
0x140068dda  jnb     short loc_140068E02
0x140068ddc  mov     rcx, cs:WPP_GLOBAL_Control
0x140068de3  cmp     rcx, rbx
0x140068de6  jz      loc_140069002
0x140068dec  mov     edx, 13h
0x140068df1  mov     rcx, [rcx+18h]
0x140068df5  mov     r8, r12
0x140068df8  call    WPP_SF_
0x140068dfd  jmp     loc_140069002
0x140068e02  mov     rcx, cs:WPP_GLOBAL_Control
0x140068e09  cmp     rcx, rbx
0x140068e0c  jz      loc_140069002
0x140068e12  mov     r9, [r9+10h]
0x140068e16  mov     edx, 14h
0x140068e1b  mov     eax, [rsi]
0x140068e1d  mov     r8, r12
0x140068e20  mov     rcx, [rcx+18h]
0x140068e24  mov     dword ptr [rsp+0F0h+var_D0], eax
0x140068e28  mov     r9d, [r9+6ACh]
0x140068e2f  call    WPP_SF_Dd
0x140068e34  jmp     loc_140069002
0x140068e39  mov     r8d, r14d; unsigned int
0x140068e3c  mov     rdx, rsi; struct DOT11_ROAMING_START_PARAMETERS *
0x140068e3f  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140068e42  call    ?ExtSTARoamingStart@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_ROAMING_START_PARAMETERS@@K@Z; ExtSTARoamingStart(EXTSTA_VELAN *,DOT11_ROAMING_START_PARAMETERS *,ulong)
0x140068e47  jmp     loc_140069002
0x140068e4c  mov     ecx, r15d
0x140068e4f  sub     ecx, 40030007h
0x140068e55  jz      short loc_140068EBB
0x140068e57  sub     ecx, 1
0x140068e5a  jz      short loc_140068EA8
0x140068e5c  sub     ecx, 1
0x140068e5f  jz      short loc_140068E95
0x140068e61  sub     ecx, 1
0x140068e64  jz      short loc_140068E82
0x140068e66  cmp     ecx, 2
0x140068e69  jnz     loc_140069002
0x140068e6f  mov     r8d, r14d
0x140068e72  mov     rdx, rsi
0x140068e75  mov     rcx, rdi
0x140068e78  call    ExtSTALinkQuality
0x140068e7d  jmp     loc_140069002
  ... truncated ...
```
