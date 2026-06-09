# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180158ab0`
- end: `0x180158cdc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180158768`
- `0x180158d9c`

## callees

- `0x18002be34`
- `0x18004fce4`
- `0x18007778c`
- `0x180158ab0`
- `0x180200500`
- `0x18020fcc0`
- `0x1802284b0`
- `0x18022b00c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180158b81`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180158bf0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180158b81`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180158bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158c82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180158c82`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  bool v8; // zf
  WCHAR *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rax
  __int64 v12; // r8
  HANDLE v13; // rax
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  HANDLE v16; // rax
  const char *v17; // r9
  int v18; // eax
  const char *v20; // r9
  size_t v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-C0h] BYREF
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
  v8 = v5 == 0;
  v9 = v4 - 1;
  v10 = 260;
  if ( !v8 )
    v9 = v4;
  v11 = Name;
  *v9 = 0;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  if ( v10 )
  {
    v12 = (260 - v10) & -(__int64)(v10 != 0);
    StringCopyWorkerW(&Name[v12], 260 - v12, (size_t *)v12, L"_p0", v21);
  }
  v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v25[0] = v13;
  if ( v13 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v24 = v16;
      if ( v16 )
      {
        v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v22);
        LastError = v18;
        if ( v18 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
          *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v18,
          v21);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v21);
    }
    goto LABEL_23;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_23:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v20);
}

