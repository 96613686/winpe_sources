# CWapNodeValidator::ValidateNode(EnrollmentEnrollType,ATL::CComPtr<IDomNode>,int *)

- ea: `0x18002d810`
- end: `0x18002df37`
- name: `?ValidateNode@CWapNodeValidator@@QEAAJW4EnrollmentEnrollType@@V?$CComPtr@UIDomNode@@@ATL@@PEAH@Z`
- size: `1831`
- prototype: `__int64 __fastcall(CWapNodeValidator *this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180029240`

## callees

- `0x180001bd0`
- `0x1800107a0`
- `0x1800110bc`
- `0x1800116f4`
- `0x1800118a0`
- `0x1800118e4`
- `0x180011d9c`
- `0x18001396c`
- `0x180013ba4`
- `0x180014330`
- `0x18001d87c`
- `0x180022874`
- `0x180024028`
- `0x18002c110`
- `0x18002c1cc`
- `0x18002c760`
- `0x18002c7cc`
- `0x18002ca78`
- `0x18002d810`
- `0x180030010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dbbd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dbe9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dc15`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dc77`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dca3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dbbd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dbe9`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dc15`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dc77`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002dca3`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 __fastcall CWapNodeValidator::ValidateNode(CWapNodeValidator *this, unsigned int a2, _QWORD *a3, int *a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  int DdfFolder; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rax
  unsigned __int16 **v18; // rcx
  __int64 v19; // rcx
  int CspName; // eax
  unsigned int v21; // ebx
  unsigned __int16 **v22; // rcx
  unsigned __int16 **v23; // rcx
  unsigned __int16 **v24; // rcx
  unsigned __int16 **v25; // rcx
  unsigned __int16 **v26; // rcx
  const unsigned __int16 *v27; // rdx
  int DdfForCsp; // eax
  unsigned int v29; // ebx
  const unsigned __int16 *v30; // rdx
  int IsNodeSupported; // eax
  unsigned int v32; // ebx
  __int64 v33; // rcx
  int IsPolicyNodeSupported; // eax
  int v35; // r8d
  int v36; // r9d
  unsigned int v37; // ebx
  int v38; // [rsp+20h] [rbp-F8h]
  int v39; // [rsp+20h] [rbp-F8h]
  __int64 v40; // [rsp+30h] [rbp-E8h] BYREF
  CDdfInfo *v41; // [rsp+38h] [rbp-E0h] BYREF
  int v42; // [rsp+40h] [rbp-D8h] BYREF
  _QWORD *v43; // [rsp+48h] [rbp-D0h]
  unsigned __int16 *v44[3]; // [rsp+60h] [rbp-B8h] BYREF
  unsigned __int64 v45; // [rsp+78h] [rbp-A0h]
  unsigned __int16 *v46[2]; // [rsp+80h] [rbp-98h] BYREF
  __int64 v47; // [rsp+90h] [rbp-88h]
  unsigned __int64 v48; // [rsp+98h] [rbp-80h]
  __int128 v49; // [rsp+A0h] [rbp-78h] BYREF
  _OWORD v50[2]; // [rsp+B0h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v43 = a3;
  v40 = 0;
  std::wstring::wstring(v46);
  std::wstring::wstring(v44);
  v49 = *(_OWORD *)L"/wap-provisioningdoc";
  v50[0] = *(_OWORD *)L"visioningdoc";
  *(_OWORD *)((char *)v50 + 10) = *(_OWORD *)L"ningdoc";
  v41 = 0;
  v8 = CWapNodeValidator::InitializeNodeRemovalStat(this);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
      (const char *)(unsigned int)v8,
      v38);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v46);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
    return v9;
  }
  if ( !*a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
      (const char *)0x80070057LL,
      v38);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v46);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC1,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
      (const char *)0x80070057LL,
      v38);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v46);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
    return 2147942487LL;
  }
  *a4 = 0;
  DdfFolder = CWapNodeValidator::GetDdfFolder(this);
  v12 = DdfFolder;
  if ( DdfFolder < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
      (const char *)(unsigned int)DdfFolder,
      v38);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v46);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
    return v12;
  }
  v13 = *a3;
  v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*a3 + 80LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v40,
    0);
  v15 = v14(v13, &v40);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC6,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
      (const char *)(unsigned int)v15,
      v38);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v46);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
    return v16;
  }
  std::wstring::assign(v46);
  v17 = -1;
  do
    ++v17;
  while ( *((_WORD *)&v50[-1] + v17) );
  v18 = v46;
  if ( v48 > 7 )
    LODWORD(v18) = v46[0];
  if ( !std::_Traits_find<std::char_traits<unsigned short>>((_DWORD)v18, v47, 0, (unsigned int)&v49, v17) )
    std::wstring::erase(v46);
  if ( !v47 )
    goto LABEL_48;
  CspName = CWapNodeValidator::GetCspName(v19, v46, v44);
  v21 = CspName;
  if ( CspName < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
      (const char *)(unsigned int)CspName,
      v39);
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v46);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
    return v21;
  }
  v22 = v44;
  if ( v45 > 7 )
    v22 = (unsigned __int16 **)v44[0];
  if ( !(unsigned int)_o__wcsicmp(v22, L"Application") )
    goto LABEL_48;
  v23 = v44;
  if ( v45 > 7 )
    v23 = (unsigned __int16 **)v44[0];
  if ( !(unsigned int)_o__wcsicmp(v23, L"EnterpriseAppManagement") )
    goto LABEL_48;
  v24 = v44;
  if ( v45 > 7 )
    v24 = (unsigned __int16 **)v44[0];
  if ( (unsigned int)_o__wcsicmp(v24, L"CertificateStore") )
  {
    v25 = v44;
    if ( v45 > 7 )
      v25 = (unsigned __int16 **)v44[0];
    if ( !(unsigned int)_o__wcsicmp(v25, L"Policy") )
      goto LABEL_44;
    v26 = v44;
    if ( v45 > 7 )
      v26 = (unsigned __int16 **)v44[0];
    if ( (unsigned int)_o__wcsicmp(v26, L"PolicyManager") )
    {
      v27 = (const unsigned __int16 *)v44;
      if ( v45 > 7 )
        v27 = v44[0];
      DdfForCsp = CWapNodeValidator::GetDdfForCsp(this, v27, &v41);
      v29 = DdfForCsp;
      if ( DdfForCsp >= 0 )
      {
        v30 = (const unsigned __int16 *)v46;
        if ( v48 > 7 )
          v30 = v46[0];
        IsNodeSupported = CDdfInfo::IsNodeSupported(v41, v30, a4);
        v32 = IsNodeSupported;
        if ( IsNodeSupported >= 0 )
        {
          std::wstring::_Tidy_deallocate(v44);
          std::wstring::_Tidy_deallocate(v46);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
          wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x111,
            (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
            (const char *)(unsigned int)IsNodeSupported,
            v39);
          std::wstring::_Tidy_deallocate(v44);
          std::wstring::_Tidy_deallocate(v46);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
          wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
          return v32;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x107,
          (unsigned int)"onecoreuap\\admin\\dm\\coredpus\\wapdpu\\ddfinfo.cpp",
          (const char *)(unsigned int)DdfForCsp,
          v39);
        std::wstring::_Tidy_deallocate(v44);
        std::wstring::_Tidy_deallocate(v46);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
        wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
        return v29;
      }
    }
    else
    {
LABEL_44:
      ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(&v41, *a3);
      IsPolicyNodeSupported = CWapNodeValidator::IsPolicyNodeSupported(v33, a2, &v41, a4);
      v37 = IsPolicyNodeSupported;
      if ( IsPolicyNodeSupported < 0 && (unsigned int)dword_18003E080 > 5 )
      {
        v42 = IsPolicyNodeSupported;
        v41 = (CDdfInfo *)"IsPolicyNodeSupported failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          dword_18003E080,
          (unsigned int)byte_180037E8B,
          v35,
          v36,
          (__int64)&v41,
          (__int64)&v42);
      }
      std::wstring::_Tidy_deallocate(v44);
      std::wstring::_Tidy_deallocate(v46);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
      wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
      return v37;
    }
  }
  else
  {
LABEL_48:
    *a4 = 1;
    std::wstring::_Tidy_deallocate(v44);
    std::wstring::_Tidy_deallocate(v46);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
    wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(a3);
    return 0;
  }
}

```

