# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003dffc`
- end: `0x18003e1cd`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003df78`

## callees

- `0x18002dc28`
- `0x180038270`
- `0x18003ae60`
- `0x18003c29c`
- `0x18003d434`
- `0x18003dae8`
- `0x18003db74`
- `0x18003dffc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003e065`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003e111`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003e065`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003e111`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e07b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e07b`

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
0x18003dffc  mov     [rsp-8+arg_8], rbx
0x18003e001  push    rbp
0x18003e002  push    rdi
0x18003e003  push    r14
0x18003e005  lea     rbp, [rsp-160h]
0x18003e00d  sub     rsp, 260h
0x18003e014  mov     rax, cs:__security_cookie
0x18003e01b  xor     rax, rsp
0x18003e01e  mov     [rbp+170h+var_20], rax
0x18003e025  mov     rdi, r8
0x18003e028  mov     qword ptr [r8], 0
0x18003e02f  mov     r8, rcx; unsigned __int16 *
0x18003e032  mov     r14d, 104h
0x18003e038  mov     edx, r14d; unsigned __int64
0x18003e03b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003e040  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003e045  lea     r8, aP0; "_p0"
0x18003e04c  mov     edx, r14d; unsigned __int64
0x18003e04f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003e054  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003e059  lea     r8, [rsp+270h+Name]; lpName
0x18003e05e  xor     edx, edx; bInheritHandle
0x18003e060  mov     ecx, 1F0003h; dwDesiredAccess
0x18003e065  call    cs:__imp_OpenSemaphoreW
0x18003e06c  nop     dword ptr [rax+rax+00h]
0x18003e071  mov     [rsp+270h+var_240], rax
0x18003e076  test    rax, rax
0x18003e079  jnz     short loc_18003E0AE
0x18003e07b  call    cs:__imp_GetLastError
0x18003e082  nop     dword ptr [rax+rax+00h]
0x18003e087  cmp     eax, 2
0x18003e08a  jz      loc_18003E19B
0x18003e090  mov     rcx, [rbp+178h]; this
0x18003e097  lea     r8, aWil; "wil"
0x18003e09e  lea     edx, [r14-34h]; void *
0x18003e0a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e0a7  mov     ebx, eax
0x18003e0a9  jmp     loc_18003E19D
0x18003e0ae  lea     rdx, [rsp+270h+var_24C]; int *
0x18003e0b3  mov     [rsp+270h+var_24C], 0
0x18003e0bb  mov     rcx, rax; hHandle
0x18003e0be  mov     [rsp+270h+var_250], 0; int
0x18003e0c6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003e0cb  mov     ebx, eax
0x18003e0cd  test    eax, eax
0x18003e0cf  jns     short loc_18003E0F1
0x18003e0d1  mov     rcx, [rbp+178h]; this
0x18003e0d8  lea     r8, aWil; "wil"
0x18003e0df  mov     r9d, eax; char *
0x18003e0e2  mov     edx, 0D6h; void *
0x18003e0e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e0ec  jmp     loc_18003E19D
0x18003e0f1  lea     r8, asc_180089368; "h"
0x18003e0f8  mov     rdx, r14; unsigned __int64
0x18003e0fb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18003e100  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003e105  lea     r8, [rsp+270h+Name]; lpName
0x18003e10a  xor     edx, edx; bInheritHandle
0x18003e10c  mov     ecx, 1F0003h; dwDesiredAccess
0x18003e111  call    cs:__imp_OpenSemaphoreW
0x18003e118  nop     dword ptr [rax+rax+00h]
0x18003e11d  mov     [rsp+270h+var_248], rax
0x18003e122  test    rax, rax
0x18003e125  jnz     short loc_18003E14D
0x18003e127  mov     rcx, [rbp+178h]; this
0x18003e12e  lea     r8, aWil; "wil"
0x18003e135  mov     edx, 0DCh; void *
0x18003e13a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e13f  mov     ebx, eax
0x18003e141  lea     rcx, [rsp+270h+var_248]
0x18003e146  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003e14b  jmp     short loc_18003E19D
0x18003e14d  lea     rdx, [rsp+270h+var_250]; int *
0x18003e152  mov     rcx, rax; hHandle
0x18003e155  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003e15a  mov     ebx, eax
0x18003e15c  test    eax, eax
0x18003e15e  jns     short loc_18003E17D
0x18003e160  mov     rcx, [rbp+178h]; this
0x18003e167  lea     r8, aWil; "wil"
0x18003e16e  mov     r9d, eax; char *
0x18003e171  mov     edx, 0DEh; void *
0x18003e176  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e17b  jmp     short loc_18003E141
0x18003e17d  lea     rcx, [rsp+270h+var_248]
0x18003e182  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003e187  movsxd  rcx, [rsp+270h+var_250]
0x18003e18c  movsxd  rax, [rsp+270h+var_24C]
0x18003e191  shl     rcx, 1Fh
0x18003e195  or      rcx, rax
0x18003e198  mov     [rdi], rcx
0x18003e19b  xor     ebx, ebx
0x18003e19d  lea     rcx, [rsp+270h+var_240]
0x18003e1a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003e1a7  mov     eax, ebx
0x18003e1a9  mov     rcx, [rbp+170h+var_20]
0x18003e1b0  xor     rcx, rsp; StackCookie
0x18003e1b3  call    __security_check_cookie
0x18003e1b8  mov     rbx, [rsp+270h+arg_8]
0x18003e1c0  add     rsp, 260h
0x18003e1c7  pop     r14
0x18003e1c9  pop     rdi
0x18003e1ca  pop     rbp
0x18003e1cb  retn
```
