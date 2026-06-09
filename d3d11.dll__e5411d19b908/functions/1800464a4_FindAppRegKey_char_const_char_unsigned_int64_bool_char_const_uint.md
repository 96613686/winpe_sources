# FindAppRegKey(char const *,char *,unsigned __int64 *,bool *,char const *,uint)

- ea: `0x1800464a4`
- end: `0x180046870`
- name: `?FindAppRegKey@@YA_NPEBDPEADPEA_KPEA_N0I@Z`
- size: `972`
- prototype: `bool __fastcall(const char *, char *, unsigned __int64 *, bool *, const char *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800462b0`

## callees

- `0x180045700`
- `0x1800464a4`
- `0x180046878`
- `0x1800a3858`
- `0x1800a9d20`
- `0x1800aa914`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800466c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180046704`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800466c4`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180046704`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800465f9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExA` at `0x1800465f9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004655d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046711`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046802`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004655d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046711`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180046802`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180046547`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004667e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180046547`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18004667e`

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
  _BYTE *v12; // r12
  char *v13; // r13
  HKEY v15; // r13
  LSTATUS v16; // ebx
  int v17; // edx
  CHAR *v18; // r8
  char *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rdx
  char *v22; // rax
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // rax
  DWORD v25; // [rsp+40h] [rbp-C0h]
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v28; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  BYTE Data[4]; // [rsp+5Ch] [rbp-A4h] BYREF
  unsigned __int64 v31; // [rsp+60h] [rbp-A0h]
  HKEY v32; // [rsp+68h] [rbp-98h] BYREF
  DWORD v33; // [rsp+70h] [rbp-90h]
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 *v35; // [rsp+80h] [rbp-80h]
  bool *v36; // [rsp+88h] [rbp-78h]
  char *v37; // [rsp+90h] [rbp-70h]
  HKEY hKey[2]; // [rsp+98h] [rbp-68h]
  CHAR Name[272]; // [rsp+B0h] [rbp-50h] BYREF
  CHAR SubKey[272]; // [rsp+1C0h] [rbp+C0h] BYREF
  BYTE v41[272]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v42[272]; // [rsp+3E0h] [rbp+2E0h] BYREF

  v28 = (HKEY)a5;
  v36 = a4;
  v35 = a3;
  v37 = a2;
  if ( !a3 )
    return 0;
  v6 = 0;
  v7 = v28;
  v8 = 0;
  LODWORD(v31) = 261;
  phkResult = 0;
  v9 = 0;
  *(__m128i *)hKey = _mm_load_si128((const __m128i *)&_xmm_ffffffff80000002ffffffff80000001);
  v10 = 1;
  do
  {
    v28 = hKey[v9];
    if ( RegOpenKeyExA(v28, "Software\\Microsoft\\Direct3D", 0, 0x20019u, &phkResult) )
      goto LABEL_6;
    v11 = 0;
    v15 = v28;
    while ( 1 )
    {
      cchName = 261;
      if ( RegEnumKeyExA(phkResult, v11, Name, &cchName, 0, 0, 0, 0) )
        break;
      v25 = ++v11;
      if ( !(unsigned int)o__stricmp_0(Name, "MostRecentApplication") )
        goto LABEL_28;
      StringCchPrintfA(SubKey, 0x105u, "%s\\%s", "Software\\Microsoft\\Direct3D", Name);
      v32 = 0;
      v33 = cchName + 29;
      if ( RegOpenKeyExA(v15, SubKey, 0, 0x20019u, &v32) )
        goto LABEL_28;
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExA(v32, "Size", 0, &Type, Data, &cbData)
        && Type == 4
        && *(_DWORD *)Data
        && *(_DWORD *)Data != a6 )
      {
        RegCloseKey(v32);
        goto LABEL_28;
      }
      cbData = 261;
      v16 = RegQueryValueExA(v32, "Name", 0, &Type, v41, &cbData);
      RegCloseKey(v32);
      if ( v16 || Type != 1 )
        goto LABEL_27;
      v28 = 0;
      v17 = EvaluatePathCandidate(v41, v7, &v28);
      if ( v17 == 1 )
        goto LABEL_19;
      if ( v17 == 2 )
      {
        if ( v6 != 2 )
          goto LABEL_19;
LABEL_27:
        v11 = v25;
LABEL_28:
        if ( v6 == 1 )
          break;
      }
      else
      {
        if ( v17 != 3 || v6 == 2 )
          goto LABEL_27;
        if ( v6 != 3 || (v11 = v25, v28 > v8) )
        {
LABEL_19:
          v18 = SubKey;
          v8 = v28;
          v19 = v42;
          LODWORD(v31) = v33;
          v6 = v17;
          v20 = 2147483646;
          v21 = 261;
          do
          {
            if ( !v20 )
              break;
            if ( !*v18 )
              break;
            *v19++ = *v18++;
            --v20;
            --v21;
          }
          while ( v21 );
          v22 = v19 - 1;
          if ( v21 )
            v22 = v19;
          *v22 = 0;
          if ( (_DWORD)v9 )
            v10 = 0;
          goto LABEL_27;
        }
      }
    }
    RegCloseKey(phkResult);
    if ( v6 == 1 )
      break;
