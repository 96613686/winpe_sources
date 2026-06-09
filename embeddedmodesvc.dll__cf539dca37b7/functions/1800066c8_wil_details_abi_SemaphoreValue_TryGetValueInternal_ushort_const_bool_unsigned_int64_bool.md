# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800066c8`
- end: `0x180006880`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180004628`

## callees

- `0x180002b10`
- `0x1800044e0`
- `0x180005274`
- `0x180005fa4`
- `0x180005fc4`
- `0x1800064e0`
- `0x1800065c0`
- `0x1800066c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000672c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800067ca`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000672c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800067ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000673c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000673c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  size_t v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v22; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v23; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v18);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v23 = v6;
  if ( v6 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v19);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v22 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v20);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v16);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v23,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x1800066c8  mov     [rsp-8+arg_8], rbx
0x1800066cd  mov     [rsp-8+arg_18], rdi
0x1800066d2  push    rbp
0x1800066d3  lea     rbp, [rsp-170h]
0x1800066db  sub     rsp, 270h
0x1800066e2  mov     rax, cs:__security_cookie
0x1800066e9  xor     rax, rsp
0x1800066ec  mov     [rbp+170h+var_10], rax
0x1800066f3  mov     r9, rcx; pszSrc
0x1800066f6  mov     qword ptr [r8], 0
0x1800066fd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180006702  mov     edx, 104h; cchDest
0x180006707  mov     rdi, r8
0x18000670a  call    StringCopyWorkerW
0x18000670f  lea     r8, aP0; "_p0"
0x180006716  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000671b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006720  lea     r8, [rsp+270h+pszDest]; lpName
0x180006725  xor     edx, edx; bInheritHandle
0x180006727  mov     ecx, 1F0003h; dwDesiredAccess
0x18000672c  call    cs:__imp_OpenSemaphoreW
0x180006732  mov     [rsp+270h+var_230], rax
0x180006737  test    rax, rax
0x18000673a  jnz     short loc_18000676A
0x18000673c  call    cs:__imp_GetLastError
0x180006742  cmp     eax, 2
0x180006745  jz      loc_18000684E
0x18000674b  mov     rcx, [rbp+178h]; this
0x180006752  lea     r8, aWil; "wil"
0x180006759  mov     edx, 0D0h; void *
0x18000675e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006763  mov     ebx, eax
0x180006765  jmp     loc_180006850
0x18000676a  lea     rdx, [rsp+270h+var_23C]; int *
0x18000676f  mov     [rsp+270h+var_23C], 0
0x180006777  mov     rcx, rax; hHandle
0x18000677a  mov     [rsp+270h+var_240], 0
0x180006782  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006787  mov     ebx, eax
0x180006789  test    eax, eax
0x18000678b  jns     short loc_1800067AD
0x18000678d  mov     rcx, [rbp+178h]; this
0x180006794  lea     r8, aWil; "wil"
0x18000679b  mov     r9d, eax; char *
0x18000679e  mov     edx, 0D6h; void *
0x1800067a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800067a8  jmp     loc_180006850
0x1800067ad  lea     r8, asc_18001DE68; "h"
0x1800067b4  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800067b9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800067be  lea     r8, [rsp+270h+pszDest]; lpName
0x1800067c3  xor     edx, edx; bInheritHandle
0x1800067c5  mov     ecx, 1F0003h; dwDesiredAccess
0x1800067ca  call    cs:__imp_OpenSemaphoreW
0x1800067d0  mov     [rsp+270h+var_238], rax
0x1800067d5  test    rax, rax
0x1800067d8  jnz     short loc_180006800
0x1800067da  mov     rcx, [rbp+178h]; this
0x1800067e1  lea     r8, aWil; "wil"
0x1800067e8  mov     edx, 0DCh; void *
0x1800067ed  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800067f2  mov     ebx, eax
0x1800067f4  lea     rcx, [rsp+270h+var_238]
0x1800067f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800067fe  jmp     short loc_180006850
0x180006800  lea     rdx, [rsp+270h+var_240]; int *
0x180006805  mov     rcx, rax; hHandle
0x180006808  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000680d  mov     ebx, eax
0x18000680f  test    eax, eax
0x180006811  jns     short loc_180006830
0x180006813  mov     rcx, [rbp+178h]; this
0x18000681a  lea     r8, aWil; "wil"
0x180006821  mov     r9d, eax; char *
0x180006824  mov     edx, 0DEh; void *
0x180006829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000682e  jmp     short loc_1800067F4
0x180006830  lea     rcx, [rsp+270h+var_238]
0x180006835  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000683a  movsxd  rcx, [rsp+270h+var_240]
0x18000683f  movsxd  rax, [rsp+270h+var_23C]
0x180006844  shl     rcx, 1Fh
0x180006848  or      rcx, rax
0x18000684b  mov     [rdi], rcx
0x18000684e  xor     ebx, ebx
0x180006850  lea     rcx, [rsp+270h+var_230]
0x180006855  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000685a  mov     eax, ebx
0x18000685c  mov     rcx, [rbp+170h+var_10]
0x180006863  xor     rcx, rsp; StackCookie
0x180006866  call    __security_check_cookie
0x18000686b  lea     r11, [rsp+270h+var_s0]
0x180006873  mov     rbx, [r11+18h]
0x180006877  mov     rdi, [r11+28h]
0x18000687b  mov     rsp, r11
0x18000687e  pop     rbp
0x18000687f  retn
```
