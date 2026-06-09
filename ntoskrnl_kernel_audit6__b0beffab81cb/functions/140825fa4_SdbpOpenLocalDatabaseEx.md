# SdbpOpenLocalDatabaseEx

- ea: `0x140825fa4`
- end: `0x1408261ee`
- name: `SdbpOpenLocalDatabaseEx`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140825a5c`

## callees

- `0x1406dc8c0`
- `0x140821914`
- `0x140821c40`
- `0x1408243cc`
- `0x140825ed0`
- `0x140825fa4`
- `0x1408262ec`
- `0x1408c2f88`

## string_xrefs

- `0x1408260a6`: `SdbpOpenLocalDatabaseEx`
- `0x1408261b4`: `SdbpOpenLocalDatabaseEx`
- `0x14082610b`: `Custom database has invalid path %S`
- `0x14082612c`: `Failed to open database`
- `0x1408261a4`: `Cannot resolve database, the path length is 0x%lx`

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
  int v14; // ecx
  const char *v15; // r9
  int v16; // r8d
  int FileTimestamp; // eax
  _QWORD *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  __int128 v21; // xmm0
  __int64 v23; // [rsp+20h] [rbp-E0h]
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v26; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v27; // [rsp+40h] [rbp-C0h]
  wchar_t v28[264]; // [rsp+50h] [rbp-B0h] BYREF

  v27 = 0;
  v8 = *a5;
  v9 = 0;
  v10 = *a5;
  LODWORD(v26) = 0;
  v11 = v10 >> 28;
  v24 = 0;
  v25 = 0;
  if ( (v8 & 0xF0000000) == 0 )
    v11 = v8;
  if ( (_DWORD)v11 != 1 && (unsigned int)(v11 - 3) > 0xC )
  {
    LODWORD(v23) = v11;
    v12 = "Bad index 0x%lx";
    v13 = 1123;
LABEL_28:
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenLocalDatabaseEx", v13, (_DWORD)v12, v23);
    return v9;
  }
  SdbpCloseLocalDatabaseEx(a1, 0, (unsigned int)v11);
  v14 = SdbResolveDatabaseEx(a1, (_DWORD)a2, (unsigned int)&v26, (unsigned int)&v24, (__int64)v28);
  if ( (unsigned int)(v14 - 1) > 0x102 )
  {
    LODWORD(v23) = v14;
    v12 = "Cannot resolve database, the path length is 0x%lx";
    v13 = 1157;
    goto LABEL_28;
  }
  if ( *(_WORD *)(a1 + 584) != 0x7FFF )
  {
    if ( !(unsigned int)SdbpCheckRuntimePlatformImpl(&v25, 0, *(unsigned int *)(a1 + 552), v24) )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpOpenLocalDatabaseEx",
        1174,
        (unsigned int)"Cannot check database runtime platform against current process");
      return v9;
    }
    if ( !v25 )
    {
      v15 = "Database \"%ws\" is not of the same type as the main EXE";
      v16 = 1178;
LABEL_13:
      AslLogCallPrintf(3, (unsigned int)"SdbpOpenLocalDatabaseEx", v16, (_DWORD)v15, v28);
      return v9;
    }
  }
  v26 = 0;
  FileTimestamp = SdbpGetFileTimestamp(&v26, v28, 0);
  if ( FileTimestamp < 0 && FileTimestamp != -1073741790 && FileTimestamp != -1073741757 )
  {
    v15 = "Custom database has invalid path %S";
    v16 = 1196;
    goto LABEL_13;
  }
  v18 = SdbOpenDatabaseEx(v28);
  if ( v18 )
  {
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
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"SdbpOpenLocalDatabaseEx", 1202, (unsigned int)"Failed to open database");
  }
  return v9;
}

```

## disassembly

