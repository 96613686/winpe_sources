# WskStopClientModule

- ea: `0x140001c70`
- end: `0x140001cb0`
- name: `WskStopClientModule`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001d010`

## callees

- `0x140001c70`

## import_xrefs

- `NETIO!NmrDeregisterClient` at `0x140001c80`
- `NETIO!NmrDeregisterClient` at `0x140001c80`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140001c93`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140001c93`

## pseudocode

```c
NTSTATUS WskStopClientModule()
{
  NTSTATUS result; // eax

  if ( WskClientHandle )
  {
    NmrDeregisterClient(WskClientHandle);
    result = NmrWaitForClientDeregisterComplete(WskClientHandle);
    WskClientHandle = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140001c70  sub     rsp, 28h
0x140001c74  mov     rcx, cs:WskClientHandle; NmrClientHandle
0x140001c7b  test    rcx, rcx
0x140001c7e  jz      short loc_140001CAA
0x140001c80  call    cs:__imp_NmrDeregisterClient
0x140001c87  nop     dword ptr [rax+rax+00h]
0x140001c8c  mov     rcx, cs:WskClientHandle; NmrClientHandle
0x140001c93  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x140001c9a  nop     dword ptr [rax+rax+00h]
0x140001c9f  mov     cs:WskClientHandle, 0
0x140001caa  add     rsp, 28h
0x140001cae  retn
```
