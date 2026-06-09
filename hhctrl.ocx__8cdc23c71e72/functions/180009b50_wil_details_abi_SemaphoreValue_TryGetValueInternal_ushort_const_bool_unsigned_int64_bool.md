# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009b50`
- end: `0x180009cf2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009adc`

## callees

- `0x180003ee8`
- `0x180005cac`
- `0x180008b5c`
- `0x180008b7c`
- `0x180009574`
- `0x18000960c`
- `0x180009b50`
- `0x180075c90`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180009bb9`
- `KERNEL32!OpenSemaphoreW` at `0x180009c4b`
- `KERNEL32!OpenSemaphoreW` at `0x180009bb9`
- `KERNEL32!OpenSemaphoreW` at `0x180009c4b`
- `KERNEL32!GetLastError` at `0x180009bc9`
- `KERNEL32!GetLastError` at `0x180009bc9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180009b50  mov     [rsp-8+arg_8], rbx
0x180009b55  push    rbp
0x180009b56  push    rdi
0x180009b57  push    r14
0x180009b59  lea     rbp, [rsp-160h]
0x180009b61  sub     rsp, 260h
0x180009b68  mov     rax, cs:__security_cookie
0x180009b6f  xor     rax, rsp
0x180009b72  mov     [rbp+170h+var_20], rax
0x180009b79  mov     rdi, r8
0x180009b7c  mov     qword ptr [r8], 0
0x180009b83  mov     r8, rcx; unsigned __int16 *
0x180009b86  mov     r14d, 104h
0x180009b8c  mov     edx, r14d; unsigned __int64
0x180009b8f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009b94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009b99  lea     r8, aP0; "_p0"
0x180009ba0  mov     edx, r14d; unsigned __int64
0x180009ba3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009ba8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009bad  lea     r8, [rsp+270h+Name]; lpName
0x180009bb2  xor     edx, edx; bInheritHandle
0x180009bb4  mov     ecx, 1F0003h; dwDesiredAccess
0x180009bb9  call    cs:__imp_OpenSemaphoreW
0x180009bbf  mov     [rsp+270h+var_240], rax
0x180009bc4  test    rax, rax
0x180009bc7  jnz     short loc_180009BEF
0x180009bc9  call    cs:__imp_GetLastError
0x180009bcf  cmp     eax, 2
0x180009bd2  jz      loc_180009CC1
0x180009bd8  mov     rcx, [rbp+178h]; this
0x180009bdf  lea     edx, [r14-34h]; void *
0x180009be3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009be8  mov     ebx, eax
0x180009bea  jmp     loc_180009CC3
0x180009bef  lea     rdx, [rsp+270h+var_24C]; int *
0x180009bf4  mov     [rsp+270h+var_24C], 0
0x180009bfc  mov     rcx, rax; hHandle
0x180009bff  mov     [rsp+270h+var_250], 0; int
0x180009c07  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009c0c  mov     ebx, eax
0x180009c0e  test    eax, eax
0x180009c10  jns     short loc_180009C2B
0x180009c12  mov     rcx, [rbp+178h]; this
0x180009c19  mov     r9d, eax; char *
0x180009c1c  mov     edx, 0D6h; void *
0x180009c21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009c26  jmp     loc_180009CC3
0x180009c2b  lea     r8, asc_18007D920; "h"
0x180009c32  mov     rdx, r14; unsigned __int64
0x180009c35  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009c3a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009c3f  lea     r8, [rsp+270h+Name]; lpName
0x180009c44  xor     edx, edx; bInheritHandle
0x180009c46  mov     ecx, 1F0003h; dwDesiredAccess
0x180009c4b  call    cs:__imp_OpenSemaphoreW
0x180009c51  mov     [rsp+270h+var_248], rax
0x180009c56  test    rax, rax
0x180009c59  jnz     short loc_180009C7A
0x180009c5b  mov     rcx, [rbp+178h]; this
0x180009c62  mov     edx, 0DCh; void *
0x180009c67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009c6c  mov     ebx, eax
0x180009c6e  lea     rcx, [rsp+270h+var_248]
0x180009c73  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009c78  jmp     short loc_180009CC3
0x180009c7a  lea     rdx, [rsp+270h+var_250]; int *
0x180009c7f  mov     rcx, rax; hHandle
0x180009c82  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009c87  mov     ebx, eax
0x180009c89  test    eax, eax
0x180009c8b  jns     short loc_180009CA3
0x180009c8d  mov     rcx, [rbp+178h]; this
0x180009c94  mov     r9d, eax; char *
0x180009c97  mov     edx, 0DEh; void *
0x180009c9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ca1  jmp     short loc_180009C6E
0x180009ca3  lea     rcx, [rsp+270h+var_248]
0x180009ca8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009cad  movsxd  rcx, [rsp+270h+var_250]
0x180009cb2  movsxd  rax, [rsp+270h+var_24C]
0x180009cb7  shl     rcx, 1Fh
0x180009cbb  or      rcx, rax
0x180009cbe  mov     [rdi], rcx
0x180009cc1  xor     ebx, ebx
0x180009cc3  lea     rcx, [rsp+270h+var_240]
0x180009cc8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009ccd  mov     eax, ebx
0x180009ccf  mov     rcx, [rbp+170h+var_20]
0x180009cd6  xor     rcx, rsp; StackCookie
0x180009cd9  call    __security_check_cookie
0x180009cde  mov     rbx, [rsp+270h+arg_8]
0x180009ce6  add     rsp, 260h
0x180009ced  pop     r14
0x180009cef  pop     rdi
0x180009cf0  pop     rbp
0x180009cf1  retn
```
