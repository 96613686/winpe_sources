# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140004f44`
- end: `0x1400050e0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140002f70`

## callees

- `0x140002ef0`
- `0x140003cdc`
- `0x1400049b4`
- `0x1400049d4`
- `0x140004cec`
- `0x140004d68`
- `0x140004f44`
- `0x1400059b0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x140004fa8`
- `KERNEL32!OpenSemaphoreW` at `0x140005038`
- `KERNEL32!OpenSemaphoreW` at `0x140004fa8`
- `KERNEL32!OpenSemaphoreW` at `0x140005038`
- `KERNEL32!GetLastError` at `0x140004fb8`
- `KERNEL32!GetLastError` at `0x140004fb8`

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
0x140004f44  mov     [rsp-8+arg_8], rbx
0x140004f49  mov     [rsp-8+arg_18], rdi
0x140004f4e  push    rbp
0x140004f4f  lea     rbp, [rsp-160h]
0x140004f57  sub     rsp, 260h
0x140004f5e  mov     rax, cs:__security_cookie
0x140004f65  xor     rax, rsp
0x140004f68  mov     [rbp+160h+var_10], rax
0x140004f6f  mov     rdi, r8
0x140004f72  mov     qword ptr [r8], 0
0x140004f79  mov     r8, rcx; unsigned __int16 *
0x140004f7c  mov     edx, 104h; unsigned __int64
0x140004f81  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140004f86  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140004f8b  lea     r8, aP0; "_p0"
0x140004f92  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140004f97  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140004f9c  lea     r8, [rsp+260h+Name]; lpName
0x140004fa1  xor     edx, edx; bInheritHandle
0x140004fa3  mov     ecx, 1F0003h; dwDesiredAccess
0x140004fa8  call    cs:__imp_OpenSemaphoreW
0x140004fae  mov     [rsp+260h+var_230], rax
0x140004fb3  test    rax, rax
0x140004fb6  jnz     short loc_140004FDF
0x140004fb8  call    cs:__imp_GetLastError
0x140004fbe  cmp     eax, 2
0x140004fc1  jz      loc_1400050AE
0x140004fc7  mov     rcx, [rbp+168h]; this
0x140004fce  mov     edx, 0D0h; void *
0x140004fd3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140004fd8  mov     ebx, eax
0x140004fda  jmp     loc_1400050B0
0x140004fdf  lea     rdx, [rsp+260h+var_23C]; int *
0x140004fe4  mov     [rsp+260h+var_23C], 0
0x140004fec  mov     rcx, rax; hHandle
0x140004fef  mov     [rsp+260h+var_240], 0; int
0x140004ff7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140004ffc  mov     ebx, eax
0x140004ffe  test    eax, eax
0x140005000  jns     short loc_14000501B
0x140005002  mov     rcx, [rbp+168h]; this
0x140005009  mov     r9d, eax; char *
0x14000500c  mov     edx, 0D6h; void *
0x140005011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005016  jmp     loc_1400050B0
0x14000501b  lea     r8, asc_1400078E8; "h"
0x140005022  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x140005027  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000502c  lea     r8, [rsp+260h+Name]; lpName
0x140005031  xor     edx, edx; bInheritHandle
0x140005033  mov     ecx, 1F0003h; dwDesiredAccess
0x140005038  call    cs:__imp_OpenSemaphoreW
0x14000503e  mov     [rsp+260h+var_238], rax
0x140005043  test    rax, rax
0x140005046  jnz     short loc_140005067
0x140005048  mov     rcx, [rbp+168h]; this
0x14000504f  mov     edx, 0DCh; void *
0x140005054  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005059  mov     ebx, eax
0x14000505b  lea     rcx, [rsp+260h+var_238]
0x140005060  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005065  jmp     short loc_1400050B0
0x140005067  lea     rdx, [rsp+260h+var_240]; int *
0x14000506c  mov     rcx, rax; hHandle
0x14000506f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005074  mov     ebx, eax
0x140005076  test    eax, eax
0x140005078  jns     short loc_140005090
0x14000507a  mov     rcx, [rbp+168h]; this
0x140005081  mov     r9d, eax; char *
0x140005084  mov     edx, 0DEh; void *
0x140005089  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000508e  jmp     short loc_14000505B
0x140005090  lea     rcx, [rsp+260h+var_238]
0x140005095  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000509a  movsxd  rcx, [rsp+260h+var_240]
0x14000509f  movsxd  rax, [rsp+260h+var_23C]
0x1400050a4  shl     rcx, 1Fh
0x1400050a8  or      rcx, rax
0x1400050ab  mov     [rdi], rcx
0x1400050ae  xor     ebx, ebx
0x1400050b0  lea     rcx, [rsp+260h+var_230]
0x1400050b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400050ba  mov     eax, ebx
0x1400050bc  mov     rcx, [rbp+160h+var_10]
0x1400050c3  xor     rcx, rsp; StackCookie
0x1400050c6  call    __security_check_cookie
0x1400050cb  lea     r11, [rsp+260h+var_s0]
0x1400050d3  mov     rbx, [r11+18h]
0x1400050d7  mov     rdi, [r11+28h]
0x1400050db  mov     rsp, r11
0x1400050de  pop     rbp
0x1400050df  retn
```
