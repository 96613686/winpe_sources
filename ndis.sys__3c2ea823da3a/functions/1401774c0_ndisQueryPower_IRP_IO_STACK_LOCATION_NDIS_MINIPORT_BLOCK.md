# ndisQueryPower(_IRP *,_IO_STACK_LOCATION *,_NDIS_MINIPORT_BLOCK *)

- ea: `0x1401774c0`
- end: `0x140177916`
- name: `?ndisQueryPower@@_Y2PAGENPNP@@AJPEAU_IRP@@PEAU_IO_STACK_LOCATION@@PEAU_NDIS_MINIPORT_BLOCK@@@Z`
- size: `1110`
- prototype: `__int64 __fastcall(PIRP Irp, struct _IO_STACK_LOCATION *, struct _NDIS_MINIPORT_BLOCK *)`
- caller_count: `2`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14005aad0`
- `0x1400a5d20`

## callees

- `0x14001cf50`
- `0x14001d030`
- `0x14001d350`
- `0x14003a720`
- `0x14003c190`
- `0x14003cde0`
- `0x14003d920`
- `0x14003ef00`
- `0x14003f330`
- `0x14004e050`
- `0x14005a330`
- `0x14007b4e0`
- `0x1400e6160`
- `0x1400e65c0`
- `0x1401774c0`
- `0x140177920`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14017769c`
- `ntoskrnl!IofCallDriver` at `0x140177754`
- `ntoskrnl!IofCallDriver` at `0x14017769c`
- `ntoskrnl!IofCallDriver` at `0x140177754`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14017766c`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14017766c`
- `ntoskrnl!IofCompleteRequest` at `0x1401777c0`
- `ntoskrnl!IofCompleteRequest` at `0x1401777da`
- `ntoskrnl!IofCompleteRequest` at `0x1401777c0`
- `ntoskrnl!IofCompleteRequest` at `0x1401777da`

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
    if ( (byte_14011B002 & 0x40) != 0 )
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
          if ( (byte_14011B001 & 8) != 0 )
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
    if ( (byte_14011B001 & 8) != 0 )
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
0x1401774c0  push    rbx
0x1401774c2  push    rbp
0x1401774c3  push    rsi
0x1401774c4  push    rdi
0x1401774c5  push    r12
0x1401774c7  push    r13
0x1401774c9  push    r15
0x1401774cb  sub     rsp, 120h
0x1401774d2  mov     rax, cs:__security_cookie
0x1401774d9  xor     rax, rsp
0x1401774dc  mov     [rsp+158h+var_48], rax
0x1401774e4  mov     rbx, r8
0x1401774e7  mov     rsi, rdx
0x1401774ea  mov     rbp, rcx
0x1401774ed  xor     r12d, r12d
0x1401774f0  xor     edx, edx; Val
0x1401774f2  mov     [rsp+158h+var_108], r12d
0x1401774f7  mov     r8d, 0B0h; Size
0x1401774fd  lea     rcx, [rsp+158h+var_F8]; void *
0x140177502  call    memset
0x140177507  lea     r15, WPP_RECORDER_INITIALIZED
0x14017750e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140177515  lea     r13, WPP_dc968d99198e32e9263b7dc94e457b33_Traceguids
0x14017751c  jnz     loc_1401776F1
0x140177522  lea     rdi, ?ndisPkgs@@3PAU_PKG_REF@@A; _PKG_REF near * ndisPkgs
0x140177529  mov     rcx, rdi; struct _PKG_REF *
0x14017752c  call    ?ndisReferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisReferencePackage(_PKG_REF *)
0x140177531  mov     ecx, [rsi+10h]
0x140177534  cmp     ecx, 1
0x140177537  jz      loc_14017771E
0x14017753d  mov     [rsp+158h+arg_18], r14
0x140177545  test    ecx, ecx
0x140177547  jnz     loc_140177797
0x14017754d  mov     r8d, [rsi+8]
0x140177551  lea     r9, [rsp+158h+var_108]; enum _DEVICE_POWER_STATE *
0x140177556  mov     edx, [rsi+18h]; enum _SYSTEM_POWER_STATE
0x140177559  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x14017755c  shr     r8d, 8
0x140177560  and     r8d, 0Fh; enum _SYSTEM_POWER_STATE
0x140177564  mov     byte ptr [rsp+158h+RemlockSize], 1; unsigned __int8
0x140177569  call    ?ndisMPowerPolicy@@_Y2PAGENPNP@@AJPEAU_NDIS_MINIPORT_BLOCK@@W4_SYSTEM_POWER_STATE@@1PEAW4_DEVICE_POWER_STATE@@E@Z; ndisMPowerPolicy(_NDIS_MINIPORT_BLOCK *,_SYSTEM_POWER_STATE,_SYSTEM_POWER_STATE,_DEVICE_POWER_STATE *,uchar)
0x14017756e  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x140177571  mov     r14d, eax
0x140177574  call    ?ndisIsMiniportStarted@@YAEPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisIsMiniportStarted(_NDIS_MINIPORT_BLOCK *)
0x140177579  test    al, al
0x14017757b  jz      loc_1401777D1
0x140177581  cmp     dword ptr [rbx+5F0h], 1
0x140177588  jnz     loc_1401777D1
0x14017758e  cmp     r14d, 8000000Fh
0x140177595  jz      loc_1401777D1
0x14017759b  test    r14d, r14d
0x14017759e  js      loc_14017785F
0x1401775a4  xor     edx, edx; struct _KEVENT *
0x1401775a6  lea     rcx, [rsp+158h+var_F8]; struct _NET_PNP_EVENT_NOTIFICATION *
0x1401775ab  call    ?ndisInitializeNetPnPEvent@@YAXPEAU_NET_PNP_EVENT_NOTIFICATION@@PEAU_KEVENT@@@Z; ndisInitializeNetPnPEvent(_NET_PNP_EVENT_NOTIFICATION *,_KEVENT *)
0x1401775b0  lea     rax, [rsp+158h+var_108]
0x1401775b5  mov     [rsp+158h+var_F8.NetPnPEvent.NetEvent], 1
0x1401775bd  lea     rdx, [rsp+158h+var_F8]; struct _NET_PNP_EVENT_NOTIFICATION *
0x1401775c2  mov     [rsp+158h+var_F8.NetPnPEvent.Buffer], rax
0x1401775c7  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401775ca  mov     [rsp+158h+var_F8.NetPnPEvent.BufferLength], 4
0x1401775d2  call    ?ndisDevicePnPEventNotifyFiltersAndAllTransports@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NET_PNP_EVENT_NOTIFICATION@@@Z; ndisDevicePnPEventNotifyFiltersAndAllTransports(_NDIS_MINIPORT_BLOCK *,_NET_PNP_EVENT_NOTIFICATION *)
0x1401775d7  test    eax, eax
0x1401775d9  jnz     loc_1401778A1
0x1401775df  mov     eax, [rbx+7Ch]
0x1401775e2  test    al, 20h
0x1401775e4  jz      short loc_140177605
0x1401775e6  mov     edx, [rsp+158h+var_108]; enum _DEVICE_POWER_STATE
0x1401775ea  xor     r9d, r9d; unsigned __int8
0x1401775ed  mov     r8d, 0FD010102h; unsigned int
0x1401775f3  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1401775f6  call    ?ndisQuerySetMiniportDeviceState@@YAHPEAU_NDIS_MINIPORT_BLOCK@@W4_DEVICE_POWER_STATE@@KE@Z; ndisQuerySetMiniportDeviceState(_NDIS_MINIPORT_BLOCK *,_DEVICE_POWER_STATE,ulong,uchar)
0x1401775fb  mov     esi, eax
0x1401775fd  test    eax, eax
0x1401775ff  jnz     loc_1401778DB
0x140177605  mov     rax, [rbp+0B8h]
0x14017760c  lea     rcx, [rbx+1018h]; RemoveLock
0x140177613  mov     r9d, 1; Line
0x140177619  mov     [rsp+158h+RemlockSize], 20h ; ' '; RemlockSize
0x140177621  lea     r8, File; File
0x140177628  mov     rdx, rbp; Tag
0x14017762b  or      byte ptr [rax+3], 1
0x14017762f  mov     rax, [rbp+0B8h]
0x140177636  movups  xmm0, xmmword ptr [rax]
0x140177639  movups  xmmword ptr [rax-48h], xmm0
0x14017763d  movups  xmm1, xmmword ptr [rax+10h]
0x140177641  movups  xmmword ptr [rax-38h], xmm1
0x140177645  movups  xmm0, xmmword ptr [rax+20h]
0x140177649  movups  xmmword ptr [rax-28h], xmm0
0x14017764d  movsd   xmm1, qword ptr [rax+30h]
0x140177652  movsd   qword ptr [rax-18h], xmm1
0x140177657  mov     [rax-45h], r12b
0x14017765b  mov     eax, [rsp+158h+var_108]
0x14017765f  mov     [rbx+0C48h], eax
0x140177665  mov     [rbx+308h], rbp
0x14017766c  call    cs:__imp_IoAcquireRemoveLockEx
0x140177673  nop     dword ptr [rax+rax+00h]
0x140177678  mov     rax, [rbp+0B8h]
0x14017767f  lea     rcx, ?ndisQueryPowerCompleteSystemState@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z; ndisQueryPowerCompleteSystemState(_DEVICE_OBJECT *,_IRP *,void *)
0x140177686  mov     rdx, rbp; Irp
0x140177689  mov     [rax-10h], rcx
0x14017768d  mov     [rax-8], rbx
0x140177691  mov     byte ptr [rax-45h], 0E0h
0x140177695  mov     rcx, [rbx+0F00h]; DeviceObject
0x14017769c  call    cs:__imp_IofCallDriver
0x1401776a3  nop     dword ptr [rax+rax+00h]
0x1401776a8  mov     rcx, rdi; struct _PKG_REF *
0x1401776ab  mov     r14d, 103h
0x1401776b1  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x1401776b6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401776bd  jnz     loc_140177765
0x1401776c3  mov     eax, r14d
0x1401776c6  mov     r14, [rsp+158h+arg_18]
0x1401776ce  mov     rcx, [rsp+158h+var_48]
0x1401776d6  xor     rcx, rsp; StackCookie
0x1401776d9  call    __security_check_cookie
0x1401776de  add     rsp, 120h
0x1401776e5  pop     r15
0x1401776e7  pop     r13
0x1401776e9  pop     r12
0x1401776eb  pop     rdi
0x1401776ec  pop     rsi
0x1401776ed  pop     rbp
0x1401776ee  pop     rbx
0x1401776ef  retn
0x1401776f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1401776f8  mov     r9d, 26h ; '&'; int
0x1401776fe  mov     qword ptr [rsp+158h+var_130], rbx; char
0x140177703  mov     r8d, 0Eh; int
0x140177709  mov     dl, 4; int
0x14017770b  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x140177710  mov     rcx, [rcx+40h]; int
0x140177714  call    WPP_RECORDER_SF_q
0x140177719  jmp     loc_140177522
0x14017771e  mov     rax, [rbp+0B8h]
0x140177725  mov     rdx, rbp; Irp
0x140177728  movups  xmm0, xmmword ptr [rax]
0x14017772b  movups  xmmword ptr [rax-48h], xmm0
0x14017772f  movups  xmm1, xmmword ptr [rax+10h]
0x140177733  movups  xmmword ptr [rax-38h], xmm1
0x140177737  movups  xmm0, xmmword ptr [rax+20h]
0x14017773b  movups  xmmword ptr [rax-28h], xmm0
0x14017773f  movsd   xmm1, qword ptr [rax+30h]
0x140177744  movsd   qword ptr [rax-18h], xmm1
0x140177749  mov     [rax-45h], r12b
0x14017774d  mov     rcx, [rbx+0F00h]; DeviceObject
0x140177754  call    cs:__imp_IofCallDriver
0x14017775b  nop     dword ptr [rax+rax+00h]
0x140177760  jmp     loc_1401776CE
0x140177765  mov     rcx, cs:WPP_GLOBAL_Control
0x14017776c  mov     r9d, 2Bh ; '+'; int
0x140177772  mov     dword ptr [rsp+158h+var_128], r14d; char
0x140177777  mov     r8d, 0Eh; int
0x14017777d  mov     qword ptr [rsp+158h+var_130], rbx; char
0x140177782  mov     dl, 4; int
0x140177784  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x140177789  mov     rcx, [rcx+40h]; int
0x14017778d  call    WPP_RECORDER_SF_qL
0x140177792  jmp     loc_1401776C3
0x140177797  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x14017779e  jnz     short loc_1401777ED
0x1401777a0  test    cs:byte_14011B002, 40h
0x1401777a7  jnz     short loc_140177820
0x1401777a9  mov     r14d, 0C0000010h
0x1401777af  mov     rcx, rdi; struct _PKG_REF *
0x1401777b2  call    ?ndisDereferencePackage@@YAXPEAU_PKG_REF@@@Z; ndisDereferencePackage(_PKG_REF *)
0x1401777b7  xor     edx, edx; PriorityBoost
0x1401777b9  mov     [rbp+30h], r14d
0x1401777bd  mov     rcx, rbp; Irp
0x1401777c0  call    cs:__imp_IofCompleteRequest
0x1401777c7  nop     dword ptr [rax+rax+00h]
0x1401777cc  jmp     loc_1401776B6
0x1401777d1  xor     edx, edx; PriorityBoost
0x1401777d3  mov     [rbp+30h], r12d
0x1401777d7  mov     rcx, rbp; Irp
0x1401777da  call    cs:__imp_IofCompleteRequest
0x1401777e1  nop     dword ptr [rax+rax+00h]
0x1401777e6  xor     eax, eax
0x1401777e8  jmp     loc_1401776C6
0x1401777ed  mov     eax, [rsi+18h]
0x1401777f0  mov     r9d, 27h ; '''; int
0x1401777f6  mov     dword ptr [rsp+158h+var_120], eax; char
0x1401777fa  mov     r8d, 0Eh; int
0x140177800  mov     dword ptr [rsp+158h+var_128], ecx; char
0x140177804  mov     rcx, cs:WPP_GLOBAL_Control
0x14017780b  mov     qword ptr [rsp+158h+var_130], rbx; char
0x140177810  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x140177815  mov     rcx, [rcx+40h]; int
0x140177819  call    WPP_RECORDER_SF_qLL
0x14017781e  jmp     short loc_1401777A0
0x140177820  mov     eax, [rsi+18h]
0x140177823  lea     r8, [rbx+0FA8h]
0x14017782a  mov     dword ptr [rsp+158h+var_120], eax
0x14017782e  lea     rdx, InvalidSystemPowerState
0x140177835  mov     eax, [rsi+10h]
0x140177838  mov     r9, r8
0x14017783b  mov     dword ptr [rsp+158h+var_128], eax
0x14017783f  mov     rax, [rbx+0FB8h]
0x140177846  mov     qword ptr [rsp+158h+var_130], rax
0x14017784b  mov     eax, [rbx+0FD8h]
0x140177851  mov     [rsp+158h+RemlockSize], eax
0x140177855  call    McTemplateK0jqxqq_EtwWriteTransfer
0x14017785a  jmp     loc_1401777A9
0x14017785f  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x140177866  jz      loc_1401835BC
0x14017786c  mov     rcx, cs:WPP_GLOBAL_Control
0x140177873  mov     r9d, 28h ; '('; int
0x140177879  mov     eax, [rsi+18h]
0x14017787c  mov     r8d, 0Eh; int
0x140177882  mov     dword ptr [rsp+158h+var_128], eax; char
0x140177886  mov     dl, 4; int
0x140177888  mov     qword ptr [rsp+158h+var_130], rbx; char
0x14017788d  mov     rcx, [rcx+40h]; int
0x140177891  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x140177896  call    WPP_RECORDER_SF_qD
0x14017789b  nop
0x14017789c  jmp     loc_1401835BC
0x1401778a1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401778a8  jz      loc_1401775DF
0x1401778ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1401778b5  mov     r9d, 29h ; ')'; int
0x1401778bb  mov     qword ptr [rsp+158h+var_130], rbx; char
0x1401778c0  mov     r8d, 0Eh; int
0x1401778c6  mov     dl, 2; int
0x1401778c8  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x1401778cd  mov     rcx, [rcx+40h]; int
0x1401778d1  call    WPP_RECORDER_SF_q
0x1401778d6  jmp     loc_1401775DF
0x1401778db  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1401778e2  jz      loc_14018360F
0x1401778e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1401778ef  mov     r9d, 2Ah ; '*'; int
0x1401778f5  mov     qword ptr [rsp+158h+var_130], rbx; char
0x1401778fa  mov     r8d, 0Eh; int
0x140177900  mov     dl, 4; int
0x140177902  mov     qword ptr [rsp+158h+RemlockSize], r13; struct _GUID *
0x140177907  mov     rcx, [rcx+40h]; int
0x14017790b  call    WPP_RECORDER_SF_q
0x140177910  nop
0x140177911  jmp     loc_14018360F
0x1401835bc  test    cs:byte_14011B001, 8
0x1401835c3  jz      loc_1401777AF
0x1401835c9  mov     eax, [rsi+18h]
0x1401835cc  lea     r8, [rbx+0FA8h]
0x1401835d3  mov     [rsp+158h+var_118], eax
0x1401835d7  lea     rdx, QueryPowerFailed
0x1401835de  mov     rax, [rbx+0FB8h]
0x1401835e5  mov     r9, r8
0x1401835e8  mov     dword ptr [rsp+158h+var_120], 10001h
0x1401835f0  mov     dword ptr [rsp+158h+var_128], r14d
0x1401835f5  mov     qword ptr [rsp+158h+var_130], rax
0x1401835fa  mov     eax, [rbx+0FD8h]
0x140183600  mov     [rsp+158h+RemlockSize], eax
0x140183604  call    McTemplateK0jqxddq_EtwWriteTransfer
0x140183609  nop
0x14018360a  jmp     loc_1401777AF
0x14018360f  test    cs:byte_14011B001, 8
0x140183616  jz      loc_140177605
0x14018361c  mov     rax, [rbx+0FB8h]
0x140183623  lea     r8, [rbx+0FA8h]
0x14018362a  mov     [rsp+158h+var_118], r12d
0x14018362f  lea     rdx, QueryPowerFailed
0x140183636  mov     dword ptr [rsp+158h+var_120], 10002h
0x14018363e  mov     r9, r8
0x140183641  mov     dword ptr [rsp+158h+var_128], esi
0x140183645  mov     qword ptr [rsp+158h+var_130], rax
0x14018364a  mov     eax, [rbx+0FD8h]
0x140183650  mov     [rsp+158h+RemlockSize], eax
0x140183654  call    McTemplateK0jqxddq_EtwWriteTransfer
0x140183659  nop
0x14018365a  jmp     loc_140177605
```
