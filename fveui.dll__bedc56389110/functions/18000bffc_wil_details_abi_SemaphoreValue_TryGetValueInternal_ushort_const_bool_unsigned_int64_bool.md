# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bffc`
- end: `0x18000c198`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000bf88`

## callees

- `0x180001bb0`
- `0x1800047f0`
- `0x180009258`
- `0x18000b16c`
- `0x18000b18c`
- `0x18000b91c`
- `0x18000b978`
- `0x18000bffc`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18000c060`
- `KERNEL32!OpenSemaphoreW` at `0x18000c0f0`
- `KERNEL32!OpenSemaphoreW` at `0x18000c060`
- `KERNEL32!OpenSemaphoreW` at `0x18000c0f0`
- `KERNEL32!GetLastError` at `0x18000c070`
- `KERNEL32!GetLastError` at `0x18000c070`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  __int64 v12; // rdx
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
  StringCchCopyW(Name, 0x104u, a1);
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
0x18000bffc  mov     [rsp-8+arg_8], rbx
0x18000c001  mov     [rsp-8+arg_18], rdi
0x18000c006  push    rbp
0x18000c007  lea     rbp, [rsp-160h]
0x18000c00f  sub     rsp, 260h
0x18000c016  mov     rax, cs:__security_cookie
0x18000c01d  xor     rax, rsp
0x18000c020  mov     [rbp+160h+var_10], rax
0x18000c027  mov     rdi, r8
0x18000c02a  mov     qword ptr [r8], 0
0x18000c031  mov     r8, rcx; unsigned __int16 *
0x18000c034  mov     edx, 104h; unsigned __int64
0x18000c039  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000c03e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c043  lea     r8, aP0; "_p0"
0x18000c04a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000c04f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c054  lea     r8, [rsp+260h+Name]; lpName
0x18000c059  xor     edx, edx; bInheritHandle
0x18000c05b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c060  call    cs:__imp_OpenSemaphoreW
0x18000c066  mov     [rsp+260h+var_230], rax
0x18000c06b  test    rax, rax
0x18000c06e  jnz     short loc_18000C097
0x18000c070  call    cs:__imp_GetLastError
0x18000c076  cmp     eax, 2
0x18000c079  jz      loc_18000C166
0x18000c07f  mov     rcx, [rbp+168h]; this
0x18000c086  mov     edx, 0D0h; void *
0x18000c08b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c090  mov     ebx, eax
0x18000c092  jmp     loc_18000C168
0x18000c097  lea     rdx, [rsp+260h+var_23C]; int *
0x18000c09c  mov     [rsp+260h+var_23C], 0
0x18000c0a4  mov     rcx, rax; hHandle
0x18000c0a7  mov     [rsp+260h+var_240], 0; int
0x18000c0af  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c0b4  mov     ebx, eax
0x18000c0b6  test    eax, eax
0x18000c0b8  jns     short loc_18000C0D3
0x18000c0ba  mov     rcx, [rbp+168h]; this
0x18000c0c1  mov     r9d, eax; char *
0x18000c0c4  mov     edx, 0D6h; void *
0x18000c0c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c0ce  jmp     loc_18000C168
0x18000c0d3  lea     r8, asc_1800315B0; "h"
0x18000c0da  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000c0df  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c0e4  lea     r8, [rsp+260h+Name]; lpName
0x18000c0e9  xor     edx, edx; bInheritHandle
0x18000c0eb  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c0f0  call    cs:__imp_OpenSemaphoreW
0x18000c0f6  mov     [rsp+260h+var_238], rax
0x18000c0fb  test    rax, rax
0x18000c0fe  jnz     short loc_18000C11F
0x18000c100  mov     rcx, [rbp+168h]; this
0x18000c107  mov     edx, 0DCh; void *
0x18000c10c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c111  mov     ebx, eax
0x18000c113  lea     rcx, [rsp+260h+var_238]
0x18000c118  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c11d  jmp     short loc_18000C168
0x18000c11f  lea     rdx, [rsp+260h+var_240]; int *
0x18000c124  mov     rcx, rax; hHandle
0x18000c127  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c12c  mov     ebx, eax
0x18000c12e  test    eax, eax
0x18000c130  jns     short loc_18000C148
0x18000c132  mov     rcx, [rbp+168h]; this
0x18000c139  mov     r9d, eax; char *
0x18000c13c  mov     edx, 0DEh; void *
0x18000c141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c146  jmp     short loc_18000C113
0x18000c148  lea     rcx, [rsp+260h+var_238]
0x18000c14d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c152  movsxd  rcx, [rsp+260h+var_240]
0x18000c157  movsxd  rax, [rsp+260h+var_23C]
0x18000c15c  shl     rcx, 1Fh
0x18000c160  or      rcx, rax
0x18000c163  mov     [rdi], rcx
0x18000c166  xor     ebx, ebx
0x18000c168  lea     rcx, [rsp+260h+var_230]
0x18000c16d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c172  mov     eax, ebx
0x18000c174  mov     rcx, [rbp+160h+var_10]
0x18000c17b  xor     rcx, rsp; StackCookie
0x18000c17e  call    __security_check_cookie
0x18000c183  lea     r11, [rsp+260h+var_s0]
0x18000c18b  mov     rbx, [r11+18h]
0x18000c18f  mov     rdi, [r11+28h]
0x18000c193  mov     rsp, r11
0x18000c196  pop     rbp
0x18000c197  retn
```
