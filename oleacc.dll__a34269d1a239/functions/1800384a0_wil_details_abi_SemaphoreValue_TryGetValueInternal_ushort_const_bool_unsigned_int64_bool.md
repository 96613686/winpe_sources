# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800384a0`
- end: `0x18003863c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003842c`

## callees

- `0x18001e4c0`
- `0x1800334c0`
- `0x180035a88`
- `0x1800378bc`
- `0x1800378dc`
- `0x180037fdc`
- `0x1800380c0`
- `0x1800384a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038514`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038514`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180038504`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180038594`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180038504`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180038594`

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
0x1800384a0  mov     [rsp-8+arg_8], rbx
0x1800384a5  mov     [rsp-8+arg_18], rdi
0x1800384aa  push    rbp
0x1800384ab  lea     rbp, [rsp-170h]
0x1800384b3  sub     rsp, 270h
0x1800384ba  mov     rax, cs:__security_cookie
0x1800384c1  xor     rax, rsp
0x1800384c4  mov     [rbp+170h+var_10], rax
0x1800384cb  mov     r9, rcx; pszSrc
0x1800384ce  mov     qword ptr [r8], 0
0x1800384d5  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800384da  mov     edx, 104h; cchDest
0x1800384df  mov     rdi, r8
0x1800384e2  call    StringCopyWorkerW
0x1800384e7  lea     r8, aP0; "_p0"
0x1800384ee  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800384f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800384f8  lea     r8, [rsp+270h+pszDest]; lpName
0x1800384fd  xor     edx, edx; bInheritHandle
0x1800384ff  mov     ecx, 1F0003h; dwDesiredAccess
0x180038504  call    cs:__imp_OpenSemaphoreW
0x18003850a  mov     [rsp+270h+var_230], rax
0x18003850f  test    rax, rax
0x180038512  jnz     short loc_18003853B
0x180038514  call    cs:__imp_GetLastError
0x18003851a  cmp     eax, 2
0x18003851d  jz      loc_18003860A
0x180038523  mov     rcx, [rbp+178h]; this
0x18003852a  mov     edx, 0D0h; void *
0x18003852f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180038534  mov     ebx, eax
0x180038536  jmp     loc_18003860C
0x18003853b  lea     rdx, [rsp+270h+var_23C]; int *
0x180038540  mov     [rsp+270h+var_23C], 0
0x180038548  mov     rcx, rax; hHandle
0x18003854b  mov     [rsp+270h+var_240], 0
0x180038553  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180038558  mov     ebx, eax
0x18003855a  test    eax, eax
0x18003855c  jns     short loc_180038577
0x18003855e  mov     rcx, [rbp+178h]; this
0x180038565  mov     r9d, eax; char *
0x180038568  mov     edx, 0D6h; void *
0x18003856d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038572  jmp     loc_18003860C
0x180038577  lea     r8, asc_180057778; "h"
0x18003857e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180038583  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180038588  lea     r8, [rsp+270h+pszDest]; lpName
0x18003858d  xor     edx, edx; bInheritHandle
0x18003858f  mov     ecx, 1F0003h; dwDesiredAccess
0x180038594  call    cs:__imp_OpenSemaphoreW
0x18003859a  mov     [rsp+270h+var_238], rax
0x18003859f  test    rax, rax
0x1800385a2  jnz     short loc_1800385C3
0x1800385a4  mov     rcx, [rbp+178h]; this
0x1800385ab  mov     edx, 0DCh; void *
0x1800385b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800385b5  mov     ebx, eax
0x1800385b7  lea     rcx, [rsp+270h+var_238]
0x1800385bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800385c1  jmp     short loc_18003860C
0x1800385c3  lea     rdx, [rsp+270h+var_240]; int *
0x1800385c8  mov     rcx, rax; hHandle
0x1800385cb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800385d0  mov     ebx, eax
0x1800385d2  test    eax, eax
0x1800385d4  jns     short loc_1800385EC
0x1800385d6  mov     rcx, [rbp+178h]; this
0x1800385dd  mov     r9d, eax; char *
0x1800385e0  mov     edx, 0DEh; void *
0x1800385e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800385ea  jmp     short loc_1800385B7
0x1800385ec  lea     rcx, [rsp+270h+var_238]
0x1800385f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800385f6  movsxd  rcx, [rsp+270h+var_240]
0x1800385fb  movsxd  rax, [rsp+270h+var_23C]
0x180038600  shl     rcx, 1Fh
0x180038604  or      rcx, rax
0x180038607  mov     [rdi], rcx
0x18003860a  xor     ebx, ebx
0x18003860c  lea     rcx, [rsp+270h+var_230]
0x180038611  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180038616  mov     eax, ebx
0x180038618  mov     rcx, [rbp+170h+var_10]
0x18003861f  xor     rcx, rsp; StackCookie
0x180038622  call    __security_check_cookie
0x180038627  lea     r11, [rsp+270h+var_s0]
0x18003862f  mov     rbx, [r11+18h]
0x180038633  mov     rdi, [r11+28h]
0x180038637  mov     rsp, r11
0x18003863a  pop     rbp
0x18003863b  retn
```
