# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c560`
- end: `0x18000c6fc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800079a8`

## callees

- `0x18000601c`
- `0x180007818`
- `0x180009d94`
- `0x18000bd3c`
- `0x18000bd5c`
- `0x18000c4ec`
- `0x18000c560`
- `0x18002b960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c5c4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c654`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c5c4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000c654`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5d4`

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
0x18000c560  mov     [rsp-8+arg_8], rbx
0x18000c565  mov     [rsp-8+arg_18], rdi
0x18000c56a  push    rbp
0x18000c56b  lea     rbp, [rsp-160h]
0x18000c573  sub     rsp, 260h
0x18000c57a  mov     rax, cs:__security_cookie
0x18000c581  xor     rax, rsp
0x18000c584  mov     [rbp+160h+var_10], rax
0x18000c58b  mov     rdi, r8
0x18000c58e  mov     qword ptr [r8], 0
0x18000c595  mov     r8, rcx; unsigned __int16 *
0x18000c598  mov     edx, 104h; unsigned __int64
0x18000c59d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000c5a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000c5a7  lea     r8, aP0; "_p0"
0x18000c5ae  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000c5b3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c5b8  lea     r8, [rsp+260h+Name]; lpName
0x18000c5bd  xor     edx, edx; bInheritHandle
0x18000c5bf  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c5c4  call    cs:__imp_OpenSemaphoreW
0x18000c5ca  mov     [rsp+260h+var_230], rax
0x18000c5cf  test    rax, rax
0x18000c5d2  jnz     short loc_18000C5FB
0x18000c5d4  call    cs:__imp_GetLastError
0x18000c5da  cmp     eax, 2
0x18000c5dd  jz      loc_18000C6CA
0x18000c5e3  mov     rcx, [rbp+168h]; this
0x18000c5ea  mov     edx, 0D0h; void *
0x18000c5ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c5f4  mov     ebx, eax
0x18000c5f6  jmp     loc_18000C6CC
0x18000c5fb  lea     rdx, [rsp+260h+var_23C]; int *
0x18000c600  mov     [rsp+260h+var_23C], 0
0x18000c608  mov     rcx, rax; hHandle
0x18000c60b  mov     [rsp+260h+var_240], 0; int
0x18000c613  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c618  mov     ebx, eax
0x18000c61a  test    eax, eax
0x18000c61c  jns     short loc_18000C637
0x18000c61e  mov     rcx, [rbp+168h]; this
0x18000c625  mov     r9d, eax; char *
0x18000c628  mov     edx, 0D6h; void *
0x18000c62d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c632  jmp     loc_18000C6CC
0x18000c637  lea     r8, asc_18002F988; "h"
0x18000c63e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000c643  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000c648  lea     r8, [rsp+260h+Name]; lpName
0x18000c64d  xor     edx, edx; bInheritHandle
0x18000c64f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000c654  call    cs:__imp_OpenSemaphoreW
0x18000c65a  mov     [rsp+260h+var_238], rax
0x18000c65f  test    rax, rax
0x18000c662  jnz     short loc_18000C683
0x18000c664  mov     rcx, [rbp+168h]; this
0x18000c66b  mov     edx, 0DCh; void *
0x18000c670  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000c675  mov     ebx, eax
0x18000c677  lea     rcx, [rsp+260h+var_238]
0x18000c67c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c681  jmp     short loc_18000C6CC
0x18000c683  lea     rdx, [rsp+260h+var_240]; int *
0x18000c688  mov     rcx, rax; hHandle
0x18000c68b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000c690  mov     ebx, eax
0x18000c692  test    eax, eax
0x18000c694  jns     short loc_18000C6AC
0x18000c696  mov     rcx, [rbp+168h]; this
0x18000c69d  mov     r9d, eax; char *
0x18000c6a0  mov     edx, 0DEh; void *
0x18000c6a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c6aa  jmp     short loc_18000C677
0x18000c6ac  lea     rcx, [rsp+260h+var_238]
0x18000c6b1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c6b6  movsxd  rcx, [rsp+260h+var_240]
0x18000c6bb  movsxd  rax, [rsp+260h+var_23C]
0x18000c6c0  shl     rcx, 1Fh
0x18000c6c4  or      rcx, rax
0x18000c6c7  mov     [rdi], rcx
0x18000c6ca  xor     ebx, ebx
0x18000c6cc  lea     rcx, [rsp+260h+var_230]
0x18000c6d1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000c6d6  mov     eax, ebx
0x18000c6d8  mov     rcx, [rbp+160h+var_10]
0x18000c6df  xor     rcx, rsp; StackCookie
0x18000c6e2  call    __security_check_cookie
0x18000c6e7  lea     r11, [rsp+260h+var_s0]
0x18000c6ef  mov     rbx, [r11+18h]
0x18000c6f3  mov     rdi, [r11+28h]
0x18000c6f7  mov     rsp, r11
0x18000c6fa  pop     rbp
0x18000c6fb  retn
```
