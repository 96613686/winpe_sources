# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180082094`
- end: `0x180082244`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180082010`

## callees

- `0x180043030`
- `0x18007bd18`
- `0x18007f2a8`
- `0x18008164c`
- `0x18008166c`
- `0x180081d2c`
- `0x180082094`
- `0x1800cf080`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008210d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008210d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800820fd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180082196`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800820fd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180082196`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // r9
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  size_t v11; // r9
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0", v5);
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h", v11);
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180082094  mov     [rsp-8+arg_8], rbx
0x180082099  push    rbp
0x18008209a  push    rdi
0x18008209b  push    r14
0x18008209d  lea     rbp, [rsp-160h]
0x1800820a5  sub     rsp, 260h
0x1800820ac  mov     rax, cs:__security_cookie
0x1800820b3  xor     rax, rsp
0x1800820b6  mov     [rbp+170h+var_20], rax
0x1800820bd  mov     rdi, r8
0x1800820c0  mov     qword ptr [r8], 0
0x1800820c7  mov     r8, rcx; unsigned __int16 *
0x1800820ca  mov     r14d, 104h
0x1800820d0  mov     edx, r14d; unsigned __int64
0x1800820d3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800820d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800820dd  lea     r8, aP0; "_p0"
0x1800820e4  mov     edx, r14d; unsigned __int64
0x1800820e7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800820ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800820f1  lea     r8, [rsp+270h+Name]; lpName
0x1800820f6  xor     edx, edx; bInheritHandle
0x1800820f8  mov     ecx, 1F0003h; dwDesiredAccess
0x1800820fd  call    cs:__imp_OpenSemaphoreW
0x180082103  mov     [rsp+270h+var_240], rax
0x180082108  test    rax, rax
0x18008210b  jnz     short loc_180082133
0x18008210d  call    cs:__imp_GetLastError
0x180082113  cmp     eax, 2
0x180082116  jz      loc_180082213
0x18008211c  mov     rcx, [rbp+178h]; this
0x180082123  lea     edx, [r14-34h]; void *
0x180082127  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008212c  mov     ebx, eax
0x18008212e  jmp     loc_180082215
0x180082133  lea     rdx, [rsp+270h+var_24C]; int *
0x180082138  mov     [rsp+270h+var_24C], 0
0x180082140  mov     rcx, rax; hHandle
0x180082143  mov     [rsp+270h+var_250], 0; int
0x18008214b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180082150  mov     ebx, eax
0x180082152  test    eax, eax
0x180082154  jns     short loc_180082176
0x180082156  mov     rcx, [rbp+178h]; this
0x18008215d  lea     r8, aWil; "wil"
0x180082164  mov     r9d, eax; char *
0x180082167  mov     edx, 0D6h; void *
0x18008216c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180082171  jmp     loc_180082215
0x180082176  lea     r8, asc_1800E35D0; "h"
0x18008217d  mov     rdx, r14; unsigned __int64
0x180082180  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180082185  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008218a  lea     r8, [rsp+270h+Name]; lpName
0x18008218f  xor     edx, edx; bInheritHandle
0x180082191  mov     ecx, 1F0003h; dwDesiredAccess
0x180082196  call    cs:__imp_OpenSemaphoreW
0x18008219c  mov     [rsp+270h+var_248], rax
0x1800821a1  test    rax, rax
0x1800821a4  jnz     short loc_1800821C5
0x1800821a6  mov     rcx, [rbp+178h]; this
0x1800821ad  mov     edx, 0DCh; void *
0x1800821b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800821b7  mov     ebx, eax
0x1800821b9  lea     rcx, [rsp+270h+var_248]
0x1800821be  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800821c3  jmp     short loc_180082215
0x1800821c5  lea     rdx, [rsp+270h+var_250]; int *
0x1800821ca  mov     rcx, rax; hHandle
0x1800821cd  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800821d2  mov     ebx, eax
0x1800821d4  test    eax, eax
0x1800821d6  jns     short loc_1800821F5
0x1800821d8  mov     rcx, [rbp+178h]; this
0x1800821df  lea     r8, aWil; "wil"
0x1800821e6  mov     r9d, eax; char *
0x1800821e9  mov     edx, 0DEh; void *
0x1800821ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800821f3  jmp     short loc_1800821B9
0x1800821f5  lea     rcx, [rsp+270h+var_248]
0x1800821fa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800821ff  movsxd  rcx, [rsp+270h+var_250]
0x180082204  movsxd  rax, [rsp+270h+var_24C]
0x180082209  shl     rcx, 1Fh
0x18008220d  or      rcx, rax
0x180082210  mov     [rdi], rcx
0x180082213  xor     ebx, ebx
0x180082215  lea     rcx, [rsp+270h+var_240]
0x18008221a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18008221f  mov     eax, ebx
0x180082221  mov     rcx, [rbp+170h+var_20]
0x180082228  xor     rcx, rsp; StackCookie
0x18008222b  call    __security_check_cookie
0x180082230  mov     rbx, [rsp+270h+arg_8]
0x180082238  add     rsp, 260h
0x18008223f  pop     r14
0x180082241  pop     rdi
0x180082242  pop     rbp
0x180082243  retn
```
