# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000909c`
- end: `0x18000924c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009018`

## callees

- `0x1800025f0`
- `0x18000533c`
- `0x180006858`
- `0x1800084cc`
- `0x1800084ec`
- `0x180008bac`
- `0x180008c38`
- `0x18000909c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009105`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000919e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009105`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000919e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009115`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
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
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18000909c  mov     [rsp-8+arg_8], rbx
0x1800090a1  push    rbp
0x1800090a2  push    rdi
0x1800090a3  push    r14
0x1800090a5  lea     rbp, [rsp-160h]
0x1800090ad  sub     rsp, 260h
0x1800090b4  mov     rax, cs:__security_cookie
0x1800090bb  xor     rax, rsp
0x1800090be  mov     [rbp+170h+var_20], rax
0x1800090c5  mov     rdi, r8
0x1800090c8  mov     qword ptr [r8], 0
0x1800090cf  mov     r8, rcx; unsigned __int16 *
0x1800090d2  mov     r14d, 104h
0x1800090d8  mov     edx, r14d; unsigned __int64
0x1800090db  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800090e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800090e5  lea     r8, aP0; "_p0"
0x1800090ec  mov     edx, r14d; unsigned __int64
0x1800090ef  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800090f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800090f9  lea     r8, [rsp+270h+Name]; lpName
0x1800090fe  xor     edx, edx; bInheritHandle
0x180009100  mov     ecx, 1F0003h; dwDesiredAccess
0x180009105  call    cs:__imp_OpenSemaphoreW
0x18000910b  mov     [rsp+270h+var_240], rax
0x180009110  test    rax, rax
0x180009113  jnz     short loc_18000913B
0x180009115  call    cs:__imp_GetLastError
0x18000911b  cmp     eax, 2
0x18000911e  jz      loc_18000921B
0x180009124  mov     rcx, [rbp+178h]; this
0x18000912b  lea     edx, [r14-34h]; void *
0x18000912f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009134  mov     ebx, eax
0x180009136  jmp     loc_18000921D
0x18000913b  lea     rdx, [rsp+270h+var_24C]; int *
0x180009140  mov     [rsp+270h+var_24C], 0
0x180009148  mov     rcx, rax; hHandle
0x18000914b  mov     [rsp+270h+var_250], 0; int
0x180009153  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009158  mov     ebx, eax
0x18000915a  test    eax, eax
0x18000915c  jns     short loc_18000917E
0x18000915e  mov     rcx, [rbp+178h]; this
0x180009165  lea     r8, aWil; "wil"
0x18000916c  mov     r9d, eax; char *
0x18000916f  mov     edx, 0D6h; void *
0x180009174  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009179  jmp     loc_18000921D
0x18000917e  lea     r8, asc_180044030; "h"
0x180009185  mov     rdx, r14; unsigned __int64
0x180009188  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000918d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009192  lea     r8, [rsp+270h+Name]; lpName
0x180009197  xor     edx, edx; bInheritHandle
0x180009199  mov     ecx, 1F0003h; dwDesiredAccess
0x18000919e  call    cs:__imp_OpenSemaphoreW
0x1800091a4  mov     [rsp+270h+var_248], rax
0x1800091a9  test    rax, rax
0x1800091ac  jnz     short loc_1800091CD
0x1800091ae  mov     rcx, [rbp+178h]; this
0x1800091b5  mov     edx, 0DCh; void *
0x1800091ba  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800091bf  mov     ebx, eax
0x1800091c1  lea     rcx, [rsp+270h+var_248]
0x1800091c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800091cb  jmp     short loc_18000921D
0x1800091cd  lea     rdx, [rsp+270h+var_250]; int *
0x1800091d2  mov     rcx, rax; hHandle
0x1800091d5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800091da  mov     ebx, eax
0x1800091dc  test    eax, eax
0x1800091de  jns     short loc_1800091FD
0x1800091e0  mov     rcx, [rbp+178h]; this
0x1800091e7  lea     r8, aWil; "wil"
0x1800091ee  mov     r9d, eax; char *
0x1800091f1  mov     edx, 0DEh; void *
0x1800091f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091fb  jmp     short loc_1800091C1
0x1800091fd  lea     rcx, [rsp+270h+var_248]
0x180009202  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009207  movsxd  rcx, [rsp+270h+var_250]
0x18000920c  movsxd  rax, [rsp+270h+var_24C]
0x180009211  shl     rcx, 1Fh
0x180009215  or      rcx, rax
0x180009218  mov     [rdi], rcx
0x18000921b  xor     ebx, ebx
0x18000921d  lea     rcx, [rsp+270h+var_240]
0x180009222  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009227  mov     eax, ebx
0x180009229  mov     rcx, [rbp+170h+var_20]
0x180009230  xor     rcx, rsp; StackCookie
0x180009233  call    __security_check_cookie
0x180009238  mov     rbx, [rsp+270h+arg_8]
0x180009240  add     rsp, 260h
0x180009247  pop     r14
0x180009249  pop     rdi
0x18000924a  pop     rbp
0x18000924b  retn
```
