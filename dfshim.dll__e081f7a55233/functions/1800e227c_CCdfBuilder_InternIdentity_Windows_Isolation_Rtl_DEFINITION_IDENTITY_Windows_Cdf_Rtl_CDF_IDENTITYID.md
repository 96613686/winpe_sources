# CCdfBuilder::InternIdentity(Windows::Isolation::Rtl::_DEFINITION_IDENTITY,Windows::Cdf::Rtl::_CDF_IDENTITYID &)

- ea: `0x1800e227c`
- end: `0x1800e24b8`
- name: `?InternIdentity@CCdfBuilder@@QEAAJU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@AEAU_CDF_IDENTITYID@3Cdf@5@@Z`
- size: `572`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800de9f8`
- `0x1800e2bf0`
- `0x1800e6418`
- `0x1800e66d4`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x1800437f8`
- `0x180043f80`
- `0x18004f2dc`
- `0x1800da330`
- `0x1800e1d2c`
- `0x1800e227c`
- `0x180127dc0`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e23c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e2476`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e23c2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800e2476`

## string_xrefs

- `0x1800e237d`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800e2435`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800e22a1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\pcmc_pcmbuilder.cpp`

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
  v22 = 0;
  v16[0] = 0;
  v20 = -1073741595;
  HIDWORD(v17) = -1;
  v5 = BCL::HashTable::CTable<CCdfBuilder::CIdentityTableTraits>::FindOrInsertIfNotPresent<Windows::Isolation::Rtl::_DEFINITION_IDENTITY,CCdfBuilder::_IDENTITY_TO_BLOB>(
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
      v19 = 326;
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
    v5 = RtlQueryInformationDefinitionIdentity(v21, 1, 24, &v23);
    if ( v5 < 0 || (v5 = RtlCreateDefinitionIdentityAttributeEnumerator(v21, &v17), v5 < 0) )
    {
      v7 = v17;
    }
    else
    {
      v11 = CCdfBuilder::IdentityToStoredBlob(a1, (unsigned int)v23, v17, v6 + 1, 4);
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
0x1800e227c  push    rbp
0x1800e227e  push    rbx
0x1800e227f  push    rsi
0x1800e2280  push    rdi
0x1800e2281  push    r12
0x1800e2283  push    r13
0x1800e2285  push    r14
0x1800e2287  lea     rbp, [rsp-27h]
0x1800e228c  sub     rsp, 90h
0x1800e2293  mov     rax, cs:__security_cookie
0x1800e229a  xor     rax, rsp
0x1800e229d  mov     [rbp+57h+var_40], rax
0x1800e22a1  lea     rax, aOnecoreComNetf_30; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800e22a8  mov     [rbp+57h+var_68], rdx
0x1800e22ac  mov     [rbp+57h+var_80], rax
0x1800e22b0  lea     r9, [rbp+57h+var_60]
0x1800e22b4  mov     eax, [rcx+2C8h]
0x1800e22ba  lea     rdx, [rbp+57h+var_68]
0x1800e22be  mov     dword ptr [rbp+57h+var_88], eax
0x1800e22c1  mov     r14, r8
0x1800e22c4  lea     rax, [rbp+57h+var_90]
0x1800e22c8  mov     [rbp+57h+var_60], 0
0x1800e22d0  mov     rsi, rcx
0x1800e22d3  mov     [rsp+0C0h+var_A0], rax
0x1800e22d8  mov     r13d, 0C00000E5h
0x1800e22de  mov     [rbp+57h+var_90], 0
0x1800e22e2  add     rcx, 180h
0x1800e22e9  mov     [rbp+57h+var_70], r13d
0x1800e22ed  lea     r8, [rbp+57h+var_88]
0x1800e22f1  mov     dword ptr [rbp+57h+var_88+4], 0FFFFFFFFh
0x1800e22f8  call    ??$FindOrInsertIfNotPresent@U_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@U_IDENTITY_TO_BLOB@CCdfBuilder@@@?$CTable@VCIdentityTableTraits@CCdfBuilder@@@HashTable@BCL@@QEAAJAEBU_DEFINITION_IDENTITY@Rtl@Isolation@Windows@@AEBU_IDENTITY_TO_BLOB@CCdfBuilder@@PEAPEAU78@PEA_N@Z; BCL::HashTable::CTable<CCdfBuilder::CIdentityTableTraits>::FindOrInsertIfNotPresent<Windows::Isolation::Rtl::_DEFINITION_IDENTITY,CCdfBuilder::_IDENTITY_TO_BLOB>(Windows::Isolation::Rtl::_DEFINITION_IDENTITY const &,CCdfBuilder::_IDENTITY_TO_BLOB const &,CCdfBuilder::_IDENTITY_TO_BLOB * *,bool *)
0x1800e22fd  mov     ebx, eax
0x1800e22ff  test    eax, eax
0x1800e2301  js      loc_1800E2483
0x1800e2307  mov     rdi, [rbp+57h+var_60]
0x1800e230b  test    rdi, rdi
0x1800e230e  jnz     short loc_1800E232C
0x1800e2310  mov     [rbp+57h+var_78], 146h
0x1800e2317  lea     rdx, [rbp+57h+var_80]
0x1800e231b  lea     rcx, [rbp+57h+var_80]
0x1800e231f  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x1800e2324  mov     ebx, [rbp+57h+var_70]
0x1800e2327  jmp     loc_1800E2483
0x1800e232c  cmp     [rbp+57h+var_90], 0
0x1800e2330  jnz     loc_1800E247C
0x1800e2336  mov     rcx, [rbp+57h+var_68]
0x1800e233a  lea     r9, [rbp+57h+var_58]
0x1800e233e  xor     eax, eax
0x1800e2340  mov     [rbp+57h+var_88], 0
0x1800e2348  xorps   xmm0, xmm0
0x1800e234b  mov     [rbp+57h+var_48], rax
0x1800e234f  movups  [rbp+57h+var_58], xmm0
0x1800e2353  lea     r12d, [rax+1]
0x1800e2357  mov     edx, r12d
0x1800e235a  lea     r8d, [rax+18h]
0x1800e235e  call    RtlQueryInformationDefinitionIdentity
0x1800e2363  mov     ebx, eax
0x1800e2365  test    eax, eax
0x1800e2367  jns     short loc_1800E23E2
0x1800e2369  mov     r10, [rbp+57h+var_88]
0x1800e236d  test    r10, r10
0x1800e2370  jz      loc_1800E2483
0x1800e2376  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800e237d  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800e2384  mov     [rbp+57h+var_70], r13d
0x1800e2388  mov     [rbp+57h+var_80], rax
0x1800e238c  test    r11, r11
0x1800e238f  jz      short loc_1800E23CD
0x1800e2391  mov     rdx, r11
0x1800e2394  mov     rcx, r10
0x1800e2397  call    RtlIsTypeSafeHandleValid
0x1800e239c  test    al, al
0x1800e239e  jz      short loc_1800E23CD
0x1800e23a0  mov     ecx, [r11]
0x1800e23a3  mov     rdx, r10
0x1800e23a6  mov     rax, [r11+20h]
0x1800e23aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e23af  xor     ecx, ecx; dwExceptionCode
0x1800e23b1  test    ecx, ecx
0x1800e23b3  jns     loc_1800E2483
0x1800e23b9  xor     r9d, r9d; lpArguments
0x1800e23bc  xor     r8d, r8d; nNumberOfArguments
0x1800e23bf  mov     edx, r12d; dwExceptionFlags
0x1800e23c2  call    cs:__imp_RaiseException
0x1800e23c8  jmp     loc_1800E2483
0x1800e23cd  mov     [rbp+57h+var_78], 124h
0x1800e23d4  lea     rcx, [rbp+57h+var_80]
0x1800e23d8  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800e23dd  mov     ecx, [rbp+57h+var_70]
0x1800e23e0  jmp     short loc_1800E23B1
0x1800e23e2  mov     rcx, [rbp+57h+var_68]
0x1800e23e6  lea     rdx, [rbp+57h+var_88]
0x1800e23ea  call    RtlCreateDefinitionIdentityAttributeEnumerator
0x1800e23ef  mov     ebx, eax
0x1800e23f1  test    eax, eax
0x1800e23f3  js      loc_1800E2369
0x1800e23f9  mov     r8, [rbp+57h+var_88]
0x1800e23fd  lea     r9, [rdi+4]
0x1800e2401  mov     edx, dword ptr [rbp+57h+var_58]
0x1800e2404  mov     rcx, rsi
0x1800e2407  mov     dword ptr [rsp+0C0h+var_A0], 4
0x1800e240f  call    ?IdentityToStoredBlob@CCdfBuilder@@AEAAJKU_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@AEAU_CDF_BLOBID@3Cdf@5@W4_CDF_BLOB_TYPE@@@Z; CCdfBuilder::IdentityToStoredBlob(ulong,Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,Windows::Cdf::Rtl::_CDF_BLOBID &,_CDF_BLOB_TYPE)
0x1800e2414  mov     r10, [rbp+57h+var_88]
0x1800e2418  mov     ebx, eax
0x1800e241a  test    eax, eax
0x1800e241c  js      loc_1800E236D
0x1800e2422  add     [rsi+2C8h], r12d
0x1800e2429  test    r10, r10
0x1800e242c  jz      short loc_1800E247C
0x1800e242e  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_IDENTITY_ATTRIBUTE_ENUMERATOR@Rtl@Isolation@Windows@@VCIdentityAttributeEnumerator@@VCIdentityAttributeEnumeratorCD@@VCIdentityAttributeEnumeratorTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_IDENTITY_ATTRIBUTE_ENUMERATOR,CIdentityAttributeEnumerator,CIdentityAttributeEnumeratorCD,CIdentityAttributeEnumeratorTraits>::ms_ptti
0x1800e2435  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800e243c  mov     [rbp+57h+var_70], r13d
0x1800e2440  mov     [rbp+57h+var_80], rax
0x1800e2444  test    r11, r11
0x1800e2447  jz      short loc_1800E24A3
0x1800e2449  mov     rdx, r11
0x1800e244c  mov     rcx, r10
0x1800e244f  call    RtlIsTypeSafeHandleValid
0x1800e2454  test    al, al
0x1800e2456  jz      short loc_1800E24A3
0x1800e2458  mov     ecx, [r11]
0x1800e245b  mov     rdx, r10
0x1800e245e  mov     rax, [r11+20h]
0x1800e2462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e2467  xor     ecx, ecx; dwExceptionCode
0x1800e2469  test    ecx, ecx
0x1800e246b  jns     short loc_1800E247C
0x1800e246d  xor     r9d, r9d; lpArguments
0x1800e2470  xor     r8d, r8d; nNumberOfArguments
0x1800e2473  mov     edx, r12d; dwExceptionFlags
0x1800e2476  call    cs:__imp_RaiseException
0x1800e247c  mov     eax, [rdi]
0x1800e247e  xor     ebx, ebx
0x1800e2480  mov     [r14], eax
0x1800e2483  mov     eax, ebx
0x1800e2485  mov     rcx, [rbp+57h+var_40]
0x1800e2489  xor     rcx, rsp; StackCookie
0x1800e248c  call    __security_check_cookie
0x1800e2491  add     rsp, 90h
0x1800e2498  pop     r14
0x1800e249a  pop     r13
0x1800e249c  pop     r12
0x1800e249e  pop     rdi
0x1800e249f  pop     rsi
0x1800e24a0  pop     rbx
0x1800e24a1  pop     rbp
0x1800e24a2  retn
0x1800e24a3  mov     [rbp+57h+var_78], 124h
0x1800e24aa  lea     rcx, [rbp+57h+var_80]
0x1800e24ae  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800e24b3  mov     ecx, [rbp+57h+var_70]
0x1800e24b6  jmp     short loc_1800E2469
```
