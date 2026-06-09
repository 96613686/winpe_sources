# MupiRegisterUncHardeningConfigurationRegistryChangeNotification

- ea: `0x140015380`
- end: `0x1400153d9`
- name: `MupiRegisterUncHardeningConfigurationRegistryChangeNotification`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140014b70`
- `0x140014ea0`
- `0x1400153e0`

## import_xrefs

- `ntoskrnl!ZwNotifyChangeKey` at `0x1400153c7`
- `ntoskrnl!ZwNotifyChangeKey` at `0x1400153c7`

## pseudocode

```c
NTSTATUS __fastcall MupiRegisterUncHardeningConfigurationRegistryChangeNotification(__int64 a1)
{
  *(_QWORD *)(a1 + 56) = MupiUncHardeningRegistryWatcherKeyChangeNotification;
  *(_QWORD *)(a1 + 64) = a1;
  *(_QWORD *)(a1 + 40) = 0;
  return ZwNotifyChangeKey(
           *(HANDLE *)(a1 + 32),
           0,
           (PIO_APC_ROUTINE)(a1 + 40),
           (PVOID)1,
           (PIO_STATUS_BLOCK)(a1 + 72),
           4u,
           0,
           0,
           0,
           1u);
}

```

## disassembly

```asm
0x140015380  sub     rsp, 58h
0x140015384  xor     edx, edx; Event
0x140015386  mov     [rsp+58h+Asynchronous], 1; Asynchronous
0x14001538b  lea     r8, [rcx+28h]; ApcRoutine
0x14001538f  mov     [rsp+58h+BufferSize], edx; BufferSize
0x140015393  mov     [rsp+58h+Buffer], rdx; Buffer
0x140015398  lea     rax, MupiUncHardeningRegistryWatcherKeyChangeNotification
0x14001539f  mov     [r8+10h], rax
0x1400153a3  lea     rax, [rcx+48h]
0x1400153a7  mov     [rsp+58h+WatchTree], dl; WatchTree
0x1400153ab  lea     r9d, [rdx+1]; ApcContext
0x1400153af  mov     [r8+18h], rcx
0x1400153b3  mov     [r8], rdx
0x1400153b6  mov     rcx, [rcx+20h]; KeyHandle
0x1400153ba  mov     [rsp+58h+CompletionFilter], 4; CompletionFilter
0x1400153c2  mov     [rsp+58h+IoStatusBlock], rax; IoStatusBlock
0x1400153c7  call    cs:__imp_ZwNotifyChangeKey
0x1400153ce  nop     dword ptr [rax+rax+00h]
0x1400153d3  add     rsp, 58h
0x1400153d7  retn
```
