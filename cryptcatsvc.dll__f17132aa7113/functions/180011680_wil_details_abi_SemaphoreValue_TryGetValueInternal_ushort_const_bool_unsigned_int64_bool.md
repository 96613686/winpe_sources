# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180011680`
- end: `0x180011822`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001160c`

## callees

- `0x180004170`
- `0x1800041ec`
- `0x18000b238`
- `0x18000be40`
- `0x18000de20`
- `0x18000f214`
- `0x180010a6c`
- `0x180011680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800116e9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001177b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800116e9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001177b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116f9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800116f9`

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
0x180011680  mov     [rsp-8+arg_8], rbx
0x180011685  push    rbp
0x180011686  push    rdi
0x180011687  push    r14
0x180011689  lea     rbp, [rsp-160h]
0x180011691  sub     rsp, 260h
0x180011698  mov     rax, cs:__security_cookie
0x18001169f  xor     rax, rsp
0x1800116a2  mov     [rbp+170h+var_20], rax
0x1800116a9  mov     rdi, r8
0x1800116ac  mov     qword ptr [r8], 0
0x1800116b3  mov     r8, rcx; unsigned __int16 *
0x1800116b6  mov     r14d, 104h
0x1800116bc  mov     edx, r14d; unsigned __int64
0x1800116bf  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800116c4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800116c9  lea     r8, aP0; "_p0"
0x1800116d0  mov     edx, r14d; unsigned __int64
0x1800116d3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800116d8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800116dd  lea     r8, [rsp+270h+Name]; lpName
0x1800116e2  xor     edx, edx; bInheritHandle
0x1800116e4  mov     ecx, 1F0003h; dwDesiredAccess
0x1800116e9  call    cs:__imp_OpenSemaphoreW
0x1800116ef  mov     [rsp+270h+var_240], rax
0x1800116f4  test    rax, rax
0x1800116f7  jnz     short loc_18001171F
0x1800116f9  call    cs:__imp_GetLastError
0x1800116ff  cmp     eax, 2
0x180011702  jz      loc_1800117F1
0x180011708  mov     rcx, [rbp+178h]; this
0x18001170f  lea     edx, [r14-34h]; void *
0x180011713  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011718  mov     ebx, eax
0x18001171a  jmp     loc_1800117F3
0x18001171f  lea     rdx, [rsp+270h+var_24C]; int *
0x180011724  mov     [rsp+270h+var_24C], 0
0x18001172c  mov     rcx, rax; hHandle
0x18001172f  mov     [rsp+270h+var_250], 0; int
0x180011737  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001173c  mov     ebx, eax
0x18001173e  test    eax, eax
0x180011740  jns     short loc_18001175B
0x180011742  mov     rcx, [rbp+178h]; this
0x180011749  mov     r9d, eax; char *
0x18001174c  mov     edx, 0D6h; void *
0x180011751  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011756  jmp     loc_1800117F3
0x18001175b  lea     r8, asc_180025A10; "h"
0x180011762  mov     rdx, r14; unsigned __int64
0x180011765  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001176a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001176f  lea     r8, [rsp+270h+Name]; lpName
0x180011774  xor     edx, edx; bInheritHandle
0x180011776  mov     ecx, 1F0003h; dwDesiredAccess
0x18001177b  call    cs:__imp_OpenSemaphoreW
0x180011781  mov     [rsp+270h+var_248], rax
0x180011786  test    rax, rax
0x180011789  jnz     short loc_1800117AA
0x18001178b  mov     rcx, [rbp+178h]; this
0x180011792  mov     edx, 0DCh; void *
0x180011797  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001179c  mov     ebx, eax
0x18001179e  lea     rcx, [rsp+270h+var_248]
0x1800117a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800117a8  jmp     short loc_1800117F3
0x1800117aa  lea     rdx, [rsp+270h+var_250]; int *
0x1800117af  mov     rcx, rax; hHandle
0x1800117b2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800117b7  mov     ebx, eax
0x1800117b9  test    eax, eax
0x1800117bb  jns     short loc_1800117D3
0x1800117bd  mov     rcx, [rbp+178h]; this
0x1800117c4  mov     r9d, eax; char *
0x1800117c7  mov     edx, 0DEh; void *
0x1800117cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800117d1  jmp     short loc_18001179E
0x1800117d3  lea     rcx, [rsp+270h+var_248]
0x1800117d8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800117dd  movsxd  rcx, [rsp+270h+var_250]
0x1800117e2  movsxd  rax, [rsp+270h+var_24C]
0x1800117e7  shl     rcx, 1Fh
0x1800117eb  or      rcx, rax
0x1800117ee  mov     [rdi], rcx
0x1800117f1  xor     ebx, ebx
0x1800117f3  lea     rcx, [rsp+270h+var_240]
0x1800117f8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800117fd  mov     eax, ebx
0x1800117ff  mov     rcx, [rbp+170h+var_20]
0x180011806  xor     rcx, rsp; StackCookie
0x180011809  call    __security_check_cookie
0x18001180e  mov     rbx, [rsp+270h+arg_8]
0x180011816  add     rsp, 260h
0x18001181d  pop     r14
0x18001181f  pop     rdi
0x180011820  pop     rbp
0x180011821  retn
```
