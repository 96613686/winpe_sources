# ATL::CComObject<ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComSingleThreadModel>>::Release(void)

- ea: `0x18000de20`
- end: `0x18000de9e`
- name: `?Release@?$CComObject@V?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@@ATL@@UEAAKXZ`
- size: `126`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x18000de20`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000de84`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000de84`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CComObject<ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::Release(
        _DWORD *a1)
{
  int v2; // edi
  unsigned int v3; // edi
  __int64 v4; // rcx

  v2 = a1[8];
  if ( v2 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v2 - 1;
    a1[8] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180024B28);
      if ( a1 )
      {
        *(_QWORD *)a1 = &ATL::CComObject<ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::`vftable';
        a1[8] = 1;
        _InterlockedDecrement(&dword_180024B28);
        v4 = *((_QWORD *)a1 + 1);
        if ( v4 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        operator delete(a1);
      }
      _InterlockedDecrement(&dword_180024B28);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000de20  mov     [rsp+arg_0], rbx
0x18000de25  push    rdi
0x18000de26  sub     rsp, 20h
0x18000de2a  mov     rbx, rcx
0x18000de2d  mov     edi, [rcx+20h]
0x18000de30  cmp     edi, 7FFFFFFFh
0x18000de36  jnz     short loc_18000DE3F
0x18000de38  mov     edi, 7FFFFFFEh
0x18000de3d  jmp     short loc_18000DE91
0x18000de3f  sub     edi, 1
0x18000de42  mov     [rcx+20h], edi
0x18000de45  jnz     short loc_18000DE91
0x18000de47  lock inc cs:dword_180024B28
0x18000de4e  test    rbx, rbx
0x18000de51  jz      short loc_18000DE8A
0x18000de53  lea     rax, ??_7?$CComObject@V?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::`vftable'
0x18000de5a  mov     [rcx], rax
0x18000de5d  mov     dword ptr [rcx+20h], 1
0x18000de64  lock dec cs:dword_180024B28
0x18000de6b  mov     rcx, [rcx+8]
0x18000de6f  test    rcx, rcx
0x18000de72  jz      short loc_18000DE81
0x18000de74  mov     rax, [rcx]
0x18000de77  mov     rax, [rax+10h]
0x18000de7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de80  nop
0x18000de81  mov     rcx, rbx
0x18000de84  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000de8a  lock dec cs:dword_180024B28
0x18000de91  mov     eax, edi
0x18000de93  mov     rbx, [rsp+28h+arg_0]
0x18000de98  add     rsp, 20h
0x18000de9c  pop     rdi
0x18000de9d  retn
```
