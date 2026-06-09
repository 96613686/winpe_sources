# ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>(void)

- ea: `0x1800652cc`
- end: `0x180065302`
- name: `??1?$CComEnum@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@QEAA@XZ`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800653ec`

## callees

- `0x180065368`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x1800652d9`
- `MSDART!MPDeleteCriticalSection` at `0x1800652e9`
- `MSDART!MPDeleteCriticalSection` at `0x1800652d9`
- `MSDART!MPDeleteCriticalSection` at `0x1800652e9`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>(
        __int64 a1)
{
  MPDeleteCriticalSection(a1 + 64);
  MPDeleteCriticalSection(a1 + 56);
  return ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(a1);
}

```

## disassembly

```asm
0x1800652cc  push    rbx
0x1800652ce  sub     rsp, 20h
0x1800652d2  mov     rbx, rcx
0x1800652d5  add     rcx, 40h ; '@'
0x1800652d9  call    cs:__imp_MPDeleteCriticalSection
0x1800652e0  nop     dword ptr [rax+rax+00h]
0x1800652e5  lea     rcx, [rbx+38h]
0x1800652e9  call    cs:__imp_MPDeleteCriticalSection
0x1800652f0  nop     dword ptr [rax+rax+00h]
0x1800652f5  mov     rcx, rbx
0x1800652f8  add     rsp, 20h
0x1800652fc  pop     rbx
0x1800652fd  jmp     ??1?$CComEnumImpl@UIEnumConnections@@$1?IID_IEnumConnections@@3U_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@QEAA@XZ; ATL::CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&_GUID const IID_IEnumConnections,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(void)
```
