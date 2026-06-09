# PolicyManager::ParseJsonPoliciesRef(winrt::Windows::Internal::Flighting::FeatureConfiguration::FeatureRollbackPolicy &)

- ea: `0x18007aaf0`
- end: `0x18007af6f`
- name: `?ParseJsonPoliciesRef@PolicyManager@@SA?AV?$vector@URollbackPolicy@@V?$allocator@URollbackPolicy@@@std@@@std@@AEAUFeatureRollbackPolicy@FeatureConfiguration@Flighting@Internal@Windows@winrt@@@Z`
- size: `1151`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18007a7c8`

## callees

- `0x180014114`
- `0x18001be24`
- `0x18001bed0`
- `0x180021690`
- `0x180023bbc`
- `0x180024684`
- `0x18002a3d0`
- `0x1800582f4`
- `0x180060d94`
- `0x18006d390`
- `0x18007a100`
- `0x18007a3b0`
- `0x18007a428`
- `0x18007a4c8`
- `0x18007a65c`
- `0x18007a6b0`
- `0x18007a704`
- `0x18007a768`
- `0x18007aa38`
- `0x18007aaf0`
- `0x18007af78`
- `0x18007b034`
- `0x18007b0f8`

## string_xrefs

- `0x18007ab86`: `shell\onecore\desktopshellext\lib\rollbackpolicy.cpp`
- `0x18007ac50`: `shell\onecore\desktopshellext\lib\rollbackpolicy.cpp`
- `0x18007aeba`: `shell\onecore\desktopshellext\lib\rollbackpolicy.cpp`
- `0x18007abe6`: `Feature %u is missing rollback policies: %s`
- `0x18007ab7b`: `Feature %u has malformed rollback policy %s`
- `0x18007aea8`: `Feature %u has malformed TIP policy json: %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall PolicyManager::ParseJsonPoliciesRef(_QWORD *a1, __int64 a2)
{
  const unsigned __int16 *v4; // rax
  __int64 *Array; // rsi
  __int64 v6; // rcx
  unsigned int v7; // esi
  int v8; // r12d
  int NamedNumber; // r14d
  int v10; // r15d
  double v11; // xmm0_8
  __int64 v12; // rdx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  char *v18; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v19; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v20; // [rsp+30h] [rbp-D0h]
  _BYTE v21[8]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v22[8]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v24; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+68h] [rbp-98h]
  _BYTE v26[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[8]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v28[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v29[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[32]; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD v32[2]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v28[0] = a1;
  v24 = 0;
  v25 = 0;
  winrt::Windows::Data::Json::JsonArray::JsonArray((winrt::Windows::Data::Json::JsonArray *)&v23);
  winrt::Windows::Data::Json::JsonObject::JsonObject((winrt::Windows::Data::Json::JsonObject *)v22);
  *(_QWORD *)&v32[0] = *(_QWORD *)(a2 + 16);
  if ( !(unsigned __int8)winrt::Windows::Data::Json::JsonObject::TryParse(
                           (const struct winrt::param::hstring *)v32,
                           (struct winrt::Windows::Data::Json::JsonObject *)v22) )
  {
    v19 = winrt::hstring::c_str((winrt::hstring *)(a2 + 16));
    LODWORD(v18) = *(_DWORD *)a2;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x46,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\rollbackpolicy.cpp",
      (const char *)0x80004005LL,
      (int)"Feature %u has malformed rollback policy %s",
      v18,
      v19);
LABEL_3:
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
    goto LABEL_28;
  }
  winrt::param::hstring::hstring((winrt::param::hstring *)v32, L"policy");
  if ( !(unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                           v22,
                           v32) )
  {
    v20 = winrt::hstring::c_str((winrt::hstring *)(a2 + 16));
    LODWORD(v18) = *(_DWORD *)a2;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x4C,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\rollbackpolicy.cpp",
      (const char *)0x80004005LL,
      (int)"Feature %u is missing rollback policies: %s",
      v18,
      v20);
    goto LABEL_3;
  }
  winrt::param::hstring::hstring((winrt::param::hstring *)v31, L"policy");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedValue(
    v22,
    v26,
    v31);
  if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(v26) == 4 )
  {
    Array = (__int64 *)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetArray(
                         v26,
                         v27);
    if ( &v23 != Array )
    {
      if ( v23 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v23);
      v6 = *Array;
      *Array = 0;
      v23 = v6;
    }
    winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)v27);
    *(_BYTE *)(a2 + 24) = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v32, L"telemetryOnly");
    if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                            v22,
                            v32) )
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)v32, L"telemetryOnly");
      winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedValue(
        v22,
        v21,
        v32);
      if ( (unsigned int)winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(v21) == 1 )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v30, L"telemetryOnly");
        *(_BYTE *)(a2 + 24) = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(
                                v22,
                                v30);
      }
      winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)v21);
    }
    v7 = 0;
    v8 = winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(&v23);
    while ( v7 != v8 )
    {
      winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(
        &v23,
        v27,
        v7);
      v32[0] = 0;
      winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(v27, v21);
      winrt::param::hstring::hstring((winrt::param::hstring *)v30, L"tip");
      if ( (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                              v21,
                              v30)
        && (winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"count"),
            (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                               v21,
                               v29))
        && (winrt::param::hstring::hstring((winrt::param::hstring *)v30, L"passrate"),
            (unsigned __int8)winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
                               v21,
                               v30)) )
      {
        winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"tip");
        NamedNumber = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                             v21,
                             v29);
        LODWORD(v32[0]) = NamedNumber;
        winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"count");
        v10 = (int)winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                     v21,
                     v29);
        DWORD1(v32[0]) = v10;
        winrt::param::hstring::hstring((winrt::param::hstring *)v29, L"passrate");
        v11 = winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(
                v21,
                v29);
        *((double *)v32 + 1) = v11;
        v12 = *((_QWORD *)&v24 + 1);
        if ( *((_QWORD *)&v24 + 1) == v25 )
        {
          std::vector<RollbackPolicy>::_Emplace_reallocate<RollbackPolicy const &>(&v24, *((_QWORD *)&v24 + 1), v32);
        }
        else
        {
          **((_DWORD **)&v24 + 1) = NamedNumber;
          *(_DWORD *)(v12 + 4) = v10;
          *(double *)(v12 + 8) = v11;
          *((_QWORD *)&v24 + 1) += 16LL;
        }
      }
      else
      {
        v13 = (_QWORD *)winrt::impl::consume_Windows_Foundation_IStringable<winrt::Windows::Data::Json::JsonObject>::ToString(
                          v21,
                          v28);
        LODWORD(v18) = *(_DWORD *)a2;
        wil::details::in1diag3::Log_HrMsg(
          retaddr,
          (void *)0x71,
          (unsigned int)"shell\\onecore\\desktopshellext\\lib\\rollbackpolicy.cpp",
          (const char *)0x80004005LL,
          (int)"Feature %u has malformed TIP policy json: %s",
          v18,
          *v13);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v28);
      }
      winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)v21);
      winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)v27);
      ++v7;
    }
    v14 = v25;
    v25 = 0;
    v15 = *((_QWORD *)&v24 + 1);
    v16 = v24;
    v24 = 0u;
    *a1 = v16;
    a1[1] = v15;
    a1[2] = v14;
  }
  else
  {
    v4 = winrt::hstring::c_str((winrt::hstring *)(a2 + 16));
    LODWORD(v18) = *(_DWORD *)a2;
    wil::details::in1diag3::Log_HrMsg(
      retaddr,
      (void *)0x53,
      (unsigned int)"shell\\onecore\\desktopshellext\\lib\\rollbackpolicy.cpp",
      (const char *)0x80004005LL,
      (int)"Feature %u has malformed policies array: %s",
      v18,
      v4);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)v26);
