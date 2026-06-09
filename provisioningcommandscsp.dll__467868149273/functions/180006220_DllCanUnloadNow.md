# DllCanUnloadNow

- ea: `0x180006220`
- end: `0x180006238`
- name: `DllCanUnloadNow`
- size: `24`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006220`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = 0;
  if ( dword_180014AB8 || dword_180014B04 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180006220  xor     eax, eax
0x180006222  cmp     cs:dword_180014AB8, eax
0x180006228  jnz     short loc_180006232
0x18000622a  cmp     cs:dword_180014B04, eax
0x180006230  jz      short locret_180006237
0x180006232  mov     eax, 1
0x180006237  retn
```
