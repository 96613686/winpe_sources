# ndisPnPRemoveDevice(_NDIS_MINIPORT_BLOCK *,uchar)

- ea: `0x14017fc50`
- end: `0x14017fff4`
- name: `?ndisPnPRemoveDevice@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z`
- size: `932`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, unsigned __int8)`
- caller_count: `3`
- callee_count: `29`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x140005cb0`
- `0x140070890`
- `0x140087be8`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x140017480`
- `0x140017510`
- `0x14002ab60`
- `0x14003d6e0`
- `0x1400400d0`
- `0x140044e80`
- `0x140053280`
- `0x140057600`
- `0x14005b320`
- `0x140063390`
- `0x14006f4e0`
- `0x1400834f0`
- `0x14008b7f0`
- `0x14009d560`
- `0x1400e1804`
- `0x1400eb380`
- `0x1400eb4c0`
- `0x1400eb7c0`
- `0x140142850`
- `0x1401531e4`
- `0x14015d480`
- `0x14015dae0`
- `0x14015ddf0`
- `0x14015dec0`
- `0x14015ed60`
- `0x14016b210`
- `0x14017fc50`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14017fec6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14017fec6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14017fede`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14017fede`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14017ff7c`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14017ff7c`
- `ntoskrnl!IoWMIWriteEvent` at `0x14018971f`
- `ntoskrnl!IoWMIWriteEvent` at `0x14018971f`
- `ntoskrnl!KeReleaseMutex` at `0x14017ffa9`
- `ntoskrnl!KeReleaseMutex` at `0x14017ffa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018979d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14018979d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017fd8e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14017fd8e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14017fd66`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14017fd66`

## pseudocode

