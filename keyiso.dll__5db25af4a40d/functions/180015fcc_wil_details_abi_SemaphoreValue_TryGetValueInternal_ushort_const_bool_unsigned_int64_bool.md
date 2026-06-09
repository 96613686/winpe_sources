# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180015fcc`
- end: `0x180016168`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015f58`

## callees

- `0x180012390`
- `0x1800138b4`
- `0x18001537c`
- `0x18001539c`
- `0x180015a5c`
- `0x180015b3c`
- `0x180015fcc`
- `0x180018950`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016040`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180016030`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800160c0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180016030`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800160c0`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  size_t v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v25; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v26; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v22);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v26 = v6;
  if ( v6 )
  {
    v24 = 0;
    v23 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v24);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v25 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v23);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v25,
          v19);
        *a3 = v24 | (unsigned __int64)((__int64)v23 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v25,
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
    &v26,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180015fcc  mov     [rsp-8+arg_8], rbx
0x180015fd1  mov     [rsp-8+arg_18], rdi
0x180015fd6  push    rbp
0x180015fd7  lea     rbp, [rsp-170h]
0x180015fdf  sub     rsp, 270h
0x180015fe6  mov     rax, cs:__security_cookie
0x180015fed  xor     rax, rsp
0x180015ff0  mov     [rbp+170h+var_10], rax
0x180015ff7  mov     rdi, r8
0x180015ffa  mov     qword ptr [r8], 0
0x180016001  mov     r9, rcx; pszSrc
0x180016004  mov     edx, 104h; cchDest
0x180016009  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18001600e  call    StringCopyWorkerW
0x180016013  lea     r8, aP0; "_p0"
0x18001601a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18001601f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180016024  lea     r8, [rsp+270h+pszDest]; lpName
0x180016029  xor     edx, edx; bInheritHandle
0x18001602b  mov     ecx, 1F0003h; dwDesiredAccess
0x180016030  call    cs:__imp_OpenSemaphoreW
0x180016036  mov     [rsp+270h+var_230], rax
0x18001603b  test    rax, rax
0x18001603e  jnz     short loc_180016067
0x180016040  call    cs:__imp_GetLastError
0x180016046  cmp     eax, 2
0x180016049  jz      loc_180016136
0x18001604f  mov     rcx, [rbp+178h]; this
0x180016056  mov     edx, 0D0h; void *
0x18001605b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016060  mov     ebx, eax
0x180016062  jmp     loc_180016138
0x180016067  mov     [rsp+270h+var_23C], 0
0x18001606f  mov     [rsp+270h+var_240], 0
0x180016077  lea     rdx, [rsp+270h+var_23C]; int *
0x18001607c  mov     rcx, rax; hHandle
0x18001607f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180016084  mov     ebx, eax
0x180016086  test    eax, eax
0x180016088  jns     short loc_1800160A3
0x18001608a  mov     rcx, [rbp+178h]; this
0x180016091  mov     r9d, eax; char *
0x180016094  mov     edx, 0D6h; void *
0x180016099  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001609e  jmp     loc_180016138
0x1800160a3  lea     r8, asc_180020928; "h"
0x1800160aa  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800160af  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800160b4  lea     r8, [rsp+270h+pszDest]; lpName
0x1800160b9  xor     edx, edx; bInheritHandle
0x1800160bb  mov     ecx, 1F0003h; dwDesiredAccess
0x1800160c0  call    cs:__imp_OpenSemaphoreW
0x1800160c6  mov     [rsp+270h+var_238], rax
0x1800160cb  test    rax, rax
0x1800160ce  jnz     short loc_1800160EF
0x1800160d0  mov     rcx, [rbp+178h]; this
0x1800160d7  mov     edx, 0DCh; void *
0x1800160dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800160e1  mov     ebx, eax
0x1800160e3  lea     rcx, [rsp+270h+var_238]
0x1800160e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800160ed  jmp     short loc_180016138
0x1800160ef  lea     rdx, [rsp+270h+var_240]; int *
0x1800160f4  mov     rcx, rax; hHandle
0x1800160f7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800160fc  mov     ebx, eax
0x1800160fe  test    eax, eax
0x180016100  jns     short loc_180016118
0x180016102  mov     rcx, [rbp+178h]; this
0x180016109  mov     r9d, eax; char *
0x18001610c  mov     edx, 0DEh; void *
0x180016111  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016116  jmp     short loc_1800160E3
0x180016118  lea     rcx, [rsp+270h+var_238]
0x18001611d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016122  movsxd  rcx, [rsp+270h+var_240]
0x180016127  shl     rcx, 1Fh
0x18001612b  movsxd  rax, [rsp+270h+var_23C]
0x180016130  or      rcx, rax
0x180016133  mov     [rdi], rcx
0x180016136  xor     ebx, ebx
0x180016138  lea     rcx, [rsp+270h+var_230]
0x18001613d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180016142  mov     eax, ebx
0x180016144  mov     rcx, [rbp+170h+var_10]
0x18001614b  xor     rcx, rsp; StackCookie
0x18001614e  call    __security_check_cookie
0x180016153  lea     r11, [rsp+270h+var_s0]
0x18001615b  mov     rbx, [r11+18h]
0x18001615f  mov     rdi, [r11+28h]
0x180016163  mov     rsp, r11
0x180016166  pop     rbp
0x180016167  retn
```
