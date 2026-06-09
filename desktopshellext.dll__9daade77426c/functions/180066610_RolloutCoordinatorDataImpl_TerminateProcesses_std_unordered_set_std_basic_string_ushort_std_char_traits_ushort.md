# RolloutCoordinatorDataImpl::TerminateProcesses(std::unordered_set<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> const &)

- ea: `0x180066610`
- end: `0x180066a95`
- name: `?TerminateProcesses@RolloutCoordinatorDataImpl@@UEAA?AV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV23@@Z`
- size: `1157`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000bdf0`
- `0x18000c444`
- `0x180015cf0`
- `0x180019ec8`
- `0x18001a100`
- `0x18001c608`
- `0x18001f874`
- `0x18002a3d0`
- `0x1800433a0`
- `0x18005a07c`
- `0x18005c6b0`
- `0x18005c948`
- `0x18005c9f8`
- `0x18005ec2c`
- `0x18006299c`
- `0x180066610`
- `0x1800688ec`
- `0x180068a60`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18006699c`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x18006699c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180066981`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180066981`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180066a31`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x180066a31`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateProcessesW` at `0x1800666ee`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSEnumerateProcessesW` at `0x1800666ee`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall RolloutCoordinatorDataImpl::TerminateProcesses(__int64 a1, __int64 a2, int a3)
{
  BOOL v5; // ebx
  bool v6; // zf
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  bool v10; // bl
  _QWORD *v11; // rax
  _QWORD *v12; // rax
  char *v13; // rax
  PVOID v14; // rcx
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  PVOID pMemory; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pCount; // [rsp+40h] [rbp-C0h] BYREF
  void *v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h]
  _QWORD *v21; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v22; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v23; // [rsp+68h] [rbp-98h] BYREF
  _QWORD *v24; // [rsp+70h] [rbp-90h] BYREF
  char *v25; // [rsp+78h] [rbp-88h] BYREF
  PVOID *p_pMemory; // [rsp+80h] [rbp-80h] BYREF
  PWTS_PROCESS_INFOW ppProcessInfo; // [rsp+88h] [rbp-78h] BYREF
  char v28; // [rsp+90h] [rbp-70h]
  _QWORD v29[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v30[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v31[3]; // [rsp+C0h] [rbp-40h] BYREF
  char v32[8]; // [rsp+D8h] [rbp-28h] BYREF
  char v33[8]; // [rsp+E0h] [rbp-20h] BYREF
  char v34[8]; // [rsp+E8h] [rbp-18h] BYREF
  char v35[8]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD *v36; // [rsp+F8h] [rbp-8h]
  __int64 v37; // [rsp+100h] [rbp+0h]
  char v38[8]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD *v39; // [rsp+138h] [rbp+38h]
  char v40[8]; // [rsp+170h] [rbp+70h] BYREF
  _QWORD *v41; // [rsp+178h] [rbp+78h]
  char v42[8]; // [rsp+1B0h] [rbp+B0h] BYREF
  _QWORD *v43; // [rsp+1B8h] [rbp+B8h]
  __int64 v44; // [rsp+1C0h] [rbp+C0h]
  _BYTE v45[64]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v46[32]; // [rsp+230h] [rbp+130h] BYREF

  v31[2] = a2;
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(a2);
  v20 = 1;
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v40);
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v35);
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v38);
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v45);
  std::unordered_set<std::wstring>::unordered_set<std::wstring>(v42);
  GetImpactedProcessLists(a3, (unsigned int)v40, (unsigned int)v35, (unsigned int)v38);
  pMemory = 0;
  pCount = 0;
  p_pMemory = &pMemory;
  ppProcessInfo = 0;
  v28 = 1;
  v5 = WTSEnumerateProcessesW(0, 0, 1u, &ppProcessInfo, &pCount);
  wil::details::out_param_t<wistd::unique_ptr<_WTS_PROCESS_INFOW [0],wil::function_deleter<void (*)(void *),&void WTSFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_WTS_PROCESS_INFOW [0],wil::function_deleter<void (*)(void *),&void WTSFreeMemory(void *)>>>(&p_pMemory);
  if ( v5 )
  {
    v16 = 0;
    if ( pCount )
    {
      while ( 1 )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::GetImpl'::`2'::impl) )
        {
          v29[0] = &pMemory;
          v29[1] = &v16;
          std::find_if_std::_List_const_iterator_std::_List_val_std::_List_simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_f2e4909beca97f4a5e4c15d63bf0188f___(
            &v21,
            *v41,
            v41,
            v29);
          v6 = v21 == v41;
        }
        else
        {
          std::wstring::wstring(v46, *((_QWORD *)pMemory + 3 * v16 + 1));
          v7 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                           v40,
                           v32,
                           v46);
          v8 = v41;
          v9 = (_QWORD *)*v7;
          std::wstring::~wstring(v46);
          v6 = v9 == v8;
        }
        v10 = !v6;
        if ( v6 )
        {
          if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::GetImpl'::`2'::impl) )
          {
            v30[0] = &pMemory;
            v30[1] = &v16;
            std::find_if_std::_List_const_iterator_std::_List_val_std::_List_simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_f2e4909beca97f4a5e4c15d63bf0188f___(
              &v22,
              *v39,
              v39,
              v30);
            v10 = v22 != v39;
          }
          else
          {
            std::wstring::wstring(v46, *((_QWORD *)pMemory + 3 * v16 + 1));
            v11 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                              v38,
                              v33,
                              v46);
            v10 = *v11 != (_QWORD)v39;
            std::wstring::~wstring(v46);
          }
          if ( !v10 && v37 )
          {
            GetBackgroundTaskPackageIdentity(
              &v19,
              *((_QWORD *)pMemory + 3 * v16 + 1),
              *((_DWORD *)pMemory + 6 * v16 + 1));
            if ( v19 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::GetImpl'::`2'::impl) )
              {
                std::find_if_std::_List_const_iterator_std::_List_val_std::_List_simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_a6f9daafcd5fedccb258aa6ba48916c4___(
                  &v23,
                  *v36,
                  v36,
                  &v19);
                v10 = v23 != v36;
              }
              else
              {
                std::wstring::wstring(v46, v19);
                v12 = (_QWORD *)std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(
                                  v35,
                                  v34,
                                  v46);
                v10 = *v12 != (_QWORD)v36;
                std::wstring::~wstring(v46);
              }
            }
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v19);
          }
        }
        if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendDelayReasons>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ExtendDelayReasons>::GetImpl'::`2'::impl) )
          goto LABEL_21;
        if ( v10 )
          goto LABEL_22;
        if ( v44 )
          break;
