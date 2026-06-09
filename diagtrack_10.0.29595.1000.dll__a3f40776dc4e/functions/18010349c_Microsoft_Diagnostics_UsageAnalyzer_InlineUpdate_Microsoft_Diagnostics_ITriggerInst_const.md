# Microsoft::Diagnostics::UsageAnalyzer::InlineUpdate(Microsoft::Diagnostics::ITriggerInst const &)

- ea: `0x18010349c`
- end: `0x180103a58`
- name: `?InlineUpdate@UsageAnalyzer@Diagnostics@Microsoft@@QEAAXAEBVITriggerInst@23@@Z`
- size: `1468`
- prototype: `void __fastcall(Microsoft::Diagnostics::UsageAnalyzer *__hidden this, const struct Microsoft::Diagnostics::ITriggerInst *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180182cb0`

## callees

- `0x18002e030`
- `0x180054a74`
- `0x1800552c0`
- `0x180055730`
- `0x18006d074`
- `0x1800788cc`
- `0x18007afd0`
- `0x18007d47c`
- `0x18010349c`
- `0x180134044`
- `0x1801a9494`
- `0x180300844`
- `0x1803011ac`
- `0x1803032b0`
- `0x180369010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180103586`
- `msvcp_win!_Mtx_unlock` at `0x1801037a3`
- `msvcp_win!_Mtx_unlock` at `0x180103586`
- `msvcp_win!_Mtx_unlock` at `0x1801037a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801037df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801039e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801037df`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1801039e3`

## string_xrefs

- `0x180103846`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x18010385e`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x180103876`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x180103891`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x1801038a9`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x1801038c4`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x1801038dc`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x1801039f8`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x180103a10`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x180103a2b`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`
- `0x180103a43`: `onecore\base\telemetry\utc\service\analysis\usageanalyzer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Microsoft::Diagnostics::UsageAnalyzer::InlineUpdate(
        Microsoft::Diagnostics::UsageAnalyzer *this,
        const struct Microsoft::Diagnostics::ITriggerInst *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rcx
  char *v6; // r14
  __int64 v7; // r15
  _QWORD *v8; // rax
  _QWORD *v9; // rcx
  char *v10; // r14
  __int64 v11; // r15
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  wil::details::in1diag3 *v14; // r10
  __int64 v15; // rax
  unsigned int v16; // edx
  wil::details::in1diag3 *v17; // r10
  int v18; // r15d
  __int64 v19; // rax
  unsigned int v20; // edx
  wil::details::in1diag3 *v21; // r10
  __int64 v22; // rbx
  __int64 v23; // rbx
  ULONGLONG TickCount64; // rax
  _BYTE *v25; // rax
  unsigned __int64 v26; // r9
  wil::details::in1diag3 *v27; // r10
  __int64 v28; // rax
  unsigned int v29; // edx
  wil::details::in1diag3 *v30; // r10
  struct Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord *v31; // rbx
  int v32[4]; // [rsp+20h] [rbp-40h] BYREF
  const wchar_t *v33; // [rsp+30h] [rbp-30h] BYREF
  __int64 v34; // [rsp+38h] [rbp-28h]
  const char *v35; // [rsp+40h] [rbp-20h] BYREF
  __int64 v36; // [rsp+48h] [rbp-18h]
  const char *v37; // [rsp+50h] [rbp-10h] BYREF
  __int64 v38; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  __int64 v40; // [rsp+A0h] [rbp+40h] BYREF
  char *v41; // [rsp+B0h] [rbp+50h]
  char *v42; // [rsp+B8h] [rbp+58h]

  if ( (unsigned __int8)std::_Atomic_storage<bool,1>::load((char *)this + 576, 5) )
  {
    v41 = (char *)this + 592;
    std::_Mutex_base::lock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 592));
    if ( !*(_BYTE *)((*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 120LL))(a2)
                   + 48) )
    {
      v33 = L"data";
      v34 = 4;
      v35 = (char *)a2 + 16;
      LODWORD(v36) = 0;
      JsonBuilder::find<>((char *)a2 + 16, v32, &v35, &v33);
      if ( !v32[2] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4F,
          (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
          (const char *)0x80070490LL,
          v32[0]);
      v4 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 80LL))(a2);
      v5 = *v4 - *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data1;
      if ( *v4 == *(_QWORD *)&Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data1 )
        v5 = v4[1] - *(_QWORD *)Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid.Data4;
      if ( !v5 )
      {
        if ( *((_QWORD *)this + 11) <= 7u )
          v6 = (char *)this + 64;
        else
          v6 = (char *)*((_QWORD *)this + 8);
        v7 = *((_QWORD *)this + 10);
        v8 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 120LL))(a2);
        if ( v8[5] <= 7u )
          v9 = v8 + 2;
        else
          v9 = (_QWORD *)v8[2];
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v9, v8[4], v6, v7) )
        {
          LODWORD(v33) = 0;
          v34 = 0;
          LODWORD(v40) = 0;
          v35 = L"InstanceId";
          v36 = 10;
          JsonBuilder::find<>((char *)a2 + 16, &v37, v32, &v35);
          if ( !(_DWORD)v38 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x58,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
              (const char *)0x80070490LL,
              v32[0]);
          if ( !(unsigned __int8)ConvertToJsonUInt_unsigned_long_(*(_QWORD *)v37 + 4LL * (unsigned int)v38, &v40) )
            wil::details::in1diag3::Throw_Hr(
              v27,
              (void *)0x59,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
              (const char *)0x8007070CLL,
              v32[0]);
          LODWORD(v33) = v40;
          v40 = 0;
          v37 = L"ProcessStartKey";
          v38 = 15;
          v28 = JsonBuilder::find<>((char *)a2 + 16, &v35, v32, &v37);
          v29 = *(_DWORD *)(v28 + 8);
          if ( !v29 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x5E,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
              (const char *)0x80070490LL,
              v32[0]);
          if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v28 + 4LL * v29, &v40) )
            wil::details::in1diag3::Throw_Hr(
              v30,
              (void *)0x5F,
              (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
              (const char *)0x8007070CLL,
              v32[0]);
          v34 = v40;
          v31 = Microsoft::Diagnostics::UsageAnalyzer::AcquireProcessRecord(this, (const struct ProcessKey *)&v33);
          if ( v31 )
            *((_QWORD *)v31 + 1) = GetTickCount64();
        }
        else
        {
          if ( *((_QWORD *)this + 15) <= 7u )
            v10 = (char *)this + 96;
          else
            v10 = (char *)*((_QWORD *)this + 12);
          v11 = *((_QWORD *)this + 14);
          v12 = (_QWORD *)(*(__int64 (__fastcall **)(const struct Microsoft::Diagnostics::ITriggerInst *))(*(_QWORD *)a2 + 120LL))(a2);
          if ( v12[5] <= 7u )
            v13 = v12 + 2;
          else
            v13 = (_QWORD *)v12[2];
          if ( (unsigned __int8)std::_Traits_equal<std::char_traits<wchar_t>>(v13, v12[4], v10, v11) )
          {
            v40 = 0;
            v37 = L"AppStateChange";
            v38 = 14;
            JsonBuilder::find<>((char *)a2 + 16, &v35, v32, &v37);
            if ( !(_DWORD)v36 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x6C,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                (const char *)0x80070490LL,
                v32[0]);
            if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(
                                     *(_QWORD *)v35 + 4LL * (unsigned int)v36,
                                     &v40) )
              wil::details::in1diag3::Throw_Hr(
                v14,
                (void *)0x6D,
                (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                (const char *)0x8007070CLL,
                v32[0]);
            if ( (_DWORD)v40 == 3 )
            {
              LODWORD(v40) = 0;
              v37 = L"InstanceId";
              v38 = 10;
              v15 = JsonBuilder::find<>((char *)a2 + 16, &v35, v32, &v37);
              v16 = *(_DWORD *)(v15 + 8);
              if ( !v16 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x75,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                  (const char *)0x80070490LL,
                  v32[0]);
              if ( !(unsigned __int8)ConvertToJsonUInt_unsigned_long_(**(_QWORD **)v15 + 4LL * v16, &v40) )
                wil::details::in1diag3::Throw_Hr(
                  v17,
                  (void *)0x76,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                  (const char *)0x8007070CLL,
                  v32[0]);
              v18 = v40;
              LODWORD(v35) = v40;
              v40 = 0;
              v37 = L"ProcessStartKey";
              v38 = 15;
              v19 = JsonBuilder::find<>((char *)a2 + 16, &v33, v32, &v37);
              v20 = *(_DWORD *)(v19 + 8);
              if ( !v20 )
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x7B,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                  (const char *)0x80070490LL,
                  v32[0]);
              if ( !(unsigned __int8)JsonImplementType<unsigned __int64>::ConvertTo(**(_QWORD **)v19 + 4LL * v20, &v40) )
                wil::details::in1diag3::Throw_Hr(
                  v21,
                  (void *)0x7C,
                  (unsigned int)"onecore\\base\\telemetry\\utc\\service\\analysis\\usageanalyzer.cpp",
                  (const char *)0x8007070CLL,
                  v32[0]);
              v22 = v40;
              v36 = v40;
              v42 = (char *)this + 736;
              std::_Mutex_base::lock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 736));
              std::_Hash<std::_Umap_traits<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord,std::_Uhash_compare<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessKeyHash,std::equal_to<ProcessKey>>,std::allocator<std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord>>,0>>::find(
                (char *)this + 672,
                &v40,
                &v35);
              if ( v22 != -1 || v18 != -1 )
              {
                v23 = v40;
                if ( v40 != *((_QWORD *)this + 85) )
                {
                  TickCount64 = GetTickCount64();
                  v25 = (_BYTE *)std::_Atomic_storage<BitTimePair64,8>::load((char *)this + 192, &v40, 5, TickCount64);
                  Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord::RecordUpdate(
                    (Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord *)(v23 + 32),
                    *v25 & 1,
                    v26);
                  *(_QWORD *)(v23 + 40) = 0;
                  if ( *((_DWORD *)this + 266) )
                  {
                    Microsoft::Diagnostics::UsageAnalyzer::AggregatePerProcessRecord((char *)this + 816, v23 + 16);
                    std::_Hash<std::_Umap_traits<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord,std::_Uhash_compare<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessKeyHash,std::equal_to<ProcessKey>>,std::allocator<std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord>>>>,0>(
                      (char *)this + 672,
                      &v40,
                      v23);
                  }
                }
              }
              _Mtx_unlock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 736));
            }
          }
        }
      }
    }
    _Mtx_unlock((Microsoft::Diagnostics::UsageAnalyzer *)((char *)this + 592));
  }
}

