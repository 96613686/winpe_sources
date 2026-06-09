# ExtSTAIoctlConnect(EXTSTA_VELAN *,_IRP *,void *,ulong,void *,ulong *)

- ea: `0x1400600a0`
- end: `0x1400605e5`
- name: `?ExtSTAIoctlConnect@@YAJPEAUEXTSTA_VELAN@@PEAU_IRP@@PEAXK2PEAK@Z`
- size: `1349`
- prototype: `__int64 __fastcall(struct EXTSTA_VELAN *, struct _IRP *, union _LARGE_INTEGER, int, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14006a440`

## callees

- `0x14000a82c`
- `0x14000d22c`
- `0x1400160e0`
- `0x1400165c4`
- `0x140019494`
- `0x140019e34`
- `0x14001a320`
- `0x140020870`
- `0x140020dc0`
- `0x14002530c`
- `0x14005c608`
- `0x14005e14c`
- `0x1400600a0`
- `0x1400622ec`
- `0x140062f88`
- `0x1400648dc`
- `0x14007a1d8`

## import_xrefs

- `NDIS!NdisGetSystemUpTimeEx` at `0x14006042e`
- `NDIS!NdisGetSystemUpTimeEx` at `0x14006042e`
- `NDIS!NdisWaitEvent` at `0x14006050d`
- `NDIS!NdisWaitEvent` at `0x14006050d`
- `NDIS!NdisInitializeEvent` at `0x1400603f3`
- `NDIS!NdisInitializeEvent` at `0x1400603f3`
- `NDIS!NdisAcquireRWLockWrite` at `0x140060296`
- `NDIS!NdisAcquireRWLockWrite` at `0x140060539`
- `NDIS!NdisAcquireRWLockWrite` at `0x140060296`
- `NDIS!NdisAcquireRWLockWrite` at `0x140060539`
- `NDIS!NdisReleaseRWLock` at `0x1400604f2`
- `NDIS!NdisReleaseRWLock` at `0x14006057b`
- `NDIS!NdisReleaseRWLock` at `0x1400604f2`
- `NDIS!NdisReleaseRWLock` at `0x14006057b`

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
  signed int LowPart; // edi
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
  signed int v24; // [rsp+A0h] [rbp+40h] BYREF
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
    v10 = 102;
