# Exception::AsComError(void)

- ea: `0x18000db50`
- end: `0x18000db54`
- name: `?AsComError@Exception@@UEBAJXZ`
- size: `4`
- prototype: `__int64 __fastcall(Exception *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000db80`

## pseudocode

```c
__int64 __fastcall Exception::AsComError(Exception *this)
{
  return *((unsigned int *)this + 2);
}

```

## disassembly

```asm
0x18000db50  mov     eax, [rcx+8]
0x18000db53  retn
```
