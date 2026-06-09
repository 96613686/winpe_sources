# CCdfBuilder::InternIdentity(Windows::Isolation::Rtl::_REFERENCE_IDENTITY,Windows::Cdf::Rtl::_CDF_IDENTITYID &)

- ea: `0x1800e24c0`
- end: `0x1800e26fc`
- name: `?InternIdentity@CCdfBuilder@@QEAAJU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@AEAU_CDF_IDENTITYID@3Cdf@5@@Z`
- size: `572`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800ded64`
- `0x1800e2bf0`
- `0x1800e6978`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x1800448bc`
- `0x180044f60`
- `0x18004f2dc`
- `0x1800db2b8`
- `0x1800e1d2c`
- `0x1800e24c0`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e2606`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e26ba`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e2606`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e26ba`

## string_xrefs

- `0x1800e25c1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800e2679`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800e24e5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmc_pcmbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CCdfBuilder::InternIdentity(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v5; // ebx
  _DWORD *v6; // rdi
  __int64 v7; // r10
  __int64 v8; // r10
  unsigned int *v9; // r11
  signed int v10; // ecx
  int v11; // eax
  __int64 v12; // r10
  unsigned int *v13; // r11
  signed int v14; // ecx
  _BYTE v16[8]; // [rsp+30h] [rbp-39h] BYREF
  __int64 v17; // [rsp+38h] [rbp-31h] BYREF
  const char *v18; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+48h] [rbp-21h]
  unsigned int v20; // [rsp+50h] [rbp-19h]
  __int64 v21; // [rsp+58h] [rbp-11h] BYREF
  _DWORD *v22; // [rsp+60h] [rbp-9h] BYREF
  __int128 v23; // [rsp+68h] [rbp-1h] BYREF
  __int64 v24; // [rsp+78h] [rbp+Fh]

  v21 = a2;
  v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\pcmc_pcmbuilder.cpp";
  LODWORD(v17) = *(_DWORD *)(a1 + 712);
  HIDWORD(v17) = -1;
  v22 = 0;
  v20 = -1073741595;
  v16[0] = 0;
  v5 = BCL::HashTable::CTable<CCdfBuilder::CIdentityTableTraits>::FindOrInsertIfNotPresent<Windows::Isolation::Rtl::_REFERENCE_IDENTITY,CCdfBuilder::_IDENTITY_TO_BLOB>(
         (int)a1 + 384,
         (unsigned int)&v21,
         (unsigned int)&v17,
         (unsigned int)&v22,
         (__int64)v16);
  if ( v5 >= 0 )
  {
    v6 = v22;
    if ( !v22 )
    {
      v19 = 386;
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
        &v18,
        &v18);
      return v20;
    }
    if ( v16[0] )
    {
LABEL_22:
      v5 = 0;
      *a3 = *v6;
      return (unsigned int)v5;
    }
    v17 = 0;
    v24 = 0;
    v23 = 0;
    v5 = RtlQueryInformationReferenceIdentity(v21, 1, 24, &v23);
    if ( v5 < 0 || (v5 = RtlCreateReferenceIdentityAttributeEnumerator(v21, &v17), v5 < 0) )
    {
      v7 = v17;
    }
    else
    {
      v11 = CCdfBuilder::IdentityToStoredBlob(a1, (unsigned int)v23, v17, v6 + 1, 5);
      v7 = v17;
      v5 = v11;
      if ( v11 >= 0 )
      {
        ++*(_DWORD *)(a1 + 712);
        if ( v7 )
        {
          v20 = -1073741595;
          v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v7) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v13 + 4))(*v13, v12);
            v14 = 0;
          }
          else
          {
            v19 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v18);
            v14 = v20;
          }
          if ( v14 < 0 )
            RaiseException(v14, 1u, 0, 0);
        }
        goto LABEL_22;
      }
    }
    if ( v7 )
    {
      v20 = -1073741595;
      v18 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
      if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
        && (unsigned __int8)RtlIsTypeSafeHandleValid(v7) )
      {
        (*((void (__fastcall **)(_QWORD, __int64))v9 + 4))(*v9, v8);
        v10 = 0;
      }
      else
      {
        v19 = 292;
        Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v18);
        v10 = v20;
      }
      if ( v10 < 0 )
        RaiseException(v10, 1u, 0, 0);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800e24c0  push    rbp
