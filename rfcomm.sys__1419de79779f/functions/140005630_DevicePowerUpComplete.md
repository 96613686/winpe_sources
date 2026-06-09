# DevicePowerUpComplete

- ea: `0x140005630`
- end: `0x1400056fa`
- name: `DevicePowerUpComplete`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140004a68`
- `0x140005630`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400056db`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400056db`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400056c2`
- `ntoskrnl!PoStartNextPowerIrp` at `0x1400056c2`
- `ntoskrnl!PoSetPowerState` at `0x14000569b`
- `ntoskrnl!PoSetPowerState` at `0x14000569b`

## pseudocode

```c
__int64 __fastcall DevicePowerUpComplete(__int64 a1, IRP *a2)
{
  __int64 v2; // rsi
  _IO_STACK_LOCATION *CurrentStackLocation; // r8
  struct _DEVICE_OBJECT *v5; // rcx
  POWER_STATE_TYPE Type; // edx

  v2 = *(_QWORD *)(a1 + 64);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      3,
      15,
      (__int64)WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids,
      *(_QWORD *)(v2 + 80));
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = *(struct _DEVICE_OBJECT **)(v2 + 80);
  Type = CurrentStackLocation->Parameters.Power.Type;
  LODWORD(CurrentStackLocation) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  *(_DWORD *)(v2 + 104) = (_DWORD)CurrentStackLocation;
  PoSetPowerState(v5, Type, (POWER_STATE)CurrentStackLocation);
  if ( a2->PendingReturned )
    a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  a2->IoStatus.Status = 0;
  PoStartNextPowerIrp(a2);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v2 + 40), a2, 0x20u);
  return 0;
}

```

## disassembly

```asm
0x140005630  mov     r11, rsp
0x140005633  mov     [r11+8], rbx
0x140005637  mov     [r11+10h], rsi
0x14000563b  push    rdi
0x14000563c  sub     rsp, 30h
0x140005640  mov     rsi, [rcx+40h]
0x140005644  mov     rbx, rdx
0x140005647  lea     rax, WPP_RECORDER_INITIALIZED
0x14000564e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140005655  jz      short loc_140005684
0x140005657  mov     rax, [rsi+50h]
0x14000565b  mov     r9d, 0Fh
0x140005661  mov     rcx, cs:WPP_GLOBAL_Control
0x140005668  mov     [r11-10h], rax
0x14000566c  lea     rax, WPP_e15486fb2c2c30e5b5da7d379a643730_Traceguids
0x140005673  mov     [r11-18h], rax
0x140005677  lea     r8d, [r9-0Ch]
0x14000567b  mov     rcx, [rcx+40h]
0x14000567f  call    WPP_RECORDER_SF_q
0x140005684  mov     r8, [rbx+0B8h]
0x14000568b  mov     rcx, [rsi+50h]; DeviceObject
0x14000568f  mov     edx, [r8+10h]; Type
0x140005693  mov     r8d, [r8+18h]; State
0x140005697  mov     [rsi+68h], r8d
0x14000569b  call    cs:__imp_PoSetPowerState
0x1400056a2  nop     dword ptr [rax+rax+00h]
0x1400056a7  cmp     byte ptr [rbx+41h], 0
0x1400056ab  jz      short loc_1400056B8
0x1400056ad  mov     rax, [rbx+0B8h]
0x1400056b4  or      byte ptr [rax+3], 1
0x1400056b8  mov     rcx, rbx; Irp
0x1400056bb  mov     dword ptr [rbx+30h], 0
0x1400056c2  call    cs:__imp_PoStartNextPowerIrp
0x1400056c9  nop     dword ptr [rax+rax+00h]
0x1400056ce  lea     rcx, [rsi+28h]; RemoveLock
0x1400056d2  mov     r8d, 20h ; ' '; RemlockSize
0x1400056d8  mov     rdx, rbx; Tag
0x1400056db  call    cs:__imp_IoReleaseRemoveLockEx
0x1400056e2  nop     dword ptr [rax+rax+00h]
0x1400056e7  mov     rbx, [rsp+38h+arg_0]
0x1400056ec  xor     eax, eax
0x1400056ee  mov     rsi, [rsp+38h+arg_8]
0x1400056f3  add     rsp, 30h
0x1400056f7  pop     rdi
0x1400056f8  retn
```
