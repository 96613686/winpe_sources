# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1801455c8`
- end: `0x18014578a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `450`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180145544`

## callees

- `0x18013ce80`
- `0x180141a30`
- `0x180143078`
- `0x180144c30`
- `0x180144c50`
- `0x1801450dc`
- `0x180145130`
- `0x1801455c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18014562c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1801456d4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18014562c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1801456d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180145642`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
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
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
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
0x1801455c8  mov     [rsp-8+arg_8], rbx
0x1801455cd  mov     [rsp-8+arg_18], rdi
0x1801455d2  push    rbp
0x1801455d3  lea     rbp, [rsp-160h]
0x1801455db  sub     rsp, 260h
0x1801455e2  mov     rax, cs:__security_cookie
0x1801455e9  xor     rax, rsp
0x1801455ec  mov     [rbp+160h+var_10], rax
0x1801455f3  mov     rdi, r8
0x1801455f6  mov     qword ptr [r8], 0
0x1801455fd  mov     r8, rcx; unsigned __int16 *
0x180145600  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180145605  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18014560a  lea     r8, aP0; "_p0"
0x180145611  mov     edx, 104h; unsigned __int64
0x180145616  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18014561b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180145620  lea     r8, [rsp+260h+Name]; lpName
0x180145625  xor     edx, edx; bInheritHandle
0x180145627  mov     ecx, 1F0003h; dwDesiredAccess
0x18014562c  call    cs:__imp_OpenSemaphoreW
0x180145633  nop     dword ptr [rax+rax+00h]
0x180145638  mov     [rsp+260h+var_230], rax
0x18014563d  test    rax, rax
0x180145640  jnz     short loc_18014566F
0x180145642  call    cs:__imp_GetLastError
0x180145649  nop     dword ptr [rax+rax+00h]
0x18014564e  cmp     eax, 2
0x180145651  jz      loc_180145757
0x180145657  mov     rcx, [rbp+168h]; this
0x18014565e  mov     edx, 0D0h; void *
0x180145663  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180145668  mov     ebx, eax
0x18014566a  jmp     loc_180145759
0x18014566f  lea     rdx, [rsp+260h+var_23C]; int *
0x180145674  mov     [rsp+260h+var_23C], 0
0x18014567c  mov     rcx, rax; hHandle
0x18014567f  mov     [rsp+260h+var_240], 0; int
0x180145687  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18014568c  mov     ebx, eax
0x18014568e  test    eax, eax
0x180145690  jns     short loc_1801456B2
0x180145692  mov     rcx, [rbp+168h]; this
0x180145699  lea     r8, aWil; "wil"
0x1801456a0  mov     r9d, eax; char *
0x1801456a3  mov     edx, 0D6h; void *
0x1801456a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801456ad  jmp     loc_180145759
0x1801456b2  lea     r8, asc_1802ADC30; "h"
0x1801456b9  mov     edx, 104h; unsigned __int64
0x1801456be  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1801456c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801456c8  lea     r8, [rsp+260h+Name]; lpName
0x1801456cd  xor     edx, edx; bInheritHandle
0x1801456cf  mov     ecx, 1F0003h; dwDesiredAccess
0x1801456d4  call    cs:__imp_OpenSemaphoreW
0x1801456db  nop     dword ptr [rax+rax+00h]
0x1801456e0  mov     [rsp+260h+var_238], rax
0x1801456e5  test    rax, rax
0x1801456e8  jnz     short loc_180145709
0x1801456ea  mov     rcx, [rbp+168h]; this
0x1801456f1  mov     edx, 0DCh; void *
0x1801456f6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801456fb  mov     ebx, eax
0x1801456fd  lea     rcx, [rsp+260h+var_238]
0x180145702  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180145707  jmp     short loc_180145759
0x180145709  lea     rdx, [rsp+260h+var_240]; int *
0x18014570e  mov     rcx, rax; hHandle
0x180145711  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180145716  mov     ebx, eax
0x180145718  test    eax, eax
0x18014571a  jns     short loc_180145739
0x18014571c  mov     rcx, [rbp+168h]; this
0x180145723  lea     r8, aWil; "wil"
0x18014572a  mov     r9d, eax; char *
0x18014572d  mov     edx, 0DEh; void *
0x180145732  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180145737  jmp     short loc_1801456FD
0x180145739  lea     rcx, [rsp+260h+var_238]
0x18014573e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180145743  movsxd  rcx, [rsp+260h+var_240]
0x180145748  movsxd  rax, [rsp+260h+var_23C]
0x18014574d  shl     rcx, 1Fh
0x180145751  or      rcx, rax
0x180145754  mov     [rdi], rcx
0x180145757  xor     ebx, ebx
0x180145759  lea     rcx, [rsp+260h+var_230]
0x18014575e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180145763  mov     eax, ebx
0x180145765  mov     rcx, [rbp+160h+var_10]
0x18014576c  xor     rcx, rsp; StackCookie
0x18014576f  call    __security_check_cookie
0x180145774  lea     r11, [rsp+260h+var_s0]
0x18014577c  mov     rbx, [r11+18h]
0x180145780  mov     rdi, [r11+28h]
0x180145784  mov     rsp, r11
0x180145787  pop     rbp
0x180145788  retn
```
