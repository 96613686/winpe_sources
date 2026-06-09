# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006f08`
- end: `0x1800070a4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800048a8`

## callees

- `0x1800023e0`
- `0x1800046b0`
- `0x180005788`
- `0x1800065f4`
- `0x180006614`
- `0x180006b40`
- `0x180006c24`
- `0x180006f08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006f6c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ffc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006f6c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ffc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f7c`

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
0x180006f08  mov     [rsp-8+arg_8], rbx
0x180006f0d  mov     [rsp-8+arg_18], rdi
0x180006f12  push    rbp
0x180006f13  lea     rbp, [rsp-160h]
0x180006f1b  sub     rsp, 260h
0x180006f22  mov     rax, cs:__security_cookie
0x180006f29  xor     rax, rsp
0x180006f2c  mov     [rbp+160h+var_10], rax
0x180006f33  mov     rdi, r8
0x180006f36  mov     qword ptr [r8], 0
0x180006f3d  mov     r8, rcx; unsigned __int16 *
0x180006f40  mov     edx, 104h; unsigned __int64
0x180006f45  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180006f4a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006f4f  lea     r8, aP0; "_p0"
0x180006f56  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180006f5b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006f60  lea     r8, [rsp+260h+Name]; lpName
0x180006f65  xor     edx, edx; bInheritHandle
0x180006f67  mov     ecx, 1F0003h; dwDesiredAccess
0x180006f6c  call    cs:__imp_OpenSemaphoreW
0x180006f72  mov     [rsp+260h+var_230], rax
0x180006f77  test    rax, rax
0x180006f7a  jnz     short loc_180006FA3
0x180006f7c  call    cs:__imp_GetLastError
0x180006f82  cmp     eax, 2
0x180006f85  jz      loc_180007072
0x180006f8b  mov     rcx, [rbp+168h]; this
0x180006f92  mov     edx, 0D0h; void *
0x180006f97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006f9c  mov     ebx, eax
0x180006f9e  jmp     loc_180007074
0x180006fa3  lea     rdx, [rsp+260h+var_23C]; int *
0x180006fa8  mov     [rsp+260h+var_23C], 0
0x180006fb0  mov     rcx, rax; hHandle
0x180006fb3  mov     [rsp+260h+var_240], 0; int
0x180006fbb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006fc0  mov     ebx, eax
0x180006fc2  test    eax, eax
0x180006fc4  jns     short loc_180006FDF
0x180006fc6  mov     rcx, [rbp+168h]; this
0x180006fcd  mov     r9d, eax; char *
0x180006fd0  mov     edx, 0D6h; void *
0x180006fd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006fda  jmp     loc_180007074
0x180006fdf  lea     r8, asc_1800B6DC8; "h"
0x180006fe6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180006feb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006ff0  lea     r8, [rsp+260h+Name]; lpName
0x180006ff5  xor     edx, edx; bInheritHandle
0x180006ff7  mov     ecx, 1F0003h; dwDesiredAccess
0x180006ffc  call    cs:__imp_OpenSemaphoreW
0x180007002  mov     [rsp+260h+var_238], rax
0x180007007  test    rax, rax
0x18000700a  jnz     short loc_18000702B
0x18000700c  mov     rcx, [rbp+168h]; this
0x180007013  mov     edx, 0DCh; void *
0x180007018  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000701d  mov     ebx, eax
0x18000701f  lea     rcx, [rsp+260h+var_238]
0x180007024  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007029  jmp     short loc_180007074
0x18000702b  lea     rdx, [rsp+260h+var_240]; int *
0x180007030  mov     rcx, rax; hHandle
0x180007033  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007038  mov     ebx, eax
0x18000703a  test    eax, eax
0x18000703c  jns     short loc_180007054
0x18000703e  mov     rcx, [rbp+168h]; this
0x180007045  mov     r9d, eax; char *
0x180007048  mov     edx, 0DEh; void *
0x18000704d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007052  jmp     short loc_18000701F
0x180007054  lea     rcx, [rsp+260h+var_238]
0x180007059  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000705e  movsxd  rcx, [rsp+260h+var_240]
0x180007063  movsxd  rax, [rsp+260h+var_23C]
0x180007068  shl     rcx, 1Fh
0x18000706c  or      rcx, rax
0x18000706f  mov     [rdi], rcx
0x180007072  xor     ebx, ebx
0x180007074  lea     rcx, [rsp+260h+var_230]
0x180007079  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000707e  mov     eax, ebx
0x180007080  mov     rcx, [rbp+160h+var_10]
0x180007087  xor     rcx, rsp; StackCookie
0x18000708a  call    __security_check_cookie
0x18000708f  lea     r11, [rsp+260h+var_s0]
0x180007097  mov     rbx, [r11+18h]
0x18000709b  mov     rdi, [r11+28h]
0x18000709f  mov     rsp, r11
0x1800070a2  pop     rbp
0x1800070a3  retn
```
