# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180013b68`
- end: `0x180013d04`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000fb50`

## callees

- `0x18000a590`
- `0x18000ab30`
- `0x18000e440`
- `0x18000faf8`
- `0x1800108dc`
- `0x180013104`
- `0x180013ab8`
- `0x180013b68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013bcc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013c5c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013bcc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180013c5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013bdc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x180013b68  mov     [rsp-8+arg_8], rbx
0x180013b6d  mov     [rsp-8+arg_18], rdi
0x180013b72  push    rbp
0x180013b73  lea     rbp, [rsp-160h]
0x180013b7b  sub     rsp, 260h
0x180013b82  mov     rax, cs:__security_cookie
0x180013b89  xor     rax, rsp
0x180013b8c  mov     [rbp+160h+var_10], rax
0x180013b93  mov     rdi, r8
0x180013b96  mov     qword ptr [r8], 0
0x180013b9d  mov     r8, rcx; unsigned __int16 *
0x180013ba0  mov     edx, 104h; unsigned __int64
0x180013ba5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180013baa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013baf  lea     r8, aP0; "_p0"
0x180013bb6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180013bbb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013bc0  lea     r8, [rsp+260h+Name]; lpName
0x180013bc5  xor     edx, edx; bInheritHandle
0x180013bc7  mov     ecx, 1F0003h; dwDesiredAccess
0x180013bcc  call    cs:__imp_OpenSemaphoreW
0x180013bd2  mov     [rsp+260h+var_230], rax
0x180013bd7  test    rax, rax
0x180013bda  jnz     short loc_180013C03
0x180013bdc  call    cs:__imp_GetLastError
0x180013be2  cmp     eax, 2
0x180013be5  jz      loc_180013CD2
0x180013beb  mov     rcx, [rbp+168h]; this
0x180013bf2  mov     edx, 0D0h; void *
0x180013bf7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013bfc  mov     ebx, eax
0x180013bfe  jmp     loc_180013CD4
0x180013c03  lea     rdx, [rsp+260h+var_23C]; int *
0x180013c08  mov     [rsp+260h+var_23C], 0
0x180013c10  mov     rcx, rax; hHandle
0x180013c13  mov     [rsp+260h+var_240], 0; int
0x180013c1b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180013c20  mov     ebx, eax
0x180013c22  test    eax, eax
0x180013c24  jns     short loc_180013C3F
0x180013c26  mov     rcx, [rbp+168h]; this
0x180013c2d  mov     r9d, eax; char *
0x180013c30  mov     edx, 0D6h; void *
0x180013c35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013c3a  jmp     loc_180013CD4
0x180013c3f  lea     r8, asc_18002FF90; "h"
0x180013c46  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180013c4b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180013c50  lea     r8, [rsp+260h+Name]; lpName
0x180013c55  xor     edx, edx; bInheritHandle
0x180013c57  mov     ecx, 1F0003h; dwDesiredAccess
0x180013c5c  call    cs:__imp_OpenSemaphoreW
0x180013c62  mov     [rsp+260h+var_238], rax
0x180013c67  test    rax, rax
0x180013c6a  jnz     short loc_180013C8B
0x180013c6c  mov     rcx, [rbp+168h]; this
0x180013c73  mov     edx, 0DCh; void *
0x180013c78  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180013c7d  mov     ebx, eax
0x180013c7f  lea     rcx, [rsp+260h+var_238]
0x180013c84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013c89  jmp     short loc_180013CD4
0x180013c8b  lea     rdx, [rsp+260h+var_240]; int *
0x180013c90  mov     rcx, rax; hHandle
0x180013c93  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180013c98  mov     ebx, eax
0x180013c9a  test    eax, eax
0x180013c9c  jns     short loc_180013CB4
0x180013c9e  mov     rcx, [rbp+168h]; this
0x180013ca5  mov     r9d, eax; char *
0x180013ca8  mov     edx, 0DEh; void *
0x180013cad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013cb2  jmp     short loc_180013C7F
0x180013cb4  lea     rcx, [rsp+260h+var_238]
0x180013cb9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013cbe  movsxd  rcx, [rsp+260h+var_240]
0x180013cc3  movsxd  rax, [rsp+260h+var_23C]
0x180013cc8  shl     rcx, 1Fh
0x180013ccc  or      rcx, rax
0x180013ccf  mov     [rdi], rcx
0x180013cd2  xor     ebx, ebx
0x180013cd4  lea     rcx, [rsp+260h+var_230]
0x180013cd9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180013cde  mov     eax, ebx
0x180013ce0  mov     rcx, [rbp+160h+var_10]
0x180013ce7  xor     rcx, rsp; StackCookie
0x180013cea  call    __security_check_cookie
0x180013cef  lea     r11, [rsp+260h+var_s0]
0x180013cf7  mov     rbx, [r11+18h]
0x180013cfb  mov     rdi, [r11+28h]
0x180013cff  mov     rsp, r11
0x180013d02  pop     rbp
0x180013d03  retn
```
