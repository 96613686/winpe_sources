# ndisQueryPower(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)

- ea: `0x14017d490`
- end: `0x14017d8e6`
- name: `?ndisQueryPower@@_Y2PAGENPNP@@AJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `1110`
- prototype: `__int64 __fastcall(PIRP Irp, struct _IO_STACK_LOCATION *, struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005f0c0`
- `0x1400ab160`

## callees

- `0x1400110b0`
- `0x140011190`
- `0x1400114b0`
- `0x14003e940`
- `0x14003f590`
- `0x1400400d0`
- `0x1400416b0`
- `0x140041ae0`
- `0x140041bc0`
- `0x140053280`
- `0x14005ea20`
- `0x140080b80`
- `0x1400eb380`
- `0x1400eb7c0`
- `0x14017d490`
- `0x14017d8f0`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14017d66c`
- `ntoskrnl!IofCallDriver` at `0x14017d724`
- `ntoskrnl!IofCallDriver` at `0x14017d66c`
- `ntoskrnl!IofCallDriver` at `0x14017d724`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14017d63c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14017d63c`
- `ntoskrnl!IofCompleteRequest` at `0x14017d790`
- `ntoskrnl!IofCompleteRequest` at `0x14017d7aa`
- `ntoskrnl!IofCompleteRequest` at `0x14017d790`
- `ntoskrnl!IofCompleteRequest` at `0x14017d7aa`

## pseudocode

```c
NTSTATUS __fastcall ndisQueryPower(PIRP Irp, struct _IO_STACK_LOCATION *a2, struct _NDIS_MINIPORT_BLOCK *a3)
{
  int v6; // edx
  int v7; // edx
  __int64 Options; // rcx
  int v9; // r14d
  int v10; // edx
  int v11; // ecx
  int v12; // edx
  int SetMiniportDeviceState; // eax
  int v14; // edx
  int v15; // ecx
  char v16; // si
  _IO_STACK_LOCATION *v17; // rax
  _IO_STACK_LOCATION *v18; // rax
  int v19; // edx
  _IO_STACK_LOCATION *CurrentStackLocation; // rax
  enum _DEVICE_POWER_STATE v22[4]; // [rsp+50h] [rbp-108h] BYREF
  struct _NET_PNP_EVENT_NOTIFICATION v23; // [rsp+60h] [rbp-F8h] BYREF

  v22[0] = PowerDeviceUnspecified;
  memset(&v23, 0, sizeof(v23));
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v6,
      14,
      38,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)a3);
  }
  ndisReferencePackage((struct _PKG_REF *)&ndisPkgs);
  Options = a2->Parameters.Create.Options;
  if ( (_DWORD)Options == 1 )
  {
    CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&CurrentStackLocation[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&CurrentStackLocation->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)&CurrentStackLocation[-1].Parameters.ReadWriteConfig.Length = *(_OWORD *)&CurrentStackLocation->Parameters.ReadWriteConfig.Length;
    CurrentStackLocation[-1].FileObject = CurrentStackLocation->FileObject;
    CurrentStackLocation[-1].Control = 0;
    return IofCallDriver(a3->NextDeviceObject, Irp);
  }
  if ( (_DWORD)Options )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qLL(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v7,
        14,
        39,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)a3,
        Options,
        a2->Parameters.Read.ByteOffset.LowPart);
    if ( (byte_140121002 & 0x40) != 0 )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _DWORD))McTemplateK0jqxqq_EtwWriteTransfer)(
        Options,
        InvalidSystemPowerState,
        &a3->InterfaceGuid,
        &a3->InterfaceGuid,
        a3->IfIndex,
        (_NET_LUID_LH)a3->NetLuid.Value,
        a2->Parameters.Create.Options,
        a2->Parameters.Read.ByteOffset.LowPart);
    v9 = -1073741808;
  }
  else
  {
    v9 = ndisMPowerPolicy(
           a3,
           a2->Parameters.Power.State.SystemState,
           (enum _SYSTEM_POWER_STATE)((a2->Parameters.Read.Length >> 8) & 0xF),
           v22,
           1u);
    if ( !ndisIsMiniportStarted(a3) || a3->PnPDeviceState != NdisPnPDeviceStarted || v9 == -2147483633 )
    {
      Irp->IoStatus.Status = 0;
      IofCompleteRequest(Irp, 0);
      return 0;
    }
    if ( v9 >= 0 )
    {
      ndisInitializeNetPnPEvent(&v23, 0);
      v23.NetPnPEvent.NetEvent = NetEventQueryPower;
      v23.NetPnPEvent.Buffer = v22;
      v23.NetPnPEvent.BufferLength = 4;
      if ( (unsigned int)ndisDevicePnPEventNotifyFiltersAndAllTransports(a3, &v23)
        && *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v12) = 2;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v12,
          14,
          41,
          (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
          (char)a3);
      }
      if ( (a3->PnPFlags & 0x20) != 0 )
      {
        SetMiniportDeviceState = ndisQuerySetMiniportDeviceState(a3, v22[0], 0xFD010102, 0);
        v16 = SetMiniportDeviceState;
        if ( SetMiniportDeviceState )
        {
          if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v14) = 4;
            WPP_RECORDER_SF_q(
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              v14,
              14,
              42,
              (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
              (char)a3);
          }
          if ( (byte_140121001 & 8) != 0 )
            McTemplateK0jqxddq_EtwWriteTransfer(
              v15,
              (unsigned int)QueryPowerFailed,
              (_DWORD)a3 + 4008,
              (_DWORD)a3 + 4008,
              a3->IfIndex,
              a3->NetLuid.Value,
              v16,
              2,
              0);
        }
      }
      Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
      v17 = Irp->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v17[-1].MajorFunction = *(_OWORD *)&v17->MajorFunction;
      *(_OWORD *)&v17[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v17->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)&v17[-1].Parameters.ReadWriteConfig.Length = *(_OWORD *)&v17->Parameters.ReadWriteConfig.Length;
      v17[-1].FileObject = v17->FileObject;
      v17[-1].Control = 0;
      a3->QueryPowerDeviceState = v22[0];
      a3->PendingQueryPowerIrp = Irp;
      IoAcquireRemoveLockEx(&a3->RemoveLock, Irp, File, 1u, 0x20u);
      v18 = Irp->Tail.Overlay.CurrentStackLocation;
      v18[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))ndisQueryPowerCompleteSystemState;
      v18[-1].Context = a3;
      v18[-1].Control = -32;
      IofCallDriver(a3->NextDeviceObject, Irp);
      v9 = 259;
      ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
      goto LABEL_13;
    }
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = 4;
      WPP_RECORDER_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v10,
        14,
        40,
        (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
        (char)a3,
        a2->Parameters.Read.ByteOffset.LowPart);
    }
    if ( (byte_140121001 & 8) != 0 )
      McTemplateK0jqxddq_EtwWriteTransfer(
        v11,
        (unsigned int)QueryPowerFailed,
        (_DWORD)a3 + 4008,
        (_DWORD)a3 + 4008,
        a3->IfIndex,
        a3->NetLuid.Value,
        v9,
        1,
        a2->Parameters.Read.ByteOffset.LowPart);
  }
  ndisDereferencePackage((struct _PKG_REF *)&ndisPkgs);
  Irp->IoStatus.Status = v9;
  IofCompleteRequest(Irp, 0);
