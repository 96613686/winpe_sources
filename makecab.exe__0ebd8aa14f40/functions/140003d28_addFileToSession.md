# addFileToSession

- ea: `0x140003d28`
- end: `0x140003f60`
- name: `addFileToSession`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000488c`

## callees

- `0x140001a24`
- `0x140003d28`
- `0x140008620`
- `0x14000a29c`
- `0x14000a4f8`
- `0x14000a670`
- `0x14000dfd8`

## import_xrefs

- `msvcrt!atoi` at `0x140003d5a`
- `msvcrt!atoi` at `0x140003d5a`
- `msvcrt!malloc` at `0x140003e01`
- `msvcrt!malloc` at `0x140003e01`
- `msvcrt!free` at `0x140003e64`
- `msvcrt!free` at `0x140003ee5`
- `msvcrt!free` at `0x140003e64`
- `msvcrt!free` at `0x140003ee5`
- `msvcrt!_strdup` at `0x140003e35`
- `msvcrt!_strdup` at `0x140003e35`

## string_xrefs

- `0x140003ebe`: `Duplicate file name: %1 already defined at %2(%3)`

## pseudocode

```c
__int64 __fastcall addFileToSession(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5, __int64 a6)
{
  __int64 v8; // rax
  int v9; // ebp
  const char *v10; // r8
  _QWORD *v11; // rbx
  __int64 Item; // rax
  char **v13; // rcx
  __int64 result; // rax
  __int64 v15; // rax
  _DWORD *v16; // rbx
  char *v17; // rax

  v8 = VarFind(*(_QWORD *)(a1 + 16), "UniqueFiles", a6);
  v9 = atoi(*(const char **)(v8 + 8));
  v11 = *(_QWORD **)(a5 + 4360);
  if ( v11 )
  {
    Item = findItem(*v11, "Unique");
    v13 = Item ? *(char ***)(Item + 8) : (char **)v11[2];
    if ( v13 )
    {
      v9 = BOOLfromPSZ(*v13);
      if ( v9 == -1 )
        return 0;
    }
  }
  if ( *(_DWORD *)(a1 + 192) == 3 && !v9 )
  {
    ErrSet(a6, "/unique=OFF not allowed for relational INF generation", v10);
    return 0;
  }
  if ( !*(_QWORD *)(a1 + 168) )
  {
    v15 = GLCreateList(0, DestroyFileInfo, "file info", a6);
    *(_QWORD *)(a1 + 168) = v15;
    if ( !v15 )
      return 0;
  }
  v16 = malloc(0x60u);
  if ( !v16 )
  {
    ErrSet(a6, "Out of memory %1", "%s", "tracking files");
    return 0;
  }
  v17 = _strdup(*(const char **)(a6 + 520));
  *((_QWORD *)v16 + 1) = v17;
  if ( !v17 )
  {
    ErrSet(a6, "Out of memory %1", "%s", "tracking files");
LABEL_17:
    free(v16);
    return 0;
  }
  result = GLAdd(*(_QWORD *)(a1 + 168), &pszFileName, v16, "file", v9, a6);
  if ( !result )
  {
    if ( *(_DWORD *)(a6 + 544) == 257 )
      ErrSet(
        a6,
        "Duplicate file name: %1 already defined at %2(%3)",
        "%s%s%d",
        &pszFileName,
        *(const char **)(*(_QWORD *)(*(_QWORD *)(a6 + 552) + 8LL) + 8LL),
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a6 + 552) + 8LL) + 16LL));
    free(*((void **)v16 + 1));
    goto LABEL_17;
  }
  v16[4] = *(_DWORD *)(a6 + 528);
  *v16 = a4;
  *(_QWORD *)(v16 + 5) = -1;
  v16[7] = *(_DWORD *)(a1 + 132);
  *((_QWORD *)v16 + 4) = 0;
  *((_WORD *)v16 + 20) = 0;
  *((_QWORD *)v16 + 7) = 0;
  *((_QWORD *)v16 + 6) = *(_QWORD *)(a5 + 4360);
  *((_QWORD *)v16 + 8) = 0;
  v16[18] = 0;
  *((_QWORD *)v16 + 10) = 0;
  *((_QWORD *)v16 + 11) = 0;
  *(_QWORD *)(a5 + 4360) = 0;
  return result;
}

