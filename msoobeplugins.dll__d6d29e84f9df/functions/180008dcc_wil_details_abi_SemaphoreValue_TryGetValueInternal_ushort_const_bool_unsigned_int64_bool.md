# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008dcc`
- end: `0x180008f8a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008d48`

## callees

- `0x180003470`
- `0x180006b18`
- `0x1800078a0`
- `0x180008524`
- `0x180008544`
- `0x180008a60`
- `0x180008b54`
- `0x180008dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008e35`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008ed5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008e35`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e45`

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
0x180008dcc  mov     [rsp-8+arg_8], rbx
0x180008dd1  push    rbp
0x180008dd2  push    rdi
0x180008dd3  push    r14
0x180008dd5  lea     rbp, [rsp-160h]
0x180008ddd  sub     rsp, 260h
0x180008de4  mov     rax, cs:__security_cookie
0x180008deb  xor     rax, rsp
0x180008dee  mov     [rbp+170h+var_20], rax
0x180008df5  mov     rdi, r8
0x180008df8  mov     qword ptr [r8], 0
0x180008dff  mov     r8, rcx; unsigned __int16 *
0x180008e02  mov     r14d, 104h
0x180008e08  mov     edx, r14d; unsigned __int64
0x180008e0b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008e10  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008e15  lea     r8, aP0; "_p0"
0x180008e1c  mov     edx, r14d; unsigned __int64
0x180008e1f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008e24  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008e29  lea     r8, [rsp+270h+Name]; lpName
0x180008e2e  xor     edx, edx; bInheritHandle
0x180008e30  mov     ecx, 1F0003h; dwDesiredAccess
0x180008e35  call    cs:__imp_OpenSemaphoreW
0x180008e3b  mov     [rsp+270h+var_240], rax
0x180008e40  test    rax, rax
0x180008e43  jnz     short loc_180008E72
0x180008e45  call    cs:__imp_GetLastError
0x180008e4b  cmp     eax, 2
0x180008e4e  jz      loc_180008F59
0x180008e54  mov     rcx, [rbp+178h]; this
0x180008e5b  lea     r8, aWil; "wil"
0x180008e62  lea     edx, [r14-34h]; void *
0x180008e66  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008e6b  mov     ebx, eax
0x180008e6d  jmp     loc_180008F5B
0x180008e72  lea     rdx, [rsp+270h+var_24C]; int *
0x180008e77  mov     [rsp+270h+var_24C], 0
0x180008e7f  mov     rcx, rax; hHandle
0x180008e82  mov     [rsp+270h+var_250], 0; int
0x180008e8a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008e8f  mov     ebx, eax
0x180008e91  test    eax, eax
0x180008e93  jns     short loc_180008EB5
0x180008e95  mov     rcx, [rbp+178h]; this
0x180008e9c  lea     r8, aWil; "wil"
0x180008ea3  mov     r9d, eax; char *
0x180008ea6  mov     edx, 0D6h; void *
0x180008eab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008eb0  jmp     loc_180008F5B
0x180008eb5  lea     r8, asc_1800DA1C8; "h"
0x180008ebc  mov     rdx, r14; unsigned __int64
0x180008ebf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008ec4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008ec9  lea     r8, [rsp+270h+Name]; lpName
0x180008ece  xor     edx, edx; bInheritHandle
0x180008ed0  mov     ecx, 1F0003h; dwDesiredAccess
0x180008ed5  call    cs:__imp_OpenSemaphoreW
0x180008edb  mov     [rsp+270h+var_248], rax
0x180008ee0  test    rax, rax
0x180008ee3  jnz     short loc_180008F0B
0x180008ee5  mov     rcx, [rbp+178h]; this
0x180008eec  lea     r8, aWil; "wil"
0x180008ef3  mov     edx, 0DCh; void *
0x180008ef8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008efd  mov     ebx, eax
0x180008eff  lea     rcx, [rsp+270h+var_248]
0x180008f04  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008f09  jmp     short loc_180008F5B
0x180008f0b  lea     rdx, [rsp+270h+var_250]; int *
0x180008f10  mov     rcx, rax; hHandle
0x180008f13  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008f18  mov     ebx, eax
0x180008f1a  test    eax, eax
0x180008f1c  jns     short loc_180008F3B
0x180008f1e  mov     rcx, [rbp+178h]; this
0x180008f25  lea     r8, aWil; "wil"
0x180008f2c  mov     r9d, eax; char *
0x180008f2f  mov     edx, 0DEh; void *
0x180008f34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008f39  jmp     short loc_180008EFF
0x180008f3b  lea     rcx, [rsp+270h+var_248]
0x180008f40  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008f45  movsxd  rcx, [rsp+270h+var_250]
0x180008f4a  movsxd  rax, [rsp+270h+var_24C]
0x180008f4f  shl     rcx, 1Fh
0x180008f53  or      rcx, rax
0x180008f56  mov     [rdi], rcx
0x180008f59  xor     ebx, ebx
0x180008f5b  lea     rcx, [rsp+270h+var_240]
0x180008f60  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008f65  mov     eax, ebx
0x180008f67  mov     rcx, [rbp+170h+var_20]
0x180008f6e  xor     rcx, rsp; StackCookie
0x180008f71  call    __security_check_cookie
0x180008f76  mov     rbx, [rsp+270h+arg_8]
0x180008f7e  add     rsp, 260h
0x180008f85  pop     r14
0x180008f87  pop     rdi
0x180008f88  pop     rbp
0x180008f89  retn
```
