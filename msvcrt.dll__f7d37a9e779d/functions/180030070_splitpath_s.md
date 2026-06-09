# _splitpath_s

- ea: `0x180030070`
- end: `0x18003032d`
- name: `_splitpath_s`
- size: `701`
- prototype: `errno_t __cdecl(const char *FullPath, char *Drive, size_t DriveCount, char *Dir, size_t DirCount, char *Filename, size_t FilenameCount, char *Ext, size_t ExtCount)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180007f00`
- `0x180024ad0`
- `0x18002f050`
- `0x180030070`
- `0x180060fd0`

## pseudocode

```c
errno_t __cdecl splitpath_s(
        const char *FullPath,
        char *Drive,
        size_t DriveCount,
        char *Dir,
        size_t DirCount,
        char *Filename,
        size_t FilenameCount,
        char *Ext,
        size_t ExtCount)
{
  size_t v11; // r10
  const char *v12; // rdi
  int v13; // ecx
  __int64 v14; // rax
  const char *v15; // rbx
  char v16; // al
  const char *v17; // rsi
  const char *v18; // rbx
  const char *v19; // rbp
  int v20; // eax
  rsize_t v21; // rbx
  rsize_t v22; // rbx

  v11 = DriveCount;
  v12 = FullPath;
  if ( !FullPath )
    goto LABEL_4;
  if ( Drive )
  {
    if ( !DriveCount )
      goto LABEL_4;
  }
  else if ( DriveCount )
  {
LABEL_4:
    v13 = 1;
    goto LABEL_62;
  }
  if ( Dir )
  {
    if ( !DirCount )
      goto LABEL_4;
  }
  else if ( DirCount )
  {
    goto LABEL_4;
  }
  if ( Filename )
  {
    if ( !FilenameCount )
      goto LABEL_4;
  }
  else if ( FilenameCount )
  {
    goto LABEL_4;
  }
  if ( Ext )
  {
    if ( !ExtCount )
      goto LABEL_4;
  }
  else if ( ExtCount )
  {
    goto LABEL_4;
  }
  v13 = 0;
  v14 = 1;
  v15 = v12;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v14;
  }
  while ( v14 );
  if ( *v15 == 58 )
  {
    if ( Drive )
    {
      if ( DriveCount < 3 )
        goto LABEL_63;
      strncpy_s(Drive, DriveCount, v12, 2u);
    }
    v12 = v15 + 1;
  }
  else if ( Drive )
  {
    *Drive = 0;
  }
  v16 = *v12;
  v17 = 0;
  v18 = v12;
  if ( !*v12 )
    goto LABEL_43;
  v19 = 0;
  do
  {
    if ( ismbblead(v16) )
    {
      ++v18;
    }
    else
    {
      v20 = *(unsigned __int8 *)v18;
      if ( *v18 == 47 || (_BYTE)v20 == 92 )
      {
        v19 = v18 + 1;
      }
      else if ( (_BYTE)v20 == 46 )
      {
        v17 = v18;
      }
    }
    v16 = *++v18;
  }
  while ( *v18 );
  if ( v19 )
  {
    if ( Dir )
    {
      if ( DirCount <= v19 - v12 )
      {
        v13 = 0;
        goto LABEL_61;
      }
      strncpy_s(Dir, DirCount, v12, v19 - v12);
    }
    v12 = v19;
  }
  else
  {
LABEL_43:
    if ( Dir )
      *Dir = 0;
  }
  if ( !v17 || v17 < v12 )
  {
    if ( Filename )
    {
      v22 = v18 - v12;
      if ( FilenameCount <= v22 )
        goto LABEL_59;
      strncpy_s(Filename, FilenameCount, v12, v22);
    }
    if ( Ext )
      *Ext = 0;
    return 0;
  }
  if ( !Filename )
  {
LABEL_50:
    if ( !Ext )
      return 0;
    v21 = v18 - v17;
    if ( ExtCount > v21 )
    {
      strncpy_s(Ext, ExtCount, v17, v21);
      return 0;
    }
    goto LABEL_59;
  }
  if ( FilenameCount > v17 - v12 )
  {
    strncpy_s(Filename, FilenameCount, v12, v17 - v12);
    goto LABEL_50;
  }
LABEL_59:
  v13 = 0;
LABEL_61:
  v11 = DriveCount;
LABEL_62:
  if ( Drive )
  {
LABEL_63:
    if ( v11 )
      *Drive = 0;
  }
  if ( Dir && DirCount )
    *Dir = 0;
  if ( Filename && FilenameCount )
    *Filename = 0;
  if ( Ext && ExtCount )
    *Ext = 0;
  if ( !v12 || v13 )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  *errno() = 34;
  return 34;
}

```

## disassembly

