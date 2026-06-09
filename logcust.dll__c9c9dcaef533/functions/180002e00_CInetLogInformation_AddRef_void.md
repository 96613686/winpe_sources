# CInetLogInformation::AddRef(void)

- ea: `0x180002e00`
- end: `0x180002e06`
- name: `?AddRef@CInetLogInformation@@UEAAKXZ`
- size: `6`
- prototype: `unsigned int __fastcall(CInetLogInformation *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001314`

## pseudocode

```c
__int64 __fastcall CInetLogInformation::AddRef(CInetLogInformation *this)
{
  return 1;
}

```

## disassembly

```asm
0x180002e00  mov     eax, 1
0x180002e05  retn
```
