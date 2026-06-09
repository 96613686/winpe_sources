# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002c624`
- end: `0x18002c871`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `589`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18004715c`

## callees

- `0x18002c624`
- `0x180040c34`
- `0x18004731c`
- `0x1800473c4`
- `0x180047550`
- `0x180047664`
- `0x180049cf0`
- `0x18004e850`
- `0x180051488`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002c6f4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002c775`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002c6f4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002c775`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c80d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c80d`

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
0x18002c624  mov     [rsp-8+arg_0], rbx
0x18002c629  mov     [rsp-8+arg_8], rsi
0x18002c62e  push    rbp
0x18002c62f  push    rdi
0x18002c630  push    r14
0x18002c632  lea     rbp, [rsp-170h]
0x18002c63a  sub     rsp, 270h
0x18002c641  mov     rax, cs:__security_cookie
0x18002c648  xor     rax, rsp
0x18002c64b  mov     [rbp+180h+var_20], rax
0x18002c652  xor     r14d, r14d
0x18002c655  lea     rax, [rsp+280h+Name]
0x18002c65a  mov     edx, 104h
0x18002c65f  mov     [r8], r14
0x18002c662  mov     r9d, edx
0x18002c665  mov     rsi, r8
0x18002c668  mov     r10d, 7FFFFFFEh
0x18002c66e  test    r10, r10
0x18002c671  jz      short loc_18002C692
0x18002c673  movzx   r8d, word ptr [rcx]
0x18002c677  test    r8w, r8w
0x18002c67b  jz      short loc_18002C692
0x18002c67d  mov     [rax], r8w
0x18002c681  add     rcx, 2
0x18002c685  add     rax, 2
0x18002c689  dec     r10
0x18002c68c  sub     r9, 1
0x18002c690  jnz     short loc_18002C66E
0x18002c692  lea     rcx, [rax-2]
0x18002c696  test    r9, r9
0x18002c699  mov     r8, rdx
0x18002c69c  cmovnz  rcx, rax
0x18002c6a0  lea     rax, [rsp+280h+Name]
0x18002c6a5  mov     [rcx], r14w
0x18002c6a9  cmp     [rax], r14w
0x18002c6ad  jz      short loc_18002C6B9
0x18002c6af  add     rax, 2
0x18002c6b3  sub     r8, 1; pcchNewDestLength
0x18002c6b7  jnz     short loc_18002C6A9
0x18002c6b9  mov     rcx, rdx
0x18002c6bc  mov     rax, r8
0x18002c6bf  sub     rcx, r8
0x18002c6c2  neg     rax
0x18002c6c5  sbb     r9, r9
0x18002c6c8  and     r9, rcx
0x18002c6cb  test    r8, r8
0x18002c6ce  jz      short loc_18002C6E8
0x18002c6d0  sub     rdx, r9; cchDest
0x18002c6d3  lea     rcx, [rsp+280h+Name]
0x18002c6d8  lea     rcx, [rcx+r9*2]; pszDest
0x18002c6dc  lea     r9, aP0; "_p0"
0x18002c6e3  call    StringCopyWorkerW
0x18002c6e8  lea     r8, [rsp+280h+Name]; lpName
0x18002c6ed  xor     edx, edx; bInheritHandle
0x18002c6ef  mov     ecx, 1F0003h; dwDesiredAccess
0x18002c6f4  call    cs:__imp_OpenSemaphoreW
0x18002c6fb  nop     dword ptr [rax+rax+00h]
0x18002c700  mov     [rsp+280h+var_240], rax
0x18002c705  mov     rbx, rax
0x18002c708  test    rax, rax
0x18002c70b  jz      loc_18002C80D
0x18002c711  lea     rdx, [rsp+280h+var_24C]; int *
0x18002c716  mov     [rsp+280h+var_24C], r14d
0x18002c71b  mov     rcx, rax; hHandle
0x18002c71e  mov     [rsp+280h+var_250], r14d
0x18002c723  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002c728  mov     edi, eax
0x18002c72a  test    eax, eax
0x18002c72c  jns     short loc_18002C758
0x18002c72e  mov     rcx, [rbp+188h]; this
0x18002c735  lea     r8, aWil; "wil"
0x18002c73c  mov     r9d, eax; char *
0x18002c73f  mov     edx, 0D6h; void *
0x18002c744  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c749  mov     rcx, rbx; this
0x18002c74c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18002c751  mov     eax, edi
0x18002c753  jmp     loc_18002C849
0x18002c758  lea     r8, asc_1800A9960; "h"
0x18002c75f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18002c764  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002c769  lea     r8, [rsp+280h+Name]; lpName
0x18002c76e  xor     edx, edx; bInheritHandle
0x18002c770  mov     ecx, 1F0003h; dwDesiredAccess
0x18002c775  call    cs:__imp_OpenSemaphoreW
0x18002c77c  nop     dword ptr [rax+rax+00h]
0x18002c781  mov     [rsp+280h+var_248], rax
0x18002c786  test    rax, rax
0x18002c789  jz      short loc_18002C7E7
0x18002c78b  lea     rdx, [rsp+280h+var_250]; int *
0x18002c790  mov     rcx, rax; hHandle
0x18002c793  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002c798  mov     ebx, eax
0x18002c79a  test    eax, eax
0x18002c79c  jns     short loc_18002C7BB
0x18002c79e  mov     rcx, [rbp+188h]; this
0x18002c7a5  lea     r8, aWil; "wil"
0x18002c7ac  mov     r9d, eax; char *
0x18002c7af  mov     edx, 0DEh; void *
0x18002c7b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c7b9  jmp     short loc_18002C801
0x18002c7bb  lea     rcx, [rsp+280h+var_248]
0x18002c7c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c7c5  movsxd  rax, [rsp+280h+var_24C]
0x18002c7ca  movsxd  rcx, [rsp+280h+var_250]
0x18002c7cf  shl     rcx, 1Fh
0x18002c7d3  or      rcx, rax
0x18002c7d6  mov     [rsi], rcx
0x18002c7d9  lea     rcx, [rsp+280h+var_240]
0x18002c7de  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c7e3  xor     eax, eax
0x18002c7e5  jmp     short loc_18002C849
0x18002c7e7  mov     rcx, [rbp+188h]; this
0x18002c7ee  lea     r8, aWil; "wil"
0x18002c7f5  mov     edx, 0DCh; void *
0x18002c7fa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c7ff  mov     ebx, eax
0x18002c801  lea     rcx, [rsp+280h+var_248]
0x18002c806  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c80b  jmp     short loc_18002C83D
0x18002c80d  call    cs:__imp_GetLastError
0x18002c814  nop     dword ptr [rax+rax+00h]
0x18002c819  cmp     eax, 2
0x18002c81c  jnz     short loc_18002C823
0x18002c81e  mov     ebx, r14d
0x18002c821  jmp     short loc_18002C83D
0x18002c823  mov     rcx, [rbp+188h]; this
0x18002c82a  lea     r8, aWil; "wil"
0x18002c831  mov     edx, 0D0h; void *
0x18002c836  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002c83b  mov     ebx, eax
0x18002c83d  lea     rcx, [rsp+280h+var_240]
0x18002c842  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002c847  mov     eax, ebx
0x18002c849  mov     rcx, [rbp+180h+var_20]
0x18002c850  xor     rcx, rsp; StackCookie
0x18002c853  call    __security_check_cookie
0x18002c858  lea     r11, [rsp+280h+var_10]
0x18002c860  mov     rbx, [r11+20h]
0x18002c864  mov     rsi, [r11+28h]
0x18002c868  mov     rsp, r11
0x18002c86b  pop     r14
0x18002c86d  pop     rdi
0x18002c86e  pop     rbp
0x18002c86f  retn
```
