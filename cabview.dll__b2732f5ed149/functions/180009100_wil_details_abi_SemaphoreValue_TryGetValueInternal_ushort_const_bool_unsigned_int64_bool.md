# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009100`
- end: `0x1800092b0`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000907c`

## callees

- `0x180002620`
- `0x180004050`
- `0x1800063ac`
- `0x180008478`
- `0x180008498`
- `0x180008af8`
- `0x180008c48`
- `0x180009100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009179`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009179`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009169`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009202`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009169`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009202`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
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
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
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
0x180009100  mov     [rsp-8+arg_8], rbx
0x180009105  push    rbp
0x180009106  push    rdi
0x180009107  push    r14
0x180009109  lea     rbp, [rsp-160h]
0x180009111  sub     rsp, 260h
0x180009118  mov     rax, cs:__security_cookie
0x18000911f  xor     rax, rsp
0x180009122  mov     [rbp+170h+var_20], rax
0x180009129  mov     rdi, r8
0x18000912c  mov     qword ptr [r8], 0
0x180009133  mov     r8, rcx; unsigned __int16 *
0x180009136  mov     r14d, 104h
0x18000913c  mov     edx, r14d; unsigned __int64
0x18000913f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009144  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009149  lea     r8, aP0; "_p0"
0x180009150  mov     edx, r14d; unsigned __int64
0x180009153  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009158  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000915d  lea     r8, [rsp+270h+Name]; lpName
0x180009162  xor     edx, edx; bInheritHandle
0x180009164  mov     ecx, 1F0003h; dwDesiredAccess
0x180009169  call    cs:__imp_OpenSemaphoreW
0x18000916f  mov     [rsp+270h+var_240], rax
0x180009174  test    rax, rax
0x180009177  jnz     short loc_18000919F
0x180009179  call    cs:__imp_GetLastError
0x18000917f  cmp     eax, 2
0x180009182  jz      loc_18000927F
0x180009188  mov     rcx, [rbp+178h]; this
0x18000918f  lea     edx, [r14-34h]; void *
0x180009193  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009198  mov     ebx, eax
0x18000919a  jmp     loc_180009281
0x18000919f  lea     rdx, [rsp+270h+var_24C]; int *
0x1800091a4  mov     [rsp+270h+var_24C], 0
0x1800091ac  mov     rcx, rax; hHandle
0x1800091af  mov     [rsp+270h+var_250], 0; int
0x1800091b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800091bc  mov     ebx, eax
0x1800091be  test    eax, eax
0x1800091c0  jns     short loc_1800091E2
0x1800091c2  mov     rcx, [rbp+178h]; this
0x1800091c9  lea     r8, aWil; "wil"
0x1800091d0  mov     r9d, eax; char *
0x1800091d3  mov     edx, 0D6h; void *
0x1800091d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800091dd  jmp     loc_180009281
0x1800091e2  lea     r8, asc_180015560; "h"
0x1800091e9  mov     rdx, r14; unsigned __int64
0x1800091ec  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800091f1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800091f6  lea     r8, [rsp+270h+Name]; lpName
0x1800091fb  xor     edx, edx; bInheritHandle
0x1800091fd  mov     ecx, 1F0003h; dwDesiredAccess
0x180009202  call    cs:__imp_OpenSemaphoreW
0x180009208  mov     [rsp+270h+var_248], rax
0x18000920d  test    rax, rax
0x180009210  jnz     short loc_180009231
0x180009212  mov     rcx, [rbp+178h]; this
0x180009219  mov     edx, 0DCh; void *
0x18000921e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009223  mov     ebx, eax
0x180009225  lea     rcx, [rsp+270h+var_248]
0x18000922a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000922f  jmp     short loc_180009281
0x180009231  lea     rdx, [rsp+270h+var_250]; int *
0x180009236  mov     rcx, rax; hHandle
0x180009239  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000923e  mov     ebx, eax
0x180009240  test    eax, eax
0x180009242  jns     short loc_180009261
0x180009244  mov     rcx, [rbp+178h]; this
0x18000924b  lea     r8, aWil; "wil"
0x180009252  mov     r9d, eax; char *
0x180009255  mov     edx, 0DEh; void *
0x18000925a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000925f  jmp     short loc_180009225
0x180009261  lea     rcx, [rsp+270h+var_248]
0x180009266  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000926b  movsxd  rcx, [rsp+270h+var_250]
0x180009270  movsxd  rax, [rsp+270h+var_24C]
0x180009275  shl     rcx, 1Fh
0x180009279  or      rcx, rax
0x18000927c  mov     [rdi], rcx
0x18000927f  xor     ebx, ebx
0x180009281  lea     rcx, [rsp+270h+var_240]
0x180009286  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000928b  mov     eax, ebx
0x18000928d  mov     rcx, [rbp+170h+var_20]
0x180009294  xor     rcx, rsp; StackCookie
0x180009297  call    __security_check_cookie
0x18000929c  mov     rbx, [rsp+270h+arg_8]
0x1800092a4  add     rsp, 260h
0x1800092ab  pop     r14
0x1800092ad  pop     rdi
0x1800092ae  pop     rbp
0x1800092af  retn
```
