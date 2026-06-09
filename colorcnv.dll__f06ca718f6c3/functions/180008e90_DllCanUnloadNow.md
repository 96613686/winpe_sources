# DllCanUnloadNow

- ea: `0x180008e90`
- end: `0x180008ead`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008e90`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( CClassFactory::m_cLocked > 0 )
    LODWORD(v0) = 1;
  else
    return g_cActiveObjects != 0;
  return v0;
}

```

## disassembly

```asm
0x180008e90  cmp     cs:?m_cLocked@CClassFactory@@0HA, 0; int CClassFactory::m_cLocked
0x180008e97  jg      short loc_180008EA7
0x180008e99  mov     ecx, cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x180008e9f  xor     eax, eax
0x180008ea1  test    ecx, ecx
0x180008ea3  setnz   al
0x180008ea6  retn
0x180008ea7  mov     eax, 1
0x180008eac  retn
```
