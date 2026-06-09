# DllCanUnloadNow

- ea: `0x18000cd70`
- end: `0x18000cd8d`
- name: `DllCanUnloadNow`
- size: `29`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18000cd70`

## pseudocode

```c
HRESULT __stdcall DllCanUnloadNow()
{
  __int64 v0; // rax

  if ( CClassFactory::m_cLocked <= 0 )
    return g_cActiveObjects != 0;
  else
    LODWORD(v0) = 1;
  return v0;
}

```

## disassembly

```asm
0x18000cd70  cmp     cs:?m_cLocked@CClassFactory@@0HA, 0; int CClassFactory::m_cLocked
0x18000cd77  jle     short loc_18000CD7F
0x18000cd79  mov     eax, 1
0x18000cd7e  retn
0x18000cd7f  mov     ecx, cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18000cd85  xor     eax, eax
0x18000cd87  test    ecx, ecx
0x18000cd89  setnz   al
0x18000cd8c  retn
```
