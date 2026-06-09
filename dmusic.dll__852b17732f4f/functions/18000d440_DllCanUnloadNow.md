# DllCanUnloadNow

- ea: `0x18000d440`
- end: `0x18000d45b`
- name: `DllCanUnloadNow`
- size: `27`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d440`

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
0x18000d440  cmp     cs:?g_cComponent@@3JA, 0; long g_cComponent
0x18000d447  jnz     short loc_18000D455
0x18000d449  xor     eax, eax
0x18000d44b  cmp     cs:?g_cLock@@3JA, eax; long g_cLock
0x18000d451  setnz   al
0x18000d454  retn
0x18000d455  mov     eax, 1
0x18000d45a  retn
```
