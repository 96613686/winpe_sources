# Windows::Isolation::RegProv::Rtl::CreateIsolatedRegistryFromProvider(ulong,Windows::Isolation::RegProv::Rtl::_ISOLATED_REGISTRY_PROVIDER *,Windows::Isolation::Rtl::_ISOLATED_REGISTRY *,Windows::Isolation::Rtl::_ISOLATED_KEY *)

- ea: `0x1800408bc`
- end: `0x180040a77`
- name: `?CreateIsolatedRegistryFromProvider@Rtl@RegProv@Isolation@Windows@@YAJKPEAU_ISOLATED_REGISTRY_PROVIDER@1234@PEAU_ISOLATED_REGISTRY@134@PEAU_ISOLATED_KEY@134@@Z`
- size: `443`
- prototype: `__int64 __fastcall(Windows::Isolation::RegProv::Rtl *__hidden this, unsigned int, struct Windows::Isolation::RegProv::Rtl::_ISOLATED_REGISTRY_PROVIDER *, struct Windows::Isolation::Rtl::_ISOLATED_REGISTRY *, struct Windows::Isolation::Rtl::_ISOLATED_KEY *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800264c8`

## callees

- `0x180012b1c`
- `0x18001766c`
- `0x1800403dc`
- `0x1800408bc`
- `0x18004f2dc`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800409a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040a45`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800409a2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180040a45`

## string_xrefs

- `0x180040959`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180040a00`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800408de`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\isoreg_top.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Isolation::RegProv::Rtl::CreateIsolatedRegistryFromProvider(
        Windows::Isolation::RegProv::Rtl *this,
        __int64 a2,
        struct Windows::Isolation::RegProv::Rtl::_ISOLATED_REGISTRY_PROVIDER *a3,
        struct Windows::Isolation::Rtl::_ISOLATED_REGISTRY *a4)
{
  int v5; // ebx
  __int64 v6; // r10
  unsigned int *v7; // r11
  signed int v8; // ecx
  __int64 v9; // rax
  __int64 v10; // r10
  unsigned int *v11; // r11
  signed int v12; // ecx
  _DWORD v14[2]; // [rsp+20h] [rbp-40h] BYREF
  void *v15; // [rsp+28h] [rbp-38h]
  const char *v16; // [rsp+30h] [rbp-30h] BYREF
  int v17; // [rsp+38h] [rbp-28h]
  unsigned int v18; // [rsp+40h] [rbp-20h]
  const char *v19; // [rsp+48h] [rbp-18h] BYREF
  int v20; // [rsp+50h] [rbp-10h]
  int v21; // [rsp+58h] [rbp-8h]
  __int64 v22; // [rsp+78h] [rbp+18h] BYREF
  __int64 v23; // [rsp+88h] [rbp+28h] BYREF

  v18 = -1073741595;
  v16 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\isoreg_top.cpp";
  v14[1] = 0;
  v23 = 0;
  v22 = 0;
  if ( a3 )
  {
    *(_QWORD *)a3 = 0;
    v15 = &Windows::Isolation::Implementation::Rtl::RtlpDirectIsolatedRegistry;
    v14[0] = 0;
    v5 = ((__int64 (__fastcall *)(_DWORD *, __int64 *, struct Windows::Isolation::RegProv::Rtl::_ISOLATED_REGISTRY_PROVIDER *, struct Windows::Isolation::Rtl::_ISOLATED_REGISTRY *))Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::Allocate)(
           v14,
           &v23,
           a3,
           a4);
    if ( v5 >= 0 )
    {
      v9 = v23;
      v5 = 0;
      v23 = *(_QWORD *)a3;
      *(_QWORD *)a3 = v9;
    }
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v22);
    if ( v23 )
    {
      v16 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      v18 = -1073741595;
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v23) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v7 + 4))(*v7, v6);
        v8 = 0;
      }
      else
      {
        v17 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v16);
        v8 = v18;
      }
      if ( v8 < 0 )
        RaiseException(v8, 1u, 0, 0);
    }
  }
  else
  {
    v17 = 858;
    Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v16);
    Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(&v22);
    if ( v23 )
    {
      v21 = -1073741595;
      v19 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v23) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v11 + 4))(*v11, v10);
        v12 = 0;
      }
      else
      {
        v20 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v19);
        v12 = v21;
      }
      if ( v12 < 0 )
        RaiseException(v12, 1u, 0, 0);
    }
    return v18;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800408bc  mov     rax, rsp
