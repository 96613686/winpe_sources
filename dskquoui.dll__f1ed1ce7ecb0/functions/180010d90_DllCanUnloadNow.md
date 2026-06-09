# DllCanUnloadNow

- ea: `0x180010d90`
- end: `0x180010da8`
- name: `DllCanUnloadNow`
- size: `24`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180010d90`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT result; // eax

  result = 0;
  if ( g_cRefThisDll || g_cLockThisDll )
    return 1;
  return result;
}

```

## disassembly

```asm
0x180010d90  xor     eax, eax
0x180010d92  cmp     cs:?g_cRefThisDll@@3JA, eax; long g_cRefThisDll
0x180010d98  jnz     short loc_180010DA2
0x180010d9a  cmp     cs:?g_cLockThisDll@@3JA, eax; long g_cLockThisDll
0x180010da0  jz      short locret_180010DA7
0x180010da2  mov     eax, 1
0x180010da7  retn
```
