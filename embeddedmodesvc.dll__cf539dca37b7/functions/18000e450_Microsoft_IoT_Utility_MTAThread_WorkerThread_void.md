# Microsoft::IoT::Utility::MTAThread::WorkerThread(void)

- ea: `0x18000e450`
- end: `0x18000e686`
- name: `?WorkerThread@MTAThread@Utility@IoT@Microsoft@@MEAAJXZ`
- size: `566`
- prototype: `__int64 __fastcall(Microsoft::IoT::Utility::MTAThread *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180008358`
- `0x180008378`
- `0x18000a658`
- `0x18000aa40`
- `0x18000d410`
- `0x18000d7c8`
- `0x18000d7ec`
- `0x18000dc84`
- `0x18000dcb4`
- `0x18000e450`
- `0x18000eb34`
- `0x18000eb84`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e4c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e4c1`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e604`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18000e604`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e464`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000e464`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e668`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000e668`

## string_xrefs

- `0x18000e479`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`
- `0x18000e656`: `onecoreuap\shell\embedded\shell\iotshellhostext\iotshellcbt\mtathreadpool.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::IoT::Utility::MTAThread::WorkerThread(Microsoft::IoT::Utility::MTAThread *this)
{
  HRESULT v2; // eax
  void *v3; // rdx
  struct _RTL_CRITICAL_SECTION *v4; // rbx
  __int64 v5; // rdx
  _QWORD *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  void *v11; // rdx
  wil::details *v12; // rcx
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  DWORD v14; // ebx
  unsigned int v15; // r8d
  const char *v16; // r9
  const char *v17; // r9
  BOOL bAlertable; // [rsp+20h] [rbp-78h]
  wil::ResultException *v20; // [rsp+30h] [rbp-68h] BYREF
  HANDLE Handles[2]; // [rsp+38h] [rbp-60h] BYREF
  _QWORD *v22; // [rsp+48h] [rbp-50h] BYREF
  __int64 v23; // [rsp+50h] [rbp-48h]
  __int64 v24; // [rsp+58h] [rbp-40h]
  __int64 v25; // [rsp+60h] [rbp-38h]
  __int64 v26; // [rsp+68h] [rbp-30h]
  std::bad_alloc *v27; // [rsp+70h] [rbp-28h] BYREF
  std::invalid_argument *v28; // [rsp+78h] [rbp-20h] BYREF
  std::range_error *v29; // [rsp+80h] [rbp-18h] BYREF
  std::runtime_error *v30; // [rsp+88h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  int v32; // [rsp+B0h] [rbp+18h]
  struct _RTL_CRITICAL_SECTION *v33; // [rsp+B8h] [rbp+20h] BYREF

  v2 = CoInitializeEx(0, 0);
  if ( v2 < 0 )
    wil::details::in1diag3::FailFast_Hr(
      retaddr,
      (void *)0xAB,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      (const char *)(unsigned int)v2,
      bAlertable);
  v32 = 0;
  try
  {
    do
    {
      wil::details::ResetEvent(*((wil::details **)this + 2), v3);
      _InterlockedIncrement((volatile signed __int32 *)this + 10);
      std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>(&v22);
      v4 = (struct _RTL_CRITICAL_SECTION *)(*((_QWORD *)this + 4) + 104LL);
      EnterCriticalSection(v4);
      v33 = v4;
      v5 = *((_QWORD *)this + 4) + 144LL;
      if ( (_QWORD **)v5 != &v22 )
      {
        v6 = *(_QWORD **)v5;
        *(_QWORD *)v5 = v22;
        v22 = v6;
        if ( *(_QWORD *)v5 )
        {
          **(_QWORD **)v5 = v5;
          v6 = v22;
        }
        if ( v6 )
          *v6 = &v22;
        v7 = *(_QWORD *)(v5 + 8);
        *(_QWORD *)(v5 + 8) = v23;
        v23 = v7;
        v8 = *(_QWORD *)(v5 + 16);
        *(_QWORD *)(v5 + 16) = v24;
        v24 = v8;
        v9 = *(_QWORD *)(v5 + 24);
        *(_QWORD *)(v5 + 24) = v25;
        v25 = v9;
        v10 = *(_QWORD *)(v5 + 32);
        *(_QWORD *)(v5 + 32) = v26;
        v26 = v10;
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v33);
      v12 = (wil::details *)**((_QWORD **)this + 4);
      if ( v12 )
        v12 = *(wil::details **)v12;
      wil::details::SetEvent(v12, v11);
      while ( v26 )
      {
        v13 = *(struct _RTL_CRITICAL_SECTION **)std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::front(&v22);
        v33 = v13;
        Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(&v33);
        std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::pop_front(&v22);
        ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v13->DebugInfo->ProcessLocksList.Blink)(v13);
        if ( v13 )
          ((void (__fastcall *)(struct _RTL_CRITICAL_SECTION *))v13->DebugInfo->ProcessLocksList.Flink)(v13);
      }
      _InterlockedDecrement((volatile signed __int32 *)this + 10);
      Handles[0] = *((HANDLE *)this + 2);
      Handles[1] = *((HANDLE *)this + 1);
      v14 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 1);
      if ( v14 == -1 )
        wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0xC7, v15, v16);
      std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::~deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>(&v22);
    }
    while ( v14 != 1 );
  }
  catch ( wil::ResultException *v20 )
  {
    v32 = *((_DWORD *)v20 + 8);
  }
  catch ( std::bad_alloc *v27 )
  {
    v32 = -2147024882;
  }
  catch ( std::invalid_argument *v28 )
  {
    v32 = -2147024809;
  }
  catch ( std::range_error *v29 )
  {
    v32 = -2147483637;
  }
  catch ( std::runtime_error *v30 )
  {
    v32 = -2147467259;
  }
  catch ( ... )
  {
    wil::details::in1diag3::FailFast_CaughtException(
      retaddr,
      (void *)0xCA,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      v17);
  }
  if ( v32 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xCA,
      (int)"onecoreuap\\shell\\embedded\\shell\\iotshellhostext\\iotshellcbt\\mtathreadpool.cpp",
      (const char *)(unsigned int)v32);
  CoUninitialize();
  return (unsigned int)v32;
}

```

