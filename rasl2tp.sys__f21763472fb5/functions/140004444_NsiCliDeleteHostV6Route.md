# NsiCliDeleteHostV6Route

- ea: `0x140004444`
- end: `0x14000445b`
- name: `NsiCliDeleteHostV6Route`
- size: `23`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001f304`

## callees

- `0x140004374`

## pseudocode

```c
__int64 __fastcall NsiCliDeleteHostV6Route(__int64 a1)
{
  return NsiCliDeleteHostRouteHelper(0x17u, a1);
}

```

## disassembly

```asm
0x140004444  sub     rsp, 28h
0x140004448  mov     rdx, rcx
0x14000444b  mov     ecx, 17h
0x140004450  call    NsiCliDeleteHostRouteHelper
0x140004455  add     rsp, 28h
0x140004459  retn
```
