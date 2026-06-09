# VerifyAndGetSchemaLocation(ushort const *,IMigrationContext *,ushort * *)

- ea: `0x180003698`
- end: `0x180003891`
- name: `?VerifyAndGetSchemaLocation@@YAJPEBGPEAUIMigrationContext@@PEAPEAG@Z`
- size: `505`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, struct IMigrationContext *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180003434`
- `0x1800926e8`

## callees

- `0x180003698`
- `0x180004148`
- `0x18000457c`
- `0x180025dd4`
- `0x18002f9e0`
- `0x18006a0b8`
- `0x18006d768`
- `0x18006dad4`
- `0x180092c6c`
- `0x180092e88`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800036d3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1800036d3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000371f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180003802`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18000371f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180003802`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800036c3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180003848`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800036c3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180003848`

## string_xrefs

- `0x180003702`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x180003757`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x180003783`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x1800037d6`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x18000386b`: `onecoreuap\shell\propsys\schemacachehelpers.cpp`
- `0x180003771`: `Expanded path %ws not found`
- `0x1800037c4`: `Schema at %ws not found on program files, trying x86 path`
- `0x180003857`: `Extension %ws is not .propdesc`
- `0x18000381f`: `Correctly Expanded path %ws to %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VerifyAndGetSchemaLocation(LPCWSTR pszPath, struct IMigrationContext *a2, const char **a3)
{
  const WCHAR *v5; // rax
  int v6; // eax
  unsigned int v7; // edi
  const char *v8; // rdi
  int v9; // eax
  unsigned __int16 *v11; // rsi
  const char *ExtensionW; // rax
  int v13; // [rsp+20h] [rbp-20h]
  LPCWSTR pszPatha; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]

  *a3 = 0;
  if ( !pszPath || (v5 = PathFindExtensionW(pszPath), StrCmpICW(L".propdesc", v5)) )
  {
    ExtensionW = (const char *)PathFindExtensionW(pszPath);
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1A5,
      (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
      (const char *)0x80070057LL,
      (int)"Extension %ws is not .propdesc",
      ExtensionW);
    return 2147942487LL;
  }
  else
  {
    pszPatha = 0;
    v6 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
           pszPath,
           &pszPatha);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
        (const char *)(unsigned int)v6,
        v13);
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPatha);
      return v7;
    }
    v8 = (const char *)pszPatha;
    if ( !PathFileExistsW(pszPatha) )
    {
      v15 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v15,
        0);
      v9 = TryProgramFilesx86Translation(pszPath, &v15);
      if ( v9 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B6,
          (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
          (const char *)(unsigned int)v9,
          v13);
LABEL_8:
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0x1C1,
          (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
          (const char *)0x80070002LL,
          (int)"Expanded path %ws not found",
          v8);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
        v7 = -2147024894;
        goto LABEL_9;
      }
      v11 = v15;
      if ( !v15 )
        goto LABEL_8;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x1BA,
        (unsigned int)"onecoreuap\\shell\\propsys\\schemacachehelpers.cpp",
        (const char *)0x80070002LL,
        (int)"Schema at %ws not found on program files, trying x86 path",
        (const char *)pszPath);
      v15 = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pszPatha,
        v11);
      v8 = (const char *)pszPatha;
      if ( !PathFileExistsW(pszPatha) )
        goto LABEL_8;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
    }
    SchemaCacheMigrationLogMessage(0, L"Correctly Expanded path %ws to %ws", pszPath, v8);
    pszPatha = 0;
    *a3 = v8;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pszPatha);
    return 0;
  }
}