0x1800e24c2  push    rbx
0x1800e24c3  push    rsi
0x1800e24c4  push    rdi
0x1800e24c5  push    r12
0x1800e24c7  push    r13
0x1800e24c9  push    r14
0x1800e24cb  lea     rbp, [rsp-27h]
0x1800e24d0  sub     rsp, 90h
0x1800e24d7  mov     rax, cs:__security_cookie
0x1800e24de  xor     rax, rsp
0x1800e24e1  mov     [rbp+57h+var_40], rax
0x1800e24e5  lea     rax, aOnecoreComNetf_30; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800e24ec  mov     [rbp+57h+var_68], rdx
0x1800e24f0  mov     [rbp+57h+var_80], rax
0x1800e24f4  lea     r9, [rbp+57h+var_60]
0x1800e24f8  mov     eax, [rcx+2C8h]
0x1800e24fe  lea     rdx, [rbp+57h+var_68]
0x1800e2502  mov     dword ptr [rbp+57h+var_88], eax
0x1800e2505  mov     r14, r8
0x1800e2508  lea     rax, [rbp+57h+var_90]
0x1800e250c  mov     dword ptr [rbp+57h+var_88+4], 0FFFFFFFFh
0x1800e2513  mov     rsi, rcx
0x1800e2516  mov     [rsp+0C0h+var_A0], rax
0x1800e251b  mov     r13d, 0C00000E5h
0x1800e2521  mov     [rbp+57h+var_60], 0
0x1800e2529  add     rcx, 180h
0x1800e2530  mov     [rbp+57h+var_70], r13d
0x1800e2534  lea     r8, [rbp+57h+var_88]
0x1800e2538  mov     [rbp+57h+var_90], 0
0x1800e253c  call    ??$FindOrInsertIfNotPresent@U_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@U_IDENTITY_TO_BLOB@CCdfBuilder@@@?$CTable@VCIdentityTableTraits@CCdfBuilder@@@HashTable@BCL@@QEAAJAEBU_REFERENCE_IDENTITY@Rtl@Isolation@Windows@@AEBU_IDENTITY_TO_BLOB@CCdfBuilder@@PEAPEAU78@PEA_N@Z; BCL::HashTable::CTable<CCdfBuilder::CIdentityTableTraits>::FindOrInsertIfNotPresent<Windows::Isolation::Rtl::_REFERENCE_IDENTITY,CCdfBuilder::_IDENTITY_TO_BLOB>(Windows::Isolation::Rtl::_REFERENCE_IDENTITY const &,CCdfBuilder::_IDENTITY_TO_BLOB const &,CCdfBuilder::_IDENTITY_TO_BLOB * *,bool *)
0x1800e2541  mov     ebx, eax
0x1800e2543  test    eax, eax
0x1800e2545  js      loc_1800E26C7
0x1800e254b  mov     rdi, [rbp+57h+var_60]
0x1800e254f  test    rdi, rdi
0x1800e2552  jnz     short loc_1800E2570
0x1800e2554  mov     [rbp+57h+var_78], 182h
0x1800e255b  lea     rdx, [rbp+57h+var_80]
0x1800e255f  lea     rcx, [rbp+57h+var_80]
0x1800e2563  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800e2568  mov     ebx, [rbp+57h+var_70]
0x1800e256b  jmp     loc_1800E26C7
0x1800e2570  cmp     [rbp+57h+var_90], 0
0x1800e2574  jnz     loc_1800E26C0
0x1800e257a  mov     rcx, [rbp+57h+var_68]
0x1800e257e  lea     r9, [rbp+57h+var_58]
0x1800e2582  xor     eax, eax
0x1800e2584  mov     [rbp+57h+var_88], 0
0x1800e258c  xorps   xmm0, xmm0
0x1800e258f  mov     [rbp+57h+var_48], rax
0x1800e2593  movups  [rbp+57h+var_58], xmm0
0x1800e2597  lea     r12d, [rax+1]
0x1800e259b  mov     edx, r12d
0x1800e259e  lea     r8d, [rax+18h]
0x1800e25a2  call    RtlQueryInformationReferenceIdentity
0x1800e25a7  mov     ebx, eax
0x1800e25a9  test    eax, eax
0x1800e25ab  jns     short loc_1800E2626
0x1800e25ad  mov     r10, [rbp+57h+var_88]
0x1800e25b1  test    r10, r10
0x1800e25b4  jz      loc_1800E26C7
0x1800e25ba  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800e25c1  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800e25c8  mov     [rbp+57h+var_70], r13d
0x1800e25cc  mov     [rbp+57h+var_80], rax
0x1800e25d0  test    r11, r11
0x1800e25d3  jz      short loc_1800E2611
0x1800e25d5  mov     rdx, r11
0x1800e25d8  mov     rcx, r10
0x1800e25db  call    RtlIsTypeSafeHandleValid
0x1800e25e0  test    al, al
0x1800e25e2  jz      short loc_1800E2611
0x1800e25e4  mov     ecx, [r11]
0x1800e25e7  mov     rdx, r10
0x1800e25ea  mov     rax, [r11+20h]
0x1800e25ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e25f3  xor     ecx, ecx; dwExceptionCode
0x1800e25f5  test    ecx, ecx
0x1800e25f7  jns     loc_1800E26C7
0x1800e25fd  xor     r9d, r9d; lpArguments
0x1800e2600  xor     r8d, r8d; nNumberOfArguments
0x1800e2603  mov     edx, r12d; dwExceptionFlags
0x1800e2606  call    cs:__imp_RaiseException
0x1800e260c  jmp     loc_1800E26C7
0x1800e2611  mov     [rbp+57h+var_78], 124h
0x1800e2618  lea     rcx, [rbp+57h+var_80]
0x1800e261c  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800e2621  mov     ecx, [rbp+57h+var_70]
0x1800e2624  jmp     short loc_1800E25F5
0x1800e2626  mov     rcx, [rbp+57h+var_68]
0x1800e262a  lea     rdx, [rbp+57h+var_88]
0x1800e262e  call    RtlCreateReferenceIdentityAttributeEnumerator
0x1800e2633  mov     ebx, eax
0x1800e2635  test    eax, eax
0x1800e2637  js      loc_1800E25AD
0x1800e263d  mov     r8, [rbp+57h+var_88]
0x1800e2641  lea     r9, [rdi+4]
0x1800e2645  mov     edx, dword ptr [rbp+57h+var_58]
0x1800e2648  mov     rcx, rsi
0x1800e264b  mov     dword ptr [rsp+0C0h+var_A0], 5
0x1800e2653  call    ?IdentityToStoredBlob@CCdfBuilder@@AEAAJKU_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@AEAU_CDF_BLOBID@3Cdf@5@W4_CDF_BLOB_TYPE@@@Z; CCdfBuilder::IdentityToStoredBlob(ulong,Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_BLOBID &,_CDF_BLOB_TYPE)
0x1800e2658  mov     r10, [rbp+57h+var_88]
0x1800e265c  mov     ebx, eax
0x1800e265e  test    eax, eax
0x1800e2660  js      loc_1800E25B1
0x1800e2666  add     [rsi+2C8h], r12d
0x1800e266d  test    r10, r10
0x1800e2670  jz      short loc_1800E26C0
0x1800e2672  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800e2679  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800e2680  mov     [rbp+57h+var_70], r13d
0x1800e2684  mov     [rbp+57h+var_80], rax
0x1800e2688  test    r11, r11
0x1800e268b  jz      short loc_1800E26E7
0x1800e268d  mov     rdx, r11
0x1800e2690  mov     rcx, r10
0x1800e2693  call    RtlIsTypeSafeHandleValid
0x1800e2698  test    al, al
0x1800e269a  jz      short loc_1800E26E7
0x1800e269c  mov     ecx, [r11]
0x1800e269f  mov     rdx, r10
0x1800e26a2  mov     rax, [r11+20h]
0x1800e26a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e26ab  xor     ecx, ecx; dwExceptionCode
0x1800e26ad  test    ecx, ecx
0x1800e26af  jns     short loc_1800E26C0
0x1800e26b1  xor     r9d, r9d; lpArguments
0x1800e26b4  xor     r8d, r8d; nNumberOfArguments
0x1800e26b7  mov     edx, r12d; dwExceptionFlags
0x1800e26ba  call    cs:__imp_RaiseException
0x1800e26c0  mov     eax, [rdi]
0x1800e26c2  xor     ebx, ebx
0x1800e26c4  mov     [r14], eax
0x1800e26c7  mov     eax, ebx
0x1800e26c9  mov     rcx, [rbp+57h+var_40]
0x1800e26cd  xor     rcx, rsp; StackCookie
0x1800e26d0  call    __security_check_cookie
0x1800e26d5  add     rsp, 90h
0x1800e26dc  pop     r14
0x1800e26de  pop     r13
0x1800e26e0  pop     r12
0x1800e26e2  pop     rdi
0x1800e26e3  pop     rsi
0x1800e26e4  pop     rbx
0x1800e26e5  pop     rbp
0x1800e26e6  retn
0x1800e26e7  mov     [rbp+57h+var_78], 124h
0x1800e26ee  lea     rcx, [rbp+57h+var_80]
0x1800e26f2  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800e26f7  mov     ecx, [rbp+57h+var_70]
0x1800e26fa  jmp     short loc_1800E26AD
```
