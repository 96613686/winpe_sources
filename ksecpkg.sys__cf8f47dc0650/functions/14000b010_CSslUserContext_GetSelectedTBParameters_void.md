# CSslUserContext::GetSelectedTBParameters(void)

- ea: `0x14000b010`
- end: `0x14000b018`
- name: `?GetSelectedTBParameters@CSslUserContext@@UEAAQEAU_SecPkgContext_TokenBinding@@XZ`
- size: `8`
- prototype: `struct _SecPkgContext_TokenBinding *__fastcall(CSslUserContext *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
struct _SecPkgContext_TokenBinding *__fastcall CSslUserContext::GetSelectedTBParameters(CSslUserContext *this)
{
  return (struct _SecPkgContext_TokenBinding *)*((_QWORD *)this + 56);
}

```

## disassembly

```asm
0x14000b010  mov     rax, [rcx+1C0h]
0x14000b017  retn
```
