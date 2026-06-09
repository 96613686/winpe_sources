# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000892c`
- end: `0x180008c0a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `734`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180008d68`
- `0x180021058`

## callees

- `0x18000892c`
- `0x180008c10`
- `0x1800214cc`
- `0x1800222a0`
- `0x1800234e0`
- `0x1800254e0`
- `0x180029de4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008a38`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008b0c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008a38`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008b0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ba9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ba9`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rsi
  WCHAR *v29; // rdx
  wil::details *v30; // rax
  const char *v31; // r9
  wil::details *v32; // rbx
  int v33; // eax
  void *v34; // rdx
  int v35; // esi
  void *v36; // rdx
  const char *v38; // r9
  int v39; // [rsp+20h] [rbp-E0h] BYREF
  int v40; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v41; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v42; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"_p0";
    v15 = 2147483646;
    v16 = &Name[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v42 = v19;
  v20 = v19;
  if ( v19 )
  {
    v40 = 0;
    v39 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v40);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      v23 = 260;
      v24 = Name;
      do
      {
        if ( !*v24 )
          break;
        ++v24;
        --v23;
      }
      while ( v23 );
      v25 = (260 - v23) & -(__int64)(v23 != 0);
      if ( v23 )
      {
        v26 = &Name[v25];
        v27 = L"h";
        v28 = 260 - v25;
        if ( 260 != v25 )
        {
          do
          {
            if ( !v5 )
              break;
            if ( !*v27 )
              break;
            *v26++ = *v27++;
            --v5;
            --v28;
          }
          while ( v28 );
        }
        v29 = v26 - 1;
        if ( v28 )
          v29 = v26;
        *v29 = 0;
      }
      v30 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v41 = v30;
      v32 = v30;
      if ( v30 )
      {
        v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v39);
        v35 = v33;
        if ( v33 >= 0 )
        {
          wil::details::CloseHandle(v32, v34);
          *a3 = v40 | (unsigned __int64)((__int64)v39 << 31);
          wil::details::CloseHandle(v20, v36);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v33,
          v39);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
        LastError = v35;
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v39);
    }
  }
  else if ( GetLastError() == 2 )
  {
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v38);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
  return LastError;
}

