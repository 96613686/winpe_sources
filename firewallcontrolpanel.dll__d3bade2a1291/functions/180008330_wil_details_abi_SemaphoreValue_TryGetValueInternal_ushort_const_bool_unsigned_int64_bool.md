# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008330`
- end: `0x1800084d2`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006508`

## callees

- `0x1800063fc`
- `0x1800070f4`
- `0x180007bf4`
- `0x180007c14`
- `0x1800080ec`
- `0x180008178`
- `0x180008330`
- `0x180030ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008399`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000842b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008399`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000842b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800083a9`

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
0x180008330  mov     [rsp-8+arg_8], rbx
0x180008335  push    rbp
0x180008336  push    rdi
0x180008337  push    r14
0x180008339  lea     rbp, [rsp-160h]
0x180008341  sub     rsp, 260h
0x180008348  mov     rax, cs:__security_cookie
0x18000834f  xor     rax, rsp
0x180008352  mov     [rbp+170h+var_20], rax
0x180008359  mov     rdi, r8
0x18000835c  mov     qword ptr [r8], 0
0x180008363  mov     r8, rcx; unsigned __int16 *
0x180008366  mov     r14d, 104h
0x18000836c  mov     edx, r14d; unsigned __int64
0x18000836f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008374  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008379  lea     r8, aP0; "_p0"
0x180008380  mov     edx, r14d; unsigned __int64
0x180008383  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180008388  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000838d  lea     r8, [rsp+270h+Name]; lpName
0x180008392  xor     edx, edx; bInheritHandle
0x180008394  mov     ecx, 1F0003h; dwDesiredAccess
0x180008399  call    cs:__imp_OpenSemaphoreW
0x18000839f  mov     [rsp+270h+var_240], rax
0x1800083a4  test    rax, rax
0x1800083a7  jnz     short loc_1800083CF
0x1800083a9  call    cs:__imp_GetLastError
0x1800083af  cmp     eax, 2
0x1800083b2  jz      loc_1800084A1
0x1800083b8  mov     rcx, [rbp+178h]; this
0x1800083bf  lea     edx, [r14-34h]; void *
0x1800083c3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800083c8  mov     ebx, eax
0x1800083ca  jmp     loc_1800084A3
0x1800083cf  lea     rdx, [rsp+270h+var_24C]; int *
0x1800083d4  mov     [rsp+270h+var_24C], 0
0x1800083dc  mov     rcx, rax; hHandle
0x1800083df  mov     [rsp+270h+var_250], 0; int
0x1800083e7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800083ec  mov     ebx, eax
0x1800083ee  test    eax, eax
0x1800083f0  jns     short loc_18000840B
0x1800083f2  mov     rcx, [rbp+178h]; this
0x1800083f9  mov     r9d, eax; char *
0x1800083fc  mov     edx, 0D6h; void *
0x180008401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008406  jmp     loc_1800084A3
0x18000840b  lea     r8, asc_180036C08; "h"
0x180008412  mov     rdx, r14; unsigned __int64
0x180008415  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000841a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000841f  lea     r8, [rsp+270h+Name]; lpName
0x180008424  xor     edx, edx; bInheritHandle
0x180008426  mov     ecx, 1F0003h; dwDesiredAccess
0x18000842b  call    cs:__imp_OpenSemaphoreW
0x180008431  mov     [rsp+270h+var_248], rax
0x180008436  test    rax, rax
0x180008439  jnz     short loc_18000845A
0x18000843b  mov     rcx, [rbp+178h]; this
0x180008442  mov     edx, 0DCh; void *
0x180008447  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000844c  mov     ebx, eax
0x18000844e  lea     rcx, [rsp+270h+var_248]
0x180008453  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008458  jmp     short loc_1800084A3
0x18000845a  lea     rdx, [rsp+270h+var_250]; int *
0x18000845f  mov     rcx, rax; hHandle
0x180008462  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008467  mov     ebx, eax
0x180008469  test    eax, eax
0x18000846b  jns     short loc_180008483
0x18000846d  mov     rcx, [rbp+178h]; this
0x180008474  mov     r9d, eax; char *
0x180008477  mov     edx, 0DEh; void *
0x18000847c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008481  jmp     short loc_18000844E
0x180008483  lea     rcx, [rsp+270h+var_248]
0x180008488  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000848d  movsxd  rcx, [rsp+270h+var_250]
0x180008492  movsxd  rax, [rsp+270h+var_24C]
0x180008497  shl     rcx, 1Fh
0x18000849b  or      rcx, rax
0x18000849e  mov     [rdi], rcx
0x1800084a1  xor     ebx, ebx
0x1800084a3  lea     rcx, [rsp+270h+var_240]
0x1800084a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800084ad  mov     eax, ebx
0x1800084af  mov     rcx, [rbp+170h+var_20]
0x1800084b6  xor     rcx, rsp; StackCookie
0x1800084b9  call    __security_check_cookie
0x1800084be  mov     rbx, [rsp+270h+arg_8]
0x1800084c6  add     rsp, 260h
0x1800084cd  pop     r14
0x1800084cf  pop     rdi
0x1800084d0  pop     rbp
0x1800084d1  retn
```
