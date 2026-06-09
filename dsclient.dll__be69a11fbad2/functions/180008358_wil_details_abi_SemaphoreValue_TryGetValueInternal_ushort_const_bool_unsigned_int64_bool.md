# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008358`
- end: `0x1800084ef`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800082e4`

## callees

- `0x18000499c`
- `0x180005e5c`
- `0x180007928`
- `0x180007948`
- `0x180007df4`
- `0x180007e40`
- `0x180008358`
- `0x180009950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083c7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800083b7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008447`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800083b7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008447`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v24; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v22);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v19);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180008358  mov     [rsp-8+arg_8], rbx
0x18000835d  mov     [rsp-8+arg_18], rdi
0x180008362  push    rbp
0x180008363  lea     rbp, [rsp-160h]
0x18000836b  sub     rsp, 260h
0x180008372  mov     rax, cs:__security_cookie
0x180008379  xor     rax, rsp
0x18000837c  mov     [rbp+160h+var_10], rax
0x180008383  mov     rdi, r8
0x180008386  mov     qword ptr [r8], 0
0x18000838d  mov     r8, rcx; unsigned __int16 *
0x180008390  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180008395  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000839a  lea     r8, aP0; "_p0"
0x1800083a1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800083a6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800083ab  lea     r8, [rsp+260h+Name]; lpName
0x1800083b0  xor     edx, edx; bInheritHandle
0x1800083b2  mov     ecx, 1F0003h; dwDesiredAccess
0x1800083b7  call    cs:__imp_OpenSemaphoreW
0x1800083bd  mov     [rsp+260h+var_230], rax
0x1800083c2  test    rax, rax
0x1800083c5  jnz     short loc_1800083EE
0x1800083c7  call    cs:__imp_GetLastError
0x1800083cd  cmp     eax, 2
0x1800083d0  jz      loc_1800084BD
0x1800083d6  mov     rcx, [rbp+168h]; this
0x1800083dd  mov     edx, 0D0h; void *
0x1800083e2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800083e7  mov     ebx, eax
0x1800083e9  jmp     loc_1800084BF
0x1800083ee  lea     rdx, [rsp+260h+var_23C]; int *
0x1800083f3  mov     [rsp+260h+var_23C], 0
0x1800083fb  mov     rcx, rax; hHandle
0x1800083fe  mov     [rsp+260h+var_240], 0; int
0x180008406  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000840b  mov     ebx, eax
0x18000840d  test    eax, eax
0x18000840f  jns     short loc_18000842A
0x180008411  mov     rcx, [rbp+168h]; this
0x180008418  mov     r9d, eax; char *
0x18000841b  mov     edx, 0D6h; void *
0x180008420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008425  jmp     loc_1800084BF
0x18000842a  lea     r8, asc_18000C878; "h"
0x180008431  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180008436  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000843b  lea     r8, [rsp+260h+Name]; lpName
0x180008440  xor     edx, edx; bInheritHandle
0x180008442  mov     ecx, 1F0003h; dwDesiredAccess
0x180008447  call    cs:__imp_OpenSemaphoreW
0x18000844d  mov     [rsp+260h+var_238], rax
0x180008452  test    rax, rax
0x180008455  jnz     short loc_180008476
0x180008457  mov     rcx, [rbp+168h]; this
0x18000845e  mov     edx, 0DCh; void *
0x180008463  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008468  mov     ebx, eax
0x18000846a  lea     rcx, [rsp+260h+var_238]
0x18000846f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008474  jmp     short loc_1800084BF
0x180008476  lea     rdx, [rsp+260h+var_240]; int *
0x18000847b  mov     rcx, rax; hHandle
0x18000847e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008483  mov     ebx, eax
0x180008485  test    eax, eax
0x180008487  jns     short loc_18000849F
0x180008489  mov     rcx, [rbp+168h]; this
0x180008490  mov     r9d, eax; char *
0x180008493  mov     edx, 0DEh; void *
0x180008498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000849d  jmp     short loc_18000846A
0x18000849f  lea     rcx, [rsp+260h+var_238]
0x1800084a4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800084a9  movsxd  rcx, [rsp+260h+var_240]
0x1800084ae  movsxd  rax, [rsp+260h+var_23C]
0x1800084b3  shl     rcx, 1Fh
0x1800084b7  or      rcx, rax
0x1800084ba  mov     [rdi], rcx
0x1800084bd  xor     ebx, ebx
0x1800084bf  lea     rcx, [rsp+260h+var_230]
0x1800084c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800084c9  mov     eax, ebx
0x1800084cb  mov     rcx, [rbp+160h+var_10]
0x1800084d2  xor     rcx, rsp; StackCookie
0x1800084d5  call    __security_check_cookie
0x1800084da  lea     r11, [rsp+260h+var_s0]
0x1800084e2  mov     rbx, [r11+18h]
0x1800084e6  mov     rdi, [r11+28h]
0x1800084ea  mov     rsp, r11
0x1800084ed  pop     rbp
0x1800084ee  retn
```
