# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18005d24c`
- end: `0x18005d3f6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18005d1d8`

## callees

- `0x18000df90`
- `0x180058f90`
- `0x18005a718`
- `0x18005c5bc`
- `0x18005c5dc`
- `0x18005cca4`
- `0x18005cd20`
- `0x18005d24c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005d2b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005d347`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005d2b0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005d347`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d2c0`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  unsigned int v11; // r8d
  HANDLE v12; // rax
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18005d24c  mov     [rsp-8+arg_8], rbx
0x18005d251  mov     [rsp-8+arg_18], rdi
0x18005d256  push    rbp
0x18005d257  lea     rbp, [rsp-160h]
0x18005d25f  sub     rsp, 260h
0x18005d266  mov     rax, cs:__security_cookie
0x18005d26d  xor     rax, rsp
0x18005d270  mov     [rbp+160h+var_10], rax
0x18005d277  mov     rdi, r8
0x18005d27a  mov     qword ptr [r8], 0
0x18005d281  mov     r8, rcx; unsigned __int16 *
0x18005d284  mov     edx, 104h; unsigned __int64
0x18005d289  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18005d28e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005d293  lea     r8, aP0; "_p0"
0x18005d29a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18005d29f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005d2a4  lea     r8, [rsp+260h+Name]; lpName
0x18005d2a9  xor     edx, edx; bInheritHandle
0x18005d2ab  mov     ecx, 1F0003h; dwDesiredAccess
0x18005d2b0  call    cs:__imp_OpenSemaphoreW
0x18005d2b6  mov     [rsp+260h+var_230], rax
0x18005d2bb  test    rax, rax
0x18005d2be  jnz     short loc_18005D2EE
0x18005d2c0  call    cs:__imp_GetLastError
0x18005d2c6  cmp     eax, 2
0x18005d2c9  jz      loc_18005D3C4
0x18005d2cf  mov     rcx, [rbp+168h]; this
0x18005d2d6  lea     r8, aWil; "wil"
0x18005d2dd  mov     edx, 0D0h; void *
0x18005d2e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005d2e7  mov     ebx, eax
0x18005d2e9  jmp     loc_18005D3C6
0x18005d2ee  lea     rdx, [rsp+260h+var_23C]; int *
0x18005d2f3  mov     [rsp+260h+var_23C], 0
0x18005d2fb  mov     rcx, rax; hHandle
0x18005d2fe  mov     [rsp+260h+var_240], 0; int
0x18005d306  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005d30b  mov     ebx, eax
0x18005d30d  test    eax, eax
0x18005d30f  jns     short loc_18005D32A
0x18005d311  mov     rcx, [rbp+168h]; this
0x18005d318  mov     r9d, eax; char *
0x18005d31b  mov     edx, 0D6h; void *
0x18005d320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d325  jmp     loc_18005D3C6
0x18005d32a  lea     r8, asc_180111D60; "h"
0x18005d331  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18005d336  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005d33b  lea     r8, [rsp+260h+Name]; lpName
0x18005d340  xor     edx, edx; bInheritHandle
0x18005d342  mov     ecx, 1F0003h; dwDesiredAccess
0x18005d347  call    cs:__imp_OpenSemaphoreW
0x18005d34d  mov     [rsp+260h+var_238], rax
0x18005d352  test    rax, rax
0x18005d355  jnz     short loc_18005D37D
0x18005d357  mov     rcx, [rbp+168h]; this
0x18005d35e  lea     r8, aWil; "wil"
0x18005d365  mov     edx, 0DCh; void *
0x18005d36a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005d36f  mov     ebx, eax
0x18005d371  lea     rcx, [rsp+260h+var_238]
0x18005d376  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005d37b  jmp     short loc_18005D3C6
0x18005d37d  lea     rdx, [rsp+260h+var_240]; int *
0x18005d382  mov     rcx, rax; hHandle
0x18005d385  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005d38a  mov     ebx, eax
0x18005d38c  test    eax, eax
0x18005d38e  jns     short loc_18005D3A6
0x18005d390  mov     rcx, [rbp+168h]; this
0x18005d397  mov     r9d, eax; char *
0x18005d39a  mov     edx, 0DEh; void *
0x18005d39f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d3a4  jmp     short loc_18005D371
0x18005d3a6  lea     rcx, [rsp+260h+var_238]
0x18005d3ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005d3b0  movsxd  rcx, [rsp+260h+var_240]
0x18005d3b5  movsxd  rax, [rsp+260h+var_23C]
0x18005d3ba  shl     rcx, 1Fh
0x18005d3be  or      rcx, rax
0x18005d3c1  mov     [rdi], rcx
0x18005d3c4  xor     ebx, ebx
0x18005d3c6  lea     rcx, [rsp+260h+var_230]
0x18005d3cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005d3d0  mov     eax, ebx
0x18005d3d2  mov     rcx, [rbp+160h+var_10]
0x18005d3d9  xor     rcx, rsp; StackCookie
0x18005d3dc  call    __security_check_cookie
0x18005d3e1  lea     r11, [rsp+260h+var_s0]
0x18005d3e9  mov     rbx, [r11+18h]
0x18005d3ed  mov     rdi, [r11+28h]
0x18005d3f1  mov     rsp, r11
0x18005d3f4  pop     rbp
0x18005d3f5  retn
```
