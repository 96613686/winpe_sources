# CADMCOMSrvFactoryW::LockServer(int)

- ea: `0x180009e60`
- end: `0x180009e77`
- name: `?LockServer@CADMCOMSrvFactoryW@@UEAAJH@Z`
- size: `23`
- prototype: `__int64 __fastcall(CADMCOMSrvFactoryW *__hidden this, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009e60`

## pseudocode

```c
__int64 __fastcall CADMCOMSrvFactoryW::LockServer(CADMCOMSrvFactoryW *this, int a2)
{
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)&g_dwRefCount);
  else
    _InterlockedDecrement((volatile signed __int32 *)&g_dwRefCount);
  return 0;
}

```

## disassembly

```asm
0x180009e60  test    edx, edx
0x180009e62  jz      short loc_180009E6D
0x180009e64  lock inc cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x180009e6b  jmp     short loc_180009E74
0x180009e6d  lock dec cs:?g_dwRefCount@@3KA; ulong g_dwRefCount
0x180009e74  xor     eax, eax
0x180009e76  retn
```
