# CConsoleFilePersistor::ScGetUserDataPath(ushort const *,tstring &)

- ea: `0x140037144`
- end: `0x14003732a`
- name: `?ScGetUserDataPath@CConsoleFilePersistor@@CA?AVSC@mmcerror@@PEBGAEAVtstring@@@Z`
- size: `486`
- prototype: `mmcerror::SC *__fastcall(mmcerror::SC *, const wchar_t *, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1400e073c`
- `0x1400e1438`

## callees

- `0x140037144`
- `0x1400412e8`
- `0x14005b5cc`
- `0x1400cad30`
- `0x1400e0310`

## import_xrefs

- `msvcrt!wcsrchr` at `0x1400371d9`
- `msvcrt!wcsrchr` at `0x1400371d9`
- `msvcrt!iswspace` at `0x1400371ff`
- `msvcrt!iswspace` at `0x1400371ff`
- `msvcrt!_wcsicmp` at `0x1400372bf`
- `msvcrt!_wcsicmp` at `0x1400372bf`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400371aa`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003723e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400372fd`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400371aa`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x14003723e`
- `mmcbase!??1SC@mmcerror@@QEAA@XZ` at `0x1400372fd`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400371b4`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140037248`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x1400371b4`
- `mmcbase!??BSC@mmcerror@@QEBA_NXZ` at `0x140037248`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140037168`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140037190`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140037168`
- `mmcbase!??0SC@mmcerror@@QEAA@J@Z` at `0x140037190`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140037293`
- `mmcbase!?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ` at `0x140037293`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14003731e`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@J@Z` at `0x14003731e`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400372f2`
- `mmcbase!??0SC@mmcerror@@QEAA@AEBV01@@Z` at `0x1400372f2`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003719f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140037233`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x14003719f`
- `mmcbase!??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z` at `0x140037233`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003717a`
- `mmcbase!?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z` at `0x14003717a`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140037285`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x140037285`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140037265`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x140037265`

## string_xrefs

- `0x14003716f`: `CConsoleFilePersistor::ScGetUserDataPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
mmcerror::SC *__fastcall CConsoleFilePersistor::ScGetUserDataPath(mmcerror::SC *a1, const wchar_t *a2, __int64 a3)
{
  int v6; // edx
  __int64 v7; // rsi
  wchar_t *v8; // rax
  wint_t *v9; // rbx
  wint_t v10; // ax
  __int64 UserDataFolder; // rax
  const WCHAR *v12; // rcx
  DWORD FileAttributesW; // eax
  const WCHAR *v14; // rcx
  struct mmcerror::SC *Error; // rax
  const struct mmcerror::SC *v16; // rdx
  _BYTE v18[24]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v19[32]; // [rsp+40h] [rbp-20h] BYREF

  mmcerror::SC::SC((mmcerror::SC *)v18, 0);
  mmcerror::SC::SetFunctionName((mmcerror::SC *)v18, L"CConsoleFilePersistor::ScGetUserDataPath");
  v6 = -2147024809;
  if ( a2 )
    v6 = 0;
  mmcerror::SC::SC((mmcerror::SC *)v19, v6);
  mmcerror::SC::operator=(v18, v19);
  mmcerror::SC::~SC((mmcerror::SC *)v19);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v18) )
    goto LABEL_28;
  v7 = -1;
  std::wstring::erase(a3, 0, -1);
  v8 = wcsrchr(a2, 0x5Cu);
  if ( v8 )
    v9 = v8 + 1;
  else
    v9 = (wint_t *)a2;
  v10 = *v9;
  if ( !*v9 )
    goto LABEL_30;
  do
  {
    if ( !iswspace(v10) )
      break;
    v10 = *++v9;
  }
  while ( *v9 );
  if ( !*v9 )
  {
LABEL_30:
    Error = (struct mmcerror::SC *)mmcerror::SC::operator=(v18, 2147942487LL);
    goto LABEL_22;
  }
  UserDataFolder = CConsoleFilePersistor::ScGetUserDataFolder(v19, a3);
  mmcerror::SC::operator=(v18, UserDataFolder);
  mmcerror::SC::~SC((mmcerror::SC *)v19);
  if ( (unsigned __int8)mmcerror::SC::operator bool(v18) )
  {
LABEL_28:
    v16 = (const struct mmcerror::SC *)v18;
    goto LABEL_29;
  }
  if ( *(_QWORD *)(a3 + 24) < 8u )
    v12 = (const WCHAR *)a3;
  else
    v12 = *(const WCHAR **)a3;
  FileAttributesW = GetFileAttributesW(v12);
  if ( (FileAttributesW & 0x10) != 0 && FileAttributesW != -1
    || (*(_QWORD *)(a3 + 24) < 8u ? (v14 = (const WCHAR *)a3) : (v14 = *(const WCHAR **)a3), CreateDirectoryW(v14, 0)) )
  {
    do
      ++v7;
    while ( v9[v7] );
    if ( (int)v7 > 4 && !_wcsicmp(L".msc", &v9[(int)v7 - 4]) )
      LODWORD(v7) = v7 - 3;
    std::wstring::append(a3, 1, 92);
    std::wstring::append(a3, v9, (int)v7);
    goto LABEL_28;
  }
  Error = mmcerror::SC::FromLastError((mmcerror::SC *)v18);
