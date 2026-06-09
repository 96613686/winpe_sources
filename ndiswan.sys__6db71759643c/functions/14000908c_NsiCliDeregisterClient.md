# NsiCliDeregisterClient

- ea: `0x14000908c`
- end: `0x140009118`
- name: `NsiCliDeregisterClient`
- size: `140`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140026c00`
- `0x140039008`

## callees

- `0x14000908c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400090d7`
- `ntoskrnl!KeSetEvent` at `0x1400090d7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009106`
- `ntoskrnl!KeWaitForSingleObject` at `0x140009106`
- `NETIO!NmrDeregisterClient` at `0x14000909c`
- `NETIO!NmrDeregisterClient` at `0x14000909c`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400090af`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x1400090af`

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
0x14000908c  sub     rsp, 38h
0x140009090  mov     rcx, cs:NsiCliHandle; NmrClientHandle
0x140009097  test    rcx, rcx
0x14000909a  jz      short loc_140009112
0x14000909c  call    cs:__imp_NmrDeregisterClient
0x1400090a3  nop     dword ptr [rax+rax+00h]
0x1400090a8  mov     rcx, cs:NsiCliHandle; NmrClientHandle
0x1400090af  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x1400090b6  nop     dword ptr [rax+rax+00h]
0x1400090bb  or      eax, 0FFFFFFFFh
0x1400090be  lock xadd cs:NsiCliDriverRefCount, eax
0x1400090c6  cmp     eax, 1
0x1400090c9  jnz     short loc_1400090E3
0x1400090cb  xor     r8d, r8d; Wait
0x1400090ce  lea     rcx, NsiCliDriverUnloadEvent; Event
0x1400090d5  xor     edx, edx; Increment
0x1400090d7  call    cs:__imp_KeSetEvent
0x1400090de  nop     dword ptr [rax+rax+00h]
0x1400090e3  xor     r9d, r9d; Alertable
0x1400090e6  mov     cs:NsiCliHandle, 0
0x1400090f1  xor     r8d, r8d; WaitMode
0x1400090f4  mov     [rsp+38h+Timeout], 0; Timeout
0x1400090fd  xor     edx, edx; WaitReason
0x1400090ff  lea     rcx, NsiCliDriverUnloadEvent; Object
0x140009106  call    cs:__imp_KeWaitForSingleObject
0x14000910d  nop     dword ptr [rax+rax+00h]
0x140009112  add     rsp, 38h
0x140009116  retn
```
