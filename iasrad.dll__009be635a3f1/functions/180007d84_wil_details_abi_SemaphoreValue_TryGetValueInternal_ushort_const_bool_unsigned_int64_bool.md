# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007d84`
- end: `0x180007f20`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007d10`

## callees

- `0x1800033dc`
- `0x180004944`
- `0x180006f9c`
- `0x180006fbc`
- `0x180007744`
- `0x1800077c0`
- `0x180007d84`
- `0x18002e230`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007df8`
- `KERNEL32!GetLastError` at `0x180007df8`
- `KERNEL32!OpenSemaphoreW` at `0x180007de8`
- `KERNEL32!OpenSemaphoreW` at `0x180007e78`
- `KERNEL32!OpenSemaphoreW` at `0x180007de8`
- `KERNEL32!OpenSemaphoreW` at `0x180007e78`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
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
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x180007d84  mov     [rsp-8+arg_8], rbx
0x180007d89  mov     [rsp-8+arg_18], rdi
0x180007d8e  push    rbp
0x180007d8f  lea     rbp, [rsp-160h]
0x180007d97  sub     rsp, 260h
0x180007d9e  mov     rax, cs:__security_cookie
0x180007da5  xor     rax, rsp
0x180007da8  mov     [rbp+160h+var_10], rax
0x180007daf  mov     rdi, r8
0x180007db2  mov     qword ptr [r8], 0
0x180007db9  mov     r8, rcx; unsigned __int16 *
0x180007dbc  mov     edx, 104h; unsigned __int64
0x180007dc1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007dc6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007dcb  lea     r8, aP0; "_p0"
0x180007dd2  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007dd7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007ddc  lea     r8, [rsp+260h+Name]; lpName
0x180007de1  xor     edx, edx; bInheritHandle
0x180007de3  mov     ecx, 1F0003h; dwDesiredAccess
0x180007de8  call    cs:__imp_OpenSemaphoreW
0x180007dee  mov     [rsp+260h+var_230], rax
0x180007df3  test    rax, rax
0x180007df6  jnz     short loc_180007E1F
0x180007df8  call    cs:__imp_GetLastError
0x180007dfe  cmp     eax, 2
0x180007e01  jz      loc_180007EEE
0x180007e07  mov     rcx, [rbp+168h]; this
0x180007e0e  mov     edx, 0D0h; void *
0x180007e13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007e18  mov     ebx, eax
0x180007e1a  jmp     loc_180007EF0
0x180007e1f  lea     rdx, [rsp+260h+var_23C]; int *
0x180007e24  mov     [rsp+260h+var_23C], 0
0x180007e2c  mov     rcx, rax; hHandle
0x180007e2f  mov     [rsp+260h+var_240], 0; int
0x180007e37  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007e3c  mov     ebx, eax
0x180007e3e  test    eax, eax
0x180007e40  jns     short loc_180007E5B
0x180007e42  mov     rcx, [rbp+168h]; this
0x180007e49  mov     r9d, eax; char *
0x180007e4c  mov     edx, 0D6h; void *
0x180007e51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e56  jmp     loc_180007EF0
0x180007e5b  lea     r8, asc_180034208; "h"
0x180007e62  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007e67  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007e6c  lea     r8, [rsp+260h+Name]; lpName
0x180007e71  xor     edx, edx; bInheritHandle
0x180007e73  mov     ecx, 1F0003h; dwDesiredAccess
0x180007e78  call    cs:__imp_OpenSemaphoreW
0x180007e7e  mov     [rsp+260h+var_238], rax
0x180007e83  test    rax, rax
0x180007e86  jnz     short loc_180007EA7
0x180007e88  mov     rcx, [rbp+168h]; this
0x180007e8f  mov     edx, 0DCh; void *
0x180007e94  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007e99  mov     ebx, eax
0x180007e9b  lea     rcx, [rsp+260h+var_238]
0x180007ea0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007ea5  jmp     short loc_180007EF0
0x180007ea7  lea     rdx, [rsp+260h+var_240]; int *
0x180007eac  mov     rcx, rax; hHandle
0x180007eaf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007eb4  mov     ebx, eax
0x180007eb6  test    eax, eax
0x180007eb8  jns     short loc_180007ED0
0x180007eba  mov     rcx, [rbp+168h]; this
0x180007ec1  mov     r9d, eax; char *
0x180007ec4  mov     edx, 0DEh; void *
0x180007ec9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ece  jmp     short loc_180007E9B
0x180007ed0  lea     rcx, [rsp+260h+var_238]
0x180007ed5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007eda  movsxd  rcx, [rsp+260h+var_240]
0x180007edf  movsxd  rax, [rsp+260h+var_23C]
0x180007ee4  shl     rcx, 1Fh
0x180007ee8  or      rcx, rax
0x180007eeb  mov     [rdi], rcx
0x180007eee  xor     ebx, ebx
0x180007ef0  lea     rcx, [rsp+260h+var_230]
0x180007ef5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007efa  mov     eax, ebx
0x180007efc  mov     rcx, [rbp+160h+var_10]
0x180007f03  xor     rcx, rsp; StackCookie
0x180007f06  call    __security_check_cookie
0x180007f0b  lea     r11, [rsp+260h+var_s0]
0x180007f13  mov     rbx, [r11+18h]
0x180007f17  mov     rdi, [r11+28h]
0x180007f1b  mov     rsp, r11
0x180007f1e  pop     rbp
0x180007f1f  retn
```
