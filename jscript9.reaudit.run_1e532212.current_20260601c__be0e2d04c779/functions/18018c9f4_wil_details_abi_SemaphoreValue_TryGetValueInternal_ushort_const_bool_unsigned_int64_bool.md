# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18018c9f4`
- end: `0x18018cc66`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `626`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18018c7e8`
- `0x1801a3cd4`

## callees

- `0x18018c9f4`
- `0x18018cc6c`
- `0x18019bed4`
- `0x1801a0688`
- `0x1801a3d4c`
- `0x1801ad16c`
- `0x1801cc7bc`
- `0x180341dd0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18018cc10`
- `KERNEL32!GetLastError` at `0x18018cc10`
- `KERNEL32!OpenSemaphoreW` at `0x18018caf7`
- `KERNEL32!OpenSemaphoreW` at `0x18018cb74`
- `KERNEL32!OpenSemaphoreW` at `0x18018caf7`
- `KERNEL32!OpenSemaphoreW` at `0x18018cb74`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        char a2,
        unsigned __int64 *a3,
        bool *a4)
{
  __int64 v6; // rcx
  const unsigned __int16 *v7; // r8
  __int64 v8; // rdx
  WCHAR *v9; // rax
  unsigned __int16 v10; // r9
  WCHAR *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // rax
  __int64 v14; // r8
  HANDLE v15; // rax
  int v16; // esi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  HANDLE v19; // rax
  const char *v20; // r9
  int v21; // eax
  __int64 v22; // rax
  const char *v24; // r9
  size_t v25; // [rsp+28h] [rbp-E0h]
  int v26[2]; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE v27; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v28[2]; // [rsp+48h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B0h] [rbp+1A8h]

  v28[1] = -2;
  if ( a4 )
    *a4 = 0;
  *a3 = 0;
  v6 = 2147483646;
  v7 = a1;
  v8 = 260;
  v9 = Name;
  do
  {
    if ( !v6 )
      break;
    v10 = *v7;
    if ( !*v7 )
      break;
    ++v7;
    *v9++ = v10;
    --v6;
    --v8;
  }
  while ( v8 );
  v11 = v9 - 1;
  if ( v8 )
    v11 = v9;
  *v11 = 0;
  v12 = 260;
  v13 = Name;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v12;
  }
  while ( v12 );
  if ( v12 )
  {
    v14 = (260 - v12) & -(__int64)(v12 != 0);
    StringCopyWorkerW(&Name[v14], 260 - v14, (size_t *)v14, L"_p0", v25);
  }
  v15 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v28[0] = v15;
  if ( v15 )
  {
    v26[1] = 0;
    v16 = 0;
    v26[0] = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v15, &v26[1]);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v25);
LABEL_29:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v28);
      return LastError;
    }
    if ( a2 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v19 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v27 = v19;
      if ( !v19 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v20);
        goto LABEL_26;
      }
      v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, v26);
      LastError = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v21,
          v25);
LABEL_26:
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
        goto LABEL_29;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v27);
      v16 = v26[0];
    }
    v22 = v26[1];
    if ( a4 )
      *a4 = 1;
    *a3 = ((__int64)v16 << 31) | v22;
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v28);
    return 0;
  }
  else
  {
    if ( GetLastError() == 2 )
    {
      LastError = 0;
      goto LABEL_29;
    }
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v24);
  }
}

```

## disassembly

