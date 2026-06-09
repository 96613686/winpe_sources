# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800a83f0`
- end: `0x1800a8598`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `424`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800b5078`

## callees

- `0x18009f6dc`
- `0x1800a3f1c`
- `0x1800a7ad8`
- `0x1800a83f0`
- `0x1800a85a0`
- `0x1800a861c`
- `0x1800a9d20`
- `0x1800b3858`
- `0x1800b4864`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a8454`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a84e4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a8454`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a84e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8464`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a8464`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  size_t v11; // rdx
  unsigned int v12; // r8d
  __int64 v13; // rdx
  void *v14; // r8
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
    v23 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    if ( (unsigned __int8)____8V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___wil__YA_NAEBV__unique_any_t_V__semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil___0___T_Z(
                            &v23,
                            v13,
                            v23) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)v14, v15);
    }
    else
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
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
0x1800a83f0  mov     [rsp-8+arg_8], rbx
0x1800a83f5  mov     [rsp-8+arg_18], rdi
0x1800a83fa  push    rbp
0x1800a83fb  lea     rbp, [rsp-170h]
0x1800a8403  sub     rsp, 270h
0x1800a840a  mov     rax, cs:__security_cookie
0x1800a8411  xor     rax, rsp
0x1800a8414  mov     [rbp+170h+var_10], rax
0x1800a841b  mov     r9, rcx; pszSrc
0x1800a841e  mov     qword ptr [r8], 0
0x1800a8425  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800a842a  mov     edx, 104h; cchDest
0x1800a842f  mov     rdi, r8
0x1800a8432  call    StringCopyWorkerW
0x1800a8437  lea     r8, aP0; "_p0"
0x1800a843e  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800a8443  call    StringCchCatW
0x1800a8448  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a844d  xor     edx, edx; bInheritHandle
0x1800a844f  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a8454  call    cs:__imp_OpenSemaphoreW
0x1800a845a  mov     [rsp+270h+var_230], rax
0x1800a845f  test    rax, rax
0x1800a8462  jnz     short loc_1800A848B
0x1800a8464  call    cs:__imp_GetLastError
0x1800a846a  cmp     eax, 2
0x1800a846d  jz      loc_1800A8566
0x1800a8473  mov     rcx, [rbp+178h]; this
0x1800a847a  mov     edx, 0D0h; void *
0x1800a847f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a8484  mov     ebx, eax
0x1800a8486  jmp     loc_1800A8568
0x1800a848b  lea     rdx, [rsp+270h+var_23C]; int *
0x1800a8490  mov     [rsp+270h+var_23C], 0
0x1800a8498  mov     rcx, rax; hHandle
0x1800a849b  mov     [rsp+270h+var_240], 0
0x1800a84a3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a84a8  mov     ebx, eax
0x1800a84aa  test    eax, eax
0x1800a84ac  jns     short loc_1800A84C7
0x1800a84ae  mov     rcx, [rbp+178h]; this
0x1800a84b5  mov     r9d, eax; char *
0x1800a84b8  mov     edx, 0D6h; void *
0x1800a84bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a84c2  jmp     loc_1800A8568
0x1800a84c7  lea     r8, asc_1801FA0B0; "h"
0x1800a84ce  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800a84d3  call    StringCchCatW
0x1800a84d8  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a84dd  xor     edx, edx; bInheritHandle
0x1800a84df  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a84e4  call    cs:__imp_OpenSemaphoreW
0x1800a84ea  lea     rcx, [rsp+270h+var_238]
0x1800a84ef  mov     [rsp+270h+var_238], rax
0x1800a84f4  mov     r8, rax
0x1800a84f7  call    ??$?8V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@YA_NAEBV?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@0@$$T@Z
0x1800a84fc  test    al, al
0x1800a84fe  jz      short loc_1800A851F
0x1800a8500  mov     rcx, [rbp+178h]; this
0x1800a8507  mov     edx, 0DCh; void *
0x1800a850c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a8511  mov     ebx, eax
0x1800a8513  lea     rcx, [rsp+270h+var_238]
0x1800a8518  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a851d  jmp     short loc_1800A8568
0x1800a851f  lea     rdx, [rsp+270h+var_240]; int *
0x1800a8524  mov     rcx, r8; hHandle
0x1800a8527  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a852c  mov     ebx, eax
0x1800a852e  test    eax, eax
0x1800a8530  jns     short loc_1800A8548
0x1800a8532  mov     rcx, [rbp+178h]; this
0x1800a8539  mov     r9d, eax; char *
0x1800a853c  mov     edx, 0DEh; void *
0x1800a8541  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8546  jmp     short loc_1800A8513
0x1800a8548  lea     rcx, [rsp+270h+var_238]
0x1800a854d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a8552  movsxd  rcx, [rsp+270h+var_240]
0x1800a8557  movsxd  rax, [rsp+270h+var_23C]
0x1800a855c  shl     rcx, 1Fh
0x1800a8560  or      rcx, rax
0x1800a8563  mov     [rdi], rcx
0x1800a8566  xor     ebx, ebx
0x1800a8568  lea     rcx, [rsp+270h+var_230]
0x1800a856d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a8572  mov     eax, ebx
0x1800a8574  mov     rcx, [rbp+170h+var_10]
0x1800a857b  xor     rcx, rsp; StackCookie
0x1800a857e  call    __security_check_cookie
0x1800a8583  lea     r11, [rsp+270h+var_s0]
0x1800a858b  mov     rbx, [r11+18h]
0x1800a858f  mov     rdi, [r11+28h]
0x1800a8593  mov     rsp, r11
0x1800a8596  pop     rbp
0x1800a8597  retn
```
