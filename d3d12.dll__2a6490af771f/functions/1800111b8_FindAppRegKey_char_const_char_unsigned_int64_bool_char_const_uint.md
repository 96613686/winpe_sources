# FindAppRegKey(char const *,char *,unsigned __int64 *,bool *,char const *,uint)

- ea: `0x1800111b8`
- end: `0x180011535`
- name: `?FindAppRegKey@@YA_NPEBDPEADPEA_KPEA_N0I@Z`
- size: `893`
- prototype: `bool __fastcall(const char *, char *, unsigned __int64 *, bool *, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011648`

## callees

- `0x18000b410`
- `0x18000de10`
- `0x180011070`
- `0x1800111b8`
- `0x180011748`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800112d4`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x1800112d4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011382`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800113e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180011382`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800113e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113a8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800113f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800114aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001125b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001133c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001125b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18001133c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800112b5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800112b5`

## pseudocode

```c
char __fastcall FindAppRegKey(const char *a1, char *a2, unsigned __int64 *a3, bool *a4, char *a5, unsigned int a6)
{
  int v6; // edi
  HKEY v7; // rsi
  HKEY v8; // r12
  __int64 v9; // r14
  char v10; // r15
  DWORD v11; // ebx
  HKEY v12; // r13
  LSTATUS v13; // ebx
  int v14; // eax
  _BYTE *v15; // r12
  char *v16; // r13
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
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
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
  do
  {
    v23 = hKey[v9];
    if ( RegOpenKeyExA(v23, "Software\\Microsoft\\Direct3D\\Direct3D12", 0, 0x20019u, &phkResult) )
      goto LABEL_28;
    v11 = 0;
    v12 = v23;
    while ( 1 )
    {
      cchName = 261;
      if ( RegEnumKeyExA(phkResult, v11, Name, &cchName, 0, 0, 0, 0) )
        break;
      v20 = ++v11;
      if ( !(unsigned int)_o__stricmp(Name, "MostRecentApplication") )
        goto LABEL_26;
      StringCchPrintfA(SubKey, 0x105u, "%s\\%s", "Software\\Microsoft\\Direct3D\\Direct3D12", Name);
      v27 = 0;
      v29 = cchName + 40;
      if ( RegOpenKeyExA(v12, SubKey, 0, 0x20019u, &v27) )
        goto LABEL_26;
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( RegQueryValueExA(v27, "Size", 0, &Type, Data, &cbData)
        || Type != 4
        || !*(_DWORD *)Data
        || *(_DWORD *)Data == a6 )
      {
        cbData = 261;
        v13 = RegQueryValueExA(v27, "Name", 0, &Type, v36, &cbData);
        RegCloseKey(v27);
        if ( v13 || Type != 1 )
          goto LABEL_25;
        v23 = 0;
        v14 = EvaluatePathCandidate(v36, v7, &v23);
        if ( v14 == 1 )
          goto LABEL_23;
        if ( v14 == 2 )
        {
          if ( v6 != 2 )
          {
LABEL_23:
            v8 = v23;
            v6 = v14;
            StringCchCopyA(v37, 0x105u, SubKey);
            LODWORD(v26) = v29;
            if ( (_DWORD)v9 )
              v10 = 0;
          }
LABEL_25:
          v11 = v20;
          goto LABEL_26;
        }
        if ( v14 != 3 || v6 == 2 )
          goto LABEL_25;
        if ( v6 != 3 )
          goto LABEL_23;
        v11 = v20;
        if ( v23 > v8 )
          goto LABEL_23;
      }
      else
      {
        RegCloseKey(v27);
LABEL_26:
        if ( v6 == 1 )
          break;
      }
    }
    RegCloseKey(phkResult);
    if ( v6 == 1 )
      break;
LABEL_28:
    v9 = (unsigned int)(v9 + 1);
  }
  while ( (unsigned int)v9 < 2 );
  v15 = v31;
  v16 = v32;
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
  if ( v16 )
    StringCchCopyA(v16, v18, v37);
  if ( v15 )
    *v15 = v10;
  return 1;
}

```

