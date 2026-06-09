# ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Clone(IEnumConnectionPoints * *)

- ea: `0x1800174d0`
- end: `0x1800175e6`
- name: `?Clone@?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@UEAAJPEAPEAUIEnumConnectionPoints@@@Z`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180017430`

## callees

- `0x180005800`
- `0x18000ea20`
- `0x18000fc4c`
- `0x1800168a4`
- `0x1800174d0`
- `0x180017708`
- `0x18004a010`

## pseudocode

```c
__int64 __fastcall ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Clone(
        __int64 a1,
        void **a2)
{
  int Interface; // ebx
  int v5; // ebp
  struct IUnknown *v6; // r9
  int v7; // r15d
  _QWORD *v8; // rsi
  void *v10; // [rsp+68h] [rbp+10h] BYREF
  struct IUnknown *v11; // [rsp+70h] [rbp+18h] BYREF
  struct IUnknown *v12; // [rsp+78h] [rbp+20h] BYREF

  Interface = -2147467261;
  if ( a2 )
  {
    *a2 = 0;
    v10 = 0;
    Interface = ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>::CreateInstance(&v10);
    if ( Interface >= 0 )
    {
      v5 = 2;
      if ( (*(_BYTE *)(a1 + 40) & 2) != 0 )
      {
        ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(&v12, a1);
        v6 = v12;
        v5 = 0;
        v7 = 1;
      }
      else
      {
        ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(&v11, *(_QWORD *)(a1 + 8));
        v6 = v11;
        v7 = 0;
      }
      v8 = v10;
      Interface = ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(
                    (__int64)v10,
                    *(_QWORD *)(a1 + 16),
                    *(_QWORD *)(a1 + 24),
                    v6,
                    0);
      if ( v5 )
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v11);
      if ( v7 )
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v12);
      if ( Interface < 0
        || (v8[4] = *(_QWORD *)(a1 + 32),
            Interface = ATL::AtlInternalQueryInterface(
                          v8,
                          (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>::_GetEntries'::`2'::_entries,
                          &GUID_b196b285_bab4_101a_b69c_00aa00341d07,
                          a2),
            Interface < 0) )
      {
        if ( v8 )
          (*(void (__fastcall **)(_QWORD *, __int64))(*v8 + 56LL))(v8, 1);
      }
    }
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x1800174d0  mov     [rsp+arg_0], rbx
0x1800174d5  push    rbp
0x1800174d6  push    rsi
0x1800174d7  push    rdi
0x1800174d8  push    r14
0x1800174da  push    r15
0x1800174dc  sub     rsp, 30h
0x1800174e0  mov     r14, rdx
0x1800174e3  mov     rdi, rcx
0x1800174e6  mov     ebx, 80004003h
0x1800174eb  test    rdx, rdx
0x1800174ee  jz      loc_1800175D3
0x1800174f4  lea     rcx, [rsp+58h+arg_8]
0x1800174f9  mov     qword ptr [rdx], 0
0x180017500  mov     [rsp+58h+arg_8], 0
0x180017509  call    ?CreateInstance@?$CComObject@V?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComMultiThreadModel@6@@ATL@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>>::CreateInstance(ATL::CComObject<ATL::CComEnum<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>,ATL::CComMultiThreadModel>> * *)
0x18001750e  mov     ebx, eax
0x180017510  test    eax, eax
0x180017512  js      loc_1800175D3
0x180017518  mov     ebp, 2
0x18001751d  test    [rdi+28h], bpl
0x180017521  jz      short loc_18001753D
0x180017523  mov     rdx, rdi
0x180017526  lea     rcx, [rsp+58h+arg_18]
0x18001752b  call    ??0?$CComPtrBase@UIUnknown@@@ATL@@IEAA@PEAUIUnknown@@@Z; ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(IUnknown *)
0x180017530  mov     r9, [rsp+58h+arg_18]
0x180017535  xor     ebp, ebp
0x180017537  lea     r15d, [rbp+1]
0x18001753b  jmp     short loc_180017553
0x18001753d  mov     rdx, [rdi+8]
0x180017541  lea     rcx, [rsp+58h+arg_10]
0x180017546  call    ??0?$CComPtrBase@UIUnknown@@@ATL@@IEAA@PEAUIUnknown@@@Z; ATL::CComPtrBase<IUnknown>::CComPtrBase<IUnknown>(IUnknown *)
0x18001754b  mov     r9, [rsp+58h+arg_10]
0x180017550  xor     r15d, r15d
0x180017553  mov     rsi, [rsp+58h+arg_8]
0x180017558  mov     r8, [rdi+18h]
0x18001755c  mov     rcx, rsi
0x18001755f  mov     rdx, [rdi+10h]
0x180017563  mov     [rsp+58h+var_38], 0
0x18001756b  call    ?Init@?$CComEnumImpl@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@@ATL@@QEAAJPEAPEAUIConnectionPoint@@0PEAUIUnknown@@W4CComEnumFlags@2@@Z; ATL::CComEnumImpl<IEnumConnectionPoints,&__s_GUID const _GUID_b196b285_bab4_101a_b69c_00aa00341d07,IConnectionPoint *,ATL::_CopyInterface<IConnectionPoint>>::Init(IConnectionPoint * *,IConnectionPoint * *,IUnknown *,ATL::CComEnumFlags)
0x180017570  mov     ebx, eax
0x180017572  test    ebp, ebp
0x180017574  jz      short loc_180017580
0x180017576  lea     rcx, [rsp+58h+arg_10]
0x18001757b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180017580  test    r15d, r15d
0x180017583  jz      short loc_18001758F
0x180017585  lea     rcx, [rsp+58h+arg_18]
0x18001758a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001758f  test    ebx, ebx
0x180017591  js      short loc_1800175BA
0x180017593  mov     rax, [rdi+20h]
0x180017597  lea     r8, _GUID_b196b285_bab4_101a_b69c_00aa00341d07; struct _GUID *
0x18001759e  mov     r9, r14; void **
0x1800175a1  mov     [rsi+20h], rax
0x1800175a5  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnum@UIEnumConnectionPoints@@$1?_GUID_b196b285_bab4_101a_b69c_00aa00341d07@@3U__s_GUID@@BPEAUIConnectionPoint@@V?$_CopyInterface@UIConnectionPoint@@@ATL@@VCComMultiThreadModel@6@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x1800175ac  mov     rcx, rsi; void *
0x1800175af  call    ?AtlInternalQueryInterface@ATL@@YAJPEAXPEBU_ATL_INTMAP_ENTRY@1@AEBU_GUID@@PEAPEAX@Z; ATL::AtlInternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x1800175b4  mov     ebx, eax
0x1800175b6  test    eax, eax
0x1800175b8  jns     short loc_1800175D3
0x1800175ba  test    rsi, rsi
0x1800175bd  jz      short loc_1800175D3
0x1800175bf  mov     rax, [rsi]
0x1800175c2  mov     edx, 1
0x1800175c7  mov     rcx, rsi
0x1800175ca  mov     rax, [rax+38h]
0x1800175ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175d3  mov     eax, ebx
0x1800175d5  mov     rbx, [rsp+58h+arg_0]
0x1800175da  add     rsp, 30h
0x1800175de  pop     r15
0x1800175e0  pop     r14
0x1800175e2  pop     rdi
0x1800175e3  pop     rsi
0x1800175e4  pop     rbp
0x1800175e5  retn
```
