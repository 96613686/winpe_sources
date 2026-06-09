# DSUtils::CanonicalAndValidateFilePath(ushort const *,ushort * *)

- ea: `0x1800198f8`
- end: `0x180019a8b`
- name: `?CanonicalAndValidateFilePath@DSUtils@@YAJPEBGPEAPEAG@Z`
- size: `403`
- prototype: `__int64 __fastcall(wchar_t *Str, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000ca4c`
- `0x18000f740`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000c728`
- `0x18000c93c`
- `0x1800198f8`
- `0x18001afe8`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800199dd`
- `msvcrt!wcsstr` at `0x1800199dd`
- `msvcrt!wcschr` at `0x180019a01`
- `msvcrt!wcschr` at `0x180019a01`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800199c9`
- `api-ms-win-core-path-l1-1-0!PathIsUNCEx` at `0x1800199c9`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18001996a`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x18001996a`

## string_xrefs

- `0x18001999e`: `PathAllocCanonicalize failed, hr=0x%x.`
- `0x1800199b0`: `DSUtils::CanonicalAndValidateFilePath`
- `0x180019a5a`: `DSUtils::CanonicalAndValidateFilePath`
- `0x180019a4d`: `UNC file path %s is not supported`
- `0x180019a1e`: `File path %s contains invalid char %c`

## pseudocode

```c
__int64 __fastcall DSUtils::CanonicalAndValidateFilePath(wchar_t *Str, unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v5; // rdx
  __int64 v6; // rcx
  _QWORD *v7; // rsi
  __int64 v8; // r8
  PWSTR *v9; // rax
  HRESULT v10; // ebx
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  DSLogger *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int i; // esi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  DSLogger *v26; // rax
  __int64 v27; // rax
  DSLogger *v28; // rax
  __int64 v30; // [rsp+60h] [rbp+8h] BYREF
  __int64 v31; // [rsp+68h] [rbp+10h] BYREF

  if ( !Str )
    MicrosoftTelemetryAssertTriggeredNoArgs(0, a2, a3);
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(Str, a2, a3);
  v31 = 0;
  v7 = (_QWORD *)tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&void * LocalFree(void *),0>>(&v31);
  if ( !Str )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v8);
  if ( !v7 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5, v8);
  v30 = 0;
  v9 = (PWSTR *)tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&void * LocalFree(void *),0>>(&v30);
  v10 = PathAllocCanonicalize(Str, 1u, v9);
  if ( v10 >= 0 )
  {
    v11 = v30;
    v30 = 0;
    *v7 = v11;
  }
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&v30);
  if ( v10 < 0 )
  {
    v16 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v13,
                        v12,
                        v14,
                        v15);
    DSLogger::LogError(
      v16,
      L"DSUtils::CanonicalAndValidateFilePath",
      0xBFu,
      L"PathAllocCanonicalize failed, hr=0x%x.",
      Str,
      v10);
    goto LABEL_23;
  }
  if ( PathIsUNCEx(Str, 0) || wcsstr(Str, L"//") )
  {
    v28 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v18,
                        v17,
                        v19,
                        v20);
    DSLogger::LogError(v28, L"DSUtils::CanonicalAndValidateFilePath", 0xC9u, L"UNC file path %s is not supported", Str);
LABEL_23:
    v10 = -1055719416;
    goto LABEL_24;
  }
  for ( i = 0; i < 4; ++i )
  {
    if ( wcschr(Str, asc_180024C78[i]) )
    {
      v26 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                          v23,
                          v22,
                          v24,
                          v25);
      DSLogger::LogError(
        v26,
        L"DSUtils::CanonicalAndValidateFilePath",
        0xD5u,
        L"File path %s contains invalid char %c",
        Str,
        asc_180024C78[i]);
      goto LABEL_23;
    }
  }
  v27 = v31;
  v31 = 0;
  *(_QWORD *)a2 = v27;
