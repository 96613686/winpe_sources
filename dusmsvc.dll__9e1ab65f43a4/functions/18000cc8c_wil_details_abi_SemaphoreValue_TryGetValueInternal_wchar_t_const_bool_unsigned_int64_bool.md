# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000cc8c`
- end: `0x18000ce44`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000cc08`

## callees

- `0x180007c90`
- `0x18000aa54`
- `0x18000b79c`
- `0x18000c444`
- `0x18000c464`
- `0x18000c984`
- `0x18000ca00`
- `0x18000cc8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ccf0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cd8e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ccf0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cd8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cd00`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18000cc8c  mov     [rsp-8+arg_8], rbx
0x18000cc91  mov     [rsp-8+arg_18], rdi
0x18000cc96  push    rbp
0x18000cc97  lea     rbp, [rsp-160h]
0x18000cc9f  sub     rsp, 260h
0x18000cca6  mov     rax, cs:__security_cookie
0x18000ccad  xor     rax, rsp
0x18000ccb0  mov     [rbp+160h+var_10], rax
0x18000ccb7  mov     rdi, r8
0x18000ccba  mov     qword ptr [r8], 0
0x18000ccc1  mov     r8, rcx; wchar_t *
0x18000ccc4  mov     edx, 104h; unsigned __int64
0x18000ccc9  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000ccce  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ccd3  lea     r8, aP0; "_p0"
0x18000ccda  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000ccdf  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000cce4  lea     r8, [rsp+260h+Name]; lpName
0x18000cce9  xor     edx, edx; bInheritHandle
0x18000cceb  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ccf0  call    cs:__imp_OpenSemaphoreW
0x18000ccf6  mov     [rsp+260h+var_230], rax
0x18000ccfb  test    rax, rax
0x18000ccfe  jnz     short loc_18000CD2E
0x18000cd00  call    cs:__imp_GetLastError
0x18000cd06  cmp     eax, 2
0x18000cd09  jz      loc_18000CE12
0x18000cd0f  mov     rcx, [rbp+168h]; this
0x18000cd16  lea     r8, aWil; "wil"
0x18000cd1d  mov     edx, 0D0h; void *
0x18000cd22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cd27  mov     ebx, eax
0x18000cd29  jmp     loc_18000CE14
0x18000cd2e  lea     rdx, [rsp+260h+var_23C]; int *
0x18000cd33  mov     [rsp+260h+var_23C], 0
0x18000cd3b  mov     rcx, rax; hHandle
0x18000cd3e  mov     [rsp+260h+var_240], 0; int
0x18000cd46  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cd4b  mov     ebx, eax
0x18000cd4d  test    eax, eax
0x18000cd4f  jns     short loc_18000CD71
0x18000cd51  mov     rcx, [rbp+168h]; this
0x18000cd58  lea     r8, aWil; "wil"
0x18000cd5f  mov     r9d, eax; char *
0x18000cd62  mov     edx, 0D6h; void *
0x18000cd67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd6c  jmp     loc_18000CE14
0x18000cd71  lea     r8, asc_18004F8F0; "h"
0x18000cd78  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000cd7d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000cd82  lea     r8, [rsp+260h+Name]; lpName
0x18000cd87  xor     edx, edx; bInheritHandle
0x18000cd89  mov     ecx, 1F0003h; dwDesiredAccess
0x18000cd8e  call    cs:__imp_OpenSemaphoreW
0x18000cd94  mov     [rsp+260h+var_238], rax
0x18000cd99  test    rax, rax
0x18000cd9c  jnz     short loc_18000CDC4
0x18000cd9e  mov     rcx, [rbp+168h]; this
0x18000cda5  lea     r8, aWil; "wil"
0x18000cdac  mov     edx, 0DCh; void *
0x18000cdb1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cdb6  mov     ebx, eax
0x18000cdb8  lea     rcx, [rsp+260h+var_238]
0x18000cdbd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000cdc2  jmp     short loc_18000CE14
0x18000cdc4  lea     rdx, [rsp+260h+var_240]; int *
0x18000cdc9  mov     rcx, rax; hHandle
0x18000cdcc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cdd1  mov     ebx, eax
0x18000cdd3  test    eax, eax
0x18000cdd5  jns     short loc_18000CDF4
0x18000cdd7  mov     rcx, [rbp+168h]; this
0x18000cdde  lea     r8, aWil; "wil"
0x18000cde5  mov     r9d, eax; char *
0x18000cde8  mov     edx, 0DEh; void *
0x18000cded  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cdf2  jmp     short loc_18000CDB8
0x18000cdf4  lea     rcx, [rsp+260h+var_238]
0x18000cdf9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000cdfe  movsxd  rcx, [rsp+260h+var_240]
0x18000ce03  movsxd  rax, [rsp+260h+var_23C]
0x18000ce08  shl     rcx, 1Fh
0x18000ce0c  or      rcx, rax
0x18000ce0f  mov     [rdi], rcx
0x18000ce12  xor     ebx, ebx
0x18000ce14  lea     rcx, [rsp+260h+var_230]
0x18000ce19  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ce1e  mov     eax, ebx
0x18000ce20  mov     rcx, [rbp+160h+var_10]
0x18000ce27  xor     rcx, rsp; StackCookie
0x18000ce2a  call    __security_check_cookie
0x18000ce2f  lea     r11, [rsp+260h+var_s0]
0x18000ce37  mov     rbx, [r11+18h]
0x18000ce3b  mov     rdi, [r11+28h]
0x18000ce3f  mov     rsp, r11
0x18000ce42  pop     rbp
0x18000ce43  retn
```
