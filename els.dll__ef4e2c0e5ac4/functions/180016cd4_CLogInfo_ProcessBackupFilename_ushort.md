# CLogInfo::ProcessBackupFilename(ushort *)

- ea: `0x180016cd4`
- end: `0x180016ff6`
- name: `?ProcessBackupFilename@CLogInfo@@QEAAJPEAG@Z`
- size: `802`
- prototype: `int(CLogInfo *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18001fd74`

## callees

- `0x180001910`
- `0x180016cd4`
- `0x18001eef4`
- `0x18001ef94`
- `0x18001f960`
- `0x18001fc84`
- `0x180020ae0`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcschr` at `0x180016ece`
- `msvcrt!wcschr` at `0x180016ee6`
- `msvcrt!wcschr` at `0x180016ece`
- `msvcrt!wcschr` at `0x180016ee6`
- `KERNEL32!lstrcmpiW` at `0x180016d44`
- `KERNEL32!lstrcmpiW` at `0x180016d9b`
- `KERNEL32!lstrcmpiW` at `0x180016e1e`
- `KERNEL32!lstrcmpiW` at `0x180016e66`
- `KERNEL32!lstrcmpiW` at `0x180016d44`
- `KERNEL32!lstrcmpiW` at `0x180016d9b`
- `KERNEL32!lstrcmpiW` at `0x180016e1e`
- `KERNEL32!lstrcmpiW` at `0x180016e66`
- `netutils!NetApiBufferFree` at `0x180016fc3`
- `netutils!NetApiBufferFree` at `0x180016fc3`
- `srvcli!NetShareGetInfo` at `0x180016f0e`
- `srvcli!NetShareGetInfo` at `0x180016f0e`
- `SHLWAPI!PathCombineW` at `0x180016f7d`
- `SHLWAPI!PathCombineW` at `0x180016f7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CLogInfo::ProcessBackupFilename(CLogInfo *this, unsigned __int16 *a2)
{
  unsigned int v4; // ebx
  const WCHAR *v5; // rdi
  const WCHAR *v6; // rcx
  __int64 v7; // rdx
  const WCHAR *v8; // rdx
  const WCHAR *v9; // rcx
  __int64 v10; // rdx
  int v11; // eax
  LPCWSTR *v12; // rax
  __int64 v13; // rdx
  const WCHAR *v14; // rdx
  const WCHAR *v15; // rcx
  __int64 v16; // rdx
  wchar_t *v17; // rax
  WCHAR *v18; // rsi
  wchar_t *v19; // rax
  wchar_t *v20; // rdi
  signed int Info; // eax
  LPCWSTR *v22; // rax
  __int64 v23; // rdx
  LPBYTE bufptr; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpString2[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h]
  unsigned __int64 v28; // [rsp+50h] [rbp-B0h]
  LPCWSTR lpString1[3]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v30; // [rsp+70h] [rbp-90h]
  LPCWSTR v31[4]; // [rsp+78h] [rbp-88h] BYREF
  LPCWSTR v32[3]; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v33; // [rsp+B0h] [rbp-50h]
  WCHAR String1[264]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v35[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wchar_t Str[262]; // [rsp+2D4h] [rbp+1D4h] BYREF

  v4 = 0;
  bufptr = 0;
  v5 = (const WCHAR *)((char *)this + 32);
  if ( *((_WORD *)this + 16) )
  {
    GetComputerNameAsString((__int64)lpString1);
    v6 = (const WCHAR *)lpString1;
    if ( v30 >= 8 )
      v6 = lpString1[0];
    if ( !lstrcmpiW(v6, v5) )
      goto LABEL_40;
    GetNetbiosComputerNameAsString(v31, 0);
    GetNetbiosComputerNameAsString(lpString2, v5);
    if ( v31[2] && v27 )
    {
      v8 = (const WCHAR *)lpString2;
      if ( v28 >= 8 )
        v8 = lpString2[0];
      v9 = (const WCHAR *)v31;
      if ( v31[3] >= (LPCWSTR)8 )
        v9 = v31[0];
      if ( !lstrcmpiW(v9, v8) )
        goto LABEL_39;
    }
    v11 = RemoteFileToServerAndUNCPath(a2, String1, 0x105u, v35, 0x104u);
    v4 = v11;
    if ( v11 < 0 )
    {
LABEL_39:
      LOBYTE(v10) = 1;
      std::wstring::_Tidy(lpString2, v10, 0);
      LOBYTE(v23) = 1;
      std::wstring::_Tidy(v31, v23, 0);
LABEL_40:
      LOBYTE(v7) = 1;
      std::wstring::_Tidy(lpString1, v7, 0);
      goto LABEL_41;
    }
    if ( v11 == 1 )
    {
      v12 = lpString1;
      if ( v30 >= 8 )
        v12 = (LPCWSTR *)lpString1[0];
      ConsoleMsgBox(*(struct IConsole **)(*((_QWORD *)this + 609) + 1152LL), 0x11Au, v4 + 15, v5, v12);
      v4 = -2147467259;
      goto LABEL_39;
    }
    if ( lstrcmpiW(String1, v5) )
    {
      GetNetbiosComputerNameAsString(v32, String1);
      if ( v27 && v32[2] )
      {
        v14 = (const WCHAR *)v32;
        if ( v33 >= 8 )
          v14 = v32[0];
        v15 = (const WCHAR *)lpString2;
        if ( v28 >= 8 )
          v15 = lpString2[0];
        if ( lstrcmpiW(v15, v14) )
        {
          ConsoleMsgBox(*(struct IConsole **)(*((_QWORD *)this + 609) + 1152LL), 0x11Au, 0x10u, v5, String1);
          v4 = -2147467259;
LABEL_26:
          LOBYTE(v16) = 1;
          std::wstring::_Tidy(v32, v16, 0);
          goto LABEL_39;
        }
      }
      LOBYTE(v13) = 1;
      std::wstring::_Tidy(v32, v13, 0);
    }
    v17 = wcschr(Str, 0x5Cu);
    if ( !v17 || (v18 = v17 + 1, v19 = wcschr(v17 + 1, 0x5Cu), (v20 = v19) == 0) )
    {
      v4 = -2147024843;
      goto LABEL_39;
    }
    *v19 = 0;
    Info = NetShareGetInfo(String1, v18, 2u, &bufptr);
    if ( !Info )
    {
      PathCombineW(a2, *((LPCWSTR *)bufptr + 5), v20 + 1);
      goto LABEL_39;
    }
    if ( Info > 0 )
      v4 = (unsigned __int16)Info | 0x80070000;
    else
      v4 = Info;
    ComposeErrorMessgeFromHRESULT(v32, v4);
    v22 = v32;
    if ( v33 >= 8 )
      v22 = (LPCWSTR *)v32[0];
    ConsoleMsgBox(*(struct IConsole **)(*((_QWORD *)this + 609) + 1152LL), 0x101u, 0x10u, a2, v22);
    goto LABEL_26;
  }
LABEL_41:
  if ( bufptr )
    NetApiBufferFree(bufptr);
  return v4;
}

```

## disassembly

```asm
0x180016cd4  mov     [rsp-8+arg_10], rbx
0x180016cd9  mov     [rsp-8+arg_18], rsi
0x180016cde  push    rbp
0x180016cdf  push    rdi
0x180016ce0  push    r12
0x180016ce2  push    r14
0x180016ce4  push    r15
0x180016ce6  lea     rbp, [rsp-3F0h]
0x180016cee  sub     rsp, 4F0h
0x180016cf5  mov     rax, cs:__security_cookie
0x180016cfc  xor     rax, rsp
0x180016cff  mov     [rbp+410h+var_30], rax
0x180016d06  mov     r15, rdx
0x180016d09  mov     r14, rcx
0x180016d0c  xor     r12d, r12d
0x180016d0f  mov     ebx, r12d
0x180016d12  mov     [rsp+510h+bufptr], r12
0x180016d17  lea     rdi, [rcx+20h]
0x180016d1b  cmp     [rdi], r12w
0x180016d1f  jz      loc_180016FB9
0x180016d25  lea     rcx, [rsp+510h+lpString1]
0x180016d2a  call    ?GetComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; GetComputerNameAsString(void)
0x180016d2f  nop
0x180016d30  lea     rcx, [rsp+510h+lpString1]
0x180016d35  cmp     [rsp+510h+var_4A0], 8
0x180016d3b  cmovnb  rcx, [rsp+510h+lpString1]; lpString1
0x180016d41  mov     rdx, rdi; lpString2
0x180016d44  call    cs:__imp_lstrcmpiW
0x180016d4a  test    eax, eax
0x180016d4c  jz      loc_180016FAA
0x180016d52  xor     edx, edx
0x180016d54  lea     rcx, [rsp+510h+var_498]
0x180016d59  call    ?GetNetbiosComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetNetbiosComputerNameAsString(ushort const *)
0x180016d5e  nop
0x180016d5f  mov     rdx, rdi
0x180016d62  lea     rcx, [rsp+510h+lpString2]
0x180016d67  call    ?GetNetbiosComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetNetbiosComputerNameAsString(ushort const *)
0x180016d6c  nop
0x180016d6d  cmp     [rbp+410h+var_488], r12
0x180016d71  jz      short loc_180016DA9
0x180016d73  cmp     [rsp+510h+var_4C8], r12
0x180016d78  jz      short loc_180016DA9
0x180016d7a  lea     rdx, [rsp+510h+lpString2]
0x180016d7f  cmp     [rsp+510h+var_4C0], 8
0x180016d85  cmovnb  rdx, [rsp+510h+lpString2]; lpString2
0x180016d8b  lea     rcx, [rsp+510h+var_498]
0x180016d90  cmp     [rbp+410h+var_480], 8
0x180016d95  cmovnb  rcx, [rsp+510h+var_498]; lpString1
0x180016d9b  call    cs:__imp_lstrcmpiW
0x180016da1  test    eax, eax
0x180016da3  jz      loc_180016F8A
0x180016da9  mov     r8d, 105h; unsigned __int16
0x180016daf  mov     [rsp+510h+var_4F0], 104h; unsigned __int16
0x180016db6  lea     r9, [rbp+410h+var_240]; unsigned __int16 *
0x180016dbd  lea     rdx, [rbp+410h+String1]; unsigned __int16 *
0x180016dc1  mov     rcx, r15; Source
0x180016dc4  call    ?RemoteFileToServerAndUNCPath@@YAJPEBGPEAGG1G@Z; RemoteFileToServerAndUNCPath(ushort const *,ushort *,ushort,ushort *,ushort)
0x180016dc9  mov     ebx, eax
0x180016dcb  test    eax, eax
0x180016dcd  js      loc_180016F8A
0x180016dd3  cmp     eax, 1
0x180016dd6  jnz     short loc_180016E17
0x180016dd8  lea     rax, [rsp+510h+lpString1]
0x180016ddd  cmp     [rsp+510h+var_4A0], 8
0x180016de3  cmovnb  rax, [rsp+510h+lpString1]
0x180016de9  mov     rcx, [r14+1308h]
0x180016df0  mov     qword ptr [rsp+510h+var_4F0], rax
0x180016df5  mov     r9, rdi
0x180016df8  mov     edx, 11Ah; unsigned int
0x180016dfd  lea     r8d, [rbx+0Fh]; unsigned int
0x180016e01  mov     rcx, [rcx+480h]; struct IConsole *
0x180016e08  call    ?ConsoleMsgBox@@YAHPEAUIConsole@@KKZZ; ConsoleMsgBox(IConsole *,ulong,ulong,...)
0x180016e0d  mov     ebx, 80004005h
0x180016e12  jmp     loc_180016F8A
0x180016e17  mov     rdx, rdi; lpString2
0x180016e1a  lea     rcx, [rbp+410h+String1]; lpString1
0x180016e1e  call    cs:__imp_lstrcmpiW
0x180016e24  test    eax, eax
0x180016e26  jz      loc_180016EC0
0x180016e2c  lea     rdx, [rbp+410h+String1]
0x180016e30  lea     rcx, [rbp+410h+var_478]
0x180016e34  call    ?GetNetbiosComputerNameAsString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; GetNetbiosComputerNameAsString(ushort const *)
0x180016e39  nop
0x180016e3a  cmp     [rsp+510h+var_4C8], r12
0x180016e3f  jz      short loc_180016EB2
0x180016e41  cmp     [rbp+410h+var_468], r12
0x180016e45  jz      short loc_180016EB2
0x180016e47  lea     rdx, [rbp+410h+var_478]
0x180016e4b  cmp     [rbp+410h+var_460], 8
0x180016e50  cmovnb  rdx, [rbp+410h+var_478]; lpString2
0x180016e55  lea     rcx, [rsp+510h+lpString2]
0x180016e5a  cmp     [rsp+510h+var_4C0], 8
0x180016e60  cmovnb  rcx, [rsp+510h+lpString2]; lpString1
0x180016e66  call    cs:__imp_lstrcmpiW
0x180016e6c  test    eax, eax
0x180016e6e  jz      short loc_180016EB2
0x180016e70  mov     rcx, [r14+1308h]
0x180016e77  lea     rax, [rbp+410h+String1]
0x180016e7b  mov     qword ptr [rsp+510h+var_4F0], rax
0x180016e80  mov     r9, rdi
0x180016e83  mov     edx, 11Ah; unsigned int
0x180016e88  mov     r8d, 10h; unsigned int
0x180016e8e  mov     rcx, [rcx+480h]; struct IConsole *
0x180016e95  call    ?ConsoleMsgBox@@YAHPEAUIConsole@@KKZZ; ConsoleMsgBox(IConsole *,ulong,ulong,...)
0x180016e9a  mov     ebx, 80004005h
0x180016e9f  xor     r8d, r8d
0x180016ea2  mov     dl, 1
0x180016ea4  lea     rcx, [rbp+410h+var_478]
0x180016ea8  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016ead  jmp     loc_180016F8A
0x180016eb2  xor     r8d, r8d
0x180016eb5  mov     dl, 1
0x180016eb7  lea     rcx, [rbp+410h+var_478]
0x180016ebb  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016ec0  mov     edi, 5Ch ; '\'
0x180016ec5  mov     edx, edi; Ch
0x180016ec7  lea     rcx, [rbp+410h+Str]; Str
0x180016ece  call    cs:__imp_wcschr
0x180016ed4  test    rax, rax
0x180016ed7  jz      loc_180016F85
0x180016edd  lea     rsi, [rax+2]
0x180016ee1  mov     edx, edi; Ch
0x180016ee3  mov     rcx, rsi; Str
0x180016ee6  call    cs:__imp_wcschr
0x180016eec  mov     rdi, rax
0x180016eef  test    rax, rax
0x180016ef2  jz      loc_180016F85
0x180016ef8  mov     [rax], r12w
0x180016efc  lea     r9, [rsp+510h+bufptr]; bufptr
0x180016f01  mov     r8d, 2; level
0x180016f07  mov     rdx, rsi; netname
0x180016f0a  lea     rcx, [rbp+410h+String1]; servername
0x180016f0e  call    cs:__imp_NetShareGetInfo
0x180016f14  test    eax, eax
0x180016f16  jz      short loc_180016F6D
0x180016f18  jg      short loc_180016F1E
0x180016f1a  mov     ebx, eax
0x180016f1c  jmp     short loc_180016F27
0x180016f1e  movzx   ebx, ax
0x180016f21  or      ebx, 80070000h
0x180016f27  mov     edx, ebx
0x180016f29  lea     rcx, [rbp+410h+var_478]
0x180016f2d  call    ?ComposeErrorMessgeFromHRESULT@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; ComposeErrorMessgeFromHRESULT(long)
0x180016f32  nop
0x180016f33  lea     rax, [rbp+410h+var_478]
0x180016f37  cmp     [rbp+410h+var_460], 8
0x180016f3c  cmovnb  rax, [rbp+410h+var_478]
0x180016f41  mov     rcx, [r14+1308h]
0x180016f48  mov     qword ptr [rsp+510h+var_4F0], rax
0x180016f4d  mov     r9, r15
0x180016f50  mov     edx, 101h; unsigned int
0x180016f55  mov     r8d, 10h; unsigned int
0x180016f5b  mov     rcx, [rcx+480h]; struct IConsole *
0x180016f62  call    ?ConsoleMsgBox@@YAHPEAUIConsole@@KKZZ; ConsoleMsgBox(IConsole *,ulong,ulong,...)
0x180016f67  nop
0x180016f68  jmp     loc_180016E9F
0x180016f6d  lea     r8, [rdi+2]; pszFile
0x180016f71  mov     rdx, [rsp+510h+bufptr]
0x180016f76  mov     rdx, [rdx+28h]; pszDir
0x180016f7a  mov     rcx, r15; pszDest
0x180016f7d  call    cs:__imp_PathCombineW
0x180016f83  jmp     short loc_180016F8A
0x180016f85  mov     ebx, 80070035h
0x180016f8a  xor     r8d, r8d
0x180016f8d  mov     dl, 1
0x180016f8f  lea     rcx, [rsp+510h+lpString2]
0x180016f94  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016f99  nop
0x180016f9a  xor     r8d, r8d
0x180016f9d  mov     dl, 1
0x180016f9f  lea     rcx, [rsp+510h+var_498]
0x180016fa4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016fa9  nop
0x180016faa  xor     r8d, r8d
0x180016fad  mov     dl, 1
0x180016faf  lea     rcx, [rsp+510h+lpString1]
0x180016fb4  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180016fb9  mov     rcx, [rsp+510h+bufptr]; Buffer
0x180016fbe  test    rcx, rcx
0x180016fc1  jz      short loc_180016FC9
0x180016fc3  call    cs:__imp_NetApiBufferFree
0x180016fc9  mov     eax, ebx
0x180016fcb  mov     rcx, [rbp+410h+var_30]
0x180016fd2  xor     rcx, rsp; StackCookie
0x180016fd5  call    __security_check_cookie
0x180016fda  lea     r11, [rsp+510h+var_20]
0x180016fe2  mov     rbx, [r11+40h]
0x180016fe6  mov     rsi, [r11+48h]
0x180016fea  mov     rsp, r11
0x180016fed  pop     r15
0x180016fef  pop     r14
0x180016ff1  pop     r12
0x180016ff3  pop     rdi
0x180016ff4  pop     rbp
0x180016ff5  retn
```
