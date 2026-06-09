# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b984`
- end: `0x18000bb42`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b7d4`

## callees

- `0x18000b984`
- `0x18000bb48`
- `0x18000bba8`
- `0x18000bca4`
- `0x18000c130`
- `0x18000c548`
- `0x180011930`
- `0x180031c78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b9ed`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ba8d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b9ed`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ba8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9fd`

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
0x18000b984  mov     [rsp-8+arg_8], rbx
0x18000b989  push    rbp
0x18000b98a  push    rdi
0x18000b98b  push    r14
0x18000b98d  lea     rbp, [rsp-160h]
0x18000b995  sub     rsp, 260h
0x18000b99c  mov     rax, cs:__security_cookie
0x18000b9a3  xor     rax, rsp
0x18000b9a6  mov     [rbp+170h+var_20], rax
0x18000b9ad  mov     rdi, r8
0x18000b9b0  mov     qword ptr [r8], 0
0x18000b9b7  mov     r8, rcx; unsigned __int16 *
0x18000b9ba  mov     r14d, 104h
0x18000b9c0  mov     edx, r14d; unsigned __int64
0x18000b9c3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b9c8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b9cd  lea     r8, aP0; "_p0"
0x18000b9d4  mov     edx, r14d; unsigned __int64
0x18000b9d7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b9dc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b9e1  lea     r8, [rsp+270h+Name]; lpName
0x18000b9e6  xor     edx, edx; bInheritHandle
0x18000b9e8  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b9ed  call    cs:__imp_OpenSemaphoreW
0x18000b9f3  mov     [rsp+270h+var_240], rax
0x18000b9f8  test    rax, rax
0x18000b9fb  jnz     short loc_18000BA2A
0x18000b9fd  call    cs:__imp_GetLastError
0x18000ba03  cmp     eax, 2
0x18000ba06  jz      loc_18000BB11
0x18000ba0c  mov     rcx, [rbp+178h]; this
0x18000ba13  lea     r8, aWil; "wil"
0x18000ba1a  lea     edx, [r14-34h]; void *
0x18000ba1e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ba23  mov     ebx, eax
0x18000ba25  jmp     loc_18000BB13
0x18000ba2a  lea     rdx, [rsp+270h+var_24C]; int *
0x18000ba2f  mov     [rsp+270h+var_24C], 0
0x18000ba37  mov     rcx, rax; hHandle
0x18000ba3a  mov     [rsp+270h+var_250], 0; int
0x18000ba42  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ba47  mov     ebx, eax
0x18000ba49  test    eax, eax
0x18000ba4b  jns     short loc_18000BA6D
0x18000ba4d  mov     rcx, [rbp+178h]; this
0x18000ba54  lea     r8, aWil; "wil"
0x18000ba5b  mov     r9d, eax; char *
0x18000ba5e  mov     edx, 0D6h; void *
0x18000ba63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba68  jmp     loc_18000BB13
0x18000ba6d  lea     r8, asc_18003A680; "h"
0x18000ba74  mov     rdx, r14; unsigned __int64
0x18000ba77  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000ba7c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ba81  lea     r8, [rsp+270h+Name]; lpName
0x18000ba86  xor     edx, edx; bInheritHandle
0x18000ba88  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ba8d  call    cs:__imp_OpenSemaphoreW
0x18000ba93  mov     [rsp+270h+var_248], rax
0x18000ba98  test    rax, rax
0x18000ba9b  jnz     short loc_18000BAC3
0x18000ba9d  mov     rcx, [rbp+178h]; this
0x18000baa4  lea     r8, aWil; "wil"
0x18000baab  mov     edx, 0DCh; void *
0x18000bab0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bab5  mov     ebx, eax
0x18000bab7  lea     rcx, [rsp+270h+var_248]
0x18000babc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bac1  jmp     short loc_18000BB13
0x18000bac3  lea     rdx, [rsp+270h+var_250]; int *
0x18000bac8  mov     rcx, rax; hHandle
0x18000bacb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bad0  mov     ebx, eax
0x18000bad2  test    eax, eax
0x18000bad4  jns     short loc_18000BAF3
0x18000bad6  mov     rcx, [rbp+178h]; this
0x18000badd  lea     r8, aWil; "wil"
0x18000bae4  mov     r9d, eax; char *
0x18000bae7  mov     edx, 0DEh; void *
0x18000baec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000baf1  jmp     short loc_18000BAB7
0x18000baf3  lea     rcx, [rsp+270h+var_248]
0x18000baf8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bafd  movsxd  rcx, [rsp+270h+var_250]
0x18000bb02  movsxd  rax, [rsp+270h+var_24C]
0x18000bb07  shl     rcx, 1Fh
0x18000bb0b  or      rcx, rax
0x18000bb0e  mov     [rdi], rcx
0x18000bb11  xor     ebx, ebx
0x18000bb13  lea     rcx, [rsp+270h+var_240]
0x18000bb18  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bb1d  mov     eax, ebx
0x18000bb1f  mov     rcx, [rbp+170h+var_20]
0x18000bb26  xor     rcx, rsp; StackCookie
0x18000bb29  call    __security_check_cookie
0x18000bb2e  mov     rbx, [rsp+270h+arg_8]
0x18000bb36  add     rsp, 260h
0x18000bb3d  pop     r14
0x18000bb3f  pop     rdi
0x18000bb40  pop     rbp
0x18000bb41  retn
```
