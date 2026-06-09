# ExtSTAStatus

- ea: `0x140067130`
- end: `0x1400678a3`
- name: `ExtSTAStatus`
- size: `1907`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, int, struct DOT11_ROAMING_COMPLETION_PARAMETERS *, unsigned int)`
- caller_count: `0`
- callee_count: `40`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14000d22c`
- `0x14000d25c`
- `0x1400188fc`
- `0x140018984`
- `0x14001a734`
- `0x140020dc0`
- `0x140020f20`
- `0x140038ebc`
- `0x14005c43c`
- `0x14005c9dc`
- `0x14005db18`
- `0x14005e0c4`
- `0x14005e814`
- `0x14005eb44`
- `0x14005f198`
- `0x14005f5b4`
- `0x140061388`
- `0x1400621f0`
- `0x140062894`
- `0x140062984`
- `0x140062b7c`
- `0x140062d7c`
- `0x1400630a8`
- `0x1400661d8`
- `0x140066270`
- `0x140066320`
- `0x1400665c0`
- `0x140066634`
- `0x1400666cc`
- `0x1400669c4`
- `0x140066a90`
- `0x140066cd0`
- `0x140066d80`
- `0x14006703c`
- `0x140067130`
- `0x1400678ac`
- `0x140067c30`
- `0x14007d0e4`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `NDIS!NdisFIndicateStatus` at `0x14006785a`
- `NDIS!NdisFIndicateStatus` at `0x14006785a`
- `NDIS!NdisAcquireRWLockWrite` at `0x140067203`
- `NDIS!NdisAcquireRWLockWrite` at `0x140067203`
- `NDIS!NdisReleaseRWLock` at `0x140067878`
- `NDIS!NdisReleaseRWLock` at `0x140067878`

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
          ExtSTAFTParametersNeeded(a1, (struct _DOT11_FT_AUTHENTICATION_RESPONSE_PARAMETERS *)a3, v8);
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
0x140067130  push    rbp
0x140067132  push    rbx
0x140067133  push    rsi
0x140067134  push    rdi
0x140067135  push    r12
0x140067137  push    r14
0x140067139  push    r15
0x14006713b  lea     rbp, [rsp-27h]
0x140067140  sub     rsp, 0C0h
0x140067147  mov     rax, cs:__security_cookie
0x14006714e  xor     rax, rsp
0x140067151  mov     [rbp+57h+var_40], rax
0x140067155  xor     eax, eax
0x140067157  mov     [rbp+57h+LockState.OldIrql], 0
0x14006715b  mov     word ptr [rbp+57h+LockState.LockState], ax
0x14006715f  mov     r14d, r9d
0x140067162  mov     eax, [rcx]
0x140067164  mov     rsi, r8
0x140067167  mov     r15d, edx
0x14006716a  mov     rdi, rcx
0x14006716d  test    al, 4
0x14006716f  jz      short loc_1400671D5
0x140067171  mov     rcx, cs:WPP_GLOBAL_Control
0x140067178  lea     rbx, WPP_GLOBAL_Control
0x14006717f  cmp     rcx, rbx
0x140067182  jz      loc_140067884
0x140067188  cmp     byte ptr [rcx+29h], 3
0x14006718c  jb      loc_140067884
0x140067192  test    dword ptr [rcx+2Ch], 100h
0x140067199  jz      loc_140067884
0x14006719f  mov     rax, [rdi+0A38h]
0x1400671a6  lea     r8, WPP_76e11202d3fc32571e344eea390caf41_Traceguids
0x1400671ad  mov     rcx, [rcx+18h]
0x1400671b1  mov     edx, 0Bh
0x1400671b6  mov     [rsp+0F0h+var_C8], r15d
0x1400671bb  mov     [rsp+0F0h+var_D0], rdi
0x1400671c0  mov     r9, [rax+10h]
0x1400671c4  mov     r9d, [r9+6ACh]
0x1400671cb  call    WPP_SF_dqD
0x1400671d0  jmp     loc_140067884
0x1400671d5  cmp     r15d, 40010012h
0x1400671dc  jnz     short loc_1400671EE
0x1400671de  mov     r8d, r14d; unsigned int
0x1400671e1  mov     rdx, rsi; void *
0x1400671e4  call    ?ExtSTAIHVSpecificIndication@@YAXPEAUEXTSTA_VELAN@@PEAXK@Z; ExtSTAIHVSpecificIndication(EXTSTA_VELAN *,void *,ulong)
0x1400671e9  jmp     loc_140067884
0x1400671ee  mov     rcx, [rcx+0A38h]
0x1400671f5  lea     rdx, [rbp+57h+LockState]; LockState
0x1400671f9  xor     r8d, r8d; Flags
0x1400671fc  mov     rcx, [rcx+90h]; Lock
0x140067203  call    cs:__imp_NdisAcquireRWLockWrite
0x14006720a  nop     dword ptr [rax+rax+00h]
0x14006720f  lea     rbx, WPP_GLOBAL_Control
0x140067216  lea     r12, WPP_76e11202d3fc32571e344eea390caf41_Traceguids
0x14006721d  cmp     r15d, 4003000Bh
0x140067224  jnz     short loc_140067236
0x140067226  mov     rdx, rsi; struct DOT11_PHY_STATE_PARAMETERS *
0x140067229  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14006722c  call    ?ExtSTAPhyStateChange@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_PHY_STATE_PARAMETERS@@K@Z; ExtSTAPhyStateChange(EXTSTA_VELAN *,DOT11_PHY_STATE_PARAMETERS *,ulong)
0x140067231  jmp     loc_1400677CF
0x140067236  cmp     r15d, 40010017h
0x14006723d  jnz     loc_14006730D
0x140067243  test    rsi, rsi
0x140067246  jz      loc_1400677CF
0x14006724c  cmp     r14d, 28h ; '('
0x140067250  jb      loc_1400677CF
0x140067256  cmp     dword ptr [rsi+4], 1
0x14006725a  jz      short loc_140067279
0x14006725c  mov     rcx, cs:WPP_GLOBAL_Control
0x140067263  cmp     rcx, rbx
0x140067266  jz      short loc_1400672CC
0x140067268  mov     rcx, [rcx+18h]
0x14006726c  mov     edx, 0Ch
0x140067271  mov     r8, r12
0x140067274  call    WPP_SF_
0x140067279  mov     rcx, cs:WPP_GLOBAL_Control
0x140067280  cmp     rcx, rbx
0x140067283  jz      short loc_1400672CC
0x140067285  mov     rcx, [rcx+18h]
0x140067289  mov     r9, 431BDE82D7B634DBh
0x140067293  mov     rax, r9
0x140067296  mul     qword ptr [rsi+18h]
0x14006729a  mov     rax, r9
0x14006729d  mov     r8, rdx
0x1400672a0  mul     qword ptr [rsi+10h]
0x1400672a4  mov     rax, [rdi+0A38h]
0x1400672ab  shr     r8, 12h
0x1400672af  shr     rdx, 12h
0x1400672b3  mov     [rsp+0F0h+var_C8], r8d
0x1400672b8  mov     r9, [rax+10h]
0x1400672bc  mov     dword ptr [rsp+0F0h+var_D0], edx
0x1400672c0  mov     r9d, [r9+6ACh]
0x1400672c7  call    WPP_SF_dDD
0x1400672cc  mov     dword ptr [rsi], 280180h
0x1400672d2  mov     rdx, rsi
0x1400672d5  mov     eax, [rdi+61Ch]
0x1400672db  mov     rcx, rdi
0x1400672de  mov     [rsi+4], eax
0x1400672e1  movups  xmm0, xmmword ptr [rsi]
0x1400672e4  movups  xmmword ptr [rdi+618h], xmm0
0x1400672eb  movups  xmm1, xmmword ptr [rsi+10h]
0x1400672ef  movups  xmmword ptr [rdi+628h], xmm1
0x1400672f6  movsd   xmm0, qword ptr [rsi+20h]
0x1400672fb  movsd   qword ptr [rdi+638h], xmm0
0x140067303  call    ExtSTALinkState
0x140067308  jmp     loc_1400677CF
0x14006730d  cmp     r15d, 40010005h
0x140067314  jnz     short loc_140067342
0x140067316  test    rsi, rsi
0x140067319  jz      loc_1400677CF
0x14006731f  cmp     r14d, 4
0x140067323  jb      loc_1400677CF
0x140067329  cmp     dword ptr [rsi], 0C0010008h
0x14006732f  jnz     loc_1400677CF
0x140067335  mov     rcx, rdi
0x140067338  call    ExtSTADriverResetIndication
0x14006733d  jmp     loc_1400677CF
0x140067342  cmp     r15d, 40030023h
0x140067349  jnz     loc_1400673FD
0x14006734f  mov     rcx, cs:WPP_GLOBAL_Control
0x140067356  cmp     rcx, rbx
0x140067359  jz      short loc_14006737E
0x14006735b  mov     rax, [rdi+0A38h]
0x140067362  mov     edx, 0Eh
0x140067367  mov     rcx, [rcx+18h]
0x14006736b  mov     r8, r12
0x14006736e  mov     r9, [rax+10h]
0x140067372  mov     r9d, [r9+6ACh]
0x140067379  call    WPP_SF_d
0x14006737e  cmp     dword ptr [rdi+32Ch], 0
0x140067385  jz      short loc_1400673F0
0x140067387  mov     rax, [rdi+0A38h]
0x14006738e  cmp     byte ptr [rax+1F90h], 0
0x140067395  jz      short loc_1400673A9
0x140067397  cmp     byte ptr [rdi+0A4Ch], 0
0x14006739e  jz      short loc_1400673A9
0x1400673a0  cmp     dword ptr [rdi+14Ch], 0
0x1400673a7  jnz     short loc_1400673F0
0x1400673a9  mov     rax, [rax+10h]
0x1400673ad  cmp     dword ptr [rax+108h], 1
0x1400673b4  jg      short loc_1400673E5
0x1400673b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400673bd  cmp     rcx, rbx
0x1400673c0  jz      short loc_1400673D3
0x1400673c2  mov     rcx, [rcx+18h]
0x1400673c6  mov     edx, 0Fh
0x1400673cb  mov     r8, r12
0x1400673ce  call    WPP_SF_
0x1400673d3  mov     rcx, rdi; struct EXTSTA_VELAN *
0x1400673d6  call    ?ExtSTACancelConnRoamingTimer@@YAEPEAUEXTSTA_VELAN@@@Z; ExtSTACancelConnRoamingTimer(EXTSTA_VELAN *)
0x1400673db  mov     rcx, rdi; struct EXTSTA_VELAN *
0x1400673de  call    ?ExtSTATerminateConnection@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTATerminateConnection(EXTSTA_VELAN *)
0x1400673e3  jmp     short loc_1400673F0
0x1400673e5  mov     eax, 1
0x1400673ea  xchg    eax, [rdi+0A48h]
0x1400673f0  mov     rcx, rdi; struct EXTSTA_VELAN *
0x1400673f3  call    ?ExtSTAUpcallNLODiscovery@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTAUpcallNLODiscovery(EXTSTA_VELAN *)
0x1400673f8  jmp     loc_1400677CF
0x1400673fd  cmp     r15d, 40010023h
0x140067404  jnz     loc_140067498
0x14006740a  test    rsi, rsi
0x14006740d  jz      short loc_14006747E
0x14006740f  cmp     r14d, 0Ch
0x140067413  jb      short loc_14006747E
0x140067415  mov     r9d, [rsi+4]
0x140067419  cmp     r9d, 1
0x14006741d  jnz     short loc_140067458
0x14006741f  cmp     [rdi+61Ch], r9d
0x140067426  jz      loc_1400677CF
0x14006742c  mov     rcx, cs:WPP_GLOBAL_Control
0x140067433  cmp     rcx, rbx
0x140067436  jz      short loc_140067448
0x140067438  mov     rcx, [rcx+18h]
0x14006743c  lea     edx, [r9+0Fh]
0x140067440  mov     r8, r12
0x140067443  call    WPP_SF_
0x140067448  or      dword ptr [rsi+8], 1
0x14006744c  mov     dword ptr [rsi+4], 2
0x140067453  jmp     loc_1400677CF
0x140067458  mov     rcx, cs:WPP_GLOBAL_Control
0x14006745f  cmp     rcx, rbx
0x140067462  jz      loc_1400677CF
0x140067468  mov     rcx, [rcx+18h]
0x14006746c  mov     edx, 11h
0x140067471  mov     r8, r12
0x140067474  call    WPP_SF_d
0x140067479  jmp     loc_1400677CF
0x14006747e  mov     rcx, cs:WPP_GLOBAL_Control
0x140067485  cmp     rcx, rbx
0x140067488  jz      loc_1400677CF
0x14006748e  mov     edx, 12h
0x140067493  jmp     loc_1400675C1
0x140067498  cmp     r15d, 40030025h
0x14006749f  jnz     short loc_1400674B4
0x1400674a1  mov     r8d, r14d; unsigned int
0x1400674a4  mov     rdx, rsi; struct _DOT11_ANQP_QUERY_COMPLETE_PARAMETERS *
0x1400674a7  mov     rcx, rdi; struct EXTSTA_VELAN *
0x1400674aa  call    ?ExtSTAANQPQueryCompletion@@YAXPEAUEXTSTA_VELAN@@PEAU_DOT11_ANQP_QUERY_COMPLETE_PARAMETERS@@K@Z; ExtSTAANQPQueryCompletion(EXTSTA_VELAN *,_DOT11_ANQP_QUERY_COMPLETE_PARAMETERS *,ulong)
0x1400674af  jmp     loc_1400677CF
0x1400674b4  cmp     r15d, 40030031h
0x1400674bb  jnz     short loc_1400674D0
0x1400674bd  mov     r8d, r14d; unsigned int
0x1400674c0  mov     rdx, rsi; struct _DOT11_FTM_RESPONSE_PARAMS *
0x1400674c3  mov     rcx, rdi; struct EXTSTA_VELAN *
0x1400674c6  call    ?ExtSTAFtmResponse@@YAXPEAUEXTSTA_VELAN@@PEAU_DOT11_FTM_RESPONSE_PARAMS@@K@Z; ExtSTAFtmResponse(EXTSTA_VELAN *,_DOT11_FTM_RESPONSE_PARAMS *,ulong)
0x1400674cb  jmp     loc_1400677CF
0x1400674d0  cmp     r15d, 4003002Fh
0x1400674d7  jnz     short loc_1400674EC
0x1400674d9  mov     r8d, r14d
0x1400674dc  mov     rdx, rsi
0x1400674df  mov     rcx, rdi
0x1400674e2  call    ExtSTADeviceServiceEvent
0x1400674e7  jmp     loc_1400677CF
0x1400674ec  mov     r9, [rdi+0A38h]
0x1400674f3  cmp     dword ptr [r9+15F0h], 0
0x1400674fb  jnz     loc_1400677CF
0x140067501  mov     eax, 40030029h
0x140067506  cmp     r15d, eax
0x140067509  jg      loc_1400676AE
0x14006750f  jz      loc_14006769E
0x140067515  mov     eax, 40030006h
0x14006751a  cmp     r15d, eax
0x14006751d  jg      loc_14006761C
0x140067523  jz      loc_140067609
0x140067529  mov     ecx, r15d
0x14006752c  sub     ecx, 40010024h
0x140067532  jz      short loc_1400675A6
0x140067534  sub     ecx, 1FFDEh
0x14006753a  jz      short loc_140067593
0x14006753c  sub     ecx, 1
0x14006753f  jz      short loc_140067575
0x140067541  sub     ecx, 1
0x140067544  jz      short loc_140067562
0x140067546  cmp     ecx, 1
0x140067549  jnz     loc_1400677CF
0x14006754f  mov     r8d, r14d; unsigned int
0x140067552  mov     rdx, rsi; struct DOT11_CONNECTION_COMPLETION_PARAMETERS *
0x140067555  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140067558  call    ?ExtSTAConnCompletion@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_CONNECTION_COMPLETION_PARAMETERS@@K@Z; ExtSTAConnCompletion(EXTSTA_VELAN *,DOT11_CONNECTION_COMPLETION_PARAMETERS *,ulong)
0x14006755d  jmp     loc_1400677CF
0x140067562  mov     r8d, r14d; unsigned int
0x140067565  mov     rdx, rsi; struct DOT11_CONNECTION_START_PARAMETERS *
0x140067568  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14006756b  call    ?ExtSTAConnStart@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_CONNECTION_START_PARAMETERS@@K@Z; ExtSTAConnStart(EXTSTA_VELAN *,DOT11_CONNECTION_START_PARAMETERS *,ulong)
0x140067570  jmp     loc_1400677CF
0x140067575  mov     [rsp+0F0h+var_D0], 0
0x14006757e  xor     edx, edx
0x140067580  mov     r8, rsi
0x140067583  mov     r9d, r14d
0x140067586  mov     rcx, rdi
0x140067589  call    ?ExtSTAAssocCompletion@@YAXPEAUEXTSTA_VELAN@@W4_DOT11_ASSOCIATION_TYPE@@QEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@KPEAUDOT11_CONNECTION_INFO@@@Z; ExtSTAAssocCompletion(EXTSTA_VELAN *,_DOT11_ASSOCIATION_TYPE,DOT11_ASSOCIATION_COMPLETION_PARAMETERS * const,ulong,DOT11_CONNECTION_INFO *)
0x14006758e  jmp     loc_1400677CF
0x140067593  mov     r8d, r14d; unsigned int
0x140067596  mov     rdx, rsi; struct DOT11_ASSOCIATION_START_PARAMETERS *
0x140067599  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14006759c  call    ?ExtSTAAssocStart@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_ASSOCIATION_START_PARAMETERS@@K@Z; ExtSTAAssocStart(EXTSTA_VELAN *,DOT11_ASSOCIATION_START_PARAMETERS *,ulong)
0x1400675a1  jmp     loc_1400677CF
0x1400675a6  cmp     r14d, 4
0x1400675aa  jnb     short loc_1400675D2
0x1400675ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400675b3  cmp     rcx, rbx
0x1400675b6  jz      loc_1400677CF
0x1400675bc  mov     edx, 13h
0x1400675c1  mov     rcx, [rcx+18h]
0x1400675c5  mov     r8, r12
0x1400675c8  call    WPP_SF_
0x1400675cd  jmp     loc_1400677CF
0x1400675d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400675d9  cmp     rcx, rbx
0x1400675dc  jz      loc_1400677CF
0x1400675e2  mov     r9, [r9+10h]
0x1400675e6  mov     edx, 14h
0x1400675eb  mov     eax, [rsi]
0x1400675ed  mov     r8, r12
0x1400675f0  mov     rcx, [rcx+18h]
0x1400675f4  mov     dword ptr [rsp+0F0h+var_D0], eax
0x1400675f8  mov     r9d, [r9+6ACh]
0x1400675ff  call    WPP_SF_Dd
0x140067604  jmp     loc_1400677CF
0x140067609  mov     r8d, r14d; unsigned int
0x14006760c  mov     rdx, rsi; struct DOT11_ROAMING_START_PARAMETERS *
0x14006760f  mov     rcx, rdi; struct EXTSTA_VELAN *
0x140067612  call    ?ExtSTARoamingStart@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_ROAMING_START_PARAMETERS@@K@Z; ExtSTARoamingStart(EXTSTA_VELAN *,DOT11_ROAMING_START_PARAMETERS *,ulong)
0x140067617  jmp     loc_1400677CF
0x14006761c  mov     ecx, r15d
0x14006761f  sub     ecx, 40030007h
0x140067625  jz      short loc_14006768B
0x140067627  sub     ecx, 1
0x14006762a  jz      short loc_140067678
0x14006762c  sub     ecx, 1
0x14006762f  jz      short loc_140067665
0x140067631  sub     ecx, 1
0x140067634  jz      short loc_140067652
0x140067636  cmp     ecx, 2
0x140067639  jnz     loc_1400677CF
0x14006763f  mov     r8d, r14d
0x140067642  mov     rdx, rsi
0x140067645  mov     rcx, rdi
0x140067648  call    ExtSTALinkQuality
0x14006764d  jmp     loc_1400677CF
  ... truncated ...
```
