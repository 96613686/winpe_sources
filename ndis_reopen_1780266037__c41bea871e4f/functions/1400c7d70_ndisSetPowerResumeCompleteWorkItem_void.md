# ndisSetPowerResumeCompleteWorkItem(void *)

- ea: `0x1400c7d70`
- end: `0x1400c803b`
- name: `?ndisSetPowerResumeCompleteWorkItem@@YAXPEAX@Z`
- size: `715`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x14000dbe0`
- `0x1400416b0`
- `0x1400452c0`
- `0x14005ec80`
- `0x14006ddc0`
- `0x14008bf70`
- `0x1400c796c`
- `0x1400c7d70`
- `0x1400eb380`
- `0x1400eb7c0`
- `0x14014b3e8`
- `0x14015d480`
- `0x140165680`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x1400c7feb`
- `ntoskrnl!PoSetPowerState` at `0x1400c7feb`
- `ntoskrnl!IofCompleteRequest` at `0x1400c7ffc`
- `ntoskrnl!IofCompleteRequest` at `0x1400c7ffc`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c7e4c`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c7e4c`
- `ntoskrnl!KeInitializeEvent` at `0x1400c7e8c`
- `ntoskrnl!KeInitializeEvent` at `0x1400c7e8c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c7fd0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c7fd0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c7fb7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c7fb7`

## pseudocode

```c
void __fastcall ndisSetPowerResumeCompleteWorkItem(_QWORD *a1)
{
  __int64 v1; // rbx
  IRP *v2; // r15
  __int64 v3; // r14
  __int64 v4; // rcx
  int v5; // edi
  int v6; // esi
  int v7; // edx
  __int64 v8; // rcx
  int v9; // edx
  KIRQL v10; // al
  POWER_STATE State; // [rsp+40h] [rbp-C0h] BYREF
  struct _NDIS_OID_REQUEST v12; // [rsp+50h] [rbp-B0h] BYREF

  v1 = a1[4];
  v2 = (IRP *)a1[5];
  v3 = *(_QWORD *)(v1 + 4448);
  State.SystemState = PowerSystemUnspecified;
  memset(&v12, 0, 248);
  NDIS_COUNT_POWER_TRANSITION((struct _NDIS_MINIPORT_BLOCK *)v1, NdisDeviceStateD0);
  if ( (byte_140121001 & 8) != 0 )
    McTemplateK0jqxqq_EtwWriteTransfer(
      v4,
      DevicePowerStateChange,
      v1 + 4008,
      v1 + 4008,
      *(_DWORD *)(v1 + 4056),
      *(_QWORD *)(v1 + 4024),
      1,
      1);
  State.SystemState = PowerSystemWorking;
  memset(&v12, 0, 0xF8u);
  *(_DWORD *)&v12.NdisReserved[16] = 8;
  *(_QWORD *)&v12.NdisReserved[32] = &ndisIntReqGeneric;
  EtwActivityIdControl(3u, (LPGUID)&v12.NdisReserved[96]);
  *(_DWORD *)&v12.NdisReserved[16] |= 0x400u;
  v12.DATA.QUERY_INFORMATION.InformationBuffer = &State;
  v12.Header = (NDIS_OBJECT_HEADER)15466902;
  v12.DATA.QUERY_INFORMATION.Oid = -50265855;
  *(_QWORD *)&v12.RequestType = 1;
  v12.DATA.QUERY_INFORMATION.InformationBufferLength = 4;
  KeInitializeEvent((PRKEVENT)&v12.NdisReserved[40], NotificationEvent, 0);
  v5 = ndisMInvokeOidRequest((struct _NDIS_MINIPORT_BLOCK *)v1, &v12);
  if ( v5 == 259 )
  {
    ndisWaitForKernelObject(&v12.NdisReserved[40]);
    v5 = *(_DWORD *)&v12.NdisReserved[8];
  }
  if ( v5 )
  {
    v6 = -1073741823;
    NdisUnexpectedSsError((struct _NDIS_MINIPORT_BLOCK *)v1, 8u, v5);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = 2;
      WPP_RECORDER_SF_Lq(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v7,
        15,
        30,
        (struct _GUID *)&WPP_b81154d141493d7d4341dde393003738_Traceguids,
        v5,
        v1);
    }
  }
  else
  {
    v8 = *(_QWORD *)(v1 + 4456);
    v6 = 0;
    if ( v8
      && (*(_BYTE *)(v1 + 124) & 0x60) == 0x60
      && (unsigned int)(*(_DWORD *)(v1 + 1272) - 2) <= 2
      && (*(_DWORD *)(v1 + 1004) & 6) != 0
      && *(_BYTE *)(v8 + 1080) )
    {
      ndisRemoveWoLDirectedMAC((struct _NDIS_MINIPORT_BLOCK *)v1);
    }
    ndisSelectiveSuspendResumeOperations((struct _NDIS_MINIPORT_BLOCK *)v1, 1u);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qZ(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v9,
        9,
        31,
        (struct _GUID *)&WPP_b81154d141493d7d4341dde393003738_Traceguids,
        v1,
        *(_QWORD *)(v1 + 3856));
  }
  v2->IoStatus.Status = v6;
  v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v3);
  *(_DWORD *)(v3 + 504) &= ~0x20u;
  KeReleaseSpinLock((PKSPIN_LOCK)v3, v10);
  PoSetPowerState(*(PDEVICE_OBJECT *)(v1 + 3824), DevicePowerState, State);
  IofCompleteRequest(v2, 0);
  ndisSignalD0RequestComplete((struct _NDIS_MINIPORT_BLOCK *)v1, v6);
}

```

