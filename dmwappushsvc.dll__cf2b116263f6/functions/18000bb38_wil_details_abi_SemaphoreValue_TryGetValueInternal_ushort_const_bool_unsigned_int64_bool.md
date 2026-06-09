# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000bb38`
- end: `0x18000bcf0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000bab4`

## callees

- `0x180001a70`
- `0x1800040a4`
- `0x180007a28`
- `0x180008f44`
- `0x18000af58`
- `0x18000af78`
- `0x18000b4d8`
- `0x18000bb38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bb9c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bc3a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bb9c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000bc3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbac`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v20; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
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
    StringCchCatW(Name, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v20,
          v16);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x18000bb38  mov     [rsp-8+arg_8], rbx
0x18000bb3d  mov     [rsp-8+arg_18], rdi
0x18000bb42  push    rbp
0x18000bb43  lea     rbp, [rsp-160h]
0x18000bb4b  sub     rsp, 260h
0x18000bb52  mov     rax, cs:__security_cookie
0x18000bb59  xor     rax, rsp
0x18000bb5c  mov     [rbp+160h+var_10], rax
0x18000bb63  mov     rdi, r8
0x18000bb66  mov     qword ptr [r8], 0
0x18000bb6d  mov     r8, rcx; unsigned __int16 *
0x18000bb70  mov     edx, 104h; unsigned __int64
0x18000bb75  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000bb7a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000bb7f  lea     r8, aP0; "_p0"
0x18000bb86  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000bb8b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bb90  lea     r8, [rsp+260h+Name]; lpName
0x18000bb95  xor     edx, edx; bInheritHandle
0x18000bb97  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bb9c  call    cs:__imp_OpenSemaphoreW
0x18000bba2  mov     [rsp+260h+var_230], rax
0x18000bba7  test    rax, rax
0x18000bbaa  jnz     short loc_18000BBDA
0x18000bbac  call    cs:__imp_GetLastError
0x18000bbb2  cmp     eax, 2
0x18000bbb5  jz      loc_18000BCBE
0x18000bbbb  mov     rcx, [rbp+168h]; this
0x18000bbc2  lea     r8, aWil; "wil"
0x18000bbc9  mov     edx, 0D0h; void *
0x18000bbce  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bbd3  mov     ebx, eax
0x18000bbd5  jmp     loc_18000BCC0
0x18000bbda  lea     rdx, [rsp+260h+var_23C]; int *
0x18000bbdf  mov     [rsp+260h+var_23C], 0
0x18000bbe7  mov     rcx, rax; hHandle
0x18000bbea  mov     [rsp+260h+var_240], 0; int
0x18000bbf2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bbf7  mov     ebx, eax
0x18000bbf9  test    eax, eax
0x18000bbfb  jns     short loc_18000BC1D
0x18000bbfd  mov     rcx, [rbp+168h]; this
0x18000bc04  lea     r8, aWil; "wil"
0x18000bc0b  mov     r9d, eax; char *
0x18000bc0e  mov     edx, 0D6h; void *
0x18000bc13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc18  jmp     loc_18000BCC0
0x18000bc1d  lea     r8, asc_1800149C0; "h"
0x18000bc24  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000bc29  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000bc2e  lea     r8, [rsp+260h+Name]; lpName
0x18000bc33  xor     edx, edx; bInheritHandle
0x18000bc35  mov     ecx, 1F0003h; dwDesiredAccess
0x18000bc3a  call    cs:__imp_OpenSemaphoreW
0x18000bc40  mov     [rsp+260h+var_238], rax
0x18000bc45  test    rax, rax
0x18000bc48  jnz     short loc_18000BC70
0x18000bc4a  mov     rcx, [rbp+168h]; this
0x18000bc51  lea     r8, aWil; "wil"
0x18000bc58  mov     edx, 0DCh; void *
0x18000bc5d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000bc62  mov     ebx, eax
0x18000bc64  lea     rcx, [rsp+260h+var_238]
0x18000bc69  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bc6e  jmp     short loc_18000BCC0
0x18000bc70  lea     rdx, [rsp+260h+var_240]; int *
0x18000bc75  mov     rcx, rax; hHandle
0x18000bc78  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000bc7d  mov     ebx, eax
0x18000bc7f  test    eax, eax
0x18000bc81  jns     short loc_18000BCA0
0x18000bc83  mov     rcx, [rbp+168h]; this
0x18000bc8a  lea     r8, aWil; "wil"
0x18000bc91  mov     r9d, eax; char *
0x18000bc94  mov     edx, 0DEh; void *
0x18000bc99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bc9e  jmp     short loc_18000BC64
0x18000bca0  lea     rcx, [rsp+260h+var_238]
0x18000bca5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bcaa  movsxd  rcx, [rsp+260h+var_240]
0x18000bcaf  movsxd  rax, [rsp+260h+var_23C]
0x18000bcb4  shl     rcx, 1Fh
0x18000bcb8  or      rcx, rax
0x18000bcbb  mov     [rdi], rcx
0x18000bcbe  xor     ebx, ebx
0x18000bcc0  lea     rcx, [rsp+260h+var_230]
0x18000bcc5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000bcca  mov     eax, ebx
0x18000bccc  mov     rcx, [rbp+160h+var_10]
0x18000bcd3  xor     rcx, rsp; StackCookie
0x18000bcd6  call    __security_check_cookie
0x18000bcdb  lea     r11, [rsp+260h+var_s0]
0x18000bce3  mov     rbx, [r11+18h]
0x18000bce7  mov     rdi, [r11+28h]
0x18000bceb  mov     rsp, r11
0x18000bcee  pop     rbp
0x18000bcef  retn
```