```

## disassembly

```asm
0x18010349c  mov     [rsp-38h+arg_8], rbx
0x1801034a1  push    rbp
0x1801034a2  push    rsi
0x1801034a3  push    rdi
0x1801034a4  push    r12
0x1801034a6  push    r13
0x1801034a8  push    r14
0x1801034aa  push    r15
0x1801034ac  mov     rbp, rsp
0x1801034af  sub     rsp, 60h
0x1801034b3  mov     rbx, rdx
0x1801034b6  mov     rdi, rcx
0x1801034b9  add     rcx, 240h
0x1801034c0  mov     edx, 5
0x1801034c5  call    ?load@?$_Atomic_storage@_N$00@std@@QEBA_NW4memory_order@2@@Z; std::_Atomic_storage<bool,1>::load(std::memory_order)
0x1801034ca  xor     r13d, r13d
0x1801034cd  test    al, al
0x1801034cf  jnz     short loc_1801034E9
0x1801034d1  mov     rbx, [rsp+60h+arg_8]
0x1801034d9  add     rsp, 60h
0x1801034dd  pop     r15
0x1801034df  pop     r14
0x1801034e1  pop     r13
0x1801034e3  pop     r12
0x1801034e5  pop     rdi
0x1801034e6  pop     rsi
0x1801034e7  pop     rbp
0x1801034e8  retn
0x1801034e9  lea     r12, [rdi+250h]
0x1801034f0  mov     [rbp+arg_10], r12
0x1801034f4  mov     rcx, r12; this
0x1801034f7  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1801034fc  nop
0x1801034fd  mov     rax, [rbx]
0x180103500  mov     rcx, rbx
0x180103503  mov     rax, [rax+78h]
0x180103507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010350c  cmp     [rax+30h], r13b
0x180103510  jnz     short loc_180103583
0x180103512  lea     rsi, [rbx+10h]
0x180103516  lea     rax, aData_0; "data"
0x18010351d  mov     [rbp+var_30], rax
0x180103521  mov     [rbp+var_28], 4
0x180103529  mov     [rbp+var_20], rsi
0x18010352d  mov     dword ptr [rbp+var_18], r13d
0x180103531  lea     r9, [rbp+var_30]
0x180103535  lea     r8, [rbp+var_20]
0x180103539  lea     rdx, [rbp+var_40]
0x18010353d  mov     rcx, rsi
0x180103540  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180103545  cmp     [rbp+var_38], r13d
0x180103549  setz    al
0x18010354c  mov     rcx, [rbp+38h]; this
0x180103550  test    al, al
0x180103552  jnz     loc_180103840
0x180103558  mov     rax, [rbx]
0x18010355b  mov     rcx, rbx
0x18010355e  mov     rax, [rax+50h]
0x180103562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180103567  mov     rcx, [rax]
0x18010356a  sub     rcx, qword ptr cs:?k_kernelTLProcessProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data1; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid ...
0x180103571  jnz     short loc_18010357E
0x180103573  mov     rcx, [rax+8]
0x180103577  sub     rcx, qword ptr cs:?k_kernelTLProcessProviderGuid@EventBasedMetadata@Diagnostics@Microsoft@@1U_GUID@@B.Data4; _GUID const Microsoft::Diagnostics::EventBasedMetadata::k_kernelTLProcessProviderGuid ...
0x18010357e  test    rcx, rcx
0x180103581  jz      short loc_180103591
0x180103583  mov     rcx, r12; _Mtx_t
0x180103586  call    cs:__imp__Mtx_unlock
0x18010358c  jmp     loc_1801034D1
0x180103591  cmp     qword ptr [rdi+58h], 7
0x180103596  jbe     loc_1801037AE
0x18010359c  mov     r14, [rdi+40h]
0x1801035a0  mov     r15, [rdi+50h]
0x1801035a4  mov     rax, [rbx]
0x1801035a7  mov     rcx, rbx
0x1801035aa  mov     rax, [rax+78h]
0x1801035ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801035b3  cmp     qword ptr [rax+28h], 7
0x1801035b8  jbe     loc_1801037B7
0x1801035be  mov     rcx, [rax+10h]
0x1801035c2  mov     r9, r15
0x1801035c5  mov     r8, r14
0x1801035c8  mov     rdx, [rax+20h]
0x1801035cc  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1801035d1  test    al, al
0x1801035d3  jnz     loc_1801038F1
0x1801035d9  cmp     qword ptr [rdi+78h], 7
0x1801035de  jbe     loc_1801037C0
0x1801035e4  mov     r14, [rdi+60h]
0x1801035e8  mov     r15, [rdi+70h]
0x1801035ec  mov     rax, [rbx]
0x1801035ef  mov     rcx, rbx
0x1801035f2  mov     rax, [rax+78h]
0x1801035f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801035fb  cmp     qword ptr [rax+28h], 7
0x180103600  jbe     loc_1801037C9
0x180103606  mov     rcx, [rax+10h]
0x18010360a  mov     r9, r15
0x18010360d  mov     r8, r14
0x180103610  mov     rdx, [rax+20h]
0x180103614  call    ??$_Traits_equal@U?$char_traits@_W@std@@@std@@YA_NQEB_W_K01@Z; std::_Traits_equal<std::char_traits<wchar_t>>(wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x180103619  test    al, al
0x18010361b  jz      loc_180103583
0x180103621  mov     [rbp+arg_0], r13
0x180103625  lea     rax, aAppstatechange; "AppStateChange"
0x18010362c  mov     [rbp+var_10], rax
0x180103630  mov     [rbp+var_8], 0Eh
0x180103638  lea     r9, [rbp+var_10]
0x18010363c  lea     r8, [rbp+var_40]
0x180103640  lea     rdx, [rbp+var_20]
0x180103644  mov     rcx, rsi
0x180103647  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x18010364c  mov     edx, dword ptr [rbp+var_18]
0x18010364f  test    edx, edx
0x180103651  setz    al
0x180103654  mov     rcx, [rbp+38h]; this
0x180103658  test    al, al
0x18010365a  jnz     loc_180103858
0x180103660  mov     r10, [rbp+38h]
0x180103664  mov     r8d, edx
0x180103667  mov     rax, [rbp+var_20]
0x18010366b  mov     rdx, [rax]
0x18010366e  lea     rcx, [rdx+r8*4]
0x180103672  lea     rdx, [rbp+arg_0]
0x180103676  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x18010367b  test    al, al
0x18010367d  jz      loc_180103870
0x180103683  cmp     dword ptr [rbp+arg_0], 3
0x180103687  jnz     loc_180103583
0x18010368d  mov     dword ptr [rbp+arg_0], r13d
0x180103691  lea     rax, aInstanceid_0; "InstanceId"
0x180103698  mov     [rbp+var_10], rax
0x18010369c  mov     [rbp+var_8], 0Ah
0x1801036a4  lea     r9, [rbp+var_10]
0x1801036a8  lea     r8, [rbp+var_40]
0x1801036ac  lea     rdx, [rbp+var_20]
0x1801036b0  mov     rcx, rsi
0x1801036b3  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x1801036b8  movups  xmm1, xmmword ptr [rax]
0x1801036bb  mov     edx, [rax+8]
0x1801036be  test    edx, edx
0x1801036c0  setz    al
0x1801036c3  mov     rcx, [rbp+38h]; this
0x1801036c7  test    al, al
0x1801036c9  jnz     loc_18010388B
0x1801036cf  mov     r10, [rbp+38h]
0x1801036d3  mov     r8d, edx
0x1801036d6  movq    rax, xmm1
0x1801036db  mov     rdx, [rax]
0x1801036de  lea     rcx, [rdx+r8*4]
0x1801036e2  lea     rdx, [rbp+arg_0]
0x1801036e6  call    ConvertToJsonUInt_unsigned_long_
0x1801036eb  test    al, al
0x1801036ed  jz      loc_1801038A3
0x1801036f3  mov     r15d, dword ptr [rbp+arg_0]
0x1801036f7  mov     dword ptr [rbp+var_20], r15d
0x1801036fb  mov     [rbp+arg_0], r13
0x1801036ff  lea     rax, aProcessstartke; "ProcessStartKey"
0x180103706  mov     [rbp+var_10], rax
0x18010370a  mov     [rbp+var_8], 0Fh
0x180103712  lea     r9, [rbp+var_10]
0x180103716  lea     r8, [rbp+var_40]
0x18010371a  lea     rdx, [rbp+var_30]
0x18010371e  mov     rcx, rsi
0x180103721  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180103726  movups  xmm1, xmmword ptr [rax]
0x180103729  mov     edx, [rax+8]
0x18010372c  test    edx, edx
0x18010372e  setz    al
0x180103731  mov     rcx, [rbp+38h]; this
0x180103735  test    al, al
0x180103737  jnz     loc_1801038BE
0x18010373d  mov     r10, [rbp+38h]
0x180103741  mov     r8d, edx
0x180103744  movq    rax, xmm1
0x180103749  mov     rdx, [rax]
0x18010374c  lea     rcx, [rdx+r8*4]
0x180103750  lea     rdx, [rbp+arg_0]
0x180103754  call    ?ConvertTo@?$JsonImplementType@_K@@SA_NAEBVJsonValue@@AEA_K@Z; JsonImplementType<unsigned __int64>::ConvertTo(JsonValue const &,unsigned __int64 &)
0x180103759  test    al, al
0x18010375b  jz      loc_1801038D6
0x180103761  mov     rbx, [rbp+arg_0]
0x180103765  mov     [rbp+var_18], rbx
0x180103769  lea     rsi, [rdi+2E0h]
0x180103770  mov     [rbp+arg_18], rsi
0x180103774  mov     rcx, rsi; this
0x180103777  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18010377c  nop
0x18010377d  lea     r14, [rdi+2A0h]
0x180103784  lea     r8, [rbp+var_20]
0x180103788  lea     rdx, [rbp+arg_0]
0x18010378c  mov     rcx, r14
0x18010378f  call    ?find@?$_Hash@V?$_Umap_traits@UProcessKey@@UProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@V?$_Uhash_compare@UProcessKey@@UProcessKeyHash@UsageAnalyzer@Diagnostics@Microsoft@@U?$equal_to@UProcessKey@@@std@@@std@@V?$allocator@U?$pair@$$CBUProcessKey@@UProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUProcessKey@@UProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@@std@@@std@@@std@@@2@AEBUProcessKey@@@Z; std::_Hash<std::_Umap_traits<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord,std::_Uhash_compare<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessKeyHash,std::equal_to<ProcessKey>>,std::allocator<std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord>>,0>>::find(ProcessKey const &)
0x180103794  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180103798  jnz     short loc_1801037D2
0x18010379a  cmp     r15d, 0FFFFFFFFh
0x18010379e  jnz     short loc_1801037D2
0x1801037a0  mov     rcx, rsi; _Mtx_t
0x1801037a3  call    cs:__imp__Mtx_unlock
0x1801037a9  jmp     loc_180103583
0x1801037ae  lea     r14, [rdi+40h]
0x1801037b2  jmp     loc_1801035A0
0x1801037b7  lea     rcx, [rax+10h]
0x1801037bb  jmp     loc_1801035C2
0x1801037c0  lea     r14, [rdi+60h]
0x1801037c4  jmp     loc_1801035E8
0x1801037c9  lea     rcx, [rax+10h]
0x1801037cd  jmp     loc_18010360A
0x1801037d2  mov     rbx, [rbp+arg_0]
0x1801037d6  cmp     rbx, [rdi+2A8h]
0x1801037dd  jz      short loc_1801037A0
0x1801037df  call    cs:__imp_GetTickCount64
0x1801037e5  mov     r9, rax
0x1801037e8  lea     rcx, [rdi+0C0h]
0x1801037ef  mov     r8d, 5
0x1801037f5  lea     rdx, [rbp+arg_0]
0x1801037f9  call    ?load@?$_Atomic_storage@UBitTimePair64@@$07@std@@QEBA?AUBitTimePair64@@W4memory_order@2@@Z; std::_Atomic_storage<BitTimePair64,8>::load(std::memory_order)
0x1801037fe  mov     dl, [rax]
0x180103800  and     dl, 1; bool
0x180103803  lea     rcx, [rbx+20h]; this
0x180103807  mov     r8, r9; unsigned __int64
0x18010380a  call    ?RecordUpdate@ProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@QEBAX_N_K@Z; Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord::RecordUpdate(bool,unsigned __int64)
0x18010380f  mov     [rbx+28h], r13
0x180103813  cmp     [rdi+428h], r13d
0x18010381a  jz      short loc_1801037A0
0x18010381c  lea     rcx, [rdi+330h]
0x180103823  lea     rdx, [rbx+10h]
0x180103827  call    ?AggregatePerProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@CAXAEAUAggregatedAsimovData@123@AEBU?$pair@$$CBUProcessKey@@UProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@@std@@@Z; Microsoft::Diagnostics::UsageAnalyzer::AggregatePerProcessRecord(Microsoft::Diagnostics::UsageAnalyzer::AggregatedAsimovData &,std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord> const &)
0x18010382c  mov     r8, rbx
0x18010382f  lea     rdx, [rbp+arg_0]
0x180103833  mov     rcx, r14
0x180103836  call    ??$erase@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUProcessKey@@UProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@@std@@@std@@@std@@@std@@$0A@@?$_Hash@V?$_Umap_traits@UProcessKey@@UProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@V?$_Uhash_compare@UProcessKey@@UProcessKeyHash@UsageAnalyzer@Diagnostics@Microsoft@@U?$equal_to@UProcessKey@@@std@@@std@@V?$allocator@U?$pair@$$CBUProcessKey@@UProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@@std@@@7@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBUProcessKey@@UProcessRecord@UsageAnalyzer@Diagnostics@Microsoft@@@std@@@std@@@std@@@1@V21@@Z; std::_Hash<std::_Umap_traits<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord,std::_Uhash_compare<ProcessKey,Microsoft::Diagnostics::UsageAnalyzer::ProcessKeyHash,std::equal_to<ProcessKey>>,std::allocator<std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord>>,0>>::erase<std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord>>>>,0>(std::_List_iterator<std::_List_val<std::_List_simple_types<std::pair<ProcessKey const,Microsoft::Diagnostics::UsageAnalyzer::ProcessRecord>>>>)
0x18010383b  jmp     loc_1801037A0
0x180103840  mov     r9d, 80070490h; char *
0x180103846  lea     r8, aOnecoreBaseTel_151; "onecore\\base\\telemetry\\utc\\service"...
0x18010384d  mov     edx, 4Fh ; 'O'; void *
0x180103852  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103858  mov     r9d, 80070490h; char *
0x18010385e  lea     r8, aOnecoreBaseTel_151; "onecore\\base\\telemetry\\utc\\service"...
0x180103865  mov     edx, 6Ch ; 'l'; void *
0x18010386a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180103870  mov     r9d, 8007070Ch; char *
0x180103876  lea     r8, aOnecoreBaseTel_151; "onecore\\base\\telemetry\\utc\\service"...
0x18010387d  mov     edx, 6Dh ; 'm'; void *
0x180103882  mov     rcx, r10; this
0x180103885  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010388b  mov     r9d, 80070490h; char *
0x180103891  lea     r8, aOnecoreBaseTel_151; "onecore\\base\\telemetry\\utc\\service"...
0x180103898  mov     edx, 75h ; 'u'; void *
0x18010389d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801038a3  mov     r9d, 8007070Ch; char *
0x1801038a9  lea     r8, aOnecoreBaseTel_151; "onecore\\base\\telemetry\\utc\\service"...
0x1801038b0  mov     edx, 76h ; 'v'; void *
0x1801038b5  mov     rcx, r10; this
0x1801038b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801038be  mov     r9d, 80070490h; char *
0x1801038c4  lea     r8, aOnecoreBaseTel_151; "onecore\\base\\telemetry\\utc\\service"...
0x1801038cb  mov     edx, 7Bh ; '{'; void *
0x1801038d0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801038d6  mov     r9d, 8007070Ch; char *
0x1801038dc  lea     r8, aOnecoreBaseTel_151; "onecore\\base\\telemetry\\utc\\service"...
0x1801038e3  mov     edx, 7Ch ; '|'; void *
0x1801038e8  mov     rcx, r10; this
0x1801038eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801038f1  mov     dword ptr [rbp+var_30], r13d
0x1801038f5  mov     [rbp+var_28], r13
0x1801038f9  mov     dword ptr [rbp+arg_0], r13d
0x1801038fd  lea     rax, aInstanceid_0; "InstanceId"
0x180103904  mov     [rbp+var_20], rax
0x180103908  mov     [rbp+var_18], 0Ah
0x180103910  lea     r9, [rbp+var_20]
0x180103914  lea     r8, [rbp+var_40]
0x180103918  lea     rdx, [rbp+var_10]
0x18010391c  mov     rcx, rsi
0x18010391f  call    ??$find@$$V@JsonBuilder@@QEBA?AVJsonConstIterator@@AEBV1@AEBV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; JsonBuilder::find<>(JsonConstIterator const &,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>> const &)
0x180103924  mov     edx, dword ptr [rbp+var_8]
0x180103927  test    edx, edx
0x180103929  setz    al
0x18010392c  mov     rcx, [rbp+38h]; this
0x180103930  test    al, al
0x180103932  jnz     loc_1801039F2
0x180103938  mov     r10, [rbp+38h]
0x18010393c  mov     r8d, edx
0x18010393f  mov     rax, [rbp+var_10]
0x180103943  mov     rdx, [rax]
0x180103946  lea     rcx, [rdx+r8*4]
0x18010394a  lea     rdx, [rbp+arg_0]
0x18010394e  call    ConvertToJsonUInt_unsigned_long_
0x180103953  test    al, al
0x180103955  jz      loc_180103A0A
0x18010395b  mov     eax, dword ptr [rbp+arg_0]
0x18010395e  mov     dword ptr [rbp+var_30], eax
0x180103961  mov     [rbp+arg_0], r13
0x180103965  lea     rax, aProcessstartke; "ProcessStartKey"
0x18010396c  mov     [rbp+var_10], rax
0x180103970  mov     [rbp+var_8], 0Fh
0x180103978  lea     r9, [rbp+var_10]
0x18010397c  lea     r8, [rbp+var_40]
0x180103980  lea     rdx, [rbp+var_20]
0x180103984  mov     rcx, rsi
  ... truncated ...
```
