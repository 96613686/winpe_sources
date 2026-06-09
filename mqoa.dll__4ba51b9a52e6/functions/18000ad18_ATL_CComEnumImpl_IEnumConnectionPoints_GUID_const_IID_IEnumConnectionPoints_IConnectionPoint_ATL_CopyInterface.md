# ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>(void)

- ea: `0x18000ad18`
- end: `0x18000ad63`
- name: `??1?$CComEnumImpl@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@V?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAA@XZ`
- size: `75`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000ad6c`

## callees

- `0x18000178c`
- `0x1800033ec`
- `0x18000a6cc`
- `0x18000ad18`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::~CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>(
        __int64 a1)
{
  __int64 *i; // rdi

  if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
  {
    for ( i = *(__int64 **)(a1 + 16); i != *(__int64 **)(a1 + 24); ++i )
      ATL::_CopyInterface<IConnectionPoint>::destroy(i);
    operator delete(*(void **)(a1 + 16));
  }
  return R<IADs>::~R<IADs>(a1 + 8);
}

```

## disassembly

```asm
0x18000ad18  mov     [rsp+arg_0], rbx
0x18000ad1d  push    rdi
0x18000ad1e  sub     rsp, 20h
0x18000ad22  mov     rbx, rcx
0x18000ad25  test    byte ptr [rcx+28h], 2
0x18000ad29  jz      short loc_18000AD50
0x18000ad2b  mov     rdi, [rcx+10h]
0x18000ad2f  cmp     rdi, [rcx+18h]
0x18000ad33  jz      short loc_18000AD47
0x18000ad35  mov     rcx, rdi
0x18000ad38  call    ?destroy@?$_CopyInterface@UIConnectionPoint@@@ATL@@SAXPEAPEAUIConnectionPoint@@@Z; ATL::_CopyInterface<IConnectionPoint>::destroy(IConnectionPoint * *)
0x18000ad3d  add     rdi, 8
0x18000ad41  cmp     rdi, [rbx+18h]
0x18000ad45  jnz     short loc_18000AD35
0x18000ad47  mov     rcx, [rbx+10h]; Block
0x18000ad4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ad50  lea     rcx, [rbx+8]
0x18000ad54  mov     rbx, [rsp+28h+arg_0]
0x18000ad59  add     rsp, 20h
0x18000ad5d  pop     rdi
0x18000ad5e  jmp     ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
```
