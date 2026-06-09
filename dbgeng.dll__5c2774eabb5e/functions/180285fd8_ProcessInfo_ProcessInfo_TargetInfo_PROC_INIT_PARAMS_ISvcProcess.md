# ProcessInfo::ProcessInfo(TargetInfo *,PROC_INIT_PARAMS *,ISvcProcess *)

- ea: `0x180285fd8`
- end: `0x1802866c9`
- name: `??0ProcessInfo@@QEAA@PEAVTargetInfo@@PEAUPROC_INIT_PARAMS@@PEAUISvcProcess@@@Z`
- size: `1777`
- prototype: `ProcessInfo *__fastcall(ProcessInfo *__hidden this, struct TargetInfo *, struct PROC_INIT_PARAMS *, struct ISvcProcess *)`
- caller_count: `9`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18008de80`
- `0x18019776c`
- `0x180238ea0`
- `0x180239d80`
- `0x18023d1f0`
- `0x18038aacc`
- `0x1803a69d0`
- `0x1803a6eb0`
- `0x1803a83e0`

## callees

- `0x18008dbc8`
- `0x18008e130`
- `0x18009509c`
- `0x180097400`
- `0x1800986ec`
- `0x18009d40c`
- `0x1800aa8fc`
- `0x1800bc3bc`
- `0x1800bdef4`
- `0x1800c15b4`
- `0x1800c2360`
- `0x180284ca8`
- `0x180285fd8`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-environment-l1-1-0!getenv` at `0x180286433`
- `api-ms-win-crt-environment-l1-1-0!getenv` at `0x180286498`
- `api-ms-win-crt-environment-l1-1-0!getenv` at `0x180286433`
- `api-ms-win-crt-environment-l1-1-0!getenv` at `0x180286498`
- `api-ms-win-crt-convert-l1-1-0!atol` at `0x1802864ac`
- `api-ms-win-crt-convert-l1-1-0!atol` at `0x1802864ac`
- `dbghelp!SymAddrIncludeInlineTrace` at `0x18028653e`
- `dbghelp!SymAddrIncludeInlineTrace` at `0x18028653e`
- `dbghelp!SymInitializeW` at `0x180286510`
- `dbghelp!SymInitializeW` at `0x180286510`
- `dbghelp!SymSetServiceManager` at `0x18028652e`
- `dbghelp!SymSetServiceManager` at `0x18028652e`
- `dbghelp!SymRegisterCallbackW64` at `0x180286562`
- `dbghelp!SymRegisterCallbackW64` at `0x180286562`
- `dbghelp!SymRegisterFunctionEntryCallback64` at `0x18028659e`
- `dbghelp!SymRegisterFunctionEntryCallback64` at `0x18028659e`

## string_xrefs

