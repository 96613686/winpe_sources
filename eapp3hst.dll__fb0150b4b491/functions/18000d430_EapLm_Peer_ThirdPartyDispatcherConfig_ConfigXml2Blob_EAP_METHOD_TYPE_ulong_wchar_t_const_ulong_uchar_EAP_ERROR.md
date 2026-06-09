# EapLm::Peer::ThirdPartyDispatcherConfig::ConfigXml2Blob(_EAP_METHOD_TYPE *,ulong,wchar_t const *,ulong *,uchar * *,_EAP_ERROR * *)

- ea: `0x18000d430`
- end: `0x18000d6cc`
- name: `?ConfigXml2Blob@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJPEAU_EAP_METHOD_TYPE@@KPEB_WPEAKPEAPEAEPEAPEAU_EAP_ERROR@@@Z`
- size: `668`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, struct _EAP_METHOD_TYPE *, unsigned int, const wchar_t *, unsigned int *, unsigned __int8 **, struct _EAP_ERROR **)`
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
- `0x18000bf94`
- `0x18000d098`
- `0x18000d0e8`
- `0x18000d160`
- `0x18000d184`
- `0x18000d430`
- `0x18000eb94`
- `0x180012c10`
- `0x1800162d4`
- `0x180016e44`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::ConfigXml2Blob(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        struct _EAP_METHOD_TYPE *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int *a5,
        unsigned __int8 **a6,
        struct _EAP_ERROR **a7)
{
  _QWORD *v11; // rcx
  struct IUnknown *v12; // rdx
  ReferenceCounted *v13; // rbx
  void (__fastcall *v14)(ReferenceCounted *, _QWORD, __int64, void **); // rdi
  __int64 v15; // rax
  unsigned __int8 *v16; // rax
  int *v17; // r9
  struct _EAP_ERROR *v19; // [rsp+30h] [rbp-B8h] BYREF
  const struct Exception *v20; // [rsp+38h] [rbp-B0h]
  unsigned __int8 *v21; // [rsp+40h] [rbp-A8h] BYREF
  struct IUnknown *v22; // [rsp+48h] [rbp-A0h] BYREF
  void *v23; // [rsp+50h] [rbp-98h] BYREF
  size_t v24; // [rsp+58h] [rbp-90h]
  ReferenceCounted *v25; // [rsp+60h] [rbp-88h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-80h] BYREF
  const ATL::CAtlException *v27; // [rsp+70h] [rbp-78h] BYREF
  const EapHost::EapException *v28; // [rsp+78h] [rbp-70h] BYREF
  const Exception *v29; // [rsp+80h] [rbp-68h] BYREF
  void **v30; // [rsp+88h] [rbp-60h] BYREF
  BYTE type; // [rsp+90h] [rbp-58h]
  __int64 v32; // [rsp+94h] [rbp-54h]
  DWORD dwAuthorId; // [rsp+A0h] [rbp-48h]

  v20 = (const struct Exception *)a7;
  LODWORD(v19) = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids, a3);
    v11 = WPP_GLOBAL_Control;
  }
  if ( a2 && a4 && a5 && a6 && a7 )
  {
    *a5 = 0;
    *a6 = 0;
    v21 = 0;
    type = a2->eapType.type;
    v32 = *(_QWORD *)&a2->eapType.dwVendorId;
    if ( type != 0xFE )
      v32 = 0;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v30 = &EapHost::EapMethodType::`vftable';
      dwAuthorId = a2->dwAuthorId;
      EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(
        *((_QWORD **)this - 12),
        (ReferenceCounted *)&v25,
        (__int64)&v30);
      v23 = 0;
      v24 = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids);
      v22 = 0;
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(
        (__int64)&v30,
        (__int64)a4);
      v12 = (struct IUnknown *)*EapHost::BaseXmlHelper::String2Document(&ppv, (__int64)&v30);
      if ( v12 )
        ATL::AtlComPtrAssign(&v22, v12);
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&ppv);
      std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)&v30);
      v13 = v25;
      v14 = *(void (__fastcall **)(ReferenceCounted *, _QWORD, __int64, void **))(*(_QWORD *)v25 + 96LL);
      v15 = ATL::CComPtrBase<IXMLDOMDocument2>::operator*((__int64 *)&v22);
      v14(v13, a3, v15, &v23);
      if ( v24 )
      {
        com_ptr<unsigned char>::Assign(&v21, v23, v24);
        v16 = v21;
        v21 = 0;
        *a6 = v16;
        *a5 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v24);
      }
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>((__int64 *)&v22);
      HeapAllocator::Free(v23);
      if ( v25 )
        ReferenceCounted::Release(v25);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        LODWORD(v19) = -2147024882;
        *(_QWORD *)v20 = 0;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000D66E);
        goto LABEL_21;
      }
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v27) )
      {
        LODWORD(v19) = *(_DWORD *)v27;
        *(_QWORD *)v20 = 0;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000D670);
        goto LABEL_21;
      }
      if ( __eh34_catch_type(0, &EapHost::EapException `RTTI Type Descriptor', &v28) )
      {
        EapHost::EapException2EapErrorOle(v28, v20, &v19, v17);
        __eh34_try_continuation(0, &EapHost::EapException `RTTI Type Descriptor', &loc_18000D672);
        goto LABEL_21;
      }
      if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', &v29) )
      {
        EapHost::Exception2EapErrorOle(v29, v20, &v19, v17);
        __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_18000D674);
      }
    }
