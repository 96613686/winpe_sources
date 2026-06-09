# SetCatalogHints(ushort const *)

- ea: `0x180024f88`
- end: `0x180025234`
- name: `?SetCatalogHints@@YAXPEBG@Z`
- size: `684`
- prototype: `void __fastcall(PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180027668`

## callees

- `0x180002690`
- `0x180003810`
- `0x180008fac`
- `0x180009a38`
- `0x18000a578`
- `0x18000ad80`
- `0x180012818`
- `0x1800138b4`
- `0x180013970`
- `0x18002289c`
- `0x1800247e4`
- `0x180024c0c`
- `0x180024e70`
- `0x180024f88`
- `0x18002b69c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180024fd3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180024fd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024fef`

## string_xrefs

- `0x1800251ad`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x18002520c`: `onecore\vm\compute\dll\lib\storage\cicache.cpp`
- `0x1800250ff`: `Windows\System32\catroot\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}`
- `0x18002500f`: `Windows\System32\ntdll.dll`
- `0x180025041`: `Windows\System32\ntdll.dll`
- `0x180025222`: `onecore\internal\sdk\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall SetCatalogHints(PCWSTR pszPathIn)
{
  const WCHAR *v2; // rax
  DWORD FileAttributesW; // ebx
  DWORD LastError; // eax
  const WCHAR *trivial_1; // rax
  const char *v6; // r9
  const wchar_t **v7; // rbx
  char *v8; // rax
  char v9; // bl
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  void **v13; // rax
  void **Src; // rax
  PCWSTR v15; // rbx
  PCWSTR v16; // rdi
  void **v17; // rdx
  const WCHAR *v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // [rsp+20h] [rbp-59h]
  __int64 v21; // [rsp+40h] [rbp-39h] BYREF
  const wchar_t **v22; // [rsp+48h] [rbp-31h]
  _QWORD v23[2]; // [rsp+50h] [rbp-29h] BYREF
  void *v24[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v25; // [rsp+70h] [rbp-9h]
  unsigned __int64 v26; // [rsp+78h] [rbp-1h]
  PCWSTR SourceString[4]; // [rsp+80h] [rbp+7h] BYREF
  const wchar_t *v28; // [rsp+A0h] [rbp+27h] BYREF
  const WCHAR *v29; // [rsp+A8h] [rbp+2Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = (const WCHAR *)Vml::CombineFilePath(SourceString, pszPathIn, L"Windows\\WinSxS");
  if ( *((_QWORD *)v2 + 3) > 7u )
    v2 = *(const WCHAR **)v2;
  FileAttributesW = GetFileAttributesW(v2);
  std::wstring::~wstring((char **)SourceString);
  if ( FileAttributesW == -1 )
  {
    LastError = GetLastError();
    if ( LastError - 2 > 1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x179,
        (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
        (const char *)LastError,
        v20);
  }
  else
  {
    trivial_1 = (const WCHAR *)_std_find_trivial_1("$CI.CATALOGHINT", L"Windows\\System32\\ntdll.dll", 0);
    if ( trivial_1 == L"Windows\\System32\\ntdll.dll"
      || (v7 = (const wchar_t **)((char *)trivial_1 - "$CI.CATALOGHINT"), (char *)trivial_1 - "$CI.CATALOGHINT" == -1) )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xE8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\stl.h",
        v6);
    }
    v8 = (char *)Vml::CombineFilePath(SourceString, pszPathIn, L"Windows\\System32\\ntdll.dll");
    v21 = (__int64)"$CI.CATALOGHINT";
    v22 = v7;
    v9 = HasExtendedAttribute(v8, (__int64)&v21);
    std::wstring::~wstring((char **)SourceString);
    if ( !v9 )
    {
      Vml::CombineFilePath(v24, pszPathIn, L"Windows");
      v13 = v24;
      if ( v26 > 7 )
        v13 = (void **)v24[0];
      if ( *(_WORD *)v13 != 92 )
      {
        if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v25) < 4 )
          std::_Xlen_string();
        Src = v24;
        if ( v26 > 7 )
          Src = (void **)v24[0];
        std::wstring::wstring((int)SourceString, v10, v11, v12, 4, Src, v25);
        std::wstring::operator=(v24, SourceString);
        std::wstring::~wstring((char **)SourceString);
      }
      v29 = L"Windows\\System32\\catroot\\{F750E6C3-38EE-11D1-85E5-00C04FC295EE}";
      v28 = L"cat";
      v21 = 1;
      v22 = &v28;
      v23[0] = 1;
      v23[1] = &v29;
      FindFiles((__int64)SourceString, pszPathIn, v23, &v21, 0);
      v15 = SourceString[0];
      v16 = SourceString[1];
      while ( v15 != v16 )
      {
        v17 = v24;
        if ( v26 > 7 )
          v17 = (void **)v24[0];
        if ( *((_QWORD *)v15 + 3) <= 7u )
          v18 = v15;
        else
          v18 = *(const WCHAR **)v15;
        v19 = CiSetHintsForPackageCatalog2(v18, (__int64)v17);
        if ( v19 != -1073741766 && v19 )
        {
          if ( *((_QWORD *)v15 + 3) <= 7u )
            wil::details::in1diag3::Log_NtStatusMsg(
              retaddr,
              (void *)0x197,
              (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
              (const char *)v19,
              (int)"%ws",
              (const char *)v15);
          else
            wil::details::in1diag3::Log_NtStatusMsg(
              retaddr,
              (void *)0x197,
              (unsigned int)"onecore\\vm\\compute\\dll\\lib\\storage\\cicache.cpp",
              (const char *)v19,
              (int)"%ws",
              *(const char **)v15);
        }
        v15 += 16;
      }
      std::vector<std::wstring>::_Tidy(SourceString);
      std::wstring::~wstring((char **)v24);
    }
  }
}

