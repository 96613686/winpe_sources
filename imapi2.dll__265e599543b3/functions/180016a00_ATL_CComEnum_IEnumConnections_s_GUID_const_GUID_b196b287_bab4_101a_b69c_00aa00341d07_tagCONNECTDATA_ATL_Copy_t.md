# ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>(void)

- ea: `0x180016a00`
- end: `0x180016a29`
- name: `??1?$CComEnum@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@VCComMultiThreadModel@6@@ATL@@UEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016b18`

## callees

- `0x180009100`
- `0x180016a84`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180016a0d`
- `KERNEL32!DeleteCriticalSection` at `0x180016a0d`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>,ATL::CComMultiThreadModel>(
        __int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 56));
  return ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(a1);
}

```

## disassembly

```asm
0x180016a00  push    rbx
0x180016a02  sub     rsp, 20h
0x180016a06  mov     rbx, rcx
0x180016a09  add     rcx, 68h ; 'h'; lpCriticalSection
0x180016a0d  call    cs:__imp_DeleteCriticalSection
0x180016a13  lea     rcx, [rbx+38h]; this
0x180016a17  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x180016a1c  mov     rcx, rbx
0x180016a1f  add     rsp, 20h
0x180016a23  pop     rbx
0x180016a24  jmp     ??1?$CComEnumImpl@UIEnumConnections@@$1?_GUID_b196b287_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BUtagCONNECTDATA@@V?$_Copy@UtagCONNECTDATA@@@ATL@@@ATL@@UEAA@XZ; ATL::CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>::~CComEnumImpl<IEnumConnections,&__s_GUID const _GUID_b196b287_bab4_101a_b69c_00aa00341d07,tagCONNECTDATA,ATL::_Copy<tagCONNECTDATA>>(void)
```