- `0x18028640b`: `No load attempts`
- `0x180286491`: `_NT_DEBUG_CACHE_SIZE`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
ProcessInfo *__fastcall ProcessInfo::ProcessInfo(
        ProcessInfo *this,
        struct TargetInfo *a2,
        struct PROC_INIT_PARAMS *a3,
        struct ISvcProcess *a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  int v10; // esi
  __int64 size_of; // rax
  __int64 v12; // rax
  int NextUserId; // eax
  _DWORD *v14; // r10
  __int64 v15; // rax
  unsigned int v16; // ecx
  __int64 v17; // rdx
  int v18; // edx
  DWORD v19; // ecx
  int v20; // edx
  int v21; // eax
  unsigned int v22; // ecx
  __int64 v23; // rax
  char *v24; // rax
  __int64 v25; // rax
  char v26; // al
  int v27; // ecx
  struct IUnknown *ServiceManager; // rax
  struct ProcessInfo *v29; // rcx
  _DWORD *v30; // rdx
  int v31; // r8d
  int v32; // r9d
  struct TargetInfo *v34; // [rsp+78h] [rbp+10h] BYREF
  char *v35; // [rsp+80h] [rbp+18h]

  v34 = a2;
  DbgCache<OOPFunctionTableCacheKey,OOPFunctionTable,OOPFunctionTableCachePolicy>::DbgCache<OOPFunctionTableCacheKey,OOPFunctionTable,OOPFunctionTableCachePolicy>(this);
  *((_QWORD *)this + 14) = 0;
  *((_QWORD *)this + 16) = 0;
  *((_QWORD *)this + 17) = 0;
  *((_QWORD *)this + 18) = 0;
  v35 = (char *)this + 152;
  *((_DWORD *)this + 38) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_QWORD *)this + 21) = 0;
  v8 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(32);
  *v8 = v8;
  v8[1] = v8;
  *((_QWORD *)this + 20) = v8;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  *((_QWORD *)this + 25) = 7;
  *((_QWORD *)this + 26) = 8;
  *((_DWORD *)this + 38) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,unsigned __int64>>>>>>::_Assign_grow(
    (char *)this + 176,
    16,
    *((_QWORD *)this + 20));
  v35 = (char *)this + 216;
  *((_DWORD *)this + 54) = 0;
  *((_QWORD *)this + 28) = 0;
  *((_QWORD *)this + 29) = 0;
  v9 = (_QWORD *)std::_Allocate<16,std::_Default_allocate_traits>(56);
  *v9 = v9;
  v9[1] = v9;
  *((_QWORD *)this + 28) = v9;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 7;
  *((_QWORD *)this + 34) = 8;
  *((_DWORD *)this + 54) = 1065353216;
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned long const,unsigned __int64>>>>>>::_Assign_grow(
    (char *)this + 240,
    16,
    *((_QWORD *)this + 28));
  *((_QWORD *)this + 35) = 0;
  *((_QWORD *)this + 36) = 0;
  v10 = 1;
  size_of = std::_Get_size_of_n<72>(1);
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *(_QWORD *)v12 = v12;
  *(_QWORD *)(v12 + 8) = v12;
  *(_QWORD *)(v12 + 16) = v12;
  *(_WORD *)(v12 + 24) = 257;
  *((_QWORD *)this + 35) = v12;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 46) = 0;
  *((_DWORD *)this + 99) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_QWORD *)this + 152) = &ProcClrDataTarget::`vftable'{for `ICLRDataTarget2'};
  *((_QWORD *)this + 153) = &ProcClrDataTarget::`vftable'{for `ICLRMetadataLocator'};
  *((_QWORD *)this + 154) = &ProcClrDataTarget::`vftable'{for `ICLRRuntimeLocator'};
  *((_QWORD *)this + 155) = 0;
  *((_QWORD *)this + 156) = &DbgDbsVirtualUncachedBaseReadWrite::`vftable';
  *((_QWORD *)this + 157) = 0;
  *((_QWORD *)this + 158) = 0;
  MemoryCache::MemoryCache((ProcessInfo *)((char *)this + 1272), (ProcessInfo *)((char *)this + 1248), 0x100000u);
  MemoryCache::MemoryCache(
    (ProcessInfo *)((char *)this + 1384),
    (struct DbsBaseReadWrite *)&DbsNullBaseReadWrite::s_Impl,
    0x40000000u);
  *((_DWORD *)this + 390) = 0;
  *((_BYTE *)this + 1632) = 0;
  *((_BYTE *)this + 1656) = 0;
  *((_QWORD *)this + 11) = a2;
  NextUserId = FindNextUserId(1);
  *v14 = NextUserId;
  *((_QWORD *)this + 13) = a4;
  if ( a4 )
  {
    *((_BYTE *)this + 120) = 0;
    (*(void (__fastcall **)(struct ISvcProcess *))(*(_QWORD *)a4 + 8LL))(a4);
  }
  else
  {
    v15 = *((_QWORD *)this + 11);
    if ( v15 && *(_DWORD *)(v15 + 4104) == 1 )
    {
      *((_BYTE *)this + 120) = 0;
    }
    else
    {
      *((_BYTE *)this + 120) = 1;
      Microsoft::WRL::Details::MakeAndInitialize<Debugger::TargetComposition::Host::ProcessRedirector,ISvcProcess,TargetInfo * &,unsigned long &>(
        (char *)this + 104,
        &v34,
        v14);
    }
  }
  *((_QWORD *)this + 191) = 0;
  *((_QWORD *)this + 192) = 0;
  *((_QWORD *)this + 193) = 0;
  *((_QWORD *)this + 194) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 31) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 40) = 0;
  *((_DWORD *)this + 90) = 0;
  *((_QWORD *)this + 47) = 0;
  *((_DWORD *)this + 97) = *(_DWORD *)a3;
  *((_DWORD *)this + 98) &= 0xFFFFFFFC;
  v16 = *((_DWORD *)this + 98) & 0xFFFFFFFB | (*((_DWORD *)a3 + 1) >> 4) & 4;
  *((_DWORD *)this + 98) = v16;
  if ( (*((_BYTE *)a3 + 4) & 0x40) != 0
    || (v17 = *((_QWORD *)this + 11)) != 0 && *(_DWORD *)(v17 + 4104) == 1
    || (v18 = 0, (g_EngOptions & 0x20) != 0) )
  {
    v18 = 8;
  }
  v19 = (g_EngOptions >> 1) & 0x10 | v18 & 0xFFFFFC0F | v16 & 0xFFFFFC07;
  *((_DWORD *)this + 98) = v19;
  if ( !a2
    || *((_DWORD *)a2 + 1026) != 1
    || (v20 = *((_DWORD *)a2 + 1027), (unsigned int)(v20 - 1024) <= 5)
    || v20 == 3143
    || (v21 = 1024, v20 == 5) )
  {
    v21 = 0;
  }
  v22 = v21 | v19 & 0xFFFFFBFF;
  *((_DWORD *)this + 98) = v22;
  *((_QWORD *)this + 50) = *((_QWORD *)a3 + 3);
  *((_QWORD *)this + 51) = *((_QWORD *)a3 + 5);
  *((_QWORD *)this + 52) = *((_QWORD *)a3 + 2);
  *((_DWORD *)this + 106) = *((_DWORD *)a3 + 1);
  *((_DWORD *)this + 107) = *((_DWORD *)a3 + 2);
  *((_DWORD *)this + 108) = *((_DWORD *)a3 + 3);
  *((_QWORD *)this + 55) = *((_QWORD *)a3 + 4);
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 60) = 0;
  *((_DWORD *)this + 98) = v22 & 0xFFFF07FF | 0x4000;
  *((_WORD *)this + 796) = 0;
  *((_QWORD *)this + 197) = 0;
  *((_QWORD *)this + 198) = 0;
  *((_WORD *)this + 808) = 0;
  *((_QWORD *)this + 200) = 0;
  *((_QWORD *)this + 201) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_DWORD *)this + 124) = 1;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 64) = 0;
  *((_DWORD *)this + 130) = 0;
  *((_QWORD *)this + 66) = 0;
  CopyNStringW((char *)this + 536);
  *((_QWORD *)this + 149) = 0;
  *((_QWORD *)this + 150) = 0;
  *((_DWORD *)this + 302) = 0;
  *((_DWORD *)this + 303) = getenv("DBGENG_XXX_CLR") != 0;
  *((_QWORD *)this + 155) = this;
  v23 = *((_QWORD *)this + 11);
  *((_QWORD *)this + 170) = v23;
  *((_QWORD *)this + 171) = this;
  *((_QWORD *)this + 157) = v23;
  *((_QWORD *)this + 158) = this;
  *((_DWORD *)this + 335) = 128;
  *((_DWORD *)this + 336) = 3;
  *(_QWORD *)((char *)this + 1564) = 0;
  *((_BYTE *)this + 1572) = 0;
  v24 = getenv("_NT_DEBUG_CACHE_SIZE");
  if ( v24 )
    *((_DWORD *)this + 334) = atol(v24);
  *((_DWORD *)this + 375) = 0;
  v25 = *((_QWORD *)this + 11);
  if ( v25 && *(_DWORD *)(v25 + 4104) == 1 && (*(_BYTE *)(v25 + 766) & 8) == 0 )
  {
    v26 = 1;
    v27 = 1;
  }
  else
  {
    v26 = 0;
    v27 = 0;
  }
  *((_DWORD *)this + 374) = v27;
  *((_BYTE *)this + 1504) = v26;
  TargetInfo::InsertProcess(*((TargetInfo **)this + 11), this);
  SymInitializeW(*((HANDLE *)this + 51), 0, 0);
  ServiceManager = (struct IUnknown *)TargetInfo::GetServiceManager(a2);
  SymSetServiceManager(*((void **)this + 51), ServiceManager);
  g_StepTraceSignature = SymAddrIncludeInlineTrace(0, 0);
  SymRegisterCallbackW64(*((HANDLE *)this + 51), SymbolCallbackFunction, (ULONG64)this);
  v29 = (struct ProcessInfo *)*((_QWORD *)this + 11);
  if ( v29 && (unsigned int)(*((_DWORD *)v29 + 1026) - 2) <= 1 && *((_DWORD *)v29 + 23) != 332 )
    SymRegisterFunctionEntryCallback64(*((HANDLE *)this + 51), TargetInfo::DynamicFunctionTableCallback, (ULONG64)this);
  v30 = (_DWORD *)*((_QWORD *)this + 11);
  if ( v30 )
  {
    v31 = v30[1026];
    v29 = (struct ProcessInfo *)(v30 + 1027);
    if ( !v31 )
      goto LABEL_37;
    v32 = *(_DWORD *)v29;
    if ( (unsigned int)(*(_DWORD *)v29 - 1024) <= 5 || v32 == 3143 )
    {
LABEL_43:
      if ( *(_DWORD *)(*((_QWORD *)this + 11) + 64LL) != 1 )
        v10 = 0;
      goto LABEL_45;
    }
    if ( v31 == 2 )
    {
      if ( v32 != 3 )
        goto LABEL_45;
    }
    else
    {
LABEL_37:
      if ( v31 != 1 || *(_DWORD *)v29 != 5 )
        goto LABEL_45;
    }
    if ( (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 1552LL))(*((_QWORD *)this + 11))
      && *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 1552LL))(*((_QWORD *)this + 11))
                   + 4104)
      && (*(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 1552LL))(*((_QWORD *)this + 11))
                    + 4108) >= 0x400u
       && *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 1552LL))(*((_QWORD *)this + 11))
                    + 4108) <= 0x405u
       || *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 11) + 1552LL))(*((_QWORD *)this + 11))
                    + 4108) == 3143) )
    {
      goto LABEL_43;
    }
  }
LABEL_45:
  SetSymbolSearchPath(v29, v10);
  ProcessInfo::SynthesizeSymbols(this);
  return this;
}

```

