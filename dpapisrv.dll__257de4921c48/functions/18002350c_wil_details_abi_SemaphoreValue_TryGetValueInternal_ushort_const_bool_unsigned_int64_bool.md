# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002350c`
- end: `0x1800236dd`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180023488`

## callees

- `0x180010d78`
- `0x1800123e8`
- `0x18001c760`
- `0x18001c808`
- `0x18001d810`
- `0x18001f810`
- `0x18002153c`
- `0x18002350c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180023575`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180023621`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180023575`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180023621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002358b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002358b`

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
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v11);
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
0x18002350c  mov     [rsp-8+arg_8], rbx
0x180023511  push    rbp
0x180023512  push    rdi
0x180023513  push    r14
0x180023515  lea     rbp, [rsp-160h]
0x18002351d  sub     rsp, 260h
0x180023524  mov     rax, cs:__security_cookie
0x18002352b  xor     rax, rsp
0x18002352e  mov     [rbp+170h+var_20], rax
0x180023535  mov     rdi, r8
0x180023538  mov     qword ptr [r8], 0
0x18002353f  mov     r8, rcx; unsigned __int16 *
0x180023542  mov     r14d, 104h
0x180023548  mov     edx, r14d; unsigned __int64
0x18002354b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023550  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023555  lea     r8, aP0; "_p0"
0x18002355c  mov     edx, r14d; unsigned __int64
0x18002355f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023564  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023569  lea     r8, [rsp+270h+Name]; lpName
0x18002356e  xor     edx, edx; bInheritHandle
0x180023570  mov     ecx, 1F0003h; dwDesiredAccess
0x180023575  call    cs:__imp_OpenSemaphoreW
0x18002357c  nop     dword ptr [rax+rax+00h]
0x180023581  mov     [rsp+270h+var_240], rax
0x180023586  test    rax, rax
0x180023589  jnz     short loc_1800235BE
0x18002358b  call    cs:__imp_GetLastError
0x180023592  nop     dword ptr [rax+rax+00h]
0x180023597  cmp     eax, 2
0x18002359a  jz      loc_1800236AB
0x1800235a0  mov     rcx, [rbp+178h]; this
0x1800235a7  lea     r8, aWil; "wil"
0x1800235ae  lea     edx, [r14-34h]; void *
0x1800235b2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800235b7  mov     ebx, eax
0x1800235b9  jmp     loc_1800236AD
0x1800235be  lea     rdx, [rsp+270h+var_24C]; int *
0x1800235c3  mov     [rsp+270h+var_24C], 0
0x1800235cb  mov     rcx, rax; hHandle
0x1800235ce  mov     [rsp+270h+var_250], 0; int
0x1800235d6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800235db  mov     ebx, eax
0x1800235dd  test    eax, eax
0x1800235df  jns     short loc_180023601
0x1800235e1  mov     rcx, [rbp+178h]; this
0x1800235e8  lea     r8, aWil; "wil"
0x1800235ef  mov     r9d, eax; char *
0x1800235f2  mov     edx, 0D6h; void *
0x1800235f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800235fc  jmp     loc_1800236AD
0x180023601  lea     r8, asc_180042788; "h"
0x180023608  mov     rdx, r14; unsigned __int64
0x18002360b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180023610  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180023615  lea     r8, [rsp+270h+Name]; lpName
0x18002361a  xor     edx, edx; bInheritHandle
0x18002361c  mov     ecx, 1F0003h; dwDesiredAccess
0x180023621  call    cs:__imp_OpenSemaphoreW
0x180023628  nop     dword ptr [rax+rax+00h]
0x18002362d  mov     [rsp+270h+var_248], rax
0x180023632  test    rax, rax
0x180023635  jnz     short loc_18002365D
0x180023637  mov     rcx, [rbp+178h]; this
0x18002363e  lea     r8, aWil; "wil"
0x180023645  mov     edx, 0DCh; void *
0x18002364a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002364f  mov     ebx, eax
0x180023651  lea     rcx, [rsp+270h+var_248]
0x180023656  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002365b  jmp     short loc_1800236AD
0x18002365d  lea     rdx, [rsp+270h+var_250]; int *
0x180023662  mov     rcx, rax; hHandle
0x180023665  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002366a  mov     ebx, eax
0x18002366c  test    eax, eax
0x18002366e  jns     short loc_18002368D
0x180023670  mov     rcx, [rbp+178h]; this
0x180023677  lea     r8, aWil; "wil"
0x18002367e  mov     r9d, eax; char *
0x180023681  mov     edx, 0DEh; void *
0x180023686  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002368b  jmp     short loc_180023651
0x18002368d  lea     rcx, [rsp+270h+var_248]
0x180023692  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180023697  movsxd  rcx, [rsp+270h+var_250]
0x18002369c  movsxd  rax, [rsp+270h+var_24C]
0x1800236a1  shl     rcx, 1Fh
0x1800236a5  or      rcx, rax
0x1800236a8  mov     [rdi], rcx
0x1800236ab  xor     ebx, ebx
0x1800236ad  lea     rcx, [rsp+270h+var_240]
0x1800236b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800236b7  mov     eax, ebx
0x1800236b9  mov     rcx, [rbp+170h+var_20]
0x1800236c0  xor     rcx, rsp; StackCookie
0x1800236c3  call    __security_check_cookie
0x1800236c8  mov     rbx, [rsp+270h+arg_8]
0x1800236d0  add     rsp, 260h
0x1800236d7  pop     r14
0x1800236d9  pop     rdi
0x1800236da  pop     rbp
0x1800236db  retn
```
