# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180002bb0`
- end: `0x180002ea1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `753`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800024c4`
- `0x180003038`

## callees

- `0x1800023bc`
- `0x180002bb0`
- `0x180002ea8`
- `0x18000300c`
- `0x180005b60`
- `0x18000dc34`
- `0x18000fa10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002c72`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002ce9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002c72`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180002ce9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d46`

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
  wil::details *v14; // rax
  wil::details *v15; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  __int64 v18; // rdx
  WCHAR *v19; // rax
  __int64 v20; // r8
  wil::details *v21; // rax
  const char *v22; // r9
  wil::details *v23; // rbx
  void *v24; // rdx
  void *v26; // rdx
  const char *v27; // r9
  int v28; // eax
  void *v29; // rdx
  void *v30; // rdx
  void *v31; // rdx
  const unsigned __int16 *v32; // r9
  __int64 v33; // rcx
  WCHAR *v34; // rdx
  __int64 v35; // rax
  WCHAR *v36; // rcx
  WCHAR *v37; // rax
  const unsigned __int16 *v38; // rcx
  __int64 v39; // rbx
  WCHAR *v40; // rdx
  int v41; // [rsp+20h] [rbp-E0h] BYREF
  int v42; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v43; // [rsp+28h] [rbp-D8h] BYREF
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
    v32 = L"_p0";
    v33 = 2147483646;
    v34 = &Name[v13];
    v35 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v33 )
          break;
        if ( !*v32 )
          break;
        *v34++ = *v32++;
        --v33;
        --v35;
      }
      while ( v35 );
    }
    v36 = v34 - 1;
    if ( v35 )
      v36 = v34;
    *v36 = 0;
  }
  v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v43 = v14;
  v15 = v14;
  if ( !v14 )
  {
    if ( GetLastError() != 2 )
      return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v27);
    LastError = 0;
LABEL_42:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v43,
      v26);
    return LastError;
  }
  v42 = 0;
  v41 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v42);
  LastError = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, (int)"wil", (const char *)(unsigned int)ValueFromSemaphore);
    goto LABEL_42;
  }
  v18 = 260;
  v19 = Name;
  do
  {
    if ( !*v19 )
      break;
    ++v19;
    --v18;
  }
  while ( v18 );
  v20 = (260 - v18) & -(__int64)(v18 != 0);
  if ( v18 )
  {
    v37 = &Name[v20];
    v38 = L"h";
    v39 = 260 - v20;
    if ( 260 != v20 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v38 )
          break;
        *v37++ = *v38++;
        --v5;
        --v39;
      }
      while ( v39 );
    }
    v40 = v37 - 1;
    if ( v39 )
      v40 = v37;
    *v40 = 0;
  }
  v21 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v23 = v21;
  if ( !v21 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v22);
LABEL_19:
    wil::details::CloseHandle(v15, v24);
    return LastError;
  }
  v28 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v41);
  LastError = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v28);
    wil::details::CloseHandle(v23, v31);
    goto LABEL_19;
  }
  wil::details::CloseHandle(v23, v29);
  *a3 = v42 | (unsigned __int64)((__int64)v41 << 31);
  wil::details::CloseHandle(v15, v30);
  return 0;
}

