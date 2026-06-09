# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x180023a18`
- end: `0x180023b93`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `379`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800243a0`

## callees

- `0x18000a320`
- `0x180023418`
- `0x180023434`
- `0x180023a18`
- `0x180024254`
- `0x180024d4c`
- `0x180025cd8`
- `0x180026328`
- `0x1800269c4`
- `0x180026c84`
- `0x1800382c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023a95`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180023a95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023a50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023a50`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v9; // r8d
  _DWORD *v10; // rcx
  int v12; // eax
  unsigned int v13; // r8d
  wil::details *v14; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v15[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v16; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v14 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v14,
    Mutex);
  if ( v14 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v14,
      v15);
    v16 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v16);
    LastErrorFailHr = Pointer;
    if ( Pointer >= 0 )
    {
      v10 = v16;
      if ( v16 )
      {
        *a2 = v16;
        ++*v10;
      }
      else
      {
        v12 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
        LastErrorFailHr = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(retaddr, (void *)0x137, v13, (const char *)(unsigned int)v12, 304);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
          goto LABEL_8;
        }
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
      LastErrorFailHr = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x12E, v9, (const char *)(unsigned int)Pointer, 304);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v15);
    }
  }
  else
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
  }
LABEL_8:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v14,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180023a18  mov     [rsp-8+arg_10], rbx
0x180023a1d  mov     [rsp-8+arg_18], rdi
0x180023a22  push    rbp
0x180023a23  lea     rbp, [rsp-170h]
0x180023a2b  sub     rsp, 270h
0x180023a32  mov     rax, cs:__security_cookie
0x180023a39  xor     rax, rsp
0x180023a3c  mov     [rbp+170h+var_10], rax
0x180023a43  mov     rdi, rdx
0x180023a46  mov     rbx, rcx
0x180023a49  mov     qword ptr [rdx], 0
0x180023a50  call    cs:__imp_GetCurrentProcessId
0x180023a56  mov     r9d, eax
0x180023a59  mov     [rsp+270h+var_248], rbx
0x180023a5e  mov     [rsp+270h+var_250], 130h; int
0x180023a66  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180023a6d  mov     edx, 104h; unsigned __int64
0x180023a72  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023a77  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180023a7c  mov     [rsp+270h+var_240], 0
0x180023a85  mov     r9d, 1F0001h; dwDesiredAccess
0x180023a8b  xor     r8d, r8d; dwFlags
0x180023a8e  lea     rdx, [rsp+270h+Name]; lpName
0x180023a93  xor     ecx, ecx; lpMutexAttributes
0x180023a95  call    cs:__imp_CreateMutexExW
0x180023a9b  mov     rdx, rax
0x180023a9e  lea     rcx, [rsp+270h+var_240]
0x180023aa3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180023aa8  cmp     [rsp+270h+var_240], 0
0x180023aae  jnz     short loc_180023AB9
0x180023ab0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180023ab5  mov     ebx, eax
0x180023ab7  jmp     short loc_180023B29
0x180023ab9  lea     rdx, [rsp+270h+var_238]
0x180023abe  lea     rcx, [rsp+270h+var_240]
0x180023ac3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180023ac8  nop
0x180023ac9  mov     [rsp+270h+var_230], 0
0x180023ad2  lea     rdx, [rsp+270h+var_230]; void **
0x180023ad7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023adc  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180023ae1  mov     ebx, eax
0x180023ae3  test    eax, eax
0x180023ae5  jns     short loc_180023B09
0x180023ae7  mov     rcx, [rbp+178h]; this
0x180023aee  mov     r9d, eax; char *
0x180023af1  mov     edx, 12Eh; void *
0x180023af6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023afb  nop
0x180023afc  lea     rcx, [rsp+270h+var_238]
0x180023b01  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023b06  nop
0x180023b07  jmp     short loc_180023B29
0x180023b09  mov     rcx, [rsp+270h+var_230]
0x180023b0e  test    rcx, rcx
0x180023b11  jz      short loc_180023B59
0x180023b13  mov     [rdi], rcx
0x180023b16  mov     eax, [rcx]
0x180023b18  inc     eax
0x180023b1a  mov     [rcx], eax
0x180023b1c  lea     rcx, [rsp+270h+var_238]
0x180023b21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023b26  nop
0x180023b27  xor     ebx, ebx
0x180023b29  lea     rcx, [rsp+270h+var_240]
0x180023b2e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023b33  mov     eax, ebx
0x180023b35  mov     rcx, [rbp+170h+var_10]
0x180023b3c  xor     rcx, rsp; StackCookie
0x180023b3f  call    __security_check_cookie
0x180023b44  lea     r11, [rsp+270h+var_s0]
0x180023b4c  mov     rbx, [r11+20h]
0x180023b50  mov     rdi, [r11+28h]
0x180023b54  mov     rsp, r11
0x180023b57  pop     rbp
0x180023b58  retn
0x180023b59  mov     r8, rdi
0x180023b5c  lea     rdx, [rsp+270h+var_240]
0x180023b61  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023b66  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180023b6b  mov     ebx, eax
0x180023b6d  test    eax, eax
0x180023b6f  jns     short loc_180023B1C
0x180023b71  mov     rcx, [rbp+178h]; this
0x180023b78  mov     r9d, eax; char *
0x180023b7b  mov     edx, 137h; void *
0x180023b80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023b85  nop
0x180023b86  lea     rcx, [rsp+270h+var_238]
0x180023b8b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023b90  nop
0x180023b91  jmp     short loc_180023B29
```
