# MupRegisterPrefixCacheKeyChangeNotification

- ea: `0x140003350`
- end: `0x1400033c7`
- name: `MupRegisterPrefixCacheKeyChangeNotification`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140010f18`

## callees

- `0x140003350`

## import_xrefs

- `ntoskrnl!ZwNotifyChangeKey` at `0x1400033b5`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400033b5`

## pseudocode

```c
NTSTATUS MupRegisterPrefixCacheKeyChangeNotification()
{
  NTSTATUS result; // eax

  if ( MupiMupServicesKeyHandleValid )
  {
    WPP_MAIN_CB.SecurityDescriptor = MupiPrefixCacheRegistryChangeHandler;
    *(_QWORD *)&WPP_MAIN_CB.DeviceLock.Header.Lock = 0;
    WPP_MAIN_CB.Dpc.DpcData = 0;
    return ZwNotifyChangeKey(
             WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink,
             0,
             (PIO_APC_ROUTINE)&WPP_MAIN_CB.Dpc.DpcData,
             (PVOID)1,
             (PIO_STATUS_BLOCK)&WPP_MAIN_CB.SectorSize,
             4u,
             1u,
             0,
             0,
             1u);
  }
  return result;
}

```

## disassembly

```asm
0x140003350  sub     rsp, 58h
0x140003354  xor     ecx, ecx
0x140003356  cmp     cs:MupiMupServicesKeyHandleValid, cl
0x14000335c  jz      short loc_1400033C1
0x14000335e  mov     [rsp+58h+Asynchronous], 1; Asynchronous
0x140003363  lea     rax, MupiPrefixCacheRegistryChangeHandler
0x14000336a  mov     [rsp+58h+BufferSize], ecx; BufferSize
0x14000336e  lea     r9d, [rcx+1]; ApcContext
0x140003372  mov     [rsp+58h+Buffer], rcx; Buffer
0x140003377  lea     r8, WPP_MAIN_CB.Dpc.DpcData; ApcRoutine
0x14000337e  mov     cs:WPP_MAIN_CB.SecurityDescriptor, rax
0x140003385  xor     edx, edx; Event
0x140003387  mov     [rsp+58h+WatchTree], 1; WatchTree
0x14000338c  lea     rax, WPP_MAIN_CB.SectorSize
0x140003393  mov     qword ptr cs:WPP_MAIN_CB.DeviceLock.Header, rcx
0x14000339a  mov     cs:WPP_MAIN_CB.Dpc.DpcData, rcx
0x1400033a1  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Blink; KeyHandle
0x1400033a8  mov     [rsp+58h+CompletionFilter], 4; CompletionFilter
0x1400033b0  mov     [rsp+58h+IoStatusBlock], rax; IoStatusBlock
0x1400033b5  call    cs:__imp_ZwNotifyChangeKey
0x1400033bc  nop     dword ptr [rax+rax+00h]
0x1400033c1  add     rsp, 58h
0x1400033c5  retn
```