## disassembly

```asm
0x1400c7d70  mov     [rsp-8+arg_8], rbx
0x1400c7d75  mov     [rsp-8+arg_10], rsi
0x1400c7d7a  push    rbp
0x1400c7d7b  push    rdi
0x1400c7d7c  push    r13
0x1400c7d7e  push    r14
0x1400c7d80  push    r15
0x1400c7d82  lea     rbp, [rsp-60h]
0x1400c7d87  sub     rsp, 160h
0x1400c7d8e  mov     rax, cs:__security_cookie
0x1400c7d95  xor     rax, rsp
0x1400c7d98  mov     [rbp+80h+var_30], rax
0x1400c7d9c  mov     rbx, [rcx+20h]
0x1400c7da0  xor     edx, edx; Val
0x1400c7da2  mov     r15, [rcx+28h]
0x1400c7da6  mov     r8d, 0F7h; Size
0x1400c7dac  lea     rcx, [rsp+180h+var_130.Header.Revision]; void *
0x1400c7db1  mov     r14, [rbx+1160h]
0x1400c7db8  mov     dword ptr [rsp+180h+State], 0
0x1400c7dc0  mov     [rsp+180h+var_130.Header.Type], 0
0x1400c7dc5  call    memset
0x1400c7dca  mov     r13d, 1
0x1400c7dd0  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c7dd3  mov     edx, r13d; enum _NDIS_DEVICE_POWER_STATE
0x1400c7dd6  call    ?NDIS_COUNT_POWER_TRANSITION@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; NDIS_COUNT_POWER_TRANSITION(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x1400c7ddb  test    cs:byte_140121001, 8
0x1400c7de2  jz      short loc_1400C7E1A
0x1400c7de4  mov     rax, [rbx+0FB8h]
0x1400c7deb  lea     r8, [rbx+0FA8h]
0x1400c7df2  mov     [rsp+180h+var_148], r13d
0x1400c7df7  lea     rdx, DevicePowerStateChange
0x1400c7dfe  mov     dword ptr [rsp+180h+var_150], r13d
0x1400c7e03  mov     r9, r8
0x1400c7e06  mov     qword ptr [rsp+180h+var_158], rax
0x1400c7e0b  mov     eax, [rbx+0FD8h]
0x1400c7e11  mov     dword ptr [rsp+180h+var_160], eax
0x1400c7e15  call    McTemplateK0jqxqq_EtwWriteTransfer
0x1400c7e1a  xor     edx, edx; Val
0x1400c7e1c  mov     dword ptr [rsp+180h+State], r13d
0x1400c7e21  mov     r8d, 0F8h; Size
0x1400c7e27  lea     rcx, [rsp+180h+var_130]; void *
0x1400c7e2c  call    memset
0x1400c7e31  lea     rax, ?ndisIntReqGeneric@@3U_NDIS_INTERNAL_REQUEST_OBJECT@@A; _NDIS_INTERNAL_REQUEST_OBJECT ndisIntReqGeneric
0x1400c7e38  mov     dword ptr [rbp+80h+var_130.NdisReserved+10h], 8
0x1400c7e3f  lea     rdx, [rbp+80h+var_130.NdisReserved+60h]; ActivityId
0x1400c7e43  mov     qword ptr [rbp+80h+var_130.NdisReserved+20h], rax
0x1400c7e47  mov     ecx, 3; ControlCode
0x1400c7e4c  call    cs:__imp_EtwActivityIdControl
0x1400c7e53  nop     dword ptr [rax+rax+00h]
0x1400c7e58  bts     dword ptr [rbp+80h+var_130.NdisReserved+10h], 0Ah
0x1400c7e5d  lea     rax, [rsp+180h+State]
0x1400c7e62  xor     r8d, r8d; State
0x1400c7e65  mov     qword ptr [rsp+180h+var_130.DATA+8], rax
0x1400c7e6a  xor     edx, edx; Type
0x1400c7e6c  mov     dword ptr [rsp+180h+var_130.Header.Type], 0EC0196h
0x1400c7e74  lea     rcx, [rbp+80h+var_130.NdisReserved+28h]; Event
0x1400c7e78  mov     dword ptr [rsp+180h+var_130.DATA], 0FD010101h
0x1400c7e80  mov     qword ptr [rsp+180h+var_130.RequestType], r13
0x1400c7e85  mov     dword ptr [rbp+80h+var_130.DATA+10h], 4
0x1400c7e8c  call    cs:__imp_KeInitializeEvent
0x1400c7e93  nop     dword ptr [rax+rax+00h]
0x1400c7e98  lea     rdx, [rsp+180h+var_130]; struct _NDIS_OID_REQUEST *
0x1400c7e9d  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c7ea0  call    ?ndisMInvokeOidRequest@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_OID_REQUEST@@@Z; ndisMInvokeOidRequest(_NDIS_MINIPORT_BLOCK *,_NDIS_OID_REQUEST *)
0x1400c7ea5  mov     edi, eax
0x1400c7ea7  cmp     eax, 103h
0x1400c7eac  jnz     short loc_1400C7EBA
0x1400c7eae  lea     rcx, [rbp+80h+var_130.NdisReserved+28h]; void *
0x1400c7eb2  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x1400c7eb7  mov     edi, dword ptr [rbp+80h+var_130.NdisReserved+8]
0x1400c7eba  test    edi, edi
0x1400c7ebc  jz      short loc_1400C7F1D
0x1400c7ebe  mov     edx, 8; unsigned __int16
0x1400c7ec3  mov     r8d, edi; int
0x1400c7ec6  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c7ec9  mov     esi, 0C0000001h
0x1400c7ece  call    ?NdisUnexpectedSsError@@YAXPEAU_NDIS_MINIPORT_BLOCK@@GJ@Z; NdisUnexpectedSsError(_NDIS_MINIPORT_BLOCK *,ushort,long)
0x1400c7ed3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c7eda  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c7ee1  jz      loc_1400C7FB0
0x1400c7ee7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c7eee  lea     rax, WPP_b81154d141493d7d4341dde393003738_Traceguids
0x1400c7ef5  mov     r9d, 1Eh; int
0x1400c7efb  mov     qword ptr [rsp+180h+var_150], rbx; char
0x1400c7f00  mov     dword ptr [rsp+180h+var_158], edi; char
0x1400c7f04  mov     dl, 2; int
0x1400c7f06  mov     [rsp+180h+var_160], rax; struct _GUID *
0x1400c7f0b  mov     rcx, [rcx+40h]; int
0x1400c7f0f  lea     r8d, [r9-0Fh]; int
0x1400c7f13  call    WPP_RECORDER_SF_Lq
0x1400c7f18  jmp     loc_1400C7FB0
0x1400c7f1d  mov     rcx, [rbx+1168h]
0x1400c7f24  xor     esi, esi
0x1400c7f26  test    rcx, rcx
0x1400c7f29  jz      short loc_1400C7F5E
0x1400c7f2b  mov     eax, [rbx+7Ch]
0x1400c7f2e  and     eax, 60h
0x1400c7f31  cmp     al, 60h ; '`'
0x1400c7f33  jnz     short loc_1400C7F5E
0x1400c7f35  mov     eax, [rbx+4F8h]
0x1400c7f3b  sub     eax, 2
0x1400c7f3e  cmp     eax, 2
0x1400c7f41  ja      short loc_1400C7F5E
0x1400c7f43  mov     eax, [rbx+3ECh]
0x1400c7f49  test    al, 6
0x1400c7f4b  jz      short loc_1400C7F5E
0x1400c7f4d  cmp     [rcx+438h], sil
0x1400c7f54  jz      short loc_1400C7F5E
0x1400c7f56  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c7f59  call    ?ndisRemoveWoLDirectedMAC@@YAHPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisRemoveWoLDirectedMAC(_NDIS_MINIPORT_BLOCK *)
0x1400c7f5e  mov     dl, r13b; unsigned __int8
0x1400c7f61  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c7f64  call    ?ndisSelectiveSuspendResumeOperations@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisSelectiveSuspendResumeOperations(_NDIS_MINIPORT_BLOCK *,uchar)
0x1400c7f69  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c7f70  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c7f77  jz      short loc_1400C7FB0
0x1400c7f79  mov     rax, [rbx+0F10h]
0x1400c7f80  mov     r9d, 1Fh; int
0x1400c7f86  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c7f8d  mov     qword ptr [rsp+180h+var_150], rax; __int64
0x1400c7f92  lea     rax, WPP_b81154d141493d7d4341dde393003738_Traceguids
0x1400c7f99  mov     qword ptr [rsp+180h+var_158], rbx; char
0x1400c7f9e  lea     r8d, [r9-16h]; int
0x1400c7fa2  mov     [rsp+180h+var_160], rax; struct _GUID *
0x1400c7fa7  mov     rcx, [rcx+40h]; int
0x1400c7fab  call    WPP_RECORDER_SF_qZ
0x1400c7fb0  mov     rcx, r14; SpinLock
0x1400c7fb3  mov     [r15+30h], esi
0x1400c7fb7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400c7fbe  nop     dword ptr [rax+rax+00h]
0x1400c7fc3  and     dword ptr [r14+1F8h], 0FFFFFFDFh
0x1400c7fcb  mov     rcx, r14; SpinLock
0x1400c7fce  mov     dl, al; NewIrql
0x1400c7fd0  call    cs:__imp_KeReleaseSpinLock
0x1400c7fd7  nop     dword ptr [rax+rax+00h]
0x1400c7fdc  mov     r8d, dword ptr [rsp+180h+State]; State
0x1400c7fe1  mov     edx, r13d; Type
0x1400c7fe4  mov     rcx, [rbx+0EF0h]; DeviceObject
0x1400c7feb  call    cs:__imp_PoSetPowerState
0x1400c7ff2  nop     dword ptr [rax+rax+00h]
0x1400c7ff7  xor     edx, edx; PriorityBoost
0x1400c7ff9  mov     rcx, r15; Irp
0x1400c7ffc  call    cs:__imp_IofCompleteRequest
0x1400c8003  nop     dword ptr [rax+rax+00h]
0x1400c8008  mov     edx, esi; int
0x1400c800a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c800d  call    ?ndisSignalD0RequestComplete@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisSignalD0RequestComplete(_NDIS_MINIPORT_BLOCK *,long)
0x1400c8012  mov     rcx, [rbp+80h+var_30]
0x1400c8016  xor     rcx, rsp; StackCookie
0x1400c8019  call    __security_check_cookie
0x1400c801e  lea     r11, [rsp+180h+var_20]
0x1400c8026  mov     rbx, [r11+38h]
0x1400c802a  mov     rsi, [r11+40h]
0x1400c802e  mov     rsp, r11
0x1400c8031  pop     r15
0x1400c8033  pop     r14
0x1400c8035  pop     r13
0x1400c8037  pop     rdi
0x1400c8038  pop     rbp
0x1400c8039  retn
```
