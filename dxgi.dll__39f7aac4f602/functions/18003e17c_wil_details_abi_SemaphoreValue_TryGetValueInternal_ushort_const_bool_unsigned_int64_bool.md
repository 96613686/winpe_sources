# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18003e17c`
- end: `0x18003e45b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `735`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18003dec0`
- `0x18003e630`

## callees

- `0x18003e17c`
- `0x18003e464`
- `0x18003e5d0`
- `0x18003e710`
- `0x180067d2c`
- `0x1800697a8`
- `0x180075fa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003e288`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003e340`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003e288`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003e340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e39d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e39d`

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
  unsigned int LastError; // esi
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rbx
  WCHAR *v29; // rdx
  wil::details *v30; // rax
  const char *v31; // r9
  wil::details *v32; // rbx
  void *v33; // rdx
  const char *v35; // r9
  int v36; // eax
  void *v37; // rdx
  void *v38; // rdx
  void *v39; // rdx
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v42; // [rsp+28h] [rbp-D8h] BYREF
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
  v42 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v35);
    LastError = 0;
LABEL_42:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    return LastError;
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
    goto LABEL_42;
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
  v32 = v30;
  if ( !v30 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
LABEL_33:
    wil::details::CloseHandle(v20, v33);
    return LastError;
  }
  v36 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v40);
  LastError = v36;
  if ( v36 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (unsigned int)"wil", (const char *)(unsigned int)v36, v40);
    wil::details::CloseHandle(v32, v39);
    goto LABEL_33;
  }
  wil::details::CloseHandle(v32, v37);
  *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
  wil::details::CloseHandle(v20, v38);
  return 0;
}

```

## disassembly

