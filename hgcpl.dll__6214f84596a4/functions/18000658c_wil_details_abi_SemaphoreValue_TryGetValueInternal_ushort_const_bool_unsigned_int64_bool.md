# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000658c`
- end: `0x18000672e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006518`

## callees

- `0x180004960`
- `0x1800055f4`
- `0x180006050`
- `0x180006070`
- `0x180006338`
- `0x1800063c4`
- `0x18000658c`
- `0x180018a80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800065f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006687`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800065f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006605`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006605`

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
0x18000658c  mov     [rsp-8+arg_8], rbx
0x180006591  push    rbp
0x180006592  push    rdi
0x180006593  push    r14
0x180006595  lea     rbp, [rsp-160h]
0x18000659d  sub     rsp, 260h
0x1800065a4  mov     rax, cs:__security_cookie
0x1800065ab  xor     rax, rsp
0x1800065ae  mov     [rbp+170h+var_20], rax
0x1800065b5  mov     rdi, r8
0x1800065b8  mov     qword ptr [r8], 0
0x1800065bf  mov     r8, rcx; unsigned __int16 *
0x1800065c2  mov     r14d, 104h
0x1800065c8  mov     edx, r14d; unsigned __int64
0x1800065cb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800065d0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800065d5  lea     r8, aP0; "_p0"
0x1800065dc  mov     edx, r14d; unsigned __int64
0x1800065df  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800065e4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800065e9  lea     r8, [rsp+270h+Name]; lpName
0x1800065ee  xor     edx, edx; bInheritHandle
0x1800065f0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800065f5  call    cs:__imp_OpenSemaphoreW
0x1800065fb  mov     [rsp+270h+var_240], rax
0x180006600  test    rax, rax
0x180006603  jnz     short loc_18000662B
0x180006605  call    cs:__imp_GetLastError
0x18000660b  cmp     eax, 2
0x18000660e  jz      loc_1800066FD
0x180006614  mov     rcx, [rbp+178h]; this
0x18000661b  lea     edx, [r14-34h]; void *
0x18000661f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006624  mov     ebx, eax
0x180006626  jmp     loc_1800066FF
0x18000662b  lea     rdx, [rsp+270h+var_24C]; int *
0x180006630  mov     [rsp+270h+var_24C], 0
0x180006638  mov     rcx, rax; hHandle
0x18000663b  mov     [rsp+270h+var_250], 0; int
0x180006643  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006648  mov     ebx, eax
0x18000664a  test    eax, eax
0x18000664c  jns     short loc_180006667
0x18000664e  mov     rcx, [rbp+178h]; this
0x180006655  mov     r9d, eax; char *
0x180006658  mov     edx, 0D6h; void *
0x18000665d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006662  jmp     loc_1800066FF
0x180006667  lea     r8, asc_18001D968; "h"
0x18000666e  mov     rdx, r14; unsigned __int64
0x180006671  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006676  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000667b  lea     r8, [rsp+270h+Name]; lpName
0x180006680  xor     edx, edx; bInheritHandle
0x180006682  mov     ecx, 1F0003h; dwDesiredAccess
0x180006687  call    cs:__imp_OpenSemaphoreW
0x18000668d  mov     [rsp+270h+var_248], rax
0x180006692  test    rax, rax
0x180006695  jnz     short loc_1800066B6
0x180006697  mov     rcx, [rbp+178h]; this
0x18000669e  mov     edx, 0DCh; void *
0x1800066a3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800066a8  mov     ebx, eax
0x1800066aa  lea     rcx, [rsp+270h+var_248]
0x1800066af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800066b4  jmp     short loc_1800066FF
0x1800066b6  lea     rdx, [rsp+270h+var_250]; int *
0x1800066bb  mov     rcx, rax; hHandle
0x1800066be  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800066c3  mov     ebx, eax
0x1800066c5  test    eax, eax
0x1800066c7  jns     short loc_1800066DF
0x1800066c9  mov     rcx, [rbp+178h]; this
0x1800066d0  mov     r9d, eax; char *
0x1800066d3  mov     edx, 0DEh; void *
0x1800066d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800066dd  jmp     short loc_1800066AA
0x1800066df  lea     rcx, [rsp+270h+var_248]
0x1800066e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800066e9  movsxd  rcx, [rsp+270h+var_250]
0x1800066ee  movsxd  rax, [rsp+270h+var_24C]
0x1800066f3  shl     rcx, 1Fh
0x1800066f7  or      rcx, rax
0x1800066fa  mov     [rdi], rcx
0x1800066fd  xor     ebx, ebx
0x1800066ff  lea     rcx, [rsp+270h+var_240]
0x180006704  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006709  mov     eax, ebx
0x18000670b  mov     rcx, [rbp+170h+var_20]
0x180006712  xor     rcx, rsp; StackCookie
0x180006715  call    __security_check_cookie
0x18000671a  mov     rbx, [rsp+270h+arg_8]
0x180006722  add     rsp, 260h
0x180006729  pop     r14
0x18000672b  pop     rdi
0x18000672c  pop     rbp
0x18000672d  retn
```
