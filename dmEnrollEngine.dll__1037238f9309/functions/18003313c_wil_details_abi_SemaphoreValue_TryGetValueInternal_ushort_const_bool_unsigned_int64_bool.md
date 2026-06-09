# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003313c`
- end: `0x1800332fa`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800330b8`

## callees

- `0x180007040`
- `0x180011938`
- `0x18002c664`
- `0x18002e1a0`
- `0x180032260`
- `0x180032a04`
- `0x180032f20`
- `0x18003313c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800331a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180033245`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800331a5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180033245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800331b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800331b5`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x18003313c  mov     [rsp-8+arg_8], rbx
0x180033141  push    rbp
0x180033142  push    rdi
0x180033143  push    r14
0x180033145  lea     rbp, [rsp-160h]
0x18003314d  sub     rsp, 260h
0x180033154  mov     rax, cs:__security_cookie
0x18003315b  xor     rax, rsp
0x18003315e  mov     [rbp+170h+var_20], rax
0x180033165  mov     rdi, r8
0x180033168  mov     qword ptr [r8], 0
0x18003316f  mov     r8, rcx; unsigned __int16 *
0x180033172  mov     r14d, 104h
0x180033178  mov     edx, r14d; unsigned __int64
0x18003317b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033180  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033185  lea     r8, aP0; "_p0"
0x18003318c  mov     edx, r14d; unsigned __int64
0x18003318f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033194  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033199  lea     r8, [rsp+270h+Name]; lpName
0x18003319e  xor     edx, edx; bInheritHandle
0x1800331a0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800331a5  call    cs:__imp_OpenSemaphoreW
0x1800331ab  mov     [rsp+270h+var_240], rax
0x1800331b0  test    rax, rax
0x1800331b3  jnz     short loc_1800331E2
0x1800331b5  call    cs:__imp_GetLastError
0x1800331bb  cmp     eax, 2
0x1800331be  jz      loc_1800332C9
0x1800331c4  mov     rcx, [rbp+178h]; this
0x1800331cb  lea     r8, aWil; "wil"
0x1800331d2  lea     edx, [r14-34h]; void *
0x1800331d6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800331db  mov     ebx, eax
0x1800331dd  jmp     loc_1800332CB
0x1800331e2  lea     rdx, [rsp+270h+var_24C]; int *
0x1800331e7  mov     [rsp+270h+var_24C], 0
0x1800331ef  mov     rcx, rax; hHandle
0x1800331f2  mov     [rsp+270h+var_250], 0; int
0x1800331fa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800331ff  mov     ebx, eax
0x180033201  test    eax, eax
0x180033203  jns     short loc_180033225
0x180033205  mov     rcx, [rbp+178h]; this
0x18003320c  lea     r8, aWil; "wil"
0x180033213  mov     r9d, eax; char *
0x180033216  mov     edx, 0D6h; void *
0x18003321b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033220  jmp     loc_1800332CB
0x180033225  lea     r8, asc_1800805C8; "h"
0x18003322c  mov     rdx, r14; unsigned __int64
0x18003322f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180033234  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033239  lea     r8, [rsp+270h+Name]; lpName
0x18003323e  xor     edx, edx; bInheritHandle
0x180033240  mov     ecx, 1F0003h; dwDesiredAccess
0x180033245  call    cs:__imp_OpenSemaphoreW
0x18003324b  mov     [rsp+270h+var_248], rax
0x180033250  test    rax, rax
0x180033253  jnz     short loc_18003327B
0x180033255  mov     rcx, [rbp+178h]; this
0x18003325c  lea     r8, aWil; "wil"
0x180033263  mov     edx, 0DCh; void *
0x180033268  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003326d  mov     ebx, eax
0x18003326f  lea     rcx, [rsp+270h+var_248]
0x180033274  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180033279  jmp     short loc_1800332CB
0x18003327b  lea     rdx, [rsp+270h+var_250]; int *
0x180033280  mov     rcx, rax; hHandle
0x180033283  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180033288  mov     ebx, eax
0x18003328a  test    eax, eax
0x18003328c  jns     short loc_1800332AB
0x18003328e  mov     rcx, [rbp+178h]; this
0x180033295  lea     r8, aWil; "wil"
0x18003329c  mov     r9d, eax; char *
0x18003329f  mov     edx, 0DEh; void *
0x1800332a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800332a9  jmp     short loc_18003326F
0x1800332ab  lea     rcx, [rsp+270h+var_248]
0x1800332b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800332b5  movsxd  rcx, [rsp+270h+var_250]
0x1800332ba  movsxd  rax, [rsp+270h+var_24C]
0x1800332bf  shl     rcx, 1Fh
0x1800332c3  or      rcx, rax
0x1800332c6  mov     [rdi], rcx
0x1800332c9  xor     ebx, ebx
0x1800332cb  lea     rcx, [rsp+270h+var_240]
0x1800332d0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800332d5  mov     eax, ebx
0x1800332d7  mov     rcx, [rbp+170h+var_20]
0x1800332de  xor     rcx, rsp; StackCookie
0x1800332e1  call    __security_check_cookie
0x1800332e6  mov     rbx, [rsp+270h+arg_8]
0x1800332ee  add     rsp, 260h
0x1800332f5  pop     r14
0x1800332f7  pop     rdi
0x1800332f8  pop     rbp
0x1800332f9  retn
```
