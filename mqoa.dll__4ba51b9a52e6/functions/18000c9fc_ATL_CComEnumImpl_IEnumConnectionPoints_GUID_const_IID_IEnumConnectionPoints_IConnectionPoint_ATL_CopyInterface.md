# ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::Clone(IEnumConnectionPoints * *)

- ea: `0x18000c9fc`
- end: `0x18000caff`
- name: `?Clone@?$CComEnumImpl@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@V?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@UEAAJPEAPEAUIEnumConnectionPoints@@@Z`
- size: `259`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c9f0`

## callees

- `0x1800033ec`
- `0x180009144`
- `0x180009174`
- `0x18000962c`
- `0x18000b678`
- `0x18000c9fc`
- `0x18000e260`
- `0x18000f23c`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::Clone(
        __int64 a1,
        void **a2)
{
  int Interface; // ebx
  int v5; // ebp
  _QWORD *v6; // rax
  int v7; // r15d
  _QWORD *v8; // rsi
  void *Block; // [rsp+68h] [rbp+10h] BYREF
  char v11; // [rsp+70h] [rbp+18h] BYREF
  char v12; // [rsp+78h] [rbp+20h] BYREF

  Interface = -2147467261;
  if ( a2 )
  {
    *a2 = 0;
    Block = 0;
    Interface = ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::CreateInstance(&Block);
    if ( Interface >= 0 )
    {
      v5 = 1;
      if ( (*(_BYTE *)(a1 + 40) & 1) != 0 )
      {
        v6 = (_QWORD *)ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(&v12, a1);
        v7 = 0;
      }
      else
      {
        v6 = (_QWORD *)ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(&v11, a1 + 8);
        v5 = 0;
        v7 = 2;
      }
      v8 = Block;
      Interface = ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::Init(
                    Block,
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 24),
                    *v6,
                    0);
      if ( v7 )
        R<IADs>::~R<IADs>(&v11);
      if ( v5 )
        R<IADs>::~R<IADs>(&v12);
      if ( Interface < 0
        || (v8[4] = *(_QWORD *)(a1 + 32),
            Interface = ATL::AtlInternalQueryInterface(
                          v8,
                          (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>::_GetEntries'::`2'::_entries,
                          &IID_IEnumConnectionPoints,
                          a2),
            Interface < 0) )
      {
        if ( v8 )
          ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(v8);
      }
    }
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000c9fc  mov     [rsp+arg_0], rbx
0x18000ca01  push    rbp
0x18000ca02  push    rsi
0x18000ca03  push    rdi
0x18000ca04  push    r14
0x18000ca06  push    r15
0x18000ca08  sub     rsp, 30h
0x18000ca0c  mov     r14, rdx
0x18000ca0f  mov     rdi, rcx
0x18000ca12  mov     ebx, 80004003h
0x18000ca17  test    rdx, rdx
0x18000ca1a  jz      loc_18000CAEC
0x18000ca20  lea     rcx, [rsp+58h+Block]
0x18000ca25  mov     qword ptr [rdx], 0
0x18000ca2c  mov     [rsp+58h+Block], 0
0x18000ca35  call    ?CreateInstance@?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::CreateInstance(ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>> * *)
0x18000ca3a  mov     ebx, eax
0x18000ca3c  test    eax, eax
0x18000ca3e  js      loc_18000CAEC
0x18000ca44  mov     ebp, 1
0x18000ca49  test    [rdi+28h], bpl
0x18000ca4d  jz      short loc_18000CA61
0x18000ca4f  mov     rdx, rdi
0x18000ca52  lea     rcx, [rsp+58h+arg_18]
0x18000ca57  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(IUnknown *)
0x18000ca5c  xor     r15d, r15d
0x18000ca5f  jmp     short loc_18000CA75
0x18000ca61  lea     rdx, [rdi+8]
0x18000ca65  lea     rcx, [rsp+58h+arg_10]
0x18000ca6a  call    ??0?$CComPtr@UIUnknown@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IUnknown>::CComPtr<IUnknown>(ATL::CComPtr<IUnknown> const &)
0x18000ca6f  xor     ebp, ebp
0x18000ca71  lea     r15d, [rbp+2]
0x18000ca75  mov     rsi, [rsp+58h+Block]
0x18000ca7a  mov     r9, [rax]
0x18000ca7d  mov     rcx, rsi
0x18000ca80  mov     r8, [rdi+18h]
0x18000ca84  mov     rdx, [rdi+10h]
0x18000ca88  mov     [rsp+58h+var_38], 0
0x18000ca90  call    ?Init@?$CComEnumImpl@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@V?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@6@@ATL@@QEAAJPEAPEAUIConnectionPoint@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::Init(IConnectionPoint * *,IConnectionPoint * *,IUnknown *,ATL::CComEnumFlags)
0x18000ca95  mov     ebx, eax
0x18000ca97  test    r15d, r15d
0x18000ca9a  jz      short loc_18000CAA6
0x18000ca9c  lea     rcx, [rsp+58h+arg_10]
0x18000caa1  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18000caa6  test    ebp, ebp
0x18000caa8  jz      short loc_18000CAB4
0x18000caaa  lea     rcx, [rsp+58h+arg_18]
0x18000caaf  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x18000cab4  test    ebx, ebx
0x18000cab6  js      short loc_18000CADF
0x18000cab8  mov     rax, [rdi+20h]
0x18000cabc  lea     r8, IID_IEnumConnectionPoints; struct _GUID *
0x18000cac3  mov     r9, r14; void **
0x18000cac6  mov     [rsi+20h], rax
0x18000caca  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000cad1  mov     rcx, rsi; void *
0x18000cad4  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000cad9  mov     ebx, eax
0x18000cadb  test    eax, eax
0x18000cadd  jns     short loc_18000CAEC
0x18000cadf  test    rsi, rsi
0x18000cae2  jz      short loc_18000CAEC
0x18000cae4  mov     rcx, rsi; Block
0x18000cae7  call    ??_G?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?IID_IEnumConnectionPoints@@3U_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComSingleThreadModel@6@@ATL@@@ATL@@QEAAPEAXI@Z; ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&_GUID const IID_IEnumConnectionPoints,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComSingleThreadModel>>::`scalar deleting destructor'(uint)
0x18000caec  mov     eax, ebx
0x18000caee  mov     rbx, [rsp+58h+arg_0]
0x18000caf3  add     rsp, 30h
0x18000caf7  pop     r15
0x18000caf9  pop     r14
0x18000cafb  pop     rdi
0x18000cafc  pop     rsi
0x18000cafd  pop     rbp
0x18000cafe  retn
```
