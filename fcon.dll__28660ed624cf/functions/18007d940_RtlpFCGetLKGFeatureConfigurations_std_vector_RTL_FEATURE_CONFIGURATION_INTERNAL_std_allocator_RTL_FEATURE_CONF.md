# RtlpFCGetLKGFeatureConfigurations(std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL,std::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>> &)

- ea: `0x18007d940`
- end: `0x18007da4c`
- name: `?RtlpFCGetLKGFeatureConfigurations@@YAJAEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@@Z`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18007da54`

## callees

- `0x18000947c`
- `0x180018a90`
- `0x18007d3dc`
- `0x18007d49c`
- `0x18007d940`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007d962`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007d962`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d990`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007d990`

## string_xrefs

- `0x18007d95b`: `ntdll.dll`
- `0x18007d975`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007da24`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007d986`: `RtlQueryAllInternalFeatureConfigurations`

## pseudocode

```c
int __fastcall RtlpFCGetLKGFeatureConfigurations(_QWORD *a1)
{
  HMODULE ModuleHandleW; // rax
  const char *v3; // r9
  __int64 v4; // rdx
  FARPROC ProcAddress; // rsi
  int v7; // edi
  unsigned __int64 v8; // rcx
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned __int64 v11; // [rsp+48h] [rbp+10h] BYREF
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF

  v11 = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( !ModuleHandleW )
  {
    v4 = 90;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
             v3);
  }
  ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryAllInternalFeatureConfigurations");
  if ( !ProcAddress )
  {
    v4 = 94;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
             v3);
  }
  v12 = 0;
  do
  {
    v7 = ((__int64 (__fastcall *)(_QWORD, __int64 *, _QWORD, unsigned __int64 *))ProcAddress)(0, &v12, *a1, &v11);
    v8 = (__int64)(a1[1] - *a1) >> 4;
    if ( v11 >= v8 )
    {
      if ( v11 > v8 )
      {
        if ( v11 <= (__int64)(a1[2] - *a1) >> 4 )
          a1[1] = std::_Uninitialized_value_construct_n<std::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>>(
                    a1[1],
                    v11 - v8);
        else
          std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Resize_reallocate<std::_Value_init_tag>(a1);
      }
    }
    else
    {
      a1[1] = *a1 + 16 * v11;
    }
  }
  while ( v7 == -2147483643 );
  if ( v7 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x68,
             (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
             (const char *)(unsigned int)v7,
             v9);
}

```

## disassembly

```asm
0x18007d940  mov     [rsp+arg_0], rbx
0x18007d945  mov     [rsp+arg_18], rsi
0x18007d94a  push    rdi
0x18007d94b  sub     rsp, 30h
0x18007d94f  mov     rbx, rcx
0x18007d952  mov     [rsp+38h+arg_8], 0
0x18007d95b  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18007d962  call    cs:__imp_GetModuleHandleW
0x18007d968  test    rax, rax
0x18007d96b  jnz     short loc_18007D986
0x18007d96d  lea     edx, [rax+5Ah]; void *
0x18007d970  mov     rcx, [rsp+38h]; this
0x18007d975  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007d97c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007d981  jmp     loc_18007DA3C
0x18007d986  lea     rdx, aRtlqueryallint; "RtlQueryAllInternalFeatureConfiguration"...
0x18007d98d  mov     rcx, rax; hModule
0x18007d990  call    cs:__imp_GetProcAddress
0x18007d996  mov     rsi, rax
0x18007d999  test    rax, rax
0x18007d99c  jnz     short loc_18007D9A3
0x18007d99e  lea     edx, [rax+5Eh]
0x18007d9a1  jmp     short loc_18007D970
0x18007d9a3  mov     [rsp+38h+arg_10], 0
0x18007d9ac  mov     r8, [rbx]
0x18007d9af  lea     r9, [rsp+38h+arg_8]
0x18007d9b4  lea     rdx, [rsp+38h+arg_10]
0x18007d9b9  xor     ecx, ecx
0x18007d9bb  mov     rax, rsi
0x18007d9be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9c3  mov     rcx, [rbx+8]
0x18007d9c7  mov     edi, eax
0x18007d9c9  sub     rcx, [rbx]
0x18007d9cc  mov     rdx, [rsp+38h+arg_8]
0x18007d9d1  sar     rcx, 4
0x18007d9d5  cmp     rdx, rcx
0x18007d9d8  jnb     short loc_18007D9E7
0x18007d9da  shl     rdx, 4
0x18007d9de  add     rdx, [rbx]
0x18007d9e1  mov     [rbx+8], rdx
0x18007d9e5  jmp     short loc_18007DA13
0x18007d9e7  jbe     short loc_18007DA13
0x18007d9e9  mov     rax, [rbx+10h]
0x18007d9ed  sub     rax, [rbx]
0x18007d9f0  sar     rax, 4
0x18007d9f4  cmp     rdx, rax
0x18007d9f7  jbe     short loc_18007DA03
0x18007d9f9  mov     rcx, rbx
0x18007d9fc  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18007da01  jmp     short loc_18007DA13
0x18007da03  sub     rdx, rcx
0x18007da06  mov     rcx, [rbx+8]
0x18007da0a  call    ??$_Uninitialized_value_construct_n@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@YAPEAU_RTL_FEATURE_CONFIGURATION_INTERNAL@@PEAU1@_KAEAV?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>>(_RTL_FEATURE_CONFIGURATION_INTERNAL *,unsigned __int64,std::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL> &)
0x18007da0f  mov     [rbx+8], rax
0x18007da13  cmp     edi, 80000005h
0x18007da19  jz      short loc_18007D9AC
0x18007da1b  test    edi, edi
0x18007da1d  jns     short loc_18007DA3A
0x18007da1f  mov     rcx, [rsp+38h]; this
0x18007da24  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007da2b  mov     r9d, edi; char *
0x18007da2e  mov     edx, 68h ; 'h'; void *
0x18007da33  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007da38  jmp     short loc_18007DA3C
0x18007da3a  xor     eax, eax
0x18007da3c  mov     rbx, [rsp+38h+arg_0]
0x18007da41  mov     rsi, [rsp+38h+arg_18]
0x18007da46  add     rsp, 30h
0x18007da4a  pop     rdi
0x18007da4b  retn
```
