# CSslUserContext::GetTokenBindingEKM(void)

- ea: `0x14000b050`
- end: `0x14000b058`
- name: `?GetTokenBindingEKM@CSslUserContext@@UEAAQEAU_SecPkgContext_KeyingMaterial@@XZ`
- size: `8`
- prototype: `struct _SecPkgContext_KeyingMaterial *__fastcall(CSslUserContext *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
struct _SecPkgContext_KeyingMaterial *__fastcall CSslUserContext::GetTokenBindingEKM(CSslUserContext *this)
{
  return (CSslUserContext *)((char *)this + 456);
}

```

## disassembly

```asm
0x14000b050  lea     rax, [rcx+1C8h]
0x14000b057  retn
```
