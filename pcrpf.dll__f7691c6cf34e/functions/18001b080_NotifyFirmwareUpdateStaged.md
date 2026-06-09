# NotifyFirmwareUpdateStaged

- ea: `0x18001b080`
- end: `0x18001b0bc`
- name: `NotifyFirmwareUpdateStaged`
- size: `60`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x18001b080`
- `0x1800351d0`
- `0x18003529c`
- `0x180035678`
- `0x18004f9ac`

## string_xrefs

- `0x18001b09d`: `Firmware update staged`

## pseudocode

```c
__int64 NotifyFirmwareUpdateStaged()
{
  int updated; // eax
  unsigned int v1; // ebx
  char v3; // [rsp+30h] [rbp+8h] BYREF

  PpfEventLogProviderRegistration::PpfEventLogProviderRegistration((PpfEventLogProviderRegistration *)&v3);
  updated = NotifyFirmwareUpdateStagedInt();
  v1 = updated;
  if ( updated < 0 )
    PpfhLogEventGenericActivityError(L"Firmware update staged", updated);
  PpfEventLogProviderRegistration::~PpfEventLogProviderRegistration((PpfEventLogProviderRegistration *)&v3);
  return v1;
}

```

## disassembly

```asm
0x18001b080  push    rbx
0x18001b082  sub     rsp, 20h
0x18001b086  lea     rcx, [rsp+28h+arg_0]; this
0x18001b08b  call    ??0PpfEventLogProviderRegistration@@QEAA@XZ; PpfEventLogProviderRegistration::PpfEventLogProviderRegistration(void)
0x18001b090  call    ?NotifyFirmwareUpdateStagedInt@@YAJXZ; NotifyFirmwareUpdateStagedInt(void)
0x18001b095  mov     ebx, eax
0x18001b097  test    eax, eax
0x18001b099  jns     short loc_18001B0A9
0x18001b09b  mov     edx, eax; int
0x18001b09d  lea     rcx, aFirmwareUpdate; "Firmware update staged"
0x18001b0a4  call    ?PpfhLogEventGenericActivityError@@YAJPEBGJ@Z; PpfhLogEventGenericActivityError(ushort const *,long)
0x18001b0a9  lea     rcx, [rsp+28h+arg_0]; this
0x18001b0ae  call    ??1PpfEventLogProviderRegistration@@QEAA@XZ; PpfEventLogProviderRegistration::~PpfEventLogProviderRegistration(void)
0x18001b0b3  mov     eax, ebx
0x18001b0b5  add     rsp, 20h
0x18001b0b9  pop     rbx
0x18001b0ba  retn
```
