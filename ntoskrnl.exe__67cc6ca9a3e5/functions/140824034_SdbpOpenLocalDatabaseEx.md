# SdbpOpenLocalDatabaseEx

- ea: `0x140824034`
- end: `0x14082427e`
- name: `SdbpOpenLocalDatabaseEx`
- size: `586`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64, _QWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140823aec`

## callees

- `0x1406d9d70`
- `0x14081f9a4`
- `0x14081fcd0`
- `0x14082245c`
- `0x140823f60`
- `0x140824034`
- `0x14082437c`
- `0x14097d158`

## string_xrefs

- `0x140824234`: `Cannot resolve database, the path length is 0x%lx`
- `0x140824136`: `SdbpOpenLocalDatabaseEx`
- `0x140824244`: `SdbpOpenLocalDatabaseEx`
- `0x1408241bc`: `Failed to open database`
- `0x14082419b`: `Custom database has invalid path %S`

## pseudocode

```c
__int64 __fastcall SdbpOpenLocalDatabaseEx(__int64 a1, __int128 *a2, __int64 a3, _QWORD *a4, unsigned int *a5)
{
  unsigned int v8; // ecx
  unsigned int v9; // r14d
  unsigned int v10; // edi
  __int64 v11; // rdi
  const char *v12; // r9
  int v13; // r8d
  const char *v14; // r9
  int v15; // r8d
  int v16; // ecx
  int FileTimestamp; // eax
  _QWORD *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int128 v21; // xmm0
  unsigned int v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v26; // [rsp+40h] [rbp-C0h]
  wchar_t v27[264]; // [rsp+50h] [rbp-B0h] BYREF

  v26 = 0;
  v8 = *a5;
  v9 = 0;
  v10 = *a5;
  LODWORD(v25) = 0;
  v11 = v10 >> 28;
  v23 = 0;
  v24 = 0;
  if ( (v8 & 0xF0000000) == 0 )
    v11 = v8;
  if ( (_DWORD)v11 != 1 && (unsigned int)(v11 - 3) > 0xC )
  {
    v12 = "Bad index 0x%lx";
    v13 = 1123;
LABEL_28:
    v16 = 1;
    goto LABEL_29;
  }
  SdbpCloseLocalDatabaseEx(a1, 0, (unsigned int)v11);
  if ( (unsigned int)SdbResolveDatabaseEx(a1, (_DWORD)a2, (unsigned int)&v25, (unsigned int)&v23, (__int64)v27) - 1 > 0x102 )
  {
    v12 = "Cannot resolve database, the path length is 0x%lx";
    v13 = 1157;
    goto LABEL_28;
  }
  if ( *(_WORD *)(a1 + 584) != 0x7FFF )
  {
    if ( !(unsigned int)SdbpCheckRuntimePlatformImpl(&v24, 0, *(unsigned int *)(a1 + 552), v23) )
    {
      v14 = "Cannot check database runtime platform against current process";
      v15 = 1174;
LABEL_10:
      AslLogCallPrintf(1, (unsigned int)"SdbpOpenLocalDatabaseEx", v15, (_DWORD)v14);
      return v9;
    }
    if ( !v24 )
    {
      v12 = "Database \"%ws\" is not of the same type as the main EXE";
      v13 = 1178;
LABEL_13:
      v16 = 3;
LABEL_29:
      AslLogCallPrintf(v16, (unsigned int)"SdbpOpenLocalDatabaseEx", v13, (_DWORD)v12);
      return v9;
    }
  }
  v25 = 0;
  FileTimestamp = SdbpGetFileTimestamp(&v25, v27, 0);
  if ( FileTimestamp < 0 && FileTimestamp != -1073741790 && FileTimestamp != -1073741757 )
  {
    v12 = "Custom database has invalid path %S";
    v13 = 1196;
    goto LABEL_13;
  }
  v18 = SdbOpenDatabaseEx(v27);
  if ( !v18 )
  {
    v14 = "Failed to open database";
    v15 = 1202;
    goto LABEL_10;
  }
  v19 = 32LL * (unsigned int)v11;
  v20 = 32 * (v11 + 2);
  *(_QWORD *)(v19 + a1 + 56) = v18;
  *(_DWORD *)(v20 + a1) = 2;
  *(_DWORD *)(a1 + 36) |= 1 << v11;
  if ( a2 )
  {
    v21 = *a2;
    *(_DWORD *)(v20 + a1) |= 1u;
    *(_OWORD *)(v19 + a1 + 40) = v21;
  }
  else
  {
    *(_OWORD *)(v19 + a1 + 40) = 0;
  }
  v9 = 1;
  if ( (_DWORD)v11 == 1 )
    *(_QWORD *)(a1 + 24) = v18;
  *a5 = (_DWORD)v11 << 28;
  if ( a4 )
    *a4 = v18;
  return v9;
}

