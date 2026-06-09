# CWorkManager::ProcessScheduledJob(void)

- ea: `0x180049cb8`
- end: `0x180049e33`
- name: `?ProcessScheduledJob@CWorkManager@@AEAAKXZ`
- size: `379`
- prototype: `unsigned int __fastcall(CWorkManager *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x18004a8e0`

## callees

- `0x18001ad74`
- `0x18002d834`
- `0x1800497e0`
- `0x180049928`
- `0x180049964`
- `0x180049cb8`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!QueueUserWorkItem` at `0x180049d76`
- `KERNEL32!QueueUserWorkItem` at `0x180049d76`
- `KERNEL32!WaitForMultipleObjects` at `0x180049dff`
- `KERNEL32!WaitForMultipleObjects` at `0x180049dff`
- `KERNEL32!GetLastError` at `0x180049d86`
- `KERNEL32!GetLastError` at `0x180049d86`
- `KERNEL32!ResetEvent` at `0x180049d5a`
- `KERNEL32!ResetEvent` at `0x180049d5a`

## pseudocode

```c

```
