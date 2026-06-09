# DevicePowerDownRequestComplete

- ea: `0x140005560`
- end: `0x140005621`
- name: `DevicePowerDownRequestComplete`
- size: `193`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004a68`
- `0x140005560`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000560b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000560b`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400055d4`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400055d4`
- `ntoskrnl!PoSetPowerState` at `0x1400055c2`
- `ntoskrnl!PoSetPowerState` at `0x1400055c2`
- `ntoskrnl!PoCallDriver` at `0x1400055f2`
- `ntoskrnl!PoCallDriver` at `0x1400055f2`

## pseudocode

```c
void __fastcall DevicePowerDownRequestComplete(
        PDEVICE_OBJECT DeviceObject,
        UCHAR MinorFunction,
        POWER_STATE PowerState,
        IRP *Context)
{
  char *DeviceExtension; // rbp
  POWER_STATE v6; // ebx

  DeviceExtension = (char *)DeviceObject->DeviceExtension;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      MinorFunction,
      3,
      14,
      (__int64)WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids,
      *((_QWORD *)DeviceExtension + 10));
  v6.SystemState = (_SYSTEM_POWER_STATE)Context->Tail.Overlay.CurrentStackLocation->Parameters.Power.State;
  PoSetPowerState(*((PDEVICE_OBJECT *)DeviceExtension + 10), SystemPowerState, v6);
  *((POWER_STATE *)DeviceExtension + 27) = v6;
  PoStartNextPowerIrp(Context);
  ++Context->CurrentLocation;
  ++Context->Tail.Overlay.CurrentStackLocation;
  PoCallDriver(*((PDEVICE_OBJECT *)DeviceExtension + 11), Context);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 40), Context, 0x20u);
}

```

## disassembly

```asm
0x140005560  push    rbx
0x140005562  push    rbp
0x140005563  push    rsi
0x140005564  push    rdi
0x140005565  sub     rsp, 38h
0x140005569  mov     rbp, [rcx+40h]
0x14000556d  mov     rsi, r9
0x140005570  lea     rax, WPP_RECORDER_INITIALIZED
0x140005577  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000557e  jz      short loc_1400055AF
0x140005580  mov     rax, [rbp+50h]
0x140005584  mov     r9d, 0Eh
0x14000558a  mov     rcx, cs:WPP_GLOBAL_Control
0x140005591  mov     [rsp+58h+var_30], rax
0x140005596  lea     rax, WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids
0x14000559d  mov     [rsp+58h+var_38], rax
0x1400055a2  lea     r8d, [r9-0Bh]
0x1400055a6  mov     rcx, [rcx+40h]
0x1400055aa  call    WPP_RECORDER_SF_q
0x1400055af  mov     rbx, [rsi+0B8h]
0x1400055b6  xor     edx, edx; Type
0x1400055b8  mov     rcx, [rbp+50h]; DeviceObject
0x1400055bc  mov     ebx, [rbx+18h]
0x1400055bf  mov     r8d, ebx; State
0x1400055c2  call    cs:__imp_PoSetPowerState
0x1400055c9  nop     dword ptr [rax+rax+00h]
0x1400055ce  mov     rcx, rsi; Irp
0x1400055d1  mov     [rbp+6Ch], ebx
0x1400055d4  call    cs:__imp_PoStartNextPowerIrp
0x1400055db  nop     dword ptr [rax+rax+00h]
0x1400055e0  inc     byte ptr [rsi+43h]
0x1400055e3  mov     rdx, rsi; Irp
0x1400055e6  add     qword ptr [rsi+0B8h], 48h ; 'H'
0x1400055ee  mov     rcx, [rbp+58h]; DeviceObject
0x1400055f2  call    cs:__imp_PoCallDriver
0x1400055f9  nop     dword ptr [rax+rax+00h]
0x1400055fe  lea     rcx, [rbp+28h]; RemoveLock
0x140005602  mov     r8d, 20h ; ' '; RemlockSize
0x140005608  mov     rdx, rsi; Tag
0x14000560b  call    cs:__imp_IoReleaseRemoveLockEx
0x140005612  nop     dword ptr [rax+rax+00h]
0x140005617  add     rsp, 38h
0x14000561b  pop     rdi
0x14000561c  pop     rsi
0x14000561d  pop     rbp
0x14000561e  pop     rbx
0x14000561f  retn
```
