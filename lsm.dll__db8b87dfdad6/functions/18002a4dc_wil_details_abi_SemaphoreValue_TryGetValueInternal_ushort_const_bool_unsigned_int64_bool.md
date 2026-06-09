# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002a4dc`
- end: `0x18002a716`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `570`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180043fe0`

## callees

- `0x18002a4dc`
- `0x18003e4c8`
- `0x180044190`
- `0x180044234`
- `0x18004438c`
- `0x180044498`
- `0x180046d50`
- `0x18004b460`
- `0x18004e018`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002a5ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002a627`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002a5ac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002a627`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a6b9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r9
  __int64 v7; // r10
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rax
  __int64 v11; // r9
  wil::details *v12; // rax
  wil::details *v13; // rbx
  int ValueFromSemaphore; // eax
  unsigned __int64 v15; // rdx
  unsigned int v16; // edi
  void *v17; // rdx
  HANDLE v19; // rax
  const char *v20; // r9
  int v21; // eax
  unsigned int LastError; // ebx
  const char *v23; // r9
  size_t v24; // [rsp+20h] [rbp-E0h]
  int v25; // [rsp+30h] [rbp-D0h] BYREF
  int v26; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v27; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  v9 = 260;
  if ( v5 )
    v8 = v4;
  v10 = Name;
  *v8 = 0;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  if ( v9 )
  {
    v11 = (260 - v9) & -(__int64)(v9 != 0);
    StringCopyWorkerW(&Name[v11], 260 - v11, (size_t *)v9, L"_p0", v24);
  }
  v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v28[0] = v12;
  v13 = v12;
  if ( v12 )
  {
    v26 = 0;
    v25 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v26);
    v16 = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v24);
      wil::details::CloseHandle(v13, v17);
      return v16;
    }
    StringCchCatW(Name, v15, L"h");
    v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v27 = v19;
    if ( v19 )
    {
      v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v25);
      LastError = v21;
      if ( v21 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
        *a3 = v26 | (unsigned __int64)((__int64)v25 << 31);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v28);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v21,
        v24);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v20);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
  }
  else if ( GetLastError() == 2 )
  {
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v23);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v28);
  return LastError;
}

```

## disassembly

