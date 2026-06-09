# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18007a798`
- end: `0x18007a934`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007a724`

## callees

- `0x180075ff8`
- `0x180077988`
- `0x180079ccc`
- `0x180079cec`
- `0x18007a224`
- `0x18007a36c`
- `0x18007a798`
- `0x180091140`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007a80c`
- `KERNEL32!GetLastError` at `0x18007a80c`
- `KERNEL32!OpenSemaphoreW` at `0x18007a7fc`
- `KERNEL32!OpenSemaphoreW` at `0x18007a88c`
- `KERNEL32!OpenSemaphoreW` at `0x18007a7fc`
- `KERNEL32!OpenSemaphoreW` at `0x18007a88c`

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
0x18007a798  mov     [rsp-8+arg_8], rbx
0x18007a79d  mov     [rsp-8+arg_18], rdi
0x18007a7a2  push    rbp
0x18007a7a3  lea     rbp, [rsp-170h]
0x18007a7ab  sub     rsp, 270h
0x18007a7b2  mov     rax, cs:__security_cookie
0x18007a7b9  xor     rax, rsp
0x18007a7bc  mov     [rbp+170h+var_10], rax
0x18007a7c3  mov     r9, rcx; pszSrc
0x18007a7c6  mov     qword ptr [r8], 0
0x18007a7cd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18007a7d2  mov     edx, 104h; cchDest
0x18007a7d7  mov     rdi, r8
0x18007a7da  call    StringCopyWorkerW
0x18007a7df  lea     r8, aP0; "_p0"
0x18007a7e6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18007a7eb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007a7f0  lea     r8, [rsp+270h+pszDest]; lpName
0x18007a7f5  xor     edx, edx; bInheritHandle
0x18007a7f7  mov     ecx, 1F0003h; dwDesiredAccess
0x18007a7fc  call    cs:__imp_OpenSemaphoreW
0x18007a802  mov     [rsp+270h+var_230], rax
0x18007a807  test    rax, rax
0x18007a80a  jnz     short loc_18007A833
0x18007a80c  call    cs:__imp_GetLastError
0x18007a812  cmp     eax, 2
0x18007a815  jz      loc_18007A902
0x18007a81b  mov     rcx, [rbp+178h]; this
0x18007a822  mov     edx, 0D0h; void *
0x18007a827  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007a82c  mov     ebx, eax
0x18007a82e  jmp     loc_18007A904
0x18007a833  lea     rdx, [rsp+270h+var_23C]; int *
0x18007a838  mov     [rsp+270h+var_23C], 0
0x18007a840  mov     rcx, rax; hHandle
0x18007a843  mov     [rsp+270h+var_240], 0
0x18007a84b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18007a850  mov     ebx, eax
0x18007a852  test    eax, eax
0x18007a854  jns     short loc_18007A86F
0x18007a856  mov     rcx, [rbp+178h]; this
0x18007a85d  mov     r9d, eax; char *
0x18007a860  mov     edx, 0D6h; void *
0x18007a865  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a86a  jmp     loc_18007A904
0x18007a86f  lea     r8, asc_180099BA0; "h"
0x18007a876  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18007a87b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007a880  lea     r8, [rsp+270h+pszDest]; lpName
0x18007a885  xor     edx, edx; bInheritHandle
0x18007a887  mov     ecx, 1F0003h; dwDesiredAccess
0x18007a88c  call    cs:__imp_OpenSemaphoreW
0x18007a892  mov     [rsp+270h+var_238], rax
0x18007a897  test    rax, rax
0x18007a89a  jnz     short loc_18007A8BB
0x18007a89c  mov     rcx, [rbp+178h]; this
0x18007a8a3  mov     edx, 0DCh; void *
0x18007a8a8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007a8ad  mov     ebx, eax
0x18007a8af  lea     rcx, [rsp+270h+var_238]
0x18007a8b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007a8b9  jmp     short loc_18007A904
0x18007a8bb  lea     rdx, [rsp+270h+var_240]; int *
0x18007a8c0  mov     rcx, rax; hHandle
0x18007a8c3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18007a8c8  mov     ebx, eax
0x18007a8ca  test    eax, eax
0x18007a8cc  jns     short loc_18007A8E4
0x18007a8ce  mov     rcx, [rbp+178h]; this
0x18007a8d5  mov     r9d, eax; char *
0x18007a8d8  mov     edx, 0DEh; void *
0x18007a8dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007a8e2  jmp     short loc_18007A8AF
0x18007a8e4  lea     rcx, [rsp+270h+var_238]
0x18007a8e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007a8ee  movsxd  rcx, [rsp+270h+var_240]
0x18007a8f3  movsxd  rax, [rsp+270h+var_23C]
0x18007a8f8  shl     rcx, 1Fh
0x18007a8fc  or      rcx, rax
0x18007a8ff  mov     [rdi], rcx
0x18007a902  xor     ebx, ebx
0x18007a904  lea     rcx, [rsp+270h+var_230]
0x18007a909  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007a90e  mov     eax, ebx
0x18007a910  mov     rcx, [rbp+170h+var_10]
0x18007a917  xor     rcx, rsp; StackCookie
0x18007a91a  call    __security_check_cookie
0x18007a91f  lea     r11, [rsp+270h+var_s0]
0x18007a927  mov     rbx, [r11+18h]
0x18007a92b  mov     rdi, [r11+28h]
0x18007a92f  mov     rsp, r11
0x18007a932  pop     rbp
0x18007a933  retn
```
