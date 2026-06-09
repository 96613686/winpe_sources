# FindAppRegKey(char const *,char *,unsigned __int64 *,bool *,char const *,uint)

- ea: `0x180034c9c`
- end: `0x18003502f`
- name: `?FindAppRegKey@@YA_NPEBDPEADPEA_KPEA_N0I@Z`
- size: `915`
- prototype: `bool __fastcall(const char *, char *, unsigned __int64 *, bool *, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800647a0`

## callees

- `0x180006ee4`
- `0x180034c9c`
- `0x180035040`
- `0x1800350ac`
- `0x180075fa0`
- `0x180076e84`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180034eba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180034efa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180034eba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180034efa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180034df3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x180034df3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034da5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034f07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034fc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034da5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034f07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034fc1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180034d3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180034e74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180034d3f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180034e74`

## pseudocode

```c
char __fastcall FindAppRegKey(const char *a1, char *a2, unsigned __int64 *a3, bool *a4, char *a5, unsigned int a6)
{
  int v6; // edi
  HKEY v7; // rsi
  HKEY v8; // r12
  __int64 v9; // r14
  char v10; // r15
  _BYTE *v11; // r12
  char *v12; // r13
  DWORD v14; // ebx
  HKEY v15; // r13
  LSTATUS v16; // ebx
  int v17; // eax
  unsigned __int64 v18; // rdx
  unsigned __int64 v19; // rax
  DWORD v20; // [rsp+40h] [rbp-C0h]
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v23; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v26; // [rsp+60h] [rbp-A0h]
  HKEY v27; // [rsp+68h] [rbp-98h] BYREF
  DWORD v28; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 *v30; // [rsp+80h] [rbp-80h]
  bool *v31; // [rsp+88h] [rbp-78h]
  char *v32; // [rsp+90h] [rbp-70h]
  HKEY hKey[2]; // [rsp+98h] [rbp-68h]
  CHAR Name[272]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR SubKey[272]; // [rsp+1C0h] [rbp+C0h] BYREF
  BYTE v36[272]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v37[272]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v23 = (HKEY)a5;
  v31 = a4;
  v30 = a3;
  v32 = a2;
  if ( !a3 )
    return 0;
  v6 = 0;
  v7 = v23;
  v8 = 0;
  LODWORD(v26) = 261;
  phkResult = 0;
  v9 = 0;
  *(__m128i *)hKey = _mm_load_si128((const __m128i *)&_xmm_ffffffff80000002ffffffff80000001);
  v10 = 1;
  while ( 1 )
  {
    v23 = hKey[v9];
    if ( !RegOpenKeyExA(v23, "Software\\Microsoft\\Direct3D", 0, 0x20019u, &phkResult) )
      break;
LABEL_4:
    v9 = (unsigned int)(v9 + 1);
    if ( (unsigned int)v9 >= 2 )
      goto LABEL_5;
  }
  v14 = 0;
  v15 = v23;
  while ( 1 )
  {
    cchName = 261;
    if ( RegEnumKeyExA(phkResult, v14, Name, &cchName, 0, 0, 0, 0) )
      break;
    v20 = ++v14;
    if ( !(unsigned int)o__stricmp_0(Name, "MostRecentApplication") )
      goto LABEL_23;
    StringCchPrintfA(SubKey, 0x105u, "%s\\%s", "Software\\Microsoft\\Direct3D", Name);
    v27 = 0;
    v28 = cchName + 29;
    if ( RegOpenKeyExA(v15, SubKey, 0, 0x20019u, &v27) )
      goto LABEL_23;
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( !RegQueryValueExA(v27, "Size", 0, &Type, Data, &cbData)
      && Type == 4
      && *(_DWORD *)Data
      && *(_DWORD *)Data != a6 )
    {
      RegCloseKey(v27);
      goto LABEL_23;
    }
    cbData = 261;
    v16 = RegQueryValueExA(v27, "Name", 0, &Type, v36, &cbData);
    RegCloseKey(v27);
    if ( v16 || Type != 1 )
      goto LABEL_22;
    v23 = 0;
    v17 = EvaluatePathCandidate(v36, v7, &v23);
    if ( v17 == 1 )
      goto LABEL_20;
    if ( v17 == 2 )
    {
      if ( v6 != 2 )
        goto LABEL_20;
LABEL_22:
      v14 = v20;
LABEL_23:
      if ( v6 == 1 )
        break;
    }
    else
    {
      if ( v17 != 3 || v6 == 2 )
        goto LABEL_22;
      if ( v6 != 3 || (v14 = v20, v23 > v8) )
      {
LABEL_20:
        v8 = v23;
        v6 = v17;
        StringCchCopyA(v37, 0x105u, SubKey);
        LODWORD(v26) = v28;
        if ( (_DWORD)v9 )
          v10 = 0;
        goto LABEL_22;
      }
    }
  }
  RegCloseKey(phkResult);
  if ( v6 != 1 )
    goto LABEL_4;
LABEL_5:
  v11 = v31;
  v12 = v32;
  if ( !v6 )
  {
    *v30 = 0;
    return 0;
  }
  v18 = (unsigned int)v26;
  v19 = *v30;
  *v30 = (unsigned int)v26;
  if ( v19 < v18 )
    return 0;
  if ( v12 )
    StringCchCopyA(v12, v18, v37);
  if ( v11 )
    *v11 = v10;
  return 1;
}

