# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180043dd4`
- end: `0x1800440ba`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `742`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180043a38`
- `0x180043ab0`

## callees

- `0x180043dd4`
- `0x1800440c0`
- `0x180044274`
- `0x180053d50`
- `0x1800541e0`
- `0x180054428`
- `0x1800966e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180044073`
- `KERNEL32!GetLastError` at `0x180044073`
- `KERNEL32!OpenSemaphoreW` at `0x180043ee0`
- `KERNEL32!OpenSemaphoreW` at `0x180043f9e`
- `KERNEL32!OpenSemaphoreW` at `0x180043ee0`
- `KERNEL32!OpenSemaphoreW` at `0x180043f9e`

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
  wil::details *v20; // rbx
  int ValueFromSemaphore; // eax
  unsigned int v22; // r8d
  unsigned int LastError; // edi
  __int64 v24; // rdx
  WCHAR *v25; // rax
  __int64 v26; // r8
  WCHAR *v27; // rax
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rsi
  WCHAR *v30; // rdx
  HANDLE v31; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  void *v34; // rdx
  int v36; // eax
  unsigned int v37; // r8d
  void *v38; // rdx
  unsigned int v39; // r8d
  const char *v40; // r9
  unsigned int v41; // ebx
  int v42; // [rsp+20h] [rbp-E0h] BYREF
  int v43; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v44; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v45[2]; // [rsp+30h] [rbp-D0h] BYREF
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
  v45[0] = v19;
  v20 = v19;
  if ( v19 )
  {
    v43 = 0;
    v42 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v43);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v22, (const char *)(unsigned int)ValueFromSemaphore, v42);
LABEL_40:
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
      return LastError;
    }
    v24 = 260;
    v25 = Name;
    do
    {
      if ( !*v25 )
        break;
      ++v25;
      --v24;
    }
    while ( v24 );
    v26 = (260 - v24) & -(__int64)(v24 != 0);
    if ( v24 )
    {
      v27 = &Name[v26];
      v28 = L"h";
      v29 = 260 - v26;
      if ( 260 != v26 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v28 )
            break;
          *v27++ = *v28++;
          --v5;
          --v29;
        }
        while ( v29 );
      }
      v30 = v27 - 1;
      if ( v29 )
        v30 = v27;
      *v30 = 0;
    }
    v31 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v44 = v31;
    if ( !v31 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v32, v33);
      wil::details::CloseHandle(v20, v34);
      return LastError;
    }
    v36 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v31, &v42);
    LastError = v36;
    if ( v36 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v37, (const char *)(unsigned int)v36, v42);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v44);
      goto LABEL_40;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v44);
    *a3 = v43 | (unsigned __int64)((__int64)v42 << 31);
    wil::details::CloseHandle(v20, v38);
    return 0;
  }
  else
  {
    if ( GetLastError() == 2 )
    {
      LastError = 0;
      goto LABEL_40;
    }
    v41 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v39, v40);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v45);
    return v41;
  }
}

```

## disassembly

