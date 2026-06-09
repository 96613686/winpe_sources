# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeBitString>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x180006ac0`
- end: `0x180006bb3`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCCertEncodeBitString@@@ATL@@@ATL@@V?$CComFailCreator@$0?HPPLPOPA@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `243`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callees

- `0x180001008`
- `0x180001014`
- `0x18000413c`
- `0x180004bc8`
- `0x180006ac0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006b24`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180006b24`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CCertEncodeBitString>>,ATL::CComFailCreator<-2147221232>>::CreateInstance(
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
  v6 = (char *)operator new(0x48u);
  if ( v6 )
  {
    ATL::CComTypeInfoHolder::AddRef((ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>::_tih);
    *((_DWORD *)v6 + 4) = 0;
    InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 24));
    *((_QWORD *)v6 + 8) = 0;
    *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
    *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeBitString2>'};
    _InterlockedIncrement(&dword_18000F8D8);
    v5 = (**(__int64 (__fastcall ***)(void *, __int64, _QWORD *))v6)(v6, a2, a3);
    if ( v5 )
    {
      *(_QWORD *)v6 = &ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)v6 + 1) = &ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeBitString2>'};
      *((_DWORD *)v6 + 4) = 1;
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeBitString::~CCertEncodeBitString((CCertEncodeBitString *)v6);
      operator delete(v6);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x180006ac0  push    rbx
0x180006ac2  push    rbp
0x180006ac3  push    rsi
0x180006ac4  push    rdi
0x180006ac5  push    r12
0x180006ac7  push    r15
0x180006ac9  sub     rsp, 28h
0x180006acd  mov     rsi, r8
0x180006ad0  mov     rbp, rdx
0x180006ad3  test    rcx, rcx
0x180006ad6  jnz     loc_180006B8F
0x180006adc  test    r8, r8
0x180006adf  jnz     short loc_180006AEB
0x180006ae1  mov     ebx, 80004003h
0x180006ae6  jmp     loc_180006BA4
0x180006aeb  mov     ecx, 48h ; 'H'; Size
0x180006af0  mov     qword ptr [r8], 0
0x180006af7  mov     ebx, 8007000Eh
0x180006afc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180006b01  mov     rdi, rax
0x180006b04  test    rax, rax
0x180006b07  jz      loc_180006BA4
0x180006b0d  lea     rcx, ?_tih@?$IDispatchImpl@UICertEncodeBitString2@@$1?IID_ICertEncodeBitString2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180006b14  call    ?AddRef@CComTypeInfoHolder@ATL@@QEAAXXZ; ATL::CComTypeInfoHolder::AddRef(void)
0x180006b19  lea     rcx, [rdi+18h]; lpCriticalSection
0x180006b1d  mov     dword ptr [rdi+10h], 0
0x180006b24  call    cs:__imp_InitializeCriticalSection
0x180006b2a  lea     r15, ??_7?$CComObject@VCCertEncodeBitString@@@ATL@@6B?$IDispatchImpl@UICertEncodeBitString2@@$1?IID_ICertEncodeBitString2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180006b31  mov     qword ptr [rdi+40h], 0
0x180006b39  lea     r12, ??_7?$CComObject@VCCertEncodeBitString@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeBitString2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeBitString2>'}
0x180006b40  mov     [rdi], r15
0x180006b43  mov     [rdi+8], r12
0x180006b47  lock inc cs:dword_18000F8D8
0x180006b4e  mov     rax, [rdi]
0x180006b51  mov     r8, rsi
0x180006b54  mov     rdx, rbp
0x180006b57  mov     rcx, rdi
0x180006b5a  mov     rax, [rax]
0x180006b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b62  mov     ebx, eax
0x180006b64  test    eax, eax
0x180006b66  jz      short loc_180006BA4
0x180006b68  mov     [rdi], r15
0x180006b6b  mov     rcx, rdi; this
0x180006b6e  mov     [rdi+8], r12
0x180006b72  mov     dword ptr [rdi+10h], 1
0x180006b79  lock dec cs:dword_18000F8D8
0x180006b80  call    ??1CCertEncodeBitString@@QEAA@XZ; CCertEncodeBitString::~CCertEncodeBitString(void)
0x180006b85  mov     rcx, rdi; Block
0x180006b88  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006b8d  jmp     short loc_180006BA4
0x180006b8f  test    rsi, rsi
0x180006b92  jz      loc_180006AE1
0x180006b98  mov     qword ptr [r8], 0
0x180006b9f  mov     ebx, 80040110h
0x180006ba4  mov     eax, ebx
0x180006ba6  add     rsp, 28h
0x180006baa  pop     r15
0x180006bac  pop     r12
0x180006bae  pop     rdi
0x180006baf  pop     rsi
0x180006bb0  pop     rbp
0x180006bb1  pop     rbx
0x180006bb2  retn
```
