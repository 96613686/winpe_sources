# DllCanUnloadNow

- ea: `0x1800019a0`
- end: `0x1800019bd`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800019a0`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  HRESULT v0; // edx

  v0 = 1;
  if ( !ModuleCount::m_Count )
    return g_ulObjCount != 0;
  return v0;
}

```

## disassembly

```asm
0x1800019a0  cmp     cs:?m_Count@ModuleCount@@0JA, 0; long ModuleCount::m_Count
0x1800019a7  mov     edx, 1
0x1800019ac  jnz     short loc_1800019BA
0x1800019ae  mov     eax, cs:?g_ulObjCount@@3KA; ulong g_ulObjCount
0x1800019b4  neg     eax
0x1800019b6  sbb     ecx, ecx
0x1800019b8  and     edx, ecx
0x1800019ba  mov     eax, edx
0x1800019bc  retn
```
