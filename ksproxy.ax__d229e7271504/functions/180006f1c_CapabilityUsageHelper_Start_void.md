# CapabilityUsageHelper::Start(void)

- ea: `0x180006f1c`
- end: `0x180007046`
- name: `?Start@CapabilityUsageHelper@@QEAAJXZ`
- size: `298`
- prototype: `__int64 __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c110`

## callees

- `0x180006de0`
- `0x180006f1c`
- `0x1800081e4`
- `0x180016344`
- `0x18001b674`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006fed`
- `KERNEL32!GetLastError` at `0x180006fed`
- `KERNEL32!CreateThread` at `0x180006fc8`
- `KERNEL32!CreateThread` at `0x180006fc8`
- `KERNEL32!LeaveCriticalSection` at `0x180006f7c`
- `KERNEL32!LeaveCriticalSection` at `0x180006f7c`
- `KERNEL32!EnterCriticalSection` at `0x180006f35`
- `KERNEL32!EnterCriticalSection` at `0x180006f35`

## pseudocode

```c
__int64 __fastcall CapabilityUsageHelper::Start(LPVOID *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v5; // ebx
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  HANDLE Thread; // rax
  signed int LastError; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+40h] [rbp+8h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)(this + 4);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 4));
  v12 = v1;
  if ( (char *)this[3] - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(this + 2);
    v5 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      Thread = CreateThread(0, 0, CapabilityUsageHelper::StartInternal, this[2], 0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        this + 3,
        Thread);
      if ( (((unsigned __int64)this[3] + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      {
        v5 = 0;
        goto LABEL_14;
      }
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (v5 & 0x80000000) == 0 )
        goto LABEL_14;
      v6 = v5;
      v7 = 38;
    }
    else
    {
      v6 = (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
      v7 = 35;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityusagehelper.cpp",
      (const char *)v6,
      dwCreationFlags);
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v12);
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F,
    (unsigned int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityusagehelper.cpp",
    (const char *)0x8000FFFFLL,
    dwCreationFlags);
  if ( v1 )
    LeaveCriticalSection(v1);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180006f1c  mov     [rsp+arg_8], rbx
0x180006f21  mov     [rsp+arg_10], rsi
0x180006f26  push    rdi
0x180006f27  sub     rsp, 30h
0x180006f2b  lea     rbx, [rcx+20h]
0x180006f2f  mov     rdi, rcx
0x180006f32  mov     rcx, rbx; lpCriticalSection
0x180006f35  call    cs:__imp_EnterCriticalSection
0x180006f3c  nop     dword ptr [rax+rax+00h]
0x180006f41  lea     rsi, [rdi+18h]
0x180006f45  mov     [rsp+38h+arg_0], rbx
0x180006f4a  mov     rax, [rsi]
0x180006f4d  dec     rax
0x180006f50  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180006f54  ja      short loc_180006F8F
0x180006f56  mov     rcx, [rsp+38h]; this
0x180006f5b  lea     r8, aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180006f62  mov     edi, 8000FFFFh
0x180006f67  mov     edx, 1Fh; void *
0x180006f6c  mov     r9d, edi; char *
0x180006f6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f74  test    rbx, rbx
0x180006f77  jz      short loc_180006F88
0x180006f79  mov     rcx, rbx; lpCriticalSection
0x180006f7c  call    cs:__imp_LeaveCriticalSection
0x180006f83  nop     dword ptr [rax+rax+00h]
0x180006f88  mov     eax, edi
0x180006f8a  jmp     loc_180007035
0x180006f8f  lea     rcx, [rdi+10h]
0x180006f93  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180006f98  mov     ebx, eax
0x180006f9a  test    eax, eax
0x180006f9c  jns     short loc_180006FA8
0x180006f9e  mov     r9d, eax
0x180006fa1  mov     edx, 23h ; '#'
0x180006fa6  jmp     short loc_180007014
0x180006fa8  mov     r9, [rdi+10h]; lpParameter
0x180006fac  lea     r8, ?StartInternal@CapabilityUsageHelper@@CAKPEAX@Z; lpStartAddress
0x180006fb3  mov     [rsp+38h+lpThreadId], 0; lpThreadId
0x180006fbc  xor     edx, edx; dwStackSize
0x180006fbe  xor     ecx, ecx; lpThreadAttributes
0x180006fc0  mov     [rsp+38h+dwCreationFlags], 0; int
0x180006fc8  call    cs:__imp_CreateThread
0x180006fcf  nop     dword ptr [rax+rax+00h]
0x180006fd4  mov     rdx, rax
0x180006fd7  mov     rcx, rsi
0x180006fda  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180006fdf  mov     rax, [rsi]
0x180006fe2  inc     rax
0x180006fe5  test    rax, 0FFFFFFFFFFFFFFFEh
0x180006feb  jnz     short loc_180007027
0x180006fed  call    cs:__imp_GetLastError
0x180006ff4  nop     dword ptr [rax+rax+00h]
0x180006ff9  mov     ebx, eax
0x180006ffb  test    eax, eax
0x180006ffd  jle     short loc_180007008
0x180006fff  movzx   ebx, ax
0x180007002  or      ebx, 80070000h
0x180007008  test    ebx, ebx
0x18000700a  jns     short loc_180007029
0x18000700c  mov     r9d, ebx; char *
0x18000700f  mov     edx, 26h ; '&'; void *
0x180007014  mov     rcx, [rsp+38h]; this
0x180007019  lea     r8, aMultimediaDsho; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180007020  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007025  jmp     short loc_180007029
0x180007027  xor     ebx, ebx
0x180007029  lea     rcx, [rsp+38h+arg_0]
0x18000702e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180007033  mov     eax, ebx
0x180007035  mov     rbx, [rsp+38h+arg_8]
0x18000703a  mov     rsi, [rsp+38h+arg_10]
0x18000703f  add     rsp, 30h
0x180007043  pop     rdi
0x180007044  retn
```
