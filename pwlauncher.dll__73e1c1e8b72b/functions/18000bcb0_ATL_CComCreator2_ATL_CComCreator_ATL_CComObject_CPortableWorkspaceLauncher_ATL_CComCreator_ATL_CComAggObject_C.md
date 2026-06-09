# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPortableWorkspaceLauncher>>,ATL::CComCreator<ATL::CComAggObject<CPortableWorkspaceLauncher>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000bcb0`
- end: `0x18000bcbe`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCPortableWorkspaceLauncher@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCPortableWorkspaceLauncher@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000bcc4`
- `0x18000bdb0`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CPortableWorkspaceLauncher>>,ATL::CComCreator<ATL::CComAggObject<CPortableWorkspaceLauncher>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CPortableWorkspaceLauncher>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CPortableWorkspaceLauncher>>::CreateInstance();
}

```

## disassembly

```asm
0x18000bcb0  test    rcx, rcx
0x18000bcb3  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCPortableWorkspaceLauncher@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CPortableWorkspaceLauncher>>::CreateInstance(void *,_GUID const &,void * *)
0x18000bcb9  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCPortableWorkspaceLauncher@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CPortableWorkspaceLauncher>>::CreateInstance(void *,_GUID const &,void * *)
```
