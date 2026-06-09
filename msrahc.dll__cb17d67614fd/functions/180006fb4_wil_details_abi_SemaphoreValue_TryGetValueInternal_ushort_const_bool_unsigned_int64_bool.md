# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006fb4`
- end: `0x18000715e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006f30`

## callees

- `0x180003528`
- `0x1800049c4`
- `0x18000633c`
- `0x18000635c`
- `0x180006a20`
- `0x180006b04`
- `0x180006fb4`
- `0x18001a5e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007028`
- `KERNEL32!GetLastError` at `0x180007028`
- `KERNEL32!OpenSemaphoreW` at `0x180007018`
- `KERNEL32!OpenSemaphoreW` at `0x1800070af`
- `KERNEL32!OpenSemaphoreW` at `0x180007018`
- `KERNEL32!OpenSemaphoreW` at `0x1800070af`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
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
  wil::details *v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  void *v16; // rdx
  int v17; // eax
  void *v18; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v22; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v23; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v23 = v6;
  if ( v6 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v21);
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
    StringCchCatW(Name, v12, L"h");
    v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v22 = v13;
    if ( v13 )
    {
      v17 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v20);
      LastError = v17;
      if ( v17 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v18);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v16);
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
    &v23,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180006fb4  mov     [rsp-8+arg_8], rbx
0x180006fb9  mov     [rsp-8+arg_18], rdi
0x180006fbe  push    rbp
0x180006fbf  lea     rbp, [rsp-160h]
0x180006fc7  sub     rsp, 260h
0x180006fce  mov     rax, cs:__security_cookie
0x180006fd5  xor     rax, rsp
0x180006fd8  mov     [rbp+160h+var_10], rax
0x180006fdf  mov     rdi, r8
0x180006fe2  mov     qword ptr [r8], 0
0x180006fe9  mov     r8, rcx; unsigned __int16 *
0x180006fec  mov     edx, 104h; unsigned __int64
0x180006ff1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180006ff6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006ffb  lea     r8, aP0; "_p0"
0x180007002  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007007  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000700c  lea     r8, [rsp+260h+Name]; lpName
0x180007011  xor     edx, edx; bInheritHandle
0x180007013  mov     ecx, 1F0003h; dwDesiredAccess
0x180007018  call    cs:__imp_OpenSemaphoreW
0x18000701e  mov     [rsp+260h+var_230], rax
0x180007023  test    rax, rax
0x180007026  jnz     short loc_18000704F
0x180007028  call    cs:__imp_GetLastError
0x18000702e  cmp     eax, 2
0x180007031  jz      loc_18000712C
0x180007037  mov     rcx, [rbp+168h]; this
0x18000703e  mov     edx, 0D0h; void *
0x180007043  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007048  mov     ebx, eax
0x18000704a  jmp     loc_18000712E
0x18000704f  lea     rdx, [rsp+260h+var_23C]; int *
0x180007054  mov     [rsp+260h+var_23C], 0
0x18000705c  mov     rcx, rax; hHandle
0x18000705f  mov     [rsp+260h+var_240], 0; int
0x180007067  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000706c  mov     ebx, eax
0x18000706e  test    eax, eax
0x180007070  jns     short loc_180007092
0x180007072  mov     rcx, [rbp+168h]; this
0x180007079  lea     r8, aWil; "wil"
0x180007080  mov     r9d, eax; char *
0x180007083  mov     edx, 0D6h; void *
0x180007088  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000708d  jmp     loc_18000712E
0x180007092  lea     r8, asc_18001FDA8; "h"
0x180007099  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000709e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800070a3  lea     r8, [rsp+260h+Name]; lpName
0x1800070a8  xor     edx, edx; bInheritHandle
0x1800070aa  mov     ecx, 1F0003h; dwDesiredAccess
0x1800070af  call    cs:__imp_OpenSemaphoreW
0x1800070b5  mov     [rsp+260h+var_238], rax
0x1800070ba  test    rax, rax
0x1800070bd  jnz     short loc_1800070DE
0x1800070bf  mov     rcx, [rbp+168h]; this
0x1800070c6  mov     edx, 0DCh; void *
0x1800070cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800070d0  mov     ebx, eax
0x1800070d2  lea     rcx, [rsp+260h+var_238]
0x1800070d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800070dc  jmp     short loc_18000712E
0x1800070de  lea     rdx, [rsp+260h+var_240]; int *
0x1800070e3  mov     rcx, rax; hHandle
0x1800070e6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800070eb  mov     ebx, eax
0x1800070ed  test    eax, eax
0x1800070ef  jns     short loc_18000710E
0x1800070f1  mov     rcx, [rbp+168h]; this
0x1800070f8  lea     r8, aWil; "wil"
0x1800070ff  mov     r9d, eax; char *
0x180007102  mov     edx, 0DEh; void *
0x180007107  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000710c  jmp     short loc_1800070D2
0x18000710e  lea     rcx, [rsp+260h+var_238]
0x180007113  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007118  movsxd  rcx, [rsp+260h+var_240]
0x18000711d  movsxd  rax, [rsp+260h+var_23C]
0x180007122  shl     rcx, 1Fh
0x180007126  or      rcx, rax
0x180007129  mov     [rdi], rcx
0x18000712c  xor     ebx, ebx
0x18000712e  lea     rcx, [rsp+260h+var_230]
0x180007133  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007138  mov     eax, ebx
0x18000713a  mov     rcx, [rbp+160h+var_10]
0x180007141  xor     rcx, rsp; StackCookie
0x180007144  call    __security_check_cookie
0x180007149  lea     r11, [rsp+260h+var_s0]
0x180007151  mov     rbx, [r11+18h]
0x180007155  mov     rdi, [r11+28h]
0x180007159  mov     rsp, r11
0x18000715c  pop     rbp
0x18000715d  retn
```
