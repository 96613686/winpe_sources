# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData> * *)

- ea: `0x140002f70`
- end: `0x140003105`
- name: `?Acquire@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140003c18`

## callees

- `0x140002ef0`
- `0x140002f0c`
- `0x140002f70`
- `0x140003978`
- `0x140004594`
- `0x1400049d4`
- `0x140004dac`
- `0x140004f44`
- `0x140005328`
- `0x1400053e0`
- `0x1400059b0`

## import_xrefs

- `KERNEL32!CreateMutexExW` at `0x140002fed`
- `KERNEL32!CreateMutexExW` at `0x140002fed`
- `KERNEL32!GetCurrentProcessId` at `0x140002fa8`
- `KERNEL32!GetCurrentProcessId` at `0x140002fa8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::Acquire(
        __int64 a1,
        _QWORD *a2)
{
  DWORD CurrentProcessId; // eax
  HANDLE Mutex; // rax
  wil::details *v5; // rcx
  unsigned int LastErrorFailHr; // ebx
  bool v7; // dl
  bool *v8; // r9
  int ValueInternal; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r9
  __int64 v14; // rdx
  _DWORD *v15; // rcx
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  __int64 v20; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v21[8]; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a2 = 0;
  CurrentProcessId = GetCurrentProcessId();
  v18 = 120;
  StringCchPrintfW(Name, 0x104u, L"Local\\SM0:%lu:%lu:%hs", CurrentProcessId);
  v20 = 0;
  Mutex = CreateMutexExW(0, Name, 0, 0x1F0001u);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v20,
    Mutex);
  if ( v20 )
  {
    _acquire___mutex_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
      &v20,
      v21);
    v22 = 0;
    ValueInternal = wil::details_abi::SemaphoreValue::TryGetValueInternal(Name, v7, &v22, v8);
    LastErrorFailHr = ValueInternal;
    if ( ValueInternal < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x66, v10, (const char *)(unsigned int)ValueInternal, 120);
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0x6F, v11, (const char *)LastErrorFailHr, v19);
      v13 = LastErrorFailHr;
      v14 = 302;
LABEL_5:
      wil::details::in1diag3::Return_Hr(retaddr, (void *)v14, v12, (const char *)v13, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
      goto LABEL_9;
    }
    v15 = (_DWORD *)(4 * v22);
    if ( 4 * v22 )
    {
      *a2 = v15;
      ++*v15;
    }
    else
    {
      v17 = wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::MakeAndInitialize(Name);
      LastErrorFailHr = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 311;
        goto LABEL_5;
      }
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseMutex_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
    LastErrorFailHr = 0;
    goto LABEL_9;
  }
  LastErrorFailHr = wil::details::GetLastErrorFailHr(v5);
LABEL_9:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
  return LastErrorFailHr;
}

```

## disassembly

```asm
0x140002f70  mov     [rsp-8+arg_10], rbx
0x140002f75  mov     [rsp-8+arg_18], rdi
0x140002f7a  push    rbp
0x140002f7b  lea     rbp, [rsp-170h]
0x140002f83  sub     rsp, 270h
0x140002f8a  mov     rax, cs:__security_cookie
0x140002f91  xor     rax, rsp
0x140002f94  mov     [rbp+170h+var_10], rax
0x140002f9b  mov     rdi, rdx
0x140002f9e  mov     qword ptr [rdx], 0
0x140002fa5  mov     rbx, rcx
0x140002fa8  call    cs:__imp_GetCurrentProcessId
0x140002fae  mov     [rsp+270h+var_248], rbx
0x140002fb3  lea     r8, aLocalSm0LuLuHs; "Local\\SM0:%lu:%lu:%hs"
0x140002fba  mov     r9d, eax
0x140002fbd  mov     [rsp+270h+var_250], 78h ; 'x'; int
0x140002fc5  mov     edx, 104h; unsigned __int64
0x140002fca  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140002fcf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140002fd4  mov     r9d, 1F0001h; dwDesiredAccess
0x140002fda  mov     [rsp+270h+var_240], 0
0x140002fe3  xor     r8d, r8d; dwFlags
0x140002fe6  lea     rdx, [rsp+270h+Name]; lpName
0x140002feb  xor     ecx, ecx; lpMutexAttributes
0x140002fed  call    cs:__imp_CreateMutexExW
0x140002ff3  mov     rdx, rax
0x140002ff6  lea     rcx, [rsp+270h+var_240]
0x140002ffb  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140003000  cmp     [rsp+270h+var_240], 0
0x140003006  jnz     short loc_140003014
0x140003008  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x14000300d  mov     ebx, eax
0x14000300f  jmp     loc_1400030B0
0x140003014  lea     rdx, [rsp+270h+var_238]
0x140003019  lea     rcx, [rsp+270h+var_240]
0x14000301e  call    ?acquire@?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x140003023  lea     r8, [rsp+270h+var_230]; unsigned __int64 *
0x140003028  mov     [rsp+270h+var_230], 0
0x140003031  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140003036  call    ?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z; wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)
0x14000303b  mov     ebx, eax
0x14000303d  test    eax, eax
0x14000303f  jns     short loc_140003089
0x140003041  mov     rcx, [rbp+178h]; this
0x140003048  mov     r9d, eax; char *
0x14000304b  mov     edx, 66h ; 'f'; void *
0x140003050  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003055  mov     rcx, [rbp+178h]; this
0x14000305c  mov     r9d, ebx; char *
0x14000305f  mov     edx, 6Fh ; 'o'; void *
0x140003064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140003069  mov     r9d, ebx; char *
0x14000306c  mov     edx, 12Eh; void *
0x140003071  mov     rcx, [rbp+178h]; this
0x140003078  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000307d  lea     rcx, [rsp+270h+var_238]
0x140003082  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140003087  jmp     short loc_1400030B0
0x140003089  mov     rax, [rsp+270h+var_230]
0x14000308e  lea     rcx, ds:0[rax*4]
0x140003096  test    rcx, rcx
0x140003099  jz      short loc_1400030E0
0x14000309b  mov     [rdi], rcx
0x14000309e  mov     eax, [rcx]
0x1400030a0  inc     eax
0x1400030a2  mov     [rcx], eax
0x1400030a4  lea     rcx, [rsp+270h+var_238]
0x1400030a9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseMutex@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400030ae  xor     ebx, ebx
0x1400030b0  lea     rcx, [rsp+270h+var_240]
0x1400030b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400030ba  mov     eax, ebx
0x1400030bc  mov     rcx, [rbp+170h+var_10]
0x1400030c3  xor     rcx, rsp; StackCookie
0x1400030c6  call    __security_check_cookie
0x1400030cb  lea     r11, [rsp+270h+var_s0]
0x1400030d3  mov     rbx, [r11+20h]
0x1400030d7  mov     rdi, [r11+28h]
0x1400030db  mov     rsp, r11
0x1400030de  pop     rbp
0x1400030df  retn
0x1400030e0  mov     r8, rdi
0x1400030e3  lea     rdx, [rsp+270h+var_240]
0x1400030e8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1400030ed  call    ?MakeAndInitialize@?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@CAJPEBG$$QEAV?$unique_any_t@V?$mutex_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@3@PEAPEAV123@@Z
0x1400030f2  mov     ebx, eax
0x1400030f4  test    eax, eax
0x1400030f6  jns     short loc_1400030A4
0x1400030f8  mov     r9d, eax
0x1400030fb  mov     edx, 137h
0x140003100  jmp     loc_140003071
```
