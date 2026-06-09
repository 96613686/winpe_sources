# DeclaredConfigurationStore_CheckForCorruption(ushort *,ushort *,ushort *)

- ea: `0x1400585f0`
- end: `0x140058a55`
- name: `?DeclaredConfigurationStore_CheckForCorruption@@YAJPEAG00@Z`
- size: `1125`
- prototype: `int(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config`

## callers

- `0x140056b74`
- `0x140058a5c`

## callees

- `0x1400036e4`
- `0x14000b0f4`
- `0x1400575f0`
- `0x1400576f0`
- `0x1400580ac`
- `0x140058460`
- `0x1400585f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005876d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400589cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058a2b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058669`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14005876d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058888`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400589cf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140058a2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058658`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058658`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140058677`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140058677`

## string_xrefs

- `0x140058695`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\omadmalert\lib\dcalert.cpp`
- `0x14005872e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\omadmalert\lib\dcalert.cpp`
- `0x1400587eb`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\omadmalert\lib\dcalert.cpp`
- `0x140058834`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\omadmalert\lib\dcalert.cpp`
- `0x1400588ed`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\omadmalert\lib\dcalert.cpp`
- `0x14005895f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\omadmalert\lib\dcalert.cpp`
- `0x1400589a1`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\omadmalert\lib\dcalert.cpp`

## pseudocode

