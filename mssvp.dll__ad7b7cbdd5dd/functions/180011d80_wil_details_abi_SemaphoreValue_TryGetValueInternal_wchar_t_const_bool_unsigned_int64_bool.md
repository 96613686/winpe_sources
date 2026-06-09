# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180011d80`
- end: `0x180011f3e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180011cfc`

## callees

- `0x180003df0`
- `0x180004080`
- `0x1800056f4`
- `0x180006270`
- `0x18000a610`
- `0x18000de3c`
- `0x180011374`
- `0x180011d80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011df9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011de9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011e89`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011de9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180011e89`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x180011d80  mov     [rsp-8+arg_8], rbx
0x180011d85  push    rbp
0x180011d86  push    rdi
0x180011d87  push    r14
0x180011d89  lea     rbp, [rsp-160h]
0x180011d91  sub     rsp, 260h
0x180011d98  mov     rax, cs:__security_cookie
0x180011d9f  xor     rax, rsp
0x180011da2  mov     [rbp+170h+var_20], rax
0x180011da9  mov     rdi, r8
0x180011dac  mov     qword ptr [r8], 0
0x180011db3  mov     r8, rcx; wchar_t *
0x180011db6  mov     r14d, 104h
0x180011dbc  mov     edx, r14d; unsigned __int64
0x180011dbf  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180011dc4  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180011dc9  lea     r8, aP0; "_p0"
0x180011dd0  mov     edx, r14d; unsigned __int64
0x180011dd3  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180011dd8  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180011ddd  lea     r8, [rsp+270h+Name]; lpName
0x180011de2  xor     edx, edx; bInheritHandle
0x180011de4  mov     ecx, 1F0003h; dwDesiredAccess
0x180011de9  call    cs:__imp_OpenSemaphoreW
0x180011def  mov     [rsp+270h+var_240], rax
0x180011df4  test    rax, rax
0x180011df7  jnz     short loc_180011E26
0x180011df9  call    cs:__imp_GetLastError
0x180011dff  cmp     eax, 2
0x180011e02  jz      loc_180011F0D
0x180011e08  mov     rcx, [rbp+178h]; this
0x180011e0f  lea     r8, aWil; "wil"
0x180011e16  lea     edx, [r14-34h]; void *
0x180011e1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011e1f  mov     ebx, eax
0x180011e21  jmp     loc_180011F0F
0x180011e26  lea     rdx, [rsp+270h+var_24C]; int *
0x180011e2b  mov     [rsp+270h+var_24C], 0
0x180011e33  mov     rcx, rax; hHandle
0x180011e36  mov     [rsp+270h+var_250], 0; int
0x180011e3e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011e43  mov     ebx, eax
0x180011e45  test    eax, eax
0x180011e47  jns     short loc_180011E69
0x180011e49  mov     rcx, [rbp+178h]; this
0x180011e50  lea     r8, aWil; "wil"
0x180011e57  mov     r9d, eax; char *
0x180011e5a  mov     edx, 0D6h; void *
0x180011e5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e64  jmp     loc_180011F0F
0x180011e69  lea     r8, asc_1800441D0; "h"
0x180011e70  mov     rdx, r14; unsigned __int64
0x180011e73  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180011e78  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180011e7d  lea     r8, [rsp+270h+Name]; lpName
0x180011e82  xor     edx, edx; bInheritHandle
0x180011e84  mov     ecx, 1F0003h; dwDesiredAccess
0x180011e89  call    cs:__imp_OpenSemaphoreW
0x180011e8f  mov     [rsp+270h+var_248], rax
0x180011e94  test    rax, rax
0x180011e97  jnz     short loc_180011EBF
0x180011e99  mov     rcx, [rbp+178h]; this
0x180011ea0  lea     r8, aWil; "wil"
0x180011ea7  mov     edx, 0DCh; void *
0x180011eac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011eb1  mov     ebx, eax
0x180011eb3  lea     rcx, [rsp+270h+var_248]
0x180011eb8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011ebd  jmp     short loc_180011F0F
0x180011ebf  lea     rdx, [rsp+270h+var_250]; int *
0x180011ec4  mov     rcx, rax; hHandle
0x180011ec7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180011ecc  mov     ebx, eax
0x180011ece  test    eax, eax
0x180011ed0  jns     short loc_180011EEF
0x180011ed2  mov     rcx, [rbp+178h]; this
0x180011ed9  lea     r8, aWil; "wil"
0x180011ee0  mov     r9d, eax; char *
0x180011ee3  mov     edx, 0DEh; void *
0x180011ee8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011eed  jmp     short loc_180011EB3
0x180011eef  lea     rcx, [rsp+270h+var_248]
0x180011ef4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011ef9  movsxd  rcx, [rsp+270h+var_250]
0x180011efe  movsxd  rax, [rsp+270h+var_24C]
0x180011f03  shl     rcx, 1Fh
0x180011f07  or      rcx, rax
0x180011f0a  mov     [rdi], rcx
0x180011f0d  xor     ebx, ebx
0x180011f0f  lea     rcx, [rsp+270h+var_240]
0x180011f14  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180011f19  mov     eax, ebx
0x180011f1b  mov     rcx, [rbp+170h+var_20]
0x180011f22  xor     rcx, rsp; StackCookie
0x180011f25  call    __security_check_cookie
0x180011f2a  mov     rbx, [rsp+270h+arg_8]
0x180011f32  add     rsp, 260h
0x180011f39  pop     r14
0x180011f3b  pop     rdi
0x180011f3c  pop     rbp
0x180011f3d  retn
```
