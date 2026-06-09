# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000a77c`
- end: `0x14000a921`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `421`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000a6f8`

## callees

- `0x140005154`
- `0x140006d84`
- `0x14000964c`
- `0x14000966c`
- `0x140009ea4`
- `0x140009ef0`
- `0x14000a77c`
- `0x140025d70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000a7eb`
- `KERNEL32!GetLastError` at `0x14000a7eb`
- `KERNEL32!OpenSemaphoreW` at `0x14000a7db`
- `KERNEL32!OpenSemaphoreW` at `0x14000a872`
- `KERNEL32!OpenSemaphoreW` at `0x14000a7db`
- `KERNEL32!OpenSemaphoreW` at `0x14000a872`

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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x14000a77c  mov     [rsp-8+arg_8], rbx
0x14000a781  mov     [rsp-8+arg_18], rdi
0x14000a786  push    rbp
0x14000a787  lea     rbp, [rsp-160h]
0x14000a78f  sub     rsp, 260h
0x14000a796  mov     rax, cs:__security_cookie
0x14000a79d  xor     rax, rsp
0x14000a7a0  mov     [rbp+160h+var_10], rax
0x14000a7a7  mov     rdi, r8
0x14000a7aa  mov     qword ptr [r8], 0
0x14000a7b1  mov     r8, rcx; unsigned __int16 *
0x14000a7b4  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x14000a7b9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000a7be  lea     r8, aP0; "_p0"
0x14000a7c5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x14000a7ca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a7cf  lea     r8, [rsp+260h+Name]; lpName
0x14000a7d4  xor     edx, edx; bInheritHandle
0x14000a7d6  mov     ecx, 1F0003h; dwDesiredAccess
0x14000a7db  call    cs:__imp_OpenSemaphoreW
0x14000a7e1  mov     [rsp+260h+var_230], rax
0x14000a7e6  test    rax, rax
0x14000a7e9  jnz     short loc_14000A812
0x14000a7eb  call    cs:__imp_GetLastError
0x14000a7f1  cmp     eax, 2
0x14000a7f4  jz      loc_14000A8EF
0x14000a7fa  mov     rcx, [rbp+168h]; this
0x14000a801  mov     edx, 0D0h; void *
0x14000a806  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000a80b  mov     ebx, eax
0x14000a80d  jmp     loc_14000A8F1
0x14000a812  lea     rdx, [rsp+260h+var_23C]; int *
0x14000a817  mov     [rsp+260h+var_23C], 0
0x14000a81f  mov     rcx, rax; hHandle
0x14000a822  mov     [rsp+260h+var_240], 0; int
0x14000a82a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000a82f  mov     ebx, eax
0x14000a831  test    eax, eax
0x14000a833  jns     short loc_14000A855
0x14000a835  mov     rcx, [rbp+168h]; this
0x14000a83c  lea     r8, aWil; "wil"
0x14000a843  mov     r9d, eax; char *
0x14000a846  mov     edx, 0D6h; void *
0x14000a84b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a850  jmp     loc_14000A8F1
0x14000a855  lea     r8, asc_14002ADE8; "h"
0x14000a85c  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x14000a861  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000a866  lea     r8, [rsp+260h+Name]; lpName
0x14000a86b  xor     edx, edx; bInheritHandle
0x14000a86d  mov     ecx, 1F0003h; dwDesiredAccess
0x14000a872  call    cs:__imp_OpenSemaphoreW
0x14000a878  mov     [rsp+260h+var_238], rax
0x14000a87d  test    rax, rax
0x14000a880  jnz     short loc_14000A8A1
0x14000a882  mov     rcx, [rbp+168h]; this
0x14000a889  mov     edx, 0DCh; void *
0x14000a88e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000a893  mov     ebx, eax
0x14000a895  lea     rcx, [rsp+260h+var_238]
0x14000a89a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000a89f  jmp     short loc_14000A8F1
0x14000a8a1  lea     rdx, [rsp+260h+var_240]; int *
0x14000a8a6  mov     rcx, rax; hHandle
0x14000a8a9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000a8ae  mov     ebx, eax
0x14000a8b0  test    eax, eax
0x14000a8b2  jns     short loc_14000A8D1
0x14000a8b4  mov     rcx, [rbp+168h]; this
0x14000a8bb  lea     r8, aWil; "wil"
0x14000a8c2  mov     r9d, eax; char *
0x14000a8c5  mov     edx, 0DEh; void *
0x14000a8ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000a8cf  jmp     short loc_14000A895
0x14000a8d1  lea     rcx, [rsp+260h+var_238]
0x14000a8d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000a8db  movsxd  rcx, [rsp+260h+var_240]
0x14000a8e0  movsxd  rax, [rsp+260h+var_23C]
0x14000a8e5  shl     rcx, 1Fh
0x14000a8e9  or      rcx, rax
0x14000a8ec  mov     [rdi], rcx
0x14000a8ef  xor     ebx, ebx
0x14000a8f1  lea     rcx, [rsp+260h+var_230]
0x14000a8f6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000a8fb  mov     eax, ebx
0x14000a8fd  mov     rcx, [rbp+160h+var_10]
0x14000a904  xor     rcx, rsp; StackCookie
0x14000a907  call    __security_check_cookie
0x14000a90c  lea     r11, [rsp+260h+var_s0]
0x14000a914  mov     rbx, [r11+18h]
0x14000a918  mov     rdi, [r11+28h]
0x14000a91c  mov     rsp, r11
0x14000a91f  pop     rbp
0x14000a920  retn
```
