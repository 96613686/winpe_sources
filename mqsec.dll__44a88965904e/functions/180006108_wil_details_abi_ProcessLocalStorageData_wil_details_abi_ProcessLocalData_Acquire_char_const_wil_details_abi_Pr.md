# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180006108`
- end: `0x18000626a`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180007024`

## callees

- `0x180005d10`
- `0x180005d2c`
- `0x180006108`
- `0x180006e58`
- `0x18000862c`
- `0x18000989c`
- `0x18000a174`
- `0x18000a58c`
- `0x18000ac64`
- `0x18000afc8`
- `0x18002f0e0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x180006185`
- `KERNEL32!CreateMutexExW` at `0x180006185`
- `KERNEL32!GetCurrentProcessId` at `0x180006140`
- `KERNEL32!GetCurrentProcessId` at `0x180006140`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      v9 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v9, v8, (const char *)(unsigned int)Pointer, 120);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v12);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x180006108  mov     [rsp-8+arg_10], rbx
0x18000610d  mov     [rsp-8+arg_18], rdi
0x180006112  push    rbp
0x180006113  lea     rbp, [rsp-170h]
0x18000611b  sub     rsp, 270h
0x180006122  mov     rax, cs:__security_cookie
0x180006129  xor     rax, rsp
0x18000612c  mov     [rbp+170h+var_10], rax
0x180006133  mov     rdi, rdx
0x180006136  mov     rbx, rcx
0x180006139  mov     qword ptr [rdx], 0
0x180006140  call    cs:__imp_GetCurrentProcessId
0x180006146  mov     r9d, eax
0x180006149  mov     [rsp+270h+var_248], rbx
0x18000614e  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180006156  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x18000615d  mov     edx, 104h; unsigned __int64
0x180006162  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006167  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18000616c  mov     [rsp+270h+var_240], 0
0x180006175  mov     r9d, 1F0001h; dwDesiredAccess
0x18000617b  xor     r8d, r8d; dwFlags
0x18000617e  lea     rdx, [rsp+270h+Name]; lpName
0x180006183  xor     ecx, ecx; lpMutexAttributes
0x180006185  call    cs:__imp_CreateMutexExW
0x18000618b  mov     rdx, rax
0x18000618e  lea     rcx, [rsp+270h+var_240]
0x180006193  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180006198  cmp     [rsp+270h+var_240], 0
0x18000619e  jnz     short loc_1800061A9
0x1800061a0  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800061a5  mov     ebx, eax
0x1800061a7  jmp     short loc_180006217
0x1800061a9  lea     rdx, [rsp+270h+var_238]
0x1800061ae  lea     rcx, [rsp+270h+var_240]
0x1800061b3  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x1800061b8  nop
0x1800061b9  mov     [rsp+270h+var_230], 0
0x1800061c2  lea     rdx, [rsp+270h+var_230]; void **
0x1800061c7  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1800061cc  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEB_WPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(wchar_t const *,void * *)
0x1800061d1  mov     ebx, eax
0x1800061d3  test    eax, eax
0x1800061d5  jns     short loc_1800061F8
0x1800061d7  mov     edx, 12Eh; void *
0x1800061dc  mov     r9d, eax; char *
0x1800061df  mov     rcx, [rbp+178h]; this
0x1800061e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800061eb  nop
0x1800061ec  lea     rcx, [rsp+270h+var_238]
0x1800061f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800061f6  jmp     short loc_180006217
0x1800061f8  mov     rcx, [rsp+270h+var_230]
0x1800061fd  test    rcx, rcx
0x180006200  jz      short loc_180006247
0x180006202  mov     [rdi], rcx
0x180006205  mov     eax, [rcx]
0x180006207  inc     eax
0x180006209  mov     [rcx], eax
0x18000620b  lea     rcx, [rsp+270h+var_238]
0x180006210  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006215  xor     ebx, ebx
0x180006217  lea     rcx, [rsp+270h+var_240]
0x18000621c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006221  mov     eax, ebx
0x180006223  mov     rcx, [rbp+170h+var_10]
0x18000622a  xor     rcx, rsp; StackCookie
0x18000622d  call    __security_check_cookie
0x180006232  lea     r11, [rsp+270h+var_s0]
0x18000623a  mov     rbx, [r11+20h]
0x18000623e  mov     rdi, [r11+28h]
0x180006242  mov     rsp, r11
0x180006245  pop     rbp
0x180006246  retn
0x180006247  mov     r8, rdi
0x18000624a  lea     rdx, [rsp+270h+var_240]
0x18000624f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180006254  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEB_W$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x180006259  mov     ebx, eax
0x18000625b  test    eax, eax
0x18000625d  jns     short loc_18000620B
0x18000625f  mov     edx, 137h
0x180006264  jmp     loc_1800061DC
```
