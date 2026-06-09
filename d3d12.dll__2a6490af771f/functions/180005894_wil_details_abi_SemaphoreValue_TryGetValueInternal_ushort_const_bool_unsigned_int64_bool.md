# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005894`
- end: `0x180005b57`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `707`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180005584`
- `0x180005644`

## callees

- `0x180005894`
- `0x180005b60`
- `0x180005cbc`
- `0x180009d5c`
- `0x18000a600`
- `0x18000a998`
- `0x18000b410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800059a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005a58`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800059a0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005a58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005aae`

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
  unsigned int v22; // r8d
  unsigned int LastError; // esi
  __int64 v24; // rdx
  WCHAR *v25; // rax
  __int64 v26; // r8
  WCHAR *v27; // rax
  const unsigned __int16 *v28; // rcx
  __int64 v29; // rbx
  WCHAR *v30; // rdx
  wil::details *v31; // rax
  unsigned int v32; // r8d
  const char *v33; // r9
  wil::details *v34; // rbx
  void *v35; // rdx
  unsigned int v37; // r8d
  const char *v38; // r9
  int v39; // eax
  void *v40; // rdx
  unsigned int v41; // r8d
  void *v42; // rdx
  void *v43; // rdx
  int v44; // [rsp+20h] [rbp-E0h] BYREF
  int v45; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v46; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

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
  v46 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v37, v38);
    LastError = 0;
LABEL_42:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v46);
    return LastError;
  }
  v45 = 0;
  v44 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v45);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v22, (const char *)(unsigned int)ValueFromSemaphore, v44);
    goto LABEL_42;
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
  v31 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v34 = v31;
  if ( !v31 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v32, v33);
LABEL_33:
    wil::details::CloseHandle(v20, v35);
    return LastError;
  }
  v39 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v31, &v44);
  LastError = v39;
  if ( v39 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v41, (const char *)(unsigned int)v39, v44);
    wil::details::CloseHandle(v34, v43);
    goto LABEL_33;
  }
  wil::details::CloseHandle(v34, v40);
  *a3 = v45 | (unsigned __int64)((__int64)v44 << 31);
  wil::details::CloseHandle(v20, v42);
  return 0;
}

