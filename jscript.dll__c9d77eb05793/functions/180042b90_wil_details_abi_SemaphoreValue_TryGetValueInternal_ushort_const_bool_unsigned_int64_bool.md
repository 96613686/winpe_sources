# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180042b90`
- end: `0x180042e63`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `723`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180042814`
- `0x180042888`

## callees

- `0x180042b90`
- `0x180042e6c`
- `0x180042fec`
- `0x180052ef4`
- `0x180053464`
- `0x1800535ec`
- `0x1800942d0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180042e22`
- `KERNEL32!GetLastError` at `0x180042e22`
- `KERNEL32!OpenSemaphoreW` at `0x180042c9c`
- `KERNEL32!OpenSemaphoreW` at `0x180042d54`
- `KERNEL32!OpenSemaphoreW` at `0x180042c9c`
- `KERNEL32!OpenSemaphoreW` at `0x180042d54`

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
0x180042b90  mov     [rsp-8+arg_0], rbx
0x180042b95  mov     [rsp-8+arg_8], rsi
0x180042b9a  push    rbp
0x180042b9b  push    rdi
0x180042b9c  push    r12
0x180042b9e  push    r14
0x180042ba0  push    r15
0x180042ba2  lea     rbp, [rsp-160h]
0x180042baa  sub     rsp, 260h
0x180042bb1  mov     rax, cs:__security_cookie
0x180042bb8  xor     rax, rsp
0x180042bbb  mov     [rbp+180h+var_30], rax
0x180042bc2  xor     r12d, r12d
0x180042bc5  lea     rax, [rsp+280h+Name]
0x180042bca  mov     r14d, 7FFFFFFEh
0x180042bd0  mov     [r8], r12
0x180042bd3  mov     esi, 104h
0x180042bd8  mov     r9d, r14d
0x180042bdb  mov     edx, esi
0x180042bdd  mov     r15, r8
0x180042be0  test    r9, r9
0x180042be3  jz      short loc_180042C04
0x180042be5  movzx   r8d, word ptr [rcx]
0x180042be9  test    r8w, r8w
0x180042bed  jz      short loc_180042C04
0x180042bef  mov     [rax], r8w
0x180042bf3  add     rcx, 2
0x180042bf7  add     rax, 2
0x180042bfb  dec     r9
0x180042bfe  sub     rdx, 1
0x180042c02  jnz     short loc_180042BE0
0x180042c04  test    rdx, rdx
0x180042c07  lea     rcx, [rax-2]
0x180042c0b  mov     rdx, rsi
0x180042c0e  cmovnz  rcx, rax
0x180042c12  lea     rax, [rsp+280h+Name]
0x180042c17  mov     [rcx], r12w
0x180042c1b  cmp     [rax], r12w
0x180042c1f  jz      short loc_180042C2B
0x180042c21  add     rax, 2
0x180042c25  sub     rdx, 1
0x180042c29  jnz     short loc_180042C1B
0x180042c2b  mov     rcx, rsi
0x180042c2e  mov     rax, rdx
0x180042c31  sub     rcx, rdx
0x180042c34  neg     rax
0x180042c37  sbb     r8, r8
0x180042c3a  and     r8, rcx
0x180042c3d  test    rdx, rdx
0x180042c40  jz      short loc_180042C90
0x180042c42  mov     rax, rsi
0x180042c45  lea     rdx, [rsp+280h+Name]
0x180042c4a  lea     r9, aP0; "_p0"
0x180042c51  mov     rcx, r14
0x180042c54  lea     rdx, [rdx+r8*2]
0x180042c58  sub     rax, r8
0x180042c5b  jz      short loc_180042C81
0x180042c5d  test    rcx, rcx
0x180042c60  jz      short loc_180042C81
0x180042c62  movzx   r8d, word ptr [r9]
0x180042c66  test    r8w, r8w
0x180042c6a  jz      short loc_180042C81
0x180042c6c  mov     [rdx], r8w
0x180042c70  add     r9, 2
0x180042c74  add     rdx, 2
0x180042c78  dec     rcx
0x180042c7b  sub     rax, 1
0x180042c7f  jnz     short loc_180042C5D
0x180042c81  test    rax, rax
0x180042c84  lea     rcx, [rdx-2]
0x180042c88  cmovnz  rcx, rdx
0x180042c8c  mov     [rcx], r12w
0x180042c90  lea     r8, [rsp+280h+Name]; lpName
0x180042c95  xor     edx, edx; bInheritHandle
0x180042c97  mov     ecx, 1F0003h; dwDesiredAccess
0x180042c9c  call    cs:__imp_OpenSemaphoreW
0x180042ca2  mov     [rsp+280h+var_250], rax
0x180042ca7  mov     rbx, rax
0x180042caa  test    rax, rax
0x180042cad  jz      loc_180042E22
0x180042cb3  lea     rdx, [rsp+280h+var_25C]; int *
0x180042cb8  mov     [rsp+280h+var_25C], r12d
0x180042cbd  mov     rcx, rax; hHandle
0x180042cc0  mov     [rsp+280h+var_260], r12d; int
0x180042cc5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180042cca  mov     edi, eax
0x180042ccc  test    eax, eax
0x180042cce  js      loc_180042DAC
0x180042cd4  mov     rdx, rsi
0x180042cd7  lea     rax, [rsp+280h+Name]
0x180042cdc  cmp     [rax], r12w
0x180042ce0  jz      short loc_180042CEC
0x180042ce2  add     rax, 2
0x180042ce6  sub     rdx, 1
0x180042cea  jnz     short loc_180042CDC
0x180042cec  mov     rcx, rsi
0x180042cef  mov     rax, rdx
0x180042cf2  sub     rcx, rdx
0x180042cf5  neg     rax
0x180042cf8  sbb     r8, r8
0x180042cfb  and     r8, rcx
0x180042cfe  test    rdx, rdx
0x180042d01  jz      short loc_180042D48
0x180042d03  lea     rax, [rsp+280h+Name]
0x180042d08  lea     rax, [rax+r8*2]
0x180042d0c  lea     rcx, asc_1800A1FB0; "h"
0x180042d13  sub     rsi, r8
0x180042d16  jz      short loc_180042D39
0x180042d18  test    r14, r14
0x180042d1b  jz      short loc_180042D39
0x180042d1d  movzx   edx, word ptr [rcx]
0x180042d20  test    dx, dx
0x180042d23  jz      short loc_180042D39
0x180042d25  mov     [rax], dx
0x180042d28  add     rcx, 2
0x180042d2c  add     rax, 2
0x180042d30  dec     r14
0x180042d33  sub     rsi, 1
0x180042d37  jnz     short loc_180042D18
0x180042d39  test    rsi, rsi
0x180042d3c  lea     rdx, [rax-2]
0x180042d40  cmovnz  rdx, rax
0x180042d44  mov     [rdx], r12w
0x180042d48  lea     r8, [rsp+280h+Name]; lpName
0x180042d4d  xor     edx, edx; bInheritHandle
0x180042d4f  mov     ecx, 1F0003h; dwDesiredAccess
0x180042d54  call    cs:__imp_OpenSemaphoreW
0x180042d5a  mov     [rsp+280h+var_258], rax
0x180042d5f  test    rax, rax
0x180042d62  jnz     short loc_180042DC2
0x180042d64  mov     rcx, [rbp+188h]; this
0x180042d6b  mov     edx, 0DCh; void *
0x180042d70  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042d75  mov     rcx, rbx; this
0x180042d78  mov     edi, eax
0x180042d7a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180042d7f  mov     eax, edi
0x180042d81  mov     rcx, [rbp+180h+var_30]
0x180042d88  xor     rcx, rsp; StackCookie
0x180042d8b  call    __security_check_cookie
0x180042d90  lea     r11, [rsp+280h+var_20]
0x180042d98  mov     rbx, [r11+30h]
0x180042d9c  mov     rsi, [r11+38h]
0x180042da0  mov     rsp, r11
0x180042da3  pop     r15
0x180042da5  pop     r14
0x180042da7  pop     r12
0x180042da9  pop     rdi
0x180042daa  pop     rbp
0x180042dab  retn
0x180042dac  mov     rcx, [rbp+188h]; this
0x180042db3  mov     r9d, eax; char *
0x180042db6  mov     edx, 0D6h; void *
0x180042dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042dc0  jmp     short loc_180042E30
0x180042dc2  lea     rdx, [rsp+280h+var_260]; int *
0x180042dc7  mov     rcx, rax; hHandle
0x180042dca  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180042dcf  mov     edi, eax
0x180042dd1  test    eax, eax
0x180042dd3  jns     short loc_180042DF5
0x180042dd5  mov     rcx, [rbp+188h]; this
0x180042ddc  mov     r9d, eax; char *
0x180042ddf  mov     edx, 0DEh; void *
0x180042de4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042de9  lea     rcx, [rsp+280h+var_258]
0x180042dee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180042df3  jmp     short loc_180042E30
0x180042df5  lea     rcx, [rsp+280h+var_258]
0x180042dfa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180042dff  movsxd  rax, [rsp+280h+var_25C]
0x180042e04  movsxd  rcx, [rsp+280h+var_260]
0x180042e09  shl     rcx, 1Fh
0x180042e0d  or      rcx, rax
0x180042e10  mov     [r15], rcx
0x180042e13  mov     rcx, rbx; this
0x180042e16  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180042e1b  xor     eax, eax
0x180042e1d  jmp     loc_180042D81
0x180042e22  call    cs:__imp_GetLastError
0x180042e28  cmp     eax, 2
0x180042e2b  jnz     short loc_180042E3F
0x180042e2d  mov     edi, r12d
0x180042e30  lea     rcx, [rsp+280h+var_250]
0x180042e35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180042e3a  jmp     loc_180042D7F
0x180042e3f  mov     rcx, [rbp+188h]; this
0x180042e46  mov     edx, 0D0h; void *
0x180042e4b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180042e50  lea     rcx, [rsp+280h+var_250]
0x180042e55  mov     ebx, eax
0x180042e57  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180042e5c  mov     eax, ebx
0x180042e5e  jmp     loc_180042D81
```
