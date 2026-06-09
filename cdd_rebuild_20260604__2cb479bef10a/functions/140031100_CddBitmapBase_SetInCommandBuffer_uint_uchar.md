# CddBitmapBase::SetInCommandBuffer(uint,uchar)

- ea: `0x140031100`
- end: `0x140031108`
- name: `?SetInCommandBuffer@CddBitmapBase@@UEAAXIE@Z`
- size: `8`
- prototype: `void __fastcall(CddBitmapBase *__hidden this, unsigned int, unsigned __int8)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void __fastcall CddBitmapBase::SetInCommandBuffer(CddBitmapBase *this, unsigned int a2, char a3)
{
  *((_BYTE *)this + a2 + 44) = a3;
}

```

## disassembly

```asm
0x140031100  mov     eax, edx
0x140031102  mov     [rax+rcx+2Ch], r8b
0x140031107  retn
```
