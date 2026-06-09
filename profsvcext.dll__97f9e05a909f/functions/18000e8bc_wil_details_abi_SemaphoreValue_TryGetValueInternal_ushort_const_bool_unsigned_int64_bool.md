# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000e8bc`
- end: `0x18000ea7a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000e838`

## callees

- `0x180003b80`
- `0x18000547c`
- `0x180006a9c`
- `0x180006b3c`
- `0x180008e5c`
- `0x18000a520`
- `0x18000d4b8`
- `0x18000e8bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e925`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e9c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e925`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000e9c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e935`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  wil::details *v10; // rax
  const char *v11; // r9
  void *v12; // rdx
  int v13; // eax
  void *v14; // rdx
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v18; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v19; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 260, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v19 = v5;
  if ( v5 )
  {
    v17 = 0;
    v16 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v17);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, 260, L"h");
    v10 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v18 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v16);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v18,
          v14);
        *a3 = v17 | (unsigned __int64)((__int64)v16 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v11);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v18,
      v12);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v19,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x18000e8bc  mov     [rsp-8+arg_8], rbx
0x18000e8c1  push    rbp
0x18000e8c2  push    rdi
0x18000e8c3  push    r14
0x18000e8c5  lea     rbp, [rsp-160h]
0x18000e8cd  sub     rsp, 260h
0x18000e8d4  mov     rax, cs:__security_cookie
0x18000e8db  xor     rax, rsp
0x18000e8de  mov     [rbp+170h+var_20], rax
0x18000e8e5  mov     rdi, r8
0x18000e8e8  mov     qword ptr [r8], 0
0x18000e8ef  mov     r8, rcx; unsigned __int16 *
0x18000e8f2  mov     r14d, 104h
0x18000e8f8  mov     edx, r14d; unsigned __int64
0x18000e8fb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e900  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e905  lea     r8, aP0; "_p0"
0x18000e90c  mov     edx, r14d; unsigned __int64
0x18000e90f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e914  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e919  lea     r8, [rsp+270h+Name]; lpName
0x18000e91e  xor     edx, edx; bInheritHandle
0x18000e920  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e925  call    cs:__imp_OpenSemaphoreW
0x18000e92b  mov     [rsp+270h+var_240], rax
0x18000e930  test    rax, rax
0x18000e933  jnz     short loc_18000E962
0x18000e935  call    cs:__imp_GetLastError
0x18000e93b  cmp     eax, 2
0x18000e93e  jz      loc_18000EA49
0x18000e944  mov     rcx, [rbp+178h]; this
0x18000e94b  lea     r8, aWil; "wil"
0x18000e952  lea     edx, [r14-34h]; void *
0x18000e956  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e95b  mov     ebx, eax
0x18000e95d  jmp     loc_18000EA4B
0x18000e962  lea     rdx, [rsp+270h+var_24C]; int *
0x18000e967  mov     [rsp+270h+var_24C], 0
0x18000e96f  mov     rcx, rax; hHandle
0x18000e972  mov     [rsp+270h+var_250], 0; int
0x18000e97a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e97f  mov     ebx, eax
0x18000e981  test    eax, eax
0x18000e983  jns     short loc_18000E9A5
0x18000e985  mov     rcx, [rbp+178h]; this
0x18000e98c  lea     r8, aWil; "wil"
0x18000e993  mov     r9d, eax; char *
0x18000e996  mov     edx, 0D6h; void *
0x18000e99b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e9a0  jmp     loc_18000EA4B
0x18000e9a5  lea     r8, asc_1800227C0; "h"
0x18000e9ac  mov     rdx, r14; unsigned __int64
0x18000e9af  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e9b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e9b9  lea     r8, [rsp+270h+Name]; lpName
0x18000e9be  xor     edx, edx; bInheritHandle
0x18000e9c0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e9c5  call    cs:__imp_OpenSemaphoreW
0x18000e9cb  mov     [rsp+270h+var_248], rax
0x18000e9d0  test    rax, rax
0x18000e9d3  jnz     short loc_18000E9FB
0x18000e9d5  mov     rcx, [rbp+178h]; this
0x18000e9dc  lea     r8, aWil; "wil"
0x18000e9e3  mov     edx, 0DCh; void *
0x18000e9e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e9ed  mov     ebx, eax
0x18000e9ef  lea     rcx, [rsp+270h+var_248]
0x18000e9f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e9f9  jmp     short loc_18000EA4B
0x18000e9fb  lea     rdx, [rsp+270h+var_250]; int *
0x18000ea00  mov     rcx, rax; hHandle
0x18000ea03  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ea08  mov     ebx, eax
0x18000ea0a  test    eax, eax
0x18000ea0c  jns     short loc_18000EA2B
0x18000ea0e  mov     rcx, [rbp+178h]; this
0x18000ea15  lea     r8, aWil; "wil"
0x18000ea1c  mov     r9d, eax; char *
0x18000ea1f  mov     edx, 0DEh; void *
0x18000ea24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea29  jmp     short loc_18000E9EF
0x18000ea2b  lea     rcx, [rsp+270h+var_248]
0x18000ea30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ea35  movsxd  rcx, [rsp+270h+var_250]
0x18000ea3a  movsxd  rax, [rsp+270h+var_24C]
0x18000ea3f  shl     rcx, 1Fh
0x18000ea43  or      rcx, rax
0x18000ea46  mov     [rdi], rcx
0x18000ea49  xor     ebx, ebx
0x18000ea4b  lea     rcx, [rsp+270h+var_240]
0x18000ea50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ea55  mov     eax, ebx
0x18000ea57  mov     rcx, [rbp+170h+var_20]
0x18000ea5e  xor     rcx, rsp; StackCookie
0x18000ea61  call    __security_check_cookie
0x18000ea66  mov     rbx, [rsp+270h+arg_8]
0x18000ea6e  add     rsp, 260h
0x18000ea75  pop     r14
0x18000ea77  pop     rdi
0x18000ea78  pop     rbp
0x18000ea79  retn
```
