# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140007adc`
- end: `0x140007c42`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140008ff8`

## callees

- `0x1400047c8`
- `0x140004a94`
- `0x140004ae0`
- `0x140005530`
- `0x1400076d0`
- `0x1400076ec`
- `0x140007adc`
- `0x14000ad9c`
- `0x14000afdc`
- `0x14000b8f4`
- `0x14000bb94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007b59`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x140007b59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007b14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140007b14`

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
0x140007adc  mov     [rsp-8+arg_10], rbx
0x140007ae1  mov     [rsp-8+arg_18], rdi
0x140007ae6  push    rbp
0x140007ae7  lea     rbp, [rsp-170h]
0x140007aef  sub     rsp, 270h
0x140007af6  mov     rax, cs:__security_cookie
0x140007afd  xor     rax, rsp
0x140007b00  mov     [rbp+170h+var_10], rax
0x140007b07  mov     rdi, rdx
0x140007b0a  mov     qword ptr [rdx], 0
0x140007b11  mov     rbx, rcx
0x140007b14  call    cs:__imp_GetCurrentProcessId
0x140007b1a  mov     [rsp+270h+var_248], rbx
0x140007b1f  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140007b26  mov     r9d, eax
0x140007b29  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140007b31  mov     edx, 104h; unsigned __int64
0x140007b36  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007b3b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140007b40  mov     r9d, 1F0001h; dwDesiredAccess
0x140007b46  mov     [rsp+270h+var_240], 0
0x140007b4f  xor     r8d, r8d; dwFlags
0x140007b52  lea     rdx, [rsp+270h+Name]; lpName
0x140007b57  xor     ecx, ecx; lpMutexAttributes
0x140007b59  call    cs:__imp_CreateMutexExW
0x140007b5f  mov     rdx, rax
0x140007b62  lea     rcx, [rsp+270h+var_240]
0x140007b67  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140007b6c  cmp     [rsp+270h+var_240], 0
0x140007b72  jnz     short loc_140007B7D
0x140007b74  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140007b79  mov     ebx, eax
0x140007b7b  jmp     short loc_140007BF0
0x140007b7d  lea     rdx, [rsp+270h+var_238]
0x140007b82  lea     rcx, [rsp+270h+var_240]
0x140007b87  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140007b8c  lea     rdx, [rsp+270h+var_230]; void **
0x140007b91  mov     [rsp+270h+var_230], 0
0x140007b9a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007b9f  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x140007ba4  mov     ebx, eax
0x140007ba6  test    eax, eax
0x140007ba8  jns     short loc_140007BD1
0x140007baa  mov     edx, 12Eh; void *
0x140007baf  mov     rcx, [rbp+178h]; this
0x140007bb6  lea     r8, aWil; "wil"
0x140007bbd  mov     r9d, eax; char *
0x140007bc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007bc5  lea     rcx, [rsp+270h+var_238]
0x140007bca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007bcf  jmp     short loc_140007BF0
0x140007bd1  mov     rcx, [rsp+270h+var_230]
0x140007bd6  test    rcx, rcx
0x140007bd9  jz      short loc_140007C20
0x140007bdb  mov     [rdi], rcx
0x140007bde  mov     eax, [rcx]
0x140007be0  inc     eax
0x140007be2  mov     [rcx], eax
0x140007be4  lea     rcx, [rsp+270h+var_238]
0x140007be9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007bee  xor     ebx, ebx
0x140007bf0  lea     rcx, [rsp+270h+var_240]
0x140007bf5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140007bfa  mov     eax, ebx
0x140007bfc  mov     rcx, [rbp+170h+var_10]
0x140007c03  xor     rcx, rsp; StackCookie
0x140007c06  call    __security_check_cookie
0x140007c0b  lea     r11, [rsp+270h+var_s0]
0x140007c13  mov     rbx, [r11+20h]
0x140007c17  mov     rdi, [r11+28h]
0x140007c1b  mov     rsp, r11
0x140007c1e  pop     rbp
0x140007c1f  retn
0x140007c20  mov     r8, rdi
0x140007c23  lea     rdx, [rsp+270h+var_240]
0x140007c28  lea     rcx, [rsp+270h+Name]
0x140007c2d  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x140007c32  mov     ebx, eax
0x140007c34  test    eax, eax
0x140007c36  jns     short loc_140007BE4
0x140007c38  mov     edx, 137h
0x140007c3d  jmp     loc_140007BAF
```
