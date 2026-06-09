# ATL::IEnumOnSTLImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *,std::allocator<DocInfo *>>,ATL::CComSingleThreadModel>>::Clone(IEnumUnknown * *)

- ea: `0x18000d68c`
- end: `0x18000d7ac`
- name: `?Clone@?$IEnumOnSTLImpl@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@V?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@@ATL@@UEAAJPEAPEAUIEnumUnknown@@@Z`
- size: `288`
- prototype: `__int64 __fastcall(_QWORD *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000d680`

## callees

- `0x180001370`
- `0x1800093d0`
- `0x18000d68c`
- `0x180014010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000d78e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000d78e`

## pseudocode

```c
__int64 __fastcall ATL::IEnumOnSTLImpl<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::Clone(
        _QWORD *a1,
        void **a2)
{
  int Interface; // edi
  _QWORD *v5; // rax
  _QWORD *v6; // rbx
  _QWORD **v7; // r15
  _QWORD *v8; // rsi
  __int64 v9; // rdi

  Interface = -2147467261;
  if ( a2 )
  {
    *a2 = 0;
    v5 = operator new(0x30u);
    v6 = v5;
    if ( v5 )
    {
      v5[1] = 0;
      v5[3] = 0;
      *((_DWORD *)v5 + 8) = 0;
      *v5 = &ATL::CComObject<ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::`vftable';
      _InterlockedIncrement(&dword_180024B28);
      v7 = (_QWORD **)a1[2];
      v8 = v5 + 1;
      if ( v5 != (_QWORD *)-8LL )
      {
        v9 = a1[1];
        if ( v9 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(a1[1]);
        if ( *v8 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
        *v8 = v9;
      }
      v6[2] = v7;
      v6[3] = **v7;
      v6[3] = a1[3];
      Interface = ATL::CComObjectRootBase::InternalQueryInterface(
                    v6,
                    (const struct ATL::_ATL_INTMAP_ENTRY *)&`ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>::_GetEntries'::`2'::_entries,
                    &IID_IEnumUnknown,
                    a2);
      if ( Interface < 0 )
      {
        *v6 = &ATL::CComObject<ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::`vftable';
        *((_DWORD *)v6 + 8) = 1;
        _InterlockedDecrement(&dword_180024B28);
        if ( *v8 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 16LL))(*v8);
        operator delete(v6);
      }
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x18000d68c  push    rbx
0x18000d68e  push    rbp
0x18000d68f  push    rsi
0x18000d690  push    rdi
0x18000d691  push    r13
0x18000d693  push    r14
0x18000d695  push    r15
0x18000d697  sub     rsp, 20h
0x18000d69b  mov     r14, rdx
0x18000d69e  mov     rbp, rcx
0x18000d6a1  mov     edi, 80004003h
0x18000d6a6  test    rdx, rdx
0x18000d6a9  jz      loc_18000D79B
0x18000d6af  mov     qword ptr [rdx], 0
0x18000d6b6  mov     ecx, 30h ; '0'; Size
0x18000d6bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d6c0  mov     rbx, rax
0x18000d6c3  test    rax, rax
0x18000d6c6  jz      loc_18000D796
0x18000d6cc  mov     qword ptr [rax+8], 0
0x18000d6d4  mov     qword ptr [rax+18h], 0
0x18000d6dc  mov     dword ptr [rax+20h], 0
0x18000d6e3  lea     r13, ??_7?$CComObject@V?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@@ATL@@6B@; const ATL::CComObject<ATL::CComEnumOnSTL<IEnumUnknown,&_GUID const IID_IEnumUnknown,IUnknown *,CopyDocs<IUnknown>,std::list<DocInfo *>,ATL::CComSingleThreadModel>>::`vftable'
0x18000d6ea  mov     [rax], r13
0x18000d6ed  lock inc cs:dword_180024B28
0x18000d6f4  mov     r15, [rbp+10h]
0x18000d6f8  lea     rsi, [rax+8]
0x18000d6fc  test    rsi, rsi
0x18000d6ff  jz      short loc_18000D730
0x18000d701  mov     rdi, [rbp+8]
0x18000d705  test    rdi, rdi
0x18000d708  jz      short loc_18000D719
0x18000d70a  mov     rax, [rdi]
0x18000d70d  mov     rcx, rdi
0x18000d710  mov     rax, [rax+8]
0x18000d714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d719  mov     rcx, [rsi]
0x18000d71c  test    rcx, rcx
0x18000d71f  jz      short loc_18000D72D
0x18000d721  mov     rax, [rcx]
0x18000d724  mov     rax, [rax+10h]
0x18000d728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d72d  mov     [rsi], rdi
0x18000d730  mov     [rbx+10h], r15
0x18000d734  mov     rax, [r15]
0x18000d737  mov     rcx, [rax]
0x18000d73a  mov     [rbx+18h], rcx
0x18000d73e  mov     rax, [rbp+18h]
0x18000d742  mov     [rbx+18h], rax
0x18000d746  mov     r9, r14; void **
0x18000d749  lea     r8, IID_IEnumUnknown; struct _GUID *
0x18000d750  lea     rdx, ?_entries@?1??_GetEntries@?$CComEnumOnSTL@UIEnumUnknown@@$1?IID_IEnumUnknown@@3U_GUID@@BPEAUIUnknown@@V?$CopyDocs@UIUnknown@@@@V?$list@PEAUDocInfo@@V?$allocator@PEAUDocInfo@@@std@@@std@@VCComSingleThreadModel@ATL@@@ATL@@SAPEBU_ATL_INTMAP_ENTRY@3@XZ@4QBU43@B; struct ATL::_ATL_INTMAP_ENTRY *
0x18000d757  mov     rcx, rbx; void *
0x18000d75a  call    ?InternalQueryInterface@CComObjectRootBase@ATL@@SAJPEAXPEBU_ATL_INTMAP_ENTRY@2@AEBU_GUID@@PEAPEAX@Z; ATL::CComObjectRootBase::InternalQueryInterface(void *,ATL::_ATL_INTMAP_ENTRY const *,_GUID const &,void * *)
0x18000d75f  mov     edi, eax
0x18000d761  test    eax, eax
0x18000d763  jns     short loc_18000D79B
0x18000d765  mov     [rbx], r13
0x18000d768  mov     dword ptr [rbx+20h], 1
0x18000d76f  lock dec cs:dword_180024B28
0x18000d776  mov     rcx, [rsi]
0x18000d779  test    rcx, rcx
0x18000d77c  jz      short loc_18000D78B
0x18000d77e  mov     rdx, [rcx]
0x18000d781  mov     rax, [rdx+10h]
0x18000d785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d78a  nop
0x18000d78b  mov     rcx, rbx
0x18000d78e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000d794  jmp     short loc_18000D79B
0x18000d796  mov     edi, 8007000Eh
0x18000d79b  mov     eax, edi
0x18000d79d  add     rsp, 20h
0x18000d7a1  pop     r15
0x18000d7a3  pop     r14
0x18000d7a5  pop     r13
0x18000d7a7  pop     rdi
0x18000d7a8  pop     rsi
0x18000d7a9  pop     rbp
0x18000d7aa  pop     rbx
0x18000d7ab  retn
```
