# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008ea8`
- end: `0x18000904a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006ea8`

## callees

- `0x180001e70`
- `0x180006dc4`
- `0x180007a8c`
- `0x180008774`
- `0x180008794`
- `0x180008c6c`
- `0x180008cf8`
- `0x180008ea8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008f11`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008fa3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008f11`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008fa3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f21`

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
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v11; // r8d
  wil::details *v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  void *v15; // rdx
  int v16; // eax
  void *v17; // rdx
  unsigned int v18; // r8d
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v22; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v23; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v23 = v5;
  if ( v5 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v22 = v12;
    if ( v12 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v20);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v17);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v18, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v15);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v23,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x180008ea8  mov     [rsp-8+arg_8], rbx
0x180008ead  push    rbp
0x180008eae  push    rdi
0x180008eaf  push    r14
0x180008eb1  lea     rbp, [rsp-160h]
0x180008eb9  sub     rsp, 260h
0x180008ec0  mov     rax, cs:__security_cookie
0x180008ec7  xor     rax, rsp
0x180008eca  mov     [rbp+170h+var_20], rax
0x180008ed1  mov     rdi, r8
0x180008ed4  mov     qword ptr [r8], 0
0x180008edb  mov     r8, rcx; unsigned __int16 *
0x180008ede  mov     r14d, 104h
0x180008ee4  mov     edx, r14d; unsigned __int64
0x180008ee7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008eec  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008ef1  lea     r8, aP0; "_p0"
0x180008ef8  mov     edx, r14d; unsigned __int64
0x180008efb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008f00  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008f05  lea     r8, [rsp+270h+Name]; lpName
0x180008f0a  xor     edx, edx; bInheritHandle
0x180008f0c  mov     ecx, 1F0003h; dwDesiredAccess
0x180008f11  call    cs:__imp_OpenSemaphoreW
0x180008f17  mov     [rsp+270h+var_240], rax
0x180008f1c  test    rax, rax
0x180008f1f  jnz     short loc_180008F47
0x180008f21  call    cs:__imp_GetLastError
0x180008f27  cmp     eax, 2
0x180008f2a  jz      loc_180009019
0x180008f30  mov     rcx, [rbp+178h]; this
0x180008f37  lea     edx, [r14-34h]; void *
0x180008f3b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008f40  mov     ebx, eax
0x180008f42  jmp     loc_18000901B
0x180008f47  mov     [rsp+270h+var_24C], 0
0x180008f4f  mov     [rsp+270h+var_250], 0; int
0x180008f57  lea     rdx, [rsp+270h+var_24C]; int *
0x180008f5c  mov     rcx, rax; hHandle
0x180008f5f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008f64  mov     ebx, eax
0x180008f66  test    eax, eax
0x180008f68  jns     short loc_180008F83
0x180008f6a  mov     rcx, [rbp+178h]; this
0x180008f71  mov     r9d, eax; char *
0x180008f74  mov     edx, 0D6h; void *
0x180008f79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f7e  jmp     loc_18000901B
0x180008f83  lea     r8, asc_1800176A0; "h"
0x180008f8a  mov     rdx, r14; unsigned __int64
0x180008f8d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008f92  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008f97  lea     r8, [rsp+270h+Name]; lpName
0x180008f9c  xor     edx, edx; bInheritHandle
0x180008f9e  mov     ecx, 1F0003h; dwDesiredAccess
0x180008fa3  call    cs:__imp_OpenSemaphoreW
0x180008fa9  mov     [rsp+270h+var_248], rax
0x180008fae  test    rax, rax
0x180008fb1  jnz     short loc_180008FD2
0x180008fb3  mov     rcx, [rbp+178h]; this
0x180008fba  mov     edx, 0DCh; void *
0x180008fbf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008fc4  mov     ebx, eax
0x180008fc6  lea     rcx, [rsp+270h+var_248]
0x180008fcb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008fd0  jmp     short loc_18000901B
0x180008fd2  lea     rdx, [rsp+270h+var_250]; int *
0x180008fd7  mov     rcx, rax; hHandle
0x180008fda  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008fdf  mov     ebx, eax
0x180008fe1  test    eax, eax
0x180008fe3  jns     short loc_180008FFB
0x180008fe5  mov     rcx, [rbp+178h]; this
0x180008fec  mov     r9d, eax; char *
0x180008fef  mov     edx, 0DEh; void *
0x180008ff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008ff9  jmp     short loc_180008FC6
0x180008ffb  lea     rcx, [rsp+270h+var_248]
0x180009000  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009005  movsxd  rcx, [rsp+270h+var_250]
0x18000900a  shl     rcx, 1Fh
0x18000900e  movsxd  rax, [rsp+270h+var_24C]
0x180009013  or      rcx, rax
0x180009016  mov     [rdi], rcx
0x180009019  xor     ebx, ebx
0x18000901b  lea     rcx, [rsp+270h+var_240]
0x180009020  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009025  mov     eax, ebx
0x180009027  mov     rcx, [rbp+170h+var_20]
0x18000902e  xor     rcx, rsp; StackCookie
0x180009031  call    __security_check_cookie
0x180009036  mov     rbx, [rsp+270h+arg_8]
0x18000903e  add     rsp, 260h
0x180009045  pop     r14
0x180009047  pop     rdi
0x180009048  pop     rbp
0x180009049  retn
```
