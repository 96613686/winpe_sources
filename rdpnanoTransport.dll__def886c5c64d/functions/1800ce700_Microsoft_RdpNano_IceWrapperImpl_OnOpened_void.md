# Microsoft::RdpNano::IceWrapperImpl::OnOpened(void)

- ea: `0x1800ce700`
- end: `0x1800cead2`
- name: `?OnOpened@IceWrapperImpl@RdpNano@Microsoft@@MEAAXXZ`
- size: `978`
- prototype: `void __fastcall(Microsoft::RdpNano::IceWrapperImpl *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015738`
- `0x180015bb8`
- `0x180018ea4`
- `0x18001902c`
- `0x18001ab4c`
- `0x180022c8c`
- `0x180028820`
- `0x1800386d0`
- `0x18004569c`
- `0x1800c5a90`
- `0x1800c96c8`
- `0x1800ce700`
- `0x1801b0ab4`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`

## string_xrefs

- `0x1800ce7bc`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800ceac0`: `C:\__w\1\s\rdpnanodll\icewrapper\icewrapperimpl.cpp`
- `0x1800ce7a8`: `Microsoft::RdpNano::IceWrapperImpl::OnOpened`
- `0x1800ce797`: `IceWrapper::OnOpened called multiple times or before we are ready for it. Closing Wrapper.\n    %s(%d): %s()`
- `0x1800ce8fa`: `ICE Wrapper: OnOpened called`
- `0x1800ce9d9`: `Microsoft::Basix::Dct.Smiles.LinkType`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Microsoft::RdpNano::IceWrapperImpl::OnOpened(Microsoft::RdpNano::IceWrapperImpl *this)
{
  int v2; // r9d
  volatile signed __int32 *v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rcx
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rbx
  unsigned int v9; // r14d
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 Property; // rax
  unsigned int v13; // ebx
  volatile signed __int32 *v14; // rbx
  int v15; // eax
  const char *v16; // [rsp+20h] [rbp-39h]
  __int128 v17; // [rsp+30h] [rbp-29h] BYREF
  __int128 v18; // [rsp+40h] [rbp-19h]
  _OWORD v19[2]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v20; // [rsp+70h] [rbp+17h] BYREF
  __int128 v21; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  LODWORD(v20) = 1;
  if ( !(unsigned __int8)std::_Atomic_storage<enum Microsoft::Basix::Pattern::IThreadedObject::State,4>::compare_exchange_strong(
                           (char *)this + 88,
                           &v20,
                           2) )
  {
    v20 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v20);
    if ( (_QWORD)v20 && *(_BYTE *)(v20 + 128) )
    {
      v17 = 0;
      v18 = 0;
      std::string::_Construct<1,char const *>(
        &v17,
        "IceWrapper::OnOpened called multiple times or before we are ready for it. Closing Wrapper.\n    %s(%d): %s()",
        (const char *)0x6B,
        v2,
        v16);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
        (unsigned int)&v20,
        (unsigned int)"RDPNANO",
        (unsigned int)&v17,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
        15,
        (__int64)"Microsoft::RdpNano::IceWrapperImpl::OnOpened");
      std::string::_Tidy_deallocate(&v17);
    }
    v3 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
    if ( *((_QWORD *)&v20 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v20 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
        if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
      }
    }
    v21 = 0;
    v4 = *((_QWORD *)this + 16);
    if ( v4 )
      _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
    v5 = *((_QWORD *)this + 15);
    *(_QWORD *)&v21 = v5;
    v6 = (volatile signed __int32 *)*((_QWORD *)this + 16);
    *((_QWORD *)&v21 + 1) = v6;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
    v7 = *((_QWORD *)this + 12);
    if ( v7 )
      (*(void (__fastcall **)(__int64, char *, __int64, _QWORD))(*(_QWORD *)v7 + 16LL))(
        v7,
        (char *)this - 8,
        2147549183LL,
        0);
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
  }
  v20 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v20);
  if ( (_QWORD)v20 && *(_BYTE *)(v20 + 128) )
  {
    v17 = 0;
    v18 = 0;
    std::string::_Construct<1,char const *>(&v17, "ICE Wrapper: OnOpened called", 28);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(&v20, "RDPNANO", &v17);
    std::string::_Tidy_deallocate(&v17);
  }
  v8 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
  if ( *((_QWORD *)&v20 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v20 + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( !_InterlockedDecrement(v8 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  if ( !*((_BYTE *)this + 257) )
  {
    *(_QWORD *)&v20 = 50;
    std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v20);
  }
  if ( *((_QWORD *)this + 12) )
  {
    v9 = 0;
    v10 = *((_QWORD *)this + 17);
    if ( v10 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v10 + 8LL))(v10, &v21);
      v11 = v21;
      if ( (_QWORD)v21 )
      {
        memset(v19, 0, sizeof(v19));
        std::string::_Construct<1,char const *>(v19, "Microsoft::Basix::Dct.Smiles.LinkType", 37);
        Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v11 + 40, &v17, v19);
        LODWORD(v20) = 0;
        v13 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<enum Microsoft::Basix::Dct::ISmiles::LinkType>(
                *(_QWORD *)(Property + 16),
                &v20);
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v17);
        std::string::_Tidy_deallocate(v19);
        v9 = Microsoft::RdpNano::IceWrapperImpl::ConvertSmilesLinkTypeToNanoLinkType((char *)this - 8, v13);
      }
      v14 = (volatile signed __int32 *)*((_QWORD *)&v21 + 1);
      if ( *((_QWORD *)&v21 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v21 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
    }
    v15 = (***((__int64 (__fastcall ****)(_QWORD, char *, _QWORD))this + 12))(
            *((_QWORD *)this + 12),
            (char *)this - 8,
            v9);
    if ( v15 < 0 )
    {
      _mm_lfence();
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x432,
        (unsigned int)"C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\icewrapperimpl.cpp",
        (const char *)(unsigned int)v15,
        (int)v16);
    }
  }
}

