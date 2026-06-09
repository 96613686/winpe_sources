# ATL::CComObjectGlobal<CAccStore>::Release(void)

- ea: `0x180012050`
- end: `0x18001205e`
- name: `?Release@?$CComObjectGlobal@VCAccStore@@@ATL@@UEAAKXZ`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 ATL::CComObjectGlobal<CAccStore>::Release()
{
  return (unsigned int)_InterlockedDecrement(&dword_180024B28);
}

```

## disassembly

```asm
0x180012050  or      eax, 0FFFFFFFFh
0x180012053  lock xadd cs:dword_180024B28, eax
0x18001205b  dec     eax
0x18001205d  retn
```
