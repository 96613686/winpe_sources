# EudcFontCollectionLoader::Monitor(DateTime const &,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1801267cc`
- end: `0x180126aef`
- name: `?Monitor@EudcFontCollectionLoader@@CAXAEBVDateTime@@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `803`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1801274b4`

## callees

- `0x18011ef30`
- `0x18012376c`
- `0x180126540`
- `0x1801265d0`
- `0x1801267cc`
- `0x180126af8`
- `0x180127350`
- `0x18012e628`
- `0x180158480`
- `0x1801644d0`
- `0x1801edee0`
- `0x1801ee1b0`
- `0x1801ee584`
- `0x1801ef8d4`
- `0x1801efaac`
- `0x1801fb714`
- `0x1801fb7bc`
- `0x1802067e8`
- `0x180207afc`
- `0x18020a7ac`
- `0x180212490`
- `0x18021deb8`
- `0x18022aca0`
- `0x18022e3e8`
- `0x18022e430`
- `0x18022e4b8`
- `0x18022e54c`
- `0x180330010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180126928`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180126928`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18012682a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18012682a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180126a63`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180126a63`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1801269e9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1801269e9`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall EudcFontCollectionLoader::Monitor(__int64 a1, __int64 a2)
{
  int v3; // r14d
  LPCRITICAL_SECTION v4; // rdi
  signed __int64 v5; // rax
  EudcFontCollectionLoader::ChangeMonitor *v6; // rbx
  struct DWrite::RefString::Data *v7; // rax
  const void *v8; // rdx
  __int64 v9; // rax
  EudcFontCollectionLoader::Enumerator *v10; // rsi
  char v11; // bl
  struct DWrite::RefString::Data *v12; // rbx
  wchar_t *v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rax
  __int128 v19; // xmm6
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rbx
  int v24; // [rsp+38h] [rbp-69h] BYREF
  struct DWrite::RefString::Data *v25; // [rsp+40h] [rbp-61h] BYREF
  __int64 v26; // [rsp+48h] [rbp-59h] BYREF
  __int64 v27; // [rsp+50h] [rbp-51h]
  int v28; // [rsp+58h] [rbp-49h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-41h] BYREF
  _OWORD v30[2]; // [rsp+68h] [rbp-39h] BYREF
  __int64 v31; // [rsp+88h] [rbp-19h]
  _BYTE v32[16]; // [rsp+90h] [rbp-11h] BYREF
  __int128 v33; // [rsp+A0h] [rbp-1h] BYREF
  __int64 v34; // [rsp+B0h] [rbp+Fh]
  __int64 v35; // [rsp+B8h] [rbp+17h]

  v3 = 0;
  v24 = 0;
  v4 = EudcFontCollectionLoader::changeMonitor_;
  if ( !EudcFontCollectionLoader::changeMonitor_ )
  {
    v4 = (LPCRITICAL_SECTION)operator new(0x68u);
    v25 = (struct DWrite::RefString::Data *)v4;
    InitializeCriticalSection(v4);
    v4[1].DebugInfo = 0;
    *(_QWORD *)&v4[1].LockCount = 0;
    ManualResetEvent::ManualResetEvent((ManualResetEvent *)&v4[1].OwningThread, 0);
    std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(&v4[1].LockSemaphore);
    *(_QWORD *)&v4[2].LockCount = 0;
    v5 = _InterlockedCompareExchange64(
           (volatile signed __int64 *)&EudcFontCollectionLoader::changeMonitor_,
           (signed __int64)v4,
           0);
    if ( v5 )
    {
      v6 = (EudcFontCollectionLoader::ChangeMonitor *)v4;
      v4 = (LPCRITICAL_SECTION)v5;
      if ( v6 )
      {
        EudcFontCollectionLoader::ChangeMonitor::~ChangeMonitor(v6);
        RefCountedArrayImpl::Data::operator delete(v6);
      }
    }
  }
  v26 = 0;
  v27 = 0;
  std::_Tree<std::_Tmap_traits<void *,std::vector<unsigned char>,std::less<void *>,std::allocator<std::pair<void * const,std::vector<unsigned char>>>,0>>::_Alloc_sentinel_and_proxy(&v26);
  v7 = (struct DWrite::RefString::Data *)operator new(0x58u);
  v25 = v7;
  v8 = *(const void **)a2;
  if ( *(_QWORD *)a2 == *(_QWORD *)(a2 + 8) )
    v8 = 0;
  v9 = EudcFontCollectionLoader::Enumerator::Enumerator(v7, v8, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2);
  v10 = (EudcFontCollectionLoader::Enumerator *)v9;
  v31 = v9;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  v28 = 0;
  while ( 1 )
  {
    v24 = _mm_getcsr();
    if ( (int)EudcFontCollectionLoader::Enumerator::MoveNext(v10, &v28) < 0 || (v11 = 1, !v28) )
      v11 = 0;
    FPUStateSandboxSSE::~FPUStateSandboxSSE((FPUStateSandboxSSE *)&v24);
    if ( !v11 )
      break;
    v3 &= ~1u;
    EudcFontCollectionLoader::Enumerator::GetCurrentEudcFileName(v10, &v25);
    v12 = v25;
    v13 = wcsrchr((const wchar_t *)v25 + 4, 0x5Cu);
    if ( v13 )
    {
      v14 = std::wstring::wstring(&v33, (char *)v12 + 8, v13 + 1);
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
        &v26,
        v30,
        v14);
      std::wstring::_Tidy_deallocate(&v33);
    }
    DWrite::RefString::DecrementRef(v25);
  }
  v15 = *(_QWORD *)GetFontsDirectory(&v25) + 8LL;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v16 = std::_WChar_traits<wchar_t>::length(v15);
  std::wstring::_Construct<1,wchar_t const *>(&v33, v17, v16);
  v18 = std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
          &v26,
          v30,
          &v33);
  v19 = *(_OWORD *)v18;
  v20 = *(_QWORD *)(v18 + 16);
  if ( *(_BYTE *)(v20 + 25) || (unsigned __int8)std::operator<<wchar_t>(&v33, v20 + 32) )
  {
    if ( v27 == 0x3FFFFFFFFFFFFFFLL )
      std::_Xlength_error("map/set too long");
    v21 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>(
            v32,
            &v26,
            v26,
            &v33);
    v22 = *(_QWORD *)(v21 + 8);
    *(_QWORD *)(v21 + 8) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>(v32);
    v30[0] = v19;
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned short const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>>>::_Insert_node(
      &v26,
      v30,
      v22);
  }
  std::wstring::_Tidy_deallocate(&v33);
  DWrite::RefString::DecrementRef(v25);
  phkResult = 0;
  if ( RegOpenKeyExW(HKEY_CURRENT_USER, L"EUDC", 0, 0x10u, &phkResult) )
    phkResult = 0;
  EudcFontCollectionLoader::ChangeMonitor::Monitor((EudcFontCollectionLoader::ChangeMonitor *)v4);
  if ( v10 )
    (*(void (__fastcall **)(EudcFontCollectionLoader::Enumerator *))(*(_QWORD *)v10 + 16LL))(v10);
  std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring,void *>>>(
    &v26,
    &v26,
    *(_QWORD *)(v26 + 8));
  return std::_Deallocate<16>(v26, 64);
}

