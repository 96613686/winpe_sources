# ExtSTAIoctlConnect(EXTSTA_VELAN *,_IRP *,void *,ulong,void *,ulong *)

- ea: `0x1400618d0`
- end: `0x140061e15`
- name: `?ExtSTAIoctlConnect@@YAJPEAUEXTSTA_VELAN@@PEAU_IRP@@PEAXK2PEAK@Z`
- size: `1349`
- prototype: `__int64 __usercall@<rax>(struct EXTSTA_VELAN *@<rcx>, struct _IRP *@<rdx>, void *@<r8>, unsigned int@<r9d>, void *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006bc70`

## callees

- `0x14000a81c`
- `0x14000d21c`
- `0x1400160d0`
- `0x1400165b4`
- `0x140019494`
- `0x140019e34`
- `0x14001a320`
- `0x140020870`
- `0x140020dc0`
- `0x140025590`
- `0x14005de28`
- `0x14005f97c`
- `0x1400618d0`
- `0x140063b1c`
- `0x1400647b8`
- `0x14006610c`
- `0x14007ba08`

## import_xrefs

- `NDIS!NdisGetSystemUpTimeEx` at `0x140061c5e`
- `NDIS!NdisGetSystemUpTimeEx` at `0x140061c5e`
- `NDIS!NdisWaitEvent` at `0x140061d3d`
- `NDIS!NdisWaitEvent` at `0x140061d3d`
- `NDIS!NdisInitializeEvent` at `0x140061c23`
- `NDIS!NdisInitializeEvent` at `0x140061c23`
- `NDIS!NdisAcquireRWLockWrite` at `0x140061ac6`
- `NDIS!NdisAcquireRWLockWrite` at `0x140061d69`
- `NDIS!NdisAcquireRWLockWrite` at `0x140061ac6`
- `NDIS!NdisAcquireRWLockWrite` at `0x140061d69`
- `NDIS!NdisReleaseRWLock` at `0x140061d22`
- `NDIS!NdisReleaseRWLock` at `0x140061dab`
- `NDIS!NdisReleaseRWLock` at `0x140061d22`
- `NDIS!NdisReleaseRWLock` at `0x140061dab`

## pseudocode