LABEL_22:
  v16 = Error;
LABEL_29:
  mmcerror::SC::SC(a1, v16);
  mmcerror::SC::~SC((mmcerror::SC *)v18);
  return a1;
}

```

## disassembly

```asm
0x140037144  push    rbp
0x140037146  push    rbx
0x140037147  push    rsi
0x140037148  push    rdi
0x140037149  push    r12
0x14003714b  push    r14
0x14003714d  push    r15
0x14003714f  mov     rbp, rsp
0x140037152  sub     rsp, 60h
0x140037156  mov     rdi, r8
0x140037159  mov     r15, rdx
0x14003715c  mov     r14, rcx
0x14003715f  xor     r12d, r12d
0x140037162  xor     edx, edx
0x140037164  lea     rcx, [rbp+var_38]
0x140037168  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x14003716e  nop
0x14003716f  lea     rdx, aCconsolefilepe_0; "CConsoleFilePersistor::ScGetUserDataPat"...
0x140037176  lea     rcx, [rbp+var_38]
0x14003717a  call    cs:__imp_?SetFunctionName@SC@mmcerror@@QEAAXPEBG@Z; mmcerror::SC::SetFunctionName(ushort const *)
0x140037180  mov     edx, 80070057h
0x140037185  test    r15, r15
0x140037188  cmovnz  edx, r12d
0x14003718c  lea     rcx, [rbp+var_20]
0x140037190  call    cs:__imp_??0SC@mmcerror@@QEAA@J@Z; mmcerror::SC::SC(long)
0x140037196  nop
0x140037197  lea     rdx, [rbp+var_20]
0x14003719b  lea     rcx, [rbp+var_38]
0x14003719f  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x1400371a5  nop
0x1400371a6  lea     rcx, [rbp+var_20]
0x1400371aa  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x1400371b0  lea     rcx, [rbp+var_38]
0x1400371b4  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x1400371ba  test    al, al
0x1400371bc  jnz     loc_1400372EB
0x1400371c2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1400371c6  mov     r8, rsi
0x1400371c9  xor     edx, edx
0x1400371cb  mov     rcx, rdi
0x1400371ce  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x1400371d3  lea     edx, [rsi+5Dh]; Ch
0x1400371d6  mov     rcx, r15; Str
0x1400371d9  call    cs:__imp_wcsrchr
0x1400371df  mov     rbx, rax
0x1400371e2  test    rax, rax
0x1400371e5  jnz     short loc_1400371EC
0x1400371e7  mov     rbx, r15
0x1400371ea  jmp     short loc_1400371F0
0x1400371ec  add     rbx, 2
0x1400371f0  movzx   eax, word ptr [rbx]
0x1400371f3  test    ax, ax
0x1400371f6  jz      loc_140037315
0x1400371fc  movzx   ecx, ax; C
0x1400371ff  call    cs:__imp_iswspace
0x140037205  test    eax, eax
0x140037207  jz      short loc_140037215
0x140037209  add     rbx, 2
0x14003720d  movzx   eax, word ptr [rbx]
0x140037210  test    ax, ax
0x140037213  jnz     short loc_1400371FC
0x140037215  cmp     [rbx], r12w
0x140037219  jz      loc_140037315
0x14003721f  mov     rdx, rdi
0x140037222  lea     rcx, [rbp+var_20]
0x140037226  call    ?ScGetUserDataFolder@CConsoleFilePersistor@@SA?AVSC@mmcerror@@AEAVtstring@@@Z; CConsoleFilePersistor::ScGetUserDataFolder(tstring &)
0x14003722b  nop
0x14003722c  mov     rdx, rax
0x14003722f  lea     rcx, [rbp+var_38]
0x140037233  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@AEBV01@@Z; mmcerror::SC::operator=(mmcerror::SC const &)
0x140037239  nop
0x14003723a  lea     rcx, [rbp+var_20]
0x14003723e  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140037244  lea     rcx, [rbp+var_38]
0x140037248  call    cs:__imp_??BSC@mmcerror@@QEBA_NXZ; mmcerror::SC::operator bool(void)
0x14003724e  test    al, al
0x140037250  jnz     loc_1400372EB
0x140037256  cmp     qword ptr [rdi+18h], 8
0x14003725b  jb      short loc_140037262
0x14003725d  mov     rcx, [rdi]
0x140037260  jmp     short loc_140037265
0x140037262  mov     rcx, rdi; lpFileName
0x140037265  call    cs:__imp_GetFileAttributesW
0x14003726b  test    al, 10h
0x14003726d  jz      short loc_140037274
0x14003726f  cmp     eax, 0FFFFFFFFh
0x140037272  jnz     short loc_14003729E
0x140037274  cmp     qword ptr [rdi+18h], 8
0x140037279  jb      short loc_140037280
0x14003727b  mov     rcx, [rdi]
0x14003727e  jmp     short loc_140037283
0x140037280  mov     rcx, rdi; lpPathName
0x140037283  xor     edx, edx; lpSecurityAttributes
0x140037285  call    cs:__imp_CreateDirectoryW
0x14003728b  test    eax, eax
0x14003728d  jnz     short loc_14003729E
0x14003728f  lea     rcx, [rbp+var_38]
0x140037293  call    cs:__imp_?FromLastError@SC@mmcerror@@QEAAAEAV12@XZ; mmcerror::SC::FromLastError(void)
0x140037299  mov     rdx, rax
0x14003729c  jmp     short loc_1400372EF
0x14003729e  inc     rsi
0x1400372a1  cmp     [rbx+rsi*2], r12w
0x1400372a6  jnz     short loc_14003729E
0x1400372a8  cmp     esi, 4
0x1400372ab  jle     short loc_1400372CC
0x1400372ad  movsxd  rax, esi
0x1400372b0  add     rax, 0FFFFFFFFFFFFFFFCh
0x1400372b4  lea     rdx, [rbx+rax*2]; String2
0x1400372b8  lea     rcx, aMsc; ".msc"
0x1400372bf  call    cs:__imp__wcsicmp
0x1400372c5  test    eax, eax
0x1400372c7  jnz     short loc_1400372CC
0x1400372c9  sub     esi, 3
0x1400372cc  mov     edx, 1
0x1400372d1  lea     r8d, [rdx+5Bh]
0x1400372d5  mov     rcx, rdi
0x1400372d8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x1400372dd  movsxd  r8, esi
0x1400372e0  mov     rdx, rbx
0x1400372e3  mov     rcx, rdi
0x1400372e6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1400372eb  lea     rdx, [rbp+var_38]
0x1400372ef  mov     rcx, r14
0x1400372f2  call    cs:__imp_??0SC@mmcerror@@QEAA@AEBV01@@Z; mmcerror::SC::SC(mmcerror::SC const &)
0x1400372f8  nop
0x1400372f9  lea     rcx, [rbp+var_38]
0x1400372fd  call    cs:__imp_??1SC@mmcerror@@QEAA@XZ; mmcerror::SC::~SC(void)
0x140037303  mov     rax, r14
0x140037306  add     rsp, 60h
0x14003730a  pop     r15
0x14003730c  pop     r14
0x14003730e  pop     r12
0x140037310  pop     rdi
0x140037311  pop     rsi
0x140037312  pop     rbx
0x140037313  pop     rbp
0x140037314  retn
0x140037315  mov     edx, 80070057h
0x14003731a  lea     rcx, [rbp+var_38]
0x14003731e  call    cs:__imp_??4SC@mmcerror@@QEAAAEAV01@J@Z; mmcerror::SC::operator=(long)
0x140037324  jmp     loc_140037299
```
