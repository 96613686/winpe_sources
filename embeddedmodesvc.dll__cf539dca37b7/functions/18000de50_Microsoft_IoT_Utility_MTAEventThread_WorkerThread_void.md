# Microsoft::IoT::Utility::MTAEventThread::WorkerThread(void)

- ea: `0x18000de50`
- end: `0x18000e441`
- name: `?WorkerThread@MTAEventThread@Utility@IoT@Microsoft@@MEAAJXZ`
- size: `1521`
- prototype: `__int64 __fastcall(Microsoft::IoT::Utility::MTAEventThread *__hidden this)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002b10`
- `0x1800035a0`
- `0x180008358`
- `0x180008378`
- `0x180009f7c`
- `0x18000a658`
- `0x18000a730`
- `0x18000aa10`
- `0x18000aa70`
- `0x18000aad8`
- `0x18000af40`
- `0x18000c668`
- `0x18000c888`
- `0x18000c9e0`
- `0x18000c9f4`
- `0x18000cb28`
- `0x18000cc3c`
- `0x18000cd7c`
- `0x18000d2ac`
- `0x18000d410`
- `0x18000d7c8`
- `0x18000d7ec`
- `0x18000da64`
- `0x18000dc84`
- `0x18000de50`
- `0x18000ea34`
- `0x18000eb28`
- `0x18000eb40`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000def5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000def5`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e1ed`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e1ed`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000de88`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000de88`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e40a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e40a`

## string_xrefs