```c
__int64 __fastcall ExtSTAIoctlConnect(
        struct EXTSTA_VELAN *a1,
        struct _IRP *a2,
        union _LARGE_INTEGER a3,
        int a4,
        _QWORD *a5,
        unsigned int *a6)
{
  int LowPart; // edi
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  _VELAN *pGenVElan; // r9
  _ADAPT *pAdapt; // rcx
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  int v15; // r14d
  int v16; // ecx
  _VELAN *v17; // rax
  unsigned int v18; // r8d
  _VELAN *v19; // rdx
  struct _NDIS_OID_REQUEST *Request; // r8
  int v21; // r14d
  struct _NDIS_EVENT Event; // [rsp+40h] [rbp-20h] BYREF
  int v24; // [rsp+A0h] [rbp+40h] BYREF
  union _LARGE_INTEGER pSystemUpTime; // [rsp+B0h] [rbp+50h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+B8h] [rbp+58h] BYREF
  char v27; // [rsp+BBh] [rbp+5Bh]

  v27 = HIBYTE(a4);
  pSystemUpTime = a3;
  v24 = 0;
  *(_WORD *)&LockState.LockState = 0;
  LockState.OldIrql = 0;
  memset(&Event, 0, sizeof(Event));
  _InterlockedAdd(&a1->AssocMgr.ConnectIoctlRef, 1u);
  if ( *a6 < 0x18 )
  {
    LowPart = -2147483643;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_51:
      a2->IoStatus.Status = LowPart;
      NWFCompleteIrp(a1->pGenVElan, a2);
      _InterlockedDecrement(&a1->AssocMgr.ConnectIoctlRef);
      return 259;
    }
    v10 = 101;
LABEL_4:
    WPP_SF_(v9->AttachedDevice, v10, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    goto LABEL_51;
  }
  *a5 = 0;
  pGenVElan = a1->pGenVElan;
  pAdapt = pGenVElan->pAdapt;
  if ( (pAdapt->SoftwareRadioState & pAdapt->HardwareRadioState) == 0 )
  {
    if ( byte_1400B2803 < 0 )
      McTemplateK0pjq_EtwWriteTransfer(
        (_DWORD)pAdapt,
        (unsigned int)ConnectRadioOff,
        (_DWORD)pGenVElan + 4920,
        (_DWORD)pGenVElan,
        (__int64)&pGenVElan->gDeviceId,
        0);
    LowPart = -1071439870;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_51;
    v10 = 102;
    goto LABEL_4;
  }
  if ( pGenVElan->MPDevicePowerState > NdisDeviceStateD0 )
  {
    if ( byte_1400B2803 < 0 )
      McTemplateK0pjq_EtwWriteTransfer(
        (_DWORD)pAdapt,
        (unsigned int)ConnectRadioLowPower,
        (_DWORD)pGenVElan + 4920,
        (_DWORD)pGenVElan,
        (__int64)&pGenVElan->gDeviceId,
        pGenVElan->MPDevicePowerState);
    LowPart = -1071439870;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        103,
        WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids,
        (unsigned int)a1->pGenVElan->MPDevicePowerState);
    goto LABEL_51;
  }
  LowPart = ExtSTAPlumbExemptionList((__int64)a1);
  if ( LowPart < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_51;
    v14 = 104;
LABEL_18:
    WPP_SF_d(v13->AttachedDevice, v14, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids, (unsigned int)LowPart);
    goto LABEL_51;
  }
  LowPart = ExtSTAPlumbMulticastList((__int64)a1);
  if ( LowPart < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_51;
    v14 = 105;
    goto LABEL_18;
  }
  v15 = 0;
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
  ExtSTAFlushAssocTable(a1, 0, qword_1400A3E90);
  a1->AssocMgr.IndicatedDSInfo = DOT11_DS_CHANGED;
  a1->AssocMgr.RoamingDSInfo = DOT11_DS_CHANGED;
  *(_DWORD *)&a1->RoD &= ~4u;
  ExtSTASetPerftrackInfo(&a1->PerftrackInfo, 0);
  v16 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
  if ( (byte_1400B2803 & 2) != 0 )
    McTemplateK0pjp_EtwWriteTransfer(
      v16,
      (unsigned int)StartConnect,
      &a1->pGenVElan->gDeviceId,
      a1->pGenVElan,
      (__int64)&a1->pGenVElan->gDeviceId,
      (char)a2);
  v17 = a1->pGenVElan;
  pSystemUpTime.LowPart = 0;
  if ( v17->pAdapt->uConfiguredOpMode == 64 )
    WFDRoleGetConnectionTimeout(a1->pWFDRole, (unsigned int *)&pSystemUpTime);
  ExtSTAStartConnRoamingTimer(a1);
  a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = (_LIST_ENTRY *)a1;
  a1->AssocMgr.pIrp = a2;
  _InterlockedAdd(&a1->AssocMgr.ConnectIoctlRef, 1u);
  a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, (__int64)ExtSTACancelIoctlConnect);
  if ( a2->Cancel )
  {
    a1->AssocMgr.pIrp = 0;
    _InterlockedDecrement(&a1->AssocMgr.ConnectIoctlRef);
    if ( _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, 0) )
    {
      a2->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
      LowPart = -1073741536;
    }
    else
    {
      LowPart = 259;
      a2 = 0;
    }
  }
  else if ( !LowPart )
  {
    a1->pGenVElan->bInitState = 0;
    ExtSTAUpdateMiniportMacExcludedList(a1, MEMORY[0xFFFFF78000000014]);
    NdisInitializeEvent(&Event);
    if ( a1->pGenVElan->pAdapt->uConfiguredOpMode == 4 )
    {
      if ( a1->SecondsToSkipScanForIPAddress && a1->bIPBoundToAdapter )
      {
        pSystemUpTime.QuadPart = 0;
        NdisGetSystemUpTimeEx(&pSystemUpTime);
        _InterlockedExchange(&a1->bWaitingForIPv4Address, 1);
        _InterlockedExchange(&a1->bWaitingForIPv6Address, 1);
        a1->ullWaitingForIPTimeLimitMs = pSystemUpTime.QuadPart + 1000 * a1->SecondsToSkipScanForIPAddress;
      }
      v18 = 234946945;
    }
    else
    {
      v18 = 235274500;
    }
    Dot11BuildNdisRequest(
      &a1->AssocMgr.ConnectOidRequest,
      1u,
      v18,
      0,
      0,
      (void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *))ExtSTAOidConnectCompletion,
      &Event,
      &v24);
    v19 = a1->pGenVElan;
    Request = a1->AssocMgr.ConnectOidRequest.Request;
    pSystemUpTime.LowPart = 0;
    Dot11Request((int *)&pSystemUpTime, v19->pAdapt, Request);
    LowPart = pSystemUpTime.LowPart;
    v15 = 1;
    if ( pSystemUpTime.LowPart != 259 )
      Dot11RequestComplete(a1->pGenVElan->pAdapt, a1->AssocMgr.ConnectOidRequest.Request, pSystemUpTime.LowPart);
  }
  NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
  if ( v15 )
  {
    NdisWaitEvent(&Event, 0);
    LowPart = v24;
    if ( !v24 )
      return 259;
    NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
    if ( a1->AssocMgr.pIrp )
    {
      a1->AssocMgr.pIrp = 0;
      v21 = 1;
      if ( _InterlockedExchange64((volatile __int64 *)&a2->CancelRoutine, 0) )
        goto LABEL_48;
    }
    else
    {
      v21 = 0;
    }
    a2 = 0;
    LowPart = 259;
LABEL_48:
    NdisReleaseRWLock(a1->pGenVElan->pRWLock, &LockState);
    if ( v21 )
    {
      a1->pGenVElan->bInitState = 1;
      ExtSTACancelConnRoamingTimerSync(a1);
      _InterlockedDecrement(&a1->AssocMgr.ConnectIoctlRef);
    }
  }
  if ( LowPart != 259 )
    goto LABEL_51;
  return (unsigned int)LowPart;
}

```

