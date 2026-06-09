# SdbReadEntryInformation

- ea: `0x140822efc`
- end: `0x140823094`
- name: `SdbReadEntryInformation`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1408be19c`

## callees

- `0x1406dc8c0`
- `0x140822efc`
- `0x140825a5c`
- `0x1408be77c`
- `0x1408be86c`
- `0x1408c2c64`
- `0x1408c2f88`
- `0x140ae90d4`

## string_xrefs

- `0x140822f9c`: `Failed to read TAG_EXE_ID for tiExe 0x%x`
- `0x140822f66`: `SdbReadEntryInformation`
- `0x140822fae`: `SdbReadEntryInformation`
- `0x140823013`: `SdbReadEntryInformation`
- `0x140823006`: `Failed to read GUID of the database`
- `0x140822fe4`: `Failed to read GUID referenced by 0x%x`

## pseudocode

```c
__int64 __fastcall SdbReadEntryInformation(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  const char *v5; // r9
  int v6; // r8d
  __int64 v7; // rsi
  unsigned int v8; // r15d
  unsigned int FirstTag; // eax
  int EntryFlags; // eax
  __int128 v11; // xmm1
  __int64 v12; // xmm0_8
  unsigned int v14; // [rsp+30h] [rbp-40h] BYREF
  __int64 v15; // [rsp+38h] [rbp-38h] BYREF
  __int128 v16; // [rsp+40h] [rbp-30h] BYREF
  __int128 v17; // [rsp+50h] [rbp-20h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h]

  v14 = 0;
  v15 = 0;
  v18 = 0;
  v16 = 0;
  v17 = 0;
  v4 = SdbTagRefToTagID(a1, a2, &v15, &v14);
  if ( !v4 )
  {
    v5 = "Failed to convert tagref 0x%x to tagid";
    v6 = 7673;
LABEL_3:
    AslLogCallPrintf(1, (unsigned int)"SdbReadEntryInformation", v6, (_DWORD)v5);
    return v4;
  }
  v7 = v15;
  v8 = v14;
  FirstTag = SdbFindFirstTag(v15, v14, 36868);
  if ( !FirstTag )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbReadEntryInformation",
      7683,
      (unsigned int)"Failed to read TAG_EXE_ID for tiExe 0x%x");
    return 0;
  }
  v4 = SdbReadBinaryTag(v7, FirstTag, &v16, 16);
  if ( !v4 )
  {
    v5 = "Failed to read GUID referenced by 0x%x";
    v6 = 7693;
    goto LABEL_3;
  }
  if ( !(unsigned int)SdbGetDatabaseID(v7, (char *)&v17 + 8) )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbReadEntryInformation",
      7701,
      (unsigned int)"Failed to read GUID of the database");
    return 0;
  }
  EntryFlags = SdbGetEntryFlags(&v16, &v17);
  LODWORD(v17) = EntryFlags != 0 ? v17 : 0;
  DWORD1(v17) = SdbFindFirstTag(v7, v8, 28687);
  if ( a3 )
  {
    v11 = v17;
    *(_OWORD *)a3 = v16;
    v12 = v18;
    *(_OWORD *)(a3 + 16) = v11;
    *(_QWORD *)(a3 + 32) = v12;
  }
  return 1;
}

