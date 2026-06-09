# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800097f4`
- end: `0x1800099db`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `487`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009758`

## callees

- `0x180004310`
- `0x180005fc0`
- `0x180007374`
- `0x180008b3c`
- `0x180008b68`
- `0x1800092e0`
- `0x18000941c`
- `0x1800097f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009858`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000990c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009858`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000990c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009868`

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
  unsigned int v8; // r8d
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  __int64 v12; // r8
  wil::details *v13; // rax
  unsigned int v14; // r8d
  void *v15; // rdx
  int v16; // eax
  void *v17; // rdx
  __int64 v18; // r8
  char *v20; // [rsp+20h] [rbp-E0h]
  wil::details *v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v24; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v25; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, (size_t)v20);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      LODWORD(v21) = ValueFromSemaphore;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xD6,
        v12,
        "wil::details_abi::SemaphoreValue::TryGetValueInternal",
        "GetValueFromSemaphore(semaphoreLow.get(), &countLow)",
        v21);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v24 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v22);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v17);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      LODWORD(v21) = v16;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0xDE,
        v18,
        "wil::details_abi::SemaphoreValue::TryGetValueInternal",
        "GetValueFromSemaphore(semaphoreHigh.get(), &countHigh)",
        v21);
    }
    else
    {
      LastError = wil::details::in1diag5::Return_GetLastError(
                    retaddr,
                    (void *)0xDC,
                    v14,
                    "wil::details_abi::SemaphoreValue::TryGetValueInternal",
                    "semaphoreHigh",
                    (const char *)v21);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag5::Return_GetLastError(
                retaddr,
                (void *)0xD0,
                v8,
                "wil::details_abi::SemaphoreValue::TryGetValueInternal",
                0,
                (const char *)v21);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x1800097f4  mov     [rsp-8+arg_8], rbx
0x1800097f9  mov     [rsp-8+arg_18], rdi
0x1800097fe  push    rbp
0x1800097ff  lea     rbp, [rsp-170h]
0x180009807  sub     rsp, 270h
0x18000980e  mov     rax, cs:__security_cookie
0x180009815  xor     rax, rsp
0x180009818  mov     [rbp+170h+var_10], rax
0x18000981f  mov     r9, rcx; pszSrc
0x180009822  mov     qword ptr [r8], 0
0x180009829  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000982e  mov     edx, 104h; cchDest
0x180009833  mov     rdi, r8
0x180009836  call    StringCopyWorkerW
0x18000983b  lea     r8, aP0; "_p0"
0x180009842  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180009847  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000984c  lea     r8, [rsp+270h+pszDest]; lpName
0x180009851  xor     edx, edx; bInheritHandle
0x180009853  mov     ecx, 1F0003h; dwDesiredAccess
0x180009858  call    cs:__imp_OpenSemaphoreW
0x18000985e  mov     [rsp+270h+var_230], rax
0x180009863  test    rax, rax
0x180009866  jnz     short loc_18000989F
0x180009868  call    cs:__imp_GetLastError
0x18000986e  cmp     eax, 2
0x180009871  jz      loc_1800099A9
0x180009877  mov     rcx, [rbp+178h]; this
0x18000987e  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x180009885  mov     edx, 0D0h; void *
0x18000988a  mov     [rsp+270h+var_250], 0; char *
0x180009893  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180009898  mov     ebx, eax
0x18000989a  jmp     loc_1800099AB
0x18000989f  lea     rdx, [rsp+270h+var_23C]; int *
0x1800098a4  mov     [rsp+270h+var_23C], 0
0x1800098ac  mov     rcx, rax; hHandle
0x1800098af  mov     [rsp+270h+var_240], 0; int
0x1800098b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800098bc  mov     ebx, eax
0x1800098be  test    eax, eax
0x1800098c0  jns     short loc_1800098EF
0x1800098c2  mov     rcx, [rbp+178h]; this
0x1800098c9  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x1800098d0  mov     dword ptr [rsp+270h+var_248], eax; wil::details *
0x1800098d4  mov     edx, 0D6h; void *
0x1800098d9  lea     rax, aGetvaluefromse_0; "GetValueFromSemaphore(semaphoreLow.get("...
0x1800098e0  mov     [rsp+270h+var_250], rax; char *
0x1800098e5  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800098ea  jmp     loc_1800099AB
0x1800098ef  lea     r8, asc_18000DDAC; "h"
0x1800098f6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800098fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009900  lea     r8, [rsp+270h+pszDest]; lpName
0x180009905  xor     edx, edx; bInheritHandle
0x180009907  mov     ecx, 1F0003h; dwDesiredAccess
0x18000990c  call    cs:__imp_OpenSemaphoreW
0x180009912  mov     [rsp+270h+var_238], rax
0x180009917  test    rax, rax
0x18000991a  jnz     short loc_18000994E
0x18000991c  mov     rcx, [rbp+178h]; this
0x180009923  lea     rax, aSemaphorehigh; "semaphoreHigh"
0x18000992a  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x180009931  mov     [rsp+270h+var_250], rax; char *
0x180009936  mov     edx, 0DCh; void *
0x18000993b  call    ?Return_GetLastError@in1diag5@details@wil@@YAJPEAXIPEBD11@Z; wil::details::in1diag5::Return_GetLastError(void *,uint,char const *,char const *,char const *)
0x180009940  mov     ebx, eax
0x180009942  lea     rcx, [rsp+270h+var_238]
0x180009947  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000994c  jmp     short loc_1800099AB
0x18000994e  lea     rdx, [rsp+270h+var_240]; int *
0x180009953  mov     rcx, rax; hHandle
0x180009956  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000995b  mov     ebx, eax
0x18000995d  test    eax, eax
0x18000995f  jns     short loc_18000998B
0x180009961  mov     rcx, [rbp+178h]; this
0x180009968  lea     r9, aWilDetailsAbiS_1; "wil::details_abi::SemaphoreValue::TryGe"...
0x18000996f  mov     dword ptr [rsp+270h+var_248], eax; wil::details *
0x180009973  mov     edx, 0DEh; void *
0x180009978  lea     rax, aGetvaluefromse; "GetValueFromSemaphore(semaphoreHigh.get"...
0x18000997f  mov     [rsp+270h+var_250], rax; char *
0x180009984  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180009989  jmp     short loc_180009942
0x18000998b  lea     rcx, [rsp+270h+var_238]
0x180009990  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009995  movsxd  rcx, [rsp+270h+var_240]
0x18000999a  movsxd  rax, [rsp+270h+var_23C]
0x18000999f  shl     rcx, 1Fh
0x1800099a3  or      rcx, rax
0x1800099a6  mov     [rdi], rcx
0x1800099a9  xor     ebx, ebx
0x1800099ab  lea     rcx, [rsp+270h+var_230]
0x1800099b0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800099b5  mov     eax, ebx
0x1800099b7  mov     rcx, [rbp+170h+var_10]
0x1800099be  xor     rcx, rsp; StackCookie
0x1800099c1  call    __security_check_cookie
0x1800099c6  lea     r11, [rsp+270h+var_s0]
0x1800099ce  mov     rbx, [r11+18h]
0x1800099d2  mov     rdi, [r11+28h]
0x1800099d6  mov     rsp, r11
0x1800099d9  pop     rbp
0x1800099da  retn
```
