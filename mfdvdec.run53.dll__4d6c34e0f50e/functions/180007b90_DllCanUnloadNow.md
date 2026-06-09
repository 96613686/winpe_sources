# DllCanUnloadNow

- ea: `0x180007b90`
- end: `0x180007bb4`
- name: `DllCanUnloadNow`
- size: `36`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180007b90`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( CClassFactory::m_cLocked > 0 || CBaseObject::m_cObjects )
    LODWORD(v0) = 1;
  else
    return s_mfModuleLockCount > 0;
  return v0;
}

```

## disassembly

```asm
0x180007b90  xor     ecx, ecx
0x180007b92  cmp     cs:?m_cLocked@CClassFactory@@0HA, ecx; int CClassFactory::m_cLocked
0x180007b98  jg      short loc_180007BAE
0x180007b9a  cmp     cs:?m_cObjects@CBaseObject@@0JA, ecx; long CBaseObject::m_cObjects
0x180007ba0  jnz     short loc_180007BAE
0x180007ba2  cmp     cs:?s_mfModuleLockCount@@3JA, ecx; long s_mfModuleLockCount
0x180007ba8  mov     eax, ecx
0x180007baa  setnle  al
0x180007bad  retn
0x180007bae  mov     eax, 1
0x180007bb3  retn
```
