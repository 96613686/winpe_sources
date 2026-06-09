# DllCanUnloadNow

- ea: `0x180001310`
- end: `0x18000132b`
- name: `DllCanUnloadNow`
- size: `27`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001310`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  return dword_180012828 > 0 || dword_180012838 > 0;
}

```

## disassembly

```asm
0x180001310  cmp     cs:dword_180012828, 0
0x180001317  jle     short loc_18000131F
0x180001319  mov     eax, 1
0x18000131e  retn
0x18000131f  cmp     cs:dword_180012838, 0
0x180001326  jg      short loc_180001319
0x180001328  xor     eax, eax
0x18000132a  retn
```