```c
void __fastcall ndisPnPRemoveDevice(struct _NDIS_MINIPORT_BLOCK *a1, char a2)
{
  _NDIS_M_DRIVER_BLOCK *DriverHandle; // rdi
  int v5; // edx
  char v6; // r15
  KIRQL v7; // al
  struct _NDIS_MINIPORT_BLOCK *i; // rbp
  _UNICODE_STRING *pAdapterInstanceName; // rdx
  unsigned int v10; // r8d
  void *v11; // rbp
  _NDIS_SRIOV_CAPABILITIES *SriovCurrentCapabilities; // rax
  unsigned __int16 *v13; // rcx
  int v14; // edx
  __int64 v15; // rcx
  NTSTATUS v16; // r14d
  int v17; // edx
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-148h] BYREF
  char v19[256]; // [rsp+50h] [rbp-138h] BYREF

  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      13,
      93,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)a1,
      a2);
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  DriverHandle = a1->DriverHandle;
  if ( DriverHandle )
  {
    v6 = 0;
    if ( (DriverHandle->Flags & 1) != 0 )
    {
      ndisWaitForKernelObject(&DriverHandle->IMStartRemoveMutex);
      v6 = 1;
      DriverHandle->IMStartRemoveMutexOwnerThread = KeGetCurrentThread();
    }
    ndisCancelWaitWake(a1);
    v7 = KeAcquireSpinLockRaiseToDpc(&DriverHandle->Ref.SpinLock);
    for ( i = DriverHandle->MiniportQueue; i; i = i->NextMiniport )
    {
      if ( i == a1 )
        break;
    }
    KeReleaseSpinLock(&DriverHandle->Ref.SpinLock, v7);
    if ( i != a1 || a1->Ref.Closing == 1 )
    {
      a1->Ref.Closing = 1;
    }
    else
    {
      ndisReferenceDriver(DriverHandle, MDRVREF_REMOVINGMP);
      NdisResetEvent(&a1->OpenReadyEvent);
      pAdapterInstanceName = a1->pAdapterInstanceName;
      if ( pAdapterInstanceName )
      {
        v10 = a1->MiniportName.Length + 2;
        *(_QWORD *)&DestinationString.Length = 0;
        ndisSetupWmiNode(
          a1,
          pAdapterInstanceName,
          v10,
          &GUID_NDIS_NOTIFY_ADAPTER_REMOVAL,
          (struct tagWNODE_SINGLE_INSTANCE **)&DestinationString);
        v11 = *(void **)&DestinationString.Length;
        if ( *(_QWORD *)&DestinationString.Length )
        {
          v13 = (unsigned __int16 *)(*(_QWORD *)&DestinationString.Length
                                   + *(unsigned int *)(*(_QWORD *)&DestinationString.Length + 56LL));
          *v13 = a1->MiniportName.Length;
          memmove(v13 + 1, a1->MiniportName.Buffer, a1->MiniportName.Length);
          v16 = IoWMIWriteEvent(v11);
          if ( v16 < 0 )
          {
            if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v14) = 2;
              WPP_RECORDER_SF_(
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                v14,
                18,
                94,
                (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids);
            }
            if ( (byte_140121001 & 0x10) != 0 )
              ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD))McTemplateK0jqxd_EtwWriteTransfer)(
                v15,
                IndicateAdapterRemovalFailed,
                &a1->InterfaceGuid,
                &a1->InterfaceGuid,
                a1->IfIndex,
                (_NET_LUID_LH)a1->NetLuid.Value,
                v16);
            ExFreePoolWithTag(v11, 0);
          }
        }
      }
      Ndis::BindEngine::BeginPolicyUpdates(&a1->BindEngine);
      if ( Ndis::BindState::SetPause(&a1->Bindings.Miniport, DatapathPaused, PauseReason_RemovingMiniport) )
      {
        memset(v19, 0, 0xA0u);
        if ( (unsigned __int8)byte_140122AD3 >= 4u )
        {
          ndisGetBindLinkNameForTracing(a1, (struct NDIS_PNPTRACE_LOCALS *)v19);
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_Zq(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v17,
              28,
              95,
              (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
              *(__int64 *)&v19[8],
              v19[0]);
        }
      }
      Ndis::BindEngine::EndPolicyUpdates(&a1->BindEngine);
      Ndis::BindEngine::ApplyBindChanges(&a1->BindEngine, RunSynchronous, 0);
      SriovCurrentCapabilities = a1->SriovCurrentCapabilities;
      if ( SriovCurrentCapabilities && (SriovCurrentCapabilities->SriovCapabilities & 5) == 5 )
        ndisIovTeardownVf(a1);
      ndisMSetMiniportReadyForBinding(a1, 0, Reason_RemovingMiniport, RunSynchronous);
      if ( (a1->PnPFlags & 0x8000000) != 0 )
        ndisIMDeleteIfStackEntry(a1);
      ndisIovDeleteDefaultNicSwitch(a1);
      ndisMHaltMiniport(a1);
      ndisMCleanupMiniportBlockOnStop(a1);
      ndisDereferenceDriver(DriverHandle, 0, MDRVREF_REMOVINGMP);
      *(_QWORD *)&DestinationString.Length = 0x1000000;
      DestinationString.Buffer = (wchar_t *)v19;
      RtlCopyUnicodeString(&DestinationString, &ndisDosDevicesStr);
      if ( RtlAppendUnicodeStringToString(&DestinationString, &a1->BaseName) >= 0 )
        IoDeleteSymbolicLink(&DestinationString);
    }
    if ( v6 == 1 )
    {
      DriverHandle->IMStartRemoveMutexOwnerThread = 0;
      KeReleaseMutex(&DriverHandle->IMStartRemoveMutex, 0);
    }
  }
  if ( a2 )
    ndisPnPCompleteRemoveDevice(a1);
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v5) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v5,
      13,
      96,
      (struct _GUID *)&WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids,
      (char)a1);
  }
}

```

## disassembly

