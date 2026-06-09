# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180229a90`
- end: `0x180229c3a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180229a0c`

## callees

- `0x1801251ec`
- `0x180212490`
- `0x180226608`
- `0x1802278ec`
- `0x180228ecc`
- `0x180228eec`
- `0x18022956c`
- `0x180229a90`

## import_xrefs

- `kernel32!GetLastError` at `0x180229b04`
- `kernel32!GetLastError` at `0x180229b04`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180229af4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180229b8b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180229af4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180229b8b`

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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180229a90  mov     [rsp-8+arg_8], rbx
0x180229a95  mov     [rsp-8+arg_18], rdi
0x180229a9a  push    rbp
0x180229a9b  lea     rbp, [rsp-160h]
0x180229aa3  sub     rsp, 260h
0x180229aaa  mov     rax, cs:__security_cookie
0x180229ab1  xor     rax, rsp
0x180229ab4  mov     [rbp+160h+var_10], rax
0x180229abb  mov     rdi, r8
0x180229abe  mov     qword ptr [r8], 0
0x180229ac5  mov     r8, rcx; wchar_t *
0x180229ac8  mov     edx, 104h; unsigned __int64
0x180229acd  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180229ad2  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180229ad7  lea     r8, aP0; "_p0"
0x180229ade  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180229ae3  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180229ae8  lea     r8, [rsp+260h+Name]; lpName
0x180229aed  xor     edx, edx; bInheritHandle
0x180229aef  mov     ecx, 1F0003h; dwDesiredAccess
0x180229af4  call    cs:__imp_OpenSemaphoreW
0x180229afa  mov     [rsp+260h+var_230], rax
0x180229aff  test    rax, rax
0x180229b02  jnz     short loc_180229B2B
0x180229b04  call    cs:__imp_GetLastError
0x180229b0a  cmp     eax, 2
0x180229b0d  jz      loc_180229C08
0x180229b13  mov     rcx, [rbp+168h]; this
0x180229b1a  mov     edx, 0D0h; void *
0x180229b1f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180229b24  mov     ebx, eax
0x180229b26  jmp     loc_180229C0A
0x180229b2b  lea     rdx, [rsp+260h+var_23C]; int *
0x180229b30  mov     [rsp+260h+var_23C], 0
0x180229b38  mov     rcx, rax; hHandle
0x180229b3b  mov     [rsp+260h+var_240], 0; int
0x180229b43  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180229b48  mov     ebx, eax
0x180229b4a  test    eax, eax
0x180229b4c  jns     short loc_180229B6E
0x180229b4e  mov     rcx, [rbp+168h]; this
0x180229b55  lea     r8, aWil; "wil"
0x180229b5c  mov     r9d, eax; char *
0x180229b5f  mov     edx, 0D6h; void *
0x180229b64  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180229b69  jmp     loc_180229C0A
0x180229b6e  lea     r8, asc_180408BB8; "h"
0x180229b75  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180229b7a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180229b7f  lea     r8, [rsp+260h+Name]; lpName
0x180229b84  xor     edx, edx; bInheritHandle
0x180229b86  mov     ecx, 1F0003h; dwDesiredAccess
0x180229b8b  call    cs:__imp_OpenSemaphoreW
0x180229b91  mov     [rsp+260h+var_238], rax
0x180229b96  test    rax, rax
0x180229b99  jnz     short loc_180229BBA
0x180229b9b  mov     rcx, [rbp+168h]; this
0x180229ba2  mov     edx, 0DCh; void *
0x180229ba7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180229bac  mov     ebx, eax
0x180229bae  lea     rcx, [rsp+260h+var_238]
0x180229bb3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180229bb8  jmp     short loc_180229C0A
0x180229bba  lea     rdx, [rsp+260h+var_240]; int *
0x180229bbf  mov     rcx, rax; hHandle
0x180229bc2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180229bc7  mov     ebx, eax
0x180229bc9  test    eax, eax
0x180229bcb  jns     short loc_180229BEA
0x180229bcd  mov     rcx, [rbp+168h]; this
0x180229bd4  lea     r8, aWil; "wil"
0x180229bdb  mov     r9d, eax; char *
0x180229bde  mov     edx, 0DEh; void *
0x180229be3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180229be8  jmp     short loc_180229BAE
0x180229bea  lea     rcx, [rsp+260h+var_238]
0x180229bef  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180229bf4  movsxd  rcx, [rsp+260h+var_240]
0x180229bf9  movsxd  rax, [rsp+260h+var_23C]
0x180229bfe  shl     rcx, 1Fh
0x180229c02  or      rcx, rax
0x180229c05  mov     [rdi], rcx
0x180229c08  xor     ebx, ebx
0x180229c0a  lea     rcx, [rsp+260h+var_230]
0x180229c0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180229c14  mov     eax, ebx
0x180229c16  mov     rcx, [rbp+160h+var_10]
0x180229c1d  xor     rcx, rsp; StackCookie
0x180229c20  call    __security_check_cookie
0x180229c25  lea     r11, [rsp+260h+var_s0]
0x180229c2d  mov     rbx, [r11+18h]
0x180229c31  mov     rdi, [r11+28h]
0x180229c35  mov     rsp, r11
0x180229c38  pop     rbp
0x180229c39  retn
```
