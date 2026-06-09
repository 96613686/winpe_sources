# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180425efc`
- end: `0x180426084`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `392`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1804278b8`

## callees

- `0x18029e7f4`
- `0x180425bfc`
- `0x180425c24`
- `0x180425efc`
- `0x1804270c0`
- `0x1804284bc`
- `0x1804299f4`
- `0x18042ab14`
- `0x18042b344`
- `0x18042b61c`
- `0x1805a9e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180425f98`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180425f98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180425f4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180425f4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+40h] [rbp-C8h] BYREF
  void *v14[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v14[1] = (void *)-2LL;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v12 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v12,
    Mutex);
  if ( v12 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v12,
      &v13);
    v14[0] = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
      goto LABEL_9;
    }
    v10 = v14[0];
    if ( v14[0] )
    {
      *a2 = v14[0];
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
                  Name,
                  &v12,
                  a2);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180425efc  mov     rax, rsp
0x180425eff  mov     [rax+10h], rdx
0x180425f03  mov     [rax+8], rcx
0x180425f07  push    rbp
0x180425f08  lea     rbp, [rax-178h]
0x180425f0f  sub     rsp, 270h
0x180425f16  mov     qword ptr [rsp+270h+var_228], 0FFFFFFFFFFFFFFFEh
0x180425f1f  mov     [rax+18h], rbx
0x180425f23  mov     [rax+20h], rdi
0x180425f27  mov     rax, cs:__security_cookie
0x180425f2e  xor     rax, rsp
0x180425f31  mov     [rbp+170h+var_10], rax
0x180425f38  mov     rbx, [rbp+170h+arg_0]
0x180425f3f  mov     rdi, [rbp+170h+arg_8]
0x180425f46  mov     qword ptr [rdi], 0
0x180425f4d  call    cs:__imp_GetCurrentProcessId
0x180425f54  nop     dword ptr [rax+rax+00h]
0x180425f59  mov     r9d, eax
0x180425f5c  mov     [rsp+270h+var_248], rbx
0x180425f61  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180425f69  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180425f70  mov     edx, 104h; unsigned __int64
0x180425f75  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180425f7a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180425f7f  mov     [rsp+270h+var_240], 0
0x180425f88  mov     r9d, 1F0001h; dwDesiredAccess
0x180425f8e  xor     r8d, r8d; dwFlags
0x180425f91  lea     rdx, [rsp+270h+Name]; lpName
0x180425f96  xor     ecx, ecx; lpMutexAttributes
0x180425f98  call    cs:__imp_CreateMutexExW
0x180425f9f  nop     dword ptr [rax+rax+00h]
0x180425fa4  mov     rdx, rax
0x180425fa7  lea     rcx, [rsp+270h+var_240]
0x180425fac  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180425fb1  cmp     [rsp+270h+var_240], 0
0x180425fb7  jnz     short loc_180425FC2
0x180425fb9  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180425fbe  mov     ebx, eax
0x180425fc0  jmp     short loc_180426030
0x180425fc2  lea     rdx, [rsp+270h+var_238]
0x180425fc7  lea     rcx, [rsp+270h+var_240]
0x180425fcc  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180425fd1  nop
0x180425fd2  mov     [rsp+270h+var_230], 0
0x180425fdb  lea     rdx, [rsp+270h+var_230]; void **
0x180425fe0  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180425fe5  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180425fea  mov     ebx, eax
0x180425fec  test    eax, eax
0x180425fee  jns     short loc_180426011
0x180425ff0  mov     edx, 12Eh; void *
0x180425ff5  mov     r9d, eax; char *
0x180425ff8  mov     rcx, [rbp+178h]; this
0x180425fff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180426004  nop
0x180426005  lea     rcx, [rsp+270h+var_238]
0x18042600a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18042600f  jmp     short loc_180426030
0x180426011  mov     rcx, [rsp+270h+var_230]
0x180426016  test    rcx, rcx
0x180426019  jz      short loc_180426061
0x18042601b  mov     [rdi], rcx
0x18042601e  mov     eax, [rcx]
0x180426020  inc     eax
0x180426022  mov     [rcx], eax
0x180426024  lea     rcx, [rsp+270h+var_238]
0x180426029  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18042602e  xor     ebx, ebx
0x180426030  lea     rcx, [rsp+270h+var_240]
0x180426035  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18042603a  mov     eax, ebx
0x18042603c  mov     rcx, [rbp+170h+var_10]
0x180426043  xor     rcx, rsp; StackCookie
0x180426046  call    __security_check_cookie
0x18042604b  lea     r11, [rsp+270h+var_s0]
0x180426053  mov     rbx, [r11+20h]
0x180426057  mov     rdi, [r11+28h]
0x18042605b  mov     rsp, r11
0x18042605e  pop     rbp
0x18042605f  retn
0x180426061  mov     r8, rdi
0x180426064  lea     rdx, [rsp+270h+var_240]
0x180426069  lea     rcx, [rsp+270h+Name]
0x18042606e  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180426073  mov     ebx, eax
0x180426075  test    eax, eax
0x180426077  jns     short loc_180426024
0x180426079  mov     edx, 137h
0x18042607e  jmp     loc_180425FF5
```
