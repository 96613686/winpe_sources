# DllCanUnloadNow

- ea: `0x18000ebe0`
- end: `0x18000ebfb`
- name: `DllCanUnloadNow`
- size: `27`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000ebe0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( g_cComponent )
    LODWORD(v0) = 1;
  else
    return g_cLock != 0;
  return v0;
}

```

## disassembly

```asm
0x18000ebe0  cmp     cs:?g_cComponent@@3JA, 0; long g_cComponent
0x18000ebe7  jnz     short loc_18000EBF5
0x18000ebe9  xor     eax, eax
0x18000ebeb  cmp     cs:?g_cLock@@3JA, eax; long g_cLock
0x18000ebf1  setnz   al
0x18000ebf4  retn
0x18000ebf5  mov     eax, 1
0x18000ebfa  retn
```
