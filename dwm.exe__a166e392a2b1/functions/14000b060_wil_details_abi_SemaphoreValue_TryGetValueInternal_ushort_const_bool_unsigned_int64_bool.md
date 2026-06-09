# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000b060`
- end: `0x14000b20a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000afdc`

## callees

- `0x140004a94`
- `0x140005530`
- `0x1400076d0`
- `0x1400090bc`
- `0x14000a878`
- `0x14000ad20`
- `0x14000ae00`
- `0x14000b060`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b0c4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b15b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b0c4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000b15b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b0d4`

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
0x14000b060  mov     [rsp-8+arg_8], rbx
0x14000b065  mov     [rsp-8+arg_18], rdi
0x14000b06a  push    rbp
0x14000b06b  lea     rbp, [rsp-170h]
0x14000b073  sub     rsp, 270h
0x14000b07a  mov     rax, cs:__security_cookie
0x14000b081  xor     rax, rsp
0x14000b084  mov     [rbp+170h+var_10], rax
0x14000b08b  mov     r9, rcx; pszSrc
0x14000b08e  mov     qword ptr [r8], 0
0x14000b095  lea     rcx, [rsp+270h+pszDest]; pszDest
0x14000b09a  mov     edx, 104h; cchDest
0x14000b09f  mov     rdi, r8
0x14000b0a2  call    StringCopyWorkerW
0x14000b0a7  lea     r8, aP0; "_p0"
0x14000b0ae  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000b0b3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b0b8  lea     r8, [rsp+270h+pszDest]; lpName
0x14000b0bd  xor     edx, edx; bInheritHandle
0x14000b0bf  mov     ecx, 1F0003h; dwDesiredAccess
0x14000b0c4  call    cs:__imp_OpenSemaphoreW
0x14000b0ca  mov     [rsp+270h+var_230], rax
0x14000b0cf  test    rax, rax
0x14000b0d2  jnz     short loc_14000B0FB
0x14000b0d4  call    cs:__imp_GetLastError
0x14000b0da  cmp     eax, 2
0x14000b0dd  jz      loc_14000B1D8
0x14000b0e3  mov     rcx, [rbp+178h]; this
0x14000b0ea  mov     edx, 0D0h; void *
0x14000b0ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b0f4  mov     ebx, eax
0x14000b0f6  jmp     loc_14000B1DA
0x14000b0fb  lea     rdx, [rsp+270h+var_23C]; int *
0x14000b100  mov     [rsp+270h+var_23C], 0
0x14000b108  mov     rcx, rax; hHandle
0x14000b10b  mov     [rsp+270h+var_240], 0
0x14000b113  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000b118  mov     ebx, eax
0x14000b11a  test    eax, eax
0x14000b11c  jns     short loc_14000B13E
0x14000b11e  mov     rcx, [rbp+178h]; this
0x14000b125  lea     r8, aWil; "wil"
0x14000b12c  mov     r9d, eax; char *
0x14000b12f  mov     edx, 0D6h; void *
0x14000b134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b139  jmp     loc_14000B1DA
0x14000b13e  lea     r8, asc_140012B60; "h"
0x14000b145  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000b14a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b14f  lea     r8, [rsp+270h+pszDest]; lpName
0x14000b154  xor     edx, edx; bInheritHandle
0x14000b156  mov     ecx, 1F0003h; dwDesiredAccess
0x14000b15b  call    cs:__imp_OpenSemaphoreW
0x14000b161  mov     [rsp+270h+var_238], rax
0x14000b166  test    rax, rax
0x14000b169  jnz     short loc_14000B18A
0x14000b16b  mov     rcx, [rbp+178h]; this
0x14000b172  mov     edx, 0DCh; void *
0x14000b177  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b17c  mov     ebx, eax
0x14000b17e  lea     rcx, [rsp+270h+var_238]
0x14000b183  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b188  jmp     short loc_14000B1DA
0x14000b18a  lea     rdx, [rsp+270h+var_240]; int *
0x14000b18f  mov     rcx, rax; hHandle
0x14000b192  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000b197  mov     ebx, eax
0x14000b199  test    eax, eax
0x14000b19b  jns     short loc_14000B1BA
0x14000b19d  mov     rcx, [rbp+178h]; this
0x14000b1a4  lea     r8, aWil; "wil"
0x14000b1ab  mov     r9d, eax; char *
0x14000b1ae  mov     edx, 0DEh; void *
0x14000b1b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b1b8  jmp     short loc_14000B17E
0x14000b1ba  lea     rcx, [rsp+270h+var_238]
0x14000b1bf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b1c4  movsxd  rcx, [rsp+270h+var_240]
0x14000b1c9  movsxd  rax, [rsp+270h+var_23C]
0x14000b1ce  shl     rcx, 1Fh
0x14000b1d2  or      rcx, rax
0x14000b1d5  mov     [rdi], rcx
0x14000b1d8  xor     ebx, ebx
0x14000b1da  lea     rcx, [rsp+270h+var_230]
0x14000b1df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b1e4  mov     eax, ebx
0x14000b1e6  mov     rcx, [rbp+170h+var_10]
0x14000b1ed  xor     rcx, rsp; StackCookie
0x14000b1f0  call    __security_check_cookie
0x14000b1f5  lea     r11, [rsp+270h+var_s0]
0x14000b1fd  mov     rbx, [r11+18h]
0x14000b201  mov     rdi, [r11+28h]
0x14000b205  mov     rsp, r11
0x14000b208  pop     rbp
0x14000b209  retn
```
