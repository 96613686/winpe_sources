# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18005c720`
- end: `0x18005c9fc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `732`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18005bea0`
- `0x18005c464`

## callees

- `0x18002c8d0`
- `0x18005c224`
- `0x18005c720`
- `0x18005ca04`
- `0x18005cb08`
- `0x180083aa8`
- `0x1800862f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005c82c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005c932`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005c82c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005c932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c83f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c83f`

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
  const wchar_t *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  const char *v21; // r9
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  __int64 v25; // rdx
  WCHAR *v26; // rax
  __int64 v27; // r8
  WCHAR *v28; // rax
  const unsigned __int16 *v29; // rcx
  __int64 v30; // rbx
  WCHAR *v31; // rdx
  wil::details *v32; // rax
  const char *v33; // r9
  wil::details *v34; // rbx
  void *v35; // rdx
  int v36; // eax
  void *v37; // rdx
  void *v38; // rdx
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
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v21);
    LastError = 0;
    goto LABEL_42;
  }
  v40 = 0;
  v39 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v40);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v39);
    goto LABEL_35;
  }
  v25 = 260;
  v26 = Name;
  do
  {
    if ( !*v26 )
      break;
    ++v26;
    --v25;
  }
  while ( v25 );
  v27 = (260 - v25) & -(__int64)(v25 != 0);
  if ( v25 )
  {
    v28 = &Name[v27];
    v29 = L"h";
    v30 = 260 - v27;
    if ( 260 != v27 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v29 )
          break;
        *v28++ = *v29++;
        --v5;
        --v30;
      }
      while ( v30 );
    }
    v31 = v28 - 1;
    if ( v30 )
      v31 = v28;
    *v31 = 0;
  }
  v32 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v41 = v32;
  v34 = v32;
  if ( !v32 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v33);
LABEL_35:
    wil::details::CloseHandle(v20, v35);
    return LastError;
  }
  v36 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v32, &v39);
  LastError = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v36, v39);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v41);
LABEL_42:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    return LastError;
  }
  wil::details::CloseHandle(v34, v37);
  *a3 = v40 | (unsigned __int64)((__int64)v39 << 31);
  wil::details::CloseHandle(v20, v38);
  return 0;
}

```

## disassembly

