# AppContainerRegistrationHelper::DeriveTopLevelRegistryKey(void *,ushort const *,ushort const *,ushort *,unsigned __int64)

- ea: `0x180003d30`
- end: `0x180004029`
- name: `?DeriveTopLevelRegistryKey@AppContainerRegistrationHelper@@CAJPEAXPEBG1PEAG_K@Z`
- size: `761`
- prototype: `static int(void *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000a18c`
- `0x1800153b8`
- `0x180016554`

## callees

- `0x180002030`
- `0x180003d30`
- `0x180004030`
- `0x1800044e0`
- `0x1800067c0`
- `0x180022830`

## import_xrefs

- `profapi!__imp_GetAppContainerRegistryPath` at `0x180003fbc`
- `profapi!__imp_GetAppContainerRegistryPath` at `0x180003fbc`

## string_xrefs

- `0x180003f89`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180004001`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x180003f22`: `Path %ls Name %ls`
- `0x180003f44`: `Path %ls Name %ls`
- `0x180003f66`: `Path %ls Name %ls`
- `0x180003fa4`: `Name %ls Sid %ls`
- `0x180003fd7`: `Name %ls Sid %ls`
- `0x180004008`: `path %ls`

## pseudocode

```c
__int64 __fastcall AppContainerRegistrationHelper::DeriveTopLevelRegistryKey(
        void *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  __int64 v4; // rdi
  __int64 v8; // rbx
  unsigned int v9; // r12d
  HRESULT AppContainerRegistryPath; // ebp
  wchar_t *v11; // rcx
  __int64 result; // rax
  unsigned __int16 *v13; // rdx
  const unsigned __int16 *v14; // r9
  __int64 v15; // rcx
  wchar_t *v16; // r8
  size_t v17; // rdx
  wchar_t *v18; // rcx
  const unsigned __int16 *v19; // r9
  __int64 v20; // rcx
  wchar_t *v21; // r8
  size_t v22; // rdx
  wchar_t *v23; // rcx
  size_t pcchLength[2]; // [rsp+40h] [rbp-468h] BYREF
  wchar_t psz[520]; // [rsp+50h] [rbp-458h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+0h]

  v4 = 520;
  v8 = 2147483646;
  v9 = -2147024774;
  if ( !a1 )
  {
    AppContainerRegistryPath = StringCchPrintfW(
                                 psz,
                                 0x208u,
                                 L"%s\\Software\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\Ap"
                                  "pContainer\\Storage\\%s",
                                 a3,
                                 a2);
    if ( AppContainerRegistryPath >= 0 )
      goto LABEL_3;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2B2,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)AppContainerRegistryPath,
      (int)"Name %ls Sid %ls",
      (const char *)a2,
      a3);
    return (unsigned int)AppContainerRegistryPath;
  }
  AppContainerRegistryPath = GetAppContainerRegistryPath(psz, 520);
  if ( AppContainerRegistryPath < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2B7,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)AppContainerRegistryPath,
      (int)"Name %ls Sid %ls",
      (const char *)a2,
      a3);
    return (unsigned int)AppContainerRegistryPath;
  }
  pcchLength[0] = 0;
  AppContainerRegistryPath = StringLengthWorkerW(psz, 0x208u, pcchLength);
  if ( AppContainerRegistryPath < 0 )
    goto LABEL_29;
  v14 = L"\\Children";
  v15 = 2147483646;
  v16 = &psz[pcchLength[0]];
  v17 = 520 - pcchLength[0];
  if ( pcchLength[0] != 520 )
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
  AppContainerRegistryPath = -2147024774;
  if ( v17 )
  {
    v18 = v16;
    AppContainerRegistryPath = 0;
  }
  *v18 = 0;
  if ( !v17 )
  {
LABEL_29:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2BD,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)AppContainerRegistryPath,
      (int)"Path %ls Name %ls",
      (const char *)psz,
      a2);
    return (unsigned int)AppContainerRegistryPath;
  }
  pcchLength[0] = 0;
  AppContainerRegistryPath = StringLengthWorkerW(psz, 0x208u, pcchLength);
  if ( AppContainerRegistryPath < 0 )
    goto LABEL_30;
  v19 = L"\\";
  v20 = 2147483646;
  v21 = &psz[pcchLength[0]];
  v22 = 520 - pcchLength[0];
  if ( pcchLength[0] != 520 )
  {
    do
    {
      if ( !v20 )
        break;
      if ( !*v19 )
        break;
      *v21++ = *v19++;
      --v20;
      --v22;
    }
    while ( v22 );
  }
  v23 = v21 - 1;
  AppContainerRegistryPath = -2147024774;
  if ( v22 )
  {
    v23 = v21;
    AppContainerRegistryPath = 0;
  }
  *v23 = 0;
  if ( !v22 )
  {
LABEL_30:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2C0,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)AppContainerRegistryPath,
      (int)"Path %ls Name %ls",
      (const char *)psz,
      a2);
    return (unsigned int)AppContainerRegistryPath;
  }
  AppContainerRegistryPath = StringCchCatW(psz, 0x208u, a2);
  if ( AppContainerRegistryPath < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2C3,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)(unsigned int)AppContainerRegistryPath,
      (int)"Path %ls Name %ls",
      (const char *)psz,
      a2);
    return (unsigned int)AppContainerRegistryPath;
  }
LABEL_3:
  v11 = psz;
  do
  {
    if ( !v8 )
      break;
    if ( !*v11 )
      break;
    *a4++ = *v11++;
    --v8;
    --v4;
  }
  while ( v4 );
  result = 0;
  v13 = a4 - 1;
  if ( v4 )
  {
    v13 = a4;
    v9 = 0;
  }
  *v13 = 0;
  if ( !v4 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x2C6,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
      (const char *)v9,
      (int)"path %ls",
      (const char *)psz);
    return v9;
  }
  return result;
}

```

