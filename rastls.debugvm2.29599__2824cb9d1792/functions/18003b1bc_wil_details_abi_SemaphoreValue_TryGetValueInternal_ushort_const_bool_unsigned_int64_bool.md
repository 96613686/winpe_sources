# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003b1bc`
- end: `0x18003b37a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003b138`

## callees

- `0x18002b7b4`
- `0x180035680`
- `0x180038290`
- `0x180039580`
- `0x18003a654`
- `0x18003ace8`
- `0x18003ad74`
- `0x18003b1bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b225`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b2c5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b225`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003b2c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b235`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b235`

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
0x18003b1bc  mov     [rsp-8+arg_8], rbx
0x18003b1c1  push    rbp
0x18003b1c2  push    rdi
0x18003b1c3  push    r14
0x18003b1c5  lea     rbp, [rsp-160h]
0x18003b1cd  sub     rsp, 260h
0x18003b1d4  mov     rax, cs:__security_cookie
0x18003b1db  xor     rax, rsp
0x18003b1de  mov     [rbp+170h+var_20], rax
0x18003b1e5  mov     rdi, r8
0x18003b1e8  mov     qword ptr [r8], 0
0x18003b1ef  mov     r8, rcx; unsigned __int16 *
0x18003b1f2  mov     r14d, 104h
0x18003b1f8  mov     edx, r14d; unsigned __int64
0x18003b1fb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b200  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003b205  lea     r8, aP0; "_p0"
0x18003b20c  mov     edx, r14d; unsigned __int64
0x18003b20f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b214  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b219  lea     r8, [rsp+270h+Name]; lpName
0x18003b21e  xor     edx, edx; bInheritHandle
0x18003b220  mov     ecx, 1F0003h; dwDesiredAccess
0x18003b225  call    cs:__imp_OpenSemaphoreW
0x18003b22b  mov     [rsp+270h+var_240], rax
0x18003b230  test    rax, rax
0x18003b233  jnz     short loc_18003B262
0x18003b235  call    cs:__imp_GetLastError
0x18003b23b  cmp     eax, 2
0x18003b23e  jz      loc_18003B349
0x18003b244  mov     rcx, [rbp+178h]; this
0x18003b24b  lea     r8, aWil; "wil"
0x18003b252  lea     edx, [r14-34h]; void *
0x18003b256  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b25b  mov     ebx, eax
0x18003b25d  jmp     loc_18003B34B
0x18003b262  lea     rdx, [rsp+270h+var_24C]; int *
0x18003b267  mov     [rsp+270h+var_24C], 0
0x18003b26f  mov     rcx, rax; hHandle
0x18003b272  mov     [rsp+270h+var_250], 0; int
0x18003b27a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003b27f  mov     ebx, eax
0x18003b281  test    eax, eax
0x18003b283  jns     short loc_18003B2A5
0x18003b285  mov     rcx, [rbp+178h]; this
0x18003b28c  lea     r8, aWil; "wil"
0x18003b293  mov     r9d, eax; char *
0x18003b296  mov     edx, 0D6h; void *
0x18003b29b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b2a0  jmp     loc_18003B34B
0x18003b2a5  lea     r8, asc_180083358; "h"
0x18003b2ac  mov     rdx, r14; unsigned __int64
0x18003b2af  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003b2b4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003b2b9  lea     r8, [rsp+270h+Name]; lpName
0x18003b2be  xor     edx, edx; bInheritHandle
0x18003b2c0  mov     ecx, 1F0003h; dwDesiredAccess
0x18003b2c5  call    cs:__imp_OpenSemaphoreW
0x18003b2cb  mov     [rsp+270h+var_248], rax
0x18003b2d0  test    rax, rax
0x18003b2d3  jnz     short loc_18003B2FB
0x18003b2d5  mov     rcx, [rbp+178h]; this
0x18003b2dc  lea     r8, aWil; "wil"
0x18003b2e3  mov     edx, 0DCh; void *
0x18003b2e8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003b2ed  mov     ebx, eax
0x18003b2ef  lea     rcx, [rsp+270h+var_248]
0x18003b2f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b2f9  jmp     short loc_18003B34B
0x18003b2fb  lea     rdx, [rsp+270h+var_250]; int *
0x18003b300  mov     rcx, rax; hHandle
0x18003b303  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003b308  mov     ebx, eax
0x18003b30a  test    eax, eax
0x18003b30c  jns     short loc_18003B32B
0x18003b30e  mov     rcx, [rbp+178h]; this
0x18003b315  lea     r8, aWil; "wil"
0x18003b31c  mov     r9d, eax; char *
0x18003b31f  mov     edx, 0DEh; void *
0x18003b324  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b329  jmp     short loc_18003B2EF
0x18003b32b  lea     rcx, [rsp+270h+var_248]
0x18003b330  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b335  movsxd  rcx, [rsp+270h+var_250]
0x18003b33a  movsxd  rax, [rsp+270h+var_24C]
0x18003b33f  shl     rcx, 1Fh
0x18003b343  or      rcx, rax
0x18003b346  mov     [rdi], rcx
0x18003b349  xor     ebx, ebx
0x18003b34b  lea     rcx, [rsp+270h+var_240]
0x18003b350  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003b355  mov     eax, ebx
0x18003b357  mov     rcx, [rbp+170h+var_20]
0x18003b35e  xor     rcx, rsp; StackCookie
0x18003b361  call    __security_check_cookie
0x18003b366  mov     rbx, [rsp+270h+arg_8]
0x18003b36e  add     rsp, 260h
0x18003b375  pop     r14
0x18003b377  pop     rdi
0x18003b378  pop     rbp
0x18003b379  retn
```
