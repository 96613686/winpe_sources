# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800064e4`
- end: `0x180006686`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006470`

## callees

- `0x180004538`
- `0x180005274`
- `0x180005ca4`
- `0x180005cc4`
- `0x1800061e0`
- `0x18000626c`
- `0x1800064e4`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000654d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800065df`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000654d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800065df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000655d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000655d`

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
0x1800064e4  mov     [rsp-8+arg_8], rbx
0x1800064e9  push    rbp
0x1800064ea  push    rdi
0x1800064eb  push    r14
0x1800064ed  lea     rbp, [rsp-160h]
0x1800064f5  sub     rsp, 260h
0x1800064fc  mov     rax, cs:__security_cookie
0x180006503  xor     rax, rsp
0x180006506  mov     [rbp+170h+var_20], rax
0x18000650d  mov     rdi, r8
0x180006510  mov     qword ptr [r8], 0
0x180006517  mov     r8, rcx; unsigned __int16 *
0x18000651a  mov     r14d, 104h
0x180006520  mov     edx, r14d; unsigned __int64
0x180006523  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006528  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000652d  lea     r8, aP0; "_p0"
0x180006534  mov     edx, r14d; unsigned __int64
0x180006537  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000653c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006541  lea     r8, [rsp+270h+Name]; lpName
0x180006546  xor     edx, edx; bInheritHandle
0x180006548  mov     ecx, 1F0003h; dwDesiredAccess
0x18000654d  call    cs:__imp_OpenSemaphoreW
0x180006553  mov     [rsp+270h+var_240], rax
0x180006558  test    rax, rax
0x18000655b  jnz     short loc_180006583
0x18000655d  call    cs:__imp_GetLastError
0x180006563  cmp     eax, 2
0x180006566  jz      loc_180006655
0x18000656c  mov     rcx, [rbp+178h]; this
0x180006573  lea     edx, [r14-34h]; void *
0x180006577  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000657c  mov     ebx, eax
0x18000657e  jmp     loc_180006657
0x180006583  lea     rdx, [rsp+270h+var_24C]; int *
0x180006588  mov     [rsp+270h+var_24C], 0
0x180006590  mov     rcx, rax; hHandle
0x180006593  mov     [rsp+270h+var_250], 0; int
0x18000659b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800065a0  mov     ebx, eax
0x1800065a2  test    eax, eax
0x1800065a4  jns     short loc_1800065BF
0x1800065a6  mov     rcx, [rbp+178h]; this
0x1800065ad  mov     r9d, eax; char *
0x1800065b0  mov     edx, 0D6h; void *
0x1800065b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800065ba  jmp     loc_180006657
0x1800065bf  lea     r8, asc_18002F620; "h"
0x1800065c6  mov     rdx, r14; unsigned __int64
0x1800065c9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x1800065ce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800065d3  lea     r8, [rsp+270h+Name]; lpName
0x1800065d8  xor     edx, edx; bInheritHandle
0x1800065da  mov     ecx, 1F0003h; dwDesiredAccess
0x1800065df  call    cs:__imp_OpenSemaphoreW
0x1800065e5  mov     [rsp+270h+var_248], rax
0x1800065ea  test    rax, rax
0x1800065ed  jnz     short loc_18000660E
0x1800065ef  mov     rcx, [rbp+178h]; this
0x1800065f6  mov     edx, 0DCh; void *
0x1800065fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006600  mov     ebx, eax
0x180006602  lea     rcx, [rsp+270h+var_248]
0x180006607  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000660c  jmp     short loc_180006657
0x18000660e  lea     rdx, [rsp+270h+var_250]; int *
0x180006613  mov     rcx, rax; hHandle
0x180006616  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000661b  mov     ebx, eax
0x18000661d  test    eax, eax
0x18000661f  jns     short loc_180006637
0x180006621  mov     rcx, [rbp+178h]; this
0x180006628  mov     r9d, eax; char *
0x18000662b  mov     edx, 0DEh; void *
0x180006630  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006635  jmp     short loc_180006602
0x180006637  lea     rcx, [rsp+270h+var_248]
0x18000663c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006641  movsxd  rcx, [rsp+270h+var_250]
0x180006646  movsxd  rax, [rsp+270h+var_24C]
0x18000664b  shl     rcx, 1Fh
0x18000664f  or      rcx, rax
0x180006652  mov     [rdi], rcx
0x180006655  xor     ebx, ebx
0x180006657  lea     rcx, [rsp+270h+var_240]
0x18000665c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006661  mov     eax, ebx
0x180006663  mov     rcx, [rbp+170h+var_20]
0x18000666a  xor     rcx, rsp; StackCookie
0x18000666d  call    __security_check_cookie
0x180006672  mov     rbx, [rsp+270h+arg_8]
0x18000667a  add     rsp, 260h
0x180006681  pop     r14
0x180006683  pop     rdi
0x180006684  pop     rbp
0x180006685  retn
```
