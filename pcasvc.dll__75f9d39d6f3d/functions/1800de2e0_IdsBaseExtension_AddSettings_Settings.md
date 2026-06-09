# IdsBaseExtension::AddSettings(Settings *)

- ea: `0x1800de2e0`
- end: `0x1800de5db`
- name: `?AddSettings@IdsBaseExtension@@UEAAKPEAVSettings@@@Z`
- size: `763`
- prototype: `unsigned int __fastcall(IdsBaseExtension *__hidden this, struct Settings *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180012920`
- `0x1800182e0`
- `0x180018768`
- `0x1800d9f08`
- `0x1800da288`
- `0x1800da2a4`
- `0x1800da2dc`
- `0x1800da5bc`
- `0x1800da644`
- `0x1800de2e0`
- `0x1800de68c`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800de40b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de4dd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de4ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de4fb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de563`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de5ac`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de40b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de4dd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de4ec`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de4fb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de563`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de5ac`

## string_xrefs

- `0x1800de315`: `IdsBaseExtension::AddSettings failed: null settings\n`
- `0x1800de322`: `IdsBaseExtension::AddSettings`
- `0x1800de3f1`: `IdsBaseExtension::AddSettings`
- `0x1800de4c3`: `IdsBaseExtension::AddSettings`
- `0x1800de527`: `IdsBaseExtension::AddSettings`
- `0x1800de545`: `IdsBaseExtension::AddSettings`
- `0x1800de58d`: `IdsBaseExtension::AddSettings`
- `0x1800de580`: `IdsBaseExtension::AddSettings: missing or invalid /base configuration\n`
- `0x1800de56e`: `IdsBaseExtension::AddSettings: missing or invalid /base/enabled setting\n`
- `0x1800de3e4`: `IdsBaseExtension::AddSettings: base extension is disabled\n`
- `0x1800de417`: `/config`
- `0x1800de4b6`: `IdsBaseExtension::AddSettings: ProcessConfigItem failed with error: %u\n`
- `0x1800de51a`: `\nIdsBaseExtension: Total config entries: %zu\n`
- `0x1800de538`: `IdsBaseExtension::AddSettings succeeded\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall IdsBaseExtension::AddSettings(IdsBaseExtension *this, struct Settings *a2)
{
  __int64 v5; // rdx
  SettingEntry *v6; // rbx
  __int64 v7; // rdx
  SettingEntry *v8; // rdi
  SettingEntry *v9; // rcx
  const char *v10; // r9
  int v11; // r8d
  __int64 v12; // rdx
  SettingEntry *v13; // rsi
  __int64 v14; // rcx
  __int64 i; // r14
  __int64 v16; // rax
  unsigned int v17; // r12d
  __int64 v18; // [rsp+20h] [rbp-59h]
  __int64 v19; // [rsp+28h] [rbp-51h]
  __int64 v20; // [rsp+30h] [rbp-49h] BYREF
  __int64 v21; // [rsp+38h] [rbp-41h] BYREF
  SettingEntry *v22; // [rsp+40h] [rbp-39h] BYREF
  SettingEntry *v23; // [rsp+48h] [rbp-31h] BYREF
  SettingEntry *v24; // [rsp+50h] [rbp-29h] BYREF
  _BYTE v25[32]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v26[32]; // [rsp+78h] [rbp-1h] BYREF

  if ( !a2 )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"IdsBaseExtension::AddSettings",
      129,
      (unsigned int)"IdsBaseExtension::AddSettings failed: null settings\n");
    return 87;
  }
  std::wstring::wstring(v25, L"/base");
  Settings::QueryEntry(a2, &v22, 0, v25);
  LOBYTE(v5) = 1;
  std::wstring::_Tidy(v25, v5, 0);
  v6 = v22;
  if ( !v22 || !SettingEntry::IsObject(v22) )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"IdsBaseExtension::AddSettings",
      137,
      (unsigned int)"IdsBaseExtension::AddSettings: missing or invalid /base configuration\n");
    if ( !v6 )
      return 0;
