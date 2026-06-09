# FwIntfLUIDCompare(_GUID const *,_GUID const *)

- ea: `0x180013470`
- end: `0x18001347b`
- name: `?FwIntfLUIDCompare@@YAHPEBU_GUID@@0@Z`
- size: `11`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18002f668`

## pseudocode

```c
int __fastcall FwIntfLUIDCompare(const void *a1, const void *a2)
{
  return memcmp_0(a1, a2, 0x10u);
}

```

## disassembly

```asm
0x180013470  mov     r8d, 10h; Size
0x180013476  jmp     memcmp_0
```
