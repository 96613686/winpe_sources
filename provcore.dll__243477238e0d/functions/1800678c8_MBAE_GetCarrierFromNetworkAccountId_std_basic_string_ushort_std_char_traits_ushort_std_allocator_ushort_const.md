# MBAE::GetCarrierFromNetworkAccountId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800678c8`
- end: `0x180067ae3`
- name: `?GetCarrierFromNetworkAccountId@MBAE@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z`
- size: `539`
- prototype: `std::wstring *__fastcall(std::wstring *result, const std::wstring *MbaeNetworkAccountId)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005fa00`
- `0x18006230c`

## callees

- `0x180002790`
- `0x18000866c`
- `0x18000b0a0`
- `0x18000b2f4`
- `0x180011844`
- `0x180012400`
- `0x180012770`
- `0x180058a30`
- `0x1800597e8`
- `0x1800678c8`
- `0x180067bf4`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067a46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180067a46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180067923`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180067923`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006796b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18006796b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
std::wstring *__fastcall MBAE::GetCarrierFromNetworkAccountId(
        std::wstring *result,
        const std::wstring *MbaeNetworkAccountId)
{
  const wchar_t *v3; // rax
  __int64 v4; // rdx
  HRESULT String; // ebx
  int v6; // eax
  int v7; // eax
  Windows::Networking::NetworkOperators::IMobileBroadbandNetwork_vtbl *v8; // rax
  const wchar_t *StringRawBuffer; // rax
  unsigned __int64 v10; // rax
  const wchar_t *v11; // rcx
  const wchar_t *id; // rax
  __int64 v13; // rdx
  const _GUID *v14; // r8
  Microsoft::WRL::Wrappers::HStringReference v16; // [rsp+40h] [rbp-9h] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > providerId; // [rsp+60h] [rbp+17h] BYREF
  ATL::CComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> currentNetwork; // [rsp+68h] [rbp+1Fh] BYREF
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (__cdecl*)(HSTRING__ *),&WindowsDeleteString,wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t> > > networkAccountId; // [rsp+70h] [rbp+27h] BYREF
  ATL::CComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandAccount> mobileBroadbandAccount; // [rsp+78h] [rbp+2Fh] BYREF
  ATL::CComPtr<Windows::Networking::NetworkOperators::IMobileBroadbandAccountStatics> mobileBroadbandAccountStatic; // [rsp+80h] [rbp+37h] BYREF

  mobileBroadbandAccountStatic.p = 0;
  mobileBroadbandAccount.p = 0;
  networkAccountId.m_ptr = 0;
  v3 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&MbaeNetworkAccountId->_Mypair._Myval2);
  String = WindowsCreateString(v3, *(_DWORD *)(v4 + 16), &networkAccountId.m_ptr);
  if ( String >= 0 )
  {
    v16.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v16,
      RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandAccount,
      0x3Bu,
      0x3Au);
    String = RoGetActivationFactory(
               v16.hstr_,
               &GUID_aa7f4d24_afc1_4fc8_ae9a_a9175310faad,
               &mobileBroadbandAccountStatic);
    if ( String >= 0 )
    {
      v6 = mobileBroadbandAccountStatic.p->CreateFromNetworkAccountId(
             mobileBroadbandAccountStatic.p,
             networkAccountId.m_ptr,
             (Windows::Networking::NetworkOperators::IMobileBroadbandAccount **)&mobileBroadbandAccount);
      String = v6;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xAu, WPP_f06af02949b434cddba45b7b6c1c9557_Traceguids, v6);
      }
    }
  }
  currentNetwork.p = 0;
  if ( String >= 0 )
  {
    v7 = mobileBroadbandAccount.p->get_CurrentNetwork(
           mobileBroadbandAccount.p,
           (Windows::Networking::NetworkOperators::IMobileBroadbandNetwork **)&currentNetwork);
    String = v7;
    if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
      && (WPP_GLOBAL_Control->ReserveSpace[28] & 0x10) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->Control.Logger, 0xBu, WPP_f06af02949b434cddba45b7b6c1c9557_Traceguids, v7);
    }
  }
  std::wstring::wstring(result);
  if ( String >= 0 )
  {
    providerId.m_ptr = 0;
    v8 = currentNetwork.p->__vftable;
    providerId.m_ptr = 0;
    String = v8->get_RegisteredProviderId(currentNetwork.p, &providerId.m_ptr);
    StringRawBuffer = WindowsGetStringRawBuffer(providerId.m_ptr, 0);
    v10 = std::_WChar_traits<unsigned short>::length(StringRawBuffer);
    std::wstring::_Assign<unsigned short>(result, v11, v10);
    Windows::Internal::String::~String(&providerId);
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control->ReserveSpace[28] & 8) != 0 )
  {
    id = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&result->_Mypair._Myval2);
    WPP_SF_dS(*(_QWORD *)(v13 + 16), v13, v14, String, id);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&currentNetwork);
  Windows::Internal::String::~String(&networkAccountId);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&mobileBroadbandAccount);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((ATL::CComPtrBase<Windows::Networking::NetworkOperators::IMobileBroadbandNetwork> *)&mobileBroadbandAccountStatic);
  return result;
}

