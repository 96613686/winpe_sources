# SetUpLimitedCertRequest(HKEY__ *,ushort *,ulong,IX509CertificateRequestPkcs7 * *)

- ea: `0x180057994`
- end: `0x180057ca1`
- name: `?SetUpLimitedCertRequest@@YAJPEAUHKEY__@@PEAGKPEAPEAUIX509CertificateRequestPkcs7@@@Z`
- size: `781`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned int, struct IX509CertificateRequestPkcs7 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180057118`

## callees

- `0x18000e508`
- `0x180011938`
- `0x180020cb4`
- `0x18002e1a0`
- `0x180054e98`
- `0x180056764`
- `0x180057994`
- `0x180058b20`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800579fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057aa8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057b35`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800579fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057aa8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180057b35`
- `OLEAUT32!__imp_SysAllocString` at `0x180057a51`
- `OLEAUT32!__imp_SysAllocString` at `0x180057a51`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall SetUpLimitedCertRequest(
        HKEY a1,
        unsigned __int16 *a2,
        char a3,
        struct IX509CertificateRequestPkcs7 **a4)
{
  HRESULT CryptoProvider; // eax
  unsigned int v9; // r9d
  unsigned int v10; // ebx
  __int64 v11; // rdx
  OLECHAR *v12; // rbx
  HRESULT v13; // edi
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  struct IX509CertificateRequestPkcs7 *v17; // rax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  LPVOID v21; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID v22; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR *v23; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v24; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR psz[256]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v24 = 0;
  wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>::reset(&v24);
  CryptoProvider = CoCreateInstance(
                     &GUID_884e2044_217d_11da_b2a4_000e7bbb2b09,
                     0,
                     1u,
                     &GUID_728ab344_217d_11da_b2a4_000e7bbb2b09,
                     &v24);
  v10 = CryptoProvider;
  if ( CryptoProvider < 0 )
  {
    v11 = 2281;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)CryptoProvider,
      ppv);
    goto LABEL_23;
  }
  psz[0] = 0;
  CryptoProvider = GetCryptoProvider(a1, 1, psz, v9);
  v10 = CryptoProvider;
  if ( CryptoProvider < 0 )
  {
    v11 = 2285;
    goto LABEL_5;
  }
  v12 = SysAllocString(psz);
  v23 = v12;
  if ( !v12 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
    v10 = -2147024882;
    goto LABEL_23;
  }
  v21 = 0;
  v22 = 0;
  v13 = CoCreateInstance(
          &GUID_884e2007_217d_11da_b2a4_000e7bbb2b09,
          0,
          1u,
          &GUID_728ab307_217d_11da_b2a4_000e7bbb2b09,
          &v22);
  if ( v13 < 0 )
  {
    v14 = 2299;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
      (const char *)(unsigned int)v13,
      ppva);
    wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>((__int64 *)&v21);
    wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>((__int64 *)&v22);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
    v10 = v13;
    goto LABEL_23;
  }
  v21 = 0;
  v13 = CoCreateInstance(
          &GUID_884e2008_217d_11da_b2a4_000e7bbb2b09,
          0,
          1u,
          &GUID_728ab308_217d_11da_b2a4_000e7bbb2b09,
          &v21);
  if ( v13 < 0 )
  {
    v14 = 2306;
    goto LABEL_10;
  }
  v15 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)v22 + 56LL))(v22, v12);
  v10 = v15;
  if ( v15 >= 0 )
  {
    v15 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v21 + 80LL))(v21, v22);
    v10 = v15;
    if ( v15 >= 0 )
    {
      v15 = (*(__int64 (__fastcall **)(LPVOID, LPVOID))(*(_QWORD *)v24 + 208LL))(v24, v21);
      v10 = v15;
      if ( v15 >= 0 )
      {
        ppva = 12;
        v15 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, unsigned __int16 *))(*(_QWORD *)v24 + 264LL))(
                v24,
                (unsigned int)((a3 & 4) != 0) + 1,
                1,
                a2);
        v10 = v15;
        if ( v15 >= 0 )
        {
          v17 = (struct IX509CertificateRequestPkcs7 *)v24;
          v24 = 0;
          *a4 = v17;
          wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>((__int64 *)&v21);
          wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>((__int64 *)&v22);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
          v10 = 0;
          goto LABEL_23;
        }
        v16 = 2316;
      }
      else
      {
        v16 = 2310;
      }
    }
    else
    {
      v16 = 2309;
    }
  }
  else
  {
    v16 = 2308;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\lib\\certrequest.cpp",
    (const char *)(unsigned int)v15,
    ppva);
  wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>((__int64 *)&v21);
  wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>((__int64 *)&v22);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v23);
LABEL_23:
  wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>((__int64 *)&v24);
  return v10;
}

```

## disassembly

