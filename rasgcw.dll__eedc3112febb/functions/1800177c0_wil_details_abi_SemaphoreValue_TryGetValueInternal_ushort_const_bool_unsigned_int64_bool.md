# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800177c0`
- end: `0x18001795c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180014978`

## callees

- `0x180010c38`
- `0x180014774`
- `0x1800156f0`
- `0x180016bb4`
- `0x180016bd4`
- `0x18001763c`
- `0x1800177c0`
- `0x18002f3b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017824`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800178b4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017824`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800178b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017834`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
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
0x1800177c0  mov     [rsp-8+arg_8], rbx
0x1800177c5  mov     [rsp-8+arg_18], rdi
0x1800177ca  push    rbp
0x1800177cb  lea     rbp, [rsp-160h]
0x1800177d3  sub     rsp, 260h
0x1800177da  mov     rax, cs:__security_cookie
0x1800177e1  xor     rax, rsp
0x1800177e4  mov     [rbp+160h+var_10], rax
0x1800177eb  mov     rdi, r8
0x1800177ee  mov     qword ptr [r8], 0
0x1800177f5  mov     r8, rcx; unsigned __int16 *
0x1800177f8  mov     edx, 104h; unsigned __int64
0x1800177fd  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180017802  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017807  lea     r8, aP0; "_p0"
0x18001780e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180017813  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017818  lea     r8, [rsp+260h+Name]; lpName
0x18001781d  xor     edx, edx; bInheritHandle
0x18001781f  mov     ecx, 1F0003h; dwDesiredAccess
0x180017824  call    cs:__imp_OpenSemaphoreW
0x18001782a  mov     [rsp+260h+var_230], rax
0x18001782f  test    rax, rax
0x180017832  jnz     short loc_18001785B
0x180017834  call    cs:__imp_GetLastError
0x18001783a  cmp     eax, 2
0x18001783d  jz      loc_18001792A
0x180017843  mov     rcx, [rbp+168h]; this
0x18001784a  mov     edx, 0D0h; void *
0x18001784f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017854  mov     ebx, eax
0x180017856  jmp     loc_18001792C
0x18001785b  lea     rdx, [rsp+260h+var_23C]; int *
0x180017860  mov     [rsp+260h+var_23C], 0
0x180017868  mov     rcx, rax; hHandle
0x18001786b  mov     [rsp+260h+var_240], 0; int
0x180017873  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180017878  mov     ebx, eax
0x18001787a  test    eax, eax
0x18001787c  jns     short loc_180017897
0x18001787e  mov     rcx, [rbp+168h]; this
0x180017885  mov     r9d, eax; char *
0x180017888  mov     edx, 0D6h; void *
0x18001788d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017892  jmp     loc_18001792C
0x180017897  lea     r8, asc_1800381A0; "h"
0x18001789e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800178a3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800178a8  lea     r8, [rsp+260h+Name]; lpName
0x1800178ad  xor     edx, edx; bInheritHandle
0x1800178af  mov     ecx, 1F0003h; dwDesiredAccess
0x1800178b4  call    cs:__imp_OpenSemaphoreW
0x1800178ba  mov     [rsp+260h+var_238], rax
0x1800178bf  test    rax, rax
0x1800178c2  jnz     short loc_1800178E3
0x1800178c4  mov     rcx, [rbp+168h]; this
0x1800178cb  mov     edx, 0DCh; void *
0x1800178d0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800178d5  mov     ebx, eax
0x1800178d7  lea     rcx, [rsp+260h+var_238]
0x1800178dc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800178e1  jmp     short loc_18001792C
0x1800178e3  lea     rdx, [rsp+260h+var_240]; int *
0x1800178e8  mov     rcx, rax; hHandle
0x1800178eb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800178f0  mov     ebx, eax
0x1800178f2  test    eax, eax
0x1800178f4  jns     short loc_18001790C
0x1800178f6  mov     rcx, [rbp+168h]; this
0x1800178fd  mov     r9d, eax; char *
0x180017900  mov     edx, 0DEh; void *
0x180017905  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001790a  jmp     short loc_1800178D7
0x18001790c  lea     rcx, [rsp+260h+var_238]
0x180017911  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017916  movsxd  rcx, [rsp+260h+var_240]
0x18001791b  movsxd  rax, [rsp+260h+var_23C]
0x180017920  shl     rcx, 1Fh
0x180017924  or      rcx, rax
0x180017927  mov     [rdi], rcx
0x18001792a  xor     ebx, ebx
0x18001792c  lea     rcx, [rsp+260h+var_230]
0x180017931  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017936  mov     eax, ebx
0x180017938  mov     rcx, [rbp+160h+var_10]
0x18001793f  xor     rcx, rsp; StackCookie
0x180017942  call    __security_check_cookie
0x180017947  lea     r11, [rsp+260h+var_s0]
0x18001794f  mov     rbx, [r11+18h]
0x180017953  mov     rdi, [r11+28h]
0x180017957  mov     rsp, r11
0x18001795a  pop     rbp
0x18001795b  retn
```
