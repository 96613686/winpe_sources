# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180035b44`
- end: `0x180035ce6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180035ad0`

## callees

- `0x180006364`
- `0x18002e61c`
- `0x18003233c`
- `0x1800336b8`
- `0x180034fd4`
- `0x180034ff4`
- `0x180035b44`
- `0x180037620`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180035bad`
- `KERNEL32!OpenSemaphoreW` at `0x180035c3f`
- `KERNEL32!OpenSemaphoreW` at `0x180035bad`
- `KERNEL32!OpenSemaphoreW` at `0x180035c3f`
- `KERNEL32!GetLastError` at `0x180035bbd`
- `KERNEL32!GetLastError` at `0x180035bbd`

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
  int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  int v15; // r8d
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14);
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
0x180035b44  mov     [rsp-8+arg_8], rbx
0x180035b49  push    rbp
0x180035b4a  push    rdi
0x180035b4b  push    r14
0x180035b4d  lea     rbp, [rsp-160h]
0x180035b55  sub     rsp, 260h
0x180035b5c  mov     rax, cs:__security_cookie
0x180035b63  xor     rax, rsp
0x180035b66  mov     [rbp+170h+var_20], rax
0x180035b6d  mov     rdi, r8
0x180035b70  mov     qword ptr [r8], 0
0x180035b77  mov     r8, rcx; unsigned __int16 *
0x180035b7a  mov     r14d, 104h
0x180035b80  mov     edx, r14d; unsigned __int64
0x180035b83  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180035b88  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180035b8d  lea     r8, aP0; "_p0"
0x180035b94  mov     edx, r14d; unsigned __int64
0x180035b97  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180035b9c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035ba1  lea     r8, [rsp+270h+Name]; lpName
0x180035ba6  xor     edx, edx; bInheritHandle
0x180035ba8  mov     ecx, 1F0003h; dwDesiredAccess
0x180035bad  call    cs:__imp_OpenSemaphoreW
0x180035bb3  mov     [rsp+270h+var_240], rax
0x180035bb8  test    rax, rax
0x180035bbb  jnz     short loc_180035BE3
0x180035bbd  call    cs:__imp_GetLastError
0x180035bc3  cmp     eax, 2
0x180035bc6  jz      loc_180035CB5
0x180035bcc  mov     rcx, [rbp+178h]; this
0x180035bd3  lea     edx, [r14-34h]; void *
0x180035bd7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035bdc  mov     ebx, eax
0x180035bde  jmp     loc_180035CB7
0x180035be3  lea     rdx, [rsp+270h+var_24C]; int *
0x180035be8  mov     [rsp+270h+var_24C], 0
0x180035bf0  mov     rcx, rax; hHandle
0x180035bf3  mov     [rsp+270h+var_250], 0; int
0x180035bfb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180035c00  mov     ebx, eax
0x180035c02  test    eax, eax
0x180035c04  jns     short loc_180035C1F
0x180035c06  mov     rcx, [rbp+178h]; this
0x180035c0d  mov     r9d, eax; char *
0x180035c10  mov     edx, 0D6h; void *
0x180035c15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035c1a  jmp     loc_180035CB7
0x180035c1f  lea     r8, asc_18003F648; "h"
0x180035c26  mov     rdx, r14; unsigned __int64
0x180035c29  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180035c2e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035c33  lea     r8, [rsp+270h+Name]; lpName
0x180035c38  xor     edx, edx; bInheritHandle
0x180035c3a  mov     ecx, 1F0003h; dwDesiredAccess
0x180035c3f  call    cs:__imp_OpenSemaphoreW
0x180035c45  mov     [rsp+270h+var_248], rax
0x180035c4a  test    rax, rax
0x180035c4d  jnz     short loc_180035C6E
0x180035c4f  mov     rcx, [rbp+178h]; this
0x180035c56  mov     edx, 0DCh; void *
0x180035c5b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180035c60  mov     ebx, eax
0x180035c62  lea     rcx, [rsp+270h+var_248]
0x180035c67  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035c6c  jmp     short loc_180035CB7
0x180035c6e  lea     rdx, [rsp+270h+var_250]; int *
0x180035c73  mov     rcx, rax; hHandle
0x180035c76  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180035c7b  mov     ebx, eax
0x180035c7d  test    eax, eax
0x180035c7f  jns     short loc_180035C97
0x180035c81  mov     rcx, [rbp+178h]; this
0x180035c88  mov     r9d, eax; char *
0x180035c8b  mov     edx, 0DEh; void *
0x180035c90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035c95  jmp     short loc_180035C62
0x180035c97  lea     rcx, [rsp+270h+var_248]
0x180035c9c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035ca1  movsxd  rcx, [rsp+270h+var_250]
0x180035ca6  movsxd  rax, [rsp+270h+var_24C]
0x180035cab  shl     rcx, 1Fh
0x180035caf  or      rcx, rax
0x180035cb2  mov     [rdi], rcx
0x180035cb5  xor     ebx, ebx
0x180035cb7  lea     rcx, [rsp+270h+var_240]
0x180035cbc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035cc1  mov     eax, ebx
0x180035cc3  mov     rcx, [rbp+170h+var_20]
0x180035cca  xor     rcx, rsp; StackCookie
0x180035ccd  call    __security_check_cookie
0x180035cd2  mov     rbx, [rsp+270h+arg_8]
0x180035cda  add     rsp, 260h
0x180035ce1  pop     r14
0x180035ce3  pop     rdi
0x180035ce4  pop     rbp
0x180035ce5  retn
```