```asm
0x180057994  mov     [rsp-8+arg_10], rbx
0x180057999  push    rbp
0x18005799a  push    rsi
0x18005799b  push    rdi
0x18005799c  push    r14
0x18005799e  push    r15
0x1800579a0  lea     rbp, [rsp-170h]
0x1800579a8  sub     rsp, 270h
0x1800579af  mov     rax, cs:__security_cookie
0x1800579b6  xor     rax, rsp
0x1800579b9  mov     [rbp+190h+var_30], rax
0x1800579c0  mov     r14, r9
0x1800579c3  mov     esi, r8d
0x1800579c6  mov     r15, rdx
0x1800579c9  mov     rdi, rcx
0x1800579cc  mov     [rsp+290h+var_238], 0
0x1800579d5  lea     rcx, [rsp+290h+var_238]
0x1800579da  call    ?reset@?$com_ptr_t@UIX509CertificateRequestPkcs7@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IX509CertificateRequestPkcs7,wil::err_exception_policy>::reset(void)
0x1800579df  lea     rax, [rsp+290h+var_238]
0x1800579e4  mov     [rsp+290h+ppv], rax; int
0x1800579e9  lea     r9, _GUID_728ab344_217d_11da_b2a4_000e7bbb2b09; riid
0x1800579f0  xor     edx, edx; pUnkOuter
0x1800579f2  lea     r8d, [rdx+1]; dwClsContext
0x1800579f6  lea     rcx, _GUID_884e2044_217d_11da_b2a4_000e7bbb2b09; rclsid
0x1800579fd  call    cs:__imp_CoCreateInstance
0x180057a03  mov     ebx, eax
0x180057a05  test    eax, eax
0x180057a07  jns     short loc_180057A10
0x180057a09  mov     edx, 8E9h
0x180057a0e  jmp     short loc_180057A31
0x180057a10  xor     eax, eax
0x180057a12  mov     [rsp+290h+psz], ax
0x180057a17  lea     r8, [rsp+290h+psz]; unsigned __int16 *
0x180057a1c  mov     dl, 1; bool
0x180057a1e  mov     rcx, rdi; HKEY
0x180057a21  call    ?GetCryptoProvider@@YAJPEAUHKEY__@@_NPEAGK@Z; GetCryptoProvider(HKEY__ *,bool,ushort *,ulong)
0x180057a26  mov     ebx, eax
0x180057a28  test    eax, eax
0x180057a2a  jns     short loc_180057A4C
0x180057a2c  mov     edx, 8EDh; void *
0x180057a31  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180057a38  mov     r9d, eax; char *
0x180057a3b  mov     rcx, [rbp+198h]; this
0x180057a42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057a47  jmp     loc_180057C6F
0x180057a4c  lea     rcx, [rsp+290h+psz]; psz
0x180057a51  call    cs:__imp_SysAllocString
0x180057a57  mov     rbx, rax
0x180057a5a  mov     [rsp+290h+var_240], rax
0x180057a5f  test    rax, rax
0x180057a62  jnz     short loc_180057A78
0x180057a64  lea     rcx, [rsp+290h+var_240]
0x180057a69  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180057a6e  mov     ebx, 8007000Eh
0x180057a73  jmp     loc_180057C6F
0x180057a78  mov     [rsp+290h+var_250], 0
0x180057a81  mov     [rsp+290h+var_248], 0
0x180057a8a  lea     rax, [rsp+290h+var_248]
0x180057a8f  mov     [rsp+290h+ppv], rax; int
0x180057a94  lea     r9, _GUID_728ab307_217d_11da_b2a4_000e7bbb2b09; riid
0x180057a9b  xor     edx, edx; pUnkOuter
0x180057a9d  lea     r8d, [rdx+1]; dwClsContext
0x180057aa1  lea     rcx, _GUID_884e2007_217d_11da_b2a4_000e7bbb2b09; rclsid
0x180057aa8  call    cs:__imp_CoCreateInstance
0x180057aae  mov     edi, eax
0x180057ab0  test    eax, eax
0x180057ab2  jns     short loc_180057AF7
0x180057ab4  mov     edx, 8FBh; void *
0x180057ab9  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180057ac0  mov     r9d, edi; char *
0x180057ac3  mov     rcx, [rbp+198h]; this
0x180057aca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057acf  nop
0x180057ad0  lea     rcx, [rsp+290h+var_250]
0x180057ad5  call    ??1?$com_ptr_t@UICspInformations@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>(void)
0x180057ada  nop
0x180057adb  lea     rcx, [rsp+290h+var_248]
0x180057ae0  call    ??1?$com_ptr_t@UICspInformations@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>(void)
0x180057ae5  nop
0x180057ae6  lea     rcx, [rsp+290h+var_240]
0x180057aeb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180057af0  mov     ebx, edi
0x180057af2  jmp     loc_180057C6F
0x180057af7  mov     rcx, [rsp+290h+var_250]
0x180057afc  mov     [rsp+290h+var_250], 0
0x180057b05  test    rcx, rcx
0x180057b08  jz      short loc_180057B17
0x180057b0a  mov     rax, [rcx]
0x180057b0d  mov     rax, [rax+10h]
0x180057b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b16  nop
0x180057b17  lea     rax, [rsp+290h+var_250]
0x180057b1c  mov     [rsp+290h+ppv], rax; int
0x180057b21  lea     r9, _GUID_728ab308_217d_11da_b2a4_000e7bbb2b09; riid
0x180057b28  xor     edx, edx; pUnkOuter
0x180057b2a  lea     r8d, [rdx+1]; dwClsContext
0x180057b2e  lea     rcx, _GUID_884e2008_217d_11da_b2a4_000e7bbb2b09; rclsid
0x180057b35  call    cs:__imp_CoCreateInstance
0x180057b3b  mov     edi, eax
0x180057b3d  test    eax, eax
0x180057b3f  jns     short loc_180057B4B
0x180057b41  mov     edx, 902h
0x180057b46  jmp     loc_180057AB9
0x180057b4b  mov     rcx, [rsp+290h+var_248]
0x180057b50  mov     rax, [rcx]
0x180057b53  mov     rdx, rbx
0x180057b56  mov     rax, [rax+38h]
0x180057b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057b5f  mov     ebx, eax
0x180057b61  test    eax, eax
0x180057b63  jns     short loc_180057BA6
0x180057b65  mov     edx, 904h; void *
0x180057b6a  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x180057b71  mov     r9d, eax; char *
0x180057b74  mov     rcx, [rbp+198h]; this
0x180057b7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180057b80  nop
0x180057b81  lea     rcx, [rsp+290h+var_250]
0x180057b86  call    ??1?$com_ptr_t@UICspInformations@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>(void)
0x180057b8b  nop
0x180057b8c  lea     rcx, [rsp+290h+var_248]
0x180057b91  call    ??1?$com_ptr_t@UICspInformations@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>(void)
0x180057b96  nop
0x180057b97  lea     rcx, [rsp+290h+var_240]
0x180057b9c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180057ba1  jmp     loc_180057C6F
0x180057ba6  mov     rcx, [rsp+290h+var_250]
0x180057bab  mov     rax, [rcx]
0x180057bae  mov     rdx, [rsp+290h+var_248]
0x180057bb3  mov     rax, [rax+50h]
0x180057bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057bbc  mov     ebx, eax
0x180057bbe  test    eax, eax
0x180057bc0  jns     short loc_180057BC9
0x180057bc2  mov     edx, 905h
0x180057bc7  jmp     short loc_180057B6A
0x180057bc9  mov     rcx, [rsp+290h+var_238]
0x180057bce  mov     rax, [rcx]
0x180057bd1  mov     rdx, [rsp+290h+var_250]
0x180057bd6  mov     rax, [rax+0D0h]
0x180057bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057be2  mov     ebx, eax
0x180057be4  test    eax, eax
0x180057be6  jns     short loc_180057BF2
0x180057be8  mov     edx, 906h
0x180057bed  jmp     loc_180057B6A
0x180057bf2  mov     rcx, [rsp+290h+var_238]
0x180057bf7  mov     rax, [rcx]
0x180057bfa  mov     r8d, 1
0x180057c00  and     sil, 4
0x180057c04  neg     sil
0x180057c07  sbb     edx, edx
0x180057c09  neg     edx
0x180057c0b  inc     edx
0x180057c0d  mov     [rsp+290h+var_268], 2
0x180057c15  mov     dword ptr [rsp+290h+ppv], 0Ch
0x180057c1d  mov     r9, r15
0x180057c20  mov     rax, [rax+108h]
0x180057c27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057c2c  mov     ebx, eax
0x180057c2e  test    eax, eax
0x180057c30  jns     short loc_180057C3C
0x180057c32  mov     edx, 90Ch
0x180057c37  jmp     loc_180057B6A
0x180057c3c  mov     rax, [rsp+290h+var_238]
0x180057c41  mov     [rsp+290h+var_238], 0
0x180057c4a  mov     [r14], rax
0x180057c4d  lea     rcx, [rsp+290h+var_250]
0x180057c52  call    ??1?$com_ptr_t@UICspInformations@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>(void)
0x180057c57  nop
0x180057c58  lea     rcx, [rsp+290h+var_248]
0x180057c5d  call    ??1?$com_ptr_t@UICspInformations@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ICspInformations,wil::err_exception_policy>::~com_ptr_t<ICspInformations,wil::err_exception_policy>(void)
0x180057c62  nop
0x180057c63  lea     rcx, [rsp+290h+var_240]
0x180057c68  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180057c6d  xor     ebx, ebx
0x180057c6f  lea     rcx, [rsp+290h+var_238]
0x180057c74  call    ??1?$com_ptr_t@UIXMLDOMNodeList@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>::~com_ptr_t<IXMLDOMNodeList,wil::err_exception_policy>(void)
0x180057c79  mov     eax, ebx
0x180057c7b  mov     rcx, [rbp+190h+var_30]
0x180057c82  xor     rcx, rsp; StackCookie
0x180057c85  call    __security_check_cookie
0x180057c8a  mov     rbx, [rsp+290h+arg_10]
0x180057c92  add     rsp, 270h
0x180057c99  pop     r15
0x180057c9b  pop     r14
0x180057c9d  pop     rdi
0x180057c9e  pop     rsi
0x180057c9f  pop     rbp
0x180057ca0  retn
```
