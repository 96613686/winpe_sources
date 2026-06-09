# ndisSetPowerResumeCompleteWorkItem(void *)

- ea: `0x1400c2b90`
- end: `0x1400c2e5b`
- name: `?ndisSetPowerResumeCompleteWorkItem@@YAXPEAX@Z`
- size: `715`
- prototype: `void __fastcall(void *)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x140015170`
- `0x140019b40`
- `0x14003ef00`
- `0x1400423f0`
- `0x140068220`
- `0x140086c80`
- `0x1400c253c`
- `0x1400c2b90`
- `0x1400e6160`
- `0x1400e65c0`
- `0x140144448`
- `0x1401564e0`
- `0x14015e6f0`

## import_xrefs

- `ntoskrnl!PoSetPowerState` at `0x1400c2e0b`
- `ntoskrnl!PoSetPowerState` at `0x1400c2e0b`
- `ntoskrnl!IofCompleteRequest` at `0x1400c2e1c`
- `ntoskrnl!IofCompleteRequest` at `0x1400c2e1c`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c2c6c`
- `ntoskrnl!EtwActivityIdControl` at `0x1400c2c6c`
- `ntoskrnl!KeInitializeEvent` at `0x1400c2cac`
- `ntoskrnl!KeInitializeEvent` at `0x1400c2cac`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c2df0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c2df0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c2dd7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c2dd7`

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
  if ( (byte_14011B001 & 8) != 0 )
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
        (struct _GUID *)&WPP_63e371e5a248373aa5c809d99c379eef_Traceguids,
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
        (struct _GUID *)&WPP_63e371e5a248373aa5c809d99c379eef_Traceguids,
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
0x1400c2b90  mov     [rsp-8+arg_8], rbx
0x1400c2b95  mov     [rsp-8+arg_10], rsi
0x1400c2b9a  push    rbp
0x1400c2b9b  push    rdi
0x1400c2b9c  push    r13
0x1400c2b9e  push    r14
0x1400c2ba0  push    r15
0x1400c2ba2  lea     rbp, [rsp-60h]
0x1400c2ba7  sub     rsp, 160h
0x1400c2bae  mov     rax, cs:__security_cookie
0x1400c2bb5  xor     rax, rsp
0x1400c2bb8  mov     [rbp+80h+var_30], rax
0x1400c2bbc  mov     rbx, [rcx+20h]
0x1400c2bc0  xor     edx, edx; Val
0x1400c2bc2  mov     r15, [rcx+28h]
0x1400c2bc6  mov     r8d, 0F7h; Size
0x1400c2bcc  lea     rcx, [rsp+180h+var_130.Header.Revision]; void *
0x1400c2bd1  mov     r14, [rbx+1160h]
0x1400c2bd8  mov     dword ptr [rsp+180h+State], 0
0x1400c2be0  mov     [rsp+180h+var_130.Header.Type], 0
0x1400c2be5  call    memset
0x1400c2bea  mov     r13d, 1
0x1400c2bf0  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c2bf3  mov     edx, r13d; enum _NDIS_DEVICE_POWER_STATE
0x1400c2bf6  call    ?NDIS_COUNT_POWER_TRANSITION@@YAXPEAU_NDIS_MINIPORT_BLOCK@@W4_NDIS_DEVICE_POWER_STATE@@@Z; NDIS_COUNT_POWER_TRANSITION(_NDIS_MINIPORT_BLOCK *,_NDIS_DEVICE_POWER_STATE)
0x1400c2bfb  test    cs:byte_14011B001, 8
0x1400c2c02  jz      short loc_1400C2C3A
0x1400c2c04  mov     rax, [rbx+0FB8h]
0x1400c2c0b  lea     r8, [rbx+0FA8h]
0x1400c2c12  mov     [rsp+180h+var_148], r13d
0x1400c2c17  lea     rdx, DevicePowerStateChange
0x1400c2c1e  mov     dword ptr [rsp+180h+var_150], r13d
0x1400c2c23  mov     r9, r8
0x1400c2c26  mov     qword ptr [rsp+180h+var_158], rax
0x1400c2c2b  mov     eax, [rbx+0FD8h]
0x1400c2c31  mov     dword ptr [rsp+180h+var_160], eax
0x1400c2c35  call    McTemplateK0jqxqq_EtwWriteTransfer
0x1400c2c3a  xor     edx, edx; Val
0x1400c2c3c  mov     dword ptr [rsp+180h+State], r13d
0x1400c2c41  mov     r8d, 0F8h; Size
0x1400c2c47  lea     rcx, [rsp+180h+var_130]; void *
0x1400c2c4c  call    memset
0x1400c2c51  lea     rax, ?ndisIntReqGeneric@@3U_NDIS_INTERNAL_REQUEST_OBJECT@@A; _NDIS_INTERNAL_REQUEST_OBJECT ndisIntReqGeneric
0x1400c2c58  mov     dword ptr [rbp+80h+var_130.NdisReserved+10h], 8
0x1400c2c5f  lea     rdx, [rbp+80h+var_130.NdisReserved+60h]; ActivityId
0x1400c2c63  mov     qword ptr [rbp+80h+var_130.NdisReserved+20h], rax
0x1400c2c67  mov     ecx, 3; ControlCode
0x1400c2c6c  call    cs:__imp_EtwActivityIdControl
0x1400c2c73  nop     dword ptr [rax+rax+00h]
0x1400c2c78  bts     dword ptr [rbp+80h+var_130.NdisReserved+10h], 0Ah
0x1400c2c7d  lea     rax, [rsp+180h+State]
0x1400c2c82  xor     r8d, r8d; State
0x1400c2c85  mov     qword ptr [rsp+180h+var_130.DATA+8], rax
0x1400c2c8a  xor     edx, edx; Type
0x1400c2c8c  mov     dword ptr [rsp+180h+var_130.Header.Type], 0EC0196h
0x1400c2c94  lea     rcx, [rbp+80h+var_130.NdisReserved+28h]; Event
0x1400c2c98  mov     dword ptr [rsp+180h+var_130.DATA], 0FD010101h
0x1400c2ca0  mov     qword ptr [rsp+180h+var_130.RequestType], r13
0x1400c2ca5  mov     dword ptr [rbp+80h+var_130.DATA+10h], 4
0x1400c2cac  call    cs:__imp_KeInitializeEvent
0x1400c2cb3  nop     dword ptr [rax+rax+00h]
0x1400c2cb8  lea     rdx, [rsp+180h+var_130]; struct _NDIS_OID_REQUEST *
0x1400c2cbd  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c2cc0  call    ?ndisMInvokeOidRequest@@YAHPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_OID_REQUEST@@@Z; ndisMInvokeOidRequest(_NDIS_MINIPORT_BLOCK *,_NDIS_OID_REQUEST *)
0x1400c2cc5  mov     edi, eax
0x1400c2cc7  cmp     eax, 103h
0x1400c2ccc  jnz     short loc_1400C2CDA
0x1400c2cce  lea     rcx, [rbp+80h+var_130.NdisReserved+28h]; void *
0x1400c2cd2  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x1400c2cd7  mov     edi, dword ptr [rbp+80h+var_130.NdisReserved+8]
0x1400c2cda  test    edi, edi
0x1400c2cdc  jz      short loc_1400C2D3D
0x1400c2cde  mov     edx, 8; unsigned __int16
0x1400c2ce3  mov     r8d, edi; int
0x1400c2ce6  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c2ce9  mov     esi, 0C0000001h
0x1400c2cee  call    ?NdisUnexpectedSsError@@YAXPEAU_NDIS_MINIPORT_BLOCK@@GJ@Z; NdisUnexpectedSsError(_NDIS_MINIPORT_BLOCK *,ushort,long)
0x1400c2cf3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c2cfa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c2d01  jz      loc_1400C2DD0
0x1400c2d07  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c2d0e  lea     rax, WPP_63e371e5a248373aa5c809d99c379eef_Traceguids
0x1400c2d15  mov     r9d, 1Eh; int
0x1400c2d1b  mov     qword ptr [rsp+180h+var_150], rbx; char
0x1400c2d20  mov     dword ptr [rsp+180h+var_158], edi; char
0x1400c2d24  mov     dl, 2; int
0x1400c2d26  mov     [rsp+180h+var_160], rax; struct _GUID *
0x1400c2d2b  mov     rcx, [rcx+40h]; int
0x1400c2d2f  lea     r8d, [r9-0Fh]; int
0x1400c2d33  call    WPP_RECORDER_SF_Lq
0x1400c2d38  jmp     loc_1400C2DD0
0x1400c2d3d  mov     rcx, [rbx+1168h]
0x1400c2d44  xor     esi, esi
0x1400c2d46  test    rcx, rcx
0x1400c2d49  jz      short loc_1400C2D7E
0x1400c2d4b  mov     eax, [rbx+7Ch]
0x1400c2d4e  and     eax, 60h
0x1400c2d51  cmp     al, 60h ; '`'
0x1400c2d53  jnz     short loc_1400C2D7E
0x1400c2d55  mov     eax, [rbx+4F8h]
0x1400c2d5b  sub     eax, 2
0x1400c2d5e  cmp     eax, 2
0x1400c2d61  ja      short loc_1400C2D7E
0x1400c2d63  mov     eax, [rbx+3ECh]
0x1400c2d69  test    al, 6
0x1400c2d6b  jz      short loc_1400C2D7E
0x1400c2d6d  cmp     [rcx+438h], sil
0x1400c2d74  jz      short loc_1400C2D7E
0x1400c2d76  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c2d79  call    ?ndisRemoveWoLDirectedMAC@@YAHPEAU_NDIS_MINIPORT_BLOCK@@@Z; ndisRemoveWoLDirectedMAC(_NDIS_MINIPORT_BLOCK *)
0x1400c2d7e  mov     dl, r13b; unsigned __int8
0x1400c2d81  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c2d84  call    ?ndisSelectiveSuspendResumeOperations@@YAXPEAU_NDIS_MINIPORT_BLOCK@@E@Z; ndisSelectiveSuspendResumeOperations(_NDIS_MINIPORT_BLOCK *,uchar)
0x1400c2d89  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400c2d90  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400c2d97  jz      short loc_1400C2DD0
0x1400c2d99  mov     rax, [rbx+0F10h]
0x1400c2da0  mov     r9d, 1Fh; int
0x1400c2da6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400c2dad  mov     qword ptr [rsp+180h+var_150], rax; __int64
0x1400c2db2  lea     rax, WPP_63e371e5a248373aa5c809d99c379eef_Traceguids
0x1400c2db9  mov     qword ptr [rsp+180h+var_158], rbx; char
0x1400c2dbe  lea     r8d, [r9-16h]; int
0x1400c2dc2  mov     [rsp+180h+var_160], rax; struct _GUID *
0x1400c2dc7  mov     rcx, [rcx+40h]; int
0x1400c2dcb  call    WPP_RECORDER_SF_qZ
0x1400c2dd0  mov     rcx, r14; SpinLock
0x1400c2dd3  mov     [r15+30h], esi
0x1400c2dd7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400c2dde  nop     dword ptr [rax+rax+00h]
0x1400c2de3  and     dword ptr [r14+1F8h], 0FFFFFFDFh
0x1400c2deb  mov     rcx, r14; SpinLock
0x1400c2dee  mov     dl, al; NewIrql
0x1400c2df0  call    cs:__imp_KeReleaseSpinLock
0x1400c2df7  nop     dword ptr [rax+rax+00h]
0x1400c2dfc  mov     r8d, dword ptr [rsp+180h+State]; State
0x1400c2e01  mov     edx, r13d; Type
0x1400c2e04  mov     rcx, [rbx+0EF0h]; DeviceObject
0x1400c2e0b  call    cs:__imp_PoSetPowerState
0x1400c2e12  nop     dword ptr [rax+rax+00h]
0x1400c2e17  xor     edx, edx; PriorityBoost
0x1400c2e19  mov     rcx, r15; Irp
0x1400c2e1c  call    cs:__imp_IofCompleteRequest
0x1400c2e23  nop     dword ptr [rax+rax+00h]
0x1400c2e28  mov     edx, esi; int
0x1400c2e2a  mov     rcx, rbx; struct _NDIS_MINIPORT_BLOCK *
0x1400c2e2d  call    ?ndisSignalD0RequestComplete@@YAXPEAU_NDIS_MINIPORT_BLOCK@@J@Z; ndisSignalD0RequestComplete(_NDIS_MINIPORT_BLOCK *,long)
0x1400c2e32  mov     rcx, [rbp+80h+var_30]
0x1400c2e36  xor     rcx, rsp; StackCookie
0x1400c2e39  call    __security_check_cookie
0x1400c2e3e  lea     r11, [rsp+180h+var_20]
0x1400c2e46  mov     rbx, [r11+38h]
0x1400c2e4a  mov     rsi, [r11+40h]
0x1400c2e4e  mov     rsp, r11
0x1400c2e51  pop     r15
0x1400c2e53  pop     r14
0x1400c2e55  pop     r13
0x1400c2e57  pop     rdi
0x1400c2e58  pop     rbp
0x1400c2e59  retn
```
