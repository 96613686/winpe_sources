# CUSTOM_USER_CONTEXT::GetImpersonationToken(void)

- ea: `0x18000de20`
- end: `0x18000de28`
- name: `?GetImpersonationToken@CUSTOM_USER_CONTEXT@@UEAAPEAXXZ`
- size: `8`
- prototype: `void *__fastcall(CUSTOM_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void *__fastcall CUSTOM_USER_CONTEXT::GetImpersonationToken(CUSTOM_USER_CONTEXT *this)
{
  return (void *)*((_QWORD *)this + 16);
}

```

## disassembly

```asm
0x18000de20  mov     rax, [rcx+80h]
0x18000de27  retn
```
