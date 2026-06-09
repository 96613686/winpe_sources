# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18005207c`
- end: `0x18005221e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180052008`

## callees

- `0x18001c360`
- `0x180023708`
- `0x18004f478`
- `0x180050524`
- `0x180051928`
- `0x180051948`
- `0x18005207c`
- `0x180067b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800520f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800520f5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800520e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180052177`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800520e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180052177`

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
0x18005207c  mov     [rsp-8+arg_8], rbx
0x180052081  push    rbp
0x180052082  push    rdi
0x180052083  push    r14
0x180052085  lea     rbp, [rsp-160h]
0x18005208d  sub     rsp, 260h
0x180052094  mov     rax, cs:__security_cookie
0x18005209b  xor     rax, rsp
0x18005209e  mov     [rbp+170h+var_20], rax
0x1800520a5  mov     rdi, r8
0x1800520a8  mov     qword ptr [r8], 0
0x1800520af  mov     r8, rcx; unsigned __int16 *
0x1800520b2  mov     r14d, 104h
0x1800520b8  mov     edx, r14d; unsigned __int64
0x1800520bb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800520c0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800520c5  lea     r8, aP0; "_p0"
0x1800520cc  mov     edx, r14d; unsigned __int64
0x1800520cf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800520d4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800520d9  lea     r8, [rsp+270h+Name]; lpName
0x1800520de  xor     edx, edx; bInheritHandle
0x1800520e0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800520e5  call    cs:__imp_OpenSemaphoreW
0x1800520eb  mov     [rsp+270h+var_240], rax
0x1800520f0  test    rax, rax
0x1800520f3  jnz     short loc_18005211B
0x1800520f5  call    cs:__imp_GetLastError
0x1800520fb  cmp     eax, 2
0x1800520fe  jz      loc_1800521ED
0x180052104  mov     rcx, [rbp+178h]; this
0x18005210b  lea     edx, [r14-34h]; void *
0x18005210f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052114  mov     ebx, eax
0x180052116  jmp     loc_1800521EF
0x18005211b  lea     rdx, [rsp+270h+var_24C]; int *
0x180052120  mov     [rsp+270h+var_24C], 0
0x180052128  mov     rcx, rax; hHandle
0x18005212b  mov     [rsp+270h+var_250], 0; int
0x180052133  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180052138  mov     ebx, eax
0x18005213a  test    eax, eax
0x18005213c  jns     short loc_180052157
0x18005213e  mov     rcx, [rbp+178h]; this
0x180052145  mov     r9d, eax; char *
0x180052148  mov     edx, 0D6h; void *
0x18005214d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052152  jmp     loc_1800521EF
0x180052157  lea     r8, asc_180074CF8; "h"
0x18005215e  mov     rdx, r14; unsigned __int64
0x180052161  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180052166  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005216b  lea     r8, [rsp+270h+Name]; lpName
0x180052170  xor     edx, edx; bInheritHandle
0x180052172  mov     ecx, 1F0003h; dwDesiredAccess
0x180052177  call    cs:__imp_OpenSemaphoreW
0x18005217d  mov     [rsp+270h+var_248], rax
0x180052182  test    rax, rax
0x180052185  jnz     short loc_1800521A6
0x180052187  mov     rcx, [rbp+178h]; this
0x18005218e  mov     edx, 0DCh; void *
0x180052193  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052198  mov     ebx, eax
0x18005219a  lea     rcx, [rsp+270h+var_248]
0x18005219f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800521a4  jmp     short loc_1800521EF
0x1800521a6  lea     rdx, [rsp+270h+var_250]; int *
0x1800521ab  mov     rcx, rax; hHandle
0x1800521ae  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800521b3  mov     ebx, eax
0x1800521b5  test    eax, eax
0x1800521b7  jns     short loc_1800521CF
0x1800521b9  mov     rcx, [rbp+178h]; this
0x1800521c0  mov     r9d, eax; char *
0x1800521c3  mov     edx, 0DEh; void *
0x1800521c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800521cd  jmp     short loc_18005219A
0x1800521cf  lea     rcx, [rsp+270h+var_248]
0x1800521d4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800521d9  movsxd  rcx, [rsp+270h+var_250]
0x1800521de  movsxd  rax, [rsp+270h+var_24C]
0x1800521e3  shl     rcx, 1Fh
0x1800521e7  or      rcx, rax
0x1800521ea  mov     [rdi], rcx
0x1800521ed  xor     ebx, ebx
0x1800521ef  lea     rcx, [rsp+270h+var_240]
0x1800521f4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800521f9  mov     eax, ebx
0x1800521fb  mov     rcx, [rbp+170h+var_20]
0x180052202  xor     rcx, rsp; StackCookie
0x180052205  call    __security_check_cookie
0x18005220a  mov     rbx, [rsp+270h+arg_8]
0x180052212  add     rsp, 260h
0x180052219  pop     r14
0x18005221b  pop     rdi
0x18005221c  pop     rbp
0x18005221d  retn
```
