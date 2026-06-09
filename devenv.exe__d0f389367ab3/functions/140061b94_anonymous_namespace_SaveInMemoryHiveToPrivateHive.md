# _anonymous_namespace_::SaveInMemoryHiveToPrivateHive

- ea: `0x140061b94`
- end: `0x140061e95`
- name: `_anonymous_namespace_::SaveInMemoryHiveToPrivateHive`
- size: `769`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400249e0`

## callees

- `0x140001020`
- `0x140002160`
- `0x140002190`
- `0x14000fea0`
- `0x140061a60`
- `0x140061b94`

## import_xrefs

- `ADVAPI32!RegGetKeySecurity` at `0x140061bda`
- `ADVAPI32!RegGetKeySecurity` at `0x140061c77`
- `ADVAPI32!RegGetKeySecurity` at `0x140061bda`
- `ADVAPI32!RegGetKeySecurity` at `0x140061c77`
- `KERNEL32!FreeLibrary` at `0x140061e2f`
- `KERNEL32!FreeLibrary` at `0x140061e2f`
- `KERNEL32!GetProcAddress` at `0x140061caf`
- `KERNEL32!GetProcAddress` at `0x140061d0f`
- `KERNEL32!GetProcAddress` at `0x140061d7f`
- `KERNEL32!GetProcAddress` at `0x140061de7`
- `KERNEL32!GetProcAddress` at `0x140061caf`
- `KERNEL32!GetProcAddress` at `0x140061d0f`
- `KERNEL32!GetProcAddress` at `0x140061d7f`
- `KERNEL32!GetProcAddress` at `0x140061de7`
- `KERNEL32!GetLastError` at `0x140061cba`
- `KERNEL32!GetLastError` at `0x140061d1a`
- `KERNEL32!GetLastError` at `0x140061d8a`
- `KERNEL32!GetLastError` at `0x140061df2`
- `KERNEL32!GetLastError` at `0x140061cba`
- `KERNEL32!GetLastError` at `0x140061d1a`
- `KERNEL32!GetLastError` at `0x140061d8a`
- `KERNEL32!GetLastError` at `0x140061df2`

## string_xrefs

- `0x140061ca1`: `ORCreateHive`
- `0x140061d01`: `ORSetKeySecurity`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall anonymous_namespace_::SaveInMemoryHiveToPrivateHive(HKEY hKey)
{
  LSTATUS KeySecurity; // eax
  __int64 v3; // rcx
  signed int v4; // ebx
  volatile signed __int32 *v5; // rdi
  void *v6; // rbx
  volatile signed __int32 *v7; // rax
  LSTATUS v8; // eax
  signed int OffregModule; // eax
  FARPROC ProcAddress; // rax
  int v11; // eax
  __int64 v12; // rcx
  INT_PTR (__stdcall *v13)(); // rsi
  signed int LastError; // eax
  FARPROC v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  LPCWSTR v18; // rsi
  INT_PTR (__stdcall *v19)(); // r14
  signed int v20; // eax
  FARPROC v21; // rax
  int v22; // eax
  __int64 v23; // rcx
  INT_PTR (__stdcall *v24)(); // rsi
  signed int v25; // eax
  FARPROC v26; // rax
  int v27; // eax
  DWORD cbSecurityDescriptor; // [rsp+28h] [rbp-38h] BYREF
  INT_PTR (__stdcall *v30)(); // [rsp+30h] [rbp-30h] BYREF
  __int128 v31; // [rsp+38h] [rbp-28h]

  v31 = 0;
  cbSecurityDescriptor = 0;
  KeySecurity = RegGetKeySecurity(hKey, 7u, 0, &cbSecurityDescriptor);
  if ( KeySecurity != 122 )
  {
    v4 = (unsigned __int16)KeySecurity | 0x80070000;
    if ( KeySecurity <= 0 )
      v4 = KeySecurity;
    goto LABEL_4;
  }
  v6 = operator new[](cbSecurityDescriptor);
  if ( !v6 )
  {
    v4 = -2147024882;
LABEL_4:
    v5 = (volatile signed __int32 *)*((_QWORD *)&v31 + 1);
    goto LABEL_15;
  }
  v7 = (volatile signed __int32 *)operator new(0x18u);
  v5 = v7;
  if ( v7 )
  {
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count<_SECURITY_DESCRIPTOR>::`vftable';
    *((_QWORD *)v7 + 2) = v6;
  }
  else
  {
    v5 = 0;
  }
  operator delete(0, (const struct std::nothrow_t *)0x28);
  *(_QWORD *)&v31 = v6;
  *((_QWORD *)&v31 + 1) = v5;
  v8 = RegGetKeySecurity(hKey, 7u, v6, &cbSecurityDescriptor);
  if ( v8 )
  {
    v4 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v4 = v8;
  }
  else
  {
    v4 = 0;
  }