```

## disassembly

```asm
0x140822efc  mov     [rsp-28h+arg_18], rbx
0x140822f01  push    rbp
0x140822f02  push    rsi
0x140822f03  push    rdi
0x140822f04  push    r14
0x140822f06  push    r15
0x140822f08  mov     rbp, rsp
0x140822f0b  sub     rsp, 70h
0x140822f0f  mov     rax, cs:__security_cookie
0x140822f16  xor     rax, rsp
0x140822f19  mov     [rbp+var_8], rax
0x140822f1d  xorps   xmm0, xmm0
0x140822f20  mov     [rbp+var_40], 0
0x140822f27  mov     rdi, r8
0x140822f2a  mov     [rbp+var_38], 0
0x140822f32  xor     eax, eax
0x140822f34  lea     r8, [rbp+var_38]
0x140822f38  lea     r9, [rbp+var_40]
0x140822f3c  mov     [rbp+var_10], rax
0x140822f40  movups  [rbp+var_30], xmm0
0x140822f44  mov     esi, edx
0x140822f46  movups  [rbp+var_20], xmm0
0x140822f4a  call    SdbTagRefToTagID
0x140822f4f  mov     ebx, eax
0x140822f51  test    eax, eax
0x140822f53  jnz     short loc_140822F7C
0x140822f55  mov     [rsp+70h+var_50], esi
0x140822f59  lea     r9, aFailedToConver_1; "Failed to convert tagref 0x%x to tagid"
0x140822f60  mov     r8d, 1DF9h
0x140822f66  lea     rdx, aSdbreadentryin; "SdbReadEntryInformation"
0x140822f6d  mov     ecx, 1
0x140822f72  call    AslLogCallPrintf
0x140822f77  jmp     loc_140823071
0x140822f7c  mov     rsi, [rbp+var_38]
0x140822f80  mov     r8d, 9004h
0x140822f86  mov     r15d, [rbp+var_40]
0x140822f8a  mov     rcx, rsi
0x140822f8d  mov     edx, r15d
0x140822f90  call    SdbFindFirstTag
0x140822f95  mov     r14d, eax
0x140822f98  test    eax, eax
0x140822f9a  jnz     short loc_140822FC4
0x140822f9c  lea     r9, aFailedToReadTa; "Failed to read TAG_EXE_ID for tiExe 0x%"...
0x140822fa3  mov     [rsp+70h+var_50], r15d
0x140822fa8  mov     r8d, 1E03h
0x140822fae  lea     rdx, aSdbreadentryin; "SdbReadEntryInformation"
0x140822fb5  lea     ecx, [rax+1]
0x140822fb8  call    AslLogCallPrintf
0x140822fbd  xor     ebx, ebx
0x140822fbf  jmp     loc_140823071
0x140822fc4  mov     r9d, 10h
0x140822fca  lea     r8, [rbp+var_30]
0x140822fce  mov     edx, r14d
0x140822fd1  mov     rcx, rsi
0x140822fd4  call    SdbReadBinaryTag
0x140822fd9  mov     ebx, eax
0x140822fdb  test    eax, eax
0x140822fdd  jnz     short loc_140822FF6
0x140822fdf  mov     [rsp+70h+var_50], r14d
0x140822fe4  lea     r9, aFailedToReadGu_0; "Failed to read GUID referenced by 0x%x"
0x140822feb  mov     r8d, 1E0Dh
0x140822ff1  jmp     loc_140822F66
0x140822ff6  lea     rdx, [rbp+var_20+8]
0x140822ffa  mov     rcx, rsi
0x140822ffd  call    SdbGetDatabaseID
0x140823002  test    eax, eax
0x140823004  jnz     short loc_140823024
0x140823006  lea     r9, aFailedToReadGu_1; "Failed to read GUID of the database"
0x14082300d  mov     r8d, 1E15h
0x140823013  lea     rdx, aSdbreadentryin; "SdbReadEntryInformation"
0x14082301a  lea     ecx, [rax+1]
0x14082301d  call    AslLogCallPrintf
0x140823022  jmp     short loc_140822FBD
0x140823024  lea     rdx, [rbp+var_20]
0x140823028  lea     rcx, [rbp+var_30]
0x14082302c  call    SdbGetEntryFlags
0x140823031  neg     eax
0x140823033  mov     edx, r15d
0x140823036  mov     rcx, rsi
0x140823039  sbb     r8d, r8d
0x14082303c  and     dword ptr [rbp+var_20], r8d
0x140823040  mov     r8d, 700Fh
0x140823046  call    SdbFindFirstTag
0x14082304b  mov     dword ptr [rbp+var_20+4], eax
0x14082304e  test    rdi, rdi
0x140823051  jz      short loc_14082306C
0x140823053  movups  xmm0, [rbp+var_30]
0x140823057  movups  xmm1, [rbp+var_20]
0x14082305b  movups  xmmword ptr [rdi], xmm0
0x14082305e  movsd   xmm0, [rbp+var_10]
0x140823063  movups  xmmword ptr [rdi+10h], xmm1
0x140823067  movsd   qword ptr [rdi+20h], xmm0
0x14082306c  mov     ebx, 1
0x140823071  mov     eax, ebx
0x140823073  mov     rcx, [rbp+var_8]
0x140823077  xor     rcx, rsp; StackCookie
0x14082307a  call    __security_check_cookie
0x14082307f  mov     rbx, [rsp+70h+arg_18]
0x140823087  add     rsp, 70h
0x14082308b  pop     r15
0x14082308d  pop     r14
0x14082308f  pop     rdi
0x140823090  pop     rsi
0x140823091  pop     rbp
0x140823092  retn
```
