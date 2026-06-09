# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000e26c`
- end: `0x14000e408`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000e1f8`

## callees

- `0x140002070`
- `0x140009578`
- `0x14000b1f0`
- `0x14000d58c`
- `0x14000d5ac`
- `0x14000dc6c`
- `0x14000dce8`
- `0x14000e26c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000e2e0`
- `KERNEL32!GetLastError` at `0x14000e2e0`
- `KERNEL32!OpenSemaphoreW` at `0x14000e2d0`
- `KERNEL32!OpenSemaphoreW` at `0x14000e360`
- `KERNEL32!OpenSemaphoreW` at `0x14000e2d0`
- `KERNEL32!OpenSemaphoreW` at `0x14000e360`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
0x14000e26c  mov     [rsp-8+arg_8], rbx
0x14000e271  mov     [rsp-8+arg_18], rdi
0x14000e276  push    rbp
0x14000e277  lea     rbp, [rsp-160h]
0x14000e27f  sub     rsp, 260h
0x14000e286  mov     rax, cs:__security_cookie
0x14000e28d  xor     rax, rsp
0x14000e290  mov     [rbp+160h+var_10], rax
0x14000e297  mov     rdi, r8
0x14000e29a  mov     qword ptr [r8], 0
0x14000e2a1  mov     r8, rcx; wchar_t *
0x14000e2a4  mov     edx, 104h; unsigned __int64
0x14000e2a9  lea     rcx, [rsp+260h+Name]; wchar_t *
0x14000e2ae  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000e2b3  lea     r8, aP0; "_p0"
0x14000e2ba  lea     rcx, [rsp+260h+Name]; wchar_t *
0x14000e2bf  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000e2c4  lea     r8, [rsp+260h+Name]; lpName
0x14000e2c9  xor     edx, edx; bInheritHandle
0x14000e2cb  mov     ecx, 1F0003h; dwDesiredAccess
0x14000e2d0  call    cs:__imp_OpenSemaphoreW
0x14000e2d6  mov     [rsp+260h+var_230], rax
0x14000e2db  test    rax, rax
0x14000e2de  jnz     short loc_14000E307
0x14000e2e0  call    cs:__imp_GetLastError
0x14000e2e6  cmp     eax, 2
0x14000e2e9  jz      loc_14000E3D6
0x14000e2ef  mov     rcx, [rbp+168h]; this
0x14000e2f6  mov     edx, 0D0h; void *
0x14000e2fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e300  mov     ebx, eax
0x14000e302  jmp     loc_14000E3D8
0x14000e307  lea     rdx, [rsp+260h+var_23C]; int *
0x14000e30c  mov     [rsp+260h+var_23C], 0
0x14000e314  mov     rcx, rax; hHandle
0x14000e317  mov     [rsp+260h+var_240], 0; int
0x14000e31f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000e324  mov     ebx, eax
0x14000e326  test    eax, eax
0x14000e328  jns     short loc_14000E343
0x14000e32a  mov     rcx, [rbp+168h]; this
0x14000e331  mov     r9d, eax; char *
0x14000e334  mov     edx, 0D6h; void *
0x14000e339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e33e  jmp     loc_14000E3D8
0x14000e343  lea     r8, asc_140069CE0; "h"
0x14000e34a  lea     rcx, [rsp+260h+Name]; wchar_t *
0x14000e34f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x14000e354  lea     r8, [rsp+260h+Name]; lpName
0x14000e359  xor     edx, edx; bInheritHandle
0x14000e35b  mov     ecx, 1F0003h; dwDesiredAccess
0x14000e360  call    cs:__imp_OpenSemaphoreW
0x14000e366  mov     [rsp+260h+var_238], rax
0x14000e36b  test    rax, rax
0x14000e36e  jnz     short loc_14000E38F
0x14000e370  mov     rcx, [rbp+168h]; this
0x14000e377  mov     edx, 0DCh; void *
0x14000e37c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000e381  mov     ebx, eax
0x14000e383  lea     rcx, [rsp+260h+var_238]
0x14000e388  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e38d  jmp     short loc_14000E3D8
0x14000e38f  lea     rdx, [rsp+260h+var_240]; int *
0x14000e394  mov     rcx, rax; hHandle
0x14000e397  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000e39c  mov     ebx, eax
0x14000e39e  test    eax, eax
0x14000e3a0  jns     short loc_14000E3B8
0x14000e3a2  mov     rcx, [rbp+168h]; this
0x14000e3a9  mov     r9d, eax; char *
0x14000e3ac  mov     edx, 0DEh; void *
0x14000e3b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000e3b6  jmp     short loc_14000E383
0x14000e3b8  lea     rcx, [rsp+260h+var_238]
0x14000e3bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e3c2  movsxd  rcx, [rsp+260h+var_240]
0x14000e3c7  movsxd  rax, [rsp+260h+var_23C]
0x14000e3cc  shl     rcx, 1Fh
0x14000e3d0  or      rcx, rax
0x14000e3d3  mov     [rdi], rcx
0x14000e3d6  xor     ebx, ebx
0x14000e3d8  lea     rcx, [rsp+260h+var_230]
0x14000e3dd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000e3e2  mov     eax, ebx
0x14000e3e4  mov     rcx, [rbp+160h+var_10]
0x14000e3eb  xor     rcx, rsp; StackCookie
0x14000e3ee  call    __security_check_cookie
0x14000e3f3  lea     r11, [rsp+260h+var_s0]
0x14000e3fb  mov     rbx, [r11+18h]
0x14000e3ff  mov     rdi, [r11+28h]
0x14000e403  mov     rsp, r11
0x14000e406  pop     rbp
0x14000e407  retn
```