```

## disassembly

```asm
0x1800678c8  mov     [rsp-8+arg_10], rbx
0x1800678cd  push    rbp
0x1800678ce  push    rdi
0x1800678cf  push    r14
0x1800678d1  lea     rbp, [rsp-47h]
0x1800678d6  sub     rsp, 90h
0x1800678dd  mov     rax, cs:__security_cookie
0x1800678e4  xor     rax, rsp
0x1800678e7  mov     [rbp+57h+var_18], rax
0x1800678eb  mov     rdi, rcx
0x1800678ee  mov     [rbp+57h+var_68], rcx
0x1800678f2  mov     [rbp+57h+var_70], 0
0x1800678f9  mov     [rbp+57h+mobileBroadbandAccountStatic.p], 0
0x180067901  mov     [rbp+57h+mobileBroadbandAccount.p], 0
0x180067909  mov     [rbp+57h+networkAccountId.m_ptr], 0
0x180067911  mov     rcx, MbaeNetworkAccountId; this
0x180067914  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180067919  lea     r8, [rbp+57h+networkAccountId]; string
0x18006791d  mov     edx, [MbaeNetworkAccountId+10h]; length
0x180067920  mov     rcx, rax; sourceString
0x180067923  call    cs:__imp_WindowsCreateString
0x180067929  mov     ebx, eax
0x18006792b  lea     r14, WPP_GLOBAL_Control
0x180067932  test    eax, eax
0x180067934  js      loc_1800679BB
0x18006793a  mov     [rbp+57h+var_60.hstr_], 0
0x180067942  mov     r9d, 3Ah ; ':'; len
0x180067948  lea     r8d, [r9+1]; bufferLen
0x18006794c  lea     MbaeNetworkAccountId, ?RuntimeClass_Windows_Networking_NetworkOperators_MobileBroadbandAccount@@3QBGB; str
0x180067953  lea     rcx, [rbp+57h+var_60]; this
0x180067957  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18006795c  lea     r8, [rbp+57h+mobileBroadbandAccountStatic]
0x180067960  lea     MbaeNetworkAccountId, _GUID_aa7f4d24_afc1_4fc8_ae9a_a9175310faad
0x180067967  mov     rcx, [rbp+57h+var_60.hstr_]
0x18006796b  call    cs:__imp_RoGetActivationFactory
0x180067971  mov     ebx, eax
0x180067973  test    eax, eax
0x180067975  js      short loc_1800679BB
0x180067977  mov     rcx, [rbp+57h+mobileBroadbandAccountStatic.p]
0x18006797b  mov     rax, [rcx]
0x18006797e  lea     r8, [rbp+57h+mobileBroadbandAccount]
0x180067982  mov     MbaeNetworkAccountId, [rbp+57h+networkAccountId.m_ptr]
0x180067986  mov     rax, [rax+38h]
0x18006798a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006798f  mov     ebx, eax
0x180067991  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180067998  cmp     rcx, r14
0x18006799b  jz      short loc_1800679BB
0x18006799d  test    byte ptr [rcx+1Ch], 10h
0x1800679a1  jz      short loc_1800679BB
0x1800679a3  mov     edx, 0Ah; id
0x1800679a8  mov     r9d, eax; _a1
0x1800679ab  lea     r8, WPP_f06af02949b434cddba45b7b6c1c9557_Traceguids; TraceGuid
0x1800679b2  mov     rcx, [rcx+10h]; Logger
0x1800679b6  call    WPP_SF_d
0x1800679bb  mov     [rbp+57h+currentNetwork.p], 0
0x1800679c3  test    ebx, ebx
0x1800679c5  js      short loc_180067A07
0x1800679c7  mov     rcx, [rbp+57h+mobileBroadbandAccount.p]
0x1800679cb  mov     rax, [rcx]
0x1800679ce  lea     MbaeNetworkAccountId, [rbp+57h+currentNetwork]
0x1800679d2  mov     rax, [rax+48h]
0x1800679d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800679db  mov     ebx, eax
0x1800679dd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800679e4  cmp     rcx, r14
0x1800679e7  jz      short loc_180067A07
0x1800679e9  test    byte ptr [rcx+1Ch], 10h
0x1800679ed  jz      short loc_180067A07
0x1800679ef  mov     edx, 0Bh; id
0x1800679f4  mov     r9d, eax; _a1
0x1800679f7  lea     r8, WPP_f06af02949b434cddba45b7b6c1c9557_Traceguids; TraceGuid
0x1800679fe  mov     rcx, [rcx+10h]; Logger
0x180067a02  call    WPP_SF_d
0x180067a07  mov     rcx, rdi; this
0x180067a0a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180067a0f  mov     [rbp+57h+var_70], 1
0x180067a16  test    ebx, ebx
0x180067a18  js      short loc_180067A6C
0x180067a1a  mov     [rbp+57h+providerId.m_ptr], 0
0x180067a22  mov     rcx, [rbp+57h+currentNetwork.p]
0x180067a26  mov     rax, [rcx]
0x180067a29  mov     [rbp+57h+providerId.m_ptr], 0
0x180067a31  lea     MbaeNetworkAccountId, [rbp+57h+providerId]
0x180067a35  mov     rax, [rax+68h]
0x180067a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a3e  mov     ebx, eax
0x180067a40  xor     edx, edx; length
0x180067a42  mov     rcx, [rbp+57h+providerId.m_ptr]; string
0x180067a46  call    cs:__imp_WindowsGetStringRawBuffer
0x180067a4c  mov     rcx, rax; _First
0x180067a4f  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180067a54  mov     r8, rax; _Count
0x180067a57  mov     MbaeNetworkAccountId, rcx; _Ptr
0x180067a5a  mov     rcx, rdi; this
0x180067a5d  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180067a62  nop
0x180067a63  lea     rcx, [rbp+57h+providerId]; this
0x180067a67  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180067a6c  mov     MbaeNetworkAccountId, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180067a73  cmp     MbaeNetworkAccountId, r14
0x180067a76  jz      short loc_180067A98
0x180067a78  test    byte ptr [MbaeNetworkAccountId+1Ch], 8
0x180067a7c  jz      short loc_180067A98
0x180067a7e  mov     rcx, rdi; this
0x180067a81  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180067a86  mov     [rsp+0A0h+id], rax; id
0x180067a8b  mov     r9d, ebx; Logger
0x180067a8e  mov     rcx, [MbaeNetworkAccountId+10h]; Logger
0x180067a92  call    WPP_SF_dS
0x180067a97  nop
0x180067a98  lea     rcx, [rbp+57h+currentNetwork]; this
0x180067a9c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180067aa1  nop
0x180067aa2  lea     rcx, [rbp+57h+networkAccountId]; this
0x180067aa6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x180067aab  nop
0x180067aac  lea     rcx, [rbp+57h+mobileBroadbandAccount]; this
0x180067ab0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180067ab5  nop
0x180067ab6  lea     rcx, [rbp+57h+mobileBroadbandAccountStatic]; this
0x180067aba  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180067abf  mov     rax, rdi
0x180067ac2  mov     rcx, [rbp+57h+var_18]
0x180067ac6  xor     rcx, rsp; StackCookie
0x180067ac9  call    __security_check_cookie
0x180067ace  mov     rbx, [rsp+0A0h+arg_10]
0x180067ad6  add     rsp, 90h
0x180067add  pop     r14
0x180067adf  pop     rdi
0x180067ae0  pop     rbp
0x180067ae1  retn
```
