# NsiCliDeregisterClient

- ea: `0x140001be0`
- end: `0x140001c68`
- name: `NsiCliDeregisterClient`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001d010`
- `0x140021080`

## callees

- `0x140001be0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140001c2d`
- `ntoskrnl!KeSetEvent` at `0x140001c2d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c56`
- `ntoskrnl!KeWaitForSingleObject` at `0x140001c56`
- `NETIO!NmrDeregisterClient` at `0x140001bf0`
- `NETIO!NmrDeregisterClient` at `0x140001bf0`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140001c03`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x140001c03`

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
0x140001be0  sub     rsp, 38h
0x140001be4  mov     rcx, cs:NsiCliHandle; NmrClientHandle
0x140001beb  test    rcx, rcx
0x140001bee  jz      short loc_140001C62
0x140001bf0  call    cs:__imp_NmrDeregisterClient
0x140001bf7  nop     dword ptr [rax+rax+00h]
0x140001bfc  mov     rcx, cs:NsiCliHandle; NmrClientHandle
0x140001c03  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x140001c0a  nop     dword ptr [rax+rax+00h]
0x140001c0f  mov     eax, 0FFFFFFFFh
0x140001c14  lock xadd cs:NsiCliDriverRefCount, eax
0x140001c1c  cmp     eax, 1
0x140001c1f  jnz     short loc_140001C39
0x140001c21  xor     r8d, r8d; Wait
0x140001c24  lea     rcx, NsiCliDriverUnloadEvent; Event
0x140001c2b  xor     edx, edx; Increment
0x140001c2d  call    cs:__imp_KeSetEvent
0x140001c34  nop     dword ptr [rax+rax+00h]
0x140001c39  xor     eax, eax
0x140001c3b  lea     rcx, NsiCliDriverUnloadEvent; Object
0x140001c42  xor     r9d, r9d; Alertable
0x140001c45  mov     cs:NsiCliHandle, rax
0x140001c4c  xor     r8d, r8d; WaitMode
0x140001c4f  mov     [rsp+38h+Timeout], rax; Timeout
0x140001c54  xor     edx, edx; WaitReason
0x140001c56  call    cs:__imp_KeWaitForSingleObject
0x140001c5d  nop     dword ptr [rax+rax+00h]
0x140001c62  add     rsp, 38h
0x140001c66  retn
```
