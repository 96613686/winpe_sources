# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180022a7c`
- end: `0x180022c3a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800229f8`

## callees

- `0x18001e1e0`
- `0x180020b58`
- `0x180021774`
- `0x180022274`
- `0x180022294`
- `0x1800227b0`
- `0x1800228a4`
- `0x180022a7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180022ae5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180022b85`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180022ae5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180022b85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022af5`

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
0x180022a7c  mov     [rsp-8+arg_8], rbx
0x180022a81  push    rbp
0x180022a82  push    rdi
0x180022a83  push    r14
0x180022a85  lea     rbp, [rsp-160h]
0x180022a8d  sub     rsp, 260h
0x180022a94  mov     rax, cs:__security_cookie
0x180022a9b  xor     rax, rsp
0x180022a9e  mov     [rbp+170h+var_20], rax
0x180022aa5  mov     rdi, r8
0x180022aa8  mov     qword ptr [r8], 0
0x180022aaf  mov     r8, rcx; unsigned __int16 *
0x180022ab2  mov     r14d, 104h
0x180022ab8  mov     edx, r14d; unsigned __int64
0x180022abb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022ac0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022ac5  lea     r8, aP0; "_p0"
0x180022acc  mov     edx, r14d; unsigned __int64
0x180022acf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022ad4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022ad9  lea     r8, [rsp+270h+Name]; lpName
0x180022ade  xor     edx, edx; bInheritHandle
0x180022ae0  mov     ecx, 1F0003h; dwDesiredAccess
0x180022ae5  call    cs:__imp_OpenSemaphoreW
0x180022aeb  mov     [rsp+270h+var_240], rax
0x180022af0  test    rax, rax
0x180022af3  jnz     short loc_180022B22
0x180022af5  call    cs:__imp_GetLastError
0x180022afb  cmp     eax, 2
0x180022afe  jz      loc_180022C09
0x180022b04  mov     rcx, [rbp+178h]; this
0x180022b0b  lea     r8, aWil; "wil"
0x180022b12  lea     edx, [r14-34h]; void *
0x180022b16  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022b1b  mov     ebx, eax
0x180022b1d  jmp     loc_180022C0B
0x180022b22  lea     rdx, [rsp+270h+var_24C]; int *
0x180022b27  mov     [rsp+270h+var_24C], 0
0x180022b2f  mov     rcx, rax; hHandle
0x180022b32  mov     [rsp+270h+var_250], 0; int
0x180022b3a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180022b3f  mov     ebx, eax
0x180022b41  test    eax, eax
0x180022b43  jns     short loc_180022B65
0x180022b45  mov     rcx, [rbp+178h]; this
0x180022b4c  lea     r8, aWil; "wil"
0x180022b53  mov     r9d, eax; char *
0x180022b56  mov     edx, 0D6h; void *
0x180022b5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022b60  jmp     loc_180022C0B
0x180022b65  lea     r8, asc_180076200; "h"
0x180022b6c  mov     rdx, r14; unsigned __int64
0x180022b6f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180022b74  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180022b79  lea     r8, [rsp+270h+Name]; lpName
0x180022b7e  xor     edx, edx; bInheritHandle
0x180022b80  mov     ecx, 1F0003h; dwDesiredAccess
0x180022b85  call    cs:__imp_OpenSemaphoreW
0x180022b8b  mov     [rsp+270h+var_248], rax
0x180022b90  test    rax, rax
0x180022b93  jnz     short loc_180022BBB
0x180022b95  mov     rcx, [rbp+178h]; this
0x180022b9c  lea     r8, aWil; "wil"
0x180022ba3  mov     edx, 0DCh; void *
0x180022ba8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022bad  mov     ebx, eax
0x180022baf  lea     rcx, [rsp+270h+var_248]
0x180022bb4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022bb9  jmp     short loc_180022C0B
0x180022bbb  lea     rdx, [rsp+270h+var_250]; int *
0x180022bc0  mov     rcx, rax; hHandle
0x180022bc3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180022bc8  mov     ebx, eax
0x180022bca  test    eax, eax
0x180022bcc  jns     short loc_180022BEB
0x180022bce  mov     rcx, [rbp+178h]; this
0x180022bd5  lea     r8, aWil; "wil"
0x180022bdc  mov     r9d, eax; char *
0x180022bdf  mov     edx, 0DEh; void *
0x180022be4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022be9  jmp     short loc_180022BAF
0x180022beb  lea     rcx, [rsp+270h+var_248]
0x180022bf0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022bf5  movsxd  rcx, [rsp+270h+var_250]
0x180022bfa  movsxd  rax, [rsp+270h+var_24C]
0x180022bff  shl     rcx, 1Fh
0x180022c03  or      rcx, rax
0x180022c06  mov     [rdi], rcx
0x180022c09  xor     ebx, ebx
0x180022c0b  lea     rcx, [rsp+270h+var_240]
0x180022c10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022c15  mov     eax, ebx
0x180022c17  mov     rcx, [rbp+170h+var_20]
0x180022c1e  xor     rcx, rsp; StackCookie
0x180022c21  call    __security_check_cookie
0x180022c26  mov     rbx, [rsp+270h+arg_8]
0x180022c2e  add     rsp, 260h
0x180022c35  pop     r14
0x180022c37  pop     rdi
0x180022c38  pop     rbp
0x180022c39  retn
```