```

## disassembly

```asm
0x180158ab0  mov     [rsp-8+arg_0], rbx
0x180158ab5  mov     [rsp-8+arg_8], rsi
0x180158aba  push    rbp
0x180158abb  push    rdi
0x180158abc  push    r14
0x180158abe  lea     rbp, [rsp-170h]
0x180158ac6  sub     rsp, 270h
0x180158acd  mov     rax, cs:__security_cookie
0x180158ad4  xor     rax, rsp
0x180158ad7  mov     [rbp+180h+var_20], rax
0x180158ade  xor     esi, esi
0x180158ae0  lea     rax, [rsp+280h+Name]
0x180158ae5  mov     r14d, 104h
0x180158aeb  mov     [r8], rsi
0x180158aee  mov     edx, r14d
0x180158af1  mov     rdi, r8
0x180158af4  mov     r9d, 7FFFFFFEh
0x180158afa  test    r9, r9
0x180158afd  jz      short loc_180158B1E
0x180158aff  movzx   r8d, word ptr [rcx]
0x180158b03  test    r8w, r8w
0x180158b07  jz      short loc_180158B1E
0x180158b09  mov     [rax], r8w
0x180158b0d  add     rcx, 2
0x180158b11  add     rax, 2
0x180158b15  dec     r9
0x180158b18  sub     rdx, 1
0x180158b1c  jnz     short loc_180158AFA
0x180158b1e  test    rdx, rdx
0x180158b21  lea     rcx, [rax-2]
0x180158b25  mov     rdx, r14
0x180158b28  cmovnz  rcx, rax
0x180158b2c  lea     rax, [rsp+280h+Name]
0x180158b31  mov     [rcx], si
0x180158b34  cmp     [rax], si
0x180158b37  jz      short loc_180158B43
0x180158b39  add     rax, 2
0x180158b3d  sub     rdx, 1
0x180158b41  jnz     short loc_180158B34
0x180158b43  mov     rcx, r14
0x180158b46  mov     rax, rdx
0x180158b49  sub     rcx, rdx
0x180158b4c  neg     rax
0x180158b4f  sbb     r8, r8
0x180158b52  and     r8, rcx; pcchNewDestLength
0x180158b55  test    rdx, rdx
0x180158b58  jz      short loc_180158B75
0x180158b5a  mov     rdx, r14
0x180158b5d  lea     rcx, [rsp+280h+Name]
0x180158b62  sub     rdx, r8; cchDest
0x180158b65  lea     rcx, [rcx+r8*2]; pszDest
0x180158b69  lea     r9, aP0; "_p0"
0x180158b70  call    StringCopyWorkerW
0x180158b75  lea     r8, [rsp+280h+Name]; lpName
0x180158b7a  xor     edx, edx; bInheritHandle
0x180158b7c  mov     ecx, 1F0003h; dwDesiredAccess
0x180158b81  call    cs:__imp_OpenSemaphoreW
0x180158b87  mov     [rsp+280h+var_240], rax
0x180158b8c  test    rax, rax
0x180158b8f  jz      loc_180158C82
0x180158b95  lea     rdx, [rsp+280h+var_24C]; int *
0x180158b9a  mov     [rsp+280h+var_24C], esi
0x180158b9e  mov     rcx, rax; hHandle
0x180158ba1  mov     [rsp+280h+var_250], esi
0x180158ba5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180158baa  mov     ebx, eax
0x180158bac  test    eax, eax
0x180158bae  jns     short loc_180158BD0
0x180158bb0  mov     rcx, [rbp+188h]; this
0x180158bb7  lea     r8, aWil; "wil"
0x180158bbe  mov     r9d, eax; char *
0x180158bc1  mov     edx, 0D6h; void *
0x180158bc6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158bcb  jmp     loc_180158C8F
0x180158bd0  lea     r8, asc_18032AFA8; "h"
0x180158bd7  mov     rdx, r14; unsigned __int64
0x180158bda  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180158bdf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180158be4  lea     r8, [rsp+280h+Name]; lpName
0x180158be9  xor     edx, edx; bInheritHandle
0x180158beb  mov     ecx, 1F0003h; dwDesiredAccess
0x180158bf0  call    cs:__imp_OpenSemaphoreW
0x180158bf6  mov     [rsp+280h+var_248], rax
0x180158bfb  test    rax, rax
0x180158bfe  jz      short loc_180158C5C
0x180158c00  lea     rdx, [rsp+280h+var_250]; int *
0x180158c05  mov     rcx, rax; hHandle
0x180158c08  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180158c0d  mov     ebx, eax
0x180158c0f  test    eax, eax
0x180158c11  jns     short loc_180158C30
0x180158c13  mov     rcx, [rbp+188h]; this
0x180158c1a  lea     r8, aWil; "wil"
0x180158c21  mov     r9d, eax; char *
0x180158c24  mov     edx, 0DEh; void *
0x180158c29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180158c2e  jmp     short loc_180158C76
0x180158c30  lea     rcx, [rsp+280h+var_248]
0x180158c35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180158c3a  movsxd  rax, [rsp+280h+var_24C]
0x180158c3f  movsxd  rcx, [rsp+280h+var_250]
0x180158c44  shl     rcx, 1Fh
0x180158c48  or      rcx, rax
0x180158c4b  mov     [rdi], rcx
0x180158c4e  lea     rcx, [rsp+280h+var_240]
0x180158c53  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180158c58  xor     eax, eax
0x180158c5a  jmp     short loc_180158CB5
0x180158c5c  mov     rcx, [rbp+188h]; this
0x180158c63  lea     r8, aWil; "wil"
0x180158c6a  mov     edx, 0DCh; void *
0x180158c6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180158c74  mov     ebx, eax
0x180158c76  lea     rcx, [rsp+280h+var_248]
0x180158c7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180158c80  jmp     short loc_180158C8F
0x180158c82  call    cs:__imp_GetLastError
0x180158c88  cmp     eax, 2
0x180158c8b  jnz     short loc_180158C9D
0x180158c8d  mov     ebx, esi
0x180158c8f  lea     rcx, [rsp+280h+var_240]
0x180158c94  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180158c99  mov     eax, ebx
0x180158c9b  jmp     short loc_180158CB5
0x180158c9d  mov     rcx, [rbp+188h]; this
0x180158ca4  lea     r8, aWil; "wil"
0x180158cab  mov     edx, 0D0h; void *
0x180158cb0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180158cb5  mov     rcx, [rbp+180h+var_20]
0x180158cbc  xor     rcx, rsp; StackCookie
0x180158cbf  call    __security_check_cookie
0x180158cc4  lea     r11, [rsp+280h+var_10]
0x180158ccc  mov     rbx, [r11+20h]
0x180158cd0  mov     rsi, [r11+28h]
0x180158cd4  mov     rsp, r11
0x180158cd7  pop     r14
0x180158cd9  pop     rdi
0x180158cda  pop     rbp
0x180158cdb  retn
```
