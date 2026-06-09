# VmbusTlIsContainerPartition

- ea: `0x140002ffc`
- end: `0x14000302c`
- name: `VmbusTlIsContainerPartition`
- size: `48`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140004dec`
- `0x14001dfd8`
- `0x14001e5ac`
- `0x14001febc`

## callees

- `0x140002ffc`

## pseudocode

```c
bool __fastcall VmbusTlIsContainerPartition(__int64 a1)
{
  return (*(_QWORD *)(a1 + 232) != *(_QWORD *)&HV_GUID_CHILDREN.Data1
       || *(_QWORD *)(a1 + 240) != *(_QWORD *)HV_GUID_CHILDREN.Data4)
      && !*(_BYTE *)(a1 + 248);
}

```

## disassembly

```asm
0x140002ffc  mov     rax, [rcx+0E8h]
0x140003003  cmp     rax, qword ptr cs:HV_GUID_CHILDREN.Data1
0x14000300a  jnz     short loc_14000301C
0x14000300c  mov     rax, [rcx+0F0h]
0x140003013  cmp     rax, qword ptr cs:HV_GUID_CHILDREN.Data4
0x14000301a  jz      short loc_140003029
0x14000301c  cmp     byte ptr [rcx+0F8h], 0
0x140003023  jnz     short loc_140003029
0x140003025  mov     al, 1
0x140003027  retn
0x140003029  xor     al, al
0x14000302b  retn
```
