# CapabilityUsageHelper::StartInternal(void *)

- ea: `0x180007eb0`
- end: `0x1800081de`
- name: `?StartInternal@CapabilityUsageHelper@@CAKPEAX@Z`
- size: `814`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007b14`
- `0x180007eb0`
- `0x1800081e4`
- `0x18001f620`
- `0x180045010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x180007f85`
- `KERNEL32!RaiseException` at `0x180008034`
- `KERNEL32!RaiseException` at `0x1800081d1`
- `KERNEL32!RaiseException` at `0x180007f85`
- `KERNEL32!RaiseException` at `0x180008034`
- `KERNEL32!RaiseException` at `0x1800081d1`
- `KERNEL32!GetCurrentProcessId` at `0x180008089`
- `KERNEL32!GetCurrentProcessId` at `0x180008089`
- `KERNEL32!WaitForSingleObject` at `0x18000812e`
- `KERNEL32!WaitForSingleObject` at `0x18000812e`
- `ole32!CoUninitialize` at `0x180008183`
- `ole32!CoUninitialize` at `0x1800081af`
- `ole32!CoUninitialize` at `0x180008183`
- `ole32!CoUninitialize` at `0x1800081af`
- `ole32!CoInitializeEx` at `0x180007ed5`
- `ole32!CoInitializeEx` at `0x180007ed5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180007fa1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180007fa1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007f69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008018`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180007f69`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180008018`

## string_xrefs

- `0x180007f62`: `Windows.Internal.CapabilityAccess.Management.CapabilityUsage`

## pseudocode

```c
__int64 __fastcall CapabilityUsageHelper::StartInternal(PVOID Parameter)
{
  HRESULT v2; // eax
  unsigned int v3; // ebx
  signed int v5; // eax
  int ActivationFactory; // eax
  __int64 v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rsi
  unsigned __int64 v10; // rdx
  signed int v11; // eax
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64, _QWORD, _QWORD, __int64 *); // rsi
  DWORD CurrentProcessId; // eax
  int v16; // eax
  int v17; // [rsp+20h] [rbp-58h]
  __int64 v18; // [rsp+30h] [rbp-48h] BYREF
  __int64 *v19; // [rsp+38h] [rbp-40h] BYREF
  __int64 *v20; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  HSTRING string; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v2 = CoInitializeEx(0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x59,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityusagehelper.cpp",
      (const char *)(unsigned int)v2,
      v17);
    return v3;
  }
  v20 = 0;
  v19 = 0;
  v18 = 0;
  if ( !Parameter )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityusagehelper.cpp",
      (const char *)0x80070057LL,
      v17);
    v3 = -2147024809;
LABEL_30:
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v18);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v19);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v20);
LABEL_31:
    CoUninitialize();
    return v3;
  }
  string = 0;
  v5 = WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.Management.CapabilityUsage",
         0x3Cu,
         &hstringHeader,
         &string);
  if ( v5 < 0 )
  {
    RaiseException(v5, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_42947746_4ea0_48c2_9274_062ed61f8daa, &v20);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = 107;
LABEL_29:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityusagehelper.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v17);
    goto LABEL_30;
  }
  v8 = (__int64)v20;
  v9 = *v20;
  v19 = 0;
  v10 = -1;
  string = 0;
  do
    ++v10;
  while ( c_szCapabilityWebcam[v10] );
  if ( v10 > 0xFFFFFFFF || (int)v10 + 1 < (unsigned int)v10 )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    __debugbreak();
    JUMPOUT(0x1800081DELL);
  }
  v11 = WindowsCreateStringReference(c_szCapabilityWebcam, v10, &hstringHeader, &string);
  if ( v11 < 0 )
  {
    RaiseException(v11, 1u, 0, 0);
    __debugbreak();
  }
  ActivationFactory = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64 **))(v9 + 48))(v8, string, &v19);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = 109;
    goto LABEL_29;
  }
  v12 = (__int64)v19;
  v13 = *v19;
  v18 = 0;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(v13 + 48);
  CurrentProcessId = GetCurrentProcessId();
  ActivationFactory = v14(v12, CurrentProcessId, 0, &v18);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = 112;
    goto LABEL_29;
  }
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 48LL))(v18);
  v3 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x73,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityusagehelper.cpp",
      (const char *)(unsigned int)v16,
      v17);
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( v19 )
      (*(void (__fastcall **)(__int64 *))(*v19 + 16))(v19);
    if ( v20 )
      (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    goto LABEL_31;
  }
  WaitForSingleObject(Parameter, 0xFFFFFFFF);
  ActivationFactory = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 56LL))(v18);
  v3 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    v7 = 121;
    goto LABEL_29;
  }
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v18);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v19);
  wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v20);
  CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180007eb0  push    rbp
