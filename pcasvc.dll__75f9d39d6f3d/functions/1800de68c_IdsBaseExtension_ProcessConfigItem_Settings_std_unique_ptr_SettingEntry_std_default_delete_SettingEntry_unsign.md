# IdsBaseExtension::ProcessConfigItem(Settings *,std::unique_ptr<SettingEntry,std::default_delete<SettingEntry>>,unsigned __int64)

- ea: `0x1800de68c`
- end: `0x1800dec0e`
- name: `?ProcessConfigItem@IdsBaseExtension@@AEAAKPEAVSettings@@V?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@_K@Z`
- size: `1410`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800de2e0`

## callees

- `0x180012920`
- `0x1800182e0`
- `0x180018504`
- `0x180018768`
- `0x180018b40`
- `0x180055840`
- `0x1800d9f20`
- `0x1800da020`
- `0x1800da288`
- `0x1800da2c0`
- `0x1800da2f8`
- `0x1800da5bc`
- `0x1800da644`
- `0x1800de174`
- `0x1800de68c`
- `0x1800df23c`
- `0x1800df2d4`
- `0x1800df360`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800de99f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de9bd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de9d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dea91`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb37`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb56`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb65`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb74`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb90`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb9f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800debce`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800debe3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de99f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de9bd`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800de9d5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800dea91`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb37`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb56`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb65`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb74`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb90`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800deb9f`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800debce`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800debe3`

## string_xrefs

