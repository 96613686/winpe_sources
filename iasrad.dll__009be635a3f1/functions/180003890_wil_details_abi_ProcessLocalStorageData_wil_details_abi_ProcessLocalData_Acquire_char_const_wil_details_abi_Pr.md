# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x180003890`
- end: `0x1800039ef`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004880`

## callees

- `0x1800033dc`
- `0x1800033f8`
- `0x180003890`
- `0x1800046b8`
- `0x180005850`
- `0x180006fbc`
- `0x180007804`
- `0x180007d10`
- `0x1800086f4`
- `0x180008e80`
- `0x18002e230`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x1800038c8`
- `KERNEL32!GetCurrentProcessId` at `0x1800038c8`
- `KERNEL32!CreateMutexExW` at `0x18000390d`
- `KERNEL32!CreateMutexExW` at `0x18000390d`

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
0x180003890  mov     [rsp-8+arg_10], rbx
0x180003895  mov     [rsp-8+arg_18], rdi
0x18000389a  push    rbp
0x18000389b  lea     rbp, [rsp-170h]
0x1800038a3  sub     rsp, 270h
0x1800038aa  mov     rax, cs:__security_cookie
0x1800038b1  xor     rax, rsp
0x1800038b4  mov     [rbp+170h+var_10], rax
0x1800038bb  mov     rdi, rdx
0x1800038be  mov     qword ptr [rdx], 0
0x1800038c5  mov     rbx, rcx
0x1800038c8  call    cs:__imp_GetCurrentProcessId
0x1800038ce  mov     [rsp+270h+var_248], rbx
0x1800038d3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800038da  mov     r9d, eax
0x1800038dd  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x1800038e5  mov     edx, 104h; unsigned __int64
0x1800038ea  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800038ef  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800038f4  mov     r9d, 1F0001h; dwDesiredAccess
0x1800038fa  mov     [rsp+270h+var_240], 0
0x180003903  xor     r8d, r8d; dwFlags
0x180003906  lea     rdx, [rsp+270h+Name]; lpName
0x18000390b  xor     ecx, ecx; lpMutexAttributes
0x18000390d  call    cs:__imp_CreateMutexExW
0x180003913  mov     rdx, rax
0x180003916  lea     rcx, [rsp+270h+var_240]
0x18000391b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003920  cmp     [rsp+270h+var_240], 0
0x180003926  jnz     short loc_180003931
0x180003928  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000392d  mov     ebx, eax
0x18000392f  jmp     short loc_18000399D
0x180003931  lea     rdx, [rsp+270h+var_238]
0x180003936  lea     rcx, [rsp+270h+var_240]
0x18000393b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003940  lea     rdx, [rsp+270h+var_230]; void **
0x180003945  mov     [rsp+270h+var_230], 0
0x18000394e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003953  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180003958  mov     ebx, eax
0x18000395a  test    eax, eax
0x18000395c  jns     short loc_18000397E
0x18000395e  mov     edx, 12Eh; void *
0x180003963  mov     rcx, [rbp+178h]; this
0x18000396a  mov     r9d, eax; char *
0x18000396d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003972  lea     rcx, [rsp+270h+var_238]
0x180003977  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000397c  jmp     short loc_18000399D
0x18000397e  mov     rcx, [rsp+270h+var_230]
0x180003983  test    rcx, rcx
0x180003986  jz      short loc_1800039CD
0x180003988  mov     [rdi], rcx
0x18000398b  mov     eax, [rcx]
0x18000398d  inc     eax
0x18000398f  mov     [rcx], eax
0x180003991  lea     rcx, [rsp+270h+var_238]
0x180003996  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000399b  xor     ebx, ebx
0x18000399d  lea     rcx, [rsp+270h+var_240]
0x1800039a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800039a7  mov     eax, ebx
0x1800039a9  mov     rcx, [rbp+170h+var_10]
0x1800039b0  xor     rcx, rsp; StackCookie
0x1800039b3  call    __security_check_cookie
0x1800039b8  lea     r11, [rsp+270h+var_s0]
0x1800039c0  mov     rbx, [r11+20h]
0x1800039c4  mov     rdi, [r11+28h]
0x1800039c8  mov     rsp, r11
0x1800039cb  pop     rbp
0x1800039cc  retn
0x1800039cd  mov     r8, rdi
0x1800039d0  lea     rdx, [rsp+270h+var_240]
0x1800039d5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800039da  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800039df  mov     ebx, eax
0x1800039e1  test    eax, eax
0x1800039e3  jns     short loc_180003991
0x1800039e5  mov     edx, 137h
0x1800039ea  jmp     loc_180003963
```
