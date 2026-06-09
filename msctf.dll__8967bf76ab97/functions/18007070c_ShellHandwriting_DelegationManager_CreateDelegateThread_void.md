# ShellHandwriting::DelegationManager::CreateDelegateThread(void)

- ea: `0x18007070c`
- end: `0x1800708c8`
- name: `?CreateDelegateThread@DelegationManager@ShellHandwriting@@AEAAJXZ`
- size: `444`
- prototype: `__int64 __fastcall(ShellHandwriting::DelegationManager *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007065c`

## callees

- `0x18007070c`
- `0x1800708d0`
- `0x180070924`
- `0x180079854`
- `0x18008b4b4`
- `0x180092614`
- `0x180094460`
- `0x1800fe9f8`
- `0x180100240`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180070845`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180070845`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18007080b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18007080b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007079c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18007079c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007076b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007076b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800707ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800707ca`
- `USER32!GetThreadDesktop` at `0x180070773`
- `USER32!GetThreadDesktop` at `0x180070773`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180070802`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x180070802`

## string_xrefs

- `0x1800707fb`: `ShellHandwriting Delegate Thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ShellHandwriting::DelegationManager::CreateDelegateThread(ShellHandwriting::DelegationManager *this)
{
  HANDLE *v2; // rsi
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // edi
  __int64 v4; // rdx
  DWORD CurrentThreadId; // eax
  char *Thread; // rcx
  const char *v7; // r9
  HANDLE *v8; // rdi
  __int64 v9; // rdx
  DWORD v11; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-38h]
  char v13; // [rsp+30h] [rbp-28h] BYREF
  HANDLE Handles[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = (HANDLE *)((char *)this + 32);
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 32);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v4 = 391;
    goto LABEL_3;
  }
  event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z((char *)this + 40);
  if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z < 0 )
  {
    v4 = 392;
    goto LABEL_3;
  }
  if ( !*((_QWORD *)this + 1) )
  {
    CurrentThreadId = GetCurrentThreadId();
    *((_QWORD *)this + 1) = GetThreadDesktop(CurrentThreadId);
  }
  Thread = (char *)CreateThread(0, 0, ShellHandwriting::DelegationManager::s_ThreadProc, this, 4u, (LPDWORD)this + 5);
  v8 = (HANDLE *)((char *)this + 48);
  if ( (char *)this + 48 == &v13 )
  {
    if ( (unsigned __int64)(Thread - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(Thread);
  }
  else
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      (char *)this + 48,
      Thread);
  }
  if ( (((unsigned __int64)*v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v9 = 408;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\delegation\\shellhandwritingdelegation.cpp",
             v7);
  }
  SetThreadDescription(*v8, L"ShellHandwriting Delegate Thread");
  if ( ResumeThread(*v8) == -1 )
  {
    v9 = 414;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v9,
             (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\delegation\\shellhandwritingdelegation.cpp",
             v7);
  }
  Handles[0] = *v2;
  Handles[1] = *v8;
  v11 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
  switch ( v11 )
  {
    case 0u:
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = 0;
      goto LABEL_25;
    case 1u:
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = -2147467259;
      ShellHandwriting::DelegationManager::CleanupDelegateThread(this);
LABEL_25:
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v2,
        0);
      return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    case 0xFFFFFFFF:
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = ResultFromKnownLastError();
      ShellHandwriting::DelegationManager::ShutdownDelegateThread(this);
      if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
        return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
      v4 = 463;
      break;
    default:
      ShellHandwriting::DelegationManager::ShutdownDelegateThread(this);
      event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = -2147467259;
      v4 = 450;
      break;
  }
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"clientcore\\windows\\advcore\\ctf\\shellhandwriting\\delegation\\shellhandwritingdelegation.cpp",
    (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
    dwCreationFlags);
  return (unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
}

