# ndisSetSystemPower(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)

- ea: `0x1400ab504`
- end: `0x1400aba2f`
- name: `?ndisSetSystemPower@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `1323`
- prototype: `__int64 __fastcall(PVOID Context, struct _IO_STACK_LOCATION *, struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005f440`

## callees

- `0x1400110b0`
- `0x1400114b0`
- `0x14001d040`
- `0x1400416b0`
- `0x140044e80`
- `0x140045f10`
- `0x140052740`
- `0x14006d260`
- `0x140076810`
- `0x1400886c0`
- `0x1400887c0`
- `0x140088a2c`
- `0x1400ab370`
- `0x1400ab504`
- `0x14015bd60`
- `0x14015d480`
- `0x14017a630`
- `0x14017d8f0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400ab5d9`
- `ntoskrnl!IofCallDriver` at `0x1400ab70d`
- `ntoskrnl!IofCallDriver` at `0x1400aba00`
- `ntoskrnl!IofCallDriver` at `0x1400ab5d9`
- `ntoskrnl!IofCallDriver` at `0x1400ab70d`
- `ntoskrnl!IofCallDriver` at `0x1400aba00`
- `ntoskrnl!IofCompleteRequest` at `0x1400ab787`
- `ntoskrnl!IofCompleteRequest` at `0x1400ab787`
- `ntoskrnl!KeClearEvent` at `0x1400ab829`
- `ntoskrnl!KeClearEvent` at `0x1400ab829`

## pseudocode

```c
NTSTATUS __fastcall ndisSetSystemPower(IRP *Context, struct _IO_STACK_LOCATION *a2, struct _NDIS_MINIPORT_BLOCK *a3)
{
  __int64 v6; // r8
  enum _SYSTEM_POWER_STATE SystemState; // r15d
  enum Ndis::ReadBindingsOptions::Flags *v8; // rdx
  int v10; // r14d
  __int64 v11; // rcx
  int v12; // edx
  __int64 v13; // rcx
  POWER_STATE v14; // ebx
  int v15; // eax
  struct _DEVICE_OBJECT *PhysicalDeviceObject; // rcx
  int v17; // edx
  __int64 v18; // rcx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  _IO_STACK_LOCATION *v20; // rax
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+40h] [rbp-10h] BYREF
  POWER_STATE PowerState; // [rsp+88h] [rbp+38h] BYREF

  if ( MINIPORT_TEST_FLAG(a3, 0x80u) )
    NT_ASSERT("(!(MINIPORT_TEST_FLAG(Miniport, 0x00000080)))");
  SystemState = a2->Parameters.Power.State.SystemState;
  *(_DWORD *)(v6 + 1332) = SystemState;
  PowerState.SystemState = PowerSystemUnspecified;
  HIDWORD(IoStatus.Pointer) = 0;
  v8 = &WPP_RECORDER_INITIALIZED;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_LqZ(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)&WPP_RECORDER_INITIALIZED,
      (int)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      95,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      SystemState,
      (char)a3,
      (__int64)a3->pAdapterInstanceName);
    v8 = &WPP_RECORDER_INITIALIZED;
  }
  if ( a3->State != NdisMiniportHalted || a3->PnPDeviceState == NdisPnPDeviceStarted )
  {
    v10 = 0;
    if ( SystemState == PowerSystemWorking )
    {
      if ( (a3->PnPFlags & 0x800) == 0 )
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v8) = 3;
          WPP_RECORDER_SF_q(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            (int)v8,
            14,
            97,
            (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
            (char)a3);
        }
        ndisPowerSaveStop(a3, 6);
      }
      ndisMPowerPolicy(
        a3,
        PowerSystemWorking,
        (enum _SYSTEM_POWER_STATE)((a2->Parameters.Read.Length >> 8) & 0xF),
        (enum _DEVICE_POWER_STATE *)&PowerState,
        0);
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v17,
          14,
          98,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)a3);
      }
      if ( (byte_140121003 & 4) != 0 )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))McTemplateK0jqxqq_EtwWriteTransfer)(
          v18,
          MiniportPowerStates,
          &a3->InterfaceGuid,
          &a3->InterfaceGuid,
          a3->IfIndex,
          (_NET_LUID_LH)a3->NetLuid.Value,
          1,
          (POWER_STATE)PowerState.SystemState);
      CurrentStackLocation = Context->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
      *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)&CurrentStackLocation[-1].Parameters.ReadWriteConfig.Length = *(_OWORD *)&CurrentStackLocation->Parameters.ReadWriteConfig.Length;
      CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
      CurrentStackLocation[-1].Control = 0;
      v20 = Context->Tail.Overlay.CurrentStackLocation;
      v20[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ndisSetSystemPowerOnComplete;
      v20[-1].Context = a3;
      v20[-1].Control = -32;
      Context->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      IofCallDriver(a3->NextDeviceObject, Context);
      return 259;
    }
    else if ( SystemState == PowerSystemSleeping1
           || SystemState == PowerSystemSleeping2
           || SystemState == PowerSystemSleeping3
           || (v11 = (unsigned int)(SystemState - 5), SystemState == PowerSystemHibernate) )
    {
      ndisWaitForKernelObject(&a3->PowerD0CompleteEvent);
      ndisPowerSaveStop(a3, 6);
      ndisInvokeMiniportSysPowerNotify(
        a3,
        (enum _SYSTEM_POWER_STATE)((a2->Parameters.Read.Length >> 8) & 0xF),
        (enum _SYSTEM_POWER_STATE)((unsigned __int16)a2->Parameters.Read.Length >> 12));
      if ( (unsigned int)ndisMPowerPolicy(
                           a3,
                           SystemState,
                           (enum _SYSTEM_POWER_STATE)((a2->Parameters.Read.Length >> 8) & 0xF),
                           (enum _DEVICE_POWER_STATE *)&PowerState,
                           0) == -2147483633 )
      {
        Context->IoStatus.Status = 0;
        IofCompleteRequest(Context, 0);
      }
      else
      {
        if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 4;
          WPP_RECORDER_SF_qDD(
            *((_QWORD *)WPP_GLOBAL_Control + 8),
            v12,
            14,
            99,
            (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
            (char)a3,
            SystemState,
            PowerState.SystemState);
        }
        if ( (byte_140121003 & 4) != 0 )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))McTemplateK0jqxqq_EtwWriteTransfer)(
            v13,
            MiniportPowerStates,
            &a3->InterfaceGuid,
            &a3->InterfaceGuid,
            a3->IfIndex,
            (_NET_LUID_LH)a3->NetLuid.Value,
            SystemState,
            (POWER_STATE)PowerState.SystemState);
        KeClearEvent(&a3->OpenReadyEvent.Event);
        ndisCancelInitModeTimeoutTimer(a3, 1u);
        ndisPrepForLowPower(a3, (enum _NDIS_DEVICE_POWER_STATE)PowerState.SystemState);
        v14.SystemState = PowerState.SystemState;
        Context->Tail.Overlay.CurrentStackLocation[-1].DeviceObject = a3->DeviceObject;
        Context->Tail.Overlay.CurrentStackLocation->Control |= 1u;
        v15 = ndisRequestDeviceLowPower(
                a3,
                PowerState,
                ndisRequestedDevicePowerIrpComplete,
                Context,
                NdisMEventDx_SystemSleep);
        v10 = 259;
        if ( v15 != 259 )
        {
          PhysicalDeviceObject = a3->PhysicalDeviceObject;
          IoStatus.Status = v15;
          IoStatus.Information = 0;
          ndisRequestedDevicePowerIrpComplete(PhysicalDeviceObject, 2u, v14, Context, &IoStatus);
        }
      }
    }
    else if ( SystemState == PowerSystemShutdown )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v8) = 4;
        WPP_RECORDER_SF_qL(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          (int)v8,
          14,
          96,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)a3,
          6);
      }
      if ( (byte_140121003 & 4) != 0 )
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))McTemplateK0jqxqq_EtwWriteTransfer)(
          v11,
          MiniportPowerSystemState,
          &a3->InterfaceGuid,
          &a3->InterfaceGuid,
          a3->IfIndex,
          (_NET_LUID_LH)a3->NetLuid.Value,
          0,
          6);
      ndisSendSystemPowerStateIndication(a3, PowerSystemShutdown);
      if ( !ndisAllowWakeFromS5 )
        ndisCancelWaitWake(a3);
      ndisPowerSaveStop(a3, 6);
      ndisInvokeMiniportSysPowerNotify(
        a3,
        (enum _SYSTEM_POWER_STATE)((a2->Parameters.Read.Length >> 8) & 0xF),
        (enum _SYSTEM_POWER_STATE)((unsigned __int16)a2->Parameters.Read.Length >> 12));
      if ( (a3->DriverHandle->Flags & 1) == 0 )
        ndisMShutdownMiniport(a3);
      ++Context->CurrentLocation;
      ++Context->Tail.Overlay.CurrentStackLocation;
      Context->IoStatus.Status = 0;
      return IofCallDriver(a3->NextDeviceObject, Context);
    }
    return v10;
  }
  else
  {
    ++Context->CurrentLocation;
    ++Context->Tail.Overlay.CurrentStackLocation;
    Context->IoStatus.Status = 0;
    return IofCallDriver(a3->NextDeviceObject, Context);
  }
}

