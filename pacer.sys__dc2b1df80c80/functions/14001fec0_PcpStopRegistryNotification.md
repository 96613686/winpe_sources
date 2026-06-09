# PcpStopRegistryNotification

- ea: `0x14001fec0`
- end: `0x14001fed7`
- name: `PcpStopRegistryNotification`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14001fa50`

## pseudocode

```c
NTSTATUS PcpStopRegistryNotification()
{
  NTSTATUS result; // eax

  result = PcpDisableRegistryNotification();
  *(_QWORD *)&WPP_MAIN_CB.DeviceQueue.1 &= ~0x40uLL;
  return result;
}

```

## disassembly

```asm
0x14001fec0  sub     rsp, 28h
0x14001fec4  call    PcpDisableRegistryNotification
0x14001fec9  and     qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h, 0FFFFFFFFFFFFFFBFh
0x14001fed1  add     rsp, 28h
0x14001fed5  retn
```
