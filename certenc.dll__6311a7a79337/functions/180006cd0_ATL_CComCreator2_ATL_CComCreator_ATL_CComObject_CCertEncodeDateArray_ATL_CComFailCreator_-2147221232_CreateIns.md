# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeDateArray>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006cd0`
- end: `0x180006dca`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCCertEncodeDateArray@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001014`
- `0x180001a2c`
- `0x18000413c`
- `0x180006cd0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006d34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006d34`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeDateArray>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
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
    ATL::CComTypeInfoHolder::AddRef((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeDateArray2,&_GUID const IID_ICertEncodeDateArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
    *((_DWORD *)v6 + 4) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
    *((_QWORD *)v6 + 8) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeDateArray2,&_GUID const IID_ICertEncodeDateArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeDateArray2>'};
    *((_DWORD *)v6 + 20) = 0;
    _InterlockedIncrement(&dword_18000F8D8);
    v5 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, a2, a3);
    if ( v5 )
    {
      *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeDateArray2,&_GUID const IID_ICertEncodeDateArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeDateArray2>'};
      *((_DWORD *)v6 + 4) = 1;
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeDateArray::~CCertEncodeDateArray((CCertEncodeDateArray *)v6);
      operator delete(v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006cd0  push    rbx
0x180006cd2  push    rbp
0x180006cd3  push    rsi
0x180006cd4  push    rdi
0x180006cd5  push    r12
0x180006cd7  push    r15
0x180006cd9  sub     rsp, 28h
0x180006cdd  mov     rsi, r8
0x180006ce0  mov     rbp, rdx
0x180006ce3  test    rcx, rcx
0x180006ce6  jnz     loc_180006DA6
0x180006cec  test    r8, r8
0x180006cef  jnz     short loc_180006CFB
0x180006cf1  mov     ebx, 80004003h
0x180006cf6  jmp     loc_180006DBB
0x180006cfb  mov     ecx, 58h ; 'X'; Size
0x180006d00  mov     qword ptr [r8], 0
0x180006d07  mov     ebx, 8007000Eh
0x180006d0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006d11  mov     rdi, rax
0x180006d14  test    rax, rax
0x180006d17  jz      loc_180006DBB
0x180006d1d  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeDateArray2@@$1?IID_ICertEncodeDateArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180006d24  call    ?AddRef@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::AddRef(void)
0x180006d29  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006d2d  mov     dword ptr [rdi+10h], 0
0x180006d34  call    cs:__imp_InitializeCriticalSection
0x180006d3a  lea     r15, ??_7?$CComObject@VCCertEncodeDateArray@@@ATL@@6B?$IDispatchImpl@UICertEncodeDateArray2@@$1?IID_ICertEncodeDateArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeDateArray2,&_GUID const IID_ICertEncodeDateArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180006d41  mov     qword ptr [rdi+40h], 0
0x180006d49  lea     r12, ??_7?$CComObject@VCCertEncodeDateArray@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeDateArray2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeDateArray2>'}
0x180006d50  mov     [rdi], r15
0x180006d53  mov     [rdi+8], r12
0x180006d57  mov     dword ptr [rdi+50h], 0
0x180006d5e  lock inc cs:dword_18000F8D8
0x180006d65  mov     rax, [rdi]
0x180006d68  mov     r8, rsi
0x180006d6b  mov     rdx, rbp
0x180006d6e  mov     rcx, rdi
0x180006d71  mov     rax, [rax]
0x180006d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d79  mov     ebx, eax
0x180006d7b  test    eax, eax
0x180006d7d  jz      short loc_180006DBB
0x180006d7f  mov     [rdi], r15
0x180006d82  mov     rcx, rdi; this
0x180006d85  mov     [rdi+8], r12
0x180006d89  mov     dword ptr [rdi+10h], 1
0x180006d90  lock dec cs:dword_18000F8D8
0x180006d97  call    ??1CCertEncodeDateArray@@QEAA@XZ; CCertEncodeDateArray::~CCertEncodeDateArray(void)
0x180006d9c  mov     rcx, rdi; Block
0x180006d9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006da4  jmp     short loc_180006DBB
0x180006da6  test    rsi, rsi
0x180006da9  jz      loc_180006CF1
0x180006daf  mov     qword ptr [r8], 0
0x180006db6  mov     ebx, 80040110h
0x180006dbb  mov     eax, ebx
0x180006dbd  add     rsp, 28h
0x180006dc1  pop     r15
0x180006dc3  pop     r12
0x180006dc5  pop     rdi
0x180006dc6  pop     rsi
0x180006dc7  pop     rbp
0x180006dc8  pop     rbx
0x180006dc9  retn
```
