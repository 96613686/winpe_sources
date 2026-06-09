# DMGetKnownRegPath(REFKNOWNREGID)

- ea: `0x1800102d4`
- end: `0x1800102f6`
- name: `?DMGetKnownRegPath@@YAPEBGW4REFKNOWNREGID@@@Z`
- size: `34`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180010770`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800102d8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800102d8`

## pseudocode

```c
__int64 DMGetKnownRegPath()
{
  return *(__int64 *)((char *)off_180013330 + ((unsigned __int8)RtlIsStateSeparationEnabled() != 0 ? 8 : 0));
}

```

## disassembly

```asm
0x1800102d4  sub     rsp, 28h
0x1800102d8  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800102de  neg     al
0x1800102e0  lea     rcx, off_180013330; "Software\\Microsoft\\Enrollments\\"
0x1800102e7  sbb     rax, rax
0x1800102ea  and     eax, 8
0x1800102ed  mov     rax, [rax+rcx]
0x1800102f1  add     rsp, 28h
0x1800102f5  retn
```
