# TMetabase_XMLtable::~TMetabase_XMLtable(void)

- ea: `0x18000593c`
- end: `0x180005b12`
- name: `??1TMetabase_XMLtable@@UEAA@XZ`
- size: `470`
- prototype: `void __fastcall(TMetabase_XMLtable *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005c80`

## callees

- `0x180001d84`
- `0x180001f70`
- `0x180002b90`
- `0x1800057f8`
- `0x18000584c`
- `0x180005870`
- `0x18000593c`
- `0x180005b18`
- `0x180010f14`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005a81`
- `OLEAUT32!__imp_SysFreeString` at `0x180005a8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005af6`
- `OLEAUT32!__imp_SysFreeString` at `0x180005a81`
- `OLEAUT32!__imp_SysFreeString` at `0x180005a8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180005af6`

## pseudocode

```c
void __fastcall TMetabase_XMLtable::~TMetabase_XMLtable(TMetabase_XMLtable *this)
{
  char *v2; // rdi
  __int64 v3; // rcx

  *(_QWORD *)this = &TMetabase_XMLtable::`vftable'{for `ISimpleTableWrite2'};
  *((_QWORD *)this + 1) = &TMetabase_XMLtable::`vftable'{for `ISimpleTableController'};
  *((_QWORD *)this + 2) = &TMetabase_XMLtable::`vftable'{for `ISimpleTableInterceptor'};
  *((_QWORD *)this + 3) = &TMetabase_XMLtable::`vftable'{for `TXmlParsedFileNodeFactory'};
  *((_QWORD *)this + 4) = &TMetabase_XMLtable::`vftable'{for `TMSXMLBase'};
  v2 = (char *)this + 1808;
  v3 = *((_QWORD *)this + 226);
  if ( v3 && *((_QWORD *)this + 222) )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 48LL))(v3);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 284);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 283);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 255);
  TXmlParsedFile_NoCache::~TXmlParsedFile_NoCache((TMetabase_XMLtable *)((char *)this + 1960));
  ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(v2);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 225);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 224);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 223);
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>((LPVOID *)this + 222);
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>((LPVOID *)this + 221);
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>((LPVOID *)this + 220);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 219);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 218);
  ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>((__int64 *)this + 217);
  ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>((char *)this + 1728);
  ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>((char *)this + 1720);
  ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>((char *)this + 1712);
  CCfgArray<TMetabase_XMLtable::TLocation>::~CCfgArray<TMetabase_XMLtable::TLocation>((char *)this + 1688);
  SysFreeString(*((BSTR *)this + 202));
  SysFreeString(*((BSTR *)this + 201));
  TSmartPointerArray<bool>::~TSmartPointerArray<bool>((LPVOID *)this + 199);
  TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>((LPVOID *)this + 198);
  TPublicRowName::~TPublicRowName((TMetabase_XMLtable *)((char *)this + 1536));
  `eh vector destructor iterator'((char *)this + 1392, 0x10u, 9u, (void (*)(void *))TGrowableBuffer::~TGrowableBuffer);
  `eh vector destructor iterator'((char *)this + 592, 8u, 9u, (void (*)(void *))ATL::CComBSTR::~CComBSTR);
  SysFreeString(*((BSTR *)this + 72));
  *((_QWORD *)this + 4) = &TMSXMLBase::`vftable';
}

```

## disassembly

