# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1801a2834`
- end: `0x1801a29d5`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `417`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1801cf078`

## callees

- `0x1801a2834`
- `0x1801a29fc`
- `0x1801a2a24`
- `0x1801a2a58`
- `0x1801a2a90`
- `0x1801a6ca0`
- `0x1801a6d90`
- `0x1801b0ba4`
- `0x1801b61e0`
- `0x1801cfbc8`
- `0x1803481f0`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1801a2885`
- `KERNEL32!GetCurrentProcessId` at `0x1801a2885`
- `KERNEL32!CreateMutexExW` at `0x1801a28d0`
- `KERNEL32!CreateMutexExW` at `0x1801a28d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        __int64 *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v6; // rcx
  void *v7; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  void *v10; // rdx
  __int64 v11; // rdx
  void *v12; // rdx
  _DWORD *v13; // rcx
  wil::details *v15; // [rsp+38h] [rbp-D0h] BYREF
  int v16[2]; // [rsp+40h] [rbp-C8h] BYREF
  void *v17[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  v17[1] = (void *)-2LL;
  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId, 120, a1);
  v15 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v15,
    (__int64)Mutex);
  if ( v15 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      (HANDLE *)&v15,
      v16,
      0,
      0xFFFFFFFF,
      0);
    v17[0] = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, v17);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v11 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v11, (int)"wil", (const char *)(unsigned int)Pointer);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        (wil::details **)v16,
        v12);
      goto LABEL_9;
    }
    v13 = v17[0];
    if ( v17[0] )
    {
      *a2 = (__int64)v17[0];
      ++*v13;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(
                  Name,
                  &v15,
                  a2);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v11 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      (wil::details **)v16,
      v10);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v6);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v15,
    v7);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1801a2834  mov     rax, rsp
0x1801a2837  mov     [rax+10h], rdx
0x1801a283b  mov     [rax+8], rcx
0x1801a283f  push    rbp
0x1801a2840  lea     rbp, [rax-178h]
0x1801a2847  sub     rsp, 270h
0x1801a284e  mov     qword ptr [rsp+270h+var_228], 0FFFFFFFFFFFFFFFEh
0x1801a2857  mov     [rax+18h], rbx
0x1801a285b  mov     [rax+20h], rdi
0x1801a285f  mov     rax, cs:__security_cookie
0x1801a2866  xor     rax, rsp
0x1801a2869  mov     [rbp+170h+var_10], rax
0x1801a2870  mov     rbx, [rbp+170h+arg_0]
0x1801a2877  mov     rdi, [rbp+170h+arg_8]
0x1801a287e  mov     qword ptr [rdi], 0
0x1801a2885  call    cs:__imp_GetCurrentProcessId
0x1801a288c  nop     dword ptr [rax+rax+00h]
0x1801a2891  mov     r9d, eax
0x1801a2894  mov     [rsp+270h+var_248], rbx
0x1801a2899  mov     [rsp+270h+bAlertable], 78h ; 'x'
0x1801a28a1  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1801a28a8  mov     edx, 104h; unsigned __int64
0x1801a28ad  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1801a28b2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801a28b7  mov     [rsp+270h+var_240], 0
0x1801a28c0  mov     r9d, 1F0001h; dwDesiredAccess
0x1801a28c6  xor     r8d, r8d; dwFlags
0x1801a28c9  lea     rdx, [rsp+270h+Name]; lpName
0x1801a28ce  xor     ecx, ecx; lpMutexAttributes
0x1801a28d0  call    cs:__imp_CreateMutexExW
0x1801a28d7  nop     dword ptr [rax+rax+00h]
0x1801a28dc  mov     rdx, rax
0x1801a28df  lea     rcx, [rsp+270h+var_240]
0x1801a28e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1801a28e9  cmp     [rsp+270h+var_240], 0
0x1801a28ef  jnz     short loc_1801A28FD
0x1801a28f1  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1801a28f6  mov     ebx, eax
0x1801a28f8  jmp     loc_1801A2981
0x1801a28fd  mov     [rsp+270h+bAlertable], 0; int
0x1801a2905  or      r9d, 0FFFFFFFFh; int
0x1801a2909  xor     r8d, r8d; int
0x1801a290c  lea     rdx, [rsp+270h+var_238]; int
0x1801a2911  lea     rcx, [rsp+270h+var_240]; int
0x1801a2916  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1801a291b  nop
0x1801a291c  mov     [rsp+270h+var_230], 0
0x1801a2925  lea     rdx, [rsp+270h+var_230]; void **
0x1801a292a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1801a292f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1801a2934  mov     ebx, eax
0x1801a2936  test    eax, eax
0x1801a2938  jns     short loc_1801A2962
0x1801a293a  mov     edx, 12Eh; void *
0x1801a293f  lea     r8, aWil; "wil"
0x1801a2946  mov     r9d, eax; char *
0x1801a2949  mov     rcx, [rbp+178h]; this
0x1801a2950  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801a2955  nop
0x1801a2956  lea     rcx, [rsp+270h+var_238]
0x1801a295b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801a2960  jmp     short loc_1801A2981
0x1801a2962  mov     rcx, [rsp+270h+var_230]
0x1801a2967  test    rcx, rcx
0x1801a296a  jz      short loc_1801A29B2
0x1801a296c  mov     [rdi], rcx
0x1801a296f  mov     eax, [rcx]
0x1801a2971  inc     eax
0x1801a2973  mov     [rcx], eax
0x1801a2975  lea     rcx, [rsp+270h+var_238]
0x1801a297a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801a297f  xor     ebx, ebx
0x1801a2981  lea     rcx, [rsp+270h+var_240]
0x1801a2986  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1801a298b  mov     eax, ebx
0x1801a298d  mov     rcx, [rbp+170h+var_10]
0x1801a2994  xor     rcx, rsp; StackCookie
0x1801a2997  call    __security_check_cookie
0x1801a299c  lea     r11, [rsp+270h+var_s0]
0x1801a29a4  mov     rbx, [r11+20h]
0x1801a29a8  mov     rdi, [r11+28h]
0x1801a29ac  mov     rsp, r11
0x1801a29af  pop     rbp
0x1801a29b0  retn
0x1801a29b2  mov     r8, rdi
0x1801a29b5  lea     rdx, [rsp+270h+var_240]
0x1801a29ba  lea     rcx, [rsp+270h+Name]
0x1801a29bf  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1801a29c4  mov     ebx, eax
0x1801a29c6  test    eax, eax
0x1801a29c8  jns     short loc_1801A2975
0x1801a29ca  mov     edx, 137h
0x1801a29cf  jmp     loc_1801A293F
```