## disassembly

```asm
0x18002d810  push    rbx
0x18002d812  push    rsi
0x18002d813  push    rdi
0x18002d814  push    r12
0x18002d816  push    r13
0x18002d818  push    r14
0x18002d81a  push    r15
0x18002d81c  sub     rsp, 0E0h
0x18002d823  mov     rax, cs:__security_cookie
0x18002d82a  xor     rax, rsp
0x18002d82d  mov     [rsp+118h+var_48], rax
0x18002d835  mov     r14, r9
0x18002d838  mov     rsi, r8
0x18002d83b  mov     r12d, edx
0x18002d83e  mov     r15, rcx
0x18002d841  mov     [rsp+118h+var_D0], r8
0x18002d846  xor     r13d, r13d
0x18002d849  mov     [rsp+118h+var_E8], r13
0x18002d84e  lea     rcx, [rsp+118h+var_98]
0x18002d856  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d85b  nop
0x18002d85c  lea     rcx, [rsp+118h+var_B8]
0x18002d861  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002d866  nop
0x18002d867  movups  xmm1, xmmword ptr cs:aWapProvisionin; "/wap-provisioningdoc"
0x18002d86e  movups  [rsp+118h+var_78], xmm1
0x18002d876  movups  xmm0, xmmword ptr cs:aWapProvisionin+10h; "visioningdoc"
0x18002d87d  movups  xmmword ptr [rsp+118h+var_68], xmm0
0x18002d885  movups  xmm1, xmmword ptr cs:aWapProvisionin+1Ah; "ningdoc"
0x18002d88c  movups  xmmword ptr [rsp+118h+var_68+0Ah], xmm1
0x18002d894  mov     [rsp+118h+var_E0], r13
0x18002d899  mov     rcx, r15; this
0x18002d89c  call    ?InitializeNodeRemovalStat@CWapNodeValidator@@AEAAJXZ; CWapNodeValidator::InitializeNodeRemovalStat(void)
0x18002d8a1  mov     ebx, eax
0x18002d8a3  test    eax, eax
0x18002d8a5  jns     short loc_18002D8F7
0x18002d8a7  mov     rcx, [rsp+118h]; this
0x18002d8af  mov     r9d, eax; char *
0x18002d8b2  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002d8b9  mov     edx, 0BEh; void *
0x18002d8be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d8c3  nop
0x18002d8c4  lea     rcx, [rsp+118h+var_B8]; void *
0x18002d8c9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d8ce  nop
0x18002d8cf  lea     rcx, [rsp+118h+var_98]; void *
0x18002d8d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d8dc  nop
0x18002d8dd  lea     rcx, [rsp+118h+var_E8]
0x18002d8e2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d8e7  nop
0x18002d8e8  mov     rcx, rsi
0x18002d8eb  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d8f0  mov     eax, ebx
0x18002d8f2  jmp     loc_18002DF13
0x18002d8f7  cmp     [rsi], r13
0x18002d8fa  jnz     short loc_18002D951
0x18002d8fc  mov     rcx, [rsp+118h]; this
0x18002d904  mov     ebx, 80070057h
0x18002d909  mov     r9d, ebx; char *
0x18002d90c  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002d913  mov     edx, 0C0h; void *
0x18002d918  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d91d  nop
0x18002d91e  lea     rcx, [rsp+118h+var_B8]; void *
0x18002d923  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d928  nop
0x18002d929  lea     rcx, [rsp+118h+var_98]; void *
0x18002d931  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d936  nop
0x18002d937  lea     rcx, [rsp+118h+var_E8]
0x18002d93c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d941  nop
0x18002d942  mov     rcx, rsi
0x18002d945  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d94a  mov     eax, ebx
0x18002d94c  jmp     loc_18002DF13
0x18002d951  test    r14, r14
0x18002d954  jnz     short loc_18002D9AB
0x18002d956  mov     rcx, [rsp+118h]; this
0x18002d95e  mov     ebx, 80070057h
0x18002d963  mov     r9d, ebx; char *
0x18002d966  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002d96d  mov     edx, 0C1h; void *
0x18002d972  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d977  nop
0x18002d978  lea     rcx, [rsp+118h+var_B8]; void *
0x18002d97d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d982  nop
0x18002d983  lea     rcx, [rsp+118h+var_98]; void *
0x18002d98b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d990  nop
0x18002d991  lea     rcx, [rsp+118h+var_E8]
0x18002d996  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d99b  nop
0x18002d99c  mov     rcx, rsi
0x18002d99f  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002d9a4  mov     eax, ebx
0x18002d9a6  jmp     loc_18002DF13
0x18002d9ab  mov     [r14], r13d
0x18002d9ae  mov     rcx, r15; this
0x18002d9b1  call    ?GetDdfFolder@CWapNodeValidator@@AEAAJXZ; CWapNodeValidator::GetDdfFolder(void)
0x18002d9b6  mov     ebx, eax
0x18002d9b8  test    eax, eax
0x18002d9ba  jns     short loc_18002DA0C
0x18002d9bc  mov     rcx, [rsp+118h]; this
0x18002d9c4  mov     r9d, eax; char *
0x18002d9c7  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002d9ce  mov     edx, 0C5h; void *
0x18002d9d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d9d8  nop
0x18002d9d9  lea     rcx, [rsp+118h+var_B8]; void *
0x18002d9de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d9e3  nop
0x18002d9e4  lea     rcx, [rsp+118h+var_98]; void *
0x18002d9ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002d9f1  nop
0x18002d9f2  lea     rcx, [rsp+118h+var_E8]
0x18002d9f7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d9fc  nop
0x18002d9fd  mov     rcx, rsi
0x18002da00  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002da05  mov     eax, ebx
0x18002da07  jmp     loc_18002DF13
0x18002da0c  mov     rdi, [rsi]
0x18002da0f  mov     rax, [rdi]
0x18002da12  mov     rbx, [rax+50h]
0x18002da16  xor     edx, edx
0x18002da18  lea     rcx, [rsp+118h+var_E8]
0x18002da1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002da22  lea     rdx, [rsp+118h+var_E8]
0x18002da27  mov     rcx, rdi
0x18002da2a  mov     rax, rbx
0x18002da2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da32  mov     ebx, eax
0x18002da34  test    eax, eax
0x18002da36  jns     short loc_18002DA88
0x18002da38  mov     rcx, [rsp+118h]; this
0x18002da40  mov     r9d, eax; char *
0x18002da43  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002da4a  mov     edx, 0C6h; void *
0x18002da4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002da54  nop
0x18002da55  lea     rcx, [rsp+118h+var_B8]; void *
0x18002da5a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002da5f  nop
0x18002da60  lea     rcx, [rsp+118h+var_98]; void *
0x18002da68  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002da6d  nop
0x18002da6e  lea     rcx, [rsp+118h+var_E8]
0x18002da73  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002da78  nop
0x18002da79  mov     rcx, rsi
0x18002da7c  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002da81  mov     eax, ebx
0x18002da83  jmp     loc_18002DF13
0x18002da88  mov     rdx, [rsp+118h+var_E8]
0x18002da8d  lea     rcx, [rsp+118h+var_98]
0x18002da95  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18002da9a  lea     rcx, [rsp+118h+var_78]
0x18002daa2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002daa6  inc     rax
0x18002daa9  cmp     [rcx+rax*2], r13w
0x18002daae  jnz     short loc_18002DAA6
0x18002dab0  lea     rcx, [rsp+118h+var_98]
0x18002dab8  cmp     [rsp+118h+var_80], 7
0x18002dac1  cmova   rcx, [rsp+118h+var_98]
0x18002daca  mov     qword ptr [rsp+118h+var_F8], rax; int
0x18002dacf  lea     r9, [rsp+118h+var_78]
0x18002dad7  xor     r8d, r8d
0x18002dada  mov     rdx, [rsp+118h+var_88]
0x18002dae2  call    ??$_Traits_find@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x18002dae7  test    rax, rax
0x18002daea  jnz     short loc_18002DAF9
0x18002daec  lea     rcx, [rsp+118h+var_98]; void *
0x18002daf4  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18002daf9  cmp     [rsp+118h+var_88], r13
0x18002db01  jnz     short loc_18002DB3D
0x18002db03  mov     dword ptr [r14], 1
0x18002db0a  lea     rcx, [rsp+118h+var_B8]; void *
0x18002db0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002db14  nop
0x18002db15  lea     rcx, [rsp+118h+var_98]; void *
0x18002db1d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002db22  nop
0x18002db23  lea     rcx, [rsp+118h+var_E8]
0x18002db28  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002db2d  nop
0x18002db2e  mov     rcx, rsi
0x18002db31  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002db36  xor     eax, eax
0x18002db38  jmp     loc_18002DF13
0x18002db3d  lea     r8, [rsp+118h+var_B8]
0x18002db42  lea     rdx, [rsp+118h+var_98]
0x18002db4a  call    ?GetCspName@CWapNodeValidator@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z; CWapNodeValidator::GetCspName(std::wstring const &,std::wstring &)
0x18002db4f  mov     ebx, eax
0x18002db51  test    eax, eax
0x18002db53  jns     short loc_18002DBA5
0x18002db55  mov     rcx, [rsp+118h]; this
0x18002db5d  mov     r9d, eax; char *
0x18002db60  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002db67  mov     edx, 0D7h; void *
0x18002db6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002db71  nop
0x18002db72  lea     rcx, [rsp+118h+var_B8]; void *
0x18002db77  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002db7c  nop
0x18002db7d  lea     rcx, [rsp+118h+var_98]; void *
0x18002db85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002db8a  nop
0x18002db8b  lea     rcx, [rsp+118h+var_E8]
0x18002db90  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002db95  nop
0x18002db96  mov     rcx, rsi
0x18002db99  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002db9e  mov     eax, ebx
0x18002dba0  jmp     loc_18002DF13
0x18002dba5  lea     rcx, [rsp+118h+var_B8]
0x18002dbaa  cmp     [rsp+118h+var_A0], 7
0x18002dbb0  cmova   rcx, [rsp+118h+var_B8]
0x18002dbb6  lea     rdx, aApplication_0; "Application"
0x18002dbbd  call    cs:__imp__o__wcsicmp
0x18002dbc4  nop     dword ptr [rax+rax+00h]
0x18002dbc9  test    eax, eax
0x18002dbcb  jz      loc_18002DE6D
0x18002dbd1  lea     rcx, [rsp+118h+var_B8]
0x18002dbd6  cmp     [rsp+118h+var_A0], 7
0x18002dbdc  cmova   rcx, [rsp+118h+var_B8]
0x18002dbe2  lea     rdx, aEnterpriseappm; "EnterpriseAppManagement"
0x18002dbe9  call    cs:__imp__o__wcsicmp
0x18002dbf0  nop     dword ptr [rax+rax+00h]
0x18002dbf5  test    eax, eax
0x18002dbf7  jz      loc_18002DE6D
0x18002dbfd  lea     rcx, [rsp+118h+var_B8]
0x18002dc02  cmp     [rsp+118h+var_A0], 7
0x18002dc08  cmova   rcx, [rsp+118h+var_B8]
0x18002dc0e  lea     rdx, aCertificatesto; "CertificateStore"
0x18002dc15  call    cs:__imp__o__wcsicmp
0x18002dc1c  nop     dword ptr [rax+rax+00h]
0x18002dc21  test    eax, eax
0x18002dc23  jnz     short loc_18002DC5F
0x18002dc25  mov     dword ptr [r14], 1
0x18002dc2c  lea     rcx, [rsp+118h+var_B8]; void *
0x18002dc31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dc36  nop
0x18002dc37  lea     rcx, [rsp+118h+var_98]; void *
0x18002dc3f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dc44  nop
0x18002dc45  lea     rcx, [rsp+118h+var_E8]
0x18002dc4a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dc4f  nop
0x18002dc50  mov     rcx, rsi
0x18002dc53  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002dc58  xor     eax, eax
0x18002dc5a  jmp     loc_18002DF13
0x18002dc5f  lea     rcx, [rsp+118h+var_B8]
0x18002dc64  cmp     [rsp+118h+var_A0], 7
0x18002dc6a  cmova   rcx, [rsp+118h+var_B8]
0x18002dc70  lea     rdx, aPolicy; "Policy"
0x18002dc77  call    cs:__imp__o__wcsicmp
0x18002dc7e  nop     dword ptr [rax+rax+00h]
0x18002dc83  test    eax, eax
0x18002dc85  jz      loc_18002DDDB
0x18002dc8b  lea     rcx, [rsp+118h+var_B8]
0x18002dc90  cmp     [rsp+118h+var_A0], 7
0x18002dc96  cmova   rcx, [rsp+118h+var_B8]
0x18002dc9c  lea     rdx, aPolicymanager; "PolicyManager"
0x18002dca3  call    cs:__imp__o__wcsicmp
0x18002dcaa  nop     dword ptr [rax+rax+00h]
0x18002dcaf  test    eax, eax
0x18002dcb1  jz      loc_18002DDDB
0x18002dcb7  lea     rdx, [rsp+118h+var_B8]
0x18002dcbc  cmp     [rsp+118h+var_A0], 7
0x18002dcc2  cmova   rdx, [rsp+118h+var_B8]; unsigned __int16 *
0x18002dcc8  lea     r8, [rsp+118h+var_E0]; struct CDdfInfo **
0x18002dccd  mov     rcx, r15; this
0x18002dcd0  call    ?GetDdfForCsp@CWapNodeValidator@@AEAAJPEBGAEAPEAVCDdfInfo@@@Z; CWapNodeValidator::GetDdfForCsp(ushort const *,CDdfInfo * &)
0x18002dcd5  mov     ebx, eax
0x18002dcd7  test    eax, eax
0x18002dcd9  jns     short loc_18002DD2B
0x18002dcdb  mov     rcx, [rsp+118h]; this
0x18002dce3  mov     r9d, eax; char *
0x18002dce6  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\coredpus\\wapdpu"...
0x18002dced  mov     edx, 107h; void *
0x18002dcf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002dcf7  nop
0x18002dcf8  lea     rcx, [rsp+118h+var_B8]; void *
0x18002dcfd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd02  nop
0x18002dd03  lea     rcx, [rsp+118h+var_98]; void *
0x18002dd0b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002dd10  nop
0x18002dd11  lea     rcx, [rsp+118h+var_E8]
0x18002dd16  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002dd1b  nop
0x18002dd1c  mov     rcx, rsi
0x18002dd1f  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x18002dd24  mov     eax, ebx
0x18002dd26  jmp     loc_18002DF13
0x18002dd2b  lea     rdx, [rsp+118h+var_98]
  ... truncated ...
```
