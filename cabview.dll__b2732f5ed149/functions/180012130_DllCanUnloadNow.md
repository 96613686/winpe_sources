# DllCanUnloadNow

- ea: `0x180012130`
- end: `0x18001213c`
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
  return g_cRefThisDll != 0;
}

```

## disassembly

```asm
0x180012130  xor     eax, eax
0x180012132  cmp     cs:?g_cRefThisDll@@3JA, eax; long g_cRefThisDll
0x180012138  setnz   al
0x18001213b  retn
```