```

## disassembly

```asm
0x18007070c  mov     [rsp+arg_0], rbx
0x180070711  mov     [rsp+arg_8], rsi
0x180070716  push    rdi
0x180070717  sub     rsp, 50h
0x18007071b  mov     rbx, rcx
0x18007071e  lea     rsi, [rcx+20h]
0x180070722  mov     rcx, rsi
0x180070725  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18007072a  mov     edi, eax
0x18007072c  test    eax, eax
0x18007072e  jns     short loc_18007074E
0x180070730  mov     edx, 187h; void *
0x180070735  lea     r8, aClientcoreWind_7; "clientcore\\windows\\advcore\\ctf\\shel"...
0x18007073c  mov     r9d, edi; char *
0x18007073f  mov     rcx, [rsp+58h]; this
0x180070744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180070749  jmp     loc_1800708B6
0x18007074e  lea     rcx, [rbx+28h]
0x180070752  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x180070757  mov     edi, eax
0x180070759  test    eax, eax
0x18007075b  jns     short loc_180070764
0x18007075d  mov     edx, 188h
0x180070762  jmp     short loc_180070735
0x180070764  cmp     qword ptr [rbx+8], 0
0x180070769  jnz     short loc_18007077D
0x18007076b  call    cs:__imp_GetCurrentThreadId
0x180070771  mov     ecx, eax; dwThreadId
0x180070773  call    cs:__imp_GetThreadDesktop
0x180070779  mov     [rbx+8], rax
0x18007077d  lea     rax, [rbx+14h]
0x180070781  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180070786  mov     [rsp+58h+dwCreationFlags], 4; dwCreationFlags
0x18007078e  mov     r9, rbx; lpParameter
0x180070791  lea     r8, ?s_ThreadProc@DelegationManager@ShellHandwriting@@CAKPEAX@Z; lpStartAddress
0x180070798  xor     edx, edx; dwStackSize
0x18007079a  xor     ecx, ecx; lpThreadAttributes
0x18007079c  call    cs:__imp_CreateThread
0x1800707a2  mov     rcx, rax; hObject
0x1800707a5  lea     rdi, [rbx+30h]
0x1800707a9  lea     rax, [rsp+58h+var_28]
0x1800707ae  cmp     rdi, rax
0x1800707b1  jz      short loc_1800707C0
0x1800707b3  mov     rdx, rcx
0x1800707b6  mov     rcx, rdi
0x1800707b9  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800707be  jmp     short loc_1800707D1
0x1800707c0  lea     rax, [rcx-1]
0x1800707c4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800707c8  ja      short loc_1800707D1
0x1800707ca  call    cs:__imp_CloseHandle
0x1800707d0  nop
0x1800707d1  mov     rcx, [rdi]; hThread
0x1800707d4  lea     rax, [rcx+1]
0x1800707d8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800707de  jnz     short loc_1800707FB
0x1800707e0  mov     edx, 198h; void *
0x1800707e5  lea     r8, aClientcoreWind_7; "clientcore\\windows\\advcore\\ctf\\shel"...
0x1800707ec  mov     rcx, [rsp+58h]; this
0x1800707f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800707f6  jmp     loc_1800708B8
0x1800707fb  lea     rdx, ThreadDescription; "ShellHandwriting Delegate Thread"
0x180070802  call    cs:__imp_SetThreadDescription
0x180070808  mov     rcx, [rdi]; hThread
0x18007080b  call    cs:__imp_ResumeThread
0x180070811  cmp     eax, 0FFFFFFFFh
0x180070814  jnz     short loc_18007081D
0x180070816  mov     edx, 19Eh
0x18007081b  jmp     short loc_1800707E5
0x18007081d  mov     rax, [rsi]
0x180070820  mov     [rsp+58h+Handles], rax
0x180070825  mov     rax, [rdi]
0x180070828  mov     [rsp+58h+var_18], rax
0x18007082d  mov     [rsp+58h+dwCreationFlags], 0; bAlertable
0x180070835  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x180070839  xor     r8d, r8d; bWaitAll
0x18007083c  lea     rdx, [rsp+58h+Handles]; lpHandles
0x180070841  lea     ecx, [r8+2]; nCount
0x180070845  call    cs:__imp_WaitForMultipleObjectsEx
0x18007084b  test    eax, eax
0x18007084d  jz      short loc_1800708AA
0x18007084f  cmp     eax, 1
0x180070852  jz      short loc_18007089B
0x180070854  cmp     eax, 0C0h
0x180070859  jz      short loc_180070884
0x18007085b  cmp     eax, 102h
0x180070860  jz      short loc_180070884
0x180070862  cmp     eax, 0FFFFFFFFh
0x180070865  jnz     short loc_180070884
0x180070867  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18007086c  mov     edi, eax
0x18007086e  mov     rcx, rbx; this
0x180070871  call    ?ShutdownDelegateThread@DelegationManager@ShellHandwriting@@AEAA_NXZ; ShellHandwriting::DelegationManager::ShutdownDelegateThread(void)
0x180070876  test    edi, edi
0x180070878  jns     short loc_1800708B6
0x18007087a  mov     edx, 1CFh
0x18007087f  jmp     loc_180070735
0x180070884  mov     rcx, rbx; this
0x180070887  call    ?ShutdownDelegateThread@DelegationManager@ShellHandwriting@@AEAA_NXZ; ShellHandwriting::DelegationManager::ShutdownDelegateThread(void)
0x18007088c  mov     edi, 80004005h
0x180070891  mov     edx, 1C2h
0x180070896  jmp     loc_180070735
0x18007089b  mov     edi, 80004005h
0x1800708a0  mov     rcx, rbx; this
0x1800708a3  call    ?CleanupDelegateThread@DelegationManager@ShellHandwriting@@AEAAXXZ; ShellHandwriting::DelegationManager::CleanupDelegateThread(void)
0x1800708a8  jmp     short loc_1800708AC
0x1800708aa  xor     edi, edi
0x1800708ac  xor     edx, edx
0x1800708ae  mov     rcx, rsi
0x1800708b1  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800708b6  mov     eax, edi
0x1800708b8  mov     rbx, [rsp+58h+arg_0]
0x1800708bd  mov     rsi, [rsp+58h+arg_8]
0x1800708c2  add     rsp, 50h
0x1800708c6  pop     rdi
0x1800708c7  retn
```
