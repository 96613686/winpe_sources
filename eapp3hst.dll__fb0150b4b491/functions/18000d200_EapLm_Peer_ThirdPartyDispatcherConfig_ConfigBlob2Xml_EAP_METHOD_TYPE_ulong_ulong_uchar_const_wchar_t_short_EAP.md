# EapLm::Peer::ThirdPartyDispatcherConfig::ConfigBlob2Xml(_EAP_METHOD_TYPE *,ulong,ulong,uchar const *,wchar_t * *,short *,_EAP_ERROR * *)

- ea: `0x18000d200`
- end: `0x18000d424`
- name: `?ConfigBlob2Xml@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJPEAU_EAP_METHOD_TYPE@@KKPEBEPEAPEA_WPEAFPEAPEAU_EAP_ERROR@@@Z`
- size: `548`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, struct _EAP_METHOD_TYPE *, unsigned int, unsigned int, const unsigned __int8 *, wchar_t **, __int16 *, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800017a0`
- `0x180004ec0`
- `0x18000c910`
- `0x18000d0e8`
- `0x18000d160`
- `0x18000d200`
- `0x18000eb74`
- `0x18000eb94`
- `0x18000ec84`
- `0x180012c10`
- `0x1800160ac`
- `0x180016e44`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::ConfigBlob2Xml(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        struct _EAP_METHOD_TYPE *a2,
        unsigned int a3,
        unsigned int a4,
        const unsigned __int8 *a5,
        wchar_t **a6,
        __int16 *a7,
        struct _EAP_ERROR **a8)
{
  __int64 v8; // r13
  _QWORD *v12; // rcx
  __int64 v13; // rax
  _WORD *v14; // rax
  int *v15; // r9
  struct _EAP_ERROR *v17; // [rsp+30h] [rbp-B8h] BYREF
  const struct Exception *v18; // [rsp+38h] [rbp-B0h]
  __int64 v19; // [rsp+40h] [rbp-A8h] BYREF
  ReferenceCounted *v20; // [rsp+48h] [rbp-A0h] BYREF
  const unsigned __int8 *v21; // [rsp+50h] [rbp-98h]
  _QWORD v22[2]; // [rsp+58h] [rbp-90h] BYREF
  const ATL::CAtlException *v23; // [rsp+68h] [rbp-80h] BYREF
  const EapHost::EapException *v24; // [rsp+70h] [rbp-78h] BYREF
  const Exception *v25; // [rsp+78h] [rbp-70h] BYREF
  void **v26; // [rsp+80h] [rbp-68h] BYREF
  BYTE type; // [rsp+88h] [rbp-60h]
  _BYTE v28[12]; // [rsp+8Ch] [rbp-5Ch]
  DWORD dwAuthorId; // [rsp+98h] [rbp-50h]

  v8 = a4;
  v21 = a5;
  v18 = (const struct Exception *)a8;
  v12 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids, a3, a4);
    v12 = WPP_GLOBAL_Control;
  }
  LODWORD(v17) = 0;
  if ( a2 && a6 && a7 && a8 )
  {
    *a6 = 0;
    *a7 = 0;
    type = a2->eapType.type;
    *(_QWORD *)v28 = *(_QWORD *)&a2->eapType.dwVendorId;
    if ( type != 0xFE )
      *(_QWORD *)v28 = 0;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      v26 = &EapHost::EapMethodType::`vftable';
      dwAuthorId = a2->dwAuthorId;
      EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(
        *((_QWORD **)this - 12),
        (ReferenceCounted *)&v20,
        (__int64)&v26);
      v19 = 0;
      v22[0] = v21;
      v22[1] = v8;
      if ( (*(unsigned __int8 (__fastcall **)(ReferenceCounted *, _QWORD, _QWORD *, __int64 *))(*(_QWORD *)v20 + 112LL))(
             v20,
             a3,
             v22,
             &v19) )
      {
        v13 = ATL::CComPtrBase<IXMLDOMDocument2>::operator*(&v19);
        EapHost::BaseXmlHelper::Document2String((__int64)&v26, v13);
        if ( *(_QWORD *)&v28[4] )
        {
          v14 = (_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
          *a6 = (wchar_t *)Copy<TaskAllocator>(v14);
          *a7 = -1;
        }
        std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate((__int64)&v26);
      }
      ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(&v19);
      if ( v20 )
        ReferenceCounted::Release(v20);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        LODWORD(v17) = -2147024882;
        *(_QWORD *)v18 = 0;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000D3D0);
        return (unsigned int)v17;
      }
      if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', &v23) )
      {
        LODWORD(v17) = *(_DWORD *)v23;
        *(_QWORD *)v18 = 0;
        __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18000D3D2);
        return (unsigned int)v17;
      }
      if ( __eh34_catch_type(0, &EapHost::EapException `RTTI Type Descriptor', &v24) )
      {
        EapHost::EapException2EapErrorOle(v24, v18, &v17, v15);
        __eh34_try_continuation(0, &EapHost::EapException `RTTI Type Descriptor', &loc_18000D3D4);
        return (unsigned int)v17;
      }
      if ( __eh34_catch_type(0, &Exception `RTTI Type Descriptor', &v25) )
      {
        EapHost::Exception2EapErrorOle(v25, v18, &v17, v15);
        __eh34_try_continuation(0, &Exception `RTTI Type Descriptor', &loc_18000D3D6);
      }
    }
    return (unsigned int)v17;
  }
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 1) != 0 )
    WPP_SF_(v12[2], 21, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids);
  return 2147500035LL;
}

