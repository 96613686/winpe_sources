# std::call_once<`Mso::LazyValue<std::unordered_map<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,uint,std::hash<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::equal_to<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,uint>>>>::Store::EnsureValue(void)'::`3'::_lambda_1_,>(std::once_flag &,`Mso::LazyValue<std::unordered_map<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,uint,std::hash<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::equal_to<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator<char>> const,uint>>>>::Store::EnsureValue(void)'::`3'::_lambda_1_ &&)

- ea: `0x18003474c`
- end: `0x18003482b`
- name: `??$call_once@V_lambda_1_@?2??EnsureValue@Store@?$LazyValue@V?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IU?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@2@@std@@@Mso@@QEAAXXZ@$$V@std@@YAXAEAUonce_flag@0@$$QEAV_lambda_1_@?2??EnsureValue@Store@?$LazyValue@V?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IU?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@2@@std@@@Mso@@QEAAXXZ@@Z`
- size: `223`
- prototype: `__int64 __fastcall(LPINIT_ONCE lpInitOnce)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034728`

## callees

- `0x180010a10`
- `0x180011ae4`
- `0x180011b40`
- `0x18003474c`
- `0x18003482c`
- `0x18003485c`
- `0x18003d560`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180034809`
- `KERNEL32!InitOnceComplete` at `0x180034809`
- `KERNEL32!InitOnceBeginInitialize` at `0x180034772`
- `KERNEL32!InitOnceBeginInitialize` at `0x180034772`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003477c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18003477c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
BOOL __fastcall ___call_once_V_lambda_1___2__EnsureValue_Store___LazyValue_V__unordered_map_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__IU__hash_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2_U__equal_to_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2_V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__I_std___2__std___Mso__QEAAXXZ___V_std__YAXAEAUonce_flag_0___QEAV_lambda_1___2__EnsureValue_Store___LazyValue_V__unordered_map_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__IU__hash_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2_U__equal_to_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2_V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__I_std___2__std___Mso__QEAAXXZ__Z(
        LPINIT_ONCE lpInitOnce,
        __int64 *a2)
{
  BOOL result; // eax
  __int64 v5; // rbx
  __int64 v6; // rsi
  __int64 v7; // rdx
  __int64 v8; // rcx
  _BYTE v9[8]; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v10[16]; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v11[24]; // [rsp+48h] [rbp-30h] BYREF
  __int64 v12; // [rsp+60h] [rbp-18h]
  __int64 v13; // [rsp+68h] [rbp-10h]
  BOOL v14; // [rsp+80h] [rbp+8h] BYREF

  v14 = 0;
  result = __std_init_once_begin_initialize(lpInitOnce, 0, &v14, 0);
  if ( !result )
    abort();
  if ( v14 )
  {
    v5 = *a2;
    if ( !*(_BYTE *)(v5 + 64) )
    {
      v6 = std::_Func_class<std::unique_ptr<Mso::Telemetry::Configuration::Details::IEnvironment>,>::operator()(
             v5 + 72,
             v9);
      if ( *(_BYTE *)(v5 + 64) )
      {
        std::_Hash<std::_Umap_traits<std::string,unsigned int,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,unsigned int>>,0>>::~_Hash<std::_Umap_traits<std::string,unsigned int,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,unsigned int>>,0>>(v5);
        *(_BYTE *)(v5 + 64) = 0;
      }
      std::_Hash<std::_Umap_traits<std::string,unsigned int,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,unsigned int>>,0>>::_Hash<std::_Umap_traits<std::string,unsigned int,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,unsigned int>>,0>>(
        v5,
        v6);
      *(_BYTE *)(v5 + 64) = 1;
      v12 = 7;
      v13 = 8;
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,bool>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,bool>>>>>>(v11);
      std::list<std::pair<std::string const,unsigned int>>::~list<std::pair<std::string const,unsigned int>>(v10);
    }
    result = InitOnceComplete(lpInitOnce, 0, 0);
    if ( !result )
      _std_init_once_link_alternate_names_and_abort(v8, v7);
  }
  return result;
}

```

## disassembly

