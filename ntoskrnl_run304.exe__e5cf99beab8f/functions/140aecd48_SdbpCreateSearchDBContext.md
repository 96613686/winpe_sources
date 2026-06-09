# SdbpCreateSearchDBContext

- ea: `0x140aecd48`
- end: `0x140aecf95`
- name: `SdbpCreateSearchDBContext`
- size: `589`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x14097965c`
- `0x140ab5178`

## callees

- `0x1402dc448`
- `0x1404a9868`
- `0x1406d9d70`
- `0x1406f4880`
- `0x140979890`
- `0x14097b68c`
- `0x14097d158`
- `0x140aa2b78`
- `0x140aecd48`

## string_xrefs

- `0x140aecdd4`: `Unable to allocate memory for directory path`
- `0x140aece19`: `Unable to parse executable path for "%ws"`
- `0x140aecde1`: `SdbpCreateSearchDBContext`
- `0x140aece2b`: `SdbpCreateSearchDBContext`
- `0x140aece61`: `SdbpCreateSearchDBContext`
- `0x140aecf3b`: `SdbpCreateSearchDBContext`

## pseudocode

```c
__int64 __fastcall SdbpCreateSearchDBContext(_QWORD *a1, const wchar_t **a2)
{
  unsigned int v4; // r12d
  __int64 v5; // rcx
  const wchar_t *v6; // rbp
  __int64 v7; // rax
  unsigned int v8; // ebx
  wchar_t *v9; // rsi
  __int64 v10; // rcx
  wchar_t *v11; // rbx
  __int64 v12; // rcx
  wchar_t *v13; // rax
  unsigned int v14; // r11d
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rax
  _WORD *v18; // r14
  int v20; // [rsp+20h] [rbp-488h]
  wchar_t pszSrc[264]; // [rsp+40h] [rbp-468h] BYREF
  wchar_t v22[264]; // [rsp+250h] [rbp-258h] BYREF

  v4 = 0;
  memset_0(v22, 0, 0x208u);
  memset_0(pszSrc, 0, 0x208u);
  if ( !a2 )
  {
    v9 = (wchar_t *)AslAlloc(v5, 4);
    v11 = (wchar_t *)AslAlloc(v15, 2);
    v17 = AslAlloc(v16, 2);
    v18 = (_WORD *)v17;
    if ( !v9 || !v11 || !v17 )
    {
      AslLogCallPrintf(1, (unsigned int)"SdbpCreateSearchDBContext", 469, (unsigned int)"Unable to allocate memory");
      if ( !v9 )
        goto LABEL_20;
      goto LABEL_19;
    }
    RtlStringCchCopyW(v9, 2u, L".");
    *v11 = 0;
    *v18 = 0;
    a1[3] = v18;
    goto LABEL_17;
  }
  v6 = *a2;
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  v8 = v7 + 1;
  v9 = (wchar_t *)AslAlloc(v5, 2LL * (unsigned int)(v7 + 1));
  if ( !v9 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCreateSearchDBContext",
      437,
      (unsigned int)"Unable to allocate memory for directory path");
    return v4;
  }
  if ( (int)AslPathSplit(v6, v9, v8, pszSrc, v20, v22) >= 0 )
  {
    v13 = (wchar_t *)AslAlloc(v10, 520);
    v11 = v13;
    if ( !v13 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpCreateSearchDBContext",
        454,
        (unsigned int)"Unable to allocate memory for full name");
      goto LABEL_19;
    }
    if ( RtlStringCchCopyW(v13, 0x104u, pszSrc) < 0 || RtlStringCchCatW(v11, v14, v22) < 0 )
      goto LABEL_19;
LABEL_17:
    a1[1] = a2;
    v4 = 1;
    a1[7] = 0;
    a1[4] = v9;
    a1[5] = v11;
    a1[6] = 0;
    a1[9] = 0;
    a1[8] = 0;
    a1[11] = 0;
    a1[12] = 0;
    return v4;
  }
  v11 = 0;
  AslLogCallPrintf(
    1,
    (unsigned int)"SdbpCreateSearchDBContext",
    448,
    (unsigned int)"Unable to parse executable path for \"%ws\"",
    v6);