## disassembly

```asm
0x180003d30  push    rbx
0x180003d32  push    rbp
0x180003d33  push    rsi
0x180003d34  push    rdi
0x180003d35  push    r12
0x180003d37  push    r14
0x180003d39  push    r15
0x180003d3b  sub     rsp, 470h
0x180003d42  mov     rax, cs:__security_cookie
0x180003d49  xor     rax, rsp
0x180003d4c  mov     [rsp+4A8h+var_48], rax
0x180003d54  mov     edi, 208h
0x180003d59  mov     r14, rdx
0x180003d5c  test    rcx, rcx
0x180003d5f  mov     edx, edi; unsigned __int64
0x180003d61  mov     rsi, r9
0x180003d64  lea     rcx, [rsp+4A8h+psz]; unsigned __int16 *
0x180003d69  mov     r15, r8
0x180003d6c  mov     ebx, 7FFFFFFEh
0x180003d71  mov     r12d, 8007007Ah
0x180003d77  jnz     loc_180003FBC
0x180003d7d  mov     r9, r8
0x180003d80  mov     qword ptr [rsp+4A8h+var_488], r14
0x180003d85  lea     r8, aSSoftwareClass_2; "%s\\Software\\Classes\\Local Settings\\"...
0x180003d8c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003d91  mov     ebp, eax
0x180003d93  test    eax, eax
0x180003d95  js      loc_180003F9F
0x180003d9b  lea     rcx, [rsp+4A8h+psz]
0x180003da0  test    rbx, rbx
0x180003da3  jz      short loc_180003DC1
0x180003da5  movzx   eax, word ptr [rcx]
0x180003da8  test    ax, ax
0x180003dab  jz      short loc_180003DC1
0x180003dad  mov     [rsi], ax
0x180003db0  add     rcx, 2
0x180003db4  add     rsi, 2
0x180003db8  dec     rbx
0x180003dbb  sub     rdi, 1
0x180003dbf  jnz     short loc_180003DA0
0x180003dc1  xor     eax, eax
0x180003dc3  lea     rdx, [rsi-2]
0x180003dc7  test    rdi, rdi
0x180003dca  cmovnz  rdx, rsi
0x180003dce  cmovnz  r12d, eax
0x180003dd2  xor     ecx, ecx
0x180003dd4  mov     [rdx], cx
0x180003dd7  test    rdi, rdi
0x180003dda  jz      loc_180003FEF
0x180003de0  mov     rcx, [rsp+4A8h+var_48]
0x180003de8  xor     rcx, rsp; StackCookie
0x180003deb  call    __security_check_cookie
0x180003df0  add     rsp, 470h
0x180003df7  pop     r15
0x180003df9  pop     r14
0x180003dfb  pop     r12
0x180003dfd  pop     rdi
0x180003dfe  pop     rsi
0x180003dff  pop     rbp
0x180003e00  pop     rbx
0x180003e01  retn
0x180003e03  lea     r8, [rsp+4A8h+pcchLength]; pcchLength
0x180003e08  mov     [rsp+4A8h+pcchLength], 0
0x180003e11  mov     rdx, rdi; cchMax
0x180003e14  lea     rcx, [rsp+4A8h+psz]; psz
0x180003e19  call    StringLengthWorkerW
0x180003e1e  mov     ebp, eax
0x180003e20  test    eax, eax
0x180003e22  js      loc_180003F3F
0x180003e28  mov     rax, [rsp+4A8h+pcchLength]
0x180003e2d  lea     r8, [rsp+4A8h+psz]
0x180003e32  mov     rdx, rdi
0x180003e35  lea     r9, aChildren; "\\Children"
0x180003e3c  mov     rcx, rbx
0x180003e3f  lea     r8, [r8+rax*2]
0x180003e43  sub     rdx, rax
0x180003e46  jz      short loc_180003E6B
0x180003e48  test    rcx, rcx
0x180003e4b  jz      short loc_180003E6B
0x180003e4d  movzx   eax, word ptr [r9]
0x180003e51  test    ax, ax
0x180003e54  jz      short loc_180003E6B
0x180003e56  mov     [r8], ax
0x180003e5a  add     r9, 2
0x180003e5e  add     r8, 2
0x180003e62  dec     rcx
0x180003e65  sub     rdx, 1
0x180003e69  jnz     short loc_180003E48
0x180003e6b  xor     eax, eax
0x180003e6d  lea     rcx, [r8-2]
0x180003e71  test    rdx, rdx
0x180003e74  mov     ebp, r12d
0x180003e77  cmovnz  rcx, r8
0x180003e7b  cmovnz  ebp, eax
0x180003e7e  mov     [rcx], ax
0x180003e81  jz      loc_180003F3F
0x180003e87  lea     r8, [rsp+4A8h+pcchLength]; pcchLength
0x180003e8c  mov     [rsp+4A8h+pcchLength], rax
0x180003e91  mov     rdx, rdi; cchMax
0x180003e94  lea     rcx, [rsp+4A8h+psz]; psz
0x180003e99  call    StringLengthWorkerW
0x180003e9e  mov     ebp, eax
0x180003ea0  test    eax, eax
0x180003ea2  js      loc_180003F61
0x180003ea8  mov     rax, [rsp+4A8h+pcchLength]
0x180003ead  lea     r8, [rsp+4A8h+psz]
0x180003eb2  mov     rdx, rdi
0x180003eb5  lea     r9, asc_180026BFC; "\\"
0x180003ebc  mov     rcx, rbx
0x180003ebf  lea     r8, [r8+rax*2]
0x180003ec3  sub     rdx, rax
0x180003ec6  jz      short loc_180003EEB
0x180003ec8  test    rcx, rcx
0x180003ecb  jz      short loc_180003EEB
0x180003ecd  movzx   eax, word ptr [r9]
0x180003ed1  test    ax, ax
0x180003ed4  jz      short loc_180003EEB
0x180003ed6  mov     [r8], ax
0x180003eda  add     r9, 2
0x180003ede  add     r8, 2
0x180003ee2  dec     rcx
0x180003ee5  sub     rdx, 1
0x180003ee9  jnz     short loc_180003EC8
0x180003eeb  xor     eax, eax
0x180003eed  lea     rcx, [r8-2]
0x180003ef1  test    rdx, rdx
0x180003ef4  mov     ebp, r12d
0x180003ef7  cmovnz  rcx, r8
0x180003efb  cmovnz  ebp, eax
0x180003efe  mov     [rcx], ax
0x180003f01  jz      short loc_180003F61
0x180003f03  mov     r8, r14; unsigned __int16 *
0x180003f06  lea     rcx, [rsp+4A8h+psz]; unsigned __int16 *
0x180003f0b  mov     rdx, rdi; unsigned __int64
0x180003f0e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003f13  mov     ebp, eax
0x180003f15  test    eax, eax
0x180003f17  jns     loc_180003D9B
0x180003f1d  mov     [rsp+4A8h+var_478], r14
0x180003f22  lea     rdx, aPathLsNameLs; "Path %ls Name %ls"
0x180003f29  lea     rax, [rsp+4A8h+psz]
0x180003f2e  mov     [rsp+4A8h+var_480], rax
0x180003f33  mov     qword ptr [rsp+4A8h+var_488], rdx
0x180003f38  mov     edx, 2C3h
0x180003f3d  jmp     short loc_180003F81
0x180003f3f  mov     [rsp+4A8h+var_478], r14
0x180003f44  lea     rdx, aPathLsNameLs; "Path %ls Name %ls"
0x180003f4b  lea     rax, [rsp+4A8h+psz]
0x180003f50  mov     [rsp+4A8h+var_480], rax
0x180003f55  mov     qword ptr [rsp+4A8h+var_488], rdx
0x180003f5a  mov     edx, 2BDh
0x180003f5f  jmp     short loc_180003F81
0x180003f61  mov     [rsp+4A8h+var_478], r14
0x180003f66  lea     rdx, aPathLsNameLs; "Path %ls Name %ls"
0x180003f6d  lea     rax, [rsp+4A8h+psz]
0x180003f72  mov     [rsp+4A8h+var_480], rax; char *
0x180003f77  mov     qword ptr [rsp+4A8h+var_488], rdx; int
0x180003f7c  mov     edx, 2C0h; void *
0x180003f81  mov     rcx, [rsp+4A8h]; this
0x180003f89  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180003f90  mov     r9d, ebp; char *
0x180003f93  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180003f98  mov     eax, ebp
0x180003f9a  jmp     loc_180003DE0
0x180003f9f  mov     [rsp+4A8h+var_478], r15
0x180003fa4  lea     rax, aNameLsSidLs; "Name %ls Sid %ls"
0x180003fab  mov     [rsp+4A8h+var_480], r14
0x180003fb0  mov     edx, 2B2h
0x180003fb5  mov     qword ptr [rsp+4A8h+var_488], rax
0x180003fba  jmp     short loc_180003F81
0x180003fbc  call    cs:__imp_GetAppContainerRegistryPath
0x180003fc3  nop     dword ptr [rax+rax+00h]
0x180003fc8  mov     ebp, eax
0x180003fca  test    eax, eax
0x180003fcc  jns     loc_180003E03
0x180003fd2  mov     [rsp+4A8h+var_478], r15
0x180003fd7  lea     rax, aNameLsSidLs; "Name %ls Sid %ls"
0x180003fde  mov     [rsp+4A8h+var_480], r14
0x180003fe3  mov     edx, 2B7h
0x180003fe8  mov     qword ptr [rsp+4A8h+var_488], rax
0x180003fed  jmp     short loc_180003F81
0x180003fef  mov     rcx, [rsp+4A8h]; this
0x180003ff7  lea     rax, [rsp+4A8h+psz]
0x180003ffc  mov     [rsp+4A8h+var_480], rax; char *
0x180004001  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x180004008  lea     rax, aPathLs; "path %ls"
0x18000400f  mov     r9d, r12d; char *
0x180004012  mov     edx, 2C6h; void *
0x180004017  mov     qword ptr [rsp+4A8h+var_488], rax; int
0x18000401c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180004021  mov     eax, r12d
0x180004024  jmp     loc_180003DE0
```
