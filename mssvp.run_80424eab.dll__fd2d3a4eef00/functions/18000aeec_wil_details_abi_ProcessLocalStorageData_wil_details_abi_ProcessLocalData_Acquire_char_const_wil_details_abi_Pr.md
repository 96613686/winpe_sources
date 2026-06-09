# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x18000aeec`
- end: `0x18000b052`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18000dd3c`

## callees

- `0x180005b8c`
- `0x180006270`
- `0x180008a74`
- `0x18000a610`
- `0x18000a62c`
- `0x18000aeec`
- `0x18000e694`
- `0x180011374`
- `0x180011cfc`
- `0x180012b34`
- `0x1800130f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000af24`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000af24`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000af69`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18000af69`

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
  __int64 v8; // rdx
  _DWORD *v9; // rcx
  __int64 v11; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[8]; // [rsp+38h] [rbp-C8h] BYREF
  void *v13; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v11 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v11,
    Mutex);
  if ( v11 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v11,
      v12);
    v13 = 0;
    Pointer = wil::details_abi::SemaphoreValue::TryGetPointer(Name, &v13);
    LastErrorFailHr = Pointer;
    if ( Pointer < 0 )
    {
      v8 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
      goto LABEL_9;
    }
    v9 = v13;
    if ( v13 )
    {
      *a2 = v13;
      ++*v9;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v8 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v12);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v11);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x18000aeec  mov     [rsp-8+arg_10], rbx
0x18000aef1  mov     [rsp-8+arg_18], rdi
0x18000aef6  push    rbp
0x18000aef7  lea     rbp, [rsp-170h]
0x18000aeff  sub     rsp, 270h
0x18000af06  mov     rax, cs:__security_cookie
0x18000af0d  xor     rax, rsp
0x18000af10  mov     [rbp+170h+var_10], rax
0x18000af17  mov     rdi, rdx
0x18000af1a  mov     qword ptr [rdx], 0
0x18000af21  mov     rbx, rcx
0x18000af24  call    cs:__imp_GetCurrentProcessId
0x18000af2a  mov     [rsp+270h+var_248], rbx
0x18000af2f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000af36  mov     r9d, eax
0x18000af39  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18000af41  mov     edx, 104h; unsigned __int64
0x18000af46  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000af4b  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000af50  mov     r9d, 1F0001h; dwDesiredAccess
0x18000af56  mov     [rsp+270h+var_240], 0
0x18000af5f  xor     r8d, r8d; dwFlags
0x18000af62  lea     rdx, [rsp+270h+Name]; lpName
0x18000af67  xor     ecx, ecx; lpMutexAttributes
0x18000af69  call    cs:__imp_CreateMutexExW
0x18000af6f  mov     rdx, rax
0x18000af72  lea     rcx, [rsp+270h+var_240]
0x18000af77  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000af7c  cmp     [rsp+270h+var_240], 0
0x18000af82  jnz     short loc_18000AF8D
0x18000af84  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000af89  mov     ebx, eax
0x18000af8b  jmp     short loc_18000B000
0x18000af8d  lea     rdx, [rsp+270h+var_238]
0x18000af92  lea     rcx, [rsp+270h+var_240]
0x18000af97  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18000af9c  lea     rdx, [rsp+270h+var_230]; void **
0x18000afa1  mov     [rsp+270h+var_230], 0
0x18000afaa  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000afaf  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x18000afb4  mov     ebx, eax
0x18000afb6  test    eax, eax
0x18000afb8  jns     short loc_18000AFE1
0x18000afba  mov     edx, 12Eh; void *
0x18000afbf  mov     rcx, [rbp+178h]; this
0x18000afc6  lea     r8, aWil; "wil"
0x18000afcd  mov     r9d, eax; char *
0x18000afd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000afd5  lea     rcx, [rsp+270h+var_238]
0x18000afda  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000afdf  jmp     short loc_18000B000
0x18000afe1  mov     rcx, [rsp+270h+var_230]
0x18000afe6  test    rcx, rcx
0x18000afe9  jz      short loc_18000B030
0x18000afeb  mov     [rdi], rcx
0x18000afee  mov     eax, [rcx]
0x18000aff0  inc     eax
0x18000aff2  mov     [rcx], eax
0x18000aff4  lea     rcx, [rsp+270h+var_238]
0x18000aff9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000affe  xor     ebx, ebx
0x18000b000  lea     rcx, [rsp+270h+var_240]
0x18000b005  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b00a  mov     eax, ebx
0x18000b00c  mov     rcx, [rbp+170h+var_10]
0x18000b013  xor     rcx, rsp; StackCookie
0x18000b016  call    __security_check_cookie
0x18000b01b  lea     r11, [rsp+270h+var_s0]
0x18000b023  mov     rbx, [r11+20h]
0x18000b027  mov     rdi, [r11+28h]
0x18000b02b  mov     rsp, r11
0x18000b02e  pop     rbp
0x18000b02f  retn
0x18000b030  mov     r8, rdi
0x18000b033  lea     rdx, [rsp+270h+var_240]
0x18000b038  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000b03d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18000b042  mov     ebx, eax
0x18000b044  test    eax, eax
0x18000b046  jns     short loc_18000AFF4
0x18000b048  mov     edx, 137h
0x18000b04d  jmp     loc_18000AFBF
```