LABEL_21:
    com_ptr<unsigned char>::Clear((void **)&v21);
    return (unsigned int)v19;
  }
  if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
    WPP_SF_(v11[2], 16, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000d430  push    rbx
0x18000d432  push    rsi
0x18000d433  push    rdi
0x18000d434  push    r12
0x18000d436  push    r13
0x18000d438  push    r14
0x18000d43a  push    r15
0x18000d43c  sub     rsp, 0B0h
0x18000d443  mov     rax, cs:__security_cookie
0x18000d44a  xor     rax, rsp
0x18000d44d  mov     [rsp+0E8h+var_40], rax
0x18000d455  mov     rsi, r9
0x18000d458  mov     r12d, r8d
0x18000d45b  mov     rbx, rdx
0x18000d45e  mov     r13, rcx
0x18000d461  mov     r14, [rsp+0E8h+arg_20]
0x18000d469  mov     r15, [rsp+0E8h+arg_28]
0x18000d471  mov     rdi, [rsp+0E8h+arg_30]
0x18000d479  mov     [rsp+0E8h+var_B0], rdi
0x18000d47e  xor     edx, edx
0x18000d480  mov     dword ptr [rsp+0E8h+var_B8], edx
0x18000d484  lea     rax, WPP_GLOBAL_Control
0x18000d48b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d492  cmp     rcx, rax
0x18000d495  jz      short loc_18000D4C5
0x18000d497  test    byte ptr [rcx+1Ch], 4
0x18000d49b  jz      short loc_18000D4C5
0x18000d49d  mov     edx, 0Fh
0x18000d4a2  mov     r9d, r8d
0x18000d4a5  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000d4ac  mov     rcx, [rcx+10h]
0x18000d4b0  call    WPP_SF_d
0x18000d4b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4bc  xor     edx, edx
0x18000d4be  lea     rax, WPP_GLOBAL_Control
0x18000d4c5  test    rbx, rbx
0x18000d4c8  jz      loc_18000D684
0x18000d4ce  test    rsi, rsi
0x18000d4d1  jz      loc_18000D684
0x18000d4d7  test    r14, r14
0x18000d4da  jz      loc_18000D684
0x18000d4e0  test    r15, r15
0x18000d4e3  jz      loc_18000D684
0x18000d4e9  test    rdi, rdi
0x18000d4ec  jz      loc_18000D684
0x18000d4f2  mov     [r14], edx
0x18000d4f5  mov     [r15], rdx
0x18000d4f8  mov     [rsp+0E8h+var_A8], rdx
0x18000d4fd  mov     cl, [rbx]
0x18000d4ff  mov     [rsp+0E8h+var_58], cl
0x18000d506  mov     eax, [rbx+4]
0x18000d509  mov     dword ptr [rsp+0E8h+var_54], eax
0x18000d510  mov     eax, [rbx+8]
0x18000d513  mov     dword ptr [rsp+0E8h+var_54+4], eax
0x18000d51a  cmp     cl, 0FEh
0x18000d51d  jz      short loc_18000D52B
0x18000d51f  mov     [rsp+0E8h+var_54], 0
0x18000d52b  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000d532  mov     [rsp+0E8h+var_60], rax
0x18000d53a  mov     eax, [rbx+0Ch]
0x18000d53d  mov     [rsp+0E8h+var_48], eax
0x18000d544  lea     r8, [rsp+0E8h+var_60]
0x18000d54c  lea     rdx, [rsp+0E8h+var_88]
0x18000d551  mov     rcx, [r13-60h]
0x18000d555  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000d55a  nop
0x18000d55b  xor     r13d, r13d
0x18000d55e  mov     [rsp+0E8h+var_98], r13
0x18000d563  mov     [rsp+0E8h+var_90], r13
0x18000d568  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d56f  lea     rax, WPP_GLOBAL_Control
0x18000d576  cmp     rcx, rax
0x18000d579  jz      short loc_18000D595
0x18000d57b  test    byte ptr [rcx+1Ch], 4
0x18000d57f  jz      short loc_18000D595
0x18000d581  lea     edx, [r13+11h]
0x18000d585  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000d58c  mov     rcx, [rcx+10h]
0x18000d590  call    WPP_SF_
0x18000d595  mov     [rsp+0E8h+var_A0], r13
0x18000d59a  mov     rdx, rsi
0x18000d59d  lea     rcx, [rsp+0E8h+var_60]
0x18000d5a5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@QEB_W@Z; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(wchar_t const * const)
0x18000d5aa  nop
0x18000d5ab  lea     rdx, [rsp+0E8h+var_60]
0x18000d5b3  lea     rcx, [rsp+0E8h+ppv]; ppv
0x18000d5b8  call    ?String2Document@BaseXmlHelper@EapHost@@SA?AV?$CComPtr@UIXMLDOMDocument2@@@ATL@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@Z; EapHost::BaseXmlHelper::String2Document(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const &)
0x18000d5bd  mov     rdx, [rax]; struct IUnknown *
0x18000d5c0  test    rdx, rdx
0x18000d5c3  jz      short loc_18000D5CF
0x18000d5c5  lea     rcx, [rsp+0E8h+var_A0]; struct IUnknown **
0x18000d5ca  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18000d5cf  lea     rcx, [rsp+0E8h+ppv]
0x18000d5d4  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000d5d9  nop
0x18000d5da  lea     rcx, [rsp+0E8h+var_60]
0x18000d5e2  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18000d5e7  mov     rbx, [rsp+0E8h+var_88]
0x18000d5ec  mov     rax, [rbx]
0x18000d5ef  mov     rdi, [rax+60h]
0x18000d5f3  lea     rcx, [rsp+0E8h+var_A0]
0x18000d5f8  call    ??D?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEBAAEAUIXMLDOMDocument2@@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::operator*(void)
0x18000d5fd  lea     r9, [rsp+0E8h+var_98]
0x18000d602  mov     r8, rax
0x18000d605  mov     edx, r12d
0x18000d608  mov     rcx, rbx
0x18000d60b  mov     rax, rdi
0x18000d60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d613  mov     r8, [rsp+0E8h+var_90]
0x18000d618  test    r8, r8
0x18000d61b  jz      short loc_18000D646
0x18000d61d  mov     rdx, [rsp+0E8h+var_98]
0x18000d622  lea     rcx, [rsp+0E8h+var_A8]
0x18000d627  call    ?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z; com_ptr<uchar>::Assign(uchar const *,unsigned __int64)
0x18000d62c  mov     rax, [rsp+0E8h+var_A8]
0x18000d631  mov     [rsp+0E8h+var_A8], r13
0x18000d636  mov     [r15], rax
0x18000d639  mov     rcx, [rsp+0E8h+var_90]
0x18000d63e  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000d643  mov     [r14], eax
0x18000d646  lea     rcx, [rsp+0E8h+var_A0]
0x18000d64b  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000d650  nop
0x18000d651  mov     rcx, [rsp+0E8h+var_98]; void *
0x18000d656  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000d65b  nop
0x18000d65c  mov     rcx, [rsp+0E8h+var_88]; this
0x18000d661  test    rcx, rcx
0x18000d664  jz      short loc_18000D66C
0x18000d666  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000d66b  nop
0x18000d66c  jmp     short loc_18000D674
0x18000d66e  jmp     short loc_18000D674
0x18000d670  jmp     short loc_18000D674
0x18000d672  jmp     short $+2
0x18000d674  lea     rcx, [rsp+0E8h+var_A8]
0x18000d679  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18000d67e  mov     eax, dword ptr [rsp+0E8h+var_B8]
0x18000d682  jmp     short loc_18000D6A9
0x18000d684  cmp     rcx, rax
0x18000d687  jz      short loc_18000D6A4
0x18000d689  test    byte ptr [rcx+1Ch], 1
0x18000d68d  jz      short loc_18000D6A4
0x18000d68f  mov     edx, 10h
0x18000d694  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000d69b  mov     rcx, [rcx+10h]
0x18000d69f  call    WPP_SF_
0x18000d6a4  mov     eax, 80004003h
0x18000d6a9  mov     rcx, [rsp+0E8h+var_40]
0x18000d6b1  xor     rcx, rsp; StackCookie
0x18000d6b4  call    __security_check_cookie
0x18000d6b9  add     rsp, 0B0h
0x18000d6c0  pop     r15
0x18000d6c2  pop     r14
0x18000d6c4  pop     r13
0x18000d6c6  pop     r12
0x18000d6c8  pop     rdi
0x18000d6c9  pop     rsi
0x18000d6ca  pop     rbx
0x18000d6cb  retn
```
