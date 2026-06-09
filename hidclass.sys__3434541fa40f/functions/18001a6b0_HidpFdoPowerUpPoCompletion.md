# HidpFdoPowerUpPoCompletion

- ea: `0x18001a6b0`
- end: `0x18001a700`
- name: `HidpFdoPowerUpPoCompletion`
- size: `80`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009bec`
- `0x180010814`
- `0x18001a6b0`
- `0x18001e8ec`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x18001a6c9`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x18001a6c9`

## pseudocode

```c
void __fastcall HidpFdoPowerUpPoCompletion(
        PDEVICE_OBJECT DeviceObject,
        __int64 MinorFunction,
        __int64 PowerState,
        _QWORD *Context)
{
  if ( (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(DeviceObject, MinorFunction, PowerState) )
    KeQuerySystemTimePrecise(Context + 280);
  if ( *(_BYTE *)(Context[1] + 297LL) == 1 )
    HidpFdoCompleteSIrp(Context, 0);
  HIDSM_AddHidsmEvent(Context, 2002);
}

```

## disassembly

```asm
0x18001a6b0  push    rbx
0x18001a6b2  sub     rsp, 20h
0x18001a6b6  mov     rbx, r9
0x18001a6b9  call    Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline
0x18001a6be  test    eax, eax
0x18001a6c0  jz      short loc_18001A6D5
0x18001a6c2  lea     rcx, [rbx+8C0h]
0x18001a6c9  call    cs:__imp_KeQuerySystemTimePrecise
0x18001a6d0  nop     dword ptr [rax+rax+00h]
0x18001a6d5  mov     rax, [rbx+8]
0x18001a6d9  cmp     byte ptr [rax+129h], 1
0x18001a6e0  jnz     short loc_18001A6EC
0x18001a6e2  xor     edx, edx
0x18001a6e4  mov     rcx, rbx
0x18001a6e7  call    HidpFdoCompleteSIrp
0x18001a6ec  mov     edx, 7D2h
0x18001a6f1  mov     rcx, rbx
0x18001a6f4  call    HIDSM_AddHidsmEvent
0x18001a6f9  add     rsp, 20h
0x18001a6fd  pop     rbx
0x18001a6fe  retn
```
