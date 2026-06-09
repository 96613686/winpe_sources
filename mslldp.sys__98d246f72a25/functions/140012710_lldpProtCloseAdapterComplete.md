# lldpProtCloseAdapterComplete

- ea: `0x140012710`
- end: `0x140012727`
- name: `lldpProtCloseAdapterComplete`
- size: `23`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012730`

## pseudocode

```c
void __fastcall lldpProtCloseAdapterComplete(_QWORD *a1)
{
  a1[1] = 0;
  lldpCleanupBinding(a1);
}

```

## disassembly

```asm
0x140012710  sub     rsp, 28h
0x140012714  mov     qword ptr [rcx+8], 0
0x14001271c  call    lldpCleanupBinding
0x140012721  add     rsp, 28h
0x140012725  retn
```
