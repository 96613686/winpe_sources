# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002d2b4`
- end: `0x18002d47f`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003f8ac`

## callees

- `0x18001a9d0`
- `0x180024540`
- `0x18002d2b4`
- `0x18002d488`
- `0x18002df48`
- `0x180030ad0`
- `0x18003bc70`
- `0x18003ec18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002d318`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002d3c2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002d318`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002d3c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d32e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d32e`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18002d2b4  mov     [rsp-8+arg_8], rbx
0x18002d2b9  mov     [rsp-8+arg_18], rdi
0x18002d2be  push    rbp
0x18002d2bf  lea     rbp, [rsp-160h]
0x18002d2c7  sub     rsp, 260h
0x18002d2ce  mov     rax, cs:__security_cookie
0x18002d2d5  xor     rax, rsp
0x18002d2d8  mov     [rbp+160h+var_10], rax
0x18002d2df  mov     rdi, r8
0x18002d2e2  mov     qword ptr [r8], 0
0x18002d2e9  mov     r8, rcx; unsigned __int16 *
0x18002d2ec  mov     edx, 104h; unsigned __int64
0x18002d2f1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002d2f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d2fb  lea     r8, aP0; "_p0"
0x18002d302  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002d307  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d30c  lea     r8, [rsp+260h+Name]; lpName
0x18002d311  xor     edx, edx; bInheritHandle
0x18002d313  mov     ecx, 1F0003h; dwDesiredAccess
0x18002d318  call    cs:__imp_OpenSemaphoreW
0x18002d31f  nop     dword ptr [rax+rax+00h]
0x18002d324  mov     [rsp+260h+var_230], rax
0x18002d329  test    rax, rax
0x18002d32c  jnz     short loc_18002D362
0x18002d32e  call    cs:__imp_GetLastError
0x18002d335  nop     dword ptr [rax+rax+00h]
0x18002d33a  cmp     eax, 2
0x18002d33d  jz      loc_18002D44C
0x18002d343  mov     rcx, [rbp+168h]; this
0x18002d34a  lea     r8, aWil; "wil"
0x18002d351  mov     edx, 0D0h; void *
0x18002d356  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d35b  mov     ebx, eax
0x18002d35d  jmp     loc_18002D44E
0x18002d362  lea     rdx, [rsp+260h+var_23C]; int *
0x18002d367  mov     [rsp+260h+var_23C], 0
0x18002d36f  mov     rcx, rax; hHandle
0x18002d372  mov     [rsp+260h+var_240], 0; int
0x18002d37a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002d37f  mov     ebx, eax
0x18002d381  test    eax, eax
0x18002d383  jns     short loc_18002D3A5
0x18002d385  mov     rcx, [rbp+168h]; this
0x18002d38c  lea     r8, aWil; "wil"
0x18002d393  mov     r9d, eax; char *
0x18002d396  mov     edx, 0D6h; void *
0x18002d39b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d3a0  jmp     loc_18002D44E
0x18002d3a5  lea     r8, asc_1800646B0; "h"
0x18002d3ac  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18002d3b1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002d3b6  lea     r8, [rsp+260h+Name]; lpName
0x18002d3bb  xor     edx, edx; bInheritHandle
0x18002d3bd  mov     ecx, 1F0003h; dwDesiredAccess
0x18002d3c2  call    cs:__imp_OpenSemaphoreW
0x18002d3c9  nop     dword ptr [rax+rax+00h]
0x18002d3ce  mov     [rsp+260h+var_238], rax
0x18002d3d3  test    rax, rax
0x18002d3d6  jnz     short loc_18002D3FE
0x18002d3d8  mov     rcx, [rbp+168h]; this
0x18002d3df  lea     r8, aWil; "wil"
0x18002d3e6  mov     edx, 0DCh; void *
0x18002d3eb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002d3f0  mov     ebx, eax
0x18002d3f2  lea     rcx, [rsp+260h+var_238]
0x18002d3f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002d3fc  jmp     short loc_18002D44E
0x18002d3fe  lea     rdx, [rsp+260h+var_240]; int *
0x18002d403  mov     rcx, rax; hHandle
0x18002d406  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002d40b  mov     ebx, eax
0x18002d40d  test    eax, eax
0x18002d40f  jns     short loc_18002D42E
0x18002d411  mov     rcx, [rbp+168h]; this
0x18002d418  lea     r8, aWil; "wil"
0x18002d41f  mov     r9d, eax; char *
0x18002d422  mov     edx, 0DEh; void *
0x18002d427  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d42c  jmp     short loc_18002D3F2
0x18002d42e  lea     rcx, [rsp+260h+var_238]
0x18002d433  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002d438  movsxd  rcx, [rsp+260h+var_240]
0x18002d43d  movsxd  rax, [rsp+260h+var_23C]
0x18002d442  shl     rcx, 1Fh
0x18002d446  or      rcx, rax
0x18002d449  mov     [rdi], rcx
0x18002d44c  xor     ebx, ebx
0x18002d44e  lea     rcx, [rsp+260h+var_230]
0x18002d453  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002d458  mov     eax, ebx
0x18002d45a  mov     rcx, [rbp+160h+var_10]
0x18002d461  xor     rcx, rsp; StackCookie
0x18002d464  call    __security_check_cookie
0x18002d469  lea     r11, [rsp+260h+var_s0]
0x18002d471  mov     rbx, [r11+18h]
0x18002d475  mov     rdi, [r11+28h]
0x18002d479  mov     rsp, r11
0x18002d47c  pop     rbp
0x18002d47d  retn
```
