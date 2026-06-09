# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18007caec`
- end: `0x18007cc9b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18007ca74`

## callees

- `0x180078090`
- `0x180079bf0`
- `0x18007c0e4`
- `0x18007c104`
- `0x18007c658`
- `0x18007c7a8`
- `0x18007caec`
- `0x180093c00`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007cb66`
- `KERNEL32!GetLastError` at `0x18007cb66`
- `KERNEL32!OpenSemaphoreW` at `0x18007cb50`
- `KERNEL32!OpenSemaphoreW` at `0x18007cbec`
- `KERNEL32!OpenSemaphoreW` at `0x18007cb50`
- `KERNEL32!OpenSemaphoreW` at `0x18007cbec`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x18007caec  mov     [rsp-8+arg_8], rbx
0x18007caf1  mov     [rsp-8+arg_18], rdi
0x18007caf6  push    rbp
0x18007caf7  lea     rbp, [rsp-170h]
0x18007caff  sub     rsp, 270h
0x18007cb06  mov     rax, cs:__security_cookie
0x18007cb0d  xor     rax, rsp
0x18007cb10  mov     [rbp+170h+var_10], rax
0x18007cb17  mov     r9, rcx; pszSrc
0x18007cb1a  mov     qword ptr [r8], 0
0x18007cb21  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18007cb26  mov     edx, 104h; cchDest
0x18007cb2b  mov     rdi, r8
0x18007cb2e  call    StringCopyWorkerW
0x18007cb33  lea     r8, aP0; "_p0"
0x18007cb3a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18007cb3f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007cb44  lea     r8, [rsp+270h+pszDest]; lpName
0x18007cb49  xor     edx, edx; bInheritHandle
0x18007cb4b  mov     ecx, 1F0003h; dwDesiredAccess
0x18007cb50  call    cs:__imp_OpenSemaphoreW
0x18007cb57  nop     dword ptr [rax+rax+00h]
0x18007cb5c  mov     [rsp+270h+var_230], rax
0x18007cb61  test    rax, rax
0x18007cb64  jnz     short loc_18007CB93
0x18007cb66  call    cs:__imp_GetLastError
0x18007cb6d  nop     dword ptr [rax+rax+00h]
0x18007cb72  cmp     eax, 2
0x18007cb75  jz      loc_18007CC68
0x18007cb7b  mov     rcx, [rbp+178h]; this
0x18007cb82  mov     edx, 0D0h; void *
0x18007cb87  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007cb8c  mov     ebx, eax
0x18007cb8e  jmp     loc_18007CC6A
0x18007cb93  lea     rdx, [rsp+270h+var_23C]; int *
0x18007cb98  mov     [rsp+270h+var_23C], 0
0x18007cba0  mov     rcx, rax; hHandle
0x18007cba3  mov     [rsp+270h+var_240], 0
0x18007cbab  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18007cbb0  mov     ebx, eax
0x18007cbb2  test    eax, eax
0x18007cbb4  jns     short loc_18007CBCF
0x18007cbb6  mov     rcx, [rbp+178h]; this
0x18007cbbd  mov     r9d, eax; char *
0x18007cbc0  mov     edx, 0D6h; void *
0x18007cbc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cbca  jmp     loc_18007CC6A
0x18007cbcf  lea     r8, asc_18009CB88; "h"
0x18007cbd6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18007cbdb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18007cbe0  lea     r8, [rsp+270h+pszDest]; lpName
0x18007cbe5  xor     edx, edx; bInheritHandle
0x18007cbe7  mov     ecx, 1F0003h; dwDesiredAccess
0x18007cbec  call    cs:__imp_OpenSemaphoreW
0x18007cbf3  nop     dword ptr [rax+rax+00h]
0x18007cbf8  mov     [rsp+270h+var_238], rax
0x18007cbfd  test    rax, rax
0x18007cc00  jnz     short loc_18007CC21
0x18007cc02  mov     rcx, [rbp+178h]; this
0x18007cc09  mov     edx, 0DCh; void *
0x18007cc0e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18007cc13  mov     ebx, eax
0x18007cc15  lea     rcx, [rsp+270h+var_238]
0x18007cc1a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007cc1f  jmp     short loc_18007CC6A
0x18007cc21  lea     rdx, [rsp+270h+var_240]; int *
0x18007cc26  mov     rcx, rax; hHandle
0x18007cc29  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18007cc2e  mov     ebx, eax
0x18007cc30  test    eax, eax
0x18007cc32  jns     short loc_18007CC4A
0x18007cc34  mov     rcx, [rbp+178h]; this
0x18007cc3b  mov     r9d, eax; char *
0x18007cc3e  mov     edx, 0DEh; void *
0x18007cc43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cc48  jmp     short loc_18007CC15
0x18007cc4a  lea     rcx, [rsp+270h+var_238]
0x18007cc4f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007cc54  movsxd  rcx, [rsp+270h+var_240]
0x18007cc59  movsxd  rax, [rsp+270h+var_23C]
0x18007cc5e  shl     rcx, 1Fh
0x18007cc62  or      rcx, rax
0x18007cc65  mov     [rdi], rcx
0x18007cc68  xor     ebx, ebx
0x18007cc6a  lea     rcx, [rsp+270h+var_230]
0x18007cc6f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18007cc74  mov     eax, ebx
0x18007cc76  mov     rcx, [rbp+170h+var_10]
0x18007cc7d  xor     rcx, rsp; StackCookie
0x18007cc80  call    __security_check_cookie
0x18007cc85  lea     r11, [rsp+270h+var_s0]
0x18007cc8d  mov     rbx, [r11+18h]
0x18007cc91  mov     rdi, [r11+28h]
0x18007cc95  mov     rsp, r11
0x18007cc98  pop     rbp
0x18007cc99  retn
```
