# StagingControls_SetLKGFeatureConfigurations(void)

- ea: `0x18007dbf0`
- end: `0x18007dd99`
- name: `?StagingControls_SetLKGFeatureConfigurations@@YAJXZ`
- size: `425`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callers

- `0x1800654a0`

## callees

- `0x18000947c`
- `0x18000949c`
- `0x180018a90`
- `0x18004c08c`
- `0x18007cfa4`
- `0x18007d3dc`
- `0x18007d49c`
- `0x18007dbf0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007dc23`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18007dc23`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007dc5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18007dc5f`

## string_xrefs

- `0x18007dc1c`: `ntdll.dll`
- `0x18007dc33`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007dc72`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007dd1d`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007dd5b`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007dc55`: `RtlQueryAllInternalFeatureConfigurations`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 StagingControls_SetLKGFeatureConfigurations(void)
{
  HMODULE ModuleHandleW; // rax
  const char *v1; // r9
  unsigned int v2; // ebx
  __int64 result; // rax
  FARPROC ProcAddress; // rax
  const char *v5; // r9
  __int64 (__fastcall *v6)(_QWORD, _QWORD, _QWORD, _QWORD); // rdi
  unsigned int LastError; // ebx
  int v8; // ebx
  unsigned __int64 v9; // rcx
  unsigned int v10; // ebx
  const char *v11; // r9
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // [rsp+20h] [rbp-38h]
  __int128 v15; // [rsp+30h] [rbp-28h] BYREF
  __int64 v16; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int64 v18; // [rsp+60h] [rbp+8h] BYREF
  __int64 v19; // [rsp+68h] [rbp+10h] BYREF

  v19 = 0;
  v15 = 0;
  v16 = 0;
  v18 = 0;
  ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryAllInternalFeatureConfigurations");
    v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))ProcAddress;
    if ( ProcAddress )
    {
      try
      {
        do
        {
          v8 = v6(0, &v19, v15, &v18);
          v9 = (__int64)(*((_QWORD *)&v15 + 1) - v15) >> 4;
          if ( v18 >= v9 )
          {
            if ( v18 > v9 )
            {
              if ( v18 <= (v16 - (__int64)v15) >> 4 )
                *((_QWORD *)&v15 + 1) = std::_Uninitialized_value_construct_n<std::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>>(
                                          *((_QWORD *)&v15 + 1),
                                          v18 - v9);
              else
                std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Resize_reallocate<std::_Value_init_tag>(&v15);
            }
          }
          else
          {
            *((_QWORD *)&v15 + 1) = v15 + 16 * v18;
          }
        }
        while ( v8 == -2147483643 );
        if ( v8 >= 0 )
        {
          v12 = StorageWriter::WriteLKGFeatureConfigurations((struct _RTL_FEATURE_CONFIGURATION_INTERNAL *)v15, v18);
          v13 = v12;
          if ( v12 >= 0 )
          {
            std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(&v15);
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x25,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
              (const char *)(unsigned int)v12,
              v14);
            std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(&v15);
            result = v13;
          }
        }
        else
        {
          v10 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x23,
                  (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
                  (const char *)(unsigned int)v8,
                  v14);
          std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(&v15);
          result = v10;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x29,
                               (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stag"
                                             "ingcontrolslkg.cpp",
                               v11);
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1A,
                    (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
                    v5);
      std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(&v15);
      return LastError;
    }
  }
  else
  {
    v2 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x16,
           (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
           v1);
    std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(&v15);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x18007dbf0  mov     rax, rsp
0x18007dbf3  mov     [rax+18h], rbx
0x18007dbf7  push    rdi
0x18007dbf8  sub     rsp, 50h
0x18007dbfc  mov     qword ptr [rax+10h], 0
0x18007dc04  xorps   xmm0, xmm0
0x18007dc07  movdqu  xmmword ptr [rax-28h], xmm0
0x18007dc0c  mov     qword ptr [rax-18h], 0
0x18007dc14  mov     qword ptr [rax+8], 0
0x18007dc1c  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18007dc23  call    cs:__imp_GetModuleHandleW
0x18007dc29  test    rax, rax
0x18007dc2c  jnz     short loc_18007DC55
0x18007dc2e  mov     rcx, [rsp+58h]; this
0x18007dc33  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007dc3a  lea     edx, [rax+16h]; void *
0x18007dc3d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007dc42  mov     ebx, eax
0x18007dc44  lea     rcx, [rsp+58h+var_28]
0x18007dc49  call    ?_Tidy@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEAAXXZ; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(void)
0x18007dc4e  mov     eax, ebx
0x18007dc50  jmp     loc_18007DD8D
0x18007dc55  lea     rdx, aRtlqueryallint; "RtlQueryAllInternalFeatureConfiguration"...
0x18007dc5c  mov     rcx, rax; hModule
0x18007dc5f  call    cs:__imp_GetProcAddress
0x18007dc65  mov     rdi, rax
0x18007dc68  test    rax, rax
0x18007dc6b  jnz     short loc_18007DC94
0x18007dc6d  mov     rcx, [rsp+58h]; this
0x18007dc72  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007dc79  lea     edx, [rax+1Ah]; void *
0x18007dc7c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007dc81  mov     ebx, eax
0x18007dc83  lea     rcx, [rsp+58h+var_28]
0x18007dc88  call    ?_Tidy@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEAAXXZ; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(void)
0x18007dc8d  mov     eax, ebx
0x18007dc8f  jmp     loc_18007DD8D
0x18007dc94  lea     r9, [rsp+58h+arg_0]
0x18007dc99  mov     r8, [rsp+58h+var_28]
0x18007dc9e  lea     rdx, [rsp+58h+arg_8]
0x18007dca3  xor     ecx, ecx
0x18007dca5  mov     rax, rdi
0x18007dca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dcad  mov     ebx, eax
0x18007dcaf  mov     rdx, [rsp+58h+arg_0]
0x18007dcb4  mov     r8, [rsp+58h+var_28]
0x18007dcb9  mov     rcx, [rsp+58h+var_20]
0x18007dcbe  sub     rcx, r8
0x18007dcc1  sar     rcx, 4
0x18007dcc5  cmp     rdx, rcx
0x18007dcc8  jnb     short loc_18007DCD8
0x18007dcca  shl     rdx, 4
0x18007dcce  add     rdx, r8
0x18007dcd1  mov     [rsp+58h+var_20], rdx
0x18007dcd6  jmp     short loc_18007DD09
0x18007dcd8  jbe     short loc_18007DD09
0x18007dcda  mov     rax, [rsp+58h+var_18]
0x18007dcdf  sub     rax, r8
0x18007dce2  sar     rax, 4
0x18007dce6  cmp     rdx, rax
0x18007dce9  jbe     short loc_18007DCF7
0x18007dceb  lea     rcx, [rsp+58h+var_28]
0x18007dcf0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18007dcf5  jmp     short loc_18007DD09
0x18007dcf7  sub     rdx, rcx
0x18007dcfa  mov     rcx, [rsp+58h+var_20]
0x18007dcff  call    ??$_Uninitialized_value_construct_n@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@YAPEAU_RTL_FEATURE_CONFIGURATION_INTERNAL@@PEAU1@_KAEAV?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>>(_RTL_FEATURE_CONFIGURATION_INTERNAL *,unsigned __int64,std::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL> &)
0x18007dd04  mov     [rsp+58h+var_20], rax
0x18007dd09  cmp     ebx, 80000005h
0x18007dd0f  jz      short loc_18007DC94
0x18007dd11  test    ebx, ebx
0x18007dd13  jns     short loc_18007DD3E
0x18007dd15  mov     rcx, [rsp+58h]; this
0x18007dd1a  mov     r9d, ebx; char *
0x18007dd1d  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007dd24  mov     edx, 23h ; '#'; void *
0x18007dd29  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007dd2e  mov     ebx, eax
0x18007dd30  lea     rcx, [rsp+58h+var_28]
0x18007dd35  call    ?_Tidy@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEAAXXZ; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(void)
0x18007dd3a  mov     eax, ebx
0x18007dd3c  jmp     short loc_18007DD8D
0x18007dd3e  mov     rdx, [rsp+58h+arg_0]; unsigned __int64
0x18007dd43  mov     rcx, [rsp+58h+var_28]; struct _RTL_FEATURE_CONFIGURATION_INTERNAL *
0x18007dd48  call    ?WriteLKGFeatureConfigurations@StorageWriter@@SAJPEAU_RTL_FEATURE_CONFIGURATION_INTERNAL@@_K@Z; StorageWriter::WriteLKGFeatureConfigurations(_RTL_FEATURE_CONFIGURATION_INTERNAL *,unsigned __int64)
0x18007dd4d  mov     ebx, eax
0x18007dd4f  test    eax, eax
0x18007dd51  jns     short loc_18007DD7B
0x18007dd53  mov     rcx, [rsp+58h]; this
0x18007dd58  mov     r9d, eax; char *
0x18007dd5b  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007dd62  mov     edx, 25h ; '%'; void *
0x18007dd67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dd6c  nop
0x18007dd6d  lea     rcx, [rsp+58h+var_28]
0x18007dd72  call    ?_Tidy@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEAAXXZ; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(void)
0x18007dd77  mov     eax, ebx
0x18007dd79  jmp     short loc_18007DD8D
0x18007dd7b  lea     rcx, [rsp+58h+var_28]
0x18007dd80  call    ?_Tidy@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@AEAAXXZ; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::_Tidy(void)
0x18007dd85  xor     eax, eax
0x18007dd87  jmp     short loc_18007DD8D
0x18007dd89  mov     eax, dword ptr [rsp+58h+arg_0]
0x18007dd8d  mov     rbx, [rsp+58h+arg_10]
0x18007dd92  add     rsp, 50h
0x18007dd96  pop     rdi
0x18007dd97  retn
```
