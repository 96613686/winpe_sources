# OnDeleteHelper

- ea: `0x18003ca4c`
- end: `0x18003cd56`
- name: `OnDeleteHelper`
- size: `778`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ca30`

## callees

- `0x180017f8c`
- `0x18001aec8`
- `0x180020cb4`
- `0x18002e1a0`
- `0x18003a96c`
- `0x18003aabc`
- `0x18003bb30`
- `0x18003c198`
- `0x18003c1d0`
- `0x18003c4c8`
- `0x18003c968`
- `0x18003ca4c`
- `0x1800741a8`
- `0x18007b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003cb4f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003cb4f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003cc46`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18003cc46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003cc2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003cc2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall OnDeleteHelper(__int64 a1)
{
  __int64 (__fastcall *v2)(void ***, __int64, HSTRING *); // rbx
  int v3; // eax
  HSTRING v4; // rdi
  unsigned int (__fastcall *v5)(HSTRING, __int64 *); // rbx
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, __int64); // rbx
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, __int64); // rbx
  __int64 v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // ebx
  unsigned __int16 **i; // rdi
  unsigned __int16 **v16; // r14
  unsigned __int16 *v17; // r15
  int v18; // esi
  CEnrollmentLogger *Logger; // rax
  int v21[2]; // [rsp+20h] [rbp-78h] BYREF
  __int64 v22; // [rsp+28h] [rbp-70h] BYREF
  OLECHAR *v23; // [rsp+30h] [rbp-68h] BYREF
  __int128 v24; // [rsp+38h] [rbp-60h] BYREF
  __int64 v25; // [rsp+48h] [rbp-50h]
  OLECHAR *v26; // [rsp+50h] [rbp-48h] BYREF
  HSTRING string; // [rsp+58h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v24 = 0;
  v25 = 0;
  string = 0;
  v2 = (__int64 (__fastcall *)(void ***, __int64, HSTRING *))off_1800AF740[4];
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&string);
  v3 = v2(&off_1800AF740, 222310497, &string);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\core\\enrolluserprofilenotifyhandler.cpp",
      (const char *)(unsigned int)v3,
      v21[0]);
  v22 = 0;
  while ( 1 )
  {
    v4 = string;
    v5 = *(unsigned int (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)string + 24LL);
    Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v22);
    if ( v5(v4, &v22) )
      break;
    v23 = 0;
    v6 = v22;
    v7 = *(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 112LL);
    v8 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&v23);
    if ( v7(v6, v8) >= 0 && !(unsigned int)_o__wcsicmp(a1, v23) )
    {
      *(_QWORD *)v21 = 0;
      v9 = v22;
      v10 = *(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v22 + 32LL);
      v11 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v21);
      v12 = v10(v9, v11);
      if ( v12 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x43,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\core\\enrolluserprofilenotifyhandler.cpp",
          (const char *)(unsigned int)v12,
          v21[0]);
      if ( *((_QWORD *)&v24 + 1) == v25 )
      {
        std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &v24,
          *((_QWORD *)&v24 + 1),
          v21);
      }
      else
      {
        **((_QWORD **)&v24 + 1) = *(_QWORD *)v21;
        *(_QWORD *)v21 = 0;
        *((_QWORD *)&v24 + 1) += 8LL;
      }
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((OLECHAR **)v21);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
  }
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v22);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&string);
  v26 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.Management.Enrollment.Enroller", 0x2Fu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v13 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(
          (__int64)string,
          &v26);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x4B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\core\\enrolluserprofilenotifyhandler.cpp",
      (const char *)(unsigned int)v13,
      v21[0]);
  v14 = 0;
  v16 = (unsigned __int16 **)*((_QWORD *)&v24 + 1);
  for ( i = (unsigned __int16 **)v24; i != v16; ++i )
  {
    v17 = *i;
    v23 = v26;
    string = (HSTRING)v17;
    hstringHeader.Reserved.Reserved1 = &v23;
    v18 = lambda_e30fe20ef030a3063577525fe416448b_::operator()(&string);
    Logger = CEnrollmentLogger::GetLogger();
    CEnrollmentLogger::LogUserDeleteUnenrollFinished(Logger, v18, v17);
    if ( v18 < 0 )
      v14 = v18;
  }
  if ( v14 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x55,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollengine\\core\\enrolluserprofilenotifyhandler.cpp",
      (const char *)(unsigned int)v14,
      v21[0]);
  Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(&v26);
  if ( (_QWORD)v24 )
  {
    std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
      v24,
      *((_QWORD *)&v24 + 1));
    std::_Deallocate<16>((_QWORD *)v24, (v25 - v24) & 0xFFFFFFFFFFFFFFF8uLL);
  }
  return 0;
}

```

## disassembly

