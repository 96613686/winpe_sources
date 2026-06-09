# MupiRegisterUncHardeningConfigurationRegistryChangeNotification

- ea: `0x1400153d0`
- end: `0x140015429`
- name: `MupiRegisterUncHardeningConfigurationRegistryChangeNotification`
- size: `89`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140014bc0`
- `0x140014ef0`
- `0x140015430`

## import_xrefs

- `ntoskrnl!ZwNotifyChangeKey` at `0x140015417`
- `ntoskrnl!ZwNotifyChangeKey` at `0x140015417`

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
0x1400153d0  sub     rsp, 58h
0x1400153d4  xor     edx, edx; Event
0x1400153d6  mov     [rsp+58h+Asynchronous], 1; Asynchronous
0x1400153db  lea     r8, [rcx+28h]; ApcRoutine
0x1400153df  mov     [rsp+58h+BufferSize], edx; BufferSize
0x1400153e3  mov     [rsp+58h+Buffer], rdx; Buffer
0x1400153e8  lea     rax, MupiUncHardeningRegistryWatcherKeyChangeNotification
0x1400153ef  mov     [r8+10h], rax
0x1400153f3  lea     rax, [rcx+48h]
0x1400153f7  mov     [rsp+58h+WatchTree], dl; WatchTree
0x1400153fb  lea     r9d, [rdx+1]; ApcContext
0x1400153ff  mov     [r8+18h], rcx
0x140015403  mov     [r8], rdx
0x140015406  mov     rcx, [rcx+20h]; KeyHandle
0x14001540a  mov     [rsp+58h+CompletionFilter], 4; CompletionFilter
0x140015412  mov     [rsp+58h+IoStatusBlock], rax; IoStatusBlock
0x140015417  call    cs:__imp_ZwNotifyChangeKey
0x14001541e  nop     dword ptr [rax+rax+00h]
0x140015423  add     rsp, 58h
0x140015427  retn
```
