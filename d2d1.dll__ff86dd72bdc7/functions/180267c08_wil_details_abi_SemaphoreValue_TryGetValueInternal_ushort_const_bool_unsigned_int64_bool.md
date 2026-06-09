# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180267c08`
- end: `0x180267da4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180267b94`

## callees

- `0x1801d506c`
- `0x18020b19c`
- `0x1802373b0`
- `0x18025b100`
- `0x180264db8`
- `0x18026605c`
- `0x180267508`
- `0x180267c08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180267c6c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180267cfc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180267c6c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180267cfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180267c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180267c7c`

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
0x180267c08  mov     [rsp-8+arg_8], rbx
0x180267c0d  mov     [rsp-8+arg_18], rdi
0x180267c12  push    rbp
0x180267c13  lea     rbp, [rsp-160h]
0x180267c1b  sub     rsp, 260h
0x180267c22  mov     rax, cs:__security_cookie
0x180267c29  xor     rax, rsp
0x180267c2c  mov     [rbp+160h+var_10], rax
0x180267c33  mov     rdi, r8
0x180267c36  mov     qword ptr [r8], 0
0x180267c3d  mov     r8, rcx; unsigned __int16 *
0x180267c40  mov     edx, 104h; unsigned __int64
0x180267c45  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180267c4a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180267c4f  lea     r8, aP0; "_p0"
0x180267c56  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180267c5b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180267c60  lea     r8, [rsp+260h+Name]; lpName
0x180267c65  xor     edx, edx; bInheritHandle
0x180267c67  mov     ecx, 1F0003h; dwDesiredAccess
0x180267c6c  call    cs:__imp_OpenSemaphoreW
0x180267c72  mov     [rsp+260h+var_230], rax
0x180267c77  test    rax, rax
0x180267c7a  jnz     short loc_180267CA3
0x180267c7c  call    cs:__imp_GetLastError
0x180267c82  cmp     eax, 2
0x180267c85  jz      loc_180267D72
0x180267c8b  mov     rcx, [rbp+168h]; this
0x180267c92  mov     edx, 0D0h; void *
0x180267c97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180267c9c  mov     ebx, eax
0x180267c9e  jmp     loc_180267D74
0x180267ca3  lea     rdx, [rsp+260h+var_23C]; int *
0x180267ca8  mov     [rsp+260h+var_23C], 0
0x180267cb0  mov     rcx, rax; hHandle
0x180267cb3  mov     [rsp+260h+var_240], 0; int
0x180267cbb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180267cc0  mov     ebx, eax
0x180267cc2  test    eax, eax
0x180267cc4  jns     short loc_180267CDF
0x180267cc6  mov     rcx, [rbp+168h]; this
0x180267ccd  mov     r9d, eax; char *
0x180267cd0  mov     edx, 0D6h; void *
0x180267cd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180267cda  jmp     loc_180267D74
0x180267cdf  lea     r8, asc_1803E9870; "h"
0x180267ce6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180267ceb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180267cf0  lea     r8, [rsp+260h+Name]; lpName
0x180267cf5  xor     edx, edx; bInheritHandle
0x180267cf7  mov     ecx, 1F0003h; dwDesiredAccess
0x180267cfc  call    cs:__imp_OpenSemaphoreW
0x180267d02  mov     [rsp+260h+var_238], rax
0x180267d07  test    rax, rax
0x180267d0a  jnz     short loc_180267D2B
0x180267d0c  mov     rcx, [rbp+168h]; this
0x180267d13  mov     edx, 0DCh; void *
0x180267d18  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180267d1d  mov     ebx, eax
0x180267d1f  lea     rcx, [rsp+260h+var_238]
0x180267d24  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180267d29  jmp     short loc_180267D74
0x180267d2b  lea     rdx, [rsp+260h+var_240]; int *
0x180267d30  mov     rcx, rax; hHandle
0x180267d33  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180267d38  mov     ebx, eax
0x180267d3a  test    eax, eax
0x180267d3c  jns     short loc_180267D54
0x180267d3e  mov     rcx, [rbp+168h]; this
0x180267d45  mov     r9d, eax; char *
0x180267d48  mov     edx, 0DEh; void *
0x180267d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180267d52  jmp     short loc_180267D1F
0x180267d54  lea     rcx, [rsp+260h+var_238]
0x180267d59  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180267d5e  movsxd  rcx, [rsp+260h+var_240]
0x180267d63  movsxd  rax, [rsp+260h+var_23C]
0x180267d68  shl     rcx, 1Fh
0x180267d6c  or      rcx, rax
0x180267d6f  mov     [rdi], rcx
0x180267d72  xor     ebx, ebx
0x180267d74  lea     rcx, [rsp+260h+var_230]
0x180267d79  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180267d7e  mov     eax, ebx
0x180267d80  mov     rcx, [rbp+160h+var_10]
0x180267d87  xor     rcx, rsp; StackCookie
0x180267d8a  call    __security_check_cookie
0x180267d8f  lea     r11, [rsp+260h+var_s0]
0x180267d97  mov     rbx, [r11+18h]
0x180267d9b  mov     rdi, [r11+28h]
0x180267d9f  mov     rsp, r11
0x180267da2  pop     rbp
0x180267da3  retn
```
