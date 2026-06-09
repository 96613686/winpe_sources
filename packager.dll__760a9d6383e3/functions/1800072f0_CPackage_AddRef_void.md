# CPackage::AddRef(void)

- ea: `0x1800072f0`
- end: `0x1800072f7`
- name: `?AddRef@CPackage@@UEAAKXZ`
- size: `7`
- prototype: `__int64 __fastcall(CPackage *this)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180007300`
- `0x180007310`
- `0x180007320`
- `0x180007330`
- `0x180007340`
- `0x180007350`
- `0x180007360`
- `0x180007370`
- `0x180007380`
- `0x180007390`

## pseudocode

```c
__int64 __fastcall CPackage::AddRef(CPackage *this)
{
  return (unsigned int)++*((_DWORD *)this + 22);
}

```

## disassembly

```asm
0x1800072f0  inc     dword ptr [rcx+58h]
0x1800072f3  mov     eax, [rcx+58h]
0x1800072f6  retn
```
