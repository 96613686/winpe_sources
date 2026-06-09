# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000e57c`
- end: `0x18000e74a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `462`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000e498`

## callees

- `0x180006330`
- `0x180008cb4`
- `0x18000ac44`
- `0x18000cc14`
- `0x18000cc34`
- `0x18000de7c`
- `0x18000df08`
- `0x18000e57c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e5e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e688`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e5e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  wil::details *v10; // rax
  const char *v11; // r9
  void *v12; // rdx
  int v13; // eax
  void *v14; // rdx
  void *v15; // rdx
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v19; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v20; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v20 = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_12;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v10 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v10;
    if ( !v10 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v11);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v19,
        v12);
      goto LABEL_12;
    }
    v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v17);
    LastError = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v17);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v19,
        v15);
      goto LABEL_12;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v19,
      v14);
    *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  if ( GetLastError() == 2 )
    goto LABEL_11;
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v20,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x18000e57c  mov     [rsp-8+arg_8], rbx
0x18000e581  push    rbp
0x18000e582  push    rdi
0x18000e583  push    r14
0x18000e585  lea     rbp, [rsp-160h]
0x18000e58d  sub     rsp, 260h
0x18000e594  mov     rax, cs:__security_cookie
0x18000e59b  xor     rax, rsp
0x18000e59e  mov     [rbp+170h+var_20], rax
0x18000e5a5  mov     rdi, r8
0x18000e5a8  mov     qword ptr [r8], 0
0x18000e5af  mov     r8, rcx; unsigned __int16 *
0x18000e5b2  mov     r14d, 104h
0x18000e5b8  mov     edx, r14d; unsigned __int64
0x18000e5bb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e5c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e5c5  lea     r8, aP0; "_p0"
0x18000e5cc  mov     edx, r14d; unsigned __int64
0x18000e5cf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e5d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e5d9  lea     r8, [rsp+270h+Name]; lpName
0x18000e5de  xor     edx, edx; bInheritHandle
0x18000e5e0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e5e5  call    cs:__imp_OpenSemaphoreW
0x18000e5eb  mov     [rsp+270h+var_240], rax
0x18000e5f0  test    rax, rax
0x18000e5f3  jnz     short loc_18000E624
0x18000e5f5  call    cs:__imp_GetLastError
0x18000e5fb  cmp     eax, 2
0x18000e5fe  jnz     short loc_18000E605
0x18000e600  jmp     loc_18000E719
0x18000e605  mov     rcx, [rbp+178h]; this
0x18000e60c  lea     r8, aWil; "wil"
0x18000e613  mov     edx, 0D0h; void *
0x18000e618  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e61d  mov     ebx, eax
0x18000e61f  jmp     loc_18000E71B
0x18000e624  mov     [rsp+270h+var_24C], 0
0x18000e62c  mov     [rsp+270h+var_250], 0; int
0x18000e634  lea     rdx, [rsp+270h+var_24C]; int *
0x18000e639  mov     rcx, rax; hHandle
0x18000e63c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e641  mov     ebx, eax
0x18000e643  test    eax, eax
0x18000e645  jns     short loc_18000E668
0x18000e647  mov     rcx, [rbp+178h]; this
0x18000e64e  mov     r9d, eax; char *
0x18000e651  lea     r8, aWil; "wil"
0x18000e658  mov     edx, 0D6h; void *
0x18000e65d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e662  nop
0x18000e663  jmp     loc_18000E71B
0x18000e668  lea     r8, asc_180024AC0; "h"
0x18000e66f  mov     rdx, r14; unsigned __int64
0x18000e672  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e677  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e67c  lea     r8, [rsp+270h+Name]; lpName
0x18000e681  xor     edx, edx; bInheritHandle
0x18000e683  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e688  call    cs:__imp_OpenSemaphoreW
0x18000e68e  mov     [rsp+270h+var_248], rax
0x18000e693  test    rax, rax
0x18000e696  jnz     short loc_18000E6BF
0x18000e698  mov     rcx, [rbp+178h]; this
0x18000e69f  lea     r8, aWil; "wil"
0x18000e6a6  mov     edx, 0DCh; void *
0x18000e6ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e6b0  mov     ebx, eax
0x18000e6b2  lea     rcx, [rsp+270h+var_248]
0x18000e6b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e6bc  nop
0x18000e6bd  jmp     short loc_18000E71B
0x18000e6bf  lea     rdx, [rsp+270h+var_250]; int *
0x18000e6c4  mov     rcx, rax; hHandle
0x18000e6c7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e6cc  mov     ebx, eax
0x18000e6ce  test    eax, eax
0x18000e6d0  jns     short loc_18000E6FB
0x18000e6d2  mov     rcx, [rbp+178h]; this
0x18000e6d9  mov     r9d, eax; char *
0x18000e6dc  lea     r8, aWil; "wil"
0x18000e6e3  mov     edx, 0DEh; void *
0x18000e6e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e6ed  nop
0x18000e6ee  lea     rcx, [rsp+270h+var_248]
0x18000e6f3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e6f8  nop
0x18000e6f9  jmp     short loc_18000E71B
0x18000e6fb  lea     rcx, [rsp+270h+var_248]
0x18000e700  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e705  movsxd  rcx, [rsp+270h+var_250]
0x18000e70a  shl     rcx, 1Fh
0x18000e70e  movsxd  rax, [rsp+270h+var_24C]
0x18000e713  or      rcx, rax
0x18000e716  mov     [rdi], rcx
0x18000e719  xor     ebx, ebx
0x18000e71b  lea     rcx, [rsp+270h+var_240]
0x18000e720  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e725  mov     eax, ebx
0x18000e727  mov     rcx, [rbp+170h+var_20]
0x18000e72e  xor     rcx, rsp; StackCookie
0x18000e731  call    __security_check_cookie
0x18000e736  mov     rbx, [rsp+270h+arg_8]
0x18000e73e  add     rsp, 260h
0x18000e745  pop     r14
0x18000e747  pop     rdi
0x18000e748  pop     rbp
0x18000e749  retn
```
