# IsolationImplementation::Rtl::CApplicationResolver::FillResolversFromStoreList(Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_CUSTOM_STORE_LIST const &)

- ea: `0x180038398`
- end: `0x180038717`
- name: `?FillResolversFromStoreList@CApplicationResolver@Rtl@IsolationImplementation@@AEAAJAEBU_CREATE_APPLICATION_CONTEXT_DATA_CUSTOM_STORE_LIST@2Isolation@Windows@@@Z`
- size: `895`
- prototype: `__int64 __fastcall(IsolationImplementation::Rtl::CApplicationResolver *__hidden this, const struct Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_CUSTOM_STORE_LIST *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180039a14`

## callees

- `0x180012950`
- `0x180012b1c`
- `0x1800165fc`
- `0x180016e64`
- `0x180017c48`
- `0x180018b30`
- `0x180037cdc`
- `0x180038398`
- `0x18004f2dc`
- `0x18012a020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038594`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038642`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800386f7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038594`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038642`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800386f7`

## string_xrefs

- `0x180038552`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x180038600`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800386b1`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tsh_provider.h`
- `0x1800384f2`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\inc\tshandle.h`
- `0x1800383b5`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\ac_core.cpp`
- `0x180038689`: `onecore\com\netfx\windowsbuilt\iso_legacy\base\isolation\ac_core.cpp`

## pseudocode

```c
__int64 __fastcall IsolationImplementation::Rtl::CApplicationResolver::FillResolversFromStoreList(
        IsolationImplementation::Rtl::CApplicationResolver *this,
        const struct Windows::Isolation::Rtl::_CREATE_APPLICATION_CONTEXT_DATA_CUSTOM_STORE_LIST *a2)
{
  unsigned __int64 v2; // rsi
  __int64 v4; // r15
  int v5; // ebx
  int v6; // r9d
  __int64 v7; // r14
  __int64 v8; // r10
  __int64 v9; // r10
  int v10; // eax
  bool v11; // sf
  __int64 v12; // r10
  __int64 v13; // r8
  __int64 *v14; // rbx
  unsigned __int64 v15; // r11
  __int64 v16; // rdx
  unsigned __int64 v17; // r9
  _QWORD *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rdx
  int v21; // eax
  __int64 v22; // r10
  __int64 v23; // r10
  unsigned int *v24; // r11
  signed int v25; // ecx
  __int64 v27; // r10
  unsigned int *v28; // r11
  signed int v29; // ecx
  __int64 v30; // r10
  unsigned int *v31; // r11
  signed int v32; // ecx
  const char *v33; // [rsp+20h] [rbp-30h] BYREF
  int v34; // [rsp+28h] [rbp-28h]
  unsigned int v35; // [rsp+30h] [rbp-20h]
  const char *v36; // [rsp+38h] [rbp-18h] BYREF
  int v37; // [rsp+40h] [rbp-10h]
  int v38; // [rsp+48h] [rbp-8h]
  __int64 v39; // [rsp+88h] [rbp+38h] BYREF

  v2 = *((_QWORD *)a2 + 2);
  v33 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\ac_core.cpp";
  v35 = -1073741595;
  if ( v2 )
  {
    v4 = *((_QWORD *)a2 + 3);
    if ( v4 )
    {
      v5 = *(_DWORD *)BCL::Nt::CSmartArrayHolder<unsigned __int64,Isolation::Resolver::CComponentStoreDependencyResolver,BCL::CDefaultObjectTraits<Isolation::Resolver::CComponentStoreDependencyResolver,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(
                        (char *)this + 16,
                        &v39,
                        v2);
      if ( v5 >= 0 )
      {
        v7 = 0;
        while ( 1 )
        {
          v8 = *(_QWORD *)(v4 + 8 * v7);
          v39 = 0;
          if ( *(_DWORD *)(v8 + 12) == 1 )
            break;
          if ( *(_DWORD *)(v8 + 12) == 2 )
          {
            if ( *(_QWORD *)(v8 + 16) )
            {
              v34 = 2026;
              goto LABEL_49;
            }
            v5 = RtlCreateUserComponentStore(0, 0, &v39);
            v11 = v5 < 0;
          }
          else
          {
            if ( *(_DWORD *)(v8 + 12) != 3 )
            {
              v34 = 2036;
              goto LABEL_45;
            }
            if ( !(unsigned __int8)RtlIsComponentStoreHandleValid(*(_QWORD *)(v8 + 16)) )
            {
              v34 = 2031;
LABEL_49:
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v33);
              return v35;
            }
            v10 = RtlDuplicateComponentStoreHandle(*(_QWORD *)(v9 + 16), &v39);
            v5 = 0;
            if ( v10 < 0 )
              v5 = v10;
            v11 = v5 < 0;
          }
          if ( v11 )
            goto LABEL_51;
          if ( !(unsigned __int8)RtlIsComponentStoreHandleValid(v39) )
          {
            v34 = 2039;
            if ( v12 )
            {
              v38 = -1073741595;
              v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
              if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
                && (unsigned __int8)RtlIsTypeSafeHandleValid(v12) )
              {
                (*((void (__fastcall **)(_QWORD, __int64))v28 + 4))(*v28, v27);
                v29 = 0;
              }
              else
              {
                v37 = 292;
                Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
                v29 = v38;
              }
              if ( v29 < 0 )
                RaiseException(v29, 1u, 0, 0);
            }
            goto LABEL_45;
          }
          v13 = *((_QWORD *)this + 1);
          v14 = (__int64 *)((char *)this + 24);
          *((_QWORD *)this + 1) = v13 + 1;
          v15 = *((_QWORD *)this + 4);
          if ( *((_QWORD *)this + 5) < v15 )
          {
            v16 = *v14 + 16LL * *((_QWORD *)this + 5);
            v17 = v15 - *((_QWORD *)this + 5);
            if ( v15 != *((_QWORD *)this + 5) )
            {
              do
              {
                v18 = (_QWORD *)v16;
                v16 += 16;
                *v18 = &Isolation::Resolver::CComponentStoreDependencyResolver::`vftable';
                v18[1] = 0;
                --v17;
              }
              while ( v17 );
              v12 = v39;
            }
            *((_QWORD *)this + 5) = v15;
          }
          v19 = *v14;
          v38 = -1073741595;
          v20 = (_QWORD *)(16 * v13 + 8 + v19);
          v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tshandle.h";
          if ( *v20 )
          {
            v37 = 142;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
              &v36,
              &v36);
            v5 = v38;
          }
          else
          {
            v21 = RtlDuplicateComponentStoreHandle(v12, v20);
            v5 = 0;
            if ( v21 < 0 )
              v5 = v21;
          }
          v22 = v39;
          if ( v5 < 0 )
            goto LABEL_52;
          if ( v39 )
          {
            v38 = -1073741595;
            v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
            if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
              && (unsigned __int8)RtlIsTypeSafeHandleValid(v39) )
            {
              (*((void (__fastcall **)(_QWORD, __int64))v24 + 4))(*v24, v23);
              v25 = 0;
            }
            else
            {
              v37 = 292;
              Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
              v25 = v38;
            }
            if ( v25 < 0 )
              RaiseException(v25, 1u, 0, 0);
          }
          if ( ++v7 >= v2 )
            return 0;
        }
        v5 = -1073740756;
        Windows::ErrorHandling::COM::ReportNtErrorOrigination(
          (Windows::ErrorHandling::COM *)"onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\ac_core.cpp",
          (const char *)0x7E2,
          -1073740756,
          v6);
LABEL_51:
        v22 = v39;
LABEL_52:
        if ( v22 )
        {
          v36 = "onecore\\com\\netfx\\windowsbuilt\\iso_legacy\\base\\isolation\\inc\\tsh_provider.h";
          v38 = -1073741595;
          if ( Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
            && (unsigned __int8)RtlIsTypeSafeHandleValid(v22) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v31 + 4))(*v31, v30);
            v32 = 0;
          }
          else
          {
            v37 = 292;
            Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(&v36);
            v32 = v38;
          }
          if ( v32 < 0 )
            RaiseException(v32, 1u, 0, 0);
        }
      }
    }
    else
    {
      v34 = 2006;
LABEL_45:
      Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(
        &v33,
        &v33);
      return v35;
    }
  }
  else
  {
    return 0;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180038398  mov     [rsp-28h+arg_0], rbx
0x18003839d  mov     [rsp-28h+arg_10], rsi
0x1800383a2  push    rbp
0x1800383a3  push    rdi
0x1800383a4  push    r13
0x1800383a6  push    r14
0x1800383a8  push    r15
0x1800383aa  mov     rbp, rsp
0x1800383ad  sub     rsp, 50h
0x1800383b1  mov     rsi, [rdx+10h]
0x1800383b5  lea     rax, aOnecoreComNetf_60; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800383bc  mov     [rbp+var_30], rax
0x1800383c0  mov     r13d, 0C00000E5h
0x1800383c6  mov     [rbp+var_20], r13d
0x1800383ca  mov     rdi, rcx
0x1800383cd  test    rsi, rsi
0x1800383d0  jz      loc_1800385A6
0x1800383d6  mov     r15, [rdx+18h]
0x1800383da  test    r15, r15
0x1800383dd  jnz     short loc_1800383EB
0x1800383df  mov     [rbp+var_28], 7D6h
0x1800383e6  jmp     loc_180038648
0x1800383eb  add     rcx, 10h
0x1800383ef  lea     rdx, [rbp+arg_8]
0x1800383f3  mov     r8, rsi
0x1800383f6  call    ?EnlargeNoPreserve@?$CSmartArrayHolder@_KVCComponentStoreDependencyResolver@Resolver@Isolation@@V?$CDefaultObjectTraits@VCComponentStoreDependencyResolver@Resolver@Isolation@@VCCallDisposition@Nt@BCL@@@BCL@@V?$CDefaultArrayBufferTraits@_K@Nt@5@@Nt@BCL@@QEAA?AVCCallDisposition@23@_K@Z; BCL::Nt::CSmartArrayHolder<unsigned __int64,Isolation::Resolver::CComponentStoreDependencyResolver,BCL::CDefaultObjectTraits<Isolation::Resolver::CComponentStoreDependencyResolver,BCL::Nt::CCallDisposition>,BCL::Nt::CDefaultArrayBufferTraits<unsigned __int64>>::EnlargeNoPreserve(unsigned __int64)
0x1800383fb  mov     ebx, [rax]
0x1800383fd  test    ebx, ebx
0x1800383ff  js      loc_1800385A8
0x180038405  xor     r14d, r14d
0x180038408  test    rsi, rsi
0x18003840b  jz      loc_1800385A6
0x180038411  mov     r10, [r15+r14*8]
0x180038415  mov     [rbp+arg_8], 0
0x18003841d  mov     ecx, [r10+0Ch]
0x180038421  sub     ecx, 1
0x180038424  jz      loc_180038684
0x18003842a  sub     ecx, 1
0x18003842d  jz      short loc_180038461
0x18003842f  cmp     ecx, 1
0x180038432  jnz     loc_1800385E4
0x180038438  mov     rcx, [r10+10h]
0x18003843c  call    RtlIsComponentStoreHandleValid
0x180038441  test    al, al
0x180038443  jz      loc_1800385D8
0x180038449  mov     rcx, [r10+10h]
0x18003844d  lea     rdx, [rbp+arg_8]
0x180038451  call    RtlDuplicateComponentStoreHandle
0x180038456  xor     ebx, ebx
0x180038458  test    eax, eax
0x18003845a  cmovs   ebx, eax
0x18003845d  test    ebx, ebx
0x18003845f  jmp     short loc_18003847D
0x180038461  cmp     qword ptr [r10+10h], 0
0x180038466  jnz     loc_180038672
0x18003846c  lea     r8, [rbp+arg_8]
0x180038470  xor     edx, edx
0x180038472  xor     ecx, ecx
0x180038474  call    RtlCreateUserComponentStore
0x180038479  mov     ebx, eax
0x18003847b  test    eax, eax
0x18003847d  js      loc_18003869D
0x180038483  mov     r10, [rbp+arg_8]
0x180038487  mov     rcx, r10
0x18003848a  call    RtlIsComponentStoreHandleValid
0x18003848f  test    al, al
0x180038491  jz      loc_1800385ED
0x180038497  mov     r8, [rdi+8]
0x18003849b  lea     rbx, [rdi+18h]
0x18003849f  lea     rax, [r8+1]
0x1800384a3  mov     [rdi+8], rax
0x1800384a7  mov     r11, [rdi+20h]
0x1800384ab  cmp     [rdi+28h], r11
0x1800384af  jnb     short loc_1800384EF
0x1800384b1  mov     rdx, [rdi+28h]
0x1800384b5  mov     r9, r11
0x1800384b8  shl     rdx, 4
0x1800384bc  add     rdx, [rbx]
0x1800384bf  sub     r9, [rdi+28h]
0x1800384c3  jz      short loc_1800384EB
0x1800384c5  mov     rcx, rdx
0x1800384c8  lea     r10, ??_7CComponentStoreDependencyResolver@Resolver@Isolation@@6B@; const Isolation::Resolver::CComponentStoreDependencyResolver::`vftable'
0x1800384cf  mov     rax, rdx
0x1800384d2  add     rdx, 10h
0x1800384d6  mov     [rcx], r10
0x1800384d9  mov     qword ptr [rcx+8], 0
0x1800384e1  sub     r9, 1
0x1800384e5  jnz     short loc_1800384C5
0x1800384e7  mov     r10, [rbp+arg_8]
0x1800384eb  mov     [rdi+28h], r11
0x1800384ef  mov     rdx, [rbx]
0x1800384f2  lea     rax, aOnecoreComNetf_11; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800384f9  shl     r8, 4
0x1800384fd  add     r8, 8
0x180038501  mov     [rbp+var_8], r13d
0x180038505  add     rdx, r8
0x180038508  mov     [rbp+var_18], rax
0x18003850c  cmp     qword ptr [rdx], 0
0x180038510  jz      short loc_18003852B
0x180038512  mov     [rbp+var_10], 8Eh
0x180038519  lea     rdx, [rbp+var_18]
0x18003851d  lea     rcx, [rbp+var_18]
0x180038521  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180038526  mov     ebx, [rbp+var_8]
0x180038529  jmp     short loc_18003853A
0x18003852b  mov     rcx, r10
0x18003852e  call    RtlDuplicateComponentStoreHandle
0x180038533  xor     ebx, ebx
0x180038535  test    eax, eax
0x180038537  cmovs   ebx, eax
0x18003853a  mov     r10, [rbp+arg_8]
0x18003853e  test    ebx, ebx
0x180038540  js      loc_1800386A1
0x180038546  test    r10, r10
0x180038549  jz      short loc_18003859A
0x18003854b  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x180038552  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180038559  mov     [rbp+var_8], r13d
0x18003855d  mov     [rbp+var_18], rax
0x180038561  test    r11, r11
0x180038564  jz      short loc_1800385C3
0x180038566  mov     rdx, r11
0x180038569  mov     rcx, r10
0x18003856c  call    RtlIsTypeSafeHandleValid
0x180038571  test    al, al
0x180038573  jz      short loc_1800385C3
0x180038575  mov     ecx, [r11]
0x180038578  mov     rdx, r10
0x18003857b  mov     rax, [r11+20h]
0x18003857f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038584  xor     ecx, ecx; dwExceptionCode
0x180038586  test    ecx, ecx
0x180038588  jns     short loc_18003859A
0x18003858a  xor     r9d, r9d; lpArguments
0x18003858d  xor     r8d, r8d; nNumberOfArguments
0x180038590  lea     edx, [r9+1]; dwExceptionFlags
0x180038594  call    cs:__imp_RaiseException
0x18003859a  inc     r14
0x18003859d  cmp     r14, rsi
0x1800385a0  jb      loc_180038411
0x1800385a6  xor     ebx, ebx
0x1800385a8  lea     r11, [rsp+50h+var_s0]
0x1800385ad  mov     eax, ebx
0x1800385af  mov     rbx, [r11+30h]
0x1800385b3  mov     rsi, [r11+40h]
0x1800385b7  mov     rsp, r11
0x1800385ba  pop     r15
0x1800385bc  pop     r14
0x1800385be  pop     r13
0x1800385c0  pop     rdi
0x1800385c1  pop     rbp
0x1800385c2  retn
0x1800385c3  mov     [rbp+var_10], 124h
0x1800385ca  lea     rcx, [rbp+var_18]
0x1800385ce  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x1800385d3  mov     ecx, [rbp+var_8]
0x1800385d6  jmp     short loc_180038586
0x1800385d8  mov     [rbp+var_28], 7EFh
0x1800385df  jmp     loc_180038679
0x1800385e4  mov     [rbp+var_28], 7F4h
0x1800385eb  jmp     short loc_180038648
0x1800385ed  mov     [rbp+var_28], 7F7h
0x1800385f4  test    r10, r10
0x1800385f7  jz      short loc_180038648
0x1800385f9  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x180038600  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180038607  mov     [rbp+var_8], r13d
0x18003860b  mov     [rbp+var_18], rax
0x18003860f  test    r11, r11
0x180038612  jz      short loc_18003865D
0x180038614  mov     rdx, r11
0x180038617  mov     rcx, r10
0x18003861a  call    RtlIsTypeSafeHandleValid
0x18003861f  test    al, al
0x180038621  jz      short loc_18003865D
0x180038623  mov     ecx, [r11]
0x180038626  mov     rdx, r10
0x180038629  mov     rax, [r11+20h]
0x18003862d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038632  xor     ecx, ecx; dwExceptionCode
0x180038634  test    ecx, ecx
0x180038636  jns     short loc_180038648
0x180038638  xor     r9d, r9d; lpArguments
0x18003863b  xor     r8d, r8d; nNumberOfArguments
0x18003863e  lea     edx, [r9+1]; dwExceptionFlags
0x180038642  call    cs:__imp_RaiseException
0x180038648  lea     rdx, [rbp+var_30]
0x18003864c  lea     rcx, [rbp+var_30]
0x180038650  call    ?InternalErrorImmediateAction@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXAEBVCCallSite@34@@Z; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::InternalErrorImmediateAction(Windows::ErrorHandling::CCallSite const &)
0x180038655  mov     ebx, [rbp+var_20]
0x180038658  jmp     loc_1800385A8
0x18003865d  mov     [rbp+var_10], 124h
0x180038664  lea     rcx, [rbp+var_18]
0x180038668  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x18003866d  mov     ecx, [rbp+var_8]
0x180038670  jmp     short loc_180038634
0x180038672  mov     [rbp+var_28], 7EAh
0x180038679  lea     rcx, [rbp+var_30]
0x18003867d  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180038682  jmp     short loc_180038655
0x180038684  mov     ebx, 0C000042Ch
0x180038689  lea     rcx, aOnecoreComNetf_60; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x180038690  mov     r8d, ebx; int
0x180038693  mov     edx, 7E2h; char *
0x180038698  call    ?ReportNtErrorOrigination@COM@ErrorHandling@Windows@@YAXPEBDHJ@Z; Windows::ErrorHandling::COM::ReportNtErrorOrigination(char const *,int,long)
0x18003869d  mov     r10, [rbp+arg_8]
0x1800386a1  test    r10, r10
0x1800386a4  jz      loc_1800385A8
0x1800386aa  mov     r11, cs:?ms_ptti@?$CTsObjectTraits@U_COMPONENT_STORE@Rtl@Isolation@Windows@@VCComponentStore@@VCComponentStoreCD@@VCComponentStoreTraits@@@Rtl@Provider@TypeSafeHandle@Windows@@2PEAU_TSHANDLE_TYPE_DEFINITION_INIT@2345@EA; Windows::TypeSafeHandle::Provider::Rtl::_TSHANDLE_TYPE_DEFINITION_INIT * Windows::TypeSafeHandle::Provider::Rtl::CTsObjectTraits<Windows::Isolation::Rtl::_COMPONENT_STORE,CComponentStore,CComponentStoreCD,CComponentStoreTraits>::ms_ptti
0x1800386b1  lea     rax, aOnecoreComNetf_6; "onecore\\com\\netfx\\windowsbuilt\\iso_"...
0x1800386b8  mov     [rbp+var_18], rax
0x1800386bc  mov     [rbp+var_8], r13d
0x1800386c0  test    r11, r11
0x1800386c3  jz      short loc_180038702
0x1800386c5  mov     rdx, r11
0x1800386c8  mov     rcx, r10
0x1800386cb  call    RtlIsTypeSafeHandleValid
0x1800386d0  test    al, al
0x1800386d2  jz      short loc_180038702
0x1800386d4  mov     ecx, [r11]
0x1800386d7  mov     rdx, r10
0x1800386da  mov     rax, [r11+20h]
0x1800386de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800386e3  xor     ecx, ecx; dwExceptionCode
0x1800386e5  test    ecx, ecx
0x1800386e7  jns     loc_1800385A8
0x1800386ed  xor     r9d, r9d; lpArguments
0x1800386f0  xor     r8d, r8d; nNumberOfArguments
0x1800386f3  lea     edx, [r9+1]; dwExceptionFlags
0x1800386f7  call    cs:__imp_RaiseException
0x1800386fd  jmp     loc_1800385A8
0x180038702  mov     [rbp+var_10], 124h
0x180038709  lea     rcx, [rbp+var_18]
0x18003870d  call    ?SetInvalidParameter@?$CBaseFrame@VCVoidRaiseFrame@Nt@ErrorHandling@Windows@@@Nt@ErrorHandling@Windows@@IEAAXXZ; Windows::ErrorHandling::Nt::CBaseFrame<Windows::ErrorHandling::Nt::CVoidRaiseFrame>::SetInvalidParameter(void)
0x180038712  mov     ecx, [rbp+var_8]
0x180038715  jmp     short loc_1800386E5
```
