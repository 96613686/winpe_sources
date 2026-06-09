# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a600`
- end: `0x18000a7a2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a58c`

## callees

- `0x180003df0`
- `0x180005d10`
- `0x180007244`
- `0x18000987c`
- `0x18000989c`
- `0x18000a0f4`
- `0x18000a600`
- `0x18002f0e0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18000a669`
- `KERNEL32!OpenSemaphoreW` at `0x18000a6fb`
- `KERNEL32!OpenSemaphoreW` at `0x18000a669`
- `KERNEL32!OpenSemaphoreW` at `0x18000a6fb`
- `KERNEL32!GetLastError` at `0x18000a679`
- `KERNEL32!GetLastError` at `0x18000a679`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
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
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
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
0x18000a600  mov     [rsp-8+arg_8], rbx
0x18000a605  push    rbp
0x18000a606  push    rdi
0x18000a607  push    r14
0x18000a609  lea     rbp, [rsp-160h]
0x18000a611  sub     rsp, 260h
0x18000a618  mov     rax, cs:__security_cookie
0x18000a61f  xor     rax, rsp
0x18000a622  mov     [rbp+170h+var_20], rax
0x18000a629  mov     rdi, r8
0x18000a62c  mov     qword ptr [r8], 0
0x18000a633  mov     r8, rcx; wchar_t *
0x18000a636  mov     r14d, 104h
0x18000a63c  mov     edx, r14d; unsigned __int64
0x18000a63f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000a644  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a649  lea     r8, aP0; "_p0"
0x18000a650  mov     edx, r14d; unsigned __int64
0x18000a653  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000a658  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a65d  lea     r8, [rsp+270h+Name]; lpName
0x18000a662  xor     edx, edx; bInheritHandle
0x18000a664  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a669  call    cs:__imp_OpenSemaphoreW
0x18000a66f  mov     [rsp+270h+var_240], rax
0x18000a674  test    rax, rax
0x18000a677  jnz     short loc_18000A69F
0x18000a679  call    cs:__imp_GetLastError
0x18000a67f  cmp     eax, 2
0x18000a682  jz      loc_18000A771
0x18000a688  mov     rcx, [rbp+178h]; this
0x18000a68f  lea     edx, [r14-34h]; void *
0x18000a693  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a698  mov     ebx, eax
0x18000a69a  jmp     loc_18000A773
0x18000a69f  mov     [rsp+270h+var_24C], 0
0x18000a6a7  mov     [rsp+270h+var_250], 0; int
0x18000a6af  lea     rdx, [rsp+270h+var_24C]; int *
0x18000a6b4  mov     rcx, rax; hHandle
0x18000a6b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a6bc  mov     ebx, eax
0x18000a6be  test    eax, eax
0x18000a6c0  jns     short loc_18000A6DB
0x18000a6c2  mov     rcx, [rbp+178h]; this
0x18000a6c9  mov     r9d, eax; char *
0x18000a6cc  mov     edx, 0D6h; void *
0x18000a6d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a6d6  jmp     loc_18000A773
0x18000a6db  lea     r8, asc_180034918; "h"
0x18000a6e2  mov     rdx, r14; unsigned __int64
0x18000a6e5  lea     rcx, [rsp+270h+Name]; wchar_t *
0x18000a6ea  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000a6ef  lea     r8, [rsp+270h+Name]; lpName
0x18000a6f4  xor     edx, edx; bInheritHandle
0x18000a6f6  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a6fb  call    cs:__imp_OpenSemaphoreW
0x18000a701  mov     [rsp+270h+var_248], rax
0x18000a706  test    rax, rax
0x18000a709  jnz     short loc_18000A72A
0x18000a70b  mov     rcx, [rbp+178h]; this
0x18000a712  mov     edx, 0DCh; void *
0x18000a717  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a71c  mov     ebx, eax
0x18000a71e  lea     rcx, [rsp+270h+var_248]
0x18000a723  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a728  jmp     short loc_18000A773
0x18000a72a  lea     rdx, [rsp+270h+var_250]; int *
0x18000a72f  mov     rcx, rax; hHandle
0x18000a732  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a737  mov     ebx, eax
0x18000a739  test    eax, eax
0x18000a73b  jns     short loc_18000A753
0x18000a73d  mov     rcx, [rbp+178h]; this
0x18000a744  mov     r9d, eax; char *
0x18000a747  mov     edx, 0DEh; void *
0x18000a74c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a751  jmp     short loc_18000A71E
0x18000a753  lea     rcx, [rsp+270h+var_248]
0x18000a758  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a75d  movsxd  rcx, [rsp+270h+var_250]
0x18000a762  shl     rcx, 1Fh
0x18000a766  movsxd  rax, [rsp+270h+var_24C]
0x18000a76b  or      rcx, rax
0x18000a76e  mov     [rdi], rcx
0x18000a771  xor     ebx, ebx
0x18000a773  lea     rcx, [rsp+270h+var_240]
0x18000a778  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a77d  mov     eax, ebx
0x18000a77f  mov     rcx, [rbp+170h+var_20]
0x18000a786  xor     rcx, rsp; StackCookie
0x18000a789  call    __security_check_cookie
0x18000a78e  mov     rbx, [rsp+270h+arg_8]
0x18000a796  add     rsp, 260h
0x18000a79d  pop     r14
0x18000a79f  pop     rdi
0x18000a7a0  pop     rbp
0x18000a7a1  retn
```