```

## disassembly

```asm
0x1400ab504  mov     [rsp-28h+arg_0], rbx
0x1400ab509  mov     [rsp-28h+arg_10], rsi
0x1400ab50e  push    rbp
0x1400ab50f  push    rdi
0x1400ab510  push    r13
0x1400ab512  push    r14
0x1400ab514  push    r15
0x1400ab516  mov     rbp, rsp
0x1400ab519  sub     rsp, 50h
0x1400ab51d  mov     r13, rdx
0x1400ab520  mov     rsi, rcx
0x1400ab523  mov     edx, 80h; unsigned int
0x1400ab528  mov     rcx, r8; struct _NDIS_MINIPORT_BLOCK *
0x1400ab52b  mov     rdi, r8
0x1400ab52e  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400ab533  test    al, al
0x1400ab535  jz      short loc_1400AB539
0x1400ab537  int     2Ch; NT_ASSERT("(!(MINIPORT_TEST_FLAG(Miniport, 0x00000080)))")
0x1400ab539  mov     r15d, [r13+18h]
0x1400ab53d  mov     [r8+534h], r15d
0x1400ab544  mov     dword ptr [rbp+PowerState], 0
0x1400ab54b  mov     dword ptr [rbp+var_10.___u0+4], 0
0x1400ab552  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400ab559  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400ab560  lea     r8, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids; int
0x1400ab567  jz      short loc_1400AB5A8
0x1400ab569  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab570  mov     r9d, 5Fh ; '_'; int
0x1400ab576  mov     rax, [rdi+0F10h]
0x1400ab57d  mov     qword ptr [rsp+50h+var_18], rax; __int64
0x1400ab582  mov     qword ptr [rsp+50h+var_20], rdi; char
0x1400ab587  mov     rcx, [rcx+40h]; int
0x1400ab58b  mov     dword ptr [rsp+50h+var_28], r15d; char
0x1400ab590  mov     [rsp+50h+IoStatus], r8; struct _GUID *
0x1400ab595  call    WPP_RECORDER_SF_LqZ
0x1400ab59a  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400ab5a1  lea     r8, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1400ab5a8  mov     ebx, 1
0x1400ab5ad  cmp     [rdi+8C8h], ebx
0x1400ab5b3  jnz     short loc_1400AB5EA
0x1400ab5b5  cmp     [rdi+5F0h], ebx
0x1400ab5bb  jz      short loc_1400AB5EA
0x1400ab5bd  add     [rsi+43h], bl
0x1400ab5c0  mov     rdx, rsi; Irp
0x1400ab5c3  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x1400ab5cb  mov     dword ptr [rsi+30h], 0
0x1400ab5d2  mov     rcx, [rdi+0F00h]; DeviceObject
0x1400ab5d9  call    cs:__imp_IofCallDriver
0x1400ab5e0  nop     dword ptr [rax+rax+00h]
0x1400ab5e5  jmp     loc_1400ABA15
0x1400ab5ea  xor     r14d, r14d
0x1400ab5ed  mov     ecx, r15d
0x1400ab5f0  sub     ecx, ebx
0x1400ab5f2  jz      loc_1400AB8C5
0x1400ab5f8  sub     ecx, ebx
0x1400ab5fa  jz      loc_1400AB721
0x1400ab600  sub     ecx, ebx
0x1400ab602  jz      loc_1400AB721
0x1400ab608  sub     ecx, ebx
0x1400ab60a  jz      loc_1400AB721
0x1400ab610  sub     ecx, ebx
0x1400ab612  jz      loc_1400AB721
0x1400ab618  cmp     ecx, ebx
0x1400ab61a  jnz     loc_1400ABA12
0x1400ab620  cmp     cs:WPP_RECORDER_INITIALIZED, rdx; __annotation("TMF:",
0x1400ab627  lea     ebx, [r14+6]
0x1400ab62b  jz      short loc_1400AB655
0x1400ab62d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab634  lea     r9d, [r14+60h]; int
0x1400ab638  mov     dword ptr [rsp+50h+var_20], ebx; char
0x1400ab63c  mov     dl, 4; int
0x1400ab63e  mov     qword ptr [rsp+50h+var_28], rdi; char
0x1400ab643  mov     [rsp+50h+IoStatus], r8; struct _GUID *
0x1400ab648  lea     r8d, [r14+0Eh]; int
0x1400ab64c  mov     rcx, [rcx+40h]; int
0x1400ab650  call    WPP_RECORDER_SF_qL
0x1400ab655  test    cs:byte_140121003, 4
0x1400ab65c  jz      short loc_1400AB693
0x1400ab65e  mov     rax, [rdi+0FB8h]
0x1400ab665  lea     r8, [rdi+0FA8h]
0x1400ab66c  mov     dword ptr [rsp+50h+var_18], ebx
0x1400ab670  lea     rdx, MiniportPowerSystemState
0x1400ab677  mov     dword ptr [rsp+50h+var_20], r14d
0x1400ab67c  mov     r9, r8
0x1400ab67f  mov     qword ptr [rsp+50h+var_28], rax
0x1400ab684  mov     eax, [rdi+0FD8h]
0x1400ab68a  mov     dword ptr [rsp+50h+IoStatus], eax
0x1400ab68e  call    McTemplateK0jqxqq_EtwWriteTransfer
0x1400ab693  mov     edx, ebx; enum _SYSTEM_POWER_STATE
0x1400ab695  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab698  call    ?ndisSendSystemPowerStateIndication@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@@Z; ndisSendSystemPowerStateIndication(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE)
0x1400ab69d  cmp     cs:?ndisAllowWakeFromS5@@3EA, r14b; uchar ndisAllowWakeFromS5
0x1400ab6a4  jnz     short loc_1400AB6AE
0x1400ab6a6  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab6a9  call    ?ndisCancelWaitWake@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisCancelWaitWake(_NDIS_MINIPORT_BLOCK *)
0x1400ab6ae  mov     edx, ebx
0x1400ab6b0  mov     rcx, rdi
0x1400ab6b3  call    ?ndisPowerSaveStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisPowerSaveStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x1400ab6b8  mov     edx, [r13+8]
0x1400ab6bc  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab6bf  mov     r8d, edx
0x1400ab6c2  shr     edx, 8
0x1400ab6c5  shr     r8d, 0Ch
0x1400ab6c9  and     edx, 0Fh; enum _SYSTEM_POWER_STATE
0x1400ab6cc  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x1400ab6d0  call    ?ndisInvokeMiniportSysPowerNotify@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1@Z; ndisInvokeMiniportSysPowerNotify(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE)
0x1400ab6d5  mov     rax, [rdi+0EB0h]
0x1400ab6dc  mov     r14d, 1
0x1400ab6e2  test    [rax+1Ah], r14b
0x1400ab6e6  jnz     short loc_1400AB6F0
0x1400ab6e8  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab6eb  call    ?ndisMShutdownMiniport@@_Y2PAGENPNP@@AJPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMShutdownMiniport(_NDIS_MINIPORT_BLOCK *)
0x1400ab6f0  add     [rsi+43h], r14b
0x1400ab6f4  mov     rdx, rsi; Irp
0x1400ab6f7  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x1400ab6ff  mov     dword ptr [rsi+30h], 0
0x1400ab706  mov     rcx, [rdi+0F00h]; DeviceObject
0x1400ab70d  call    cs:__imp_IofCallDriver
0x1400ab714  nop     dword ptr [rax+rax+00h]
0x1400ab719  mov     r14d, eax
0x1400ab71c  jmp     loc_1400ABA12
0x1400ab721  lea     rcx, [rdi+1078h]; void *
0x1400ab728  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x1400ab72d  mov     edx, 6
0x1400ab732  mov     rcx, rdi
0x1400ab735  call    ?ndisPowerSaveStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisPowerSaveStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x1400ab73a  mov     edx, [r13+8]
0x1400ab73e  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab741  mov     r8d, edx
0x1400ab744  shr     edx, 8
0x1400ab747  shr     r8d, 0Ch
0x1400ab74b  and     edx, 0Fh; enum _SYSTEM_POWER_STATE
0x1400ab74e  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x1400ab752  call    ?ndisInvokeMiniportSysPowerNotify@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1@Z; ndisInvokeMiniportSysPowerNotify(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE)
0x1400ab757  mov     r8d, [r13+8]
0x1400ab75b  lea     r9, [rbp+PowerState]; enum _DEVICE_POWER_STATE *
0x1400ab75f  shr     r8d, 8
0x1400ab763  mov     edx, r15d; enum _SYSTEM_POWER_STATE
0x1400ab766  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x1400ab76a  mov     byte ptr [rsp+50h+IoStatus], r14b; unsigned __int8
0x1400ab76f  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab772  call    ?ndisMPowerPolicy@@_Y2PAGENPNP@@AJPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1PEAW4_DEVICE_POWER_STATE@@E@Z; ndisMPowerPolicy(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE,_DEVICE_POWER_STATE *,uchar)
0x1400ab777  cmp     eax, 8000000Fh
0x1400ab77c  jnz     short loc_1400AB798
0x1400ab77e  xor     edx, edx; PriorityBoost
0x1400ab780  mov     [rsi+30h], r14d
0x1400ab784  mov     rcx, rsi; Irp
0x1400ab787  call    cs:__imp_IofCompleteRequest
0x1400ab78e  nop     dword ptr [rax+rax+00h]
0x1400ab793  jmp     loc_1400ABA12
0x1400ab798  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400ab79f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ab7a6  jz      short loc_1400AB7E1
0x1400ab7a8  mov     eax, dword ptr [rbp+PowerState]
0x1400ab7ab  mov     r9d, 63h ; 'c'; int
0x1400ab7b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab7b8  mov     dl, 4; int
0x1400ab7ba  mov     dword ptr [rsp+50h+var_18], eax; char
0x1400ab7be  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1400ab7c5  mov     dword ptr [rsp+50h+var_20], r15d; char
0x1400ab7ca  lea     r8d, [r9-55h]; int
0x1400ab7ce  mov     qword ptr [rsp+50h+var_28], rdi; char
0x1400ab7d3  mov     rcx, [rcx+40h]; int
0x1400ab7d7  mov     [rsp+50h+IoStatus], rax; struct _GUID *
0x1400ab7dc  call    WPP_RECORDER_SF_qDD
0x1400ab7e1  test    cs:byte_140121003, 4
0x1400ab7e8  jz      short loc_1400AB822
0x1400ab7ea  mov     eax, dword ptr [rbp+PowerState]
0x1400ab7ed  lea     r8, [rdi+0FA8h]
0x1400ab7f4  mov     dword ptr [rsp+50h+var_18], eax
0x1400ab7f8  lea     rdx, MiniportPowerStates
0x1400ab7ff  mov     rax, [rdi+0FB8h]
0x1400ab806  mov     r9, r8
0x1400ab809  mov     dword ptr [rsp+50h+var_20], r15d
0x1400ab80e  mov     qword ptr [rsp+50h+var_28], rax
0x1400ab813  mov     eax, [rdi+0FD8h]
0x1400ab819  mov     dword ptr [rsp+50h+IoStatus], eax
0x1400ab81d  call    McTemplateK0jqxqq_EtwWriteTransfer
0x1400ab822  lea     rcx, [rdi+0E90h]; Event
0x1400ab829  call    cs:__imp_KeClearEvent
0x1400ab830  nop     dword ptr [rax+rax+00h]
0x1400ab835  mov     r14d, ebx
0x1400ab838  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab83b  mov     dl, r14b; unsigned __int8
0x1400ab83e  call    ?ndisCancelInitModeTimeoutTimer@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisCancelInitModeTimeoutTimer(_NDIS_MINIPORT_BLOCK *,uchar)
0x1400ab843  mov     edx, dword ptr [rbp+PowerState]; enum _NDIS_DEVICE_POWER_STATE
0x1400ab846  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab849  call    ?ndisPrepForLowPower@@YAJPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; ndisPrepForLowPower(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x1400ab84e  mov     rcx, [rsi+0B8h]
0x1400ab855  lea     r8, ?ndisRequestedDevicePowerIrpComplete@@YAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAXPEAU_IO_STATUS_BLOCK@@@Z; CompletionFunction
0x1400ab85c  mov     rax, [rdi+0EF0h]
0x1400ab863  mov     r9, rsi; Context
0x1400ab866  mov     ebx, dword ptr [rbp+PowerState]
0x1400ab869  mov     word ptr [rsp+50h+IoStatus], r14w; enum _NDIS_MINIPORT_EVENT
0x1400ab86f  mov     [rcx-20h], rax
0x1400ab873  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab876  mov     rax, [rsi+0B8h]
0x1400ab87d  or      [rax+3], r14b
0x1400ab881  mov     edx, dword ptr [rbp+PowerState]; PowerState
0x1400ab884  call    ?ndisRequestDeviceLowPower@@YAJPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@P6AXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAXPEAU_IO_STATUS_BLOCK@@@Z4W4_NDIS_MINIPORT_EVENT@@@Z; ndisRequestDeviceLowPower(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,void (*)(_DEVICE_OBJECT *,uchar,_POWER_STATE,void *,_IO_STATUS_BLOCK *),void *,_NDIS_MINIPORT_EVENT)
0x1400ab889  mov     r14d, 103h
0x1400ab88f  cmp     eax, r14d
0x1400ab892  jz      loc_1400ABA12
0x1400ab898  mov     rcx, [rdi+0EF8h]; DeviceObject
0x1400ab89f  mov     r9, rsi; Context
0x1400ab8a2  mov     dword ptr [rbp+var_10.___u0], eax
0x1400ab8a5  mov     r8d, ebx; PowerState
0x1400ab8a8  lea     rax, [rbp+var_10]
0x1400ab8ac  mov     [rbp+var_10.Information], 0
0x1400ab8b4  mov     dl, 2; MinorFunction
0x1400ab8b6  mov     [rsp+50h+IoStatus], rax; IoStatus
0x1400ab8bb  call    ?ndisRequestedDevicePowerIrpComplete@@YAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAXPEAU_IO_STATUS_BLOCK@@@Z; ndisRequestedDevicePowerIrpComplete(_DEVICE_OBJECT *,uchar,_POWER_STATE,void *,_IO_STATUS_BLOCK *)
0x1400ab8c0  jmp     loc_1400ABA12
0x1400ab8c5  test    dword ptr [rdi+7Ch], 800h
0x1400ab8cc  jnz     short loc_1400AB90A
0x1400ab8ce  cmp     cs:WPP_RECORDER_INITIALIZED, rdx; __annotation("TMF:",
0x1400ab8d5  jz      short loc_1400AB8FD
0x1400ab8d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab8de  mov     r9d, 61h ; 'a'; int
0x1400ab8e4  mov     qword ptr [rsp+50h+var_28], rdi; char
0x1400ab8e9  mov     dl, 3; int
0x1400ab8eb  mov     [rsp+50h+IoStatus], r8; struct _GUID *
0x1400ab8f0  mov     rcx, [rcx+40h]; int
0x1400ab8f4  lea     r8d, [r9-53h]; int
0x1400ab8f8  call    WPP_RECORDER_SF_q
0x1400ab8fd  mov     edx, 6
0x1400ab902  mov     rcx, rdi
0x1400ab905  call    ?ndisPowerSaveStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisPowerSaveStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x1400ab90a  mov     r8d, [r13+8]
0x1400ab90e  lea     r9, [rbp+PowerState]; enum _DEVICE_POWER_STATE *
0x1400ab912  shr     r8d, 8
0x1400ab916  mov     edx, ebx; enum _SYSTEM_POWER_STATE
0x1400ab918  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x1400ab91c  mov     byte ptr [rsp+50h+IoStatus], r14b; unsigned __int8
0x1400ab921  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400ab924  call    ?ndisMPowerPolicy@@_Y2PAGENPNP@@AJPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1PEAW4_DEVICE_POWER_STATE@@E@Z; ndisMPowerPolicy(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE,_DEVICE_POWER_STATE *,uchar)
0x1400ab929  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400ab930  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400ab937  jz      short loc_1400AB966
0x1400ab939  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ab940  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1400ab947  mov     r9d, 62h ; 'b'; int
0x1400ab94d  mov     qword ptr [rsp+50h+var_28], rdi; char
0x1400ab952  mov     dl, 4; int
0x1400ab954  mov     [rsp+50h+IoStatus], rax; struct _GUID *
0x1400ab959  mov     rcx, [rcx+40h]; int
0x1400ab95d  lea     r8d, [r9-54h]; int
0x1400ab961  call    WPP_RECORDER_SF_q
0x1400ab966  test    cs:byte_140121003, 4
0x1400ab96d  jz      short loc_1400AB9A6
0x1400ab96f  mov     eax, dword ptr [rbp+PowerState]
0x1400ab972  lea     r8, [rdi+0FA8h]
0x1400ab979  mov     dword ptr [rsp+50h+var_18], eax
0x1400ab97d  lea     rdx, MiniportPowerStates
0x1400ab984  mov     rax, [rdi+0FB8h]
0x1400ab98b  mov     r9, r8
0x1400ab98e  mov     dword ptr [rsp+50h+var_20], ebx
0x1400ab992  mov     qword ptr [rsp+50h+var_28], rax
0x1400ab997  mov     eax, [rdi+0FD8h]
0x1400ab99d  mov     dword ptr [rsp+50h+IoStatus], eax
0x1400ab9a1  call    McTemplateK0jqxqq_EtwWriteTransfer
0x1400ab9a6  mov     rax, [rsi+0B8h]
0x1400ab9ad  lea     rcx, ?ndisSetSystemPowerOnComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisSetSystemPowerOnComplete(_DEVICE_OBJECT *,_IRP *,void *)
0x1400ab9b4  mov     rdx, rsi; Irp
0x1400ab9b7  movups  xmm0, xmmword ptr [rax]
0x1400ab9ba  movups  xmmword ptr [rax-48h], xmm0
0x1400ab9be  movups  xmm1, xmmword ptr [rax+10h]
0x1400ab9c2  movups  xmmword ptr [rax-38h], xmm1
0x1400ab9c6  movups  xmm0, xmmword ptr [rax+20h]
0x1400ab9ca  movups  xmmword ptr [rax-28h], xmm0
0x1400ab9ce  movsd   xmm1, qword ptr [rax+30h]
0x1400ab9d3  movsd   qword ptr [rax-18h], xmm1
0x1400ab9d8  mov     [rax-45h], r14b
0x1400ab9dc  mov     rax, [rsi+0B8h]
0x1400ab9e3  mov     [rax-10h], rcx
0x1400ab9e7  mov     [rax-8], rdi
0x1400ab9eb  mov     byte ptr [rax-45h], 0E0h
0x1400ab9ef  mov     rax, [rsi+0B8h]
0x1400ab9f6  or      [rax+3], bl
0x1400ab9f9  mov     rcx, [rdi+0F00h]; DeviceObject
0x1400aba00  call    cs:__imp_IofCallDriver
0x1400aba07  nop     dword ptr [rax+rax+00h]
0x1400aba0c  mov     r14d, 103h
0x1400aba12  mov     eax, r14d
0x1400aba15  lea     r11, [rsp+50h+var_s0]
0x1400aba1a  mov     rbx, [r11+30h]
0x1400aba1e  mov     rsi, [r11+40h]
0x1400aba22  mov     rsp, r11
0x1400aba25  pop     r15
0x1400aba27  pop     r14
0x1400aba29  pop     r13
0x1400aba2b  pop     rdi
0x1400aba2c  pop     rbp
0x1400aba2d  retn
```