- `0x1800deba9`: `IdsBaseExtension::ProcessConfigItem: failed to allocate config entry\n`
- `0x1800de6ee`: `\nIdsBaseExtension: Processing config[%zu]:\n`
- `0x1800de6f9`: `IdsBaseExtension::ProcessConfigItem`
- `0x1800de7c4`: `IdsBaseExtension::ProcessConfigItem`
- `0x1800de973`: `IdsBaseExtension::ProcessConfigItem`
- `0x1800dea4b`: `IdsBaseExtension::ProcessConfigItem`
- `0x1800deaf0`: `IdsBaseExtension::ProcessConfigItem`
- `0x1800debb6`: `IdsBaseExtension::ProcessConfigItem`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall IdsBaseExtension::ProcessConfigItem(SettingEntry *a1, __int64 a2, SettingEntry *a3, char *a4)
{
  void **v4; // r14
  __int64 v5; // r15
  SettingEntry *v6; // r13
  int v7; // edi
  IdsBaseConfigEntry *v8; // rax
  IdsBaseConfigEntry *v9; // rbx
  void *v10; // rcx
  __int64 v11; // rdx
  SettingEntry *v12; // r12
  __int64 v13; // rcx
  char *v14; // rax
  __int64 v15; // r14
  void *v16; // r13
  __int64 v17; // rdx
  SettingEntry *v18; // r15
  __int64 String; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  SettingEntry *v22; // rsi
  __int64 v23; // rdx
  SettingEntry *v24; // rcx
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  SettingEntry *v29; // rsi
  char *v30; // rcx
  __int64 i; // rdi
  __int64 v32; // rdx
  SettingEntry *v33; // rdi
  char *v34; // rcx
  __int64 j; // r15
  IdsBaseConfigEntry *v36; // rbx
  char *v38; // [rsp+20h] [rbp-E0h]
  _QWORD *v39; // [rsp+28h] [rbp-D8h]
  int v40; // [rsp+30h] [rbp-D0h]
  char *v41; // [rsp+40h] [rbp-C0h] BYREF
  int v42; // [rsp+48h] [rbp-B8h]
  int Integer; // [rsp+4Ch] [rbp-B4h]
  SettingEntry *v44; // [rsp+50h] [rbp-B0h] BYREF
  SettingEntry *v45; // [rsp+58h] [rbp-A8h] BYREF
  SettingEntry *v46; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h]
  IdsBaseConfigEntry *v48; // [rsp+70h] [rbp-90h] BYREF
  SettingEntry *v49; // [rsp+78h] [rbp-88h] BYREF
  void *v50; // [rsp+80h] [rbp-80h] BYREF
  SettingEntry *v51[2]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v52[32]; // [rsp+98h] [rbp-68h] BYREF
  _WORD v53[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-38h]
  __int64 v55; // [rsp+D0h] [rbp-30h]
  int v56; // [rsp+D8h] [rbp-28h]
  _QWORD v57[4]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v58[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v59[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v60[32]; // [rsp+140h] [rbp+40h] BYREF

  v4 = (void **)a3;
  v45 = a3;
  v5 = a2;
  v47 = a2;
  v6 = a1;
  v46 = a1;
  v51[1] = a3;
  v7 = 0;
  v42 = 0;
  if ( a2 && *(_QWORD *)a3 )
  {
    v38 = a4;
    AslLogCallPrintf(
      3,
      (unsigned int)"IdsBaseExtension::ProcessConfigItem",
      35,
      (unsigned int)"\nIdsBaseExtension: Processing config[%zu]:\n");
    v8 = (IdsBaseConfigEntry *)operator new(0x58u);
    v9 = v8;
    v44 = v8;
    if ( v8 )
    {
      v10 = *v4;
      *v4 = 0;
      *(_QWORD *)v8 = v10;
      *((_QWORD *)v8 + 1) = 0;
      *((_QWORD *)v8 + 2) = 0;
      *((_QWORD *)v8 + 3) = 0;
      *((_QWORD *)v8 + 4) = 0;
      *((_QWORD *)v8 + 5) = 0;
      *((_QWORD *)v8 + 6) = 0;
      *((_QWORD *)v8 + 7) = 0;
      *((_QWORD *)v8 + 8) = 0;
      *((_QWORD *)v8 + 9) = 0;
      *((_QWORD *)v8 + 10) = 0;
    }
    else
    {
      v9 = 0;
    }
    v48 = v9;
    if ( v9 )
    {
      std::wstring::wstring(v58, L"/eventlist");
      Settings::QueryEntry(v5, &v49, *(_QWORD *)v9, v58);
      LOBYTE(v11) = 1;
      std::wstring::_Tidy(v58, v11, 0);
      v12 = v49;
      if ( v49 && SettingEntry::IsArray(v49) )
      {
        AslLogCallPrintf(3, (unsigned int)"IdsBaseExtension::ProcessConfigItem", 49, (unsigned int)"  eventlist:\n");
        v14 = 0;
        v41 = 0;
        v15 = v47;
        while ( 1 )
        {
          Settings::QueryArrayEntry(v13, &v50, v12, v14, v38, v39, v40);
          v16 = v50;
          if ( !v50 )
            break;
          std::wstring::wstring(v52, L"/provider");
          Settings::QueryEntry(v15, v51, v16, v52);
          LOBYTE(v17) = 1;
          std::wstring::_Tidy(v52, v17, 0);
          v18 = v51[0];
          if ( v51[0] && SettingEntry::IsString(v51[0]) )
          {
            String = SettingEntry::GetString(v18, v60);
            v7 |= 1u;
          }
          else
          {
            String = std::wstring::wstring(v59, &sourceString);
            v7 |= 2u;
          }
          v42 = v7;
          std::wstring::wstring(v57, String);
          if ( (v7 & 2) != 0 )
          {
            v7 &= ~2u;
            v42 = v7;
            LOBYTE(v20) = 1;
            std::wstring::_Tidy(v59, v20, 0);
          }
          if ( (v7 & 1) != 0 )
          {
            v7 &= ~1u;
            v42 = v7;
            LOBYTE(v20) = 1;
            std::wstring::_Tidy(v60, v20, 0);
          }
          std::wstring::wstring(v52, L"/eventid");
          Settings::QueryEntry(v15, &v44, v16, v52);
          LOBYTE(v21) = 1;
          std::wstring::_Tidy(v52, v21, 0);
          v22 = v44;
          v23 = 0;
          if ( v44 && SettingEntry::IsInteger(v44) )
            Integer = SettingEntry::GetInteger(v24);
          else
            Integer = v23;
          v55 = 7;
          v54 = v23;
          v53[0] = v23;
          v56 = v23;
          std::wstring::operator=(v53, v57);
          v56 = Integer;
          std::vector<IdsBaseEventEntry>::push_back((char *)v9 + 8, v53);
          v25 = v57;
          if ( v57[3] >= 8u )
            v25 = (_QWORD *)v57[0];
          v40 = v56;
          v39 = v25;
          v38 = v41;
          AslLogCallPrintf(
            3,
            (unsigned int)"IdsBaseExtension::ProcessConfigItem",
            73,
            (unsigned int)"    [%zu] provider: %ws, eventid: %u\n");
          ++v41;
          LOBYTE(v26) = 1;
          std::wstring::_Tidy(v53, v26, 0);
          if ( v22 )
            operator delete(v22);
          LOBYTE(v27) = 1;
          std::wstring::_Tidy(v57, v27, 0);
          if ( v18 )
            operator delete(v18);
          v14 = v41;
          if ( v16 )
          {
            operator delete(v16);
            v14 = v41;
          }
        }
        v4 = (void **)v45;
        v5 = v47;
        v6 = v46;
      }
      std::wstring::wstring(v52, L"/matchlist");
      Settings::QueryEntry(v5, &v46, *(_QWORD *)v9, v52);
      LOBYTE(v28) = 1;
      std::wstring::_Tidy(v52, v28, 0);
      v29 = v46;
      if ( v46 && SettingEntry::IsArray(v46) )
      {
        AslLogCallPrintf(3, (unsigned int)"IdsBaseExtension::ProcessConfigItem", 83, (unsigned int)"  matchlist:\n");
        for ( i = 0; ; ++i )
        {
          Settings::QueryArrayEntry(v30, &v41, v29, i, v38, v39, v40);
          if ( !v41 )
            break;
          std::vector<std::unique_ptr<SettingEntry>>::push_back((char *)v9 + 32, &v41);
          v30 = v41;
          if ( v41 )
            operator delete(v41);
        }
      }
      std::wstring::wstring(v58, L"/actionlist");
      Settings::QueryEntry(v5, &v45, *(_QWORD *)v9, v58);
      LOBYTE(v32) = 1;
      std::wstring::_Tidy(v58, v32, 0);
      v33 = v45;
      if ( v45 && SettingEntry::IsArray(v45) )
      {
        AslLogCallPrintf(3, (unsigned int)"IdsBaseExtension::ProcessConfigItem", 103, (unsigned int)"  actionlist:\n");
        for ( j = 0; ; ++j )
        {
          Settings::QueryArrayEntry(v34, &v41, v33, j, v38, v39, v40);
          if ( !v41 )
            break;
          std::vector<std::unique_ptr<SettingEntry>>::push_back((char *)v9 + 56, &v41);
          v34 = v41;
          if ( v41 )
            operator delete(v41);
        }
      }
      std::vector<std::unique_ptr<IdsBaseConfigEntry>>::push_back((char *)v6 + 24, &v48);
      if ( v33 )
        operator delete(v33);
      if ( v29 )
        operator delete(v29);
      if ( v12 )
        operator delete(v12);
      v36 = v48;
      if ( v48 )
      {
        IdsBaseConfigEntry::~IdsBaseConfigEntry(v48);
        operator delete(v36);
      }
      if ( *v4 )
        operator delete(*v4);
      return 0;
    }
    else
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"IdsBaseExtension::ProcessConfigItem",
        41,
        (unsigned int)"IdsBaseExtension::ProcessConfigItem: failed to allocate config entry\n");
      if ( *v4 )
        operator delete(*v4);
      return 14;
    }
  }
  else
  {
    if ( *(_QWORD *)a3 )
      operator delete(*(void **)a3);
    return 87;
  }
}

