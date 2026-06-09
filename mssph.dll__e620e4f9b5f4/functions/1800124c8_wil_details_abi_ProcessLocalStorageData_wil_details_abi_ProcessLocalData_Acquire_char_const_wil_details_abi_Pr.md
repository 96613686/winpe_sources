# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800124c8`
- end: `0x18001262e`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800132cc`

## callees

- `0x180009020`
- `0x18000f4d8`
- `0x18000f604`
- `0x18000fcd0`
- `0x1800121a8`
- `0x1800121c4`
- `0x1800124c8`
- `0x180013a54`
- `0x18001469c`
- `0x180014f68`
- `0x180015744`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012545`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x180012545`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012500`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012500`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        void **a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  void *v6; // rdx
  unsigned int LastErrorFailHr; // ebx
  int Pointer; // eax
  __int64 v9; // rdx
  _DWORD *v10; // rcx
  wil::details *v12; // [rsp+30h] [rbp-D0h] BYREF
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
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"wil",
        (const char *)(unsigned int)Pointer,
        120);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
      goto LABEL_9;
    }
    v10 = v14;
    if ( v14 )
    {
      *a2 = v14;
      ++*v10;
    }
    else
    {
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = Pointer;
      if ( Pointer < 0 )
      {
        v9 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v13);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v12,
    v6);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x1800124c8  mov     [rsp-8+arg_10], rbx
0x1800124cd  mov     [rsp-8+arg_18], rdi
0x1800124d2  push    rbp
0x1800124d3  lea     rbp, [rsp-170h]
0x1800124db  sub     rsp, 270h
0x1800124e2  mov     rax, cs:__security_cookie
0x1800124e9  xor     rax, rsp
0x1800124ec  mov     [rbp+170h+var_10], rax
0x1800124f3  mov     rdi, rdx
0x1800124f6  mov     qword ptr [rdx], 0
0x1800124fd  mov     rbx, rcx
0x180012500  call    cs:__imp_GetCurrentProcessId
0x180012506  mov     [rsp+270h+var_248], rbx
0x18001250b  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x180012512  mov     r9d, eax
0x180012515  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x18001251d  mov     edx, 104h; unsigned __int64
0x180012522  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180012527  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18001252c  mov     r9d, 1F0001h; dwDesiredAccess
0x180012532  mov     [rsp+270h+var_240], 0
0x18001253b  xor     r8d, r8d; dwFlags
0x18001253e  lea     rdx, [rsp+270h+Name]; lpName
0x180012543  xor     ecx, ecx; lpMutexAttributes
0x180012545  call    cs:__imp_CreateMutexExW
0x18001254b  mov     rdx, rax
0x18001254e  lea     rcx, [rsp+270h+var_240]
0x180012553  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180012558  cmp     [rsp+270h+var_240], 0
0x18001255e  jnz     short loc_180012569
0x180012560  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180012565  mov     ebx, eax
0x180012567  jmp     short loc_1800125DC
0x180012569  lea     rdx, [rsp+270h+var_238]
0x18001256e  lea     rcx, [rsp+270h+var_240]
0x180012573  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180012578  lea     rdx, [rsp+270h+var_230]; void **
0x18001257d  mov     [rsp+270h+var_230], 0
0x180012586  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18001258b  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x180012590  mov     ebx, eax
0x180012592  test    eax, eax
0x180012594  jns     short loc_1800125BD
0x180012596  mov     edx, 12Eh; void *
0x18001259b  mov     rcx, [rbp+178h]; this
0x1800125a2  lea     r8, aWil; "wil"
0x1800125a9  mov     r9d, eax; char *
0x1800125ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800125b1  lea     rcx, [rsp+270h+var_238]
0x1800125b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800125bb  jmp     short loc_1800125DC
0x1800125bd  mov     rcx, [rsp+270h+var_230]
0x1800125c2  test    rcx, rcx
0x1800125c5  jz      short loc_18001260C
0x1800125c7  mov     [rdi], rcx
0x1800125ca  mov     eax, [rcx]
0x1800125cc  inc     eax
0x1800125ce  mov     [rcx], eax
0x1800125d0  lea     rcx, [rsp+270h+var_238]
0x1800125d5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800125da  xor     ebx, ebx
0x1800125dc  lea     rcx, [rsp+270h+var_240]
0x1800125e1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800125e6  mov     eax, ebx
0x1800125e8  mov     rcx, [rbp+170h+var_10]
0x1800125ef  xor     rcx, rsp; StackCookie
0x1800125f2  call    __security_check_cookie
0x1800125f7  lea     r11, [rsp+270h+var_s0]
0x1800125ff  mov     rbx, [r11+20h]
0x180012603  mov     rdi, [r11+28h]
0x180012607  mov     rsp, r11
0x18001260a  pop     rbp
0x18001260b  retn
0x18001260c  mov     r8, rdi
0x18001260f  lea     rdx, [rsp+270h+var_240]
0x180012614  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180012619  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x18001261e  mov     ebx, eax
0x180012620  test    eax, eax
0x180012622  jns     short loc_1800125D0
0x180012624  mov     edx, 137h
0x180012629  jmp     loc_18001259B
```
