# SdbReadEntryInformation

- ea: `0x140820f8c`
- end: `0x140821124`
- name: `SdbReadEntryInformation`
- size: `408`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140969024`

## callees

- `0x1406d9d70`
- `0x140820f8c`
- `0x140823aec`
- `0x1409789b4`
- `0x140978aa4`
- `0x14097ce34`
- `0x14097d158`
- `0x140ae3404`

## string_xrefs

- `0x14082102c`: `Failed to read TAG_EXE_ID for tiExe 0x%x`
- `0x140821096`: `Failed to read GUID of the database`
- `0x140821074`: `Failed to read GUID referenced by 0x%x`
- `0x140820ff6`: `SdbReadEntryInformation`
- `0x14082103e`: `SdbReadEntryInformation`
- `0x1408210a3`: `SdbReadEntryInformation`

## pseudocode

```c
__int64 __fastcall SdbReadEntryInformation(__int64 a1, __int64 a2, __int64 a3)
{
  int v4; // esi
  unsigned int v5; // ebx
  __int64 v6; // rsi
  unsigned int v7; // r15d
  unsigned int FirstTag; // eax
  int v9; // r14d
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
  v4 = a2;
  v17 = 0;
  v5 = SdbTagRefToTagID(a1, a2, &v15, &v14);
  if ( !v5 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbReadEntryInformation",
      7673,
      (unsigned int)"Failed to convert tagref 0x%x to tagid",
      v4);
    return v5;
  }
  v6 = v15;
  v7 = v14;
  FirstTag = SdbFindFirstTag(v15, v14, 36868);
  v9 = FirstTag;
  if ( !FirstTag )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbReadEntryInformation",
      7683,
      (unsigned int)"Failed to read TAG_EXE_ID for tiExe 0x%x",
      v7);
    return 0;
  }
  v5 = SdbReadBinaryTag(v6, FirstTag, &v16, 16);
  if ( !v5 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbReadEntryInformation",
      7693,
      (unsigned int)"Failed to read GUID referenced by 0x%x",
      v9);
    return v5;
  }
  if ( !(unsigned int)SdbGetDatabaseID(v6, (char *)&v17 + 8) )
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
  DWORD1(v17) = SdbFindFirstTag(v6, v7, 28687);
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
0x140820f8c  mov     [rsp-28h+arg_18], rbx
0x140820f91  push    rbp
0x140820f92  push    rsi
0x140820f93  push    rdi
0x140820f94  push    r14
0x140820f96  push    r15
0x140820f98  mov     rbp, rsp
0x140820f9b  sub     rsp, 70h
0x140820f9f  mov     rax, cs:__security_cookie
0x140820fa6  xor     rax, rsp
0x140820fa9  mov     [rbp+var_8], rax
0x140820fad  xorps   xmm0, xmm0
0x140820fb0  mov     [rbp+var_40], 0
0x140820fb7  mov     rdi, r8
0x140820fba  mov     [rbp+var_38], 0
0x140820fc2  xor     eax, eax
0x140820fc4  lea     r8, [rbp+var_38]
0x140820fc8  lea     r9, [rbp+var_40]
0x140820fcc  mov     [rbp+var_10], rax
0x140820fd0  movups  [rbp+var_30], xmm0
0x140820fd4  mov     esi, edx
0x140820fd6  movups  [rbp+var_20], xmm0
0x140820fda  call    SdbTagRefToTagID
0x140820fdf  mov     ebx, eax
0x140820fe1  test    eax, eax
0x140820fe3  jnz     short loc_14082100C
0x140820fe5  mov     [rsp+70h+var_50], esi
0x140820fe9  lea     r9, aFailedToConver_1; "Failed to convert tagref 0x%x to tagid"
0x140820ff0  mov     r8d, 1DF9h
0x140820ff6  lea     rdx, aSdbreadentryin; "SdbReadEntryInformation"
0x140820ffd  mov     ecx, 1
0x140821002  call    AslLogCallPrintf
0x140821007  jmp     loc_140821101
0x14082100c  mov     rsi, [rbp+var_38]
0x140821010  mov     r8d, 9004h
0x140821016  mov     r15d, [rbp+var_40]
0x14082101a  mov     rcx, rsi
0x14082101d  mov     edx, r15d
0x140821020  call    SdbFindFirstTag
0x140821025  mov     r14d, eax
0x140821028  test    eax, eax
0x14082102a  jnz     short loc_140821054
0x14082102c  lea     r9, aFailedToReadTa; "Failed to read TAG_EXE_ID for tiExe 0x%"...
0x140821033  mov     [rsp+70h+var_50], r15d
0x140821038  mov     r8d, 1E03h
0x14082103e  lea     rdx, aSdbreadentryin; "SdbReadEntryInformation"
0x140821045  lea     ecx, [rax+1]
0x140821048  call    AslLogCallPrintf
0x14082104d  xor     ebx, ebx
0x14082104f  jmp     loc_140821101
0x140821054  mov     r9d, 10h
0x14082105a  lea     r8, [rbp+var_30]
0x14082105e  mov     edx, r14d
0x140821061  mov     rcx, rsi
0x140821064  call    SdbReadBinaryTag
0x140821069  mov     ebx, eax
0x14082106b  test    eax, eax
0x14082106d  jnz     short loc_140821086
0x14082106f  mov     [rsp+70h+var_50], r14d
0x140821074  lea     r9, aFailedToReadGu_0; "Failed to read GUID referenced by 0x%x"
0x14082107b  mov     r8d, 1E0Dh
0x140821081  jmp     loc_140820FF6
0x140821086  lea     rdx, [rbp+var_20+8]
0x14082108a  mov     rcx, rsi
0x14082108d  call    SdbGetDatabaseID
0x140821092  test    eax, eax
0x140821094  jnz     short loc_1408210B4
0x140821096  lea     r9, aFailedToReadGu_1; "Failed to read GUID of the database"
0x14082109d  mov     r8d, 1E15h
0x1408210a3  lea     rdx, aSdbreadentryin; "SdbReadEntryInformation"
0x1408210aa  lea     ecx, [rax+1]
0x1408210ad  call    AslLogCallPrintf
0x1408210b2  jmp     short loc_14082104D
0x1408210b4  lea     rdx, [rbp+var_20]
0x1408210b8  lea     rcx, [rbp+var_30]
0x1408210bc  call    SdbGetEntryFlags
0x1408210c1  neg     eax
0x1408210c3  mov     edx, r15d
0x1408210c6  mov     rcx, rsi
0x1408210c9  sbb     r8d, r8d
0x1408210cc  and     dword ptr [rbp+var_20], r8d
0x1408210d0  mov     r8d, 700Fh
0x1408210d6  call    SdbFindFirstTag
0x1408210db  mov     dword ptr [rbp+var_20+4], eax
0x1408210de  test    rdi, rdi
0x1408210e1  jz      short loc_1408210FC
0x1408210e3  movups  xmm0, [rbp+var_30]
0x1408210e7  movups  xmm1, [rbp+var_20]
0x1408210eb  movups  xmmword ptr [rdi], xmm0
0x1408210ee  movsd   xmm0, [rbp+var_10]
0x1408210f3  movups  xmmword ptr [rdi+10h], xmm1
0x1408210f7  movsd   qword ptr [rdi+20h], xmm0
0x1408210fc  mov     ebx, 1
0x140821101  mov     eax, ebx
0x140821103  mov     rcx, [rbp+var_8]
0x140821107  xor     rcx, rsp; StackCookie
0x14082110a  call    __security_check_cookie
0x14082110f  mov     rbx, [rsp+70h+arg_18]
0x140821117  add     rsp, 70h
0x14082111b  pop     r15
0x14082111d  pop     r14
0x14082111f  pop     rdi
0x140821120  pop     rsi
0x140821121  pop     rbp
0x140821122  retn
```
