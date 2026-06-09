# WskStopClientModule

- ea: `0x14000752c`
- end: `0x14000756c`
- name: `WskStopClientModule`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400159f0`

## callees

- `0x14000752c`

## import_xrefs

- `NETIO!NmrDeregisterClient` at `0x14000753c`
- `NETIO!NmrDeregisterClient` at `0x14000753c`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14000754f`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14000754f`

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
0x14000752c  sub     rsp, 28h
0x140007530  mov     rcx, cs:WskClientHandle; NmrClientHandle
0x140007537  test    rcx, rcx
0x14000753a  jz      short loc_140007566
0x14000753c  call    cs:__imp_NmrDeregisterClient
0x140007543  nop     dword ptr [rax+rax+00h]
0x140007548  mov     rcx, cs:WskClientHandle; NmrClientHandle
0x14000754f  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x140007556  nop     dword ptr [rax+rax+00h]
0x14000755b  mov     cs:WskClientHandle, 0
0x140007566  add     rsp, 28h
0x14000756a  retn
```