```asm
0x180043dd4  mov     [rsp-8+arg_0], rbx
0x180043dd9  mov     [rsp-8+arg_8], rsi
0x180043dde  push    rbp
0x180043ddf  push    rdi
0x180043de0  push    r12
0x180043de2  push    r14
0x180043de4  push    r15
0x180043de6  lea     rbp, [rsp-160h]
0x180043dee  sub     rsp, 260h
0x180043df5  mov     rax, cs:__security_cookie
0x180043dfc  xor     rax, rsp
0x180043dff  mov     [rbp+180h+var_30], rax
0x180043e06  xor     r12d, r12d
0x180043e09  lea     rax, [rsp+280h+Name]
0x180043e0e  mov     r14d, 7FFFFFFEh
0x180043e14  mov     [r8], r12
0x180043e17  mov     esi, 104h
0x180043e1c  mov     r9d, r14d
0x180043e1f  mov     edx, esi
0x180043e21  mov     r15, r8
0x180043e24  test    r9, r9
0x180043e27  jz      short loc_180043E48
0x180043e29  movzx   r8d, word ptr [rcx]
0x180043e2d  test    r8w, r8w
0x180043e31  jz      short loc_180043E48
0x180043e33  mov     [rax], r8w
0x180043e37  add     rcx, 2
0x180043e3b  add     rax, 2
0x180043e3f  dec     r9
0x180043e42  sub     rdx, 1
0x180043e46  jnz     short loc_180043E24
0x180043e48  test    rdx, rdx
0x180043e4b  lea     rcx, [rax-2]
0x180043e4f  mov     rdx, rsi
0x180043e52  cmovnz  rcx, rax
0x180043e56  lea     rax, [rsp+280h+Name]
0x180043e5b  mov     [rcx], r12w
0x180043e5f  cmp     [rax], r12w
0x180043e63  jz      short loc_180043E6F
0x180043e65  add     rax, 2
0x180043e69  sub     rdx, 1
0x180043e6d  jnz     short loc_180043E5F
0x180043e6f  mov     rcx, rsi
0x180043e72  mov     rax, rdx
0x180043e75  sub     rcx, rdx
0x180043e78  neg     rax
0x180043e7b  sbb     r8, r8
0x180043e7e  and     r8, rcx
0x180043e81  test    rdx, rdx
0x180043e84  jz      short loc_180043ED4
0x180043e86  mov     rax, rsi
0x180043e89  lea     rdx, [rsp+280h+Name]
0x180043e8e  lea     r9, aP0; "_p0"
0x180043e95  mov     rcx, r14
0x180043e98  lea     rdx, [rdx+r8*2]
0x180043e9c  sub     rax, r8
0x180043e9f  jz      short loc_180043EC5
0x180043ea1  test    rcx, rcx
0x180043ea4  jz      short loc_180043EC5
0x180043ea6  movzx   r8d, word ptr [r9]
0x180043eaa  test    r8w, r8w
0x180043eae  jz      short loc_180043EC5
0x180043eb0  mov     [rdx], r8w
0x180043eb4  add     r9, 2
0x180043eb8  add     rdx, 2
0x180043ebc  dec     rcx
0x180043ebf  sub     rax, 1
0x180043ec3  jnz     short loc_180043EA1
0x180043ec5  test    rax, rax
0x180043ec8  lea     rcx, [rdx-2]
0x180043ecc  cmovnz  rcx, rdx
0x180043ed0  mov     [rcx], r12w
0x180043ed4  lea     r8, [rsp+280h+Name]; lpName
0x180043ed9  xor     edx, edx; bInheritHandle
0x180043edb  mov     ecx, 1F0003h; dwDesiredAccess
0x180043ee0  call    cs:__imp_OpenSemaphoreW
0x180043ee7  nop     dword ptr [rax+rax+00h]
0x180043eec  mov     [rsp+280h+var_250], rax
0x180043ef1  mov     rbx, rax
0x180043ef4  test    rax, rax
0x180043ef7  jz      loc_180044073
0x180043efd  lea     rdx, [rsp+280h+var_25C]; int *
0x180043f02  mov     [rsp+280h+var_25C], r12d
0x180043f07  mov     rcx, rax; hHandle
0x180043f0a  mov     [rsp+280h+var_260], r12d; int
0x180043f0f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180043f14  mov     edi, eax
0x180043f16  test    eax, eax
0x180043f18  js      loc_180043FFD
0x180043f1e  mov     rdx, rsi
0x180043f21  lea     rax, [rsp+280h+Name]
0x180043f26  cmp     [rax], r12w
0x180043f2a  jz      short loc_180043F36
0x180043f2c  add     rax, 2
0x180043f30  sub     rdx, 1
0x180043f34  jnz     short loc_180043F26
0x180043f36  mov     rcx, rsi
0x180043f39  mov     rax, rdx
0x180043f3c  sub     rcx, rdx
0x180043f3f  neg     rax
0x180043f42  sbb     r8, r8
0x180043f45  and     r8, rcx
0x180043f48  test    rdx, rdx
0x180043f4b  jz      short loc_180043F92
0x180043f4d  lea     rax, [rsp+280h+Name]
0x180043f52  lea     rax, [rax+r8*2]
0x180043f56  lea     rcx, asc_1800A4120; "h"
0x180043f5d  sub     rsi, r8
0x180043f60  jz      short loc_180043F83
0x180043f62  test    r14, r14
0x180043f65  jz      short loc_180043F83
0x180043f67  movzx   edx, word ptr [rcx]
0x180043f6a  test    dx, dx
0x180043f6d  jz      short loc_180043F83
0x180043f6f  mov     [rax], dx
0x180043f72  add     rcx, 2
0x180043f76  add     rax, 2
0x180043f7a  dec     r14
0x180043f7d  sub     rsi, 1
0x180043f81  jnz     short loc_180043F62
0x180043f83  test    rsi, rsi
0x180043f86  lea     rdx, [rax-2]
0x180043f8a  cmovnz  rdx, rax
0x180043f8e  mov     [rdx], r12w
0x180043f92  lea     r8, [rsp+280h+Name]; lpName
0x180043f97  xor     edx, edx; bInheritHandle
0x180043f99  mov     ecx, 1F0003h; dwDesiredAccess
0x180043f9e  call    cs:__imp_OpenSemaphoreW
0x180043fa5  nop     dword ptr [rax+rax+00h]
0x180043faa  mov     [rsp+280h+var_258], rax
0x180043faf  test    rax, rax
0x180043fb2  jnz     short loc_180044013
0x180043fb4  mov     rcx, [rbp+188h]; this
0x180043fbb  mov     edx, 0DCh; void *
0x180043fc0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180043fc5  mov     rcx, rbx; this
0x180043fc8  mov     edi, eax
0x180043fca  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180043fcf  mov     eax, edi
0x180043fd1  mov     rcx, [rbp+180h+var_30]
0x180043fd8  xor     rcx, rsp; StackCookie
0x180043fdb  call    __security_check_cookie
0x180043fe0  lea     r11, [rsp+280h+var_20]
0x180043fe8  mov     rbx, [r11+30h]
0x180043fec  mov     rsi, [r11+38h]
0x180043ff0  mov     rsp, r11
0x180043ff3  pop     r15
0x180043ff5  pop     r14
0x180043ff7  pop     r12
0x180043ff9  pop     rdi
0x180043ffa  pop     rbp
0x180043ffb  retn
0x180043ffd  mov     rcx, [rbp+188h]; this
0x180044004  mov     r9d, eax; char *
0x180044007  mov     edx, 0D6h; void *
0x18004400c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044011  jmp     short loc_180044087
0x180044013  lea     rdx, [rsp+280h+var_260]; int *
0x180044018  mov     rcx, rax; hHandle
0x18004401b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180044020  mov     edi, eax
0x180044022  test    eax, eax
0x180044024  jns     short loc_180044046
0x180044026  mov     rcx, [rbp+188h]; this
0x18004402d  mov     r9d, eax; char *
0x180044030  mov     edx, 0DEh; void *
0x180044035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004403a  lea     rcx, [rsp+280h+var_258]
0x18004403f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044044  jmp     short loc_180044087
0x180044046  lea     rcx, [rsp+280h+var_258]
0x18004404b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044050  movsxd  rax, [rsp+280h+var_25C]
0x180044055  movsxd  rcx, [rsp+280h+var_260]
0x18004405a  shl     rcx, 1Fh
0x18004405e  or      rcx, rax
0x180044061  mov     [r15], rcx
0x180044064  mov     rcx, rbx; this
0x180044067  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18004406c  xor     eax, eax
0x18004406e  jmp     loc_180043FD1
0x180044073  call    cs:__imp_GetLastError
0x18004407a  nop     dword ptr [rax+rax+00h]
0x18004407f  cmp     eax, 2
0x180044082  jnz     short loc_180044096
0x180044084  mov     edi, r12d
0x180044087  lea     rcx, [rsp+280h+var_250]
0x18004408c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044091  jmp     loc_180043FCF
0x180044096  mov     rcx, [rbp+188h]; this
0x18004409d  mov     edx, 0D0h; void *
0x1800440a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800440a7  lea     rcx, [rsp+280h+var_250]
0x1800440ac  mov     ebx, eax
0x1800440ae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800440b3  mov     eax, ebx
0x1800440b5  jmp     loc_180043FD1
```
