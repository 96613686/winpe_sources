# CmpInitializeRegistryNames

- ea: `0x140c92258`
- end: `0x140c9247f`
- name: `CmpInitializeRegistryNames`
- size: `551`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x140c8ce24`

## callees

- `0x140403380`
- `0x140c92258`

## string_xrefs

- `0x140c9231c`: `\REGISTRY\USER`
- `0x140c92400`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\SERVICES\EVENTLOG`
- `0x140c92342`: `\REGISTRY\A`
- `0x140c9232f`: `\REGISTRY\WC`
- `0x140c923a1`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\HARDWARE PROFILES\CURRENT`
- `0x140c9238e`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\SERVICES`
- `0x140c9237b`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\ENUM\ROOT`
- `0x140c92368`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\ENUM`
- `0x140c923ed`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\BOOTLOG`
- `0x140c923da`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\SESSION MANAGER\MEMORY MANAGEMENT`
- `0x140c923c7`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\SAFEBOOT`
- `0x140c923b4`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\CLASS`
- `0x140c922bd`: `\REGISTRY\MACHINE\HARDWARE\DEVICEMAP`
- `0x140c922aa`: `\REGISTRY\MACHINE\HARDWARE\DESCRIPTION\SYSTEM`
- `0x140c92297`: `\REGISTRY\MACHINE\HARDWARE\DESCRIPTION`
- `0x140c92284`: `\REGISTRY\MACHINE\HARDWARE`
- `0x140c92309`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET`
- `0x140c922f6`: `\REGISTRY\MACHINE\SYSTEM`
- `0x140c922e3`: `\REGISTRY\MACHINE\HARDWARE\OWNERMAP`
- `0x140c922d0`: `\REGISTRY\MACHINE\HARDWARE\RESOURCEMAP`
- `0x140c92271`: `\REGISTRY\MACHINE`
- `0x140c9225e`: `\REGISTRY`
- `0x140c92426`: `CONTROLSET001\SERVICES\MPSSVC`
- `0x140c92439`: `Registry`
- `0x140c92413`: `SymbolicLinkValue`

## pseudocode

```c
void CmpInitializeRegistryNames()
{
  __int64 i; // rbx

  RtlInitUnicodeString(&CmRegistryRootName, L"\\REGISTRY");
  RtlInitUnicodeString(&CmRegistryMachineName, L"\\REGISTRY\\MACHINE");
  RtlInitUnicodeString(&CmRegistryMachineHardwareName, L"\\REGISTRY\\MACHINE\\HARDWARE");
  RtlInitUnicodeString(&CmRegistryMachineHardwareDescriptionName, L"\\REGISTRY\\MACHINE\\HARDWARE\\DESCRIPTION");
  RtlInitUnicodeString(
    &CmRegistryMachineHardwareDescriptionSystemName,
    L"\\REGISTRY\\MACHINE\\HARDWARE\\DESCRIPTION\\SYSTEM");
  RtlInitUnicodeString(&CmRegistryMachineHardwareDeviceMapName, L"\\REGISTRY\\MACHINE\\HARDWARE\\DEVICEMAP");
  RtlInitUnicodeString(&CmRegistryMachineHardwareResourceMapName, L"\\REGISTRY\\MACHINE\\HARDWARE\\RESOURCEMAP");
  RtlInitUnicodeString(&CmRegistryMachineHardwareOwnerMapName, L"\\REGISTRY\\MACHINE\\HARDWARE\\OWNERMAP");
  RtlInitUnicodeString(&CmRegistryMachineSystemName, L"\\REGISTRY\\MACHINE\\SYSTEM");
  RtlInitUnicodeString(&CmRegistryMachineSystemCurrentControlSet, L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET");
  RtlInitUnicodeString(&CmRegistryUserName, L"\\REGISTRY\\USER");
  RtlInitUnicodeString(&CmRegistryContainersName, L"\\REGISTRY\\WC");
  RtlInitUnicodeString(&CmRegistryAppName, L"\\REGISTRY\\A");
  RtlInitUnicodeString(&CmpSystemFileName, L"SYSTEM");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetEnumName,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\ENUM");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetEnumRootName,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\ENUM\\ROOT");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetServices,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\SERVICES");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetHardwareProfilesCurrent,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\HARDWARE PROFILES\\CURRENT");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetControlClass,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\CLASS");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetControlSafeBoot,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\SAFEBOOT");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetControlSessionManagerMemoryManagement,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\SESSION MANAGER\\MEMORY MANAGEMENT");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetControlBootLog,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\BOOTLOG");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetServicesEventLog,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\SERVICES\\EVENTLOG");
  RtlInitUnicodeString(&CmSymbolicLinkValueName, L"SymbolicLinkValue");
  RtlInitUnicodeString(&CmMpsSvcKeySubstring, L"CONTROLSET001\\SERVICES\\MPSSVC");
  RtlInitUnicodeString(&CmRegistryProcessName, L"Registry");
  for ( i = 0; i != 42; ++i )
    RtlInitUnicodeString((PUNICODE_STRING)&CmTypeName[2 * i], CmTypeString[i]);
}

