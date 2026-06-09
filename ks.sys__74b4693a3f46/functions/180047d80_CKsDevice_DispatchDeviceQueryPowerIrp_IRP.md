# CKsDevice::DispatchDeviceQueryPowerIrp(_IRP *)

- ea: `0x180047d80`
- end: `0x180047e8b`
- name: `?DispatchDeviceQueryPowerIrp@CKsDevice@@AEAAJPEAU_IRP@@@Z`
- size: `267`
- prototype: `int(CKsDevice *__hidden this, struct _IRP *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180047030`

## callees

- `0x18000b7bc`
- `0x180019c60`
- `0x180047d80`

## import_xrefs

- `ntoskrnl!PoCallDriver` at `0x180047e26`
- `ntoskrnl!PoCallDriver` at `0x180047e26`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047e01`
- `ntoskrnl!PoStartNextPowerIrp` at `0x180047e01`
- `ntoskrnl!IofCompleteRequest` at `0x180047e43`
- `ntoskrnl!IofCompleteRequest` at `0x180047e43`

## pseudocode

```c
NTSTATUS __fastcall CKsDevice::DispatchDeviceQueryPowerIrp(CKsDevice *this, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  int v3; // edi
  struct _IRP *v4; // rbx
  const _KSDEVICE_DESCRIPTOR *Descriptor; // rax
  int (__fastcall *QueryPower)(_KSDEVICE *, _IRP *, _DEVICE_POWER_STATE, _DEVICE_POWER_STATE, _SYSTEM_POWER_STATE, _SYSTEM_POWER_STATE, POWER_ACTION); // r10

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v3 = 0;
  v4 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      108,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  Descriptor = this->m_Ext.Public.Descriptor;
  if ( Descriptor )
  {
    if ( Descriptor->Dispatch )
    {
      QueryPower = Descriptor->Dispatch->QueryPower;
      if ( QueryPower )
        v3 = QueryPower(
               &this->m_Ext.Public,
               v4,
               CurrentStackLocation->Parameters.Power.State.DeviceState,
               this->m_Ext.Public.DevicePowerState,
               PowerSystemUnspecified,
               PowerSystemUnspecified,
               CurrentStackLocation->Parameters.Power.ShutdownType);
    }
  }
  v4->IoStatus.Status = v3;
  PoStartNextPowerIrp(v4);
  if ( v3 < 0 )
  {
    IofCompleteRequest(v4, 0);
    return v3;
  }
  else
  {
    ++v4->CurrentLocation;
    ++v4->Tail.Overlay.CurrentStackLocation;
    return PoCallDriver(this->m_Ext.Public.NextDeviceObject, v4);
  }
}

```

## disassembly

```asm
0x180047d80  push    rbx
0x180047d82  push    rbp
0x180047d83  push    rsi
0x180047d84  push    rdi
0x180047d85  push    r14
0x180047d87  sub     rsp, 40h
0x180047d8b  mov     rbp, [rdx+0B8h]
0x180047d92  xor     r14d, r14d
0x180047d95  mov     edi, r14d
0x180047d98  mov     rbx, rdx
0x180047d9b  mov     rsi, rcx
0x180047d9e  lea     rax, WPP_RECORDER_INITIALIZED
0x180047da5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180047dac  jnz     loc_180047E53
0x180047db2  lea     rcx, [rsi+0C8h]
0x180047db9  mov     rax, [rcx]
0x180047dbc  test    rax, rax
0x180047dbf  jz      short loc_180047DFB
0x180047dc1  mov     rdx, [rax]
0x180047dc4  test    rdx, rdx
0x180047dc7  jz      short loc_180047DFB
0x180047dc9  mov     r10, [rdx+58h]
0x180047dcd  test    r10, r10
0x180047dd0  jz      short loc_180047DFB
0x180047dd2  mov     eax, [rbp+20h]
0x180047dd5  mov     rdx, rbx
0x180047dd8  mov     r9d, [rsi+100h]
0x180047ddf  mov     r8d, [rbp+18h]
0x180047de3  mov     [rsp+68h+var_38], eax
0x180047de7  mov     rax, r10
0x180047dea  mov     [rsp+68h+var_40], r14d
0x180047def  mov     dword ptr [rsp+68h+var_48], r14d
0x180047df4  call    _guard_dispatch_icall
0x180047df9  mov     edi, eax
0x180047dfb  mov     rcx, rbx; Irp
0x180047dfe  mov     [rbx+30h], edi
0x180047e01  call    cs:__imp_PoStartNextPowerIrp
0x180047e08  nop     dword ptr [rax+rax+00h]
0x180047e0d  test    edi, edi
0x180047e0f  js      short loc_180047E3E
0x180047e11  inc     byte ptr [rbx+43h]
0x180047e14  mov     rdx, rbx; Irp
0x180047e17  add     qword ptr [rbx+0B8h], 48h ; 'H'
0x180047e1f  mov     rcx, [rsi+0F0h]; DeviceObject
0x180047e26  call    cs:__imp_PoCallDriver
0x180047e2d  nop     dword ptr [rax+rax+00h]
0x180047e32  add     rsp, 40h
0x180047e36  pop     r14
0x180047e38  pop     rdi
0x180047e39  pop     rsi
0x180047e3a  pop     rbp
0x180047e3b  pop     rbx
0x180047e3c  retn
0x180047e3e  xor     edx, edx; PriorityBoost
0x180047e40  mov     rcx, rbx; Irp
0x180047e43  call    cs:__imp_IofCompleteRequest
0x180047e4a  nop     dword ptr [rax+rax+00h]
0x180047e4f  mov     eax, edi
0x180047e51  jmp     short loc_180047E32
0x180047e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180047e5a  cmp     [rcx+48h], r14w
0x180047e5f  jz      loc_180047DB2
0x180047e65  mov     rcx, [rcx+40h]
0x180047e69  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x180047e70  mov     r9d, 6Ch ; 'l'
0x180047e76  mov     [rsp+68h+var_48], rax
0x180047e7b  mov     dl, 5
0x180047e7d  lea     r8d, [r9-6Bh]
0x180047e81  call    WPP_RECORDER_SF_
0x180047e86  jmp     loc_180047DB2
```