```asm
0x18018c9f4  mov     rax, rsp
0x18018c9f7  mov     [rax+20h], r9
0x18018c9fb  mov     [rax+18h], r8
0x18018c9ff  mov     [rax+10h], dl
0x18018ca02  mov     [rax+8], rcx
0x18018ca06  push    rbp
0x18018ca07  push    rbx
0x18018ca08  push    rsi
0x18018ca09  push    rdi
0x18018ca0a  push    r12
0x18018ca0c  push    r14
0x18018ca0e  push    r15
0x18018ca10  lea     rbp, [rax-1A8h]
0x18018ca17  sub     rsp, 270h
0x18018ca1e  mov     qword ptr [rsp+2A0h+var_258], 0FFFFFFFFFFFFFFFEh
0x18018ca27  mov     rax, cs:__security_cookie
0x18018ca2e  xor     rax, rsp
0x18018ca31  mov     [rbp+1A0h+var_40], rax
0x18018ca38  mov     r14, [rbp+1A0h+arg_10]
0x18018ca3f  mov     rdi, [rbp+1A0h+arg_18]
0x18018ca46  xor     r15d, r15d
0x18018ca49  test    rdi, rdi
0x18018ca4c  jz      short loc_18018CA51
0x18018ca4e  mov     [rdi], r15b
0x18018ca51  mov     [r14], r15
0x18018ca54  mov     ecx, 7FFFFFFEh
0x18018ca59  mov     r8, [rbp+1A0h+arg_0]
0x18018ca60  mov     r12d, 104h
0x18018ca66  mov     edx, r12d
0x18018ca69  lea     rax, [rsp+2A0h+Name]
0x18018ca6e  test    rcx, rcx
0x18018ca71  jz      short loc_18018CA92
0x18018ca73  movzx   r9d, word ptr [r8]
0x18018ca77  test    r9w, r9w
0x18018ca7b  jz      short loc_18018CA92
0x18018ca7d  add     r8, 2
0x18018ca81  mov     [rax], r9w
0x18018ca85  add     rax, 2
0x18018ca89  dec     rcx
0x18018ca8c  sub     rdx, 1
0x18018ca90  jnz     short loc_18018CA6E
0x18018ca92  lea     rcx, [rax-2]
0x18018ca96  test    rdx, rdx
0x18018ca99  cmovnz  rcx, rax
0x18018ca9d  mov     [rcx], r15w
0x18018caa1  mov     rdx, r12
0x18018caa4  lea     rax, [rsp+2A0h+Name]
0x18018caa9  cmp     [rax], r15w
0x18018caad  jz      short loc_18018CAB9
0x18018caaf  add     rax, 2
0x18018cab3  sub     rdx, 1
0x18018cab7  jnz     short loc_18018CAA9
0x18018cab9  mov     rax, rdx
0x18018cabc  mov     rcx, r12
0x18018cabf  sub     rcx, rdx
0x18018cac2  neg     rax
0x18018cac5  sbb     r8, r8
0x18018cac8  and     r8, rcx; pcchNewDestLength
0x18018cacb  test    rdx, rdx
0x18018cace  jz      short loc_18018CAEB
0x18018cad0  mov     rdx, r12
0x18018cad3  sub     rdx, r8; cchDest
0x18018cad6  lea     rcx, [rsp+2A0h+Name]
0x18018cadb  lea     rcx, [rcx+r8*2]; pszDest
0x18018cadf  lea     r9, aP0; "_p0"
0x18018cae6  call    StringCopyWorkerW
0x18018caeb  lea     r8, [rsp+2A0h+Name]; lpName
0x18018caf0  xor     edx, edx; bInheritHandle
0x18018caf2  mov     ecx, 1F0003h; dwDesiredAccess
0x18018caf7  call    cs:__imp_OpenSemaphoreW
0x18018cafd  mov     [rsp+2A0h+var_260], rax
0x18018cb02  test    rax, rax
0x18018cb05  jz      loc_18018CC10
0x18018cb0b  mov     [rsp+2A0h+var_270+4], r15d
0x18018cb10  mov     esi, r15d
0x18018cb13  mov     [rsp+2A0h+var_270], r15d
0x18018cb18  lea     rdx, [rsp+2A0h+var_270+4]; int *
0x18018cb1d  mov     rcx, rax; void *
0x18018cb20  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18018cb25  mov     ebx, eax
0x18018cb27  test    eax, eax
0x18018cb29  jns     short loc_18018CB4B
0x18018cb2b  mov     rcx, [rbp+1A8h]; this
0x18018cb32  mov     r9d, eax; char *
0x18018cb35  lea     r8, aWil; "wil"
0x18018cb3c  mov     edx, 0D6h; void *
0x18018cb41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018cb46  jmp     loc_18018CC1E
0x18018cb4b  cmp     [rbp+1A0h+arg_8], r15b
0x18018cb52  jz      short loc_18018CBC2
0x18018cb54  lea     r8, asc_1803BAA84; "h"
0x18018cb5b  mov     rdx, r12; unsigned __int64
0x18018cb5e  lea     rcx, [rsp+2A0h+Name]; unsigned __int16 *
0x18018cb63  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18018cb68  lea     r8, [rsp+2A0h+Name]; lpName
0x18018cb6d  xor     edx, edx; bInheritHandle
0x18018cb6f  mov     ecx, 1F0003h; dwDesiredAccess
0x18018cb74  call    cs:__imp_OpenSemaphoreW
0x18018cb7a  mov     [rsp+2A0h+var_268], rax
0x18018cb7f  test    rax, rax
0x18018cb82  jz      short loc_18018CBEA
0x18018cb84  lea     rdx, [rsp+2A0h+var_270]; int *
0x18018cb89  mov     rcx, rax; void *
0x18018cb8c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18018cb91  mov     ebx, eax
0x18018cb93  test    eax, eax
0x18018cb95  jns     short loc_18018CBB4
0x18018cb97  mov     rcx, [rbp+1A8h]; this
0x18018cb9e  mov     r9d, eax; char *
0x18018cba1  lea     r8, aWil; "wil"
0x18018cba8  mov     edx, 0DEh; void *
0x18018cbad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18018cbb2  jmp     short loc_18018CC04
0x18018cbb4  lea     rcx, [rsp+2A0h+var_268]
0x18018cbb9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018cbbe  mov     esi, [rsp+2A0h+var_270]
0x18018cbc2  movsxd  rcx, esi
0x18018cbc5  shl     rcx, 1Fh
0x18018cbc9  movsxd  rax, [rsp+2A0h+var_270+4]
0x18018cbce  test    rdi, rdi
0x18018cbd1  jz      short loc_18018CBD6
0x18018cbd3  mov     byte ptr [rdi], 1
0x18018cbd6  or      rax, rcx
0x18018cbd9  mov     [r14], rax
0x18018cbdc  lea     rcx, [rsp+2A0h+var_260]
0x18018cbe1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018cbe6  xor     eax, eax
0x18018cbe8  jmp     short loc_18018CC45
0x18018cbea  mov     rcx, [rbp+1A8h]; this
0x18018cbf1  lea     r8, aWil; "wil"
0x18018cbf8  mov     edx, 0DCh; void *
0x18018cbfd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18018cc02  mov     ebx, eax
0x18018cc04  lea     rcx, [rsp+2A0h+var_268]
0x18018cc09  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018cc0e  jmp     short loc_18018CC1E
0x18018cc10  call    cs:__imp_GetLastError
0x18018cc16  cmp     eax, 2
0x18018cc19  jnz     short loc_18018CC2C
0x18018cc1b  mov     ebx, r15d
0x18018cc1e  lea     rcx, [rsp+2A0h+var_260]
0x18018cc23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18018cc28  mov     eax, ebx
0x18018cc2a  jmp     short loc_18018CC45
0x18018cc2c  mov     rcx, [rbp+1A8h]; this
0x18018cc33  lea     r8, aWil; "wil"
0x18018cc3a  mov     edx, 0D0h; void *
0x18018cc3f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18018cc44  nop
0x18018cc45  mov     rcx, [rbp+1A0h+var_40]
0x18018cc4c  xor     rcx, rsp; StackCookie
0x18018cc4f  call    __security_check_cookie
0x18018cc54  add     rsp, 270h
0x18018cc5b  pop     r15
0x18018cc5d  pop     r14
0x18018cc5f  pop     r12
0x18018cc61  pop     rdi
0x18018cc62  pop     rsi
0x18018cc63  pop     rbx
0x18018cc64  pop     rbp
0x18018cc65  retn
```