```

## disassembly

```asm
0x140c92258  push    rbx
0x140c9225a  sub     rsp, 20h
0x140c9225e  lea     rdx, aRegistry; "\\REGISTRY"
0x140c92265  lea     rcx, CmRegistryRootName; DestinationString
0x140c9226c  call    RtlInitUnicodeString
0x140c92271  lea     rdx, aRegistryMachin_69; "\\REGISTRY\\MACHINE"
0x140c92278  lea     rcx, CmRegistryMachineName; DestinationString
0x140c9227f  call    RtlInitUnicodeString
0x140c92284  lea     rdx, aRegistryMachin_215; "\\REGISTRY\\MACHINE\\HARDWARE"
0x140c9228b  lea     rcx, CmRegistryMachineHardwareName; DestinationString
0x140c92292  call    RtlInitUnicodeString
0x140c92297  lea     rdx, aRegistryMachin_91; "\\REGISTRY\\MACHINE\\HARDWARE\\DESCRIPT"...
0x140c9229e  lea     rcx, CmRegistryMachineHardwareDescriptionName; DestinationString
0x140c922a5  call    RtlInitUnicodeString
0x140c922aa  lea     rdx, aRegistryMachin_55; "\\REGISTRY\\MACHINE\\HARDWARE\\DESCRIPT"...
0x140c922b1  lea     rcx, CmRegistryMachineHardwareDescriptionSystemName; DestinationString
0x140c922b8  call    RtlInitUnicodeString
0x140c922bd  lea     rdx, aRegistryMachin_124; "\\REGISTRY\\MACHINE\\HARDWARE\\DEVICEMA"...
0x140c922c4  lea     rcx, CmRegistryMachineHardwareDeviceMapName; DestinationString
0x140c922cb  call    RtlInitUnicodeString
0x140c922d0  lea     rdx, aRegistryMachin_22; "\\REGISTRY\\MACHINE\\HARDWARE\\RESOURCE"...
0x140c922d7  lea     rcx, CmRegistryMachineHardwareResourceMapName; DestinationString
0x140c922de  call    RtlInitUnicodeString
0x140c922e3  lea     rdx, aRegistryMachin_191; "\\REGISTRY\\MACHINE\\HARDWARE\\OWNERMAP"
0x140c922ea  lea     rcx, CmRegistryMachineHardwareOwnerMapName; DestinationString
0x140c922f1  call    RtlInitUnicodeString
0x140c922f6  lea     rdx, aRegistryMachin_188; "\\REGISTRY\\MACHINE\\SYSTEM"
0x140c922fd  lea     rcx, CmRegistryMachineSystemName; DestinationString
0x140c92304  call    RtlInitUnicodeString
0x140c92309  lea     rdx, aRegistryMachin_119; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c92310  lea     rcx, CmRegistryMachineSystemCurrentControlSet; DestinationString
0x140c92317  call    RtlInitUnicodeString
0x140c9231c  lea     rdx, aRegistryUser; "\\REGISTRY\\USER"
0x140c92323  lea     rcx, CmRegistryUserName; DestinationString
0x140c9232a  call    RtlInitUnicodeString
0x140c9232f  lea     rdx, aRegistryWc; "\\REGISTRY\\WC"
0x140c92336  lea     rcx, CmRegistryContainersName; DestinationString
0x140c9233d  call    RtlInitUnicodeString
0x140c92342  lea     rdx, aRegistryA; "\\REGISTRY\\A"
0x140c92349  lea     rcx, CmRegistryAppName; DestinationString
0x140c92350  call    RtlInitUnicodeString
0x140c92355  lea     rdx, aSystem_3; "SYSTEM"
0x140c9235c  lea     rcx, CmpSystemFileName; DestinationString
0x140c92363  call    RtlInitUnicodeString
0x140c92368  lea     rdx, aRegistryMachin_216; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c9236f  lea     rcx, CmRegistryMachineSystemCurrentControlSetEnumName; DestinationString
0x140c92376  call    RtlInitUnicodeString
0x140c9237b  lea     rdx, aRegistryMachin_76; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c92382  lea     rcx, CmRegistryMachineSystemCurrentControlSetEnumRootName; DestinationString
0x140c92389  call    RtlInitUnicodeString
0x140c9238e  lea     rdx, aRegistryMachin_205; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c92395  lea     rcx, CmRegistryMachineSystemCurrentControlSetServices; DestinationString
0x140c9239c  call    RtlInitUnicodeString
0x140c923a1  lea     rdx, aRegistryMachin_154; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c923a8  lea     rcx, CmRegistryMachineSystemCurrentControlSetHardwareProfilesCurrent; DestinationString
0x140c923af  call    RtlInitUnicodeString
0x140c923b4  lea     rdx, aRegistryMachin_234; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c923bb  lea     rcx, CmRegistryMachineSystemCurrentControlSetControlClass; DestinationString
0x140c923c2  call    RtlInitUnicodeString
0x140c923c7  lea     rdx, aRegistryMachin_200; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c923ce  lea     rcx, CmRegistryMachineSystemCurrentControlSetControlSafeBoot; DestinationString
0x140c923d5  call    RtlInitUnicodeString
0x140c923da  lea     rdx, aRegistryMachin_31; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c923e1  lea     rcx, CmRegistryMachineSystemCurrentControlSetControlSessionManagerMemoryManagement; DestinationString
0x140c923e8  call    RtlInitUnicodeString
0x140c923ed  lea     rdx, aRegistryMachin_83; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c923f4  lea     rcx, CmRegistryMachineSystemCurrentControlSetControlBootLog; DestinationString
0x140c923fb  call    RtlInitUnicodeString
0x140c92400  lea     rdx, aRegistryMachin_140; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c92407  lea     rcx, CmRegistryMachineSystemCurrentControlSetServicesEventLog; DestinationString
0x140c9240e  call    RtlInitUnicodeString
0x140c92413  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x140c9241a  lea     rcx, CmSymbolicLinkValueName; DestinationString
0x140c92421  call    RtlInitUnicodeString
0x140c92426  lea     rdx, aControlset001S; "CONTROLSET001\\SERVICES\\MPSSVC"
0x140c9242d  lea     rcx, CmMpsSvcKeySubstring; DestinationString
0x140c92434  call    RtlInitUnicodeString
0x140c92439  lea     rdx, aRegistry_4; "Registry"
0x140c92440  lea     rcx, CmRegistryProcessName; DestinationString
0x140c92447  call    RtlInitUnicodeString
0x140c9244c  xor     ebx, ebx
0x140c9244e  lea     rax, CmTypeName
0x140c92455  mov     rcx, rbx
0x140c92458  shl     rcx, 4
0x140c9245c  lea     rdx, CmTypeString
0x140c92463  mov     rdx, [rdx+rbx*8]; SourceString
0x140c92467  add     rcx, rax; DestinationString
0x140c9246a  call    RtlInitUnicodeString
0x140c9246f  inc     rbx
0x140c92472  cmp     rbx, 2Ah ; '*'
0x140c92476  jnz     short loc_140C9244E
0x140c92478  add     rsp, 20h
0x140c9247c  pop     rbx
0x140c9247d  retn
```
