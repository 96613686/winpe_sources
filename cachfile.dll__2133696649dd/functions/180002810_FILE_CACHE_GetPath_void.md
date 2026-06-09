# FILE_CACHE::GetPath(void *)

- ea: `0x180002810`
- end: `0x18000281f`
- name: `?GetPath@FILE_CACHE@@UEAAPEBGPEAX@Z`
- size: `15`
- prototype: `const unsigned __int16 *__fastcall(FILE_CACHE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180004010`

## pseudocode

```c
const unsigned __int16 *__fastcall FILE_CACHE::GetPath(FILE_CACHE *this, void *a2)
{
  return (const unsigned __int16 *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)a2 + 88LL))(a2);
}

```

## disassembly

```asm
0x180002810  mov     rax, [rdx]
0x180002813  mov     rcx, rdx
0x180002816  mov     rax, [rax+58h]
0x18000281a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
