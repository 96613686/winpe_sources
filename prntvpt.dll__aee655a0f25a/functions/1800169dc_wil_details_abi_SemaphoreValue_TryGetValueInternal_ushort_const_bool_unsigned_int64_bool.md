# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800169dc`
- end: `0x180016b78`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180016968`

## callees

- `0x18000f970`
- `0x18001119c`
- `0x1800136f0`
- `0x180015fb0`
- `0x180015fd0`
- `0x1800165a0`
- `0x18001661c`
- `0x1800169dc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180016a50`
- `KERNEL32!GetLastError` at `0x180016a50`
- `KERNEL32!OpenSemaphoreW` at `0x180016a40`
- `KERNEL32!OpenSemaphoreW` at `0x180016ad0`
- `KERNEL32!OpenSemaphoreW` at `0x180016a40`
- `KERNEL32!OpenSemaphoreW` at `0x180016ad0`

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
0x1800169dc  mov     [rsp-8+arg_8], rbx
0x1800169e1  mov     [rsp-8+arg_18], rdi
0x1800169e6  push    rbp
0x1800169e7  lea     rbp, [rsp-170h]
0x1800169ef  sub     rsp, 270h
0x1800169f6  mov     rax, cs:__security_cookie
0x1800169fd  xor     rax, rsp
0x180016a00  mov     [rbp+170h+var_10], rax
0x180016a07  mov     r9, rcx; pszSrc
0x180016a0a  mov     qword ptr [r8], 0
0x180016a11  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180016a16  mov     edx, 104h; cchDest
0x180016a1b  mov     rdi, r8
0x180016a1e  call    StringCopyWorkerW
0x180016a23  lea     r8, aP0; "_p0"
0x180016a2a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180016a2f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016a34  lea     r8, [rsp+270h+pszDest]; lpName
0x180016a39  xor     edx, edx; bInheritHandle
0x180016a3b  mov     ecx, 1F0003h; dwDesiredAccess
0x180016a40  call    cs:__imp_OpenSemaphoreW
0x180016a46  mov     [rsp+270h+var_230], rax
0x180016a4b  test    rax, rax
0x180016a4e  jnz     short loc_180016A77
0x180016a50  call    cs:__imp_GetLastError
0x180016a56  cmp     eax, 2
0x180016a59  jz      loc_180016B46
0x180016a5f  mov     rcx, [rbp+178h]; this
0x180016a66  mov     edx, 0D0h; void *
0x180016a6b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016a70  mov     ebx, eax
0x180016a72  jmp     loc_180016B48
0x180016a77  lea     rdx, [rsp+270h+var_23C]; int *
0x180016a7c  mov     [rsp+270h+var_23C], 0
0x180016a84  mov     rcx, rax; hHandle
0x180016a87  mov     [rsp+270h+var_240], 0
0x180016a8f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180016a94  mov     ebx, eax
0x180016a96  test    eax, eax
0x180016a98  jns     short loc_180016AB3
0x180016a9a  mov     rcx, [rbp+178h]; this
0x180016aa1  mov     r9d, eax; char *
0x180016aa4  mov     edx, 0D6h; void *
0x180016aa9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016aae  jmp     loc_180016B48
0x180016ab3  lea     r8, asc_180027BD8; "h"
0x180016aba  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180016abf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016ac4  lea     r8, [rsp+270h+pszDest]; lpName
0x180016ac9  xor     edx, edx; bInheritHandle
0x180016acb  mov     ecx, 1F0003h; dwDesiredAccess
0x180016ad0  call    cs:__imp_OpenSemaphoreW
0x180016ad6  mov     [rsp+270h+var_238], rax
0x180016adb  test    rax, rax
0x180016ade  jnz     short loc_180016AFF
0x180016ae0  mov     rcx, [rbp+178h]; this
0x180016ae7  mov     edx, 0DCh; void *
0x180016aec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016af1  mov     ebx, eax
0x180016af3  lea     rcx, [rsp+270h+var_238]
0x180016af8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016afd  jmp     short loc_180016B48
0x180016aff  lea     rdx, [rsp+270h+var_240]; int *
0x180016b04  mov     rcx, rax; hHandle
0x180016b07  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180016b0c  mov     ebx, eax
0x180016b0e  test    eax, eax
0x180016b10  jns     short loc_180016B28
0x180016b12  mov     rcx, [rbp+178h]; this
0x180016b19  mov     r9d, eax; char *
0x180016b1c  mov     edx, 0DEh; void *
0x180016b21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b26  jmp     short loc_180016AF3
0x180016b28  lea     rcx, [rsp+270h+var_238]
0x180016b2d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016b32  movsxd  rcx, [rsp+270h+var_240]
0x180016b37  movsxd  rax, [rsp+270h+var_23C]
0x180016b3c  shl     rcx, 1Fh
0x180016b40  or      rcx, rax
0x180016b43  mov     [rdi], rcx
0x180016b46  xor     ebx, ebx
0x180016b48  lea     rcx, [rsp+270h+var_230]
0x180016b4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016b52  mov     eax, ebx
0x180016b54  mov     rcx, [rbp+170h+var_10]
0x180016b5b  xor     rcx, rsp; StackCookie
0x180016b5e  call    __security_check_cookie
0x180016b63  lea     r11, [rsp+270h+var_s0]
0x180016b6b  mov     rbx, [r11+18h]
0x180016b6f  mov     rdi, [r11+28h]
0x180016b73  mov     rsp, r11
0x180016b76  pop     rbp
0x180016b77  retn
```