LABEL_28:
  winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)v22);
  winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager((winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager *)&v23);
  std::vector<RollbackPolicy>::_Tidy(&v24);
  return a1;
}

```

## disassembly

```asm
0x18007aaf0  mov     [rsp-8+arg_10], rbx
0x18007aaf5  push    rbp
0x18007aaf6  push    rsi
0x18007aaf7  push    rdi
0x18007aaf8  push    r12
0x18007aafa  push    r13
0x18007aafc  push    r14
0x18007aafe  push    r15
0x18007ab00  lea     rbp, [rsp-20h]
0x18007ab05  sub     rsp, 120h
0x18007ab0c  mov     rax, cs:__security_cookie
0x18007ab13  xor     rax, rsp
0x18007ab16  mov     [rbp+50h+var_40], rax
0x18007ab1a  mov     rdi, rdx
0x18007ab1d  mov     rbx, rcx
0x18007ab20  mov     [rbp+50h+var_D0], rcx
0x18007ab24  xor     r13d, r13d
0x18007ab27  xorps   xmm0, xmm0
0x18007ab2a  movdqu  [rsp+150h+var_F8], xmm0
0x18007ab30  mov     [rsp+150h+var_E8], r13
0x18007ab35  lea     rcx, [rsp+150h+var_100]; this
0x18007ab3a  call    ??0JsonArray@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonArray::JsonArray(void)
0x18007ab3f  nop
0x18007ab40  lea     rcx, [rsp+150h+var_108]; this
0x18007ab45  call    ??0JsonObject@Json@Data@Windows@winrt@@QEAA@XZ; winrt::Windows::Data::Json::JsonObject::JsonObject(void)
0x18007ab4a  nop
0x18007ab4b  lea     rsi, [rdi+10h]
0x18007ab4f  mov     rax, [rsi]
0x18007ab52  mov     qword ptr [rbp+50h+var_60], rax
0x18007ab56  lea     rdx, [rsp+150h+var_108]; struct winrt::Windows::Data::Json::JsonObject *
0x18007ab5b  lea     rcx, [rbp+50h+var_60]; struct winrt::param::hstring *
0x18007ab5f  call    ?TryParse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@AEAU12345@@Z; winrt::Windows::Data::Json::JsonObject::TryParse(winrt::param::hstring const &,winrt::Windows::Data::Json::JsonObject &)
0x18007ab64  test    al, al
0x18007ab66  jnz     short loc_18007ABB1
0x18007ab68  mov     rcx, rsi; this
0x18007ab6b  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18007ab70  mov     [rsp+150h+var_120], rax
0x18007ab75  mov     eax, [rdi]
0x18007ab77  mov     dword ptr [rsp+150h+var_128], eax; char *
0x18007ab7b  lea     rax, aFeatureUHasMal; "Feature %u has malformed rollback polic"...
0x18007ab82  lea     edx, [r13+46h]; void *
0x18007ab86  lea     r8, aShellOnecoreDe_3; "shell\\onecore\\desktopshellext\\lib\\r"...
0x18007ab8d  mov     r9d, 80004005h; char *
0x18007ab93  mov     qword ptr [rsp+150h+var_130], rax; int
0x18007ab98  mov     rcx, [rbp+58h]; this
0x18007ab9c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007aba1  mov     [rbx], r13
0x18007aba4  mov     [rbx+8], r13
0x18007aba8  mov     [rbx+10h], r13
0x18007abac  jmp     loc_18007AF25
0x18007abb1  lea     rdx, aPolicy; "policy"
0x18007abb8  lea     rcx, [rbp+50h+var_60]; this
0x18007abbc  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007abc1  lea     rdx, [rbp+50h+var_60]
0x18007abc5  lea     rcx, [rsp+150h+var_108]
0x18007abca  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18007abcf  test    al, al
0x18007abd1  jnz     short loc_18007ABF4
0x18007abd3  mov     rcx, rsi; this
0x18007abd6  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18007abdb  mov     [rsp+150h+var_120], rax
0x18007abe0  mov     eax, [rdi]
0x18007abe2  mov     dword ptr [rsp+150h+var_128], eax
0x18007abe6  lea     rax, aFeatureUIsMiss; "Feature %u is missing rollback policies"...
0x18007abed  mov     edx, 4Ch ; 'L'
0x18007abf2  jmp     short loc_18007AB86
0x18007abf4  lea     rdx, aPolicy; "policy"
0x18007abfb  lea     rcx, [rbp+50h+var_80]; this
0x18007abff  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007ac04  lea     r8, [rbp+50h+var_80]
0x18007ac08  lea     rdx, [rsp+150h+var_E0]
0x18007ac0d  lea     rcx, [rsp+150h+var_108]
0x18007ac12  call    ?GetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedValue(winrt::param::hstring const &)
0x18007ac17  nop
0x18007ac18  lea     rcx, [rsp+150h+var_E0]
0x18007ac1d  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x18007ac22  cmp     eax, 4
0x18007ac25  jz      short loc_18007AC71
0x18007ac27  mov     rcx, rsi; this
0x18007ac2a  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x18007ac2f  mov     rcx, [rbp+58h]; this
0x18007ac33  mov     [rsp+150h+var_120], rax
0x18007ac38  mov     eax, [rdi]
0x18007ac3a  mov     dword ptr [rsp+150h+var_128], eax; char *
0x18007ac3e  lea     rax, aFeatureUHasMal_1; "Feature %u has malformed policies array"...
0x18007ac45  mov     qword ptr [rsp+150h+var_130], rax; int
0x18007ac4a  mov     r9d, 80004005h; char *
0x18007ac50  lea     r8, aShellOnecoreDe_3; "shell\\onecore\\desktopshellext\\lib\\r"...
0x18007ac57  mov     edx, 53h ; 'S'; void *
0x18007ac5c  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007ac61  mov     [rbx], r13
0x18007ac64  mov     [rbx+8], r13
0x18007ac68  mov     [rbx+10h], r13
0x18007ac6c  jmp     loc_18007AF1A
0x18007ac71  lea     rdx, [rsp+150h+var_D8]
0x18007ac76  lea     rcx, [rsp+150h+var_E0]
0x18007ac7b  call    ?GetArray@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetArray(void)
0x18007ac80  mov     rsi, rax
0x18007ac83  lea     rax, [rsp+150h+var_100]
0x18007ac88  cmp     rax, rsi
0x18007ac8b  jz      short loc_18007ACA9
0x18007ac8d  cmp     [rsp+150h+var_100], r13
0x18007ac92  jz      short loc_18007AC9E
0x18007ac94  lea     rcx, [rsp+150h+var_100]
0x18007ac99  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18007ac9e  mov     rcx, [rsi]
0x18007aca1  mov     [rsi], r13
0x18007aca4  mov     [rsp+150h+var_100], rcx
0x18007aca9  lea     rcx, [rsp+150h+var_D8]; this
0x18007acae  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x18007acb3  mov     [rdi+18h], r13b
0x18007acb7  lea     rsi, aTelemetryonly; "telemetryOnly"
0x18007acbe  mov     rdx, rsi; unsigned __int16 *
0x18007acc1  lea     rcx, [rbp+50h+var_60]; this
0x18007acc5  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007acca  lea     rdx, [rbp+50h+var_60]
0x18007acce  lea     rcx, [rsp+150h+var_108]
0x18007acd3  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18007acd8  test    al, al
0x18007acda  jz      short loc_18007AD32
0x18007acdc  mov     rdx, rsi; unsigned __int16 *
0x18007acdf  lea     rcx, [rbp+50h+var_60]; this
0x18007ace3  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007ace8  lea     r8, [rbp+50h+var_60]
0x18007acec  lea     rdx, [rsp+150h+var_110]
0x18007acf1  lea     rcx, [rsp+150h+var_108]
0x18007acf6  call    ?GetNamedValue@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedValue(winrt::param::hstring const &)
0x18007acfb  nop
0x18007acfc  lea     rcx, [rsp+150h+var_110]
0x18007ad01  call    ?ValueType@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::ValueType(void)
0x18007ad06  cmp     eax, 1
0x18007ad09  jnz     short loc_18007AD28
0x18007ad0b  mov     rdx, rsi; unsigned __int16 *
0x18007ad0e  lea     rcx, [rbp+50h+var_A0]; this
0x18007ad12  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007ad17  lea     rdx, [rbp+50h+var_A0]
0x18007ad1b  lea     rcx, [rsp+150h+var_108]
0x18007ad20  call    ?GetNamedBoolean@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedBoolean(winrt::param::hstring const &)
0x18007ad25  mov     [rdi+18h], al
0x18007ad28  lea     rcx, [rsp+150h+var_110]; this
0x18007ad2d  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x18007ad32  mov     esi, r13d
0x18007ad35  lea     rcx, [rsp+150h+var_100]
0x18007ad3a  call    ?Size@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::Size(void)
0x18007ad3f  mov     r12d, eax
0x18007ad42  cmp     esi, r12d
0x18007ad45  jz      loc_18007AEF1
0x18007ad4b  mov     r8d, esi
0x18007ad4e  lea     rdx, [rsp+150h+var_D8]
0x18007ad53  lea     rcx, [rsp+150h+var_100]
0x18007ad58  call    ?GetAt@?$consume_Windows_Foundation_Collections_IVector@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@I@Z; winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::GetAt(uint)
0x18007ad5d  nop
0x18007ad5e  xorps   xmm0, xmm0
0x18007ad61  movups  [rbp+50h+var_60], xmm0
0x18007ad65  lea     rdx, [rsp+150h+var_110]
0x18007ad6a  lea     rcx, [rsp+150h+var_D8]
0x18007ad6f  call    ?GetObjectW@?$consume_Windows_Data_Json_IJsonValue@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonValue>::GetObjectW(void)
0x18007ad74  nop
0x18007ad75  lea     rdx, aTip; "tip"
0x18007ad7c  lea     rcx, [rbp+50h+var_A0]; this
0x18007ad80  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007ad85  lea     rdx, [rbp+50h+var_A0]
0x18007ad89  lea     rcx, [rsp+150h+var_110]
0x18007ad8e  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18007ad93  test    al, al
0x18007ad95  jz      loc_18007AE88
0x18007ad9b  lea     rdx, aCount; "count"
0x18007ada2  lea     rcx, [rbp+50h+var_C0]; this
0x18007ada6  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007adab  lea     rdx, [rbp+50h+var_C0]
0x18007adaf  lea     rcx, [rsp+150h+var_110]
0x18007adb4  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18007adb9  test    al, al
0x18007adbb  jz      loc_18007AE88
0x18007adc1  lea     rdx, aPassrate; "passrate"
0x18007adc8  lea     rcx, [rbp+50h+var_A0]; this
0x18007adcc  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007add1  lea     rdx, [rbp+50h+var_A0]
0x18007add5  lea     rcx, [rsp+150h+var_110]
0x18007adda  call    ?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)
0x18007addf  test    al, al
0x18007ade1  jz      loc_18007AE88
0x18007ade7  lea     rdx, aTip; "tip"
0x18007adee  lea     rcx, [rbp+50h+var_C0]; this
0x18007adf2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007adf7  lea     rdx, [rbp+50h+var_C0]
0x18007adfb  lea     rcx, [rsp+150h+var_110]
0x18007ae00  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18007ae05  cvttsd2si r14, xmm0
0x18007ae0a  mov     dword ptr [rbp+50h+var_60], r14d
0x18007ae0e  lea     rdx, aCount; "count"
0x18007ae15  lea     rcx, [rbp+50h+var_C0]; this
0x18007ae19  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007ae1e  lea     rdx, [rbp+50h+var_C0]
0x18007ae22  lea     rcx, [rsp+150h+var_110]
0x18007ae27  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18007ae2c  cvttsd2si r15, xmm0
0x18007ae31  mov     dword ptr [rbp+50h+var_60+4], r15d
0x18007ae35  lea     rdx, aPassrate; "passrate"
0x18007ae3c  lea     rcx, [rbp+50h+var_C0]; this
0x18007ae40  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18007ae45  lea     rdx, [rbp+50h+var_C0]
0x18007ae49  lea     rcx, [rsp+150h+var_110]
0x18007ae4e  call    ?GetNamedNumber@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedNumber(winrt::param::hstring const &)
0x18007ae53  movsd   qword ptr [rbp+50h+var_60+8], xmm0
0x18007ae58  mov     rdx, qword ptr [rsp+150h+var_F8+8]
0x18007ae5d  cmp     rdx, [rsp+150h+var_E8]
0x18007ae62  jz      short loc_18007AE78
0x18007ae64  mov     [rdx], r14d
0x18007ae67  mov     [rdx+4], r15d
0x18007ae6b  movsd   qword ptr [rdx+8], xmm0
0x18007ae70  add     qword ptr [rsp+150h+var_F8+8], 10h
0x18007ae76  jmp     short loc_18007AED5
0x18007ae78  lea     r8, [rbp+50h+var_60]
0x18007ae7c  lea     rcx, [rsp+150h+var_F8]
0x18007ae81  call    ??$_Emplace_reallocate@AEBURollbackPolicy@@@?$vector@URollbackPolicy@@V?$allocator@URollbackPolicy@@@std@@@std@@AEAAPEAURollbackPolicy@@QEAU2@AEBU2@@Z; std::vector<RollbackPolicy>::_Emplace_reallocate<RollbackPolicy const &>(RollbackPolicy * const,RollbackPolicy const &)
0x18007ae86  jmp     short loc_18007AED5
0x18007ae88  lea     rdx, [rbp+50h+var_D0]
0x18007ae8c  lea     rcx, [rsp+150h+var_110]
0x18007ae91  call    ?ToString@?$consume_Windows_Foundation_IStringable@UJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IStringable<winrt::Windows::Data::Json::JsonObject>::ToString(void)
0x18007ae96  mov     rax, [rax]
0x18007ae99  mov     rcx, [rbp+58h]; this
0x18007ae9d  mov     [rsp+150h+var_120], rax
0x18007aea2  mov     eax, [rdi]
0x18007aea4  mov     dword ptr [rsp+150h+var_128], eax; char *
0x18007aea8  lea     rax, aFeatureUHasMal_0; "Feature %u has malformed TIP policy jso"...
0x18007aeaf  mov     qword ptr [rsp+150h+var_130], rax; int
0x18007aeb4  mov     r9d, 80004005h; char *
0x18007aeba  lea     r8, aShellOnecoreDe_3; "shell\\onecore\\desktopshellext\\lib\\r"...
0x18007aec1  mov     edx, 71h ; 'q'; void *
0x18007aec6  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18007aecb  lea     rcx, [rbp+50h+var_D0]
0x18007aecf  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x18007aed4  nop
0x18007aed5  lea     rcx, [rsp+150h+var_110]; this
0x18007aeda  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x18007aedf  nop
0x18007aee0  lea     rcx, [rsp+150h+var_D8]; this
0x18007aee5  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x18007aeea  inc     esi
0x18007aeec  jmp     loc_18007AD42
0x18007aef1  mov     rdx, [rsp+150h+var_E8]
0x18007aef6  mov     [rsp+150h+var_E8], r13
0x18007aefb  mov     rcx, qword ptr [rsp+150h+var_F8+8]
0x18007af00  mov     qword ptr [rsp+150h+var_F8+8], r13
0x18007af05  mov     rax, qword ptr [rsp+150h+var_F8]
0x18007af0a  mov     qword ptr [rsp+150h+var_F8], r13
0x18007af0f  mov     [rbx], rax
0x18007af12  mov     [rbx+8], rcx
0x18007af16  mov     [rbx+10h], rdx
0x18007af1a  lea     rcx, [rsp+150h+var_E0]; this
0x18007af1f  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x18007af24  nop
0x18007af25  lea     rcx, [rsp+150h+var_108]; this
0x18007af2a  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x18007af2f  nop
0x18007af30  lea     rcx, [rsp+150h+var_100]; this
0x18007af35  call    ??1SmartFeatureTuningManager@FeatureTuning@Flighting@Internal@Windows@winrt@@QEAA@XZ; winrt::Windows::Internal::Flighting::FeatureTuning::SmartFeatureTuningManager::~SmartFeatureTuningManager(void)
0x18007af3a  nop
0x18007af3b  lea     rcx, [rsp+150h+var_F8]
0x18007af40  call    ?_Tidy@?$vector@URollbackPolicy@@V?$allocator@URollbackPolicy@@@std@@@std@@AEAAXXZ; std::vector<RollbackPolicy>::_Tidy(void)
0x18007af45  mov     rax, rbx
0x18007af48  mov     rcx, [rbp+50h+var_40]
0x18007af4c  xor     rcx, rsp; StackCookie
0x18007af4f  call    __security_check_cookie
0x18007af54  mov     rbx, [rsp+150h+arg_10]
0x18007af5c  add     rsp, 120h
0x18007af63  pop     r15
0x18007af65  pop     r14
0x18007af67  pop     r13
0x18007af69  pop     r12
0x18007af6b  pop     rdi
0x18007af6c  pop     rsi
0x18007af6d  pop     rbp
0x18007af6e  retn
```