## disassembly

```asm
0x18000e450  mov     [rsp+arg_0], rbx
0x18000e455  push    rdi
0x18000e456  sub     rsp, 90h
0x18000e45d  mov     rdi, rcx
0x18000e460  xor     edx, edx; dwCoInit
0x18000e462  xor     ecx, ecx; pvReserved
0x18000e464  call    cs:__imp_CoInitializeEx
0x18000e46a  mov     rcx, [rsp+98h]; this
0x18000e472  test    eax, eax
0x18000e474  jns     short loc_18000E48B
0x18000e476  mov     r9d, eax; char *
0x18000e479  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000e480  mov     edx, 0ABh; void *
0x18000e485  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x18000e48b  mov     [rsp+98h+arg_9], 1
0x18000e493  mov     dword ptr [rsp+98h+arg_10], 0
0x18000e49e  mov     rcx, [rdi+10h]; this
0x18000e4a2  call    ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
0x18000e4a7  lock inc dword ptr [rdi+28h]
0x18000e4ab  lea     rcx, [rsp+98h+var_50]
0x18000e4b0  call    ??0?$queue@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@@std@@QEAA@XZ; std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>,std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>>(void)
0x18000e4b5  nop
0x18000e4b6  mov     rbx, [rdi+20h]
0x18000e4ba  add     rbx, 68h ; 'h'
0x18000e4be  mov     rcx, rbx; lpCriticalSection
0x18000e4c1  call    cs:__imp_EnterCriticalSection
0x18000e4c7  mov     [rsp+98h+arg_18], rbx
0x18000e4cf  mov     rdx, [rdi+20h]
0x18000e4d3  add     rdx, 90h
0x18000e4da  lea     rax, [rsp+98h+var_50]
0x18000e4df  cmp     rdx, rax
0x18000e4e2  jz      short loc_18000E559
0x18000e4e4  mov     rcx, [rdx]
0x18000e4e7  mov     rax, [rsp+98h+var_50]
0x18000e4ec  mov     [rdx], rax
0x18000e4ef  mov     [rsp+98h+var_50], rcx
0x18000e4f4  mov     rax, [rdx]
0x18000e4f7  test    rax, rax
0x18000e4fa  jz      short loc_18000E504
0x18000e4fc  mov     [rax], rdx
0x18000e4ff  mov     rcx, [rsp+98h+var_50]
0x18000e504  test    rcx, rcx
0x18000e507  jz      short loc_18000E511
0x18000e509  lea     rax, [rsp+98h+var_50]
0x18000e50e  mov     [rcx], rax
0x18000e511  mov     rcx, [rdx+8]
0x18000e515  mov     rax, [rsp+98h+var_48]
0x18000e51a  mov     [rdx+8], rax
0x18000e51e  mov     [rsp+98h+var_48], rcx
0x18000e523  mov     rcx, [rdx+10h]
0x18000e527  mov     rax, [rsp+98h+var_40]
0x18000e52c  mov     [rdx+10h], rax
0x18000e530  mov     [rsp+98h+var_40], rcx
0x18000e535  mov     rcx, [rdx+18h]
0x18000e539  mov     rax, [rsp+98h+var_38]
0x18000e53e  mov     [rdx+18h], rax
0x18000e542  mov     [rsp+98h+var_38], rcx
0x18000e547  mov     rcx, [rdx+20h]
0x18000e54b  mov     rax, [rsp+98h+var_30]
0x18000e550  mov     [rdx+20h], rax
0x18000e554  mov     [rsp+98h+var_30], rcx
0x18000e559  lea     rcx, [rsp+98h+arg_18]
0x18000e561  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18000e566  mov     rax, [rdi+20h]
0x18000e56a  mov     rcx, [rax]
0x18000e56d  test    rcx, rcx
0x18000e570  jz      short loc_18000E575
0x18000e572  mov     rcx, [rcx]; this
0x18000e575  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x18000e57a  cmp     [rsp+98h+var_30], 0
0x18000e580  jz      short loc_18000E5D6
0x18000e582  lea     rcx, [rsp+98h+var_50]
0x18000e587  call    ?front@?$queue@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@@std@@QEAAAEAV?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@XZ; std::queue<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::front(void)
0x18000e58c  mov     rbx, [rax]
0x18000e58f  mov     [rsp+98h+arg_18], rbx
0x18000e597  lea     rcx, [rsp+98h+arg_18]
0x18000e59f  call    ?InternalAddRef@?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>::InternalAddRef(void)
0x18000e5a4  nop
0x18000e5a5  lea     rcx, [rsp+98h+var_50]
0x18000e5aa  call    ?pop_front@?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAAXXZ; std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::pop_front(void)
0x18000e5af  mov     rax, [rbx]
0x18000e5b2  mov     rcx, rbx
0x18000e5b5  mov     rax, [rax+18h]
0x18000e5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5be  nop
0x18000e5bf  test    rbx, rbx
0x18000e5c2  jz      short loc_18000E5D4
0x18000e5c4  mov     rax, [rbx]
0x18000e5c7  mov     rcx, rbx
0x18000e5ca  mov     rax, [rax+10h]
0x18000e5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5d3  nop
0x18000e5d4  jmp     short loc_18000E57A
0x18000e5d6  lock dec dword ptr [rdi+28h]
0x18000e5da  mov     rax, [rdi+10h]
0x18000e5de  mov     [rsp+98h+Handles], rax
0x18000e5e3  mov     rax, [rdi+8]
0x18000e5e7  mov     [rsp+98h+var_58], rax
0x18000e5ec  mov     [rsp+98h+bAlertable], 1; int
0x18000e5f4  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000e5f8  xor     r8d, r8d; bWaitAll
0x18000e5fb  lea     rdx, [rsp+98h+Handles]; lpHandles
0x18000e600  lea     ecx, [r8+2]; nCount
0x18000e604  call    cs:__imp_WaitForMultipleObjectsEx
0x18000e60a  mov     ebx, eax
0x18000e60c  cmp     eax, 0FFFFFFFFh
0x18000e60f  jnz     short loc_18000E624
0x18000e611  mov     rcx, [rsp+98h]; this
0x18000e619  mov     edx, 0C7h; void *
0x18000e61e  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18000e623  nop
0x18000e624  lea     rcx, [rsp+98h+var_50]
0x18000e629  call    ??1?$deque@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMTAThreadPoolWorkCallback@Utility@IoT@Microsoft@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ; std::deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>::~deque<Microsoft::WRL::ComPtr<Microsoft::IoT::Utility::IMTAThreadPoolWorkCallback>>(void)
0x18000e62e  cmp     ebx, 1
0x18000e631  jnz     loc_18000E49E
0x18000e637  jmp     short loc_18000E641
0x18000e639  jmp     short loc_18000E641
0x18000e63b  jmp     short loc_18000E641
0x18000e63d  jmp     short loc_18000E641
0x18000e63f  jmp     short $+2
0x18000e641  mov     rcx, [rsp+98h]; this
0x18000e649  mov     r9d, dword ptr [rsp+98h+arg_10]; char *
0x18000e651  test    r9d, r9d
0x18000e654  jns     short loc_18000E668
0x18000e656  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\embedded\\shell\\iot"...
0x18000e65d  mov     edx, 0CAh; void *
0x18000e662  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e667  nop
0x18000e668  call    cs:__imp_CoUninitialize
0x18000e66e  mov     eax, dword ptr [rsp+98h+arg_10]
0x18000e675  mov     rbx, [rsp+98h+arg_0]
0x18000e67d  add     rsp, 90h
0x18000e684  pop     rdi
0x18000e685  retn
```
