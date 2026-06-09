# DllCanUnloadNow

- ea: `0x180005f50`
- end: `0x180005f68`
- name: `DllCanUnloadNow`
- size: `24`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005f50`

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
0x180005f50  xor     eax, eax
0x180005f52  cmp     cs:dword_180014AB8, eax
0x180005f58  jnz     short loc_180005F62
0x180005f5a  cmp     cs:dword_180014B04, eax
0x180005f60  jz      short locret_180005F67
0x180005f62  mov     eax, 1
0x180005f67  retn
```