## disassembly

```asm
0x1400618d0  mov     [rsp-38h+arg_8], rbx
0x1400618d5  mov     dword ptr [rsp-38h+LockState.OldIrql], r9d
0x1400618da  mov     qword ptr [rsp-38h+pSystemUpTime], r8
0x1400618df  push    rbp
0x1400618e0  push    rsi
0x1400618e1  push    rdi
0x1400618e2  push    r12
0x1400618e4  push    r13
0x1400618e6  push    r14
0x1400618e8  push    r15
0x1400618ea  mov     rbp, rsp
0x1400618ed  sub     rsp, 60h
0x1400618f1  xor     r15d, r15d
0x1400618f4  xorps   xmm0, xmm0
0x1400618f7  xor     eax, eax
0x1400618f9  mov     [rbp+arg_0], r15d
0x1400618fd  mov     word ptr [rbp+LockState.LockState], ax
0x140061901  mov     rsi, rdx
0x140061904  mov     [rbp+LockState.OldIrql], r15b
0x140061908  mov     rbx, rcx
0x14006190b  mov     dword ptr [rbp+Event.Event.Header.___u0], r15d
0x14006190f  lea     r12d, [r15+1]
0x140061913  movups  xmmword ptr [rbp+Event.Event.Header.SignalState], xmm0
0x140061917  mov     dword ptr [rbp+Event.Event.Header.WaitListHead.Blink+4], eax
0x14006191a  lock add [rcx+330h], r12d
0x140061922  mov     rax, [rbp+arg_28]
0x140061926  mov     r13d, 103h
0x14006192c  cmp     dword ptr [rax], 18h
0x14006192f  jnb     short loc_140061966
0x140061931  mov     edi, 80000005h
0x140061936  mov     rcx, cs:WPP_GLOBAL_Control
0x14006193d  lea     rax, WPP_GLOBAL_Control
0x140061944  cmp     rcx, rax
0x140061947  jz      loc_140061DDE
0x14006194d  lea     edx, [r15+65h]
0x140061951  mov     rcx, [rcx+18h]
0x140061955  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14006195c  call    WPP_SF_
0x140061961  jmp     loc_140061DDE
0x140061966  mov     rax, [rbp+arg_20]
0x14006196a  mov     [rax], r15
0x14006196d  mov     r9, [rcx+0A38h]
0x140061974  mov     rcx, [r9+10h]
0x140061978  mov     rax, [rcx+30h]
0x14006197c  test    [rcx+28h], rax
0x140061980  jnz     short loc_1400619CB
0x140061982  cmp     cs:byte_1400B2803, r15b
0x140061989  jge     short loc_1400619A8
0x14006198b  lea     r8, [r9+1338h]
0x140061992  mov     dword ptr [rsp+60h+var_38], r15d
0x140061997  lea     rdx, ConnectRadioOff
0x14006199e  mov     [rsp+60h+var_40], r8
0x1400619a3  call    McTemplateK0pjq_EtwWriteTransfer
0x1400619a8  mov     edi, 0C0232002h
0x1400619ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1400619b4  lea     rax, WPP_GLOBAL_Control
0x1400619bb  cmp     rcx, rax
0x1400619be  jz      loc_140061DDE
0x1400619c4  mov     edx, 66h ; 'f'
0x1400619c9  jmp     short loc_140061951
0x1400619cb  mov     eax, [r9+13F4h]
0x1400619d2  cmp     eax, r12d
0x1400619d5  jle     short loc_140061A40
0x1400619d7  cmp     cs:byte_1400B2803, r15b
0x1400619de  jge     short loc_1400619FC
0x1400619e0  lea     r8, [r9+1338h]
0x1400619e7  mov     dword ptr [rsp+60h+var_38], eax
0x1400619eb  lea     rdx, ConnectRadioLowPower
0x1400619f2  mov     [rsp+60h+var_40], r8
0x1400619f7  call    McTemplateK0pjq_EtwWriteTransfer
0x1400619fc  mov     edi, 0C0232002h
0x140061a01  mov     rcx, cs:WPP_GLOBAL_Control
0x140061a08  lea     rax, WPP_GLOBAL_Control
0x140061a0f  cmp     rcx, rax
0x140061a12  jz      loc_140061DDE
0x140061a18  mov     r9, [rbx+0A38h]
0x140061a1f  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x140061a26  mov     rcx, [rcx+18h]
0x140061a2a  mov     edx, 67h ; 'g'
0x140061a2f  mov     r9d, [r9+13F4h]
0x140061a36  call    WPP_SF_d
0x140061a3b  jmp     loc_140061DDE
0x140061a40  mov     rcx, rbx
0x140061a43  call    ExtSTAPlumbExemptionList
0x140061a48  mov     edi, eax
0x140061a4a  test    eax, eax
0x140061a4c  jns     short loc_140061A82
0x140061a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140061a55  lea     rax, WPP_GLOBAL_Control
0x140061a5c  cmp     rcx, rax
0x140061a5f  jz      loc_140061DDE
0x140061a65  mov     edx, 68h ; 'h'
0x140061a6a  mov     rcx, [rcx+18h]
0x140061a6e  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x140061a75  mov     r9d, edi
0x140061a78  call    WPP_SF_d
0x140061a7d  jmp     loc_140061DDE
0x140061a82  mov     rcx, rbx
0x140061a85  call    ExtSTAPlumbMulticastList
0x140061a8a  mov     edi, eax
0x140061a8c  test    eax, eax
0x140061a8e  jns     short loc_140061AAE
0x140061a90  mov     rcx, cs:WPP_GLOBAL_Control
0x140061a97  lea     rax, WPP_GLOBAL_Control
0x140061a9e  cmp     rcx, rax
0x140061aa1  jz      loc_140061DDE
0x140061aa7  mov     edx, 69h ; 'i'
0x140061aac  jmp     short loc_140061A6A
0x140061aae  mov     rcx, [rbx+0A38h]
0x140061ab5  lea     rdx, [rbp+LockState]; LockState
0x140061ab9  xor     r8d, r8d; Flags
0x140061abc  mov     r14d, r15d
0x140061abf  mov     rcx, [rcx+90h]; Lock
0x140061ac6  call    cs:__imp_NdisAcquireRWLockWrite
0x140061acd  nop     dword ptr [rax+rax+00h]
0x140061ad2  lea     r8, qword_1400A3E90
0x140061ad9  xor     edx, edx
0x140061adb  mov     rcx, rbx
0x140061ade  call    ExtSTAFlushAssocTable
0x140061ae3  mov     [rbx+160h], r15d
0x140061aea  lea     rcx, [rbx+608h]; struct EXTSTA_PERFTRACK_INFO *
0x140061af1  mov     [rbx+158h], r15d
0x140061af8  xor     edx, edx; int
0x140061afa  and     dword ptr [rbx+610h], 0FFFFFFFBh
0x140061b01  call    ?ExtSTASetPerftrackInfo@@YAXPEAUEXTSTA_PERFTRACK_INFO@@H@Z; ExtSTASetPerftrackInfo(EXTSTA_PERFTRACK_INFO *,int)
0x140061b06  mov     rcx, cs:WPP_GLOBAL_Control
0x140061b0d  lea     rax, WPP_GLOBAL_Control
0x140061b14  cmp     rcx, rax
0x140061b17  jz      short loc_140061B2E
0x140061b19  mov     rcx, [rcx+18h]
0x140061b1d  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x140061b24  mov     edx, 6Ah ; 'j'
0x140061b29  call    WPP_SF_
0x140061b2e  test    cs:byte_1400B2803, 2
0x140061b35  jz      short loc_140061B5B
0x140061b37  mov     r9, [rbx+0A38h]
0x140061b3e  lea     rdx, StartConnect
0x140061b45  mov     [rsp+60h+var_38], rsi
0x140061b4a  lea     r8, [r9+1338h]
0x140061b51  mov     [rsp+60h+var_40], r8
0x140061b56  call    McTemplateK0pjp_EtwWriteTransfer
0x140061b5b  mov     rax, [rbx+0A38h]
0x140061b62  mov     dword ptr [rbp+pSystemUpTime], r15d
0x140061b66  mov     rcx, [rax+10h]
0x140061b6a  cmp     dword ptr [rcx+118h], 40h ; '@'
0x140061b71  jnz     short loc_140061B8A
0x140061b73  mov     rcx, [rbx+0A40h]; struct _WFD_ROLE *
0x140061b7a  lea     rdx, [rbp+pSystemUpTime]; unsigned int *
0x140061b7e  call    ?WFDRoleGetConnectionTimeout@@YAHPEAU_WFD_ROLE@@PEAK@Z; WFDRoleGetConnectionTimeout(_WFD_ROLE *,ulong *)
0x140061b83  mov     edx, dword ptr [rbp+pSystemUpTime]
0x140061b86  test    edx, edx
0x140061b88  jnz     short loc_140061B90
0x140061b8a  mov     edx, [rbx+308h]
0x140061b90  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140061b93  call    ExtSTAStartConnRoamingTimer
0x140061b98  mov     [rsi+78h], rbx
0x140061b9c  mov     [rbx+10h], rsi
0x140061ba0  lock add [rbx+330h], r12d
0x140061ba8  mov     rax, [rsi+0B8h]
0x140061baf  or      [rax+3], r12b
0x140061bb3  lea     rax, ?ExtSTACancelIoctlConnect@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ExtSTACancelIoctlConnect(_DEVICE_OBJECT *,_IRP *)
0x140061bba  xchg    rax, [rsi+68h]
0x140061bbe  cmp     [rsi+44h], r15b
0x140061bc2  jz      short loc_140061BF4
0x140061bc4  mov     [rbx+10h], r15
0x140061bc8  mov     rax, r15
0x140061bcb  lock dec dword ptr [rbx+330h]
0x140061bd2  xchg    rax, [rsi+68h]
0x140061bd6  test    rax, rax
0x140061bd9  jz      short loc_140061BE9
0x140061bdb  mov     [rsi+78h], r15
0x140061bdf  mov     edi, 0C0000120h
0x140061be4  jmp     loc_140061D10
0x140061be9  mov     edi, r13d
0x140061bec  mov     rsi, r15
0x140061bef  jmp     loc_140061D10
0x140061bf4  test    edi, edi
0x140061bf6  jnz     loc_140061D10
0x140061bfc  mov     rax, [rbx+0A38h]
0x140061c03  mov     rdx, 0FFFFF78000000014h
0x140061c0d  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140061c10  mov     [rax+15F0h], r15d
0x140061c17  mov     rdx, [rdx]; unsigned __int64
0x140061c1a  call    ?ExtSTAUpdateMiniportMacExcludedList@@YAXPEAUEXTSTA_VELAN@@_K@Z; ExtSTAUpdateMiniportMacExcludedList(EXTSTA_VELAN *,unsigned __int64)
0x140061c1f  lea     rcx, [rbp+Event]; Event
0x140061c23  call    cs:__imp_NdisInitializeEvent
0x140061c2a  nop     dword ptr [rax+rax+00h]
0x140061c2f  mov     rax, [rbx+0A38h]
0x140061c36  mov     rcx, [rax+10h]
0x140061c3a  cmp     dword ptr [rcx+118h], 4
0x140061c41  jnz     short loc_140061C9A
0x140061c43  cmp     [rbx+0A78h], r15
0x140061c4a  jbe     short loc_140061C92
0x140061c4c  mov     eax, [rbx+0A70h]
0x140061c52  test    eax, eax
0x140061c54  jz      short loc_140061C92
0x140061c56  lea     rcx, [rbp+pSystemUpTime]; pSystemUpTime
0x140061c5a  mov     qword ptr [rbp+pSystemUpTime], r15
0x140061c5e  call    cs:__imp_NdisGetSystemUpTimeEx
0x140061c65  nop     dword ptr [rax+rax+00h]
0x140061c6a  mov     eax, r12d
0x140061c6d  xchg    eax, [rbx+0A60h]
0x140061c73  mov     eax, r12d
0x140061c76  xchg    eax, [rbx+0A64h]
0x140061c7c  imul    rcx, [rbx+0A78h], 3E8h
0x140061c87  add     rcx, qword ptr [rbp+pSystemUpTime]
0x140061c8b  mov     [rbx+0A58h], rcx
0x140061c92  mov     r8d, 0E010181h
0x140061c98  jmp     short loc_140061CA0
0x140061c9a  mov     r8d, 0E060104h; unsigned int
0x140061ca0  lea     rax, [rbp+arg_0]
0x140061ca4  xor     r9d, r9d; unsigned int
0x140061ca7  mov     [rsp+60h+var_28], rax; void *
0x140061cac  lea     rcx, [rbx+18h]; struct DOT11_NDIS_REQUEST *
0x140061cb0  lea     rax, [rbp+Event]
0x140061cb4  mov     edx, r12d; unsigned int
0x140061cb7  mov     [rsp+60h+var_30], rax; void *
0x140061cbc  lea     rax, ?ExtSTAOidConnectCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; ExtSTAOidConnectCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x140061cc3  mov     [rsp+60h+var_38], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x140061cc8  mov     [rsp+60h+var_40], r15; void *
0x140061ccd  call    ?Dot11BuildNdisRequest@@YAXPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@0@Z11@Z; Dot11BuildNdisRequest(DOT11_NDIS_REQUEST *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x140061cd2  mov     rdx, [rbx+0A38h]
0x140061cd9  lea     rcx, [rbp+pSystemUpTime]; int *
0x140061cdd  mov     r8, [rbx+20h]; struct _NDIS_OID_REQUEST *
0x140061ce1  mov     dword ptr [rbp+pSystemUpTime], r15d
0x140061ce5  mov     rdx, [rdx+10h]; struct _ADAPT *
0x140061ce9  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x140061cee  mov     edi, dword ptr [rbp+pSystemUpTime]
0x140061cf1  mov     r14d, r12d
0x140061cf4  cmp     edi, r13d
0x140061cf7  jz      short loc_140061D10
0x140061cf9  mov     rcx, [rbx+0A38h]
0x140061d00  mov     r8d, edi; int
0x140061d03  mov     rdx, [rbx+20h]; struct _NDIS_OID_REQUEST *
0x140061d07  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140061d0b  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x140061d10  mov     rcx, [rbx+0A38h]
0x140061d17  lea     rdx, [rbp+LockState]; LockState
0x140061d1b  mov     rcx, [rcx+90h]; Lock
0x140061d22  call    cs:__imp_NdisReleaseRWLock
0x140061d29  nop     dword ptr [rax+rax+00h]
0x140061d2e  test    r14d, r14d
0x140061d31  jz      loc_140061DD9
0x140061d37  xor     edx, edx; MsToWait
0x140061d39  lea     rcx, [rbp+Event]; Event
0x140061d3d  call    cs:__imp_NdisWaitEvent
0x140061d44  nop     dword ptr [rax+rax+00h]
0x140061d49  mov     edi, [rbp+arg_0]
0x140061d4c  test    edi, edi
0x140061d4e  jz      loc_140061DF7
0x140061d54  mov     rcx, [rbx+0A38h]
0x140061d5b  lea     rdx, [rbp+LockState]; LockState
0x140061d5f  xor     r8d, r8d; Flags
0x140061d62  mov     rcx, [rcx+90h]; Lock
0x140061d69  call    cs:__imp_NdisAcquireRWLockWrite
0x140061d70  nop     dword ptr [rax+rax+00h]
0x140061d75  cmp     [rbx+10h], r15
0x140061d79  jz      short loc_140061D90
0x140061d7b  mov     rax, r15
0x140061d7e  mov     [rbx+10h], r15
0x140061d82  xchg    rax, [rsi+68h]
0x140061d86  mov     r14d, r12d
0x140061d89  test    rax, rax
0x140061d8c  jnz     short loc_140061D99
0x140061d8e  jmp     short loc_140061D93
0x140061d90  mov     r14d, r15d
0x140061d93  mov     rsi, r15
0x140061d96  mov     edi, r13d
0x140061d99  mov     rcx, [rbx+0A38h]
0x140061da0  lea     rdx, [rbp+LockState]; LockState
0x140061da4  mov     rcx, [rcx+90h]; Lock
0x140061dab  call    cs:__imp_NdisReleaseRWLock
0x140061db2  nop     dword ptr [rax+rax+00h]
0x140061db7  test    r14d, r14d
0x140061dba  jz      short loc_140061DD9
0x140061dbc  mov     rax, [rbx+0A38h]
0x140061dc3  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140061dc6  mov     [rax+15F0h], r12d
0x140061dcd  call    ExtSTACancelConnRoamingTimerSync
0x140061dd2  lock dec dword ptr [rbx+330h]
0x140061dd9  cmp     edi, r13d
0x140061ddc  jz      short loc_140061DFA
0x140061dde  mov     [rsi+30h], edi
0x140061de1  mov     rdx, rsi; struct _IRP *
0x140061de4  mov     rcx, [rbx+0A38h]; struct _VELAN *
0x140061deb  call    ?NWFCompleteIrp@@YAXPEAU_VELAN@@PEAU_IRP@@@Z; NWFCompleteIrp(_VELAN *,_IRP *)
0x140061df0  lock dec dword ptr [rbx+330h]
0x140061df7  mov     edi, r13d
0x140061dfa  mov     rbx, [rsp+60h+arg_8]
0x140061e02  mov     eax, edi
0x140061e04  add     rsp, 60h
0x140061e08  pop     r15
0x140061e0a  pop     r14
0x140061e0c  pop     r13
0x140061e0e  pop     r12
0x140061e10  pop     rdi
0x140061e11  pop     rsi
0x140061e12  pop     rbp
0x140061e13  retn
```
