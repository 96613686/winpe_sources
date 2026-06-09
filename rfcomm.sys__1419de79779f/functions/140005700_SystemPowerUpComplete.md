# SystemPowerUpComplete

- ea: `0x140005700`
- end: `0x1400057f4`
- name: `SystemPowerUpComplete`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004a68`
- `0x140005700`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400057d9`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400057d9`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400057c0`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400057c0`
- `ntoskrnl!PoSetPowerState` at `0x14000573d`
- `ntoskrnl!PoSetPowerState` at `0x14000573d`
- `ntoskrnl!PoRequestPowerIrp` at `0x1400057a7`
- `ntoskrnl!PoRequestPowerIrp` at `0x1400057a7`

## pseudocode

```c
__int64 __fastcall SystemPowerUpComplete(__int64 a1, IRP *a2)
{
  __int64 v3; // rdi
  _IO_STACK_LOCATION *CurrentStackLocation; // r8
  POWER_STATE_TYPE Type; // edx
  POWER_STATE v6; // r8d
  struct _DEVICE_OBJECT *v7; // rcx
  int v8; // edx
  NTSTATUS v9; // eax
  NTSTATUS v10; // ecx

  v3 = *(_QWORD *)(a1 + 64);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( a2->PendingReturned )
    CurrentStackLocation->Control |= 1u;
  if ( a2->IoStatus.Status >= 0 )
  {
    Type = CurrentStackLocation->Parameters.Power.Type;
    v6.SystemState = (_SYSTEM_POWER_STATE)CurrentStackLocation->Parameters.Power.State;
    v7 = *(struct _DEVICE_OBJECT **)(v3 + 80);
    *(POWER_STATE *)(v3 + 108) = v6;
    PoSetPowerState(v7, Type, v6);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        3,
        16,
        (__int64)WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids,
        *(_QWORD *)(v3 + 80));
    v9 = PoRequestPowerIrp(*(PDEVICE_OBJECT *)(v3 + 80), 2u, (POWER_STATE)1, 0, 0, 0);
    v10 = 0;
    if ( v9 < 0 )
      v10 = v9;
    a2->IoStatus.Status = v10;
  }
  PoStartNextPowerIrp(a2);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 40), a2, 0x20u);
  return (unsigned int)a2->IoStatus.Status;
}

```

## disassembly

```asm
0x140005700  mov     [rsp+arg_0], rbx
0x140005705  push    rdi
0x140005706  sub     rsp, 30h
0x14000570a  cmp     byte ptr [rdx+41h], 0
0x14000570e  mov     rbx, rdx
0x140005711  mov     rdi, [rcx+40h]
0x140005715  mov     r8, [rdx+0B8h]
0x14000571c  jz      short loc_140005723
0x14000571e  or      byte ptr [r8+3], 1
0x140005723  cmp     dword ptr [rdx+30h], 0
0x140005727  jl      loc_1400057BD
0x14000572d  mov     edx, [r8+10h]; Type
0x140005731  mov     r8d, [r8+18h]; State
0x140005735  mov     rcx, [rdi+50h]; DeviceObject
0x140005739  mov     [rdi+6Ch], r8d
0x14000573d  call    cs:__imp_PoSetPowerState
0x140005744  nop     dword ptr [rax+rax+00h]
0x140005749  lea     rax, WPP_RECORDER_INITIALIZED
0x140005750  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005757  jz      short loc_140005788
0x140005759  mov     rax, [rdi+50h]
0x14000575d  mov     r9d, 10h
0x140005763  mov     rcx, cs:WPP_GLOBAL_Control
0x14000576a  mov     [rsp+38h+Irp], rax
0x14000576f  lea     rax, WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids
0x140005776  mov     [rsp+38h+Context], rax
0x14000577b  lea     r8d, [r9-0Dh]
0x14000577f  mov     rcx, [rcx+40h]
0x140005783  call    WPP_RECORDER_SF_q
0x140005788  mov     rcx, [rdi+50h]; DeviceObject
0x14000578c  xor     r9d, r9d; CompletionFunction
0x14000578f  mov     [rsp+38h+Irp], 0; Irp
0x140005798  mov     dl, 2; MinorFunction
0x14000579a  mov     [rsp+38h+Context], 0; Context
0x1400057a3  lea     r8d, [r9+1]; PowerState
0x1400057a7  call    cs:__imp_PoRequestPowerIrp
0x1400057ae  nop     dword ptr [rax+rax+00h]
0x1400057b3  xor     ecx, ecx
0x1400057b5  test    eax, eax
0x1400057b7  cmovs   ecx, eax
0x1400057ba  mov     [rbx+30h], ecx
0x1400057bd  mov     rcx, rbx; Irp
0x1400057c0  call    cs:__imp_PoStartNextPowerIrp
0x1400057c7  nop     dword ptr [rax+rax+00h]
0x1400057cc  lea     rcx, [rdi+28h]; RemoveLock
0x1400057d0  mov     r8d, 20h ; ' '; RemlockSize
0x1400057d6  mov     rdx, rbx; Tag
0x1400057d9  call    cs:__imp_IoReleaseRemoveLockEx
0x1400057e0  nop     dword ptr [rax+rax+00h]
0x1400057e5  mov     eax, [rbx+30h]
0x1400057e8  mov     rbx, [rsp+38h+arg_0]
0x1400057ed  add     rsp, 30h
0x1400057f1  pop     rdi
0x1400057f2  retn
```
