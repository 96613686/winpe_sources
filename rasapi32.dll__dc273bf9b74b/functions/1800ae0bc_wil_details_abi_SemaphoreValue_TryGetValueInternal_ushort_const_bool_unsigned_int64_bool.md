# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800ae0bc`
- end: `0x1800ae25e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800ae048`

## callees

- `0x1800203dc`
- `0x18008d814`
- `0x1800a9aec`
- `0x1800ab804`
- `0x1800ad84c`
- `0x1800ad86c`
- `0x1800ae0bc`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ae125`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ae1b7`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ae125`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ae1b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae135`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ae135`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t pszDest[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(pszDest, 0x104u, pszSrc);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x1800ae0bc  mov     [rsp-8+arg_8], rbx
0x1800ae0c1  push    rbp
0x1800ae0c2  push    rdi
0x1800ae0c3  push    r14
0x1800ae0c5  lea     rbp, [rsp-160h]
0x1800ae0cd  sub     rsp, 260h
0x1800ae0d4  mov     rax, cs:__security_cookie
0x1800ae0db  xor     rax, rsp
0x1800ae0de  mov     [rbp+170h+var_20], rax
0x1800ae0e5  mov     rdi, r8
0x1800ae0e8  mov     qword ptr [r8], 0
0x1800ae0ef  mov     r8, rcx; pszSrc
0x1800ae0f2  mov     r14d, 104h
0x1800ae0f8  mov     edx, r14d; cchDest
0x1800ae0fb  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800ae100  call    StringCchCopyW
0x1800ae105  lea     r8, aP0; "_p0"
0x1800ae10c  mov     edx, r14d; cchDest
0x1800ae10f  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800ae114  call    StringCchCatW
0x1800ae119  lea     r8, [rsp+270h+pszDest]; lpName
0x1800ae11e  xor     edx, edx; bInheritHandle
0x1800ae120  mov     ecx, 1F0003h; dwDesiredAccess
0x1800ae125  call    cs:__imp_OpenSemaphoreW
0x1800ae12b  mov     [rsp+270h+var_240], rax
0x1800ae130  test    rax, rax
0x1800ae133  jnz     short loc_1800AE15B
0x1800ae135  call    cs:__imp_GetLastError
0x1800ae13b  cmp     eax, 2
0x1800ae13e  jz      loc_1800AE22D
0x1800ae144  mov     rcx, [rbp+178h]; this
0x1800ae14b  lea     edx, [r14-34h]; void *
0x1800ae14f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ae154  mov     ebx, eax
0x1800ae156  jmp     loc_1800AE22F
0x1800ae15b  lea     rdx, [rsp+270h+var_24C]; int *
0x1800ae160  mov     [rsp+270h+var_24C], 0
0x1800ae168  mov     rcx, rax; hHandle
0x1800ae16b  mov     [rsp+270h+var_250], 0; int
0x1800ae173  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800ae178  mov     ebx, eax
0x1800ae17a  test    eax, eax
0x1800ae17c  jns     short loc_1800AE197
0x1800ae17e  mov     rcx, [rbp+178h]; this
0x1800ae185  mov     r9d, eax; char *
0x1800ae188  mov     edx, 0D6h; void *
0x1800ae18d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae192  jmp     loc_1800AE22F
0x1800ae197  lea     r8, asc_1800E90F8; "h"
0x1800ae19e  mov     rdx, r14; cchDest
0x1800ae1a1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800ae1a6  call    StringCchCatW
0x1800ae1ab  lea     r8, [rsp+270h+pszDest]; lpName
0x1800ae1b0  xor     edx, edx; bInheritHandle
0x1800ae1b2  mov     ecx, 1F0003h; dwDesiredAccess
0x1800ae1b7  call    cs:__imp_OpenSemaphoreW
0x1800ae1bd  mov     [rsp+270h+var_248], rax
0x1800ae1c2  test    rax, rax
0x1800ae1c5  jnz     short loc_1800AE1E6
0x1800ae1c7  mov     rcx, [rbp+178h]; this
0x1800ae1ce  mov     edx, 0DCh; void *
0x1800ae1d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ae1d8  mov     ebx, eax
0x1800ae1da  lea     rcx, [rsp+270h+var_248]
0x1800ae1df  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ae1e4  jmp     short loc_1800AE22F
0x1800ae1e6  lea     rdx, [rsp+270h+var_250]; int *
0x1800ae1eb  mov     rcx, rax; hHandle
0x1800ae1ee  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800ae1f3  mov     ebx, eax
0x1800ae1f5  test    eax, eax
0x1800ae1f7  jns     short loc_1800AE20F
0x1800ae1f9  mov     rcx, [rbp+178h]; this
0x1800ae200  mov     r9d, eax; char *
0x1800ae203  mov     edx, 0DEh; void *
0x1800ae208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ae20d  jmp     short loc_1800AE1DA
0x1800ae20f  lea     rcx, [rsp+270h+var_248]
0x1800ae214  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ae219  movsxd  rcx, [rsp+270h+var_250]
0x1800ae21e  movsxd  rax, [rsp+270h+var_24C]
0x1800ae223  shl     rcx, 1Fh
0x1800ae227  or      rcx, rax
0x1800ae22a  mov     [rdi], rcx
0x1800ae22d  xor     ebx, ebx
0x1800ae22f  lea     rcx, [rsp+270h+var_240]
0x1800ae234  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ae239  mov     eax, ebx
0x1800ae23b  mov     rcx, [rbp+170h+var_20]
0x1800ae242  xor     rcx, rsp; StackCookie
0x1800ae245  call    __security_check_cookie
0x1800ae24a  mov     rbx, [rsp+270h+arg_8]
0x1800ae252  add     rsp, 260h
0x1800ae259  pop     r14
0x1800ae25b  pop     rdi
0x1800ae25c  pop     rbp
0x1800ae25d  retn
```
