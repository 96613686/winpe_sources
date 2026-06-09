# ndisPnPRemoveDevice(_NDIS_MINIPORT_BLOCK *,uchar)

- ea: `0x140179c80`
- end: `0x14017a024`
- name: `?ndisPnPRemoveDevice@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z`
- size: `932`
- prototype: `void __fastcall(struct _NDIS_MINIPORT_BLOCK *, unsigned __int8)`
- caller_count: `3`
- callee_count: `29`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x140036ee0`
- `0x14006af10`
- `0x140082968`

## callees

- `0x140012a70`
- `0x14001cf50`
- `0x14001d030`
- `0x140023320`
- `0x1400233b0`
- `0x140029620`
- `0x14003a010`
- `0x14003d920`
- `0x14004e050`
- `0x140052300`
- `0x140056ae0`
- `0x14005edf0`
- `0x140069e80`
- `0x14007dd00`
- `0x140086570`
- `0x1400982e0`
- `0x1400dc654`
- `0x1400e6160`
- `0x1400e62c0`
- `0x1400e65c0`
- `0x14013b910`
- `0x14014c244`
- `0x1401564e0`
- `0x140156b40`
- `0x140156e50`
- `0x140156f20`
- `0x140157dc0`
- `0x140164280`
- `0x140179c80`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140179ef6`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140179ef6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140179f0e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140179f0e`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140179fac`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140179fac`
- `ntoskrnl!IoWMIWriteEvent` at `0x14018374f`
- `ntoskrnl!IoWMIWriteEvent` at `0x14018374f`
- `ntoskrnl!KeReleaseMutex` at `0x140179fd9`
- `ntoskrnl!KeReleaseMutex` at `0x140179fd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401837cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401837cd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140179dbe`
- `ntoskrnl!KeReleaseSpinLock` at `0x140179dbe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140179d96`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140179d96`

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
          (__int128 *)&GUID_NDIS_NOTIFY_ADAPTER_REMOVAL,
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
            if ( (byte_14011B001 & 0x10) != 0 )
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
        if ( (unsigned __int8)byte_14011CAD3 >= 4u )
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
0x140179c80  mov     r11, rsp
0x140179c83  push    rbx
0x140179c84  push    r13
0x140179c86  sub     rsp, 178h
0x140179c8d  mov     rax, cs:__security_cookie
0x140179c94  xor     rax, rsp
0x140179c97  mov     [rsp+188h+var_38], rax
0x140179c9f  mov     [r11+18h], rsi
0x140179ca3  mov     rbx, rcx
0x140179ca6  mov     [r11+20h], rdi
0x140179caa  mov     [r11-18h], r12
0x140179cae  movzx   esi, dl
0x140179cb1  lea     r12, WPP_RECORDER_INITIALIZED
0x140179cb8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140179cbf  lea     r13, WPP_b0ad62796b5830cbf8ad07ce2f1bab24_Traceguids
0x140179cc6  jz      short loc_140179CF4
0x140179cc8  mov     dword ptr [rsp+188h+var_158], esi; char
0x140179ccc  mov     r9d, 5Dh ; ']'; int
0x140179cd2  mov     qword ptr [rsp+188h+var_160], rcx; char
0x140179cd7  mov     r8d, 0Dh; int
0x140179cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140179ce4  mov     dl, 4; int
0x140179ce6  mov     [rsp+188h+var_168], r13; struct _GUID *
0x140179ceb  mov     rcx, [rcx+40h]; int
0x140179cef  call    WPP_RECORDER_SF_qD
0x140179cf4  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140179cfb  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140179d00  mov     rdi, [rbx+0EB0h]
0x140179d07  test    rdi, rdi
0x140179d0a  jnz     short loc_140179D62
0x140179d0c  mov     rdi, [rsp+188h+arg_18]
0x140179d14  test    sil, sil
0x140179d17  mov     rsi, [rsp+188h+arg_10]
0x140179d1f  jnz     loc_140179FEA
0x140179d25  lea     rcx, ?ndisPkgs@@3PAU_PKG_REF@@A; struct _PKG_REF *
0x140179d2c  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x140179d31  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140179d38  mov     r12, [rsp+188h+var_18]
0x140179d40  jnz     loc_140179FF7
0x140179d46  mov     rcx, [rsp+188h+var_38]
0x140179d4e  xor     rcx, rsp; StackCookie
0x140179d51  call    __security_check_cookie
0x140179d56  add     rsp, 178h
0x140179d5d  pop     r13
0x140179d5f  pop     rbx
0x140179d60  retn
0x140179d62  mov     [rsp+188h+arg_8], rbp
0x140179d6a  mov     [rsp+188h+var_20], r14
0x140179d72  mov     [rsp+188h+var_28], r15
0x140179d7a  xor     r15b, r15b
0x140179d7d  test    byte ptr [rdi+1Ah], 1
0x140179d81  jnz     loc_140179F49
0x140179d87  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179d8a  call    ?ndisCancelWaitWake@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisCancelWaitWake(_NDIS_MINIPORT_BLOCK *)
0x140179d8f  lea     rcx, [rdi+188h]; SpinLock
0x140179d96  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140179d9d  nop     dword ptr [rax+rax+00h]
0x140179da2  mov     rbp, [rdi+10h]
0x140179da6  test    rbp, rbp
0x140179da9  jz      short loc_140179DB4
0x140179dab  cmp     rbp, rbx
0x140179dae  jnz     loc_140179F6D
0x140179db4  movzx   edx, al; NewIrql
0x140179db7  lea     rcx, [rdi+188h]; SpinLock
0x140179dbe  call    cs:__imp_KeReleaseSpinLock
0x140179dc5  nop     dword ptr [rax+rax+00h]
0x140179dca  xor     r14d, r14d
0x140179dcd  cmp     rbp, rbx
0x140179dd0  jnz     loc_140179FBD
0x140179dd6  cmp     byte ptr [rbx+115Ch], 1
0x140179ddd  jz      loc_140179FBD
0x140179de3  mov     dl, 1; enum _NDIS_MDRV_REFTAG
0x140179de5  mov     rcx, rdi; struct _NDIS_M_DRIVER_BLOCK *
0x140179de8  call    ?ndisReferenceDriver@@YAEPEAU_NDIS_M_DRIVER_BLOCK@@W4_NDIS_MDRV_REFTAG@@@Z; ndisReferenceDriver(_NDIS_M_DRIVER_BLOCK *,_NDIS_MDRV_REFTAG)
0x140179ded  lea     rcx, [rbx+0E90h]; Event
0x140179df4  call    NdisResetEvent
0x140179df9  mov     rdx, [rbx+0F10h]; struct _UNICODE_STRING *
0x140179e00  test    rdx, rdx
0x140179e03  jz      short loc_140179E3D
0x140179e05  movzx   r8d, word ptr [rbx+0EE0h]
0x140179e0d  lea     rax, [rsp+188h+DestinationString]
0x140179e12  add     r8d, 2; unsigned int
0x140179e16  mov     qword ptr [rsp+188h+DestinationString.Length], r14
0x140179e1b  lea     r9, GUID_NDIS_NOTIFY_ADAPTER_REMOVAL; void *
0x140179e22  mov     [rsp+188h+var_168], rax; struct tagWNODE_SINGLE_INSTANCE **
0x140179e27  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179e2a  call    ?ndisSetupWmiNode@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEBU_UNICODE_STRING@@KPEAXPEAPEAUtagWNODE_SINGLE_INSTANCE@@@Z; ndisSetupWmiNode(_NDIS_MINIPORT_BLOCK *,_UNICODE_STRING const *,ulong,void *,tagWNODE_SINGLE_INSTANCE * *)
0x140179e2f  mov     rbp, qword ptr [rsp+188h+DestinationString.Length]
0x140179e34  test    rbp, rbp
0x140179e37  jnz     loc_140183724
0x140179e3d  lea     rcx, [rbx+1400h]; this
0x140179e44  call    ?BeginPolicyUpdates@BindEngine@Ndis@@QEAAXXZ; Ndis::BindEngine::BeginPolicyUpdates(void)
0x140179e49  lea     rcx, [rbx+13B8h]; this
0x140179e50  xor     edx, edx; enum PAUSE_OR_RESTART
0x140179e52  mov     r8d, 8; enum NDIS_PAUSE_REASON
0x140179e58  call    ?SetPause@BindState@Ndis@@QEAA_NW4PAUSE_OR_RESTART@@W4NDIS_PAUSE_REASON@@@Z; Ndis::BindState::SetPause(PAUSE_OR_RESTART,NDIS_PAUSE_REASON)
0x140179e5d  test    al, al
0x140179e5f  jnz     loc_1401837E1
0x140179e65  lea     rcx, [rbx+1400h]; this
0x140179e6c  call    ?EndPolicyUpdates@BindEngine@Ndis@@QEAAXXZ; Ndis::BindEngine::EndPolicyUpdates(void)
0x140179e71  xor     r8d, r8d; bool
0x140179e74  lea     rcx, [rbx+1400h]; this
0x140179e7b  xor     edx, edx; enum CallRunMode
0x140179e7d  call    ?ApplyBindChanges@BindEngine@Ndis@@QEAAXW4CallRunMode@@_N@Z; Ndis::BindEngine::ApplyBindChanges(CallRunMode,bool)
0x140179e82  mov     rax, [rbx+1200h]
0x140179e89  test    rax, rax
0x140179e8c  jnz     loc_140179F7F
0x140179e92  xor     r9d, r9d; enum CallRunMode
0x140179e95  xor     edx, edx; bool
0x140179e97  mov     r8d, 1000h; enum NDIS_DO_NOT_BIND_REASON
0x140179e9d  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179ea0  call    ?ndisMSetMiniportReadyForBinding@@YAXPEAU_NDIS_MINIPORT_BLOCK@@_NW4NDIS_DO_NOT_BIND_REASON@@W4CallRunMode@@@Z; ndisMSetMiniportReadyForBinding(_NDIS_MINIPORT_BLOCK *,bool,NDIS_DO_NOT_BIND_REASON,CallRunMode)
0x140179ea5  test    dword ptr [rbx+7Ch], 8000000h
0x140179eac  jnz     loc_140179F9A
0x140179eb2  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179eb5  call    ?ndisIovDeleteDefaultNicSwitch@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIovDeleteDefaultNicSwitch(_NDIS_MINIPORT_BLOCK *)
0x140179eba  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179ebd  call    ?ndisMHaltMiniport@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMHaltMiniport(_NDIS_MINIPORT_BLOCK *)
0x140179ec2  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179ec5  call    ?ndisMCleanupMiniportBlockOnStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMCleanupMiniportBlockOnStop(_NDIS_MINIPORT_BLOCK *)
0x140179eca  mov     r8b, 1; enum _NDIS_MDRV_REFTAG
0x140179ecd  xor     edx, edx; unsigned __int8
0x140179ecf  mov     rcx, rdi; struct _NDIS_M_DRIVER_BLOCK *
0x140179ed2  call    ?ndisDereferenceDriver@@YAXPEAU_NDIS_M_DRIVER_BLOCK@@EW4_NDIS_MDRV_REFTAG@@@Z; ndisDereferenceDriver(_NDIS_M_DRIVER_BLOCK *,uchar,_NDIS_MDRV_REFTAG)
0x140179ed7  lea     rax, [rsp+188h+var_138]
0x140179edc  mov     qword ptr [rsp+188h+DestinationString.Length], 1000000h
0x140179ee5  lea     rdx, ?ndisDosDevicesStr@@3U_UNICODE_STRING@@A; SourceString
0x140179eec  mov     [rsp+188h+DestinationString.Buffer], rax
0x140179ef1  lea     rcx, [rsp+188h+DestinationString]; DestinationString
0x140179ef6  call    cs:__imp_RtlCopyUnicodeString
0x140179efd  nop     dword ptr [rax+rax+00h]
0x140179f02  lea     rdx, [rbx+0ED0h]; Source
0x140179f09  lea     rcx, [rsp+188h+DestinationString]; Destination
0x140179f0e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140179f15  nop     dword ptr [rax+rax+00h]
0x140179f1a  test    eax, eax
0x140179f1c  jns     loc_140179FA7
0x140179f22  mov     rbp, [rsp+188h+arg_8]
0x140179f2a  cmp     r15b, 1
0x140179f2e  mov     r15, [rsp+188h+var_28]
0x140179f36  jz      loc_140179FC9
0x140179f3c  mov     r14, [rsp+188h+var_20]
0x140179f44  jmp     loc_140179D0C
0x140179f49  lea     rcx, [rdi+1A0h]; void *
0x140179f50  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x140179f55  mov     rax, gs:188h
0x140179f5e  mov     r15b, 1
0x140179f61  mov     [rdi+1D8h], rax
0x140179f68  jmp     loc_140179D87
0x140179f6d  mov     rbp, [rbp+8]
0x140179f71  test    rbp, rbp
0x140179f74  jnz     loc_140179DAB
0x140179f7a  jmp     loc_140179DB4
0x140179f7f  mov     eax, [rax+8]
0x140179f82  and     eax, 5
0x140179f85  cmp     al, 5
0x140179f87  jnz     loc_140179E92
0x140179f8d  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179f90  call    ?ndisIovTeardownVf@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIovTeardownVf(_NDIS_MINIPORT_BLOCK *)
0x140179f95  jmp     loc_140179E92
0x140179f9a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179f9d  call    ?ndisIMDeleteIfStackEntry@@YAJPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIMDeleteIfStackEntry(_NDIS_MINIPORT_BLOCK *)
0x140179fa2  jmp     loc_140179EB2
0x140179fa7  lea     rcx, [rsp+188h+DestinationString]; SymbolicLinkName
0x140179fac  call    cs:__imp_IoDeleteSymbolicLink
0x140179fb3  nop     dword ptr [rax+rax+00h]
0x140179fb8  jmp     loc_140179F22
0x140179fbd  mov     byte ptr [rbx+115Ch], 1
0x140179fc4  jmp     loc_140179F22
0x140179fc9  lea     rcx, [rdi+1A0h]; Mutex
0x140179fd0  mov     [rdi+1D8h], r14
0x140179fd7  xor     edx, edx; Wait
0x140179fd9  call    cs:__imp_KeReleaseMutex
0x140179fe0  nop     dword ptr [rax+rax+00h]
0x140179fe5  jmp     loc_140179F3C
0x140179fea  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140179fed  call    ?ndisPnPCompleteRemoveDevice@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisPnPCompleteRemoveDevice(_NDIS_MINIPORT_BLOCK *)
0x140179ff2  jmp     loc_140179D25
0x140179ff7  mov     rcx, cs:WPP_GLOBAL_Control
0x140179ffe  mov     r9d, 60h ; '`'; int
0x14017a004  mov     qword ptr [rsp+188h+var_160], rbx; char
0x14017a009  mov     r8d, 0Dh; int
0x14017a00f  mov     dl, 4; int
0x14017a011  mov     [rsp+188h+var_168], r13; struct _GUID *
0x14017a016  mov     rcx, [rcx+40h]; int
0x14017a01a  call    WPP_RECORDER_SF_q
0x14017a01f  jmp     loc_140179D46
0x140183724  mov     ecx, [rbp+38h]
0x140183727  movzx   eax, word ptr [rbx+0EE0h]
0x14018372e  add     rcx, rbp
0x140183731  mov     [rcx], ax
0x140183734  add     rcx, 2; void *
0x140183738  movzx   r8d, word ptr [rbx+0EE0h]; Size
0x140183740  mov     rdx, [rbx+0EE8h]; Src
0x140183747  call    memmove
0x14018374c  mov     rcx, rbp; WnodeEventItem
0x14018374f  call    cs:__imp_IoWMIWriteEvent
0x140183756  nop     dword ptr [rax+rax+00h]
0x14018375b  mov     r14d, eax
0x14018375e  test    eax, eax
0x140183760  jns     short loc_1401837D9
0x140183762  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140183769  jz      short loc_14018378E
0x14018376b  mov     rcx, cs:WPP_GLOBAL_Control
0x140183772  mov     r9d, 5Eh ; '^'; int
0x140183778  mov     r8d, 12h; int
0x14018377e  mov     [rsp+188h+var_168], r13; struct _GUID *
0x140183783  mov     dl, 2; int
0x140183785  mov     rcx, [rcx+40h]; int
0x140183789  call    WPP_RECORDER_SF_
0x14018378e  test    cs:byte_14011B001, 10h
0x140183795  jz      short loc_1401837C8
0x140183797  mov     rax, [rbx+0FB8h]
0x14018379e  lea     r8, [rbx+0FA8h]
0x1401837a5  mov     dword ptr [rsp+188h+var_158], r14d
0x1401837aa  lea     rdx, IndicateAdapterRemovalFailed
0x1401837b1  mov     qword ptr [rsp+188h+var_160], rax
0x1401837b6  mov     r9, r8
0x1401837b9  mov     eax, [rbx+0FD8h]
0x1401837bf  mov     dword ptr [rsp+188h+var_168], eax
0x1401837c3  call    McTemplateK0jqxd_EtwWriteTransfer
0x1401837c8  xor     edx, edx; Tag
0x1401837ca  mov     rcx, rbp; P
0x1401837cd  call    cs:__imp_ExFreePoolWithTag
0x1401837d4  nop     dword ptr [rax+rax+00h]
0x1401837d9  xor     r14d, r14d
0x1401837dc  jmp     loc_140179E3D
0x1401837e1  xor     edx, edx; Val
0x1401837e3  lea     rcx, [rsp+188h+var_138]; void *
0x1401837e8  mov     r8d, 0A0h; Size
0x1401837ee  call    memset
0x1401837f3  cmp     cs:byte_14011CAD3, 4
0x1401837fa  jb      loc_140179E65
0x140183800  lea     rdx, [rsp+188h+var_138]; struct NDIS_PNPTRACE_LOCALS *
0x140183805  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140183808  call    ?ndisGetBindLinkNameForTracing@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAUNDIS_PNPTRACE_LOCALS@@@Z; ndisGetBindLinkNameForTracing(_NDIS_MINIPORT_BLOCK *,NDIS_PNPTRACE_LOCALS *)
0x14018380d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x140183814  jz      loc_140179E65
0x14018381a  mov     rax, qword ptr [rsp+188h+var_138]
0x14018381f  mov     r9d, 5Fh ; '_'; int
0x140183825  mov     rcx, cs:WPP_GLOBAL_Control
0x14018382c  mov     r8d, 1Ch; int
0x140183832  mov     qword ptr [rsp+188h+var_158], rax; char
0x140183837  mov     rax, [rsp+188h+var_130]
0x14018383c  mov     qword ptr [rsp+188h+var_160], rax; __int64
0x140183841  mov     rcx, [rcx+40h]; int
0x140183845  mov     [rsp+188h+var_168], r13; struct _GUID *
0x14018384a  call    WPP_RECORDER_SF_Zq
0x14018384f  nop
0x140183850  jmp     loc_140179E65
```
