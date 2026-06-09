# ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>(void)

- ea: `0x180065290`
- end: `0x1800652c6`
- name: `??1?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComMultiThreadModel@6@@ATL@@QEAA@XZ`
- size: `54`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800653c8`
- `0x180065608`

## callees

- `0x180065308`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18006529d`
- `MSDART!MPDeleteCriticalSection` at `0x1800652ad`
- `MSDART!MPDeleteCriticalSection` at `0x18006529d`
- `MSDART!MPDeleteCriticalSection` at `0x1800652ad`

## pseudocode

```c
__int64 __fastcall ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>::~CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>(
        __int64 a1)
{
  MPDeleteCriticalSection(a1 + 64);
  MPDeleteCriticalSection(a1 + 56);
  return ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>(a1);
}

```

## disassembly

```asm
0x180065290  push    rbx
0x180065292  sub     rsp, 20h
0x180065296  mov     rbx, rcx
0x180065299  add     rcx, 40h ; '@'
0x18006529d  call    cs:__imp_MPDeleteCriticalSection
0x1800652a4  nop     dword ptr [rax+rax+00h]
0x1800652a9  lea     rcx, [rbx+38h]
0x1800652ad  call    cs:__imp_MPDeleteCriticalSection
0x1800652b4  nop     dword ptr [rax+rax+00h]
0x1800652b9  mov     rcx, rbx
0x1800652bc  add     rsp, 20h
0x1800652c0  pop     rbx
0x1800652c1  jmp     ??1?$CComEnumImpl@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@QEAA@XZ; ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::~CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>(void)
```