- `0x18000de9f`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`
- `0x18000e048`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`
- `0x18000e116`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`
- `0x18000e2da`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`
- `0x18000e3f8`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Microsoft::IoT::Utility::MTAEventThread::WorkerThread(Microsoft::IoT::Utility::MTAEventThread *this)
{
  Microsoft::IoT::Utility::MTAEventThread *v1; // r15
  HRESULT v2; // eax
  void *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r9
  __int64 i; // rbx
  __int64 v14; // r14
  unsigned __int64 v15; // rbx
  DWORD v16; // esi
  __int64 v17; // rdx
  unsigned __int64 v18; // rcx
  __int64 *v19; // r9
  void **v20; // r8
  void *v21; // rax
  __int64 v22; // rax
  DWORD v23; // eax
  unsigned int v24; // r8d
  const char *v25; // r9
  __int64 v26; // r12
  __int64 v27; // r15
  Microsoft::IoT::Utility::MTAThreadPool *v28; // rsi
  struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *v29; // rbx
  int v30; // esi
  __int64 v31; // rcx
  __int64 v32; // rsi
  __int64 v33; // r14
  __int64 v34; // rbx
  const char *v35; // r9
  BOOL bAlertable; // [rsp+20h] [rbp-538h]
  int v38; // [rsp+30h] [rbp-528h]
  __int64 v39; // [rsp+38h] [rbp-520h] BYREF
  __int64 v40; // [rsp+40h] [rbp-518h]
  __int64 v41; // [rsp+48h] [rbp-510h]
  __int64 *v42; // [rsp+50h] [rbp-508h] BYREF
  __int64 *v43; // [rsp+58h] [rbp-500h]
  __int64 *v44; // [rsp+60h] [rbp-4F8h]
  char v45; // [rsp+69h] [rbp-4EFh]
  struct _RTL_CRITICAL_SECTION *v46; // [rsp+70h] [rbp-4E8h] BYREF
  Microsoft::IoT::Utility::MTAEventThread *v47; // [rsp+78h] [rbp-4E0h]
  _QWORD *v48; // [rsp+80h] [rbp-4D8h] BYREF
  __int64 v49; // [rsp+88h] [rbp-4D0h]
  __int64 v50; // [rsp+90h] [rbp-4C8h]
  __int64 v51; // [rsp+98h] [rbp-4C0h]
  __int64 v52; // [rsp+A0h] [rbp-4B8h]
  struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *v53; // [rsp+A8h] [rbp-4B0h] BYREF
  _QWORD v54[2]; // [rsp+B0h] [rbp-4A8h] BYREF
  __int64 v55; // [rsp+C0h] [rbp-498h] BYREF
  _QWORD v56[3]; // [rsp+C8h] [rbp-490h] BYREF
  __int64 v57; // [rsp+E0h] [rbp-478h] BYREF
  __int64 *v58; // [rsp+E8h] [rbp-470h] BYREF
  wil::ResultException *v59; // [rsp+F0h] [rbp-468h] BYREF
  HANDLE Handles[64]; // [rsp+100h] [rbp-458h] BYREF
  _QWORD v61[64]; // [rsp+300h] [rbp-258h] BYREF
  std::bad_alloc *v62; // [rsp+500h] [rbp-58h] BYREF
  std::invalid_argument *v63; // [rsp+508h] [rbp-50h] BYREF
  std::range_error *v64; // [rsp+510h] [rbp-48h] BYREF
  std::runtime_error *v65; // [rsp+518h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+558h] [rbp+0h]

  v1 = this;
  v47 = this;
  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xCF,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      (const char *)(unsigned int)v2,
      bAlertable);
  v45 = 1;
  v38 = 0;
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(&v42);
  std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(&v39);
  try
  {
    do
    {
      wil::details::ResetEvent(*((wil::details **)v1 + 2), v3);
      std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>(&v48);
      v4 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)v1 + 4) + 184LL);
      EnterCriticalSection(v4);
      v46 = v4;
      v5 = *((_QWORD *)v1 + 4) + 224LL;
      if ( (_QWORD **)v5 != &v48 )
      {
        v6 = *(_QWORD **)v5;
        *(_QWORD *)v5 = v48;
        v48 = v6;
        if ( *(_QWORD *)v5 )
        {
          **(_QWORD **)v5 = v5;
          v6 = v48;
        }
        if ( v6 )
          *v6 = &v48;
        v7 = *(_QWORD *)(v5 + 8);
        *(_QWORD *)(v5 + 8) = v49;
        v49 = v7;
        v8 = *(_QWORD *)(v5 + 16);
        *(_QWORD *)(v5 + 16) = v50;
        v50 = v8;
        v9 = *(_QWORD *)(v5 + 24);
        *(_QWORD *)(v5 + 24) = v51;
        v51 = v9;
        v10 = *(_QWORD *)(v5 + 32);
        *(_QWORD *)(v5 + 32) = v52;
        v52 = v10;
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v46);
      while ( v52 )
      {
        v11 = std::queue<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::front(&v48);
        std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>(
          v56,
          v11);
        v57 = *(_QWORD *)(v11 + 24);
        Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(&v57);
        std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::pop_front(&v48);
        v12 = v40;
        if ( (unsigned __int64)(v52 + 2 + ((v40 - v39) >> 4)) > 0x40 )
          wil::details::in1diag3::FailFast_Hr(
            retaddr,
            (void *)0xE7,
            (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
            (const char *)0x8000FFFFLL,
            bAlertable);
        for ( i = v56[0]; i != v56[1]; i += 16 )
        {
          if ( v12 == v41 )
          {
            std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::_Emplace_reallocate<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> const &>(
              &v39,
              v12,
              i);
          }
          else
          {
            std::_Construct_in_place<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>> const &>(
              v12,
              i);
            v40 += 16;
          }
          if ( v43 == v44 )
            std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> const &>(
              &v42,
              v43,
              &v57);
          else
            std::_Construct_in_place<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> const &>(
              v43++,
              &v57);
          v12 = v40;
        }
        std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::~pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>((__int64)v56);
      }
      v14 = v39;
      v15 = (v40 - v39) >> 4;
      v16 = v15 + 2;
      if ( (unsigned int)(v15 + 2) > 0x40 )
        wil::details::in1diag3::FailFast_Hr(
          retaddr,
          (void *)0xF3,
          (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
          (const char *)0x8000FFFFLL,
          bAlertable);
      memset_0(Handles, 0, sizeof(Handles));
      memset_0(v61, 0, sizeof(v61));
      v17 = 0;
      v18 = 0;
      if ( v15 )
      {
        v19 = v42;
        do
        {
          if ( v18 && v19[v18] != v19[v18 - 1] )
            v17 = 0;
          v20 = *(void ***)(v14 + 16 * v18);
          if ( v20 )
            v21 = *v20;
          else
            v21 = 0;
          Handles[v18] = v21;
          v22 = v17++;
          v61[v18++] = v22;
        }
        while ( v18 < v15 );
      }
      v1 = v47;
      Handles[(unsigned int)v15] = (HANDLE)*((_QWORD *)v47 + 2);
      LODWORD(v46) = v15 + 1;
      Handles[(unsigned int)(v15 + 1)] = (HANDLE)*((_QWORD *)v1 + 1);
      v23 = WaitForMultipleObjectsEx(v16, Handles, 0, 0xFFFFFFFF, 1);
      v26 = v23;
      if ( v23 == -1 )
        wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x108, v24, v25);
      if ( v16 > 2 && (unsigned int)v26 < (unsigned int)v15 )
      {
        v55 = v42[v26];
        v27 = v55;
        Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(&v55);
        v28 = (Microsoft::IoT::Utility::MTAThreadPool *)*((_QWORD *)v47 + 4);
        v54[0] = v27;
        Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(v54);
        v54[1] = v61[v26];
        Microsoft::WRL::Details::Make_Microsoft::IoT::Utility::MTAThreadPool::LambdaWorkCallback__lambda_e5e820ed515346ac483c45f56bfacfa7_____lambda_e5e820ed515346ac483c45f56bfacfa7___(
          &v53,
          v54);
        v29 = v53;
        if ( v53 )
          v30 = Microsoft::IoT::Utility::MTAThreadPool::QueueWorkItem(v28, v53);
        else
          v30 = -2147024882;
        if ( v29 )
        {
          v53 = 0;
          (*(void (__fastcall **)(struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *))(*(_QWORD *)v29 + 16LL))(v29);
        }
        if ( v30 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x111,
            (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
            (const char *)(unsigned int)v30);
        v31 = v54[0];
        if ( v54[0] )
        {
          v54[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        }
        v32 = 16 * v26 + v39;
        v33 = v40;
        v34 = v32 + 16;
        if ( v32 + 16 != v40 )
        {
          do
          {
            if ( v32 != v34 )
              std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::operator=(
                v32,
                v34);
            v32 += 16;
            v34 += 16;
          }
          while ( v34 != v33 );
          v33 = v40;
        }
        std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>(v33 - 16);
        v40 -= 16;
        std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::erase(
          (__int64)&v42,
          &v58,
          &v42[v26]);
        if ( v27 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        v1 = v47;
      }
      __1__deque_U__pair_V__vector_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil__V__allocator_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil___std___std__V__ComPtr_UIMTAThreadPoolEventCallback_Utility_IoT_Microsoft___WRL_Microsoft___std__V__allocator_U__pair_V__vector_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil__V__allocator_V__shared_any_t_V__shared_storage_V__unique_any_t_V__unique_storage_U__handle_null_resource_policy_P6AHPEAX_Z_1_CloseHandle__YAH0_Z_details_wil___details_wil___wil___details_wil___wil___std___std__V__ComPtr_UIMTAThreadPoolEventCallback_Utility_IoT_Microsoft___WRL_Microsoft___std___2__std__QEAA_XZ(&v48);
    }
    while ( (_DWORD)v26 != (_DWORD)v46 );
    std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>>>::_Tidy(&v39);
    if ( v42 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>(
        v42,
        v43);
      std::_Deallocate<16>(v42, ((char *)v44 - (char *)v42) & 0xFFFFFFFFFFFFFFF8uLL);
    }
  }
  catch ( wil::ResultException *v59 )
  {
    v38 = *((_DWORD *)v59 + 8);
  }
  catch ( std::bad_alloc *v62 )
  {
    v38 = -2147024882;
  }
  catch ( std::invalid_argument *v63 )
  {
    v38 = -2147024809;
  }
  catch ( std::range_error *v64 )
  {
    v38 = -2147483637;
  }
  catch ( std::runtime_error *v65 )
  {
    v38 = -2147467259;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0x118,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      v35);
  }
  if ( v38 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x118,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      (const char *)(unsigned int)v38);
  CoUninitialize();
  return (unsigned int)v38;
}

