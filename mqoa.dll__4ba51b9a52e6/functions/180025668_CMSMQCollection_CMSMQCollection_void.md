# CMSMQCollection::~CMSMQCollection(void)

- ea: `0x180025668`
- end: `0x1800256d9`
- name: `??1CMSMQCollection@@QEAA@XZ`
- size: `113`
- prototype: `void __fastcall(CMSMQCollection *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180025620`

## callees

- `0x18000178c`
- `0x1800033ec`
- `0x180003848`
- `0x180026368`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800256b6`
- `KERNEL32!DeleteCriticalSection` at `0x1800256b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CMSMQCollection::~CMSMQCollection(CMSMQCollection *this)
{
  char v2; // [rsp+30h] [rbp+8h] BYREF

  std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::erase(
    (char *)this + 120,
    &v2,
    **((_QWORD **)this + 16),
    *((_QWORD *)this + 16));
  operator delete(*((void **)this + 16));
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  R<IADs>::~R<IADs>((char *)this + 72);
  ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection((CMSMQCollection *)((char *)this + 24));
}

```

## disassembly

```asm
0x180025668  mov     [rsp+arg_8], rbx
0x18002566d  push    rdi
0x18002566e  sub     rsp, 20h
0x180025672  mov     rdi, rcx
0x180025675  mov     r8, [rcx+80h]
0x18002567c  mov     r9, r8
0x18002567f  mov     r8, [r8]
0x180025682  lea     rdx, [rsp+28h+arg_0]
0x180025687  add     rcx, 78h ; 'x'
0x18002568b  call    ?erase@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@VCComVariant@2@U?$less@VCComBSTR@ATL@@@std@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@QEAA?AViterator@12@V312@0@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::erase(std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::iterator,std::_Tree<std::_Tmap_traits<ATL::CComBSTR,ATL::CComVariant,std::less<ATL::CComBSTR>,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComVariant>>,0>>::iterator)
0x180025690  mov     rcx, [rdi+80h]; Block
0x180025697  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002569c  mov     qword ptr [rdi+80h], 0
0x1800256a7  mov     qword ptr [rdi+88h], 0
0x1800256b2  lea     rcx, [rdi+50h]; lpCriticalSection
0x1800256b6  call    cs:__imp_DeleteCriticalSection
0x1800256bc  nop
0x1800256bd  lea     rcx, [rdi+48h]
0x1800256c1  call    ??1?$R@UIADs@@@@QEAA@XZ; R<IADs>::~R<IADs>(void)
0x1800256c6  lea     rcx, [rdi+18h]; this
0x1800256ca  mov     rbx, [rsp+28h+arg_8]
0x1800256cf  add     rsp, 20h
0x1800256d3  pop     rdi
0x1800256d4  jmp     ??1CComAutoDeleteCriticalSection@ATL@@QEAA@XZ; ATL::CComAutoDeleteCriticalSection::~CComAutoDeleteCriticalSection(void)
```
