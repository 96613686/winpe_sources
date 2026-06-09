# PcpDisableRegistryNotification

- ea: `0x14001fa50`
- end: `0x14001fadd`
- name: `PcpDisableRegistryNotification`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001fd60`
- `0x14001fec0`

## callees

- `0x14001fa50`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14001fa84`
- `ntoskrnl!ZwClose` at `0x14001fa84`
- `ntoskrnl!KeSetEvent` at `0x14001faa7`
- `ntoskrnl!KeSetEvent` at `0x14001faa7`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fa6c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001facb`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001fa6c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001facb`

## pseudocode

```c
NTSTATUS PcpDisableRegistryNotification()
{
  KeWaitForSingleObject(&PcgRegistryStateLock, Executive, 0, 0, 0);
  if ( PcgPolicyKeyHandle )
  {
    ZwClose(PcgPolicyKeyHandle);
    PcgPolicyKeyHandle = 0;
  }
  KeSetEvent(&PcgRegistryStateLock, 0, 0);
  return KeWaitForSingleObject(&PcgRegistryCompletionEvent, Executive, 0, 0, 0);
}

```

## disassembly

```asm
0x14001fa50  sub     rsp, 38h
0x14001fa54  xor     r9d, r9d; Alertable
0x14001fa57  mov     [rsp+38h+Timeout], 0; Timeout
0x14001fa60  xor     r8d, r8d; WaitMode
0x14001fa63  lea     rcx, PcgRegistryStateLock; Object
0x14001fa6a  xor     edx, edx; WaitReason
0x14001fa6c  call    cs:__imp_KeWaitForSingleObject
0x14001fa73  nop     dword ptr [rax+rax+00h]
0x14001fa78  mov     rcx, cs:PcgPolicyKeyHandle; Handle
0x14001fa7f  test    rcx, rcx
0x14001fa82  jz      short loc_14001FA9B
0x14001fa84  call    cs:__imp_ZwClose
0x14001fa8b  nop     dword ptr [rax+rax+00h]
0x14001fa90  mov     cs:PcgPolicyKeyHandle, 0
0x14001fa9b  xor     r8d, r8d; Wait
0x14001fa9e  lea     rcx, PcgRegistryStateLock; Event
0x14001faa5  xor     edx, edx; Increment
0x14001faa7  call    cs:__imp_KeSetEvent
0x14001faae  nop     dword ptr [rax+rax+00h]
0x14001fab3  xor     r9d, r9d; Alertable
0x14001fab6  mov     [rsp+38h+Timeout], 0; Timeout
0x14001fabf  xor     r8d, r8d; WaitMode
0x14001fac2  lea     rcx, PcgRegistryCompletionEvent; Object
0x14001fac9  xor     edx, edx; WaitReason
0x14001facb  call    cs:__imp_KeWaitForSingleObject
0x14001fad2  nop     dword ptr [rax+rax+00h]
0x14001fad7  add     rsp, 38h
0x14001fadb  retn
```
