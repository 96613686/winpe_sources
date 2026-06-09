# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeLongArray>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006dd0`
- end: `0x180006eca`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCCertEncodeLongArray@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001014`
- `0x1800022ac`
- `0x18000413c`
- `0x180006dd0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006e34`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006e34`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeLongArray>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
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
    ATL::CComTypeInfoHolder::AddRef((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
    *((_DWORD *)v6 + 4) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
    *((_QWORD *)v6 + 8) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeLongArray2>'};
    *((_DWORD *)v6 + 20) = 0;
    _InterlockedIncrement(&dword_18000F8D8);
    v5 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, a2, a3);
    if ( v5 )
    {
      *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeLongArray2>'};
      *((_DWORD *)v6 + 4) = 1;
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeLongArray::~CCertEncodeLongArray((CCertEncodeLongArray *)v6);
      operator delete(v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006dd0  push    rbx
0x180006dd2  push    rbp
0x180006dd3  push    rsi
0x180006dd4  push    rdi
0x180006dd5  push    r12
0x180006dd7  push    r15
0x180006dd9  sub     rsp, 28h
0x180006ddd  mov     rsi, r8
0x180006de0  mov     rbp, rdx
0x180006de3  test    rcx, rcx
0x180006de6  jnz     loc_180006EA6
0x180006dec  test    r8, r8
0x180006def  jnz     short loc_180006DFB
0x180006df1  mov     ebx, 80004003h
0x180006df6  jmp     loc_180006EBB
0x180006dfb  mov     ecx, 58h ; 'X'; Size
0x180006e00  mov     qword ptr [r8], 0
0x180006e07  mov     ebx, 8007000Eh
0x180006e0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006e11  mov     rdi, rax
0x180006e14  test    rax, rax
0x180006e17  jz      loc_180006EBB
0x180006e1d  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeLongArray2@@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180006e24  call    ?AddRef@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::AddRef(void)
0x180006e29  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006e2d  mov     dword ptr [rdi+10h], 0
0x180006e34  call    cs:__imp_InitializeCriticalSection
0x180006e3a  lea     r15, ??_7?$CComObject@VCCertEncodeLongArray@@@ATL@@6B?$IDispatchImpl@UICertEncodeLongArray2@@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180006e41  mov     qword ptr [rdi+40h], 0
0x180006e49  lea     r12, ??_7?$CComObject@VCCertEncodeLongArray@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeLongArray2>'}
0x180006e50  mov     [rdi], r15
0x180006e53  mov     [rdi+8], r12
0x180006e57  mov     dword ptr [rdi+50h], 0
0x180006e5e  lock inc cs:dword_18000F8D8
0x180006e65  mov     rax, [rdi]
0x180006e68  mov     r8, rsi
0x180006e6b  mov     rdx, rbp
0x180006e6e  mov     rcx, rdi
0x180006e71  mov     rax, [rax]
0x180006e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e79  mov     ebx, eax
0x180006e7b  test    eax, eax
0x180006e7d  jz      short loc_180006EBB
0x180006e7f  mov     [rdi], r15
0x180006e82  mov     rcx, rdi; this
0x180006e85  mov     [rdi+8], r12
0x180006e89  mov     dword ptr [rdi+10h], 1
0x180006e90  lock dec cs:dword_18000F8D8
0x180006e97  call    ??1CCertEncodeLongArray@@QEAA@XZ; CCertEncodeLongArray::~CCertEncodeLongArray(void)
0x180006e9c  mov     rcx, rdi; Block
0x180006e9f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006ea4  jmp     short loc_180006EBB
0x180006ea6  test    rsi, rsi
0x180006ea9  jz      loc_180006DF1
0x180006eaf  mov     qword ptr [r8], 0
0x180006eb6  mov     ebx, 80040110h
0x180006ebb  mov     eax, ebx
0x180006ebd  add     rsp, 28h
0x180006ec1  pop     r15
0x180006ec3  pop     r12
0x180006ec5  pop     rdi
0x180006ec6  pop     rsi
0x180006ec7  pop     rbp
0x180006ec8  pop     rbx
0x180006ec9  retn
```
