# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180025918`
- end: `0x180025aca`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `434`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800258a4`

## callees

- `0x18000b940`
- `0x18000b9cc`
- `0x180022918`
- `0x180023a68`
- `0x180025234`
- `0x180025254`
- `0x180025918`
- `0x180039740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025981`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025a16`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025981`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180025a16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025991`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  void *v19; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v23; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v24; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v24 = v5;
  if ( v5 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore, v21);
      goto LABEL_12;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v23 = v12;
    if ( !v12 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v23,
        v15);
      goto LABEL_12;
    }
    v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v21);
    LastError = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v18, (const char *)(unsigned int)v16, v21);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v23,
        v19);
      goto LABEL_12;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v23,
      v17);
    *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  if ( GetLastError() == 2 )
    goto LABEL_11;
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v24,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x180025918  mov     [rsp-8+arg_8], rbx
0x18002591d  push    rbp
0x18002591e  push    rdi
0x18002591f  push    r14
0x180025921  lea     rbp, [rsp-160h]
0x180025929  sub     rsp, 260h
0x180025930  mov     rax, cs:__security_cookie
0x180025937  xor     rax, rsp
0x18002593a  mov     [rbp+170h+var_20], rax
0x180025941  mov     rdi, r8
0x180025944  mov     qword ptr [r8], 0
0x18002594b  mov     r8, rcx; unsigned __int16 *
0x18002594e  mov     r14d, 104h
0x180025954  mov     edx, r14d; unsigned __int64
0x180025957  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002595c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180025961  lea     r8, aP0; "_p0"
0x180025968  mov     edx, r14d; unsigned __int64
0x18002596b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025970  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025975  lea     r8, [rsp+270h+Name]; lpName
0x18002597a  xor     edx, edx; bInheritHandle
0x18002597c  mov     ecx, 1F0003h; dwDesiredAccess
0x180025981  call    cs:__imp_OpenSemaphoreW
0x180025987  mov     [rsp+270h+var_240], rax
0x18002598c  test    rax, rax
0x18002598f  jnz     short loc_1800259B9
0x180025991  call    cs:__imp_GetLastError
0x180025997  cmp     eax, 2
0x18002599a  jnz     short loc_1800259A1
0x18002599c  jmp     loc_180025A99
0x1800259a1  mov     rcx, [rbp+178h]; this
0x1800259a8  mov     edx, 0D0h; void *
0x1800259ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800259b2  mov     ebx, eax
0x1800259b4  jmp     loc_180025A9B
0x1800259b9  mov     [rsp+270h+var_24C], 0
0x1800259c1  mov     [rsp+270h+var_250], 0; int
0x1800259c9  lea     rdx, [rsp+270h+var_24C]; int *
0x1800259ce  mov     rcx, rax; hHandle
0x1800259d1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800259d6  mov     ebx, eax
0x1800259d8  test    eax, eax
0x1800259da  jns     short loc_1800259F6
0x1800259dc  mov     rcx, [rbp+178h]; this
0x1800259e3  mov     r9d, eax; char *
0x1800259e6  mov     edx, 0D6h; void *
0x1800259eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800259f0  nop
0x1800259f1  jmp     loc_180025A9B
0x1800259f6  lea     r8, asc_180054128; "h"
0x1800259fd  mov     rdx, r14; unsigned __int64
0x180025a00  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180025a05  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180025a0a  lea     r8, [rsp+270h+Name]; lpName
0x180025a0f  xor     edx, edx; bInheritHandle
0x180025a11  mov     ecx, 1F0003h; dwDesiredAccess
0x180025a16  call    cs:__imp_OpenSemaphoreW
0x180025a1c  mov     [rsp+270h+var_248], rax
0x180025a21  test    rax, rax
0x180025a24  jnz     short loc_180025A46
0x180025a26  mov     rcx, [rbp+178h]; this
0x180025a2d  mov     edx, 0DCh; void *
0x180025a32  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025a37  mov     ebx, eax
0x180025a39  lea     rcx, [rsp+270h+var_248]
0x180025a3e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025a43  nop
0x180025a44  jmp     short loc_180025A9B
0x180025a46  lea     rdx, [rsp+270h+var_250]; int *
0x180025a4b  mov     rcx, rax; hHandle
0x180025a4e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180025a53  mov     ebx, eax
0x180025a55  test    eax, eax
0x180025a57  jns     short loc_180025A7B
0x180025a59  mov     rcx, [rbp+178h]; this
0x180025a60  mov     r9d, eax; char *
0x180025a63  mov     edx, 0DEh; void *
0x180025a68  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025a6d  nop
0x180025a6e  lea     rcx, [rsp+270h+var_248]
0x180025a73  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025a78  nop
0x180025a79  jmp     short loc_180025A9B
0x180025a7b  lea     rcx, [rsp+270h+var_248]
0x180025a80  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025a85  movsxd  rcx, [rsp+270h+var_250]
0x180025a8a  shl     rcx, 1Fh
0x180025a8e  movsxd  rax, [rsp+270h+var_24C]
0x180025a93  or      rcx, rax
0x180025a96  mov     [rdi], rcx
0x180025a99  xor     ebx, ebx
0x180025a9b  lea     rcx, [rsp+270h+var_240]
0x180025aa0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180025aa5  mov     eax, ebx
0x180025aa7  mov     rcx, [rbp+170h+var_20]
0x180025aae  xor     rcx, rsp; StackCookie
0x180025ab1  call    __security_check_cookie
0x180025ab6  mov     rbx, [rsp+270h+arg_8]
0x180025abe  add     rsp, 260h
0x180025ac5  pop     r14
0x180025ac7  pop     rdi
0x180025ac8  pop     rbp
0x180025ac9  retn
```
