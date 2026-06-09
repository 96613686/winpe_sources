# CKstBase::Start(ushort const *)

- ea: `0x18027b0ac`
- end: `0x18027b1b2`
- name: `?Start@CKstBase@@AEAAJPEBG@Z`
- size: `262`
- prototype: `__int64 __fastcall(CKstBase *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18027b048`

## callees

- `0x18004fce4`
- `0x180158f6c`
- `0x180158fc4`
- `0x18015a97c`
- `0x18015ab80`
- `0x1801d5ab0`
- `0x18027b0ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18027b188`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18027b188`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18027b14e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18027b14e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18027b0e9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18027b0e9`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18027b140`
- `api-ms-win-core-processthreads-l1-1-3!SetThreadDescription` at `0x18027b140`

## string_xrefs

- `0x18027b139`: `DWM Kernel Sensor Thread`

## pseudocode

```c
__int64 __fastcall CKstBase::Start(CKstBase *this, const unsigned __int16 *a2)
{
  HANDLE *v3; // rsi
  char *v5; // rbx
  int event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z; // eax
  unsigned int v7; // edi
  DWORD dwCreationFlags; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HANDLE v10; // [rsp+40h] [rbp+8h] BYREF
  DWORD lpThreadId; // [rsp+48h] [rbp+10h] BYREF
  int v12; // [rsp+4Ch] [rbp+14h]

  v12 = HIDWORD(a2);
  lpThreadId = 0;
  v3 = (HANDLE *)((char *)this + 16);
  v10 = CreateThread(0, 0, CKstBase::RunKernelThreadStatic, this, 4u, &lpThreadId);
  wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
    v3,
    &v10);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v10);
  if ( *v3 )
  {
    SetThreadDescription(*v3, L"DWM Kernel Sensor Thread");
    SetThreadPriority(*v3, 16);
    v5 = (char *)this + 40;
    event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(v5, 0);
    v7 = event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z;
    if ( event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z >= 0 )
    {
      ResumeThread(*v3);
      _wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(v5);
      _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        v5,
        0);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\input\\kstbase.cpp",
        (const char *)(unsigned int)event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z,
        dwCreationFlags);
      return v7;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\input\\kstbase.cpp",
      (const char *)0x8007000ELL,
      dwCreationFlags);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18027b0ac  mov     rax, rsp
0x18027b0af  mov     [rax+18h], rbx
0x18027b0b3  mov     [rax+20h], rsi
0x18027b0b7  mov     [rax+10h], rdx
0x18027b0bb  push    rdi
0x18027b0bc  sub     rsp, 30h
0x18027b0c0  mov     dword ptr [rax+10h], 0
0x18027b0c7  lea     rax, [rax+10h]
0x18027b0cb  mov     rbx, rcx
0x18027b0ce  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x18027b0d3  mov     r9, rcx; lpParameter
0x18027b0d6  mov     [rsp+38h+dwCreationFlags], 4; int
0x18027b0de  lea     r8, ?RunKernelThreadStatic@CKstBase@@CAKPEAX@Z; lpStartAddress
0x18027b0e5  xor     edx, edx; dwStackSize
0x18027b0e7  xor     ecx, ecx; lpThreadAttributes
0x18027b0e9  call    cs:__imp_CreateThread
0x18027b0ef  lea     rsi, [rbx+10h]
0x18027b0f3  mov     [rsp+38h+arg_0], rax
0x18027b0f8  mov     rcx, rsi
0x18027b0fb  lea     rdx, [rsp+38h+arg_0]
0x18027b100  call    ??4?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18027b105  lea     rcx, [rsp+38h+arg_0]
0x18027b10a  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18027b10f  mov     rcx, [rsi]; hThread
0x18027b112  test    rcx, rcx
0x18027b115  jnz     short loc_18027B139
0x18027b117  mov     rcx, [rsp+38h]; this
0x18027b11c  lea     r8, aOnecoreuapWind_65; "onecoreuap\\windows\\dwm\\dwmcore\\inpu"...
0x18027b123  mov     ebx, 8007000Eh
0x18027b128  mov     edx, 44h ; 'D'; void *
0x18027b12d  mov     r9d, ebx; char *
0x18027b130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027b135  mov     eax, ebx
0x18027b137  jmp     short loc_18027B1A2
0x18027b139  lea     rdx, aDwmKernelSenso; "DWM Kernel Sensor Thread"
0x18027b140  call    cs:__imp_SetThreadDescription
0x18027b146  mov     rcx, [rsi]; hThread
0x18027b149  mov     edx, 10h; nPriority
0x18027b14e  call    cs:__imp_SetThreadPriority
0x18027b154  add     rbx, 28h ; '('
0x18027b158  xor     edx, edx
0x18027b15a  mov     rcx, rbx
0x18027b15d  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18027b162  mov     edi, eax
0x18027b164  test    eax, eax
0x18027b166  jns     short loc_18027B185
0x18027b168  mov     rcx, [rsp+38h]; this
0x18027b16d  lea     r8, aOnecoreuapWind_65; "onecoreuap\\windows\\dwm\\dwmcore\\inpu"...
0x18027b174  mov     r9d, eax; char *
0x18027b177  mov     edx, 52h ; 'R'; void *
0x18027b17c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027b181  mov     eax, edi
0x18027b183  jmp     short loc_18027B1A2
0x18027b185  mov     rcx, [rsi]; hThread
0x18027b188  call    cs:__imp_ResumeThread
0x18027b18e  mov     rcx, rbx
0x18027b191  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x18027b196  xor     edx, edx
0x18027b198  mov     rcx, rbx
0x18027b19b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18027b1a0  xor     eax, eax
0x18027b1a2  mov     rbx, [rsp+38h+arg_10]
0x18027b1a7  mov     rsi, [rsp+38h+arg_18]
0x18027b1ac  add     rsp, 30h
0x18027b1b0  pop     rdi
0x18027b1b1  retn
```
