# CflApiNew::UpdateCorrelationVectorString(char const *)

- ea: `0x18002c204`
- end: `0x18002c49d`
- name: `?UpdateCorrelationVectorString@CflApiNew@@YAJPEBD@Z`
- size: `665`
- prototype: `__int64 __fastcall(CflApiNew *__hidden this, const char *)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180011540`
- `0x180012210`
- `0x180029614`
- `0x18002aee8`

## callees

- `0x180002490`
- `0x180008a68`
- `0x180008ad0`
- `0x180019fb8`
- `0x18001f948`
- `0x180028124`
- `0x18002c204`
- `0x18002c9c8`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c2ba`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002c2ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c38d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002c38d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c2ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c3bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c41f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c2ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c3bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002c41f`

## string_xrefs

- `0x18002c2cf`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002c39e`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CflApiNew::UpdateCorrelationVectorString(CflApiNew *this, const char *a2)
{
  _QWORD *v3; // rax
  _QWORD *v4; // r8
  unsigned int v5; // eax
  __int64 v6; // rdx
  unsigned int v7; // edi
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  void (__fastcall ***v11)(_QWORD, __int64); // rax
  void (__fastcall ***v12)(_QWORD, __int64); // r8
  const BYTE *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  void (__fastcall ***v24)(_QWORD, __int64); // rax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE *lpData[2]; // [rsp+58h] [rbp-A8h] BYREF
  int v29; // [rsp+68h] [rbp-98h]
  unsigned __int64 v30; // [rsp+70h] [rbp-90h]
  _QWORD v31[3]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h]
  _BYTE v33[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[64]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v35[32]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+38h]

  std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(
    v31,
    a2);
  v3 = (_QWORD *)std::string::string(v35, this);
  if ( v3[3] <= 0xFu )
    v4 = v3;
  else
    v4 = (_QWORD *)*v3;
  std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v31,
    lpData,
    v4,
    (char *)v4 + v3[2]);
  std::string::~string(v35);
  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Authentication\\CFL\\CorrelationVector",
         0,
         0,
         0,
         0x20006u,
         0,
         &hKey,
         0);
  if ( v5 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1F6,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
           (const char *)v5,
           dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    std::wstring::~wstring(lpData, v6, v8);
    v31[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::~wstring(v34, v9, v10);
    std::string::~string(v33);
    if ( !v32 )
      return v7;
    v11 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v12 = v11;
    if ( !v11 )
      return v7;
    goto LABEL_9;
  }
  v14 = (const BYTE *)lpData;
  if ( v30 > 7 )
    v14 = lpData[0];
  v15 = RegSetValueExW(hKey, L"WSI", 0, 1u, v14, 2 * v29 + 2);
  if ( v15 )
  {
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x1FF,
           (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
           (const char *)v15,
           dwOptionsa);
    if ( hKey )
      RegCloseKey(hKey);
    std::wstring::~wstring(lpData, v18, v19);
    v31[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
    std::wstring::~wstring(v34, v20, v21);
    std::string::~string(v33);
    if ( !v32 )
      return v7;
    v11 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v12 = v11;
    if ( !v11 )
      return v7;
LABEL_9:
    (**v11)(v12, 1);
    return v7;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpData, v16, v17);
  v31[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
  std::wstring::~wstring(v34, v22, v23);
  std::string::~string(v33);
  if ( v32 )
  {
    v24 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    if ( v24 )
      (**v24)(v24, 1);
  }
  return 0;
}

```

## disassembly

