# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x1800037b0`
- end: `0x18000390f`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800046bc`

## callees

- `0x180003418`
- `0x180003434`
- `0x1800037b0`
- `0x1800044e8`
- `0x180005144`
- `0x18000630c`
- `0x180006a8c`
- `0x180006f2c`
- `0x180007804`
- `0x180007f90`
- `0x180035b40`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x18000382d`
- `KERNEL32!CreateMutexExW` at `0x18000382d`
- `KERNEL32!GetCurrentProcessId` at `0x1800037e8`
- `KERNEL32!GetCurrentProcessId` at `0x1800037e8`

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
0x1800037b0  mov     [rsp-8+arg_10], rbx
0x1800037b5  mov     [rsp-8+arg_18], rdi
0x1800037ba  push    rbp
0x1800037bb  lea     rbp, [rsp-170h]
0x1800037c3  sub     rsp, 270h
0x1800037ca  mov     rax, cs:__security_cookie
0x1800037d1  xor     rax, rsp
0x1800037d4  mov     [rbp+170h+var_10], rax
0x1800037db  mov     rdi, rdx
0x1800037de  mov     qword ptr [rdx], 0
0x1800037e5  mov     rbx, rcx
0x1800037e8  call    cs:__imp_GetCurrentProcessId
0x1800037ee  mov     [rsp+270h+var_248], rbx
0x1800037f3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x1800037fa  mov     r9d, eax
0x1800037fd  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x180003805  mov     edx, 104h; unsigned __int64
0x18000380a  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000380f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003814  mov     r9d, 1F0001h; dwDesiredAccess
0x18000381a  mov     [rsp+270h+var_240], 0
0x180003823  xor     r8d, r8d; dwFlags
0x180003826  lea     rdx, [rsp+270h+Name]; lpName
0x18000382b  xor     ecx, ecx; lpMutexAttributes
0x18000382d  call    cs:__imp_CreateMutexExW
0x180003833  mov     rdx, rax
0x180003836  lea     rcx, [rsp+270h+var_240]
0x18000383b  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180003840  cmp     [rsp+270h+var_240], 0
0x180003846  jnz     short loc_180003851
0x180003848  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000384d  mov     ebx, eax
0x18000384f  jmp     short loc_1800038BD
0x180003851  lea     rdx, [rsp+270h+var_238]
0x180003856  lea     rcx, [rsp+270h+var_240]
0x18000385b  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x180003860  lea     rdx, [rsp+270h+var_230]; void **
0x180003865  mov     [rsp+270h+var_230], 0
0x18000386e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180003873  call    ?TryGetPointer@SemaphoreValue@details_abi@wil@@SAJPEBGPEAPEAX@Z; wil::details_abi::SemaphoreValue::TryGetPointer(ushort const *,void * *)
0x180003878  mov     ebx, eax
0x18000387a  test    eax, eax
0x18000387c  jns     short loc_18000389E
0x18000387e  mov     edx, 12Eh; void *
0x180003883  mov     rcx, [rbp+178h]; this
0x18000388a  mov     r9d, eax; char *
0x18000388d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003892  lea     rcx, [rsp+270h+var_238]
0x180003897  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000389c  jmp     short loc_1800038BD
0x18000389e  mov     rcx, [rsp+270h+var_230]
0x1800038a3  test    rcx, rcx
0x1800038a6  jz      short loc_1800038ED
0x1800038a8  mov     [rdi], rcx
0x1800038ab  mov     eax, [rcx]
0x1800038ad  inc     eax
0x1800038af  mov     [rcx], eax
0x1800038b1  lea     rcx, [rsp+270h+var_238]
0x1800038b6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800038bb  xor     ebx, ebx
0x1800038bd  lea     rcx, [rsp+270h+var_240]
0x1800038c2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800038c7  mov     eax, ebx
0x1800038c9  mov     rcx, [rbp+170h+var_10]
0x1800038d0  xor     rcx, rsp; StackCookie
0x1800038d3  call    __security_check_cookie
0x1800038d8  lea     r11, [rsp+270h+var_s0]
0x1800038e0  mov     rbx, [r11+20h]
0x1800038e4  mov     rdi, [r11+28h]
0x1800038e8  mov     rsp, r11
0x1800038eb  pop     rbp
0x1800038ec  retn
0x1800038ed  mov     r8, rdi
0x1800038f0  lea     rdx, [rsp+270h+var_240]
0x1800038f5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800038fa  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1800038ff  mov     ebx, eax
0x180003901  test    eax, eax
0x180003903  jns     short loc_1800038B1
0x180003905  mov     edx, 137h
0x18000390a  jmp     loc_180003883
```
