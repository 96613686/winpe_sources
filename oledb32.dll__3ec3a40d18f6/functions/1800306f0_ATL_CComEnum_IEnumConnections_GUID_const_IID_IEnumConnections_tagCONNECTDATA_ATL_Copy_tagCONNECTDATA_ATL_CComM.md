# ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>(void)

- ea: `0x1800306f0`
- end: `0x18003071a`
- name: `??1?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180030804`

## callees

- `0x180030780`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800306fd`
- `KERNEL32!DeleteCriticalSection` at `0x180030707`
- `KERNEL32!DeleteCriticalSection` at `0x1800306fd`
- `KERNEL32!DeleteCriticalSection` at `0x180030707`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>(
        __int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  return ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(a1);
}

```

## disassembly

```asm
0x1800306f0  push    rbx
0x1800306f2  sub     rsp, 20h
0x1800306f6  mov     rbx, rcx
0x1800306f9  add     rcx, 60h ; '`'; lpCriticalSection
0x1800306fd  call    cs:__imp_DeleteCriticalSection
0x180030703  lea     rcx, [rbx+38h]; lpCriticalSection
0x180030707  call    cs:__imp_DeleteCriticalSection
0x18003070d  mov     rcx, rbx
0x180030710  add     rsp, 20h
0x180030714  pop     rbx
0x180030715  jmp     ??1?$CComEnumImpl@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAA@XZ; ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(void)
```
