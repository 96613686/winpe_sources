# ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>(void)

- ea: `0x1800169d0`
- end: `0x1800169f9`
- name: `??1?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComMultiThreadModel@6@@ATL@@UEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180016ad8`

## callees

- `0x180009100`
- `0x180016a30`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800169dd`
- `KERNEL32!DeleteCriticalSection` at `0x1800169dd`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>(
        __int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 104));
  ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection((ATL::CComSafeDeleteCriticalSection *)(a1 + 56));
  return ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>(a1);
}

```

## disassembly

```asm
0x1800169d0  push    rbx
0x1800169d2  sub     rsp, 20h
0x1800169d6  mov     rbx, rcx
0x1800169d9  add     rcx, 68h ; 'h'; lpCriticalSection
0x1800169dd  call    cs:__imp_DeleteCriticalSection
0x1800169e3  lea     rcx, [rbx+38h]; this
0x1800169e7  call    ??1CComSafeDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComSafeDeleteCriticalSection::~CComSafeDeleteCriticalSection(void)
0x1800169ec  mov     rcx, rbx
0x1800169ef  add     rsp, 20h
0x1800169f3  pop     rbx
0x1800169f4  jmp     ??1?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@UEAA@XZ; ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>(void)
```