```

## disassembly

```asm
0x180002bb0  mov     [rsp-8+arg_0], rbx
0x180002bb5  mov     [rsp-8+arg_8], rsi
0x180002bba  push    rbp
0x180002bbb  push    rdi
0x180002bbc  push    r12
0x180002bbe  push    r14
0x180002bc0  push    r15
0x180002bc2  lea     rbp, [rsp-150h]
0x180002bca  sub     rsp, 250h
0x180002bd1  mov     rax, cs:__security_cookie
0x180002bd8  xor     rax, rsp
0x180002bdb  mov     [rbp+170h+var_30], rax
0x180002be2  xor     r12d, r12d
0x180002be5  lea     rax, [rsp+270h+Name]
0x180002bea  mov     r14d, 7FFFFFFEh
0x180002bf0  mov     [r8], r12
0x180002bf3  mov     ebx, 104h
0x180002bf8  mov     r9d, r14d
0x180002bfb  mov     edx, ebx
0x180002bfd  mov     r15, r8
0x180002c00  test    r9, r9
0x180002c03  jz      short loc_180002C24
0x180002c05  movzx   r8d, word ptr [rcx]
0x180002c09  test    r8w, r8w
0x180002c0d  jz      short loc_180002C24
0x180002c0f  mov     [rax], r8w
0x180002c13  add     rcx, 2
0x180002c17  add     rax, 2
0x180002c1b  dec     r9
0x180002c1e  sub     rdx, 1
0x180002c22  jnz     short loc_180002C00
0x180002c24  test    rdx, rdx
0x180002c27  lea     rcx, [rax-2]
0x180002c2b  mov     rdx, rbx
0x180002c2e  cmovnz  rcx, rax
0x180002c32  lea     rax, [rsp+270h+Name]
0x180002c37  mov     [rcx], r12w
0x180002c3b  cmp     [rax], r12w
0x180002c3f  jz      short loc_180002C4B
0x180002c41  add     rax, 2
0x180002c45  sub     rdx, 1
0x180002c49  jnz     short loc_180002C3B
0x180002c4b  mov     rcx, rbx
0x180002c4e  mov     rax, rdx
0x180002c51  sub     rcx, rdx
0x180002c54  neg     rax
0x180002c57  sbb     r8, r8
0x180002c5a  and     r8, rcx
0x180002c5d  test    rdx, rdx
0x180002c60  jnz     loc_180002DD5
0x180002c66  lea     r8, [rsp+270h+Name]; lpName
0x180002c6b  xor     edx, edx; bInheritHandle
0x180002c6d  mov     ecx, 1F0003h; dwDesiredAccess
0x180002c72  call    cs:__imp_OpenSemaphoreW
0x180002c78  mov     [rsp+270h+var_248], rax
0x180002c7d  mov     rdi, rax
0x180002c80  test    rax, rax
0x180002c83  jz      loc_180002D46
0x180002c89  lea     rdx, [rsp+270h+var_24C]; int *
0x180002c8e  mov     [rsp+270h+var_24C], r12d
0x180002c93  mov     rcx, rax; hHandle
0x180002c96  mov     [rsp+270h+var_250], r12d; int
0x180002c9b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180002ca0  mov     esi, eax
0x180002ca2  test    eax, eax
0x180002ca4  js      loc_180002E72
0x180002caa  mov     rdx, rbx
0x180002cad  lea     rax, [rsp+270h+Name]
0x180002cb2  cmp     [rax], r12w
0x180002cb6  jz      short loc_180002CC2
0x180002cb8  add     rax, 2
0x180002cbc  sub     rdx, 1
0x180002cc0  jnz     short loc_180002CB2
0x180002cc2  mov     rcx, rbx
0x180002cc5  mov     rax, rdx
0x180002cc8  sub     rcx, rdx
0x180002ccb  neg     rax
0x180002cce  sbb     r8, r8
0x180002cd1  and     r8, rcx
0x180002cd4  test    rdx, rdx
0x180002cd7  jnz     loc_180002E28
0x180002cdd  lea     r8, [rsp+270h+Name]; lpName
0x180002ce2  xor     edx, edx; bInheritHandle
0x180002ce4  mov     ecx, 1F0003h; dwDesiredAccess
0x180002ce9  call    cs:__imp_OpenSemaphoreW
0x180002cef  mov     rbx, rax
0x180002cf2  test    rax, rax
0x180002cf5  jnz     short loc_180002D6F
0x180002cf7  mov     rcx, [rbp+178h]; this
0x180002cfe  lea     r8, aWil; "wil"
0x180002d05  mov     edx, 0DCh; void *
0x180002d0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002d0f  mov     esi, eax
0x180002d11  mov     rcx, rdi; this
0x180002d14  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002d19  mov     eax, esi
0x180002d1b  mov     rcx, [rbp+170h+var_30]
0x180002d22  xor     rcx, rsp; StackCookie
0x180002d25  call    __security_check_cookie
0x180002d2a  lea     r11, [rsp+270h+var_20]
0x180002d32  mov     rbx, [r11+30h]
0x180002d36  mov     rsi, [r11+38h]
0x180002d3a  mov     rsp, r11
0x180002d3d  pop     r15
0x180002d3f  pop     r14
0x180002d41  pop     r12
0x180002d43  pop     rdi
0x180002d44  pop     rbp
0x180002d45  retn
0x180002d46  call    cs:__imp_GetLastError
0x180002d4c  cmp     eax, 2
0x180002d4f  jz      loc_180002E8F
0x180002d55  mov     rcx, [rbp+178h]; this
0x180002d5c  lea     r8, aWil; "wil"
0x180002d63  mov     edx, 0D0h; void *
0x180002d68  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180002d6d  jmp     short loc_180002D1B
0x180002d6f  lea     rdx, [rsp+270h+var_250]; int *
0x180002d74  mov     rcx, rbx; hHandle
0x180002d77  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180002d7c  mov     esi, eax
0x180002d7e  test    eax, eax
0x180002d80  js      short loc_180002DAD
0x180002d82  mov     rcx, rbx; this
0x180002d85  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002d8a  movsxd  rax, [rsp+270h+var_24C]
0x180002d8f  movsxd  rcx, [rsp+270h+var_250]
0x180002d94  shl     rcx, 1Fh
0x180002d98  or      rcx, rax
0x180002d9b  mov     [r15], rcx
0x180002d9e  mov     rcx, rdi; this
0x180002da1  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002da6  xor     eax, eax
0x180002da8  jmp     loc_180002D1B
0x180002dad  mov     rcx, [rbp+178h]; this
0x180002db4  lea     r8, aWil; "wil"
0x180002dbb  mov     r9d, eax; char *
0x180002dbe  mov     edx, 0DEh; void *
0x180002dc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002dc8  mov     rcx, rbx; this
0x180002dcb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180002dd0  jmp     loc_180002D11
0x180002dd5  mov     rax, rbx
0x180002dd8  lea     rdx, [rsp+270h+Name]
0x180002ddd  lea     r9, aP0; "_p0"
0x180002de4  mov     rcx, r14
0x180002de7  lea     rdx, [rdx+r8*2]
0x180002deb  sub     rax, r8
0x180002dee  jz      short loc_180002E14
0x180002df0  test    rcx, rcx
0x180002df3  jz      short loc_180002E14
0x180002df5  movzx   r8d, word ptr [r9]
0x180002df9  test    r8w, r8w
0x180002dfd  jz      short loc_180002E14
0x180002dff  mov     [rdx], r8w
0x180002e03  add     r9, 2
0x180002e07  add     rdx, 2
0x180002e0b  dec     rcx
0x180002e0e  sub     rax, 1
0x180002e12  jnz     short loc_180002DF0
0x180002e14  test    rax, rax
0x180002e17  lea     rcx, [rdx-2]
0x180002e1b  cmovnz  rcx, rdx
0x180002e1f  mov     [rcx], r12w
0x180002e23  jmp     loc_180002C66
0x180002e28  lea     rax, [rsp+270h+Name]
0x180002e2d  lea     rax, [rax+r8*2]
0x180002e31  lea     rcx, asc_18001A200; "h"
0x180002e38  sub     rbx, r8
0x180002e3b  jz      short loc_180002E5E
0x180002e3d  test    r14, r14
0x180002e40  jz      short loc_180002E5E
0x180002e42  movzx   edx, word ptr [rcx]
0x180002e45  test    dx, dx
0x180002e48  jz      short loc_180002E5E
0x180002e4a  mov     [rax], dx
0x180002e4d  add     rcx, 2
0x180002e51  add     rax, 2
0x180002e55  dec     r14
0x180002e58  sub     rbx, 1
0x180002e5c  jnz     short loc_180002E3D
0x180002e5e  test    rbx, rbx
0x180002e61  lea     rdx, [rax-2]
0x180002e65  cmovnz  rdx, rax
0x180002e69  mov     [rdx], r12w
0x180002e6d  jmp     loc_180002CDD
0x180002e72  mov     rcx, [rbp+178h]; this
0x180002e79  lea     r8, aWil; "wil"
0x180002e80  mov     r9d, eax; char *
0x180002e83  mov     edx, 0D6h; void *
0x180002e88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180002e8d  jmp     short loc_180002E92
0x180002e8f  mov     esi, r12d
0x180002e92  lea     rcx, [rsp+270h+var_248]
0x180002e97  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180002e9c  jmp     loc_180002D19
```
