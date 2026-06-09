# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14007b05c`
- end: `0x14007b1f8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14007afe8`

## callees

- `0x1400538bc`
- `0x140075228`
- `0x140075de0`
- `0x140077da4`
- `0x140079168`
- `0x14007a60c`
- `0x14007accc`
- `0x14007b05c`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x14007b0c0`
- `KERNEL32!OpenSemaphoreW` at `0x14007b150`
- `KERNEL32!OpenSemaphoreW` at `0x14007b0c0`
- `KERNEL32!OpenSemaphoreW` at `0x14007b150`
- `KERNEL32!GetLastError` at `0x14007b0d0`
- `KERNEL32!GetLastError` at `0x14007b0d0`

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
0x14007b05c  mov     [rsp-8+arg_8], rbx
0x14007b061  mov     [rsp-8+arg_18], rdi
0x14007b066  push    rbp
0x14007b067  lea     rbp, [rsp-170h]
0x14007b06f  sub     rsp, 270h
0x14007b076  mov     rax, cs:__security_cookie
0x14007b07d  xor     rax, rsp
0x14007b080  mov     [rbp+170h+var_10], rax
0x14007b087  mov     r9, rcx; pszSrc
0x14007b08a  mov     qword ptr [r8], 0
0x14007b091  lea     rcx, [rsp+270h+pszDest]; pszDest
0x14007b096  mov     edx, 104h; cchDest
0x14007b09b  mov     rdi, r8
0x14007b09e  call    StringCopyWorkerW
0x14007b0a3  lea     r8, aP0; "_p0"
0x14007b0aa  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14007b0af  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14007b0b4  lea     r8, [rsp+270h+pszDest]; lpName
0x14007b0b9  xor     edx, edx; bInheritHandle
0x14007b0bb  mov     ecx, 1F0003h; dwDesiredAccess
0x14007b0c0  call    cs:__imp_OpenSemaphoreW
0x14007b0c6  mov     [rsp+270h+var_230], rax
0x14007b0cb  test    rax, rax
0x14007b0ce  jnz     short loc_14007B0F7
0x14007b0d0  call    cs:__imp_GetLastError
0x14007b0d6  cmp     eax, 2
0x14007b0d9  jz      loc_14007B1C6
0x14007b0df  mov     rcx, [rbp+178h]; this
0x14007b0e6  mov     edx, 0D0h; void *
0x14007b0eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14007b0f0  mov     ebx, eax
0x14007b0f2  jmp     loc_14007B1C8
0x14007b0f7  lea     rdx, [rsp+270h+var_23C]; int *
0x14007b0fc  mov     [rsp+270h+var_23C], 0
0x14007b104  mov     rcx, rax; hHandle
0x14007b107  mov     [rsp+270h+var_240], 0
0x14007b10f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14007b114  mov     ebx, eax
0x14007b116  test    eax, eax
0x14007b118  jns     short loc_14007B133
0x14007b11a  mov     rcx, [rbp+178h]; this
0x14007b121  mov     r9d, eax; char *
0x14007b124  mov     edx, 0D6h; void *
0x14007b129  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007b12e  jmp     loc_14007B1C8
0x14007b133  lea     r8, asc_14009D090; "h"
0x14007b13a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14007b13f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14007b144  lea     r8, [rsp+270h+pszDest]; lpName
0x14007b149  xor     edx, edx; bInheritHandle
0x14007b14b  mov     ecx, 1F0003h; dwDesiredAccess
0x14007b150  call    cs:__imp_OpenSemaphoreW
0x14007b156  mov     [rsp+270h+var_238], rax
0x14007b15b  test    rax, rax
0x14007b15e  jnz     short loc_14007B17F
0x14007b160  mov     rcx, [rbp+178h]; this
0x14007b167  mov     edx, 0DCh; void *
0x14007b16c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14007b171  mov     ebx, eax
0x14007b173  lea     rcx, [rsp+270h+var_238]
0x14007b178  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14007b17d  jmp     short loc_14007B1C8
0x14007b17f  lea     rdx, [rsp+270h+var_240]; int *
0x14007b184  mov     rcx, rax; hHandle
0x14007b187  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14007b18c  mov     ebx, eax
0x14007b18e  test    eax, eax
0x14007b190  jns     short loc_14007B1A8
0x14007b192  mov     rcx, [rbp+178h]; this
0x14007b199  mov     r9d, eax; char *
0x14007b19c  mov     edx, 0DEh; void *
0x14007b1a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14007b1a6  jmp     short loc_14007B173
0x14007b1a8  lea     rcx, [rsp+270h+var_238]
0x14007b1ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14007b1b2  movsxd  rcx, [rsp+270h+var_240]
0x14007b1b7  movsxd  rax, [rsp+270h+var_23C]
0x14007b1bc  shl     rcx, 1Fh
0x14007b1c0  or      rcx, rax
0x14007b1c3  mov     [rdi], rcx
0x14007b1c6  xor     ebx, ebx
0x14007b1c8  lea     rcx, [rsp+270h+var_230]
0x14007b1cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14007b1d2  mov     eax, ebx
0x14007b1d4  mov     rcx, [rbp+170h+var_10]
0x14007b1db  xor     rcx, rsp; StackCookie
0x14007b1de  call    __security_check_cookie
0x14007b1e3  lea     r11, [rsp+270h+var_s0]
0x14007b1eb  mov     rbx, [r11+18h]
0x14007b1ef  mov     rdi, [r11+28h]
0x14007b1f3  mov     rsp, r11
0x14007b1f6  pop     rbp
0x14007b1f7  retn
```
