# CreateBackupFileName(char *,ulong,int,STRAU *,STRAU *)

- ea: `0x18001cca8`
- end: `0x18001cef7`
- name: `?CreateBackupFileName@@YAJPEADKHPEAVSTRAU@@1@Z`
- size: `591`
- prototype: `__int64 __fastcall(char *, unsigned int, int, struct STRAU *, struct STRAU *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180015e30`
- `0x180016e20`
- `0x180019454`

## callees

- `0x18001cca8`
- `0x18001dcf8`
- `0x1800275e4`
- `0x1800309d0`

## import_xrefs

- `msvcrt!_ultoa` at `0x18001ce65`
- `msvcrt!_ultoa` at `0x18001ce65`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18001cd6f`
- `IisRTL!?Append@STRAU@@QEAAHPEBG@Z` at `0x18001cd6f`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001cd55`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001cd8d`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001cdc3`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001cdde`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001ce73`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001ce89`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001cd55`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001cd8d`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001cdc3`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001cdde`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001ce73`
- `IisRTL!?Append@STRAU@@QEAAHPEBD@Z` at `0x18001ce89`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18001cd37`
- `IisRTL!?Copy@STRAU@@QEAAHPEBD@Z` at `0x18001cd37`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18001cd2b`
- `IisRTL!?QueryStr@STR@@QEBAPEADXZ` at `0x18001cd2b`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x18001cdab`
- `IisRTL!?Copy@STRAU@@QEAAHPEBG@Z` at `0x18001cdab`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18001cea2`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18001ceb4`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18001cea2`
- `IisRTL!?QueryStrA@STRAU@@QEAAPEADXZ` at `0x18001ceb4`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001cd9f`
- `IisRTL!?QueryStr@STRAU@@QEAAPEADH@Z` at `0x18001cd9f`

## pseudocode

```c
__int64 __fastcall CreateBackupFileName(char *a1, unsigned int a2, int a3, struct STRAU *a4, struct STRAU *a5)
{
  int v6; // edi
  unsigned int v7; // ebp
  const char *v8; // rbx
  const char *Str; // rax
  unsigned int HighestVersion; // esi
  int v11; // eax
  const unsigned __int16 *v12; // rax
  BOOL v13; // ebx
  int v14; // edi
  int v15; // eax
  BOOL v16; // ebx
  BOOL v17; // ebx
  unsigned int v19; // [rsp+20h] [rbp-58h] BYREF
  char Buffer[16]; // [rsp+28h] [rbp-50h] BYREF

  v6 = a3;
  v7 = a2;
  v8 = a1;
  if ( a2 - 10000 <= 0xFFFFD8ED )
    return (unsigned int)-2147024809;
  if ( !a1 )
    goto LABEL_8;
  if ( !(unsigned int)ValidateBackupLocation(a1, a3) )
    return (unsigned int)-2147024809;
  if ( v6 )
  {
    if ( *(_WORD *)v8 )
      goto LABEL_9;
    goto LABEL_8;
  }
  if ( !*v8 )
  {
LABEL_8:
    v8 = "MDBackUp";
    v6 = 0;
  }
LABEL_9:
  Str = STR::QueryStr(g_pstrBackupFilePath);
  if ( !STRAU::Copy(a4, Str) || !STRAU::Append(a4, "\\") )
    return (unsigned int)-2147024882;
  if ( v6 )
  {
    v11 = STRAU::Append(a4, (const unsigned __int16 *)v8);
    HighestVersion = v11 == 0 ? 0x8007000E : 0;
    if ( !v11 )
      return HighestVersion;
  }
  else
  {
    HighestVersion = 0;
    if ( !STRAU::Append(a4, v8) )
      return (unsigned int)-2147024882;
  }
  v12 = (const unsigned __int16 *)STRAU::QueryStr(a4, 1);
  v13 = STRAU::Copy(a5, v12) == 0;
  v14 = v13 | (STRAU::Append(a4, ".MD") == 0);
  if ( !STRAU::Append(a5, ".SC") )
    v14 = 1;
  if ( v14 )
    return (unsigned int)-2147024882;
  v19 = v7;
  if ( v7 != -1 )
  {
    if ( v7 != -2 )
      goto LABEL_30;
    HighestVersion = GetHighestVersion(a4, &v19);
    goto LABEL_29;
  }
  v15 = GetHighestVersion(a4, &v19);
  HighestVersion = v15;
  if ( v15 < 0 )
  {
    if ( v15 == -2147024894 )
    {
      v7 = 0;
      HighestVersion = 0;
      goto LABEL_30;
    }
LABEL_29:
    v7 = v19;
    goto LABEL_30;
  }
  v7 = v19;
  if ( v19 < 0x270F )
  {
    v7 = v19 + 1;
    goto LABEL_31;
  }
  HighestVersion = -2147024773;
LABEL_30:
  if ( (HighestVersion & 0x80000000) != 0 )
    return HighestVersion;
LABEL_31:
  _ultoa(v7, Buffer, 10);
  v16 = STRAU::Append(a4, Buffer) == 0;
  if ( v16 | (STRAU::Append(a5, Buffer) == 0) )
    return (unsigned int)-2147024882;
  v17 = STRAU::QueryStrA(a4) == 0;
  if ( v17 | (STRAU::QueryStrA(a5) == 0) )
    return (unsigned int)-2147024882;
  return HighestVersion;
}

