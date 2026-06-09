# CSslUserContext::GetSelectedApplicationProtocol(void)

- ea: `0x14000aff0`
- end: `0x14000aff8`
- name: `?GetSelectedApplicationProtocol@CSslUserContext@@UEAAQEAU_SecPkgContext_ApplicationProtocol@@XZ`
- size: `8`
- prototype: `struct _SecPkgContext_ApplicationProtocol *__fastcall(CSslUserContext *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct _SecPkgContext_ApplicationProtocol *__fastcall CSslUserContext::GetSelectedApplicationProtocol(
        CSslUserContext *this)
{
  return (struct _SecPkgContext_ApplicationProtocol *)*((_QWORD *)this + 54);
}

```

## disassembly

```asm
0x14000aff0  mov     rax, [rcx+1B0h]
0x14000aff7  retn
```
