# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003b06c`
- end: `0x18003b20e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003aff8`

## callees

- `0x18002fb50`
- `0x180037954`
- `0x180038cf0`
- `0x18003a3cc`
- `0x18003a3ec`
- `0x18003aaac`
- `0x18003ab38`
- `0x18003b06c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b0e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b0e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b0d5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b167`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b0d5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b167`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18003b06c  mov     [rsp-8+arg_8], rbx
0x18003b071  push    rbp
0x18003b072  push    rdi
0x18003b073  push    r14
0x18003b075  lea     rbp, [rsp-160h]
0x18003b07d  sub     rsp, 260h
0x18003b084  mov     rax, cs:__security_cookie
0x18003b08b  xor     rax, rsp
0x18003b08e  mov     [rbp+170h+var_20], rax
0x18003b095  mov     rdi, r8
0x18003b098  mov     qword ptr [r8], 0
0x18003b09f  mov     r8, rcx; unsigned __int16 *
0x18003b0a2  mov     r14d, 104h
0x18003b0a8  mov     edx, r14d; unsigned __int64
0x18003b0ab  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b0b0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b0b5  lea     r8, aP0; "_p0"
0x18003b0bc  mov     edx, r14d; unsigned __int64
0x18003b0bf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b0c4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b0c9  lea     r8, [rsp+270h+Name]; lpName
0x18003b0ce  xor     edx, edx; bInheritHandle
0x18003b0d0  mov     ecx, 1F0003h; dwDesiredAccess
0x18003b0d5  call    cs:__imp_OpenSemaphoreW
0x18003b0db  mov     [rsp+270h+var_240], rax
0x18003b0e0  test    rax, rax
0x18003b0e3  jnz     short loc_18003B10B
0x18003b0e5  call    cs:__imp_GetLastError
0x18003b0eb  cmp     eax, 2
0x18003b0ee  jz      loc_18003B1DD
0x18003b0f4  mov     rcx, [rbp+178h]; this
0x18003b0fb  lea     edx, [r14-34h]; void *
0x18003b0ff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b104  mov     ebx, eax
0x18003b106  jmp     loc_18003B1DF
0x18003b10b  mov     [rsp+270h+var_24C], 0
0x18003b113  mov     [rsp+270h+var_250], 0; int
0x18003b11b  lea     rdx, [rsp+270h+var_24C]; int *
0x18003b120  mov     rcx, rax; hHandle
0x18003b123  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003b128  mov     ebx, eax
0x18003b12a  test    eax, eax
0x18003b12c  jns     short loc_18003B147
0x18003b12e  mov     rcx, [rbp+178h]; this
0x18003b135  mov     r9d, eax; char *
0x18003b138  mov     edx, 0D6h; void *
0x18003b13d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b142  jmp     loc_18003B1DF
0x18003b147  lea     r8, asc_1800730D8; "h"
0x18003b14e  mov     rdx, r14; unsigned __int64
0x18003b151  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b156  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b15b  lea     r8, [rsp+270h+Name]; lpName
0x18003b160  xor     edx, edx; bInheritHandle
0x18003b162  mov     ecx, 1F0003h; dwDesiredAccess
0x18003b167  call    cs:__imp_OpenSemaphoreW
0x18003b16d  mov     [rsp+270h+var_248], rax
0x18003b172  test    rax, rax
0x18003b175  jnz     short loc_18003B196
0x18003b177  mov     rcx, [rbp+178h]; this
0x18003b17e  mov     edx, 0DCh; void *
0x18003b183  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b188  mov     ebx, eax
0x18003b18a  lea     rcx, [rsp+270h+var_248]
0x18003b18f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b194  jmp     short loc_18003B1DF
0x18003b196  lea     rdx, [rsp+270h+var_250]; int *
0x18003b19b  mov     rcx, rax; hHandle
0x18003b19e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003b1a3  mov     ebx, eax
0x18003b1a5  test    eax, eax
0x18003b1a7  jns     short loc_18003B1BF
0x18003b1a9  mov     rcx, [rbp+178h]; this
0x18003b1b0  mov     r9d, eax; char *
0x18003b1b3  mov     edx, 0DEh; void *
0x18003b1b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b1bd  jmp     short loc_18003B18A
0x18003b1bf  lea     rcx, [rsp+270h+var_248]
0x18003b1c4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b1c9  movsxd  rcx, [rsp+270h+var_250]
0x18003b1ce  shl     rcx, 1Fh
0x18003b1d2  movsxd  rax, [rsp+270h+var_24C]
0x18003b1d7  or      rcx, rax
0x18003b1da  mov     [rdi], rcx
0x18003b1dd  xor     ebx, ebx
0x18003b1df  lea     rcx, [rsp+270h+var_240]
0x18003b1e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b1e9  mov     eax, ebx
0x18003b1eb  mov     rcx, [rbp+170h+var_20]
0x18003b1f2  xor     rcx, rsp; StackCookie
0x18003b1f5  call    __security_check_cookie
0x18003b1fa  mov     rbx, [rsp+270h+arg_8]
0x18003b202  add     rsp, 260h
0x18003b209  pop     r14
0x18003b20b  pop     rdi
0x18003b20c  pop     rbp
0x18003b20d  retn
```
