# ndisSetSystemPower(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)

- ea: `0x1400a60c4`
- end: `0x1400a65ef`
- name: `?ndisSetSystemPower@@YAJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `1323`
- prototype: `__int64 __fastcall(PVOID Context, struct _IO_STACK_LOCATION *, struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005ae50`

## callees

- `0x14001cf50`
- `0x14001d350`
- `0x140028ee0`
- `0x14003a010`
- `0x14003ef00`
- `0x140043030`
- `0x140067680`
- `0x140070dc0`
- `0x14007f7c0`
- `0x140083440`
- `0x140083540`
- `0x1400837ac`
- `0x1400a5f30`
- `0x1400a60c4`
- `0x140154dc0`
- `0x1401564e0`
- `0x140174630`
- `0x140177920`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x1400a6199`
- `ntoskrnl!IofCallDriver` at `0x1400a62cd`
- `ntoskrnl!IofCallDriver` at `0x1400a65c0`
- `ntoskrnl!IofCallDriver` at `0x1400a6199`
- `ntoskrnl!IofCallDriver` at `0x1400a62cd`
- `ntoskrnl!IofCallDriver` at `0x1400a65c0`
- `ntoskrnl!IofCompleteRequest` at `0x1400a6347`
- `ntoskrnl!IofCompleteRequest` at `0x1400a6347`
- `ntoskrnl!KeClearEvent` at `0x1400a63e9`
- `ntoskrnl!KeClearEvent` at `0x1400a63e9`

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
      if ( (byte_14011B003 & 4) != 0 )
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
        if ( (byte_14011B003 & 4) != 0 )
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
      if ( (byte_14011B003 & 4) != 0 )
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
0x1400a60c4  mov     [rsp-28h+arg_0], rbx
0x1400a60c9  mov     [rsp-28h+arg_10], rsi
0x1400a60ce  push    rbp
0x1400a60cf  push    rdi
0x1400a60d0  push    r13
0x1400a60d2  push    r14
0x1400a60d4  push    r15
0x1400a60d6  mov     rbp, rsp
0x1400a60d9  sub     rsp, 50h
0x1400a60dd  mov     r13, rdx
0x1400a60e0  mov     rsi, rcx
0x1400a60e3  mov     edx, 80h; unsigned int
0x1400a60e8  mov     rcx, r8; struct _NDIS_MINIPORT_BLOCK *
0x1400a60eb  mov     rdi, r8
0x1400a60ee  call    ?MINIPORT_TEST_FLAG@@YAEPEBU_NDIS_MINIPORT_BLOCK@@K@Z; MINIPORT_TEST_FLAG(_NDIS_MINIPORT_BLOCK const *,ulong)
0x1400a60f3  test    al, al
0x1400a60f5  jz      short loc_1400A60F9
0x1400a60f7  int     2Ch; NT_ASSERT("(!(MINIPORT_TEST_FLAG(Miniport, 0x00000080)))")
0x1400a60f9  mov     r15d, [r13+18h]
0x1400a60fd  mov     [r8+534h], r15d
0x1400a6104  mov     dword ptr [rbp+PowerState], 0
0x1400a610b  mov     dword ptr [rbp+var_10.___u0+4], 0
0x1400a6112  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a6119  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x1400a6120  lea     r8, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids; int
0x1400a6127  jz      short loc_1400A6168
0x1400a6129  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6130  mov     r9d, 5Fh ; '_'; int
0x1400a6136  mov     rax, [rdi+0F10h]
0x1400a613d  mov     qword ptr [rsp+50h+var_18], rax; __int64
0x1400a6142  mov     qword ptr [rsp+50h+var_20], rdi; char
0x1400a6147  mov     rcx, [rcx+40h]; int
0x1400a614b  mov     dword ptr [rsp+50h+var_28], r15d; char
0x1400a6150  mov     [rsp+50h+IoStatus], r8; struct _GUID *
0x1400a6155  call    WPP_RECORDER_SF_LqZ
0x1400a615a  lea     rdx, WPP_RECORDER_INITIALIZED
0x1400a6161  lea     r8, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1400a6168  mov     ebx, 1
0x1400a616d  cmp     [rdi+8C8h], ebx
0x1400a6173  jnz     short loc_1400A61AA
0x1400a6175  cmp     [rdi+5F0h], ebx
0x1400a617b  jz      short loc_1400A61AA
0x1400a617d  add     [rsi+43h], bl
0x1400a6180  mov     rdx, rsi; Irp
0x1400a6183  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x1400a618b  mov     dword ptr [rsi+30h], 0
0x1400a6192  mov     rcx, [rdi+0F00h]; DeviceObject
0x1400a6199  call    cs:__imp_IofCallDriver
0x1400a61a0  nop     dword ptr [rax+rax+00h]
0x1400a61a5  jmp     loc_1400A65D5
0x1400a61aa  xor     r14d, r14d
0x1400a61ad  mov     ecx, r15d
0x1400a61b0  sub     ecx, ebx
0x1400a61b2  jz      loc_1400A6485
0x1400a61b8  sub     ecx, ebx
0x1400a61ba  jz      loc_1400A62E1
0x1400a61c0  sub     ecx, ebx
0x1400a61c2  jz      loc_1400A62E1
0x1400a61c8  sub     ecx, ebx
0x1400a61ca  jz      loc_1400A62E1
0x1400a61d0  sub     ecx, ebx
0x1400a61d2  jz      loc_1400A62E1
0x1400a61d8  cmp     ecx, ebx
0x1400a61da  jnz     loc_1400A65D2
0x1400a61e0  cmp     cs:WPP_RECORDER_INITIALIZED, rdx; __annotation("TMF:",
0x1400a61e7  lea     ebx, [r14+6]
0x1400a61eb  jz      short loc_1400A6215
0x1400a61ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a61f4  lea     r9d, [r14+60h]; int
0x1400a61f8  mov     dword ptr [rsp+50h+var_20], ebx; char
0x1400a61fc  mov     dl, 4; int
0x1400a61fe  mov     qword ptr [rsp+50h+var_28], rdi; char
0x1400a6203  mov     [rsp+50h+IoStatus], r8; struct _GUID *
0x1400a6208  lea     r8d, [r14+0Eh]; int
0x1400a620c  mov     rcx, [rcx+40h]; int
0x1400a6210  call    WPP_RECORDER_SF_qL
0x1400a6215  test    cs:byte_14011B003, 4
0x1400a621c  jz      short loc_1400A6253
0x1400a621e  mov     rax, [rdi+0FB8h]
0x1400a6225  lea     r8, [rdi+0FA8h]
0x1400a622c  mov     dword ptr [rsp+50h+var_18], ebx
0x1400a6230  lea     rdx, MiniportPowerSystemState
0x1400a6237  mov     dword ptr [rsp+50h+var_20], r14d
0x1400a623c  mov     r9, r8
0x1400a623f  mov     qword ptr [rsp+50h+var_28], rax
0x1400a6244  mov     eax, [rdi+0FD8h]
0x1400a624a  mov     dword ptr [rsp+50h+IoStatus], eax
0x1400a624e  call    McTemplateK0jqxqq_EtwWriteTransfer
0x1400a6253  mov     edx, ebx; enum _SYSTEM_POWER_STATE
0x1400a6255  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a6258  call    ?ndisSendSystemPowerStateIndication@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@@Z; ndisSendSystemPowerStateIndication(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE)
0x1400a625d  cmp     cs:?ndisAllowWakeFromS5@@3EA, r14b; uchar ndisAllowWakeFromS5
0x1400a6264  jnz     short loc_1400A626E
0x1400a6266  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a6269  call    ?ndisCancelWaitWake@@YAXPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisCancelWaitWake(_NDIS_MINIPORT_BLOCK *)
0x1400a626e  mov     edx, ebx
0x1400a6270  mov     rcx, rdi
0x1400a6273  call    ?ndisPowerSaveStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisPowerSaveStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x1400a6278  mov     edx, [r13+8]
0x1400a627c  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a627f  mov     r8d, edx
0x1400a6282  shr     edx, 8
0x1400a6285  shr     r8d, 0Ch
0x1400a6289  and     edx, 0Fh; enum _SYSTEM_POWER_STATE
0x1400a628c  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x1400a6290  call    ?ndisInvokeMiniportSysPowerNotify@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1@Z; ndisInvokeMiniportSysPowerNotify(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE)
0x1400a6295  mov     rax, [rdi+0EB0h]
0x1400a629c  mov     r14d, 1
0x1400a62a2  test    [rax+1Ah], r14b
0x1400a62a6  jnz     short loc_1400A62B0
0x1400a62a8  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a62ab  call    ?ndisMShutdownMiniport@@_Y2PAGENPNP@@AJPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisMShutdownMiniport(_NDIS_MINIPORT_BLOCK *)
0x1400a62b0  add     [rsi+43h], r14b
0x1400a62b4  mov     rdx, rsi; Irp
0x1400a62b7  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x1400a62bf  mov     dword ptr [rsi+30h], 0
0x1400a62c6  mov     rcx, [rdi+0F00h]; DeviceObject
0x1400a62cd  call    cs:__imp_IofCallDriver
0x1400a62d4  nop     dword ptr [rax+rax+00h]
0x1400a62d9  mov     r14d, eax
0x1400a62dc  jmp     loc_1400A65D2
0x1400a62e1  lea     rcx, [rdi+1078h]; void *
0x1400a62e8  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x1400a62ed  mov     edx, 6
0x1400a62f2  mov     rcx, rdi
0x1400a62f5  call    ?ndisPowerSaveStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisPowerSaveStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x1400a62fa  mov     edx, [r13+8]
0x1400a62fe  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a6301  mov     r8d, edx
0x1400a6304  shr     edx, 8
0x1400a6307  shr     r8d, 0Ch
0x1400a630b  and     edx, 0Fh; enum _SYSTEM_POWER_STATE
0x1400a630e  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x1400a6312  call    ?ndisInvokeMiniportSysPowerNotify@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1@Z; ndisInvokeMiniportSysPowerNotify(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE)
0x1400a6317  mov     r8d, [r13+8]
0x1400a631b  lea     r9, [rbp+PowerState]; enum _DEVICE_POWER_STATE *
0x1400a631f  shr     r8d, 8
0x1400a6323  mov     edx, r15d; enum _SYSTEM_POWER_STATE
0x1400a6326  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x1400a632a  mov     byte ptr [rsp+50h+IoStatus], r14b; unsigned __int8
0x1400a632f  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a6332  call    ?ndisMPowerPolicy@@_Y2PAGENPNP@@AJPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1PEAW4_DEVICE_POWER_STATE@@E@Z; ndisMPowerPolicy(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE,_DEVICE_POWER_STATE *,uchar)
0x1400a6337  cmp     eax, 8000000Fh
0x1400a633c  jnz     short loc_1400A6358
0x1400a633e  xor     edx, edx; PriorityBoost
0x1400a6340  mov     [rsi+30h], r14d
0x1400a6344  mov     rcx, rsi; Irp
0x1400a6347  call    cs:__imp_IofCompleteRequest
0x1400a634e  nop     dword ptr [rax+rax+00h]
0x1400a6353  jmp     loc_1400A65D2
0x1400a6358  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a635f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a6366  jz      short loc_1400A63A1
0x1400a6368  mov     eax, dword ptr [rbp+PowerState]
0x1400a636b  mov     r9d, 63h ; 'c'; int
0x1400a6371  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6378  mov     dl, 4; int
0x1400a637a  mov     dword ptr [rsp+50h+var_18], eax; char
0x1400a637e  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1400a6385  mov     dword ptr [rsp+50h+var_20], r15d; char
0x1400a638a  lea     r8d, [r9-55h]; int
0x1400a638e  mov     qword ptr [rsp+50h+var_28], rdi; char
0x1400a6393  mov     rcx, [rcx+40h]; int
0x1400a6397  mov     [rsp+50h+IoStatus], rax; struct _GUID *
0x1400a639c  call    WPP_RECORDER_SF_qDD
0x1400a63a1  test    cs:byte_14011B003, 4
0x1400a63a8  jz      short loc_1400A63E2
0x1400a63aa  mov     eax, dword ptr [rbp+PowerState]
0x1400a63ad  lea     r8, [rdi+0FA8h]
0x1400a63b4  mov     dword ptr [rsp+50h+var_18], eax
0x1400a63b8  lea     rdx, MiniportPowerStates
0x1400a63bf  mov     rax, [rdi+0FB8h]
0x1400a63c6  mov     r9, r8
0x1400a63c9  mov     dword ptr [rsp+50h+var_20], r15d
0x1400a63ce  mov     qword ptr [rsp+50h+var_28], rax
0x1400a63d3  mov     eax, [rdi+0FD8h]
0x1400a63d9  mov     dword ptr [rsp+50h+IoStatus], eax
0x1400a63dd  call    McTemplateK0jqxqq_EtwWriteTransfer
0x1400a63e2  lea     rcx, [rdi+0E90h]; Event
0x1400a63e9  call    cs:__imp_KeClearEvent
0x1400a63f0  nop     dword ptr [rax+rax+00h]
0x1400a63f5  mov     r14d, ebx
0x1400a63f8  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a63fb  mov     dl, r14b; unsigned __int8
0x1400a63fe  call    ?ndisCancelInitModeTimeoutTimer@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisCancelInitModeTimeoutTimer(_NDIS_MINIPORT_BLOCK *,uchar)
0x1400a6403  mov     edx, dword ptr [rbp+PowerState]; enum _NDIS_DEVICE_POWER_STATE
0x1400a6406  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a6409  call    ?ndisPrepForLowPower@@YAJPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; ndisPrepForLowPower(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x1400a640e  mov     rcx, [rsi+0B8h]
0x1400a6415  lea     r8, ?ndisRequestedDevicePowerIrpComplete@@YAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAXPEAU_IO_STATUS_BLOCK@@@Z; CompletionFunction
0x1400a641c  mov     rax, [rdi+0EF0h]
0x1400a6423  mov     r9, rsi; Context
0x1400a6426  mov     ebx, dword ptr [rbp+PowerState]
0x1400a6429  mov     word ptr [rsp+50h+IoStatus], r14w; enum _NDIS_MINIPORT_EVENT
0x1400a642f  mov     [rcx-20h], rax
0x1400a6433  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a6436  mov     rax, [rsi+0B8h]
0x1400a643d  or      [rax+3], r14b
0x1400a6441  mov     edx, dword ptr [rbp+PowerState]; PowerState
0x1400a6444  call    ?ndisRequestDeviceLowPower@@YAJPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@P6AXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAXPEAU_IO_STATUS_BLOCK@@@Z4W4_NDIS_MINIPORT_EVENT@@@Z; ndisRequestDeviceLowPower(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,void (*)(_DEVICE_OBJECT *,uchar,_POWER_STATE,void *,_IO_STATUS_BLOCK *),void *,_NDIS_MINIPORT_EVENT)
0x1400a6449  mov     r14d, 103h
0x1400a644f  cmp     eax, r14d
0x1400a6452  jz      loc_1400A65D2
0x1400a6458  mov     rcx, [rdi+0EF8h]; DeviceObject
0x1400a645f  mov     r9, rsi; Context
0x1400a6462  mov     dword ptr [rbp+var_10.___u0], eax
0x1400a6465  mov     r8d, ebx; PowerState
0x1400a6468  lea     rax, [rbp+var_10]
0x1400a646c  mov     [rbp+var_10.Information], 0
0x1400a6474  mov     dl, 2; MinorFunction
0x1400a6476  mov     [rsp+50h+IoStatus], rax; IoStatus
0x1400a647b  call    ?ndisRequestedDevicePowerIrpComplete@@YAXPEAU_DEVICE_OBJECT@@ET_POWER_STATE@@PEAXPEAU_IO_STATUS_BLOCK@@@Z; ndisRequestedDevicePowerIrpComplete(_DEVICE_OBJECT *,uchar,_POWER_STATE,void *,_IO_STATUS_BLOCK *)
0x1400a6480  jmp     loc_1400A65D2
0x1400a6485  test    dword ptr [rdi+7Ch], 800h
0x1400a648c  jnz     short loc_1400A64CA
0x1400a648e  cmp     cs:WPP_RECORDER_INITIALIZED, rdx; __annotation("TMF:",
0x1400a6495  jz      short loc_1400A64BD
0x1400a6497  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a649e  mov     r9d, 61h ; 'a'; int
0x1400a64a4  mov     qword ptr [rsp+50h+var_28], rdi; char
0x1400a64a9  mov     dl, 3; int
0x1400a64ab  mov     [rsp+50h+IoStatus], r8; struct _GUID *
0x1400a64b0  mov     rcx, [rcx+40h]; int
0x1400a64b4  lea     r8d, [r9-53h]; int
0x1400a64b8  call    WPP_RECORDER_SF_q
0x1400a64bd  mov     edx, 6
0x1400a64c2  mov     rcx, rdi
0x1400a64c5  call    ?ndisPowerSaveStop@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_SS_STOP_REASON@@@Z; ndisPowerSaveStop(_NDIS_MINIPORT_BLOCK *,_NDIS_SS_STOP_REASON)
0x1400a64ca  mov     r8d, [r13+8]
0x1400a64ce  lea     r9, [rbp+PowerState]; enum _DEVICE_POWER_STATE *
0x1400a64d2  shr     r8d, 8
0x1400a64d6  mov     edx, ebx; enum _SYSTEM_POWER_STATE
0x1400a64d8  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x1400a64dc  mov     byte ptr [rsp+50h+IoStatus], r14b; unsigned __int8
0x1400a64e1  mov     rcx, rdi; struct _NDIS_MINIPORT_BLOCK *
0x1400a64e4  call    ?ndisMPowerPolicy@@_Y2PAGENPNP@@AJPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1PEAW4_DEVICE_POWER_STATE@@E@Z; ndisMPowerPolicy(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE,_DEVICE_POWER_STATE *,uchar)
0x1400a64e9  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400a64f0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400a64f7  jz      short loc_1400A6526
0x1400a64f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400a6500  lea     rax, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x1400a6507  mov     r9d, 62h ; 'b'; int
0x1400a650d  mov     qword ptr [rsp+50h+var_28], rdi; char
0x1400a6512  mov     dl, 4; int
0x1400a6514  mov     [rsp+50h+IoStatus], rax; struct _GUID *
0x1400a6519  mov     rcx, [rcx+40h]; int
0x1400a651d  lea     r8d, [r9-54h]; int
0x1400a6521  call    WPP_RECORDER_SF_q
0x1400a6526  test    cs:byte_14011B003, 4
0x1400a652d  jz      short loc_1400A6566
0x1400a652f  mov     eax, dword ptr [rbp+PowerState]
0x1400a6532  lea     r8, [rdi+0FA8h]
0x1400a6539  mov     dword ptr [rsp+50h+var_18], eax
0x1400a653d  lea     rdx, MiniportPowerStates
0x1400a6544  mov     rax, [rdi+0FB8h]
0x1400a654b  mov     r9, r8
0x1400a654e  mov     dword ptr [rsp+50h+var_20], ebx
0x1400a6552  mov     qword ptr [rsp+50h+var_28], rax
0x1400a6557  mov     eax, [rdi+0FD8h]
0x1400a655d  mov     dword ptr [rsp+50h+IoStatus], eax
0x1400a6561  call    McTemplateK0jqxqq_EtwWriteTransfer
0x1400a6566  mov     rax, [rsi+0B8h]
0x1400a656d  lea     rcx, ?ndisSetSystemPowerOnComplete@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisSetSystemPowerOnComplete(_DEVICE_OBJECT *,_IRP *,void *)
0x1400a6574  mov     rdx, rsi; Irp
0x1400a6577  movups  xmm0, xmmword ptr [rax]
0x1400a657a  movups  xmmword ptr [rax-48h], xmm0
0x1400a657e  movups  xmm1, xmmword ptr [rax+10h]
0x1400a6582  movups  xmmword ptr [rax-38h], xmm1
0x1400a6586  movups  xmm0, xmmword ptr [rax+20h]
0x1400a658a  movups  xmmword ptr [rax-28h], xmm0
0x1400a658e  movsd   xmm1, qword ptr [rax+30h]
0x1400a6593  movsd   qword ptr [rax-18h], xmm1
0x1400a6598  mov     [rax-45h], r14b
0x1400a659c  mov     rax, [rsi+0B8h]
0x1400a65a3  mov     [rax-10h], rcx
0x1400a65a7  mov     [rax-8], rdi
0x1400a65ab  mov     byte ptr [rax-45h], 0E0h
0x1400a65af  mov     rax, [rsi+0B8h]
0x1400a65b6  or      [rax+3], bl
0x1400a65b9  mov     rcx, [rdi+0F00h]; DeviceObject
0x1400a65c0  call    cs:__imp_IofCallDriver
0x1400a65c7  nop     dword ptr [rax+rax+00h]
0x1400a65cc  mov     r14d, 103h
0x1400a65d2  mov     eax, r14d
0x1400a65d5  lea     r11, [rsp+50h+var_s0]
0x1400a65da  mov     rbx, [r11+30h]
0x1400a65de  mov     rsi, [r11+40h]
0x1400a65e2  mov     rsp, r11
0x1400a65e5  pop     r15
0x1400a65e7  pop     r14
0x1400a65e9  pop     r13
0x1400a65eb  pop     rdi
0x1400a65ec  pop     rbp
0x1400a65ed  retn
```