## disassembly

```asm
0x180285fd8  mov     [rsp+arg_8], rdx
0x180285fdd  mov     [rsp+arg_0], rcx
0x180285fe2  push    rbx
0x180285fe3  push    rbp
0x180285fe4  push    rsi
0x180285fe5  push    rdi
0x180285fe6  push    r13
0x180285fe8  push    r14
0x180285fea  push    r15
0x180285fec  sub     rsp, 30h
0x180285ff0  mov     [rsp+68h+var_48], 0FFFFFFFFFFFFFFFEh
0x180285ff9  mov     r15, r9
0x180285ffc  mov     r14, r8
0x180285fff  mov     rbp, rdx
0x180286002  mov     rdi, rcx
0x180286005  call    ??0?$DbgCache@UOOPFunctionTableCacheKey@@UOOPFunctionTable@@UOOPFunctionTableCachePolicy@@@@QEAA@XZ; DbgCache<OOPFunctionTableCacheKey,OOPFunctionTable,OOPFunctionTableCachePolicy>::DbgCache<OOPFunctionTableCacheKey,OOPFunctionTable,OOPFunctionTableCachePolicy>(void)
0x18028600a  nop
0x18028600b  xor     r13d, r13d
0x18028600e  mov     [rdi+70h], r13
0x180286012  mov     [rdi+80h], r13
0x180286019  mov     [rdi+88h], r13
0x180286020  mov     [rdi+90h], r13
0x180286027  lea     rbx, [rdi+98h]
0x18028602e  mov     [rsp+68h+arg_10], rbx
0x180286036  mov     [rbx], r13d
0x180286039  mov     [rbx+8], r13
0x18028603d  mov     [rbx+10h], r13
0x180286041  lea     ecx, [r13+20h]
0x180286045  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18028604a  mov     [rax], rax
0x18028604d  mov     [rax+8], rax
0x180286051  mov     [rbx+8], rax
0x180286055  lea     rcx, [rbx+18h]
0x180286059  mov     [rcx], r13
0x18028605c  mov     [rcx+8], r13
0x180286060  mov     [rcx+10h], r13
0x180286064  mov     qword ptr [rbx+30h], 7
0x18028606c  mov     qword ptr [rbx+38h], 8
0x180286074  mov     esi, 3F800000h
0x180286079  mov     [rbx], esi
0x18028607b  mov     r8, [rbx+8]
0x18028607f  lea     edx, [r13+10h]
0x180286083  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBK_K@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBK_K@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,unsigned __int64>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,unsigned __int64>>>>)
0x180286088  nop
0x180286089  lea     rbx, [rdi+0D8h]
0x180286090  mov     [rsp+68h+arg_10], rbx
0x180286098  mov     [rbx], r13d
0x18028609b  mov     [rbx+8], r13
0x18028609f  mov     [rbx+10h], r13
0x1802860a3  lea     ecx, [r13+38h]
0x1802860a7  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1802860ac  mov     [rax], rax
0x1802860af  mov     [rax+8], rax
0x1802860b3  mov     [rbx+8], rax
0x1802860b7  lea     rcx, [rbx+18h]
0x1802860bb  mov     [rcx], r13
0x1802860be  mov     [rcx+8], r13
0x1802860c2  mov     [rcx+10h], r13
0x1802860c6  mov     qword ptr [rbx+30h], 7
0x1802860ce  mov     qword ptr [rbx+38h], 8
0x1802860d6  mov     [rbx], esi
0x1802860d8  mov     r8, [rbx+8]
0x1802860dc  lea     edx, [r13+10h]
0x1802860e0  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBK_K@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBK_K@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,unsigned __int64>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<ulong const,unsigned __int64>>>>)
0x1802860e5  nop
0x1802860e6  lea     rbx, [rdi+118h]
0x1802860ed  mov     [rbx], r13
0x1802860f0  mov     [rbx+8], r13
0x1802860f4  lea     esi, [r13+1]
0x1802860f8  mov     ecx, esi
0x1802860fa  call    ??$_Get_size_of_n@$0EI@@std@@YA_K_K@Z; std::_Get_size_of_n<72>(unsigned __int64)
0x1802860ff  mov     rcx, rax
0x180286102  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180286107  mov     [rax], rax
0x18028610a  mov     [rax+8], rax
0x18028610e  mov     [rax+10h], rax
0x180286112  mov     word ptr [rax+18h], 101h
0x180286118  mov     [rbx], rax
0x18028611b  mov     [rdi+148h], r13
0x180286122  mov     [rdi+170h], r13
0x180286129  mov     [rdi+18Ch], r13d
0x180286130  mov     [rdi+1C0h], r13
0x180286137  mov     [rdi+1C8h], r13
0x18028613e  lea     rax, ??_7ProcClrDataTarget@@6BICLRDataTarget2@@@; const ProcClrDataTarget::`vftable'{for `ICLRDataTarget2'}
0x180286145  mov     [rdi+4C0h], rax
0x18028614c  lea     rax, ??_7ProcClrDataTarget@@6BICLRMetadataLocator@@@; const ProcClrDataTarget::`vftable'{for `ICLRMetadataLocator'}
0x180286153  mov     [rdi+4C8h], rax
0x18028615a  lea     rax, ??_7ProcClrDataTarget@@6BICLRRuntimeLocator@@@; const ProcClrDataTarget::`vftable'{for `ICLRRuntimeLocator'}
0x180286161  mov     [rdi+4D0h], rax
0x180286168  mov     [rdi+4D8h], r13
0x18028616f  lea     rbx, [rdi+4E0h]
0x180286176  lea     rax, ??_7DbgDbsVirtualUncachedBaseReadWrite@@6B@; const DbgDbsVirtualUncachedBaseReadWrite::`vftable'
0x18028617d  mov     [rbx], rax
0x180286180  mov     [rbx+8], r13
0x180286184  mov     [rbx+10h], r13
0x180286188  lea     rcx, [rdi+4F8h]; this
0x18028618f  mov     r8d, 100000h; unsigned int
0x180286195  mov     rdx, rbx; struct DbsBaseReadWrite *
0x180286198  call    ??0MemoryCache@@QEAA@PEAVDbsBaseReadWrite@@K@Z; MemoryCache::MemoryCache(DbsBaseReadWrite *,ulong)
0x18028619d  nop
0x18028619e  lea     rcx, [rdi+568h]; this
0x1802861a5  mov     r8d, 40000000h; unsigned int
0x1802861ab  lea     rdx, ?s_Impl@DbsNullBaseReadWrite@@2V1@A; struct DbsBaseReadWrite *
0x1802861b2  call    ??0MemoryCache@@QEAA@PEAVDbsBaseReadWrite@@K@Z; MemoryCache::MemoryCache(DbsBaseReadWrite *,ulong)
0x1802861b7  nop
0x1802861b8  mov     [rdi+618h], r13d
0x1802861bf  mov     [rdi+660h], r13b
0x1802861c6  mov     [rdi+678h], r13b
0x1802861cd  mov     [rdi+58h], rbp
0x1802861d1  lea     r10, [rdi+180h]
0x1802861d8  mov     ecx, esi
0x1802861da  call    ?FindNextUserId@@YAKW4LAYER@@@Z; FindNextUserId(LAYER)
0x1802861df  mov     [r10], eax
0x1802861e2  lea     rcx, [rdi+68h]
0x1802861e6  mov     [rcx], r15
0x1802861e9  test    r15, r15
0x1802861ec  jz      short loc_180286203
0x1802861ee  mov     [rdi+78h], r13b
0x1802861f2  mov     rax, [r15]
0x1802861f5  mov     rcx, r15
0x1802861f8  mov     rax, [rax+8]
0x1802861fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180286201  jmp     short loc_18028622B
0x180286203  mov     rax, [rdi+58h]
0x180286207  test    rax, rax
0x18028620a  jz      short loc_18028621A
0x18028620c  cmp     [rax+1008h], esi
0x180286212  jnz     short loc_18028621A
0x180286214  mov     [rdi+78h], r13b
0x180286218  jmp     short loc_18028622B
0x18028621a  mov     [rdi+78h], sil
0x18028621e  mov     r8, r10
0x180286221  lea     rdx, [rsp+68h+arg_8]
0x180286226  call    ??$MakeAndInitialize@VProcessRedirector@Host@TargetComposition@Debugger@@UISvcProcess@@AEAPEAVTargetInfo@@AEAK@Details@WRL@Microsoft@@YAJPEAPEAUISvcProcess@@AEAPEAVTargetInfo@@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<Debugger::TargetComposition::Host::ProcessRedirector,ISvcProcess,TargetInfo * &,ulong &>(ISvcProcess * *,TargetInfo * &,ulong &)
0x18028622b  mov     [rdi+5F8h], r13
0x180286232  mov     [rdi+600h], r13
0x180286239  mov     [rdi+608h], r13
0x180286240  mov     [rdi+610h], r13
0x180286247  mov     [rdi+60h], r13
0x18028624b  mov     [rdi+7Ch], r13d
0x18028624f  mov     [rdi+128h], r13
0x180286256  mov     [rdi+150h], r13
0x18028625d  mov     [rdi+130h], r13
0x180286264  mov     [rdi+140h], r13
0x18028626b  mov     [rdi+168h], r13d
0x180286272  mov     [rdi+178h], r13
0x180286279  mov     eax, [r14]
0x18028627c  mov     [rdi+184h], eax
0x180286282  and     dword ptr [rdi+188h], 0FFFFFFFCh
0x180286289  mov     eax, [rdi+188h]
0x18028628f  mov     ecx, [r14+4]
0x180286293  shr     ecx, 4
0x180286296  and     ecx, 4
0x180286299  and     eax, 0FFFFFFFBh
0x18028629c  or      ecx, eax
0x18028629e  mov     [rdi+188h], ecx
0x1802862a4  mov     eax, cs:?g_EngOptions@@3KA; ulong g_EngOptions
0x1802862aa  test    byte ptr [r14+4], 40h
0x1802862af  jnz     short loc_1802862C9
0x1802862b1  mov     rdx, [rdi+58h]
0x1802862b5  test    rdx, rdx
0x1802862b8  jz      short loc_1802862C2
0x1802862ba  cmp     [rdx+1008h], esi
0x1802862c0  jz      short loc_1802862C9
0x1802862c2  test    al, 20h
0x1802862c4  mov     edx, r13d
0x1802862c7  jz      short loc_1802862CE
0x1802862c9  mov     edx, 8
0x1802862ce  and     ecx, 0FFFFFFF7h
0x1802862d1  or      ecx, edx
0x1802862d3  and     ecx, 0FFFFFC0Fh
0x1802862d9  shr     eax, 1
0x1802862db  and     eax, 10h
0x1802862de  or      ecx, eax
0x1802862e0  mov     [rdi+188h], ecx
0x1802862e6  mov     r15d, 0C47h
0x1802862ec  test    rbp, rbp
0x1802862ef  jz      short loc_180286319
0x1802862f1  cmp     [rbp+1008h], esi
0x1802862f7  jnz     short loc_180286319
0x1802862f9  mov     edx, [rbp+100Ch]
0x1802862ff  lea     eax, [rdx-400h]
0x180286305  cmp     eax, 5
0x180286308  jbe     short loc_180286319
0x18028630a  cmp     edx, r15d
0x18028630d  jz      short loc_180286319
0x18028630f  cmp     edx, 5
0x180286312  mov     eax, 400h
0x180286317  jnz     short loc_18028631C
0x180286319  mov     eax, r13d
0x18028631c  btr     ecx, 0Ah
0x180286320  or      ecx, eax
0x180286322  mov     [rdi+188h], ecx
0x180286328  mov     rax, [r14+18h]
0x18028632c  mov     [rdi+190h], rax
0x180286333  mov     rax, [r14+28h]
0x180286337  mov     [rdi+198h], rax
0x18028633e  mov     rax, [r14+10h]
0x180286342  mov     [rdi+1A0h], rax
0x180286349  mov     eax, [r14+4]
0x18028634d  mov     [rdi+1A8h], eax
0x180286353  mov     eax, [r14+8]
0x180286357  mov     [rdi+1ACh], eax
0x18028635d  mov     eax, [r14+0Ch]
0x180286361  mov     [rdi+1B0h], eax
0x180286367  mov     rax, [r14+20h]
0x18028636b  mov     [rdi+1B8h], rax
0x180286372  mov     [rdi+1D0h], r13
0x180286379  mov     [rdi+1D8h], r13
0x180286380  mov     [rdi+158h], r13
0x180286387  mov     [rdi+160h], r13
0x18028638e  mov     [rdi+1E0h], r13
0x180286395  and     ecx, 0FFFF47FFh
0x18028639b  bts     ecx, 0Eh
0x18028639f  mov     [rdi+188h], ecx
0x1802863a5  mov     [rdi+638h], r13w
0x1802863ad  mov     [rdi+628h], r13
0x1802863b4  mov     [rdi+630h], r13
0x1802863bb  mov     [rdi+650h], r13w
0x1802863c3  mov     [rdi+640h], r13
0x1802863ca  mov     [rdi+648h], r13
0x1802863d1  mov     [rdi+1E8h], r13
0x1802863d8  mov     [rdi+1F0h], esi
0x1802863de  mov     [rdi+1F8h], r13
0x1802863e5  mov     [rdi+200h], r13
0x1802863ec  mov     [rdi+208h], r13d
0x1802863f3  mov     [rdi+210h], r13
0x1802863fa  lea     rcx, [rdi+218h]; void *
0x180286401  mov     r9d, 145h
0x180286407  or      r8d, 0FFFFFFFFh
0x18028640b  lea     rdx, aNoLoadAttempts; "No load attempts"
0x180286412  call    CopyNStringW
0x180286417  mov     [rdi+4A8h], r13
0x18028641e  mov     [rdi+4B0h], r13
0x180286425  mov     [rdi+4B8h], r13d
0x18028642c  lea     rcx, aDbgengXxxClr; "DBGENG_XXX_CLR"
0x180286433  call    cs:__imp_getenv
0x18028643a  nop     dword ptr [rax+rax+00h]
0x18028643f  mov     ecx, r13d
0x180286442  test    rax, rax
0x180286445  setnz   cl
0x180286448  mov     [rdi+4BCh], ecx
0x18028644e  mov     [rdi+4D8h], rdi
0x180286455  mov     rax, [rdi+58h]
0x180286459  mov     [rdi+550h], rax
0x180286460  mov     [rdi+558h], rdi
0x180286467  mov     [rbx+8], rax
0x18028646b  mov     [rbx+10h], rdi
0x18028646f  mov     dword ptr [rdi+53Ch], 80h
0x180286479  mov     dword ptr [rdi+540h], 3
0x180286483  mov     [rdi+61Ch], r13
0x18028648a  mov     [rdi+624h], r13b
0x180286491  lea     rcx, VarName; "_NT_DEBUG_CACHE_SIZE"
0x180286498  call    cs:__imp_getenv
0x18028649f  nop     dword ptr [rax+rax+00h]
0x1802864a4  test    rax, rax
0x1802864a7  jz      short loc_1802864BE
0x1802864a9  mov     rcx, rax; String
0x1802864ac  call    cs:__imp_atol
0x1802864b3  nop     dword ptr [rax+rax+00h]
0x1802864b8  mov     [rdi+538h], eax
0x1802864be  mov     [rdi+5DCh], r13d
0x1802864c5  mov     rax, [rdi+58h]
0x1802864c9  test    rax, rax
0x1802864cc  jz      short loc_1802864E6
0x1802864ce  cmp     [rax+1008h], esi
0x1802864d4  jnz     short loc_1802864E6
0x1802864d6  test    byte ptr [rax+2FEh], 8
0x1802864dd  jnz     short loc_1802864E6
0x1802864df  mov     al, sil
0x1802864e2  mov     ecx, esi
0x1802864e4  jmp     short loc_1802864EC
0x1802864e6  mov     al, r13b
0x1802864e9  mov     ecx, r13d
0x1802864ec  mov     [rdi+5D8h], ecx
0x1802864f2  mov     [rdi+5E0h], al
0x1802864f8  mov     rdx, rdi; struct ProcessInfo *
0x1802864fb  mov     rcx, [rdi+58h]; this
0x1802864ff  call    ?InsertProcess@TargetInfo@@QEAAXPEAVProcessInfo@@@Z; TargetInfo::InsertProcess(ProcessInfo *)
0x180286504  xor     r8d, r8d; fInvadeProcess
0x180286507  xor     edx, edx; UserSearchPath
0x180286509  mov     rcx, [rdi+198h]; hProcess
0x180286510  call    cs:__imp_SymInitializeW
0x180286517  nop     dword ptr [rax+rax+00h]
0x18028651c  mov     rcx, rbp; this
0x18028651f  call    ?GetServiceManager@TargetInfo@@QEAAPEAUIDebugServiceManager@@XZ; TargetInfo::GetServiceManager(void)
0x180286524  mov     rdx, rax
0x180286527  mov     rcx, [rdi+198h]
0x18028652e  call    cs:__imp_?SymSetServiceManager@@YAHPEAXPEAUIUnknown@@@Z; SymSetServiceManager(void *,IUnknown *)
0x180286535  nop     dword ptr [rax+rax+00h]
0x18028653a  xor     edx, edx; Address
0x18028653c  xor     ecx, ecx; hProcess
0x18028653e  call    cs:__imp_SymAddrIncludeInlineTrace
0x180286545  nop     dword ptr [rax+rax+00h]
0x18028654a  mov     cs:?g_StepTraceSignature@@3GA, ax; ushort g_StepTraceSignature
0x180286551  mov     r8, rdi; UserContext
0x180286554  lea     rdx, ?SymbolCallbackFunction@@YAHPEAXK_K1@Z; CallbackFunction
0x18028655b  mov     rcx, [rdi+198h]; hProcess
0x180286562  call    cs:__imp_SymRegisterCallbackW64
0x180286569  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