```

## disassembly

```asm
0x180005894  mov     [rsp-8+arg_0], rbx
0x180005899  mov     [rsp-8+arg_8], rsi
0x18000589e  push    rbp
0x18000589f  push    rdi
0x1800058a0  push    r12
0x1800058a2  push    r14
0x1800058a4  push    r15
0x1800058a6  lea     rbp, [rsp-150h]
0x1800058ae  sub     rsp, 250h
0x1800058b5  mov     rax, cs:__security_cookie
0x1800058bc  xor     rax, rsp
0x1800058bf  mov     [rbp+170h+var_30], rax
0x1800058c6  xor     r12d, r12d
0x1800058c9  lea     rax, [rsp+270h+Name]
0x1800058ce  mov     r14d, 7FFFFFFEh
0x1800058d4  mov     [r8], r12
0x1800058d7  mov     ebx, 104h
0x1800058dc  mov     r9d, r14d
0x1800058df  mov     edx, ebx
0x1800058e1  mov     r15, r8
0x1800058e4  test    r9, r9
0x1800058e7  jz      short loc_180005908
0x1800058e9  movzx   r8d, word ptr [rcx]
0x1800058ed  test    r8w, r8w
0x1800058f1  jz      short loc_180005908
0x1800058f3  mov     [rax], r8w
0x1800058f7  add     rcx, 2
0x1800058fb  add     rax, 2
0x1800058ff  dec     r9
0x180005902  sub     rdx, 1
0x180005906  jnz     short loc_1800058E4
0x180005908  test    rdx, rdx
0x18000590b  lea     rcx, [rax-2]
0x18000590f  mov     rdx, rbx
0x180005912  cmovnz  rcx, rax
0x180005916  lea     rax, [rsp+270h+Name]
0x18000591b  mov     [rcx], r12w
0x18000591f  cmp     [rax], r12w
0x180005923  jz      short loc_18000592F
0x180005925  add     rax, 2
0x180005929  sub     rdx, 1
0x18000592d  jnz     short loc_18000591F
0x18000592f  mov     rcx, rbx
0x180005932  mov     rax, rdx
0x180005935  sub     rcx, rdx
0x180005938  neg     rax
0x18000593b  sbb     r8, r8
0x18000593e  and     r8, rcx
0x180005941  test    rdx, rdx
0x180005944  jz      short loc_180005994
0x180005946  mov     rax, rbx
0x180005949  lea     rdx, [rsp+270h+Name]
0x18000594e  lea     r9, aP0; "_p0"
0x180005955  mov     rcx, r14
0x180005958  lea     rdx, [rdx+r8*2]
0x18000595c  sub     rax, r8
0x18000595f  jz      short loc_180005985
0x180005961  test    rcx, rcx
0x180005964  jz      short loc_180005985
0x180005966  movzx   r8d, word ptr [r9]
0x18000596a  test    r8w, r8w
0x18000596e  jz      short loc_180005985
0x180005970  mov     [rdx], r8w
0x180005974  add     r9, 2
0x180005978  add     rdx, 2
0x18000597c  dec     rcx
0x18000597f  sub     rax, 1
0x180005983  jnz     short loc_180005961
0x180005985  test    rax, rax
0x180005988  lea     rcx, [rdx-2]
0x18000598c  cmovnz  rcx, rdx
0x180005990  mov     [rcx], r12w
0x180005994  lea     r8, [rsp+270h+Name]; lpName
0x180005999  xor     edx, edx; bInheritHandle
0x18000599b  mov     ecx, 1F0003h; dwDesiredAccess
0x1800059a0  call    cs:__imp_OpenSemaphoreW
0x1800059a6  mov     [rsp+270h+var_248], rax
0x1800059ab  mov     rdi, rax
0x1800059ae  test    rax, rax
0x1800059b1  jz      loc_180005AAE
0x1800059b7  lea     rdx, [rsp+270h+var_24C]; int *
0x1800059bc  mov     [rsp+270h+var_24C], r12d
0x1800059c1  mov     rcx, rax; hHandle
0x1800059c4  mov     [rsp+270h+var_250], r12d; int
0x1800059c9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800059ce  mov     esi, eax
0x1800059d0  test    eax, eax
0x1800059d2  js      loc_180005B2F
0x1800059d8  mov     rdx, rbx
0x1800059db  lea     rax, [rsp+270h+Name]
0x1800059e0  cmp     [rax], r12w
0x1800059e4  jz      short loc_1800059F0
0x1800059e6  add     rax, 2
0x1800059ea  sub     rdx, 1
0x1800059ee  jnz     short loc_1800059E0
0x1800059f0  mov     rcx, rbx
0x1800059f3  mov     rax, rdx
0x1800059f6  sub     rcx, rdx
0x1800059f9  neg     rax
0x1800059fc  sbb     r8, r8
0x1800059ff  and     r8, rcx
0x180005a02  test    rdx, rdx
0x180005a05  jz      short loc_180005A4C
0x180005a07  lea     rax, [rsp+270h+Name]
0x180005a0c  lea     rax, [rax+r8*2]
0x180005a10  lea     rcx, asc_180017098; "h"
0x180005a17  sub     rbx, r8
0x180005a1a  jz      short loc_180005A3D
0x180005a1c  test    r14, r14
0x180005a1f  jz      short loc_180005A3D
0x180005a21  movzx   edx, word ptr [rcx]
0x180005a24  test    dx, dx
0x180005a27  jz      short loc_180005A3D
0x180005a29  mov     [rax], dx
0x180005a2c  add     rcx, 2
0x180005a30  add     rax, 2
0x180005a34  dec     r14
0x180005a37  sub     rbx, 1
0x180005a3b  jnz     short loc_180005A1C
0x180005a3d  test    rbx, rbx
0x180005a40  lea     rdx, [rax-2]
0x180005a44  cmovnz  rdx, rax
0x180005a48  mov     [rdx], r12w
0x180005a4c  lea     r8, [rsp+270h+Name]; lpName
0x180005a51  xor     edx, edx; bInheritHandle
0x180005a53  mov     ecx, 1F0003h; dwDesiredAccess
0x180005a58  call    cs:__imp_OpenSemaphoreW
0x180005a5e  mov     rbx, rax
0x180005a61  test    rax, rax
0x180005a64  jnz     short loc_180005AD0
0x180005a66  mov     rcx, [rbp+178h]; this
0x180005a6d  mov     edx, 0DCh; void *
0x180005a72  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005a77  mov     esi, eax
0x180005a79  mov     rcx, rdi; this
0x180005a7c  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005a81  mov     eax, esi
0x180005a83  mov     rcx, [rbp+170h+var_30]
0x180005a8a  xor     rcx, rsp; StackCookie
0x180005a8d  call    __security_check_cookie
0x180005a92  lea     r11, [rsp+270h+var_20]
0x180005a9a  mov     rbx, [r11+30h]
0x180005a9e  mov     rsi, [r11+38h]
0x180005aa2  mov     rsp, r11
0x180005aa5  pop     r15
0x180005aa7  pop     r14
0x180005aa9  pop     r12
0x180005aab  pop     rdi
0x180005aac  pop     rbp
0x180005aad  retn
0x180005aae  call    cs:__imp_GetLastError
0x180005ab4  cmp     eax, 2
0x180005ab7  jz      loc_180005B45
0x180005abd  mov     rcx, [rbp+178h]; this
0x180005ac4  mov     edx, 0D0h; void *
0x180005ac9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005ace  jmp     short loc_180005A83
0x180005ad0  lea     rdx, [rsp+270h+var_250]; int *
0x180005ad5  mov     rcx, rbx; hHandle
0x180005ad8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005add  mov     esi, eax
0x180005adf  test    eax, eax
0x180005ae1  js      short loc_180005B0E
0x180005ae3  mov     rcx, rbx; this
0x180005ae6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005aeb  movsxd  rax, [rsp+270h+var_24C]
0x180005af0  movsxd  rcx, [rsp+270h+var_250]
0x180005af5  shl     rcx, 1Fh
0x180005af9  or      rcx, rax
0x180005afc  mov     [r15], rcx
0x180005aff  mov     rcx, rdi; this
0x180005b02  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005b07  xor     eax, eax
0x180005b09  jmp     loc_180005A83
0x180005b0e  mov     rcx, [rbp+178h]; this
0x180005b15  mov     r9d, eax; char *
0x180005b18  mov     edx, 0DEh; void *
0x180005b1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b22  mov     rcx, rbx; this
0x180005b25  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005b2a  jmp     loc_180005A79
0x180005b2f  mov     rcx, [rbp+178h]; this
0x180005b36  mov     r9d, eax; char *
0x180005b39  mov     edx, 0D6h; void *
0x180005b3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005b43  jmp     short loc_180005B48
0x180005b45  mov     esi, r12d
0x180005b48  lea     rcx, [rsp+270h+var_248]
0x180005b4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005b52  jmp     loc_180005A81
```
