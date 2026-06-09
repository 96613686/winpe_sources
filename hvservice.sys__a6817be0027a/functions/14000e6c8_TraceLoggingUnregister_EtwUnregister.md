# TraceLoggingUnregister_EtwUnregister

- ea: `0x14000e6c8`
- end: `0x14000e6f3`
- name: `TraceLoggingUnregister_EtwUnregister`
- size: `43`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000e520`
- `0x14000e600`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x14000e6e1`
- `ntoskrnl!EtwUnregister` at `0x14000e6e1`

## pseudocode

```c
NTSTATUS __fastcall TraceLoggingUnregister_EtwUnregister(__int64 a1)
{
  REGHANDLE v2; // rcx

  v2 = *(_QWORD *)(a1 + 32);
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 32) = 0;
  return EtwUnregister(v2);
}

```

## disassembly

```asm
0x14000e6c8  sub     rsp, 28h
0x14000e6cc  mov     rax, rcx
0x14000e6cf  mov     rcx, [rcx+20h]; RegHandle
0x14000e6d3  mov     dword ptr [rax], 0
0x14000e6d9  mov     qword ptr [rax+20h], 0
0x14000e6e1  call    cs:__imp_EtwUnregister
0x14000e6e8  nop     dword ptr [rax+rax+00h]
0x14000e6ed  add     rsp, 28h
0x14000e6f1  retn
```