LABEL_26:
        if ( ++v16 >= pCount )
          goto LABEL_27;
      }
      v31[0] = &pMemory;
      v31[1] = &v16;
      std::find_if_std::_List_const_iterator_std::_List_val_std::_List_simple_types_std::basic_string_unsigned_short_std::char_traits_unsigned_short__std::allocator_unsigned_short___________lambda_f2e4909beca97f4a5e4c15d63bf0188f___(
        &v24,
        *v43,
        v43,
        v31);
      v10 = v24 != v43;
LABEL_21:
      if ( v10 )
      {
LABEL_22:
        v13 = (char *)OpenProcess(0x101001u, 0, *((_DWORD *)pMemory + 6 * v16 + 1));
        v25 = v13;
        if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && TerminateProcess(v13, 0xFFFFFFFF) )
        {
          RebootlessFeatureRolloutTIPTelemetry::RebootlessFeatureRollout_TerminatedProcess<unsigned short * &>((char *)pMemory + 24 * v16 + 8);
          std::wstring::wstring(v46, *((_QWORD *)pMemory + 3 * v16 + 1));
          std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(
            a2,
            &p_pMemory,
            v46);
          std::wstring::~wstring(v46);
        }
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v25);
        goto LABEL_26;
      }
      goto LABEL_26;
    }
  }
LABEL_27:
  v14 = pMemory;
  pMemory = 0;
  if ( v14 )
    WTSFreeMemory(v14);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v42);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v45);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v38);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v35);
  std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(v40);
  return a2;
}

