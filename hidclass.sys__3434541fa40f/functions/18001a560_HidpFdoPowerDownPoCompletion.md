# HidpFdoPowerDownPoCompletion

- ea: `0x18001a560`
- end: `0x18001a5a3`
- name: `HidpFdoPowerDownPoCompletion`
- size: `67`
- prototype: `REQUEST_POWER_COMPLETE`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180009bec`
- `0x180010814`
- `0x18001a560`
- `0x18001e8ec`

## import_xrefs

- `ntoskrnl!KeQuerySystemTimePrecise` at `0x18001a579`
- `ntoskrnl!KeQuerySystemTimePrecise` at `0x18001a579`

## pseudocode

```c
void __fastcall HidpFdoPowerDownPoCompletion(
        PDEVICE_OBJECT DeviceObject,
        __int64 MinorFunction,
        __int64 PowerState,
        char *Context)
{
  if ( (unsigned int)Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline(DeviceObject, MinorFunction, PowerState) )
    KeQuerySystemTimePrecise(Context + 2232);
  HidpFdoCompleteSIrp(Context, 0);
  HIDSM_AddHidsmEvent(Context, 2006);
}

```

## disassembly

```asm
0x18001a560  push    rbx
0x18001a562  sub     rsp, 20h
0x18001a566  mov     rbx, r9
0x18001a569  call    Feature_HPPICNS__private_IsEnabledDeviceUsageNoInline
0x18001a56e  test    eax, eax
0x18001a570  jz      short loc_18001A585
0x18001a572  lea     rcx, [rbx+8B8h]
0x18001a579  call    cs:__imp_KeQuerySystemTimePrecise
0x18001a580  nop     dword ptr [rax+rax+00h]
0x18001a585  xor     edx, edx
0x18001a587  mov     rcx, rbx
0x18001a58a  call    HidpFdoCompleteSIrp
0x18001a58f  mov     edx, 7D6h
0x18001a594  mov     rcx, rbx
0x18001a597  call    HIDSM_AddHidsmEvent
0x18001a59c  add     rsp, 20h
0x18001a5a0  pop     rbx
0x18001a5a1  retn
```
