# IHttpTokenKey::GetCacheName(void)

- ea: `0x18000d770`
- end: `0x18000d778`
- name: `?GetCacheName@IHttpTokenKey@@UEBAPEBGXZ`
- size: `8`
- prototype: `const unsigned __int16 *__fastcall(IHttpTokenKey *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x18000d770`: `TOKEN`

## pseudocode

```c
const unsigned __int16 *__fastcall IHttpTokenKey::GetCacheName(IHttpTokenKey *this)
{
  return L"TOKEN";
}

```

## disassembly

```asm
0x18000d770  lea     rax, aToken; "TOKEN"
0x18000d777  retn
```