0x1800408bf  mov     [rax+8], rbx
0x1800408c3  mov     [rax+18h], rdi
0x1800408c7  mov     [rax+20h], r9
0x1800408cb  mov     [rax+10h], rdx
0x1800408cf  push    rbp
0x1800408d0  mov     rbp, rsp
0x1800408d3  sub     rsp, 60h
0x1800408d7  mov     [rbp+var_20], 0C00000E5h
0x1800408de  lea     rax, aOnecoreComNetf_96; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800408e5  mov     [rbp+var_30], rax
0x1800408e9  mov     rdi, r8
0x1800408ec  mov     [rbp+var_3C], 0
0x1800408f3  mov     [rbp+arg_18], 0
0x1800408fb  mov     [rbp+arg_8], 0
0x180040903  test    r8, r8
0x180040906  jz      loc_1800409D7
0x18004090c  lea     rax, ?RtlpDirectIsolatedRegistry@Rtl@Implementation@Isolation@Windows@@3U_ISOLATED_REGISTRY_PROVIDER@1RegProv@34@B; Windows::Isolation::RegProv::Rtl::_ISOLATED_REGISTRY_PROVIDER const Windows::Isolation::Implementation::Rtl::RtlpDirectIsolatedRegistry
0x180040913  mov     qword ptr [r8], 0
0x18004091a  lea     rdx, [rbp+arg_18]
0x18004091e  mov     [rbp+var_38], rax
0x180040922  lea     rcx, [rbp+var_40]
0x180040926  mov     [rbp+var_40], 0
0x18004092d  call    ?Allocate@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@SAJAEAUISOLATED_REGISTRY_CONSTRUCTOR_DATA@@AEAU_ISOLATED_REGISTRY@2Isolation@5@@Z; Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::Allocate(ISOLATED_REGISTRY_CONSTRUCTOR_DATA &,Windows::Isolation::Rtl::_ISOLATED_REGISTRY &)
0x180040932  mov     ebx, eax
0x180040934  test    eax, eax
0x180040936  jns     loc_1800409C2
0x18004093c  lea     rcx, [rbp+arg_8]
0x180040940  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x180040945  mov     r10, [rbp+arg_18]
0x180040949  test    r10, r10
0x18004094c  jz      loc_180040A4E
0x180040952  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
0x180040959  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180040960  mov     [rbp+var_30], rax
0x180040964  mov     [rbp+var_20], 0C00000E5h
0x18004096b  test    r11, r11
0x18004096e  jz      short loc_1800409AD
0x180040970  mov     rdx, r11
0x180040973  mov     rcx, r10
0x180040976  call    RtlIsTypeSafeHandleValid
0x18004097b  test    al, al
0x18004097d  jz      short loc_1800409AD
0x18004097f  mov     ecx, [r11]
0x180040982  mov     rdx, r10
0x180040985  mov     rax, [r11+20h]
0x180040989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004098e  xor     ecx, ecx; dwExceptionCode
0x180040990  test    ecx, ecx
0x180040992  jns     loc_180040A4E
0x180040998  xor     r9d, r9d; lpArguments
0x18004099b  xor     r8d, r8d; nNumberOfArguments
0x18004099e  lea     edx, [r9+1]; dwExceptionFlags
0x1800409a2  call    cs:__imp_RaiseException
0x1800409a8  jmp     loc_180040A4E
0x1800409ad  mov     [rbp+var_28], 124h
0x1800409b4  lea     rcx, [rbp+var_30]
0x1800409b8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800409bd  mov     ecx, [rbp+var_20]
0x1800409c0  jmp     short loc_180040990
0x1800409c2  mov     rax, [rbp+arg_18]
0x1800409c6  xor     ebx, ebx
0x1800409c8  mov     rcx, [rdi]
0x1800409cb  mov     [rbp+arg_18], rcx
0x1800409cf  mov     [rdi], rax
0x1800409d2  jmp     loc_18004093C
0x1800409d7  lea     rcx, [rbp+var_30]
0x1800409db  mov     [rbp+var_28], 35Ah
0x1800409e2  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800409e7  lea     rcx, [rbp+arg_8]
0x1800409eb  call    ?Close@?$CTSHANDLE@VCISOLATED_KEY_Traits@Rtl@Isolation@Windows@@@Rtl@TypeSafeHandle@Windows@@QEAAXXZ; Windows::TypeSafeHandle::Rtl::CTSHANDLE<Windows::Isolation::Rtl::CISOLATED_KEY_Traits>::Close(void)
0x1800409f0  mov     r10, [rbp+arg_18]
0x1800409f4  test    r10, r10
0x1800409f7  jz      short loc_180040A4B
0x1800409f9  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_ISOLATED_REGISTRY@Rtl@Isolation@Windows@@VCIsolatedRegistry@@UISOLATED_REGISTRY_CONSTRUCTOR_DATA@@VCIsolatedRegistryTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_ISOLATED_REGISTRY,CIsolatedRegistry,ISOLATED_REGISTRY_CONSTRUCTOR_DATA,CIsolatedRegistryTraits>::ms_ptti
0x180040a00  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180040a07  mov     [rbp+var_8], 0C00000E5h
0x180040a0e  mov     [rbp+var_18], rax
0x180040a12  test    r11, r11
0x180040a15  jz      short loc_180040A62
0x180040a17  mov     rdx, r11
0x180040a1a  mov     rcx, r10
0x180040a1d  call    RtlIsTypeSafeHandleValid
0x180040a22  test    al, al
0x180040a24  jz      short loc_180040A62
0x180040a26  mov     ecx, [r11]
0x180040a29  mov     rdx, r10
0x180040a2c  mov     rax, [r11+20h]
0x180040a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040a35  xor     ecx, ecx; dwExceptionCode
0x180040a37  test    ecx, ecx
0x180040a39  jns     short loc_180040A4B
0x180040a3b  xor     r9d, r9d; lpArguments
0x180040a3e  xor     r8d, r8d; nNumberOfArguments
0x180040a41  lea     edx, [r9+1]; dwExceptionFlags
0x180040a45  call    cs:__imp_RaiseException
0x180040a4b  mov     ebx, [rbp+var_20]
0x180040a4e  lea     r11, [rsp+60h+var_s0]
0x180040a53  mov     eax, ebx
0x180040a55  mov     rbx, [r11+10h]
0x180040a59  mov     rdi, [r11+20h]
0x180040a5d  mov     rsp, r11
0x180040a60  pop     rbp
0x180040a61  retn
0x180040a62  mov     [rbp+var_10], 124h
0x180040a69  lea     rcx, [rbp+var_18]
0x180040a6d  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180040a72  mov     ecx, [rbp+var_8]
0x180040a75  jmp     short loc_180040A37
```