```

## disassembly

```asm
0x180024f88  mov     [rsp-8+arg_8], rbx
0x180024f8d  mov     [rsp-8+arg_10], rsi
0x180024f92  push    rbp
0x180024f93  push    rdi
0x180024f94  push    r14
0x180024f96  lea     rbp, [rsp-47h]
0x180024f9b  sub     rsp, 0C0h
0x180024fa2  mov     rax, cs:__security_cookie
0x180024fa9  xor     rax, rsp
0x180024fac  mov     [rbp+57h+var_20], rax
0x180024fb0  mov     rdi, rcx
0x180024fb3  lea     r8, aWindowsWinsxs; "Windows\\WinSxS"
0x180024fba  mov     rdx, rcx; pszPathIn
0x180024fbd  lea     rcx, [rbp+57h+SourceString]; Src
0x180024fc1  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180024fc6  cmp     qword ptr [rax+18h], 7
0x180024fcb  jbe     short loc_180024FD0
0x180024fcd  mov     rax, [rax]
0x180024fd0  mov     rcx, rax; lpFileName
0x180024fd3  call    cs:__imp_GetFileAttributesW
0x180024fda  nop     dword ptr [rax+rax+00h]
0x180024fdf  mov     ebx, eax
0x180024fe1  lea     rcx, [rbp+57h+SourceString]
0x180024fe5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024fea  cmp     ebx, 0FFFFFFFFh
0x180024fed  jnz     short loc_18002500C
0x180024fef  call    cs:__imp_GetLastError
0x180024ff6  nop     dword ptr [rax+rax+00h]
0x180024ffb  lea     ecx, [rax-2]
0x180024ffe  cmp     ecx, 1
0x180025001  ja      loc_180025205
0x180025007  jmp     loc_1800251DA
0x18002500c  xor     r8d, r8d
0x18002500f  lea     rsi, aWindowsSystem3_3; "Windows\\System32\\ntdll.dll"
0x180025016  mov     rdx, rsi
0x180025019  lea     r14, aCiCataloghint_0; "$CI.CATALOGHINT"
0x180025020  mov     rcx, r14
0x180025023  call    __std_find_trivial_1
0x180025028  mov     rbx, rax
0x18002502b  cmp     rax, rsi
0x18002502e  jz      loc_18002521E
0x180025034  sub     rbx, r14
0x180025037  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002503b  jz      loc_18002521E
0x180025041  lea     r8, aWindowsSystem3_3; "Windows\\System32\\ntdll.dll"
0x180025048  mov     rdx, rdi; pszPathIn
0x18002504b  lea     rcx, [rbp+57h+SourceString]; Src
0x18002504f  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x180025054  nop
0x180025055  mov     [rbp+57h+var_90], r14
0x180025059  mov     [rbp+57h+var_88], rbx
0x18002505d  lea     rdx, [rbp+57h+var_90]
0x180025061  mov     rcx, rax; char *
0x180025064  call    ?HasExtendedAttribute@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_zstring_view@D@wil@@@Z; HasExtendedAttribute(std::wstring const &,wil::basic_zstring_view<char>)
0x180025069  mov     bl, al
0x18002506b  lea     rcx, [rbp+57h+SourceString]
0x18002506f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025074  test    bl, bl
0x180025076  jnz     loc_1800251DA
0x18002507c  lea     r8, aWindows; "Windows"
0x180025083  mov     rdx, rdi; pszPathIn
0x180025086  lea     rcx, [rbp+57h+var_70]; Src
0x18002508a  call    ?CombineFilePath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG0@Z; Vml::CombineFilePath(ushort const *,ushort const *)
0x18002508f  nop
0x180025090  lea     rax, [rbp+57h+var_70]
0x180025094  cmp     [rbp+57h+var_58], 7
0x180025099  cmova   rax, [rbp+57h+var_70]
0x18002509e  cmp     word ptr [rax], 5Ch ; '\'
0x1800250a2  jz      short loc_1800250FF
0x1800250a4  mov     rcx, [rbp+57h+var_60]
0x1800250a8  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800250b2  sub     rax, rcx
0x1800250b5  cmp     rax, 4
0x1800250b9  jb      loc_1800251FF
0x1800250bf  lea     rax, [rbp+57h+var_70]
0x1800250c3  cmp     [rbp+57h+var_58], 7
0x1800250c8  cmova   rax, [rbp+57h+var_70]
0x1800250cd  mov     [rsp+0D0h+var_A0], rcx; __int64
0x1800250d2  mov     [rsp+0D0h+Src], rax; Src
0x1800250d7  mov     [rsp+0D0h+var_B0], 4; __int64
0x1800250e0  lea     rcx, [rbp+57h+SourceString]; int
0x1800250e4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800250e9  lea     rdx, [rbp+57h+SourceString]
0x1800250ed  lea     rcx, [rbp+57h+var_70]
0x1800250f1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800250f6  lea     rcx, [rbp+57h+SourceString]
0x1800250fa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800250ff  lea     rax, aWindowsSystem3_6; "Windows\\System32\\catroot\\{F750E6C3-3"...
0x180025106  mov     [rbp+57h+var_28], rax
0x18002510a  lea     rax, aCat; "cat"
0x180025111  mov     [rbp+57h+var_30], rax
0x180025115  mov     [rbp+57h+var_90], 1
0x18002511d  lea     rax, [rbp+57h+var_30]
0x180025121  mov     [rbp+57h+var_88], rax
0x180025125  mov     [rbp+57h+var_80], 1
0x18002512d  lea     rax, [rbp+57h+var_28]
0x180025131  mov     [rbp+57h+var_78], rax
0x180025135  mov     byte ptr [rsp+0D0h+var_B0], 0
0x18002513a  lea     r9, [rbp+57h+var_90]
0x18002513e  lea     r8, [rbp+57h+var_80]
0x180025142  mov     rdx, rdi
0x180025145  lea     rcx, [rbp+57h+SourceString]
0x180025149  call    ?FindFiles@@YA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEBGV?$span@QEBG$0?0@gsl@@1_N@Z; FindFiles(ushort const *,gsl::span<ushort const * const,-1>,gsl::span<ushort const * const,-1>,bool)
0x18002514e  nop
0x18002514f  mov     rbx, [rbp+57h+SourceString]
0x180025153  mov     rdi, [rbp+57h+var_48]
0x180025157  jmp     short loc_1800251C2
0x180025159  lea     rdx, [rbp+57h+var_70]
0x18002515d  cmp     [rbp+57h+var_58], 7
0x180025162  cmova   rdx, [rbp+57h+var_70]
0x180025167  cmp     qword ptr [rbx+18h], 7
0x18002516c  jbe     short loc_180025173
0x18002516e  mov     rcx, [rbx]
0x180025171  jmp     short loc_180025176
0x180025173  mov     rcx, rbx; SourceString
0x180025176  call    CiSetHintsForPackageCatalog2
0x18002517b  cmp     eax, 0C000003Ah
0x180025180  jz      short loc_1800251BE
0x180025182  test    eax, eax
0x180025184  jz      short loc_1800251BE
0x180025186  cmp     qword ptr [rbx+18h], 7
0x18002518b  jbe     short loc_180025192
0x18002518d  mov     rdx, [rbx]
0x180025190  jmp     short loc_180025195
0x180025192  mov     rdx, rbx
0x180025195  mov     rcx, [rbp+5Fh]; this
0x180025199  mov     [rsp+0D0h+Src], rdx; char *
0x18002519e  lea     rdx, aWs; "%ws"
0x1800251a5  mov     [rsp+0D0h+var_B0], rdx; int
0x1800251aa  mov     r9d, eax; char *
0x1800251ad  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x1800251b4  mov     edx, 197h; void *
0x1800251b9  call    ?Log_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1800251be  add     rbx, 20h ; ' '
0x1800251c2  cmp     rbx, rdi
0x1800251c5  jnz     short loc_180025159
0x1800251c7  lea     rcx, [rbp+57h+SourceString]
0x1800251cb  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800251d0  nop
0x1800251d1  lea     rcx, [rbp+57h+var_70]
0x1800251d5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800251da  mov     rcx, [rbp+57h+var_20]
0x1800251de  xor     rcx, rsp; StackCookie
0x1800251e1  call    __security_check_cookie
0x1800251e6  lea     r11, [rsp+0D0h+var_10]
0x1800251ee  mov     rbx, [r11+28h]
0x1800251f2  mov     rsi, [r11+30h]
0x1800251f6  mov     rsp, r11
0x1800251f9  pop     r14
0x1800251fb  pop     rdi
0x1800251fc  pop     rbp
0x1800251fd  retn
0x1800251ff  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180025205  mov     rcx, [rbp+5Fh]; this
0x180025209  mov     r9d, eax; char *
0x18002520c  lea     r8, aOnecoreVmCompu_4; "onecore\\vm\\compute\\dll\\lib\\storage"...
0x180025213  mov     edx, 179h; void *
0x180025218  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18002521e  mov     rcx, [rbp+5Fh]; this
0x180025222  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180025229  mov     edx, 0E8h; void *
0x18002522e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
