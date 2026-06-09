# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006fa0`
- end: `0x180007142`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006f2c`

## callees

- `0x180003418`
- `0x1800048e4`
- `0x1800062ec`
- `0x18000630c`
- `0x1800069d4`
- `0x180006a54`
- `0x180006fa0`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007019`
- `KERNEL32!GetLastError` at `0x180007019`
- `KERNEL32!OpenSemaphoreW` at `0x180007009`
- `KERNEL32!OpenSemaphoreW` at `0x18000709b`
- `KERNEL32!OpenSemaphoreW` at `0x180007009`
- `KERNEL32!OpenSemaphoreW` at `0x18000709b`

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
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180006fa0  mov     [rsp-8+arg_8], rbx
0x180006fa5  push    rbp
0x180006fa6  push    rdi
0x180006fa7  push    r14
0x180006fa9  lea     rbp, [rsp-160h]
0x180006fb1  sub     rsp, 260h
0x180006fb8  mov     rax, cs:__security_cookie
0x180006fbf  xor     rax, rsp
0x180006fc2  mov     [rbp+170h+var_20], rax
0x180006fc9  mov     rdi, r8
0x180006fcc  mov     qword ptr [r8], 0
0x180006fd3  mov     r8, rcx; unsigned __int16 *
0x180006fd6  mov     r14d, 104h
0x180006fdc  mov     edx, r14d; unsigned __int64
0x180006fdf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006fe4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006fe9  lea     r8, aP0; "_p0"
0x180006ff0  mov     edx, r14d; unsigned __int64
0x180006ff3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006ff8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006ffd  lea     r8, [rsp+270h+Name]; lpName
0x180007002  xor     edx, edx; bInheritHandle
0x180007004  mov     ecx, 1F0003h; dwDesiredAccess
0x180007009  call    cs:__imp_OpenSemaphoreW
0x18000700f  mov     [rsp+270h+var_240], rax
0x180007014  test    rax, rax
0x180007017  jnz     short loc_18000703F
0x180007019  call    cs:__imp_GetLastError
0x18000701f  cmp     eax, 2
0x180007022  jz      loc_180007111
0x180007028  mov     rcx, [rbp+178h]; this
0x18000702f  lea     edx, [r14-34h]; void *
0x180007033  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007038  mov     ebx, eax
0x18000703a  jmp     loc_180007113
0x18000703f  lea     rdx, [rsp+270h+var_24C]; int *
0x180007044  mov     [rsp+270h+var_24C], 0
0x18000704c  mov     rcx, rax; hHandle
0x18000704f  mov     [rsp+270h+var_250], 0; int
0x180007057  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000705c  mov     ebx, eax
0x18000705e  test    eax, eax
0x180007060  jns     short loc_18000707B
0x180007062  mov     rcx, [rbp+178h]; this
0x180007069  mov     r9d, eax; char *
0x18000706c  mov     edx, 0D6h; void *
0x180007071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007076  jmp     loc_180007113
0x18000707b  lea     r8, asc_180046A58; "h"
0x180007082  mov     rdx, r14; unsigned __int64
0x180007085  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000708a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000708f  lea     r8, [rsp+270h+Name]; lpName
0x180007094  xor     edx, edx; bInheritHandle
0x180007096  mov     ecx, 1F0003h; dwDesiredAccess
0x18000709b  call    cs:__imp_OpenSemaphoreW
0x1800070a1  mov     [rsp+270h+var_248], rax
0x1800070a6  test    rax, rax
0x1800070a9  jnz     short loc_1800070CA
0x1800070ab  mov     rcx, [rbp+178h]; this
0x1800070b2  mov     edx, 0DCh; void *
0x1800070b7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800070bc  mov     ebx, eax
0x1800070be  lea     rcx, [rsp+270h+var_248]
0x1800070c3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800070c8  jmp     short loc_180007113
0x1800070ca  lea     rdx, [rsp+270h+var_250]; int *
0x1800070cf  mov     rcx, rax; hHandle
0x1800070d2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800070d7  mov     ebx, eax
0x1800070d9  test    eax, eax
0x1800070db  jns     short loc_1800070F3
0x1800070dd  mov     rcx, [rbp+178h]; this
0x1800070e4  mov     r9d, eax; char *
0x1800070e7  mov     edx, 0DEh; void *
0x1800070ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800070f1  jmp     short loc_1800070BE
0x1800070f3  lea     rcx, [rsp+270h+var_248]
0x1800070f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800070fd  movsxd  rcx, [rsp+270h+var_250]
0x180007102  movsxd  rax, [rsp+270h+var_24C]
0x180007107  shl     rcx, 1Fh
0x18000710b  or      rcx, rax
0x18000710e  mov     [rdi], rcx
0x180007111  xor     ebx, ebx
0x180007113  lea     rcx, [rsp+270h+var_240]
0x180007118  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000711d  mov     eax, ebx
0x18000711f  mov     rcx, [rbp+170h+var_20]
0x180007126  xor     rcx, rsp; StackCookie
0x180007129  call    __security_check_cookie
0x18000712e  mov     rbx, [rsp+270h+arg_8]
0x180007136  add     rsp, 260h
0x18000713d  pop     r14
0x18000713f  pop     rdi
0x180007140  pop     rbp
0x180007141  retn
```
