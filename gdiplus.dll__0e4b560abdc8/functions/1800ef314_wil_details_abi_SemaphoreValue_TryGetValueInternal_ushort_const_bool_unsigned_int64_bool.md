# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800ef314`
- end: `0x1800ef4ce`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `442`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800ef2a4`

## callees

- `0x1800669e4`
- `0x1800e9380`
- `0x1800eaf94`
- `0x1800eca04`
- `0x1800ee90c`
- `0x1800ee92c`
- `0x1800eee6c`
- `0x1800ef314`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ef37a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ef410`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ef37a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800ef410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef390`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef390`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebx
  unsigned __int64 v6; // rdx
  HANDLE v7; // rax
  unsigned int v8; // r8d
  const char *v9; // r9
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  int v13; // edi
  HANDLE v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  int v17; // eax
  unsigned int v18; // r8d
  int v20[2]; // [rsp+28h] [rbp-E0h] BYREF
  HANDLE v21; // [rsp+30h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+38h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+48h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+270h] [rbp+168h]

  LastError = 0;
  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v6, L"_p0");
  v7 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v7;
  if ( v7 )
  {
    v20[1] = 0;
    v20[0] = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v7, &v20[1]);
    v13 = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, v11, L"h");
      v14 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v21 = v14;
      if ( !v14 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v15, v16);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        goto LABEL_12;
      }
      v17 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, v20);
      v13 = v17;
      if ( v17 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20[1] | (unsigned __int64)((__int64)v20[0] << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v18, (const char *)(unsigned int)v17, v20[0]);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD3,
        v12,
        (const char *)(unsigned int)ValueFromSemaphore,
        v20[0]);
    }
    LastError = v13;
  }
  else if ( GetLastError() != 2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v8, v9);
  }
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x1800ef314  mov     rax, rsp
0x1800ef317  mov     [rax+8], rbx
0x1800ef31b  mov     [rax+10h], rsi
0x1800ef31f  mov     [rax+20h], rdi
0x1800ef323  push    rbp
0x1800ef324  lea     rbp, [rax-168h]
0x1800ef32b  sub     rsp, 260h
0x1800ef332  mov     rax, cs:__security_cookie
0x1800ef339  xor     rax, rsp
0x1800ef33c  mov     [rbp+160h+var_10], rax
0x1800ef343  mov     rsi, r8
0x1800ef346  xor     ebx, ebx
0x1800ef348  mov     [r8], rbx
0x1800ef34b  mov     edx, 104h; unsigned __int64
0x1800ef350  mov     r8, rcx; unsigned __int16 *
0x1800ef353  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800ef358  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ef35d  lea     r8, aP0; "_p0"
0x1800ef364  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800ef369  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ef36e  lea     r8, [rsp+260h+Name]; lpName
0x1800ef373  xor     edx, edx; bInheritHandle
0x1800ef375  mov     ecx, 1F0003h; dwDesiredAccess
0x1800ef37a  call    cs:__imp_OpenSemaphoreW
0x1800ef381  nop     dword ptr [rax+rax+00h]
0x1800ef386  mov     [rsp+260h+var_230], rax
0x1800ef38b  test    rax, rax
0x1800ef38e  jnz     short loc_1800EF3BD
0x1800ef390  call    cs:__imp_GetLastError
0x1800ef397  nop     dword ptr [rax+rax+00h]
0x1800ef39c  cmp     eax, 2
0x1800ef39f  jz      loc_1800EF499
0x1800ef3a5  mov     rcx, [rbp+168h]; this
0x1800ef3ac  mov     edx, 0CDh; void *
0x1800ef3b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ef3b6  mov     ebx, eax
0x1800ef3b8  jmp     loc_1800EF499
0x1800ef3bd  lea     rdx, [rsp+260h+var_240+4]; int *
0x1800ef3c2  mov     [rsp+260h+var_240+4], ebx
0x1800ef3c6  mov     rcx, rax; hHandle
0x1800ef3c9  mov     [rsp+260h+var_240], ebx; int
0x1800ef3cd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800ef3d2  mov     edi, eax
0x1800ef3d4  test    eax, eax
0x1800ef3d6  jns     short loc_1800EF3F3
0x1800ef3d8  mov     rcx, [rbp+168h]; this
0x1800ef3df  mov     r9d, eax; char *
0x1800ef3e2  mov     edx, 0D3h; void *
0x1800ef3e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef3ec  mov     ebx, edi
0x1800ef3ee  jmp     loc_1800EF499
0x1800ef3f3  lea     r8, asc_18018A738; "h"
0x1800ef3fa  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800ef3ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800ef404  lea     r8, [rsp+260h+Name]; lpName
0x1800ef409  xor     edx, edx; bInheritHandle
0x1800ef40b  mov     ecx, 1F0003h; dwDesiredAccess
0x1800ef410  call    cs:__imp_OpenSemaphoreW
0x1800ef417  nop     dword ptr [rax+rax+00h]
0x1800ef41c  mov     [rsp+260h+var_238], rax
0x1800ef421  test    rax, rax
0x1800ef424  jnz     short loc_1800EF445
0x1800ef426  mov     rcx, [rbp+168h]; this
0x1800ef42d  mov     edx, 0D9h; void *
0x1800ef432  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800ef437  lea     rcx, [rsp+260h+var_238]
0x1800ef43c  mov     ebx, eax
0x1800ef43e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ef443  jmp     short loc_1800EF499
0x1800ef445  lea     rdx, [rsp+260h+var_240]; int *
0x1800ef44a  mov     rcx, rax; hHandle
0x1800ef44d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800ef452  mov     edi, eax
0x1800ef454  test    eax, eax
0x1800ef456  jns     short loc_1800EF47B
0x1800ef458  mov     rcx, [rbp+168h]; this
0x1800ef45f  mov     r9d, eax; char *
0x1800ef462  mov     edx, 0DBh; void *
0x1800ef467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ef46c  lea     rcx, [rsp+260h+var_238]
0x1800ef471  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ef476  jmp     loc_1800EF3EC
0x1800ef47b  lea     rcx, [rsp+260h+var_238]
0x1800ef480  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ef485  movsxd  rdx, [rsp+260h+var_240]
0x1800ef48a  movsxd  rcx, [rsp+260h+var_240+4]
0x1800ef48f  shl     rdx, 1Fh
0x1800ef493  or      rdx, rcx
0x1800ef496  mov     [rsi], rdx
0x1800ef499  lea     rcx, [rsp+260h+var_230]
0x1800ef49e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800ef4a3  mov     eax, ebx
0x1800ef4a5  mov     rcx, [rbp+160h+var_10]
0x1800ef4ac  xor     rcx, rsp; StackCookie
0x1800ef4af  call    __security_check_cookie
0x1800ef4b4  lea     r11, [rsp+260h+var_s0]
0x1800ef4bc  mov     rbx, [r11+10h]
0x1800ef4c0  mov     rsi, [r11+18h]
0x1800ef4c4  mov     rdi, [r11+28h]
0x1800ef4c8  mov     rsp, r11
0x1800ef4cb  pop     rbp
0x1800ef4cc  retn
```
