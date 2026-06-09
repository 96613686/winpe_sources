# W3_URL_INFO_CACHE::ReferenceRecord(void *)

- ea: `0x180001380`
- end: `0x18000138f`
- name: `?ReferenceRecord@W3_URL_INFO_CACHE@@UEAAXPEAX@Z`
- size: `15`
- prototype: `void __fastcall(W3_URL_INFO_CACHE *__hidden this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180003010`

## pseudocode

```c
void __fastcall W3_URL_INFO_CACHE::ReferenceRecord(W3_URL_INFO_CACHE *this, void *a2)
{
  (*(void (__fastcall **)(void *))(*(_QWORD *)a2 + 8LL))(a2);
}

```

## disassembly

```asm
0x180001380  mov     rax, [rdx]
0x180001383  mov     rcx, rdx
0x180001386  mov     rax, [rax+8]
0x18000138a  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
