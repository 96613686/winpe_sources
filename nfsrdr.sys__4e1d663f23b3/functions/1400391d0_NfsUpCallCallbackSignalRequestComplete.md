# NfsUpCallCallbackSignalRequestComplete

- ea: `0x1400391d0`
- end: `0x1400391ef`
- name: `NfsUpCallCallbackSignalRequestComplete`
- size: `31`
- prototype: `LONG __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400391dd`
- `ntoskrnl!KeSetEvent` at `0x1400391dd`

## pseudocode

```c
LONG __fastcall NfsUpCallCallbackSignalRequestComplete(__int64 a1)
{
  return KeSetEvent((PRKEVENT)(a1 + 8), 0, 0);
}

```

## disassembly

```asm
0x1400391d0  sub     rsp, 28h
0x1400391d4  add     rcx, 8; Event
0x1400391d8  xor     r8d, r8d; Wait
0x1400391db  xor     edx, edx; Increment
0x1400391dd  call    cs:__imp_KeSetEvent
0x1400391e4  nop     dword ptr [rax+rax+00h]
0x1400391e9  add     rsp, 28h
0x1400391ed  retn
```
