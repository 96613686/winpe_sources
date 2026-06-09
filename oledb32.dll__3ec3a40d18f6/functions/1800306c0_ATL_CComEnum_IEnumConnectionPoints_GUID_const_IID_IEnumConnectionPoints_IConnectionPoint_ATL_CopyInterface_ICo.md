# ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>(void)

- ea: `0x1800306c0`
- end: `0x1800306ea`
- name: `??1?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComMultiThreadModel@6@@ATL@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800307e0`
- `0x180031614`

## callees

- `0x180030720`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800306cd`
- `KERNEL32!DeleteCriticalSection` at `0x1800306d7`
- `KERNEL32!DeleteCriticalSection` at `0x1800306cd`
- `KERNEL32!DeleteCriticalSection` at `0x1800306d7`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>(
        __int64 a1)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  return ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>(a1);
}

```

## disassembly

```asm
0x1800306c0  push    rbx
0x1800306c2  sub     rsp, 20h
0x1800306c6  mov     rbx, rcx
0x1800306c9  add     rcx, 60h ; '`'; lpCriticalSection
0x1800306cd  call    cs:__imp_DeleteCriticalSection
0x1800306d3  lea     rcx, [rbx+38h]; lpCriticalSection
0x1800306d7  call    cs:__imp_DeleteCriticalSection
0x1800306dd  mov     rcx, rbx
0x1800306e0  add     rsp, 20h
0x1800306e4  pop     rbx
0x1800306e5  jmp     ??1?$CComEnumImpl@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@QEAA@XZ; ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>(void)
```
