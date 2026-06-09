# DllCanUnloadNow

- ea: `0x180007be0`
- end: `0x180007bfb`
- name: `DllCanUnloadNow`
- size: `27`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007be0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( g_cLoaderComponent )
    LODWORD(v0) = 1;
  else
    return g_cLoaderLock != 0;
  return v0;
}

```

## disassembly

```asm
0x180007be0  cmp     cs:?g_cLoaderComponent@@3JA, 0; long g_cLoaderComponent
0x180007be7  jnz     short loc_180007BF5
0x180007be9  xor     eax, eax
0x180007beb  cmp     cs:?g_cLoaderLock@@3JA, eax; long g_cLoaderLock
0x180007bf1  setnz   al
0x180007bf4  retn
0x180007bf5  mov     eax, 1
0x180007bfa  retn
```
