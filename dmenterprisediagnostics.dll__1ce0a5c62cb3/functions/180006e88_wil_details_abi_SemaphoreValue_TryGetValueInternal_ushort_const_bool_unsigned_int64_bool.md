# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006e88`
- end: `0x180007046`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003d18`

## callees

- `0x1800017e0`
- `0x180003ba8`
- `0x180004c3c`
- `0x1800059f4`
- `0x180005a14`
- `0x180006960`
- `0x1800069ec`
- `0x180006e88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ef1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006f91`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ef1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006f91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f01`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
0x180006e88  mov     [rsp-8+arg_8], rbx
0x180006e8d  push    rbp
0x180006e8e  push    rdi
0x180006e8f  push    r14
0x180006e91  lea     rbp, [rsp-160h]
0x180006e99  sub     rsp, 260h
0x180006ea0  mov     rax, cs:__security_cookie
0x180006ea7  xor     rax, rsp
0x180006eaa  mov     [rbp+170h+var_20], rax
0x180006eb1  mov     rdi, r8
0x180006eb4  mov     qword ptr [r8], 0
0x180006ebb  mov     r8, rcx; unsigned __int16 *
0x180006ebe  mov     r14d, 104h
0x180006ec4  mov     edx, r14d; unsigned __int64
0x180006ec7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006ecc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006ed1  lea     r8, aP0; "_p0"
0x180006ed8  mov     edx, r14d; unsigned __int64
0x180006edb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006ee0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006ee5  lea     r8, [rsp+270h+Name]; lpName
0x180006eea  xor     edx, edx; bInheritHandle
0x180006eec  mov     ecx, 1F0003h; dwDesiredAccess
0x180006ef1  call    cs:__imp_OpenSemaphoreW
0x180006ef7  mov     [rsp+270h+var_240], rax
0x180006efc  test    rax, rax
0x180006eff  jnz     short loc_180006F2E
0x180006f01  call    cs:__imp_GetLastError
0x180006f07  cmp     eax, 2
0x180006f0a  jz      loc_180007015
0x180006f10  mov     rcx, [rbp+178h]; this
0x180006f17  lea     r8, aWil; "wil"
0x180006f1e  lea     edx, [r14-34h]; void *
0x180006f22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006f27  mov     ebx, eax
0x180006f29  jmp     loc_180007017
0x180006f2e  lea     rdx, [rsp+270h+var_24C]; int *
0x180006f33  mov     [rsp+270h+var_24C], 0
0x180006f3b  mov     rcx, rax; hHandle
0x180006f3e  mov     [rsp+270h+var_250], 0; int
0x180006f46  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006f4b  mov     ebx, eax
0x180006f4d  test    eax, eax
0x180006f4f  jns     short loc_180006F71
0x180006f51  mov     rcx, [rbp+178h]; this
0x180006f58  lea     r8, aWil; "wil"
0x180006f5f  mov     r9d, eax; char *
0x180006f62  mov     edx, 0D6h; void *
0x180006f67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f6c  jmp     loc_180007017
0x180006f71  lea     r8, asc_1800296A0; "h"
0x180006f78  mov     rdx, r14; unsigned __int64
0x180006f7b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006f80  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006f85  lea     r8, [rsp+270h+Name]; lpName
0x180006f8a  xor     edx, edx; bInheritHandle
0x180006f8c  mov     ecx, 1F0003h; dwDesiredAccess
0x180006f91  call    cs:__imp_OpenSemaphoreW
0x180006f97  mov     [rsp+270h+var_248], rax
0x180006f9c  test    rax, rax
0x180006f9f  jnz     short loc_180006FC7
0x180006fa1  mov     rcx, [rbp+178h]; this
0x180006fa8  lea     r8, aWil; "wil"
0x180006faf  mov     edx, 0DCh; void *
0x180006fb4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006fb9  mov     ebx, eax
0x180006fbb  lea     rcx, [rsp+270h+var_248]
0x180006fc0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006fc5  jmp     short loc_180007017
0x180006fc7  lea     rdx, [rsp+270h+var_250]; int *
0x180006fcc  mov     rcx, rax; hHandle
0x180006fcf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006fd4  mov     ebx, eax
0x180006fd6  test    eax, eax
0x180006fd8  jns     short loc_180006FF7
0x180006fda  mov     rcx, [rbp+178h]; this
0x180006fe1  lea     r8, aWil; "wil"
0x180006fe8  mov     r9d, eax; char *
0x180006feb  mov     edx, 0DEh; void *
0x180006ff0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006ff5  jmp     short loc_180006FBB
0x180006ff7  lea     rcx, [rsp+270h+var_248]
0x180006ffc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007001  movsxd  rcx, [rsp+270h+var_250]
0x180007006  movsxd  rax, [rsp+270h+var_24C]
0x18000700b  shl     rcx, 1Fh
0x18000700f  or      rcx, rax
0x180007012  mov     [rdi], rcx
0x180007015  xor     ebx, ebx
0x180007017  lea     rcx, [rsp+270h+var_240]
0x18000701c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007021  mov     eax, ebx
0x180007023  mov     rcx, [rbp+170h+var_20]
0x18000702a  xor     rcx, rsp; StackCookie
0x18000702d  call    __security_check_cookie
0x180007032  mov     rbx, [rsp+270h+arg_8]
0x18000703a  add     rsp, 260h
0x180007041  pop     r14
0x180007043  pop     rdi
0x180007044  pop     rbp
0x180007045  retn
```