```asm
0x18005c720  mov     [rsp-8+arg_0], rbx
0x18005c725  mov     [rsp-8+arg_8], rsi
0x18005c72a  push    rbp
0x18005c72b  push    rdi
0x18005c72c  push    r12
0x18005c72e  push    r14
0x18005c730  push    r15
0x18005c732  lea     rbp, [rsp-160h]
0x18005c73a  sub     rsp, 260h
0x18005c741  mov     rax, cs:__security_cookie
0x18005c748  xor     rax, rsp
0x18005c74b  mov     [rbp+180h+var_30], rax
0x18005c752  xor     r12d, r12d
0x18005c755  lea     rax, [rsp+280h+Name]
0x18005c75a  mov     r14d, 7FFFFFFEh
0x18005c760  mov     [r8], r12
0x18005c763  mov     ebx, 104h
0x18005c768  mov     r9d, r14d
0x18005c76b  mov     edx, ebx
0x18005c76d  mov     r15, r8
0x18005c770  test    r9, r9
0x18005c773  jz      short loc_18005C794
0x18005c775  movzx   r8d, word ptr [rcx]
0x18005c779  test    r8w, r8w
0x18005c77d  jz      short loc_18005C794
0x18005c77f  mov     [rax], r8w
0x18005c783  add     rcx, 2
0x18005c787  add     rax, 2
0x18005c78b  dec     r9
0x18005c78e  sub     rdx, 1
0x18005c792  jnz     short loc_18005C770
0x18005c794  test    rdx, rdx
0x18005c797  lea     rcx, [rax-2]
0x18005c79b  mov     rdx, rbx
0x18005c79e  cmovnz  rcx, rax
0x18005c7a2  lea     rax, [rsp+280h+Name]
0x18005c7a7  mov     [rcx], r12w
0x18005c7ab  cmp     [rax], r12w
0x18005c7af  jz      short loc_18005C7BB
0x18005c7b1  add     rax, 2
0x18005c7b5  sub     rdx, 1
0x18005c7b9  jnz     short loc_18005C7AB
0x18005c7bb  mov     rcx, rbx
0x18005c7be  mov     rax, rdx
0x18005c7c1  sub     rcx, rdx
0x18005c7c4  neg     rax
0x18005c7c7  sbb     r8, r8
0x18005c7ca  and     r8, rcx
0x18005c7cd  test    rdx, rdx
0x18005c7d0  jz      short loc_18005C820
0x18005c7d2  mov     rax, rbx
0x18005c7d5  lea     rdx, [rsp+280h+Name]
0x18005c7da  lea     r9, aP0; "_p0"
0x18005c7e1  mov     rcx, r14
0x18005c7e4  lea     rdx, [rdx+r8*2]
0x18005c7e8  sub     rax, r8
0x18005c7eb  jz      short loc_18005C811
0x18005c7ed  test    rcx, rcx
0x18005c7f0  jz      short loc_18005C811
0x18005c7f2  movzx   r8d, word ptr [r9]
0x18005c7f6  test    r8w, r8w
0x18005c7fa  jz      short loc_18005C811
0x18005c7fc  mov     [rdx], r8w
0x18005c800  add     r9, 2
0x18005c804  add     rdx, 2
0x18005c808  dec     rcx
0x18005c80b  sub     rax, 1
0x18005c80f  jnz     short loc_18005C7ED
0x18005c811  test    rax, rax
0x18005c814  lea     rcx, [rdx-2]
0x18005c818  cmovnz  rcx, rdx
0x18005c81c  mov     [rcx], r12w
0x18005c820  lea     r8, [rsp+280h+Name]; lpName
0x18005c825  xor     edx, edx; bInheritHandle
0x18005c827  mov     ecx, 1F0003h; dwDesiredAccess
0x18005c82c  call    cs:__imp_OpenSemaphoreW
0x18005c832  mov     [rsp+280h+var_250], rax
0x18005c837  mov     rdi, rax
0x18005c83a  test    rax, rax
0x18005c83d  jnz     short loc_18005C891
0x18005c83f  call    cs:__imp_GetLastError
0x18005c845  cmp     eax, 2
0x18005c848  jz      loc_18005C9F4
0x18005c84e  mov     rcx, [rbp+188h]; this
0x18005c855  lea     r8, aWil; "wil"
0x18005c85c  mov     edx, 0D0h; void *
0x18005c861  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c866  mov     rcx, [rbp+180h+var_30]
0x18005c86d  xor     rcx, rsp; StackCookie
0x18005c870  call    __security_check_cookie
0x18005c875  lea     r11, [rsp+280h+var_20]
0x18005c87d  mov     rbx, [r11+30h]
0x18005c881  mov     rsi, [r11+38h]
0x18005c885  mov     rsp, r11
0x18005c888  pop     r15
0x18005c88a  pop     r14
0x18005c88c  pop     r12
0x18005c88e  pop     rdi
0x18005c88f  pop     rbp
0x18005c890  retn
0x18005c891  lea     rdx, [rsp+280h+var_25C]; int *
0x18005c896  mov     [rsp+280h+var_25C], r12d
0x18005c89b  mov     rcx, rdi; hHandle
0x18005c89e  mov     [rsp+280h+var_260], r12d; int
0x18005c8a3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005c8a8  mov     esi, eax
0x18005c8aa  test    eax, eax
0x18005c8ac  js      loc_18005C9AC
0x18005c8b2  mov     rdx, rbx
0x18005c8b5  lea     rax, [rsp+280h+Name]
0x18005c8ba  cmp     [rax], r12w
0x18005c8be  jz      short loc_18005C8CA
0x18005c8c0  add     rax, 2
0x18005c8c4  sub     rdx, 1
0x18005c8c8  jnz     short loc_18005C8BA
0x18005c8ca  mov     rcx, rbx
0x18005c8cd  mov     rax, rdx
0x18005c8d0  sub     rcx, rdx
0x18005c8d3  neg     rax
0x18005c8d6  sbb     r8, r8
0x18005c8d9  and     r8, rcx
0x18005c8dc  test    rdx, rdx
0x18005c8df  jz      short loc_18005C926
0x18005c8e1  lea     rax, [rsp+280h+Name]
0x18005c8e6  lea     rax, [rax+r8*2]
0x18005c8ea  lea     rcx, asc_1800DFD74; "h"
0x18005c8f1  sub     rbx, r8
0x18005c8f4  jz      short loc_18005C917
0x18005c8f6  test    r14, r14
0x18005c8f9  jz      short loc_18005C917
0x18005c8fb  movzx   edx, word ptr [rcx]
0x18005c8fe  test    dx, dx
0x18005c901  jz      short loc_18005C917
0x18005c903  mov     [rax], dx
0x18005c906  add     rcx, 2
0x18005c90a  add     rax, 2
0x18005c90e  dec     r14
0x18005c911  sub     rbx, 1
0x18005c915  jnz     short loc_18005C8F6
0x18005c917  test    rbx, rbx
0x18005c91a  lea     rdx, [rax-2]
0x18005c91e  cmovnz  rdx, rax
0x18005c922  mov     [rdx], r12w
0x18005c926  lea     r8, [rsp+280h+Name]; lpName
0x18005c92b  xor     edx, edx; bInheritHandle
0x18005c92d  mov     ecx, 1F0003h; dwDesiredAccess
0x18005c932  call    cs:__imp_OpenSemaphoreW
0x18005c938  mov     [rsp+280h+var_258], rax
0x18005c93d  mov     rbx, rax
0x18005c940  test    rax, rax
0x18005c943  jnz     short loc_18005C96E
0x18005c945  mov     rcx, [rbp+188h]; this
0x18005c94c  lea     r8, aWil; "wil"
0x18005c953  mov     edx, 0DCh; void *
0x18005c958  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c95d  mov     esi, eax
0x18005c95f  mov     rcx, rdi; this
0x18005c962  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005c967  mov     eax, esi
0x18005c969  jmp     loc_18005C866
0x18005c96e  lea     rdx, [rsp+280h+var_260]; int *
0x18005c973  mov     rcx, rbx; hHandle
0x18005c976  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18005c97b  mov     esi, eax
0x18005c97d  test    eax, eax
0x18005c97f  js      short loc_18005C9C9
0x18005c981  mov     rcx, rbx; this
0x18005c984  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005c989  movsxd  rax, [rsp+280h+var_25C]
0x18005c98e  movsxd  rcx, [rsp+280h+var_260]
0x18005c993  shl     rcx, 1Fh
0x18005c997  or      rcx, rax
0x18005c99a  mov     [r15], rcx
0x18005c99d  mov     rcx, rdi; this
0x18005c9a0  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18005c9a5  xor     eax, eax
0x18005c9a7  jmp     loc_18005C866
0x18005c9ac  mov     rcx, [rbp+188h]; this
0x18005c9b3  lea     r8, aWil; "wil"
0x18005c9ba  mov     r9d, eax; char *
0x18005c9bd  mov     edx, 0D6h; void *
0x18005c9c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c9c7  jmp     short loc_18005C95F
0x18005c9c9  mov     rcx, [rbp+188h]; this
0x18005c9d0  lea     r8, aWil; "wil"
0x18005c9d7  mov     r9d, eax; char *
0x18005c9da  mov     edx, 0DEh; void *
0x18005c9df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005c9e4  lea     rcx, [rsp+280h+var_258]
0x18005c9e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005c9ee  nop
0x18005c9ef  jmp     loc_1800C3C9E
0x18005c9f4  mov     esi, r12d
0x18005c9f7  jmp     loc_1800C3C9E
0x1800c3c9e  lea     rcx, [rsp+280h+var_250]
0x1800c3ca3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800c3ca8  nop
0x1800c3ca9  jmp     loc_18005C967
```
