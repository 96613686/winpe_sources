# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140008f00`
- end: `0x1400090be`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400063b8`

## callees

- `0x140006210`
- `0x140007494`
- `0x140008168`
- `0x140008188`
- `0x140008c10`
- `0x140008c9c`
- `0x140008f00`
- `0x14006a120`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008f79`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008f69`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009009`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140008f69`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140009009`

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
0x140008f00  mov     [rsp-8+arg_8], rbx
0x140008f05  push    rbp
0x140008f06  push    rdi
0x140008f07  push    r14
0x140008f09  lea     rbp, [rsp-160h]
0x140008f11  sub     rsp, 260h
0x140008f18  mov     rax, cs:__security_cookie
0x140008f1f  xor     rax, rsp
0x140008f22  mov     [rbp+170h+var_20], rax
0x140008f29  mov     rdi, r8
0x140008f2c  mov     qword ptr [r8], 0
0x140008f33  mov     r8, rcx; unsigned __int16 *
0x140008f36  mov     r14d, 104h
0x140008f3c  mov     edx, r14d; unsigned __int64
0x140008f3f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140008f44  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140008f49  lea     r8, aP0; "_p0"
0x140008f50  mov     edx, r14d; unsigned __int64
0x140008f53  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140008f58  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008f5d  lea     r8, [rsp+270h+Name]; lpName
0x140008f62  xor     edx, edx; bInheritHandle
0x140008f64  mov     ecx, 1F0003h; dwDesiredAccess
0x140008f69  call    cs:__imp_OpenSemaphoreW
0x140008f6f  mov     [rsp+270h+var_240], rax
0x140008f74  test    rax, rax
0x140008f77  jnz     short loc_140008FA6
0x140008f79  call    cs:__imp_GetLastError
0x140008f7f  cmp     eax, 2
0x140008f82  jz      loc_14000908D
0x140008f88  mov     rcx, [rbp+178h]; this
0x140008f8f  lea     r8, aWil; "wil"
0x140008f96  lea     edx, [r14-34h]; void *
0x140008f9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008f9f  mov     ebx, eax
0x140008fa1  jmp     loc_14000908F
0x140008fa6  lea     rdx, [rsp+270h+var_24C]; int *
0x140008fab  mov     [rsp+270h+var_24C], 0
0x140008fb3  mov     rcx, rax; hHandle
0x140008fb6  mov     [rsp+270h+var_250], 0; int
0x140008fbe  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140008fc3  mov     ebx, eax
0x140008fc5  test    eax, eax
0x140008fc7  jns     short loc_140008FE9
0x140008fc9  mov     rcx, [rbp+178h]; this
0x140008fd0  lea     r8, aWil; "wil"
0x140008fd7  mov     r9d, eax; char *
0x140008fda  mov     edx, 0D6h; void *
0x140008fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008fe4  jmp     loc_14000908F
0x140008fe9  lea     r8, asc_140070E90; "h"
0x140008ff0  mov     rdx, r14; unsigned __int64
0x140008ff3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140008ff8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140008ffd  lea     r8, [rsp+270h+Name]; lpName
0x140009002  xor     edx, edx; bInheritHandle
0x140009004  mov     ecx, 1F0003h; dwDesiredAccess
0x140009009  call    cs:__imp_OpenSemaphoreW
0x14000900f  mov     [rsp+270h+var_248], rax
0x140009014  test    rax, rax
0x140009017  jnz     short loc_14000903F
0x140009019  mov     rcx, [rbp+178h]; this
0x140009020  lea     r8, aWil; "wil"
0x140009027  mov     edx, 0DCh; void *
0x14000902c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140009031  mov     ebx, eax
0x140009033  lea     rcx, [rsp+270h+var_248]
0x140009038  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000903d  jmp     short loc_14000908F
0x14000903f  lea     rdx, [rsp+270h+var_250]; int *
0x140009044  mov     rcx, rax; hHandle
0x140009047  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000904c  mov     ebx, eax
0x14000904e  test    eax, eax
0x140009050  jns     short loc_14000906F
0x140009052  mov     rcx, [rbp+178h]; this
0x140009059  lea     r8, aWil; "wil"
0x140009060  mov     r9d, eax; char *
0x140009063  mov     edx, 0DEh; void *
0x140009068  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000906d  jmp     short loc_140009033
0x14000906f  lea     rcx, [rsp+270h+var_248]
0x140009074  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009079  movsxd  rcx, [rsp+270h+var_250]
0x14000907e  movsxd  rax, [rsp+270h+var_24C]
0x140009083  shl     rcx, 1Fh
0x140009087  or      rcx, rax
0x14000908a  mov     [rdi], rcx
0x14000908d  xor     ebx, ebx
0x14000908f  lea     rcx, [rsp+270h+var_240]
0x140009094  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140009099  mov     eax, ebx
0x14000909b  mov     rcx, [rbp+170h+var_20]
0x1400090a2  xor     rcx, rsp; StackCookie
0x1400090a5  call    __security_check_cookie
0x1400090aa  mov     rbx, [rsp+270h+arg_8]
0x1400090b2  add     rsp, 260h
0x1400090b9  pop     r14
0x1400090bb  pop     rdi
0x1400090bc  pop     rbp
0x1400090bd  retn
```
