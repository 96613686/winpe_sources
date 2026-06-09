# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800078c8`
- end: `0x180007a80`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180004d28`

## callees

- `0x180001a50`
- `0x1800044e0`
- `0x180005db8`
- `0x180006cf4`
- `0x180006d14`
- `0x180007560`
- `0x180007640`
- `0x1800078c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000792c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800079ca`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000792c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800079ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000793c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000793c`

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
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v18; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v19[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v15);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v19[0] = v6;
  if ( v6 )
  {
    v17 = 0;
    v16 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v17);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v18 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v16);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
        *a3 = v17 | (unsigned __int64)((__int64)v16 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v18);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v19);
  return LastError;
}

```

## disassembly

```asm
0x1800078c8  mov     [rsp-8+arg_8], rbx
0x1800078cd  mov     [rsp-8+arg_18], rdi
0x1800078d2  push    rbp
0x1800078d3  lea     rbp, [rsp-170h]
0x1800078db  sub     rsp, 270h
0x1800078e2  mov     rax, cs:__security_cookie
0x1800078e9  xor     rax, rsp
0x1800078ec  mov     [rbp+170h+var_10], rax
0x1800078f3  mov     r9, rcx; pszSrc
0x1800078f6  mov     qword ptr [r8], 0
0x1800078fd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180007902  mov     edx, 104h; cchDest
0x180007907  mov     rdi, r8
0x18000790a  call    StringCopyWorkerW
0x18000790f  lea     r8, aP0; "_p0"
0x180007916  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000791b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007920  lea     r8, [rsp+270h+pszDest]; lpName
0x180007925  xor     edx, edx; bInheritHandle
0x180007927  mov     ecx, 1F0003h; dwDesiredAccess
0x18000792c  call    cs:__imp_OpenSemaphoreW
0x180007932  mov     [rsp+270h+var_230], rax
0x180007937  test    rax, rax
0x18000793a  jnz     short loc_18000796A
0x18000793c  call    cs:__imp_GetLastError
0x180007942  cmp     eax, 2
0x180007945  jz      loc_180007A4E
0x18000794b  mov     rcx, [rbp+178h]; this
0x180007952  lea     r8, aWil; "wil"
0x180007959  mov     edx, 0D0h; void *
0x18000795e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007963  mov     ebx, eax
0x180007965  jmp     loc_180007A50
0x18000796a  lea     rdx, [rsp+270h+var_23C]; int *
0x18000796f  mov     [rsp+270h+var_23C], 0
0x180007977  mov     rcx, rax; hHandle
0x18000797a  mov     [rsp+270h+var_240], 0
0x180007982  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007987  mov     ebx, eax
0x180007989  test    eax, eax
0x18000798b  jns     short loc_1800079AD
0x18000798d  mov     rcx, [rbp+178h]; this
0x180007994  lea     r8, aWil; "wil"
0x18000799b  mov     r9d, eax; char *
0x18000799e  mov     edx, 0D6h; void *
0x1800079a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800079a8  jmp     loc_180007A50
0x1800079ad  lea     r8, asc_1800141D8; "h"
0x1800079b4  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800079b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800079be  lea     r8, [rsp+270h+pszDest]; lpName
0x1800079c3  xor     edx, edx; bInheritHandle
0x1800079c5  mov     ecx, 1F0003h; dwDesiredAccess
0x1800079ca  call    cs:__imp_OpenSemaphoreW
0x1800079d0  mov     [rsp+270h+var_238], rax
0x1800079d5  test    rax, rax
0x1800079d8  jnz     short loc_180007A00
0x1800079da  mov     rcx, [rbp+178h]; this
0x1800079e1  lea     r8, aWil; "wil"
0x1800079e8  mov     edx, 0DCh; void *
0x1800079ed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800079f2  mov     ebx, eax
0x1800079f4  lea     rcx, [rsp+270h+var_238]
0x1800079f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800079fe  jmp     short loc_180007A50
0x180007a00  lea     rdx, [rsp+270h+var_240]; int *
0x180007a05  mov     rcx, rax; hHandle
0x180007a08  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007a0d  mov     ebx, eax
0x180007a0f  test    eax, eax
0x180007a11  jns     short loc_180007A30
0x180007a13  mov     rcx, [rbp+178h]; this
0x180007a1a  lea     r8, aWil; "wil"
0x180007a21  mov     r9d, eax; char *
0x180007a24  mov     edx, 0DEh; void *
0x180007a29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a2e  jmp     short loc_1800079F4
0x180007a30  lea     rcx, [rsp+270h+var_238]
0x180007a35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007a3a  movsxd  rcx, [rsp+270h+var_240]
0x180007a3f  movsxd  rax, [rsp+270h+var_23C]
0x180007a44  shl     rcx, 1Fh
0x180007a48  or      rcx, rax
0x180007a4b  mov     [rdi], rcx
0x180007a4e  xor     ebx, ebx
0x180007a50  lea     rcx, [rsp+270h+var_230]
0x180007a55  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007a5a  mov     eax, ebx
0x180007a5c  mov     rcx, [rbp+170h+var_10]
0x180007a63  xor     rcx, rsp; StackCookie
0x180007a66  call    __security_check_cookie
0x180007a6b  lea     r11, [rsp+270h+var_s0]
0x180007a73  mov     rbx, [r11+18h]
0x180007a77  mov     rdi, [r11+28h]
0x180007a7b  mov     rsp, r11
0x180007a7e  pop     rbp
0x180007a7f  retn
```
