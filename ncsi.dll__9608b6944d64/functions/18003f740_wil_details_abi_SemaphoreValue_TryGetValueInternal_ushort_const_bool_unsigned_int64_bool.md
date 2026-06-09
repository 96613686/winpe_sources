# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003f740`
- end: `0x18003f8f8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004efac`

## callees

- `0x18002283c`
- `0x18003f740`
- `0x18003f900`
- `0x18003f958`
- `0x18003fa18`
- `0x180047240`
- `0x18004d248`
- `0x18004eaa4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003f7a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003f842`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003f7a4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003f842`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f7b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003f7b4`

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
0x18003f740  mov     [rsp-8+arg_8], rbx
0x18003f745  mov     [rsp-8+arg_18], rdi
0x18003f74a  push    rbp
0x18003f74b  lea     rbp, [rsp-160h]
0x18003f753  sub     rsp, 260h
0x18003f75a  mov     rax, cs:__security_cookie
0x18003f761  xor     rax, rsp
0x18003f764  mov     [rbp+160h+var_10], rax
0x18003f76b  mov     rdi, r8
0x18003f76e  mov     qword ptr [r8], 0
0x18003f775  mov     r8, rcx; unsigned __int16 *
0x18003f778  mov     edx, 104h; unsigned __int64
0x18003f77d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003f782  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003f787  lea     r8, aP0; "_p0"
0x18003f78e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003f793  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f798  lea     r8, [rsp+260h+Name]; lpName
0x18003f79d  xor     edx, edx; bInheritHandle
0x18003f79f  mov     ecx, 1F0003h; dwDesiredAccess
0x18003f7a4  call    cs:__imp_OpenSemaphoreW
0x18003f7aa  mov     [rsp+260h+var_230], rax
0x18003f7af  test    rax, rax
0x18003f7b2  jnz     short loc_18003F7E2
0x18003f7b4  call    cs:__imp_GetLastError
0x18003f7ba  cmp     eax, 2
0x18003f7bd  jz      loc_18003F8C6
0x18003f7c3  mov     rcx, [rbp+168h]; this
0x18003f7ca  lea     r8, aWil; "wil"
0x18003f7d1  mov     edx, 0D0h; void *
0x18003f7d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f7db  mov     ebx, eax
0x18003f7dd  jmp     loc_18003F8C8
0x18003f7e2  lea     rdx, [rsp+260h+var_23C]; int *
0x18003f7e7  mov     [rsp+260h+var_23C], 0
0x18003f7ef  mov     rcx, rax; hHandle
0x18003f7f2  mov     [rsp+260h+var_240], 0; int
0x18003f7fa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003f7ff  mov     ebx, eax
0x18003f801  test    eax, eax
0x18003f803  jns     short loc_18003F825
0x18003f805  mov     rcx, [rbp+168h]; this
0x18003f80c  lea     r8, aWil; "wil"
0x18003f813  mov     r9d, eax; char *
0x18003f816  mov     edx, 0D6h; void *
0x18003f81b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f820  jmp     loc_18003F8C8
0x18003f825  lea     r8, asc_18007FE80; "h"
0x18003f82c  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003f831  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003f836  lea     r8, [rsp+260h+Name]; lpName
0x18003f83b  xor     edx, edx; bInheritHandle
0x18003f83d  mov     ecx, 1F0003h; dwDesiredAccess
0x18003f842  call    cs:__imp_OpenSemaphoreW
0x18003f848  mov     [rsp+260h+var_238], rax
0x18003f84d  test    rax, rax
0x18003f850  jnz     short loc_18003F878
0x18003f852  mov     rcx, [rbp+168h]; this
0x18003f859  lea     r8, aWil; "wil"
0x18003f860  mov     edx, 0DCh; void *
0x18003f865  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003f86a  mov     ebx, eax
0x18003f86c  lea     rcx, [rsp+260h+var_238]
0x18003f871  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003f876  jmp     short loc_18003F8C8
0x18003f878  lea     rdx, [rsp+260h+var_240]; int *
0x18003f87d  mov     rcx, rax; hHandle
0x18003f880  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003f885  mov     ebx, eax
0x18003f887  test    eax, eax
0x18003f889  jns     short loc_18003F8A8
0x18003f88b  mov     rcx, [rbp+168h]; this
0x18003f892  lea     r8, aWil; "wil"
0x18003f899  mov     r9d, eax; char *
0x18003f89c  mov     edx, 0DEh; void *
0x18003f8a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003f8a6  jmp     short loc_18003F86C
0x18003f8a8  lea     rcx, [rsp+260h+var_238]
0x18003f8ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003f8b2  movsxd  rcx, [rsp+260h+var_240]
0x18003f8b7  movsxd  rax, [rsp+260h+var_23C]
0x18003f8bc  shl     rcx, 1Fh
0x18003f8c0  or      rcx, rax
0x18003f8c3  mov     [rdi], rcx
0x18003f8c6  xor     ebx, ebx
0x18003f8c8  lea     rcx, [rsp+260h+var_230]
0x18003f8cd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003f8d2  mov     eax, ebx
0x18003f8d4  mov     rcx, [rbp+160h+var_10]
0x18003f8db  xor     rcx, rsp; StackCookie
0x18003f8de  call    __security_check_cookie
0x18003f8e3  lea     r11, [rsp+260h+var_s0]
0x18003f8eb  mov     rbx, [r11+18h]
0x18003f8ef  mov     rdi, [r11+28h]
0x18003f8f3  mov     rsp, r11
0x18003f8f6  pop     rbp
0x18003f8f7  retn
```