0x180007eb2  push    rbx
0x180007eb3  push    rsi
0x180007eb4  push    rdi
0x180007eb5  push    r14
0x180007eb7  push    r15
0x180007eb9  mov     rbp, rsp
0x180007ebc  sub     rsp, 78h
0x180007ec0  mov     rax, cs:__security_cookie
0x180007ec7  xor     rax, rsp
0x180007eca  mov     [rbp+var_10], rax
0x180007ece  mov     rdi, rcx
0x180007ed1  xor     edx, edx; dwCoInit
0x180007ed3  xor     ecx, ecx; pvReserved
0x180007ed5  call    cs:__imp_CoInitializeEx
0x180007edc  nop     dword ptr [rax+rax+00h]
0x180007ee1  xor     r14d, r14d
0x180007ee4  mov     ebx, eax
0x180007ee6  test    eax, eax
0x180007ee8  jns     short loc_180007F1D
0x180007eea  mov     rcx, [rbp+30h]; this
0x180007eee  lea     r8, aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180007ef5  mov     r9d, eax; char *
0x180007ef8  lea     edx, [r14+59h]; void *
0x180007efc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f01  mov     eax, ebx
0x180007f03  mov     rcx, [rbp+var_10]
0x180007f07  xor     rcx, rsp; StackCookie
0x180007f0a  call    __security_check_cookie
0x180007f0f  add     rsp, 78h
0x180007f13  pop     r15
0x180007f15  pop     r14
0x180007f17  pop     rdi
0x180007f18  pop     rsi
0x180007f19  pop     rbx
0x180007f1a  pop     rbp
0x180007f1b  retn
0x180007f1d  mov     [rbp+var_38], r14
0x180007f21  mov     [rbp+var_40], r14
0x180007f25  mov     [rbp+var_48], r14
0x180007f29  test    rdi, rdi
0x180007f2c  jnz     short loc_180007F51
0x180007f2e  mov     rcx, [rbp+30h]; this
0x180007f32  lea     r8, aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180007f39  mov     r9d, 80070057h; char *
0x180007f3f  lea     edx, [rdi+64h]; void *
0x180007f42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f47  mov     ebx, 80070057h
0x180007f4c  jmp     loc_180008168
0x180007f51  lea     r9, [rbp+string]; string
0x180007f55  mov     [rbp+string], r14
0x180007f59  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180007f5d  mov     edx, 3Ch ; '<'; length
0x180007f62  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityUsage@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x180007f69  call    cs:__imp_WindowsCreateStringReference
0x180007f70  nop     dword ptr [rax+rax+00h]
0x180007f75  test    eax, eax
0x180007f77  jns     short loc_180007F92
0x180007f79  xor     r9d, r9d; lpArguments
0x180007f7c  xor     r8d, r8d; nNumberOfArguments
0x180007f7f  mov     ecx, eax; dwExceptionCode
0x180007f81  lea     edx, [r9+1]; dwExceptionFlags
0x180007f85  call    cs:__imp_RaiseException
0x180007f8c  nop     dword ptr [rax+rax+00h]
0x180007f91  int     3; Trap to Debugger
0x180007f92  mov     rcx, [rbp+string]
0x180007f96  lea     r8, [rbp+var_38]
0x180007f9a  lea     rdx, _GUID_42947746_4ea0_48c2_9274_062ed61f8daa
0x180007fa1  call    cs:__imp_RoGetActivationFactory
0x180007fa8  nop     dword ptr [rax+rax+00h]
0x180007fad  mov     ebx, eax
0x180007faf  test    eax, eax
0x180007fb1  jns     short loc_180007FBD
0x180007fb3  mov     edx, 6Bh ; 'k'
0x180007fb8  jmp     loc_180008155
0x180007fbd  mov     rcx, [rbp+var_40]
0x180007fc1  mov     rbx, [rbp+var_38]
0x180007fc5  mov     rsi, [rbx]
0x180007fc8  mov     [rbp+var_40], r14
0x180007fcc  test    rcx, rcx
0x180007fcf  jz      short loc_180007FDD
0x180007fd1  mov     rax, [rcx]
0x180007fd4  mov     rax, [rax+10h]
0x180007fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fdd  mov     rcx, cs:?c_szCapabilityWebcam@@3QEBGEB; sourceString
0x180007fe4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180007fe8  mov     [rbp+string], r14
0x180007fec  inc     rdx; length
0x180007fef  cmp     [rcx+rdx*2], r14w
0x180007ff4  jnz     short loc_180007FEC
0x180007ff6  mov     r15d, 0FFFFFFFFh
0x180007ffc  cmp     rdx, r15
0x180007fff  ja      loc_1800081C2
0x180008005  lea     eax, [rdx+1]
0x180008008  cmp     eax, edx
0x18000800a  jb      loc_1800081C2
0x180008010  lea     r9, [rbp+string]; string
0x180008014  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180008018  call    cs:__imp_WindowsCreateStringReference
0x18000801f  nop     dword ptr [rax+rax+00h]
0x180008024  test    eax, eax
0x180008026  jns     short loc_180008041
0x180008028  xor     r9d, r9d; lpArguments
0x18000802b  xor     r8d, r8d; nNumberOfArguments
0x18000802e  mov     ecx, eax; dwExceptionCode
0x180008030  lea     edx, [r9+1]; dwExceptionFlags
0x180008034  call    cs:__imp_RaiseException
0x18000803b  nop     dword ptr [rax+rax+00h]
0x180008040  int     3; Trap to Debugger
0x180008041  mov     rdx, [rbp+string]
0x180008045  lea     r8, [rbp+var_40]
0x180008049  mov     rax, [rsi+30h]
0x18000804d  mov     rcx, rbx
0x180008050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008055  mov     ebx, eax
0x180008057  test    eax, eax
0x180008059  jns     short loc_180008065
0x18000805b  mov     edx, 6Dh ; 'm'
0x180008060  jmp     loc_180008155
0x180008065  mov     rcx, [rbp+var_48]
0x180008069  mov     rbx, [rbp+var_40]
0x18000806d  mov     rax, [rbx]
0x180008070  mov     [rbp+var_48], r14
0x180008074  mov     rsi, [rax+30h]
0x180008078  test    rcx, rcx
0x18000807b  jz      short loc_180008089
0x18000807d  mov     rax, [rcx]
0x180008080  mov     rax, [rax+10h]
0x180008084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008089  call    cs:__imp_GetCurrentProcessId
0x180008090  nop     dword ptr [rax+rax+00h]
0x180008095  lea     r9, [rbp+var_48]
0x180008099  xor     r8d, r8d
0x18000809c  mov     edx, eax
0x18000809e  mov     rcx, rbx
0x1800080a1  mov     rax, rsi
0x1800080a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a9  mov     ebx, eax
0x1800080ab  test    eax, eax
0x1800080ad  jns     short loc_1800080B9
0x1800080af  mov     edx, 70h ; 'p'
0x1800080b4  jmp     loc_180008155
0x1800080b9  mov     rcx, [rbp+var_48]
0x1800080bd  mov     rax, [rcx]
0x1800080c0  mov     rax, [rax+30h]
0x1800080c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c9  mov     ebx, eax
0x1800080cb  test    eax, eax
0x1800080cd  jns     short loc_180008128
0x1800080cf  mov     rcx, [rbp+30h]; this
0x1800080d3  lea     r8, aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1800080da  mov     r9d, eax; char *
0x1800080dd  mov     edx, 73h ; 's'; void *
0x1800080e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800080e7  mov     rcx, [rbp+var_48]
0x1800080eb  test    rcx, rcx
0x1800080ee  jz      short loc_1800080FC
0x1800080f0  mov     rax, [rcx]
0x1800080f3  mov     rax, [rax+10h]
0x1800080f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080fc  mov     rcx, [rbp+var_40]
0x180008100  test    rcx, rcx
0x180008103  jz      short loc_180008111
0x180008105  mov     rax, [rcx]
0x180008108  mov     rax, [rax+10h]
0x18000810c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008111  mov     rcx, [rbp+var_38]
0x180008115  test    rcx, rcx
0x180008118  jz      short loc_180008183
0x18000811a  mov     rax, [rcx]
0x18000811d  mov     rax, [rax+10h]
0x180008121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008126  jmp     short loc_180008183
0x180008128  mov     edx, r15d; dwMilliseconds
0x18000812b  mov     rcx, rdi; hHandle
0x18000812e  call    cs:__imp_WaitForSingleObject
0x180008135  nop     dword ptr [rax+rax+00h]
0x18000813a  mov     rcx, [rbp+var_48]
0x18000813e  mov     rax, [rcx]
0x180008141  mov     rax, [rax+38h]
0x180008145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000814a  mov     ebx, eax
0x18000814c  test    eax, eax
0x18000814e  jns     short loc_180008194
0x180008150  mov     edx, 79h ; 'y'; void *
0x180008155  mov     rcx, [rbp+30h]; this
0x180008159  lea     r8, aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180008160  mov     r9d, eax; char *
0x180008163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008168  lea     rcx, [rbp+var_48]
0x18000816c  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180008171  lea     rcx, [rbp+var_40]
0x180008175  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18000817a  lea     rcx, [rbp+var_38]
0x18000817e  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180008183  call    cs:__imp_CoUninitialize
0x18000818a  nop     dword ptr [rax+rax+00h]
0x18000818f  jmp     loc_180007F01
0x180008194  lea     rcx, [rbp+var_48]
0x180008198  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18000819d  lea     rcx, [rbp+var_40]
0x1800081a1  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x1800081a6  lea     rcx, [rbp+var_38]
0x1800081aa  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x1800081af  call    cs:__imp_CoUninitialize
0x1800081b6  nop     dword ptr [rax+rax+00h]
0x1800081bb  xor     eax, eax
0x1800081bd  jmp     loc_180007F03
0x1800081c2  xor     r9d, r9d; lpArguments
0x1800081c5  xor     r8d, r8d; nNumberOfArguments
0x1800081c8  mov     ecx, 80070216h; dwExceptionCode
0x1800081cd  lea     edx, [r9+1]; dwExceptionFlags
0x1800081d1  call    cs:__imp_RaiseException
0x1800081d8  nop     dword ptr [rax+rax+00h]
0x1800081dd  int     3; Trap to Debugger
```