```c
__int64 __fastcall DeclaredConfigurationStore_CheckForCorruption(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  int v4; // r13d
  unsigned __int16 *v5; // r14
  int v6; // esi
  _QWORD *v7; // rdi
  __int64 v8; // r15
  HKEY v9; // r14
  DWORD LastError; // ebx
  int v11; // ebx
  void *v12; // rcx
  void *v14; // rcx
  int v15; // eax
  HKEY v16; // rbx
  void *v17; // rcx
  void *v18; // rcx
  int v19; // eax
  int v20; // [rsp+20h] [rbp-60h]
  void *v21; // [rsp+40h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-38h] BYREF
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR v24; // [rsp+58h] [rbp-28h] BYREF
  HKEY v25; // [rsp+60h] [rbp-20h]
  _QWORD *p_hKey; // [rsp+68h] [rbp-18h]
  __int64 v27; // [rsp+70h] [rbp-10h] BYREF
  char v28; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  void *Block; // [rsp+D8h] [rbp+58h] BYREF

  v28 = 1;
  hKey = 0;
  v21 = 0;
  Block = 0;
  p_hKey = &hKey;
  v4 = (int)a2;
  v27 = 0;
  v5 = a1;
  v6 = DCGetReadonlyEnrollmentIdSidStateKey(a1, a2, &v27);
  if ( v28 )
  {
    v7 = p_hKey;
    v8 = v27;
    v9 = (HKEY)*p_hKey;
    if ( *p_hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v9);
      SetLastError(LastError);
    }
    v5 = a1;
    *v7 = v8;
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x417,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\omadmalert\\lib\\dcalert.cpp",
      (const char *)(unsigned int)v6,
      v20);
    if ( Block )
      operator delete(Block);
    if ( v21 )
      operator delete(v21);
LABEL_62:
    if ( hKey )
      RegCloseKey(hKey);
    return (unsigned int)v6;
  }
  p_hKey = &Block;
  v27 = 0;
  v28 = 1;
  v11 = DCGetRegistryString(hKey, a3, L"MostRecentVersion", &v27);
  if ( v28 )
  {
    v12 = (void *)*p_hKey;
    *p_hKey = v27;
    if ( v12 )
      operator delete(v12);
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x41F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\omadmalert\\lib\\dcalert.cpp",
      (const char *)(unsigned int)v11,
      v20);
LABEL_15:
    if ( Block )
      operator delete(Block);
    if ( v21 )
      operator delete(v21);
    goto LABEL_19;
  }
  p_hKey = &lpSubKey;
  lpSubKey = 0;
  v27 = 0;
  v28 = 1;
  v11 = DCStringCchPrintfAllStrings(&v27, qword_140085180, 4, v5);
  if ( v28 )
  {
    v14 = (void *)*p_hKey;
    *p_hKey = v27;
    if ( v14 )
      operator delete(v14);
  }
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x42B,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\omadmalert\\lib\\dcalert.cpp",
      (const char *)(unsigned int)v11,
      v4);
    if ( lpSubKey )
      operator delete((void *)lpSubKey);
    goto LABEL_15;
  }
  v25 = 0;
  v15 = DCGetReadonlyHKey(lpSubKey);
  v11 = v15;
  if ( v15 >= 0 )
  {
    v16 = v25;
    p_hKey = &v21;
    v27 = 0;
    v28 = 1;
    v6 = DCGetRegistryString(v25, 0, L"ScenarioId", &v27);
    if ( v28 )
    {
      v17 = (void *)*p_hKey;
      *p_hKey = v27;
      if ( v17 )
        operator delete(v17);
    }
    if ( v6 >= 0 )
    {
      p_hKey = &v24;
      v24 = 0;
      v27 = 0;
      v28 = 1;
      v6 = DCStringCchPrintfAllStrings(&v27, qword_140085150, 1, v21);
      if ( v28 )
      {
        v18 = (void *)*p_hKey;
        *p_hKey = v27;
        if ( v18 )
          operator delete(v18);
      }
      if ( v6 >= 0 )
      {
        v25 = 0;
        v19 = DCGetReadonlyHKey(v24);
        v6 = v19;
        if ( v19 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x446,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\omadmalert\\lib\\dcalert.cpp",
            (const char *)(unsigned int)v19,
            v4);
        if ( v24 )
          operator delete((void *)v24);
        if ( v25 )
          RegCloseKey(v25);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x442,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\omadmalert\\lib\\dcalert.cpp",
          (const char *)(unsigned int)v6,
          v4);
        if ( v24 )
          operator delete((void *)v24);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x437,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\omadmalert\\lib\\dcalert.cpp",
        (const char *)(unsigned int)v6,
        v4);
    }
    if ( lpSubKey )
      operator delete((void *)lpSubKey);
    if ( Block )
      operator delete(Block);
    if ( v21 )
      operator delete(v21);
    if ( v16 )
      RegCloseKey(v16);
    goto LABEL_62;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x42F,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\omadmalert\\lib\\dcalert.cpp",
    (const char *)(unsigned int)v15,
    v4);
  if ( lpSubKey )
    operator delete((void *)lpSubKey);
  if ( Block )
    operator delete(Block);
  if ( v21 )
    operator delete(v21);
  if ( v25 )
    RegCloseKey(v25);
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400585f0  mov     [rsp-38h+arg_8], rbx
0x1400585f5  mov     [rsp-38h+arg_0], rcx
0x1400585fa  push    rbp
0x1400585fb  push    rsi
0x1400585fc  push    rdi
0x1400585fd  push    r12
0x1400585ff  push    r13
0x140058601  push    r14
0x140058603  push    r15
0x140058605  mov     rbp, rsp
0x140058608  sub     rsp, 80h
0x14005860f  xor     r15d, r15d
0x140058612  mov     [rbp+var_8], 1
0x140058616  mov     r12, r8
0x140058619  mov     [rbp+hKey], r15
0x14005861d  lea     rax, [rbp+hKey]
0x140058621  mov     [rbp+var_40], r15
0x140058625  lea     r8, [rbp+var_10]
0x140058629  mov     [rbp+Block], r15
0x14005862d  mov     [rbp+var_18], rax
0x140058631  mov     r13, rdx
0x140058634  mov     [rbp+var_10], r15
0x140058638  mov     r14, rcx
0x14005863b  call    DCGetReadonlyEnrollmentIdSidStateKey
0x140058640  mov     esi, eax
0x140058642  cmp     [rbp+var_8], r15b
0x140058646  jz      short loc_14005868D
0x140058648  mov     rdi, [rbp+var_18]
0x14005864c  mov     r15, [rbp+var_10]
0x140058650  mov     r14, [rdi]
0x140058653  test    r14, r14
0x140058656  jz      short loc_140058683
0x140058658  call    cs:__imp_GetLastError
0x14005865f  nop     dword ptr [rax+rax+00h]
0x140058664  mov     rcx, r14; hKey
0x140058667  mov     ebx, eax
0x140058669  call    cs:__imp_RegCloseKey
0x140058670  nop     dword ptr [rax+rax+00h]
0x140058675  mov     ecx, ebx; dwErrCode
0x140058677  call    cs:__imp_SetLastError
0x14005867e  nop     dword ptr [rax+rax+00h]
0x140058683  mov     r14, [rbp+arg_0]
0x140058687  mov     [rdi], r15
0x14005868a  xor     r15d, r15d
0x14005868d  test    esi, esi
0x14005868f  jns     short loc_1400586D8
0x140058691  mov     rcx, [rbp+38h]; this
0x140058695  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x14005869c  mov     r9d, esi; char *
0x14005869f  mov     edx, 417h; void *
0x1400586a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400586a9  mov     rcx, [rbp+Block]; Block
0x1400586ad  mov     edi, 2
0x1400586b2  test    rcx, rcx
0x1400586b5  jz      short loc_1400586BE
0x1400586b7  mov     edx, edi
0x1400586b9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400586be  mov     rcx, [rbp+var_40]; Block
0x1400586c2  test    rcx, rcx
0x1400586c5  jz      loc_140058A22
0x1400586cb  mov     rdx, rdi
0x1400586ce  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400586d3  jmp     loc_140058A22
0x1400586d8  mov     rcx, [rbp+hKey]
0x1400586dc  lea     rax, [rbp+Block]
0x1400586e0  lea     r9, [rbp+var_10]
0x1400586e4  mov     [rbp+var_18], rax
0x1400586e8  lea     r8, aMostrecentvers; "MostRecentVersion"
0x1400586ef  mov     [rbp+var_10], r15
0x1400586f3  mov     rdx, r12
0x1400586f6  mov     [rbp+var_8], 1
0x1400586fa  call    DCGetRegistryString
0x1400586ff  mov     ebx, eax
0x140058701  mov     edi, 2
0x140058706  cmp     [rbp+var_8], r15b
0x14005870a  jz      short loc_140058726
0x14005870c  mov     r8, [rbp+var_18]
0x140058710  mov     rdx, [rbp+var_10]
0x140058714  mov     rcx, [r8]; Block
0x140058717  mov     [r8], rdx
0x14005871a  test    rcx, rcx
0x14005871d  jz      short loc_140058726
0x14005871f  mov     edx, edi
0x140058721  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058726  test    ebx, ebx
0x140058728  jns     short loc_140058780
0x14005872a  mov     rcx, [rbp+38h]; this
0x14005872e  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x140058735  mov     r9d, ebx; char *
0x140058738  mov     edx, 41Fh; void *
0x14005873d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058742  mov     rcx, [rbp+Block]; Block
0x140058746  test    rcx, rcx
0x140058749  jz      short loc_140058753
0x14005874b  mov     rdx, rdi
0x14005874e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058753  mov     rcx, [rbp+var_40]; Block
0x140058757  test    rcx, rcx
0x14005875a  jz      short loc_140058764
0x14005875c  mov     rdx, rdi
0x14005875f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058764  mov     rcx, [rbp+hKey]; hKey
0x140058768  test    rcx, rcx
0x14005876b  jz      short loc_140058779
0x14005876d  call    cs:__imp_RegCloseKey
0x140058774  nop     dword ptr [rax+rax+00h]
0x140058779  mov     eax, ebx
0x14005877b  jmp     loc_140058A39
0x140058780  mov     rax, [rbp+Block]
0x140058784  lea     rcx, [rbp+lpSubKey]
0x140058788  mov     rdx, cs:qword_140085180
0x14005878f  mov     r9, r14
0x140058792  mov     [rsp+80h+var_50], rax
0x140058797  mov     r8d, 4
0x14005879d  mov     [rbp+var_18], rcx
0x1400587a1  lea     rcx, [rbp+var_10]
0x1400587a5  mov     [rsp+80h+var_58], r12
0x1400587aa  mov     qword ptr [rsp+80h+var_60], r13; int
0x1400587af  mov     [rbp+lpSubKey], r15
0x1400587b3  mov     [rbp+var_10], r15
0x1400587b7  mov     [rbp+var_8], 1
0x1400587bb  call    DCStringCchPrintfAllStrings
0x1400587c0  mov     ebx, eax
0x1400587c2  cmp     [rbp+var_8], r15b
0x1400587c6  jz      short loc_1400587E3
0x1400587c8  mov     r8, [rbp+var_18]
0x1400587cc  mov     rdx, [rbp+var_10]
0x1400587d0  mov     rcx, [r8]; Block
0x1400587d3  mov     [r8], rdx
0x1400587d6  test    rcx, rcx
0x1400587d9  jz      short loc_1400587E3
0x1400587db  mov     rdx, rdi
0x1400587de  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400587e3  test    ebx, ebx
0x1400587e5  jns     short loc_140058819
0x1400587e7  mov     rcx, [rbp+38h]; this
0x1400587eb  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1400587f2  mov     r9d, ebx; char *
0x1400587f5  mov     edx, 42Bh; void *
0x1400587fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400587ff  mov     rcx, [rbp+lpSubKey]; Block
0x140058803  test    rcx, rcx
0x140058806  jz      loc_140058742
0x14005880c  mov     rdx, rdi
0x14005880f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058814  jmp     loc_140058742
0x140058819  mov     rcx, [rbp+lpSubKey]; lpSubKey
0x14005881d  lea     rdx, [rbp+var_20]
0x140058821  mov     [rbp+var_20], r15
0x140058825  call    DCGetReadonlyHKey
0x14005882a  mov     ebx, eax
0x14005882c  test    eax, eax
0x14005882e  jns     short loc_140058899
0x140058830  mov     rcx, [rbp+38h]; this
0x140058834  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x14005883b  mov     r9d, eax; char *
0x14005883e  mov     edx, 42Fh; void *
0x140058843  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058848  mov     rcx, [rbp+lpSubKey]; Block
0x14005884c  test    rcx, rcx
0x14005884f  jz      short loc_140058859
0x140058851  mov     rdx, rdi
0x140058854  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058859  mov     rcx, [rbp+Block]; Block
0x14005885d  test    rcx, rcx
0x140058860  jz      short loc_14005886A
0x140058862  mov     rdx, rdi
0x140058865  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005886a  mov     rcx, [rbp+var_40]; Block
0x14005886e  test    rcx, rcx
0x140058871  jz      short loc_14005887B
0x140058873  mov     rdx, rdi
0x140058876  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14005887b  mov     rcx, [rbp+var_20]; hKey
0x14005887f  test    rcx, rcx
0x140058882  jz      loc_140058764
0x140058888  call    cs:__imp_RegCloseKey
0x14005888f  nop     dword ptr [rax+rax+00h]
0x140058894  jmp     loc_140058764
0x140058899  mov     rbx, [rbp+var_20]
0x14005889d  lea     rax, [rbp+var_40]
0x1400588a1  mov     rcx, rbx
0x1400588a4  mov     [rbp+var_18], rax
0x1400588a8  lea     r9, [rbp+var_10]
0x1400588ac  mov     [rbp+var_10], r15
0x1400588b0  lea     r8, aScenarioid; "ScenarioId"
0x1400588b7  mov     [rbp+var_8], 1
0x1400588bb  xor     edx, edx
0x1400588bd  call    DCGetRegistryString
0x1400588c2  mov     esi, eax
0x1400588c4  cmp     [rbp+var_8], r15b
0x1400588c8  jz      short loc_1400588E5
0x1400588ca  mov     r8, [rbp+var_18]
0x1400588ce  mov     rdx, [rbp+var_10]
0x1400588d2  mov     rcx, [r8]; Block
0x1400588d5  mov     [r8], rdx
0x1400588d8  test    rcx, rcx
0x1400588db  jz      short loc_1400588E5
0x1400588dd  mov     rdx, rdi
0x1400588e0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400588e5  test    esi, esi
0x1400588e7  jns     short loc_140058906
0x1400588e9  mov     rcx, [rbp+38h]; this
0x1400588ed  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1400588f4  mov     r9d, esi; char *
0x1400588f7  mov     edx, 437h; void *
0x1400588fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058901  jmp     loc_1400589DB
0x140058906  mov     r9, [rbp+var_40]
0x14005890a  lea     rax, [rbp+var_28]
0x14005890e  mov     rdx, cs:qword_140085150
0x140058915  lea     rcx, [rbp+var_10]
0x140058919  mov     r8d, 1
0x14005891f  mov     [rbp+var_18], rax
0x140058923  mov     [rbp+var_28], r15
0x140058927  mov     [rbp+var_10], r15
0x14005892b  mov     [rbp+var_8], 1
0x14005892f  call    DCStringCchPrintfAllStrings
0x140058934  mov     esi, eax
0x140058936  cmp     [rbp+var_8], r15b
0x14005893a  jz      short loc_140058957
0x14005893c  mov     r8, [rbp+var_18]
0x140058940  mov     rdx, [rbp+var_10]
0x140058944  mov     rcx, [r8]; Block
0x140058947  mov     [r8], rdx
0x14005894a  test    rcx, rcx
0x14005894d  jz      short loc_140058957
0x14005894f  mov     rdx, rdi
0x140058952  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058957  test    esi, esi
0x140058959  jns     short loc_140058986
0x14005895b  mov     rcx, [rbp+38h]; this
0x14005895f  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x140058966  mov     r9d, esi; char *
0x140058969  mov     edx, 442h; void *
0x14005896e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140058973  mov     rcx, [rbp+var_28]; Block
0x140058977  test    rcx, rcx
0x14005897a  jz      short loc_1400589DB
0x14005897c  mov     rdx, rdi
0x14005897f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058984  jmp     short loc_1400589DB
0x140058986  mov     rcx, [rbp+var_28]; lpSubKey
0x14005898a  lea     rdx, [rbp+var_20]
0x14005898e  mov     [rbp+var_20], r15
0x140058992  call    DCGetReadonlyHKey
0x140058997  mov     esi, eax
0x140058999  test    eax, eax
0x14005899b  jns     short loc_1400589B5
0x14005899d  mov     rcx, [rbp+38h]; this
0x1400589a1  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1400589a8  mov     r9d, eax; char *
0x1400589ab  mov     edx, 446h; void *
0x1400589b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400589b5  mov     rcx, [rbp+var_28]; Block
0x1400589b9  test    rcx, rcx
0x1400589bc  jz      short loc_1400589C6
0x1400589be  mov     rdx, rdi
0x1400589c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400589c6  mov     rcx, [rbp+var_20]; hKey
0x1400589ca  test    rcx, rcx
0x1400589cd  jz      short loc_1400589DB
0x1400589cf  call    cs:__imp_RegCloseKey
0x1400589d6  nop     dword ptr [rax+rax+00h]
0x1400589db  mov     rcx, [rbp+lpSubKey]; Block
0x1400589df  test    rcx, rcx
0x1400589e2  jz      short loc_1400589EC
0x1400589e4  mov     rdx, rdi
0x1400589e7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400589ec  mov     rcx, [rbp+Block]; Block
0x1400589f0  test    rcx, rcx
0x1400589f3  jz      short loc_1400589FD
0x1400589f5  mov     rdx, rdi
0x1400589f8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400589fd  mov     rcx, [rbp+var_40]; Block
0x140058a01  test    rcx, rcx
0x140058a04  jz      short loc_140058A0E
0x140058a06  mov     rdx, rdi
0x140058a09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058a0e  test    rbx, rbx
0x140058a11  jz      short loc_140058A22
0x140058a13  mov     rcx, rbx; hKey
0x140058a16  call    cs:__imp_RegCloseKey
0x140058a1d  nop     dword ptr [rax+rax+00h]
0x140058a22  mov     rcx, [rbp+hKey]; hKey
0x140058a26  test    rcx, rcx
0x140058a29  jz      short loc_140058A37
0x140058a2b  call    cs:__imp_RegCloseKey
0x140058a32  nop     dword ptr [rax+rax+00h]
0x140058a37  mov     eax, esi
0x140058a39  mov     rbx, [rsp+80h+arg_8]
0x140058a41  add     rsp, 80h
0x140058a48  pop     r15
0x140058a4a  pop     r14
0x140058a4c  pop     r13
0x140058a4e  pop     r12
0x140058a50  pop     rdi
0x140058a51  pop     rsi
0x140058a52  pop     rbp
0x140058a53  retn
  ... truncated ...
```
