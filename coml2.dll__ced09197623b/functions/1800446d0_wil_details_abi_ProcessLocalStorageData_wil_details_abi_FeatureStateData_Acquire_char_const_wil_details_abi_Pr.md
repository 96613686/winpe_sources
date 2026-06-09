# wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)

- ea: `0x1800446d0`
- end: `0x180044836`
- name: `?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180045328`

## callees

- `0x18001fd08`
- `0x18003cd20`
- `0x18003f3e4`
- `0x18003f54c`
- `0x180042800`
- `0x180044394`
- `0x1800443b0`
- `0x1800446d0`
- `0x180047114`
- `0x1800479e4`
- `0x180047bc8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044708`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180044708`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004474d`
- `api-ms-win-core-synch-l1-1-0!CreateMutexExW` at `0x18004474d`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
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
        304);
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
      Pointer = wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::MakeAndInitialize(Name);
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
0x1800446d0  mov     [rsp-8+arg_10], rbx
0x1800446d5  mov     [rsp-8+arg_18], rdi
0x1800446da  push    rbp
0x1800446db  lea     rbp, [rsp-170h]
0x1800446e3  sub     rsp, 270h
0x1800446ea  mov     rax, cs:__security_cookie
0x1800446f1  xor     rax, rsp
0x1800446f4  mov     [rbp+170h+var_10], rax
0x1800446fb  mov     rdi, rdx
0x1800446fe  mov     qword ptr [rdx], 0
0x180044705  mov     rbx, rcx
0x180044708  call    cs:__imp_GetCurrentProcessId
0x18004470e  mov     [rsp+270h+var_248], rbx
0x180044713  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18004471a  mov     r9d, eax
0x18004471d  mov     [rsp+270h+var_250], 130h; int
0x180044725  mov     edx, 104h; unsigned __int64
0x18004472a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004472f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044734  mov     r9d, 1F0001h; dwDesiredAccess
0x18004473a  mov     [rsp+270h+var_240], 0
0x180044743  xor     r8d, r8d; dwFlags
0x180044746  lea     rdx, [rsp+270h+Name]; lpName
0x18004474b  xor     ecx, ecx; lpMutexAttributes
0x18004474d  call    cs:__imp_CreateMutexExW
0x180044753  mov     rdx, rax
0x180044756  lea     rcx, [rsp+270h+var_240]
0x18004475b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180044760  cmp     [rsp+270h+var_240], 0
0x180044766  jnz     short loc_180044771
0x180044768  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18004476d  mov     ebx, eax
0x18004476f  jmp     short loc_1800447E4
0x180044771  lea     rdx, [rsp+270h+var_238]
0x180044776  lea     rcx, [rsp+270h+var_240]
0x18004477b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180044780  lea     rdx, [rsp+270h+var_230]; void **
0x180044785  mov     [rsp+270h+var_230], 0
0x18004478e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180044793  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180044798  mov     ebx, eax
0x18004479a  test    eax, eax
0x18004479c  jns     short loc_1800447C5
0x18004479e  mov     edx, 12Eh; void *
0x1800447a3  mov     rcx, [rbp+178h]; this
0x1800447aa  lea     r8, aWil; "wil"
0x1800447b1  mov     r9d, eax; char *
0x1800447b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800447b9  lea     rcx, [rsp+270h+var_238]
0x1800447be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800447c3  jmp     short loc_1800447E4
0x1800447c5  mov     rcx, [rsp+270h+var_230]
0x1800447ca  test    rcx, rcx
0x1800447cd  jz      short loc_180044814
0x1800447cf  mov     [rdi], rcx
0x1800447d2  mov     eax, [rcx]
0x1800447d4  inc     eax
0x1800447d6  mov     [rcx], eax
0x1800447d8  lea     rcx, [rsp+270h+var_238]
0x1800447dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800447e2  xor     ebx, ebx
0x1800447e4  lea     rcx, [rsp+270h+var_240]
0x1800447e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800447ee  mov     eax, ebx
0x1800447f0  mov     rcx, [rbp+170h+var_10]
0x1800447f7  xor     rcx, rsp; StackCookie
0x1800447fa  call    __security_check_cookie
0x1800447ff  lea     r11, [rsp+270h+var_s0]
0x180044807  mov     rbx, [r11+20h]
0x18004480b  mov     rdi, [r11+28h]
0x18004480f  mov     rsp, r11
0x180044812  pop     rbp
0x180044813  retn
0x180044814  mov     r8, rdi
0x180044817  lea     rdx, [rsp+270h+var_240]
0x18004481c  lea     rcx, [rsp+270h+Name]
0x180044821  call    ?MakeAndInitialize@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180044826  mov     ebx, eax
0x180044828  test    eax, eax
0x18004482a  jns     short loc_1800447D8
0x18004482c  mov     edx, 137h
0x180044831  jmp     loc_1800447A3
```
