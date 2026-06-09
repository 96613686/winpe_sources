# WebRuntimeDiagnostics::LCIEDiagnosticsSession::UninitializeIsoSession(void)

- ea: `0x18002652c`
- end: `0x18002677c`
- name: `?UninitializeIsoSession@LCIEDiagnosticsSession@WebRuntimeDiagnostics@@AEAAXXZ`
- size: `592`
- prototype: `void __fastcall(WebRuntimeDiagnostics::LCIEDiagnosticsSession *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800689a4`
- `0x18006915c`

## callees

- `0x180018b30`
- `0x18002343c`
- `0x18002652c`
- `0x180026784`
- `0x1800281dc`
- `0x1800281fc`
- `0x18002a16c`
- `0x18002b530`
- `0x180065184`
- `0x1800681bc`
- `0x1800682f8`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800265dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800265dc`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800266a2`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800266a2`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1800266dd`
- `edgeIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1800266dd`
- `edgeIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@W4IsoArtifactType@@PEAXPEAKPEAPEAU_IsoArtifact@@3@Z` at `0x1800265b2`
- `edgeIso!__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@W4IsoArtifactType@@PEAXPEAKPEAPEAU_IsoArtifact@@3@Z` at `0x1800265b2`
- `edgeIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1800266d5`
- `edgeIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1800266d5`
- `edgeIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1800266cf`
- `edgeIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1800266cf`
- `edgeIso!__imp_?IsoPostMessageWithoutBuffer@@YAJKKKKU_GUID@@@Z` at `0x18002666d`
- `edgeIso!__imp_?IsoPostMessageWithoutBuffer@@YAJKKKKU_GUID@@@Z` at `0x18002666d`
- `edgeIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18002664b`
- `edgeIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x18002664b`
- `edgeIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1800266ec`
- `edgeIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x1800266ec`
- `edgeIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1800266e6`
- `edgeIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x18002672b`
- `edgeIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1800266e6`
- `edgeIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x18002672b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall WebRuntimeDiagnostics::LCIEDiagnosticsSession::UninitializeIsoSession(
        WebRuntimeDiagnostics::LCIEDiagnosticsSession *this)
{
  unsigned int v2; // r14d
  int NextArtifact; // esi
  __int64 v4; // rdi
  DWORD CurrentProcessId; // eax
  unsigned __int64 v6; // rcx
  __int64 v7; // rdi
  unsigned __int64 appended; // rax
  __int64 v9; // rcx
  _QWORD *v10; // r8
  unsigned int CurrentProcessManager; // eax
  const char *v12; // r9
  unsigned int CurrentThreadHandle; // eax
  struct IsoScope *DefaultScope; // rax
  const char *v15; // r9
  unsigned __int8 v16[4]; // [rsp+38h] [rbp-79h] BYREF
  HANDLE *lpHandles; // [rsp+40h] [rbp-71h] BYREF
  char *v18; // [rsp+48h] [rbp-69h]
  char *v19; // [rsp+50h] [rbp-61h]
  __int64 v20; // [rsp+58h] [rbp-59h] BYREF
  char v21[8]; // [rsp+60h] [rbp-51h] BYREF
  __int64 v22; // [rsp+68h] [rbp-49h]
  GUID v23; // [rsp+78h] [rbp-39h] BYREF
  char v24[16]; // [rsp+88h] [rbp-29h] BYREF
  char v25[32]; // [rsp+98h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+110h] [rbp+5Fh]

  if ( *(_BYTE *)this )
  {
    v20 = 0;
    *(_DWORD *)v16 = 0;
    v2 = 1;
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>>>(&lpHandles);
    ThreadSafeData<std::unordered_map<unsigned long,void *>,wil::critical_section,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>>::AcquireExclusive(
      (char *)this + 8,
      v21);
    do
    {
      while ( 1 )
      {
        NextArtifact = IsoGetNextArtifact(v2, 1, v25, v16, &v20, 0);
        if ( NextArtifact )
          break;
        v4 = v20;
        if ( (unsigned __int16)(*(_WORD *)(v20 + 2) - 525) > 1u )
          break;
        CurrentProcessId = GetCurrentProcessId();
        v6 = *(unsigned int *)(v4 + 16);
        if ( (_DWORD)v6 != CurrentProcessId )
          break;
        v7 = v22;
        appended = std::_Fnv1a_append_bytes(v6, v16, (unsigned int)(NextArtifact + 4));
        v9 = *(_QWORD *)(std::_Hash<std::_Umap_traits<unsigned long,void *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,void *>>,0>>::_Find_last<unsigned long>(
                           v7,
                           v24,
                           v16,
                           appended)
                       + 8);
        if ( v9 && v9 != *(_QWORD *)(v7 + 8) )
        {
          v10 = (_QWORD *)(v9 + 24);
          if ( v18 == v19 )
          {
            std::vector<void *>::_Emplace_reallocate<void * const &>(&lpHandles, v18, v10);
          }
          else
          {
            *(_QWORD *)v18 = *v10;
            v18 += 8;
          }
        }
        CurrentProcessManager = IsoGetCurrentProcessManager();
        v23 = GUID_NULL;
        IsoPostMessageWithoutBuffer(*(unsigned int *)v16, CurrentProcessManager, 0xDE0u, 0, &v23);
      }
      v2 = 2;
    }
    while ( !NextArtifact );
    if ( WaitForMultipleObjects((v18 - (char *)lpHandles) >> 3, lpHandles, 1, 0x1388u) == 258 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
        v12);
    std::_Hash<std::_Umap_traits<unsigned long,void *,std::_Uhash_compare<unsigned long,std::hash<unsigned long>,std::equal_to<unsigned long>>,std::allocator<std::pair<unsigned long const,void *>>,0>>::clear(v22);
    IsoUninitializeThread(0);
    CurrentThreadHandle = IsoGetCurrentThreadHandle();
    IsoRemoveArtifact(CurrentThreadHandle);
    IsoReleaseDefaultScope(1u);
    DefaultScope = IsoGetDefaultScope();
    if ( (*(unsigned int (__fastcall **)(struct IsoScope *, __int64))(*(_QWORD *)DefaultScope + 256LL))(
           DefaultScope,
           32) == 3 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1F7,
        (unsigned int)"onecoreuap\\inetcore\\edgemanager\\webruntime\\webruntimediagnostics\\lciediagnosticssession.cpp",
        v15);
    IsoReleaseDefaultScope(0);
    *(_BYTE *)this = 0;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(v21);
    if ( lpHandles )
      std::_Deallocate<16>(lpHandles, (v19 - (char *)lpHandles) & 0xFFFFFFFFFFFFFFF8uLL);
  }
}

```

