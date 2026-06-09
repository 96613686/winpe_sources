# CPackage::SetLinked(void)

- ea: `0x18000a400`
- end: `0x18000a40a`
- name: `?SetLinked@CPackage@@UEAAJXZ`
- size: `10`
- prototype: `__int64 __fastcall(CPackage *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CPackage::SetLinked(CPackage *this)
{
  *((_DWORD *)this + 13) = 1;
  return 0;
}

```

## disassembly

```asm
0x18000a400  mov     dword ptr [rcx+34h], 1
0x18000a407  xor     eax, eax
0x18000a409  retn
```
