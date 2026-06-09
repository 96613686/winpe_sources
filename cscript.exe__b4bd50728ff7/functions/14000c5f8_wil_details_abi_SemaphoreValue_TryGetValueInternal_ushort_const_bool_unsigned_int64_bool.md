# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000c5f8`
- end: `0x14000c794`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000b004`

## callees

- `0x14000af84`
- `0x14000b880`
- `0x14000c1e8`
- `0x14000c208`
- `0x14000c22c`
- `0x14000c2a8`
- `0x14000c5f8`
- `0x1400161d0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x14000c65c`
- `KERNEL32!OpenSemaphoreW` at `0x14000c6ec`
- `KERNEL32!OpenSemaphoreW` at `0x14000c65c`
- `KERNEL32!OpenSemaphoreW` at `0x14000c6ec`
- `KERNEL32!GetLastError` at `0x14000c66c`
- `KERNEL32!GetLastError` at `0x14000c66c`

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
0x14000c5f8  mov     [rsp-8+arg_8], rbx
0x14000c5fd  mov     [rsp-8+arg_18], rdi
0x14000c602  push    rbp
0x14000c603  lea     rbp, [rsp-160h]
0x14000c60b  sub     rsp, 260h
0x14000c612  mov     rax, cs:__security_cookie
0x14000c619  xor     rax, rsp
0x14000c61c  mov     [rbp+160h+var_10], rax
0x14000c623  mov     rdi, r8
0x14000c626  mov     qword ptr [r8], 0
0x14000c62d  mov     r8, rcx; unsigned __int16 *
0x14000c630  mov     edx, 104h; unsigned __int64
0x14000c635  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x14000c63a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000c63f  lea     r8, aP0; "_p0"
0x14000c646  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x14000c64b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c650  lea     r8, [rsp+260h+Name]; lpName
0x14000c655  xor     edx, edx; bInheritHandle
0x14000c657  mov     ecx, 1F0003h; dwDesiredAccess
0x14000c65c  call    cs:__imp_OpenSemaphoreW
0x14000c662  mov     [rsp+260h+var_230], rax
0x14000c667  test    rax, rax
0x14000c66a  jnz     short loc_14000C693
0x14000c66c  call    cs:__imp_GetLastError
0x14000c672  cmp     eax, 2
0x14000c675  jz      loc_14000C762
0x14000c67b  mov     rcx, [rbp+168h]; this
0x14000c682  mov     edx, 0D0h; void *
0x14000c687  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c68c  mov     ebx, eax
0x14000c68e  jmp     loc_14000C764
0x14000c693  lea     rdx, [rsp+260h+var_23C]; int *
0x14000c698  mov     [rsp+260h+var_23C], 0
0x14000c6a0  mov     rcx, rax; hHandle
0x14000c6a3  mov     [rsp+260h+var_240], 0; int
0x14000c6ab  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c6b0  mov     ebx, eax
0x14000c6b2  test    eax, eax
0x14000c6b4  jns     short loc_14000C6CF
0x14000c6b6  mov     rcx, [rbp+168h]; this
0x14000c6bd  mov     r9d, eax; char *
0x14000c6c0  mov     edx, 0D6h; void *
0x14000c6c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c6ca  jmp     loc_14000C764
0x14000c6cf  lea     r8, asc_14001A098; "h"
0x14000c6d6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x14000c6db  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000c6e0  lea     r8, [rsp+260h+Name]; lpName
0x14000c6e5  xor     edx, edx; bInheritHandle
0x14000c6e7  mov     ecx, 1F0003h; dwDesiredAccess
0x14000c6ec  call    cs:__imp_OpenSemaphoreW
0x14000c6f2  mov     [rsp+260h+var_238], rax
0x14000c6f7  test    rax, rax
0x14000c6fa  jnz     short loc_14000C71B
0x14000c6fc  mov     rcx, [rbp+168h]; this
0x14000c703  mov     edx, 0DCh; void *
0x14000c708  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000c70d  mov     ebx, eax
0x14000c70f  lea     rcx, [rsp+260h+var_238]
0x14000c714  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000c719  jmp     short loc_14000C764
0x14000c71b  lea     rdx, [rsp+260h+var_240]; int *
0x14000c720  mov     rcx, rax; hHandle
0x14000c723  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000c728  mov     ebx, eax
0x14000c72a  test    eax, eax
0x14000c72c  jns     short loc_14000C744
0x14000c72e  mov     rcx, [rbp+168h]; this
0x14000c735  mov     r9d, eax; char *
0x14000c738  mov     edx, 0DEh; void *
0x14000c73d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c742  jmp     short loc_14000C70F
0x14000c744  lea     rcx, [rsp+260h+var_238]
0x14000c749  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000c74e  movsxd  rcx, [rsp+260h+var_240]
0x14000c753  movsxd  rax, [rsp+260h+var_23C]
0x14000c758  shl     rcx, 1Fh
0x14000c75c  or      rcx, rax
0x14000c75f  mov     [rdi], rcx
0x14000c762  xor     ebx, ebx
0x14000c764  lea     rcx, [rsp+260h+var_230]
0x14000c769  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000c76e  mov     eax, ebx
0x14000c770  mov     rcx, [rbp+160h+var_10]
0x14000c777  xor     rcx, rsp; StackCookie
0x14000c77a  call    __security_check_cookie
0x14000c77f  lea     r11, [rsp+260h+var_s0]
0x14000c787  mov     rbx, [r11+18h]
0x14000c78b  mov     rdi, [r11+28h]
0x14000c78f  mov     rsp, r11
0x14000c792  pop     rbp
0x14000c793  retn
```
