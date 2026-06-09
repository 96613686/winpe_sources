# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bd7c`
- end: `0x18000bf26`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000bcf8`

## callees

- `0x180001640`
- `0x180007ca0`
- `0x180009268`
- `0x18000b16c`
- `0x18000b18c`
- `0x18000b84c`
- `0x18000b92c`
- `0x18000bd7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bdf0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bde0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000be77`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bde0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000be77`

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
0x18000bd7c  mov     [rsp-8+arg_8], rbx
0x18000bd81  mov     [rsp-8+arg_18], rdi
0x18000bd86  push    rbp
0x18000bd87  lea     rbp, [rsp-170h]
0x18000bd8f  sub     rsp, 270h
0x18000bd96  mov     rax, cs:__security_cookie
0x18000bd9d  xor     rax, rsp
0x18000bda0  mov     [rbp+170h+var_10], rax
0x18000bda7  mov     r9, rcx; pszSrc
0x18000bdaa  mov     qword ptr [r8], 0
0x18000bdb1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000bdb6  mov     edx, 104h; cchDest
0x18000bdbb  mov     rdi, r8
0x18000bdbe  call    StringCopyWorkerW
0x18000bdc3  lea     r8, aP0; "_p0"
0x18000bdca  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000bdcf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bdd4  lea     r8, [rsp+270h+pszDest]; lpName
0x18000bdd9  xor     edx, edx; bInheritHandle
0x18000bddb  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bde0  call    cs:__imp_OpenSemaphoreW
0x18000bde6  mov     [rsp+270h+var_230], rax
0x18000bdeb  test    rax, rax
0x18000bdee  jnz     short loc_18000BE17
0x18000bdf0  call    cs:__imp_GetLastError
0x18000bdf6  cmp     eax, 2
0x18000bdf9  jz      loc_18000BEF4
0x18000bdff  mov     rcx, [rbp+178h]; this
0x18000be06  mov     edx, 0D0h; void *
0x18000be0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000be10  mov     ebx, eax
0x18000be12  jmp     loc_18000BEF6
0x18000be17  lea     rdx, [rsp+270h+var_23C]; int *
0x18000be1c  mov     [rsp+270h+var_23C], 0
0x18000be24  mov     rcx, rax; hHandle
0x18000be27  mov     [rsp+270h+var_240], 0
0x18000be2f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000be34  mov     ebx, eax
0x18000be36  test    eax, eax
0x18000be38  jns     short loc_18000BE5A
0x18000be3a  mov     rcx, [rbp+178h]; this
0x18000be41  lea     r8, aWil; "wil"
0x18000be48  mov     r9d, eax; char *
0x18000be4b  mov     edx, 0D6h; void *
0x18000be50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000be55  jmp     loc_18000BEF6
0x18000be5a  lea     r8, asc_18002D068; "h"
0x18000be61  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000be66  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000be6b  lea     r8, [rsp+270h+pszDest]; lpName
0x18000be70  xor     edx, edx; bInheritHandle
0x18000be72  mov     ecx, 1F0003h; dwDesiredAccess
0x18000be77  call    cs:__imp_OpenSemaphoreW
0x18000be7d  mov     [rsp+270h+var_238], rax
0x18000be82  test    rax, rax
0x18000be85  jnz     short loc_18000BEA6
0x18000be87  mov     rcx, [rbp+178h]; this
0x18000be8e  mov     edx, 0DCh; void *
0x18000be93  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000be98  mov     ebx, eax
0x18000be9a  lea     rcx, [rsp+270h+var_238]
0x18000be9f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bea4  jmp     short loc_18000BEF6
0x18000bea6  lea     rdx, [rsp+270h+var_240]; int *
0x18000beab  mov     rcx, rax; hHandle
0x18000beae  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000beb3  mov     ebx, eax
0x18000beb5  test    eax, eax
0x18000beb7  jns     short loc_18000BED6
0x18000beb9  mov     rcx, [rbp+178h]; this
0x18000bec0  lea     r8, aWil; "wil"
0x18000bec7  mov     r9d, eax; char *
0x18000beca  mov     edx, 0DEh; void *
0x18000becf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bed4  jmp     short loc_18000BE9A
0x18000bed6  lea     rcx, [rsp+270h+var_238]
0x18000bedb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bee0  movsxd  rcx, [rsp+270h+var_240]
0x18000bee5  movsxd  rax, [rsp+270h+var_23C]
0x18000beea  shl     rcx, 1Fh
0x18000beee  or      rcx, rax
0x18000bef1  mov     [rdi], rcx
0x18000bef4  xor     ebx, ebx
0x18000bef6  lea     rcx, [rsp+270h+var_230]
0x18000befb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bf00  mov     eax, ebx
0x18000bf02  mov     rcx, [rbp+170h+var_10]
0x18000bf09  xor     rcx, rsp; StackCookie
0x18000bf0c  call    __security_check_cookie
0x18000bf11  lea     r11, [rsp+270h+var_s0]
0x18000bf19  mov     rbx, [r11+18h]
0x18000bf1d  mov     rdi, [r11+28h]
0x18000bf21  mov     rsp, r11
0x18000bf24  pop     rbp
0x18000bf25  retn
```