LABEL_15:
  if ( v4 < 0 )
    goto LABEL_60;
  OffregModule = anonymous_namespace_::GetOffregModule(v3);
  if ( !OffregModule )
  {
    ProcAddress = GetProcAddress(qword_14009F1F0, "ORCreateHive");
    if ( ProcAddress )
      goto LABEL_23;
    OffregModule = GetLastError();
  }
  v4 = (unsigned __int16)OffregModule | 0x80070000;
  if ( OffregModule <= 0 )
    v4 = OffregModule;
  if ( v4 < 0 )
    goto LABEL_60;
  ProcAddress = v30;
LABEL_23:
  v11 = ((__int64 (__fastcall *)(INT_PTR (__stdcall **)()))ProcAddress)(&v30);
  if ( v11 )
  {
    v4 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 <= 0 )
      v4 = v11;
    goto LABEL_60;
  }
  v13 = v30;
  LastError = anonymous_namespace_::GetOffregModule(v12);
  if ( !LastError )
  {
    v15 = GetProcAddress(qword_14009F1F0, "ORSetKeySecurity");
    if ( v15 )
      goto LABEL_34;
    LastError = GetLastError();
  }
  v4 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v4 = LastError;
  if ( v4 < 0 )
    goto LABEL_60;
  v15 = v30;
LABEL_34:
  _mm_lfence();
  v16 = ((__int64 (__fastcall *)(INT_PTR (__stdcall *)(), __int64, _QWORD))v15)(v13, 7, v31);
  if ( v16 )
  {
    v4 = (unsigned __int16)v16 | 0x80070000;
    if ( v16 <= 0 )
      v4 = v16;
    goto LABEL_60;
  }
  v18 = lpFile;
  v19 = v30;
  v20 = anonymous_namespace_::GetOffregModule(v17);
  if ( v20 )
    goto LABEL_41;
  v21 = GetProcAddress(qword_14009F1F0, "ORSaveHive");
  if ( !v21 )
  {
    v20 = GetLastError();
LABEL_41:
    v4 = (unsigned __int16)v20 | 0x80070000;
    if ( v20 <= 0 )
      v4 = v20;
    if ( v4 < 0 )
      goto LABEL_60;
    v21 = v30;
  }
  v22 = ((__int64 (__fastcall *)(INT_PTR (__stdcall *)(), LPCWSTR, __int64))v21)(v19, v18, 6);
  if ( v22 )
  {
    v4 = (unsigned __int16)v22 | 0x80070000;
    if ( v22 <= 0 )
      v4 = v22;
    goto LABEL_60;
  }
  v24 = v30;
  v25 = anonymous_namespace_::GetOffregModule(v23);
  if ( !v25 )
  {
    v26 = GetProcAddress(qword_14009F1F0, "ORCloseHive");
    if ( v26 )
    {
      v4 = 0;
      v27 = ((__int64 (__fastcall *)(INT_PTR (__stdcall *)()))v26)(v24);
      goto LABEL_57;
    }
    v25 = GetLastError();
  }
  v4 = (unsigned __int16)v25 | 0x80070000;
  if ( v25 <= 0 )
    v4 = v25;
  if ( v4 >= 0 )
  {
    v27 = ((__int64 (__fastcall *)(INT_PTR (__stdcall *)()))v30)(v24);
LABEL_57:
    if ( v27 )
    {
      v4 = (unsigned __int16)v27 | 0x80070000;
      if ( v27 <= 0 )
        v4 = v27;
    }
  }