```

## disassembly

```asm
0x1800ce700  mov     rax, rsp
0x1800ce703  mov     [rax+10h], rbx
0x1800ce707  mov     [rax+18h], rsi
0x1800ce70b  mov     [rax+20h], rdi
0x1800ce70f  push    rbp
0x1800ce710  push    r12
0x1800ce712  push    r14
0x1800ce714  lea     rbp, [rax-5Fh]
0x1800ce718  mov     eax, 0A0h
0x1800ce71d  call    _alloca_probe
0x1800ce722  sub     rsp, rax
0x1800ce725  mov     rax, cs:__security_cookie
0x1800ce72c  xor     rax, rsp
0x1800ce72f  mov     [rbp+57h+var_20], rax
0x1800ce733  mov     rdi, rcx
0x1800ce736  mov     dword ptr [rbp+57h+var_40], 1
0x1800ce73d  add     rcx, 58h ; 'X'
0x1800ce741  mov     r9d, 5
0x1800ce747  lea     r8d, [r9-3]
0x1800ce74b  lea     rdx, [rbp+57h+var_40]
0x1800ce74f  call    ?compare_exchange_strong@?$_Atomic_storage@W4State@IThreadedObject@Pattern@Basix@Microsoft@@$03@std@@QEAA_NAEAW4State@IThreadedObject@Pattern@Basix@Microsoft@@W434567@W4memory_order@2@@Z; std::_Atomic_storage<Microsoft::Basix::Pattern::IThreadedObject::State,4>::compare_exchange_strong(Microsoft::Basix::Pattern::IThreadedObject::State &,Microsoft::Basix::Pattern::IThreadedObject::State,std::memory_order)
0x1800ce754  or      r12d, 0FFFFFFFFh
0x1800ce758  test    al, al
0x1800ce75a  jnz     loc_1800CE8C2
0x1800ce760  xorps   xmm0, xmm0
0x1800ce763  movups  [rbp+57h+var_40], xmm0
0x1800ce767  lea     rcx, [rbp+57h+var_40]
0x1800ce76b  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1800ce770  nop
0x1800ce771  mov     rax, qword ptr [rbp+57h+var_40]
0x1800ce775  test    rax, rax
0x1800ce778  jz      short loc_1800CE7E2
0x1800ce77a  cmp     byte ptr [rax+80h], 0
0x1800ce781  jz      short loc_1800CE7E2
0x1800ce783  xorps   xmm0, xmm0
0x1800ce786  movups  [rbp+57h+var_80], xmm0
0x1800ce78a  xorps   xmm1, xmm1
0x1800ce78d  movdqu  [rbp+57h+var_70], xmm1
0x1800ce792  lea     r8d, [r12+6Ch]
0x1800ce797  lea     rdx, aIcewrapperOnop; "IceWrapper::OnOpened called multiple ti"...
0x1800ce79e  lea     rcx, [rbp+57h+var_80]
0x1800ce7a2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800ce7a7  nop
0x1800ce7a8  lea     rax, aMicrosoftRdpna_23; "Microsoft::RdpNano::IceWrapperImpl::OnO"...
0x1800ce7af  mov     [rsp+0B0h+var_88], rax
0x1800ce7b4  mov     [rsp+0B0h+var_90], 40Fh; int
0x1800ce7bc  lea     r9, aCW1SRdpnanodll_12; "C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\"...
0x1800ce7c3  lea     r8, [rbp+57h+var_80]
0x1800ce7c7  lea     rdx, aRdpnano; "RDPNANO"
0x1800ce7ce  lea     rcx, [rbp+57h+var_40]
0x1800ce7d2  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x1800ce7d7  nop
0x1800ce7d8  lea     rcx, [rbp+57h+var_80]
0x1800ce7dc  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800ce7e1  nop
0x1800ce7e2  mov     rbx, qword ptr [rbp+57h+var_40+8]
0x1800ce7e6  test    rbx, rbx
0x1800ce7e9  jz      short loc_1800CE824
0x1800ce7eb  mov     eax, r12d
0x1800ce7ee  lock xadd [rbx+8], eax
0x1800ce7f3  add     eax, r12d
0x1800ce7f6  jnz     short loc_1800CE824
0x1800ce7f8  mov     rax, [rbx]
0x1800ce7fb  mov     rcx, rbx
0x1800ce7fe  mov     rax, [rax]
0x1800ce801  call    cs:__guard_dispatch_icall_fptr
0x1800ce807  mov     eax, r12d
0x1800ce80a  lock xadd [rbx+0Ch], eax
0x1800ce80f  add     eax, r12d
0x1800ce812  jnz     short loc_1800CE824
0x1800ce814  mov     rax, [rbx]
0x1800ce817  mov     rcx, rbx
0x1800ce81a  mov     rax, [rax+8]
0x1800ce81e  call    cs:__guard_dispatch_icall_fptr
0x1800ce824  xorps   xmm0, xmm0
0x1800ce827  movups  [rbp+57h+var_30], xmm0
0x1800ce82b  mov     rax, [rdi+80h]
0x1800ce832  test    rax, rax
0x1800ce835  jz      short loc_1800CE83B
0x1800ce837  lock inc dword ptr [rax+8]
0x1800ce83b  mov     rcx, [rdi+78h]
0x1800ce83f  mov     qword ptr [rbp+57h+var_30], rcx
0x1800ce843  mov     rbx, [rdi+80h]
0x1800ce84a  mov     qword ptr [rbp+57h+var_30+8], rbx
0x1800ce84e  test    rcx, rcx
0x1800ce851  jz      short loc_1800CE860
0x1800ce853  mov     rax, [rcx]
0x1800ce856  mov     rax, [rax+18h]
0x1800ce85a  call    cs:__guard_dispatch_icall_fptr
0x1800ce860  mov     rcx, [rdi+60h]
0x1800ce864  test    rcx, rcx
0x1800ce867  jz      short loc_1800CE884
0x1800ce869  mov     rax, [rcx]
0x1800ce86c  xor     r9d, r9d
0x1800ce86f  mov     r8d, 8000FFFFh
0x1800ce875  lea     rdx, [rdi-8]
0x1800ce879  mov     rax, [rax+10h]
0x1800ce87d  call    cs:__guard_dispatch_icall_fptr
0x1800ce883  nop
0x1800ce884  test    rbx, rbx
0x1800ce887  jz      short loc_1800CE8C2
0x1800ce889  mov     eax, r12d
0x1800ce88c  lock xadd [rbx+8], eax
0x1800ce891  add     eax, r12d
0x1800ce894  jnz     short loc_1800CE8C2
0x1800ce896  mov     rax, [rbx]
0x1800ce899  mov     rcx, rbx
0x1800ce89c  mov     rax, [rax]
0x1800ce89f  call    cs:__guard_dispatch_icall_fptr
0x1800ce8a5  mov     eax, r12d
0x1800ce8a8  lock xadd [rbx+0Ch], eax
0x1800ce8ad  add     eax, r12d
0x1800ce8b0  jnz     short loc_1800CE8C2
0x1800ce8b2  mov     rax, [rbx]
0x1800ce8b5  mov     rcx, rbx
0x1800ce8b8  mov     rax, [rax+8]
0x1800ce8bc  call    cs:__guard_dispatch_icall_fptr
0x1800ce8c2  xorps   xmm0, xmm0
0x1800ce8c5  movups  [rbp+57h+var_40], xmm0
0x1800ce8c9  lea     rcx, [rbp+57h+var_40]
0x1800ce8cd  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1800ce8d2  nop
0x1800ce8d3  mov     rax, qword ptr [rbp+57h+var_40]
0x1800ce8d7  test    rax, rax
0x1800ce8da  jz      short loc_1800CE92A
0x1800ce8dc  cmp     byte ptr [rax+80h], 0
0x1800ce8e3  jz      short loc_1800CE92A
0x1800ce8e5  xorps   xmm0, xmm0
0x1800ce8e8  movups  [rbp+57h+var_80], xmm0
0x1800ce8ec  xorps   xmm1, xmm1
0x1800ce8ef  movdqu  [rbp+57h+var_70], xmm1
0x1800ce8f4  mov     r8d, 1Ch
0x1800ce8fa  lea     rdx, aIceWrapperOnop; "ICE Wrapper: OnOpened called"
0x1800ce901  lea     rcx, [rbp+57h+var_80]
0x1800ce905  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800ce90a  nop
0x1800ce90b  lea     r8, [rbp+57h+var_80]
0x1800ce90f  lea     rdx, aRdpnano; "RDPNANO"
0x1800ce916  lea     rcx, [rbp+57h+var_40]
0x1800ce91a  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x1800ce91f  nop
0x1800ce920  lea     rcx, [rbp+57h+var_80]
0x1800ce924  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800ce929  nop
0x1800ce92a  mov     rbx, qword ptr [rbp+57h+var_40+8]
0x1800ce92e  test    rbx, rbx
0x1800ce931  jz      short loc_1800CE96C
0x1800ce933  mov     eax, r12d
0x1800ce936  lock xadd [rbx+8], eax
0x1800ce93b  add     eax, r12d
0x1800ce93e  jnz     short loc_1800CE96C
0x1800ce940  mov     rax, [rbx]
0x1800ce943  mov     rcx, rbx
0x1800ce946  mov     rax, [rax]
0x1800ce949  call    cs:__guard_dispatch_icall_fptr
0x1800ce94f  mov     eax, r12d
0x1800ce952  lock xadd [rbx+0Ch], eax
0x1800ce957  add     eax, r12d
0x1800ce95a  jnz     short loc_1800CE96C
0x1800ce95c  mov     rax, [rbx]
0x1800ce95f  mov     rcx, rbx
0x1800ce962  mov     rax, [rax+8]
0x1800ce966  call    cs:__guard_dispatch_icall_fptr
0x1800ce96c  cmp     byte ptr [rdi+101h], 0
0x1800ce973  jnz     short loc_1800CE986
0x1800ce975  mov     qword ptr [rbp+57h+var_40], 32h ; '2'
0x1800ce97d  lea     rcx, [rbp+57h+var_40]
0x1800ce981  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1800ce986  cmp     qword ptr [rdi+60h], 0
0x1800ce98b  jz      loc_1800CEA8D
0x1800ce991  xor     r14d, r14d
0x1800ce994  mov     rcx, [rdi+88h]
0x1800ce99b  test    rcx, rcx
0x1800ce99e  jz      loc_1800CEA72
0x1800ce9a4  xorps   xmm0, xmm0
0x1800ce9a7  movups  [rbp+57h+var_30], xmm0
0x1800ce9ab  mov     rax, [rcx]
0x1800ce9ae  lea     rdx, [rbp+57h+var_30]
0x1800ce9b2  mov     rax, [rax+8]
0x1800ce9b6  call    cs:__guard_dispatch_icall_fptr
0x1800ce9bc  nop
0x1800ce9bd  mov     rbx, qword ptr [rbp+57h+var_30]
0x1800ce9c1  test    rbx, rbx
0x1800ce9c4  jz      short loc_1800CEA30
0x1800ce9c6  xorps   xmm0, xmm0
0x1800ce9c9  movups  [rbp+57h+var_60], xmm0
0x1800ce9cd  xorps   xmm1, xmm1
0x1800ce9d0  movdqu  [rbp+57h+var_50], xmm1
0x1800ce9d5  lea     r8d, [r14+25h]
0x1800ce9d9  lea     rdx, aMicrosoftBasix_102; "Microsoft::Basix::Dct.Smiles.LinkType"
0x1800ce9e0  lea     rcx, [rbp+57h+var_60]
0x1800ce9e4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800ce9e9  nop
0x1800ce9ea  lea     r8, [rbp+57h+var_60]
0x1800ce9ee  lea     rdx, [rbp+57h+var_80]
0x1800ce9f2  lea     rcx, [rbx+28h]
0x1800ce9f6  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x1800ce9fb  nop
0x1800ce9fc  mov     dword ptr [rbp+57h+var_40], r14d
0x1800cea00  lea     rdx, [rbp+57h+var_40]
0x1800cea04  mov     rcx, [rax+10h]
0x1800cea08  call    ??$get_value@W4LinkType@ISmiles@Dct@Basix@Microsoft@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AW4LinkType@ISmiles@Dct@Basix@Microsoft@@AEBW434567@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Dct::ISmiles::LinkType>(Microsoft::Basix::Dct::ISmiles::LinkType const &)
0x1800cea0d  mov     ebx, eax
0x1800cea0f  lea     rcx, [rbp+57h+var_80]
0x1800cea13  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1800cea18  nop
0x1800cea19  lea     rcx, [rbp+57h+var_60]
0x1800cea1d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800cea22  mov     edx, ebx
0x1800cea24  lea     rcx, [rdi-8]
0x1800cea28  call    ?ConvertSmilesLinkTypeToNanoLinkType@IceWrapperImpl@RdpNano@Microsoft@@IEAAIW4LinkType@ISmiles@Dct@Basix@3@@Z; Microsoft::RdpNano::IceWrapperImpl::ConvertSmilesLinkTypeToNanoLinkType(Microsoft::Basix::Dct::ISmiles::LinkType)
0x1800cea2d  mov     r14d, eax
0x1800cea30  mov     rbx, qword ptr [rbp+57h+var_30+8]
0x1800cea34  test    rbx, rbx
0x1800cea37  jz      short loc_1800CEA72
0x1800cea39  mov     ecx, r12d
0x1800cea3c  lock xadd [rbx+8], ecx
0x1800cea41  add     ecx, r12d
0x1800cea44  jnz     short loc_1800CEA72
0x1800cea46  mov     rax, [rbx]
0x1800cea49  mov     rcx, rbx
0x1800cea4c  mov     rax, [rax]
0x1800cea4f  call    cs:__guard_dispatch_icall_fptr
0x1800cea55  mov     eax, r12d
0x1800cea58  lock xadd [rbx+0Ch], eax
0x1800cea5d  add     eax, r12d
0x1800cea60  jnz     short loc_1800CEA72
0x1800cea62  mov     rax, [rbx]
0x1800cea65  mov     rcx, rbx
0x1800cea68  mov     rax, [rax+8]
0x1800cea6c  call    cs:__guard_dispatch_icall_fptr
0x1800cea72  mov     rcx, [rdi+60h]
0x1800cea76  mov     rax, [rcx]
0x1800cea79  mov     r8d, r14d
0x1800cea7c  lea     rdx, [rdi-8]
0x1800cea80  mov     rax, [rax]
0x1800cea83  call    cs:__guard_dispatch_icall_fptr
0x1800cea89  test    eax, eax
0x1800cea8b  js      short loc_1800CEAB6
0x1800cea8d  mov     rcx, [rbp+57h+var_20]
0x1800cea91  xor     rcx, rsp; StackCookie
0x1800cea94  call    __security_check_cookie
0x1800cea99  lea     r11, [rsp+0B0h+var_10]
0x1800ceaa1  mov     rbx, [r11+28h]
0x1800ceaa5  mov     rsi, [r11+30h]
0x1800ceaa9  mov     rdi, [r11+38h]
0x1800ceaad  mov     rsp, r11
0x1800ceab0  pop     r14
0x1800ceab2  pop     r12
0x1800ceab4  pop     rbp
0x1800ceab5  retn
0x1800ceab6  lfence
0x1800ceab9  mov     rcx, [rbp+5Fh]; this
0x1800ceabd  mov     r9d, eax; char *
0x1800ceac0  lea     r8, aCW1SRdpnanodll_12; "C:\\__w\\1\\s\\rdpnanodll\\icewrapper\\"...
0x1800ceac7  mov     edx, 432h; void *
0x1800ceacc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
