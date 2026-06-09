# StagingControls_RestoreLKGFeatureConfigurations(std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL,std::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>> &,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL,std::allocator<_RTL_FEATURE_CONFIGURATION_INTERNAL>> &,std::vector<_RTL_FEATURE_CONFIGURATION_UPDATE,std::allocator<_RTL_FEATURE_CONFIGURATION_UPDATE>> &)

- ea: `0x18007da54`
- end: `0x18007dbea`
- name: `?StagingControls_RestoreLKGFeatureConfigurations@@YAJAEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@0AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_UPDATE@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_UPDATE@@@std@@@2@@Z`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x1800654a0`

## callees

- `0x18000949c`
- `0x180018a90`
- `0x180064e7c`
- `0x1800658d4`
- `0x180079f88`
- `0x18007cacc`
- `0x18007d70c`
- `0x18007d8b8`
- `0x18007d940`
- `0x18007da54`

## import_xrefs

- `ntdll!RtlSetFeatureConfigurations` at `0x18007db7f`
- `ntdll!RtlSetFeatureConfigurations` at `0x18007db7f`
- `ntdll!RtlQueryFeatureConfigurationChangeStamp` at `0x18007db23`
- `ntdll!RtlQueryFeatureConfigurationChangeStamp` at `0x18007db23`

## string_xrefs

- `0x18007daa5`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007dafc`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007db52`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007db98`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`
- `0x18007dbbe`: `onecore\base\flighting\featuremanagement\libs\featurestatewriter\stagingcontrolslkg.cpp`

## pseudocode

```c
int __fastcall StagingControls_RestoreLKGFeatureConfigurations(_QWORD *a1, _QWORD *a2, _QWORD *a3)
{
  int v6; // eax
  int v7; // r14d
  const char *v8; // r9
  int result; // eax
  __int64 v10; // r14
  _QWORD *v11; // rax
  int v12; // eax
  int v13; // r14d
  int v14; // eax
  int v15; // ebx
  int v16; // eax
  int v17; // eax
  int v18; // ebx
  int v19; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v21; // [rsp+40h] [rbp+8h] BYREF
  char v22; // [rsp+48h] [rbp+10h] BYREF

  if ( *a1 != a1[1] )
    a1[1] = *a1;
  if ( *a2 != a2[1] )
    a2[1] = *a2;
  if ( *a3 != a3[1] )
    a3[1] = *a3;
  try
  {
    v6 = RtlpFCGetLKGFeatureConfigurations();
    v7 = v6;
    if ( v6 >= 0 )
    {
      v10 = a1[1];
      v11 = (_QWORD *)std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_INTERNAL>>>,bool (*)(_RTL_FEATURE_CONFIGURATION_INTERNAL const &,_RTL_FEATURE_CONFIGURATION_INTERNAL const &)>(
                        &v21,
                        *a1,
                        v10);
      std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::erase(a1, &v22, *v11, v10);
      v12 = RtlpFCGetCurrentFeatureConfigurations(a2);
      v13 = v12;
      if ( v12 >= 0 )
      {
        GetUpdateFeatureConfigEntries(a1, a2, a3);
        do
        {
          v21 = RtlQueryFeatureConfigurationChangeStamp();
          v14 = StorageWriter::WriteFeatureStates(
                  (struct _RTL_FEATURE_CONFIGURATION_UPDATE *)*a3,
                  (__int64)(a3[1] - *a3) >> 5,
                  0);
          v15 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x43,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
              (const char *)(unsigned int)v14,
              v19);
            return v15;
          }
          v16 = RtlSetFeatureConfigurations(&v21, 1, *a3, (__int64)(a3[1] - *a3) >> 5);
        }
        while ( v16 == -1073741823 );
        if ( v16 >= 0 )
        {
          v17 = StorageWriter::FlushFeatureOverrides();
          v18 = v17;
          if ( v17 >= 0 )
          {
            result = 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x4A,
              (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
              (const char *)(unsigned int)v17,
              v19);
            result = v18;
          }
        }
        else
        {
          result = wil::details::in1diag3::Return_NtStatus(
                     retaddr,
                     (void *)0x48,
                     (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
                     (const char *)(unsigned int)v16,
                     v19);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x39,
          (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
          (const char *)(unsigned int)v12,
          v19);
        result = v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
        (const char *)(unsigned int)v6,
        v19);
      result = v7;
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Return_CaughtException(
             retaddr,
             (void *)0x4E,
             (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\featurestatewriter\\stagingcontrolslkg.cpp",
             v8);
  }
  return result;
}

```

## disassembly

```asm
0x18007da54  mov     [rsp+arg_10], rbx
0x18007da59  push    rsi
0x18007da5a  push    rdi
0x18007da5b  push    r14; int
0x18007da5d  sub     rsp, 20h
0x18007da61  mov     rdi, r8
0x18007da64  mov     rsi, rdx
0x18007da67  mov     rbx, rcx
0x18007da6a  mov     rax, [rcx]
0x18007da6d  cmp     rax, [rcx+8]
0x18007da71  jz      short loc_18007DA77
0x18007da73  mov     [rcx+8], rax
0x18007da77  mov     rax, [rdx]
0x18007da7a  cmp     rax, [rdx+8]
0x18007da7e  jz      short loc_18007DA84
0x18007da80  mov     [rdx+8], rax
0x18007da84  mov     rax, [r8]
0x18007da87  cmp     rax, [r8+8]
0x18007da8b  jz      short loc_18007DA91
0x18007da8d  mov     [r8+8], rax
0x18007da91  call    ?RtlpFCGetLKGFeatureConfigurations@@YAJAEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@@Z; RtlpFCGetLKGFeatureConfigurations(std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &)
0x18007da96  mov     r14d, eax
0x18007da99  test    eax, eax
0x18007da9b  jns     short loc_18007DABE
0x18007da9d  mov     rcx, [rsp+38h]; this
0x18007daa2  mov     r9d, eax; char *
0x18007daa5  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007daac  mov     edx, 35h ; '5'; void *
0x18007dab1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dab6  mov     eax, r14d
0x18007dab9  jmp     loc_18007DBDB
0x18007dabe  mov     r14, [rbx+8]
0x18007dac2  mov     r8, r14
0x18007dac5  mov     rdx, [rbx]
0x18007dac8  lea     rcx, [rsp+38h+arg_0]
0x18007dacd  call    ??$unique@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@@std@@P6A_NAEBU_RTL_FEATURE_CONFIGURATION_INTERNAL@@0@Z@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@@0@V10@0P6A_NAEBU_RTL_FEATURE_CONFIGURATION_INTERNAL@@1@Z@Z; std::unique<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_INTERNAL>>>,bool (*)(_RTL_FEATURE_CONFIGURATION_INTERNAL const &,_RTL_FEATURE_CONFIGURATION_INTERNAL const &)>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_INTERNAL>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_INTERNAL>>>,bool (*)(_RTL_FEATURE_CONFIGURATION_INTERNAL const &,_RTL_FEATURE_CONFIGURATION_INTERNAL const &))
0x18007dad2  mov     r9, r14
0x18007dad5  mov     r8, [rax]
0x18007dad8  lea     rdx, [rsp+38h+arg_8]
0x18007dadd  mov     rcx, rbx
0x18007dae0  call    ?erase@?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@@2@0@Z; std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_INTERNAL>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<_RTL_FEATURE_CONFIGURATION_INTERNAL>>>)
0x18007dae5  mov     rcx, rsi
0x18007dae8  call    ?RtlpFCGetCurrentFeatureConfigurations@@YAJAEAV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@@Z; RtlpFCGetCurrentFeatureConfigurations(std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> &)
0x18007daed  mov     r14d, eax
0x18007daf0  test    eax, eax
0x18007daf2  jns     short loc_18007DB15
0x18007daf4  mov     rcx, [rsp+38h]; this
0x18007daf9  mov     r9d, eax; char *
0x18007dafc  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007db03  mov     edx, 39h ; '9'; void *
0x18007db08  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007db0d  mov     eax, r14d
0x18007db10  jmp     loc_18007DBDB
0x18007db15  mov     r8, rdi
0x18007db18  mov     rdx, rsi
0x18007db1b  mov     rcx, rbx
0x18007db1e  call    ?GetUpdateFeatureConfigEntries@@YAXAEBV?$vector@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_INTERNAL@@@std@@@std@@0AEAV?$vector@U_RTL_FEATURE_CONFIGURATION_UPDATE@@V?$allocator@U_RTL_FEATURE_CONFIGURATION_UPDATE@@@std@@@2@@Z; GetUpdateFeatureConfigEntries(std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> const &,std::vector<_RTL_FEATURE_CONFIGURATION_INTERNAL> const &,std::vector<_RTL_FEATURE_CONFIGURATION_UPDATE> &)
0x18007db23  call    cs:__imp_RtlQueryFeatureConfigurationChangeStamp
0x18007db29  mov     [rsp+38h+arg_0], rax
0x18007db2e  mov     rdx, [rdi+8]
0x18007db32  sub     rdx, [rdi]
0x18007db35  sar     rdx, 5; unsigned __int64
0x18007db39  xor     r8d, r8d; bool
0x18007db3c  mov     rcx, [rdi]; struct _RTL_FEATURE_CONFIGURATION_UPDATE *
0x18007db3f  call    ?WriteFeatureStates@StorageWriter@@SAJPEAU_RTL_FEATURE_CONFIGURATION_UPDATE@@_K_N@Z; StorageWriter::WriteFeatureStates(_RTL_FEATURE_CONFIGURATION_UPDATE *,unsigned __int64,bool)
0x18007db44  mov     ebx, eax
0x18007db46  test    eax, eax
0x18007db48  jns     short loc_18007DB67
0x18007db4a  mov     rcx, [rsp+38h]; this
0x18007db4f  mov     r9d, eax; char *
0x18007db52  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007db59  mov     edx, 43h ; 'C'; void *
0x18007db5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007db63  mov     eax, ebx
0x18007db65  jmp     short loc_18007DBDB
0x18007db67  mov     r9, [rdi+8]
0x18007db6b  sub     r9, [rdi]
0x18007db6e  sar     r9, 5
0x18007db72  mov     r8, [rdi]
0x18007db75  mov     edx, 1
0x18007db7a  lea     rcx, [rsp+38h+arg_0]
0x18007db7f  call    cs:__imp_RtlSetFeatureConfigurations
0x18007db85  cmp     eax, 0C0000001h
0x18007db8a  jz      short loc_18007DB23
0x18007db8c  test    eax, eax
0x18007db8e  jns     short loc_18007DBAB
0x18007db90  mov     rcx, [rsp+38h]; this
0x18007db95  mov     r9d, eax; char *
0x18007db98  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007db9f  mov     edx, 48h ; 'H'; void *
0x18007dba4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007dba9  jmp     short loc_18007DBDB
0x18007dbab  call    ?FlushFeatureOverrides@StorageWriter@@SAJXZ; StorageWriter::FlushFeatureOverrides(void)
0x18007dbb0  mov     ebx, eax
0x18007dbb2  test    eax, eax
0x18007dbb4  jns     short loc_18007DBD3
0x18007dbb6  mov     rcx, [rsp+38h]; this
0x18007dbbb  mov     r9d, eax; char *
0x18007dbbe  lea     r8, aOnecoreBaseFli_13; "onecore\\base\\flighting\\featuremanage"...
0x18007dbc5  mov     edx, 4Ah ; 'J'; void *
0x18007dbca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007dbcf  mov     eax, ebx
0x18007dbd1  jmp     short loc_18007DBDB
0x18007dbd3  xor     eax, eax
0x18007dbd5  jmp     short loc_18007DBDB
0x18007dbd7  mov     eax, dword ptr [rsp+38h+arg_0]
0x18007dbdb  mov     rbx, [rsp+38h+arg_10]
0x18007dbe0  add     rsp, 20h
0x18007dbe4  pop     r14
0x18007dbe6  pop     rdi
0x18007dbe7  pop     rsi
0x18007dbe8  retn
```
