# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180026c2c`
- end: `0x180026dd6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180026ba8`

## callees

- `0x1800210f0`
- `0x180025394`
- `0x180025eb0`
- `0x180026484`
- `0x1800264a4`
- `0x1800269c0`
- `0x180026aa0`
- `0x180026c2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ca0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ca0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026c90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026d27`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026c90`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180026d27`

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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  size_t v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v21; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v17);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
0x180026c2c  mov     [rsp-8+arg_8], rbx
0x180026c31  mov     [rsp-8+arg_18], rdi
0x180026c36  push    rbp
0x180026c37  lea     rbp, [rsp-170h]
0x180026c3f  sub     rsp, 270h
0x180026c46  mov     rax, cs:__security_cookie
0x180026c4d  xor     rax, rsp
0x180026c50  mov     [rbp+170h+var_10], rax
0x180026c57  mov     r9, rcx; pszSrc
0x180026c5a  mov     qword ptr [r8], 0
0x180026c61  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180026c66  mov     edx, 104h; cchDest
0x180026c6b  mov     rdi, r8
0x180026c6e  call    StringCopyWorkerW
0x180026c73  lea     r8, aP0; "_p0"
0x180026c7a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180026c7f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026c84  lea     r8, [rsp+270h+pszDest]; lpName
0x180026c89  xor     edx, edx; bInheritHandle
0x180026c8b  mov     ecx, 1F0003h; dwDesiredAccess
0x180026c90  call    cs:__imp_OpenSemaphoreW
0x180026c96  mov     [rsp+270h+var_230], rax
0x180026c9b  test    rax, rax
0x180026c9e  jnz     short loc_180026CC7
0x180026ca0  call    cs:__imp_GetLastError
0x180026ca6  cmp     eax, 2
0x180026ca9  jz      loc_180026DA4
0x180026caf  mov     rcx, [rbp+178h]; this
0x180026cb6  mov     edx, 0D0h; void *
0x180026cbb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026cc0  mov     ebx, eax
0x180026cc2  jmp     loc_180026DA6
0x180026cc7  lea     rdx, [rsp+270h+var_23C]; int *
0x180026ccc  mov     [rsp+270h+var_23C], 0
0x180026cd4  mov     rcx, rax; hHandle
0x180026cd7  mov     [rsp+270h+var_240], 0
0x180026cdf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026ce4  mov     ebx, eax
0x180026ce6  test    eax, eax
0x180026ce8  jns     short loc_180026D0A
0x180026cea  mov     rcx, [rbp+178h]; this
0x180026cf1  lea     r8, aWil; "wil"
0x180026cf8  mov     r9d, eax; char *
0x180026cfb  mov     edx, 0D6h; void *
0x180026d00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d05  jmp     loc_180026DA6
0x180026d0a  lea     r8, asc_18004AB08; "h"
0x180026d11  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180026d16  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180026d1b  lea     r8, [rsp+270h+pszDest]; lpName
0x180026d20  xor     edx, edx; bInheritHandle
0x180026d22  mov     ecx, 1F0003h; dwDesiredAccess
0x180026d27  call    cs:__imp_OpenSemaphoreW
0x180026d2d  mov     [rsp+270h+var_238], rax
0x180026d32  test    rax, rax
0x180026d35  jnz     short loc_180026D56
0x180026d37  mov     rcx, [rbp+178h]; this
0x180026d3e  mov     edx, 0DCh; void *
0x180026d43  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180026d48  mov     ebx, eax
0x180026d4a  lea     rcx, [rsp+270h+var_238]
0x180026d4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026d54  jmp     short loc_180026DA6
0x180026d56  lea     rdx, [rsp+270h+var_240]; int *
0x180026d5b  mov     rcx, rax; hHandle
0x180026d5e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180026d63  mov     ebx, eax
0x180026d65  test    eax, eax
0x180026d67  jns     short loc_180026D86
0x180026d69  mov     rcx, [rbp+178h]; this
0x180026d70  lea     r8, aWil; "wil"
0x180026d77  mov     r9d, eax; char *
0x180026d7a  mov     edx, 0DEh; void *
0x180026d7f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026d84  jmp     short loc_180026D4A
0x180026d86  lea     rcx, [rsp+270h+var_238]
0x180026d8b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026d90  movsxd  rcx, [rsp+270h+var_240]
0x180026d95  movsxd  rax, [rsp+270h+var_23C]
0x180026d9a  shl     rcx, 1Fh
0x180026d9e  or      rcx, rax
0x180026da1  mov     [rdi], rcx
0x180026da4  xor     ebx, ebx
0x180026da6  lea     rcx, [rsp+270h+var_230]
0x180026dab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180026db0  mov     eax, ebx
0x180026db2  mov     rcx, [rbp+170h+var_10]
0x180026db9  xor     rcx, rsp; StackCookie
0x180026dbc  call    __security_check_cookie
0x180026dc1  lea     r11, [rsp+270h+var_s0]
0x180026dc9  mov     rbx, [r11+18h]
0x180026dcd  mov     rdi, [r11+28h]
0x180026dd1  mov     rsp, r11
0x180026dd4  pop     rbp
0x180026dd5  retn
```