```

## disassembly

```asm
0x180034c9c  mov     [rsp-8+arg_0], rbx
0x180034ca1  push    rbp
0x180034ca2  push    rsi
0x180034ca3  push    rdi
0x180034ca4  push    r12
0x180034ca6  push    r13
0x180034ca8  push    r14
0x180034caa  push    r15
0x180034cac  lea     rbp, [rsp-400h]
0x180034cb4  sub     rsp, 500h
0x180034cbb  mov     rax, cs:__security_cookie
0x180034cc2  xor     rax, rsp
0x180034cc5  mov     [rbp+430h+var_40], rax
0x180034ccc  mov     rax, [rbp+430h+arg_20]
0x180034cd3  mov     [rsp+530h+var_4E0], rax
0x180034cd8  mov     [rbp+430h+var_4A8], r9
0x180034cdc  mov     [rbp+430h+var_4B0], r8
0x180034ce0  mov     [rbp+430h+var_4A0], rdx
0x180034ce4  test    r8, r8
0x180034ce7  jz      loc_180034D6D
0x180034ced  movdqa  xmm0, cs:__xmm@ffffffff80000002ffffffff80000001
0x180034cf5  xor     edi, edi
0x180034cf7  mov     rsi, [rsp+530h+var_4E0]
0x180034cfc  mov     eax, 105h
0x180034d01  xor     r12d, r12d
0x180034d04  mov     dword ptr [rsp+530h+var_4D0], eax
0x180034d08  mov     [rsp+530h+var_4B8], rdi
0x180034d0d  xor     r14d, r14d
0x180034d10  movdqu  xmmword ptr [rbp+430h+hKey], xmm0
0x180034d15  mov     r15b, 1
0x180034d18  mov     rax, [rbp+r14*8+430h+hKey]
0x180034d1d  lea     rcx, [rsp+530h+var_4B8]
0x180034d22  mov     [rsp+530h+phkResult], rcx; phkResult
0x180034d27  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Direct3D"
0x180034d2e  mov     rcx, rax; hKey
0x180034d31  mov     [rsp+530h+var_4E0], rax
0x180034d36  mov     r9d, 20019h; samDesired
0x180034d3c  xor     r8d, r8d; ulOptions
0x180034d3f  call    cs:__imp_RegOpenKeyExA
0x180034d45  test    eax, eax
0x180034d47  jz      short loc_180034D99
0x180034d49  inc     r14d
0x180034d4c  cmp     r14d, 2
0x180034d50  jb      short loc_180034D18
0x180034d52  mov     rsi, [rbp+430h+var_4B0]
0x180034d56  mov     r12, [rbp+430h+var_4A8]
0x180034d5a  mov     r13, [rbp+430h+var_4A0]
0x180034d5e  test    edi, edi
0x180034d60  jnz     loc_180034FF8
0x180034d66  mov     qword ptr [rsi], 0
0x180034d6d  xor     al, al
0x180034d6f  mov     rcx, [rbp+430h+var_40]
0x180034d76  xor     rcx, rsp; StackCookie
0x180034d79  call    __security_check_cookie
0x180034d7e  mov     rbx, [rsp+530h+arg_0]
0x180034d86  add     rsp, 500h
0x180034d8d  pop     r15
0x180034d8f  pop     r14
0x180034d91  pop     r13
0x180034d93  pop     r12
0x180034d95  pop     rdi
0x180034d96  pop     rsi
0x180034d97  pop     rbp
0x180034d98  retn
0x180034d99  xor     ebx, ebx
0x180034d9b  cmp     edi, 1
0x180034d9e  jnz     short loc_180034DB2
0x180034da0  mov     rcx, [rsp+530h+var_4B8]; hKey
0x180034da5  call    cs:__imp_RegCloseKey
0x180034dab  cmp     edi, 1
0x180034dae  jnz     short loc_180034D49
0x180034db0  jmp     short loc_180034D52
0x180034db2  mov     r13, [rsp+530h+var_4E0]
0x180034db7  mov     rcx, [rsp+530h+var_4B8]; hKey
0x180034dbc  lea     r9, [rsp+530h+cchName]; lpcchName
0x180034dc1  mov     [rsp+530h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180034dca  lea     r8, [rbp+430h+Name]; lpName
0x180034dce  mov     [rsp+530h+lpcchClass], 0; lpcchClass
0x180034dd7  mov     edx, ebx; dwIndex
0x180034dd9  mov     [rsp+530h+lpClass], 0; lpClass
0x180034de2  mov     [rsp+530h+phkResult], 0; lpReserved
0x180034deb  mov     [rsp+530h+cchName], 105h
0x180034df3  call    cs:__imp_RegEnumKeyExA
0x180034df9  test    eax, eax
0x180034dfb  jnz     short loc_180034DA0
0x180034dfd  inc     ebx
0x180034dff  lea     rdx, aMostrecentappl; "MostRecentApplication"
0x180034e06  lea     rcx, [rbp+430h+Name]
0x180034e0a  mov     [rsp+530h+var_4F0], ebx
0x180034e0e  call    _o__stricmp_0
0x180034e13  test    eax, eax
0x180034e15  jz      loc_180034F8B
0x180034e1b  lea     rax, [rbp+430h+Name]
0x180034e1f  mov     edx, 105h; unsigned __int64
0x180034e24  lea     r9, aSoftwareMicros_3; "Software\\Microsoft\\Direct3D"
0x180034e2b  mov     [rsp+530h+phkResult], rax
0x180034e30  lea     r8, aSS; "%s\\%s"
0x180034e37  lea     rcx, [rbp+430h+SubKey]; char *
0x180034e3e  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180034e43  mov     eax, [rsp+530h+cchName]
0x180034e47  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x180034e4e  add     eax, 1Dh
0x180034e51  mov     [rsp+530h+var_4C8], 0
0x180034e5a  mov     [rsp+530h+var_4C0], eax
0x180034e5e  mov     r9d, 20019h; samDesired
0x180034e64  lea     rax, [rsp+530h+var_4C8]
0x180034e69  xor     r8d, r8d; ulOptions
0x180034e6c  mov     rcx, r13; hKey
0x180034e6f  mov     [rsp+530h+phkResult], rax; phkResult
0x180034e74  call    cs:__imp_RegOpenKeyExA
0x180034e7a  test    eax, eax
0x180034e7c  jnz     loc_180034F8B
0x180034e82  mov     rcx, [rsp+530h+var_4C8]; hKey
0x180034e87  lea     r9, [rsp+530h+Type]; lpType
0x180034e8c  mov     [rsp+530h+Type], eax
0x180034e90  lea     rdx, ValueName; "Size"
0x180034e97  mov     dword ptr [rsp+530h+Data], eax
0x180034e9b  xor     r8d, r8d; lpReserved
0x180034e9e  lea     rax, [rsp+530h+cbData]
0x180034ea3  mov     [rsp+530h+cbData], 4
0x180034eab  mov     [rsp+530h+lpClass], rax; lpcbData
0x180034eb0  lea     rax, [rsp+530h+Data]
0x180034eb5  mov     [rsp+530h+phkResult], rax; lpData
0x180034eba  call    cs:__imp_RegQueryValueExA
0x180034ec0  test    eax, eax
0x180034ec2  jz      loc_180034F99
0x180034ec8  mov     rcx, [rsp+530h+var_4C8]; hKey
0x180034ecd  lea     rax, [rsp+530h+cbData]
0x180034ed2  mov     [rsp+530h+lpClass], rax; lpcbData
0x180034ed7  lea     r9, [rsp+530h+Type]; lpType
0x180034edc  lea     rax, [rbp+430h+var_260]
0x180034ee3  mov     [rsp+530h+cbData], 105h
0x180034eeb  xor     r8d, r8d; lpReserved
0x180034eee  mov     [rsp+530h+phkResult], rax; lpData
0x180034ef3  lea     rdx, aName_0; "Name"
0x180034efa  call    cs:__imp_RegQueryValueExA
0x180034f00  mov     rcx, [rsp+530h+var_4C8]; hKey
0x180034f05  mov     ebx, eax
0x180034f07  call    cs:__imp_RegCloseKey
0x180034f0d  test    ebx, ebx
0x180034f0f  jnz     short loc_180034F87
0x180034f11  cmp     [rsp+530h+Type], 1
0x180034f16  jnz     short loc_180034F87
0x180034f18  lea     r8, [rsp+530h+var_4E0]
0x180034f1d  mov     [rsp+530h+var_4E0], 0
0x180034f26  mov     rdx, rsi
0x180034f29  lea     rcx, [rbp+430h+var_260]
0x180034f30  call    ?EvaluatePathCandidate@@YA?AW4PATH_CANDIDATE_EVALUATION@@PEBD0PEA_K@Z; EvaluatePathCandidate(char const *,char const *,unsigned __int64 *)
0x180034f35  mov     ecx, eax
0x180034f37  sub     ecx, 1
0x180034f3a  jz      short loc_180034F53
0x180034f3c  sub     ecx, 1
0x180034f3f  jnz     loc_180034FC9
0x180034f45  cmp     edi, 1
0x180034f48  jz      loc_180034DA0
0x180034f4e  cmp     edi, 2
0x180034f51  jz      short loc_180034F87
0x180034f53  mov     r12, [rsp+530h+var_4E0]
0x180034f58  lea     r8, [rbp+430h+SubKey]; char *
0x180034f5f  mov     edx, 105h; unsigned __int64
0x180034f64  lea     rcx, [rbp+430h+var_150]; char *
0x180034f6b  mov     edi, eax
0x180034f6d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180034f72  mov     eax, [rsp+530h+var_4C0]
0x180034f76  mov     dword ptr [rsp+530h+var_4D0], eax
0x180034f7a  xor     eax, eax
0x180034f7c  test    r14d, r14d
0x180034f7f  movzx   r15d, r15b
0x180034f83  cmovnz  r15d, eax
0x180034f87  mov     ebx, [rsp+530h+var_4F0]
0x180034f8b  cmp     edi, 1
0x180034f8e  jnz     loc_180034DB7
0x180034f94  jmp     loc_180034DA0
0x180034f99  cmp     [rsp+530h+Type], 4
0x180034f9e  jnz     loc_180034EC8
0x180034fa4  mov     eax, dword ptr [rsp+530h+Data]
0x180034fa8  test    eax, eax
0x180034faa  jz      loc_180034EC8
0x180034fb0  cmp     eax, [rbp+430h+arg_28]
0x180034fb6  jz      loc_180034EC8
0x180034fbc  mov     rcx, [rsp+530h+var_4C8]; hKey
0x180034fc1  call    cs:__imp_RegCloseKey
0x180034fc7  jmp     short loc_180034F8B
0x180034fc9  cmp     ecx, 1
0x180034fcc  jnz     short loc_180034F87
0x180034fce  cmp     edi, ecx
0x180034fd0  jz      loc_180034DA0
0x180034fd6  cmp     edi, 2
0x180034fd9  jz      short loc_180034F87
0x180034fdb  cmp     edi, 3
0x180034fde  jnz     loc_180034F53
0x180034fe4  mov     ebx, [rsp+530h+var_4F0]
0x180034fe8  cmp     [rsp+530h+var_4E0], r12
0x180034fed  jbe     loc_180034DB7
0x180034ff3  jmp     loc_180034F53
0x180034ff8  mov     edx, dword ptr [rsp+530h+var_4D0]; unsigned __int64
0x180034ffc  mov     rax, [rsi]
0x180034fff  mov     [rsi], rdx
0x180035002  cmp     rax, rdx
0x180035005  jb      loc_180034D6D
0x18003500b  test    r13, r13
0x18003500e  jz      short loc_18003501F
0x180035010  lea     r8, [rbp+430h+var_150]; char *
0x180035017  mov     rcx, r13; char *
0x18003501a  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18003501f  test    r12, r12
0x180035022  jz      short loc_180035028
0x180035024  mov     [r12], r15b
0x180035028  mov     al, 1
0x18003502a  jmp     loc_180034D6F
```
