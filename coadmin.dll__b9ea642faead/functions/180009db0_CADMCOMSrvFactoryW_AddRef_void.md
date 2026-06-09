# CADMCOMSrvFactoryW::AddRef(void)

- ea: `0x180009db0`
- end: `0x180009dc4`
- name: `?AddRef@CADMCOMSrvFactoryW@@UEAAKXZ`
- size: `20`
- prototype: `unsigned int __fastcall(CADMCOMSrvFactoryW *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CADMCOMSrvFactoryW::AddRef(CADMCOMSrvFactoryW *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 2);
  _InterlockedIncrement((volatile signed __int32 *)&g_dwRefCount);
  return result;
}

```

## disassembly

```asm
0x180009db0  mov     eax, 1
0x180009db5  lock xadd [rcx+8], eax
0x180009dba  inc     eax
0x180009dbc  lock inc cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x180009dc3  retn
```