```

## disassembly

```asm
0x1801267cc  mov     rax, rsp
0x1801267cf  mov     [rax+8], rbx
0x1801267d3  mov     [rax+18h], rsi
0x1801267d7  push    rbp
0x1801267d8  push    rdi
0x1801267d9  push    r12
0x1801267db  push    r14
0x1801267dd  push    r15
0x1801267df  lea     rbp, [rax-5Fh]
0x1801267e3  sub     rsp, 0D0h
0x1801267ea  movaps  xmmword ptr [rax-38h], xmm6
0x1801267ee  mov     rax, cs:__security_cookie
0x1801267f5  xor     rax, rsp
0x1801267f8  mov     [rbp+57h+var_38], rax
0x1801267fc  mov     rsi, rdx
0x1801267ff  mov     r15, rcx
0x180126802  xor     r12d, r12d
0x180126805  mov     r14d, r12d
0x180126808  mov     [rbp+57h+var_C0], r12d
0x18012680c  mov     rdi, cs:?changeMonitor_@EudcFontCollectionLoader@@0V?$ScopedPtr@VChangeMonitor@EudcFontCollectionLoader@@@@A; ScopedPtr<EudcFontCollectionLoader::ChangeMonitor> EudcFontCollectionLoader::changeMonitor_
0x180126813  test    rdi, rdi
0x180126816  jnz     short loc_18012687E
0x180126818  lea     ecx, [rdi+68h]; Size
0x18012681b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180126820  mov     rdi, rax
0x180126823  mov     [rbp+57h+var_B8], rax
0x180126827  mov     rcx, rax; lpCriticalSection
0x18012682a  call    cs:__imp_InitializeCriticalSection
0x180126830  nop
0x180126831  mov     [rdi+28h], r12
0x180126835  mov     [rdi+30h], r12
0x180126839  lea     rcx, [rdi+38h]; this
0x18012683d  xor     edx, edx; bool
0x18012683f  call    ??0ManualResetEvent@@QEAA@_N@Z; ManualResetEvent::ManualResetEvent(bool)
0x180126844  lea     rcx, [rdi+40h]; void *
0x180126848  call    ??0?$vector@V?$KeyValuePair@HVOpenTypeName@@@@V?$allocator@V?$KeyValuePair@HVOpenTypeName@@@@@std@@@std@@QEAA@XZ; std::vector<KeyValuePair<int,OpenTypeName>>::vector<KeyValuePair<int,OpenTypeName>>(void)
0x18012684d  mov     [rdi+58h], r12
0x180126851  xor     eax, eax
0x180126853  lock cmpxchg cs:?changeMonitor_@EudcFontCollectionLoader@@0V?$ScopedPtr@VChangeMonitor@EudcFontCollectionLoader@@@@A, rdi; ScopedPtr<EudcFontCollectionLoader::ChangeMonitor> EudcFontCollectionLoader::changeMonitor_
0x18012685c  jz      short loc_18012687E
0x18012685e  mov     rbx, rdi
0x180126861  mov     rdi, rax
0x180126864  test    rbx, rbx
0x180126867  jz      short loc_18012687E
0x180126869  mov     rcx, rbx; this
0x18012686c  call    ??1ChangeMonitor@EudcFontCollectionLoader@@QEAA@XZ; EudcFontCollectionLoader::ChangeMonitor::~ChangeMonitor(void)
0x180126871  lea     edx, [r12+68h]
0x180126876  mov     rcx, rbx; Block
0x180126879  call    ??3Data@RefCountedArrayImpl@@SAXPEAX_K@Z; RefCountedArrayImpl::Data::operator delete(void *,unsigned __int64)
0x18012687e  mov     [rbp+57h+var_B0], r12
0x180126882  mov     [rbp+57h+var_A8], r12
0x180126886  lea     rcx, [rbp+57h+var_B0]
0x18012688a  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@PEAXV?$vector@EV?$allocator@E@std@@@std@@U?$less@PEAX@2@V?$allocator@U?$pair@QEAXV?$vector@EV?$allocator@E@std@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<void *,std::vector<uchar>,std::less<void *>,std::allocator<std::pair<void * const,std::vector<uchar>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18012688f  nop
0x180126890  mov     ecx, 58h ; 'X'; Size
0x180126895  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18012689a  mov     [rbp+57h+var_B8], rax
0x18012689e  mov     r8d, [rsi+8]
0x1801268a2  sub     r8d, [rsi]; unsigned int
0x1801268a5  mov     rdx, [rsi]
0x1801268a8  cmp     rdx, [rsi+8]
0x1801268ac  cmovz   rdx, r12; void *
0x1801268b0  mov     rcx, rax; this
0x1801268b3  call    ??0Enumerator@EudcFontCollectionLoader@@QEAA@PEBXI@Z; EudcFontCollectionLoader::Enumerator::Enumerator(void const *,uint)
0x1801268b8  mov     rsi, rax
0x1801268bb  mov     [rbp+57h+var_70], rax
0x1801268bf  test    rax, rax
0x1801268c2  jz      short loc_1801268D4
0x1801268c4  mov     rcx, [rax]
0x1801268c7  mov     rax, [rcx+8]
0x1801268cb  mov     rcx, rsi
0x1801268ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801268d3  nop
0x1801268d4  mov     [rbp+57h+var_A0], r12d
0x1801268d8  stmxcsr [rbp+57h+var_C0]
0x1801268dc  mov     eax, [rbp+57h+var_C0]
0x1801268df  mov     [rbp+57h+var_C0], eax
0x1801268e2  lea     rdx, [rbp+57h+var_A0]; int *
0x1801268e6  mov     rcx, rsi; this
0x1801268e9  call    ?MoveNext@Enumerator@EudcFontCollectionLoader@@UEAAJPEAH@Z; EudcFontCollectionLoader::Enumerator::MoveNext(int *)
0x1801268ee  test    eax, eax
0x1801268f0  js      short loc_1801268FA
0x1801268f2  cmp     [rbp+57h+var_A0], r12d
0x1801268f6  mov     bl, 1
0x1801268f8  jnz     short loc_1801268FD
0x1801268fa  mov     bl, r12b
0x1801268fd  lea     rcx, [rbp+57h+var_C0]; this
0x180126901  call    ??1FPUStateSandboxSSE@@QEAA@XZ; FPUStateSandboxSSE::~FPUStateSandboxSSE(void)
0x180126906  test    bl, bl
0x180126908  jz      short loc_18012696E
0x18012690a  and     r14d, 0FFFFFFFEh
0x18012690e  lea     rdx, [rbp+57h+var_B8]
0x180126912  mov     rcx, rsi
0x180126915  call    ?GetCurrentEudcFileName@Enumerator@EudcFontCollectionLoader@@QEAA?AVRefString@DWrite@@XZ; EudcFontCollectionLoader::Enumerator::GetCurrentEudcFileName(void)
0x18012691a  nop
0x18012691b  mov     rbx, [rbp+57h+var_B8]
0x18012691f  mov     edx, 5Ch ; '\'; Ch
0x180126924  lea     rcx, [rbx+8]; Str
0x180126928  call    cs:__imp_wcsrchr
0x18012692e  test    rax, rax
0x180126931  jz      short loc_180126960
0x180126933  lea     r8, [rax+2]
0x180126937  lea     rdx, [rbx+8]
0x18012693b  lea     rcx, [rbp+57h+var_58]
0x18012693f  call    ??$?0PEB_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t const *,wchar_t const *,std::allocator<wchar_t> const &)
0x180126944  nop
0x180126945  mov     r8, rax
0x180126948  lea     rdx, [rbp+57h+var_90]
0x18012694c  lea     rcx, [rbp+57h+var_B0]
0x180126950  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180126955  nop
0x180126956  lea     rcx, [rbp+57h+var_58]
0x18012695a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18012695f  nop
0x180126960  mov     rcx, [rbp+57h+var_B8]; struct DWrite::RefString::Data *
0x180126964  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180126969  jmp     loc_1801268D8
0x18012696e  lea     rcx, [rbp+57h+var_B8]
0x180126972  call    ?GetFontsDirectory@@YA?AVRefString@DWrite@@XZ; GetFontsDirectory(void)
0x180126977  nop
0x180126978  mov     rcx, [rax]
0x18012697b  add     rcx, 8
0x18012697f  xorps   xmm0, xmm0
0x180126982  movups  [rbp+57h+var_58], xmm0
0x180126986  mov     [rbp+57h+var_48], r12
0x18012698a  mov     [rbp+57h+var_40], r12
0x18012698e  call    ?length@?$_WChar_traits@_W@std@@SA_KPEB_W@Z; std::_WChar_traits<wchar_t>::length(wchar_t const *)
0x180126993  mov     r8, rax
0x180126996  mov     rdx, rcx
0x180126999  lea     rcx, [rbp+57h+var_58]
0x18012699d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1801269a2  nop
0x1801269a3  lea     r8, [rbp+57h+var_58]
0x1801269a7  lea     rdx, [rbp+57h+var_90]
0x1801269ab  lea     rcx, [rbp+57h+var_B0]
0x1801269af  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x1801269b4  movups  xmm6, xmmword ptr [rax]
0x1801269b7  mov     rdx, [rax+10h]
0x1801269bb  cmp     [rdx+19h], r12b
0x1801269bf  jnz     short loc_1801269D2
0x1801269c1  add     rdx, 20h ; ' '
0x1801269c5  lea     rcx, [rbp+57h+var_58]
0x1801269c9  call    ??$?M_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator<<wchar_t>(std::wstring const &,std::wstring const &)
0x1801269ce  test    al, al
0x1801269d0  jz      short loc_180126A2C
0x1801269d2  mov     rax, 3FFFFFFFFFFFFFFh
0x1801269dc  cmp     [rbp+57h+var_A8], rax
0x1801269e0  jnz     short loc_1801269F0
0x1801269e2  lea     rcx, aMapSetTooLong; "map/set too long"
0x1801269e9  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1801269f0  lea     r9, [rbp+57h+var_58]
0x1801269f4  mov     r8, [rbp+57h+var_B0]
0x1801269f8  lea     rdx, [rbp+57h+var_B0]
0x1801269fc  lea     rcx, [rbp+57h+var_68]
0x180126a00  call    ??$?0V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@1@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &,std::_Tree_node<std::wstring,void *> *,std::wstring &&)
0x180126a05  mov     rbx, [rax+8]
0x180126a09  mov     [rax+8], r12
0x180126a0d  lea     rcx, [rbp+57h+var_68]
0x180126a11  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::wstring,void *>>>(void)
0x180126a16  movdqu  [rbp+57h+var_90], xmm6
0x180126a1b  mov     r8, rbx
0x180126a1e  lea     rdx, [rbp+57h+var_90]
0x180126a22  lea     rcx, [rbp+57h+var_B0]
0x180126a26  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBGV?$CoalescedRegionPtr@V?$ArrayRegion@UNameDictionaryEntry@FontApi@DWriteCore@@@CacheHelpers@DWriteCore@@@CacheHelpers@DWriteCore@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>,void *> *>,std::_Tree_node<std::pair<ushort const,DWriteCore::CacheHelpers::CoalescedRegionPtr<DWriteCore::CacheHelpers::ArrayRegion<DWriteCore::FontApi::NameDictionaryEntry>>>,void *> * const)
0x180126a2b  nop
0x180126a2c  lea     rcx, [rbp+57h+var_58]
0x180126a30  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180126a35  nop
0x180126a36  mov     rcx, [rbp+57h+var_B8]; struct DWrite::RefString::Data *
0x180126a3a  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180126a3f  mov     [rbp+57h+var_98], r12
0x180126a43  lea     rax, [rbp+57h+var_98]
0x180126a47  mov     [rsp+0F0h+phkResult], rax; phkResult
0x180126a4c  mov     r9d, 10h; samDesired
0x180126a52  xor     r8d, r8d; ulOptions
0x180126a55  lea     rdx, SubKey; "EUDC"
0x180126a5c  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180126a63  call    cs:__imp_RegOpenKeyExW
0x180126a69  test    eax, eax
0x180126a6b  jz      short loc_180126A76
0x180126a6d  mov     r8, r12
0x180126a70  mov     [rbp+57h+var_98], r12
0x180126a74  jmp     short loc_180126A7A
0x180126a76  mov     r8, [rbp+57h+var_98]
0x180126a7a  lea     r9, [rbp+57h+var_B0]
0x180126a7e  mov     rdx, r15
0x180126a81  mov     rcx, rdi; this
0x180126a84  call    ?Monitor@ChangeMonitor@EudcFontCollectionLoader@@QEAAXAEBVDateTime@@PEAUHKEY__@@AEBV?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; EudcFontCollectionLoader::ChangeMonitor::Monitor(DateTime const &,HKEY__ *,std::set<std::wstring> const &)
0x180126a89  nop
0x180126a8a  test    rsi, rsi
0x180126a8d  jz      short loc_180126A9F
0x180126a8f  mov     rax, [rsi]
0x180126a92  mov     rcx, rsi
0x180126a95  mov     rax, [rax+10h]
0x180126a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180126a9e  nop
0x180126a9f  mov     r8, [rbp+57h+var_B0]
0x180126aa3  mov     r8, [r8+8]
0x180126aa7  lea     rdx, [rbp+57h+var_B0]
0x180126aab  lea     rcx, [rbp+57h+var_B0]
0x180126aaf  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::wstring>>::_Erase_tree<std::allocator<std::_Tree_node<std::wstring,void *>>>(std::allocator<std::_Tree_node<std::wstring,void *>> &,std::_Tree_node<std::wstring,void *> *)
0x180126ab4  mov     edx, 40h ; '@'
0x180126ab9  mov     rcx, [rbp+57h+var_B0]
0x180126abd  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180126ac2  mov     rcx, [rbp+57h+var_38]
0x180126ac6  xor     rcx, rsp; StackCookie
0x180126ac9  call    __security_check_cookie
0x180126ace  lea     r11, [rsp+0F0h+var_20]
0x180126ad6  mov     rbx, [r11+30h]
0x180126ada  mov     rsi, [r11+40h]
0x180126ade  movaps  xmm6, xmmword ptr [r11-10h]
0x180126ae3  mov     rsp, r11
0x180126ae6  pop     r15
0x180126ae8  pop     r14
0x180126aea  pop     r12
0x180126aec  pop     rdi
0x180126aed  pop     rbp
0x180126aee  retn
```
