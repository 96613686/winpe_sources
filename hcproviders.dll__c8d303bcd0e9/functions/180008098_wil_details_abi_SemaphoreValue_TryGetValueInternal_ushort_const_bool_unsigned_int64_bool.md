# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008098`
- end: `0x180008247`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800066b8`

## callees

- `0x180006568`
- `0x1800072f4`
- `0x180007c24`
- `0x180007c44`
- `0x180007fc0`
- `0x180008040`
- `0x180008098`
- `0x180009e40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008112`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800080fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008198`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800080fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008198`

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
0x180008098  mov     [rsp-8+arg_8], rbx
0x18000809d  mov     [rsp-8+arg_18], rdi
0x1800080a2  push    rbp
0x1800080a3  lea     rbp, [rsp-170h]
0x1800080ab  sub     rsp, 270h
0x1800080b2  mov     rax, cs:__security_cookie
0x1800080b9  xor     rax, rsp
0x1800080bc  mov     [rbp+170h+var_10], rax
0x1800080c3  mov     r9, rcx; pszSrc
0x1800080c6  mov     qword ptr [r8], 0
0x1800080cd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800080d2  mov     edx, 104h; cchDest
0x1800080d7  mov     rdi, r8
0x1800080da  call    StringCopyWorkerW
0x1800080df  lea     r8, aP0; "_p0"
0x1800080e6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800080eb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800080f0  lea     r8, [rsp+270h+pszDest]; lpName
0x1800080f5  xor     edx, edx; bInheritHandle
0x1800080f7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800080fc  call    cs:__imp_OpenSemaphoreW
0x180008103  nop     dword ptr [rax+rax+00h]
0x180008108  mov     [rsp+270h+var_230], rax
0x18000810d  test    rax, rax
0x180008110  jnz     short loc_18000813F
0x180008112  call    cs:__imp_GetLastError
0x180008119  nop     dword ptr [rax+rax+00h]
0x18000811e  cmp     eax, 2
0x180008121  jz      loc_180008214
0x180008127  mov     rcx, [rbp+178h]; this
0x18000812e  mov     edx, 0D0h; void *
0x180008133  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008138  mov     ebx, eax
0x18000813a  jmp     loc_180008216
0x18000813f  lea     rdx, [rsp+270h+var_23C]; int *
0x180008144  mov     [rsp+270h+var_23C], 0
0x18000814c  mov     rcx, rax; hHandle
0x18000814f  mov     [rsp+270h+var_240], 0
0x180008157  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000815c  mov     ebx, eax
0x18000815e  test    eax, eax
0x180008160  jns     short loc_18000817B
0x180008162  mov     rcx, [rbp+178h]; this
0x180008169  mov     r9d, eax; char *
0x18000816c  mov     edx, 0D6h; void *
0x180008171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008176  jmp     loc_180008216
0x18000817b  lea     r8, asc_18000DA00; "h"
0x180008182  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180008187  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000818c  lea     r8, [rsp+270h+pszDest]; lpName
0x180008191  xor     edx, edx; bInheritHandle
0x180008193  mov     ecx, 1F0003h; dwDesiredAccess
0x180008198  call    cs:__imp_OpenSemaphoreW
0x18000819f  nop     dword ptr [rax+rax+00h]
0x1800081a4  mov     [rsp+270h+var_238], rax
0x1800081a9  test    rax, rax
0x1800081ac  jnz     short loc_1800081CD
0x1800081ae  mov     rcx, [rbp+178h]; this
0x1800081b5  mov     edx, 0DCh; void *
0x1800081ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800081bf  mov     ebx, eax
0x1800081c1  lea     rcx, [rsp+270h+var_238]
0x1800081c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800081cb  jmp     short loc_180008216
0x1800081cd  lea     rdx, [rsp+270h+var_240]; int *
0x1800081d2  mov     rcx, rax; hHandle
0x1800081d5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800081da  mov     ebx, eax
0x1800081dc  test    eax, eax
0x1800081de  jns     short loc_1800081F6
0x1800081e0  mov     rcx, [rbp+178h]; this
0x1800081e7  mov     r9d, eax; char *
0x1800081ea  mov     edx, 0DEh; void *
0x1800081ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081f4  jmp     short loc_1800081C1
0x1800081f6  lea     rcx, [rsp+270h+var_238]
0x1800081fb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008200  movsxd  rcx, [rsp+270h+var_240]
0x180008205  movsxd  rax, [rsp+270h+var_23C]
0x18000820a  shl     rcx, 1Fh
0x18000820e  or      rcx, rax
0x180008211  mov     [rdi], rcx
0x180008214  xor     ebx, ebx
0x180008216  lea     rcx, [rsp+270h+var_230]
0x18000821b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008220  mov     eax, ebx
0x180008222  mov     rcx, [rbp+170h+var_10]
0x180008229  xor     rcx, rsp; StackCookie
0x18000822c  call    __security_check_cookie
0x180008231  lea     r11, [rsp+270h+var_s0]
0x180008239  mov     rbx, [r11+18h]
0x18000823d  mov     rdi, [r11+28h]
0x180008241  mov     rsp, r11
0x180008244  pop     rbp
0x180008245  retn
```
