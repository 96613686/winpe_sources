# CClassFactory::AddRef(void)

- ea: `0x180001ad0`
- end: `0x180001add`
- name: `?AddRef@CClassFactory@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(CClassFactory *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall CClassFactory::AddRef(CClassFactory *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
}

```

## disassembly

```asm
0x180001ad0  mov     eax, 1
0x180001ad5  lock xadd [rcx+8], eax
0x180001ada  inc     eax
0x180001adc  retn
```
