# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000809c`
- end: `0x180008254`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008018`

## callees

- `0x180002b60`
- `0x180005378`
- `0x1800064e8`
- `0x1800076b4`
- `0x1800076d4`
- `0x180007cb8`
- `0x180007de0`
- `0x18000809c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008100`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000819e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008100`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000819e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008110`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008110`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  size_t v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v19; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
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
        v16);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
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
0x18000809c  mov     [rsp-8+arg_8], rbx
0x1800080a1  mov     [rsp-8+arg_18], rdi
0x1800080a6  push    rbp
0x1800080a7  lea     rbp, [rsp-170h]
0x1800080af  sub     rsp, 270h
0x1800080b6  mov     rax, cs:__security_cookie
0x1800080bd  xor     rax, rsp
0x1800080c0  mov     [rbp+170h+var_10], rax
0x1800080c7  mov     r9, rcx; pszSrc
0x1800080ca  mov     qword ptr [r8], 0
0x1800080d1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800080d6  mov     edx, 104h; cchDest
0x1800080db  mov     rdi, r8
0x1800080de  call    StringCopyWorkerW
0x1800080e3  lea     r8, aP0; "_p0"
0x1800080ea  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800080ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800080f4  lea     r8, [rsp+270h+pszDest]; lpName
0x1800080f9  xor     edx, edx; bInheritHandle
0x1800080fb  mov     ecx, 1F0003h; dwDesiredAccess
0x180008100  call    cs:__imp_OpenSemaphoreW
0x180008106  mov     [rsp+270h+var_230], rax
0x18000810b  test    rax, rax
0x18000810e  jnz     short loc_18000813E
0x180008110  call    cs:__imp_GetLastError
0x180008116  cmp     eax, 2
0x180008119  jz      loc_180008222
0x18000811f  mov     rcx, [rbp+178h]; this
0x180008126  lea     r8, aWil; "wil"
0x18000812d  mov     edx, 0D0h; void *
0x180008132  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008137  mov     ebx, eax
0x180008139  jmp     loc_180008224
0x18000813e  lea     rdx, [rsp+270h+var_23C]; int *
0x180008143  mov     [rsp+270h+var_23C], 0
0x18000814b  mov     rcx, rax; hHandle
0x18000814e  mov     [rsp+270h+var_240], 0
0x180008156  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000815b  mov     ebx, eax
0x18000815d  test    eax, eax
0x18000815f  jns     short loc_180008181
0x180008161  mov     rcx, [rbp+178h]; this
0x180008168  lea     r8, aWil; "wil"
0x18000816f  mov     r9d, eax; char *
0x180008172  mov     edx, 0D6h; void *
0x180008177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000817c  jmp     loc_180008224
0x180008181  lea     r8, asc_18008A4A8; "h"
0x180008188  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000818d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008192  lea     r8, [rsp+270h+pszDest]; lpName
0x180008197  xor     edx, edx; bInheritHandle
0x180008199  mov     ecx, 1F0003h; dwDesiredAccess
0x18000819e  call    cs:__imp_OpenSemaphoreW
0x1800081a4  mov     [rsp+270h+var_238], rax
0x1800081a9  test    rax, rax
0x1800081ac  jnz     short loc_1800081D4
0x1800081ae  mov     rcx, [rbp+178h]; this
0x1800081b5  lea     r8, aWil; "wil"
0x1800081bc  mov     edx, 0DCh; void *
0x1800081c1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800081c6  mov     ebx, eax
0x1800081c8  lea     rcx, [rsp+270h+var_238]
0x1800081cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800081d2  jmp     short loc_180008224
0x1800081d4  lea     rdx, [rsp+270h+var_240]; int *
0x1800081d9  mov     rcx, rax; hHandle
0x1800081dc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800081e1  mov     ebx, eax
0x1800081e3  test    eax, eax
0x1800081e5  jns     short loc_180008204
0x1800081e7  mov     rcx, [rbp+178h]; this
0x1800081ee  lea     r8, aWil; "wil"
0x1800081f5  mov     r9d, eax; char *
0x1800081f8  mov     edx, 0DEh; void *
0x1800081fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008202  jmp     short loc_1800081C8
0x180008204  lea     rcx, [rsp+270h+var_238]
0x180008209  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000820e  movsxd  rcx, [rsp+270h+var_240]
0x180008213  movsxd  rax, [rsp+270h+var_23C]
0x180008218  shl     rcx, 1Fh
0x18000821c  or      rcx, rax
0x18000821f  mov     [rdi], rcx
0x180008222  xor     ebx, ebx
0x180008224  lea     rcx, [rsp+270h+var_230]
0x180008229  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000822e  mov     eax, ebx
0x180008230  mov     rcx, [rbp+170h+var_10]
0x180008237  xor     rcx, rsp; StackCookie
0x18000823a  call    __security_check_cookie
0x18000823f  lea     r11, [rsp+270h+var_s0]
0x180008247  mov     rbx, [r11+18h]
0x18000824b  mov     rdi, [r11+28h]
0x18000824f  mov     rsp, r11
0x180008252  pop     rbp
0x180008253  retn
```