LABEL_19:
  AslFree(v12, v9);
LABEL_20:
  if ( v11 )
    AslFree(v12, v11);
  return v4;
}

```

## disassembly

```asm
0x140aecd48  mov     [rsp+arg_10], rbx
0x140aecd4d  push    rbp
0x140aecd4e  push    rsi
0x140aecd4f  push    rdi
0x140aecd50  push    r12
0x140aecd52  push    r13
0x140aecd54  push    r14
0x140aecd56  push    r15
0x140aecd58  sub     rsp, 470h
0x140aecd5f  mov     rax, cs:__security_cookie
0x140aecd66  xor     rax, rsp
0x140aecd69  mov     [rsp+4A8h+var_48], rax
0x140aecd71  mov     r15, rdx
0x140aecd74  mov     rdi, rcx
0x140aecd77  mov     r14d, 208h
0x140aecd7d  lea     rcx, [rsp+4A8h+var_258]; void *
0x140aecd85  xor     r13d, r13d
0x140aecd88  mov     r8d, r14d; Size
0x140aecd8b  xor     edx, edx; Val
0x140aecd8d  mov     r12d, r13d
0x140aecd90  call    memset_0
0x140aecd95  mov     r8d, r14d; Size
0x140aecd98  lea     rcx, [rsp+4A8h+pszSrc]; void *
0x140aecd9d  xor     edx, edx; Val
0x140aecd9f  call    memset_0
0x140aecda4  test    r15, r15
0x140aecda7  jz      loc_140AECEB0
0x140aecdad  mov     rbp, [r15]
0x140aecdb0  or      rax, 0FFFFFFFFFFFFFFFFh
0x140aecdb4  inc     rax
0x140aecdb7  cmp     [rbp+rax*2+0], r13w
0x140aecdbd  jnz     short loc_140AECDB4
0x140aecdbf  lea     ebx, [rax+1]
0x140aecdc2  mov     edx, ebx
0x140aecdc4  add     rdx, rdx
0x140aecdc7  call    AslAlloc
0x140aecdcc  mov     rsi, rax
0x140aecdcf  test    rax, rax
0x140aecdd2  jnz     short loc_140AECDF5
0x140aecdd4  lea     r9, aUnableToAlloca_2; "Unable to allocate memory for directory"...
0x140aecddb  mov     r8d, 1B5h
0x140aecde1  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140aecde8  lea     ecx, [rax+1]
0x140aecdeb  call    AslLogCallPrintf
0x140aecdf0  jmp     loc_140AECF66
0x140aecdf5  lea     rax, [rsp+4A8h+var_258]
0x140aecdfd  mov     r8d, ebx; cchDest
0x140aece00  lea     r9, [rsp+4A8h+pszSrc]; NTSTRSAFE_PWSTR
0x140aece05  mov     [rsp+4A8h+var_480], rax; NTSTRSAFE_PWSTR
0x140aece0a  mov     rdx, rsi; pszDest
0x140aece0d  mov     rcx, rbp; pszSrc
0x140aece10  call    AslPathSplit
0x140aece15  test    eax, eax
0x140aece17  jns     short loc_140AECE44
0x140aece19  lea     r9, aUnableToParseE; "Unable to parse executable path for \"%"...
0x140aece20  mov     [rsp+4A8h+var_488], rbp
0x140aece25  mov     r8d, 1C0h
0x140aece2b  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140aece32  mov     ecx, 1
0x140aece37  mov     rbx, r13
0x140aece3a  call    AslLogCallPrintf
0x140aece3f  jmp     loc_140AECF51
0x140aece44  mov     rdx, r14
0x140aece47  call    AslAlloc
0x140aece4c  mov     rbx, rax
0x140aece4f  test    rax, rax
0x140aece52  jnz     short loc_140AECE75
0x140aece54  lea     r9, aUnableToAlloca_1; "Unable to allocate memory for full name"
0x140aece5b  mov     r8d, 1C6h
0x140aece61  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140aece68  lea     ecx, [rax+1]
0x140aece6b  call    AslLogCallPrintf
0x140aece70  jmp     loc_140AECF51
0x140aece75  mov     r11d, 104h
0x140aece7b  lea     r8, [rsp+4A8h+pszSrc]; pszSrc
0x140aece80  mov     edx, r11d; cchDest
0x140aece83  mov     rcx, rbx; pszDest
0x140aece86  call    RtlStringCchCopyW
0x140aece8b  test    eax, eax
0x140aece8d  js      loc_140AECF51
0x140aece93  lea     r8, [rsp+4A8h+var_258]; pszSrc
0x140aece9b  mov     edx, r11d; cchDest
0x140aece9e  mov     rcx, rbx; pszDest
0x140aecea1  call    RtlStringCchCatW
0x140aecea6  test    eax, eax
0x140aecea8  js      loc_140AECF51
0x140aeceae  jmp     short loc_140AECF02
0x140aeceb0  mov     edx, 4
0x140aeceb5  call    AslAlloc
0x140aeceba  mov     ebp, 2
0x140aecebf  mov     rsi, rax
0x140aecec2  mov     edx, ebp
0x140aecec4  call    AslAlloc
0x140aecec9  mov     edx, ebp
0x140aececb  mov     rbx, rax
0x140aecece  call    AslAlloc
0x140aeced3  mov     r14, rax
0x140aeced6  test    rsi, rsi
0x140aeced9  jz      short loc_140AECF2E
0x140aecedb  test    rbx, rbx
0x140aecede  jz      short loc_140AECF2E
0x140aecee0  test    rax, rax
0x140aecee3  jz      short loc_140AECF2E
0x140aecee5  lea     r8, asc_14003D9AC; "."
0x140aeceec  mov     edx, ebp; cchDest
0x140aeceee  mov     rcx, rsi; pszDest
0x140aecef1  call    RtlStringCchCopyW
0x140aecef6  mov     [rbx], r13w
0x140aecefa  mov     [r14], r13w
0x140aecefe  mov     [rdi+18h], r14
0x140aecf02  mov     [rdi+8], r15
0x140aecf06  mov     r12d, 1
0x140aecf0c  mov     [rdi+38h], r13
0x140aecf10  mov     [rdi+20h], rsi
0x140aecf14  mov     [rdi+28h], rbx
0x140aecf18  mov     [rdi+30h], r13
0x140aecf1c  mov     [rdi+48h], r13
0x140aecf20  mov     [rdi+40h], r13
0x140aecf24  mov     [rdi+58h], r13
0x140aecf28  mov     [rdi+60h], r13
0x140aecf2c  jmp     short loc_140AECF66
0x140aecf2e  lea     r9, aUnableToAlloca_0; "Unable to allocate memory"
0x140aecf35  mov     r8d, 1D5h
0x140aecf3b  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140aecf42  mov     ecx, 1
0x140aecf47  call    AslLogCallPrintf
0x140aecf4c  test    rsi, rsi
0x140aecf4f  jz      short loc_140AECF59
0x140aecf51  mov     rdx, rsi
0x140aecf54  call    AslFree
0x140aecf59  test    rbx, rbx
0x140aecf5c  jz      short loc_140AECF66
0x140aecf5e  mov     rdx, rbx
0x140aecf61  call    AslFree
0x140aecf66  mov     eax, r12d
0x140aecf69  mov     rcx, [rsp+4A8h+var_48]
0x140aecf71  xor     rcx, rsp; StackCookie
0x140aecf74  call    __security_check_cookie
0x140aecf79  mov     rbx, [rsp+4A8h+arg_10]
0x140aecf81  add     rsp, 470h
0x140aecf88  pop     r15
0x140aecf8a  pop     r14
0x140aecf8c  pop     r13
0x140aecf8e  pop     r12
0x140aecf90  pop     rdi
0x140aecf91  pop     rsi
0x140aecf92  pop     rbp
0x140aecf93  retn
```
