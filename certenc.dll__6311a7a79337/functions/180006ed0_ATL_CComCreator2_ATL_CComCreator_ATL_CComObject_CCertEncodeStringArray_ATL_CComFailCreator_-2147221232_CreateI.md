# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeStringArray>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006ed0`
- end: `0x180006fca`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCCertEncodeStringArray@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001014`
- `0x18000374c`
- `0x18000413c`
- `0x180006ed0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006f34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006f34`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeStringArray>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  unsigned int v5; // ebx
  char *v6; // rdi

  if ( a1 )
  {
    if ( a3 )
    {
      *a3 = 0;
      return (unsigned int)-2147221232;
    }
    return (unsigned int)-2147467261;
  }
  if ( !a3 )
    return (unsigned int)-2147467261;
  *a3 = 0;
  v5 = -2147024882;
  v6 = (char *)operator new(0x58u);
  if ( v6 )
  {
    ATL::CComTypeInfoHolder::AddRef((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
    *((_DWORD *)v6 + 4) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
    *((_QWORD *)v6 + 8) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeStringArray2>'};
    *((_DWORD *)v6 + 20) = 0;
    _InterlockedIncrement(&dword_18000F8D8);
    v5 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, a2, a3);
    if ( v5 )
    {
      *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeStringArray2>'};
      *((_DWORD *)v6 + 4) = 1;
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeStringArray::~CCertEncodeStringArray((CCertEncodeStringArray *)v6);
      operator delete(v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006ed0  push    rbx
0x180006ed2  push    rbp
0x180006ed3  push    rsi
0x180006ed4  push    rdi
0x180006ed5  push    r12
0x180006ed7  push    r15
0x180006ed9  sub     rsp, 28h
0x180006edd  mov     rsi, r8
0x180006ee0  mov     rbp, rdx
0x180006ee3  test    rcx, rcx
0x180006ee6  jnz     loc_180006FA6
0x180006eec  test    r8, r8
0x180006eef  jnz     short loc_180006EFB
0x180006ef1  mov     ebx, 80004003h
0x180006ef6  jmp     loc_180006FBB
0x180006efb  mov     ecx, 58h ; 'X'; Size
0x180006f00  mov     qword ptr [r8], 0
0x180006f07  mov     ebx, 8007000Eh
0x180006f0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006f11  mov     rdi, rax
0x180006f14  test    rax, rax
0x180006f17  jz      loc_180006FBB
0x180006f1d  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180006f24  call    ?AddRef@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::AddRef(void)
0x180006f29  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006f2d  mov     dword ptr [rdi+10h], 0
0x180006f34  call    cs:__imp_InitializeCriticalSection
0x180006f3a  lea     r15, ??_7?$CComObject@VCCertEncodeStringArray@@@ATL@@6B?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180006f41  mov     qword ptr [rdi+40h], 0
0x180006f49  lea     r12, ??_7?$CComObject@VCCertEncodeStringArray@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeStringArray2>'}
0x180006f50  mov     [rdi], r15
0x180006f53  mov     [rdi+8], r12
0x180006f57  mov     dword ptr [rdi+50h], 0
0x180006f5e  lock inc cs:dword_18000F8D8
0x180006f65  mov     rax, [rdi]
0x180006f68  mov     r8, rsi
0x180006f6b  mov     rdx, rbp
0x180006f6e  mov     rcx, rdi
0x180006f71  mov     rax, [rax]
0x180006f74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f79  mov     ebx, eax
0x180006f7b  test    eax, eax
0x180006f7d  jz      short loc_180006FBB
0x180006f7f  mov     [rdi], r15
0x180006f82  mov     rcx, rdi; this
0x180006f85  mov     [rdi+8], r12
0x180006f89  mov     dword ptr [rdi+10h], 1
0x180006f90  lock dec cs:dword_18000F8D8
0x180006f97  call    ??1CCertEncodeStringArray@@QEAA@XZ; CCertEncodeStringArray::~CCertEncodeStringArray(void)
0x180006f9c  mov     rcx, rdi; Block
0x180006f9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006fa4  jmp     short loc_180006FBB
0x180006fa6  test    rsi, rsi
0x180006fa9  jz      loc_180006EF1
0x180006faf  mov     qword ptr [r8], 0
0x180006fb6  mov     ebx, 80040110h
0x180006fbb  mov     eax, ebx
0x180006fbd  add     rsp, 28h
0x180006fc1  pop     r15
0x180006fc3  pop     r12
0x180006fc5  pop     rdi
0x180006fc6  pop     rsi
0x180006fc7  pop     rbp
0x180006fc8  pop     rbx
0x180006fc9  retn
```
