# ATL::CComObjectGlobal<CAccStore>::AddRef(void)

- ea: `0x18000e290`
- end: `0x18000e2a0`
- name: `?AddRef@?$CComObjectGlobal@VCAccStore@@@ATL@@UEAAKXZ`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 ATL::CComObjectGlobal<CAccStore>::AddRef()
{
  return (unsigned int)_InterlockedIncrement(&dword_180024B28);
}

```

## disassembly

```asm
0x18000e290  mov     eax, 1
0x18000e295  lock xadd cs:dword_180024B28, eax
0x18000e29d  inc     eax
0x18000e29f  retn
```