LABEL_60:
  if ( qword_14009F1F0 )
  {
    FreeLibrary(qword_14009F1F0);
    qword_14009F1F0 = 0;
  }
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140061b94  mov     [rsp-18h+arg_8], rbx
0x140061b99  mov     [rsp-18h+arg_10], rsi
0x140061b9e  mov     [rsp-18h+arg_18], rdi
0x140061ba3  push    rbp
0x140061ba4  push    r14
0x140061ba6  push    r15
0x140061ba8  mov     rbp, rsp
0x140061bab  sub     rsp, 60h
0x140061baf  mov     rax, cs:__security_cookie
0x140061bb6  xor     rax, rsp
0x140061bb9  mov     [rbp+var_10], rax
0x140061bbd  mov     rsi, rcx
0x140061bc0  xorps   xmm1, xmm1
0x140061bc3  movdqu  [rbp+var_28], xmm1
0x140061bc8  and     [rbp+cbSecurityDescriptor], 0
0x140061bcc  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x140061bd0  xor     r8d, r8d; pSecurityDescriptor
0x140061bd3  lea     r14d, [r8+7]
0x140061bd7  mov     edx, r14d; SecurityInformation
0x140061bda  call    cs:__imp_RegGetKeySecurity
0x140061be0  mov     r15d, 80070000h
0x140061be6  cmp     eax, 7Ah ; 'z'
0x140061be9  jz      short loc_140061BFF
0x140061beb  movzx   ebx, ax
0x140061bee  or      ebx, r15d
0x140061bf1  test    eax, eax
0x140061bf3  cmovle  ebx, eax
0x140061bf6  mov     rdi, qword ptr [rbp+var_28+8]
0x140061bfa  jmp     loc_140061C90
0x140061bff  mov     ecx, [rbp+cbSecurityDescriptor]; unsigned __int64
0x140061c02  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140061c07  mov     rbx, rax
0x140061c0a  test    rax, rax
0x140061c0d  jnz     short loc_140061C16
0x140061c0f  mov     ebx, 8007000Eh
0x140061c14  jmp     short loc_140061BF6
0x140061c16  mov     [rbp+var_40], rbx
0x140061c1a  mov     ecx, 18h; Size
0x140061c1f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140061c24  mov     rdi, rax
0x140061c27  mov     [rbp+var_40], rax
0x140061c2b  test    rax, rax
0x140061c2e  jz      short loc_140061C54
0x140061c30  xorps   xmm0, xmm0
0x140061c33  movups  xmmword ptr [rax], xmm0
0x140061c36  mov     dword ptr [rax+8], 1
0x140061c3d  mov     dword ptr [rax+0Ch], 1
0x140061c44  lea     rax, ??_7?$_Ref_count@U_SECURITY_DESCRIPTOR@@@std@@6B@; const std::_Ref_count<_SECURITY_DESCRIPTOR>::`vftable'
0x140061c4b  mov     [rdi], rax
0x140061c4e  mov     [rdi+10h], rbx
0x140061c52  jmp     short loc_140061C56
0x140061c54  xor     edi, edi
0x140061c56  mov     edx, 28h ; '('; struct std::nothrow_t *
0x140061c5b  xor     ecx, ecx; void *
0x140061c5d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140061c62  mov     qword ptr [rbp+var_28], rbx
0x140061c66  mov     qword ptr [rbp+var_28+8], rdi
0x140061c6a  lea     r9, [rbp+cbSecurityDescriptor]; lpcbSecurityDescriptor
0x140061c6e  mov     r8, rbx; pSecurityDescriptor
0x140061c71  mov     edx, r14d; SecurityInformation
0x140061c74  mov     rcx, rsi; hKey
0x140061c77  call    cs:__imp_RegGetKeySecurity
0x140061c7d  test    eax, eax
0x140061c7f  jz      short loc_140061C8E
0x140061c81  movzx   ebx, ax
0x140061c84  or      ebx, r15d
0x140061c87  test    eax, eax
0x140061c89  cmovle  ebx, eax
0x140061c8c  jmp     short loc_140061C90
0x140061c8e  xor     ebx, ebx
0x140061c90  test    ebx, ebx
0x140061c92  js      loc_140061E23
0x140061c98  call    _anonymous_namespace___GetOffregModule
0x140061c9d  test    eax, eax
0x140061c9f  jnz     short loc_140061CC0
0x140061ca1  lea     rdx, aOrcreatehive; "ORCreateHive"
0x140061ca8  mov     rcx, cs:qword_14009F1F0; hModule
0x140061caf  call    cs:__imp_GetProcAddress
0x140061cb5  test    rax, rax
0x140061cb8  jnz     short loc_140061CD7
0x140061cba  call    cs:__imp_GetLastError
0x140061cc0  movzx   ebx, ax
0x140061cc3  or      ebx, r15d
0x140061cc6  test    eax, eax
0x140061cc8  cmovle  ebx, eax
0x140061ccb  test    ebx, ebx
0x140061ccd  js      loc_140061E23
0x140061cd3  mov     rax, [rbp+var_30]
0x140061cd7  lea     rcx, [rbp+var_30]
0x140061cdb  call    rax
0x140061cdd  test    eax, eax
0x140061cdf  jz      short loc_140061CF4
0x140061ce1  movzx   ebx, ax
0x140061ce4  or      ebx, r15d
0x140061ce7  test    eax, eax
0x140061ce9  cmovle  ebx, eax
0x140061cec  test    ebx, ebx
0x140061cee  js      loc_140061E23
0x140061cf4  mov     rsi, [rbp+var_30]
0x140061cf8  call    _anonymous_namespace___GetOffregModule
0x140061cfd  test    eax, eax
0x140061cff  jnz     short loc_140061D20
0x140061d01  lea     rdx, aOrsetkeysecuri; "ORSetKeySecurity"
0x140061d08  mov     rcx, cs:qword_14009F1F0; hModule
0x140061d0f  call    cs:__imp_GetProcAddress
0x140061d15  test    rax, rax
0x140061d18  jnz     short loc_140061D37
0x140061d1a  call    cs:__imp_GetLastError
0x140061d20  movzx   ebx, ax
0x140061d23  or      ebx, r15d
0x140061d26  test    eax, eax
0x140061d28  cmovle  ebx, eax
0x140061d2b  test    ebx, ebx
0x140061d2d  js      loc_140061E23
0x140061d33  mov     rax, [rbp+var_30]
0x140061d37  lfence
0x140061d3a  mov     r8, qword ptr [rbp+var_28]
0x140061d3e  mov     edx, r14d
0x140061d41  mov     rcx, rsi
0x140061d44  call    rax
0x140061d46  test    eax, eax
0x140061d48  jz      short loc_140061D5D
0x140061d4a  movzx   ebx, ax
0x140061d4d  or      ebx, r15d
0x140061d50  test    eax, eax
0x140061d52  cmovle  ebx, eax
0x140061d55  test    ebx, ebx
0x140061d57  js      loc_140061E23
0x140061d5d  mov     rsi, cs:lpFile
0x140061d64  mov     r14, [rbp+var_30]
0x140061d68  call    _anonymous_namespace___GetOffregModule
0x140061d6d  test    eax, eax
0x140061d6f  jnz     short loc_140061D90
0x140061d71  lea     rdx, aOrsavehive; "ORSaveHive"
0x140061d78  mov     rcx, cs:qword_14009F1F0; hModule
0x140061d7f  call    cs:__imp_GetProcAddress
0x140061d85  test    rax, rax
0x140061d88  jnz     short loc_140061DA7
0x140061d8a  call    cs:__imp_GetLastError
0x140061d90  movzx   ebx, ax
0x140061d93  or      ebx, r15d
0x140061d96  test    eax, eax
0x140061d98  cmovle  ebx, eax
0x140061d9b  test    ebx, ebx
0x140061d9d  js      loc_140061E23
0x140061da3  mov     rax, [rbp+var_30]
0x140061da7  mov     r9d, 1
0x140061dad  lea     r8d, [r9+5]
0x140061db1  mov     rdx, rsi
0x140061db4  mov     rcx, r14
0x140061db7  call    rax
0x140061db9  test    eax, eax
0x140061dbb  jz      short loc_140061DCC
0x140061dbd  movzx   ebx, ax
0x140061dc0  or      ebx, r15d
0x140061dc3  test    eax, eax
0x140061dc5  cmovle  ebx, eax
0x140061dc8  test    ebx, ebx
0x140061dca  js      short loc_140061E23
0x140061dcc  mov     rsi, [rbp+var_30]
0x140061dd0  call    _anonymous_namespace___GetOffregModule
0x140061dd5  test    eax, eax
0x140061dd7  jnz     short loc_140061DF8
0x140061dd9  lea     rdx, aOrclosehive; "ORCloseHive"
0x140061de0  mov     rcx, cs:qword_14009F1F0; hModule
0x140061de7  call    cs:__imp_GetProcAddress
0x140061ded  test    rax, rax
0x140061df0  jnz     short loc_140061E0D
0x140061df2  call    cs:__imp_GetLastError
0x140061df8  movzx   ebx, ax
0x140061dfb  or      ebx, r15d
0x140061dfe  test    eax, eax
0x140061e00  cmovle  ebx, eax
0x140061e03  test    ebx, ebx
0x140061e05  js      short loc_140061E23
0x140061e07  mov     rax, [rbp+var_30]
0x140061e0b  jmp     short loc_140061E0F
0x140061e0d  xor     ebx, ebx
0x140061e0f  mov     rcx, rsi
0x140061e12  call    rax
0x140061e14  test    eax, eax
0x140061e16  jz      short loc_140061E23
0x140061e18  movzx   ebx, ax
0x140061e1b  or      ebx, r15d
0x140061e1e  test    eax, eax
0x140061e20  cmovle  ebx, eax
0x140061e23  mov     rcx, cs:qword_14009F1F0; hLibModule
0x140061e2a  test    rcx, rcx
0x140061e2d  jz      short loc_140061E3D
0x140061e2f  call    cs:__imp_FreeLibrary
0x140061e35  and     cs:qword_14009F1F0, 0
0x140061e3d  test    rdi, rdi
0x140061e40  jz      short loc_140061E6D
0x140061e42  or      esi, 0FFFFFFFFh
0x140061e45  mov     eax, esi
0x140061e47  lock xadd [rdi+8], eax
0x140061e4c  add     eax, esi
0x140061e4e  jnz     short loc_140061E6D
0x140061e50  mov     rax, [rdi]
0x140061e53  mov     rcx, rdi
0x140061e56  call    qword ptr [rax]
0x140061e58  mov     edx, esi
0x140061e5a  lock xadd [rdi+0Ch], edx
0x140061e5f  add     edx, esi
0x140061e61  jnz     short loc_140061E6D
0x140061e63  mov     rdx, [rdi]
0x140061e66  mov     rcx, rdi
0x140061e69  call    qword ptr [rdx+8]
0x140061e6c  nop
0x140061e6d  mov     eax, ebx
0x140061e6f  mov     rcx, [rbp+var_10]
0x140061e73  xor     rcx, rsp; StackCookie
0x140061e76  call    __security_check_cookie
0x140061e7b  lea     r11, [rsp+60h+var_s0]
0x140061e80  mov     rbx, [r11+28h]
0x140061e84  mov     rsi, [r11+30h]
0x140061e88  mov     rdi, [r11+38h]
0x140061e8c  mov     rsp, r11
0x140061e8f  pop     r15
0x140061e91  pop     r14
0x140061e93  pop     rbp
0x140061e94  retn
```
