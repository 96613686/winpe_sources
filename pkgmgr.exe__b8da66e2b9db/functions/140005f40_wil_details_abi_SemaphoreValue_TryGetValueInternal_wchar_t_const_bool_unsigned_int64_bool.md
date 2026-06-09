# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005f40`
- end: `0x1400060fe`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140005ebc`

## callees

- `0x140002360`
- `0x140003ea8`
- `0x140004bd4`
- `0x140005684`
- `0x1400056ac`
- `0x140005bf0`
- `0x140005c44`
- `0x140005f40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005fa9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006049`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005fa9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005fb9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // r9
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  size_t v11; // r9
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v20; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0", v5);
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h", v11);
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v20,
          v16);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x140005f40  mov     [rsp-8+arg_8], rbx
0x140005f45  push    rbp
0x140005f46  push    rdi
0x140005f47  push    r14
0x140005f49  lea     rbp, [rsp-160h]
0x140005f51  sub     rsp, 260h
0x140005f58  mov     rax, cs:__security_cookie
0x140005f5f  xor     rax, rsp
0x140005f62  mov     [rbp+170h+var_20], rax
0x140005f69  mov     rdi, r8
0x140005f6c  mov     qword ptr [r8], 0
0x140005f73  mov     r8, rcx; wchar_t *
0x140005f76  mov     r14d, 104h
0x140005f7c  mov     edx, r14d; unsigned __int64
0x140005f7f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140005f84  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140005f89  lea     r8, aP0; "_p0"
0x140005f90  mov     edx, r14d; unsigned __int64
0x140005f93  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140005f98  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140005f9d  lea     r8, [rsp+270h+Name]; lpName
0x140005fa2  xor     edx, edx; bInheritHandle
0x140005fa4  mov     ecx, 1F0003h; dwDesiredAccess
0x140005fa9  call    cs:__imp_OpenSemaphoreW
0x140005faf  mov     [rsp+270h+var_240], rax
0x140005fb4  test    rax, rax
0x140005fb7  jnz     short loc_140005FE6
0x140005fb9  call    cs:__imp_GetLastError
0x140005fbf  cmp     eax, 2
0x140005fc2  jz      loc_1400060CD
0x140005fc8  mov     rcx, [rbp+178h]; this
0x140005fcf  lea     r8, aWil; "wil"
0x140005fd6  lea     edx, [r14-34h]; void *
0x140005fda  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005fdf  mov     ebx, eax
0x140005fe1  jmp     loc_1400060CF
0x140005fe6  lea     rdx, [rsp+270h+var_24C]; int *
0x140005feb  mov     [rsp+270h+var_24C], 0
0x140005ff3  mov     rcx, rax; hHandle
0x140005ff6  mov     [rsp+270h+var_250], 0; int
0x140005ffe  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006003  mov     ebx, eax
0x140006005  test    eax, eax
0x140006007  jns     short loc_140006029
0x140006009  mov     rcx, [rbp+178h]; this
0x140006010  lea     r8, aWil; "wil"
0x140006017  mov     r9d, eax; char *
0x14000601a  mov     edx, 0D6h; void *
0x14000601f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006024  jmp     loc_1400060CF
0x140006029  lea     r8, asc_14002D478; "h"
0x140006030  mov     rdx, r14; unsigned __int64
0x140006033  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140006038  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000603d  lea     r8, [rsp+270h+Name]; lpName
0x140006042  xor     edx, edx; bInheritHandle
0x140006044  mov     ecx, 1F0003h; dwDesiredAccess
0x140006049  call    cs:__imp_OpenSemaphoreW
0x14000604f  mov     [rsp+270h+var_248], rax
0x140006054  test    rax, rax
0x140006057  jnz     short loc_14000607F
0x140006059  mov     rcx, [rbp+178h]; this
0x140006060  lea     r8, aWil; "wil"
0x140006067  mov     edx, 0DCh; void *
0x14000606c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006071  mov     ebx, eax
0x140006073  lea     rcx, [rsp+270h+var_248]
0x140006078  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000607d  jmp     short loc_1400060CF
0x14000607f  lea     rdx, [rsp+270h+var_250]; int *
0x140006084  mov     rcx, rax; hHandle
0x140006087  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000608c  mov     ebx, eax
0x14000608e  test    eax, eax
0x140006090  jns     short loc_1400060AF
0x140006092  mov     rcx, [rbp+178h]; this
0x140006099  lea     r8, aWil; "wil"
0x1400060a0  mov     r9d, eax; char *
0x1400060a3  mov     edx, 0DEh; void *
0x1400060a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400060ad  jmp     short loc_140006073
0x1400060af  lea     rcx, [rsp+270h+var_248]
0x1400060b4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400060b9  movsxd  rcx, [rsp+270h+var_250]
0x1400060be  movsxd  rax, [rsp+270h+var_24C]
0x1400060c3  shl     rcx, 1Fh
0x1400060c7  or      rcx, rax
0x1400060ca  mov     [rdi], rcx
0x1400060cd  xor     ebx, ebx
0x1400060cf  lea     rcx, [rsp+270h+var_240]
0x1400060d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400060d9  mov     eax, ebx
0x1400060db  mov     rcx, [rbp+170h+var_20]
0x1400060e2  xor     rcx, rsp; StackCookie
0x1400060e5  call    __security_check_cookie
0x1400060ea  mov     rbx, [rsp+270h+arg_8]
0x1400060f2  add     rsp, 260h
0x1400060f9  pop     r14
0x1400060fb  pop     rdi
0x1400060fc  pop     rbp
0x1400060fd  retn
```