```

## disassembly

```asm
0x18000892c  mov     [rsp-8+arg_0], rbx
0x180008931  mov     [rsp-8+arg_8], rsi
0x180008936  push    rbp
0x180008937  push    rdi
0x180008938  push    r12
0x18000893a  push    r14
0x18000893c  push    r15
0x18000893e  lea     rbp, [rsp-160h]
0x180008946  sub     rsp, 260h
0x18000894d  mov     rax, cs:__security_cookie
0x180008954  xor     rax, rsp
0x180008957  mov     [rbp+180h+var_30], rax
0x18000895e  xor     r12d, r12d
0x180008961  lea     rax, [rsp+280h+Name]
0x180008966  mov     r14d, 7FFFFFFEh
0x18000896c  mov     [r8], r12
0x18000896f  mov     esi, 104h
0x180008974  mov     r9d, r14d
0x180008977  mov     edx, esi
0x180008979  mov     r15, r8
0x18000897c  test    r9, r9
0x18000897f  jz      short loc_1800089A0
0x180008981  movzx   r8d, word ptr [rcx]
0x180008985  test    r8w, r8w
0x180008989  jz      short loc_1800089A0
0x18000898b  mov     [rax], r8w
0x18000898f  add     rcx, 2
0x180008993  add     rax, 2
0x180008997  dec     r9
0x18000899a  sub     rdx, 1
0x18000899e  jnz     short loc_18000897C
0x1800089a0  test    rdx, rdx
0x1800089a3  lea     rcx, [rax-2]
0x1800089a7  mov     rdx, rsi
0x1800089aa  cmovnz  rcx, rax
0x1800089ae  lea     rax, [rsp+280h+Name]
0x1800089b3  mov     [rcx], r12w
0x1800089b7  cmp     [rax], r12w
0x1800089bb  jz      short loc_1800089C7
0x1800089bd  add     rax, 2
0x1800089c1  sub     rdx, 1
0x1800089c5  jnz     short loc_1800089B7
0x1800089c7  mov     rcx, rsi
0x1800089ca  mov     rax, rdx
0x1800089cd  sub     rcx, rdx
0x1800089d0  neg     rax
0x1800089d3  sbb     r8, r8
0x1800089d6  and     r8, rcx
0x1800089d9  test    rdx, rdx
0x1800089dc  jz      short loc_180008A2C
0x1800089de  mov     rax, rsi
0x1800089e1  lea     rdx, [rsp+280h+Name]
0x1800089e6  lea     r9, aP0; "_p0"
0x1800089ed  mov     rcx, r14
0x1800089f0  lea     rdx, [rdx+r8*2]
0x1800089f4  sub     rax, r8
0x1800089f7  jz      short loc_180008A1D
0x1800089f9  test    rcx, rcx
0x1800089fc  jz      short loc_180008A1D
0x1800089fe  movzx   r8d, word ptr [r9]
0x180008a02  test    r8w, r8w
0x180008a06  jz      short loc_180008A1D
0x180008a08  mov     [rdx], r8w
0x180008a0c  add     r9, 2
0x180008a10  add     rdx, 2
0x180008a14  dec     rcx
0x180008a17  sub     rax, 1
0x180008a1b  jnz     short loc_1800089F9
0x180008a1d  test    rax, rax
0x180008a20  lea     rcx, [rdx-2]
0x180008a24  cmovnz  rcx, rdx
0x180008a28  mov     [rcx], r12w
0x180008a2c  lea     r8, [rsp+280h+Name]; lpName
0x180008a31  xor     edx, edx; bInheritHandle
0x180008a33  mov     ecx, 1F0003h; dwDesiredAccess
0x180008a38  call    cs:__imp_OpenSemaphoreW
0x180008a3e  mov     [rsp+280h+var_250], rax
0x180008a43  mov     rdi, rax
0x180008a46  test    rax, rax
0x180008a49  jz      loc_180008BA9
0x180008a4f  lea     rdx, [rsp+280h+var_25C]; int *
0x180008a54  mov     [rsp+280h+var_25C], r12d
0x180008a59  mov     rcx, rax; hHandle
0x180008a5c  mov     [rsp+280h+var_260], r12d; int
0x180008a61  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008a66  mov     ebx, eax
0x180008a68  test    eax, eax
0x180008a6a  jns     short loc_180008A8C
0x180008a6c  mov     rcx, [rbp+188h]; this
0x180008a73  lea     r8, aWil; "wil"
0x180008a7a  mov     r9d, eax; char *
0x180008a7d  mov     edx, 0D6h; void *
0x180008a82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a87  jmp     loc_180008BD3
0x180008a8c  mov     rdx, rsi
0x180008a8f  lea     rax, [rsp+280h+Name]
0x180008a94  cmp     [rax], r12w
0x180008a98  jz      short loc_180008AA4
0x180008a9a  add     rax, 2
0x180008a9e  sub     rdx, 1
0x180008aa2  jnz     short loc_180008A94
0x180008aa4  mov     rcx, rsi
0x180008aa7  mov     rax, rdx
0x180008aaa  sub     rcx, rdx
0x180008aad  neg     rax
0x180008ab0  sbb     r8, r8
0x180008ab3  and     r8, rcx
0x180008ab6  test    rdx, rdx
0x180008ab9  jz      short loc_180008B00
0x180008abb  lea     rax, [rsp+280h+Name]
0x180008ac0  lea     rax, [rax+r8*2]
0x180008ac4  lea     rcx, asc_18007D748; "h"
0x180008acb  sub     rsi, r8
0x180008ace  jz      short loc_180008AF1
0x180008ad0  test    r14, r14
0x180008ad3  jz      short loc_180008AF1
0x180008ad5  movzx   edx, word ptr [rcx]
0x180008ad8  test    dx, dx
0x180008adb  jz      short loc_180008AF1
0x180008add  mov     [rax], dx
0x180008ae0  add     rcx, 2
0x180008ae4  add     rax, 2
0x180008ae8  dec     r14
0x180008aeb  sub     rsi, 1
0x180008aef  jnz     short loc_180008AD0
0x180008af1  test    rsi, rsi
0x180008af4  lea     rdx, [rax-2]
0x180008af8  cmovnz  rdx, rax
0x180008afc  mov     [rdx], r12w
0x180008b00  lea     r8, [rsp+280h+Name]; lpName
0x180008b05  xor     edx, edx; bInheritHandle
0x180008b07  mov     ecx, 1F0003h; dwDesiredAccess
0x180008b0c  call    cs:__imp_OpenSemaphoreW
0x180008b12  mov     [rsp+280h+var_258], rax
0x180008b17  mov     rbx, rax
0x180008b1a  test    rax, rax
0x180008b1d  jz      short loc_180008B83
0x180008b1f  lea     rdx, [rsp+280h+var_260]; int *
0x180008b24  mov     rcx, rax; hHandle
0x180008b27  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008b2c  mov     esi, eax
0x180008b2e  test    eax, eax
0x180008b30  jns     short loc_180008B5B
0x180008b32  mov     rcx, [rbp+188h]; this
0x180008b39  lea     r8, aWil; "wil"
0x180008b40  mov     r9d, eax; char *
0x180008b43  mov     edx, 0DEh; void *
0x180008b48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b4d  lea     rcx, [rsp+280h+var_258]
0x180008b52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008b57  mov     ebx, esi
0x180008b59  jmp     short loc_180008BD3
0x180008b5b  mov     rcx, rbx; this
0x180008b5e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008b63  movsxd  rax, [rsp+280h+var_25C]
0x180008b68  movsxd  rcx, [rsp+280h+var_260]
0x180008b6d  shl     rcx, 1Fh
0x180008b71  or      rcx, rax
0x180008b74  mov     [r15], rcx
0x180008b77  mov     rcx, rdi; this
0x180008b7a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008b7f  xor     eax, eax
0x180008b81  jmp     short loc_180008BDF
0x180008b83  mov     rcx, [rbp+188h]; this
0x180008b8a  lea     r8, aWil; "wil"
0x180008b91  mov     edx, 0DCh; void *
0x180008b96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008b9b  lea     rcx, [rsp+280h+var_258]
0x180008ba0  mov     ebx, eax
0x180008ba2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008ba7  jmp     short loc_180008BD3
0x180008ba9  call    cs:__imp_GetLastError
0x180008baf  cmp     eax, 2
0x180008bb2  jnz     short loc_180008BB9
0x180008bb4  mov     ebx, r12d
0x180008bb7  jmp     short loc_180008BD3
0x180008bb9  mov     rcx, [rbp+188h]; this
0x180008bc0  lea     r8, aWil; "wil"
0x180008bc7  mov     edx, 0D0h; void *
0x180008bcc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008bd1  mov     ebx, eax
0x180008bd3  lea     rcx, [rsp+280h+var_250]
0x180008bd8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008bdd  mov     eax, ebx
0x180008bdf  mov     rcx, [rbp+180h+var_30]
0x180008be6  xor     rcx, rsp; StackCookie
0x180008be9  call    __security_check_cookie
0x180008bee  lea     r11, [rsp+280h+var_20]
0x180008bf6  mov     rbx, [r11+30h]
0x180008bfa  mov     rsi, [r11+38h]
0x180008bfe  mov     rsp, r11
0x180008c01  pop     r15
0x180008c03  pop     r14
0x180008c05  pop     r12
0x180008c07  pop     rdi
0x180008c08  pop     rbp
0x180008c09  retn
```
