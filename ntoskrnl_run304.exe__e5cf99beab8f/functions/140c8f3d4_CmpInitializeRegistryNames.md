# CmpInitializeRegistryNames

- ea: `0x140c8f3d4`
- end: `0x140c8f5fb`
- name: `CmpInitializeRegistryNames`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, registry_config, service_task, installer_update`

## callers

- `0x140c89fc4`

## callees

- `0x1403f2d50`
- `0x140c8f3d4`

## string_xrefs

- `0x140c8f57c`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\SERVICES\EVENTLOG`
- `0x140c8f498`: `\REGISTRY\USER`
- `0x140c8f543`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\SAFEBOOT`
- `0x140c8f530`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\CLASS`
- `0x140c8f569`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\BOOTLOG`
- `0x140c8f556`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\CONTROL\SESSION MANAGER\MEMORY MANAGEMENT`
- `0x140c8f4f7`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\ENUM\ROOT`
- `0x140c8f4e4`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\ENUM`
- `0x140c8f51d`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\HARDWARE PROFILES\CURRENT`
- `0x140c8f50a`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET\SERVICES`
- `0x140c8f45f`: `\REGISTRY\MACHINE\HARDWARE\OWNERMAP`
- `0x140c8f44c`: `\REGISTRY\MACHINE\HARDWARE\RESOURCEMAP`
- `0x140c8f485`: `\REGISTRY\MACHINE\SYSTEM\CURRENTCONTROLSET`
- `0x140c8f472`: `\REGISTRY\MACHINE\SYSTEM`
- `0x140c8f413`: `\REGISTRY\MACHINE\HARDWARE\DESCRIPTION`
- `0x140c8f400`: `\REGISTRY\MACHINE\HARDWARE`
- `0x140c8f439`: `\REGISTRY\MACHINE\HARDWARE\DEVICEMAP`
- `0x140c8f426`: `\REGISTRY\MACHINE\HARDWARE\DESCRIPTION\SYSTEM`
- `0x140c8f3ed`: `\REGISTRY\MACHINE`
- `0x140c8f3da`: `\REGISTRY`
- `0x140c8f5b5`: `Registry`
- `0x140c8f58f`: `SymbolicLinkValue`
- `0x140c8f5a2`: `CONTROLSET001\SERVICES\MPSSVC`
- `0x140c8f4be`: `\REGISTRY\A`
- `0x140c8f4ab`: `\REGISTRY\WC`

## pseudocode

```c
void CmpInitializeRegistryNames()
{
  __int64 i; // rbx

  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.SchedulerApcFill5[48], L"\\REGISTRY");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.WaitBlockFill11[32], L"\\REGISTRY\\MACHINE");
  RtlInitUnicodeString(
    (PUNICODE_STRING)&PspActiveProcessLock.SchedulerSharedSwappablePage,
    L"\\REGISTRY\\MACHINE\\HARDWARE");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.1144, L"\\REGISTRY\\MACHINE\\HARDWARE\\DESCRIPTION");
  RtlInitUnicodeString(
    (PUNICODE_STRING)&PspActiveProcessLock.WaitBlockFill11[48],
    L"\\REGISTRY\\MACHINE\\HARDWARE\\DESCRIPTION\\SYSTEM");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.IptSaveArea, L"\\REGISTRY\\MACHINE\\HARDWARE\\DEVICEMAP");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.792, L"\\REGISTRY\\MACHINE\\HARDWARE\\RESOURCEMAP");
  RtlInitUnicodeString(&CmRegistryMachineHardwareOwnerMapName, L"\\REGISTRY\\MACHINE\\HARDWARE\\OWNERMAP");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.OtherTransferCount, L"\\REGISTRY\\MACHINE\\SYSTEM");
  RtlInitUnicodeString(
    (PUNICODE_STRING)&PspActiveProcessLock.AffinityPrimaryGroup,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.ExtendedFeatureDisableMask, L"\\REGISTRY\\USER");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.KernelShadowStackBase, L"\\REGISTRY\\WC");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.KernelShadowStack, L"\\REGISTRY\\A");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.SchedulerAssist, L"SYSTEM");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetEnumName,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\ENUM");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetEnumRootName,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\ENUM\\ROOT");
  RtlInitUnicodeString(
    (PUNICODE_STRING)&PspActiveProcessLock.Queue,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\SERVICES");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetHardwareProfilesCurrent,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\HARDWARE PROFILES\\CURRENT");
  RtlInitUnicodeString(
    &CmRegistryMachineSystemCurrentControlSetControlClass,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\CLASS");
  RtlInitUnicodeString(
    (PUNICODE_STRING)&PspActiveProcessLock.ThreadTimerDelay,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\SAFEBOOT");
  RtlInitUnicodeString(
    (PUNICODE_STRING)&PspActiveProcessLock.SchedulerApcFill5[32],
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\SESSION MANAGER\\MEMORY MANAGEMENT");
  RtlInitUnicodeString(
    (PUNICODE_STRING)&PspActiveProcessLock.ReadTransferCount,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\CONTROL\\BOOTLOG");
  RtlInitUnicodeString(
    (PUNICODE_STRING)&PspActiveProcessLock.InGlobalUpdateVpThreadPriorityList,
    L"\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCONTROLSET\\SERVICES\\EVENTLOG");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.SchedulingGroup, L"SymbolicLinkValue");
  RtlInitUnicodeString((PUNICODE_STRING)PspActiveProcessLock.Spare35, L"CONTROLSET001\\SERVICES\\MPSSVC");
  RtlInitUnicodeString((PUNICODE_STRING)&PspActiveProcessLock.Spare36, L"Registry");
  for ( i = 0; i != 42; ++i )
    RtlInitUnicodeString((PUNICODE_STRING)&CmTypeName + i, CmTypeString[i]);
}

```