```

## disassembly

```asm
0x18001cca8  mov     [rsp+arg_10], rbx
0x18001ccad  push    rbp
0x18001ccae  push    rsi
0x18001ccaf  push    rdi
0x18001ccb0  push    r12
0x18001ccb2  push    r13
0x18001ccb4  push    r14
0x18001ccb6  push    r15
0x18001ccb8  sub     rsp, 40h
0x18001ccbc  mov     rax, cs:__security_cookie
0x18001ccc3  xor     rax, rsp
0x18001ccc6  mov     [rsp+78h+var_40], rax
0x18001cccb  mov     r12, [rsp+78h+arg_20]
0x18001ccd3  lea     eax, [rdx-2710h]
0x18001ccd9  mov     r15, r9
0x18001ccdc  mov     edi, r8d
0x18001ccdf  mov     ebp, edx
0x18001cce1  mov     rbx, rcx
0x18001cce4  cmp     eax, 0FFFFD8EDh
0x18001cce9  jbe     loc_18001CECB
0x18001ccef  xor     r13d, r13d
0x18001ccf2  test    rcx, rcx
0x18001ccf5  jz      short loc_18001CD1A
0x18001ccf7  mov     edx, r8d; int
0x18001ccfa  call    ?ValidateBackupLocation@@YAHPEADH@Z; ValidateBackupLocation(char *,int)
0x18001ccff  test    eax, eax
0x18001cd01  jz      loc_18001CECB
0x18001cd07  test    edi, edi
0x18001cd09  jz      short loc_18001CD15
0x18001cd0b  cmp     [rbx], r13w
0x18001cd0f  jz      short loc_18001CD1A
0x18001cd11  test    edi, edi
0x18001cd13  jnz     short loc_18001CD24
0x18001cd15  cmp     [rbx], r13b
0x18001cd18  jnz     short loc_18001CD24
0x18001cd1a  lea     rbx, aMdbackup; "MDBackUp"
0x18001cd21  mov     edi, r13d
0x18001cd24  mov     rcx, cs:?g_pstrBackupFilePath@@3PEAVSTR@@EA; STR * g_pstrBackupFilePath
0x18001cd2b  call    cs:__imp_?QueryStr@STR@@QEBAPEADXZ; STR::QueryStr(void)
0x18001cd31  mov     rdx, rax
0x18001cd34  mov     rcx, r15
0x18001cd37  call    cs:__imp_?Copy@STRAU@@QEAAHPEBD@Z; STRAU::Copy(char const *)
0x18001cd3d  test    eax, eax
0x18001cd3f  jnz     short loc_18001CD4B
0x18001cd41  mov     esi, 8007000Eh
0x18001cd46  jmp     loc_18001CED0
0x18001cd4b  lea     rdx, asc_18003A528; "\\"
0x18001cd52  mov     rcx, r15
0x18001cd55  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001cd5b  test    eax, eax
0x18001cd5d  jz      short loc_18001CD41
0x18001cd5f  mov     r14d, 8007000Eh
0x18001cd65  mov     rdx, rbx
0x18001cd68  mov     rcx, r15
0x18001cd6b  test    edi, edi
0x18001cd6d  jz      short loc_18001CD8A
0x18001cd6f  call    cs:__imp_?Append@STRAU@@QEAAHPEBG@Z; STRAU::Append(ushort const *)
0x18001cd75  mov     ecx, eax
0x18001cd77  neg     ecx
0x18001cd79  sbb     esi, esi
0x18001cd7b  not     esi
0x18001cd7d  and     esi, r14d
0x18001cd80  test    eax, eax
0x18001cd82  jz      loc_18001CED0
0x18001cd88  jmp     short loc_18001CD97
0x18001cd8a  mov     esi, r13d
0x18001cd8d  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001cd93  test    eax, eax
0x18001cd95  jz      short loc_18001CDF2
0x18001cd97  mov     edx, 1
0x18001cd9c  mov     rcx, r15
0x18001cd9f  call    cs:__imp_?QueryStr@STRAU@@QEAAPEADH@Z; STRAU::QueryStr(int)
0x18001cda5  mov     rdx, rax
0x18001cda8  mov     rcx, r12
0x18001cdab  call    cs:__imp_?Copy@STRAU@@QEAAHPEBG@Z; STRAU::Copy(ushort const *)
0x18001cdb1  mov     ebx, r13d
0x18001cdb4  lea     rdx, aMd; ".MD"
0x18001cdbb  test    eax, eax
0x18001cdbd  mov     rcx, r15
0x18001cdc0  setz    bl
0x18001cdc3  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001cdc9  mov     edi, r13d
0x18001cdcc  lea     rdx, aSc; ".SC"
0x18001cdd3  test    eax, eax
0x18001cdd5  mov     rcx, r12
0x18001cdd8  setz    dil
0x18001cddc  or      edi, ebx
0x18001cdde  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001cde4  test    eax, eax
0x18001cde6  mov     ebx, 1
0x18001cdeb  cmovz   edi, ebx
0x18001cdee  test    edi, edi
0x18001cdf0  jz      short loc_18001CDFA
0x18001cdf2  mov     esi, r14d
0x18001cdf5  jmp     loc_18001CED0
0x18001cdfa  mov     [rsp+78h+var_58], ebp
0x18001cdfe  cmp     ebp, 0FFFFFFFFh
0x18001ce01  jnz     short loc_18001CE3C
0x18001ce03  lea     rdx, [rsp+78h+var_58]; unsigned int *
0x18001ce08  mov     rcx, r15; struct STRAU *
0x18001ce0b  call    ?GetHighestVersion@@YAJPEAVSTRAU@@PEAK@Z; GetHighestVersion(STRAU *,ulong *)
0x18001ce10  mov     esi, eax
0x18001ce12  test    eax, eax
0x18001ce14  js      short loc_18001CE2D
0x18001ce16  mov     ebp, [rsp+78h+var_58]
0x18001ce1a  cmp     ebp, 270Fh
0x18001ce20  jnb     short loc_18001CE26
0x18001ce22  add     ebp, ebx
0x18001ce24  jmp     short loc_18001CE58
0x18001ce26  mov     esi, 8007007Bh
0x18001ce2b  jmp     short loc_18001CE54
0x18001ce2d  cmp     eax, 80070002h
0x18001ce32  jnz     short loc_18001CE50
0x18001ce34  mov     ebp, r13d
0x18001ce37  mov     esi, r13d
0x18001ce3a  jmp     short loc_18001CE54
0x18001ce3c  cmp     ebp, 0FFFFFFFEh
0x18001ce3f  jnz     short loc_18001CE54
0x18001ce41  lea     rdx, [rsp+78h+var_58]; unsigned int *
0x18001ce46  mov     rcx, r15; struct STRAU *
0x18001ce49  call    ?GetHighestVersion@@YAJPEAVSTRAU@@PEAK@Z; GetHighestVersion(STRAU *,ulong *)
0x18001ce4e  mov     esi, eax
0x18001ce50  mov     ebp, [rsp+78h+var_58]
0x18001ce54  test    esi, esi
0x18001ce56  js      short loc_18001CED0
0x18001ce58  mov     r8d, 0Ah; Radix
0x18001ce5e  lea     rdx, [rsp+78h+Buffer]; Buffer
0x18001ce63  mov     ecx, ebp; Value
0x18001ce65  call    cs:__imp__ultoa
0x18001ce6b  lea     rdx, [rsp+78h+Buffer]
0x18001ce70  mov     rcx, r15
0x18001ce73  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001ce79  mov     ebx, r13d
0x18001ce7c  lea     rdx, [rsp+78h+Buffer]
0x18001ce81  test    eax, eax
0x18001ce83  mov     rcx, r12
0x18001ce86  setz    bl
0x18001ce89  call    cs:__imp_?Append@STRAU@@QEAAHPEBD@Z; STRAU::Append(char const *)
0x18001ce8f  test    eax, eax
0x18001ce91  mov     ecx, r13d
0x18001ce94  setz    cl
0x18001ce97  or      ecx, ebx
0x18001ce99  jnz     loc_18001CDF2
0x18001ce9f  mov     rcx, r15
0x18001cea2  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x18001cea8  mov     ebx, r13d
0x18001ceab  mov     rcx, r12
0x18001ceae  test    rax, rax
0x18001ceb1  setz    bl
0x18001ceb4  call    cs:__imp_?QueryStrA@STRAU@@QEAAPEADXZ; STRAU::QueryStrA(void)
0x18001ceba  test    rax, rax
0x18001cebd  mov     ecx, r13d
0x18001cec0  setz    cl
0x18001cec3  or      ecx, ebx
0x18001cec5  cmovnz  esi, r14d
0x18001cec9  jmp     short loc_18001CED0
0x18001cecb  mov     esi, 80070057h
0x18001ced0  mov     eax, esi
0x18001ced2  mov     rcx, [rsp+78h+var_40]
0x18001ced7  xor     rcx, rsp; StackCookie
0x18001ceda  call    __security_check_cookie
0x18001cedf  mov     rbx, [rsp+78h+arg_10]
0x18001cee7  add     rsp, 40h
0x18001ceeb  pop     r15
0x18001ceed  pop     r14
0x18001ceef  pop     r13
0x18001cef1  pop     r12
0x18001cef3  pop     rdi
0x18001cef4  pop     rsi
0x18001cef5  pop     rbp
0x18001cef6  retn
```
