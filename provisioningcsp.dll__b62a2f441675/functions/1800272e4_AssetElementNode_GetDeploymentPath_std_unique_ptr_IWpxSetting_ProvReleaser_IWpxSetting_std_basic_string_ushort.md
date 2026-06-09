# AssetElementNode::_GetDeploymentPath(std::unique_ptr<IWpxSetting,ProvReleaser<IWpxSetting>> &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800272e4`
- end: `0x1800277bb`
- name: `?_GetDeploymentPath@AssetElementNode@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_ptr@UIWpxSetting@@U?$ProvReleaser@UIWpxSetting@@@@@3@AEBV23@@Z`
- size: `1239`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180026dbc`

## callees

- `0x180006974`
- `0x1800090e0`
- `0x180009fac`
- `0x18000f054`
- `0x180022928`
- `0x180026454`
- `0x1800272e4`
- `0x180027a00`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800275b9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800275b9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002752e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002765f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002752e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002765f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800273be`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800273be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800274aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800274aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027647`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027647`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027427`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800275c9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180027427`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800275c9`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18002759d`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18002759d`
- `AppXDeploymentClient!__imp_IsSharedAppsEnabled` at `0x1800276b5`
- `AppXDeploymentClient!__imp_IsSharedAppsEnabled` at `0x1800276b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall AssetElementNode::_GetDeploymentPath(__int64 a1, _QWORD *a2, _QWORD *a3, __int64 a4)
{
  int v8; // eax
  int v9; // eax
  const unsigned __int16 *v10; // rdi
  HRESULT v11; // eax
  __int64 v12; // rax
  int v13; // eax
  DWORD v14; // eax
  int v15; // edi
  WCHAR *v16; // rdx
  __int64 v17; // r8
  _QWORD *v18; // rcx
  LPVOID v19; // rcx
  void (*v20)(void); // rax
  _QWORD *v21; // rcx
  LPVOID v22; // rcx
  PCWSTR *v23; // rax
  HRESULT v24; // eax
  DWORD FileAttributesW; // eax
  int v26; // edi
  PWSTR v27; // rdx
  __int64 v28; // r8
  _QWORD *v29; // rcx
  LPVOID v30; // rcx
  int v31; // eax
  int ppv; // [rsp+20h] [rbp-59h]
  int ppva; // [rsp+20h] [rbp-59h]
  _QWORD *v35; // [rsp+30h] [rbp-49h] BYREF
  LPVOID v36; // [rsp+38h] [rbp-41h] BYREF
  int v37; // [rsp+40h] [rbp-39h] BYREF
  PWSTR ppszPathOut; // [rsp+48h] [rbp-31h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+50h] [rbp-29h] BYREF
  _QWORD *v40; // [rsp+60h] [rbp-19h] BYREF
  void *v41[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v42; // [rsp+80h] [rbp+7h]
  unsigned __int64 v43; // [rsp+88h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v40 = a2;
  v37 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a3 + 208LL))(*a3, &v37);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xFA,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
      (const char *)(unsigned int)v8,
      ppv);
  if ( ((v37 - 4) & 0xFFFFFFFB) != 0 )
  {
    v40 = 0;
    v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(*(_QWORD *)*a3 + 296LL))(*a3, &v40);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10A,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
        (const char *)(unsigned int)v9,
        ppv);
    v10 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(_QWORD *))(*v40 + 184LL))(v40);
    if ( !v10 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x10C,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
        (const char *)0x80070057LL,
        ppv);
    v36 = 0;
    v11 = CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, &v36);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x111,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
        (const char *)(unsigned int)v11,
        ppva);
    v35 = 0;
    if ( (*(int (__fastcall **)(LPVOID, const unsigned __int16 *, _QWORD **))(*(_QWORD *)v36 + 56LL))(v36, v10, &v35) < 0 )
    {
      v43 = 7;
      v42 = 0;
      LOWORD(v41[0]) = 0;
      if ( (unsigned __int8)AssetElementNode::_GetInternalKnownFolder(a1, v10, a4, v41) )
      {
        std::wstring::wstring(a2, v41);
        if ( v43 >= 8 )
          operator delete(v41[0]);
        v43 = 7;
        v42 = 0;
        LOWORD(v41[0]) = 0;
        v21 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
        }
        v22 = v36;
        if ( v36 )
        {
          v36 = 0;
          v20 = *(void (**)(void))(*(_QWORD *)v22 + 16LL);
          goto LABEL_29;
        }
      }
      else
      {
        ppszPathOut = 0;
        v23 = (PCWSTR *)expanded_wstring::expanded_wstring((expanded_wstring *)lpFileName, v10);
        v24 = PathAllocCanonicalize(*v23, 1u, &ppszPathOut);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x125,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
            (const char *)(unsigned int)v24,
            ppva);
        operator delete[]((void *)lpFileName[0]);
        FileAttributesW = GetFileAttributesW(ppszPathOut);
        if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
        {
          v26 = -2147024893;
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC7,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
            (const char *)0x80070003LL,
            ppva);
        }
        else
        {
          v26 = 0;
        }
        if ( v26 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x126,
            (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
            (const char *)(unsigned int)v26,
            ppva);
        v27 = ppszPathOut;
        a2[3] = 7;
        a2[2] = 0;
        *(_WORD *)a2 = 0;
        if ( *v27 )
        {
          v28 = -1;
          do
            ++v28;
          while ( v27[v28] );
        }
        std::wstring::assign(a2, v27);
        if ( ppszPathOut )
          LocalFree(ppszPathOut);
        if ( v43 >= 8 )
          operator delete(v41[0]);
        v43 = 7;
        v42 = 0;
        LOWORD(v41[0]) = 0;
        v29 = v35;
        if ( v35 )
        {
          v35 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
        }
        v30 = v36;
        if ( v36 )
        {
          v36 = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
        }
      }
    }
    else
    {
      lpFileName[0] = 0;
      v12 = *v35;
      lpFileName[0] = 0;
      v13 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, LPCWSTR *))(v12 + 48))(v35, 0, lpFileName);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
          (const char *)(unsigned int)v13,
          ppva);
      v14 = GetFileAttributesW(lpFileName[0]);
      if ( v14 == -1 || (v14 & 0x10) == 0 )
      {
        v15 = -2147024893;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC7,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
          (const char *)0x80070003LL,
          ppva);
      }
      else
      {
        v15 = 0;
      }
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x118,
          (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
          (const char *)(unsigned int)v15,
          ppva);
      v16 = (WCHAR *)lpFileName[0];
      a2[3] = 7;
      a2[2] = 0;
      *(_WORD *)a2 = 0;
      if ( *v16 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v16[v17] );
      }
      std::wstring::assign(a2, v16);
      if ( lpFileName[0] )
        CoTaskMemFree((LPVOID)lpFileName[0]);
      v18 = v35;
      if ( v35 )
      {
        v35 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
      }
      v19 = v36;
      if ( v36 )
      {
        v36 = 0;
        v20 = *(void (**)(void))(*(_QWORD *)v19 + 16LL);
LABEL_29:
        v20();
      }
    }
  }
  else
  {
    v31 = IsSharedAppsEnabled(a1 + 172);
    if ( v31 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\assetelementnode.cpp",
        (const char *)(unsigned int)v31,
        ppv);
    a2[3] = 7;
    a2[2] = 0;
    *(_WORD *)a2 = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x1800272e4  push    rbp
0x1800272e6  push    rbx
0x1800272e7  push    rsi
0x1800272e8  push    rdi
0x1800272e9  push    r12
0x1800272eb  push    r14
0x1800272ed  push    r15
0x1800272ef  lea     rbp, [rsp-27h]
0x1800272f4  sub     rsp, 0A0h
0x1800272fb  mov     rax, cs:__security_cookie
0x180027302  xor     rax, rsp
0x180027305  mov     [rbp+57h+var_40], rax
0x180027309  mov     r15, r9
0x18002730c  mov     rdi, r8
0x18002730f  mov     rbx, rdx
0x180027312  mov     r14, rcx
0x180027315  mov     [rbp+57h+var_70], rdx
0x180027319  xor     r12d, r12d
0x18002731c  mov     [rbp+57h+var_90], r12d
0x180027320  mov     rcx, [r8]
0x180027323  mov     rax, [rcx]
0x180027326  lea     rdx, [rbp+57h+var_90]
0x18002732a  mov     rax, [rax+0D0h]
0x180027331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027336  mov     rcx, [rbp+5Fh]; this
0x18002733a  test    eax, eax
0x18002733c  js      loc_180027725
0x180027342  mov     eax, [rbp+57h+var_90]
0x180027345  add     eax, 0FFFFFFFCh
0x180027348  test    eax, 0FFFFFFFBh
0x18002734d  jz      loc_1800276AE
0x180027353  mov     [rbp+57h+var_70], r12
0x180027357  mov     rcx, [rdi]
0x18002735a  mov     rax, [rcx]
0x18002735d  lea     rdx, [rbp+57h+var_70]
0x180027361  mov     rax, [rax+128h]
0x180027368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002736d  mov     rcx, [rbp+5Fh]; this
0x180027371  test    eax, eax
0x180027373  js      loc_18002773A
0x180027379  mov     rcx, [rbp+57h+var_70]
0x18002737d  mov     rax, [rcx]
0x180027380  mov     rax, [rax+0B8h]
0x180027387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002738c  mov     rdi, rax
0x18002738f  mov     rcx, [rbp+5Fh]; this
0x180027393  test    rax, rax
0x180027396  jz      loc_18002774F
0x18002739c  mov     [rbp+57h+var_98], r12
0x1800273a0  lea     rax, [rbp+57h+var_98]
0x1800273a4  mov     qword ptr [rsp+0D0h+ppv], rax; int
0x1800273a9  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x1800273b0  xor     edx, edx; pUnkOuter
0x1800273b2  lea     r8d, [r12+1]; dwClsContext
0x1800273b7  lea     rcx, CLSID_KnownFolderManager; rclsid
0x1800273be  call    cs:__imp_CoCreateInstance
0x1800273c5  nop     dword ptr [rax+rax+00h]
0x1800273ca  mov     rcx, [rbp+5Fh]; this
0x1800273ce  test    eax, eax
0x1800273d0  js      loc_180027767
0x1800273d6  mov     [rbp+57h+var_A0], r12
0x1800273da  mov     rcx, [rbp+57h+var_98]
0x1800273de  mov     rax, [rcx]
0x1800273e1  lea     r8, [rbp+57h+var_A0]
0x1800273e5  mov     rdx, rdi
0x1800273e8  mov     rax, [rax+38h]
0x1800273ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273f1  test    eax, eax
0x1800273f3  js      loc_1800274EE
0x1800273f9  mov     [rbp+57h+lpFileName], r12
0x1800273fd  mov     rcx, [rbp+57h+var_A0]
0x180027401  mov     rax, [rcx]
0x180027404  mov     [rbp+57h+lpFileName], r12
0x180027408  lea     r8, [rbp+57h+lpFileName]
0x18002740c  xor     edx, edx
0x18002740e  mov     rax, [rax+30h]
0x180027412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027417  mov     rcx, [rbp+5Fh]; this
0x18002741b  test    eax, eax
0x18002741d  js      loc_18002777C
0x180027423  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x180027427  call    cs:__imp_GetFileAttributesW
0x18002742e  nop     dword ptr [rax+rax+00h]
0x180027433  cmp     eax, 0FFFFFFFFh
0x180027436  jz      short loc_180027441
0x180027438  test    al, 10h
0x18002743a  jz      short loc_180027441
0x18002743c  mov     edi, r12d
0x18002743f  jmp     short loc_18002745E
0x180027441  mov     rcx, [rbp+5Fh]; this
0x180027445  mov     edi, 80070003h
0x18002744a  mov     r9d, edi; char *
0x18002744d  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180027454  mov     edx, 0C7h; void *
0x180027459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002745e  mov     rcx, [rbp+5Fh]; this
0x180027462  test    edi, edi
0x180027464  js      loc_180027791
0x18002746a  mov     rdx, [rbp+57h+lpFileName]; Src
0x18002746e  mov     esi, 7
0x180027473  mov     [rbx+18h], rsi
0x180027477  mov     [rbx+10h], r12
0x18002747b  mov     [rbx], r12w
0x18002747f  cmp     [rdx], r12w
0x180027483  jnz     short loc_18002748A
0x180027485  mov     r8, r12
0x180027488  jmp     short loc_180027498
0x18002748a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002748e  inc     r8
0x180027491  cmp     [rdx+r8*2], r12w
0x180027496  jnz     short loc_18002748E
0x180027498  mov     rcx, rbx; void *
0x18002749b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800274a0  nop
0x1800274a1  mov     rcx, [rbp+57h+lpFileName]; pv
0x1800274a5  test    rcx, rcx
0x1800274a8  jz      short loc_1800274B7
0x1800274aa  call    cs:__imp_CoTaskMemFree
0x1800274b1  nop     dword ptr [rax+rax+00h]
0x1800274b6  nop
0x1800274b7  mov     rcx, [rbp+57h+var_A0]
0x1800274bb  test    rcx, rcx
0x1800274be  jz      short loc_1800274D1
0x1800274c0  mov     [rbp+57h+var_A0], r12
0x1800274c4  mov     rax, [rcx]
0x1800274c7  mov     rax, [rax+10h]
0x1800274cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800274d0  nop
0x1800274d1  mov     rcx, [rbp+57h+var_98]
0x1800274d5  test    rcx, rcx
0x1800274d8  jz      loc_18002757B
0x1800274de  mov     [rbp+57h+var_98], r12
0x1800274e2  mov     rax, [rcx]
0x1800274e5  mov     rax, [rax+10h]
0x1800274e9  jmp     loc_180027575
0x1800274ee  mov     esi, 7
0x1800274f3  mov     [rbp+57h+var_48], rsi
0x1800274f7  mov     [rbp+57h+var_50], r12
0x1800274fb  mov     word ptr [rbp+57h+var_60], r12w
0x180027500  lea     r9, [rbp+57h+var_60]
0x180027504  mov     r8, r15
0x180027507  mov     rdx, rdi
0x18002750a  mov     rcx, r14
0x18002750d  call    ?_GetInternalKnownFolder@AssetElementNode@@AEAA_NPEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAV23@@Z; AssetElementNode::_GetInternalKnownFolder(ushort const *,std::wstring const &,std::wstring *)
0x180027512  test    al, al
0x180027514  jz      short loc_180027580
0x180027516  lea     rdx, [rbp+57h+var_60]
0x18002751a  mov     rcx, rbx
0x18002751d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180027522  nop
0x180027523  cmp     [rbp+57h+var_48], 8
0x180027528  jb      short loc_18002753A
0x18002752a  mov     rcx, [rbp+57h+var_60]
0x18002752e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027535  nop     dword ptr [rax+rax+00h]
0x18002753a  mov     [rbp+57h+var_48], rsi
0x18002753e  mov     [rbp+57h+var_50], r12
0x180027542  mov     word ptr [rbp+57h+var_60], r12w
0x180027547  mov     rcx, [rbp+57h+var_A0]
0x18002754b  test    rcx, rcx
0x18002754e  jz      short loc_180027561
0x180027550  mov     [rbp+57h+var_A0], r12
0x180027554  mov     rax, [rcx]
0x180027557  mov     rax, [rax+10h]
0x18002755b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027560  nop
0x180027561  mov     rcx, [rbp+57h+var_98]
0x180027565  test    rcx, rcx
0x180027568  jz      short loc_18002757B
0x18002756a  mov     [rbp+57h+var_98], r12
0x18002756e  mov     rdx, [rcx]
0x180027571  mov     rax, [rdx+10h]
0x180027575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002757a  nop
0x18002757b  jmp     loc_1800276EE
0x180027580  mov     [rbp+57h+ppszPathOut], r12
0x180027584  mov     rdx, rdi; unsigned __int16 *
0x180027587  lea     rcx, [rbp+57h+lpFileName]; this
0x18002758b  call    ??0expanded_wstring@@QEAA@PEBG@Z; expanded_wstring::expanded_wstring(ushort const *)
0x180027590  nop
0x180027591  lea     r8, [rbp+57h+ppszPathOut]; ppszPathOut
0x180027595  mov     edx, 1; dwFlags
0x18002759a  mov     rcx, [rax]; pszPathIn
0x18002759d  call    cs:__imp_PathAllocCanonicalize
0x1800275a4  nop     dword ptr [rax+rax+00h]
0x1800275a9  mov     rcx, [rbp+5Fh]; this
0x1800275ad  test    eax, eax
0x1800275af  js      loc_1800277A6
0x1800275b5  mov     rcx, [rbp+57h+lpFileName]
0x1800275b9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800275c0  nop     dword ptr [rax+rax+00h]
0x1800275c5  mov     rcx, [rbp+57h+ppszPathOut]; lpFileName
0x1800275c9  call    cs:__imp_GetFileAttributesW
0x1800275d0  nop     dword ptr [rax+rax+00h]
0x1800275d5  cmp     eax, 0FFFFFFFFh
0x1800275d8  jz      short loc_1800275E3
0x1800275da  test    al, 10h
0x1800275dc  jz      short loc_1800275E3
0x1800275de  mov     edi, r12d
0x1800275e1  jmp     short loc_180027600
0x1800275e3  mov     rcx, [rbp+5Fh]; this
0x1800275e7  mov     edi, 80070003h
0x1800275ec  mov     r9d, edi; char *
0x1800275ef  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800275f6  mov     edx, 0C7h; void *
0x1800275fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027600  mov     rcx, [rbp+5Fh]; this
0x180027604  test    edi, edi
0x180027606  js      loc_180027710
0x18002760c  mov     rdx, [rbp+57h+ppszPathOut]; Src
0x180027610  mov     [rbx+18h], rsi
0x180027614  mov     [rbx+10h], r12
0x180027618  mov     [rbx], r12w
0x18002761c  cmp     [rdx], r12w
0x180027620  jnz     short loc_180027627
0x180027622  mov     r8, r12
0x180027625  jmp     short loc_180027635
0x180027627  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002762b  inc     r8
0x18002762e  cmp     [rdx+r8*2], r12w
0x180027633  jnz     short loc_18002762B
0x180027635  mov     rcx, rbx; void *
0x180027638  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002763d  nop
0x18002763e  mov     rcx, [rbp+57h+ppszPathOut]; hMem
0x180027642  test    rcx, rcx
0x180027645  jz      short loc_180027654
0x180027647  call    cs:__imp_LocalFree
0x18002764e  nop     dword ptr [rax+rax+00h]
0x180027653  nop
0x180027654  cmp     [rbp+57h+var_48], 8
0x180027659  jb      short loc_18002766B
0x18002765b  mov     rcx, [rbp+57h+var_60]
0x18002765f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180027666  nop     dword ptr [rax+rax+00h]
0x18002766b  mov     [rbp+57h+var_48], rsi
0x18002766f  mov     [rbp+57h+var_50], r12
0x180027673  mov     word ptr [rbp+57h+var_60], r12w
0x180027678  mov     rcx, [rbp+57h+var_A0]
0x18002767c  test    rcx, rcx
0x18002767f  jz      short loc_180027692
0x180027681  mov     [rbp+57h+var_A0], r12
0x180027685  mov     rax, [rcx]
0x180027688  mov     rax, [rax+10h]
0x18002768c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027691  nop
0x180027692  mov     rcx, [rbp+57h+var_98]
0x180027696  test    rcx, rcx
0x180027699  jz      short loc_1800276AC
0x18002769b  mov     [rbp+57h+var_98], r12
0x18002769f  mov     rax, [rcx]
0x1800276a2  mov     rax, [rax+10h]
0x1800276a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276ab  nop
0x1800276ac  jmp     short loc_1800276EE
0x1800276ae  lea     rcx, [r14+0ACh]
0x1800276b5  call    cs:__imp_IsSharedAppsEnabled
0x1800276bc  nop     dword ptr [rax+rax+00h]
0x1800276c1  test    eax, eax
0x1800276c3  jns     short loc_1800276DD
0x1800276c5  mov     rcx, [rbp+5Fh]; this
0x1800276c9  mov     r9d, eax; char *
0x1800276cc  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x1800276d3  mov     edx, 101h; void *
0x1800276d8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800276dd  mov     esi, 7
0x1800276e2  mov     [rbx+18h], rsi
0x1800276e6  mov     [rbx+10h], r12
0x1800276ea  mov     [rbx], r12w
0x1800276ee  mov     rax, rbx
0x1800276f1  mov     rcx, [rbp+57h+var_40]
0x1800276f5  xor     rcx, rsp; StackCookie
0x1800276f8  call    __security_check_cookie
0x1800276fd  add     rsp, 0A0h
0x180027704  pop     r15
0x180027706  pop     r14
0x180027708  pop     r12
0x18002770a  pop     rdi
0x18002770b  pop     rsi
0x18002770c  pop     rbx
0x18002770d  pop     rbp
0x18002770e  retn
0x180027710  mov     r9d, edi; char *
0x180027713  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x18002771a  mov     edx, 126h; void *
0x18002771f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027725  mov     r9d, eax; char *
0x180027728  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x18002772f  mov     edx, 0FAh; void *
0x180027734  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002773a  mov     r9d, eax; char *
0x18002773d  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x180027744  mov     edx, 10Ah; void *
0x180027749  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002774f  mov     r9d, 80070057h; char *
0x180027755  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
0x18002775c  mov     edx, 10Ch; void *
0x180027761  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180027767  mov     r9d, eax; char *
0x18002776a  lea     r8, aOnecoreuapAdmi_25; "onecoreuap\\admin\\prov\\provcsp\\asset"...
  ... truncated ...
```