```asm
0x18002a4dc  mov     [rsp-8+arg_0], rbx
0x18002a4e1  mov     [rsp-8+arg_8], rsi
0x18002a4e6  push    rbp
0x18002a4e7  push    rdi
0x18002a4e8  push    r14
0x18002a4ea  lea     rbp, [rsp-170h]
0x18002a4f2  sub     rsp, 270h
0x18002a4f9  mov     rax, cs:__security_cookie
0x18002a500  xor     rax, rsp
0x18002a503  mov     [rbp+180h+var_20], rax
0x18002a50a  xor     r14d, r14d
0x18002a50d  lea     rax, [rsp+280h+Name]
0x18002a512  mov     edx, 104h
0x18002a517  mov     [r8], r14
0x18002a51a  mov     r9d, edx
0x18002a51d  mov     rsi, r8
0x18002a520  mov     r10d, 7FFFFFFEh
0x18002a526  test    r10, r10
0x18002a529  jz      short loc_18002A54A
0x18002a52b  movzx   r8d, word ptr [rcx]
0x18002a52f  test    r8w, r8w
0x18002a533  jz      short loc_18002A54A
0x18002a535  mov     [rax], r8w
0x18002a539  add     rcx, 2
0x18002a53d  add     rax, 2
0x18002a541  dec     r10
0x18002a544  sub     r9, 1
0x18002a548  jnz     short loc_18002A526
0x18002a54a  lea     rcx, [rax-2]
0x18002a54e  test    r9, r9
0x18002a551  mov     r8, rdx
0x18002a554  cmovnz  rcx, rax
0x18002a558  lea     rax, [rsp+280h+Name]
0x18002a55d  mov     [rcx], r14w
0x18002a561  cmp     [rax], r14w
0x18002a565  jz      short loc_18002A571
0x18002a567  add     rax, 2
0x18002a56b  sub     r8, 1; pcchNewDestLength
0x18002a56f  jnz     short loc_18002A561
0x18002a571  mov     rcx, rdx
0x18002a574  mov     rax, r8
0x18002a577  sub     rcx, r8
0x18002a57a  neg     rax
0x18002a57d  sbb     r9, r9
0x18002a580  and     r9, rcx
0x18002a583  test    r8, r8
0x18002a586  jz      short loc_18002A5A0
0x18002a588  sub     rdx, r9; cchDest
0x18002a58b  lea     rcx, [rsp+280h+Name]
0x18002a590  lea     rcx, [rcx+r9*2]; pszDest
0x18002a594  lea     r9, aP0; "_p0"
0x18002a59b  call    StringCopyWorkerW
0x18002a5a0  lea     r8, [rsp+280h+Name]; lpName
0x18002a5a5  xor     edx, edx; bInheritHandle
0x18002a5a7  mov     ecx, 1F0003h; dwDesiredAccess
0x18002a5ac  call    cs:__imp_OpenSemaphoreW
0x18002a5b2  mov     [rsp+280h+var_240], rax
0x18002a5b7  mov     rbx, rax
0x18002a5ba  test    rax, rax
0x18002a5bd  jz      loc_18002A6B9
0x18002a5c3  lea     rdx, [rsp+280h+var_24C]; int *
0x18002a5c8  mov     [rsp+280h+var_24C], r14d
0x18002a5cd  mov     rcx, rax; hHandle
0x18002a5d0  mov     [rsp+280h+var_250], r14d
0x18002a5d5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002a5da  mov     edi, eax
0x18002a5dc  test    eax, eax
0x18002a5de  jns     short loc_18002A60A
0x18002a5e0  mov     rcx, [rbp+188h]; this
0x18002a5e7  lea     r8, aWil; "wil"
0x18002a5ee  mov     r9d, eax; char *
0x18002a5f1  mov     edx, 0D6h; void *
0x18002a5f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a5fb  mov     rcx, rbx; this
0x18002a5fe  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18002a603  mov     eax, edi
0x18002a605  jmp     loc_18002A6EF
0x18002a60a  lea     r8, asc_1800A4770; "h"
0x18002a611  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002a616  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002a61b  lea     r8, [rsp+280h+Name]; lpName
0x18002a620  xor     edx, edx; bInheritHandle
0x18002a622  mov     ecx, 1F0003h; dwDesiredAccess
0x18002a627  call    cs:__imp_OpenSemaphoreW
0x18002a62d  mov     [rsp+280h+var_248], rax
0x18002a632  test    rax, rax
0x18002a635  jz      short loc_18002A693
0x18002a637  lea     rdx, [rsp+280h+var_250]; int *
0x18002a63c  mov     rcx, rax; hHandle
0x18002a63f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002a644  mov     ebx, eax
0x18002a646  test    eax, eax
0x18002a648  jns     short loc_18002A667
0x18002a64a  mov     rcx, [rbp+188h]; this
0x18002a651  lea     r8, aWil; "wil"
0x18002a658  mov     r9d, eax; char *
0x18002a65b  mov     edx, 0DEh; void *
0x18002a660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a665  jmp     short loc_18002A6AD
0x18002a667  lea     rcx, [rsp+280h+var_248]
0x18002a66c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a671  movsxd  rax, [rsp+280h+var_24C]
0x18002a676  movsxd  rcx, [rsp+280h+var_250]
0x18002a67b  shl     rcx, 1Fh
0x18002a67f  or      rcx, rax
0x18002a682  mov     [rsi], rcx
0x18002a685  lea     rcx, [rsp+280h+var_240]
0x18002a68a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a68f  xor     eax, eax
0x18002a691  jmp     short loc_18002A6EF
0x18002a693  mov     rcx, [rbp+188h]; this
0x18002a69a  lea     r8, aWil; "wil"
0x18002a6a1  mov     edx, 0DCh; void *
0x18002a6a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a6ab  mov     ebx, eax
0x18002a6ad  lea     rcx, [rsp+280h+var_248]
0x18002a6b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a6b7  jmp     short loc_18002A6E3
0x18002a6b9  call    cs:__imp_GetLastError
0x18002a6bf  cmp     eax, 2
0x18002a6c2  jnz     short loc_18002A6C9
0x18002a6c4  mov     ebx, r14d
0x18002a6c7  jmp     short loc_18002A6E3
0x18002a6c9  mov     rcx, [rbp+188h]; this
0x18002a6d0  lea     r8, aWil; "wil"
0x18002a6d7  mov     edx, 0D0h; void *
0x18002a6dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002a6e1  mov     ebx, eax
0x18002a6e3  lea     rcx, [rsp+280h+var_240]
0x18002a6e8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002a6ed  mov     eax, ebx
0x18002a6ef  mov     rcx, [rbp+180h+var_20]
0x18002a6f6  xor     rcx, rsp; StackCookie
0x18002a6f9  call    __security_check_cookie
0x18002a6fe  lea     r11, [rsp+280h+var_10]
0x18002a706  mov     rbx, [r11+20h]
0x18002a70a  mov     rsi, [r11+28h]
0x18002a70e  mov     rsp, r11
0x18002a711  pop     r14
0x18002a713  pop     rdi
0x18002a714  pop     rbp
0x18002a715  retn
```