```

## disassembly

```asm
0x18000de50  mov     [rsp+arg_8], rbx
0x18000de55  mov     [rsp+arg_10], rsi
0x18000de5a  push    rdi
0x18000de5b  push    r12
0x18000de5d  push    r13
0x18000de5f  push    r14
0x18000de61  push    r15
0x18000de63  sub     rsp, 530h
0x18000de6a  mov     rax, cs:__security_cookie
0x18000de71  xor     rax, rsp
0x18000de74  mov     [rsp+558h+var_38], rax
0x18000de7c  mov     r15, rcx
0x18000de7f  mov     [rsp+558h+var_4E0], rcx
0x18000de84  xor     edx, edx; dwCoInit
0x18000de86  xor     ecx, ecx; pvReserved
0x18000de88  call    cs:__imp_CoInitializeEx
0x18000de8e  mov     rcx, [rsp+558h]; this
0x18000de96  xor     edi, edi
0x18000de98  test    eax, eax
0x18000de9a  jns     short loc_18000DEB1
0x18000de9c  mov     r9d, eax; char *
0x18000de9f  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000dea6  mov     edx, 0CFh; void *
0x18000deab  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000deb1  mov     [rsp+558h+var_4EF], 1
0x18000deb6  mov     dword ptr [rsp+558h+var_528], edi
0x18000deba  lea     rcx, [rsp+558h+var_508]
0x18000debf  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x18000dec4  nop
0x18000dec5  lea     rcx, [rsp+558h+var_520]
0x18000deca  call    ??0?$vector@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@VCCBTLauncher@ShellExtension@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::ShellExtension::CCBTLauncher>>(void)
0x18000decf  nop
0x18000ded0  mov     rcx, [r15+10h]; this
0x18000ded4  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x18000ded9  lea     rcx, [rsp+558h+var_4D8]
0x18000dee1  call    ??0?$queue@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@@std@@QEAA@XZ; std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>(void)
0x18000dee6  nop
0x18000dee7  mov     rbx, [r15+20h]
0x18000deeb  add     rbx, 0B8h
0x18000def2  mov     rcx, rbx; lpCriticalSection
0x18000def5  call    cs:__imp_EnterCriticalSection
0x18000defb  mov     [rsp+558h+var_4E8], rbx
0x18000df00  mov     rdx, [r15+20h]
0x18000df04  add     rdx, 0E0h
0x18000df0b  lea     rax, [rsp+558h+var_4D8]
0x18000df13  cmp     rdx, rax
0x18000df16  jz      loc_18000DFB5
0x18000df1c  mov     rcx, [rdx]
0x18000df1f  mov     rax, [rsp+558h+var_4D8]
0x18000df27  mov     [rdx], rax
0x18000df2a  mov     [rsp+558h+var_4D8], rcx
0x18000df32  mov     rax, [rdx]
0x18000df35  test    rax, rax
0x18000df38  jz      short loc_18000DF45
0x18000df3a  mov     [rax], rdx
0x18000df3d  mov     rcx, [rsp+558h+var_4D8]
0x18000df45  test    rcx, rcx
0x18000df48  jz      short loc_18000DF55
0x18000df4a  lea     rax, [rsp+558h+var_4D8]
0x18000df52  mov     [rcx], rax
0x18000df55  mov     rcx, [rdx+8]
0x18000df59  mov     rax, [rsp+558h+var_4D0]
0x18000df61  mov     [rdx+8], rax
0x18000df65  mov     [rsp+558h+var_4D0], rcx
0x18000df6d  mov     rcx, [rdx+10h]
0x18000df71  mov     rax, [rsp+558h+var_4C8]
0x18000df79  mov     [rdx+10h], rax
0x18000df7d  mov     [rsp+558h+var_4C8], rcx
0x18000df85  mov     rcx, [rdx+18h]
0x18000df89  mov     rax, [rsp+558h+var_4C0]
0x18000df91  mov     [rdx+18h], rax
0x18000df95  mov     [rsp+558h+var_4C0], rcx
0x18000df9d  mov     rcx, [rdx+20h]
0x18000dfa1  mov     rax, [rsp+558h+var_4B8]
0x18000dfa9  mov     [rdx+20h], rax
0x18000dfad  mov     [rsp+558h+var_4B8], rcx
0x18000dfb5  lea     rcx, [rsp+558h+var_4E8]
0x18000dfba  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000dfbf  cmp     [rsp+558h+var_4B8], rdi
0x18000dfc7  jz      loc_18000E0EF
0x18000dfcd  lea     rcx, [rsp+558h+var_4D8]
0x18000dfd5  call    ?front@?$queue@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@2@@std@@QEAAAEAU?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@2@XZ
0x18000dfda  mov     rbx, rax
0x18000dfdd  mov     rdx, rax
0x18000dfe0  lea     rcx, [rsp+558h+var_490]
0x18000dfe8  call    ??0?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>(std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>> const &)
0x18000dfed  mov     rax, [rbx+18h]
0x18000dff1  mov     [rsp+558h+var_478], rax
0x18000dff9  lea     rcx, [rsp+558h+var_478]
0x18000e001  call    ?InternalAddRef@?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(void)
0x18000e006  nop
0x18000e007  lea     rcx, [rsp+558h+var_4D8]
0x18000e00f  call    ?pop_front@?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@QEAAXXZ; std::deque<std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>::pop_front(void)
0x18000e014  mov     r9, [rsp+558h+var_518]
0x18000e019  mov     rcx, r9
0x18000e01c  sub     rcx, [rsp+558h+var_520]
0x18000e021  sar     rcx, 4
0x18000e025  mov     rax, [rsp+558h+var_4B8]
0x18000e02d  add     rax, 2
0x18000e031  add     rcx, rax
0x18000e034  cmp     rcx, 40h ; '@'
0x18000e038  jbe     short loc_18000E05A
0x18000e03a  mov     rcx, [rsp+558h]; this
0x18000e042  mov     r9d, 8000FFFFh; char *
0x18000e048  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000e04f  mov     edx, 0E7h; void *
0x18000e054  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e05a  mov     rbx, [rsp+558h+var_490]
0x18000e062  cmp     rbx, [rsp+558h+var_488]
0x18000e06a  jnz     short loc_18000E07E
0x18000e06c  lea     rcx, [rsp+558h+var_490]
0x18000e074  call    ??1?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::~pair<std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>(void)
0x18000e079  jmp     loc_18000DFBF
0x18000e07e  cmp     r9, [rsp+558h+var_510]
0x18000e083  jz      short loc_18000E098
0x18000e085  mov     rdx, rbx
0x18000e088  mov     rcx, r9
0x18000e08b  call    ??$_Construct_in_place@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV12@@std@@YAXAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV12@@Z; std::_Construct_in_place<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &>(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x18000e090  add     [rsp+558h+var_518], 10h
0x18000e096  jmp     short loc_18000E0A8
0x18000e098  mov     r8, rbx
0x18000e09b  mov     rdx, r9
0x18000e09e  lea     rcx, [rsp+558h+var_520]
0x18000e0a3  call    ??$_Emplace_reallocate@AEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAV23@AEBV23@@Z; std::vector<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>>::_Emplace_reallocate<wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &>(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> * const,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> const &)
0x18000e0a8  mov     rax, [rsp+558h+var_500]
0x18000e0ad  cmp     rax, [rsp+558h+var_4F8]
0x18000e0b2  jz      short loc_18000E0CC
0x18000e0b4  lea     rdx, [rsp+558h+var_478]
0x18000e0bc  mov     rcx, rax
0x18000e0bf  call    ??$_Construct_in_place@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@AEBV123@@std@@YAXAEAV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@AEBV123@@Z; std::_Construct_in_place<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> const &>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> &,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> const &)
0x18000e0c4  add     [rsp+558h+var_500], 8
0x18000e0ca  jmp     short loc_18000E0E1
0x18000e0cc  lea     r8, [rsp+558h+var_478]
0x18000e0d4  mov     rdx, rax
0x18000e0d7  lea     rcx, [rsp+558h+var_508]
0x18000e0dc  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> const &>(Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> * const,Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback> const &)
0x18000e0e1  add     rbx, 10h
0x18000e0e5  mov     r9, [rsp+558h+var_518]
0x18000e0ea  jmp     loc_18000E062
0x18000e0ef  mov     rbx, [rsp+558h+var_518]
0x18000e0f4  mov     r14, [rsp+558h+var_520]
0x18000e0f9  sub     rbx, r14
0x18000e0fc  sar     rbx, 4
0x18000e100  lea     esi, [rbx+2]
0x18000e103  cmp     esi, 40h ; '@'
0x18000e106  jbe     short loc_18000E128
0x18000e108  mov     rcx, [rsp+558h]; this
0x18000e110  mov     r9d, 8000FFFFh; char *
0x18000e116  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000e11d  mov     edx, 0F3h; void *
0x18000e122  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e128  mov     r12d, 200h
0x18000e12e  mov     r8d, r12d; Size
0x18000e131  xor     edx, edx; Val
0x18000e133  lea     rcx, [rsp+558h+Handles]; void *
0x18000e13b  call    memset_0
0x18000e140  mov     r8d, r12d; Size
0x18000e143  xor     edx, edx; Val
0x18000e145  lea     rcx, [rsp+558h+var_258]; void *
0x18000e14d  call    memset_0
0x18000e152  mov     rdx, rdi
0x18000e155  mov     rcx, rdi
0x18000e158  test    rbx, rbx
0x18000e15b  jz      short loc_18000E1A9
0x18000e15d  mov     r9, [rsp+558h+var_508]
0x18000e162  test    rcx, rcx
0x18000e165  jz      short loc_18000E174
0x18000e167  mov     rax, [r9+rcx*8-8]
0x18000e16c  cmp     [r9+rcx*8], rax
0x18000e170  cmovnz  rdx, rdi
0x18000e174  mov     rax, rcx
0x18000e177  add     rax, rax
0x18000e17a  mov     r8, [r14+rax*8]
0x18000e17e  test    r8, r8
0x18000e181  jz      short loc_18000E188
0x18000e183  mov     rax, [r8]
0x18000e186  jmp     short loc_18000E18B
0x18000e188  mov     rax, rdi
0x18000e18b  mov     [rsp+rcx*8+558h+Handles], rax
0x18000e193  mov     rax, rdx
0x18000e196  inc     rdx
0x18000e199  mov     [rsp+rcx*8+558h+var_258], rax
0x18000e1a1  inc     rcx
0x18000e1a4  cmp     rcx, rbx
0x18000e1a7  jb      short loc_18000E162
0x18000e1a9  mov     ecx, ebx
0x18000e1ab  mov     r15, [rsp+558h+var_4E0]
0x18000e1b0  mov     rax, [r15+10h]
0x18000e1b4  mov     [rsp+rcx*8+558h+Handles], rax
0x18000e1bc  lea     eax, [rsi-1]
0x18000e1bf  mov     dword ptr [rsp+558h+var_4E8], eax
0x18000e1c3  mov     ecx, eax
0x18000e1c5  mov     rax, [r15+8]
0x18000e1c9  mov     [rsp+rcx*8+558h+Handles], rax
0x18000e1d1  mov     [rsp+558h+bAlertable], 1; int
0x18000e1d9  or      r13d, 0FFFFFFFFh
0x18000e1dd  mov     r9d, r13d; dwMilliseconds
0x18000e1e0  xor     r8d, r8d; bWaitAll
0x18000e1e3  lea     rdx, [rsp+558h+Handles]; lpHandles
0x18000e1eb  mov     ecx, esi; nCount
0x18000e1ed  call    cs:__imp_WaitForMultipleObjectsEx
0x18000e1f3  mov     r12d, eax
0x18000e1f6  cmp     eax, r13d
0x18000e1f9  jnz     short loc_18000E20D
0x18000e1fb  mov     rcx, [rsp+558h]; this
0x18000e203  mov     edx, 108h; void *
0x18000e208  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18000e20d  cmp     esi, 2
0x18000e210  jbe     loc_18000E38E
0x18000e216  cmp     r12d, ebx
0x18000e219  jnb     loc_18000E38E
0x18000e21f  mov     r14, r12
0x18000e222  lea     r13, ds:0[r12*8]
0x18000e22a  mov     rax, [rsp+558h+var_508]
0x18000e22f  mov     r15, [rax+r13]
0x18000e233  mov     [rsp+558h+var_498], r15
0x18000e23b  lea     rcx, [rsp+558h+var_498]
0x18000e243  call    ?InternalAddRef@?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(void)
0x18000e248  nop
0x18000e249  mov     rsi, [rsp+558h+var_4E0]
0x18000e24e  mov     rsi, [rsi+20h]
0x18000e252  mov     [rsp+558h+var_4A8], r15
0x18000e25a  lea     rcx, [rsp+558h+var_4A8]
0x18000e262  call    ?InternalAddRef@?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(void)
0x18000e267  mov     rax, [rsp+r13+558h+var_258]
0x18000e26f  mov     [rsp+558h+var_4A0], rax
0x18000e277  lea     rdx, [rsp+558h+var_4A8]
0x18000e27f  lea     rcx, [rsp+558h+var_4B0]
0x18000e287  call    Microsoft__WRL__Details__Make_Microsoft__IoT__Utility__MTAThreadPool__LambdaWorkCallback__lambda_e5e820ed515346ac483c45f56bfacfa7_____lambda_e5e820ed515346ac483c45f56bfacfa7___
0x18000e28c  nop
0x18000e28d  mov     rbx, [rsp+558h+var_4B0]
0x18000e295  test    rbx, rbx
0x18000e298  jz      short loc_18000E2A9
0x18000e29a  mov     rdx, rbx; struct Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *
0x18000e29d  mov     rcx, rsi; this
0x18000e2a0  call    ?QueueWorkItem@MTAThreadPool@Utility@IoT@Microsoft@@QEAAJPEAUIMTAThreadPoolWorkCallback@234@@Z; Microsoft::IoT::Utility::MTAThreadPool::QueueWorkItem(Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback *)
0x18000e2a5  mov     esi, eax
0x18000e2a7  jmp     short loc_18000E2AE
0x18000e2a9  mov     esi, 8007000Eh
0x18000e2ae  test    rbx, rbx
0x18000e2b1  jz      short loc_18000E2CB
0x18000e2b3  mov     [rsp+558h+var_4B0], rdi
0x18000e2bb  mov     rax, [rbx]
0x18000e2be  mov     rcx, rbx
0x18000e2c1  mov     rax, [rax+10h]
0x18000e2c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ca  nop
0x18000e2cb  mov     rcx, [rsp+558h]; this
0x18000e2d3  test    esi, esi
0x18000e2d5  jns     short loc_18000E2EC
0x18000e2d7  mov     r9d, esi; char *
0x18000e2da  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000e2e1  mov     edx, 111h; void *
0x18000e2e6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e2eb  nop
0x18000e2ec  mov     rcx, [rsp+558h+var_4A8]
0x18000e2f4  test    rcx, rcx
0x18000e2f7  jz      short loc_18000E30E
0x18000e2f9  mov     [rsp+558h+var_4A8], rdi
0x18000e301  mov     rax, [rcx]
0x18000e304  mov     rax, [rax+10h]
0x18000e308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e30d  nop
0x18000e30e  shl     r14, 4
0x18000e312  mov     rsi, [rsp+558h+var_520]
0x18000e317  add     rsi, r14
0x18000e31a  mov     r14, [rsp+558h+var_518]
0x18000e31f  lea     rbx, [rsi+10h]
0x18000e323  cmp     rbx, r14
0x18000e326  jz      short loc_18000E34A
0x18000e328  cmp     rsi, rbx
0x18000e32b  jz      short loc_18000E338
0x18000e32d  mov     rdx, rbx
0x18000e330  mov     rcx, rsi
0x18000e333  call    ??4?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::operator=(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>> &&)
0x18000e338  add     rsi, 10h
0x18000e33c  add     rbx, 10h
0x18000e340  cmp     rbx, r14
0x18000e343  jnz     short loc_18000E328
0x18000e345  mov     r14, [rsp+558h+var_518]
0x18000e34a  lea     rcx, [r14-10h]
0x18000e34e  call    ??1?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>(void)
0x18000e353  sub     [rsp+558h+var_518], 10h
0x18000e359  mov     r8, [rsp+558h+var_508]
0x18000e35e  add     r8, r13
0x18000e361  lea     rdx, [rsp+558h+var_470]
0x18000e369  lea     rcx, [rsp+558h+var_508]
0x18000e36e  call    ?erase@?$vector@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@@2@@Z; std::vector<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolEventCallback>>>>)
0x18000e373  nop
0x18000e374  test    r15, r15
0x18000e377  jz      short loc_18000E389
0x18000e379  mov     rax, [r15]
0x18000e37c  mov     rcx, r15
0x18000e37f  mov     rax, [rax+10h]
0x18000e383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e388  nop
0x18000e389  mov     r15, [rsp+558h+var_4E0]
0x18000e38e  lea     rcx, [rsp+558h+var_4D8]
0x18000e396  call    ??1?$deque@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@V?$allocator@U?$pair@V?$vector@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@V?$allocator@V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@std@@@std@@V?$ComPtr@UIMTAThreadPoolEventCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@2@@std@@QEAA@XZ
0x18000e39b  cmp     r12d, dword ptr [rsp+558h+var_4E8]
  ... truncated ...
```
