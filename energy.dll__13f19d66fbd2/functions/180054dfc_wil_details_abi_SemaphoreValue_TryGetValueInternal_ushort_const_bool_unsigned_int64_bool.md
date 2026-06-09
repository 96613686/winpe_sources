# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180054dfc`
- end: `0x180054f93`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `407`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180054d88`

## callees

- `0x180045d70`
- `0x18004ca90`
- `0x180051098`
- `0x18005290c`
- `0x18005421c`
- `0x18005423c`
- `0x1800548fc`
- `0x180054dfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180054e5b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180054eeb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180054e5b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180054eeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054e6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054e6b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
0x180054dfc  mov     [rsp-8+arg_8], rbx
0x180054e01  mov     [rsp-8+arg_18], rdi
0x180054e06  push    rbp
0x180054e07  lea     rbp, [rsp-160h]
0x180054e0f  sub     rsp, 260h
0x180054e16  mov     rax, cs:__security_cookie
0x180054e1d  xor     rax, rsp
0x180054e20  mov     [rbp+160h+var_10], rax
0x180054e27  mov     rdi, r8
0x180054e2a  mov     qword ptr [r8], 0
0x180054e31  mov     r8, rcx; unsigned __int16 *
0x180054e34  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180054e39  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180054e3e  lea     r8, aP0; "_p0"
0x180054e45  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180054e4a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180054e4f  lea     r8, [rsp+260h+Name]; lpName
0x180054e54  xor     edx, edx; bInheritHandle
0x180054e56  mov     ecx, 1F0003h; dwDesiredAccess
0x180054e5b  call    cs:__imp_OpenSemaphoreW
0x180054e61  mov     [rsp+260h+var_230], rax
0x180054e66  test    rax, rax
0x180054e69  jnz     short loc_180054E92
0x180054e6b  call    cs:__imp_GetLastError
0x180054e71  cmp     eax, 2
0x180054e74  jz      loc_180054F61
0x180054e7a  mov     rcx, [rbp+168h]; this
0x180054e81  mov     edx, 0D0h; void *
0x180054e86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180054e8b  mov     ebx, eax
0x180054e8d  jmp     loc_180054F63
0x180054e92  lea     rdx, [rsp+260h+var_23C]; int *
0x180054e97  mov     [rsp+260h+var_23C], 0
0x180054e9f  mov     rcx, rax; hHandle
0x180054ea2  mov     [rsp+260h+var_240], 0; int
0x180054eaa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180054eaf  mov     ebx, eax
0x180054eb1  test    eax, eax
0x180054eb3  jns     short loc_180054ECE
0x180054eb5  mov     rcx, [rbp+168h]; this
0x180054ebc  mov     r9d, eax; char *
0x180054ebf  mov     edx, 0D6h; void *
0x180054ec4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054ec9  jmp     loc_180054F63
0x180054ece  lea     r8, asc_1800A0768; "h"
0x180054ed5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180054eda  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180054edf  lea     r8, [rsp+260h+Name]; lpName
0x180054ee4  xor     edx, edx; bInheritHandle
0x180054ee6  mov     ecx, 1F0003h; dwDesiredAccess
0x180054eeb  call    cs:__imp_OpenSemaphoreW
0x180054ef1  mov     [rsp+260h+var_238], rax
0x180054ef6  test    rax, rax
0x180054ef9  jnz     short loc_180054F1A
0x180054efb  mov     rcx, [rbp+168h]; this
0x180054f02  mov     edx, 0DCh; void *
0x180054f07  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180054f0c  mov     ebx, eax
0x180054f0e  lea     rcx, [rsp+260h+var_238]
0x180054f13  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054f18  jmp     short loc_180054F63
0x180054f1a  lea     rdx, [rsp+260h+var_240]; int *
0x180054f1f  mov     rcx, rax; hHandle
0x180054f22  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180054f27  mov     ebx, eax
0x180054f29  test    eax, eax
0x180054f2b  jns     short loc_180054F43
0x180054f2d  mov     rcx, [rbp+168h]; this
0x180054f34  mov     r9d, eax; char *
0x180054f37  mov     edx, 0DEh; void *
0x180054f3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054f41  jmp     short loc_180054F0E
0x180054f43  lea     rcx, [rsp+260h+var_238]
0x180054f48  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054f4d  movsxd  rcx, [rsp+260h+var_240]
0x180054f52  movsxd  rax, [rsp+260h+var_23C]
0x180054f57  shl     rcx, 1Fh
0x180054f5b  or      rcx, rax
0x180054f5e  mov     [rdi], rcx
0x180054f61  xor     ebx, ebx
0x180054f63  lea     rcx, [rsp+260h+var_230]
0x180054f68  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180054f6d  mov     eax, ebx
0x180054f6f  mov     rcx, [rbp+160h+var_10]
0x180054f76  xor     rcx, rsp; StackCookie
0x180054f79  call    __security_check_cookie
0x180054f7e  lea     r11, [rsp+260h+var_s0]
0x180054f86  mov     rbx, [r11+18h]
0x180054f8a  mov     rdi, [r11+28h]
0x180054f8e  mov     rsp, r11
0x180054f91  pop     rbp
0x180054f92  retn
```
