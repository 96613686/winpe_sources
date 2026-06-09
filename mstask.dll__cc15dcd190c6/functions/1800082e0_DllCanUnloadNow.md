# DllCanUnloadNow

- ea: `0x1800082e0`
- end: `0x1800082ec`
- name: `DllCanUnloadNow`
- size: `12`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return CDll::s_cObjs != 0;
}

```

## disassembly

```asm
0x1800082e0  xor     eax, eax
0x1800082e2  cmp     cs:?s_cObjs@CDll@@2KA, eax; ulong CDll::s_cObjs
0x1800082e8  setnz   al
0x1800082eb  retn
```
