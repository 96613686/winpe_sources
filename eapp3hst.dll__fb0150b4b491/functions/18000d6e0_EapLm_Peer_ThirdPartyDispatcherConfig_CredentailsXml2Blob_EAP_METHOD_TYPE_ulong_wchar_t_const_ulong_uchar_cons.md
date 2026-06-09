# EapLm::Peer::ThirdPartyDispatcherConfig::CredentailsXml2Blob(_EAP_METHOD_TYPE *,ulong,wchar_t const *,ulong,uchar const *,ulong *,uchar * *,_EAP_ERROR * *)

- ea: `0x18000d6e0`
- end: `0x18000d989`
- name: `?CredentailsXml2Blob@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJPEAU_EAP_METHOD_TYPE@@KPEB_WKPEBEPEAKPEAPEAEPEAPEAU_EAP_ERROR@@@Z`
- size: `681`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *this, struct _EAP_METHOD_TYPE *, unsigned int, const wchar_t *, unsigned int, struct IUnknown *, unsigned int *, unsigned __int8 **, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x1800017a0`
- `0x18000439c`
- `0x180004ec0`
- `0x180005894`
- `0x1800067cc`
- `0x180006c0c`
- `0x18000d098`
- `0x18000d0e8`
- `0x18000d160`
- `0x18000d184`
- `0x18000d6e0`
- `0x18000eb94`
- `0x18000ec84`
- `0x180012c10`
- `0x1800162d4`
- `0x180016e44`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::CredentailsXml2Blob(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        struct _EAP_METHOD_TYPE *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        struct IUnknown *a6,
        unsigned int *a7,
        unsigned __int8 **a8,
        struct _EAP_ERROR **a9)
{
  _QWORD *v12; // rcx
  unsigned int v13; // edi
  struct IUnknown *v14; // rdx
  ReferenceCounted *v15; // rbx
  void (__fastcall *v16)(ReferenceCounted *, _QWORD, __int64, _QWORD *, void **); // rdi
  __int64 v17; // rax
  unsigned __int8 *v18; // rax
  int *v19; // r9
  struct _EAP_ERROR *v21; // [rsp+30h] [rbp-D8h] BYREF
  struct IUnknown *v22; // [rsp+38h] [rbp-D0h] BYREF
  const struct Exception *v23; // [rsp+40h] [rbp-C8h]
  unsigned __int8 *v24; // [rsp+48h] [rbp-C0h] BYREF
  unsigned int v25; // [rsp+50h] [rbp-B8h]
  void *v26; // [rsp+58h] [rbp-B0h] BYREF
  size_t v27; // [rsp+60h] [rbp-A8h]
  ReferenceCounted *v28; // [rsp+68h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v30[2]; // [rsp+78h] [rbp-90h] BYREF
  const ATL::CAtlException *v31; // [rsp+88h] [rbp-80h] BYREF
  const EapHost::EapException *v32; // [rsp+90h] [rbp-78h] BYREF
  const Exception *v33; // [rsp+98h] [rbp-70h] BYREF
  void **v34; // [rsp+A0h] [rbp-68h] BYREF
  BYTE type; // [rsp+A8h] [rbp-60h]
  __int64 v36; // [rsp+ACh] [rbp-5Ch]
  DWORD dwAuthorId; // [rsp+B8h] [rbp-50h]

  v25 = a3;
  v22 = a6;
  v23 = (const struct Exception *)a9;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
  {
    v13 = a5;
  }
  else
  {
    v13 = a5;
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids, a3, a5);
    v12 = WPP_GLOBAL_Control;
  }
  LODWORD(v21) = 0;
  if ( a2 && a4 && a7 && a8 && a9 )
  {
    *a7 = 0;
    *a8 = 0;
    v24 = 0;
    type = a2->eapType.type;
    v36 = *(_QWORD *)&a2->eapType.dwVendorId;
    if ( type != 0xFE )
      v36 = 0;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v34 = &EapHost::EapMethodType::`vftable';
      dwAuthorId = a2->dwAuthorId;
      EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(
        *((_QWORD **)this - 12),
        (ReferenceCounted *)&v28,
        (__int64)&v34);
      v30[0] = v22;
      v30[1] = v13;
      v22 = 0;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
        (__int64)&v34,
        (__int64)a4);
      v14 = (struct IUnknown *)*EapHost::BaseXmlHelper::String2Document(&ppv, (__int64)&v34);
      if ( v14 )
        ATL::AtlComPtrAssign(&v22, v14);
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&ppv);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)&v34);
      v26 = 0;
      v27 = 0;
      v15 = v28;
      v16 = *(void (__fastcall **)(ReferenceCounted *, _QWORD, __int64, _QWORD *, void **))(*(_QWORD *)v28 + 104LL);
      v17 = ATL::CComPtrBase<IXMLDOMDocument2>::operator*((__int64 *)&v22);
      v16(v15, v25, v17, v30, &v26);
      if ( v27 )
      {
        com_ptr<unsigned char>::Assign(&v24, v26, v27);
        v18 = v24;
        v24 = 0;
        *a8 = v18;
        *a7 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v27);
      }
      HeapAllocator::Free(v26);
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v22);
      if ( v28 )
        ReferenceCounted::Release(v28);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        LODWORD(v21) = -2147024882;
        *(_QWORD *)v23 = 0;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000D92B);
        goto LABEL_19;
      }
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v31) )
      {
        LODWORD(v21) = *(_DWORD *)v31;
        *(_QWORD *)v23 = 0;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000D92D);
        goto LABEL_19;
      }
      if ( __eh34_catch_type(0, &EapHost::EapException `RTTI Type Descriptor', &v32) )
      {
        EapHost::EapException2EapErrorOle(v32, v23, &v21, v19);
        __eh34_try_continuation(0, &EapHost::EapException `RTTI Type Descriptor', &loc_18000D92F);
        goto LABEL_19;
      }
      if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', &v33) )
      {
        EapHost::Exception2EapErrorOle(v33, v23, &v21, v19);
        __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_18000D931);
      }
    }