```asm
0x140825fa4  mov     [rsp-8+arg_10], rbx
0x140825fa9  push    rbp
0x140825faa  push    rsi
0x140825fab  push    rdi
0x140825fac  push    r12
0x140825fae  push    r13
0x140825fb0  push    r14
0x140825fb2  push    r15
0x140825fb4  lea     rbp, [rsp-170h]
0x140825fbc  sub     rsp, 270h
0x140825fc3  mov     rax, cs:__security_cookie
0x140825fca  xor     rax, rsp
0x140825fcd  mov     [rbp+1A0h+var_40], rax
0x140825fd4  mov     r12, [rbp+1A0h+arg_20]
0x140825fdb  mov     rbx, rcx
0x140825fde  mov     r15, rdx
0x140825fe1  xorps   xmm0, xmm0
0x140825fe4  xor     edx, edx
0x140825fe6  mov     rsi, r9
0x140825fe9  movups  [rsp+2A0h+var_260], xmm0
0x140825fee  mov     ecx, [r12]
0x140825ff2  mov     r14d, edx
0x140825ff5  mov     edi, ecx
0x140825ff7  mov     dword ptr [rsp+2A0h+var_268], edx
0x140825ffb  shr     edi, 1Ch
0x140825ffe  lea     r13d, [rdx+1]
0x140826002  test    ecx, 0F0000000h
0x140826008  mov     [rsp+2A0h+var_270], edx
0x14082600c  mov     [rsp+2A0h+var_26C], edx
0x140826010  cmovz   edi, ecx
0x140826013  cmp     edi, r13d
0x140826016  jz      short loc_140826036
0x140826018  lea     eax, [rdi-3]
0x14082601b  cmp     eax, 0Ch
0x14082601e  jbe     short loc_140826036
0x140826020  mov     dword ptr [rsp+2A0h+var_280], edi
0x140826024  lea     r9, aBadIndex0xLx; "Bad index 0x%lx"
0x14082602b  mov     r8d, 463h
0x140826031  jmp     loc_1408261B1
0x140826036  mov     r8d, edi
0x140826039  mov     rcx, rbx
0x14082603c  call    SdbpCloseLocalDatabaseEx
0x140826041  lea     rax, [rsp+2A0h+var_250]
0x140826046  mov     rdx, r15
0x140826049  lea     r9, [rsp+2A0h+var_270]
0x14082604e  mov     [rsp+2A0h+var_280], rax
0x140826053  lea     r8, [rsp+2A0h+var_268]
0x140826058  mov     rcx, rbx
0x14082605b  call    SdbResolveDatabaseEx
0x140826060  mov     ecx, eax
0x140826062  dec     eax
0x140826064  cmp     eax, 102h
0x140826069  ja      loc_1408261A0
0x14082606f  mov     eax, 7FFFh
0x140826074  cmp     [rbx+248h], ax
0x14082607b  jz      short loc_1408260E2
0x14082607d  mov     r9d, [rsp+2A0h+var_270]
0x140826082  lea     rcx, [rsp+2A0h+var_26C]
0x140826087  mov     r8d, [rbx+228h]
0x14082608e  xor     edx, edx
0x140826090  call    SdbpCheckRuntimePlatformImpl
0x140826095  test    eax, eax
0x140826097  jnz     short loc_1408260BA
0x140826099  lea     r9, aCannotCheckDat; "Cannot check database runtime platform "...
0x1408260a0  mov     r8d, 496h
0x1408260a6  lea     rdx, aSdbpopenlocald; "SdbpOpenLocalDatabaseEx"
0x1408260ad  mov     ecx, r13d
0x1408260b0  call    AslLogCallPrintf
0x1408260b5  jmp     loc_1408261C0
0x1408260ba  cmp     [rsp+2A0h+var_26C], r14d
0x1408260bf  jnz     short loc_1408260E2
0x1408260c1  lea     r9, aDatabaseWsIsNo; "Database \"%ws\" is not of the same typ"...
0x1408260c8  mov     r8d, 49Ah
0x1408260ce  lea     rax, [rsp+2A0h+var_250]
0x1408260d3  mov     ecx, 3
0x1408260d8  mov     [rsp+2A0h+var_280], rax
0x1408260dd  jmp     loc_1408261B4
0x1408260e2  xor     r8d, r8d
0x1408260e5  mov     [rsp+2A0h+var_268], r14
0x1408260ea  lea     rdx, [rsp+2A0h+var_250]
0x1408260ef  lea     rcx, [rsp+2A0h+var_268]
0x1408260f4  call    SdbpGetFileTimestamp
0x1408260f9  test    eax, eax
0x1408260fb  jns     short loc_14082611A
0x1408260fd  cmp     eax, 0C0000022h
0x140826102  jz      short loc_14082611A
0x140826104  cmp     eax, 0C0000043h
0x140826109  jz      short loc_14082611A
0x14082610b  lea     r9, aCustomDatabase; "Custom database has invalid path %S"
0x140826112  mov     r8d, 4ACh
0x140826118  jmp     short loc_1408260CE
0x14082611a  lea     rcx, [rsp+2A0h+var_250]
0x14082611f  call    SdbOpenDatabaseEx
0x140826124  mov     rdx, rax
0x140826127  test    rax, rax
0x14082612a  jnz     short loc_14082613E
0x14082612c  lea     r9, aFailedToOpenDa; "Failed to open database"
0x140826133  mov     r8d, 4B2h
0x140826139  jmp     loc_1408260A6
0x14082613e  mov     r8d, edi
0x140826141  lea     r9, [rdi+2]
0x140826145  shl     r8, 5
0x140826149  mov     ecx, edi
0x14082614b  shl     r9, 5
0x14082614f  mov     eax, r13d
0x140826152  shl     eax, cl
0x140826154  mov     [r8+rbx+38h], rdx
0x140826159  mov     dword ptr [r9+rbx], 2
0x140826161  or      [rbx+24h], eax
0x140826164  test    r15, r15
0x140826167  jz      short loc_14082617A
0x140826169  movups  xmm0, xmmword ptr [r15]
0x14082616d  or      [r9+rbx], r13d
0x140826171  movdqu  xmmword ptr [r8+rbx+28h], xmm0
0x140826178  jmp     short loc_140826183
0x14082617a  xorps   xmm0, xmm0
0x14082617d  movups  xmmword ptr [r8+rbx+28h], xmm0
0x140826183  mov     r14d, r13d
0x140826186  cmp     edi, r13d
0x140826189  jnz     short loc_14082618F
0x14082618b  mov     [rbx+18h], rdx
0x14082618f  shl     edi, 1Ch
0x140826192  mov     [r12], edi
0x140826196  test    rsi, rsi
0x140826199  jz      short loc_1408261C0
0x14082619b  mov     [rsi], rdx
0x14082619e  jmp     short loc_1408261C0
0x1408261a0  mov     dword ptr [rsp+2A0h+var_280], ecx
0x1408261a4  lea     r9, aCannotResolveD; "Cannot resolve database, the path lengt"...
0x1408261ab  mov     r8d, 485h
0x1408261b1  mov     ecx, r13d
0x1408261b4  lea     rdx, aSdbpopenlocald; "SdbpOpenLocalDatabaseEx"
0x1408261bb  call    AslLogCallPrintf
0x1408261c0  mov     eax, r14d
0x1408261c3  mov     rcx, [rbp+1A0h+var_40]
0x1408261ca  xor     rcx, rsp; StackCookie
0x1408261cd  call    __security_check_cookie
0x1408261d2  mov     rbx, [rsp+2A0h+arg_10]
0x1408261da  add     rsp, 270h
0x1408261e1  pop     r15
0x1408261e3  pop     r14
0x1408261e5  pop     r13
0x1408261e7  pop     r12
0x1408261e9  pop     rdi
0x1408261ea  pop     rsi
0x1408261eb  pop     rbp
0x1408261ec  retn
```
