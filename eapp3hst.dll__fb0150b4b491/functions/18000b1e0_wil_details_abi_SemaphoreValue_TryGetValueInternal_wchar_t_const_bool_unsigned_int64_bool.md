# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b1e0`
- end: `0x18000b377`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b16c`

## callees

- `0x1800017a0`
- `0x1800046b8`
- `0x180005fcc`
- `0x1800088c0`
- `0x18000a74c`
- `0x18000a76c`
- `0x18000ae6c`
- `0x18000b1e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b23f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b2cf`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b23f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b2cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b24f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b24f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        unsigned __int64 a2,
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
  StringCchCopyW(Name, a2, a1);
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
0x18000b1e0  mov     [rsp-8+arg_8], rbx
0x18000b1e5  mov     [rsp-8+arg_18], rdi
0x18000b1ea  push    rbp
0x18000b1eb  lea     rbp, [rsp-160h]
0x18000b1f3  sub     rsp, 260h
0x18000b1fa  mov     rax, cs:__security_cookie
0x18000b201  xor     rax, rsp
0x18000b204  mov     [rbp+160h+var_10], rax
0x18000b20b  mov     rdi, r8
0x18000b20e  mov     qword ptr [r8], 0
0x18000b215  mov     r8, rcx; wchar_t *
0x18000b218  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000b21d  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b222  lea     r8, aP0; "_p0"
0x18000b229  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000b22e  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b233  lea     r8, [rsp+260h+Name]; lpName
0x18000b238  xor     edx, edx; bInheritHandle
0x18000b23a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b23f  call    cs:__imp_OpenSemaphoreW
0x18000b245  mov     [rsp+260h+var_230], rax
0x18000b24a  test    rax, rax
0x18000b24d  jnz     short loc_18000B276
0x18000b24f  call    cs:__imp_GetLastError
0x18000b255  cmp     eax, 2
0x18000b258  jz      loc_18000B345
0x18000b25e  mov     rcx, [rbp+168h]; this
0x18000b265  mov     edx, 0D0h; void *
0x18000b26a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b26f  mov     ebx, eax
0x18000b271  jmp     loc_18000B347
0x18000b276  lea     rdx, [rsp+260h+var_23C]; int *
0x18000b27b  mov     [rsp+260h+var_23C], 0
0x18000b283  mov     rcx, rax; hHandle
0x18000b286  mov     [rsp+260h+var_240], 0; int
0x18000b28e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b293  mov     ebx, eax
0x18000b295  test    eax, eax
0x18000b297  jns     short loc_18000B2B2
0x18000b299  mov     rcx, [rbp+168h]; this
0x18000b2a0  mov     r9d, eax; char *
0x18000b2a3  mov     edx, 0D6h; void *
0x18000b2a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2ad  jmp     loc_18000B347
0x18000b2b2  lea     r8, asc_180039520; "h"
0x18000b2b9  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000b2be  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000b2c3  lea     r8, [rsp+260h+Name]; lpName
0x18000b2c8  xor     edx, edx; bInheritHandle
0x18000b2ca  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b2cf  call    cs:__imp_OpenSemaphoreW
0x18000b2d5  mov     [rsp+260h+var_238], rax
0x18000b2da  test    rax, rax
0x18000b2dd  jnz     short loc_18000B2FE
0x18000b2df  mov     rcx, [rbp+168h]; this
0x18000b2e6  mov     edx, 0DCh; void *
0x18000b2eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b2f0  mov     ebx, eax
0x18000b2f2  lea     rcx, [rsp+260h+var_238]
0x18000b2f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b2fc  jmp     short loc_18000B347
0x18000b2fe  lea     rdx, [rsp+260h+var_240]; int *
0x18000b303  mov     rcx, rax; hHandle
0x18000b306  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b30b  mov     ebx, eax
0x18000b30d  test    eax, eax
0x18000b30f  jns     short loc_18000B327
0x18000b311  mov     rcx, [rbp+168h]; this
0x18000b318  mov     r9d, eax; char *
0x18000b31b  mov     edx, 0DEh; void *
0x18000b320  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b325  jmp     short loc_18000B2F2
0x18000b327  lea     rcx, [rsp+260h+var_238]
0x18000b32c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b331  movsxd  rcx, [rsp+260h+var_240]
0x18000b336  movsxd  rax, [rsp+260h+var_23C]
0x18000b33b  shl     rcx, 1Fh
0x18000b33f  or      rcx, rax
0x18000b342  mov     [rdi], rcx
0x18000b345  xor     ebx, ebx
0x18000b347  lea     rcx, [rsp+260h+var_230]
0x18000b34c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b351  mov     eax, ebx
0x18000b353  mov     rcx, [rbp+160h+var_10]
0x18000b35a  xor     rcx, rsp; StackCookie
0x18000b35d  call    __security_check_cookie
0x18000b362  lea     r11, [rsp+260h+var_s0]
0x18000b36a  mov     rbx, [r11+18h]
0x18000b36e  mov     rdi, [r11+28h]
0x18000b372  mov     rsp, r11
0x18000b375  pop     rbp
0x18000b376  retn
```