LABEL_24:
  tlx::auto_xxx<void *,void * (*)(void *),&void * LocalFree(void *),0>::_Delete(&v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800198f8  mov     [rsp+arg_10], rbx
0x1800198fd  push    rbp
0x1800198fe  push    rsi
0x1800198ff  push    rdi
0x180019900  push    r12
0x180019902  push    r14
0x180019904  sub     rsp, 30h
0x180019908  mov     r14, rdx
0x18001990b  mov     rdi, rcx
0x18001990e  test    rcx, rcx
0x180019911  jnz     short loc_180019918
0x180019913  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019918  test    r14, r14
0x18001991b  jnz     short loc_180019922
0x18001991d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019922  mov     [rsp+58h+arg_8], 0
0x18001992b  lea     rcx, [rsp+58h+arg_8]
0x180019930  call    ??$replace@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>> &)
0x180019935  mov     rsi, rax
0x180019938  test    rdi, rdi
0x18001993b  jnz     short loc_180019942
0x18001993d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019942  test    rsi, rsi
0x180019945  jnz     short loc_18001994C
0x180019947  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001994c  mov     [rsp+58h+arg_0], 0
0x180019955  lea     rcx, [rsp+58h+arg_0]
0x18001995a  call    ??$replace@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (*)(void *),&LocalFree(void *),0>> &)
0x18001995f  mov     r8, rax; ppszPathOut
0x180019962  mov     edx, 1; dwFlags
0x180019967  mov     rcx, rdi; pszPathIn
0x18001996a  call    cs:__imp_PathAllocCanonicalize
0x180019970  mov     ebx, eax
0x180019972  test    eax, eax
0x180019974  js      short loc_180019987
0x180019976  mov     rax, [rsp+58h+arg_0]
0x18001997b  mov     [rsp+58h+arg_0], 0
0x180019984  mov     [rsi], rax
0x180019987  lea     rcx, [rsp+58h+arg_0]
0x18001998c  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180019991  test    ebx, ebx
0x180019993  jns     short loc_1800199C4
0x180019995  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18001999a  mov     [rsp+58h+var_30], ebx
0x18001999e  lea     r9, aPathalloccanon; "PathAllocCanonicalize failed, hr=0x%x."
0x1800199a5  mov     r8d, 0BFh; unsigned int
0x1800199ab  mov     [rsp+58h+var_38], rdi
0x1800199b0  lea     rdx, aDsutilsCanonic; "DSUtils::CanonicalAndValidateFilePath"
0x1800199b7  mov     rcx, rax; this
0x1800199ba  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x1800199bf  jmp     loc_180019A69
0x1800199c4  xor     edx, edx; ppszServer
0x1800199c6  mov     rcx, rdi; pszPath
0x1800199c9  call    cs:__imp_PathIsUNCEx
0x1800199cf  test    eax, eax
0x1800199d1  jnz     short loc_180019A43
0x1800199d3  lea     rdx, SubStr; "//"
0x1800199da  mov     rcx, rdi; Str
0x1800199dd  call    cs:__imp_wcsstr
0x1800199e3  test    rax, rax
0x1800199e6  jnz     short loc_180019A43
0x1800199e8  xor     esi, esi
0x1800199ea  cmp     esi, 4
0x1800199ed  jnb     short loc_180019A30
0x1800199ef  movsxd  rbp, esi
0x1800199f2  lea     r12, asc_180024C78; "\"<>|"
0x1800199f9  movzx   edx, word ptr [r12+rbp*2]; Ch
0x1800199fe  mov     rcx, rdi; Str
0x180019a01  call    cs:__imp_wcschr
0x180019a07  test    rax, rax
0x180019a0a  jnz     short loc_180019A10
0x180019a0c  inc     esi
0x180019a0e  jmp     short loc_1800199EA
0x180019a10  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180019a15  movzx   ecx, word ptr [r12+rbp*2]
0x180019a1a  mov     [rsp+58h+var_30], ecx
0x180019a1e  lea     r9, aFilePathSConta; "File path %s contains invalid char %c"
0x180019a25  mov     r8d, 0D5h
0x180019a2b  jmp     loc_1800199AB
0x180019a30  mov     rax, [rsp+58h+arg_8]
0x180019a35  mov     [rsp+58h+arg_8], 0
0x180019a3e  mov     [r14], rax
0x180019a41  jmp     short loc_180019A6E
0x180019a43  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180019a48  mov     [rsp+58h+var_38], rdi
0x180019a4d  lea     r9, aUncFilePathSIs; "UNC file path %s is not supported"
0x180019a54  mov     r8d, 0C9h; unsigned int
0x180019a5a  lea     rdx, aDsutilsCanonic; "DSUtils::CanonicalAndValidateFilePath"
0x180019a61  mov     rcx, rax; this
0x180019a64  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180019a69  mov     ebx, 0C1130008h
0x180019a6e  lea     rcx, [rsp+58h+arg_8]
0x180019a73  call    ?_Delete@?$auto_xxx@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<void *,void * (*)(void *),&LocalFree(void *),0>::_Delete(void)
0x180019a78  mov     eax, ebx
0x180019a7a  mov     rbx, [rsp+58h+arg_10]
0x180019a7f  add     rsp, 30h
0x180019a83  pop     r14
0x180019a85  pop     r12
0x180019a87  pop     rdi
0x180019a88  pop     rsi
0x180019a89  pop     rbp
0x180019a8a  retn
```