LABEL_31:
    if ( v6 )
      operator delete(v6);
    return 0;
  }
  std::wstring::wstring(v26, L"/enabled");
  Settings::QueryEntry(a2, &v23, v6, v26);
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v26, v7, 0);
  v8 = v23;
  if ( !v23 || !SettingEntry::IsBool(v23) )
  {
    v10 = "IdsBaseExtension::AddSettings: missing or invalid /base/enabled setting\n";
    v11 = 144;
    goto LABEL_9;
  }
  if ( !SettingEntry::GetBool(v9) )
  {
    v10 = "IdsBaseExtension::AddSettings: base extension is disabled\n";
    v11 = 152;
LABEL_9:
    AslLogCallPrintf(3, (unsigned int)"IdsBaseExtension::AddSettings", v11, (_DWORD)v10);
LABEL_10:
    if ( v8 )
      operator delete(v8);
    goto LABEL_31;
  }
  std::wstring::wstring(v25, L"/config");
  Settings::QueryEntry(a2, &v24, v6, v25);
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(v25, v12, 0);
  v13 = v24;
  if ( !v24 || !SettingEntry::IsArray(v24) )
  {
LABEL_27:
    AslLogCallPrintf(
      3,
      (unsigned int)"IdsBaseExtension::AddSettings",
      183,
      (unsigned int)"IdsBaseExtension::AddSettings succeeded\n");
    if ( v13 )
      operator delete(v13);
    goto LABEL_10;
  }
  for ( i = 0; ; ++i )
  {
    Settings::QueryArrayEntry(v14, &v21, v13, i, v18, v19, v20);
    v16 = v21;
    if ( !v21 )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"IdsBaseExtension::AddSettings",
        180,
        (unsigned int)"\nIdsBaseExtension: Total config entries: %zu\n");
      goto LABEL_27;
    }
    v21 = 0;
    v20 = v16;
    v17 = IdsBaseExtension::ProcessConfigItem(this, a2, &v20, i);
    if ( v17 )
      break;
  }
  AslLogCallPrintf(
    3,
    (unsigned int)"IdsBaseExtension::AddSettings",
    173,
    (unsigned int)"IdsBaseExtension::AddSettings: ProcessConfigItem failed with error: %u\n");
  if ( v13 )
    operator delete(v13);
  if ( v8 )
    operator delete(v8);
  if ( v6 )
    operator delete(v6);
  return v17;
}

