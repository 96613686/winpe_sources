# XMLScrServProv::AddRef(void)

- ea: `0x1400111d0`
- end: `0x1400111dd`
- name: `?AddRef@XMLScrServProv@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(XMLScrServProv *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## pseudocode

```c
__int64 __fastcall XMLScrServProv::AddRef(XMLScrServProv *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 4);
}

```

## disassembly

```asm
0x1400111d0  mov     eax, 1
0x1400111d5  lock xadd [rcx+10h], eax
0x1400111da  inc     eax
0x1400111dc  retn
```
