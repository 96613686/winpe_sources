# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003d73c`
- end: `0x18003d8d8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003afa0`

## callees

- `0x180024220`
- `0x18003af40`
- `0x18003c2d0`
- `0x18003d27c`
- `0x18003d29c`
- `0x18003d510`
- `0x18003d5f0`
- `0x18003d73c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d7a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d830`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d7a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003d830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d7b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d7b0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x18003d73c  mov     [rsp-8+arg_8], rbx
0x18003d741  mov     [rsp-8+arg_18], rdi
0x18003d746  push    rbp
0x18003d747  lea     rbp, [rsp-170h]
0x18003d74f  sub     rsp, 270h
0x18003d756  mov     rax, cs:__security_cookie
0x18003d75d  xor     rax, rsp
0x18003d760  mov     [rbp+170h+var_10], rax
0x18003d767  mov     r9, rcx; pszSrc
0x18003d76a  mov     qword ptr [r8], 0
0x18003d771  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18003d776  mov     edx, 104h; cchDest
0x18003d77b  mov     rdi, r8
0x18003d77e  call    StringCopyWorkerW
0x18003d783  lea     r8, aP0; "_p0"
0x18003d78a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18003d78f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003d794  lea     r8, [rsp+270h+pszDest]; lpName
0x18003d799  xor     edx, edx; bInheritHandle
0x18003d79b  mov     ecx, 1F0003h; dwDesiredAccess
0x18003d7a0  call    cs:__imp_OpenSemaphoreW
0x18003d7a6  mov     [rsp+270h+var_230], rax
0x18003d7ab  test    rax, rax
0x18003d7ae  jnz     short loc_18003D7D7
0x18003d7b0  call    cs:__imp_GetLastError
0x18003d7b6  cmp     eax, 2
0x18003d7b9  jz      loc_18003D8A6
0x18003d7bf  mov     rcx, [rbp+178h]; this
0x18003d7c6  mov     edx, 0D0h; void *
0x18003d7cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d7d0  mov     ebx, eax
0x18003d7d2  jmp     loc_18003D8A8
0x18003d7d7  lea     rdx, [rsp+270h+var_23C]; int *
0x18003d7dc  mov     [rsp+270h+var_23C], 0
0x18003d7e4  mov     rcx, rax; hHandle
0x18003d7e7  mov     [rsp+270h+var_240], 0
0x18003d7ef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003d7f4  mov     ebx, eax
0x18003d7f6  test    eax, eax
0x18003d7f8  jns     short loc_18003D813
0x18003d7fa  mov     rcx, [rbp+178h]; this
0x18003d801  mov     r9d, eax; char *
0x18003d804  mov     edx, 0D6h; void *
0x18003d809  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d80e  jmp     loc_18003D8A8
0x18003d813  lea     r8, asc_1800914F8; "h"
0x18003d81a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18003d81f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003d824  lea     r8, [rsp+270h+pszDest]; lpName
0x18003d829  xor     edx, edx; bInheritHandle
0x18003d82b  mov     ecx, 1F0003h; dwDesiredAccess
0x18003d830  call    cs:__imp_OpenSemaphoreW
0x18003d836  mov     [rsp+270h+var_238], rax
0x18003d83b  test    rax, rax
0x18003d83e  jnz     short loc_18003D85F
0x18003d840  mov     rcx, [rbp+178h]; this
0x18003d847  mov     edx, 0DCh; void *
0x18003d84c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003d851  mov     ebx, eax
0x18003d853  lea     rcx, [rsp+270h+var_238]
0x18003d858  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d85d  jmp     short loc_18003D8A8
0x18003d85f  lea     rdx, [rsp+270h+var_240]; int *
0x18003d864  mov     rcx, rax; hHandle
0x18003d867  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003d86c  mov     ebx, eax
0x18003d86e  test    eax, eax
0x18003d870  jns     short loc_18003D888
0x18003d872  mov     rcx, [rbp+178h]; this
0x18003d879  mov     r9d, eax; char *
0x18003d87c  mov     edx, 0DEh; void *
0x18003d881  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d886  jmp     short loc_18003D853
0x18003d888  lea     rcx, [rsp+270h+var_238]
0x18003d88d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d892  movsxd  rcx, [rsp+270h+var_240]
0x18003d897  movsxd  rax, [rsp+270h+var_23C]
0x18003d89c  shl     rcx, 1Fh
0x18003d8a0  or      rcx, rax
0x18003d8a3  mov     [rdi], rcx
0x18003d8a6  xor     ebx, ebx
0x18003d8a8  lea     rcx, [rsp+270h+var_230]
0x18003d8ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003d8b2  mov     eax, ebx
0x18003d8b4  mov     rcx, [rbp+170h+var_10]
0x18003d8bb  xor     rcx, rsp; StackCookie
0x18003d8be  call    __security_check_cookie
0x18003d8c3  lea     r11, [rsp+270h+var_s0]
0x18003d8cb  mov     rbx, [r11+18h]
0x18003d8cf  mov     rdi, [r11+28h]
0x18003d8d3  mov     rsp, r11
0x18003d8d6  pop     rbp
0x18003d8d7  retn
```
