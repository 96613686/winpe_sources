# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000e11c`
- end: `0x18000e2e4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `456`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000e0ac`

## callees

- `0x180006734`
- `0x180009ed0`
- `0x18000c874`
- `0x18000c894`
- `0x18000cf54`
- `0x18000cff0`
- `0x18000e11c`
- `0x1800a0fb0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18000e188`
- `KERNEL32!OpenSemaphoreW` at `0x18000e224`
- `KERNEL32!OpenSemaphoreW` at `0x18000e188`
- `KERNEL32!OpenSemaphoreW` at `0x18000e224`
- `KERNEL32!GetLastError` at `0x18000e19e`
- `KERNEL32!GetLastError` at `0x18000e19e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  int v11; // edi
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  unsigned int v16; // r8d
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v20; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  LastError = 0;
  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21[0] = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
    v11 = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v20 = v12;
      if ( !v12 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v13, v14);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
        goto LABEL_12;
      }
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
      v11 = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
        *a3 = ((__int64)v18 << 31) | v19;
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v16, (const char *)(unsigned int)v15, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v10, (const char *)(unsigned int)ValueFromSemaphore, v18);
    }
    LastError = v11;
  }
  else if ( GetLastError() != 2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v7, v8);
  }
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
  return LastError;
}

```

## disassembly

```asm
0x18000e11c  mov     [rsp-8+arg_0], rbx
0x18000e121  mov     [rsp-8+arg_8], rsi
0x18000e126  push    rbp
0x18000e127  push    rdi
0x18000e128  push    r14
0x18000e12a  lea     rbp, [rsp-160h]
0x18000e132  sub     rsp, 260h
0x18000e139  mov     rax, cs:__security_cookie
0x18000e140  xor     rax, rsp
0x18000e143  mov     [rbp+170h+var_20], rax
0x18000e14a  mov     rsi, r8
0x18000e14d  xor     ebx, ebx
0x18000e14f  mov     [r8], rbx
0x18000e152  mov     r8, rcx; unsigned __int16 *
0x18000e155  mov     r14d, 104h
0x18000e15b  mov     edx, r14d; unsigned __int64
0x18000e15e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e163  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e168  lea     r8, aP0; "_p0"
0x18000e16f  mov     edx, r14d; unsigned __int64
0x18000e172  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e177  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e17c  lea     r8, [rsp+270h+Name]; lpName
0x18000e181  xor     edx, edx; bInheritHandle
0x18000e183  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e188  call    cs:__imp_OpenSemaphoreW
0x18000e18f  nop     dword ptr [rax+rax+00h]
0x18000e194  mov     [rsp+270h+var_240], rax
0x18000e199  test    rax, rax
0x18000e19c  jnz     short loc_18000E1CD
0x18000e19e  call    cs:__imp_GetLastError
0x18000e1a5  nop     dword ptr [rax+rax+00h]
0x18000e1aa  cmp     eax, 2
0x18000e1ad  jnz     short loc_18000E1B4
0x18000e1af  jmp     loc_18000E2B0
0x18000e1b4  mov     rcx, [rbp+178h]; this
0x18000e1bb  mov     edx, 0CDh; void *
0x18000e1c0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e1c5  nop
0x18000e1c6  mov     ebx, eax
0x18000e1c8  jmp     loc_18000E2B0
0x18000e1cd  mov     [rsp+270h+var_24C], ebx
0x18000e1d1  mov     [rsp+270h+var_250], ebx; int
0x18000e1d5  lea     rdx, [rsp+270h+var_24C]; int *
0x18000e1da  mov     rcx, rax; hHandle
0x18000e1dd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e1e2  mov     edi, eax
0x18000e1e4  test    eax, eax
0x18000e1e6  jns     short loc_18000E204
0x18000e1e8  mov     rcx, [rbp+178h]; this
0x18000e1ef  mov     r9d, eax; char *
0x18000e1f2  mov     edx, 0D3h; void *
0x18000e1f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e1fc  nop
0x18000e1fd  mov     ebx, edi
0x18000e1ff  jmp     loc_18000E2B0
0x18000e204  lea     r8, asc_1800B67F8; "h"
0x18000e20b  mov     rdx, r14; unsigned __int64
0x18000e20e  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000e213  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e218  lea     r8, [rsp+270h+Name]; lpName
0x18000e21d  xor     edx, edx; bInheritHandle
0x18000e21f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000e224  call    cs:__imp_OpenSemaphoreW
0x18000e22b  nop     dword ptr [rax+rax+00h]
0x18000e230  mov     [rsp+270h+var_248], rax
0x18000e235  test    rax, rax
0x18000e238  jnz     short loc_18000E25A
0x18000e23a  mov     rcx, [rbp+178h]; this
0x18000e241  mov     edx, 0D9h; void *
0x18000e246  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000e24b  mov     ebx, eax
0x18000e24d  lea     rcx, [rsp+270h+var_248]
0x18000e252  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e257  nop
0x18000e258  jmp     short loc_18000E2B0
0x18000e25a  lea     rdx, [rsp+270h+var_250]; int *
0x18000e25f  mov     rcx, rax; hHandle
0x18000e262  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000e267  mov     edi, eax
0x18000e269  test    eax, eax
0x18000e26b  jns     short loc_18000E292
0x18000e26d  mov     rcx, [rbp+178h]; this
0x18000e274  mov     r9d, eax; char *
0x18000e277  mov     edx, 0DBh; void *
0x18000e27c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e281  nop
0x18000e282  lea     rcx, [rsp+270h+var_248]
0x18000e287  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e28c  nop
0x18000e28d  jmp     loc_18000E1FD
0x18000e292  lea     rcx, [rsp+270h+var_248]
0x18000e297  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e29c  movsxd  rdx, [rsp+270h+var_250]
0x18000e2a1  shl     rdx, 1Fh
0x18000e2a5  movsxd  rcx, [rsp+270h+var_24C]
0x18000e2aa  or      rcx, rdx
0x18000e2ad  mov     [rsi], rcx
0x18000e2b0  lea     rcx, [rsp+270h+var_240]
0x18000e2b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000e2ba  mov     eax, ebx
0x18000e2bc  mov     rcx, [rbp+170h+var_20]
0x18000e2c3  xor     rcx, rsp; StackCookie
0x18000e2c6  call    __security_check_cookie
0x18000e2cb  lea     r11, [rsp+270h+var_10]
0x18000e2d3  mov     rbx, [r11+20h]
0x18000e2d7  mov     rsi, [r11+28h]
0x18000e2db  mov     rsp, r11
0x18000e2de  pop     r14
0x18000e2e0  pop     rdi
0x18000e2e1  pop     rbp
0x18000e2e2  retn
```
