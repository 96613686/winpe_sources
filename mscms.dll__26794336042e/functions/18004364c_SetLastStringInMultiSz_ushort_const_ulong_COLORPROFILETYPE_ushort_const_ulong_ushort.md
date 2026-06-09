# SetLastStringInMultiSz(ushort const *,ulong,COLORPROFILETYPE,ushort const *,ulong *,ushort *)

- ea: `0x18004364c`
- end: `0x1800437d7`
- name: `?SetLastStringInMultiSz@@YAHPEBGKW4COLORPROFILETYPE@@0PEAKPEAG@Z`
- size: `395`
- prototype: `__int64 __usercall@<rax>(PCNZWCH lpString1@<rcx>, unsigned int@<edx>, enum COLORPROFILETYPE@<r8d>, const unsigned __int16 *@<r9>, unsigned int *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180042ccc`

## callees

- `0x18001fcb4`
- `0x18002f2dc`
- `0x180040ea4`
- `0x180041888`
- `0x180042458`
- `0x18004364c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800437c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800437c0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800436fd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800436fd`

## pseudocode

```c
_BOOL8 __fastcall SetLastStringInMultiSz(
        PCNZWCH lpString1,
        unsigned int a2,
        enum COLORPROFILETYPE a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        unsigned __int16 *a6)
{
  __int64 v6; // rbx
  __int64 cchCount2; // rdi
  __int64 v10; // rbp
  __int64 v12; // rbx
  unsigned int v13; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v14; // [rsp+34h] [rbp-44h] BYREF
  PCNZWCH lpString1a; // [rsp+38h] [rbp-40h] BYREF

  v6 = a2;
  v13 = 0;
  lpString1a = 0;
  v14 = 0;
  if ( !a6 )
    goto LABEL_17;
  if ( !a4 )
    goto LABEL_17;
  if ( a2 > 0x800 )
    goto LABEL_17;
  cchCount2 = -1;
  do
    ++cchCount2;
  while ( a4[cchCount2] );
  v10 = (unsigned int)(cchCount2 + 1);
  if ( !(_DWORD)cchCount2 || (unsigned int)v10 > 0x104 )
  {
LABEL_17:
    SetLastError(0x57u);
    return 0;
  }
  if ( (unsigned int)GetLastStringInMultiSz(lpString1, a2, a3, &v13, &lpString1a) )
  {
    if ( CompareStringW(0x7Fu, 1u, lpString1a, v13 - 1, a4, cchCount2) == 2 )
    {
      *a5 = v6;
      memcpy_0(a6, lpString1, 2 * v6);
      return 1;
    }
    if ( !(unsigned int)IsStringInMultiSz(lpString1, v6, a4) )
    {
      v12 = (unsigned int)(v6 - 1);
LABEL_15:
      if ( (unsigned int)(v10 + v12 + 1) <= 0x800 )
      {
        memcpy_0(&a6[v12], a4, 2 * v10);
        a6[v12 + v10] = 0;
        return (unsigned int)GetMultiSzStringSize(a6, 0x800u, a5) != 0;
      }
      goto LABEL_17;
    }
    memcpy_0(a6, lpString1, 2 * v6);
    if ( RemoveStringFromMultiSz(a6, v6, a4, &v14) )
    {
      v12 = v14 - 1;
      goto LABEL_15;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18004364c  push    rbx
0x18004364e  push    rbp
0x18004364f  push    rsi
0x180043650  push    rdi
0x180043651  push    r12
0x180043653  push    r14
0x180043655  push    r15
0x180043657  sub     rsp, 40h
0x18004365b  mov     r14, [rsp+78h+arg_28]
0x180043663  xor     r12d, r12d
0x180043666  mov     ebx, edx
0x180043668  mov     rsi, r9
0x18004366b  mov     [rsp+78h+var_48], r12d
0x180043670  mov     r15, rcx
0x180043673  mov     [rsp+78h+lpString1], r12
0x180043678  mov     [rsp+78h+var_44], r12d
0x18004367d  test    r14, r14
0x180043680  jz      loc_1800437BB
0x180043686  test    r9, r9
0x180043689  jz      loc_1800437BB
0x18004368f  cmp     ebx, 800h
0x180043695  ja      loc_1800437BB
0x18004369b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004369f  inc     rdi
0x1800436a2  cmp     [r9+rdi*2], r12w
0x1800436a7  jnz     short loc_18004369F
0x1800436a9  lea     ebp, [rdi+1]
0x1800436ac  cmp     ebp, 1
0x1800436af  jz      loc_1800437BB
0x1800436b5  cmp     ebp, 104h
0x1800436bb  ja      loc_1800437BB
0x1800436c1  lea     rax, [rsp+78h+lpString1]
0x1800436c6  mov     edx, ebx; unsigned int
0x1800436c8  lea     r9, [rsp+78h+var_48]; unsigned int *
0x1800436cd  mov     [rsp+78h+lpString2], rax; unsigned __int16 **
0x1800436d2  call    ?GetLastStringInMultiSz@@YAHPEBGKW4COLORPROFILETYPE@@PEAKPEAPEBG@Z; GetLastStringInMultiSz(ushort const *,ulong,COLORPROFILETYPE,ulong *,ushort const * *)
0x1800436d7  test    eax, eax
0x1800436d9  jz      loc_1800437C6
0x1800436df  mov     r9d, [rsp+78h+var_48]
0x1800436e4  mov     edx, 1; dwCmpFlags
0x1800436e9  mov     r8, [rsp+78h+lpString1]; lpString1
0x1800436ee  dec     r9d; cchCount1
0x1800436f1  mov     [rsp+78h+cchCount2], edi; cchCount2
0x1800436f5  mov     [rsp+78h+lpString2], rsi; lpString2
0x1800436fa  lea     ecx, [rdx+7Eh]; Locale
0x1800436fd  call    cs:__imp_CompareStringW
0x180043703  cmp     eax, 2
0x180043706  jnz     short loc_18004372D
0x180043708  mov     rdx, [rsp+78h+arg_20]
0x180043710  mov     r8, rbx
0x180043713  add     r8, r8; Size
0x180043716  mov     rcx, r14; void *
0x180043719  mov     [rdx], ebx
0x18004371b  mov     rdx, r15; Src
0x18004371e  call    memcpy_0
0x180043723  mov     eax, 1
0x180043728  jmp     loc_1800437C8
0x18004372d  mov     r8, rsi; unsigned __int16 *
0x180043730  mov     edx, ebx; unsigned int
0x180043732  mov     rcx, r15; lpString1
0x180043735  call    ?IsStringInMultiSz@@YAHPEBGK0@Z; IsStringInMultiSz(ushort const *,ulong,ushort const *)
0x18004373a  test    eax, eax
0x18004373c  jz      short loc_18004376D
0x18004373e  mov     r8, rbx
0x180043741  mov     rdx, r15; Src
0x180043744  add     r8, r8; Size
0x180043747  mov     rcx, r14; void *
0x18004374a  call    memcpy_0
0x18004374f  lea     r9, [rsp+78h+var_44]; unsigned int *
0x180043754  mov     r8, rsi; unsigned __int16 *
0x180043757  mov     edx, ebx; unsigned int
0x180043759  mov     rcx, r14; unsigned __int16 *
0x18004375c  call    ?RemoveStringFromMultiSz@@YAHPEAGKPEBGPEAK@Z; RemoveStringFromMultiSz(ushort *,ulong,ushort const *,ulong *)
0x180043761  test    eax, eax
0x180043763  jz      short loc_1800437C6
0x180043765  mov     ebx, [rsp+78h+var_44]
0x180043769  dec     ebx
0x18004376b  jmp     short loc_18004376F
0x18004376d  dec     ebx
0x18004376f  lea     eax, [rbx+1]
0x180043772  mov     r15d, 800h
0x180043778  add     eax, ebp
0x18004377a  cmp     eax, r15d
0x18004377d  ja      short loc_1800437BB
0x18004377f  lea     r8, ds:0[rbp*2]; Size
0x180043787  mov     rdx, rsi; Src
0x18004378a  lea     rcx, [r14+rbx*2]; void *
0x18004378e  call    memcpy_0
0x180043793  mov     r8, [rsp+78h+arg_20]; unsigned int *
0x18004379b  lea     rcx, [rbx+rbp]
0x18004379f  mov     [r14+rcx*2], r12w
0x1800437a4  mov     edx, r15d; unsigned int
0x1800437a7  mov     rcx, r14; unsigned __int16 *
0x1800437aa  call    ?GetMultiSzStringSize@@YAHPEBGKPEAK@Z; GetMultiSzStringSize(ushort const *,ulong,ulong *)
0x1800437af  test    eax, eax
0x1800437b1  mov     ecx, r12d
0x1800437b4  setnz   cl
0x1800437b7  mov     eax, ecx
0x1800437b9  jmp     short loc_1800437C8
0x1800437bb  mov     ecx, 57h ; 'W'; dwErrCode
0x1800437c0  call    cs:__imp_SetLastError
0x1800437c6  xor     eax, eax
0x1800437c8  add     rsp, 40h
0x1800437cc  pop     r15
0x1800437ce  pop     r14
0x1800437d0  pop     r12
0x1800437d2  pop     rdi
0x1800437d3  pop     rsi
0x1800437d4  pop     rbp
0x1800437d5  pop     rbx
0x1800437d6  retn
```