```

## disassembly

```asm
0x1800de68c  push    rbp
0x1800de68e  push    rbx
0x1800de68f  push    rsi
0x1800de690  push    rdi
0x1800de691  push    r12
0x1800de693  push    r13
0x1800de695  push    r14
0x1800de697  push    r15
0x1800de699  lea     rbp, [rsp-78h]
0x1800de69e  sub     rsp, 178h
0x1800de6a5  mov     rax, cs:__security_cookie
0x1800de6ac  xor     rax, rsp
0x1800de6af  mov     [rbp+0B0h+var_50], rax
0x1800de6b3  mov     r14, r8
0x1800de6b6  mov     [rsp+1B0h+var_158], r8
0x1800de6bb  mov     r15, rdx
0x1800de6be  mov     [rsp+1B0h+var_148], rdx
0x1800de6c3  mov     r13, rcx
0x1800de6c6  mov     [rsp+1B0h+var_150], rcx
0x1800de6cb  mov     [rbp+0B0h+var_120], r8
0x1800de6cf  xor     esi, esi
0x1800de6d1  mov     edi, esi
0x1800de6d3  mov     [rsp+1B0h+var_168], esi
0x1800de6d7  test    rdx, rdx
0x1800de6da  jz      loc_1800DEBDB
0x1800de6e0  cmp     [r8], rsi
0x1800de6e3  jz      loc_1800DEBDB
0x1800de6e9  mov     [rsp+1B0h+var_190], r9
0x1800de6ee  lea     r9, aIdsbaseextensi_3; "\nIdsBaseExtension: Processing config[%"...
0x1800de6f5  lea     r8d, [rsi+23h]
0x1800de6f9  lea     rdx, aIdsbaseextensi_0; "IdsBaseExtension::ProcessConfigItem"
0x1800de700  lea     r12d, [rsi+3]
0x1800de704  mov     ecx, r12d
0x1800de707  call    AslLogCallPrintf
0x1800de70c  lea     ecx, [rsi+58h]; Size
0x1800de70f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800de714  mov     rbx, rax
0x1800de717  mov     [rsp+1B0h+var_160], rax
0x1800de71c  test    rax, rax
0x1800de71f  jz      short loc_1800DE754
0x1800de721  mov     rcx, [r14]
0x1800de724  mov     [r14], rsi
0x1800de727  mov     [rax], rcx
0x1800de72a  mov     [rax+8], rsi
0x1800de72e  mov     [rax+10h], rsi
0x1800de732  mov     [rax+18h], rsi
0x1800de736  mov     [rax+20h], rsi
0x1800de73a  mov     [rax+28h], rsi
0x1800de73e  mov     [rax+30h], rsi
0x1800de742  mov     [rax+38h], rsi
0x1800de746  mov     [rax+40h], rsi
0x1800de74a  mov     [rax+48h], rsi
0x1800de74e  mov     [rax+50h], rsi
0x1800de752  jmp     short loc_1800DE757
0x1800de754  mov     rbx, rsi
0x1800de757  mov     [rsp+1B0h+var_140], rbx
0x1800de75c  test    rbx, rbx
0x1800de75f  jz      loc_1800DEBA9
0x1800de765  lea     rdx, aEventlist_0; "/eventlist"
0x1800de76c  lea     rcx, [rbp+0B0h+var_B0]
0x1800de770  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800de775  nop
0x1800de776  lea     r9, [rbp+0B0h+var_B0]
0x1800de77a  mov     r8, [rbx]
0x1800de77d  lea     rdx, [rsp+1B0h+var_138]
0x1800de782  mov     rcx, r15
0x1800de785  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800de78a  nop
0x1800de78b  xor     r8d, r8d
0x1800de78e  mov     dl, 1
0x1800de790  lea     rcx, [rbp+0B0h+var_B0]
0x1800de794  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de799  mov     r12, [rsp+1B0h+var_138]
0x1800de79e  test    r12, r12
0x1800de7a1  jz      loc_1800DE9F4
0x1800de7a7  mov     rcx, r12; this
0x1800de7aa  call    ?IsArray@SettingEntry@@QEBA_NXZ; SettingEntry::IsArray(void)
0x1800de7af  test    al, al
0x1800de7b1  jz      loc_1800DE9F4
0x1800de7b7  lea     r9, aEventlist_1; "  eventlist:\n"
0x1800de7be  mov     r8d, 31h ; '1'
0x1800de7c4  lea     rdx, aIdsbaseextensi_0; "IdsBaseExtension::ProcessConfigItem"
0x1800de7cb  lea     ecx, [r8-2Eh]
0x1800de7cf  call    AslLogCallPrintf
0x1800de7d4  mov     rax, rsi
0x1800de7d7  mov     [rsp+1B0h+var_170], rax
0x1800de7dc  mov     r14, [rsp+1B0h+var_148]
0x1800de7e1  mov     r9, rax
0x1800de7e4  mov     r8, r12
0x1800de7e7  lea     rdx, [rbp+0B0h+var_130]
0x1800de7eb  call    ?QueryArrayEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@_K@Z; Settings::QueryArrayEntry(SettingEntry const *,unsigned __int64)
0x1800de7f0  nop
0x1800de7f1  mov     r13, [rbp+0B0h+var_130]
0x1800de7f5  test    r13, r13
0x1800de7f8  jz      loc_1800DE9E5
0x1800de7fe  lea     rdx, aProvider; "/provider"
0x1800de805  lea     rcx, [rbp+0B0h+var_118]
0x1800de809  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800de80e  nop
0x1800de80f  lea     r9, [rbp+0B0h+var_118]
0x1800de813  mov     r8, r13
0x1800de816  lea     rdx, [rbp+0B0h+var_128]
0x1800de81a  mov     rcx, r14
0x1800de81d  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800de822  nop
0x1800de823  xor     r8d, r8d
0x1800de826  mov     dl, 1
0x1800de828  lea     rcx, [rbp+0B0h+var_118]
0x1800de82c  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de831  mov     r15, [rbp+0B0h+var_128]
0x1800de835  test    r15, r15
0x1800de838  jz      short loc_1800DE858
0x1800de83a  mov     rcx, r15; this
0x1800de83d  call    ?IsString@SettingEntry@@QEBA_NXZ; SettingEntry::IsString(void)
0x1800de842  test    al, al
0x1800de844  jz      short loc_1800DE858
0x1800de846  lea     rdx, [rbp+0B0h+var_70]
0x1800de84a  mov     rcx, r15
0x1800de84d  call    ?GetString@SettingEntry@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; SettingEntry::GetString(void)
0x1800de852  nop
0x1800de853  or      edi, 1
0x1800de856  jmp     short loc_1800DE86B
0x1800de858  lea     rdx, sourceString
0x1800de85f  lea     rcx, [rbp+0B0h+var_90]
0x1800de863  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800de868  or      edi, 2
0x1800de86b  mov     [rsp+1B0h+var_168], edi
0x1800de86f  mov     rdx, rax
0x1800de872  lea     rcx, [rbp+0B0h+var_D0]
0x1800de876  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800de87b  nop
0x1800de87c  test    dil, 2
0x1800de880  jz      short loc_1800DE898
0x1800de882  and     edi, 0FFFFFFFDh
0x1800de885  mov     [rsp+1B0h+var_168], edi
0x1800de889  xor     r8d, r8d
0x1800de88c  mov     dl, 1
0x1800de88e  lea     rcx, [rbp+0B0h+var_90]
0x1800de892  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de897  nop
0x1800de898  test    dil, 1
0x1800de89c  jz      short loc_1800DE8B3
0x1800de89e  and     edi, 0FFFFFFFEh
0x1800de8a1  mov     [rsp+1B0h+var_168], edi
0x1800de8a5  xor     r8d, r8d
0x1800de8a8  mov     dl, 1
0x1800de8aa  lea     rcx, [rbp+0B0h+var_70]
0x1800de8ae  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de8b3  lea     rdx, aEventid_0; "/eventid"
0x1800de8ba  lea     rcx, [rbp+0B0h+var_118]
0x1800de8be  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800de8c3  nop
0x1800de8c4  lea     r9, [rbp+0B0h+var_118]
0x1800de8c8  mov     r8, r13
0x1800de8cb  lea     rdx, [rsp+1B0h+var_160]
0x1800de8d0  mov     rcx, r14
0x1800de8d3  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800de8d8  nop
0x1800de8d9  xor     r8d, r8d
0x1800de8dc  mov     dl, 1
0x1800de8de  lea     rcx, [rbp+0B0h+var_118]
0x1800de8e2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de8e7  mov     rsi, [rsp+1B0h+var_160]
0x1800de8ec  xor     edx, edx
0x1800de8ee  test    rsi, rsi
0x1800de8f1  jz      short loc_1800DE90A
0x1800de8f3  mov     rcx, rsi; this
0x1800de8f6  call    ?IsInteger@SettingEntry@@QEBA_NXZ; SettingEntry::IsInteger(void)
0x1800de8fb  test    al, al
0x1800de8fd  jz      short loc_1800DE90A
0x1800de8ff  call    ?GetInteger@SettingEntry@@QEBAHXZ; SettingEntry::GetInteger(void)
0x1800de904  mov     [rsp+1B0h+var_164], eax
0x1800de908  jmp     short loc_1800DE90E
0x1800de90a  mov     [rsp+1B0h+var_164], edx
0x1800de90e  mov     [rbp+0B0h+var_E0], 7
0x1800de916  mov     [rbp+0B0h+var_E8], rdx
0x1800de91a  mov     [rbp+0B0h+var_F8], dx
0x1800de91e  mov     [rbp+0B0h+var_D8], edx
0x1800de921  lea     rdx, [rbp+0B0h+var_D0]
0x1800de925  lea     rcx, [rbp+0B0h+var_F8]
0x1800de929  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800de92e  mov     eax, [rsp+1B0h+var_164]
0x1800de932  mov     [rbp+0B0h+var_D8], eax
0x1800de935  lea     rcx, [rbx+8]
0x1800de939  lea     rdx, [rbp+0B0h+var_F8]
0x1800de93d  call    ?push_back@?$vector@UIdsBaseEventEntry@@V?$allocator@UIdsBaseEventEntry@@@std@@@std@@QEAAXAEBUIdsBaseEventEntry@@@Z; std::vector<IdsBaseEventEntry>::push_back(IdsBaseEventEntry const &)
0x1800de942  lea     rcx, [rbp+0B0h+var_D0]
0x1800de946  cmp     [rbp+0B0h+var_B8], 8
0x1800de94b  cmovnb  rcx, [rbp+0B0h+var_D0]
0x1800de950  mov     eax, [rbp+0B0h+var_D8]
0x1800de953  mov     [rsp+1B0h+var_180], eax
0x1800de957  mov     [rsp+1B0h+var_188], rcx
0x1800de95c  mov     rax, [rsp+1B0h+var_170]
0x1800de961  mov     [rsp+1B0h+var_190], rax
0x1800de966  lea     r9, aZuProviderWsEv; "    [%zu] provider: %ws, eventid: %u\n"
0x1800de96d  mov     r8d, 49h ; 'I'
0x1800de973  lea     rdx, aIdsbaseextensi_0; "IdsBaseExtension::ProcessConfigItem"
0x1800de97a  lea     ecx, [r8-46h]
0x1800de97e  call    AslLogCallPrintf
0x1800de983  inc     [rsp+1B0h+var_170]
0x1800de988  xor     r8d, r8d
0x1800de98b  mov     dl, 1
0x1800de98d  lea     rcx, [rbp+0B0h+var_F8]
0x1800de991  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de996  nop
0x1800de997  test    rsi, rsi
0x1800de99a  jz      short loc_1800DE9A6
0x1800de99c  mov     rcx, rsi
0x1800de99f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de9a5  nop
0x1800de9a6  xor     r8d, r8d
0x1800de9a9  mov     dl, 1
0x1800de9ab  lea     rcx, [rbp+0B0h+var_D0]
0x1800de9af  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800de9b4  nop
0x1800de9b5  test    r15, r15
0x1800de9b8  jz      short loc_1800DE9C4
0x1800de9ba  mov     rcx, r15
0x1800de9bd  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de9c3  nop
0x1800de9c4  test    r13, r13
0x1800de9c7  mov     rax, [rsp+1B0h+var_170]
0x1800de9cc  jz      loc_1800DE7E1
0x1800de9d2  mov     rcx, r13
0x1800de9d5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800de9db  mov     rax, [rsp+1B0h+var_170]
0x1800de9e0  jmp     loc_1800DE7E1
0x1800de9e5  mov     r14, [rsp+1B0h+var_158]
0x1800de9ea  mov     r15, [rsp+1B0h+var_148]
0x1800de9ef  mov     r13, [rsp+1B0h+var_150]
0x1800de9f4  lea     rdx, aMatchlist; "/matchlist"
0x1800de9fb  lea     rcx, [rbp+0B0h+var_118]
0x1800de9ff  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800dea04  nop
0x1800dea05  lea     r9, [rbp+0B0h+var_118]
0x1800dea09  mov     r8, [rbx]
0x1800dea0c  lea     rdx, [rsp+1B0h+var_150]
0x1800dea11  mov     rcx, r15
0x1800dea14  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800dea19  nop
0x1800dea1a  xor     r8d, r8d
0x1800dea1d  mov     dl, 1
0x1800dea1f  lea     rcx, [rbp+0B0h+var_118]
0x1800dea23  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800dea28  mov     rsi, [rsp+1B0h+var_150]
0x1800dea2d  test    rsi, rsi
0x1800dea30  jz      short loc_1800DEA99
0x1800dea32  mov     rcx, rsi; this
0x1800dea35  call    ?IsArray@SettingEntry@@QEBA_NXZ; SettingEntry::IsArray(void)
0x1800dea3a  test    al, al
0x1800dea3c  jz      short loc_1800DEA99
0x1800dea3e  lea     r9, aMatchlist_0; "  matchlist:\n"
0x1800dea45  mov     r8d, 53h ; 'S'
0x1800dea4b  lea     rdx, aIdsbaseextensi_0; "IdsBaseExtension::ProcessConfigItem"
0x1800dea52  lea     ecx, [r8-50h]
0x1800dea56  call    AslLogCallPrintf
0x1800dea5b  xor     edi, edi
0x1800dea5d  mov     r9, rdi
0x1800dea60  mov     r8, rsi
0x1800dea63  lea     rdx, [rsp+1B0h+var_170]
0x1800dea68  call    ?QueryArrayEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@_K@Z; Settings::QueryArrayEntry(SettingEntry const *,unsigned __int64)
0x1800dea6d  nop
0x1800dea6e  cmp     [rsp+1B0h+var_170], 0
0x1800dea74  jz      short loc_1800DEA99
0x1800dea76  lea     rcx, [rbx+20h]
0x1800dea7a  lea     rdx, [rsp+1B0h+var_170]
0x1800dea7f  call    ?push_back@?$vector@V?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@V?$allocator@V?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@@2@@std@@QEAAX$$QEAV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@2@@Z; std::vector<std::unique_ptr<SettingEntry>>::push_back(std::unique_ptr<SettingEntry> &&)
0x1800dea84  inc     rdi
0x1800dea87  mov     rcx, [rsp+1B0h+var_170]
0x1800dea8c  test    rcx, rcx
0x1800dea8f  jz      short loc_1800DEA5D
0x1800dea91  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800dea97  jmp     short loc_1800DEA5D
0x1800dea99  lea     rdx, aActionlist_1; "/actionlist"
0x1800deaa0  lea     rcx, [rbp+0B0h+var_B0]
0x1800deaa4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1800deaa9  nop
0x1800deaaa  lea     r9, [rbp+0B0h+var_B0]
0x1800deaae  mov     r8, [rbx]
0x1800deab1  lea     rdx, [rsp+1B0h+var_158]
0x1800deab6  mov     rcx, r15
0x1800deab9  call    ?QueryEntry@Settings@@QEAA?AV?$unique_ptr@VSettingEntry@@U?$default_delete@VSettingEntry@@@std@@@std@@PEBVSettingEntry@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z; Settings::QueryEntry(SettingEntry const *,std::wstring const &)
0x1800deabe  nop
0x1800deabf  xor     r8d, r8d
0x1800deac2  mov     dl, 1
0x1800deac4  lea     rcx, [rbp+0B0h+var_B0]
0x1800deac8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800deacd  mov     rdi, [rsp+1B0h+var_158]
0x1800dead2  test    rdi, rdi
0x1800dead5  jz      short loc_1800DEB3F
0x1800dead7  mov     rcx, rdi; this
0x1800deada  call    ?IsArray@SettingEntry@@QEBA_NXZ; SettingEntry::IsArray(void)
0x1800deadf  test    al, al
0x1800deae1  jz      short loc_1800DEB3F
0x1800deae3  lea     r9, aActionlist_0; "  actionlist:\n"
0x1800deaea  mov     r8d, 67h ; 'g'
0x1800deaf0  lea     rdx, aIdsbaseextensi_0; "IdsBaseExtension::ProcessConfigItem"
0x1800deaf7  lea     ecx, [r8-64h]
0x1800deafb  call    AslLogCallPrintf
0x1800deb00  xor     r15d, r15d
  ... truncated ...
```
