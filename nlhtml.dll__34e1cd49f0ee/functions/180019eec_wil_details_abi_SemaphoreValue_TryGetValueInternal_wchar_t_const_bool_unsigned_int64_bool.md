# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180019eec`
- end: `0x18001a09c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180019e68`

## callees

- `0x1800112e0`
- `0x180011324`
- `0x1800138ec`
- `0x180014130`
- `0x1800161c4`
- `0x18001779c`
- `0x18001943c`
- `0x180019eec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019f55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019fee`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019f55`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019fee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f65`

## pseudocode

```c
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
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180019eec  mov     [rsp-8+arg_8], rbx
0x180019ef1  push    rbp
0x180019ef2  push    rdi
0x180019ef3  push    r14
0x180019ef5  lea     rbp, [rsp-160h]
0x180019efd  sub     rsp, 260h
0x180019f04  mov     rax, cs:__security_cookie
0x180019f0b  xor     rax, rsp
0x180019f0e  mov     [rbp+170h+var_20], rax
0x180019f15  mov     rdi, r8
0x180019f18  mov     qword ptr [r8], 0
0x180019f1f  mov     r8, rcx; wchar_t *
0x180019f22  mov     r14d, 104h
0x180019f28  mov     edx, r14d; unsigned __int64
0x180019f2b  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180019f30  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180019f35  lea     r8, aP0; "_p0"
0x180019f3c  mov     edx, r14d; unsigned __int64
0x180019f3f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180019f44  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180019f49  lea     r8, [rsp+270h+Name]; lpName
0x180019f4e  xor     edx, edx; bInheritHandle
0x180019f50  mov     ecx, 1F0003h; dwDesiredAccess
0x180019f55  call    cs:__imp_OpenSemaphoreW
0x180019f5b  mov     [rsp+270h+var_240], rax
0x180019f60  test    rax, rax
0x180019f63  jnz     short loc_180019F8B
0x180019f65  call    cs:__imp_GetLastError
0x180019f6b  cmp     eax, 2
0x180019f6e  jz      loc_18001A06B
0x180019f74  mov     rcx, [rbp+178h]; this
0x180019f7b  lea     edx, [r14-34h]; void *
0x180019f7f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019f84  mov     ebx, eax
0x180019f86  jmp     loc_18001A06D
0x180019f8b  lea     rdx, [rsp+270h+var_24C]; int *
0x180019f90  mov     [rsp+270h+var_24C], 0
0x180019f98  mov     rcx, rax; hHandle
0x180019f9b  mov     [rsp+270h+var_250], 0; int
0x180019fa3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180019fa8  mov     ebx, eax
0x180019faa  test    eax, eax
0x180019fac  jns     short loc_180019FCE
0x180019fae  mov     rcx, [rbp+178h]; this
0x180019fb5  lea     r8, aWil; "wil"
0x180019fbc  mov     r9d, eax; char *
0x180019fbf  mov     edx, 0D6h; void *
0x180019fc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fc9  jmp     loc_18001A06D
0x180019fce  lea     r8, asc_180031750; "h"
0x180019fd5  mov     rdx, r14; unsigned __int64
0x180019fd8  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180019fdd  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180019fe2  lea     r8, [rsp+270h+Name]; lpName
0x180019fe7  xor     edx, edx; bInheritHandle
0x180019fe9  mov     ecx, 1F0003h; dwDesiredAccess
0x180019fee  call    cs:__imp_OpenSemaphoreW
0x180019ff4  mov     [rsp+270h+var_248], rax
0x180019ff9  test    rax, rax
0x180019ffc  jnz     short loc_18001A01D
0x180019ffe  mov     rcx, [rbp+178h]; this
0x18001a005  mov     edx, 0DCh; void *
0x18001a00a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001a00f  mov     ebx, eax
0x18001a011  lea     rcx, [rsp+270h+var_248]
0x18001a016  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a01b  jmp     short loc_18001A06D
0x18001a01d  lea     rdx, [rsp+270h+var_250]; int *
0x18001a022  mov     rcx, rax; hHandle
0x18001a025  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001a02a  mov     ebx, eax
0x18001a02c  test    eax, eax
0x18001a02e  jns     short loc_18001A04D
0x18001a030  mov     rcx, [rbp+178h]; this
0x18001a037  lea     r8, aWil; "wil"
0x18001a03e  mov     r9d, eax; char *
0x18001a041  mov     edx, 0DEh; void *
0x18001a046  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a04b  jmp     short loc_18001A011
0x18001a04d  lea     rcx, [rsp+270h+var_248]
0x18001a052  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a057  movsxd  rcx, [rsp+270h+var_250]
0x18001a05c  movsxd  rax, [rsp+270h+var_24C]
0x18001a061  shl     rcx, 1Fh
0x18001a065  or      rcx, rax
0x18001a068  mov     [rdi], rcx
0x18001a06b  xor     ebx, ebx
0x18001a06d  lea     rcx, [rsp+270h+var_240]
0x18001a072  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001a077  mov     eax, ebx
0x18001a079  mov     rcx, [rbp+170h+var_20]
0x18001a080  xor     rcx, rsp; StackCookie
0x18001a083  call    __security_check_cookie
0x18001a088  mov     rbx, [rsp+270h+arg_8]
0x18001a090  add     rsp, 260h
0x18001a097  pop     r14
0x18001a099  pop     rdi
0x18001a09a  pop     rbp
0x18001a09b  retn
```