```asm
0x180030070  mov     [rsp+arg_8], rbx
0x180030075  mov     [rsp+arg_10], r8
0x18003007a  push    rbp
0x18003007b  push    rsi
0x18003007c  push    rdi
0x18003007d  push    r12
0x18003007f  push    r13
0x180030081  push    r14
0x180030083  push    r15
0x180030085  sub     rsp, 30h
0x180030089  mov     r14, [rsp+68h+Ext]
0x180030091  mov     r12, rdx
0x180030094  mov     r15, [rsp+68h+Filename]
0x18003009c  xor     edx, edx
0x18003009e  mov     r13, r9
0x1800300a1  mov     r10, r8
0x1800300a4  mov     rdi, rcx
0x1800300a7  test    rcx, rcx
0x1800300aa  jz      short loc_1800300B6
0x1800300ac  test    r12, r12
0x1800300af  jnz     short loc_1800300C0
0x1800300b1  test    r8, r8
0x1800300b4  jz      short loc_1800300C5
0x1800300b6  mov     ecx, 1
0x1800300bb  jmp     loc_180030294
0x1800300c0  test    r10, r10
0x1800300c3  jz      short loc_1800300B6
0x1800300c5  test    r13, r13
0x1800300c8  jnz     short loc_1800300D6
0x1800300ca  cmp     [rsp+68h+DirCount], rdx
0x1800300d2  jnz     short loc_1800300B6
0x1800300d4  jmp     short loc_1800300E0
0x1800300d6  cmp     [rsp+68h+DirCount], rdx
0x1800300de  jz      short loc_1800300B6
0x1800300e0  test    r15, r15
0x1800300e3  jnz     short loc_1800300F1
0x1800300e5  cmp     [rsp+68h+FilenameCount], rdx
0x1800300ed  jnz     short loc_1800300B6
0x1800300ef  jmp     short loc_1800300FB
0x1800300f1  cmp     [rsp+68h+FilenameCount], rdx
0x1800300f9  jz      short loc_1800300B6
0x1800300fb  test    r14, r14
0x1800300fe  jnz     short loc_18003010C
0x180030100  cmp     [rsp+68h+ExtCount], rdx
0x180030108  jnz     short loc_1800300B6
0x18003010a  jmp     short loc_180030116
0x18003010c  cmp     [rsp+68h+ExtCount], rdx
0x180030114  jz      short loc_1800300B6
0x180030116  mov     ecx, edx
0x180030118  mov     [rsp+68h+arg_0], edx
0x18003011c  mov     eax, 1
0x180030121  mov     rbx, rdi
0x180030124  cmp     [rbx], dl
0x180030126  jz      short loc_180030131
0x180030128  inc     rbx
0x18003012b  sub     rax, 1
0x18003012f  jnz     short loc_180030124
0x180030131  cmp     byte ptr [rbx], 3Ah ; ':'
0x180030134  jnz     short loc_180030161
0x180030136  test    r12, r12
0x180030139  jz      short loc_18003015B
0x18003013b  cmp     r10, 3
0x18003013f  jb      loc_180030299
0x180030145  mov     r9d, 2; MaxCount
0x18003014b  mov     r8, rdi; Source
0x18003014e  mov     rdx, r10; SizeInBytes
0x180030151  mov     rcx, r12; Destination
0x180030154  call    strncpy_s
0x180030159  xor     edx, edx
0x18003015b  lea     rdi, [rbx+1]
0x18003015f  jmp     short loc_18003016A
0x180030161  test    r12, r12
0x180030164  jz      short loc_18003016A
0x180030166  mov     [r12], dl
0x18003016a  mov     al, [rdi]
0x18003016c  mov     rsi, rdx
0x18003016f  mov     rbx, rdi
0x180030172  test    al, al
0x180030174  jz      short loc_1800301E4
0x180030176  mov     rbp, rdx
0x180030179  movsx   ecx, al; Ch
0x18003017c  call    _ismbblead
0x180030181  xor     edx, edx
0x180030183  test    eax, eax
0x180030185  jz      short loc_18003018C
0x180030187  inc     rbx
0x18003018a  jmp     short loc_1800301A3
0x18003018c  mov     al, [rbx]
0x18003018e  cmp     al, 2Fh ; '/'
0x180030190  jz      short loc_18003019F
0x180030192  cmp     al, 5Ch ; '\'
0x180030194  jz      short loc_18003019F
0x180030196  cmp     al, 2Eh ; '.'
0x180030198  jnz     short loc_1800301A3
0x18003019a  mov     rsi, rbx
0x18003019d  jmp     short loc_1800301A3
0x18003019f  lea     rbp, [rbx+1]
0x1800301a3  inc     rbx
0x1800301a6  mov     al, [rbx]
0x1800301a8  test    al, al
0x1800301aa  jnz     short loc_180030179
0x1800301ac  test    rbp, rbp
0x1800301af  jz      short loc_1800301E4
0x1800301b1  test    r13, r13
0x1800301b4  jz      short loc_1800301DF
0x1800301b6  mov     r9, rbp
0x1800301b9  sub     r9, rdi; MaxCount
0x1800301bc  cmp     [rsp+68h+DirCount], r9
0x1800301c4  jbe     loc_18003028A
0x1800301ca  mov     rdx, [rsp+68h+DirCount]; SizeInBytes
0x1800301d2  mov     r8, rdi; Source
0x1800301d5  mov     rcx, r13; Destination
0x1800301d8  call    strncpy_s
0x1800301dd  xor     edx, edx
0x1800301df  mov     rdi, rbp
0x1800301e2  jmp     short loc_1800301ED
0x1800301e4  test    r13, r13
0x1800301e7  jz      short loc_1800301ED
0x1800301e9  mov     [r13+0], dl
0x1800301ed  test    rsi, rsi
0x1800301f0  jz      short loc_18003024B
0x1800301f2  cmp     rsi, rdi
0x1800301f5  jb      short loc_18003024B
0x1800301f7  test    r15, r15
0x1800301fa  jz      short loc_180030221
0x1800301fc  mov     r9, rsi
0x1800301ff  sub     r9, rdi; MaxCount
0x180030202  cmp     [rsp+68h+FilenameCount], r9
0x18003020a  jbe     short loc_180030284
0x18003020c  mov     rdx, [rsp+68h+FilenameCount]; SizeInBytes
0x180030214  mov     r8, rdi; Source
0x180030217  mov     rcx, r15; Destination
0x18003021a  call    strncpy_s
0x18003021f  xor     edx, edx
0x180030221  test    r14, r14
0x180030224  jz      short loc_18003027D
0x180030226  sub     rbx, rsi
0x180030229  cmp     [rsp+68h+ExtCount], rbx
0x180030231  jbe     short loc_180030284
0x180030233  mov     rdx, [rsp+68h+ExtCount]; SizeInBytes
0x18003023b  mov     r9, rbx; MaxCount
0x18003023e  mov     r8, rsi; Source
0x180030241  mov     rcx, r14; Destination
0x180030244  call    strncpy_s
0x180030249  jmp     short loc_18003027D
0x18003024b  test    r15, r15
0x18003024e  jz      short loc_180030275
0x180030250  sub     rbx, rdi
0x180030253  cmp     [rsp+68h+FilenameCount], rbx
0x18003025b  jbe     short loc_180030284
0x18003025d  mov     rdx, [rsp+68h+FilenameCount]; SizeInBytes
0x180030265  mov     r9, rbx; MaxCount
0x180030268  mov     r8, rdi; Source
0x18003026b  mov     rcx, r15; Destination
0x18003026e  call    strncpy_s
0x180030273  xor     edx, edx
0x180030275  test    r14, r14
0x180030278  jz      short loc_18003027D
0x18003027a  mov     [r14], dl
0x18003027d  xor     eax, eax
0x18003027f  jmp     loc_180030318
0x180030284  mov     ecx, [rsp+68h+arg_0]
0x180030288  jmp     short loc_18003028C
0x18003028a  mov     ecx, edx
0x18003028c  mov     r10, [rsp+68h+arg_10]
0x180030294  test    r12, r12
0x180030297  jz      short loc_1800302A2
0x180030299  test    r10, r10
0x18003029c  jz      short loc_1800302A2
0x18003029e  mov     [r12], dl
0x1800302a2  test    r13, r13
0x1800302a5  jz      short loc_1800302B5
0x1800302a7  cmp     [rsp+68h+DirCount], rdx
0x1800302af  jbe     short loc_1800302B5
0x1800302b1  mov     [r13+0], dl
0x1800302b5  test    r15, r15
0x1800302b8  jz      short loc_1800302C7
0x1800302ba  cmp     [rsp+68h+FilenameCount], rdx
0x1800302c2  jbe     short loc_1800302C7
0x1800302c4  mov     [r15], dl
0x1800302c7  test    r14, r14
0x1800302ca  jz      short loc_1800302D9
0x1800302cc  cmp     [rsp+68h+ExtCount], rdx
0x1800302d4  jbe     short loc_1800302D9
0x1800302d6  mov     [r14], dl
0x1800302d9  test    rdi, rdi
0x1800302dc  jnz     short loc_180030306
0x1800302de  call    _errno
0x1800302e3  mov     ebx, 16h
0x1800302e8  mov     [rsp+68h+Reserved], 0; Reserved
0x1800302f1  xor     r9d, r9d; LineNo
0x1800302f4  xor     r8d, r8d; FileName
0x1800302f7  xor     edx, edx; FunctionName
0x1800302f9  xor     ecx, ecx; Expression
0x1800302fb  mov     [rax], ebx
0x1800302fd  call    _invalid_parameter
0x180030302  mov     eax, ebx
0x180030304  jmp     short loc_180030318
0x180030306  test    ecx, ecx
0x180030308  jnz     short loc_1800302DE
0x18003030a  call    _errno
0x18003030f  mov     ecx, 22h ; '"'
0x180030314  mov     [rax], ecx
0x180030316  mov     eax, ecx
0x180030318  mov     rbx, [rsp+68h+arg_8]
0x18003031d  add     rsp, 30h
0x180030321  pop     r15
0x180030323  pop     r14
0x180030325  pop     r13
0x180030327  pop     r12
0x180030329  pop     rdi
0x18003032a  pop     rsi
0x18003032b  pop     rbp
0x18003032c  retn
```
