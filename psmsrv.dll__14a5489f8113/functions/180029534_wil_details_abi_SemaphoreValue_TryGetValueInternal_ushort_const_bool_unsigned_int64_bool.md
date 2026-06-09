# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180029534`
- end: `0x1800296d3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `415`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800294c0`

## callees

- `0x180004730`
- `0x18001a804`
- `0x18001b7e0`
- `0x180026550`
- `0x18002780c`
- `0x180028d60`
- `0x180029200`
- `0x180029534`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295ab`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002959b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002962b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002959b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002962b`

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
  int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  int v17; // r8d
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v22; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, 0, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v23[0] = v6;
  if ( v6 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v22 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v20);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
  return LastError;
}

```

## disassembly

```asm
0x180029534  mov     [rsp-8+arg_8], rbx
0x180029539  mov     [rsp-8+arg_18], rdi
0x18002953e  push    rbp
0x18002953f  lea     rbp, [rsp-170h]
0x180029547  sub     rsp, 270h
0x18002954e  mov     rax, cs:__security_cookie
0x180029555  xor     rax, rsp
0x180029558  mov     [rbp+170h+var_10], rax
0x18002955f  mov     rdi, r8
0x180029562  mov     qword ptr [r8], 0
0x180029569  mov     r9, rcx; pszSrc
0x18002956c  xor     r8d, r8d; pcchNewDestLength
0x18002956f  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180029574  mov     edx, 104h; cchDest
0x180029579  call    StringCopyWorkerW
0x18002957e  lea     r8, aP0; "_p0"
0x180029585  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18002958a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002958f  lea     r8, [rsp+270h+pszDest]; lpName
0x180029594  xor     edx, edx; bInheritHandle
0x180029596  mov     ecx, 1F0003h; dwDesiredAccess
0x18002959b  call    cs:__imp_OpenSemaphoreW
0x1800295a1  mov     [rsp+270h+var_230], rax
0x1800295a6  test    rax, rax
0x1800295a9  jnz     short loc_1800295D2
0x1800295ab  call    cs:__imp_GetLastError
0x1800295b1  cmp     eax, 2
0x1800295b4  jz      loc_1800296A1
0x1800295ba  mov     rcx, [rbp+178h]; this
0x1800295c1  mov     edx, 0D0h; void *
0x1800295c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800295cb  mov     ebx, eax
0x1800295cd  jmp     loc_1800296A3
0x1800295d2  lea     rdx, [rsp+270h+var_23C]; int *
0x1800295d7  mov     [rsp+270h+var_23C], 0
0x1800295df  mov     rcx, rax; hHandle
0x1800295e2  mov     [rsp+270h+var_240], 0
0x1800295ea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800295ef  mov     ebx, eax
0x1800295f1  test    eax, eax
0x1800295f3  jns     short loc_18002960E
0x1800295f5  mov     rcx, [rbp+178h]; this
0x1800295fc  mov     r9d, eax; char *
0x1800295ff  mov     edx, 0D6h; void *
0x180029604  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029609  jmp     loc_1800296A3
0x18002960e  lea     r8, asc_180036118; "h"
0x180029615  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18002961a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002961f  lea     r8, [rsp+270h+pszDest]; lpName
0x180029624  xor     edx, edx; bInheritHandle
0x180029626  mov     ecx, 1F0003h; dwDesiredAccess
0x18002962b  call    cs:__imp_OpenSemaphoreW
0x180029631  mov     [rsp+270h+var_238], rax
0x180029636  test    rax, rax
0x180029639  jnz     short loc_18002965A
0x18002963b  mov     rcx, [rbp+178h]; this
0x180029642  mov     edx, 0DCh; void *
0x180029647  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002964c  mov     ebx, eax
0x18002964e  lea     rcx, [rsp+270h+var_238]
0x180029653  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180029658  jmp     short loc_1800296A3
0x18002965a  lea     rdx, [rsp+270h+var_240]; int *
0x18002965f  mov     rcx, rax; hHandle
0x180029662  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180029667  mov     ebx, eax
0x180029669  test    eax, eax
0x18002966b  jns     short loc_180029683
0x18002966d  mov     rcx, [rbp+178h]; this
0x180029674  mov     r9d, eax; char *
0x180029677  mov     edx, 0DEh; void *
0x18002967c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029681  jmp     short loc_18002964E
0x180029683  lea     rcx, [rsp+270h+var_238]
0x180029688  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002968d  movsxd  rcx, [rsp+270h+var_240]
0x180029692  movsxd  rax, [rsp+270h+var_23C]
0x180029697  shl     rcx, 1Fh
0x18002969b  or      rcx, rax
0x18002969e  mov     [rdi], rcx
0x1800296a1  xor     ebx, ebx
0x1800296a3  lea     rcx, [rsp+270h+var_230]
0x1800296a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800296ad  mov     eax, ebx
0x1800296af  mov     rcx, [rbp+170h+var_10]
0x1800296b6  xor     rcx, rsp; StackCookie
0x1800296b9  call    __security_check_cookie
0x1800296be  lea     r11, [rsp+270h+var_s0]
0x1800296c6  mov     rbx, [r11+18h]
0x1800296ca  mov     rdi, [r11+28h]
0x1800296ce  mov     rsp, r11
0x1800296d1  pop     rbp
0x1800296d2  retn
```