```

## disassembly

```asm
0x18000d200  push    rbx
0x18000d202  push    rsi
0x18000d203  push    rdi
0x18000d204  push    r12
0x18000d206  push    r13
0x18000d208  push    r14
0x18000d20a  push    r15
0x18000d20c  sub     rsp, 0B0h
0x18000d213  mov     rax, cs:__security_cookie
0x18000d21a  xor     rax, rsp
0x18000d21d  mov     [rsp+0E8h+var_48], rax
0x18000d225  mov     r13d, r9d
0x18000d228  mov     r12d, r8d
0x18000d22b  mov     rbx, rdx
0x18000d22e  mov     r15, rcx
0x18000d231  mov     rax, [rsp+0E8h+arg_20]
0x18000d239  mov     [rsp+0E8h+var_98], rax
0x18000d23e  mov     rdi, [rsp+0E8h+arg_28]
0x18000d246  mov     rsi, [rsp+0E8h+arg_30]
0x18000d24e  mov     r14, [rsp+0E8h+arg_38]
0x18000d256  mov     [rsp+0E8h+var_B0], r14
0x18000d25b  lea     rax, WPP_GLOBAL_Control
0x18000d262  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d269  cmp     rcx, rax
0x18000d26c  jz      short loc_18000D29F
0x18000d26e  test    byte ptr [rcx+1Ch], 4
0x18000d272  jz      short loc_18000D29F
0x18000d274  mov     edx, 14h
0x18000d279  mov     [rsp+0E8h+var_C8], r13d
0x18000d27e  mov     r9d, r8d
0x18000d281  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000d288  mov     rcx, [rcx+10h]
0x18000d28c  call    WPP_SF_dd
0x18000d291  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d298  lea     rax, WPP_GLOBAL_Control
0x18000d29f  xor     edx, edx
0x18000d2a1  mov     dword ptr [rsp+0E8h+var_B8], edx
0x18000d2a5  test    rbx, rbx
0x18000d2a8  jz      loc_18000D3DC
0x18000d2ae  test    rdi, rdi
0x18000d2b1  jz      loc_18000D3DC
0x18000d2b7  test    rsi, rsi
0x18000d2ba  jz      loc_18000D3DC
0x18000d2c0  test    r14, r14
0x18000d2c3  jz      loc_18000D3DC
0x18000d2c9  mov     [rdi], rdx
0x18000d2cc  mov     [rsi], dx
0x18000d2cf  mov     cl, [rbx]
0x18000d2d1  mov     [rsp+0E8h+var_60], cl
0x18000d2d8  mov     eax, [rbx+4]
0x18000d2db  mov     dword ptr [rsp+0E8h+var_5C], eax
0x18000d2e2  mov     eax, [rbx+8]
0x18000d2e5  mov     dword ptr [rsp+0E8h+var_5C+4], eax
0x18000d2ec  cmp     cl, 0FEh
0x18000d2ef  jz      short loc_18000D2F9
0x18000d2f1  mov     qword ptr [rsp+0E8h+var_5C], rdx
0x18000d2f9  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000d300  mov     [rsp+0E8h+var_68], rax
0x18000d308  mov     eax, [rbx+0Ch]
0x18000d30b  mov     [rsp+0E8h+var_50], eax
0x18000d312  lea     r8, [rsp+0E8h+var_68]
0x18000d31a  lea     rdx, [rsp+0E8h+var_A0]
0x18000d31f  mov     rcx, [r15-60h]
0x18000d323  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000d328  nop
0x18000d329  mov     [rsp+0E8h+var_A8], 0
0x18000d332  mov     rax, [rsp+0E8h+var_98]
0x18000d337  mov     [rsp+0E8h+var_90], rax
0x18000d33c  mov     [rsp+0E8h+var_88], r13
0x18000d341  mov     rcx, [rsp+0E8h+var_A0]
0x18000d346  mov     rax, [rcx]
0x18000d349  lea     r9, [rsp+0E8h+var_A8]
0x18000d34e  lea     r8, [rsp+0E8h+var_90]
0x18000d353  mov     edx, r12d
0x18000d356  mov     rax, [rax+70h]
0x18000d35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d35f  test    al, al
0x18000d361  jz      short loc_18000D3B3
0x18000d363  lea     rcx, [rsp+0E8h+var_A8]
0x18000d368  call    ??D?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEBAAEAUIXMLDOMDocument2@@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::operator*(void)
0x18000d36d  mov     rdx, rax
0x18000d370  lea     rcx, [rsp+0E8h+var_68]
0x18000d378  call    ?Document2String@BaseXmlHelper@EapHost@@SA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAUIXMLDOMDocument2@@@Z; EapHost::BaseXmlHelper::Document2String(IXMLDOMDocument2 &)
0x18000d37d  cmp     qword ptr [rsp+0E8h+var_5C+4], 0
0x18000d386  jbe     short loc_18000D3A5
0x18000d388  lea     rcx, [rsp+0E8h+var_68]
0x18000d390  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18000d395  mov     rcx, rax; Src
0x18000d398  call    ??$Copy@VTaskAllocator@@@@YAPEA_WPEB_W@Z; Copy<TaskAllocator>(wchar_t const *)
0x18000d39d  mov     [rdi], rax
0x18000d3a0  mov     word ptr [rsi], 0FFFFh
0x18000d3a5  lea     rcx, [rsp+0E8h+var_68]
0x18000d3ad  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@AEAAXXZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::_Tidy_deallocate(void)
0x18000d3b2  nop
0x18000d3b3  lea     rcx, [rsp+0E8h+var_A8]
0x18000d3b8  call    ??1?$CComPtrBase@UIXMLDOMDocument2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IXMLDOMDocument2>::~CComPtrBase<IXMLDOMDocument2>(void)
0x18000d3bd  nop
0x18000d3be  mov     rcx, [rsp+0E8h+var_A0]; this
0x18000d3c3  test    rcx, rcx
0x18000d3c6  jz      short loc_18000D3CE
0x18000d3c8  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000d3cd  nop
0x18000d3ce  jmp     short loc_18000D3D6
0x18000d3d0  jmp     short loc_18000D3D6
0x18000d3d2  jmp     short loc_18000D3D6
0x18000d3d4  jmp     short $+2
0x18000d3d6  mov     eax, dword ptr [rsp+0E8h+var_B8]
0x18000d3da  jmp     short loc_18000D401
0x18000d3dc  cmp     rcx, rax
0x18000d3df  jz      short loc_18000D3FC
0x18000d3e1  test    byte ptr [rcx+1Ch], 1
0x18000d3e5  jz      short loc_18000D3FC
0x18000d3e7  mov     edx, 15h
0x18000d3ec  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000d3f3  mov     rcx, [rcx+10h]
0x18000d3f7  call    WPP_SF_
0x18000d3fc  mov     eax, 80004003h
0x18000d401  mov     rcx, [rsp+0E8h+var_48]
0x18000d409  xor     rcx, rsp; StackCookie
0x18000d40c  call    __security_check_cookie
0x18000d411  add     rsp, 0B0h
0x18000d418  pop     r15
0x18000d41a  pop     r14
0x18000d41c  pop     r13
0x18000d41e  pop     r12
0x18000d420  pop     rdi
0x18000d421  pop     rsi
0x18000d422  pop     rbx
0x18000d423  retn
```