LABEL_13:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v19) = 4;
    WPP_RECORDER_SF_qL(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v19,
      14,
      43,
      (struct _GUID *)&WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids,
      (char)a3,
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x14017d490  push    rbx
0x14017d492  push    rbp
0x14017d493  push    rsi
0x14017d494  push    rdi
0x14017d495  push    r12
0x14017d497  push    r13
0x14017d499  push    r15
0x14017d49b  sub     rsp, 120h
0x14017d4a2  mov     rax, cs:__security_cookie
0x14017d4a9  xor     rax, rsp
0x14017d4ac  mov     [rsp+158h+var_48], rax
0x14017d4b4  mov     rbx, r8
0x14017d4b7  mov     rsi, rdx
0x14017d4ba  mov     rbp, rcx
0x14017d4bd  xor     r12d, r12d
0x14017d4c0  xor     edx, edx; Val
0x14017d4c2  mov     [rsp+158h+var_108], r12d
0x14017d4c7  mov     r8d, 0B0h; Size
0x14017d4cd  lea     rcx, [rsp+158h+var_F8]; void *
0x14017d4d2  call    memset
0x14017d4d7  lea     r15, WPP_RECORDER_INITIALIZED
0x14017d4de  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14017d4e5  lea     r13, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017d4ec  jnz     loc_14017D6C1
0x14017d4f2  lea     rdi, ?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x14017d4f9  mov     rcx, rdi; struct _PKG_REF *
0x14017d4fc  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x14017d501  mov     ecx, [rsi+10h]
0x14017d504  cmp     ecx, 1
0x14017d507  jz      loc_14017D6EE
0x14017d50d  mov     [rsp+158h+arg_18], r14
0x14017d515  test    ecx, ecx
0x14017d517  jnz     loc_14017D767
0x14017d51d  mov     r8d, [rsi+8]
0x14017d521  lea     r9, [rsp+158h+var_108]; enum _DEVICE_POWER_STATE *
0x14017d526  mov     edx, [rsi+18h]; enum _SYSTEM_POWER_STATE
0x14017d529  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017d52c  shr     r8d, 8
0x14017d530  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x14017d534  mov     byte ptr [rsp+158h+RemlockSize], 1; unsigned __int8
0x14017d539  call    ?ndisMPowerPolicy@@_Y2PAGENPNP@@AJPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1PEAW4_DEVICE_POWER_STATE@@E@Z; ndisMPowerPolicy(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE,_DEVICE_POWER_STATE *,uchar)
0x14017d53e  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017d541  mov     r14d, eax
0x14017d544  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x14017d549  test    al, al
0x14017d54b  jz      loc_14017D7A1
0x14017d551  cmp     dword ptr [rbx+5F0h], 1
0x14017d558  jnz     loc_14017D7A1
0x14017d55e  cmp     r14d, 8000000Fh
0x14017d565  jz      loc_14017D7A1
0x14017d56b  test    r14d, r14d
0x14017d56e  js      loc_14017D82F
0x14017d574  xor     edx, edx; struct _KEVENT *
0x14017d576  lea     rcx, [rsp+158h+var_F8]; struct _NET_PNP_EVENT_NOTIFICATION *
0x14017d57b  call    ?ndisInitializeNetPnPEvent@@YAXPEAU_NET_PNP_EVENT_NOTIFICATION@@PEAU_KEVENT@@@Z; ndisInitializeNetPnPEvent(_NET_PNP_EVENT_NOTIFICATION *,_KEVENT *)
0x14017d580  lea     rax, [rsp+158h+var_108]
0x14017d585  mov     [rsp+158h+var_F8.NetPnPEvent.NetEvent], 1
0x14017d58d  lea     rdx, [rsp+158h+var_F8]; struct _NET_PNP_EVENT_NOTIFICATION *
0x14017d592  mov     [rsp+158h+var_F8.NetPnPEvent.Buffer], rax
0x14017d597  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017d59a  mov     [rsp+158h+var_F8.NetPnPEvent.BufferLength], 4
0x14017d5a2  call    ?ndisDevicePnPEventNotifyFiltersAndAllTransports@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NET_PNP_EVENT_NOTIFICATION@@@Z; ndisDevicePnPEventNotifyFiltersAndAllTransports(_NDIS_MINIPORT_BLOCK *,_NET_PNP_EVENT_NOTIFICATION *)
0x14017d5a7  test    eax, eax
0x14017d5a9  jnz     loc_14017D871
0x14017d5af  mov     eax, [rbx+7Ch]
0x14017d5b2  test    al, 20h
0x14017d5b4  jz      short loc_14017D5D5
0x14017d5b6  mov     edx, [rsp+158h+var_108]; enum _DEVICE_POWER_STATE
0x14017d5ba  xor     r9d, r9d; unsigned __int8
0x14017d5bd  mov     r8d, 0FD010102h; unsigned int
0x14017d5c3  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017d5c6  call    ?ndisQuerySetMiniportDeviceState@@YAHPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@KE@Z; ndisQuerySetMiniportDeviceState(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,ulong,uchar)
0x14017d5cb  mov     esi, eax
0x14017d5cd  test    eax, eax
0x14017d5cf  jnz     loc_14017D8AB
0x14017d5d5  mov     rax, [rbp+0B8h]
0x14017d5dc  lea     rcx, [rbx+1018h]; RemoveLock
0x14017d5e3  mov     r9d, 1; Line
0x14017d5e9  mov     [rsp+158h+RemlockSize], 20h ; ' '; RemlockSize
0x14017d5f1  lea     r8, File; File
0x14017d5f8  mov     rdx, rbp; Tag
0x14017d5fb  or      byte ptr [rax+3], 1
0x14017d5ff  mov     rax, [rbp+0B8h]
0x14017d606  movups  xmm0, xmmword ptr [rax]
0x14017d609  movups  xmmword ptr [rax-48h], xmm0
0x14017d60d  movups  xmm1, xmmword ptr [rax+10h]
0x14017d611  movups  xmmword ptr [rax-38h], xmm1
0x14017d615  movups  xmm0, xmmword ptr [rax+20h]
0x14017d619  movups  xmmword ptr [rax-28h], xmm0
0x14017d61d  movsd   xmm1, qword ptr [rax+30h]
0x14017d622  movsd   qword ptr [rax-18h], xmm1
0x14017d627  mov     [rax-45h], r12b
0x14017d62b  mov     eax, [rsp+158h+var_108]
0x14017d62f  mov     [rbx+0C48h], eax
0x14017d635  mov     [rbx+308h], rbp
0x14017d63c  call    cs:__imp_IoAcquireRemoveLockEx
0x14017d643  nop     dword ptr [rax+rax+00h]
0x14017d648  mov     rax, [rbp+0B8h]
0x14017d64f  lea     rcx, ?ndisQueryPowerCompleteSystemState@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisQueryPowerCompleteSystemState(_DEVICE_OBJECT *,_IRP *,void *)
0x14017d656  mov     rdx, rbp; Irp
0x14017d659  mov     [rax-10h], rcx
0x14017d65d  mov     [rax-8], rbx
0x14017d661  mov     byte ptr [rax-45h], 0E0h
0x14017d665  mov     rcx, [rbx+0F00h]; DeviceObject
0x14017d66c  call    cs:__imp_IofCallDriver
0x14017d673  nop     dword ptr [rax+rax+00h]
0x14017d678  mov     rcx, rdi; struct _PKG_REF *
0x14017d67b  mov     r14d, 103h
0x14017d681  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x14017d686  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14017d68d  jnz     loc_14017D735
0x14017d693  mov     eax, r14d
0x14017d696  mov     r14, [rsp+158h+arg_18]
0x14017d69e  mov     rcx, [rsp+158h+var_48]
0x14017d6a6  xor     rcx, rsp; StackCookie
0x14017d6a9  call    __security_check_cookie
0x14017d6ae  add     rsp, 120h
0x14017d6b5  pop     r15
0x14017d6b7  pop     r13
0x14017d6b9  pop     r12
0x14017d6bb  pop     rdi
0x14017d6bc  pop     rsi
0x14017d6bd  pop     rbp
0x14017d6be  pop     rbx
0x14017d6bf  retn
0x14017d6c1  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d6c8  mov     r9d, 26h ; '&'; int
0x14017d6ce  mov     qword ptr [rsp+158h+var_130], rbx; char
0x14017d6d3  mov     r8d, 0Eh; int
0x14017d6d9  mov     dl, 4; int
0x14017d6db  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x14017d6e0  mov     rcx, [rcx+40h]; int
0x14017d6e4  call    WPP_RECORDER_SF_q
0x14017d6e9  jmp     loc_14017D4F2
0x14017d6ee  mov     rax, [rbp+0B8h]
0x14017d6f5  mov     rdx, rbp; Irp
0x14017d6f8  movups  xmm0, xmmword ptr [rax]
0x14017d6fb  movups  xmmword ptr [rax-48h], xmm0
0x14017d6ff  movups  xmm1, xmmword ptr [rax+10h]
0x14017d703  movups  xmmword ptr [rax-38h], xmm1
0x14017d707  movups  xmm0, xmmword ptr [rax+20h]
0x14017d70b  movups  xmmword ptr [rax-28h], xmm0
0x14017d70f  movsd   xmm1, qword ptr [rax+30h]
0x14017d714  movsd   qword ptr [rax-18h], xmm1
0x14017d719  mov     [rax-45h], r12b
0x14017d71d  mov     rcx, [rbx+0F00h]; DeviceObject
0x14017d724  call    cs:__imp_IofCallDriver
0x14017d72b  nop     dword ptr [rax+rax+00h]
0x14017d730  jmp     loc_14017D69E
0x14017d735  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d73c  mov     r9d, 2Bh ; '+'; int
0x14017d742  mov     dword ptr [rsp+158h+var_128], r14d; char
0x14017d747  mov     r8d, 0Eh; int
0x14017d74d  mov     qword ptr [rsp+158h+var_130], rbx; char
0x14017d752  mov     dl, 4; int
0x14017d754  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x14017d759  mov     rcx, [rcx+40h]; int
0x14017d75d  call    WPP_RECORDER_SF_qL
0x14017d762  jmp     loc_14017D693
0x14017d767  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14017d76e  jnz     short loc_14017D7BD
0x14017d770  test    cs:byte_140121002, 40h
0x14017d777  jnz     short loc_14017D7F0
0x14017d779  mov     r14d, 0C0000010h
0x14017d77f  mov     rcx, rdi; struct _PKG_REF *
0x14017d782  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x14017d787  xor     edx, edx; PriorityBoost
0x14017d789  mov     [rbp+30h], r14d
0x14017d78d  mov     rcx, rbp; Irp
0x14017d790  call    cs:__imp_IofCompleteRequest
0x14017d797  nop     dword ptr [rax+rax+00h]
0x14017d79c  jmp     loc_14017D686
0x14017d7a1  xor     edx, edx; PriorityBoost
0x14017d7a3  mov     [rbp+30h], r12d
0x14017d7a7  mov     rcx, rbp; Irp
0x14017d7aa  call    cs:__imp_IofCompleteRequest
0x14017d7b1  nop     dword ptr [rax+rax+00h]
0x14017d7b6  xor     eax, eax
0x14017d7b8  jmp     loc_14017D696
0x14017d7bd  mov     eax, [rsi+18h]
0x14017d7c0  mov     r9d, 27h ; '''; int
0x14017d7c6  mov     dword ptr [rsp+158h+var_120], eax; char
0x14017d7ca  mov     r8d, 0Eh; int
0x14017d7d0  mov     dword ptr [rsp+158h+var_128], ecx; char
0x14017d7d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d7db  mov     qword ptr [rsp+158h+var_130], rbx; char
0x14017d7e0  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x14017d7e5  mov     rcx, [rcx+40h]; int
0x14017d7e9  call    WPP_RECORDER_SF_qLL
0x14017d7ee  jmp     short loc_14017D770
0x14017d7f0  mov     eax, [rsi+18h]
0x14017d7f3  lea     r8, [rbx+0FA8h]
0x14017d7fa  mov     dword ptr [rsp+158h+var_120], eax
0x14017d7fe  lea     rdx, InvalidSystemPowerState
0x14017d805  mov     eax, [rsi+10h]
0x14017d808  mov     r9, r8
0x14017d80b  mov     dword ptr [rsp+158h+var_128], eax
0x14017d80f  mov     rax, [rbx+0FB8h]
0x14017d816  mov     qword ptr [rsp+158h+var_130], rax
0x14017d81b  mov     eax, [rbx+0FD8h]
0x14017d821  mov     [rsp+158h+RemlockSize], eax
0x14017d825  call    McTemplateK0jqxqq_EtwWriteTransfer
0x14017d82a  jmp     loc_14017D779
0x14017d82f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14017d836  jz      loc_14018958C
0x14017d83c  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d843  mov     r9d, 28h ; '('; int
0x14017d849  mov     eax, [rsi+18h]
0x14017d84c  mov     r8d, 0Eh; int
0x14017d852  mov     dword ptr [rsp+158h+var_128], eax; char
0x14017d856  mov     dl, 4; int
0x14017d858  mov     qword ptr [rsp+158h+var_130], rbx; char
0x14017d85d  mov     rcx, [rcx+40h]; int
0x14017d861  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x14017d866  call    WPP_RECORDER_SF_qD
0x14017d86b  nop
0x14017d86c  jmp     loc_14018958C
0x14017d871  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14017d878  jz      loc_14017D5AF
0x14017d87e  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d885  mov     r9d, 29h ; ')'; int
0x14017d88b  mov     qword ptr [rsp+158h+var_130], rbx; char
0x14017d890  mov     r8d, 0Eh; int
0x14017d896  mov     dl, 2; int
0x14017d898  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x14017d89d  mov     rcx, [rcx+40h]; int
0x14017d8a1  call    WPP_RECORDER_SF_q
0x14017d8a6  jmp     loc_14017D5AF
0x14017d8ab  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14017d8b2  jz      loc_1401895DF
0x14017d8b8  mov     rcx, cs:WPP_GLOBAL_Control
0x14017d8bf  mov     r9d, 2Ah ; '*'; int
0x14017d8c5  mov     qword ptr [rsp+158h+var_130], rbx; char
0x14017d8ca  mov     r8d, 0Eh; int
0x14017d8d0  mov     dl, 4; int
0x14017d8d2  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x14017d8d7  mov     rcx, [rcx+40h]; int
0x14017d8db  call    WPP_RECORDER_SF_q
0x14017d8e0  nop
0x14017d8e1  jmp     loc_1401895DF
0x14018958c  test    cs:byte_140121001, 8
0x140189593  jz      loc_14017D77F
0x140189599  mov     eax, [rsi+18h]
0x14018959c  lea     r8, [rbx+0FA8h]
0x1401895a3  mov     [rsp+158h+var_118], eax
0x1401895a7  lea     rdx, QueryPowerFailed
0x1401895ae  mov     rax, [rbx+0FB8h]
0x1401895b5  mov     r9, r8
0x1401895b8  mov     dword ptr [rsp+158h+var_120], 10001h
0x1401895c0  mov     dword ptr [rsp+158h+var_128], r14d
0x1401895c5  mov     qword ptr [rsp+158h+var_130], rax
0x1401895ca  mov     eax, [rbx+0FD8h]
0x1401895d0  mov     [rsp+158h+RemlockSize], eax
0x1401895d4  call    McTemplateK0jqxddq_EtwWriteTransfer
0x1401895d9  nop
0x1401895da  jmp     loc_14017D77F
0x1401895df  test    cs:byte_140121001, 8
0x1401895e6  jz      loc_14017D5D5
0x1401895ec  mov     rax, [rbx+0FB8h]
0x1401895f3  lea     r8, [rbx+0FA8h]
0x1401895fa  mov     [rsp+158h+var_118], r12d
0x1401895ff  lea     rdx, QueryPowerFailed
0x140189606  mov     dword ptr [rsp+158h+var_120], 10002h
0x14018960e  mov     r9, r8
0x140189611  mov     dword ptr [rsp+158h+var_128], esi
0x140189615  mov     qword ptr [rsp+158h+var_130], rax
0x14018961a  mov     eax, [rbx+0FD8h]
0x140189620  mov     [rsp+158h+RemlockSize], eax
0x140189624  call    McTemplateK0jqxddq_EtwWriteTransfer
0x140189629  nop
0x14018962a  jmp     loc_14017D5D5
```