```asm
0x18002c204  mov     [rsp-8+arg_8], rbx
0x18002c209  mov     [rsp-8+arg_10], rdi
0x18002c20e  push    rbp
0x18002c20f  lea     rbp, [rsp-30h]
0x18002c214  sub     rsp, 130h
0x18002c21b  mov     rax, cs:__security_cookie
0x18002c222  xor     rax, rsp
0x18002c225  mov     [rbp+30h+var_10], rax
0x18002c229  mov     rbx, rcx
0x18002c22c  lea     rcx, [rbp+30h+var_B0]
0x18002c230  call    ??0?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18002c235  nop
0x18002c236  mov     rdx, rbx
0x18002c239  lea     rcx, [rbp+30h+var_30]
0x18002c23d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002c242  nop
0x18002c243  cmp     qword ptr [rax+18h], 0Fh
0x18002c248  jbe     short loc_18002C24F
0x18002c24a  mov     r8, [rax]
0x18002c24d  jmp     short loc_18002C252
0x18002c24f  mov     r8, rax
0x18002c252  mov     r9, [rax+10h]
0x18002c256  add     r9, r8
0x18002c259  lea     rdx, [rsp+130h+lpData]
0x18002c25e  lea     rcx, [rbp+30h+var_B0]
0x18002c262  call    ?from_bytes@?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x18002c267  nop
0x18002c268  lea     rcx, [rbp+30h+var_30]
0x18002c26c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002c271  mov     [rsp+130h+hKey], 0
0x18002c27a  mov     [rsp+130h+lpdwDisposition], 0; lpdwDisposition
0x18002c283  lea     rax, [rsp+130h+hKey]
0x18002c288  mov     [rsp+130h+phkResult], rax; phkResult
0x18002c28d  mov     [rsp+130h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002c296  mov     [rsp+130h+samDesired], 20006h; samDesired
0x18002c29e  mov     [rsp+130h+dwOptions], 0; unsigned int
0x18002c2a6  xor     r9d, r9d; lpClass
0x18002c2a9  xor     r8d, r8d; Reserved
0x18002c2ac  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002c2b3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002c2ba  call    cs:__imp_RegCreateKeyExW
0x18002c2c0  test    eax, eax
0x18002c2c2  jz      loc_18002C351
0x18002c2c8  mov     rcx, [rbp+38h]; this
0x18002c2cc  mov     r9d, eax; char *
0x18002c2cf  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002c2d6  mov     edx, 1F6h; void *
0x18002c2db  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c2e0  mov     edi, eax
0x18002c2e2  mov     rcx, [rsp+130h+hKey]; hKey
0x18002c2e7  test    rcx, rcx
0x18002c2ea  jz      short loc_18002C2F2
0x18002c2ec  call    cs:__imp_RegCloseKey
0x18002c2f2  lea     rcx, [rsp+130h+lpData]
0x18002c2f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c2fc  nop
0x18002c2fd  lea     rcx, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18002c304  mov     [rbp+30h+var_B0], rcx
0x18002c308  lea     rcx, [rbp+30h+var_70]
0x18002c30c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c311  lea     rcx, [rbp+30h+var_90]
0x18002c315  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002c31a  mov     rcx, [rbp+30h+var_98]
0x18002c31e  test    rcx, rcx
0x18002c321  jz      short loc_18002C34A
0x18002c323  mov     rax, [rcx]
0x18002c326  mov     rax, [rax+10h]
0x18002c32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c32f  mov     r8, rax
0x18002c332  test    rax, rax
0x18002c335  jz      short loc_18002C34A
0x18002c337  mov     edx, 1
0x18002c33c  mov     rcx, [rax]
0x18002c33f  mov     rax, [rcx]
0x18002c342  mov     rcx, r8
0x18002c345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c34a  mov     eax, edi
0x18002c34c  jmp     loc_18002C47C
0x18002c351  mov     eax, [rsp+130h+var_C8]
0x18002c355  lea     rdx, [rsp+130h+lpData]
0x18002c35a  cmp     [rsp+130h+var_C0], 7
0x18002c360  cmova   rdx, [rsp+130h+lpData]
0x18002c366  lea     eax, ds:2[rax*2]
0x18002c36d  mov     [rsp+130h+samDesired], eax; cbData
0x18002c371  mov     qword ptr [rsp+130h+dwOptions], rdx; unsigned int
0x18002c376  mov     ebx, 1
0x18002c37b  mov     r9d, ebx; dwType
0x18002c37e  xor     r8d, r8d; Reserved
0x18002c381  lea     rdx, aWsi; "WSI"
0x18002c388  mov     rcx, [rsp+130h+hKey]; hKey
0x18002c38d  call    cs:__imp_RegSetValueExW
0x18002c393  test    eax, eax
0x18002c395  jz      short loc_18002C415
0x18002c397  mov     rcx, [rbp+38h]; this
0x18002c39b  mov     r9d, eax; char *
0x18002c39e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002c3a5  mov     edx, 1FFh; void *
0x18002c3aa  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002c3af  mov     edi, eax
0x18002c3b1  mov     rcx, [rsp+130h+hKey]; hKey
0x18002c3b6  test    rcx, rcx
0x18002c3b9  jz      short loc_18002C3C1
0x18002c3bb  call    cs:__imp_RegCloseKey
0x18002c3c1  lea     rcx, [rsp+130h+lpData]
0x18002c3c6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c3cb  nop
0x18002c3cc  lea     rcx, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18002c3d3  mov     [rbp+30h+var_B0], rcx
0x18002c3d7  lea     rcx, [rbp+30h+var_70]
0x18002c3db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c3e0  lea     rcx, [rbp+30h+var_90]
0x18002c3e4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002c3e9  mov     rcx, [rbp+30h+var_98]
0x18002c3ed  test    rcx, rcx
0x18002c3f0  jz      loc_18002C34A
0x18002c3f6  mov     rax, [rcx]
0x18002c3f9  mov     rax, [rax+10h]
0x18002c3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c402  mov     r8, rax
0x18002c405  test    rax, rax
0x18002c408  jz      loc_18002C34A
0x18002c40e  mov     edx, ebx
0x18002c410  jmp     loc_18002C33C
0x18002c415  mov     rcx, [rsp+130h+hKey]; hKey
0x18002c41a  test    rcx, rcx
0x18002c41d  jz      short loc_18002C425
0x18002c41f  call    cs:__imp_RegCloseKey
0x18002c425  lea     rcx, [rsp+130h+lpData]
0x18002c42a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c42f  nop
0x18002c430  lea     rcx, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18002c437  mov     [rbp+30h+var_B0], rcx
0x18002c43b  lea     rcx, [rbp+30h+var_70]
0x18002c43f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002c444  lea     rcx, [rbp+30h+var_90]
0x18002c448  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002c44d  mov     rcx, [rbp+30h+var_98]
0x18002c451  test    rcx, rcx
0x18002c454  jz      short loc_18002C47A
0x18002c456  mov     rax, [rcx]
0x18002c459  mov     rax, [rax+10h]
0x18002c45d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c462  mov     r8, rax
0x18002c465  test    rax, rax
0x18002c468  jz      short loc_18002C47A
0x18002c46a  mov     rcx, [rax]
0x18002c46d  mov     rax, [rcx]
0x18002c470  mov     edx, ebx
0x18002c472  mov     rcx, r8
0x18002c475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c47a  xor     eax, eax
0x18002c47c  mov     rcx, [rbp+30h+var_10]
0x18002c480  xor     rcx, rsp; StackCookie
0x18002c483  call    __security_check_cookie
0x18002c488  lea     r11, [rsp+130h+var_s0]
0x18002c490  mov     rbx, [r11+18h]
0x18002c494  mov     rdi, [r11+20h]
0x18002c498  mov     rsp, r11
0x18002c49b  pop     rbp
0x18002c49c  retn
```
