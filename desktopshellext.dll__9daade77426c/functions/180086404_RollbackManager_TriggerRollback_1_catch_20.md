# _RollbackManager::TriggerRollback_::_1_::catch$20

- ea: `0x180086404`
- end: `0x180086507`
- name: `_RollbackManager::TriggerRollback_::_1_::catch$20`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, installer_update`

## callees

- `0x18001e7f8`
- `0x180053fec`
- `0x180055108`
- `0x1800556f8`
- `0x180055a30`
- `0x180055f5c`
- `0x1800563f8`
- `0x180057390`
- `0x18005930c`
- `0x180086404`
- `0x180089010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18008647b`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x18008647b`

## string_xrefs

- `0x1800864cd`: `shell\onecore\desktopshellext\lib\rollbackmanager.cpp`
- `0x1800864c6`: `Rollback failed for features %s`

## pseudocode

```c
__int64 __fastcall RollbackManager::TriggerRollback_::_1_::catch_20(__int64 a1, __int64 a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rcx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rax
  const char *v8; // rax

  std::ostringstream::ostringstream(a2 + 112);
  v3 = 0;
  *(_DWORD *)(a2 + 48) = 0;
  v4 = *(_QWORD *)(a2 + 56);
  *(_DWORD *)(a2 + 352) = 0;
  *(_OWORD *)(a2 + 360) = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 56LL))(v4, a2 + 48);
  winrt::check_hresult(a2 + 64, v5, a2 + 352);
  while ( 1 )
  {
    v6 = a2 + 352;
    if ( v3 == *(_DWORD *)(a2 + 48) )
      break;
    winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>,winrt::Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>::GetAt(
      a2 + 56,
      v6,
      v3);
    v7 = std::ostream::operator<<(a2 + 112, *(unsigned int *)(a2 + 352));
    std::operator<<<std::char_traits<char>>(v7);
    winrt::Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy::~FeatureRollbackPolicy((winrt::Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy *)(a2 + 352));
    ++v3;
  }
  std::stringbuf::str(a2 + 120, v6);
  v8 = (const char *)(a2 + 352);
  if ( *(_QWORD *)(a2 + 376) > 0xFu )
    v8 = *(const char **)(a2 + 352);
  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 408),
    (void *)0xAB,
    (unsigned int)"shell\\onecore\\desktopshellext\\lib\\rollbackmanager.cpp",
    "Rollback failed for features %s",
    v8);
  std::string::~string(a2 + 352);
  std::ostringstream::`vbase destructor'(a2 + 112);
  return 0;
}

```

## disassembly

```asm
0x180086404  mov     [rsp+arg_8], rdx
0x180086409  push    rbx
0x18008640a  push    rbp
0x18008640b  sub     rsp, 38h
0x18008640f  mov     rbp, rdx
0x180086412  lea     rcx, [rbp+70h]
0x180086416  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x18008641b  nop
0x18008641c  xor     ebx, ebx
0x18008641e  mov     [rbp+30h], ebx
0x180086421  mov     rcx, [rbp+38h]
0x180086425  mov     [rbp+160h], ebx
0x18008642b  xorps   xmm0, xmm0
0x18008642e  movdqu  xmmword ptr [rbp+168h], xmm0
0x180086436  mov     rax, [rcx]
0x180086439  lea     rdx, [rbp+30h]
0x18008643d  mov     rax, [rax+38h]
0x180086441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086446  lea     r8, [rbp+160h]
0x18008644d  mov     edx, eax
0x18008644f  lea     rcx, [rbp+40h]
0x180086453  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180086458  lea     rdx, [rbp+160h]
0x18008645f  cmp     ebx, [rbp+30h]
0x180086462  jz      short loc_18008649A
0x180086464  mov     r8d, ebx
0x180086467  lea     rcx, [rbp+38h]
0x18008646b  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@45@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>,winrt::Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy>::GetAt(uint)
0x180086470  nop
0x180086471  mov     edx, [rbp+160h]
0x180086477  lea     rcx, [rbp+70h]
0x18008647b  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180086481  mov     rcx, rax
0x180086484  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180086489  nop
0x18008648a  lea     rcx, [rbp+160h]; this
0x180086491  call    ??1FeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy::~FeatureRollbackPolicy(void)
0x180086496  inc     ebx
0x180086498  jmp     short loc_180086458
0x18008649a  lea     rcx, [rbp+78h]
0x18008649e  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x1800864a3  lea     rax, [rbp+160h]
0x1800864aa  cmp     qword ptr [rbp+178h], 0Fh
0x1800864b2  cmova   rax, [rbp+160h]
0x1800864ba  mov     rcx, [rbp+198h]; this
0x1800864c1  mov     [rsp+48h+var_28], rax; char *
0x1800864c6  lea     r9, aRollbackFailed; "Rollback failed for features %s"
0x1800864cd  lea     r8, aShellOnecoreDe_8; "shell\\onecore\\desktopshellext\\lib\\r"...
0x1800864d4  mov     edx, 0ABh; void *
0x1800864d9  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x1800864de  lea     rcx, [rbp+160h]
0x1800864e5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800864ea  nop
0x1800864eb  lea     rcx, [rbp+70h]
0x1800864ef  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x1800864f4  nop
0x1800864f5  mov     rax, 0
0x1800864ff  add     rsp, 38h
0x180086503  pop     rbp
0x180086504  pop     rbx
0x180086505  retn
```
