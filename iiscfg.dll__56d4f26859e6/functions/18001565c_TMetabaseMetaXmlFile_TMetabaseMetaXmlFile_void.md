# TMetabaseMetaXmlFile::~TMetabaseMetaXmlFile(void)

- ea: `0x18001565c`
- end: `0x1800156d4`
- name: `??1TMetabaseMetaXmlFile@@UEAA@XZ`
- size: `120`
- prototype: `void __fastcall(TMetabaseMetaXmlFile *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015f34`
- `0x1800190f0`
- `0x18002e981`

## callees

- `0x180001f70`
- `0x18000584c`
- `0x180005870`
- `0x18001551c`
- `0x180015578`

## pseudocode

```c
void __fastcall TMetabaseMetaXmlFile::~TMetabaseMetaXmlFile(TMetabaseMetaXmlFile *this)
{
  TBaseHeap::~TBaseHeap((TMetabaseMetaXmlFile *)((char *)this + 2640));
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 329);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 328);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 327);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 326);
  ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>((__int64 *)this + 325);
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>((LPVOID *)this + 101);
  *((_QWORD *)this + 35) = &TMSXMLBase::`vftable';
  TFixupHeaps::~TFixupHeaps(this);
}

```

## disassembly

```asm
0x18001565c  push    rbx
0x18001565e  sub     rsp, 20h
0x180015662  mov     rbx, rcx
0x180015665  add     rcx, 0A50h; this
0x18001566c  call    ??1TBaseHeap@@UEAA@XZ; TBaseHeap::~TBaseHeap(void)
0x180015671  lea     rcx, [rbx+0A48h]
0x180015678  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x18001567d  lea     rcx, [rbx+0A40h]
0x180015684  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180015689  lea     rcx, [rbx+0A38h]
0x180015690  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180015695  lea     rcx, [rbx+0A30h]
0x18001569c  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800156a1  lea     rcx, [rbx+0A28h]
0x1800156a8  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x1800156ad  lea     rcx, [rbx+328h]; void *
0x1800156b4  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x1800156b9  lea     rax, ??_7TMSXMLBase@@6B@; const TMSXMLBase::`vftable'
0x1800156c0  mov     rcx, rbx; this
0x1800156c3  mov     [rbx+118h], rax
0x1800156ca  add     rsp, 20h
0x1800156ce  pop     rbx
0x1800156cf  jmp     ??1TFixupHeaps@@UEAA@XZ; TFixupHeaps::~TFixupHeaps(void)
```
