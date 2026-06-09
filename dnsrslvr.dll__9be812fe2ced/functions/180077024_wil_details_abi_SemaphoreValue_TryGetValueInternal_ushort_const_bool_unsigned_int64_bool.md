# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180077024`
- end: `0x1800771c6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180076fb0`

## callees

- `0x1800088f0`
- `0x180040448`
- `0x180046ec0`
- `0x180074098`
- `0x180075270`
- `0x1800767c4`
- `0x1800767e4`
- `0x180077024`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007709d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007709d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18007708d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18007711f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18007708d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18007711f`

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
0x180077024  mov     [rsp-8+arg_8], rbx
0x180077029  push    rbp
0x18007702a  push    rdi
0x18007702b  push    r14
0x18007702d  lea     rbp, [rsp-160h]
0x180077035  sub     rsp, 260h
0x18007703c  mov     rax, cs:__security_cookie
0x180077043  xor     rax, rsp
0x180077046  mov     [rbp+170h+var_20], rax
0x18007704d  mov     rdi, r8
0x180077050  mov     qword ptr [r8], 0
0x180077057  mov     r8, rcx; pszSrc
0x18007705a  mov     r14d, 104h
0x180077060  mov     edx, r14d; cchDest
0x180077063  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180077068  call    StringCchCopyW
0x18007706d  lea     r8, aP0; "_p0"
0x180077074  mov     edx, r14d; cchDest
0x180077077  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18007707c  call    StringCchCatW
0x180077081  lea     r8, [rsp+270h+pszDest]; lpName
0x180077086  xor     edx, edx; bInheritHandle
0x180077088  mov     ecx, 1F0003h; dwDesiredAccess
0x18007708d  call    cs:__imp_OpenSemaphoreW
0x180077093  mov     [rsp+270h+var_240], rax
0x180077098  test    rax, rax
0x18007709b  jnz     short loc_1800770C3
0x18007709d  call    cs:__imp_GetLastError
0x1800770a3  cmp     eax, 2
0x1800770a6  jz      loc_180077195
0x1800770ac  mov     rcx, [rbp+178h]; this
0x1800770b3  lea     edx, [r14-34h]; void *
0x1800770b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800770bc  mov     ebx, eax
0x1800770be  jmp     loc_180077197
0x1800770c3  lea     rdx, [rsp+270h+var_24C]; int *
0x1800770c8  mov     [rsp+270h+var_24C], 0
0x1800770d0  mov     rcx, rax; hHandle
0x1800770d3  mov     [rsp+270h+var_250], 0; int
0x1800770db  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800770e0  mov     ebx, eax
0x1800770e2  test    eax, eax
0x1800770e4  jns     short loc_1800770FF
0x1800770e6  mov     rcx, [rbp+178h]; this
0x1800770ed  mov     r9d, eax; char *
0x1800770f0  mov     edx, 0D6h; void *
0x1800770f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800770fa  jmp     loc_180077197
0x1800770ff  lea     r8, asc_18009D060; "h"
0x180077106  mov     rdx, r14; cchDest
0x180077109  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18007710e  call    StringCchCatW
0x180077113  lea     r8, [rsp+270h+pszDest]; lpName
0x180077118  xor     edx, edx; bInheritHandle
0x18007711a  mov     ecx, 1F0003h; dwDesiredAccess
0x18007711f  call    cs:__imp_OpenSemaphoreW
0x180077125  mov     [rsp+270h+var_248], rax
0x18007712a  test    rax, rax
0x18007712d  jnz     short loc_18007714E
0x18007712f  mov     rcx, [rbp+178h]; this
0x180077136  mov     edx, 0DCh; void *
0x18007713b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180077140  mov     ebx, eax
0x180077142  lea     rcx, [rsp+270h+var_248]
0x180077147  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007714c  jmp     short loc_180077197
0x18007714e  lea     rdx, [rsp+270h+var_250]; int *
0x180077153  mov     rcx, rax; hHandle
0x180077156  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18007715b  mov     ebx, eax
0x18007715d  test    eax, eax
0x18007715f  jns     short loc_180077177
0x180077161  mov     rcx, [rbp+178h]; this
0x180077168  mov     r9d, eax; char *
0x18007716b  mov     edx, 0DEh; void *
0x180077170  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077175  jmp     short loc_180077142
0x180077177  lea     rcx, [rsp+270h+var_248]
0x18007717c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180077181  movsxd  rcx, [rsp+270h+var_250]
0x180077186  movsxd  rax, [rsp+270h+var_24C]
0x18007718b  shl     rcx, 1Fh
0x18007718f  or      rcx, rax
0x180077192  mov     [rdi], rcx
0x180077195  xor     ebx, ebx
0x180077197  lea     rcx, [rsp+270h+var_240]
0x18007719c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800771a1  mov     eax, ebx
0x1800771a3  mov     rcx, [rbp+170h+var_20]
0x1800771aa  xor     rcx, rsp; StackCookie
0x1800771ad  call    __security_check_cookie
0x1800771b2  mov     rbx, [rsp+270h+arg_8]
0x1800771ba  add     rsp, 260h
0x1800771c1  pop     r14
0x1800771c3  pop     rdi
0x1800771c4  pop     rbp
0x1800771c5  retn
```
