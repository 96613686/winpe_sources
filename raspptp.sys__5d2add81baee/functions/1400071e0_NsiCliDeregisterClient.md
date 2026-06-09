# NsiCliDeregisterClient

- ea: `0x1400071e0`
- end: `0x14000726c`
- name: `NsiCliDeregisterClient`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400159f0`
- `0x14001f078`

## callees

- `0x1400071e0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000722b`
- `ntoskrnl!KeSetEvent` at `0x14000722b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000725a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000725a`
- `NETIO!NmrDeregisterClient` at `0x1400071f0`
- `NETIO!NmrDeregisterClient` at `0x1400071f0`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140007203`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140007203`

## pseudocode

```c
NTSTATUS NsiCliDeregisterClient()
{
  NTSTATUS result; // eax

  if ( NsiCliHandle )
  {
    NmrDeregisterClient(NsiCliHandle);
    NmrWaitForClientDeregisterComplete(NsiCliHandle);
    if ( _InterlockedExchangeAdd(&NsiCliDriverRefCount, 0xFFFFFFFF) == 1 )
      KeSetEvent(&NsiCliDriverUnloadEvent, 0, 0);
    NsiCliHandle = 0;
    return KeWaitForSingleObject(&NsiCliDriverUnloadEvent, Executive, 0, 0, 0);
  }
  return result;
}

```

## disassembly

```asm
0x1400071e0  sub     rsp, 38h
0x1400071e4  mov     rcx, cs:NsiCliHandle; NmrClientHandle
0x1400071eb  test    rcx, rcx
0x1400071ee  jz      short loc_140007266
0x1400071f0  call    cs:__imp_NmrDeregisterClient
0x1400071f7  nop     dword ptr [rax+rax+00h]
0x1400071fc  mov     rcx, cs:NsiCliHandle; NmrClientHandle
0x140007203  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14000720a  nop     dword ptr [rax+rax+00h]
0x14000720f  or      eax, 0FFFFFFFFh
0x140007212  lock xadd cs:NsiCliDriverRefCount, eax
0x14000721a  cmp     eax, 1
0x14000721d  jnz     short loc_140007237
0x14000721f  xor     r8d, r8d; Wait
0x140007222  lea     rcx, NsiCliDriverUnloadEvent; Event
0x140007229  xor     edx, edx; Increment
0x14000722b  call    cs:__imp_KeSetEvent
0x140007232  nop     dword ptr [rax+rax+00h]
0x140007237  xor     r9d, r9d; Alertable
0x14000723a  mov     cs:NsiCliHandle, 0
0x140007245  xor     r8d, r8d; WaitMode
0x140007248  mov     [rsp+38h+Timeout], 0; Timeout
0x140007251  xor     edx, edx; WaitReason
0x140007253  lea     rcx, NsiCliDriverUnloadEvent; Object
0x14000725a  call    cs:__imp_KeWaitForSingleObject
0x140007261  nop     dword ptr [rax+rax+00h]
0x140007266  add     rsp, 38h
0x14000726a  retn
```