LABEL_19:
    com_ptr<unsigned char>::Clear((void **)&v24);
    return (unsigned int)v21;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_(v12[2], 19, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000d6e0  push    rbx
0x18000d6e2  push    rsi
0x18000d6e3  push    rdi
0x18000d6e4  push    r12
0x18000d6e6  push    r13
0x18000d6e8  push    r14
0x18000d6ea  push    r15
0x18000d6ec  sub     rsp, 0D0h
0x18000d6f3  mov     rax, cs:__security_cookie
0x18000d6fa  xor     rax, rsp
0x18000d6fd  mov     [rsp+108h+var_48], rax
0x18000d705  mov     r12, r9
0x18000d708  mov     [rsp+108h+var_B8], r8d
0x18000d70d  mov     rbx, rdx
0x18000d710  mov     r13, rcx
0x18000d713  mov     rax, [rsp+108h+arg_28]
0x18000d71b  mov     [rsp+108h+var_D0], rax
0x18000d720  mov     rsi, [rsp+108h+arg_30]
0x18000d728  mov     r14, [rsp+108h+arg_38]
0x18000d730  mov     r15, [rsp+108h+arg_40]
0x18000d738  mov     [rsp+108h+var_C8], r15
0x18000d73d  lea     rax, WPP_GLOBAL_Control
0x18000d744  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d74b  cmp     rcx, rax
0x18000d74e  jz      short loc_18000D789
0x18000d750  test    byte ptr [rcx+1Ch], 4
0x18000d754  jz      short loc_18000D789
0x18000d756  mov     edx, 12h
0x18000d75b  mov     edi, [rsp+108h+arg_20]
0x18000d762  mov     dword ptr [rsp+108h+var_E8], edi
0x18000d766  mov     r9d, r8d
0x18000d769  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000d770  mov     rcx, [rcx+10h]
0x18000d774  call    WPP_SF_dd
0x18000d779  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d780  lea     rax, WPP_GLOBAL_Control
0x18000d787  jmp     short loc_18000D790
0x18000d789  mov     edi, [rsp+108h+arg_20]
0x18000d790  xor     edx, edx
0x18000d792  mov     dword ptr [rsp+108h+var_D8], edx
0x18000d796  test    rbx, rbx
0x18000d799  jz      loc_18000D941
0x18000d79f  test    r12, r12
0x18000d7a2  jz      loc_18000D941
0x18000d7a8  test    rsi, rsi
0x18000d7ab  jz      loc_18000D941
0x18000d7b1  test    r14, r14
0x18000d7b4  jz      loc_18000D941
0x18000d7ba  test    r15, r15
0x18000d7bd  jz      loc_18000D941
0x18000d7c3  mov     [rsi], edx
0x18000d7c5  mov     [r14], rdx
0x18000d7c8  mov     [rsp+108h+var_C0], rdx
0x18000d7cd  mov     cl, [rbx]
0x18000d7cf  mov     [rsp+108h+var_60], cl
0x18000d7d6  mov     eax, [rbx+4]
0x18000d7d9  mov     dword ptr [rsp+108h+var_5C], eax
0x18000d7e0  mov     eax, [rbx+8]
0x18000d7e3  mov     dword ptr [rsp+108h+var_5C+4], eax
0x18000d7ea  cmp     cl, 0FEh
0x18000d7ed  jz      short loc_18000D7F7
0x18000d7ef  mov     [rsp+108h+var_5C], rdx
0x18000d7f7  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000d7fe  mov     [rsp+108h+var_68], rax
0x18000d806  mov     eax, [rbx+0Ch]
0x18000d809  mov     [rsp+108h+var_50], eax
0x18000d810  lea     r8, [rsp+108h+var_68]
0x18000d818  lea     rdx, [rsp+108h+var_A0]
0x18000d81d  mov     rcx, [r13-60h]
0x18000d821  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000d826  nop
0x18000d827  mov     rax, [rsp+108h+var_D0]
0x18000d82c  mov     [rsp+108h+var_90], rax
0x18000d831  mov     eax, edi
0x18000d833  mov     [rsp+108h+var_88], rax
0x18000d83b  xor     r15d, r15d
0x18000d83e  mov     [rsp+108h+var_D0], r15
0x18000d843  mov     rdx, r12
0x18000d846  lea     rcx, [rsp+108h+var_68]
0x18000d84e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18000d853  nop
0x18000d854  lea     rdx, [rsp+108h+var_68]
0x18000d85c  lea     rcx, [rsp+108h+ppv]; ppv
0x18000d861  call    ?String2Document@BaseXmlHelper@EapHost@@SA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapHost::BaseXmlHelper::String2Document(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18000d866  mov     rdx, [rax]; struct IUnknown *
0x18000d869  test    rdx, rdx
0x18000d86c  jz      short loc_18000D878
0x18000d86e  lea     rcx, [rsp+108h+var_D0]; struct IUnknown **
0x18000d873  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000d878  lea     rcx, [rsp+108h+ppv]
0x18000d87d  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000d882  nop
0x18000d883  lea     rcx, [rsp+108h+var_68]
0x18000d88b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18000d890  mov     [rsp+108h+var_B0], r15
0x18000d895  mov     [rsp+108h+var_A8], r15
0x18000d89a  mov     rbx, [rsp+108h+var_A0]
0x18000d89f  mov     rax, [rbx]
0x18000d8a2  mov     rdi, [rax+68h]
0x18000d8a6  lea     rcx, [rsp+108h+var_D0]
0x18000d8ab  call    ??D?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEBAAEAUIXMLDOMDocument2@@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::operator*(void)
0x18000d8b0  lea     rcx, [rsp+108h+var_B0]
0x18000d8b5  mov     [rsp+108h+var_E8], rcx
0x18000d8ba  lea     r9, [rsp+108h+var_90]
0x18000d8bf  mov     r8, rax
0x18000d8c2  mov     edx, [rsp+108h+var_B8]
0x18000d8c6  mov     rcx, rbx
0x18000d8c9  mov     rax, rdi
0x18000d8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8d1  mov     r8, [rsp+108h+var_A8]
0x18000d8d6  test    r8, r8
0x18000d8d9  jz      short loc_18000D903
0x18000d8db  mov     rdx, [rsp+108h+var_B0]
0x18000d8e0  lea     rcx, [rsp+108h+var_C0]
0x18000d8e5  call    ?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z; com_ptr<uchar>::Assign(uchar const *,unsigned __int64)
0x18000d8ea  mov     rax, [rsp+108h+var_C0]
0x18000d8ef  mov     [rsp+108h+var_C0], r15
0x18000d8f4  mov     [r14], rax
0x18000d8f7  mov     rcx, [rsp+108h+var_A8]
0x18000d8fc  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000d901  mov     [rsi], eax
0x18000d903  mov     rcx, [rsp+108h+var_B0]; void *
0x18000d908  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000d90d  nop
0x18000d90e  lea     rcx, [rsp+108h+var_D0]
0x18000d913  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000d918  nop
0x18000d919  mov     rcx, [rsp+108h+var_A0]; this
0x18000d91e  test    rcx, rcx
0x18000d921  jz      short loc_18000D929
0x18000d923  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000d928  nop
0x18000d929  jmp     short loc_18000D931
0x18000d92b  jmp     short loc_18000D931
0x18000d92d  jmp     short loc_18000D931
0x18000d92f  jmp     short $+2
0x18000d931  lea     rcx, [rsp+108h+var_C0]
0x18000d936  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18000d93b  mov     eax, dword ptr [rsp+108h+var_D8]
0x18000d93f  jmp     short loc_18000D966
0x18000d941  cmp     rcx, rax
0x18000d944  jz      short loc_18000D961
0x18000d946  test    byte ptr [rcx+1Ch], 1
0x18000d94a  jz      short loc_18000D961
0x18000d94c  mov     edx, 13h
0x18000d951  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000d958  mov     rcx, [rcx+10h]
0x18000d95c  call    WPP_SF_
0x18000d961  mov     eax, 80004003h
0x18000d966  mov     rcx, [rsp+108h+var_48]
0x18000d96e  xor     rcx, rsp; StackCookie
0x18000d971  call    __security_check_cookie
0x18000d976  add     rsp, 0D0h
0x18000d97d  pop     r15
0x18000d97f  pop     r14
0x18000d981  pop     r13
0x18000d983  pop     r12
0x18000d985  pop     rdi
0x18000d986  pop     rsi
0x18000d987  pop     rbx
0x18000d988  retn
```
