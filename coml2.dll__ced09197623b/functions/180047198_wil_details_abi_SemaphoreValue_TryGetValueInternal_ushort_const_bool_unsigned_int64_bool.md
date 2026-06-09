# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180047198`
- end: `0x180047350`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180047114`

## callees

- `0x18002e87c`
- `0x18003f54c`
- `0x18003f62c`
- `0x180042800`
- `0x180044394`
- `0x18004555c`
- `0x180046e2c`
- `0x180047198`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004720c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004720c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800471fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004729a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800471fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004729a`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
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
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180047198  mov     [rsp-8+arg_8], rbx
0x18004719d  mov     [rsp-8+arg_18], rdi
0x1800471a2  push    rbp
0x1800471a3  lea     rbp, [rsp-160h]
0x1800471ab  sub     rsp, 260h
0x1800471b2  mov     rax, cs:__security_cookie
0x1800471b9  xor     rax, rsp
0x1800471bc  mov     [rbp+160h+var_10], rax
0x1800471c3  mov     rdi, r8
0x1800471c6  mov     qword ptr [r8], 0
0x1800471cd  mov     r8, rcx; unsigned __int16 *
0x1800471d0  mov     edx, 104h; unsigned __int64
0x1800471d5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800471da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800471df  lea     r8, aP0; "_p0"
0x1800471e6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800471eb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800471f0  lea     r8, [rsp+260h+Name]; lpName
0x1800471f5  xor     edx, edx; bInheritHandle
0x1800471f7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800471fc  call    cs:__imp_OpenSemaphoreW
0x180047202  mov     [rsp+260h+var_230], rax
0x180047207  test    rax, rax
0x18004720a  jnz     short loc_18004723A
0x18004720c  call    cs:__imp_GetLastError
0x180047212  cmp     eax, 2
0x180047215  jz      loc_18004731E
0x18004721b  mov     rcx, [rbp+168h]; this
0x180047222  lea     r8, aWil; "wil"
0x180047229  mov     edx, 0D0h; void *
0x18004722e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180047233  mov     ebx, eax
0x180047235  jmp     loc_180047320
0x18004723a  lea     rdx, [rsp+260h+var_23C]; int *
0x18004723f  mov     [rsp+260h+var_23C], 0
0x180047247  mov     rcx, rax; hHandle
0x18004724a  mov     [rsp+260h+var_240], 0; int
0x180047252  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180047257  mov     ebx, eax
0x180047259  test    eax, eax
0x18004725b  jns     short loc_18004727D
0x18004725d  mov     rcx, [rbp+168h]; this
0x180047264  lea     r8, aWil; "wil"
0x18004726b  mov     r9d, eax; char *
0x18004726e  mov     edx, 0D6h; void *
0x180047273  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047278  jmp     loc_180047320
0x18004727d  lea     r8, asc_1800675E8; "h"
0x180047284  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180047289  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004728e  lea     r8, [rsp+260h+Name]; lpName
0x180047293  xor     edx, edx; bInheritHandle
0x180047295  mov     ecx, 1F0003h; dwDesiredAccess
0x18004729a  call    cs:__imp_OpenSemaphoreW
0x1800472a0  mov     [rsp+260h+var_238], rax
0x1800472a5  test    rax, rax
0x1800472a8  jnz     short loc_1800472D0
0x1800472aa  mov     rcx, [rbp+168h]; this
0x1800472b1  lea     r8, aWil; "wil"
0x1800472b8  mov     edx, 0DCh; void *
0x1800472bd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800472c2  mov     ebx, eax
0x1800472c4  lea     rcx, [rsp+260h+var_238]
0x1800472c9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800472ce  jmp     short loc_180047320
0x1800472d0  lea     rdx, [rsp+260h+var_240]; int *
0x1800472d5  mov     rcx, rax; hHandle
0x1800472d8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800472dd  mov     ebx, eax
0x1800472df  test    eax, eax
0x1800472e1  jns     short loc_180047300
0x1800472e3  mov     rcx, [rbp+168h]; this
0x1800472ea  lea     r8, aWil; "wil"
0x1800472f1  mov     r9d, eax; char *
0x1800472f4  mov     edx, 0DEh; void *
0x1800472f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800472fe  jmp     short loc_1800472C4
0x180047300  lea     rcx, [rsp+260h+var_238]
0x180047305  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004730a  movsxd  rcx, [rsp+260h+var_240]
0x18004730f  movsxd  rax, [rsp+260h+var_23C]
0x180047314  shl     rcx, 1Fh
0x180047318  or      rcx, rax
0x18004731b  mov     [rdi], rcx
0x18004731e  xor     ebx, ebx
0x180047320  lea     rcx, [rsp+260h+var_230]
0x180047325  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004732a  mov     eax, ebx
0x18004732c  mov     rcx, [rbp+160h+var_10]
0x180047333  xor     rcx, rsp; StackCookie
0x180047336  call    __security_check_cookie
0x18004733b  lea     r11, [rsp+260h+var_s0]
0x180047343  mov     rbx, [r11+18h]
0x180047347  mov     rdi, [r11+28h]
0x18004734b  mov     rsp, r11
0x18004734e  pop     rbp
0x18004734f  retn
```
