# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800eb2cc`
- end: `0x1800eb432`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ec938`

## callees

- `0x1800d3390`
- `0x1800e9380`
- `0x1800eaf94`
- `0x1800eafb4`
- `0x1800eb2cc`
- `0x1800ec5cc`
- `0x1800ed690`
- `0x1800ee92c`
- `0x1800ef2a4`
- `0x1800efc54`
- `0x1800eff18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800eb349`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x1800eb349`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800eb301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800eb301`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  unsigned int v8; // r8d
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v13[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v14; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

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
      v13);
    v14 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v14);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v9 = 299;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      *(_DWORD *)*a2 = *v10 + 1;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 308;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
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
0x1800eb2cc  mov     [rsp-8+arg_10], rbx
0x1800eb2d1  mov     [rsp-8+arg_18], rdi
0x1800eb2d6  push    rbp
0x1800eb2d7  lea     rbp, [rsp-170h]
0x1800eb2df  sub     rsp, 270h
0x1800eb2e6  mov     rax, cs:__security_cookie
0x1800eb2ed  xor     rax, rsp
0x1800eb2f0  mov     [rbp+170h+var_10], rax
0x1800eb2f7  and     qword ptr [rdx], 0
0x1800eb2fb  mov     rdi, rdx
0x1800eb2fe  mov     rbx, rcx
0x1800eb301  call    cs:__imp_GetCurrentProcessId
0x1800eb308  nop     dword ptr [rax+rax+00h]
0x1800eb30d  mov     [rsp+270h+var_248], rbx
0x1800eb312  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800eb319  mov     r9d, eax
0x1800eb31c  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800eb324  mov     edx, 104h; unsigned __int64
0x1800eb329  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800eb32e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800eb333  and     [rsp+270h+var_240], 0
0x1800eb339  lea     rdx, [rsp+270h+Name]; lpName
0x1800eb33e  mov     r9d, 1F0001h; dwDesiredAccess
0x1800eb344  xor     r8d, r8d; dwFlags
0x1800eb347  xor     ecx, ecx; lpMutexAttributes
0x1800eb349  call    cs:__imp_CreateMutexExW
0x1800eb350  nop     dword ptr [rax+rax+00h]
0x1800eb355  mov     rdx, rax
0x1800eb358  lea     rcx, [rsp+270h+var_240]
0x1800eb35d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800eb362  cmp     [rsp+270h+var_240], 0
0x1800eb368  jnz     short loc_1800EB373
0x1800eb36a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800eb36f  mov     ebx, eax
0x1800eb371  jmp     short loc_1800EB3DF
0x1800eb373  lea     rdx, [rsp+270h+var_238]
0x1800eb378  lea     rcx, [rsp+270h+var_240]
0x1800eb37d  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800eb382  and     [rsp+270h+var_230], 0
0x1800eb388  lea     rdx, [rsp+270h+var_230]; void **
0x1800eb38d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800eb392  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x1800eb397  mov     ebx, eax
0x1800eb399  test    eax, eax
0x1800eb39b  jns     short loc_1800EB3BD
0x1800eb39d  mov     edx, 12Bh; void *
0x1800eb3a2  mov     rcx, [rbp+178h]; this
0x1800eb3a9  mov     r9d, eax; char *
0x1800eb3ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800eb3b1  lea     rcx, [rsp+270h+var_238]
0x1800eb3b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800eb3bb  jmp     short loc_1800EB3DF
0x1800eb3bd  mov     rcx, [rsp+270h+var_230]
0x1800eb3c2  test    rcx, rcx
0x1800eb3c5  jz      short loc_1800EB410
0x1800eb3c7  mov     [rdi], rcx
0x1800eb3ca  mov     ecx, [rcx]
0x1800eb3cc  mov     rax, [rdi]
0x1800eb3cf  inc     ecx
0x1800eb3d1  mov     [rax], ecx
0x1800eb3d3  lea     rcx, [rsp+270h+var_238]
0x1800eb3d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800eb3dd  xor     ebx, ebx
0x1800eb3df  lea     rcx, [rsp+270h+var_240]
0x1800eb3e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800eb3e9  mov     eax, ebx
0x1800eb3eb  mov     rcx, [rbp+170h+var_10]
0x1800eb3f2  xor     rcx, rsp; StackCookie
0x1800eb3f5  call    __security_check_cookie
0x1800eb3fa  lea     r11, [rsp+270h+var_s0]
0x1800eb402  mov     rbx, [r11+20h]
0x1800eb406  mov     rdi, [r11+28h]
0x1800eb40a  mov     rsp, r11
0x1800eb40d  pop     rbp
0x1800eb40e  retn
0x1800eb410  mov     r8, rdi
0x1800eb413  lea     rdx, [rsp+270h+var_240]
0x1800eb418  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800eb41d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800eb422  mov     ebx, eax
0x1800eb424  test    eax, eax
0x1800eb426  jns     short loc_1800EB3D3
0x1800eb428  mov     edx, 134h
0x1800eb42d  jmp     loc_1800EB3A2
```
