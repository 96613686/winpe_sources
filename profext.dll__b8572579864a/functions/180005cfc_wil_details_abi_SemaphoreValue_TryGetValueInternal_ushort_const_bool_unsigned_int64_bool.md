# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005cfc`
- end: `0x180005fee`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `754`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180005aa8`
- `0x18000637c`

## callees

- `0x180004594`
- `0x18000590c`
- `0x180005cfc`
- `0x180006478`
- `0x18000d540`
- `0x18000f864`
- `0x180022830`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005e08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005f1b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005e08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005e21`

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
    goto LABEL_36;
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
LABEL_36:
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
0x180005cfc  mov     [rsp-8+arg_0], rbx
0x180005d01  mov     [rsp-8+arg_8], rsi
0x180005d06  push    rbp
0x180005d07  push    rdi
0x180005d08  push    r12
0x180005d0a  push    r14
0x180005d0c  push    r15
0x180005d0e  lea     rbp, [rsp-160h]
0x180005d16  sub     rsp, 260h
0x180005d1d  mov     rax, cs:__security_cookie
0x180005d24  xor     rax, rsp
0x180005d27  mov     [rbp+180h+var_30], rax
0x180005d2e  xor     r12d, r12d
0x180005d31  lea     rax, [rsp+280h+Name]
0x180005d36  mov     r14d, 7FFFFFFEh
0x180005d3c  mov     [r8], r12
0x180005d3f  mov     ebx, 104h
0x180005d44  mov     r9d, r14d
0x180005d47  mov     edx, ebx
0x180005d49  mov     r15, r8
0x180005d4c  test    r9, r9
0x180005d4f  jz      short loc_180005D70
0x180005d51  movzx   r8d, word ptr [rcx]
0x180005d55  test    r8w, r8w
0x180005d59  jz      short loc_180005D70
0x180005d5b  mov     [rax], r8w
0x180005d5f  add     rcx, 2
0x180005d63  add     rax, 2
0x180005d67  dec     r9
0x180005d6a  sub     rdx, 1
0x180005d6e  jnz     short loc_180005D4C
0x180005d70  test    rdx, rdx
0x180005d73  lea     rcx, [rax-2]
0x180005d77  mov     rdx, rbx
0x180005d7a  cmovnz  rcx, rax
0x180005d7e  lea     rax, [rsp+280h+Name]
0x180005d83  mov     [rcx], r12w
0x180005d87  cmp     [rax], r12w
0x180005d8b  jz      short loc_180005D97
0x180005d8d  add     rax, 2
0x180005d91  sub     rdx, 1
0x180005d95  jnz     short loc_180005D87
0x180005d97  mov     rcx, rbx
0x180005d9a  mov     rax, rdx
0x180005d9d  sub     rcx, rdx
0x180005da0  neg     rax
0x180005da3  sbb     r8, r8
0x180005da6  and     r8, rcx
0x180005da9  test    rdx, rdx
0x180005dac  jz      short loc_180005DFC
0x180005dae  mov     rax, rbx
0x180005db1  lea     rdx, [rsp+280h+Name]
0x180005db6  lea     r9, aP0; "_p0"
0x180005dbd  mov     rcx, r14
0x180005dc0  lea     rdx, [rdx+r8*2]
0x180005dc4  sub     rax, r8
0x180005dc7  jz      short loc_180005DED
0x180005dc9  test    rcx, rcx
0x180005dcc  jz      short loc_180005DED
0x180005dce  movzx   r8d, word ptr [r9]
0x180005dd2  test    r8w, r8w
0x180005dd6  jz      short loc_180005DED
0x180005dd8  mov     [rdx], r8w
0x180005ddc  add     r9, 2
0x180005de0  add     rdx, 2
0x180005de4  dec     rcx
0x180005de7  sub     rax, 1
0x180005deb  jnz     short loc_180005DC9
0x180005ded  test    rax, rax
0x180005df0  lea     rcx, [rdx-2]
0x180005df4  cmovnz  rcx, rdx
0x180005df8  mov     [rcx], r12w
0x180005dfc  lea     r8, [rsp+280h+Name]; lpName
0x180005e01  xor     edx, edx; bInheritHandle
0x180005e03  mov     ecx, 1F0003h; dwDesiredAccess
0x180005e08  call    cs:__imp_OpenSemaphoreW
0x180005e0f  nop     dword ptr [rax+rax+00h]
0x180005e14  mov     [rsp+280h+var_250], rax
0x180005e19  mov     rdi, rax
0x180005e1c  test    rax, rax
0x180005e1f  jnz     short loc_180005E7A
0x180005e21  call    cs:__imp_GetLastError
0x180005e28  nop     dword ptr [rax+rax+00h]
0x180005e2d  cmp     eax, 2
0x180005e30  jz      loc_180005FDF
0x180005e36  mov     rcx, [rbp+188h]; this
0x180005e3d  lea     r8, aWil; "wil"
0x180005e44  mov     edx, 0D0h; void *
0x180005e49  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005e4e  mov     rcx, [rbp+180h+var_30]
0x180005e55  xor     rcx, rsp; StackCookie
0x180005e58  call    __security_check_cookie
0x180005e5d  lea     r11, [rsp+280h+var_20]
0x180005e65  mov     rbx, [r11+30h]
0x180005e69  mov     rsi, [r11+38h]
0x180005e6d  mov     rsp, r11
0x180005e70  pop     r15
0x180005e72  pop     r14
0x180005e74  pop     r12
0x180005e76  pop     rdi
0x180005e77  pop     rbp
0x180005e78  retn
0x180005e7a  lea     rdx, [rsp+280h+var_25C]; int *
0x180005e7f  mov     [rsp+280h+var_25C], r12d
0x180005e84  mov     rcx, rdi; hHandle
0x180005e87  mov     [rsp+280h+var_260], r12d; int
0x180005e8c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005e91  mov     esi, eax
0x180005e93  test    eax, eax
0x180005e95  js      loc_180005F50
0x180005e9b  mov     rdx, rbx
0x180005e9e  lea     rax, [rsp+280h+Name]
0x180005ea3  cmp     [rax], r12w
0x180005ea7  jz      short loc_180005EB3
0x180005ea9  add     rax, 2
0x180005ead  sub     rdx, 1
0x180005eb1  jnz     short loc_180005EA3
0x180005eb3  mov     rcx, rbx
0x180005eb6  mov     rax, rdx
0x180005eb9  sub     rcx, rdx
0x180005ebc  neg     rax
0x180005ebf  sbb     r8, r8
0x180005ec2  and     r8, rcx
0x180005ec5  test    rdx, rdx
0x180005ec8  jz      short loc_180005F0F
0x180005eca  lea     rax, [rsp+280h+Name]
0x180005ecf  lea     rax, [rax+r8*2]
0x180005ed3  lea     rcx, asc_180026D40; "h"
0x180005eda  sub     rbx, r8
0x180005edd  jz      short loc_180005F00
0x180005edf  test    r14, r14
0x180005ee2  jz      short loc_180005F00
0x180005ee4  movzx   edx, word ptr [rcx]
0x180005ee7  test    dx, dx
0x180005eea  jz      short loc_180005F00
0x180005eec  mov     [rax], dx
0x180005eef  add     rcx, 2
0x180005ef3  add     rax, 2
0x180005ef7  dec     r14
0x180005efa  sub     rbx, 1
0x180005efe  jnz     short loc_180005EDF
0x180005f00  test    rbx, rbx
0x180005f03  lea     rdx, [rax-2]
0x180005f07  cmovnz  rdx, rax
0x180005f0b  mov     [rdx], r12w
0x180005f0f  lea     r8, [rsp+280h+Name]; lpName
0x180005f14  xor     edx, edx; bInheritHandle
0x180005f16  mov     ecx, 1F0003h; dwDesiredAccess
0x180005f1b  call    cs:__imp_OpenSemaphoreW
0x180005f22  nop     dword ptr [rax+rax+00h]
0x180005f27  mov     [rsp+280h+var_258], rax
0x180005f2c  mov     rbx, rax
0x180005f2f  test    rax, rax
0x180005f32  jnz     short loc_180005F7A
0x180005f34  mov     rcx, [rbp+188h]; this
0x180005f3b  lea     r8, aWil; "wil"
0x180005f42  mov     edx, 0DCh; void *
0x180005f47  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005f4c  mov     esi, eax
0x180005f4e  jmp     short loc_180005F6B
0x180005f50  mov     rcx, [rbp+188h]; this
0x180005f57  lea     r8, aWil; "wil"
0x180005f5e  mov     r9d, eax; char *
0x180005f61  mov     edx, 0D6h; void *
0x180005f66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005f6b  mov     rcx, rdi; this
0x180005f6e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005f73  mov     eax, esi
0x180005f75  jmp     loc_180005E4E
0x180005f7a  lea     rdx, [rsp+280h+var_260]; int *
0x180005f7f  mov     rcx, rbx; hHandle
0x180005f82  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005f87  mov     esi, eax
0x180005f89  test    eax, eax
0x180005f8b  js      short loc_180005FB8
0x180005f8d  mov     rcx, rbx; this
0x180005f90  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005f95  movsxd  rax, [rsp+280h+var_25C]
0x180005f9a  movsxd  rcx, [rsp+280h+var_260]
0x180005f9f  shl     rcx, 1Fh
0x180005fa3  or      rcx, rax
0x180005fa6  mov     [r15], rcx
0x180005fa9  mov     rcx, rdi; this
0x180005fac  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005fb1  xor     eax, eax
0x180005fb3  jmp     loc_180005E4E
0x180005fb8  mov     rcx, [rbp+188h]; this
0x180005fbf  lea     r8, aWil; "wil"
0x180005fc6  mov     r9d, eax; char *
0x180005fc9  mov     edx, 0DEh; void *
0x180005fce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005fd3  lea     rcx, [rsp+280h+var_258]
0x180005fd8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005fdd  jmp     short loc_180005FE2
0x180005fdf  mov     esi, r12d
0x180005fe2  lea     rcx, [rsp+280h+var_250]
0x180005fe7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005fec  jmp     short loc_180005F73
```
