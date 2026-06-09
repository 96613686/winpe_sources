# DriverEntry

- ea: `0x14001dcb4`
- end: `0x14001dea9`
- name: `DriverEntry`
- size: `501`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140022010`

## callees

- `0x14001dcb4`
- `0x14001e808`
- `0x14001e88c`
- `0x14001e920`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14001ddaf`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001dddd`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001de11`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001de2b`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001ddaf`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001dddd`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001de11`
- `ntoskrnl!KeInitializeSpinLock` at `0x14001de2b`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001ddfe`
- `ntoskrnl!KeInitializeSemaphore` at `0x14001ddfe`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001dd87`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001dd87`
- `NDIS!NdisFreeMemoryWithTag` at `0x14001de81`
- `NDIS!NdisFreeMemoryWithTag` at `0x14001de81`
- `NDIS!NdisAllocateMemoryWithTag` at `0x14001dd57`
- `NDIS!NdisAllocateMemoryWithTag` at `0x14001dd57`
- `NDIS!NdisInitializeEvent` at `0x14001dd11`
- `NDIS!NdisInitializeEvent` at `0x14001dd11`
- `NETIO!RtlInvokeStartRoutines` at `0x14001de5e`
- `NETIO!RtlInvokeStartRoutines` at `0x14001de5e`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  NTSTATUS MemoryWithTag; // ebx
  NTSTATUS result; // eax
  NTSTATUS v6; // ebx

  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_NETIO;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  NdisInitializeEvent((PNDIS_EVENT)&WPP_MAIN_CB.DeviceQueue);
  *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels = DriverObject;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)PcUnload;
  PcgRegistryPath.MaximumLength = RegistryPath->Length + 2;
  PcgRegistryPath.Length = RegistryPath->Length;
  MemoryWithTag = NdisAllocateMemoryWithTag(
                    (PVOID *)&PcgRegistryPath.Buffer,
                    PcgRegistryPath.MaximumLength,
                    0x65676350u);
  if ( MemoryWithTag )
  {
    WppCleanupKm();
    result = -1073741823;
    if ( MemoryWithTag < 0 )
      return MemoryWithTag;
  }
  else
  {
    RtlCopyUnicodeString(&PcgRegistryPath, RegistryPath);
    WPP_MAIN_CB.Dpc.ProcessorHistory = (KAFFINITY)&WPP_MAIN_CB.Dpc.DpcListEntry;
    WPP_MAIN_CB.Dpc.DpcListEntry.Next = &WPP_MAIN_CB.Dpc.DpcListEntry;
    KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.SystemArgument1);
    LODWORD(WPP_MAIN_CB.Dpc.SystemArgument2) = 0;
    *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfMapRegisters = &WPP_MAIN_CB.Queue.Wcb.DeviceContext;
    WPP_MAIN_CB.Queue.Wcb.DeviceContext = &WPP_MAIN_CB.Queue.Wcb.DeviceContext;
    KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.DeviceObject);
    LODWORD(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) = 0;
    KeInitializeSemaphore(&PcgWfpInitSemaphore, 1, 1);
    KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc);
    *(_QWORD *)&WPP_MAIN_CB.AlignmentRequirement = 0;
    KeInitializeSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Dpc.DeferredContext);
    *(_QWORD *)&WPP_MAIN_CB.ActiveThreadCount = 0;
    WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
    HIDWORD(WPP_MAIN_CB.Dpc.DpcData) = 0;
    v6 = RtlInvokeStartRoutines(&PcgStartStopRoutines, 8, &WPP_MAIN_CB.DeviceQueue.Busy);
    if ( v6 >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)&WPP_MAIN_CB.DeviceQueue.Lock);
    }
    else
    {
      WppCleanupKm();
      NdisFreeMemoryWithTag(PcgRegistryPath.Buffer, 0x65676350u);
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x14001dcb4  mov     [rsp+arg_0], rbx
0x14001dcb9  mov     [rsp+arg_8], rsi
0x14001dcbe  push    rdi
0x14001dcbf  sub     rsp, 20h
0x14001dcc3  xor     esi, esi
0x14001dcc5  mov     cs:WPP_MAIN_CB.Timer, 1
0x14001dcd0  lea     rax, WPP_ThisDir_CTLGUID_NETIO
0x14001dcd7  mov     qword ptr cs:WPP_MAIN_CB.Type, rsi
0x14001dcde  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14001dce5  mov     rdi, rdx
0x14001dce8  mov     cs:WPP_MAIN_CB.NextDevice, rsi
0x14001dcef  mov     rbx, rcx
0x14001dcf2  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14001dcf9  call    WppLoadTracingSupport
0x14001dcfe  mov     cs:WPP_MAIN_CB.CurrentIrp, rsi
0x14001dd05  call    WppInitKm
0x14001dd0a  lea     rcx, WPP_MAIN_CB.DeviceQueue; Event
0x14001dd11  call    cs:__imp_NdisInitializeEvent
0x14001dd18  nop     dword ptr [rax+rax+00h]
0x14001dd1d  lea     rax, PcUnload
0x14001dd24  mov     qword ptr cs:WPP_MAIN_CB.Queue+10h, rbx
0x14001dd2b  mov     [rbx+68h], rax
0x14001dd2f  lea     rcx, PcgRegistryPath.Buffer; VirtualAddress
0x14001dd36  movzx   eax, word ptr [rdi]
0x14001dd39  mov     r8d, 65676350h; Tag
0x14001dd3f  add     ax, 2
0x14001dd43  movzx   edx, ax; Length
0x14001dd46  mov     cs:PcgRegistryPath.MaximumLength, dx
0x14001dd4d  movzx   eax, word ptr [rdi]
0x14001dd50  mov     cs:PcgRegistryPath.Length, ax
0x14001dd57  call    cs:__imp_NdisAllocateMemoryWithTag
0x14001dd5e  nop     dword ptr [rax+rax+00h]
0x14001dd63  mov     ebx, eax
0x14001dd65  test    eax, eax
0x14001dd67  jz      short loc_14001DD7D
0x14001dd69  call    WppCleanupKm
0x14001dd6e  test    ebx, ebx
0x14001dd70  mov     eax, 0C0000001h
0x14001dd75  cmovs   eax, ebx
0x14001dd78  jmp     loc_14001DE98
0x14001dd7d  mov     rdx, rdi; SourceString
0x14001dd80  lea     rcx, PcgRegistryPath; DestinationString
0x14001dd87  call    cs:__imp_RtlCopyUnicodeString
0x14001dd8e  nop     dword ptr [rax+rax+00h]
0x14001dd93  lea     rax, WPP_MAIN_CB.Dpc.DpcListEntry
0x14001dd9a  lea     rcx, WPP_MAIN_CB.Dpc.SystemArgument1; SpinLock
0x14001dda1  mov     cs:WPP_MAIN_CB.Dpc.ProcessorHistory, rax
0x14001dda8  mov     cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next, rax
0x14001ddaf  call    cs:__imp_KeInitializeSpinLock
0x14001ddb6  nop     dword ptr [rax+rax+00h]
0x14001ddbb  lea     rax, WPP_MAIN_CB.Queue+20h
0x14001ddc2  mov     dword ptr cs:WPP_MAIN_CB.Dpc.SystemArgument2, esi
0x14001ddc8  lea     rcx, WPP_MAIN_CB.Queue+30h; SpinLock
0x14001ddcf  mov     qword ptr cs:WPP_MAIN_CB.Queue+28h, rax
0x14001ddd6  mov     qword ptr cs:WPP_MAIN_CB.Queue+20h, rax
0x14001dddd  call    cs:__imp_KeInitializeSpinLock
0x14001dde4  nop     dword ptr [rax+rax+00h]
0x14001dde9  mov     edx, 1; Count
0x14001ddee  mov     dword ptr cs:WPP_MAIN_CB.Queue+38h, esi
0x14001ddf4  mov     r8d, edx; Limit
0x14001ddf7  lea     rcx, PcgWfpInitSemaphore; Semaphore
0x14001ddfe  call    cs:__imp_KeInitializeSemaphore
0x14001de05  nop     dword ptr [rax+rax+00h]
0x14001de0a  lea     rcx, WPP_MAIN_CB.Queue+40h; SpinLock
0x14001de11  call    cs:__imp_KeInitializeSpinLock
0x14001de18  nop     dword ptr [rax+rax+00h]
0x14001de1d  lea     rcx, WPP_MAIN_CB.Dpc.DeferredContext; SpinLock
0x14001de24  mov     qword ptr cs:WPP_MAIN_CB.AlignmentRequirement, rsi
0x14001de2b  call    cs:__imp_KeInitializeSpinLock
0x14001de32  nop     dword ptr [rax+rax+00h]
0x14001de37  lea     r8, WPP_MAIN_CB.DeviceQueue.20h
0x14001de3e  mov     qword ptr cs:WPP_MAIN_CB.ActiveThreadCount, rsi
0x14001de45  mov     edx, 8
0x14001de4a  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, rsi
0x14001de51  lea     rcx, PcgStartStopRoutines
0x14001de58  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DpcData+4, esi
0x14001de5e  call    cs:__imp_RtlInvokeStartRoutines
0x14001de65  nop     dword ptr [rax+rax+00h]
0x14001de6a  mov     ebx, eax
0x14001de6c  test    eax, eax
0x14001de6e  jns     short loc_14001DE8F
0x14001de70  call    WppCleanupKm
0x14001de75  mov     rcx, cs:PcgRegistryPath.Buffer; VirtualAddress
0x14001de7c  mov     edx, 65676350h; Tag
0x14001de81  call    cs:__imp_NdisFreeMemoryWithTag
0x14001de88  nop     dword ptr [rax+rax+00h]
0x14001de8d  jmp     short loc_14001DE96
0x14001de8f  lock inc dword ptr cs:WPP_MAIN_CB.DeviceQueue.Lock
0x14001de96  mov     eax, ebx
0x14001de98  mov     rbx, [rsp+28h+arg_0]
0x14001de9d  mov     rsi, [rsp+28h+arg_8]
0x14001dea2  add     rsp, 20h
0x14001dea6  pop     rdi
0x14001dea7  retn
```