```

## disassembly

```asm
0x140003d28  push    rbx
0x140003d2a  push    rbp
0x140003d2b  push    rsi
0x140003d2c  push    rdi
0x140003d2d  push    r14
0x140003d2f  push    r15
0x140003d31  sub     rsp, 38h
0x140003d35  mov     rdi, [rsp+68h+arg_28]
0x140003d3d  lea     rdx, aUniquefiles; "UniqueFiles"
0x140003d44  mov     rsi, rcx
0x140003d47  mov     r8, rdi
0x140003d4a  mov     rcx, [rcx+10h]
0x140003d4e  mov     r15d, r9d
0x140003d51  call    VarFind
0x140003d56  mov     rcx, [rax+8]; String
0x140003d5a  call    cs:__imp_atoi
0x140003d60  mov     r14, [rsp+68h+arg_20]
0x140003d68  mov     ebp, eax
0x140003d6a  mov     rbx, [r14+1108h]
0x140003d71  test    rbx, rbx
0x140003d74  jz      short loc_140003DAB
0x140003d76  mov     rcx, [rbx]
0x140003d79  lea     rdx, aUnique_0; "Unique"
0x140003d80  call    findItem
0x140003d85  test    rax, rax
0x140003d88  jz      short loc_140003D90
0x140003d8a  mov     rcx, [rax+8]
0x140003d8e  jmp     short loc_140003D94
0x140003d90  mov     rcx, [rbx+10h]
0x140003d94  test    rcx, rcx
0x140003d97  jz      short loc_140003DAB
0x140003d99  mov     rcx, [rcx]; String1
0x140003d9c  mov     rdx, rdi
0x140003d9f  call    BOOLfromPSZ
0x140003da4  mov     ebp, eax
0x140003da6  cmp     eax, 0FFFFFFFFh
0x140003da9  jz      short loc_140003DC7
0x140003dab  cmp     dword ptr [rsi+0C0h], 3
0x140003db2  jnz     short loc_140003DCE
0x140003db4  test    ebp, ebp
0x140003db6  jnz     short loc_140003DCE
0x140003db8  lea     rdx, aUniqueOffNotAl; "/unique=OFF not allowed for relational "...
0x140003dbf  mov     rcx, rdi
0x140003dc2  call    ErrSet
0x140003dc7  xor     eax, eax
0x140003dc9  jmp     loc_140003F53
0x140003dce  cmp     qword ptr [rsi+0A8h], 0
0x140003dd6  jnz     short loc_140003DFC
0x140003dd8  mov     r9, rdi
0x140003ddb  lea     r8, aFileInfo; "file info"
0x140003de2  lea     rdx, DestroyFileInfo
0x140003de9  xor     ecx, ecx
0x140003deb  call    GLCreateList
0x140003df0  mov     [rsi+0A8h], rax
0x140003df7  test    rax, rax
0x140003dfa  jz      short loc_140003DC7
0x140003dfc  mov     ecx, 60h ; '`'; Size
0x140003e01  call    cs:__imp_malloc
0x140003e07  mov     rbx, rax
0x140003e0a  test    rax, rax
0x140003e0d  jnz     short loc_140003E2E
0x140003e0f  lea     r9, aTrackingFiles; "tracking files"
0x140003e16  mov     rcx, rdi
0x140003e19  lea     r8, aS_4; "%s"
0x140003e20  lea     rdx, aOutOfMemory1; "Out of memory %1"
0x140003e27  call    ErrSet
0x140003e2c  jmp     short loc_140003DC7
0x140003e2e  mov     rcx, [rdi+208h]; Source
0x140003e35  call    cs:__imp__strdup
0x140003e3b  mov     [rbx+8], rax
0x140003e3f  test    rax, rax
0x140003e42  jnz     short loc_140003E6F
0x140003e44  lea     r9, aTrackingFiles; "tracking files"
0x140003e4b  mov     rcx, rdi
0x140003e4e  lea     r8, aS_4; "%s"
0x140003e55  lea     rdx, aOutOfMemory1; "Out of memory %1"
0x140003e5c  call    ErrSet
0x140003e61  mov     rcx, rbx; Block
0x140003e64  call    cs:__imp_free
0x140003e6a  jmp     loc_140003DC7
0x140003e6f  mov     rcx, [rsi+0A8h]
0x140003e76  lea     r9, aFile_1; "file"
0x140003e7d  mov     [rsp+68h+var_40], rdi
0x140003e82  lea     rdx, pszFileName
0x140003e89  mov     r8, rbx
0x140003e8c  mov     dword ptr [rsp+68h+var_48], ebp
0x140003e90  call    GLAdd
0x140003e95  mov     rcx, rax
0x140003e98  test    rax, rax
0x140003e9b  jnz     short loc_140003EF0
0x140003e9d  cmp     dword ptr [rdi+220h], 101h
0x140003ea7  jnz     short loc_140003EE1
0x140003ea9  mov     rax, [rdi+228h]
0x140003eb0  lea     r9, pszFileName
0x140003eb7  lea     r8, aSSD; "%s%s%d"
0x140003ebe  lea     rdx, aDuplicateFileN; "Duplicate file name: %1 already defined"...
0x140003ec5  mov     rcx, [rax+8]
0x140003ec9  mov     eax, [rcx+10h]
0x140003ecc  mov     dword ptr [rsp+68h+var_40], eax
0x140003ed0  mov     rax, [rcx+8]
0x140003ed4  mov     rcx, rdi
0x140003ed7  mov     [rsp+68h+var_48], rax
0x140003edc  call    ErrSet
0x140003ee1  mov     rcx, [rbx+8]; Block
0x140003ee5  call    cs:__imp_free
0x140003eeb  jmp     loc_140003E61
0x140003ef0  mov     eax, [rdi+210h]
0x140003ef6  mov     [rbx+10h], eax
0x140003ef9  mov     [rbx], r15d
0x140003efc  mov     qword ptr [rbx+14h], 0FFFFFFFFFFFFFFFFh
0x140003f04  mov     eax, [rsi+84h]
0x140003f0a  mov     [rbx+1Ch], eax
0x140003f0d  xor     eax, eax
0x140003f0f  mov     [rbx+20h], rax
0x140003f13  mov     [rbx+28h], ax
0x140003f17  mov     [rbx+38h], rax
0x140003f1b  mov     rax, [r14+1108h]
0x140003f22  mov     [rbx+30h], rax
0x140003f26  mov     rax, rcx
0x140003f29  mov     qword ptr [rbx+40h], 0
0x140003f31  mov     dword ptr [rbx+48h], 0
0x140003f38  mov     qword ptr [rbx+50h], 0
0x140003f40  mov     qword ptr [rbx+58h], 0
0x140003f48  mov     qword ptr [r14+1108h], 0
0x140003f53  add     rsp, 38h
0x140003f57  pop     r15
0x140003f59  pop     r14
0x140003f5b  pop     rdi
0x140003f5c  pop     rsi
0x140003f5d  pop     rbp
0x140003f5e  pop     rbx
0x140003f5f  retn
```
