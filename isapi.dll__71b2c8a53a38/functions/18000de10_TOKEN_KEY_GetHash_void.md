# TOKEN_KEY::GetHash(void)

- ea: `0x18000de10`
- end: `0x18000de14`
- name: `?GetHash@TOKEN_KEY@@UEBAKXZ`
- size: `4`
- prototype: `unsigned int __fastcall(TOKEN_KEY *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall TOKEN_KEY::GetHash(TOKEN_KEY *this)
{
  return *((unsigned int *)this + 31);
}

```

## disassembly

```asm
0x18000de10  mov     eax, [rcx+7Ch]
0x18000de13  retn
```