```

## disassembly

```asm
0x1800de2e0  mov     [rsp-8+arg_10], rbx
0x1800de2e5  push    rbp
0x1800de2e6  push    rsi
0x1800de2e7  push    rdi
0x1800de2e8  push    r12
0x1800de2ea  push    r13
0x1800de2ec  push    r14
0x1800de2ee  push    r15
0x1800de2f0  lea     rbp, [rsp-27h]
0x1800de2f5  sub     rsp, 0A0h
0x1800de2fc  mov     rax, cs:__security_cookie
0x1800de303  xor     rax, rsp
0x1800de306  mov     [rbp+57h+var_38], rax
0x1800de30a  mov     r15, rdx
0x1800de30d  mov     r13, rcx
0x1800de310  test    rdx, rdx
0x1800de313  jnz     short loc_1800DE33B
0x1800de315  lea     r9, aIdsbaseextensi_11; "IdsBaseExtension::AddSettings failed: n"...
0x1800de31c  mov     r8d, 81h
0x1800de322  lea     rdx, aIdsbaseextensi_2; "IdsBaseExtension::AddSettings"
0x1800de329  lea     ecx, [r15+3]
0x1800de32d  call    AslLogCallPrintf
0x1800de332  lea     eax, [r15+57h]
0x1800de336  jmp     loc_1800DE5B4
0x1800de33b  lea     rdx, aBase; "/base"
0x1800de342  lea     rcx, [rbp+57h+var_78]
0x1800de346  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800de34b  nop
0x1800de34c  lea     r9, [rbp+57h+var_78]
0x1800de350  xor     r8d, r8d
0x1800de353  lea     rdx, [rbp+57h+var_90]
0x1800de357  mov     rcx, r15
0x1800de35a  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800de35f  nop
0x1800de360  xor     r8d, r8d
0x1800de363  mov     dl, 1
0x1800de365  lea     rcx, [rbp+57h+var_78]
0x1800de369  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de36e  mov     rbx, [rbp+57h+var_90]
0x1800de372  test    rbx, rbx
0x1800de375  jz      loc_1800DE580
0x1800de37b  mov     rcx, rbx; this
0x1800de37e  call    ?IsObject@SettingEntry@@QEBA_NXZ; SettingEntry::IsObject(void)
0x1800de383  test    al, al
0x1800de385  jz      loc_1800DE580
0x1800de38b  lea     rdx, aEnabled; "/enabled"
0x1800de392  lea     rcx, [rbp+57h+var_58]
0x1800de396  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800de39b  nop
0x1800de39c  lea     r9, [rbp+57h+var_58]
0x1800de3a0  mov     r8, rbx
0x1800de3a3  lea     rdx, [rbp+57h+var_88]
0x1800de3a7  mov     rcx, r15
0x1800de3aa  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800de3af  nop
0x1800de3b0  xor     r8d, r8d
0x1800de3b3  mov     dl, 1
0x1800de3b5  lea     rcx, [rbp+57h+var_58]
0x1800de3b9  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de3be  mov     rdi, [rbp+57h+var_88]
0x1800de3c2  test    rdi, rdi
0x1800de3c5  jz      loc_1800DE56E
0x1800de3cb  mov     rcx, rdi; this
0x1800de3ce  call    ?IsBool@SettingEntry@@QEBA_NXZ; SettingEntry::IsBool(void)
0x1800de3d3  test    al, al
0x1800de3d5  jz      loc_1800DE56E
0x1800de3db  call    ?GetBool@SettingEntry@@QEBA_NXZ; SettingEntry::GetBool(void)
0x1800de3e0  test    al, al
0x1800de3e2  jnz     short loc_1800DE417
0x1800de3e4  lea     r9, aIdsbaseextensi_15; "IdsBaseExtension::AddSettings: base ext"...
0x1800de3eb  mov     r8d, 98h
0x1800de3f1  lea     rdx, aIdsbaseextensi_2; "IdsBaseExtension::AddSettings"
0x1800de3f8  mov     ecx, 3
0x1800de3fd  call    AslLogCallPrintf
0x1800de402  nop
0x1800de403  test    rdi, rdi
0x1800de406  jz      short loc_1800DE412
0x1800de408  mov     rcx, rdi
0x1800de40b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de411  nop
0x1800de412  jmp     loc_1800DE5A4
0x1800de417  lea     rdx, aConfig; "/config"
0x1800de41e  lea     rcx, [rbp+57h+var_78]
0x1800de422  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800de427  nop
0x1800de428  lea     r9, [rbp+57h+var_78]
0x1800de42c  mov     r8, rbx
0x1800de42f  lea     rdx, [rbp+57h+var_80]
0x1800de433  mov     rcx, r15
0x1800de436  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800de43b  nop
0x1800de43c  xor     r8d, r8d
0x1800de43f  mov     dl, 1
0x1800de441  lea     rcx, [rbp+57h+var_78]
0x1800de445  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de44a  mov     rsi, [rbp+57h+var_80]
0x1800de44e  test    rsi, rsi
0x1800de451  jz      loc_1800DE538
0x1800de457  mov     rcx, rsi; this
0x1800de45a  call    ?IsArray@SettingEntry@@QEBA_NXZ; SettingEntry::IsArray(void)
0x1800de45f  test    al, al
0x1800de461  jz      loc_1800DE538
0x1800de467  xor     r14d, r14d
0x1800de46a  mov     r9, r14
0x1800de46d  mov     r8, rsi
0x1800de470  lea     rdx, [rbp+57h+var_98]
0x1800de474  call    ?QueryArrayEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@_K@Z; Settings::QueryArrayEntry(SettingEntry const *,unsigned __int64)
0x1800de479  nop
0x1800de47a  mov     rax, [rbp+57h+var_98]
0x1800de47e  test    rax, rax
0x1800de481  jz      loc_1800DE509
0x1800de487  mov     [rbp+57h+var_98], 0
0x1800de48f  mov     [rbp+57h+var_A0], rax
0x1800de493  mov     r9, r14
0x1800de496  lea     r8, [rbp+57h+var_A0]
0x1800de49a  mov     rdx, r15
0x1800de49d  mov     rcx, r13
0x1800de4a0  call    ?ProcessConfigItem@IdsBaseExtension@@AEAAKPEAVSettings@@V?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@_K@Z; IdsBaseExtension::ProcessConfigItem(Settings *,std::unique_ptr<SettingEntry>,unsigned __int64)
0x1800de4a5  mov     r12d, eax
0x1800de4a8  test    eax, eax
0x1800de4aa  jnz     short loc_1800DE4B1
0x1800de4ac  inc     r14
0x1800de4af  jmp     short loc_1800DE46A
0x1800de4b1  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x1800de4b6  lea     r9, aIdsbaseextensi_5; "IdsBaseExtension::AddSettings: ProcessC"...
0x1800de4bd  mov     r8d, 0ADh
0x1800de4c3  lea     rdx, aIdsbaseextensi_2; "IdsBaseExtension::AddSettings"
0x1800de4ca  mov     ecx, 3
0x1800de4cf  call    AslLogCallPrintf
0x1800de4d4  nop
0x1800de4d5  test    rsi, rsi
0x1800de4d8  jz      short loc_1800DE4E4
0x1800de4da  mov     rcx, rsi
0x1800de4dd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de4e3  nop
0x1800de4e4  test    rdi, rdi
0x1800de4e7  jz      short loc_1800DE4F3
0x1800de4e9  mov     rcx, rdi
0x1800de4ec  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de4f2  nop
0x1800de4f3  test    rbx, rbx
0x1800de4f6  jz      short loc_1800DE501
0x1800de4f8  mov     rcx, rbx
0x1800de4fb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de501  mov     eax, r12d
0x1800de504  jmp     loc_1800DE5B4
0x1800de509  mov     rax, [r13+20h]
0x1800de50d  sub     rax, [r13+18h]
0x1800de511  sar     rax, 3
0x1800de515  mov     [rsp+0D0h+var_B0], rax
0x1800de51a  lea     r9, aIdsbaseextensi_7; "\nIdsBaseExtension: Total config entrie"...
0x1800de521  mov     r8d, 0B4h
0x1800de527  lea     rdx, aIdsbaseextensi_2; "IdsBaseExtension::AddSettings"
0x1800de52e  mov     ecx, 3
0x1800de533  call    AslLogCallPrintf
0x1800de538  lea     r9, aIdsbaseextensi_1; "IdsBaseExtension::AddSettings succeeded"...
0x1800de53f  mov     r8d, 0B7h
0x1800de545  lea     rdx, aIdsbaseextensi_2; "IdsBaseExtension::AddSettings"
0x1800de54c  mov     ecx, 3
0x1800de551  call    AslLogCallPrintf
0x1800de556  nop
0x1800de557  test    rsi, rsi
0x1800de55a  jz      loc_1800DE403
0x1800de560  mov     rcx, rsi
0x1800de563  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de569  jmp     loc_1800DE403
0x1800de56e  lea     r9, aIdsbaseextensi_9; "IdsBaseExtension::AddSettings: missing "...
0x1800de575  mov     r8d, 90h
0x1800de57b  jmp     loc_1800DE3F1
0x1800de580  lea     r9, aIdsbaseextensi_8; "IdsBaseExtension::AddSettings: missing "...
0x1800de587  mov     r8d, 89h
0x1800de58d  lea     rdx, aIdsbaseextensi_2; "IdsBaseExtension::AddSettings"
0x1800de594  mov     ecx, 3
0x1800de599  call    AslLogCallPrintf
0x1800de59e  nop
0x1800de59f  test    rbx, rbx
0x1800de5a2  jz      short loc_1800DE5B2
0x1800de5a4  test    rbx, rbx
0x1800de5a7  jz      short loc_1800DE5B2
0x1800de5a9  mov     rcx, rbx
0x1800de5ac  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de5b2  xor     eax, eax
0x1800de5b4  mov     rcx, [rbp+57h+var_38]
0x1800de5b8  xor     rcx, rsp; StackCookie
0x1800de5bb  call    __security_check_cookie
0x1800de5c0  mov     rbx, [rsp+0D0h+arg_10]
0x1800de5c8  add     rsp, 0A0h
0x1800de5cf  pop     r15
0x1800de5d1  pop     r14
0x1800de5d3  pop     r13
0x1800de5d5  pop     r12
0x1800de5d7  pop     rdi
0x1800de5d8  pop     rsi
0x1800de5d9  pop     rbp
0x1800de5da  retn
```
