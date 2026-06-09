# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007b40`
- end: `0x180007cdc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007acc`

## callees

- `0x180003810`
- `0x180004fa4`
- `0x180006e4c`
- `0x180006e6c`
- `0x18000752c`
- `0x1800075a8`
- `0x180007b40`
- `0x1800273b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007bb4`
- `KERNEL32!GetLastError` at `0x180007bb4`
- `KERNEL32!OpenSemaphoreW` at `0x180007ba4`
- `KERNEL32!OpenSemaphoreW` at `0x180007c34`
- `KERNEL32!OpenSemaphoreW` at `0x180007ba4`
- `KERNEL32!OpenSemaphoreW` at `0x180007c34`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x180007b40  mov     [rsp-8+arg_8], rbx
0x180007b45  mov     [rsp-8+arg_18], rdi
0x180007b4a  push    rbp
0x180007b4b  lea     rbp, [rsp-160h]
0x180007b53  sub     rsp, 260h
0x180007b5a  mov     rax, cs:__security_cookie
0x180007b61  xor     rax, rsp
0x180007b64  mov     [rbp+160h+var_10], rax
0x180007b6b  mov     rdi, r8
0x180007b6e  mov     qword ptr [r8], 0
0x180007b75  mov     r8, rcx; wchar_t *
0x180007b78  mov     edx, 104h; unsigned __int64
0x180007b7d  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180007b82  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007b87  lea     r8, aP0; "_p0"
0x180007b8e  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180007b93  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007b98  lea     r8, [rsp+260h+Name]; lpName
0x180007b9d  xor     edx, edx; bInheritHandle
0x180007b9f  mov     ecx, 1F0003h; dwDesiredAccess
0x180007ba4  call    cs:__imp_OpenSemaphoreW
0x180007baa  mov     [rsp+260h+var_230], rax
0x180007baf  test    rax, rax
0x180007bb2  jnz     short loc_180007BDB
0x180007bb4  call    cs:__imp_GetLastError
0x180007bba  cmp     eax, 2
0x180007bbd  jz      loc_180007CAA
0x180007bc3  mov     rcx, [rbp+168h]; this
0x180007bca  mov     edx, 0D0h; void *
0x180007bcf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007bd4  mov     ebx, eax
0x180007bd6  jmp     loc_180007CAC
0x180007bdb  mov     [rsp+260h+var_23C], 0
0x180007be3  mov     [rsp+260h+var_240], 0; int
0x180007beb  lea     rdx, [rsp+260h+var_23C]; int *
0x180007bf0  mov     rcx, rax; hHandle
0x180007bf3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007bf8  mov     ebx, eax
0x180007bfa  test    eax, eax
0x180007bfc  jns     short loc_180007C17
0x180007bfe  mov     rcx, [rbp+168h]; this
0x180007c05  mov     r9d, eax; char *
0x180007c08  mov     edx, 0D6h; void *
0x180007c0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c12  jmp     loc_180007CAC
0x180007c17  lea     r8, asc_18002F138; "h"
0x180007c1e  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180007c23  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180007c28  lea     r8, [rsp+260h+Name]; lpName
0x180007c2d  xor     edx, edx; bInheritHandle
0x180007c2f  mov     ecx, 1F0003h; dwDesiredAccess
0x180007c34  call    cs:__imp_OpenSemaphoreW
0x180007c3a  mov     [rsp+260h+var_238], rax
0x180007c3f  test    rax, rax
0x180007c42  jnz     short loc_180007C63
0x180007c44  mov     rcx, [rbp+168h]; this
0x180007c4b  mov     edx, 0DCh; void *
0x180007c50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007c55  mov     ebx, eax
0x180007c57  lea     rcx, [rsp+260h+var_238]
0x180007c5c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007c61  jmp     short loc_180007CAC
0x180007c63  lea     rdx, [rsp+260h+var_240]; int *
0x180007c68  mov     rcx, rax; hHandle
0x180007c6b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007c70  mov     ebx, eax
0x180007c72  test    eax, eax
0x180007c74  jns     short loc_180007C8C
0x180007c76  mov     rcx, [rbp+168h]; this
0x180007c7d  mov     r9d, eax; char *
0x180007c80  mov     edx, 0DEh; void *
0x180007c85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c8a  jmp     short loc_180007C57
0x180007c8c  lea     rcx, [rsp+260h+var_238]
0x180007c91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007c96  movsxd  rcx, [rsp+260h+var_240]
0x180007c9b  shl     rcx, 1Fh
0x180007c9f  movsxd  rax, [rsp+260h+var_23C]
0x180007ca4  or      rcx, rax
0x180007ca7  mov     [rdi], rcx
0x180007caa  xor     ebx, ebx
0x180007cac  lea     rcx, [rsp+260h+var_230]
0x180007cb1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007cb6  mov     eax, ebx
0x180007cb8  mov     rcx, [rbp+160h+var_10]
0x180007cbf  xor     rcx, rsp; StackCookie
0x180007cc2  call    __security_check_cookie
0x180007cc7  lea     r11, [rsp+260h+var_s0]
0x180007ccf  mov     rbx, [r11+18h]
0x180007cd3  mov     rdi, [r11+28h]
0x180007cd7  mov     rsp, r11
0x180007cda  pop     rbp
0x180007cdb  retn
```
