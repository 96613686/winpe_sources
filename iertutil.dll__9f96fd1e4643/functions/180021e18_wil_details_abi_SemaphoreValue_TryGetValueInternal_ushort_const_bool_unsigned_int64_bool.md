# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180021e18`
- end: `0x1800220fc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `740`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180021a04`
- `0x180021ae4`

## callees

- `0x180021a70`
- `0x180021e18`
- `0x180022104`
- `0x180022270`
- `0x18004f890`
- `0x180053a98`
- `0x180083c10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021f24`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021fdc`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021f24`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021fdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220c3`

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
  void *v38; // rdx
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v42; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v43; // [rsp+30h] [rbp-D0h] BYREF
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
    if ( GetLastError() == 2 )
      LastError = 0;
    else
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v39);
    goto LABEL_41;
  }
  v41 = 0;
  v40 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v41);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v40);
LABEL_41:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    return LastError;
  }
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
  v43 = v30;
  v32 = v30;
  if ( v30 )
  {
    v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v40);
    v35 = v33;
    if ( v33 >= 0 )
    {
      wil::details::CloseHandle(v32, v34);
      *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
      wil::details::CloseHandle(v20, v36);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v33, v40);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
    LastError = v35;
    goto LABEL_41;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
  wil::details::CloseHandle(v20, v38);
  return LastError;
}

```

## disassembly