```

## disassembly

```asm
0x180066610  mov     [rsp-8+arg_0], rbx
0x180066615  push    rbp
0x180066616  push    rsi
0x180066617  push    rdi
0x180066618  lea     rbp, [rsp-160h]
0x180066620  sub     rsp, 260h
0x180066627  mov     rax, cs:__security_cookie
0x18006662e  xor     rax, rsp
0x180066631  mov     [rbp+170h+var_20], rax
0x180066638  mov     rbx, r8
0x18006663b  mov     rsi, rdx
0x18006663e  mov     [rbp+170h+var_1A0], rdx
0x180066642  mov     [rsp+270h+var_220], 0
0x18006664a  mov     rcx, rdx
0x18006664d  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180066652  mov     [rsp+270h+var_220], 1
0x18006665a  lea     rcx, [rbp+170h+var_100]
0x18006665e  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180066663  nop
0x180066664  lea     rcx, [rbp+170h+var_180]
0x180066668  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x18006666d  nop
0x18006666e  lea     rcx, [rbp+170h+var_140]
0x180066672  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180066677  nop
0x180066678  lea     rcx, [rbp+170h+var_80]
0x18006667f  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180066684  nop
0x180066685  lea     rcx, [rbp+170h+var_C0]
0x18006668c  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x180066691  nop
0x180066692  lea     rax, [rbp+170h+var_C0]
0x180066699  mov     [rsp+270h+var_248], rax
0x18006669e  lea     r9, [rbp+170h+var_140]
0x1800666a2  lea     r8, [rbp+170h+var_180]
0x1800666a6  lea     rdx, [rbp+170h+var_100]
0x1800666aa  mov     rcx, rbx
0x1800666ad  call    ?GetImpactedProcessLists@@YAXAEBV?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV12@1111@Z; GetImpactedProcessLists(std::unordered_set<std::wstring> const &,std::unordered_set<std::wstring> &,std::unordered_set<std::wstring> &,std::unordered_set<std::wstring> &,std::unordered_set<std::wstring> &,std::unordered_set<std::wstring> &)
0x1800666b2  mov     [rsp+270h+pMemory], 0
0x1800666bb  mov     [rsp+270h+var_230], 0
0x1800666c3  lea     rax, [rsp+270h+pMemory]
0x1800666c8  mov     [rbp+170h+var_1F0], rax
0x1800666cc  mov     [rbp+170h+ppProcessInfo], 0
0x1800666d4  mov     [rbp+170h+var_1E0], 1
0x1800666d8  lea     rax, [rsp+270h+var_230]
0x1800666dd  mov     [rsp+270h+pCount], rax; pCount
0x1800666e2  lea     r9, [rbp+170h+ppProcessInfo]; ppProcessInfo
0x1800666e6  xor     edx, edx; Reserved
0x1800666e8  xor     ecx, ecx; hServer
0x1800666ea  lea     r8d, [rdx+1]; Version
0x1800666ee  call    cs:__imp_WTSEnumerateProcessesW
0x1800666f4  mov     ebx, eax
0x1800666f6  lea     rcx, [rbp+170h+var_1F0]
0x1800666fa  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@U_WTS_PROCESS_INFOW@@U?$function_deleter@P6AXPEAX@Z$1?WTSFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_WTS_PROCESS_INFOW [0],wil::function_deleter<void (*)(void *),&WTSFreeMemory(void *)>>>::~out_param_t<wistd::unique_ptr<_WTS_PROCESS_INFOW [0],wil::function_deleter<void (*)(void *),&WTSFreeMemory(void *)>>>(void)
0x1800666ff  test    ebx, ebx
0x180066701  jz      loc_180066A1E
0x180066707  mov     [rsp+270h+var_240], 0
0x18006670f  cmp     [rsp+270h+var_230], 0
0x180066714  jbe     loc_180066A1E
0x18006671a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VelRestartProfiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VelRestartProfiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::GetImpl(void)'::`2'::impl
0x180066721  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VelRestartProfiles@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::__private_IsEnabled(void)
0x180066726  test    al, al
0x180066728  jz      short loc_18006675F
0x18006672a  mov     rdx, [rbp+170h+var_F8]
0x18006672e  lea     rax, [rsp+270h+pMemory]
0x180066733  mov     [rbp+170h+var_1D0], rax
0x180066737  lea     rax, [rsp+270h+var_240]
0x18006673c  mov     [rbp+170h+var_1C8], rax
0x180066740  lea     r9, [rbp+170h+var_1D0]
0x180066744  mov     r8, rdx
0x180066747  mov     rdx, [rdx]
0x18006674a  lea     rcx, [rsp+270h+var_218]
0x18006674f  call    std__find_if_std___List_const_iterator_std___List_val_std___List_simple_types_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________lambda_f2e4909beca97f4a5e4c15d63bf0188f___
0x180066754  mov     rax, [rbp+170h+var_F8]
0x180066758  cmp     [rsp+270h+var_218], rax
0x18006675d  jmp     short loc_1800667A7
0x18006675f  mov     eax, [rsp+270h+var_240]
0x180066763  lea     rcx, [rax+rax*2]
0x180066767  mov     rdx, [rsp+270h+pMemory]
0x18006676c  mov     rdx, [rdx+rcx*8+8]
0x180066771  lea     rcx, [rbp+170h+var_40]
0x180066778  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006677d  lea     r8, [rbp+170h+var_40]
0x180066784  lea     rdx, [rbp+170h+var_198]
0x180066788  lea     rcx, [rbp+170h+var_100]
0x18006678c  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x180066791  mov     rbx, [rbp+170h+var_F8]
0x180066795  mov     rdi, [rax]
0x180066798  lea     rcx, [rbp+170h+var_40]
0x18006679f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800667a4  cmp     rdi, rbx
0x1800667a7  setnz   bl
0x1800667aa  test    bl, bl
0x1800667ac  jnz     loc_180066902
0x1800667b2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VelRestartProfiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VelRestartProfiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::GetImpl(void)'::`2'::impl
0x1800667b9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VelRestartProfiles@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::__private_IsEnabled(void)
0x1800667be  test    al, al
0x1800667c0  jz      short loc_1800667FA
0x1800667c2  mov     rdx, [rbp+170h+var_138]
0x1800667c6  lea     rax, [rsp+270h+pMemory]
0x1800667cb  mov     [rbp+170h+var_1C0], rax
0x1800667cf  lea     rax, [rsp+270h+var_240]
0x1800667d4  mov     [rbp+170h+var_1B8], rax
0x1800667d8  lea     r9, [rbp+170h+var_1C0]
0x1800667dc  mov     r8, rdx
0x1800667df  mov     rdx, [rdx]
0x1800667e2  lea     rcx, [rsp+270h+var_210]
0x1800667e7  call    std__find_if_std___List_const_iterator_std___List_val_std___List_simple_types_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________lambda_f2e4909beca97f4a5e4c15d63bf0188f___
0x1800667ec  mov     rax, [rbp+170h+var_138]
0x1800667f0  cmp     [rsp+270h+var_210], rax
0x1800667f5  setnz   bl
0x1800667f8  jmp     short loc_180066845
0x1800667fa  mov     eax, [rsp+270h+var_240]
0x1800667fe  lea     rcx, [rax+rax*2]
0x180066802  mov     rdx, [rsp+270h+pMemory]
0x180066807  mov     rdx, [rdx+rcx*8+8]
0x18006680c  lea     rcx, [rbp+170h+var_40]
0x180066813  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180066818  lea     r8, [rbp+170h+var_40]
0x18006681f  lea     rdx, [rbp+170h+var_190]
0x180066823  lea     rcx, [rbp+170h+var_140]
0x180066827  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x18006682c  mov     rcx, rax
0x18006682f  mov     rax, [rbp+170h+var_138]
0x180066833  cmp     [rcx], rax
0x180066836  setnz   bl
0x180066839  lea     rcx, [rbp+170h+var_40]
0x180066840  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180066845  test    bl, bl
0x180066847  jnz     loc_180066902
0x18006684d  cmp     [rbp+170h+var_170], 0
0x180066852  jbe     loc_180066902
0x180066858  mov     eax, [rsp+270h+var_240]
0x18006685c  lea     rcx, [rax+rax*2]
0x180066860  mov     rdx, [rsp+270h+pMemory]
0x180066865  mov     r8d, [rdx+rcx*8+4]
0x18006686a  mov     rdx, [rdx+rcx*8+8]
0x18006686f  lea     rcx, [rsp+270h+var_228]; void *
0x180066874  call    ?GetBackgroundTaskPackageIdentity@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBGK@Z; GetBackgroundTaskPackageIdentity(ushort const *,ulong)
0x180066879  nop
0x18006687a  cmp     [rsp+270h+var_228], 0
0x180066880  jz      short loc_1800668F8
0x180066882  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_VelRestartProfiles@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VelRestartProfiles@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles> `wil::Feature<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::GetImpl(void)'::`2'::impl
0x180066889  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_VelRestartProfiles@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_VelRestartProfiles>::__private_IsEnabled(void)
0x18006688e  test    al, al
0x180066890  jz      short loc_1800668B9
0x180066892  mov     rdx, [rbp+170h+var_178]
0x180066896  lea     r9, [rsp+270h+var_228]
0x18006689b  mov     r8, rdx
0x18006689e  mov     rdx, [rdx]
0x1800668a1  lea     rcx, [rsp+270h+var_208]
0x1800668a6  call    std__find_if_std___List_const_iterator_std___List_val_std___List_simple_types_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________lambda_a6f9daafcd5fedccb258aa6ba48916c4___
0x1800668ab  mov     rax, [rbp+170h+var_178]
0x1800668af  cmp     [rsp+270h+var_208], rax
0x1800668b4  setnz   bl
0x1800668b7  jmp     short loc_1800668F8
0x1800668b9  mov     rdx, [rsp+270h+var_228]
0x1800668be  lea     rcx, [rbp+170h+var_40]
0x1800668c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800668ca  lea     r8, [rbp+170h+var_40]
0x1800668d1  lea     rdx, [rbp+170h+var_188]
0x1800668d5  lea     rcx, [rbp+170h+var_180]
0x1800668d9  call    ?find@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::find(std::wstring const &)
0x1800668de  mov     rcx, rax
0x1800668e1  mov     rax, [rbp+170h+var_178]
0x1800668e5  cmp     [rcx], rax
0x1800668e8  setnz   bl
0x1800668eb  lea     rcx, [rbp+170h+var_40]
0x1800668f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800668f7  nop
0x1800668f8  lea     rcx, [rsp+270h+var_228]
0x1800668fd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180066902  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ExtendDelayReasons@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ExtendDelayReasons@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendDelayReasons> `wil::Feature<__WilFeatureTraits_Feature_ExtendDelayReasons>::GetImpl(void)'::`2'::impl
0x180066909  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ExtendDelayReasons@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ExtendDelayReasons>::__private_IsEnabled(void)
0x18006690e  test    al, al
0x180066910  jz      short loc_180066960
0x180066912  test    bl, bl
0x180066914  jnz     short loc_180066968
0x180066916  cmp     [rbp+170h+var_B0], 0
0x18006691e  jbe     loc_180066A0A
0x180066924  mov     rdx, [rbp+170h+var_B8]
0x18006692b  lea     rax, [rsp+270h+pMemory]
0x180066930  mov     [rbp+170h+var_1B0], rax
0x180066934  lea     rax, [rsp+270h+var_240]
0x180066939  mov     [rbp+170h+var_1A8], rax
0x18006693d  lea     r9, [rbp+170h+var_1B0]
0x180066941  mov     r8, rdx
0x180066944  mov     rdx, [rdx]
0x180066947  lea     rcx, [rsp+270h+var_200]
0x18006694c  call    std__find_if_std___List_const_iterator_std___List_val_std___List_simple_types_std__basic_string_unsigned_short_std__char_traits_unsigned_short__std__allocator_unsigned_short___________lambda_f2e4909beca97f4a5e4c15d63bf0188f___
0x180066951  mov     rax, [rbp+170h+var_B8]
0x180066958  cmp     [rsp+270h+var_200], rax
0x18006695d  setnz   bl
0x180066960  test    bl, bl
0x180066962  jz      loc_180066A0A
0x180066968  mov     eax, [rsp+270h+var_240]
0x18006696c  lea     rcx, [rax+rax*2]
0x180066970  mov     r8, [rsp+270h+pMemory]
0x180066975  mov     r8d, [r8+rcx*8+4]; dwProcessId
0x18006697a  xor     edx, edx; bInheritHandle
0x18006697c  mov     ecx, 101001h; dwDesiredAccess
0x180066981  call    cs:__imp_OpenProcess
0x180066987  mov     [rsp+270h+var_1F8], rax
0x18006698c  lea     rcx, [rax-1]
0x180066990  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180066994  ja      short loc_180066A00
0x180066996  or      edx, 0FFFFFFFFh; uExitCode
0x180066999  mov     rcx, rax; hProcess
0x18006699c  call    cs:__imp_TerminateProcess
0x1800669a2  test    eax, eax
0x1800669a4  jz      short loc_180066A00
0x1800669a6  mov     eax, [rsp+270h+var_240]
0x1800669aa  lea     rcx, [rax+rax*2]
0x1800669ae  mov     rax, [rsp+270h+pMemory]
0x1800669b3  lea     rcx, [rcx+1]
0x1800669b7  lea     rcx, [rax+rcx*8]
0x1800669bb  call    ??$RebootlessFeatureRollout_TerminatedProcess@AEAPEAG@RebootlessFeatureRolloutTIPTelemetry@@SAXAEAPEAG@Z; RebootlessFeatureRolloutTIPTelemetry::RebootlessFeatureRollout_TerminatedProcess<ushort * &>(ushort * &)
0x1800669c0  mov     eax, [rsp+270h+var_240]
0x1800669c4  lea     rcx, [rax+rax*2]
0x1800669c8  mov     rdx, [rsp+270h+pMemory]
0x1800669cd  mov     rdx, [rdx+rcx*8+8]
0x1800669d2  lea     rcx, [rbp+170h+var_40]
0x1800669d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800669de  nop
0x1800669df  lea     r8, [rbp+170h+var_40]
0x1800669e6  lea     rdx, [rbp+170h+var_1F0]
0x1800669ea  mov     rcx, rsi
0x1800669ed  call    ??$emplace@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::emplace<std::wstring>(std::wstring &&)
0x1800669f2  nop
0x1800669f3  lea     rcx, [rbp+170h+var_40]
0x1800669fa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800669ff  nop
0x180066a00  lea     rcx, [rsp+270h+var_1F8]
0x180066a05  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180066a0a  mov     eax, [rsp+270h+var_240]
0x180066a0e  inc     eax
0x180066a10  mov     [rsp+270h+var_240], eax
0x180066a14  cmp     eax, [rsp+270h+var_230]
0x180066a18  jb      loc_18006671A
0x180066a1e  mov     rcx, [rsp+270h+pMemory]; pMemory
0x180066a23  mov     [rsp+270h+pMemory], 0
0x180066a2c  test    rcx, rcx
0x180066a2f  jz      short loc_180066A38
0x180066a31  call    cs:__imp_WTSFreeMemory
0x180066a37  nop
0x180066a38  lea     rcx, [rbp+170h+var_C0]
0x180066a3f  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180066a44  nop
0x180066a45  lea     rcx, [rbp+170h+var_80]
0x180066a4c  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180066a51  nop
0x180066a52  lea     rcx, [rbp+170h+var_140]
0x180066a56  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180066a5b  nop
0x180066a5c  lea     rcx, [rbp+170h+var_180]
0x180066a60  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180066a65  nop
0x180066a66  lea     rcx, [rbp+170h+var_100]
0x180066a6a  call    ??1?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::~_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>(void)
0x180066a6f  mov     rax, rsi
0x180066a72  mov     rcx, [rbp+170h+var_20]
0x180066a79  xor     rcx, rsp; StackCookie
0x180066a7c  call    __security_check_cookie
0x180066a81  mov     rbx, [rsp+270h+arg_0]
0x180066a89  add     rsp, 260h
0x180066a90  pop     rdi
0x180066a91  pop     rsi
0x180066a92  pop     rbp
0x180066a93  retn
```