LABEL_6:
    v9 = (unsigned int)(v9 + 1);
  }
  while ( (unsigned int)v9 < 2 );
  v12 = v36;
  v13 = v37;
  if ( !v6 )
  {
    *v35 = 0;
    return 0;
  }
  v23 = (unsigned int)v31;
  v24 = *v35;
  *v35 = (unsigned int)v31;
  if ( v24 < v23 )
    return 0;
  if ( v13 )
    StringCchCopyA(v13, v23, v42);
  if ( v12 )
    *v12 = v10;
  return 1;
}

```

## disassembly

```asm
0x1800464a4  mov     [rsp-8+arg_0], rbx
0x1800464a9  push    rbp
0x1800464aa  push    rsi
0x1800464ab  push    rdi
0x1800464ac  push    r12
0x1800464ae  push    r13
0x1800464b0  push    r14
0x1800464b2  push    r15
0x1800464b4  lea     rbp, [rsp-400h]
0x1800464bc  sub     rsp, 500h
0x1800464c3  mov     rax, cs:__security_cookie
0x1800464ca  xor     rax, rsp
0x1800464cd  mov     [rbp+430h+var_40], rax
0x1800464d4  mov     rax, [rbp+430h+arg_20]
0x1800464db  mov     [rsp+530h+var_4E0], rax
0x1800464e0  mov     [rbp+430h+var_4A8], r9
0x1800464e4  mov     [rbp+430h+var_4B0], r8
0x1800464e8  mov     [rbp+430h+var_4A0], rdx
0x1800464ec  test    r8, r8
0x1800464ef  jz      loc_18004658C
0x1800464f5  movdqa  xmm0, cs:__xmm@ffffffff80000002ffffffff80000001
0x1800464fd  xor     edi, edi
0x1800464ff  mov     rsi, [rsp+530h+var_4E0]
0x180046504  mov     eax, 105h
0x180046509  xor     r12d, r12d
0x18004650c  mov     dword ptr [rsp+530h+var_4D0], eax
0x180046510  mov     [rsp+530h+var_4B8], rdi
0x180046515  xor     r14d, r14d
0x180046518  movdqu  xmmword ptr [rbp+430h+hKey], xmm0
0x18004651d  mov     r15b, 1
0x180046520  mov     rax, [rbp+r14*8+430h+hKey]
0x180046525  lea     rcx, [rsp+530h+var_4B8]
0x18004652a  mov     [rsp+530h+phkResult], rcx; phkResult
0x18004652f  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Direct3D"
0x180046536  mov     rcx, rax; hKey
0x180046539  mov     [rsp+530h+var_4E0], rax
0x18004653e  mov     r9d, 20019h; samDesired
0x180046544  xor     r8d, r8d; ulOptions
0x180046547  call    cs:__imp_RegOpenKeyExA
0x18004654d  test    eax, eax
0x18004654f  jnz     short loc_180046568
0x180046551  xor     ebx, ebx
0x180046553  cmp     edi, 1
0x180046556  jnz     short loc_1800465B8
0x180046558  mov     rcx, [rsp+530h+var_4B8]; hKey
0x18004655d  call    cs:__imp_RegCloseKey
0x180046563  cmp     edi, 1
0x180046566  jz      short loc_180046571
0x180046568  inc     r14d
0x18004656b  cmp     r14d, 2
0x18004656f  jb      short loc_180046520
0x180046571  mov     rsi, [rbp+430h+var_4B0]
0x180046575  mov     r12, [rbp+430h+var_4A8]
0x180046579  mov     r13, [rbp+430h+var_4A0]
0x18004657d  test    edi, edi
0x18004657f  jnz     loc_180046839
0x180046585  mov     qword ptr [rsi], 0
0x18004658c  xor     al, al
0x18004658e  mov     rcx, [rbp+430h+var_40]
0x180046595  xor     rcx, rsp; StackCookie
0x180046598  call    __security_check_cookie
0x18004659d  mov     rbx, [rsp+530h+arg_0]
0x1800465a5  add     rsp, 500h
0x1800465ac  pop     r15
0x1800465ae  pop     r14
0x1800465b0  pop     r13
0x1800465b2  pop     r12
0x1800465b4  pop     rdi
0x1800465b5  pop     rsi
0x1800465b6  pop     rbp
0x1800465b7  retn
0x1800465b8  mov     r13, [rsp+530h+var_4E0]
0x1800465bd  mov     rcx, [rsp+530h+var_4B8]; hKey
0x1800465c2  lea     r9, [rsp+530h+cchName]; lpcchName
0x1800465c7  mov     [rsp+530h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800465d0  lea     r8, [rbp+430h+Name]; lpName
0x1800465d4  mov     [rsp+530h+lpcchClass], 0; lpcchClass
0x1800465dd  mov     edx, ebx; dwIndex
0x1800465df  mov     [rsp+530h+lpClass], 0; lpClass
0x1800465e8  mov     [rsp+530h+phkResult], 0; lpReserved
0x1800465f1  mov     [rsp+530h+cchName], 105h
0x1800465f9  call    cs:__imp_RegEnumKeyExA
0x1800465ff  test    eax, eax
0x180046601  jnz     loc_180046558
0x180046607  inc     ebx
0x180046609  lea     rdx, aMostrecentappl; "MostRecentApplication"
0x180046610  lea     rcx, [rbp+430h+Name]
0x180046614  mov     [rsp+530h+var_4F0], ebx
0x180046618  call    _o__stricmp_0
0x18004661d  test    eax, eax
0x18004661f  jz      loc_1800467CC
0x180046625  lea     rax, [rbp+430h+Name]
0x180046629  mov     edx, 105h; unsigned __int64
0x18004662e  lea     r9, aSoftwareMicros_0; "Software\\Microsoft\\Direct3D"
0x180046635  mov     [rsp+530h+phkResult], rax
0x18004663a  lea     r8, aSS; "%s\\%s"
0x180046641  lea     rcx, [rbp+430h+SubKey]; char *
0x180046648  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18004664d  mov     eax, [rsp+530h+cchName]
0x180046651  lea     rdx, [rbp+430h+SubKey]; lpSubKey
0x180046658  add     eax, 1Dh
0x18004665b  mov     [rsp+530h+var_4C8], 0
0x180046664  mov     [rsp+530h+var_4C0], eax
0x180046668  mov     r9d, 20019h; samDesired
0x18004666e  lea     rax, [rsp+530h+var_4C8]
0x180046673  xor     r8d, r8d; ulOptions
0x180046676  mov     rcx, r13; hKey
0x180046679  mov     [rsp+530h+phkResult], rax; phkResult
0x18004667e  call    cs:__imp_RegOpenKeyExA
0x180046684  test    eax, eax
0x180046686  jnz     loc_1800467CC
0x18004668c  mov     rcx, [rsp+530h+var_4C8]; hKey
0x180046691  lea     r9, [rsp+530h+Type]; lpType
0x180046696  mov     [rsp+530h+Type], eax
0x18004669a  lea     rdx, ValueName; "Size"
0x1800466a1  mov     dword ptr [rsp+530h+Data], eax
0x1800466a5  xor     r8d, r8d; lpReserved
0x1800466a8  lea     rax, [rsp+530h+cbData]
0x1800466ad  mov     [rsp+530h+cbData], 4
0x1800466b5  mov     [rsp+530h+lpClass], rax; lpcbData
0x1800466ba  lea     rax, [rsp+530h+Data]
0x1800466bf  mov     [rsp+530h+phkResult], rax; lpData
0x1800466c4  call    cs:__imp_RegQueryValueExA
0x1800466ca  test    eax, eax
0x1800466cc  jz      loc_1800467DA
0x1800466d2  mov     rcx, [rsp+530h+var_4C8]; hKey
0x1800466d7  lea     rax, [rsp+530h+cbData]
0x1800466dc  mov     [rsp+530h+lpClass], rax; lpcbData
0x1800466e1  lea     r9, [rsp+530h+Type]; lpType
0x1800466e6  lea     rax, [rbp+430h+var_260]
0x1800466ed  mov     [rsp+530h+cbData], 105h
0x1800466f5  xor     r8d, r8d; lpReserved
0x1800466f8  mov     [rsp+530h+phkResult], rax; lpData
0x1800466fd  lea     rdx, aName; "Name"
0x180046704  call    cs:__imp_RegQueryValueExA
0x18004670a  mov     rcx, [rsp+530h+var_4C8]; hKey
0x18004670f  mov     ebx, eax
0x180046711  call    cs:__imp_RegCloseKey
0x180046717  test    ebx, ebx
0x180046719  jnz     loc_1800467C8
0x18004671f  cmp     [rsp+530h+Type], 1
0x180046724  jnz     loc_1800467C8
0x18004672a  lea     r8, [rsp+530h+var_4E0]
0x18004672f  mov     [rsp+530h+var_4E0], 0
0x180046738  mov     rdx, rsi
0x18004673b  lea     rcx, [rbp+430h+var_260]
0x180046742  call    ?EvaluatePathCandidate@@YA?AW4PATH_CANDIDATE_EVALUATION@@PEBD0PEA_K@Z; EvaluatePathCandidate(char const *,char const *,unsigned __int64 *)
0x180046747  mov     ecx, eax
0x180046749  mov     edx, eax
0x18004674b  sub     ecx, 1
0x18004674e  jz      short loc_180046767
0x180046750  sub     ecx, 1
0x180046753  jnz     loc_18004680A
0x180046759  cmp     edi, 1
0x18004675c  jz      loc_180046558
0x180046762  cmp     edi, 2
0x180046765  jz      short loc_1800467C8
0x180046767  mov     eax, [rsp+530h+var_4C0]
0x18004676b  lea     r8, [rbp+430h+SubKey]
0x180046772  mov     r12, [rsp+530h+var_4E0]
0x180046777  lea     rcx, [rbp+430h+var_150]
0x18004677e  mov     dword ptr [rsp+530h+var_4D0], eax
0x180046782  mov     edi, edx
0x180046784  mov     eax, 7FFFFFFEh
0x180046789  mov     edx, 105h
0x18004678e  test    rax, rax
0x180046791  jz      short loc_1800467AD
0x180046793  mov     r9b, [r8]
0x180046796  test    r9b, r9b
0x180046799  jz      short loc_1800467AD
0x18004679b  mov     [rcx], r9b
0x18004679e  inc     r8
0x1800467a1  inc     rcx
0x1800467a4  dec     rax
0x1800467a7  sub     rdx, 1
0x1800467ab  jnz     short loc_18004678E
0x1800467ad  test    rdx, rdx
0x1800467b0  movzx   r15d, r15b
0x1800467b4  lea     rax, [rcx-1]
0x1800467b8  cmovnz  rax, rcx
0x1800467bc  mov     byte ptr [rax], 0
0x1800467bf  xor     eax, eax
0x1800467c1  test    r14d, r14d
0x1800467c4  cmovnz  r15d, eax
0x1800467c8  mov     ebx, [rsp+530h+var_4F0]
0x1800467cc  cmp     edi, 1
0x1800467cf  jnz     loc_1800465BD
0x1800467d5  jmp     loc_180046558
0x1800467da  cmp     [rsp+530h+Type], 4
0x1800467df  jnz     loc_1800466D2
0x1800467e5  mov     eax, dword ptr [rsp+530h+Data]
0x1800467e9  test    eax, eax
0x1800467eb  jz      loc_1800466D2
0x1800467f1  cmp     eax, [rbp+430h+arg_28]
0x1800467f7  jz      loc_1800466D2
0x1800467fd  mov     rcx, [rsp+530h+var_4C8]; hKey
0x180046802  call    cs:__imp_RegCloseKey
0x180046808  jmp     short loc_1800467CC
0x18004680a  cmp     ecx, 1
0x18004680d  jnz     short loc_1800467C8
0x18004680f  cmp     edi, ecx
0x180046811  jz      loc_180046558
0x180046817  cmp     edi, 2
0x18004681a  jz      short loc_1800467C8
0x18004681c  cmp     edi, 3
0x18004681f  jnz     loc_180046767
0x180046825  mov     ebx, [rsp+530h+var_4F0]
0x180046829  cmp     [rsp+530h+var_4E0], r12
0x18004682e  jbe     loc_1800465BD
0x180046834  jmp     loc_180046767
0x180046839  mov     edx, dword ptr [rsp+530h+var_4D0]; unsigned __int64
0x18004683d  mov     rax, [rsi]
0x180046840  mov     [rsi], rdx
0x180046843  cmp     rax, rdx
0x180046846  jb      loc_18004658C
0x18004684c  test    r13, r13
0x18004684f  jz      short loc_180046860
0x180046851  lea     r8, [rbp+430h+var_150]; char *
0x180046858  mov     rcx, r13; char *
0x18004685b  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180046860  test    r12, r12
0x180046863  jz      short loc_180046869
0x180046865  mov     [r12], r15b
0x180046869  mov     al, 1
0x18004686b  jmp     loc_18004658E
```
