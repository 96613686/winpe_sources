# CddBitmapBase::GetInCommandBuffer(uint)

- ea: `0x140030060`
- end: `0x140030067`
- name: `?GetInCommandBuffer@CddBitmapBase@@UEBAEI@Z`
- size: `7`
- prototype: `unsigned __int8 __fastcall(CddBitmapBase *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
unsigned __int8 __fastcall CddBitmapBase::GetInCommandBuffer(CddBitmapBase *this, unsigned int a2)
{
  return *((_BYTE *)this + a2 + 44);
}

```

## disassembly

```asm
0x140030060  mov     eax, edx
0x140030062  mov     al, [rax+rcx+2Ch]
0x140030066  retn
```