## disassembly

```asm
0x1800111b8  mov     [rsp-8+arg_0], rbx
0x1800111bd  push    rbp
0x1800111be  push    rsi
0x1800111bf  push    rdi
0x1800111c0  push    r12
0x1800111c2  push    r13
0x1800111c4  push    r14
0x1800111c6  push    r15
0x1800111c8  lea     rbp, [rsp-400h]
0x1800111d0  sub     rsp, 500h
0x1800111d7  mov     rax, cs:__security_cookie
0x1800111de  xor     rax, rsp
0x1800111e1  mov     [rbp+430h+var_40], rax
0x1800111e8  mov     rax, [rbp+430h+arg_20]
0x1800111ef  mov     [rsp+530h+var_4E0], rax
0x1800111f4  mov     [rbp+430h+var_4A8], r9
0x1800111f8  mov     [rbp+430h+var_4B0], r8
0x1800111fc  mov     [rbp+430h+var_4A0], rdx
0x180011200  test    r8, r8
0x180011203  jz      loc_1800114D9
0x180011209  movdqa  xmm0, cs:__xmm@ffffffff80000002ffffffff80000001
0x180011211  xor     edi, edi
0x180011213  mov     rsi, [rsp+530h+var_4E0]
0x180011218  mov     eax, 105h
0x18001121d  xor     r12d, r12d
0x180011220  mov     dword ptr [rsp+530h+var_4D0], eax
0x180011224  mov     [rsp+530h+var_4C0], rdi
0x180011229  xor     r14d, r14d
0x18001122c  movdqu  xmmword ptr [rbp+430h+hKey], xmm0
0x180011231  mov     r15b, 1
0x180011234  mov     rax, [rbp+r14*8+430h+hKey]
0x180011239  lea     rcx, [rsp+530h+var_4C0]
0x18001123e  mov     [rsp+530h+phkResult], rcx; phkResult
0x180011243  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Direct3D\\Direct3D"...
0x18001124a  mov     rcx, rax; hKey
0x18001124d  mov     [rsp+530h+var_4E0], rax
0x180011252  mov     r9d, 20019h; samDesired
0x180011258  xor     r8d, r8d; ulOptions
0x18001125b  call    cs:__imp_RegOpenKeyExA
0x180011261  test    eax, eax
0x180011263  jnz     loc_1800114B5
0x180011269  xor     ebx, ebx
0x18001126b  cmp     edi, 1
0x18001126e  jz      loc_1800114A5
0x180011274  mov     r13, [rsp+530h+var_4E0]
0x180011279  mov     rcx, [rsp+530h+var_4C0]; hKey
0x18001127e  lea     r9, [rsp+530h+cchName]; lpcchName
0x180011283  mov     [rsp+530h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001128c  lea     r8, [rbp+430h+Name]; lpName
0x180011290  mov     [rsp+530h+lpcchClass], 0; lpcchClass
0x180011299  mov     edx, ebx; dwIndex
0x18001129b  mov     [rsp+530h+lpClass], 0; lpClass
0x1800112a4  mov     [rsp+530h+phkResult], 0; lpReserved
0x1800112ad  mov     [rsp+530h+cchName], 105h
0x1800112b5  call    cs:__imp_RegEnumKeyExA
0x1800112bb  test    eax, eax
0x1800112bd  jnz     loc_1800114A5
0x1800112c3  inc     ebx
0x1800112c5  lea     rdx, aMostrecentappl; "MostRecentApplication"
0x1800112cc  lea     rcx, [rbp+430h+Name]
0x1800112d0  mov     [rsp+530h+var_4F0], ebx
0x1800112d4  call    cs:__imp__o__stricmp
0x1800112da  test    eax, eax
0x1800112dc  jz      loc_18001149C
0x1800112e2  lea     rax, [rbp+430h+Name]
0x1800112e6  mov     edx, 105h; unsigned __int64
0x1800112eb  lea     r9, aSoftwareMicros; "Software\\Microsoft\\Direct3D\\Direct3D"...
0x1800112f2  mov     [rsp+530h+phkResult], rax
0x1800112f7  lea     r8, aSS; "%s\\%s"
0x1800112fe  lea     rcx, [rbp+430h+SubKey]; char *
0x180011305  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001130a  mov     eax, [rsp+530h+cchName]
0x18001130e  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x180011315  add     eax, 28h ; '('
0x180011318  mov     [rsp+530h+var_4C8], 0
0x180011321  mov     [rsp+530h+var_4B8], rax
0x180011326  mov     r9d, 20019h; samDesired
0x18001132c  lea     rax, [rsp+530h+var_4C8]
0x180011331  xor     r8d, r8d; ulOptions
0x180011334  mov     rcx, r13; hKey
0x180011337  mov     [rsp+530h+phkResult], rax; phkResult
0x18001133c  call    cs:__imp_RegOpenKeyExA
0x180011342  test    eax, eax
0x180011344  jnz     loc_18001149C
0x18001134a  mov     rcx, [rsp+530h+var_4C8]; hKey
0x18001134f  lea     r9, [rsp+530h+Type]; lpType
0x180011354  mov     [rsp+530h+Type], eax
0x180011358  lea     rdx, aSize; "Size"
0x18001135f  mov     dword ptr [rsp+530h+Data], eax
0x180011363  xor     r8d, r8d; lpReserved
0x180011366  lea     rax, [rsp+530h+cbData]
0x18001136b  mov     [rsp+530h+cbData], 4
0x180011373  mov     [rsp+530h+lpClass], rax; lpcbData
0x180011378  lea     rax, [rsp+530h+Data]
0x18001137d  mov     [rsp+530h+phkResult], rax; lpData
0x180011382  call    cs:__imp_RegQueryValueExA
0x180011388  test    eax, eax
0x18001138a  jnz     short loc_1800113B3
0x18001138c  cmp     [rsp+530h+Type], 4
0x180011391  jnz     short loc_1800113B3
0x180011393  mov     eax, dword ptr [rsp+530h+Data]
0x180011397  test    eax, eax
0x180011399  jz      short loc_1800113B3
0x18001139b  cmp     eax, [rbp+430h+arg_28]
0x1800113a1  jz      short loc_1800113B3
0x1800113a3  mov     rcx, [rsp+530h+var_4C8]; hKey
0x1800113a8  call    cs:__imp_RegCloseKey
0x1800113ae  jmp     loc_18001149C
0x1800113b3  mov     rcx, [rsp+530h+var_4C8]; hKey
0x1800113b8  lea     rax, [rsp+530h+cbData]
0x1800113bd  mov     [rsp+530h+lpClass], rax; lpcbData
0x1800113c2  lea     r9, [rsp+530h+Type]; lpType
0x1800113c7  lea     rax, [rbp+430h+var_260]
0x1800113ce  mov     [rsp+530h+cbData], 105h
0x1800113d6  xor     r8d, r8d; lpReserved
0x1800113d9  mov     [rsp+530h+phkResult], rax; lpData
0x1800113de  lea     rdx, aName; "Name"
0x1800113e5  call    cs:__imp_RegQueryValueExA
0x1800113eb  mov     rcx, [rsp+530h+var_4C8]; hKey
0x1800113f0  mov     ebx, eax
0x1800113f2  call    cs:__imp_RegCloseKey
0x1800113f8  test    ebx, ebx
0x1800113fa  jnz     loc_180011498
0x180011400  cmp     [rsp+530h+Type], 1
0x180011405  jnz     loc_180011498
0x18001140b  lea     r8, [rsp+530h+var_4E0]
0x180011410  mov     [rsp+530h+var_4E0], 0
0x180011419  mov     rdx, rsi
0x18001141c  lea     rcx, [rbp+430h+var_260]
0x180011423  call    ?EvaluatePathCandidate@@YA?AW4PATH_CANDIDATE_EVALUATION@@PEBD0PEA_K@Z; EvaluatePathCandidate(char const *,char const *,unsigned __int64 *)
0x180011428  mov     ecx, eax
0x18001142a  sub     ecx, 1
0x18001142d  jz      short loc_180011462
0x18001142f  sub     ecx, 1
0x180011432  jz      short loc_180011458
0x180011434  cmp     ecx, 1
0x180011437  jnz     short loc_180011498
0x180011439  cmp     edi, ecx
0x18001143b  jz      short loc_1800114A5
0x18001143d  cmp     edi, 2
0x180011440  jz      short loc_180011498
0x180011442  cmp     edi, 3
0x180011445  jnz     short loc_180011462
0x180011447  mov     ebx, [rsp+530h+var_4F0]
0x18001144b  cmp     [rsp+530h+var_4E0], r12
0x180011450  jbe     loc_180011279
0x180011456  jmp     short loc_180011462
0x180011458  cmp     edi, 1
0x18001145b  jz      short loc_1800114A5
0x18001145d  cmp     edi, 2
0x180011460  jz      short loc_180011498
0x180011462  mov     r12, [rsp+530h+var_4E0]
0x180011467  lea     r8, [rbp+430h+SubKey]; char *
0x18001146e  mov     edx, 105h; unsigned __int64
0x180011473  lea     rcx, [rbp+430h+var_150]; char *
0x18001147a  mov     edi, eax
0x18001147c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180011481  mov     r10, [rsp+530h+var_4B8]
0x180011486  xor     eax, eax
0x180011488  test    r14d, r14d
0x18001148b  movzx   r15d, r15b
0x18001148f  mov     dword ptr [rsp+530h+var_4D0], r10d
0x180011494  cmovnz  r15d, eax
0x180011498  mov     ebx, [rsp+530h+var_4F0]
0x18001149c  cmp     edi, 1
0x18001149f  jnz     loc_180011279
0x1800114a5  mov     rcx, [rsp+530h+var_4C0]; hKey
0x1800114aa  call    cs:__imp_RegCloseKey
0x1800114b0  cmp     edi, 1
0x1800114b3  jz      short loc_1800114C2
0x1800114b5  inc     r14d
0x1800114b8  cmp     r14d, 2
0x1800114bc  jb      loc_180011234
0x1800114c2  mov     rsi, [rbp+430h+var_4B0]
0x1800114c6  mov     r12, [rbp+430h+var_4A8]
0x1800114ca  mov     r13, [rbp+430h+var_4A0]
0x1800114ce  test    edi, edi
0x1800114d0  jnz     short loc_180011505
0x1800114d2  mov     qword ptr [rsi], 0
0x1800114d9  xor     al, al
0x1800114db  mov     rcx, [rbp+430h+var_40]
0x1800114e2  xor     rcx, rsp; StackCookie
0x1800114e5  call    __security_check_cookie
0x1800114ea  mov     rbx, [rsp+530h+arg_0]
0x1800114f2  add     rsp, 500h
0x1800114f9  pop     r15
0x1800114fb  pop     r14
0x1800114fd  pop     r13
0x1800114ff  pop     r12
0x180011501  pop     rdi
0x180011502  pop     rsi
0x180011503  pop     rbp
0x180011504  retn
0x180011505  mov     edx, dword ptr [rsp+530h+var_4D0]; unsigned __int64
0x180011509  mov     rax, [rsi]
0x18001150c  mov     [rsi], rdx
0x18001150f  cmp     rax, rdx
0x180011512  jb      short loc_1800114D9
0x180011514  test    r13, r13
0x180011517  jz      short loc_180011528
0x180011519  lea     r8, [rbp+430h+var_150]; char *
0x180011520  mov     rcx, r13; char *
0x180011523  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180011528  test    r12, r12
0x18001152b  jz      short loc_180011531
0x18001152d  mov     [r12], r15b
0x180011531  mov     al, 1
0x180011533  jmp     short loc_1800114DB
```
