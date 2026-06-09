# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007e1c`
- end: `0x180007fda`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007d98`

## callees

- `0x180002300`
- `0x1800042bc`
- `0x180005788`
- `0x180007458`
- `0x180007478`
- `0x1800078f0`
- `0x180007944`
- `0x180007e1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007e85`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f25`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007e85`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f25`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e95`

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
0x180007e1c  mov     [rsp-8+arg_8], rbx
0x180007e21  push    rbp
0x180007e22  push    rdi
0x180007e23  push    r14
0x180007e25  lea     rbp, [rsp-160h]
0x180007e2d  sub     rsp, 260h
0x180007e34  mov     rax, cs:__security_cookie
0x180007e3b  xor     rax, rsp
0x180007e3e  mov     [rbp+170h+var_20], rax
0x180007e45  mov     rdi, r8
0x180007e48  mov     qword ptr [r8], 0
0x180007e4f  mov     r8, rcx; unsigned __int16 *
0x180007e52  mov     r14d, 104h
0x180007e58  mov     edx, r14d; unsigned __int64
0x180007e5b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007e60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007e65  lea     r8, aP0; "_p0"
0x180007e6c  mov     edx, r14d; unsigned __int64
0x180007e6f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007e74  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007e79  lea     r8, [rsp+270h+Name]; lpName
0x180007e7e  xor     edx, edx; bInheritHandle
0x180007e80  mov     ecx, 1F0003h; dwDesiredAccess
0x180007e85  call    cs:__imp_OpenSemaphoreW
0x180007e8b  mov     [rsp+270h+var_240], rax
0x180007e90  test    rax, rax
0x180007e93  jnz     short loc_180007EC2
0x180007e95  call    cs:__imp_GetLastError
0x180007e9b  cmp     eax, 2
0x180007e9e  jz      loc_180007FA9
0x180007ea4  mov     rcx, [rbp+178h]; this
0x180007eab  lea     r8, aWil; "wil"
0x180007eb2  lea     edx, [r14-34h]; void *
0x180007eb6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007ebb  mov     ebx, eax
0x180007ebd  jmp     loc_180007FAB
0x180007ec2  lea     rdx, [rsp+270h+var_24C]; int *
0x180007ec7  mov     [rsp+270h+var_24C], 0
0x180007ecf  mov     rcx, rax; hHandle
0x180007ed2  mov     [rsp+270h+var_250], 0; int
0x180007eda  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007edf  mov     ebx, eax
0x180007ee1  test    eax, eax
0x180007ee3  jns     short loc_180007F05
0x180007ee5  mov     rcx, [rbp+178h]; this
0x180007eec  lea     r8, aWil; "wil"
0x180007ef3  mov     r9d, eax; char *
0x180007ef6  mov     edx, 0D6h; void *
0x180007efb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f00  jmp     loc_180007FAB
0x180007f05  lea     r8, asc_18003C648; "h"
0x180007f0c  mov     rdx, r14; unsigned __int64
0x180007f0f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180007f14  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007f19  lea     r8, [rsp+270h+Name]; lpName
0x180007f1e  xor     edx, edx; bInheritHandle
0x180007f20  mov     ecx, 1F0003h; dwDesiredAccess
0x180007f25  call    cs:__imp_OpenSemaphoreW
0x180007f2b  mov     [rsp+270h+var_248], rax
0x180007f30  test    rax, rax
0x180007f33  jnz     short loc_180007F5B
0x180007f35  mov     rcx, [rbp+178h]; this
0x180007f3c  lea     r8, aWil; "wil"
0x180007f43  mov     edx, 0DCh; void *
0x180007f48  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007f4d  mov     ebx, eax
0x180007f4f  lea     rcx, [rsp+270h+var_248]
0x180007f54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007f59  jmp     short loc_180007FAB
0x180007f5b  lea     rdx, [rsp+270h+var_250]; int *
0x180007f60  mov     rcx, rax; hHandle
0x180007f63  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007f68  mov     ebx, eax
0x180007f6a  test    eax, eax
0x180007f6c  jns     short loc_180007F8B
0x180007f6e  mov     rcx, [rbp+178h]; this
0x180007f75  lea     r8, aWil; "wil"
0x180007f7c  mov     r9d, eax; char *
0x180007f7f  mov     edx, 0DEh; void *
0x180007f84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f89  jmp     short loc_180007F4F
0x180007f8b  lea     rcx, [rsp+270h+var_248]
0x180007f90  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007f95  movsxd  rcx, [rsp+270h+var_250]
0x180007f9a  movsxd  rax, [rsp+270h+var_24C]
0x180007f9f  shl     rcx, 1Fh
0x180007fa3  or      rcx, rax
0x180007fa6  mov     [rdi], rcx
0x180007fa9  xor     ebx, ebx
0x180007fab  lea     rcx, [rsp+270h+var_240]
0x180007fb0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007fb5  mov     eax, ebx
0x180007fb7  mov     rcx, [rbp+170h+var_20]
0x180007fbe  xor     rcx, rsp; StackCookie
0x180007fc1  call    __security_check_cookie
0x180007fc6  mov     rbx, [rsp+270h+arg_8]
0x180007fce  add     rsp, 260h
0x180007fd5  pop     r14
0x180007fd7  pop     rdi
0x180007fd8  pop     rbp
0x180007fd9  retn
```
