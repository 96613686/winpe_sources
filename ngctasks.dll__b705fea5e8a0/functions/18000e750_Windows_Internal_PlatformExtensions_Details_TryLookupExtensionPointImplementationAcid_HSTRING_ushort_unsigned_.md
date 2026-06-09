# Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)

- ea: `0x18000e750`
- end: `0x18000e905`
- name: `?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(HSTRING this, HSTRING, unsigned __int16 *, unsigned __int64, const struct _GUID *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e11c`

## callees

- `0x180006330`
- `0x180008138`
- `0x180008ad4`
- `0x180008c94`
- `0x1800090b8`
- `0x180009ae4`
- `0x180009b9c`
- `0x18000b39c`
- `0x18000cc34`
- `0x18000d318`
- `0x18000d754`
- `0x18000e750`

## string_xrefs

- `0x18000e878`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18000e8b7`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18000e8a1`: `The product platform extension registry is invalid. There are multiple extensions and no default registered for the extension point.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
        HSTRING this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _OWORD *a4)
{
  char v6; // bl
  __int64 v7; // rax
  int v8; // edi
  int v10; // [rsp+20h] [rbp-E0h]
  char *v11[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v12; // [rsp+40h] [rbp-C0h] BYREF
  RTL_SRWLOCK *v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v15[8]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v16[15]; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v17[34]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v18; // [rsp+1F0h] [rbp+F0h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  v12 = a2;
  v14 = 128;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>((__int64)v17);
  v17[0] = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::`vftable';
  v6 = 1;
  if ( a4 )
  {
    wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)v17,
      &v13);
    v7 = v18;
    *(_OWORD *)(v18 + 24) = *a4;
    *(_BYTE *)(v7 + 4) = 1;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
    (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)v17,
    this);
  *v12 = 0;
  LOBYTE(v11[0]) = 0;
  HIDWORD(v11[0]) = 0;
  v13 = (RTL_SRWLOCK *)v16;
  v16[0] = &wistd::__function::__func<_lambda_4f9cb091d726181fa859ce89134efc24_,long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)>::`vftable';
  v16[1] = &v12;
  v16[2] = &v14;
  v16[3] = v17;
  v16[4] = v11;
  v16[5] = (char *)v11 + 4;
  v16[13] = v16;
  v8 = Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(this, (__int64)v15);
  wistd::function<bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::~function<bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>(v15);
  if ( v8 >= 0 )
  {
    if ( LOBYTE(v11[0]) || SHIDWORD(v11[0]) <= 1 )
      v6 = 0;
    wil::details::in1diag3::FailFast_HrIfMsg(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)0x8007000DLL,
      v6,
      (bool)"The product platform extension registry is invalid. There are multiple extensions and no default registered "
            "for the extension point.",
      v11[0]);
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(
      (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)v17,
      v12);
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B7,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v8,
      v10);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::~TryLookupExtensionPointImplementationAcid((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)v17);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000e750  mov     [rsp-8+arg_10], rbx
0x18000e755  push    rbp
0x18000e756  push    rsi
0x18000e757  push    rdi
0x18000e758  lea     rbp, [rsp-140h]
0x18000e760  sub     rsp, 240h
0x18000e767  mov     rax, cs:__security_cookie
0x18000e76e  xor     rax, rsp
0x18000e771  mov     [rbp+150h+var_20], rax
0x18000e778  mov     rdi, r9
0x18000e77b  mov     rsi, rcx
0x18000e77e  mov     [rsp+250h+var_210], rdx
0x18000e783  mov     [rsp+250h+var_1F8], 80h
0x18000e78c  lea     rcx, [rbp+150h+var_170]
0x18000e790  call    ??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18000e795  nop
0x18000e796  lea     rax, ??_7TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::`vftable'
0x18000e79d  mov     [rbp+150h+var_170], rax
0x18000e7a1  mov     ebx, 1
0x18000e7a6  test    rdi, rdi
0x18000e7a9  jz      short loc_18000E7D6
0x18000e7ab  lea     rdx, [rsp+250h+var_200]
0x18000e7b0  lea     rcx, [rbp+150h+var_170]
0x18000e7b4  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e7b9  nop
0x18000e7ba  mov     rax, [rbp+150h+var_60]
0x18000e7c1  movups  xmm0, xmmword ptr [rdi]
0x18000e7c4  movdqu  xmmword ptr [rax+18h], xmm0
0x18000e7c9  mov     [rax+4], bl
0x18000e7cc  lea     rcx, [rsp+250h+var_200]
0x18000e7d1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e7d6  mov     rdx, rsi; HSTRING
0x18000e7d9  lea     rcx, [rbp+150h+var_170]; this
0x18000e7dd  call    ?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)
0x18000e7e2  xor     ecx, ecx
0x18000e7e4  mov     rax, [rsp+250h+var_210]
0x18000e7e9  mov     [rax], cx
0x18000e7ec  mov     byte ptr [rsp+250h+var_220], cl; char *
0x18000e7f0  mov     dword ptr [rsp+250h+var_220+4], ecx
0x18000e7f4  mov     [rbp+150h+var_180], rcx
0x18000e7f8  lea     rax, [rsp+250h+var_1E8]
0x18000e7fd  mov     [rsp+250h+var_200], rax
0x18000e802  lea     rax, ??_7?$__base@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@__function@wistd@@6B@; const wistd::__function::__base<long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)>::`vftable'
0x18000e809  mov     [rsp+250h+var_1E8], rax
0x18000e80e  lea     rax, ??_7?$__func@V_lambda_4f9cb091d726181fa859ce89134efc24_@@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_4f9cb091d726181fa859ce89134efc24_,long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)>::`vftable'
0x18000e815  mov     [rsp+250h+var_1E8], rax
0x18000e81a  lea     rax, [rsp+250h+var_210]
0x18000e81f  mov     [rsp+250h+var_1E0], rax
0x18000e824  lea     rax, [rsp+250h+var_1F8]
0x18000e829  mov     [rsp+250h+var_1D8], rax
0x18000e82e  lea     rax, [rbp+150h+var_170]
0x18000e832  mov     [rbp+150h+var_1D0], rax
0x18000e836  lea     rax, [rsp+250h+var_220]
0x18000e83b  mov     [rbp+150h+var_1C8], rax
0x18000e83f  lea     rax, [rsp+250h+var_220+4]
0x18000e844  mov     [rbp+150h+var_1C0], rax
0x18000e848  lea     rax, [rsp+250h+var_1E8]
0x18000e84d  mov     [rbp+150h+var_180], rax
0x18000e851  lea     rdx, [rsp+250h+var_1F0]
0x18000e856  mov     rcx, rsi
0x18000e859  call    ?ForEachEnabledExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@AEBV?$function@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@wistd@@@Z; Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(HSTRING__ *,wistd::function<long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)> const &)
0x18000e85e  mov     edi, eax
0x18000e860  lea     rcx, [rsp+250h+var_1F0]
0x18000e865  call    ??1?$function@$$A6A_NPEAX_K01I@Z@wistd@@QEAA@XZ; wistd::function<bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::~function<bool (void *,unsigned __int64,void *,unsigned __int64,uint)>(void)
0x18000e86a  test    edi, edi
0x18000e86c  jns     short loc_18000E88B
0x18000e86e  mov     rcx, [rbp+158h]; this
0x18000e875  mov     r9d, edi; char *
0x18000e878  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000e87f  mov     edx, 1B7h; void *
0x18000e884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e889  jmp     short loc_18000E8D8
0x18000e88b  cmp     byte ptr [rsp+250h+var_220], 0
0x18000e890  jnz     short loc_18000E898
0x18000e892  cmp     dword ptr [rsp+250h+var_220+4], ebx
0x18000e896  jg      short loc_18000E89A
0x18000e898  xor     bl, bl
0x18000e89a  mov     rcx, [rbp+158h]; this
0x18000e8a1  lea     rax, aTheProductPlat; "The product platform extension registry"...
0x18000e8a8  mov     qword ptr [rsp+250h+var_228], rax; bool
0x18000e8ad  mov     [rsp+250h+var_230], bl; char
0x18000e8b1  mov     r9d, 8007000Dh; char *
0x18000e8b7  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000e8be  mov     edx, 1BBh; void *
0x18000e8c3  call    ?FailFast_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::FailFast_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18000e8c8  mov     rdx, [rsp+250h+var_210]; unsigned __int16 *
0x18000e8cd  lea     rcx, [rbp+150h+var_170]; this
0x18000e8d1  call    ?Stop@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::Stop(ushort const *)
0x18000e8d6  xor     edi, edi
0x18000e8d8  lea     rcx, [rbp+150h+var_170]; this
0x18000e8dc  call    ??1TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::~TryLookupExtensionPointImplementationAcid(void)
0x18000e8e1  mov     eax, edi
0x18000e8e3  mov     rcx, [rbp+150h+var_20]
0x18000e8ea  xor     rcx, rsp; StackCookie
0x18000e8ed  call    __security_check_cookie
0x18000e8f2  mov     rbx, [rsp+250h+arg_10]
0x18000e8fa  add     rsp, 240h
0x18000e901  pop     rdi
0x18000e902  pop     rsi
0x18000e903  pop     rbp
0x18000e904  retn
```
