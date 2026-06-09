# XMLScrSite::AddRef(void)

- ea: `0x14000e580`
- end: `0x14000e58d`
- name: `?AddRef@XMLScrSite@@UEAAKXZ`
- size: `13`
- prototype: `unsigned int __fastcall(XMLScrSite *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1400111f0`
- `0x140011200`

## pseudocode

```c
__int64 __fastcall XMLScrSite::AddRef(XMLScrSite *this)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 6);
}

```

## disassembly

```asm
0x14000e580  mov     eax, 1
0x14000e585  lock xadd [rcx+18h], eax
0x14000e58a  inc     eax
0x14000e58c  retn
```
