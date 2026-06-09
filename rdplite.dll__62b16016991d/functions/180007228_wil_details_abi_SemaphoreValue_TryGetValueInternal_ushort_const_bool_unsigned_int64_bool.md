# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007228`
- end: `0x1800073e0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180005338`

## callees

- `0x1800036f0`
- `0x180005130`
- `0x180005e4c`
- `0x180006a54`
- `0x180006a74`
- `0x180006f90`
- `0x180007120`
- `0x180007228`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000728c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000732a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000728c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000732a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000729c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000729c`

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
0x180007228  mov     [rsp-8+arg_8], rbx
0x18000722d  mov     [rsp-8+arg_18], rdi
0x180007232  push    rbp
0x180007233  lea     rbp, [rsp-170h]
0x18000723b  sub     rsp, 270h
0x180007242  mov     rax, cs:__security_cookie
0x180007249  xor     rax, rsp
0x18000724c  mov     [rbp+170h+var_10], rax
0x180007253  mov     r9, rcx; pszSrc
0x180007256  mov     qword ptr [r8], 0
0x18000725d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180007262  mov     edx, 104h; cchDest
0x180007267  mov     rdi, r8
0x18000726a  call    StringCopyWorkerW
0x18000726f  lea     r8, aP0; "_p0"
0x180007276  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000727b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007280  lea     r8, [rsp+270h+pszDest]; lpName
0x180007285  xor     edx, edx; bInheritHandle
0x180007287  mov     ecx, 1F0003h; dwDesiredAccess
0x18000728c  call    cs:__imp_OpenSemaphoreW
0x180007292  mov     [rsp+270h+var_230], rax
0x180007297  test    rax, rax
0x18000729a  jnz     short loc_1800072CA
0x18000729c  call    cs:__imp_GetLastError
0x1800072a2  cmp     eax, 2
0x1800072a5  jz      loc_1800073AE
0x1800072ab  mov     rcx, [rbp+178h]; this
0x1800072b2  lea     r8, aWil; "wil"
0x1800072b9  mov     edx, 0D0h; void *
0x1800072be  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800072c3  mov     ebx, eax
0x1800072c5  jmp     loc_1800073B0
0x1800072ca  lea     rdx, [rsp+270h+var_23C]; int *
0x1800072cf  mov     [rsp+270h+var_23C], 0
0x1800072d7  mov     rcx, rax; hHandle
0x1800072da  mov     [rsp+270h+var_240], 0
0x1800072e2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800072e7  mov     ebx, eax
0x1800072e9  test    eax, eax
0x1800072eb  jns     short loc_18000730D
0x1800072ed  mov     rcx, [rbp+178h]; this
0x1800072f4  lea     r8, aWil; "wil"
0x1800072fb  mov     r9d, eax; char *
0x1800072fe  mov     edx, 0D6h; void *
0x180007303  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007308  jmp     loc_1800073B0
0x18000730d  lea     r8, asc_18002D950; "h"
0x180007314  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180007319  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000731e  lea     r8, [rsp+270h+pszDest]; lpName
0x180007323  xor     edx, edx; bInheritHandle
0x180007325  mov     ecx, 1F0003h; dwDesiredAccess
0x18000732a  call    cs:__imp_OpenSemaphoreW
0x180007330  mov     [rsp+270h+var_238], rax
0x180007335  test    rax, rax
0x180007338  jnz     short loc_180007360
0x18000733a  mov     rcx, [rbp+178h]; this
0x180007341  lea     r8, aWil; "wil"
0x180007348  mov     edx, 0DCh; void *
0x18000734d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007352  mov     ebx, eax
0x180007354  lea     rcx, [rsp+270h+var_238]
0x180007359  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000735e  jmp     short loc_1800073B0
0x180007360  lea     rdx, [rsp+270h+var_240]; int *
0x180007365  mov     rcx, rax; hHandle
0x180007368  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000736d  mov     ebx, eax
0x18000736f  test    eax, eax
0x180007371  jns     short loc_180007390
0x180007373  mov     rcx, [rbp+178h]; this
0x18000737a  lea     r8, aWil; "wil"
0x180007381  mov     r9d, eax; char *
0x180007384  mov     edx, 0DEh; void *
0x180007389  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000738e  jmp     short loc_180007354
0x180007390  lea     rcx, [rsp+270h+var_238]
0x180007395  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000739a  movsxd  rcx, [rsp+270h+var_240]
0x18000739f  movsxd  rax, [rsp+270h+var_23C]
0x1800073a4  shl     rcx, 1Fh
0x1800073a8  or      rcx, rax
0x1800073ab  mov     [rdi], rcx
0x1800073ae  xor     ebx, ebx
0x1800073b0  lea     rcx, [rsp+270h+var_230]
0x1800073b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800073ba  mov     eax, ebx
0x1800073bc  mov     rcx, [rbp+170h+var_10]
0x1800073c3  xor     rcx, rsp; StackCookie
0x1800073c6  call    __security_check_cookie
0x1800073cb  lea     r11, [rsp+270h+var_s0]
0x1800073d3  mov     rbx, [r11+18h]
0x1800073d7  mov     rdi, [r11+28h]
0x1800073db  mov     rsp, r11
0x1800073de  pop     rbp
0x1800073df  retn
```
