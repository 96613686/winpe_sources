# QosTraceEvent

- ea: `0x14000c42c`
- end: `0x14000c44d`
- name: `QosTraceEvent`
- size: `33`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000b4d0`
- `0x14000c380`
- `0x140012410`
- `0x140012ec4`

## callees

- `0x140013150`

## pseudocode

```c
__int64 __fastcall QosTraceEvent(int a1, __int64 a2)
{
  return (*(__int64 (__fastcall **)(__int64))(QosgEtwDispatchTable + 8LL * a1 + 8))(a2);
}

```

## disassembly

```asm
0x14000c42c  sub     rsp, 28h
0x14000c430  mov     rax, cs:QosgEtwDispatchTable
0x14000c437  movsxd  r8, ecx
0x14000c43a  mov     rcx, rdx
0x14000c43d  mov     rax, [rax+r8*8+8]
0x14000c442  call    _guard_dispatch_icall
0x14000c447  add     rsp, 28h
0x14000c44b  retn
```