```asm
0x18000593c  mov     [rsp+arg_0], rbx
0x180005941  push    rdi
0x180005942  sub     rsp, 20h
0x180005946  mov     rbx, rcx
0x180005949  lea     rax, ??_7TMetabase_XMLtable@@6BISimpleTableWrite2@@@; const TMetabase_XMLtable::`vftable'{for `ISimpleTableWrite2'}
0x180005950  mov     [rcx], rax
0x180005953  lea     rax, ??_7TMetabase_XMLtable@@6BISimpleTableController@@@; const TMetabase_XMLtable::`vftable'{for `ISimpleTableController'}
0x18000595a  mov     [rcx+8], rax
0x18000595e  lea     rax, ??_7TMetabase_XMLtable@@6BISimpleTableInterceptor@@@; const TMetabase_XMLtable::`vftable'{for `ISimpleTableInterceptor'}
0x180005965  mov     [rcx+10h], rax
0x180005969  lea     rax, ??_7TMetabase_XMLtable@@6BTXmlParsedFileNodeFactory@@@; const TMetabase_XMLtable::`vftable'{for `TXmlParsedFileNodeFactory'}
0x180005970  mov     [rcx+18h], rax
0x180005974  lea     rax, ??_7TMetabase_XMLtable@@6BTMSXMLBase@@@; const TMetabase_XMLtable::`vftable'{for `TMSXMLBase'}
0x18000597b  mov     [rcx+20h], rax
0x18000597f  lea     rdi, [rcx+710h]
0x180005986  mov     rcx, [rdi]
0x180005989  test    rcx, rcx
0x18000598c  jz      short loc_1800059A6
0x18000598e  mov     rdx, [rbx+6F0h]
0x180005995  test    rdx, rdx
0x180005998  jz      short loc_1800059A6
0x18000599a  mov     rax, [rcx]
0x18000599d  mov     rax, [rax+30h]
0x1800059a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059a6  lea     rcx, [rbx+8E0h]
0x1800059ad  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800059b2  lea     rcx, [rbx+8D8h]
0x1800059b9  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800059be  lea     rcx, [rbx+7F8h]
0x1800059c5  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800059ca  lea     rcx, [rbx+7A8h]; this
0x1800059d1  call    ??1TXmlParsedFile_NoCache@@UEAA@XZ; TXmlParsedFile_NoCache::~TXmlParsedFile_NoCache(void)
0x1800059d6  mov     rcx, rdi
0x1800059d9  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x1800059de  lea     rcx, [rbx+708h]
0x1800059e5  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800059ea  lea     rcx, [rbx+700h]
0x1800059f1  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x1800059f6  lea     rcx, [rbx+6F8h]
0x1800059fd  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180005a02  lea     rcx, [rbx+6F0h]; void *
0x180005a09  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x180005a0e  lea     rcx, [rbx+6E8h]; void *
0x180005a15  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x180005a1a  lea     rcx, [rbx+6E0h]; void *
0x180005a21  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x180005a26  lea     rcx, [rbx+6D8h]
0x180005a2d  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180005a32  lea     rcx, [rbx+6D0h]
0x180005a39  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180005a3e  lea     rcx, [rbx+6C8h]
0x180005a45  call    ??1?$CComPtr@UIClassFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IClassFactory>::~CComPtr<IClassFactory>(void)
0x180005a4a  lea     rcx, [rbx+6C0h]
0x180005a51  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x180005a56  lea     rcx, [rbx+6B8h]
0x180005a5d  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x180005a62  lea     rcx, [rbx+6B0h]
0x180005a69  call    ??1?$CComPtr@UIAdvancedTableDispenser@@@ATL@@QEAA@XZ; ATL::CComPtr<IAdvancedTableDispenser>::~CComPtr<IAdvancedTableDispenser>(void)
0x180005a6e  lea     rcx, [rbx+698h]
0x180005a75  call    ??1?$CCfgArray@VTLocation@TMetabase_XMLtable@@@@QEAA@XZ; CCfgArray<TMetabase_XMLtable::TLocation>::~CCfgArray<TMetabase_XMLtable::TLocation>(void)
0x180005a7a  mov     rcx, [rbx+650h]; bstrString
0x180005a81  call    cs:__imp_SysFreeString
0x180005a87  mov     rcx, [rbx+648h]; bstrString
0x180005a8e  call    cs:__imp_SysFreeString
0x180005a94  lea     rcx, [rbx+638h]; void *
0x180005a9b  call    ??1?$TSmartPointerArray@_N@@QEAA@XZ; TSmartPointerArray<bool>::~TSmartPointerArray<bool>(void)
0x180005aa0  lea     rcx, [rbx+630h]
0x180005aa7  call    ??1?$TSmartPointerArray@U__MIDL___MIDL_itf_catalog_0000_0000_0004@@@@QEAA@XZ; TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>::~TSmartPointerArray<__MIDL___MIDL_itf_catalog_0000_0000_0004>(void)
0x180005aac  lea     rcx, [rbx+600h]; this
0x180005ab3  call    ??1TPublicRowName@@QEAA@XZ; TPublicRowName::~TPublicRowName(void)
0x180005ab8  lea     rcx, [rbx+570h]; void *
0x180005abf  lea     r9, ??1TGrowableBuffer@@QEAA@XZ; void (*)(void *)
0x180005ac6  mov     edi, 9
0x180005acb  mov     r8d, edi; unsigned __int64
0x180005ace  lea     edx, [rdi+7]; unsigned __int64
0x180005ad1  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180005ad6  lea     rcx, [rbx+250h]; void *
0x180005add  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180005ae4  mov     r8d, edi; unsigned __int64
0x180005ae7  lea     edx, [rdi-1]; unsigned __int64
0x180005aea  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180005aef  mov     rcx, [rbx+240h]; bstrString
0x180005af6  call    cs:__imp_SysFreeString
0x180005afc  lea     rax, ??_7TMSXMLBase@@6B@; const TMSXMLBase::`vftable'
0x180005b03  mov     [rbx+20h], rax
0x180005b07  mov     rbx, [rsp+28h+arg_0]
0x180005b0c  add     rsp, 20h
0x180005b10  pop     rdi
0x180005b11  retn
```