```asm
0x14017fc50  mov     r11, rsp
0x14017fc53  push    rbx
0x14017fc54  push    r13
0x14017fc56  sub     rsp, 178h
0x14017fc5d  mov     rax, cs:__security_cookie
0x14017fc64  xor     rax, rsp
0x14017fc67  mov     [rsp+188h+var_38], rax
0x14017fc6f  mov     [r11+18h], rsi
0x14017fc73  mov     rbx, rcx
0x14017fc76  mov     [r11+20h], rdi
0x14017fc7a  mov     [r11-18h], r12
0x14017fc7e  movzx   esi, dl
0x14017fc81  lea     r12, WPP_RECORDER_INITIALIZED
0x14017fc88  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14017fc8f  lea     r13, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x14017fc96  jz      short loc_14017FCC4
0x14017fc98  mov     dword ptr [rsp+188h+var_158], esi; char
0x14017fc9c  mov     r9d, 5Dh ; ']'; int
0x14017fca2  mov     qword ptr [rsp+188h+var_160], rcx; char
0x14017fca7  mov     r8d, 0Dh; int
0x14017fcad  mov     rcx, cs:WPP_GLOBAL_Control
0x14017fcb4  mov     dl, 4; int
0x14017fcb6  mov     [rsp+188h+var_168], r13; struct _GUID *
0x14017fcbb  mov     rcx, [rcx+40h]; int
0x14017fcbf  call    WPP_RECORDER_SF_qD
0x14017fcc4  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14017fccb  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14017fcd0  mov     rdi, [rbx+0EB0h]
0x14017fcd7  test    rdi, rdi
0x14017fcda  jnz     short loc_14017FD32
0x14017fcdc  mov     rdi, [rsp+188h+arg_18]
0x14017fce4  test    sil, sil
0x14017fce7  mov     rsi, [rsp+188h+arg_10]
0x14017fcef  jnz     loc_14017FFBA
0x14017fcf5  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x14017fcfc  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x14017fd01  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14017fd08  mov     r12, [rsp+188h+var_18]
0x14017fd10  jnz     loc_14017FFC7
0x14017fd16  mov     rcx, [rsp+188h+var_38]
0x14017fd1e  xor     rcx, rsp; StackCookie
0x14017fd21  call    __security_check_cookie
0x14017fd26  add     rsp, 178h
0x14017fd2d  pop     r13
0x14017fd2f  pop     rbx
0x14017fd30  retn
0x14017fd32  mov     [rsp+188h+arg_8], rbp
0x14017fd3a  mov     [rsp+188h+var_20], r14
0x14017fd42  mov     [rsp+188h+var_28], r15
0x14017fd4a  xor     r15b, r15b
0x14017fd4d  test    byte ptr [rdi+1Ah], 1
0x14017fd51  jnz     loc_14017FF19
0x14017fd57  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017fd5a  call    ?ndisCancelWaitWake@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisCancelWaitWake(_NDIS_MINIPORT_BLOCK *)
0x14017fd5f  lea     rcx, [rdi+188h]; SpinLock
0x14017fd66  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14017fd6d  nop     dword ptr [rax+rax+00h]
0x14017fd72  mov     rbp, [rdi+10h]
0x14017fd76  test    rbp, rbp
0x14017fd79  jz      short loc_14017FD84
0x14017fd7b  cmp     rbp, rbx
0x14017fd7e  jnz     loc_14017FF3D
0x14017fd84  movzx   edx, al; NewIrql
0x14017fd87  lea     rcx, [rdi+188h]; SpinLock
0x14017fd8e  call    cs:__imp_KeReleaseSpinLock
0x14017fd95  nop     dword ptr [rax+rax+00h]
0x14017fd9a  xor     r14d, r14d
0x14017fd9d  cmp     rbp, rbx
0x14017fda0  jnz     loc_14017FF8D
0x14017fda6  cmp     byte ptr [rbx+115Ch], 1
0x14017fdad  jz      loc_14017FF8D
0x14017fdb3  mov     dl, 1; enum _NDIS_MDRV_REFTAG
0x14017fdb5  mov     rcx, rdi; struct _NDIS_M_DRIVER_BLOCK *
0x14017fdb8  call    ?ndisReferenceDriver@@YAEPEAU_NDIS_M_DRIVER_BLOCK@@W4_NDIS_MDRV_REFTAG@@@Z; ndisReferenceDriver(_NDIS_M_DRIVER_BLOCK *,_NDIS_MDRV_REFTAG)
0x14017fdbd  lea     rcx, [rbx+0E90h]; Event
0x14017fdc4  call    NdisResetEvent
0x14017fdc9  mov     rdx, [rbx+0F10h]; struct _UNICODE_STRING *
0x14017fdd0  test    rdx, rdx
0x14017fdd3  jz      short loc_14017FE0D
0x14017fdd5  movzx   r8d, word ptr [rbx+0EE0h]
0x14017fddd  lea     rax, [rsp+188h+DestinationString]
0x14017fde2  add     r8d, 2; unsigned int
0x14017fde6  mov     qword ptr [rsp+188h+DestinationString.Length], r14
0x14017fdeb  lea     r9, GUID_NDIS_NOTIFY_ADAPTER_REMOVAL; void *
0x14017fdf2  mov     [rsp+188h+var_168], rax; struct tagWNODE_SINGLE_INSTANCE **
0x14017fdf7  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017fdfa  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x14017fdff  mov     rbp, qword ptr [rsp+188h+DestinationString.Length]
0x14017fe04  test    rbp, rbp
0x14017fe07  jnz     loc_1401896F4
0x14017fe0d  lea     rcx, [rbx+1400h]; this
0x14017fe14  call    ?BeginPolicyUpdates@BindEngine@Ndis@@QEAAXXZ; Ndis::BindEngine::BeginPolicyUpdates(void)
0x14017fe19  lea     rcx, [rbx+13B8h]; this
0x14017fe20  xor     edx, edx; enum PAUSE_OR_RESTART
0x14017fe22  mov     r8d, 8; enum NDIS_PAUSE_REASON
0x14017fe28  call    ?SetPause@BindState@Ndis@@QEAA_NW4PAUSE_OR_RESTART@@W4NDIS_PAUSE_REASON@@@Z; Ndis::BindState::SetPause(PAUSE_OR_RESTART,NDIS_PAUSE_REASON)
0x14017fe2d  test    al, al
0x14017fe2f  jnz     loc_1401897B1
0x14017fe35  lea     rcx, [rbx+1400h]; this
0x14017fe3c  call    ?EndPolicyUpdates@BindEngine@Ndis@@QEAAXXZ; Ndis::BindEngine::EndPolicyUpdates(void)
0x14017fe41  xor     r8d, r8d; bool
0x14017fe44  lea     rcx, [rbx+1400h]; this
0x14017fe4b  xor     edx, edx; enum CallRunMode
0x14017fe4d  call    ?ApplyBindChanges@BindEngine@Ndis@@QEAAXW4CallRunMode@@_N@Z; Ndis::BindEngine::ApplyBindChanges(CallRunMode,bool)
0x14017fe52  mov     rax, [rbx+1200h]
0x14017fe59  test    rax, rax
0x14017fe5c  jnz     loc_14017FF4F
0x14017fe62  xor     r9d, r9d; enum CallRunMode
0x14017fe65  xor     edx, edx; bool
0x14017fe67  mov     r8d, 1000h; enum NDIS_DO_NOT_BIND_REASON
0x14017fe6d  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017fe70  call    ?ndisMSetMiniportReadyForBinding@@YAXPEAU_NDIS_MINIPORT_BLOCK@@_NW4NDIS_DO_NOT_BIND_REASON@@W4CallRunMode@@@Z; ndisMSetMiniportReadyForBinding(_NDIS_MINIPORT_BLOCK *,bool,NDIS_DO_NOT_BIND_REASON,CallRunMode)
0x14017fe75  test    dword ptr [rbx+7Ch], 8000000h
0x14017fe7c  jnz     loc_14017FF6A
0x14017fe82  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017fe85  call    ?ndisIovDeleteDefaultNicSwitch@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIovDeleteDefaultNicSwitch(_NDIS_MINIPORT_BLOCK *)
0x14017fe8a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017fe8d  call    ?ndisMHaltMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMHaltMiniport(_NDIS_MINIPORT_BLOCK *)
0x14017fe92  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017fe95  call    ?ndisMCleanupMiniportBlockOnStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMCleanupMiniportBlockOnStop(_NDIS_MINIPORT_BLOCK *)
0x14017fe9a  mov     r8b, 1; enum _NDIS_MDRV_REFTAG
0x14017fe9d  xor     edx, edx; unsigned __int8
0x14017fe9f  mov     rcx, rdi; struct _NDIS_M_DRIVER_BLOCK *
0x14017fea2  call    ?ndisDereferenceDriver@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@EW4_NDIS_MDRV_REFTAG@@@Z; ndisDereferenceDriver(_NDIS_M_DRIVER_BLOCK *,uchar,_NDIS_MDRV_REFTAG)
0x14017fea7  lea     rax, [rsp+188h+var_138]
0x14017feac  mov     qword ptr [rsp+188h+DestinationString.Length], 1000000h
0x14017feb5  lea     rdx, ?ndisDosDevicesStr@@3U_UNICODE_STRING@@A; SourceString
0x14017febc  mov     [rsp+188h+DestinationString.Buffer], rax
0x14017fec1  lea     rcx, [rsp+188h+DestinationString]; DestinationString
0x14017fec6  call    cs:__imp_RtlCopyUnicodeString
0x14017fecd  nop     dword ptr [rax+rax+00h]
0x14017fed2  lea     rdx, [rbx+0ED0h]; Source
0x14017fed9  lea     rcx, [rsp+188h+DestinationString]; Destination
0x14017fede  call    cs:__imp_RtlAppendUnicodeStringToString
0x14017fee5  nop     dword ptr [rax+rax+00h]
0x14017feea  test    eax, eax
0x14017feec  jns     loc_14017FF77
0x14017fef2  mov     rbp, [rsp+188h+arg_8]
0x14017fefa  cmp     r15b, 1
0x14017fefe  mov     r15, [rsp+188h+var_28]
0x14017ff06  jz      loc_14017FF99
0x14017ff0c  mov     r14, [rsp+188h+var_20]
0x14017ff14  jmp     loc_14017FCDC
0x14017ff19  lea     rcx, [rdi+1A0h]; void *
0x14017ff20  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x14017ff25  mov     rax, gs:188h
0x14017ff2e  mov     r15b, 1
0x14017ff31  mov     [rdi+1D8h], rax
0x14017ff38  jmp     loc_14017FD57
0x14017ff3d  mov     rbp, [rbp+8]
0x14017ff41  test    rbp, rbp
0x14017ff44  jnz     loc_14017FD7B
0x14017ff4a  jmp     loc_14017FD84
0x14017ff4f  mov     eax, [rax+8]
0x14017ff52  and     eax, 5
0x14017ff55  cmp     al, 5
0x14017ff57  jnz     loc_14017FE62
0x14017ff5d  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017ff60  call    ?ndisIovTeardownVf@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIovTeardownVf(_NDIS_MINIPORT_BLOCK *)
0x14017ff65  jmp     loc_14017FE62
0x14017ff6a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017ff6d  call    ?ndisIMDeleteIfStackEntry@@YAJPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIMDeleteIfStackEntry(_NDIS_MINIPORT_BLOCK *)
0x14017ff72  jmp     loc_14017FE82
0x14017ff77  lea     rcx, [rsp+188h+DestinationString]; SymbolicLinkName
0x14017ff7c  call    cs:__imp_IoDeleteSymbolicLink
0x14017ff83  nop     dword ptr [rax+rax+00h]
0x14017ff88  jmp     loc_14017FEF2
0x14017ff8d  mov     byte ptr [rbx+115Ch], 1
0x14017ff94  jmp     loc_14017FEF2
0x14017ff99  lea     rcx, [rdi+1A0h]; Mutex
0x14017ffa0  mov     [rdi+1D8h], r14
0x14017ffa7  xor     edx, edx; Wait
0x14017ffa9  call    cs:__imp_KeReleaseMutex
0x14017ffb0  nop     dword ptr [rax+rax+00h]
0x14017ffb5  jmp     loc_14017FF0C
0x14017ffba  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017ffbd  call    ?ndisPnPCompleteRemoveDevice@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPnPCompleteRemoveDevice(_NDIS_MINIPORT_BLOCK *)
0x14017ffc2  jmp     loc_14017FCF5
0x14017ffc7  mov     rcx, cs:WPP_GLOBAL_Control
0x14017ffce  mov     r9d, 60h ; '`'; int
0x14017ffd4  mov     qword ptr [rsp+188h+var_160], rbx; char
0x14017ffd9  mov     r8d, 0Dh; int
0x14017ffdf  mov     dl, 4; int
0x14017ffe1  mov     [rsp+188h+var_168], r13; struct _GUID *
0x14017ffe6  mov     rcx, [rcx+40h]; int
0x14017ffea  call    WPP_RECORDER_SF_q
0x14017ffef  jmp     loc_14017FD16
0x1401896f4  mov     ecx, [rbp+38h]
0x1401896f7  movzx   eax, word ptr [rbx+0EE0h]
0x1401896fe  add     rcx, rbp
0x140189701  mov     [rcx], ax
0x140189704  add     rcx, 2; void *
0x140189708  movzx   r8d, word ptr [rbx+0EE0h]; Size
0x140189710  mov     rdx, [rbx+0EE8h]; Src
0x140189717  call    memmove
0x14018971c  mov     rcx, rbp; WnodeEventItem
0x14018971f  call    cs:__imp_IoWMIWriteEvent
0x140189726  nop     dword ptr [rax+rax+00h]
0x14018972b  mov     r14d, eax
0x14018972e  test    eax, eax
0x140189730  jns     short loc_1401897A9
0x140189732  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140189739  jz      short loc_14018975E
0x14018973b  mov     rcx, cs:WPP_GLOBAL_Control
0x140189742  mov     r9d, 5Eh ; '^'; int
0x140189748  mov     r8d, 12h; int
0x14018974e  mov     [rsp+188h+var_168], r13; struct _GUID *
0x140189753  mov     dl, 2; int
0x140189755  mov     rcx, [rcx+40h]; int
0x140189759  call    WPP_RECORDER_SF_
0x14018975e  test    cs:byte_140121001, 10h
0x140189765  jz      short loc_140189798
0x140189767  mov     rax, [rbx+0FB8h]
0x14018976e  lea     r8, [rbx+0FA8h]
0x140189775  mov     dword ptr [rsp+188h+var_158], r14d
0x14018977a  lea     rdx, IndicateAdapterRemovalFailed
0x140189781  mov     qword ptr [rsp+188h+var_160], rax
0x140189786  mov     r9, r8
0x140189789  mov     eax, [rbx+0FD8h]
0x14018978f  mov     dword ptr [rsp+188h+var_168], eax
0x140189793  call    McTemplateK0jqxd_EtwWriteTransfer
0x140189798  xor     edx, edx; Tag
0x14018979a  mov     rcx, rbp; P
0x14018979d  call    cs:__imp_ExFreePoolWithTag
0x1401897a4  nop     dword ptr [rax+rax+00h]
0x1401897a9  xor     r14d, r14d
0x1401897ac  jmp     loc_14017FE0D
0x1401897b1  xor     edx, edx; Val
0x1401897b3  lea     rcx, [rsp+188h+var_138]; void *
0x1401897b8  mov     r8d, 0A0h; Size
0x1401897be  call    memset
0x1401897c3  cmp     cs:byte_140122AD3, 4
0x1401897ca  jb      loc_14017FE35
0x1401897d0  lea     rdx, [rsp+188h+var_138]; struct NDIS_PNPTRACE_LOCALS *
0x1401897d5  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401897d8  call    ?ndisGetBindLinkNameForTracing@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_PNPTRACE_LOCALS@@@Z; ndisGetBindLinkNameForTracing(_NDIS_MINIPORT_BLOCK *,NDIS_PNPTRACE_LOCALS *)
0x1401897dd  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401897e4  jz      loc_14017FE35
0x1401897ea  mov     rax, qword ptr [rsp+188h+var_138]
0x1401897ef  mov     r9d, 5Fh ; '_'; int
0x1401897f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1401897fc  mov     r8d, 1Ch; int
0x140189802  mov     qword ptr [rsp+188h+var_158], rax; char
0x140189807  mov     rax, [rsp+188h+var_130]
0x14018980c  mov     qword ptr [rsp+188h+var_160], rax; __int64
0x140189811  mov     rcx, [rcx+40h]; int
0x140189815  mov     [rsp+188h+var_168], r13; struct _GUID *
0x14018981a  call    WPP_RECORDER_SF_Zq
0x14018981f  nop
0x140189820  jmp     loc_14017FE35
```