```asm
0x180021e18  mov     [rsp-8+arg_0], rbx
0x180021e1d  mov     [rsp-8+arg_8], rsi
0x180021e22  push    rbp
0x180021e23  push    rdi
0x180021e24  push    r12
0x180021e26  push    r14
0x180021e28  push    r15
0x180021e2a  lea     rbp, [rsp-160h]
0x180021e32  sub     rsp, 260h
0x180021e39  mov     rax, cs:__security_cookie
0x180021e40  xor     rax, rsp
0x180021e43  mov     [rbp+180h+var_30], rax
0x180021e4a  xor     r12d, r12d
0x180021e4d  lea     rax, [rsp+280h+Name]
0x180021e52  mov     r14d, 7FFFFFFEh
0x180021e58  mov     [r8], r12
0x180021e5b  mov     esi, 104h
0x180021e60  mov     r9d, r14d
0x180021e63  mov     edx, esi
0x180021e65  mov     r15, r8
0x180021e68  test    r9, r9
0x180021e6b  jz      short loc_180021E8C
0x180021e6d  movzx   r8d, word ptr [rcx]
0x180021e71  test    r8w, r8w
0x180021e75  jz      short loc_180021E8C
0x180021e77  mov     [rax], r8w
0x180021e7b  add     rcx, 2
0x180021e7f  add     rax, 2
0x180021e83  dec     r9
0x180021e86  sub     rdx, 1
0x180021e8a  jnz     short loc_180021E68
0x180021e8c  test    rdx, rdx
0x180021e8f  lea     rcx, [rax-2]
0x180021e93  mov     rdx, rsi
0x180021e96  cmovnz  rcx, rax
0x180021e9a  lea     rax, [rsp+280h+Name]
0x180021e9f  mov     [rcx], r12w
0x180021ea3  cmp     [rax], r12w
0x180021ea7  jz      short loc_180021EB3
0x180021ea9  add     rax, 2
0x180021ead  sub     rdx, 1
0x180021eb1  jnz     short loc_180021EA3
0x180021eb3  mov     rcx, rsi
0x180021eb6  mov     rax, rdx
0x180021eb9  sub     rcx, rdx
0x180021ebc  neg     rax
0x180021ebf  sbb     r8, r8
0x180021ec2  and     r8, rcx
0x180021ec5  test    rdx, rdx
0x180021ec8  jz      short loc_180021F18
0x180021eca  mov     rax, rsi
0x180021ecd  lea     rdx, [rsp+280h+Name]
0x180021ed2  lea     r9, aP0; "_p0"
0x180021ed9  mov     rcx, r14
0x180021edc  lea     rdx, [rdx+r8*2]
0x180021ee0  sub     rax, r8
0x180021ee3  jz      short loc_180021F09
0x180021ee5  test    rcx, rcx
0x180021ee8  jz      short loc_180021F09
0x180021eea  movzx   r8d, word ptr [r9]
0x180021eee  test    r8w, r8w
0x180021ef2  jz      short loc_180021F09
0x180021ef4  mov     [rdx], r8w
0x180021ef8  add     r9, 2
0x180021efc  add     rdx, 2
0x180021f00  dec     rcx
0x180021f03  sub     rax, 1
0x180021f07  jnz     short loc_180021EE5
0x180021f09  test    rax, rax
0x180021f0c  lea     rcx, [rdx-2]
0x180021f10  cmovnz  rcx, rdx
0x180021f14  mov     [rcx], r12w
0x180021f18  lea     r8, [rsp+280h+Name]; lpName
0x180021f1d  xor     edx, edx; bInheritHandle
0x180021f1f  mov     ecx, 1F0003h; dwDesiredAccess
0x180021f24  call    cs:__imp_OpenSemaphoreW
0x180021f2a  mov     [rsp+280h+var_258], rax
0x180021f2f  mov     rdi, rax
0x180021f32  test    rax, rax
0x180021f35  jz      loc_1800220C3
0x180021f3b  lea     rdx, [rsp+280h+var_25C]; int *
0x180021f40  mov     [rsp+280h+var_25C], r12d
0x180021f45  mov     rcx, rax; hHandle
0x180021f48  mov     [rsp+280h+var_260], r12d; int
0x180021f4d  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180021f52  mov     ebx, eax
0x180021f54  test    eax, eax
0x180021f56  js      loc_18002207D
0x180021f5c  mov     rdx, rsi
0x180021f5f  lea     rax, [rsp+280h+Name]
0x180021f64  cmp     [rax], r12w
0x180021f68  jz      short loc_180021F74
0x180021f6a  add     rax, 2
0x180021f6e  sub     rdx, 1
0x180021f72  jnz     short loc_180021F64
0x180021f74  mov     rcx, rsi
0x180021f77  mov     rax, rdx
0x180021f7a  sub     rcx, rdx
0x180021f7d  neg     rax
0x180021f80  sbb     r8, r8
0x180021f83  and     r8, rcx
0x180021f86  test    rdx, rdx
0x180021f89  jz      short loc_180021FD0
0x180021f8b  lea     rax, [rsp+280h+Name]
0x180021f90  lea     rax, [rax+r8*2]
0x180021f94  lea     rcx, asc_180158D30; "h"
0x180021f9b  sub     rsi, r8
0x180021f9e  jz      short loc_180021FC1
0x180021fa0  test    r14, r14
0x180021fa3  jz      short loc_180021FC1
0x180021fa5  movzx   edx, word ptr [rcx]
0x180021fa8  test    dx, dx
0x180021fab  jz      short loc_180021FC1
0x180021fad  mov     [rax], dx
0x180021fb0  add     rcx, 2
0x180021fb4  add     rax, 2
0x180021fb8  dec     r14
0x180021fbb  sub     rsi, 1
0x180021fbf  jnz     short loc_180021FA0
0x180021fc1  test    rsi, rsi
0x180021fc4  lea     rdx, [rax-2]
0x180021fc8  cmovnz  rdx, rax
0x180021fcc  mov     [rdx], r12w
0x180021fd0  lea     r8, [rsp+280h+Name]; lpName
0x180021fd5  xor     edx, edx; bInheritHandle
0x180021fd7  mov     ecx, 1F0003h; dwDesiredAccess
0x180021fdc  call    cs:__imp_OpenSemaphoreW
0x180021fe2  mov     [rsp+280h+var_250], rax
0x180021fe7  mov     rbx, rax
0x180021fea  test    rax, rax
0x180021fed  jz      short loc_18002202E
0x180021fef  lea     rdx, [rsp+280h+var_260]; int *
0x180021ff4  mov     rcx, rax; hHandle
0x180021ff7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180021ffc  mov     esi, eax
0x180021ffe  test    eax, eax
0x180022000  js      loc_18002209A
0x180022006  mov     rcx, rbx; this
0x180022009  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18002200e  movsxd  rax, [rsp+280h+var_25C]
0x180022013  movsxd  rcx, [rsp+280h+var_260]
0x180022018  shl     rcx, 1Fh
0x18002201c  or      rcx, rax
0x18002201f  mov     [r15], rcx
0x180022022  mov     rcx, rdi; this
0x180022025  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18002202a  xor     eax, eax
0x18002202c  jmp     short loc_180022052
0x18002202e  mov     rcx, [rbp+188h]; this
0x180022035  lea     r8, aWil; "wil"
0x18002203c  mov     edx, 0DCh; void *
0x180022041  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022046  mov     rcx, rdi; this
0x180022049  mov     ebx, eax
0x18002204b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180022050  mov     eax, ebx
0x180022052  mov     rcx, [rbp+180h+var_30]
0x180022059  xor     rcx, rsp; StackCookie
0x18002205c  call    __security_check_cookie
0x180022061  lea     r11, [rsp+280h+var_20]
0x180022069  mov     rbx, [r11+30h]
0x18002206d  mov     rsi, [r11+38h]
0x180022071  mov     rsp, r11
0x180022074  pop     r15
0x180022076  pop     r14
0x180022078  pop     r12
0x18002207a  pop     rdi
0x18002207b  pop     rbp
0x18002207c  retn
0x18002207d  mov     rcx, [rbp+188h]; this
0x180022084  lea     r8, aWil; "wil"
0x18002208b  mov     r9d, eax; char *
0x18002208e  mov     edx, 0D6h; void *
0x180022093  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022098  jmp     short loc_1800220ED
0x18002209a  mov     rcx, [rbp+188h]; this
0x1800220a1  lea     r8, aWil; "wil"
0x1800220a8  mov     r9d, esi; char *
0x1800220ab  mov     edx, 0DEh; void *
0x1800220b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800220b5  lea     rcx, [rsp+280h+var_250]
0x1800220ba  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800220bf  mov     ebx, esi
0x1800220c1  jmp     short loc_1800220ED
0x1800220c3  call    cs:__imp_GetLastError
0x1800220c9  cmp     eax, 2
0x1800220cc  jnz     short loc_1800220D3
0x1800220ce  mov     ebx, r12d
0x1800220d1  jmp     short loc_1800220ED
0x1800220d3  mov     rcx, [rbp+188h]; this
0x1800220da  lea     r8, aWil; "wil"
0x1800220e1  mov     edx, 0D0h; void *
0x1800220e6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800220eb  mov     ebx, eax
0x1800220ed  lea     rcx, [rsp+280h+var_258]
0x1800220f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800220f7  jmp     loc_180022050
```