```

## disassembly

```asm
0x180003698  mov     [rsp-18h+arg_8], rbx
0x18000369d  mov     [rsp-18h+arg_18], rsi
0x1800036a2  push    rbp
0x1800036a3  push    rdi
0x1800036a4  push    r14
0x1800036a6  mov     rbp, rsp
0x1800036a9  sub     rsp, 40h
0x1800036ad  mov     r14, r8
0x1800036b0  mov     rbx, rcx
0x1800036b3  mov     qword ptr [r8], 0
0x1800036ba  test    rcx, rcx
0x1800036bd  jz      loc_180003845
0x1800036c3  call    cs:__imp_PathFindExtensionW
0x1800036c9  mov     rdx, rax; pszStr2
0x1800036cc  lea     rcx, pszStr1; ".propdesc"
0x1800036d3  call    cs:__imp_StrCmpICW
0x1800036d9  test    eax, eax
0x1800036db  jnz     loc_180003845
0x1800036e1  mov     [rbp+pszPath], 0
0x1800036e9  lea     rdx, [rbp+pszPath]
0x1800036ed  mov     rcx, rbx
0x1800036f0  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x1800036f5  mov     edi, eax
0x1800036f7  test    eax, eax
0x1800036f9  jns     short loc_180003718
0x1800036fb  mov     rcx, [rbp+18h]; this
0x1800036ff  mov     r9d, eax; char *
0x180003702  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x180003709  mov     edx, 1AAh; void *
0x18000370e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003713  jmp     loc_1800037A2
0x180003718  mov     rdi, [rbp+pszPath]
0x18000371c  mov     rcx, rdi; pszPath
0x18000371f  call    cs:__imp_PathFileExistsW
0x180003725  test    eax, eax
0x180003727  jnz     loc_180003819
0x18000372d  mov     [rbp+var_8], 0
0x180003735  xor     edx, edx
0x180003737  lea     rcx, [rbp+var_8]
0x18000373b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180003740  lea     rdx, [rbp+var_8]; unsigned __int16 **
0x180003744  mov     rcx, rbx; pszFirst
0x180003747  call    ?TryProgramFilesx86Translation@@YAJPEBGPEAPEAG@Z; TryProgramFilesx86Translation(ushort const *,ushort * *)
0x18000374c  mov     rcx, [rbp+18h]; this
0x180003750  test    eax, eax
0x180003752  jns     short loc_1800037B2
0x180003754  mov     r9d, eax; char *
0x180003757  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x18000375e  mov     edx, 1B6h; void *
0x180003763  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180003768  mov     rcx, [rbp+18h]; this
0x18000376c  mov     [rsp+40h+var_18], rdi; char *
0x180003771  lea     rax, aExpandedPathWs; "Expanded path %ws not found"
0x180003778  mov     qword ptr [rsp+40h+var_20], rax; int
0x18000377d  mov     r9d, 80070002h; char *
0x180003783  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x18000378a  mov     edx, 1C1h; void *
0x18000378f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180003794  lea     rcx, [rbp+var_8]
0x180003798  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18000379d  mov     edi, 80070002h
0x1800037a2  lea     rcx, [rbp+pszPath]
0x1800037a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800037ab  mov     eax, edi
0x1800037ad  jmp     loc_18000387E
0x1800037b2  mov     rsi, [rbp+var_8]
0x1800037b6  test    rsi, rsi
0x1800037b9  jz      short loc_180003768
0x1800037bb  mov     rcx, [rbp+18h]; this
0x1800037bf  mov     [rsp+40h+var_18], rbx; char *
0x1800037c4  lea     rax, aSchemaAtWsNotF; "Schema at %ws not found on program file"...
0x1800037cb  mov     qword ptr [rsp+40h+var_20], rax; int
0x1800037d0  mov     r9d, 80070002h; char *
0x1800037d6  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x1800037dd  mov     edx, 1BAh; void *
0x1800037e2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800037e7  mov     [rbp+var_8], 0
0x1800037ef  mov     rdx, rsi
0x1800037f2  lea     rcx, [rbp+pszPath]
0x1800037f6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800037fb  mov     rdi, [rbp+pszPath]
0x1800037ff  mov     rcx, rdi; pszPath
0x180003802  call    cs:__imp_PathFileExistsW
0x180003808  test    eax, eax
0x18000380a  jz      loc_180003768
0x180003810  lea     rcx, [rbp+var_8]
0x180003814  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003819  mov     r9, rdi
0x18000381c  mov     r8, rbx
0x18000381f  lea     rdx, aCorrectlyExpan; "Correctly Expanded path %ws to %ws"
0x180003826  xor     ecx, ecx; struct IMigrationContext *
0x180003828  call    ?SchemaCacheMigrationLogMessage@@YAXPEAUIMigrationContext@@PEBGZZ; SchemaCacheMigrationLogMessage(IMigrationContext *,ushort const *,...)
0x18000382d  mov     [rbp+pszPath], 0
0x180003835  mov     [r14], rdi
0x180003838  lea     rcx, [rbp+pszPath]
0x18000383c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180003841  xor     eax, eax
0x180003843  jmp     short loc_18000387E
0x180003845  mov     rcx, rbx; pszPath
0x180003848  call    cs:__imp_PathFindExtensionW
0x18000384e  mov     rcx, [rbp+18h]; this
0x180003852  mov     [rsp+40h+var_18], rax; char *
0x180003857  lea     rax, aExtensionWsIsN; "Extension %ws is not .propdesc"
0x18000385e  mov     qword ptr [rsp+40h+var_20], rax; int
0x180003863  mov     ebx, 80070057h
0x180003868  mov     r9d, ebx; char *
0x18000386b  lea     r8, aOnecoreuapShel_11; "onecoreuap\\shell\\propsys\\schemacache"...
0x180003872  mov     edx, 1A5h; void *
0x180003877  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18000387c  mov     eax, ebx
0x18000387e  mov     rbx, [rsp+40h+arg_8]
0x180003883  mov     rsi, [rsp+40h+arg_18]
0x180003888  add     rsp, 40h
0x18000388c  pop     r14
0x18000388e  pop     rdi
0x18000388f  pop     rbp
0x180003890  retn
```