```asm
0x18003e17c  mov     [rsp-8+arg_0], rbx
0x18003e181  mov     [rsp-8+arg_8], rsi
0x18003e186  push    rbp
0x18003e187  push    rdi
0x18003e188  push    r12
0x18003e18a  push    r14
0x18003e18c  push    r15
0x18003e18e  lea     rbp, [rsp-150h]
0x18003e196  sub     rsp, 250h
0x18003e19d  mov     rax, cs:__security_cookie
0x18003e1a4  xor     rax, rsp
0x18003e1a7  mov     [rbp+170h+var_30], rax
0x18003e1ae  xor     r12d, r12d
0x18003e1b1  lea     rax, [rsp+270h+Name]
0x18003e1b6  mov     r14d, 7FFFFFFEh
0x18003e1bc  mov     [r8], r12
0x18003e1bf  mov     ebx, 104h
0x18003e1c4  mov     r9d, r14d
0x18003e1c7  mov     edx, ebx
0x18003e1c9  mov     r15, r8
0x18003e1cc  test    r9, r9
0x18003e1cf  jz      short loc_18003E1F0
0x18003e1d1  movzx   r8d, word ptr [rcx]
0x18003e1d5  test    r8w, r8w
0x18003e1d9  jz      short loc_18003E1F0
0x18003e1db  mov     [rax], r8w
0x18003e1df  add     rcx, 2
0x18003e1e3  add     rax, 2
0x18003e1e7  dec     r9
0x18003e1ea  sub     rdx, 1
0x18003e1ee  jnz     short loc_18003E1CC
0x18003e1f0  test    rdx, rdx
0x18003e1f3  lea     rcx, [rax-2]
0x18003e1f7  mov     rdx, rbx
0x18003e1fa  cmovnz  rcx, rax
0x18003e1fe  lea     rax, [rsp+270h+Name]
0x18003e203  mov     [rcx], r12w
0x18003e207  cmp     [rax], r12w
0x18003e20b  jz      short loc_18003E217
0x18003e20d  add     rax, 2
0x18003e211  sub     rdx, 1
0x18003e215  jnz     short loc_18003E207
0x18003e217  mov     rcx, rbx
0x18003e21a  mov     rax, rdx
0x18003e21d  sub     rcx, rdx
0x18003e220  neg     rax
0x18003e223  sbb     r8, r8
0x18003e226  and     r8, rcx
0x18003e229  test    rdx, rdx
0x18003e22c  jz      short loc_18003E27C
0x18003e22e  mov     rax, rbx
0x18003e231  lea     rdx, [rsp+270h+Name]
0x18003e236  lea     r9, aP0; "_p0"
0x18003e23d  mov     rcx, r14
0x18003e240  lea     rdx, [rdx+r8*2]
0x18003e244  sub     rax, r8
0x18003e247  jz      short loc_18003E26D
0x18003e249  test    rcx, rcx
0x18003e24c  jz      short loc_18003E26D
0x18003e24e  movzx   r8d, word ptr [r9]
0x18003e252  test    r8w, r8w
0x18003e256  jz      short loc_18003E26D
0x18003e258  mov     [rdx], r8w
0x18003e25c  add     r9, 2
0x18003e260  add     rdx, 2
0x18003e264  dec     rcx
0x18003e267  sub     rax, 1
0x18003e26b  jnz     short loc_18003E249
0x18003e26d  test    rax, rax
0x18003e270  lea     rcx, [rdx-2]
0x18003e274  cmovnz  rcx, rdx
0x18003e278  mov     [rcx], r12w
0x18003e27c  lea     r8, [rsp+270h+Name]; lpName
0x18003e281  xor     edx, edx; bInheritHandle
0x18003e283  mov     ecx, 1F0003h; dwDesiredAccess
0x18003e288  call    cs:__imp_OpenSemaphoreW
0x18003e28e  mov     [rsp+270h+var_248], rax
0x18003e293  mov     rdi, rax
0x18003e296  test    rax, rax
0x18003e299  jz      loc_18003E39D
0x18003e29f  lea     rdx, [rsp+270h+var_24C]; int *
0x18003e2a4  mov     [rsp+270h+var_24C], r12d
0x18003e2a9  mov     rcx, rax; hHandle
0x18003e2ac  mov     [rsp+270h+var_250], r12d; int
0x18003e2b1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003e2b6  mov     esi, eax
0x18003e2b8  test    eax, eax
0x18003e2ba  js      loc_18003E42C
0x18003e2c0  mov     rdx, rbx
0x18003e2c3  lea     rax, [rsp+270h+Name]
0x18003e2c8  cmp     [rax], r12w
0x18003e2cc  jz      short loc_18003E2D8
0x18003e2ce  add     rax, 2
0x18003e2d2  sub     rdx, 1
0x18003e2d6  jnz     short loc_18003E2C8
0x18003e2d8  mov     rcx, rbx
0x18003e2db  mov     rax, rdx
0x18003e2de  sub     rcx, rdx
0x18003e2e1  neg     rax
0x18003e2e4  sbb     r8, r8
0x18003e2e7  and     r8, rcx
0x18003e2ea  test    rdx, rdx
0x18003e2ed  jz      short loc_18003E334
0x18003e2ef  lea     rax, [rsp+270h+Name]
0x18003e2f4  lea     rax, [rax+r8*2]
0x18003e2f8  lea     rcx, asc_1800D74C8; "h"
0x18003e2ff  sub     rbx, r8
0x18003e302  jz      short loc_18003E325
0x18003e304  test    r14, r14
0x18003e307  jz      short loc_18003E325
0x18003e309  movzx   edx, word ptr [rcx]
0x18003e30c  test    dx, dx
0x18003e30f  jz      short loc_18003E325
0x18003e311  mov     [rax], dx
0x18003e314  add     rcx, 2
0x18003e318  add     rax, 2
0x18003e31c  dec     r14
0x18003e31f  sub     rbx, 1
0x18003e323  jnz     short loc_18003E304
0x18003e325  test    rbx, rbx
0x18003e328  lea     rdx, [rax-2]
0x18003e32c  cmovnz  rdx, rax
0x18003e330  mov     [rdx], r12w
0x18003e334  lea     r8, [rsp+270h+Name]; lpName
0x18003e339  xor     edx, edx; bInheritHandle
0x18003e33b  mov     ecx, 1F0003h; dwDesiredAccess
0x18003e340  call    cs:__imp_OpenSemaphoreW
0x18003e346  mov     rbx, rax
0x18003e349  test    rax, rax
0x18003e34c  jnz     short loc_18003E3C6
0x18003e34e  mov     rcx, [rbp+178h]; this
0x18003e355  lea     r8, aWil; "wil"
0x18003e35c  mov     edx, 0DCh; void *
0x18003e361  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e366  mov     esi, eax
0x18003e368  mov     rcx, rdi; this
0x18003e36b  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003e370  mov     eax, esi
0x18003e372  mov     rcx, [rbp+170h+var_30]
0x18003e379  xor     rcx, rsp; StackCookie
0x18003e37c  call    __security_check_cookie
0x18003e381  lea     r11, [rsp+270h+var_20]
0x18003e389  mov     rbx, [r11+30h]
0x18003e38d  mov     rsi, [r11+38h]
0x18003e391  mov     rsp, r11
0x18003e394  pop     r15
0x18003e396  pop     r14
0x18003e398  pop     r12
0x18003e39a  pop     rdi
0x18003e39b  pop     rbp
0x18003e39c  retn
0x18003e39d  call    cs:__imp_GetLastError
0x18003e3a3  cmp     eax, 2
0x18003e3a6  jz      loc_18003E449
0x18003e3ac  mov     rcx, [rbp+178h]; this
0x18003e3b3  lea     r8, aWil; "wil"
0x18003e3ba  mov     edx, 0D0h; void *
0x18003e3bf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003e3c4  jmp     short loc_18003E372
0x18003e3c6  lea     rdx, [rsp+270h+var_250]; int *
0x18003e3cb  mov     rcx, rbx; hHandle
0x18003e3ce  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003e3d3  mov     esi, eax
0x18003e3d5  test    eax, eax
0x18003e3d7  js      short loc_18003E404
0x18003e3d9  mov     rcx, rbx; this
0x18003e3dc  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003e3e1  movsxd  rax, [rsp+270h+var_24C]
0x18003e3e6  movsxd  rcx, [rsp+270h+var_250]
0x18003e3eb  shl     rcx, 1Fh
0x18003e3ef  or      rcx, rax
0x18003e3f2  mov     [r15], rcx
0x18003e3f5  mov     rcx, rdi; this
0x18003e3f8  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003e3fd  xor     eax, eax
0x18003e3ff  jmp     loc_18003E372
0x18003e404  mov     rcx, [rbp+178h]; this
0x18003e40b  lea     r8, aWil; "wil"
0x18003e412  mov     r9d, eax; char *
0x18003e415  mov     edx, 0DEh; void *
0x18003e41a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e41f  mov     rcx, rbx; this
0x18003e422  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18003e427  jmp     loc_18003E368
0x18003e42c  mov     rcx, [rbp+178h]; this
0x18003e433  lea     r8, aWil; "wil"
0x18003e43a  mov     r9d, eax; char *
0x18003e43d  mov     edx, 0D6h; void *
0x18003e442  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003e447  jmp     short loc_18003E44C
0x18003e449  mov     esi, r12d
0x18003e44c  lea     rcx, [rsp+270h+var_248]
0x18003e451  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003e456  jmp     loc_18003E370
```