```asm
0x18003474c  mov     rax, rsp
0x18003474f  mov     [rax+10h], rbx
0x180034753  mov     [rax+18h], rsi
0x180034757  push    rdi
0x180034758  sub     rsp, 70h
0x18003475c  mov     rbx, rdx
0x18003475f  mov     rdi, rcx
0x180034762  mov     dword ptr [rax+8], 0
0x180034769  xor     r9d, r9d; lpContext
0x18003476c  lea     r8, [rax+8]; fPending
0x180034770  xor     edx, edx; dwFlags
0x180034772  call    cs:__imp___std_init_once_begin_initialize
0x180034778  test    eax, eax
0x18003477a  jnz     short loc_180034783
0x18003477c  call    cs:__imp_abort
0x180034783  cmp     [rsp+78h+arg_0], 0
0x18003478b  jz      loc_180034819
0x180034791  mov     [rsp+78h+var_58], rdi
0x180034796  mov     [rsp+78h+var_50], 4
0x18003479f  mov     rbx, [rbx]
0x1800347a2  cmp     byte ptr [rbx+40h], 0
0x1800347a6  jnz     short loc_180034801
0x1800347a8  lea     rcx, [rbx+48h]
0x1800347ac  lea     rdx, [rsp+78h+var_48]
0x1800347b1  call    ??R?$_Func_class@V?$unique_ptr@UIEnvironment@Details@Configuration@Telemetry@Mso@@U?$default_delete@UIEnvironment@Details@Configuration@Telemetry@Mso@@@std@@@std@@$$V@std@@QEBA?AV?$unique_ptr@UIEnvironment@Details@Configuration@Telemetry@Mso@@U?$default_delete@UIEnvironment@Details@Configuration@Telemetry@Mso@@@std@@@1@XZ; std::_Func_class<std::unique_ptr<Mso::Telemetry::Configuration::Details::IEnvironment>,>::operator()(void)
0x1800347b6  mov     rsi, rax
0x1800347b9  cmp     byte ptr [rbx+40h], 0
0x1800347bd  jz      short loc_1800347CB
0x1800347bf  mov     rcx, rbx
0x1800347c2  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::string,uint,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,uint>>,0>>::~_Hash<std::_Umap_traits<std::string,uint,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,uint>>,0>>(void)
0x1800347c7  mov     byte ptr [rbx+40h], 0
0x1800347cb  mov     rdx, rsi
0x1800347ce  mov     rcx, rbx
0x1800347d1  call    ??0?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@IV?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@2@$0A@@std@@@std@@IEAA@$$QEAV01@@Z; std::_Hash<std::_Umap_traits<std::string,uint,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,uint>>,0>>::_Hash<std::_Umap_traits<std::string,uint,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,uint>>,0>>(std::_Hash<std::_Umap_traits<std::string,uint,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,uint>>,0>> &&)
0x1800347d6  mov     byte ptr [rbx+40h], 1
0x1800347da  mov     [rsp+78h+var_18], 7
0x1800347e3  mov     [rsp+78h+var_10], 8
0x1800347ec  lea     rcx, [rsp+78h+var_30]
0x1800347f1  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,bool>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<std::wstring const,bool>>>>>>(void)
0x1800347f6  lea     rcx, [rsp+78h+var_40]
0x1800347fb  call    ??1?$list@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I@std@@@2@@std@@QEAA@XZ; std::list<std::pair<std::string const,uint>>::~list<std::pair<std::string const,uint>>(void)
0x180034800  nop
0x180034801  xor     r8d, r8d; lpContext
0x180034804  xor     edx, edx; dwFlags
0x180034806  mov     rcx, rdi; lpInitOnce
0x180034809  call    cs:__imp_InitOnceComplete
0x18003480f  test    eax, eax
0x180034811  jnz     short loc_180034819
0x180034813  call    __std_init_once_link_alternate_names_and_abort
0x180034819  lea     r11, [rsp+78h+var_8]
0x18003481e  mov     rbx, [r11+18h]
0x180034822  mov     rsi, [r11+20h]
0x180034826  mov     rsp, r11
0x180034829  pop     rdi
0x18003482a  retn
```
