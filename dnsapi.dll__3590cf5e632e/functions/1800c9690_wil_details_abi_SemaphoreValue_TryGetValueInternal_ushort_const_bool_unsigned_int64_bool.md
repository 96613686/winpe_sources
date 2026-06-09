# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800c9690`
- end: `0x1800c9845`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `437`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800c9618`

## callees

- `0x18004e3b0`
- `0x1800587a0`
- `0x18008b5f0`
- `0x1800c681c`
- `0x1800c7ab8`
- `0x1800c9010`
- `0x1800c9030`
- `0x1800c9690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c970f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c970f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800c96f9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800c9797`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800c96f9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800c9797`

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
0x1800c9690  mov     [rsp-8+arg_8], rbx
0x1800c9695  push    rbp
0x1800c9696  push    rdi
0x1800c9697  push    r14
0x1800c9699  lea     rbp, [rsp-160h]
0x1800c96a1  sub     rsp, 260h
0x1800c96a8  mov     rax, cs:__security_cookie
0x1800c96af  xor     rax, rsp
0x1800c96b2  mov     [rbp+170h+var_20], rax
0x1800c96b9  mov     rdi, r8
0x1800c96bc  mov     qword ptr [r8], 0
0x1800c96c3  mov     r8, rcx; pszSrc
0x1800c96c6  mov     r14d, 104h
0x1800c96cc  mov     edx, r14d; cchDest
0x1800c96cf  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800c96d4  call    StringCchCopyW
0x1800c96d9  lea     r8, aP0; "_p0"
0x1800c96e0  mov     edx, r14d; cchDest
0x1800c96e3  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800c96e8  call    StringCchCatW
0x1800c96ed  lea     r8, [rsp+270h+pszDest]; lpName
0x1800c96f2  xor     edx, edx; bInheritHandle
0x1800c96f4  mov     ecx, 1F0003h; dwDesiredAccess
0x1800c96f9  call    cs:__imp_OpenSemaphoreW
0x1800c9700  nop     dword ptr [rax+rax+00h]
0x1800c9705  mov     [rsp+270h+var_240], rax
0x1800c970a  test    rax, rax
0x1800c970d  jnz     short loc_1800C973B
0x1800c970f  call    cs:__imp_GetLastError
0x1800c9716  nop     dword ptr [rax+rax+00h]
0x1800c971b  cmp     eax, 2
0x1800c971e  jz      loc_1800C9813
0x1800c9724  mov     rcx, [rbp+178h]; this
0x1800c972b  lea     edx, [r14-34h]; void *
0x1800c972f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c9734  mov     ebx, eax
0x1800c9736  jmp     loc_1800C9815
0x1800c973b  lea     rdx, [rsp+270h+var_24C]; int *
0x1800c9740  mov     [rsp+270h+var_24C], 0
0x1800c9748  mov     rcx, rax; hHandle
0x1800c974b  mov     [rsp+270h+var_250], 0; int
0x1800c9753  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800c9758  mov     ebx, eax
0x1800c975a  test    eax, eax
0x1800c975c  jns     short loc_1800C9777
0x1800c975e  mov     rcx, [rbp+178h]; this
0x1800c9765  mov     r9d, eax; char *
0x1800c9768  mov     edx, 0D6h; void *
0x1800c976d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c9772  jmp     loc_1800C9815
0x1800c9777  lea     r8, asc_1800FC8E0; "h"
0x1800c977e  mov     rdx, r14; cchDest
0x1800c9781  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800c9786  call    StringCchCatW
0x1800c978b  lea     r8, [rsp+270h+pszDest]; lpName
0x1800c9790  xor     edx, edx; bInheritHandle
0x1800c9792  mov     ecx, 1F0003h; dwDesiredAccess
0x1800c9797  call    cs:__imp_OpenSemaphoreW
0x1800c979e  nop     dword ptr [rax+rax+00h]
0x1800c97a3  mov     [rsp+270h+var_248], rax
0x1800c97a8  test    rax, rax
0x1800c97ab  jnz     short loc_1800C97CC
0x1800c97ad  mov     rcx, [rbp+178h]; this
0x1800c97b4  mov     edx, 0DCh; void *
0x1800c97b9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800c97be  mov     ebx, eax
0x1800c97c0  lea     rcx, [rsp+270h+var_248]
0x1800c97c5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c97ca  jmp     short loc_1800C9815
0x1800c97cc  lea     rdx, [rsp+270h+var_250]; int *
0x1800c97d1  mov     rcx, rax; hHandle
0x1800c97d4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800c97d9  mov     ebx, eax
0x1800c97db  test    eax, eax
0x1800c97dd  jns     short loc_1800C97F5
0x1800c97df  mov     rcx, [rbp+178h]; this
0x1800c97e6  mov     r9d, eax; char *
0x1800c97e9  mov     edx, 0DEh; void *
0x1800c97ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c97f3  jmp     short loc_1800C97C0
0x1800c97f5  lea     rcx, [rsp+270h+var_248]
0x1800c97fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c97ff  movsxd  rcx, [rsp+270h+var_250]
0x1800c9804  movsxd  rax, [rsp+270h+var_24C]
0x1800c9809  shl     rcx, 1Fh
0x1800c980d  or      rcx, rax
0x1800c9810  mov     [rdi], rcx
0x1800c9813  xor     ebx, ebx
0x1800c9815  lea     rcx, [rsp+270h+var_240]
0x1800c981a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c981f  mov     eax, ebx
0x1800c9821  mov     rcx, [rbp+170h+var_20]
0x1800c9828  xor     rcx, rsp; StackCookie
0x1800c982b  call    __security_check_cookie
0x1800c9830  mov     rbx, [rsp+270h+arg_8]
0x1800c9838  add     rsp, 260h
0x1800c983f  pop     r14
0x1800c9841  pop     rdi
0x1800c9842  pop     rbp
0x1800c9843  retn
```
