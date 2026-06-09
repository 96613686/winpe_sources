# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800f1e8c`
- end: `0x1800f2028`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800f02e8`

## callees

- `0x1800b0008`
- `0x1800f01b0`
- `0x1800f0e34`
- `0x1800f1854`
- `0x1800f187c`
- `0x1800f1d64`
- `0x1800f1e8c`
- `0x1801178f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1f00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f1f00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800f1ef0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800f1f80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800f1ef0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800f1f80`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
0x1800f1e8c  mov     [rsp-8+arg_8], rbx
0x1800f1e91  mov     [rsp-8+arg_18], rdi
0x1800f1e96  push    rbp
0x1800f1e97  lea     rbp, [rsp-160h]
0x1800f1e9f  sub     rsp, 260h
0x1800f1ea6  mov     rax, cs:__security_cookie
0x1800f1ead  xor     rax, rsp
0x1800f1eb0  mov     [rbp+160h+var_10], rax
0x1800f1eb7  mov     rdi, r8
0x1800f1eba  mov     qword ptr [r8], 0
0x1800f1ec1  mov     r8, rcx; wchar_t *
0x1800f1ec4  mov     edx, 104h; unsigned __int64
0x1800f1ec9  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800f1ece  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800f1ed3  lea     r8, aP0; "_p0"
0x1800f1eda  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800f1edf  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800f1ee4  lea     r8, [rsp+260h+Name]; lpName
0x1800f1ee9  xor     edx, edx; bInheritHandle
0x1800f1eeb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800f1ef0  call    cs:__imp_OpenSemaphoreW
0x1800f1ef6  mov     [rsp+260h+var_230], rax
0x1800f1efb  test    rax, rax
0x1800f1efe  jnz     short loc_1800F1F27
0x1800f1f00  call    cs:__imp_GetLastError
0x1800f1f06  cmp     eax, 2
0x1800f1f09  jz      loc_1800F1FF6
0x1800f1f0f  mov     rcx, [rbp+168h]; this
0x1800f1f16  mov     edx, 0D0h; void *
0x1800f1f1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f1f20  mov     ebx, eax
0x1800f1f22  jmp     loc_1800F1FF8
0x1800f1f27  lea     rdx, [rsp+260h+var_23C]; int *
0x1800f1f2c  mov     [rsp+260h+var_23C], 0
0x1800f1f34  mov     rcx, rax; hHandle
0x1800f1f37  mov     [rsp+260h+var_240], 0; int
0x1800f1f3f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800f1f44  mov     ebx, eax
0x1800f1f46  test    eax, eax
0x1800f1f48  jns     short loc_1800F1F63
0x1800f1f4a  mov     rcx, [rbp+168h]; this
0x1800f1f51  mov     r9d, eax; char *
0x1800f1f54  mov     edx, 0D6h; void *
0x1800f1f59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1f5e  jmp     loc_1800F1FF8
0x1800f1f63  lea     r8, asc_18014A230; "h"
0x1800f1f6a  lea     rcx, [rsp+260h+Name]; wchar_t *
0x1800f1f6f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800f1f74  lea     r8, [rsp+260h+Name]; lpName
0x1800f1f79  xor     edx, edx; bInheritHandle
0x1800f1f7b  mov     ecx, 1F0003h; dwDesiredAccess
0x1800f1f80  call    cs:__imp_OpenSemaphoreW
0x1800f1f86  mov     [rsp+260h+var_238], rax
0x1800f1f8b  test    rax, rax
0x1800f1f8e  jnz     short loc_1800F1FAF
0x1800f1f90  mov     rcx, [rbp+168h]; this
0x1800f1f97  mov     edx, 0DCh; void *
0x1800f1f9c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f1fa1  mov     ebx, eax
0x1800f1fa3  lea     rcx, [rsp+260h+var_238]
0x1800f1fa8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800f1fad  jmp     short loc_1800F1FF8
0x1800f1faf  lea     rdx, [rsp+260h+var_240]; int *
0x1800f1fb4  mov     rcx, rax; hHandle
0x1800f1fb7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800f1fbc  mov     ebx, eax
0x1800f1fbe  test    eax, eax
0x1800f1fc0  jns     short loc_1800F1FD8
0x1800f1fc2  mov     rcx, [rbp+168h]; this
0x1800f1fc9  mov     r9d, eax; char *
0x1800f1fcc  mov     edx, 0DEh; void *
0x1800f1fd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f1fd6  jmp     short loc_1800F1FA3
0x1800f1fd8  lea     rcx, [rsp+260h+var_238]
0x1800f1fdd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800f1fe2  movsxd  rcx, [rsp+260h+var_240]
0x1800f1fe7  movsxd  rax, [rsp+260h+var_23C]
0x1800f1fec  shl     rcx, 1Fh
0x1800f1ff0  or      rcx, rax
0x1800f1ff3  mov     [rdi], rcx
0x1800f1ff6  xor     ebx, ebx
0x1800f1ff8  lea     rcx, [rsp+260h+var_230]
0x1800f1ffd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800f2002  mov     eax, ebx
0x1800f2004  mov     rcx, [rbp+160h+var_10]
0x1800f200b  xor     rcx, rsp; StackCookie
0x1800f200e  call    __security_check_cookie
0x1800f2013  lea     r11, [rsp+260h+var_s0]
0x1800f201b  mov     rbx, [r11+18h]
0x1800f201f  mov     rdi, [r11+28h]
0x1800f2023  mov     rsp, r11
0x1800f2026  pop     rbp
0x1800f2027  retn
```