## disassembly

```asm
0x140c8f3d4  push    rbx
0x140c8f3d6  sub     rsp, 20h
0x140c8f3da  lea     rdx, aRegistry; "\\REGISTRY"
0x140c8f3e1  lea     rcx, PspActiveProcessLock.___u58+30h; DestinationString
0x140c8f3e8  call    RtlInitUnicodeString
0x140c8f3ed  lea     rdx, aRegistryMachin_69; "\\REGISTRY\\MACHINE"
0x140c8f3f4  lea     rcx, PspActiveProcessLock.___u33+20h; DestinationString
0x140c8f3fb  call    RtlInitUnicodeString
0x140c8f400  lea     rdx, aRegistryMachin_215; "\\REGISTRY\\MACHINE\\HARDWARE"
0x140c8f407  lea     rcx, PspActiveProcessLock.SchedulerSharedSwappablePage; DestinationString
0x140c8f40e  call    RtlInitUnicodeString
0x140c8f413  lea     rdx, aRegistryMachin_91; "\\REGISTRY\\MACHINE\\HARDWARE\\DESCRIPT"...
0x140c8f41a  lea     rcx, PspActiveProcessLock.___u116; DestinationString
0x140c8f421  call    RtlInitUnicodeString
0x140c8f426  lea     rdx, aRegistryMachin_55; "\\REGISTRY\\MACHINE\\HARDWARE\\DESCRIPT"...
0x140c8f42d  lea     rcx, PspActiveProcessLock.___u33+30h; DestinationString
0x140c8f434  call    RtlInitUnicodeString
0x140c8f439  lea     rdx, aRegistryMachin_124; "\\REGISTRY\\MACHINE\\HARDWARE\\DEVICEMA"...
0x140c8f440  lea     rcx, PspActiveProcessLock.IptSaveArea; DestinationString
0x140c8f447  call    RtlInitUnicodeString
0x140c8f44c  lea     rdx, aRegistryMachin_22; "\\REGISTRY\\MACHINE\\HARDWARE\\RESOURCE"...
0x140c8f453  lea     rcx, PspActiveProcessLock.___u62; DestinationString
0x140c8f45a  call    RtlInitUnicodeString
0x140c8f45f  lea     rdx, aRegistryMachin_191; "\\REGISTRY\\MACHINE\\HARDWARE\\OWNERMAP"
0x140c8f466  lea     rcx, CmRegistryMachineHardwareOwnerMapName; DestinationString
0x140c8f46d  call    RtlInitUnicodeString
0x140c8f472  lea     rdx, aRegistryMachin_188; "\\REGISTRY\\MACHINE\\SYSTEM"
0x140c8f479  lea     rcx, PspActiveProcessLock.OtherTransferCount; DestinationString
0x140c8f480  call    RtlInitUnicodeString
0x140c8f485  lea     rdx, aRegistryMachin_119; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f48c  lea     rcx, PspActiveProcessLock.AffinityPrimaryGroup; DestinationString
0x140c8f493  call    RtlInitUnicodeString
0x140c8f498  lea     rdx, aRegistryUser; "\\REGISTRY\\USER"
0x140c8f49f  lea     rcx, PspActiveProcessLock.ExtendedFeatureDisableMask; DestinationString
0x140c8f4a6  call    RtlInitUnicodeString
0x140c8f4ab  lea     rdx, aRegistryWc; "\\REGISTRY\\WC"
0x140c8f4b2  lea     rcx, PspActiveProcessLock.KernelShadowStackBase; DestinationString
0x140c8f4b9  call    RtlInitUnicodeString
0x140c8f4be  lea     rdx, aRegistryA; "\\REGISTRY\\A"
0x140c8f4c5  lea     rcx, PspActiveProcessLock.KernelShadowStack; DestinationString
0x140c8f4cc  call    RtlInitUnicodeString
0x140c8f4d1  lea     rdx, aSystem_3; "SYSTEM"
0x140c8f4d8  lea     rcx, PspActiveProcessLock.SchedulerAssist; DestinationString
0x140c8f4df  call    RtlInitUnicodeString
0x140c8f4e4  lea     rdx, aRegistryMachin_216; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f4eb  lea     rcx, CmRegistryMachineSystemCurrentControlSetEnumName; DestinationString
0x140c8f4f2  call    RtlInitUnicodeString
0x140c8f4f7  lea     rdx, aRegistryMachin_76; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f4fe  lea     rcx, CmRegistryMachineSystemCurrentControlSetEnumRootName; DestinationString
0x140c8f505  call    RtlInitUnicodeString
0x140c8f50a  lea     rdx, aRegistryMachin_205; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f511  lea     rcx, PspActiveProcessLock.Queue; DestinationString
0x140c8f518  call    RtlInitUnicodeString
0x140c8f51d  lea     rdx, aRegistryMachin_154; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f524  lea     rcx, CmRegistryMachineSystemCurrentControlSetHardwareProfilesCurrent; DestinationString
0x140c8f52b  call    RtlInitUnicodeString
0x140c8f530  lea     rdx, aRegistryMachin_235; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f537  lea     rcx, CmRegistryMachineSystemCurrentControlSetControlClass; DestinationString
0x140c8f53e  call    RtlInitUnicodeString
0x140c8f543  lea     rdx, aRegistryMachin_200; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f54a  lea     rcx, PspActiveProcessLock.ThreadTimerDelay; DestinationString
0x140c8f551  call    RtlInitUnicodeString
0x140c8f556  lea     rdx, aRegistryMachin_31; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f55d  lea     rcx, PspActiveProcessLock.___u58+20h; DestinationString
0x140c8f564  call    RtlInitUnicodeString
0x140c8f569  lea     rdx, aRegistryMachin_83; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f570  lea     rcx, PspActiveProcessLock.ReadTransferCount; DestinationString
0x140c8f577  call    RtlInitUnicodeString
0x140c8f57c  lea     rdx, aRegistryMachin_140; "\\REGISTRY\\MACHINE\\SYSTEM\\CURRENTCON"...
0x140c8f583  lea     rcx, PspActiveProcessLock.___u95+8; DestinationString
0x140c8f58a  call    RtlInitUnicodeString
0x140c8f58f  lea     rdx, aSymboliclinkva; "SymbolicLinkValue"
0x140c8f596  lea     rcx, PspActiveProcessLock.SchedulingGroup; DestinationString
0x140c8f59d  call    RtlInitUnicodeString
0x140c8f5a2  lea     rdx, aControlset001S; "CONTROLSET001\\SERVICES\\MPSSVC"
0x140c8f5a9  lea     rcx, PspActiveProcessLock.Spare35; DestinationString
0x140c8f5b0  call    RtlInitUnicodeString
0x140c8f5b5  lea     rdx, aRegistry_4; "Registry"
0x140c8f5bc  lea     rcx, PspActiveProcessLock.Spare36; DestinationString
0x140c8f5c3  call    RtlInitUnicodeString
0x140c8f5c8  xor     ebx, ebx
0x140c8f5ca  lea     rax, CmTypeName
0x140c8f5d1  mov     rcx, rbx
0x140c8f5d4  shl     rcx, 4
0x140c8f5d8  lea     rdx, CmTypeString
0x140c8f5df  mov     rdx, [rdx+rbx*8]; SourceString
0x140c8f5e3  add     rcx, rax; DestinationString
0x140c8f5e6  call    RtlInitUnicodeString
0x140c8f5eb  inc     rbx
0x140c8f5ee  cmp     rbx, 2Ah ; '*'
0x140c8f5f2  jnz     short loc_140C8F5CA
0x140c8f5f4  add     rsp, 20h
0x140c8f5f8  pop     rbx
0x140c8f5f9  retn
```
