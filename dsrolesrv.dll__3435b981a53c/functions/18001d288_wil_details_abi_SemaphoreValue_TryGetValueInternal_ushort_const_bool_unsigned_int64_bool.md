# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001d288`
- end: `0x18001d424`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001d214`

## callees

- `0x180019330`
- `0x18001ae28`
- `0x18001c894`
- `0x18001c8b4`
- `0x18001cd60`
- `0x18001cddc`
- `0x18001d288`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d2fc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001d2ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001d37c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001d2ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001d37c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v24; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v22);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v19);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x18001d288  mov     [rsp-8+arg_8], rbx
0x18001d28d  mov     [rsp-8+arg_18], rdi
0x18001d292  push    rbp
0x18001d293  lea     rbp, [rsp-160h]
0x18001d29b  sub     rsp, 260h
0x18001d2a2  mov     rax, cs:__security_cookie
0x18001d2a9  xor     rax, rsp
0x18001d2ac  mov     [rbp+160h+var_10], rax
0x18001d2b3  mov     rdi, r8
0x18001d2b6  mov     qword ptr [r8], 0
0x18001d2bd  mov     r8, rcx; unsigned __int16 *
0x18001d2c0  mov     edx, 104h; unsigned __int64
0x18001d2c5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001d2ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001d2cf  lea     r8, aP0; "_p0"
0x18001d2d6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001d2db  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d2e0  lea     r8, [rsp+260h+Name]; lpName
0x18001d2e5  xor     edx, edx; bInheritHandle
0x18001d2e7  mov     ecx, 1F0003h; dwDesiredAccess
0x18001d2ec  call    cs:__imp_OpenSemaphoreW
0x18001d2f2  mov     [rsp+260h+var_230], rax
0x18001d2f7  test    rax, rax
0x18001d2fa  jnz     short loc_18001D323
0x18001d2fc  call    cs:__imp_GetLastError
0x18001d302  cmp     eax, 2
0x18001d305  jz      loc_18001D3F2
0x18001d30b  mov     rcx, [rbp+168h]; this
0x18001d312  mov     edx, 0D0h; void *
0x18001d317  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d31c  mov     ebx, eax
0x18001d31e  jmp     loc_18001D3F4
0x18001d323  lea     rdx, [rsp+260h+var_23C]; int *
0x18001d328  mov     [rsp+260h+var_23C], 0
0x18001d330  mov     rcx, rax; hHandle
0x18001d333  mov     [rsp+260h+var_240], 0; int
0x18001d33b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001d340  mov     ebx, eax
0x18001d342  test    eax, eax
0x18001d344  jns     short loc_18001D35F
0x18001d346  mov     rcx, [rbp+168h]; this
0x18001d34d  mov     r9d, eax; char *
0x18001d350  mov     edx, 0D6h; void *
0x18001d355  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d35a  jmp     loc_18001D3F4
0x18001d35f  lea     r8, asc_1800410A8; "h"
0x18001d366  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001d36b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001d370  lea     r8, [rsp+260h+Name]; lpName
0x18001d375  xor     edx, edx; bInheritHandle
0x18001d377  mov     ecx, 1F0003h; dwDesiredAccess
0x18001d37c  call    cs:__imp_OpenSemaphoreW
0x18001d382  mov     [rsp+260h+var_238], rax
0x18001d387  test    rax, rax
0x18001d38a  jnz     short loc_18001D3AB
0x18001d38c  mov     rcx, [rbp+168h]; this
0x18001d393  mov     edx, 0DCh; void *
0x18001d398  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001d39d  mov     ebx, eax
0x18001d39f  lea     rcx, [rsp+260h+var_238]
0x18001d3a4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d3a9  jmp     short loc_18001D3F4
0x18001d3ab  lea     rdx, [rsp+260h+var_240]; int *
0x18001d3b0  mov     rcx, rax; hHandle
0x18001d3b3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001d3b8  mov     ebx, eax
0x18001d3ba  test    eax, eax
0x18001d3bc  jns     short loc_18001D3D4
0x18001d3be  mov     rcx, [rbp+168h]; this
0x18001d3c5  mov     r9d, eax; char *
0x18001d3c8  mov     edx, 0DEh; void *
0x18001d3cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d3d2  jmp     short loc_18001D39F
0x18001d3d4  lea     rcx, [rsp+260h+var_238]
0x18001d3d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d3de  movsxd  rcx, [rsp+260h+var_240]
0x18001d3e3  movsxd  rax, [rsp+260h+var_23C]
0x18001d3e8  shl     rcx, 1Fh
0x18001d3ec  or      rcx, rax
0x18001d3ef  mov     [rdi], rcx
0x18001d3f2  xor     ebx, ebx
0x18001d3f4  lea     rcx, [rsp+260h+var_230]
0x18001d3f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001d3fe  mov     eax, ebx
0x18001d400  mov     rcx, [rbp+160h+var_10]
0x18001d407  xor     rcx, rsp; StackCookie
0x18001d40a  call    __security_check_cookie
0x18001d40f  lea     r11, [rsp+260h+var_s0]
0x18001d417  mov     rbx, [r11+18h]
0x18001d41b  mov     rdi, [r11+28h]
0x18001d41f  mov     rsp, r11
0x18001d422  pop     rbp
0x18001d423  retn
```