```asm
0x18003ca4c  mov     r11, rsp
0x18003ca4f  mov     [r11+10h], rbx
0x18003ca53  mov     [r11+18h], rsi
0x18003ca57  push    rdi
0x18003ca58  push    r14
0x18003ca5a  push    r15
0x18003ca5c  sub     rsp, 80h
0x18003ca63  mov     rax, cs:__security_cookie
0x18003ca6a  xor     rax, rsp
0x18003ca6d  mov     [rsp+98h+var_20], rax
0x18003ca72  mov     rsi, rcx
0x18003ca75  xorps   xmm0, xmm0
0x18003ca78  movdqu  [rsp+98h+var_60], xmm0
0x18003ca7e  mov     qword ptr [r11-50h], 0
0x18003ca86  mov     qword ptr [r11-40h], 0
0x18003ca8e  mov     rax, cs:off_1800AF740
0x18003ca95  mov     rbx, [rax+20h]
0x18003ca99  lea     rcx, [r11-40h]
0x18003ca9d  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18003caa2  lea     r8, [rsp+98h+string]
0x18003caa7  mov     edx, 0D403061h
0x18003caac  lea     rcx, off_1800AF740
0x18003cab3  mov     rax, rbx
0x18003cab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cabb  mov     rcx, [rsp+98h]; this
0x18003cac3  test    eax, eax
0x18003cac5  jns     short loc_18003CADB
0x18003cac7  mov     r9d, eax; char *
0x18003caca  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cad1  mov     edx, 38h ; '8'; void *
0x18003cad6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003cadb  mov     [rsp+98h+var_70], 0
0x18003cae4  mov     rdi, [rsp+98h+string]
0x18003cae9  mov     rax, [rdi]
0x18003caec  mov     rbx, [rax+18h]
0x18003caf0  lea     rcx, [rsp+98h+var_70]
0x18003caf5  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18003cafa  lea     rdx, [rsp+98h+var_70]
0x18003caff  mov     rcx, rdi
0x18003cb02  mov     rax, rbx
0x18003cb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb0a  test    eax, eax
0x18003cb0c  jnz     loc_18003CBF9
0x18003cb12  mov     [rsp+98h+var_68], 0
0x18003cb1b  mov     rdi, [rsp+98h+var_70]
0x18003cb20  mov     rax, [rdi]
0x18003cb23  mov     rbx, [rax+70h]
0x18003cb27  lea     rcx, [rsp+98h+var_68]
0x18003cb2c  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18003cb31  mov     rdx, rax
0x18003cb34  mov     rcx, rdi
0x18003cb37  mov     rax, rbx
0x18003cb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb3f  test    eax, eax
0x18003cb41  js      loc_18003CBEA
0x18003cb47  mov     rdx, [rsp+98h+var_68]
0x18003cb4c  mov     rcx, rsi
0x18003cb4f  call    cs:__imp__o__wcsicmp
0x18003cb55  test    eax, eax
0x18003cb57  jnz     loc_18003CBEA
0x18003cb5d  mov     qword ptr [rsp+98h+var_78], 0; int
0x18003cb66  mov     rdi, [rsp+98h+var_70]
0x18003cb6b  mov     rax, [rdi]
0x18003cb6e  mov     rbx, [rax+20h]
0x18003cb72  lea     rcx, [rsp+98h+var_78]
0x18003cb77  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAGXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::put(void)
0x18003cb7c  mov     rdx, rax
0x18003cb7f  mov     rcx, rdi
0x18003cb82  mov     rax, rbx
0x18003cb85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb8a  mov     rcx, [rsp+98h]; this
0x18003cb92  test    eax, eax
0x18003cb94  jns     short loc_18003CBAA
0x18003cb96  mov     r9d, eax; char *
0x18003cb99  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cba0  mov     edx, 43h ; 'C'; void *
0x18003cba5  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003cbaa  mov     rdx, qword ptr [rsp+98h+var_60+8]
0x18003cbaf  cmp     rdx, [rsp+98h+var_50]
0x18003cbb4  jz      short loc_18003CBCF
0x18003cbb6  mov     rax, qword ptr [rsp+98h+var_78]
0x18003cbbb  mov     [rdx], rax
0x18003cbbe  mov     qword ptr [rsp+98h+var_78], 0
0x18003cbc7  add     qword ptr [rsp+98h+var_60+8], 8
0x18003cbcd  jmp     short loc_18003CBDF
0x18003cbcf  lea     r8, [rsp+98h+var_78]
0x18003cbd4  lea     rcx, [rsp+98h+var_60]
0x18003cbd9  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18003cbde  nop
0x18003cbdf  lea     rcx, [rsp+98h+var_78]
0x18003cbe4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cbe9  nop
0x18003cbea  lea     rcx, [rsp+98h+var_68]
0x18003cbef  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003cbf4  jmp     loc_18003CAE4
0x18003cbf9  lea     rcx, [rsp+98h+var_70]
0x18003cbfe  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18003cc03  nop
0x18003cc04  lea     rcx, [rsp+98h+string]
0x18003cc09  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18003cc0e  mov     [rsp+98h+var_48], 0
0x18003cc17  lea     r9, [rsp+98h+string]; string
0x18003cc1c  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x18003cc21  mov     edx, 2Fh ; '/'; length
0x18003cc26  lea     rcx, ?RuntimeClass_Windows_Internal_Management_Enrollment_Enroller@@3QBGB; "Windows.Internal.Management.Enrollment."...
0x18003cc2d  call    cs:__imp_WindowsCreateStringReference
0x18003cc33  test    eax, eax
0x18003cc35  jns     short loc_18003CC4C
0x18003cc37  xor     r9d, r9d; lpArguments
0x18003cc3a  xor     r8d, r8d; nNumberOfArguments
0x18003cc3d  lea     edx, [r9+1]; dwExceptionFlags
0x18003cc41  mov     ecx, 0C000000Dh; dwExceptionCode
0x18003cc46  call    cs:__imp_RaiseException
0x18003cc4c  lea     rdx, [rsp+98h+var_48]
0x18003cc51  mov     rcx, [rsp+98h+string]
0x18003cc56  call    ??$ActivateInstance@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIEnrollment@Enrollment@Management@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Management::Enrollment::IEnrollment>>)
0x18003cc5b  mov     rcx, [rsp+98h]; this
0x18003cc63  test    eax, eax
0x18003cc65  jns     short loc_18003CC7B
0x18003cc67  mov     r9d, eax; char *
0x18003cc6a  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cc71  mov     edx, 4Bh ; 'K'; void *
0x18003cc76  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003cc7b  xor     ebx, ebx
0x18003cc7d  mov     rdi, qword ptr [rsp+98h+var_60]
0x18003cc82  mov     r14, qword ptr [rsp+98h+var_60+8]
0x18003cc87  cmp     rdi, r14
0x18003cc8a  jz      short loc_18003CCD1
0x18003cc8c  mov     r15, [rdi]
0x18003cc8f  mov     rax, [rsp+98h+var_48]
0x18003cc94  mov     [rsp+98h+var_68], rax
0x18003cc99  mov     [rsp+98h+string], r15
0x18003cc9e  lea     rax, [rsp+98h+var_68]
0x18003cca3  mov     qword ptr [rsp+98h+hstringHeader.Reserved], rax
0x18003cca8  lea     rcx, [rsp+98h+string]
0x18003ccad  call    _lambda_e30fe20ef030a3063577525fe416448b___operator__
0x18003ccb2  mov     esi, eax
0x18003ccb4  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18003ccb9  mov     r8, r15; unsigned __int16 *
0x18003ccbc  mov     edx, esi; int
0x18003ccbe  mov     rcx, rax; this
0x18003ccc1  call    ?LogUserDeleteUnenrollFinished@CEnrollmentLogger@@QEAAXJPEBG@Z; CEnrollmentLogger::LogUserDeleteUnenrollFinished(long,ushort const *)
0x18003ccc6  test    esi, esi
0x18003ccc8  cmovs   ebx, esi
0x18003cccb  add     rdi, 8
0x18003cccf  jmp     short loc_18003CC87
0x18003ccd1  mov     rcx, [rsp+98h]; this
0x18003ccd9  test    ebx, ebx
0x18003ccdb  jns     short loc_18003CCF2
0x18003ccdd  mov     r9d, ebx; char *
0x18003cce0  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x18003cce7  mov     edx, 55h ; 'U'; void *
0x18003ccec  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18003ccf2  lea     rcx, [rsp+98h+var_48]
0x18003ccf7  call    ?InternalRelease@?$ComPtr@UIX509CertificateRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IX509CertificateRequest>::InternalRelease(void)
0x18003ccfc  nop
0x18003ccfd  mov     rcx, qword ptr [rsp+98h+var_60]
0x18003cd02  test    rcx, rcx
0x18003cd05  jz      short loc_18003CD27
0x18003cd07  mov     rdx, qword ptr [rsp+98h+var_60+8]
0x18003cd0c  call    ??$_Destroy_range@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@YAXPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV12@AEAV?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@0@@Z; std::_Destroy_range<std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> &)
0x18003cd11  mov     rcx, qword ptr [rsp+98h+var_60]
0x18003cd16  mov     rdx, [rsp+98h+var_50]
0x18003cd1b  sub     rdx, rcx
0x18003cd1e  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18003cd22  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003cd27  xor     eax, eax
0x18003cd29  jmp     short loc_18003CD2F
0x18003cd2b  mov     eax, [rsp+98h+var_78]
0x18003cd2f  mov     rcx, [rsp+98h+var_20]
0x18003cd34  xor     rcx, rsp; StackCookie
0x18003cd37  call    __security_check_cookie
0x18003cd3c  lea     r11, [rsp+98h+var_18]
0x18003cd44  mov     rbx, [r11+28h]
0x18003cd48  mov     rsi, [r11+30h]
0x18003cd4c  mov     rsp, r11
0x18003cd4f  pop     r15
0x18003cd51  pop     r14
0x18003cd53  pop     rdi
0x18003cd54  retn
```
