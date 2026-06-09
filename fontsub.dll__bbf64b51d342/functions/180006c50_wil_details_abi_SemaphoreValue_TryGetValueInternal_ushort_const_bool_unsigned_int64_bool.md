# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006c50`
- end: `0x180006dec`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003c38`

## callees

- `0x180003a84`
- `0x180004954`
- `0x180005a74`
- `0x180005a94`
- `0x180006ac4`
- `0x180006ba4`
- `0x180006c50`
- `0x18001ac90`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180006cb4`
- `KERNEL32!OpenSemaphoreW` at `0x180006d44`
- `KERNEL32!OpenSemaphoreW` at `0x180006cb4`
- `KERNEL32!OpenSemaphoreW` at `0x180006d44`
- `KERNEL32!GetLastError` at `0x180006cc4`
- `KERNEL32!GetLastError` at `0x180006cc4`

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
0x180006c50  mov     [rsp-8+arg_8], rbx
0x180006c55  mov     [rsp-8+arg_18], rdi
0x180006c5a  push    rbp
0x180006c5b  lea     rbp, [rsp-170h]
0x180006c63  sub     rsp, 270h
0x180006c6a  mov     rax, cs:__security_cookie
0x180006c71  xor     rax, rsp
0x180006c74  mov     [rbp+170h+var_10], rax
0x180006c7b  mov     r9, rcx; pszSrc
0x180006c7e  mov     qword ptr [r8], 0
0x180006c85  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180006c8a  mov     edx, 104h; cchDest
0x180006c8f  mov     rdi, r8
0x180006c92  call    StringCopyWorkerW
0x180006c97  lea     r8, aP0; "_p0"
0x180006c9e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180006ca3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006ca8  lea     r8, [rsp+270h+pszDest]; lpName
0x180006cad  xor     edx, edx; bInheritHandle
0x180006caf  mov     ecx, 1F0003h; dwDesiredAccess
0x180006cb4  call    cs:__imp_OpenSemaphoreW
0x180006cba  mov     [rsp+270h+var_230], rax
0x180006cbf  test    rax, rax
0x180006cc2  jnz     short loc_180006CEB
0x180006cc4  call    cs:__imp_GetLastError
0x180006cca  cmp     eax, 2
0x180006ccd  jz      loc_180006DBA
0x180006cd3  mov     rcx, [rbp+178h]; this
0x180006cda  mov     edx, 0D0h; void *
0x180006cdf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006ce4  mov     ebx, eax
0x180006ce6  jmp     loc_180006DBC
0x180006ceb  lea     rdx, [rsp+270h+var_23C]; int *
0x180006cf0  mov     [rsp+270h+var_23C], 0
0x180006cf8  mov     rcx, rax; hHandle
0x180006cfb  mov     [rsp+270h+var_240], 0
0x180006d03  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006d08  mov     ebx, eax
0x180006d0a  test    eax, eax
0x180006d0c  jns     short loc_180006D27
0x180006d0e  mov     rcx, [rbp+178h]; this
0x180006d15  mov     r9d, eax; char *
0x180006d18  mov     edx, 0D6h; void *
0x180006d1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d22  jmp     loc_180006DBC
0x180006d27  lea     r8, asc_18001D798; "h"
0x180006d2e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180006d33  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006d38  lea     r8, [rsp+270h+pszDest]; lpName
0x180006d3d  xor     edx, edx; bInheritHandle
0x180006d3f  mov     ecx, 1F0003h; dwDesiredAccess
0x180006d44  call    cs:__imp_OpenSemaphoreW
0x180006d4a  mov     [rsp+270h+var_238], rax
0x180006d4f  test    rax, rax
0x180006d52  jnz     short loc_180006D73
0x180006d54  mov     rcx, [rbp+178h]; this
0x180006d5b  mov     edx, 0DCh; void *
0x180006d60  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006d65  mov     ebx, eax
0x180006d67  lea     rcx, [rsp+270h+var_238]
0x180006d6c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006d71  jmp     short loc_180006DBC
0x180006d73  lea     rdx, [rsp+270h+var_240]; int *
0x180006d78  mov     rcx, rax; hHandle
0x180006d7b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006d80  mov     ebx, eax
0x180006d82  test    eax, eax
0x180006d84  jns     short loc_180006D9C
0x180006d86  mov     rcx, [rbp+178h]; this
0x180006d8d  mov     r9d, eax; char *
0x180006d90  mov     edx, 0DEh; void *
0x180006d95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d9a  jmp     short loc_180006D67
0x180006d9c  lea     rcx, [rsp+270h+var_238]
0x180006da1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006da6  movsxd  rcx, [rsp+270h+var_240]
0x180006dab  movsxd  rax, [rsp+270h+var_23C]
0x180006db0  shl     rcx, 1Fh
0x180006db4  or      rcx, rax
0x180006db7  mov     [rdi], rcx
0x180006dba  xor     ebx, ebx
0x180006dbc  lea     rcx, [rsp+270h+var_230]
0x180006dc1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006dc6  mov     eax, ebx
0x180006dc8  mov     rcx, [rbp+170h+var_10]
0x180006dcf  xor     rcx, rsp; StackCookie
0x180006dd2  call    __security_check_cookie
0x180006dd7  lea     r11, [rsp+270h+var_s0]
0x180006ddf  mov     rbx, [r11+18h]
0x180006de3  mov     rdi, [r11+28h]
0x180006de7  mov     rsp, r11
0x180006dea  pop     rbp
0x180006deb  retn
```