LABEL_4:
    WPP_SF_(v9->AttachedDevice, v10, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
    goto LABEL_51;
  }
  *a5 = 0;
  pGenVElan = a1->pGenVElan;
  pAdapt = pGenVElan->pAdapt;
  if ( (pAdapt->SoftwareRadioState & pAdapt->HardwareRadioState) == 0 )
  {
    if ( byte_1400AF803 < 0 )
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
    v10 = 103;
    goto LABEL_4;
  }
  if ( pGenVElan->MPDevicePowerState > NdisDeviceStateD0 )
  {
    if ( byte_1400AF803 < 0 )
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
        104,
        WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids,
        (unsigned int)a1->pGenVElan->MPDevicePowerState);
    goto LABEL_51;
  }
  LowPart = ExtSTAPlumbExemptionList(a1);
  if ( LowPart < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_51;
    v14 = 105;
LABEL_18:
    WPP_SF_d(v13->AttachedDevice, v14, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids, (unsigned int)LowPart);
    goto LABEL_51;
  }
  LowPart = ExtSTAPlumbMulticastList(a1);
  if ( LowPart < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_51;
    v14 = 106;
    goto LABEL_18;
  }
  v15 = 0;
  NdisAcquireRWLockWrite(a1->pGenVElan->pRWLock, &LockState, 0);
  ExtSTAFlushAssocTable(a1, 0, qword_1400A1D50);
  a1->AssocMgr.IndicatedDSInfo = DOT11_DS_CHANGED;
  a1->AssocMgr.RoamingDSInfo = DOT11_DS_CHANGED;
  *(_DWORD *)&a1->RoD &= ~4u;
  ExtSTASetPerftrackInfo(&a1->PerftrackInfo, 0);
  v16 = (int)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
  if ( (byte_1400AF803 & 2) != 0 )
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
0x1400600a0  mov     [rsp-38h+arg_8], rbx
0x1400600a5  mov     dword ptr [rsp-38h+LockState.OldIrql], r9d
0x1400600aa  mov     qword ptr [rsp-38h+pSystemUpTime], r8
0x1400600af  push    rbp
0x1400600b0  push    rsi
0x1400600b1  push    rdi
0x1400600b2  push    r12
0x1400600b4  push    r13
0x1400600b6  push    r14
0x1400600b8  push    r15
0x1400600ba  mov     rbp, rsp
0x1400600bd  sub     rsp, 60h
0x1400600c1  xor     r15d, r15d
0x1400600c4  xorps   xmm0, xmm0
0x1400600c7  xor     eax, eax
0x1400600c9  mov     [rbp+arg_0], r15d
0x1400600cd  mov     word ptr [rbp+LockState.LockState], ax
0x1400600d1  mov     rsi, rdx
0x1400600d4  mov     [rbp+LockState.OldIrql], r15b
0x1400600d8  mov     rbx, rcx
0x1400600db  mov     dword ptr [rbp+Event.Event.Header.___u0], r15d
0x1400600df  lea     r12d, [r15+1]
0x1400600e3  movups  xmmword ptr [rbp+Event.Event.Header.SignalState], xmm0
0x1400600e7  mov     dword ptr [rbp+Event.Event.Header.WaitListHead.Blink+4], eax
0x1400600ea  lock add [rcx+330h], r12d
0x1400600f2  mov     rax, [rbp+arg_28]
0x1400600f6  mov     r13d, 103h
0x1400600fc  cmp     dword ptr [rax], 18h
0x1400600ff  jnb     short loc_140060136
0x140060101  mov     edi, 80000005h
0x140060106  mov     rcx, cs:WPP_GLOBAL_Control
0x14006010d  lea     rax, WPP_GLOBAL_Control
0x140060114  cmp     rcx, rax
0x140060117  jz      loc_1400605AE
0x14006011d  lea     edx, [r15+66h]
0x140060121  mov     rcx, [rcx+18h]
0x140060125  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14006012c  call    WPP_SF_
0x140060131  jmp     loc_1400605AE
0x140060136  mov     rax, [rbp+arg_20]
0x14006013a  mov     [rax], r15
0x14006013d  mov     r9, [rcx+0A38h]
0x140060144  mov     rcx, [r9+10h]
0x140060148  mov     rax, [rcx+30h]
0x14006014c  test    [rcx+28h], rax
0x140060150  jnz     short loc_14006019B
0x140060152  cmp     cs:byte_1400AF803, r15b
0x140060159  jge     short loc_140060178
0x14006015b  lea     r8, [r9+1338h]
0x140060162  mov     dword ptr [rsp+60h+var_38], r15d
0x140060167  lea     rdx, ConnectRadioOff
0x14006016e  mov     [rsp+60h+var_40], r8
0x140060173  call    McTemplateK0pjq_EtwWriteTransfer
0x140060178  mov     edi, 0C0232002h
0x14006017d  mov     rcx, cs:WPP_GLOBAL_Control
0x140060184  lea     rax, WPP_GLOBAL_Control
0x14006018b  cmp     rcx, rax
0x14006018e  jz      loc_1400605AE
0x140060194  mov     edx, 67h ; 'g'
0x140060199  jmp     short loc_140060121
0x14006019b  mov     eax, [r9+13F4h]
0x1400601a2  cmp     eax, r12d
0x1400601a5  jle     short loc_140060210
0x1400601a7  cmp     cs:byte_1400AF803, r15b
0x1400601ae  jge     short loc_1400601CC
0x1400601b0  lea     r8, [r9+1338h]
0x1400601b7  mov     dword ptr [rsp+60h+var_38], eax
0x1400601bb  lea     rdx, ConnectRadioLowPower
0x1400601c2  mov     [rsp+60h+var_40], r8
0x1400601c7  call    McTemplateK0pjq_EtwWriteTransfer
0x1400601cc  mov     edi, 0C0232002h
0x1400601d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400601d8  lea     rax, WPP_GLOBAL_Control
0x1400601df  cmp     rcx, rax
0x1400601e2  jz      loc_1400605AE
0x1400601e8  mov     r9, [rbx+0A38h]
0x1400601ef  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x1400601f6  mov     rcx, [rcx+18h]
0x1400601fa  mov     edx, 68h ; 'h'
0x1400601ff  mov     r9d, [r9+13F4h]
0x140060206  call    WPP_SF_d
0x14006020b  jmp     loc_1400605AE
0x140060210  mov     rcx, rbx
0x140060213  call    ExtSTAPlumbExemptionList
0x140060218  mov     edi, eax
0x14006021a  test    eax, eax
0x14006021c  jns     short loc_140060252
0x14006021e  mov     rcx, cs:WPP_GLOBAL_Control
0x140060225  lea     rax, WPP_GLOBAL_Control
0x14006022c  cmp     rcx, rax
0x14006022f  jz      loc_1400605AE
0x140060235  mov     edx, 69h ; 'i'
0x14006023a  mov     rcx, [rcx+18h]
0x14006023e  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x140060245  mov     r9d, edi
0x140060248  call    WPP_SF_d
0x14006024d  jmp     loc_1400605AE
0x140060252  mov     rcx, rbx
0x140060255  call    ExtSTAPlumbMulticastList
0x14006025a  mov     edi, eax
0x14006025c  test    eax, eax
0x14006025e  jns     short loc_14006027E
0x140060260  mov     rcx, cs:WPP_GLOBAL_Control
0x140060267  lea     rax, WPP_GLOBAL_Control
0x14006026e  cmp     rcx, rax
0x140060271  jz      loc_1400605AE
0x140060277  mov     edx, 6Ah ; 'j'
0x14006027c  jmp     short loc_14006023A
0x14006027e  mov     rcx, [rbx+0A38h]
0x140060285  lea     rdx, [rbp+LockState]; LockState
0x140060289  xor     r8d, r8d; Flags
0x14006028c  mov     r14d, r15d
0x14006028f  mov     rcx, [rcx+90h]; Lock
0x140060296  call    cs:__imp_NdisAcquireRWLockWrite
0x14006029d  nop     dword ptr [rax+rax+00h]
0x1400602a2  lea     r8, qword_1400A1D50
0x1400602a9  xor     edx, edx
0x1400602ab  mov     rcx, rbx
0x1400602ae  call    ExtSTAFlushAssocTable
0x1400602b3  mov     [rbx+160h], r15d
0x1400602ba  lea     rcx, [rbx+608h]; struct EXTSTA_PERFTRACK_INFO *
0x1400602c1  mov     [rbx+158h], r15d
0x1400602c8  xor     edx, edx; int
0x1400602ca  and     dword ptr [rbx+610h], 0FFFFFFFBh
0x1400602d1  call    ?ExtSTASetPerftrackInfo@@YAXPEAUEXTSTA_PERFTRACK_INFO@@H@Z; ExtSTASetPerftrackInfo(EXTSTA_PERFTRACK_INFO *,int)
0x1400602d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400602dd  lea     rax, WPP_GLOBAL_Control
0x1400602e4  cmp     rcx, rax
0x1400602e7  jz      short loc_1400602FE
0x1400602e9  mov     rcx, [rcx+18h]
0x1400602ed  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x1400602f4  mov     edx, 6Bh ; 'k'
0x1400602f9  call    WPP_SF_
0x1400602fe  test    cs:byte_1400AF803, 2
0x140060305  jz      short loc_14006032B
0x140060307  mov     r9, [rbx+0A38h]
0x14006030e  lea     rdx, StartConnect
0x140060315  mov     [rsp+60h+var_38], rsi
0x14006031a  lea     r8, [r9+1338h]
0x140060321  mov     [rsp+60h+var_40], r8
0x140060326  call    McTemplateK0pjp_EtwWriteTransfer
0x14006032b  mov     rax, [rbx+0A38h]
0x140060332  mov     dword ptr [rbp+pSystemUpTime], r15d
0x140060336  mov     rcx, [rax+10h]
0x14006033a  cmp     dword ptr [rcx+118h], 40h ; '@'
0x140060341  jnz     short loc_14006035A
0x140060343  mov     rcx, [rbx+0A40h]; struct _WFD_ROLE *
0x14006034a  lea     rdx, [rbp+pSystemUpTime]; unsigned int *
0x14006034e  call    ?WFDRoleGetConnectionTimeout@@YAHPEAU_WFD_ROLE@@PEAK@Z; WFDRoleGetConnectionTimeout(_WFD_ROLE *,ulong *)
0x140060353  mov     edx, dword ptr [rbp+pSystemUpTime]
0x140060356  test    edx, edx
0x140060358  jnz     short loc_140060360
0x14006035a  mov     edx, [rbx+308h]
0x140060360  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140060363  call    ExtSTAStartConnRoamingTimer
0x140060368  mov     [rsi+78h], rbx
0x14006036c  mov     [rbx+10h], rsi
0x140060370  lock add [rbx+330h], r12d
0x140060378  mov     rax, [rsi+0B8h]
0x14006037f  or      [rax+3], r12b
0x140060383  lea     rax, ?ExtSTACancelIoctlConnect@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ExtSTACancelIoctlConnect(_DEVICE_OBJECT *,_IRP *)
0x14006038a  xchg    rax, [rsi+68h]
0x14006038e  cmp     [rsi+44h], r15b
0x140060392  jz      short loc_1400603C4
0x140060394  mov     [rbx+10h], r15
0x140060398  mov     rax, r15
0x14006039b  lock dec dword ptr [rbx+330h]
0x1400603a2  xchg    rax, [rsi+68h]
0x1400603a6  test    rax, rax
0x1400603a9  jz      short loc_1400603B9
0x1400603ab  mov     [rsi+78h], r15
0x1400603af  mov     edi, 0C0000120h
0x1400603b4  jmp     loc_1400604E0
0x1400603b9  mov     edi, r13d
0x1400603bc  mov     rsi, r15
0x1400603bf  jmp     loc_1400604E0
0x1400603c4  test    edi, edi
0x1400603c6  jnz     loc_1400604E0
0x1400603cc  mov     rax, [rbx+0A38h]
0x1400603d3  mov     rdx, 0FFFFF78000000014h
0x1400603dd  mov     rcx, rbx; struct EXTSTA_VELAN *
0x1400603e0  mov     [rax+15F0h], r15d
0x1400603e7  mov     rdx, [rdx]; unsigned __int64
0x1400603ea  call    ?ExtSTAUpdateMiniportMacExcludedList@@YAXPEAUEXTSTA_VELAN@@_K@Z; ExtSTAUpdateMiniportMacExcludedList(EXTSTA_VELAN *,unsigned __int64)
0x1400603ef  lea     rcx, [rbp+Event]; Event
0x1400603f3  call    cs:__imp_NdisInitializeEvent
0x1400603fa  nop     dword ptr [rax+rax+00h]
0x1400603ff  mov     rax, [rbx+0A38h]
0x140060406  mov     rcx, [rax+10h]
0x14006040a  cmp     dword ptr [rcx+118h], 4
0x140060411  jnz     short loc_14006046A
0x140060413  cmp     [rbx+0A78h], r15
0x14006041a  jbe     short loc_140060462
0x14006041c  mov     eax, [rbx+0A70h]
0x140060422  test    eax, eax
0x140060424  jz      short loc_140060462
0x140060426  lea     rcx, [rbp+pSystemUpTime]; pSystemUpTime
0x14006042a  mov     qword ptr [rbp+pSystemUpTime], r15
0x14006042e  call    cs:__imp_NdisGetSystemUpTimeEx
0x140060435  nop     dword ptr [rax+rax+00h]
0x14006043a  mov     eax, r12d
0x14006043d  xchg    eax, [rbx+0A60h]
0x140060443  mov     eax, r12d
0x140060446  xchg    eax, [rbx+0A64h]
0x14006044c  imul    rcx, [rbx+0A78h], 3E8h
0x140060457  add     rcx, qword ptr [rbp+pSystemUpTime]
0x14006045b  mov     [rbx+0A58h], rcx
0x140060462  mov     r8d, 0E010181h
0x140060468  jmp     short loc_140060470
0x14006046a  mov     r8d, 0E060104h; unsigned int
0x140060470  lea     rax, [rbp+arg_0]
0x140060474  xor     r9d, r9d; unsigned int
0x140060477  mov     [rsp+60h+var_28], rax; void *
0x14006047c  lea     rcx, [rbx+18h]; struct DOT11_NDIS_REQUEST *
0x140060480  lea     rax, [rbp+Event]
0x140060484  mov     edx, r12d; unsigned int
0x140060487  mov     [rsp+60h+var_30], rax; void *
0x14006048c  lea     rax, ?ExtSTAOidConnectCompletion@@YAXPEAU_ADAPT@@PEAUDOT11_NDIS_REQUEST@@@Z; ExtSTAOidConnectCompletion(_ADAPT *,DOT11_NDIS_REQUEST *)
0x140060493  mov     [rsp+60h+var_38], rax; void (*)(struct _ADAPT *, struct DOT11_NDIS_REQUEST *)
0x140060498  mov     [rsp+60h+var_40], r15; void *
0x14006049d  call    ?Dot11BuildNdisRequest@@YAXPEAUDOT11_NDIS_REQUEST@@KKKPEAXP6AXPEAU_ADAPT@@0@Z11@Z; Dot11BuildNdisRequest(DOT11_NDIS_REQUEST *,ulong,ulong,ulong,void *,void (*)(_ADAPT *,DOT11_NDIS_REQUEST *),void *,void *)
0x1400604a2  mov     rdx, [rbx+0A38h]
0x1400604a9  lea     rcx, [rbp+pSystemUpTime]; int *
0x1400604ad  mov     r8, [rbx+20h]; struct _NDIS_OID_REQUEST *
0x1400604b1  mov     dword ptr [rbp+pSystemUpTime], r15d
0x1400604b5  mov     rdx, [rdx+10h]; struct _ADAPT *
0x1400604b9  call    ?Dot11Request@@YAXPEAHPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@@Z; Dot11Request(int *,_ADAPT *,_NDIS_OID_REQUEST *)
0x1400604be  mov     edi, dword ptr [rbp+pSystemUpTime]
0x1400604c1  mov     r14d, r12d
0x1400604c4  cmp     edi, r13d
0x1400604c7  jz      short loc_1400604E0
0x1400604c9  mov     rcx, [rbx+0A38h]
0x1400604d0  mov     r8d, edi; int
0x1400604d3  mov     rdx, [rbx+20h]; struct _NDIS_OID_REQUEST *
0x1400604d7  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400604db  call    ?Dot11RequestComplete@@YAXPEAU_ADAPT@@PEAU_NDIS_OID_REQUEST@@H@Z; Dot11RequestComplete(_ADAPT *,_NDIS_OID_REQUEST *,int)
0x1400604e0  mov     rcx, [rbx+0A38h]
0x1400604e7  lea     rdx, [rbp+LockState]; LockState
0x1400604eb  mov     rcx, [rcx+90h]; Lock
0x1400604f2  call    cs:__imp_NdisReleaseRWLock
0x1400604f9  nop     dword ptr [rax+rax+00h]
0x1400604fe  test    r14d, r14d
0x140060501  jz      loc_1400605A9
0x140060507  xor     edx, edx; MsToWait
0x140060509  lea     rcx, [rbp+Event]; Event
0x14006050d  call    cs:__imp_NdisWaitEvent
0x140060514  nop     dword ptr [rax+rax+00h]
0x140060519  mov     edi, [rbp+arg_0]
0x14006051c  test    edi, edi
0x14006051e  jz      loc_1400605C7
0x140060524  mov     rcx, [rbx+0A38h]
0x14006052b  lea     rdx, [rbp+LockState]; LockState
0x14006052f  xor     r8d, r8d; Flags
0x140060532  mov     rcx, [rcx+90h]; Lock
0x140060539  call    cs:__imp_NdisAcquireRWLockWrite
0x140060540  nop     dword ptr [rax+rax+00h]
0x140060545  cmp     [rbx+10h], r15
0x140060549  jz      short loc_140060560
0x14006054b  mov     rax, r15
0x14006054e  mov     [rbx+10h], r15
0x140060552  xchg    rax, [rsi+68h]
0x140060556  mov     r14d, r12d
0x140060559  test    rax, rax
0x14006055c  jnz     short loc_140060569
0x14006055e  jmp     short loc_140060563
0x140060560  mov     r14d, r15d
0x140060563  mov     rsi, r15
0x140060566  mov     edi, r13d
0x140060569  mov     rcx, [rbx+0A38h]
0x140060570  lea     rdx, [rbp+LockState]; LockState
0x140060574  mov     rcx, [rcx+90h]; Lock
0x14006057b  call    cs:__imp_NdisReleaseRWLock
0x140060582  nop     dword ptr [rax+rax+00h]
0x140060587  test    r14d, r14d
0x14006058a  jz      short loc_1400605A9
0x14006058c  mov     rax, [rbx+0A38h]
0x140060593  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140060596  mov     [rax+15F0h], r12d
0x14006059d  call    ExtSTACancelConnRoamingTimerSync
0x1400605a2  lock dec dword ptr [rbx+330h]
0x1400605a9  cmp     edi, r13d
0x1400605ac  jz      short loc_1400605CA
0x1400605ae  mov     [rsi+30h], edi
0x1400605b1  mov     rdx, rsi; struct _IRP *
0x1400605b4  mov     rcx, [rbx+0A38h]; struct _VELAN *
0x1400605bb  call    ?NWFCompleteIrp@@YAXPEAU_VELAN@@PEAU_IRP@@@Z; NWFCompleteIrp(_VELAN *,_IRP *)
0x1400605c0  lock dec dword ptr [rbx+330h]
0x1400605c7  mov     edi, r13d
0x1400605ca  mov     rbx, [rsp+60h+arg_8]
0x1400605d2  mov     eax, edi
0x1400605d4  add     rsp, 60h
0x1400605d8  pop     r15
0x1400605da  pop     r14
0x1400605dc  pop     r13
0x1400605de  pop     r12
0x1400605e0  pop     rdi
0x1400605e1  pop     rsi
0x1400605e2  pop     rbp
0x1400605e3  retn
```