## disassembly

```asm
0x18002652c  mov     rax, rsp
0x18002652f  push    rbp
0x180026530  push    rbx
0x180026531  push    rsi
0x180026532  push    rdi
0x180026533  push    r12
0x180026535  push    r14
0x180026537  lea     rbp, [rax-5Fh]
0x18002653b  sub     rsp, 0D8h
0x180026542  movaps  xmmword ptr [rax-48h], xmm6
0x180026546  mov     rax, cs:__security_cookie
0x18002654d  xor     rax, rsp
0x180026550  mov     [rbp+57h+var_50], rax
0x180026554  mov     rbx, rcx
0x180026557  mov     al, [rcx]
0x180026559  nop
0x18002655a  test    al, al
0x18002655c  jz      loc_180026758
0x180026562  mov     [rbp+57h+var_B0], 0
0x18002656a  mov     dword ptr [rbp+57h+var_D0], 0
0x180026571  mov     r12d, 1
0x180026577  mov     r14d, r12d
0x18002657a  lea     rcx, [rbp+57h+lpHandles]
0x18002657e  call    ??$?0AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@std@@$0A@@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VCDebugTargetClientBrokerAdapterImpl@@U?$default_delete@VCDebugTargetClientBrokerAdapterImpl@@@std@@@2@@std@@@1@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>>>::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>>>>>>(std::allocator<std::pair<std::wstring const,std::unique_ptr<CDebugTargetClientBrokerAdapterImpl>>> const &)
0x180026583  nop
0x180026584  lea     rcx, [rbx+8]
0x180026588  lea     rdx, [rbp+57h+var_A8]
0x18002658c  call    ?AcquireExclusive@?$ThreadSafeData@V?$unordered_map@KPEAXU?$hash@K@std@@U?$equal_to@K@2@V?$allocator@U?$pair@$$CBKPEAX@std@@@2@@std@@Vcritical_section@wil@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@4@@@QEAA?AV?$LockedData@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@1@XZ; ThreadSafeData<std::unordered_map<ulong,void *>,wil::critical_section,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>>>::AcquireExclusive(void)
0x180026591  nop
0x180026592  mov     qword ptr [rsp+28h], 0
0x18002659b  lea     rax, [rbp+57h+var_B0]
0x18002659f  mov     [rsp+100h+var_E0], rax
0x1800265a4  lea     r9, [rbp+57h+var_D0]
0x1800265a8  lea     r8, [rbp+57h+var_70]
0x1800265ac  mov     edx, r12d
0x1800265af  mov     ecx, r14d
0x1800265b2  call    cs:__imp_?IsoGetNextArtifact@@YAJW4_IsoEnumeration@@W4IsoArtifactType@@PEAXPEAKPEAPEAU_IsoArtifact@@3@Z; IsoGetNextArtifact(_IsoEnumeration,IsoArtifactType,void *,ulong *,_IsoArtifact * *,ulong *)
0x1800265b8  mov     esi, eax
0x1800265ba  test    eax, eax
0x1800265bc  jnz     loc_180026678
0x1800265c2  mov     eax, 20Dh
0x1800265c7  mov     rdi, [rbp+57h+var_B0]
0x1800265cb  movzx   ecx, word ptr [rdi+2]
0x1800265cf  sub     cx, ax
0x1800265d2  cmp     cx, r12w
0x1800265d6  ja      loc_180026678
0x1800265dc  call    cs:__imp_GetCurrentProcessId
0x1800265e2  mov     ecx, [rdi+10h]; unsigned __int64
0x1800265e5  cmp     ecx, eax
0x1800265e7  jnz     loc_180026678
0x1800265ed  mov     rdi, [rbp+57h+var_A0]
0x1800265f1  lea     r8d, [rsi+4]; unsigned __int64
0x1800265f5  lea     rdx, [rbp+57h+var_D0]; unsigned __int8 *
0x1800265f9  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x1800265fe  mov     r9, rax
0x180026601  lea     r8, [rbp+57h+var_D0]
0x180026605  lea     rdx, [rbp+57h+var_80]
0x180026609  mov     rcx, rdi
0x18002660c  call    ??$_Find_last@K@?$_Hash@V?$_Umap_traits@KPEAXV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAX@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBKPEAX@std@@PEAX@std@@@1@AEBK_K@Z; std::_Hash<std::_Umap_traits<ulong,void *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,void *>>,0>>::_Find_last<ulong>(ulong const &,unsigned __int64)
0x180026611  mov     rcx, [rax+8]
0x180026615  test    rcx, rcx
0x180026618  jz      short loc_180026644
0x18002661a  cmp     rcx, [rdi+8]
0x18002661e  jz      short loc_180026644
0x180026620  lea     r8, [rcx+18h]
0x180026624  mov     rdx, [rbp+57h+var_C0]
0x180026628  cmp     rdx, [rbp+57h+var_B8]
0x18002662c  jz      short loc_18002663B
0x18002662e  mov     rax, [r8]
0x180026631  mov     [rdx], rax
0x180026634  add     [rbp+57h+var_C0], 8
0x180026639  jmp     short loc_180026644
0x18002663b  lea     rcx, [rbp+57h+lpHandles]
0x18002663f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x180026644  movups  xmm6, xmmword ptr cs:GUID_NULL.Data1
0x18002664b  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x180026651  movdqu  [rbp+57h+var_90], xmm6
0x180026656  lea     rcx, [rbp+57h+var_90]
0x18002665a  mov     [rsp+100h+var_E0], rcx
0x18002665f  xor     r9d, r9d
0x180026662  mov     r8d, 0DE0h
0x180026668  mov     edx, eax
0x18002666a  mov     ecx, dword ptr [rbp+57h+var_D0]
0x18002666d  call    cs:__imp_?IsoPostMessageWithoutBuffer@@YAJKKKKU_GUID@@@Z; IsoPostMessageWithoutBuffer(ulong,ulong,ulong,ulong,_GUID)
0x180026673  jmp     loc_180026592
0x180026678  mov     r14d, 2
0x18002667e  test    esi, esi
0x180026680  jz      loc_180026592
0x180026686  mov     rdx, [rbp+57h+lpHandles]; lpHandles
0x18002668a  mov     rdi, [rbp+5Fh]
0x18002668e  mov     rcx, [rbp+57h+var_C0]
0x180026692  sub     rcx, rdx
0x180026695  sar     rcx, 3; nCount
0x180026699  mov     r9d, 1388h; dwMilliseconds
0x18002669f  mov     r8d, r12d; bWaitAll
0x1800266a2  call    cs:__imp_WaitForMultipleObjects
0x1800266a8  cmp     eax, 102h
0x1800266ad  jnz     short loc_1800266C4
0x1800266af  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x1800266b6  mov     edx, 1EBh; void *
0x1800266bb  mov     rcx, rdi; this
0x1800266be  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800266c4  mov     rcx, [rbp+57h+var_A0]
0x1800266c8  call    ?clear@?$_Hash@V?$_Umap_traits@KPEAXV?$_Uhash_compare@KU?$hash@K@std@@U?$equal_to@K@2@@std@@V?$allocator@U?$pair@$$CBKPEAX@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<ulong,void *,std::_Uhash_compare<ulong,std::hash<ulong>,std::equal_to<ulong>>,std::allocator<std::pair<ulong const,void *>>,0>>::clear(void)
0x1800266cd  xor     ecx, ecx
0x1800266cf  call    cs:__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z; IsoUninitializeThread(IsoScope *)
0x1800266d5  call    cs:__imp_?IsoGetCurrentThreadHandle@@YAKXZ; IsoGetCurrentThreadHandle(void)
0x1800266db  mov     ecx, eax
0x1800266dd  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x1800266e3  mov     ecx, r12d
0x1800266e6  call    cs:__imp_?IsoReleaseDefaultScope@@YAKK@Z; IsoReleaseDefaultScope(ulong)
0x1800266ec  call    cs:__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ; IsoGetDefaultScope(void)
0x1800266f2  mov     rcx, rax
0x1800266f5  mov     rdi, [rbp+5Fh]
0x1800266f9  mov     rdx, [rax]
0x1800266fc  mov     rax, [rdx+100h]
0x180026703  xor     r8d, r8d
0x180026706  lea     edx, [r8+20h]
0x18002670a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002670f  cmp     eax, 3
0x180026712  jnz     short loc_180026729
0x180026714  lea     r8, aOnecoreuapInet_3; "onecoreuap\\inetcore\\edgemanager\\webr"...
0x18002671b  mov     edx, 1F7h; void *
0x180026720  mov     rcx, rdi; this
0x180026723  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180026729  xor     ecx, ecx
0x18002672b  call    cs:__imp_?IsoReleaseDefaultScope@@YAKK@Z; IsoReleaseDefaultScope(ulong)
0x180026731  xor     eax, eax
0x180026733  xchg    al, [rbx]
0x180026735  lea     rcx, [rbp+57h+var_A8]
0x180026739  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002673e  nop
0x18002673f  mov     rcx, [rbp+57h+lpHandles]
0x180026743  test    rcx, rcx
0x180026746  jz      short loc_180026758
0x180026748  mov     rdx, [rbp+57h+var_B8]
0x18002674c  sub     rdx, rcx
0x18002674f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180026753  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180026758  mov     rcx, [rbp+57h+var_50]
0x18002675c  xor     rcx, rsp; StackCookie
0x18002675f  call    __security_check_cookie
0x180026764  movaps  xmm6, [rsp+100h+var_48+8]
0x18002676c  add     rsp, 0D8h
0x180026773  pop     r14
0x180026775  pop     r12
0x180026777  pop     rdi
0x180026778  pop     rsi
0x180026779  pop     rbx
0x18002677a  pop     rbp
0x18002677b  retn
```