```

## disassembly

```asm
0x140824034  mov     [rsp-8+arg_10], rbx
0x140824039  push    rbp
0x14082403a  push    rsi
0x14082403b  push    rdi
0x14082403c  push    r12
0x14082403e  push    r13
0x140824040  push    r14
0x140824042  push    r15
0x140824044  lea     rbp, [rsp-170h]
0x14082404c  sub     rsp, 270h
0x140824053  mov     rax, cs:__security_cookie
0x14082405a  xor     rax, rsp
0x14082405d  mov     [rbp+1A0h+var_40], rax
0x140824064  mov     r12, [rbp+1A0h+arg_20]
0x14082406b  mov     rbx, rcx
0x14082406e  mov     r15, rdx
0x140824071  xorps   xmm0, xmm0
0x140824074  xor     edx, edx
0x140824076  mov     rsi, r9
0x140824079  movups  [rsp+2A0h+var_260], xmm0
0x14082407e  mov     ecx, [r12]
0x140824082  mov     r14d, edx
0x140824085  mov     edi, ecx
0x140824087  mov     dword ptr [rsp+2A0h+var_268], edx
0x14082408b  shr     edi, 1Ch
0x14082408e  lea     r13d, [rdx+1]
0x140824092  test    ecx, 0F0000000h
0x140824098  mov     [rsp+2A0h+var_270], edx
0x14082409c  mov     [rsp+2A0h+var_26C], edx
0x1408240a0  cmovz   edi, ecx
0x1408240a3  cmp     edi, r13d
0x1408240a6  jz      short loc_1408240C6
0x1408240a8  lea     eax, [rdi-3]
0x1408240ab  cmp     eax, 0Ch
0x1408240ae  jbe     short loc_1408240C6
0x1408240b0  mov     dword ptr [rsp+2A0h+var_280], edi
0x1408240b4  lea     r9, aBadIndex0xLx; "Bad index 0x%lx"
0x1408240bb  mov     r8d, 463h
0x1408240c1  jmp     loc_140824241
0x1408240c6  mov     r8d, edi
0x1408240c9  mov     rcx, rbx
0x1408240cc  call    SdbpCloseLocalDatabaseEx
0x1408240d1  lea     rax, [rsp+2A0h+var_250]
0x1408240d6  mov     rdx, r15
0x1408240d9  lea     r9, [rsp+2A0h+var_270]
0x1408240de  mov     [rsp+2A0h+var_280], rax
0x1408240e3  lea     r8, [rsp+2A0h+var_268]
0x1408240e8  mov     rcx, rbx
0x1408240eb  call    SdbResolveDatabaseEx
0x1408240f0  mov     ecx, eax
0x1408240f2  dec     eax
0x1408240f4  cmp     eax, 102h
0x1408240f9  ja      loc_140824230
0x1408240ff  mov     eax, 7FFFh
0x140824104  cmp     [rbx+248h], ax
0x14082410b  jz      short loc_140824172
0x14082410d  mov     r9d, [rsp+2A0h+var_270]
0x140824112  lea     rcx, [rsp+2A0h+var_26C]
0x140824117  mov     r8d, [rbx+228h]
0x14082411e  xor     edx, edx
0x140824120  call    SdbpCheckRuntimePlatformImpl
0x140824125  test    eax, eax
0x140824127  jnz     short loc_14082414A
0x140824129  lea     r9, aCannotCheckDat; "Cannot check database runtime platform "...
0x140824130  mov     r8d, 496h
0x140824136  lea     rdx, aSdbpopenlocald; "SdbpOpenLocalDatabaseEx"
0x14082413d  mov     ecx, r13d
0x140824140  call    AslLogCallPrintf
0x140824145  jmp     loc_140824250
0x14082414a  cmp     [rsp+2A0h+var_26C], r14d
0x14082414f  jnz     short loc_140824172
0x140824151  lea     r9, aDatabaseWsIsNo; "Database \"%ws\" is not of the same typ"...
0x140824158  mov     r8d, 49Ah
0x14082415e  lea     rax, [rsp+2A0h+var_250]
0x140824163  mov     ecx, 3
0x140824168  mov     [rsp+2A0h+var_280], rax
0x14082416d  jmp     loc_140824244
0x140824172  xor     r8d, r8d
0x140824175  mov     [rsp+2A0h+var_268], r14
0x14082417a  lea     rdx, [rsp+2A0h+var_250]
0x14082417f  lea     rcx, [rsp+2A0h+var_268]
0x140824184  call    SdbpGetFileTimestamp
0x140824189  test    eax, eax
0x14082418b  jns     short loc_1408241AA
0x14082418d  cmp     eax, 0C0000022h
0x140824192  jz      short loc_1408241AA
0x140824194  cmp     eax, 0C0000043h
0x140824199  jz      short loc_1408241AA
0x14082419b  lea     r9, aCustomDatabase; "Custom database has invalid path %S"
0x1408241a2  mov     r8d, 4ACh
0x1408241a8  jmp     short loc_14082415E
0x1408241aa  lea     rcx, [rsp+2A0h+var_250]
0x1408241af  call    SdbOpenDatabaseEx
0x1408241b4  mov     rdx, rax
0x1408241b7  test    rax, rax
0x1408241ba  jnz     short loc_1408241CE
0x1408241bc  lea     r9, aFailedToOpenDa; "Failed to open database"
0x1408241c3  mov     r8d, 4B2h
0x1408241c9  jmp     loc_140824136
0x1408241ce  mov     r8d, edi
0x1408241d1  lea     r9, [rdi+2]
0x1408241d5  shl     r8, 5
0x1408241d9  mov     ecx, edi
0x1408241db  shl     r9, 5
0x1408241df  mov     eax, r13d
0x1408241e2  shl     eax, cl
0x1408241e4  mov     [r8+rbx+38h], rdx
0x1408241e9  mov     dword ptr [r9+rbx], 2
0x1408241f1  or      [rbx+24h], eax
0x1408241f4  test    r15, r15
0x1408241f7  jz      short loc_14082420A
0x1408241f9  movups  xmm0, xmmword ptr [r15]
0x1408241fd  or      [r9+rbx], r13d
0x140824201  movdqu  xmmword ptr [r8+rbx+28h], xmm0
0x140824208  jmp     short loc_140824213
0x14082420a  xorps   xmm0, xmm0
0x14082420d  movups  xmmword ptr [r8+rbx+28h], xmm0
0x140824213  mov     r14d, r13d
0x140824216  cmp     edi, r13d
0x140824219  jnz     short loc_14082421F
0x14082421b  mov     [rbx+18h], rdx
0x14082421f  shl     edi, 1Ch
0x140824222  mov     [r12], edi
0x140824226  test    rsi, rsi
0x140824229  jz      short loc_140824250
0x14082422b  mov     [rsi], rdx
0x14082422e  jmp     short loc_140824250
0x140824230  mov     dword ptr [rsp+2A0h+var_280], ecx
0x140824234  lea     r9, aCannotResolveD; "Cannot resolve database, the path lengt"...
0x14082423b  mov     r8d, 485h
0x140824241  mov     ecx, r13d
0x140824244  lea     rdx, aSdbpopenlocald; "SdbpOpenLocalDatabaseEx"
0x14082424b  call    AslLogCallPrintf
0x140824250  mov     eax, r14d
0x140824253  mov     rcx, [rbp+1A0h+var_40]
0x14082425a  xor     rcx, rsp; StackCookie
0x14082425d  call    __security_check_cookie
0x140824262  mov     rbx, [rsp+2A0h+arg_10]
0x14082426a  add     rsp, 270h
0x140824271  pop     r15
0x140824273  pop     r14
0x140824275  pop     r13
0x140824277  pop     r12
0x140824279  pop     rdi
0x14082427a  pop     rsi
0x14082427b  pop     rbp
0x14082427c  retn
```
