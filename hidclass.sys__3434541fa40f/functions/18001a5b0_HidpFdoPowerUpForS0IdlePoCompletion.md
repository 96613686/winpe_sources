# HidpFdoPowerUpForS0IdlePoCompletion

- ea: `0x18001a5b0`
- end: `0x18001a6a4`
- name: `HidpFdoPowerUpForS0IdlePoCompletion`
- size: `244`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000ddc8`
- `0x180010814`
- `0x18001a5b0`
- `0x18001e8ec`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x18001a5e1`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x18001a5e1`

## pseudocode

```c
void __fastcall HidpFdoPowerUpForS0IdlePoCompletion(
        PDEVICE_OBJECT DeviceObject,
        __int64 MinorFunction,
        __int64 PowerState,
        volatile signed __int32 *Context,
        PIO_STATUS_BLOCK IoStatus)
{
  int Status; // esi
  char v7; // di
  int v8; // edx
  int v9; // r8d

  Status = IoStatus->Status;
  v7 = 1;
  if ( (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(DeviceObject, MinorFunction, PowerState) )
  {
    KeQuerySystemTimePrecise(Context + 560);
    if ( (Context[442] & 0x14) != 0 )
      _InterlockedAdd(Context + 570, 1u);
  }
  HIDSM_AddHidsmEvent(Context, 2002);
  if ( Status >= 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v7 = 0;
    }
    if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = v7;
      LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v8,
        v9,
        *((_QWORD *)Context + 84),
        4,
        9,
        44,
        (__int64)WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids,
        *(_QWORD *)Context,
        Status);
    }
  }
}

```

## disassembly

```asm
0x18001a5b0  mov     [rsp+arg_0], rbx
0x18001a5b5  mov     [rsp+arg_8], rsi
0x18001a5ba  push    rdi
0x18001a5bb  sub     rsp, 50h
0x18001a5bf  mov     rax, [rsp+58h+IoStatus]
0x18001a5c7  mov     rbx, r9
0x18001a5ca  mov     esi, [rax]
0x18001a5cc  call    Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline
0x18001a5d1  mov     edi, 1
0x18001a5d6  test    eax, eax
0x18001a5d8  jz      short loc_18001A5FE
0x18001a5da  lea     rcx, [rbx+8C0h]
0x18001a5e1  call    cs:__imp_KeQuerySystemTimePrecise
0x18001a5e8  nop     dword ptr [rax+rax+00h]
0x18001a5ed  mov     eax, [rbx+6E8h]
0x18001a5f3  test    al, 14h
0x18001a5f5  jz      short loc_18001A5FE
0x18001a5f7  lock add [rbx+8E8h], edi
0x18001a5fe  mov     edx, 7D2h
0x18001a603  mov     rcx, rbx
0x18001a606  call    HIDSM_AddHidsmEvent
0x18001a60b  test    esi, esi
0x18001a60d  js      loc_18001A693
0x18001a613  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a61a  lea     rax, WPP_GLOBAL_Control
0x18001a621  cmp     rcx, rax
0x18001a624  jz      short loc_18001A635
0x18001a626  test    dword ptr [rcx+2Ch], 100h
0x18001a62d  jz      short loc_18001A635
0x18001a62f  cmp     byte ptr [rcx+29h], 4
0x18001a633  jnb     short loc_18001A638
0x18001a635  xor     dil, dil
0x18001a638  lea     rax, WPP_RECORDER_INITIALIZED
0x18001a63f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001a646  setnz   r8b
0x18001a64a  test    dil, dil
0x18001a64d  jnz     short loc_18001A654
0x18001a64f  test    r8b, r8b
0x18001a652  jz      short loc_18001A693
0x18001a654  mov     rax, [rbx]
0x18001a657  mov     dl, dil
0x18001a65a  mov     r9, [rbx+2A0h]
0x18001a661  mov     rcx, [rcx+18h]
0x18001a665  mov     [rsp+58h+var_10], esi
0x18001a669  mov     [rsp+58h+var_18], rax
0x18001a66e  lea     rax, WPP_6b932ec2eebc3f4dfedaae6e204fdc15_Traceguids
0x18001a675  mov     [rsp+58h+var_20], rax
0x18001a67a  mov     [rsp+58h+var_28], 2Ch ; ','
0x18001a681  mov     [rsp+58h+var_30], 9
0x18001a689  mov     [rsp+58h+var_38], 4
0x18001a68e  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18001a693  mov     rbx, [rsp+58h+arg_0]
0x18001a698  mov     rsi, [rsp+58h+arg_8]
0x18001a69d  add     rsp, 50h
0x18001a6a1  pop     rdi
0x18001a6a2  retn
```
